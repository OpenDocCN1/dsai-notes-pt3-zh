# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P38：37_假设检验简介.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this section， we're going to introduce the concept of hypothesis testing。

Our learning goals for this section will be two。Go over what hypothesis testing is。



![](img/801b16578f9c92446c5a037f38d6feb5_1.png)

Discuss the Bayesian approach to hypothesis testing。



![](img/801b16578f9c92446c5a037f38d6feb5_3.png)

And then begin to motivate this with an example using coin flips。

 which you'll see towards the end of this section。

![](img/801b16578f9c92446c5a037f38d6feb5_5.png)

So a hypothesis is a statement about a population parameter。

 such as the mean of our Poson distribution in our estimate of the number of people that will come into the line for our grocery store example in the next hour。



![](img/801b16578f9c92446c5a037f38d6feb5_7.png)

![](img/801b16578f9c92446c5a037f38d6feb5_8.png)

![](img/801b16578f9c92446c5a037f38d6feb5_9.png)

We create two hypotheses， we start off with a null hypothesis and an alternative hypothesis。



![](img/801b16578f9c92446c5a037f38d6feb5_11.png)

![](img/801b16578f9c92446c5a037f38d6feb5_12.png)

And we decide which one to call the null， depending on how the problem is set up。

 So an example would be that we get an average of five people coming in per hour and the alternative may be being greater than five。

 so any number greater than five would be the alternative with just five being the null。

 or it could be a specific amounts of people such as five being the null and 8 being the alternative。



![](img/801b16578f9c92446c5a037f38d6feb5_14.png)

![](img/801b16578f9c92446c5a037f38d6feb5_15.png)

![](img/801b16578f9c92446c5a037f38d6feb5_16.png)

![](img/801b16578f9c92446c5a037f38d6feb5_17.png)

![](img/801b16578f9c92446c5a037f38d6feb5_18.png)

Now， if one of those values is less specific， for example。

 such as greater than five or not equal to5， that will usually be the alternative。

 whereas the null will be the specific value。

![](img/801b16578f9c92446c5a037f38d6feb5_20.png)

![](img/801b16578f9c92446c5a037f38d6feb5_21.png)

![](img/801b16578f9c92446c5a037f38d6feb5_22.png)

So given the data from the sample we use， we then use a hypothesis testing procedure to decide whether we're going to accept the null hypothesis or reject the null and accept the alternative。



![](img/801b16578f9c92446c5a037f38d6feb5_24.png)

![](img/801b16578f9c92446c5a037f38d6feb5_25.png)

Now it's often said that you can reject the null， but never accept the alternative。



![](img/801b16578f9c92446c5a037f38d6feb5_27.png)

Here we're just saying for practical purposes， when moving forward with your project。

 you'll be taking the path that the alternative is true depending on your test statistic。



![](img/801b16578f9c92446c5a037f38d6feb5_29.png)

![](img/801b16578f9c92446c5a037f38d6feb5_30.png)

Now， in the Bayesian interpretation， we won't get a decision boundary。



![](img/801b16578f9c92446c5a037f38d6feb5_32.png)

![](img/801b16578f9c92446c5a037f38d6feb5_33.png)

Rather， we'll get posterior probabilities of the null and the alternative hypotheses and see which one is more likely。



![](img/801b16578f9c92446c5a037f38d6feb5_35.png)