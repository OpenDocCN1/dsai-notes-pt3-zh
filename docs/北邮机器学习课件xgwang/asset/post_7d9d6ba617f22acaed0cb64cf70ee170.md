
## Plot learning curves on the training and validation sets

![](img/a04b187c89c5018c5ef6132980e27196_197_0.png)

Plot the average error per pattern (i.e. 1/n ∑_p J_p) versus the number of epochs.

## Learning curve on the training set

- The average training error typically decreases with the number of epochs and reaches an asymptotic value.
- This asymptotic value could be high if underfitting happens. The reasons could be:
  - The classification problem is difficult (Bayes error is high) and there are a large number of training samples.
  - The expressive power of the network is not enough (the numbers of weights, layers and nodes in each layer).
  - Bad initialization and get stuck at local minimum (pre-training for better initialization).
- If the learning rate is low, the training error tends to decrease monotonically, but converges slowly. If the learning rate is high, the training error may oscillate.

## Learning curve on the test and validation set

The average error on the validation or test set is virtually always higher than on the training set. It could increase or oscillate when **overfitting** happens. The reasons could be:

- Training samples are not enough.
- The expressive power of the network is too high.
- Bad initialization and get stuck at local minimum (pre-training for better initialization).

Stop training at a minimum of the error on the validation set.

## Data augmentation

- If the training set is small, one can synthesize some training samples by adding Gaussian noise to real training samples.
- Domain knowledge can be used to synthesize training samples. For example, in image classification, more training images can be synthesized by translation, scaling, and rotation.

## Normalizing input

- If the dynamic range of one input feature is much larger than others, during training, the network will mainly adjust weights on this feature while ignoring others.
- We do not want to prefer one feature over others just because they differ solely in measured units.
- To avoid such difficulty, the input patterns should be shifted so that the average over the training set of each feature is zero, and then be scaled to have the same variance as 1 in each feature.
- Input variables should be uncorrelated if possible.
  - If inputs are uncorrelated, then it is possible to solve for the value of one weight without any concern for other weights.
  - With correlated inputs, one must solve for multiple weights simultaneously, which is a much harder problem.
  - PCA can be used to remove linear correlations in inputs.

## Shuffling the training samples

打乱训练集

- Networks learn the fastest from the most unexpected sample.
- Shuffle the training set so that successive training examples never (or rarely) belong to the same class.
- Present input examples that produce a large error more frequently than examples that produce a small error.
  - This technique, applied to data containing outliers, can be disastrous because outliers can produce large errors yet should not be presented frequently.

## Error surfaces

- Backpropagation is based on gradient descent and tries to find the minimum point of the error surface **J(w)**.
- Generally speaking, it is unlikely to find the global minimum since the error surface is usually very complex.
- Backpropagation stops at local minimum and plateaus (regions where error varies only slightly as a function of weights).
- Therefore, it is important to find a good initialization for backpropagation (through pre-training).

![](img/a04b187c89c5018c5ef6132980e27196_204_0.png)

## Learning rate

- Decrease the learning rate when the weight vector "oscillates" and increase it when the weight vector follows a steady direction.
- One can choose a different learning rate for each weight, so that all the weights in the network converge roughly at the same speed.

![](img/a04b187c89c5018c5ef6132980e27196_205_0.png)

Gradient descent in a 1D quadratic criterion with different learning rates. The optimal learning rate is found by η_opt = (∂²J / ∂w²)⁻¹.
