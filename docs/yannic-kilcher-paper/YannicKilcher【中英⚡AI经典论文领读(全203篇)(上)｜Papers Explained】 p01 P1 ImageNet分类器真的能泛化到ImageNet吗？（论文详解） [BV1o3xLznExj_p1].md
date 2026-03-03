# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p01 P1 ImageNet分类器真的能泛化到ImageNet吗？（论文详解） [BV1o3xLznExj_p1]

Hi there。 Today， we're looking at to do imagenet classifiers generalized to imagenet by Benjamin Reed。

 Rebecca Rooffs， Ludwig Schmidt and Vishaal Shankar。 So the premise of this paper is pretty simple。

 we've been training models on imagenet now for a while。 almost 10 years to be exact。

 Inet is this data set with a lot of images， millions of images categorized into many thousands of categories。

 Now， the the classic part of imagenet that people know is has about 1。

5 million images in 1000 different classes。 and this。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_1.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_2.png)

ImageNet was one of the main dataset sets now or has been for the last few years。

 and as you can see on the right here， the error rate year after year was pretty much。

 I think cut in half every year since 2012 when the first Ne AlexNet was using deep learning instead of the classical visual computer vision approaches。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_4.png)

So we've been training on Inet for a while， and the。Idea or the question this paper asks if we。

Collect a second test set， right， So for Inet， we have a train。And the test set。

If we now collect a second test set here， test V2。Right。

If we have a model that was trained on training here and evaluated on test。

 Does it also perform well on this second test set， right， the idea of this being that。

Maybe over the years， we've tuned our hyperparameter and all。

 such that the models perform well on that particular test set。 Let's call this V1， right。

 and it might not。 It might not be as successful on a new test set。

 So this paper goes about collecting a test set to imagenet in exactly the way that the V1 test set was collected。

 right。So they， they try to match exactly the process of how V1 was collected to create another test set。

 and then they evaluate models on that new test set。They do this not only for IageNe。

 but also for C far 10， which is a much smaller data set。

 but also a lot of computer vision algorithms are evaluated on C far 10。

So let's just put up a hypothesis here。 The hypothesis is that we have pretty much overfitted to Imagenet By now。

 This is a very prestigious number to get。 if you have state of the art on imagenet and therefore tuning your hyperparameters and your learning rate and everything such that it performs well on the tests at V1 is very likely。

 So this paper has the most important plots are like this。

 It has two aes and on the bottom axis is the performance on V1。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_6.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_7.png)

Right。And so performance。And that means accuracy， basically， so accuracy。

 And on line 2 is V2 accuracy。Now。Here is one。Here is 0。

This line here means that if a model is performing。50% accuracy on V1。

 It is also performing 50% accuracy on V2。 So being on this line would basically mean we have not overfitted。

 and the model is performing equally well on both both sets。So what， what now。

 if we assume that we have overfitted， if we have overfitted， we would assume that， you know。

 the models that perform really poorly might also， you know， they perform kind of。

 they're not really overfitted。 But over the years， as we've gotten better on V1。

We stray away from this。 So we get better on V1， but we don't really get better on V2， right。

 And that means we've overfitted to V1。 And this might even go down， right， the more。

 the more kind of we might overfit to V1， the worse we're actually going to get on V2。So this。

 this is kind of a metater overfitting。 So this is what we would expect if we overfit。

O overfit to V1。 And I think this was the initial hypothesis behind the people that ran this experiment to check。

 Can we see an effect like this or is the effect more a continuous one where we don't overfit。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_9.png)

And what they found was neither。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_11.png)

And these are basically these interesting plots here。 So again。

 the dashed line here would be the not overfitting line。 So what they find， if you， for example。

 look at imagenet every dot here is a model， right？

 So this model right here is performing with like a 67% accuracy on V1。

 And it is performing with something like a 53% accuracy on V 2。 And if you look at this line here。

 what that means is。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_13.png)

Every model kind of drops。By about this much。Right。收。Not only not， we don't see this。

 And we don't see this， but we see this line is shifted down。 And if you look closely。

 especially in C4 10， you can see the line rather than being tilted like this is actually tilted a bit slanted upwards。

 right， So the the， the。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_15.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_16.png)

The angle is not is higher， is greater。 The slope is greater than the one to one slope。

 This is extremely interesting。 If you think about what does that mean。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_18.png)

It means that， if you。Take a model， right。Right here。If you look at its order， it's saying this。

Let's， let's look at this model here。 This model is number one。Best model in the world， right。

 It will still be number one on V2。This model here is number number 3， rank 3 on V 1。

 It will also be rank 3 on V 2。 right， So the order of models is， is pretty much constant。 So if。

 if a model is doing well on V1， it is also doing well on V2 in relation to other models。

 but every model experiences this drop in。In accuracy， and the most interesting part is that。

 And again， you can see this more here。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_20.png)

The， the better you're doing， the smaller this drop gets， right。

 This drop here is smaller than this drop here。 This is exactly counter to the notion of overfitting。

Where it seems the more accurate you get on V1， the more you're able to close this gap between V1 and V2。

 And if you extrapolate here， you might as well think that once we are at at or actually， sorry。

100% is already here。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_22.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_23.png)

If you could go higher， maybe， or maybe you can see here that in the end， the。

 these will actually converge。 but nevertheless， if。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_25.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_26.png)

The models that are doing better on V1 aren't only not overfit。

 but they are actually experienced less of a drop with regards to a new test set。

 So they generalize better to the new test set than the the worst models。 And and that is crazy。

 And it is not only neural networks， right， So up here for up here。

 you have the the deep neural networks and whatnot。 But you can also go with。

 I believe some of these or even further down here are k nearest neighbor， sorry。

 K nearest neighbor classifiers And things like this。 so。

It doesn't seem to be a property of neural networks。

 It really seems to be a property of the data set。 And this paper， first of all。

 goes over how they collected these。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_28.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_29.png)

And， second of all。Their hypotheses and investigations into why this phenomenon exists， why we are。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_31.png)

All of a sudden， worse on the new test set， but completely worse in a different way than we expected compared to the original test set。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_33.png)

Alright， so。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_35.png)

They first say potential causes of accuracy drops， and they propose a model。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_37.png)

They say here are here is the entire difference between two data sets with regards to a classifier。

 it can be decomposed into three different gaps and you see the first and the last part here are the ones from the left side。

 so this is an expanding sum in the middle。

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_39.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_40.png)

![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_41.png)

So there is the generalization gap。 The generalization gap refers to the。

Gap that you have between different data sets of the same distribution。 So these， this is。

 like you know， from the train versus test set。 You train on the training set。

 and then you have a generalization gap to the test set in this case， the。



![](img/ebe3a7cbe194e30b38f9a2c586ac87f0_43.png)