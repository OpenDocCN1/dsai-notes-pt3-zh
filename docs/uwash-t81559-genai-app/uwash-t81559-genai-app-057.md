# 057：文本转语音 🎤

![](img/1075bbc9390889ea9a6625473a5a851d_1.png)

![](img/1075bbc9390889ea9a6625473a5a851d_2.png)

在本节课中，我们将学习如何使用OpenAI的API将文本转换为语音。我们将介绍其基本用法、可用的声音选项，以及如何生成和保存语音文件。

![](img/1075bbc9390889ea9a6625473a5a851d_4.png)

上一节我们介绍了语音应用和OpenAI，本节中我们来看看文本转语音功能。相关代码链接已在描述中提供，现在让我们开始运行这部分代码。

![](img/1075bbc9390889ea9a6625473a5a851d_6.png)

![](img/1075bbc9390889ea9a6625473a5a851d_7.png)

## 环境设置与代码运行

![](img/1075bbc9390889ea9a6625473a5a851d_9.png)

首先，我将在Colab中打开并运行代码。请注意，此处使用的代码是专门针对OpenAI API的，并未使用LangChain，因为当前处理的是语音和文本。在后续构建聊天机器人时，我们会少量使用LangChain。

![](img/1075bbc9390889ea9a6625473a5a851d_11.png)

以下是安装必要库的步骤：

![](img/1075bbc9390889ea9a6625473a5a851d_12.png)

![](img/1075bbc9390889ea9a6625473a5a851d_14.png)

```python
# 安装必要的库
!pip install openai
```

虽然我们暂时用不到，但代码中包含了LangChain，因为这是我们之前课程中主要使用的工具，所以我会保留它。

## 文本转语音基础

![](img/1075bbc9390889ea9a6625473a5a851d_16.png)

文本转语音是指将文本内容渲染为语音的过程。在等待安装完成时，我们可以先了解一下相关概念。

![](img/1075bbc9390889ea9a6625473a5a851d_17.png)

OpenAI的文本转语音API提供了多种声音选择。其中，“alloy”是默认声音，是一种中性的音色，没有特别强烈的男性或女性特征。此外，API还提供了多种不同类型的男性和女性声音。

关于模型，有两种选择：`TTS-1` 和 `TTS-1-HD`。HD版本速度稍慢，但生成的语音质量更高。在实际聊天交互场景中，为了获得更快的响应速度，你可能会选择使用速度更快的 `TTS-1` 模型。

![](img/1075bbc9390889ea9a6625473a5a851d_19.png)

![](img/1075bbc9390889ea9a6625473a5a851d_20.png)

## 生成第一个语音

![](img/1075bbc9390889ea9a6625473a5a851d_22.png)

现在，让我们生成第一段语音。我们将指定使用 `TTS-1` 模型和 “alloy” 声音。

![](img/1075bbc9390889ea9a6625473a5a851d_23.png)

![](img/1075bbc9390889ea9a6625473a5a851d_24.png)

```python
from openai import OpenAI
client = OpenAI(api_key="你的API密钥")

response = client.audio.speech.create(
    model="tts-1",
    voice="alloy",
    input="Hello there. I am one of the OpenAI voices. How can I help you?"
)
```

![](img/1075bbc9390889ea9a6625473a5a851d_26.png)

![](img/1075bbc9390889ea9a6625473a5a851d_27.png)

![](img/1075bbc9390889ea9a6625473a5a851d_28.png)

执行以上代码后，语音数据便已生成。虽然它不会自动播放，但我们可以通过以下方式听到它：

![](img/1075bbc9390889ea9a6625473a5a851d_30.png)

> **播放的语音**：“Hello there. I am one of the OpenAI chat voices. How are you.”

![](img/1075bbc9390889ea9a6625473a5a851d_32.png)

这就是“alloy”声音的效果。你还可以将语音保存为文件，例如MP3格式，以便本地下载和播放，这个过程非常简单。

![](img/1075bbc9390889ea9a6625473a5a851d_34.png)

## 多声音示例

![](img/1075bbc9390889ea9a6625473a5a851d_36.png)

为了让你了解所有可用的声音，我们将循环遍历所有声音选项，并让每个声音说一句话。

![](img/1075bbc9390889ea9a6625473a5a851d_38.png)

以下是实现此功能的代码步骤：

![](img/1075bbc9390889ea9a6625473a5a851d_40.png)

1.  定义所有可用的声音列表。
2.  循环遍历每个声音，使用 `TTS-1` 模型生成对应的语音片段。
3.  使用 `pydub` 库将所有语音片段合并成一个音频文件。
4.  播放合并后的音频，以对比不同声音的效果。

![](img/1075bbc9390889ea9a6625473a5a851d_42.png)

运行代码后，你将听到类似以下内容的语音：

![](img/1075bbc9390889ea9a6625473a5a851d_44.png)

![](img/1075bbc9390889ea9a6625473a5a851d_45.png)

> **播放的语音**：“Hello, I am the alloy voice. Hello, I am the echo voice. Hello, I am the fable voice. Hello, I am the Onyx voice. Hello, I am the Nova voice. Hello, I am the shimmer voice.”

![](img/1075bbc9390889ea9a6625473a5a851d_47.png)

这样，你就听到了所有的声音。你可以选择最喜欢的一个。完成后，我们可以将合并的音频保存到文件，并下载它。

## 语音的情感与表达

![](img/1075bbc9390889ea9a6625473a5a851d_49.png)

![](img/1075bbc9390889ea9a6625473a5a851d_50.png)

![](img/1075bbc9390889ea9a6625473a5a851d_51.png)

文本转语音功能不仅限于平淡的朗读。API会尝试根据文本内容检测并添加一定的情感色彩，例如笑声或强调。虽然OpenAI的API目前可能不完全支持标准的语音标记语言（如SSML），但其他一些平台支持。我们可以通过输入带有情感暗示的文本来测试。

例如，输入以下文本：

```python
input_text = """
Oh my gosh. What the heck are you doing.
Oh, I am okay now. Actually kind of bored.
"""
```

生成的语音可能会带有相应的语气变化，而不像过去那种非常单调的电脑合成音。

## 总结

本节课中我们一起学习了OpenAI文本转语音API的基本应用。我们了解了如何设置环境、生成基础语音、探索不同的声音选项、合并多个语音片段，以及如何通过文本来引导语音的情感表达。整个过程相对简单直接，核心在于调用API并指定合适的参数（如模型和声音）。需要注意的是，所有这些处理都发生在云端，因此需要稳定的网络连接。

![](img/1075bbc9390889ea9a6625473a5a851d_53.png)

希望本教程对你有所帮助。如果你喜欢这个视频，请点赞和订阅。感谢观看！😊