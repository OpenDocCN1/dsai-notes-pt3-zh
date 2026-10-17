

## AlexNet

- Architecture of AlexNet:
  - 8 layers total
  - 18.2% top-5 error rate

- Remove upper feature extractor layers & two FC layers
  - Layer 3, 4, 6, 7
  - 33.5% drop in performance!
  - Depth of network is key

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1274_0.png)

- Plug features from each layer into linear SVM or soft-max:

| | Caltech-101 (30/class) | Caltech-256 (60/class) |
|---|---|---|
| SVM(1) | 44.8 ± 0.7 | 24.6 ± 0.4 |
| SVM(2) | 66.2 ± 0.5 | 39.6 ± 0.3 |
| SVM(3) | 72.3 ± 0.4 | 46.0 ± 0.3 |
| SVM(4) | 76.6 ± 0.4 | 51.3 ± 0.1 |
| SVM(5) | 86.2 ± 0.8 | 65.6 ± 0.3 |
| SVM(7) | 85.5 ± 0.4 | 71.7 ± 0.2 |
| Softmax(5) | 82.9 ± 0.4 | 65.7 ± 0.5 |
| Softmax(7) | 85.4 ± 0.4 | 72.6 ± 0.1 |

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1275_0.png)

## Training problem in Deep Net

- Generalization:
  - Add noise
  - Pre-training

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1276_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1276_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1276_2.png)

- Generalization:
  - Transfer learning

1. Train on Imagenet

2. Small dataset: feature extractor

3. Medium dataset: finetuning

more data = retrain more of the network (or all of it)

Freeze these

Freeze these

Train this

Train this

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1277_0.png)

## CNN for Classification

- ConvNet Architecture: AlexNet

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1279_0.png)

### Year 2010

NEC-UIUC

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1280_0.png)

[Lin CVPR 2011]

### Year 2012

SuperVision

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1280_1.png)

[Krizhevsky NIPS 2012]

### Year 2014

GoogLeNet

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1280_2.png)

[Szegedy arxiv 2014]

VGG

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1280_3.png)

[Simonyan arxiv 2014]

### Year 2015

MSRA

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1280_4.png)

# CNN for CV Tasks

# Computer Vision Tasks

# Semantic Segmentation

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1281_0.png)

GRASS, CAT, TREE, SKY

# Classification + Localization

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1281_1.png)

CAT

# Object Detection

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1281_2.png)

DOG, DOG, CAT

# Instance Segmentation

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1281_3.png)

DOG, DOG, CAT

No objects, just pixels

Single Object

Multiple Object

## CNN for Classification + Localization

# Classification + Localization

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1282_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1282_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1282_2.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1282_3.png)

GRASS, CAT, TREE, SKY

CAT

DOG, DOG, CAT

DOG, DOG, CAT

No objects, just pixels

Single Object

Multiple Object

## CNN for Classification + Localization

# Classification + Localization

Treat localization as a regression problem!

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1283_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1283_1.png)

Fully Connected: 4096 to 1000

Class Scores
Cat: 0.9
Dog: 0.05
Car: 0.01
...

Vector: 4096
Fully Connected: 4096 to 4

Box Coordinates
(x, y, w, h)

# CNN for Classification + Localization

# Classification + Localization

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1284_0.png)

Fully Connected: 4096 to 1000

Class Scores
Cat: 0.9
Dog: 0.05
Car: 0.01
...

Correct label:
Cat

Softmax Loss

Vector: 4096

Fully Connected: 4096 to 4

Box Coordinates
(x, y, w, h)

L2 Loss

Correct box:
(x’, y’, w’, h’)

Treat localization as a regression problem!

## CNN for Classification + Localization

# Classification + Localization

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1285_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1285_1.png)

Fully Connected: 4096 to 1000

Class Scores
Cat: 0.9
Dog: 0.05
Car: 0.01
...

Fully Connected: 4096 to 4

Box Coordinates
(x, y, w, h)

Correct label:
Cat

Softmax Loss

Correct box:
(x', y', w', h')

L2 Loss

Loss

Multitask Loss

Treat localization as a regression problem!

