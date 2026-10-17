
## Recurrent Neural Network

- RNN for character generation:

### Example: Character-level Language Model Sampling

#### Vocabulary: [h,e,l,o]

At test-time sample characters one at a time, feed back to model

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1321_0.png)

- RNN for character generation:

### Example: Character-level Language Model Sampling

Vocabulary:
[h,e,l,o]

At test-time sample characters one at a time, feed back to model

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1322_0.png)

- RNN for character generation:

### Example: Character-level Language Model Sampling

#### Vocabulary: [h,e,l,o]

At test-time sample characters one at a time, feed back to model

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1323_0.png)

- RNN for character generation:

### Example: Character-level Language Model Sampling

Vocabulary:
[h,e,l,o]

At test-time sample characters one at a time, feed back to model

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1324_0.png)

- How to compute loss:

### Backpropagation through time

Forward through entire sequence to compute loss, then backward through entire sequence to compute gradient

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1325_0.png)

- How to compute loss:

### Truncated Backpropagation through time

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1326_0.png)

Run forward and backward through chunks of the sequence instead of whole sequence

- How to compute loss:

### Truncated Backpropagation through time

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1327_0.png)

Carry hidden states forward in time forever, but only backpropagate for some smaller number of steps

## Application of RNN

### Image Captioning

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1329_0.png)

Explain Images with Multimodal Recurrent Neural Networks, Mao et al.
Deep Visual-Semantic Alignments for Generating Image Descriptions, Karpathy and Fei-Fei
Show and Tell: A Neural Image Caption Generator, Vinyals et al.
Long-term Recurrent Convolutional Networks for Visual Recognition and Description, Donahue et al.
Learning a Recurrent Visual Representation for Image Caption Generation, Chen and Zitnick

### Application of RNN

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1331_0.png)

test image

### Application of RNN

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1332_0.png)

- image
- conv-64
- conv-64
- maxpool
- conv-128
- conv-128
- maxpool
- conv-256
- conv-256
- maxpool
- conv-512
- conv-512
- maxpool
- conv-512
- conv-512
- maxpool
- FC-4096
- FC-4096
- FC-1000
- softmax

### Application of RNN

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1333_0.png)

test image

- image
- conv-64
- conv-64
- maxpool
- conv-128
- conv-128
- maxpool
- conv-256
- conv-256
- maxpool
- conv-512
- conv-512
- maxpool
- conv-512
- conv-512
- maxpool
- FC-4096
- FC-4096
- FC-1000
- softmax

### Application of RNN

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1334_0.png)

- image
- conv-64
- conv-64
- maxpool
- conv-128
- conv-128
- maxpool
- conv-256
- conv-256
- maxpool
- conv-512
- conv-512
- maxpool
- conv-512
- conv-512
- maxpool
- FC-4096
- FC-4096

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1334_1.png)

### Application of RNN

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1335_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1335_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1335_2.png)

**before:**

$h = \tanh(W_{xh} * x + W_{hh} * h)$

**now:**

$h = \tanh(W_{xh} * x + W_{hh} * h + W_{ih} * V)$
