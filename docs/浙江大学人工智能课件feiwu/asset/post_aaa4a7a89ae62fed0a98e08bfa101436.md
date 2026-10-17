

## Two breakthrough architectures in CNN

- Convolutional Neural Networks (ConvNet)
  - LeNet-5 by LeCun et al. 1989 ~ 1998
  - Feed-forward:
    - Convolve input
    - Non-linearity: RelU
    - Pooling
  - Good at MNIST/CIFAR-10/Traffic sign recognition
  - Less good at more complex datasets, e.g. Caltech-101/256

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_240_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_240_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_240_2.png)

## Two breakthrough architectures in CNN

- Convolutional Neural Networks (ConvNet)
  - AlexNet by Alex Krizhevsky et al. 2012
  - ILSVRC-2012 Image recognition top-1 and top-5 error rates of 37.5% and 17.0%

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_241_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_241_1.png)

## ImageNet and ILSVRC

- ImageNet Large Scale Visual Recognition Challenge (ILSVRC)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_242_0.png)

http://www.image-net.org/challenges/LSVRC/

## ImageNet and ILSVRC

### Computer Vision Tasks

#### Classification

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_243_0.png)

CAT

#### Classification + Localization

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_243_1.png)

CAT

#### Object Detection

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_243_2.png)

**CAT**, DOG, DUCK

#### Instance Segmentation

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_243_3.png)

**CAT**, DOG, DUCK

Single object

Multiple objects

## ImageNet and ILSVRC

- ILSVRC 2015
  - Two main competitions:
    - Object detection for 200 fully labeled categories.
    - Object localization for 1000 categories.
  - Two taster competitions (New):
    - Object detection from video for 30 fully labeled categories.
    - Scene classification for 401 categories. Joint with MIT Places team.
- ILSVRC 2016
  - Object localization for 1000 categories.
  - Object detection for 200 fully labeled categories.
  - Object detection from video for 30 fully labeled categories.
  - Scene classification for 365 scene categories (Joint with MIT Places team) on Places2 Database http://places2.csail.mit.edu.
  - Scene parsing (New) for 150 stuff and discrete object categories (Joint with MIT Places team).

## ImageNet and ILSVRC

- Localization and detection

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_246_0.png)

Kaiming He, Xiangyu Zhang, Shaoqing Ren, & Jian Sun. “Deep Residual Learning for Image Recognition”. arXiv 2015.
Shaoqing Ren, Kaiming He, Ross Girshick, & Jian Sun. “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”. NIPS 2015.

## ImageNet and ILSVRC

- Instance Segmentation

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_247_0.png)

Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun. “Deep Residual Learning for Image Recognition.” arXiv 2015. Jifeng Dai, Kaiming He, and Jian Sun. “Instance-aware Semantic Segmentation via Multi-task Network Cascades.” arXiv 2015.

## ImageNet and ILSVRC

- Instance Segmentation

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_248_0.png)

## ImageNet and ILSVRC

### Year 2010

### Year 2012

### Year 2014

### Year 2015

NEC-UIUC

SuperVision

GoogLeNet

VGG

MSRA

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_249_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_249_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_249_2.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_249_3.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_249_4.png)

- Dense grid descriptor: HOG, LBP
- Coding: local coordinate, super-vector
- Pooling, SPM
- Linear SVM

- Convolution
- Pooling
- Softmax
- Other

> [Lin CVPR 2011]

> [Krizhevsky NIPS 2012]

> [Szegedy arxiv 2014]

> [Simonyan arxiv 2014]

## ImageNet Classification (2010-2015)

ImageNet Classification top-5 error (%)

2016, Trimps-Soushen, 2.991

- 152 layers
- 22 layers
- 19 layers
- 8 layers
- 8 layers
- shallow

| Model | Error (%) |
|---|---|
| ILSVRC'15 ResNet | 3.57 |
| ILSVRC'14 GoogleNet | 6.7 |
| ILSVRC'14 VGG | 7.3 |
| ILSVRC'13 | 11.7 |
| ILSVRC'12 AlexNet | 16.4 |
| ILSVRC'11 | 25.8 |
| ILSVRC'10 | 28.2 |

