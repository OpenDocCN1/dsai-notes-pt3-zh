# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p08 7_常见训练选项.zh_en -BV1Rb421v71M_p8-

🎼。

![](img/2cb50e427496a72c0f14e324bf6840dc_1.png)

Depending on your data and application， you will likely need to adjust some training options to achieve good results。



![](img/2cb50e427496a72c0f14e324bf6840dc_3.png)

You've already encountered a few key training options。In this video。

 you'll learn several more and examine their impact on training。

Intelligently adjusting these options will help you train models with higher acuracies and lower losses。

Let's start with mini batch size。

![](img/2cb50e427496a72c0f14e324bf6840dc_5.png)

Recall that a model evaluates a small subset of the training data or mini batch at each iteration。



![](img/2cb50e427496a72c0f14e324bf6840dc_7.png)

![](img/2cb50e427496a72c0f14e324bf6840dc_8.png)

These mini batches are more memory efficient than analyzing every image， every iteration。

They also allow you to update model weights more frequently and prevent the model from getting stuck and returning non optimal weights。



![](img/2cb50e427496a72c0f14e324bf6840dc_10.png)

If your mini batch size is too large。You lose these benefits， and you may run out of memory。



![](img/2cb50e427496a72c0f14e324bf6840dc_12.png)

But if your mini batches are too small。Your training accuracy and loss may fluctuate wildly。



![](img/2cb50e427496a72c0f14e324bf6840dc_14.png)

If your training is irregular， try increasing the mini batch size。



![](img/2cb50e427496a72c0f14e324bf6840dc_16.png)

By default。There are 128 images per mini batch。

![](img/2cb50e427496a72c0f14e324bf6840dc_18.png)

This usually strikes a good balance， and you won't often have to change it。



![](img/2cb50e427496a72c0f14e324bf6840dc_20.png)

However， if you're running out of memory， you may need to decrease your mini batch size。



![](img/2cb50e427496a72c0f14e324bf6840dc_22.png)

Remember， leftover images that don't evenly fit into mini batches。

Are removed from analysis each epoch。If many of your images are being discarded。

 consider choosing a mini batch size that evenly divides your training set。



![](img/2cb50e427496a72c0f14e324bf6840dc_24.png)

Mini batch size affects another important training option。



![](img/2cb50e427496a72c0f14e324bf6840dc_26.png)

Validation frequency or how often the validation accuracy and loss are calculated。



![](img/2cb50e427496a72c0f14e324bf6840dc_28.png)

Larger mini batches require fewer iterations per epoch。However。

 validation data is not split into many batches。Instead， by default， validation。

 accuracy and loss are calculated every 50 iterations using all the validation images。

Changing the mini batch size updates the number of iterations per epoch。

 but leaves the validation frequency unchanged。Therefore， validation。

 accuracy and loss may be calculated only a few times during training。As you'll see。

 validation loss is generally how you choose the best weights。

 so calculating it infrequently can lead to imperfect results。

A general guideline is to compute the validation loss once or twice per epoch。



![](img/2cb50e427496a72c0f14e324bf6840dc_30.png)

It's also good practice to set the output network to Best validation loss。



![](img/2cb50e427496a72c0f14e324bf6840dc_32.png)

This way， you'll return the best model available with the lowest validation loss。

 even if the model is stopped improving or the validation loss has diverged from the training loss。



![](img/2cb50e427496a72c0f14e324bf6840dc_34.png)

To visualize how your model minimizes validation loss。

 consider a model's loss plotted as a function of its weight values。



![](img/2cb50e427496a72c0f14e324bf6840dc_36.png)

Here we use two weights for instructional purposes。

 but usually the loss is determined by millions of weights。



![](img/2cb50e427496a72c0f14e324bf6840dc_38.png)

Graadient descent is a practical and popular method for quickly optimizing weights by iteratively stepping towards the minimum loss。

Roughly speaking， gradient tocent algorithms do this by setting some initial weights as a starting point。



![](img/2cb50e427496a72c0f14e324bf6840dc_40.png)

And determining the steepest downward direction at that point。



![](img/2cb50e427496a72c0f14e324bf6840dc_42.png)

By calculating the gradient of the loss。

![](img/2cb50e427496a72c0f14e324bf6840dc_44.png)

Based on this gradient， the algorithm estimates new weights and then calculates the gradient again。



![](img/2cb50e427496a72c0f14e324bf6840dc_46.png)

This cycle of evaluating and updating the weights repeats until the loss is below a predefined threshold。

Or the training runs out of steps。

![](img/2cb50e427496a72c0f14e324bf6840dc_48.png)

In this course， we perform these calculations using the atom solver。



![](img/2cb50e427496a72c0f14e324bf6840dc_50.png)

But all matlab solver algorithms use variations of gradient descent。



![](img/2cb50e427496a72c0f14e324bf6840dc_52.png)

There's always a risk that an algorithm will get stuck in a local minimum。

Instead of the global minimum。The ways algorithms circumvent this are beyond the scope of this course。

Just now that we use the atom solver in part because it's good at continuing through local minimums。

Many training options work by changing how your algorithm behaves。For example。

 the learning rate determines how much the weights change each iteration。



![](img/2cb50e427496a72c0f14e324bf6840dc_54.png)

![](img/2cb50e427496a72c0f14e324bf6840dc_55.png)

By default， the initial learning rate establishes a uniform step size throughout training。



![](img/2cb50e427496a72c0f14e324bf6840dc_57.png)

Higher learning rates make larger changes and can approach Minma quickly。

But can also be imprecise and pose a risk of overhooting or skipping over optimal weights。

Lower learning rates offer greater consistency， but require more time and computational resources。



![](img/2cb50e427496a72c0f14e324bf6840dc_59.png)

Generally， you should train with the largest step size you can as long as the validation accuracy and loss eventually plateau。

If your loss is erratic or still rapidly climbing after the first few iterations。

 lower the initial learning rate。

![](img/2cb50e427496a72c0f14e324bf6840dc_61.png)

Learning rates that are too high might also cause training failures after a few epochs。



![](img/2cb50e427496a72c0f14e324bf6840dc_63.png)

![](img/2cb50e427496a72c0f14e324bf6840dc_64.png)

Which you'll see as validation losses of nan or not a number。

Barring errors training will stop when the model runs out of steps， as determined by your max epochs。



![](img/2cb50e427496a72c0f14e324bf6840dc_66.png)

However， this may be far from the global minimum。If your validation accuracy is still climbing or your loss is still dropping when your model reaches the maximum number of epochs。



![](img/2cb50e427496a72c0f14e324bf6840dc_68.png)

Increase the maxypo。

![](img/2cb50e427496a72c0f14e324bf6840dc_70.png)

You also may need to adjust your max E box depending on your learning rate。

 because lower learning rates need more steps to reach the minimumma。In ways like these。

 training options work in concert， allowing a great deal of flexibility。



![](img/2cb50e427496a72c0f14e324bf6840dc_72.png)

You'll probably have to try different approaches to find one that meets your application's needs。



![](img/2cb50e427496a72c0f14e324bf6840dc_74.png)

Later in this course， you'll use specialized tools to train and compare models using different training options。



![](img/2cb50e427496a72c0f14e324bf6840dc_76.png)

![](img/2cb50e427496a72c0f14e324bf6840dc_77.png)

。