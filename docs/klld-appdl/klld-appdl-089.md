# 89：L41.1- 视频中的动作识别 🎬

在本节课中，我们将要学习如何处理视频数据，并理解视频动作识别任务。视频可以看作是一系列在时间上连续的图像帧，因此它本质上是一种具有时空结构的数据。

上一节我们介绍了视频数据的基本概念，本节中我们来看看视频数据的两个重要基准数据集。

![](img/bef70c02dbede9baf4af1548d68b0a03_1.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_2.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_3.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_4.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_5.png)

## 视频数据的结构与特点

![](img/bef70c02dbede9baf4af1548d68b0a03_6.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_7.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_8.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_9.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_10.png)

视频数据可以被视为多个在时间上连续的帧。它仍然是结构化数据，具有二维网格结构，并且这个二维网格会随时间演变。因此，我们需要处理的是**三维**数据（高度、宽度、时间），而不仅仅是二维。

![](img/bef70c02dbede9baf4af1548d68b0a03_11.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_12.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_13.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_14.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_15.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_16.png)

关于视频，一个重要的观察是：我们可以很自然地将视频分解为**空间**和**时间**两个维度。

![](img/bef70c02dbede9baf4af1548d68b0a03_17.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_18.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_19.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_20.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_21.png)

## 动作识别基准数据集

![](img/bef70c02dbede9baf4af1548d68b0a03_22.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_23.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_24.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_25.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_26.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_27.png)

以下是两个用于视频动作识别的重要基准数据集。它们规模适中，非常适合进行探索性数据分析。

![](img/bef70c02dbede9baf4af1548d68b0a03_28.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_29.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_30.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_31.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_32.png)

*   **UCF101**： 数据集来源于YouTube视频，包含**101**个动作类别。
*   **HMDB51**： 包含**51**个动作类别。

![](img/bef70c02dbede9baf4af1548d68b0a03_33.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_34.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_35.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_36.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_37.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_38.png)

---

![](img/bef70c02dbede9baf4af1548d68b0a03_39.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_40.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_41.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_42.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_43.png)

本节课中我们一起学习了视频数据的三维特性（空间+时间），并介绍了UCF101和HMDB51这两个用于动作识别任务的经典基准数据集。理解数据的结构是构建有效模型的第一步。