# Edureka《通过LLMs学习生成式人工智能（机器学习和NLP基础，第1课／共4课）｜Learn Generative AI with LLMs》中英字幕 - P53：52_理解模型优化器.zh_en - GPT中英字幕课程资源 - BV1q4421Q7qh

Hello everyone welcome back now let's understand the momentum momentum is an optimization technique that accelerates gradient descent by introducing a momentum term。

😊。

![](img/78577c490fc06a7010782a15e0d898e0_1.png)

![](img/78577c490fc06a7010782a15e0d898e0_2.png)

Momentum is an optimization technique that aates gradient descent by introducing a momentum term。

 The term accumulates a fraction of the previous gradients and adds it to the current update。

 allowing the optimization process to gain momentum and overcome obstacles like local minima or plas more efficiently for example。

 imagine a ball rolling down a hill momentum stimulates the balls inertium causing it to roll faster downhill and travis flat regions more smoothly。

 ultimately leading to faster convergence towards the optimal solution means mathematically momentum is computed as a weighted moving average or past gradients where the update at each iteration is a combination of the。

😊。

![](img/78577c490fc06a7010782a15e0d898e0_4.png)

![](img/78577c490fc06a7010782a15e0d898e0_5.png)

![](img/78577c490fc06a7010782a15e0d898e0_6.png)

![](img/78577c490fc06a7010782a15e0d898e0_7.png)

![](img/78577c490fc06a7010782a15e0d898e0_8.png)

![](img/78577c490fc06a7010782a15e0d898e0_9.png)

![](img/78577c490fc06a7010782a15e0d898e0_10.png)

![](img/78577c490fc06a7010782a15e0d898e0_11.png)

![](img/78577c490fc06a7010782a15e0d898e0_12.png)

gradient。 and the momentum term。

![](img/78577c490fc06a7010782a15e0d898e0_14.png)

Form the previous iteration， this helps。

![](img/78577c490fc06a7010782a15e0d898e0_16.png)

Dampen oscillations and stabilize convergence during the optimization that is about the momentum then the next one is of stochastic gradient descent。

 so as GD is a fundamental optimization algorithm used in the machine learning and deal deep learning it updates the model parameters as GD updates the models parameters based on the gradients computed from a randomly selected subset of training samples like you know mini batchge rather than entire data set this stochastic nature introduces randomness into the optimization process leading to faster convergence and improved generalization for example。

 as GD mimics process of searching for the lowest point in a hill terrain by taking small steps in random。



![](img/78577c490fc06a7010782a15e0d898e0_18.png)

![](img/78577c490fc06a7010782a15e0d898e0_19.png)

![](img/78577c490fc06a7010782a15e0d898e0_20.png)

![](img/78577c490fc06a7010782a15e0d898e0_21.png)

![](img/78577c490fc06a7010782a15e0d898e0_22.png)

![](img/78577c490fc06a7010782a15e0d898e0_23.png)

![](img/78577c490fc06a7010782a15e0d898e0_24.png)

![](img/78577c490fc06a7010782a15e0d898e0_25.png)

![](img/78577c490fc06a7010782a15e0d898e0_26.png)

![](img/78577c490fc06a7010782a15e0d898e0_27.png)

Diions each steps involves computing the gradient of the loss function with respect to a subset of data points and updating the model parameters accordingly means technically each iteration of SGD a mini batch of training samples is randomly sampled and the gradients of the loss function with respect to this mini batchge are computed the model parameters are then updated in the opposite direction of these gradients scaled by a learning rate to minimize the loss function that is about SGD then the next one is of atom adaptive movement estimation。



![](img/78577c490fc06a7010782a15e0d898e0_29.png)

![](img/78577c490fc06a7010782a15e0d898e0_30.png)

![](img/78577c490fc06a7010782a15e0d898e0_31.png)

![](img/78577c490fc06a7010782a15e0d898e0_32.png)

![](img/78577c490fc06a7010782a15e0d898e0_33.png)

![](img/78577c490fc06a7010782a15e0d898e0_34.png)

![](img/78577c490fc06a7010782a15e0d898e0_35.png)

![](img/78577c490fc06a7010782a15e0d898e0_36.png)

Adom is an adaptive optimization algorithm that combines the benefits of both momentum and atommis probe。

 It maintains separate adaptive learning grades for each parameter based on the estimates of first and second moments of the gradients Adam dynamically adjusts the learning rate for each parameter。

 allowing it to converge quickly and adaptively to different types of data and architecture for example。

 Adam can be likened to an experienced hike navigating rugged terrain it intelligently adjusts its space and direction based on the steepness of the slopes and the past gradients encountered enabling it to efficiently reach the valet that is the optimal solution while avoiding the obstacles。

😊。

![](img/78577c490fc06a7010782a15e0d898e0_38.png)

![](img/78577c490fc06a7010782a15e0d898e0_39.png)

![](img/78577c490fc06a7010782a15e0d898e0_40.png)

![](img/78577c490fc06a7010782a15e0d898e0_41.png)

![](img/78577c490fc06a7010782a15e0d898e0_42.png)

![](img/78577c490fc06a7010782a15e0d898e0_43.png)

![](img/78577c490fc06a7010782a15e0d898e0_44.png)

![](img/78577c490fc06a7010782a15e0d898e0_45.png)

![](img/78577c490fc06a7010782a15e0d898e0_46.png)

![](img/78577c490fc06a7010782a15e0d898e0_47.png)

![](img/78577c490fc06a7010782a15e0d898e0_48.png)

So that is about Adamom。 then the next one is of aag gridd。

 So addag gridd is an optimization algorithm that adapts the learning rate of each parameter used on the frequency of its updates during the training。

 It assigns larger learning rates to parameters with infrequent updates and smaller learning grades to frequently update the parameters This enables aag gridd to converge more quickly on parameters that require larger updates and perform wellfipa data。

 for example， aag gridd can be likened to a tailor adjusting the stitching pace based on the complexity and frequency of scenes in the fabric。

 It stitches more slowly in intricate areas and speeds in simpler sections ensuring。😊。



![](img/78577c490fc06a7010782a15e0d898e0_50.png)

![](img/78577c490fc06a7010782a15e0d898e0_51.png)

![](img/78577c490fc06a7010782a15e0d898e0_52.png)

![](img/78577c490fc06a7010782a15e0d898e0_53.png)

![](img/78577c490fc06a7010782a15e0d898e0_54.png)

![](img/78577c490fc06a7010782a15e0d898e0_55.png)

![](img/78577c490fc06a7010782a15e0d898e0_56.png)

![](img/78577c490fc06a7010782a15e0d898e0_57.png)

![](img/78577c490fc06a7010782a15e0d898e0_58.png)

![](img/78577c490fc06a7010782a15e0d898e0_59.png)

Uniformity and efficiency in the sewing process means technically a grid adapts the learning rate of each parameter by dividing the initial learning rate by the square root of the sum of squared gradients accumulated for that parameter this effectively decreases the learning rate for parameters with large updates and increases it for parameters with small updates ensuring efficient convergence across the different dimensions that is about add grid then coming to the Rs probe。

 So as mentioned here it works as combination of momentum and Rs probe let's understand what exactly this Rs probe is all about Rs probe is an optimization algorithm that addresses the diminishing learning rate problem。

😊。

![](img/78577c490fc06a7010782a15e0d898e0_61.png)

![](img/78577c490fc06a7010782a15e0d898e0_62.png)

![](img/78577c490fc06a7010782a15e0d898e0_63.png)

![](img/78577c490fc06a7010782a15e0d898e0_64.png)

![](img/78577c490fc06a7010782a15e0d898e0_65.png)

![](img/78577c490fc06a7010782a15e0d898e0_66.png)

![](img/78577c490fc06a7010782a15e0d898e0_67.png)

![](img/78577c490fc06a7010782a15e0d898e0_68.png)

![](img/78577c490fc06a7010782a15e0d898e0_69.png)

![](img/78577c490fc06a7010782a15e0d898e0_70.png)

![](img/78577c490fc06a7010782a15e0d898e0_71.png)

![](img/78577c490fc06a7010782a15e0d898e0_72.png)

As probe is an optimization algorithm that addresses the diminishing learning rate problem in a gridd by using a decaying average or squ gradients to normalize the learning rates。

 this normalization presence the learning ratess from becoming too small enabling Rs probe to effectively trained deep learning neural networks with nonstationary and spae gradients。

 for example， Ars probe can be likechen gardener adjusting the watering schedule based on the changing soil moisture levels in different areas of the garden its more it waters more in dry regions unless in the wet regions maintains optimal soil moisture throughout the garden means Ars probe computes a decay。

😊。

![](img/78577c490fc06a7010782a15e0d898e0_74.png)

![](img/78577c490fc06a7010782a15e0d898e0_75.png)

![](img/78577c490fc06a7010782a15e0d898e0_76.png)

![](img/78577c490fc06a7010782a15e0d898e0_77.png)

![](img/78577c490fc06a7010782a15e0d898e0_78.png)

![](img/78577c490fc06a7010782a15e0d898e0_79.png)

![](img/78577c490fc06a7010782a15e0d898e0_80.png)

![](img/78577c490fc06a7010782a15e0d898e0_81.png)

![](img/78577c490fc06a7010782a15e0d898e0_82.png)

![](img/78577c490fc06a7010782a15e0d898e0_83.png)

![](img/78577c490fc06a7010782a15e0d898e0_84.png)

ing average of squared gradients for each parameter and uses this average to minimize the learning rates it scales the gradients by the square root of these moving average ensuring that the learning rates remain appropriate for different parameters and training scenarios so that's about Ars probe so combining all these optimization algorithms they place a very important role in training deep learning networks by efficiently navigating the high dimensional parameter space and finding optimal solutions to the complex optimization problems each algorithm has strengths and weaknesses making them suitable for different types of data architectures and training objectives by understanding an appropriate。



![](img/78577c490fc06a7010782a15e0d898e0_86.png)

![](img/78577c490fc06a7010782a15e0d898e0_87.png)

![](img/78577c490fc06a7010782a15e0d898e0_88.png)

![](img/78577c490fc06a7010782a15e0d898e0_89.png)

![](img/78577c490fc06a7010782a15e0d898e0_90.png)

![](img/78577c490fc06a7010782a15e0d898e0_91.png)

![](img/78577c490fc06a7010782a15e0d898e0_92.png)

![](img/78577c490fc06a7010782a15e0d898e0_93.png)

![](img/78577c490fc06a7010782a15e0d898e0_94.png)

![](img/78577c490fc06a7010782a15e0d898e0_95.png)

![](img/78577c490fc06a7010782a15e0d898e0_96.png)

![](img/78577c490fc06a7010782a15e0d898e0_97.png)

Selecting these optimization algorithms， we can effectively train and optimize deep learning models for various applications and domains。

😊。

![](img/78577c490fc06a7010782a15e0d898e0_99.png)

![](img/78577c490fc06a7010782a15e0d898e0_100.png)

So the upcoming video will delve further into the ongoing discussion。😊。



![](img/78577c490fc06a7010782a15e0d898e0_102.png)