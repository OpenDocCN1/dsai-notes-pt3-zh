# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P92：3_使用逻辑回归进行分类.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

As promised， we now introduce the sigmoid function。



![](img/de991714e6cc62406cba025e984782d9_1.png)

This takes our original linear regression function and wraps it into its own function。

 as we see here to the right one over 1 plus e to the negative x。

 where x is supposed to represent our original linear function。

 which we'll see in just the next slide， and this new function will always take values between0 and1。

 no matter the value of x。

![](img/de991714e6cc62406cba025e984782d9_3.png)

![](img/de991714e6cc62406cba025e984782d9_4.png)

![](img/de991714e6cc62406cba025e984782d9_5.png)

![](img/de991714e6cc62406cba025e984782d9_6.png)

And x again， representing that full linear equation。

 and it smooths out the effect of high or low values of x。



![](img/de991714e6cc62406cba025e984782d9_8.png)

![](img/de991714e6cc62406cba025e984782d9_9.png)

This way our algorithm is not skewed by these more extreme samples and it manages to find the obvious visual threshold。



![](img/de991714e6cc62406cba025e984782d9_11.png)

So instead of trying to fit y equals beta not plus beta 1 x as we do with linear regression。

 we can try to fit y equals a function of beta not plus beta 1 of x。

 with that function being what we mentioned earlier。

1 over 1 plus e to the power of the negative of our original linear function。

 which we see here is beta n plus beta 1 of x。

![](img/de991714e6cc62406cba025e984782d9_13.png)

![](img/de991714e6cc62406cba025e984782d9_14.png)

![](img/de991714e6cc62406cba025e984782d9_15.png)

![](img/de991714e6cc62406cba025e984782d9_16.png)

![](img/de991714e6cc62406cba025e984782d9_17.png)

The resulting algorithm that we have here is going to be called logistic regression。



![](img/de991714e6cc62406cba025e984782d9_19.png)

Note that this is not going to be a regression algorithm， again。

 it has logistic regression with regression in its name。



![](img/de991714e6cc62406cba025e984782d9_21.png)

![](img/de991714e6cc62406cba025e984782d9_22.png)

With regression generally meaning how much， but this is actually a classification algorithm as in choosing which one。

 which class is just unfortunate naming。

![](img/de991714e6cc62406cba025e984782d9_24.png)

![](img/de991714e6cc62406cba025e984782d9_25.png)

Also notice that y beta of x is always going to be between 0 and 1 and the location where it hits 0。

5 is going to be meaningful in that it truly is meant to represent that 5050 chance of either outcome given our model。

 and then as opposed to linear regression approach which can take on any value here we can only take on values between0 and 1。



![](img/de991714e6cc62406cba025e984782d9_27.png)

![](img/de991714e6cc62406cba025e984782d9_28.png)

![](img/de991714e6cc62406cba025e984782d9_29.png)

![](img/de991714e6cc62406cba025e984782d9_30.png)

![](img/de991714e6cc62406cba025e984782d9_31.png)

And now we see how we can correctly classify all the values on the left of our decision boundary as well as to the right of our decision boundary as well。



![](img/de991714e6cc62406cba025e984782d9_33.png)

![](img/de991714e6cc62406cba025e984782d9_34.png)

Now I want to tie this back to the original linear regression problem so that we have an intuitive sense of the model being learned。



![](img/de991714e6cc62406cba025e984782d9_36.png)

P of x here is going to be the output of our logistic regression and can be thought of as the probability of the sample being in a certain class versus the other。



![](img/de991714e6cc62406cba025e984782d9_38.png)

![](img/de991714e6cc62406cba025e984782d9_39.png)

Now we're not going to go2 in depth over the algebra， but e to the negative z and z being here。

 beta not plus beta1 of x。

![](img/de991714e6cc62406cba025e984782d9_41.png)

![](img/de991714e6cc62406cba025e984782d9_42.png)

Is going to be equal to one over e to the Z。

![](img/de991714e6cc62406cba025e984782d9_44.png)

So our denominator can be transformed into one plus1 over e to the Z。

 and we can multiply the top and bottom by E to the Z。

 and we'll end up with the equation that we have here on the right。



![](img/de991714e6cc62406cba025e984782d9_46.png)

![](img/de991714e6cc62406cba025e984782d9_47.png)

![](img/de991714e6cc62406cba025e984782d9_48.png)

Don't worry too much if you didn't follow along with the algebra。

 you can just trust that we will have this equation that we have here on the rights。



![](img/de991714e6cc62406cba025e984782d9_50.png)

We can then do some more algebra on our own to see that we can show that the odds ratio is just equal to e rays to the power of our linear function。

 the idea being here as you see us walk through the steps that we're trying to isolate what the linear function actually does。



![](img/de991714e6cc62406cba025e984782d9_52.png)

![](img/de991714e6cc62406cba025e984782d9_53.png)

![](img/de991714e6cc62406cba025e984782d9_54.png)

So our linear prediction is longer a function is no longer y but a function of y。

 so rather than p of x it's p of x over 1 minus p of x。



![](img/de991714e6cc62406cba025e984782d9_56.png)

And if we recall that p of x is a probability， we can see that we now have turned our probability into an odds ratio。

 so if we start off with a 0。7 chance， 0。75 chance of getting a certain value that is the same as saying we have 3 to 1 odds with p of x equals 0。

75 1 minus p of x would be 0。25 so it'd be 0。75 over 0。

25 and we'd end up with e to the power of our linear function is equal to 3 to 1 odds rather than our original logistic function being equal to 0。

75。

![](img/de991714e6cc62406cba025e984782d9_58.png)

![](img/de991714e6cc62406cba025e984782d9_59.png)

![](img/de991714e6cc62406cba025e984782d9_60.png)

![](img/de991714e6cc62406cba025e984782d9_61.png)

![](img/de991714e6cc62406cba025e984782d9_62.png)

![](img/de991714e6cc62406cba025e984782d9_63.png)

![](img/de991714e6cc62406cba025e984782d9_64.png)

We can then take the log of both sides and we see that our linear equation is just going to be a linear function of x where our y here。

 which is now a function of our original y， can be seen as the log odds。

 so a unit increase or decrease in our x values will change our log odds in a linear faction according to whatever the beta 1 is that we have learned。



![](img/de991714e6cc62406cba025e984782d9_66.png)

![](img/de991714e6cc62406cba025e984782d9_67.png)

![](img/de991714e6cc62406cba025e984782d9_68.png)

![](img/de991714e6cc62406cba025e984782d9_69.png)

![](img/de991714e6cc62406cba025e984782d9_70.png)

So that's going to be how you can use it for interpretive purposes。



![](img/de991714e6cc62406cba025e984782d9_72.png)

Now let's get back to our visual example to gain a deeper understanding of the boundary created by ourlog regression。



![](img/de991714e6cc62406cba025e984782d9_74.png)

![](img/de991714e6cc62406cba025e984782d9_75.png)

With one feature， the boundary is just a point corresponding to y equals 0。5。



![](img/de991714e6cc62406cba025e984782d9_77.png)

And then we have two labels not churned versus churns， and we only have that one feature。

 the amount of usage。

![](img/de991714e6cc62406cba025e984782d9_79.png)

![](img/de991714e6cc62406cba025e984782d9_80.png)

Now with two features we'll be working with a straight line and in general。

 as we move up to higher dimensions， that decision boundary will just be a hyperplane。

 the idea being that's just going to be a linear function don't mind the little rerouting on the figure it is meant to be linear we just wanted to show how it be classified using a straight line and didn't want to run through any one of our examples。



![](img/de991714e6cc62406cba025e984782d9_82.png)

![](img/de991714e6cc62406cba025e984782d9_83.png)

![](img/de991714e6cc62406cba025e984782d9_84.png)

![](img/de991714e6cc62406cba025e984782d9_85.png)

![](img/de991714e6cc62406cba025e984782d9_86.png)

And with our new decision boundary。

![](img/de991714e6cc62406cba025e984782d9_88.png)

We can now predict a new example， we see it fall somewhere around phone usage being let's say 8s and data usage being around 20。

 and we can predict this example according to where it falls given our decision boundary and we find that it would be。



![](img/de991714e6cc62406cba025e984782d9_90.png)

![](img/de991714e6cc62406cba025e984782d9_91.png)

![](img/de991714e6cc62406cba025e984782d9_92.png)

Whatever the blue label is， whether that's churned or not churned。

