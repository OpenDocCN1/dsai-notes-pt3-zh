# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p64 19_切比雪夫不等式.zh_en -BV1r483zbEzN_p64-

![](img/88a13c62c199262fe7e87842b0119275_0.png)

All right， we're going to talk about another important inequality and this is the。



![](img/88a13c62c199262fe7e87842b0119275_2.png)

![](img/88a13c62c199262fe7e87842b0119275_3.png)

We're going to talk about the Cheby Cheev's inequality。



![](img/88a13c62c199262fe7e87842b0119275_5.png)

So this is stating that the probability。

![](img/88a13c62c199262fe7e87842b0119275_7.png)

The absolute value of x minus mean。Is greater than or equal to a。



![](img/88a13c62c199262fe7e87842b0119275_9.png)

That probability is less than or equal to。

![](img/88a13c62c199262fe7e87842b0119275_11.png)

The variance of x。

![](img/88a13c62c199262fe7e87842b0119275_13.png)

Divided by。A squared。

![](img/88a13c62c199262fe7e87842b0119275_15.png)

Okay。So we know from the Markovs inequality， right that the probability of x being greater than or equal to a is less than or equal to the expected value of x。



![](img/88a13c62c199262fe7e87842b0119275_17.png)

![](img/88a13c62c199262fe7e87842b0119275_18.png)

Over a。

![](img/88a13c62c199262fe7e87842b0119275_20.png)

So if we assume now， let's assume。

![](img/88a13c62c199262fe7e87842b0119275_22.png)

That x is really now going to be equal to some。

![](img/88a13c62c199262fe7e87842b0119275_24.png)

That this x is going to be equal to some absolute value of x minus。



![](img/88a13c62c199262fe7e87842b0119275_26.png)

Mean， right， X minus mu。

![](img/88a13c62c199262fe7e87842b0119275_28.png)

RightSo now I'm going to replace this， right。 Then what I'm saying put a little dashed line so you don't think I'm talking about the same x。

 Then what I'm saying is probability that the absolute value of x minus mu。



![](img/88a13c62c199262fe7e87842b0119275_30.png)

![](img/88a13c62c199262fe7e87842b0119275_31.png)

![](img/88a13c62c199262fe7e87842b0119275_32.png)

Is greater than or equal to a。Is less than or equal to the expected value of x minus mu。



![](img/88a13c62c199262fe7e87842b0119275_34.png)

![](img/88a13c62c199262fe7e87842b0119275_35.png)

Over a right。 So what I've done is this is essentially the x here， right。

 So these are not the same xs， right， But I'm just saying the value greater than or equal to a is the expected value of that value divided by a。



![](img/88a13c62c199262fe7e87842b0119275_37.png)

![](img/88a13c62c199262fe7e87842b0119275_38.png)

Okay。

![](img/88a13c62c199262fe7e87842b0119275_40.png)

So。If that is true， I I also know then that because they're both non negative numbers。

 I can basically say to get rid of the absolute value if I square it and put x minus mu。



![](img/88a13c62c199262fe7e87842b0119275_42.png)

![](img/88a13c62c199262fe7e87842b0119275_43.png)

![](img/88a13c62c199262fe7e87842b0119275_44.png)

Squared is going to be greater than or equal to a squared。



![](img/88a13c62c199262fe7e87842b0119275_46.png)

Okay。So that will be true and so then because this is a positive number。

 we know that that's a non negative number， so that whole value here is now going to be less than or equal to。



![](img/88a13c62c199262fe7e87842b0119275_48.png)

![](img/88a13c62c199262fe7e87842b0119275_49.png)

![](img/88a13c62c199262fe7e87842b0119275_50.png)

The expected value of x minus mu。

![](img/88a13c62c199262fe7e87842b0119275_52.png)

Squared。Over a squared， not because I'm squaring anything over here。

 but I'm just reusing this formula， right， so now my a is here。



![](img/88a13c62c199262fe7e87842b0119275_54.png)

And here and my A is here and here， right， so that is all I have here is still the markov inequality。



![](img/88a13c62c199262fe7e87842b0119275_56.png)

![](img/88a13c62c199262fe7e87842b0119275_57.png)

But what I can observe。

![](img/88a13c62c199262fe7e87842b0119275_59.png)

Is that the expected value of x minus the mean squared is the variance。



![](img/88a13c62c199262fe7e87842b0119275_61.png)

And then I have a squared。 and so that is how I get that the probability。



![](img/88a13c62c199262fe7e87842b0119275_63.png)

That the。

![](img/88a13c62c199262fe7e87842b0119275_65.png)

The x minus the mean greater than a is less than the variance divided by a squared。

 and so that is another upper bound that we can place on a probability。



![](img/88a13c62c199262fe7e87842b0119275_67.png)

![](img/88a13c62c199262fe7e87842b0119275_68.png)

To give you an example of where you would use that， let's say that x is exponential。



![](img/88a13c62c199262fe7e87842b0119275_70.png)

![](img/88a13c62c199262fe7e87842b0119275_71.png)

And we'll use lambda equals1 again makes the math easy。

 so the probability that x is greater than or equal to a。



![](img/88a13c62c199262fe7e87842b0119275_73.png)

![](img/88a13c62c199262fe7e87842b0119275_74.png)

Is less than or equal to one。

![](img/88a13c62c199262fe7e87842b0119275_76.png)

Over a， that's Markov， right， so this is Markov。

![](img/88a13c62c199262fe7e87842b0119275_78.png)

Right。And so。

![](img/88a13c62c199262fe7e87842b0119275_80.png)

If I now do the probability。

![](img/88a13c62c199262fe7e87842b0119275_82.png)

That x is greater than a。

![](img/88a13c62c199262fe7e87842b0119275_84.png)

And I use Cheby chves。 Well， I can say that that is going to be the same as saying the probability that x。



![](img/88a13c62c199262fe7e87842b0119275_86.png)

![](img/88a13c62c199262fe7e87842b0119275_87.png)

inus1 is greater than or equal to a minus1。

![](img/88a13c62c199262fe7e87842b0119275_89.png)

All I've done is added minus1 to both sides， but this has now made this x minus the mean x minus the mean。



![](img/88a13c62c199262fe7e87842b0119275_91.png)

![](img/88a13c62c199262fe7e87842b0119275_92.png)

So that is saying it is that value is。

![](img/88a13c62c199262fe7e87842b0119275_94.png)

E。I。

![](img/88a13c62c199262fe7e87842b0119275_96.png)

Less than or equal to the probability that。

![](img/88a13c62c199262fe7e87842b0119275_98.png)

Absolute value of x minus1。Is。

![](img/88a13c62c199262fe7e87842b0119275_100.png)

Greater than or equal to。A minus1。

![](img/88a13c62c199262fe7e87842b0119275_102.png)

And so then by chby sves， we can say that that is less than or equal to the variance， which is one。



![](img/88a13c62c199262fe7e87842b0119275_104.png)

![](img/88a13c62c199262fe7e87842b0119275_105.png)

Over。A-1。

![](img/88a13c62c199262fe7e87842b0119275_107.png)

Squared and so hopefully you'll see that the a right being a number here。

 that that squared becomes a larger denominator than under Markovs。

 so we end up getting a tighter upper limit on probability using chbyev's inequality than we do using Markovs。



![](img/88a13c62c199262fe7e87842b0119275_109.png)

![](img/88a13c62c199262fe7e87842b0119275_110.png)

![](img/88a13c62c199262fe7e87842b0119275_111.png)

Okay， so just to show you that pictorially， if here is my number line and this was the value for1 over a。

 then this would be the value for one over a minus1 squared and so that is Chebuchav's inequality and how we can get a tighter view or a tighter upper limit。



![](img/88a13c62c199262fe7e87842b0119275_113.png)

![](img/88a13c62c199262fe7e87842b0119275_114.png)

![](img/88a13c62c199262fe7e87842b0119275_115.png)

![](img/88a13c62c199262fe7e87842b0119275_116.png)

![](img/88a13c62c199262fe7e87842b0119275_117.png)