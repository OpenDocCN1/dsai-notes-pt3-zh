# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p42 41_正态分布理论.zh_en -BV1r483zbEzN_p42-

![](img/74c5517f8de008c667a9b3a720522076_0.png)

We're now going to talk about the most important probability distribution in probably all of statistics。

 and that is the。

![](img/74c5517f8de008c667a9b3a720522076_2.png)

Gausian。

![](img/74c5517f8de008c667a9b3a720522076_4.png)

Or normal。Distribution now， oddly enough， Gauss didn't actually come up with this distribution。

 He just made it famous。 It's kind of a sad story。 But I think there's something in your textbook。

 If you're a history buff and want to want to look at such things， right。

 We're going to look at the normal。 There's a couple flavors of the normal。

 We're going to start with the standard normal。 So the standard。



![](img/74c5517f8de008c667a9b3a720522076_6.png)

![](img/74c5517f8de008c667a9b3a720522076_7.png)

Standard， normal。

![](img/74c5517f8de008c667a9b3a720522076_9.png)

Right， the standard normal。

![](img/74c5517f8de008c667a9b3a720522076_11.png)

s we use this notation of an n to reference normal and the standard normal， we have two parameters。



![](img/74c5517f8de008c667a9b3a720522076_13.png)

0 and1。 and what that's saying is the mean， which we also use the Greek letter mu for mean equals0。



![](img/74c5517f8de008c667a9b3a720522076_15.png)

![](img/74c5517f8de008c667a9b3a720522076_16.png)

And the variance。

![](img/74c5517f8de008c667a9b3a720522076_18.png)

Is one。 so the variance is one。

![](img/74c5517f8de008c667a9b3a720522076_20.png)

Or standard deviation sometimes people use， but the standard normal 01。



![](img/74c5517f8de008c667a9b3a720522076_22.png)

嗯。TheThe density function can be written as little f of x for the density function as1 over the square root of 2 pi times e to the negative x squared over 2。



![](img/74c5517f8de008c667a9b3a720522076_24.png)

![](img/74c5517f8de008c667a9b3a720522076_25.png)

![](img/74c5517f8de008c667a9b3a720522076_26.png)

![](img/74c5517f8de008c667a9b3a720522076_27.png)

That is the density function。

![](img/74c5517f8de008c667a9b3a720522076_29.png)

Okay， so what does that look like？

![](img/74c5517f8de008c667a9b3a720522076_31.png)

This is your're famous。Bell curve。 So it looks like a little bell。



![](img/74c5517f8de008c667a9b3a720522076_33.png)

Here's zero， here's x， here is our density function。

 and if we want to look at what the CDF is over the same area here， this is a capital F of x。



![](img/74c5517f8de008c667a9b3a720522076_35.png)

![](img/74c5517f8de008c667a9b3a720522076_36.png)

![](img/74c5517f8de008c667a9b3a720522076_37.png)

X well， you have a little bit of value here。And then you start adding a little bit more chunks。

 and they get increasingly larger and larger and larger， and then you start slowing down。

 adding smaller and smaller chunks， and it creates kind of this S shape pattern that you have for the CDF。



![](img/74c5517f8de008c667a9b3a720522076_39.png)

![](img/74c5517f8de008c667a9b3a720522076_40.png)

![](img/74c5517f8de008c667a9b3a720522076_41.png)

![](img/74c5517f8de008c667a9b3a720522076_42.png)

This is the Pdf。Okay， but let's get a little more intuition from that。

 So if we look at this function here， you know， we start with this x squared。

 What does an x squared function look like。 Well， an x squared function right is a parabola。😊。



![](img/74c5517f8de008c667a9b3a720522076_44.png)

![](img/74c5517f8de008c667a9b3a720522076_45.png)

![](img/74c5517f8de008c667a9b3a720522076_46.png)

Looks something like this， right？

![](img/74c5517f8de008c667a9b3a720522076_48.png)

Well， you know， and if we just divide by 2， we're just changing the scale a little bit。

 it still looks the same。 So then we go here and we make it a negative x squared over 2。

 So now what have we done well。

![](img/74c5517f8de008c667a9b3a720522076_50.png)

![](img/74c5517f8de008c667a9b3a720522076_51.png)

We have just。Reflected it across the axis， and we have a negative x squared over 2。



![](img/74c5517f8de008c667a9b3a720522076_53.png)

And then we do this E business right So when we do the E。

 this is where we're all of a sudden now kind of it does some funky things and we kind of create the bell。



![](img/74c5517f8de008c667a9b3a720522076_55.png)

![](img/74c5517f8de008c667a9b3a720522076_56.png)

is e to the negative x。Squared over2。 and then what do you think this function does What is the purpose of1 over the square root of2 pi Now I'd like you to pause the video for a second and just think about what you know about probability densities。



![](img/74c5517f8de008c667a9b3a720522076_58.png)

![](img/74c5517f8de008c667a9b3a720522076_59.png)

And what do you think this constant is doing to this function that makes it into a probability density？



![](img/74c5517f8de008c667a9b3a720522076_61.png)

![](img/74c5517f8de008c667a9b3a720522076_62.png)

I'm assuming you've paused， you've thought about it。 Well。

 the answer is what do we know about a probability density。 What must be true。

 Well it's got to be all greater than0， we have that right it's all greater than0。

 This wasn't but this is all greater than zero we know that the probability of any given point is going to be zero because you can't get mass over that point so we know that's the case so what's our third probability principle our third principle is that the overall area under the curve equals1。

 so clearly the area from negative infinity to infinity of this does not equal1。

 it actually equals the square root to two pi which is why we have to divide by the square root to two pi so that we actually make it a density function so you'll see a lot of the statistical distributions when you look at the density function they have some sort of weird constant and what that's doing is it's making sure that the area under the curve。



![](img/74c5517f8de008c667a9b3a720522076_64.png)

![](img/74c5517f8de008c667a9b3a720522076_65.png)

![](img/74c5517f8de008c667a9b3a720522076_66.png)

![](img/74c5517f8de008c667a9b3a720522076_67.png)

![](img/74c5517f8de008c667a9b3a720522076_68.png)

![](img/74c5517f8de008c667a9b3a720522076_69.png)

![](img/74c5517f8de008c667a9b3a720522076_70.png)

![](img/74c5517f8de008c667a9b3a720522076_71.png)

![](img/74c5517f8de008c667a9b3a720522076_72.png)

Is one。 So we call that a scaling constant or a scaling constant。



![](img/74c5517f8de008c667a9b3a720522076_74.png)

Okay。

![](img/74c5517f8de008c667a9b3a720522076_76.png)

So that should give us some intuition of this standard normal distribution Well。

 why is this so important， why is this distribution more important than the uniform let's say？



![](img/74c5517f8de008c667a9b3a720522076_78.png)

![](img/74c5517f8de008c667a9b3a720522076_79.png)

Well， there's a a couple reasons for it， the most important being that when you take observations from any distribution。

 it be it could be one of these distributions that's like you know like square you know like the uniform it could be a really crazy distribution that does something like this where these small values are very likely and then you've got these outliers that are really really large so you have this very skewed data it doesn't matter what the distribution is if you take some observations from that and you sum them you add them together and you take the average of that if you've taken a sufficient number of samples you take the average。

 that average value is going to be normally distributed。

 normally distributed so what we're able to do is when we when we have any kind of phenomena where we're collecting data and we don't necessarily know what the underlying distribution is if we can take several observations。



![](img/74c5517f8de008c667a9b3a720522076_81.png)

![](img/74c5517f8de008c667a9b3a720522076_82.png)

![](img/74c5517f8de008c667a9b3a720522076_83.png)

![](img/74c5517f8de008c667a9b3a720522076_84.png)

![](img/74c5517f8de008c667a9b3a720522076_85.png)

![](img/74c5517f8de008c667a9b3a720522076_86.png)

![](img/74c5517f8de008c667a9b3a720522076_87.png)

![](img/74c5517f8de008c667a9b3a720522076_88.png)

![](img/74c5517f8de008c667a9b3a720522076_89.png)

usually about 30 or more， we can take those observations and that average is normally distributed and we can make inference about the typical behavior of those values from any distribution we draw from and that uses the normal distribution。

 so that's why it's so important in statistics。😊。

![](img/74c5517f8de008c667a9b3a720522076_91.png)

![](img/74c5517f8de008c667a9b3a720522076_92.png)

![](img/74c5517f8de008c667a9b3a720522076_93.png)

It's also used quite frequently for human behavior。

 so when you look at the heights of people are going to be normally distributed。

 people's IQs are going to be normally distributed， runtime are going to be normally distributed。

 pretty much anything that involves human performance or humans you're going to find is very often normally distributed。

We're going to look at a little bit more information here， the expected value， the expected value。



![](img/74c5517f8de008c667a9b3a720522076_95.png)

![](img/74c5517f8de008c667a9b3a720522076_96.png)

We already told you was zero for a standard normal and the variance， right。

 the variance of x is going to be1。 That's what makes it a standard normal。 So there's other normals。

 right， There is the general normal， general normal distribution。



![](img/74c5517f8de008c667a9b3a720522076_98.png)

![](img/74c5517f8de008c667a9b3a720522076_99.png)

![](img/74c5517f8de008c667a9b3a720522076_100.png)

![](img/74c5517f8de008c667a9b3a720522076_101.png)

And the general normal is going to be where that mean and the variance are not necessarily0 and1。

 Well， what does that mean Well， if we look at the axis here and if this is the standard normal。

 right？

![](img/74c5517f8de008c667a9b3a720522076_103.png)

![](img/74c5517f8de008c667a9b3a720522076_104.png)

![](img/74c5517f8de008c667a9b3a720522076_105.png)

Well you might expect to find the distributions not centered around zero。

 I hope that would be the case for exam scores right。

 we want those centered up here around maybe like 90 right so you might have that all centered up here around。



![](img/74c5517f8de008c667a9b3a720522076_107.png)

![](img/74c5517f8de008c667a9b3a720522076_108.png)