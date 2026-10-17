

## Application of RNN

### Image Captioning with Attention

Distribution over L locations

Distribution over vocab

Weighted features: D

Weighted combination of features

First word

Xu et al. "Show, Attend and Tell: Neural Image Caption Generation with Visual Attention", ICML 2015

Xu et al. “Show, Attend, and Tell: Neural Image Caption Generation with Visual Attention”, ICML 2015
Figure copyright Kelvin Xu, Jimmy Lei Ba, Jamie Kiros, Kyunghyun Cho, Aaron Courville, Ruslan Salakhutdinov, Richard S. Zemel, and Yoshua Bengio, 2015. Reproduced with permission.

A woman is throwing a frisbee in a park.

A dog is standing on a hardwood floor.

A stop sign is on a road with a mountain in the background.

A little girl sitting on a bed with a teddy bear.

A group of people sitting on a boat in the water.

A giraffe standing in a forest with trees in the background.

Xu et al., “Show, Attend, and Tell: Neural Image Caption Generation with Visual Attention,” ICML 2015.

Figure copyright: Kevin Xu, Jimmy Lei Bai, Jiang Wang, Kaiyan Xie, Yunjing Chen, Andrej Karpathy, Richard Socher, Li Fei-Fei, and Yoshua Bengio; 2015. Reproduced with permission.

## Application of RNN

### Visual Question Answering

Q: What endangered animal is featured on the truck?
A: A bald eagle.
A: A sparrow.
A: A humming bird.
A: A raven.

Q: Where will the driver go if turning right?
A: Onto 24 % Rd.
A: Onto 25 % Rd.
A: Onto 23 % Rd.
A: Onto Main Street.

Q: When was the picture taken?
A: During a wedding.
A: During a bar mitzah.
A: During a funeral.
A: During a Sunday church service

Q: Who is under the umbrella?
A: Two women.
A: A child.
A: An old man.
A: A husband and a wife.

Agravat et al. “VQA: Visual Question Answering”. ICCV 2015
Zhu et al. “Visual 7W: Grounded Question Answering in Images”. CVPR 2016
Figure from Zhu et al. copyright IEEE 2016. Reproduced for educational purposes.

## Application of RNN

### Visual Question Answering: RNNs with Attention

## Application of RNN

### Multilayer RNNs

### LSTM:

## Bidirectional RNNs

Figure 10.11: Computation of a typical bidirectional recurrent neural network, meant to learn to map input sequences _x_ to target sequences _y_, with loss _L_<sup>(_t_)</sup> at each step _t_. The _h_ recurrence propagates information forward in time (toward the right), while the _g_ recurrence propagates information backward in time (toward the left). Thus at each point _t_, the output units _o_<sup>(_t_)</sup> can benefit from a relevant summary of the past in its _h_<sup>(_t_)</sup> input and from a relevant summary of the future in its _g_<sup>(_t_)</sup> input.

