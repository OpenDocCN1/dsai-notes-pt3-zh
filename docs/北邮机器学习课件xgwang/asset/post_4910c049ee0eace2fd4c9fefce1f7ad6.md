
## Reading materials
- R. O. Duda, P. E. Hart, and D. G. Stork, "Pattern Classification," Chapter 6, 2000.
- Y. Bengio, I. J. GoodFellow, and A. Courville, "Feedforward Deep Networks," Chapter 6 in "Deep Learning", Book in preparation for MIT Press, 2014.

## Reference
- W. S. McCulloch and W. Pitts. A logical calculus of ideas immanent in nervous activity. *Bulletin of Mathematical Biophysics*, 5:115-133, 1943.
- F. Rosenblatt. The perceptron: A probabilistic model for information storage and organization in the brain. *Psychological Review*, 65:386-408, 1958.
- D. Rumelhart, G. E. Hinton, and R. J. Williams. Learning internal representations by back-propagating errors. *Nature*, 323:533-536, 1986.
- Y. LeCun. A learning scheme for asymmetric threshold networks. In *Proceedings of Cognitiva 85*, pages 599-604, Paris, France, 1985.
- Y. LeCun. Learning processes in an asymmetric threshold network. In Elie Bienenstock, Francoise Fogelman-Soulie, and Gerard Weisbuch, editors, *Disordered systems and biological organization*, pages 233-240, Les Houches, France, 1986. Springer-Verlag.
- R. Hecht-Nielsen. Theory of the backpropagation neural network. In *Proceedings of the IEEE International Joint Conference on Neural Networks, Vol. 1*, pages 593-605, 1989.

## Reference
- K. Fukushima. Neocognitron: A self-organizing neural network model for a mechanism of pattern recognition unaffected by shift in position. *Biological Cybernetics*, 36(4): 93-202, 1980.
- Y. LeCun, L. Bottou, Y. Bengio, and P. Haffner. Gradient-based learning applied to document recognition. *Proceedings of the IEEE* 86 (11): 2278-2324, 1998.
- G. E. Hinton, S. Osindero, and Y. W. Teh. A fast learning algorithm for deep belief nets. *Neural Computation*, 18:1527-1554, 2006.
- G. E. Hinton, and R. R. Salakhutdinov. Reducing the dimensionality of data with neural networks. *Science*, 313:504-507, 2006.
- G. E. Hinton. Learning multiple layers of representation. *Trends in Cognitive Sciences*, Vol. 11, pp. 428-434, 2007.

## Autoencoder

Xiaogang Wang

xgwang@ee.cuhk.edu.hk

February 14, 2015

## Outline
- 1. Autoencoder
- 2. Regularized autoencoders
- 3. Multimodal autoencoders

## Deep autoencoder

Stack multiple encoders (and their corresponding decoders)

![](img/a04b187c89c5018c5ef6132980e27196_114_0.png)

## Comparison of methods of compressing images

![](img/a04b187c89c5018c5ef6132980e27196_116_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_116_1.png)

## Predictive Sparse Decomposition
- Sparse coding
  - Solving the encoder $f_0$ is non-trivial because of $L_1$ minimization and entails an iterative optimization
  - $y^* = f_0(x) = \arg\min_y \|x - Wy\|_2^2 + \lambda\|y\|_1$
  - $J_{SC} = \sum_n \|x^{(n)} - Wy^{(n)}\|_2^2$
- Predictive sparse decomposition
  - Approximation to sparse coding
  - Add sparse penalty to auto-encoder
  - Replace the costly and highly non-linear encoding step by a fast non-iterative approximation

The training criterion is simultaneously optimized with respect to the hidden codes (representation) $y^{(n)}$ and with respect to the parameters $\theta$

$J_{PSD} = \sum_n \lambda\|y^{(n)}\|_1 + \|x^{(n)} - Wy^{(n)}\|_2^2 + \|y^{(n)} - f_0(x^{(n)})\|_2^2$

$f_0(x^{(n)}) = \sigma(b + W^T x^{(n)})$

## Multimodal deep learning
- Ngiam et al. ICML'11 (audio-visual speech recognition)
- Multimodal fusion: data from all modalities is available at all phases
- Cross modality learning: data from multiple modalities is available only during feature learning; during supervised training and testing, only data from a single modality is provided. The aim is to learn better single modality representations given unlabeled data from multiple modalities.
- Matching across different modalities
- A direct approach is to train a RBM over the concatenated audio and video data. Limited as a shallow model, it is hard for a RBM to learn the highly nonlinear correlations and form multimodal representations
- It was found that learning a shallow bimodal RBM results in hidden units that have strong connections to variables from individual modality but few units that connect across the modalities.

![](img/a04b187c89c5018c5ef6132980e27196_120_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_120_1.png)

![](img/a04b187c89c5018c5ef6132980e27196_120_2.png)
