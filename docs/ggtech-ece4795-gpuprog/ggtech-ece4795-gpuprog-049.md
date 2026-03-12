# 049：自定义可编程渲染管线中的阴影

![](img/8b26138cc9a09f3c8b547806a43322e0_1.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_3.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_4.png)

## 概述
在本节课中，我们将学习如何在自定义的可编程渲染管线中实现阴影映射技术。我们将基于之前课程中构建的前向渲染管线进行扩展，添加对方向光源阴影的支持。核心内容包括理解阴影映射的基本原理、编写支持阴影的着色器，以及在C#脚本中管理阴影贴图的渲染流程。

![](img/8b26138cc9a09f3c8b547806a43322e0_6.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_8.png)

## 阴影映射原理简介
上一节我们介绍了前向渲染管线的基本结构，本节中我们来看看如何为其添加阴影。

阴影映射是现代游戏引擎中处理阴影的主流技术。其基本工作原理分为两步：
1.  从光源的视角渲染整个场景，但只记录深度信息（即每个像素距离光源的远近），生成一张**深度贴图**（Shadow Map）。
2.  从摄像机视角正常渲染场景时，对于每个需要着色的像素点，计算其到光源的距离，并与深度贴图中存储的对应深度值进行比较。如果该点的距离大于深度贴图中的值，则说明该点被其他物体遮挡，处于阴影中。

对于方向光，我们使用正交投影来模拟从无限远处平行照射的光源视角。

![](img/8b26138cc9a09f3c8b547806a43322e0_10.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_11.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_12.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_14.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_15.png)

## 着色器代码解析
以下是实现阴影的核心着色器代码部分，包含两个渲染通道（Pass）。

### 主渲染通道（计算最终颜色）
这个通道负责计算最终呈现在屏幕上的像素颜色，并加入阴影判断。

```hlsl
// 定义从世界空间转换到光源裁剪空间的矩阵
float4x4 _WorldToShadow;

// 声明阴影贴图及专用的深度比较采样器
TEXTURE2D_SHADOW(_ShadowMap);
SAMPLER_CMP(sampler_ShadowMap);

// 在片段着色器中计算阴影衰减因子
float3 shadowCoord = mul(_WorldToShadow, float4(i.worldPos, 1.0)).xyz;
// 对透视投影（如点光源/聚光灯）需要进行透视除法，方向光可省略
// shadowCoord.xyz /= shadowCoord.w;

// 使用深度比较采样器查询阴影贴图
float shadowAttenuation = SAMPLE_TEXTURE2D_SHADOW(_ShadowMap, sampler_ShadowMap, shadowCoord.xyz);

![](img/8b26138cc9a09f3c8b547806a43322e0_17.png)

// 将阴影衰减因子应用于最终颜色计算
float3 finalColor = (diffuseLight * _Color.rgb) * shadowAttenuation;
```
**代码解释**：
*   `_WorldToShadow` 矩阵将顶点从世界空间变换到光源的裁剪空间。
*   `SAMPLE_TEXTURE2D_SHADOW` 是特殊的宏，它使用 `shadowCoord.xy` 查询纹理，并将查询到的深度值与 `shadowCoord.z` 进行比较。如果纹理中的深度值更小（即物体更近），则返回1（受光），否则返回0（阴影）。
*   最终颜色乘以 `shadowAttenuation`，阴影区域颜色被衰减为黑色。

### 阴影投射通道（生成深度贴图）
这个通道专门用于从光源视角渲染场景，生成深度贴图。

![](img/8b26138cc9a09f3c8b547806a43322e0_19.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_21.png)

```hlsl
// 使用特定的LightMode标签，标识此通道用于渲染阴影
#pragma vertex vert
#pragma fragment frag
#pragma multi_compile _ _SHADOWS_DEPTH

![](img/8b26138cc9a09f3c8b547806a43322e0_23.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_24.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_26.png)

// 顶点着色器：将顶点位置转换到光源裁剪空间，并应用阴影偏移（Bias）
Varyings vert(Attributes input)
{
    Varyings output;
    VertexPositionInputs vertexInput = GetVertexPositionInputs(input.positionOS.xyz);
    output.positionCS = mul(_WorldToShadow, float4(vertexInput.positionWS, 1.0));
    // 应用Z偏移，防止阴影痤疮（Shadow Acne）
    output.positionCS.z += _ShadowBias;
    return output;
}

![](img/8b26138cc9a09f3c8b547806a43322e0_28.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_30.png)

// 片段着色器：无需输出颜色，只需保证深度值写入深度缓冲区
half4 frag(Varyings input) : SV_Target
{
    return 0;
}
```
**代码解释**：
*   此通道的 `LightMode` 被设置为 `ShadowCaster`，管线会调用它来渲染深度。
*   顶点着色器主要进行坐标变换。添加 `_ShadowBias` 是一个小技巧，用于解决由于深度精度问题导致的“阴影痤疮”（表面自阴影产生的条纹）。
*   片段着色器返回0即可，因为此通道只关心深度缓冲区的写入。

![](img/8b26138cc9a09f3c8b547806a43322e0_32.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_33.png)

## C#渲染管线脚本解析
接下来，我们分析在C#脚本中如何组织和管理阴影渲染的流程。

![](img/8b26138cc9a09f3c8b547806a43322e0_35.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_36.png)

### 初始化与资源管理
脚本开始部分定义了渲染阴影所需的资源。

```csharp
// 声明阴影贴图渲染纹理
private RenderTexture shadowMapTexture;
// 定义着色器属性标识符，用于高效传递数据
private static int shadowMapTextureId = Shader.PropertyToID("_ShadowMap");
private static int worldToShadowMatrixId = Shader.PropertyToID("_WorldToShadow");
private static int shadowBiasId = Shader.PropertyToID("_ShadowBias");

![](img/8b26138cc9a09f3c8b547806a43322e0_38.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_39.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_40.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_41.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_43.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_45.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_46.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_47.png)

// 在渲染开始时创建阴影贴图
shadowMapTexture = new RenderTexture(1024, 1024, 16, RenderTextureFormat.Shadowmap);
shadowMapTexture.filterMode = FilterMode.Bilinear;
shadowMapTexture.wrapMode = TextureWrapMode.Clamp;
CommandBuffer.SetGlobalTexture(shadowMapTextureId, shadowMapTexture);
```
**代码解释**：
*   创建一张1024x1024、16位深度的 `RenderTexture`，格式设为 `Shadowmap`，专门用于存储深度信息。
*   使用 `Shader.PropertyToID` 获取属性名称对应的整数ID，提升设置着色器属性的效率。
*   通过 `CommandBuffer.SetGlobalTexture` 将创建好的阴影贴图传递给所有着色器。

![](img/8b26138cc9a09f3c8b547806a43322e0_49.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_51.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_52.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_53.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_55.png)

### 渲染流程控制
主要的渲染函数控制着阴影贴图生成和主场景绘制的顺序。

以下是渲染一帧的关键步骤列表：
1.  **渲染阴影贴图**：调用 `RenderShadows` 方法，将命令加入 `shadowBuffer`。
2.  **设置主摄像机**：配置主摄像机的渲染目标和清空状态。
3.  **绘制不透明物体**：使用主着色器通道（包含阴影计算）绘制场景。
4.  **清理资源**：在管线销毁时，手动释放 `RenderTexture` 占用的GPU内存。

### 阴影贴图渲染函数
`RenderShadows` 函数负责具体配置并从光源视角渲染深度。

```csharp
private void RenderShadows(ScriptableRenderContext context, ref CullingResults cullingResults)
{
    // 1. 获取光源的视图和投影矩阵（此处硬编码处理第0个方向光）
    Matrix4x4 viewMatrix, projMatrix;
    ShadowSplitData splitData;
    bool success = cullingResults.ComputeDirectionalShadowMatricesAndCullingPrimitives(
        0, 0, 1, new Vector3(0, 0, 0), 1024, 
        light.shadowNearPlane, out projMatrix, out viewMatrix, out splitData);

    // 2. 设置渲染状态，以阴影贴图为目标，仅清空深度
    CommandBuffer shadowBuffer = new CommandBuffer { name = "Shadow Buffer" };
    CoreUtils.SetRenderTarget(shadowBuffer, shadowMapTexture, 
        RenderBufferLoadAction.DontCare, RenderBufferStoreAction.Store, 
        ClearFlag.Depth, Color.clear);

    // 3. 执行命令，设置视图投影矩阵和阴影偏移量
    shadowBuffer.SetViewProjectionMatrices(viewMatrix, projMatrix);
    shadowBuffer.SetGlobalFloat(shadowBiasId, light.shadowBias);
    context.ExecuteCommandBuffer(shadowBuffer);
    shadowBuffer.Clear();

    // 4. 绘制阴影投射物体
    var shadowSettings = new DrawingSettings(shaderTagId, new SortingSettings(camera));
    var shadowFilterSettings = new FilteringSettings(RenderQueueRange.opaque);
    context.DrawRenderers(cullingResults, ref shadowSettings, ref shadowFilterSettings);

    // 5. 计算并传递世界到阴影矩阵到着色器
    Matrix4x4 scaleOffsetMatrix = Matrix4x4.identity;
    scaleOffsetMatrix.m00 = scaleOffsetMatrix.m11 = scaleOffsetMatrix.m22 = 0.5f;
    scaleOffsetMatrix.m03 = scaleOffsetMatrix.m13 = scaleOffsetMatrix.m23 = 0.5f;
    // 处理平台相关的Z反转
    if (SystemInfo.usesReversedZBuffer) 
    {
        scaleOffsetMatrix.m22 = -0.5f;
        scaleOffsetMatrix.m23 = 0.5f;
    }
    Matrix4x4 worldToShadowMatrix = scaleOffsetMatrix * (projMatrix * viewMatrix);
    CommandBuffer.SetGlobalMatrix(worldToShadowMatrixId, worldToShadowMatrix);
}
```
**代码解释**：
*   `ComputeDirectionalShadowMatricesAndCullingPrimitives` 是Unity SRP API，用于计算从指定方向光视角渲染所需的矩阵和裁剪信息。
*   `SetRenderTarget` 将 `shadowMapTexture` 设置为当前渲染目标，并指定加载/存储操作。`DontCare` 表示不加载现有内容，可提升Tile-Based GPU的性能。
*   绘制设置 (`DrawingSettings`) 使用了特定的 `ShaderTagId`（如 `ShadowCaster`），确保只有标记了对应LightMode的着色器通道（即我们写的第二个Pass）会被调用。
*   最后计算的 `worldToShadowMatrix` 结合了视图投影矩阵和一个**缩放偏移矩阵**。因为裁剪空间坐标范围是[-1, 1]，而纹理采样坐标需要[0, 1]，这个矩阵就是用来进行这个转换。同时，它还处理了不同图形API（如DirectX和OpenGL）在深度缓冲区Z方向上的差异。

## 总结
本节课中我们一起学习了在自定义可编程渲染管线中实现阴影映射的完整流程。

我们首先回顾了阴影映射的基本原理：从光源视角生成深度贴图，然后在主渲染中通过比较深度值来决定阴影。接着，我们深入分析了实现该技术所需的两个着色器通道：一个用于生成深度贴图，另一个则在计算最终颜色时采样深度贴图并应用阴影衰减。最后，我们解读了C#端的管线脚本，了解了如何管理阴影贴图资源、控制渲染顺序、计算必要的变换矩阵，并将所有数据正确地传递给GPU。

![](img/8b26138cc9a09f3c8b547806a43322e0_57.png)

通过本课的学习，你掌握了在Unity SRP框架下为方向光添加动态阴影的核心技能，这是构建高质量实时渲染效果的重要一步。