# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P40：39_假设检验的贝叶斯解释示例.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/4315ce0ce96127076fa24132a56d214f_0.png)

So as discussed in the Bayesian interpretation， we need priors for each hypothesis。



![](img/4315ce0ce96127076fa24132a56d214f_2.png)

In this case， we randomly chose the coin that we were going to flip， whether it was 0。5 or 0。7。



![](img/4315ce0ce96127076fa24132a56d214f_4.png)

So we're going to say that our prior estimate of each one of these values of the chances of choosing either 0。

5 or 0。7 are each going to be a half。

![](img/4315ce0ce96127076fa24132a56d214f_6.png)

![](img/4315ce0ce96127076fa24132a56d214f_7.png)

Since we have no way before seeing the data to determine the coin that was actually chosen。

 we say that it was a 5050 chance that we're going to either choose 0。5 or choose 0。7。



![](img/4315ce0ce96127076fa24132a56d214f_9.png)

![](img/4315ce0ce96127076fa24132a56d214f_10.png)

![](img/4315ce0ce96127076fa24132a56d214f_11.png)

Now， we can imagine that if we were just pulling a coin from the general public。

 our prior distribution， given our knowledge of coins。

 would probably put a lot more weight in our prior distribution to having a fair coin and therefore make it much harder to actually come up with the hypothesis that you are going to accept。



![](img/4315ce0ce96127076fa24132a56d214f_13.png)

![](img/4315ce0ce96127076fa24132a56d214f_14.png)

![](img/4315ce0ce96127076fa24132a56d214f_15.png)

![](img/4315ce0ce96127076fa24132a56d214f_16.png)

That there is actually an unfair coin。

![](img/4315ce0ce96127076fa24132a56d214f_18.png)

So note that in our example， we're going to be assuming some knowledge of the bases rule。

 we're going to be using our priors， pH1 and pH2， as we just saw before。

 those are both going to be equal to 50% or one half。



![](img/4315ce0ce96127076fa24132a56d214f_20.png)

![](img/4315ce0ce96127076fa24132a56d214f_21.png)

![](img/4315ce0ce96127076fa24132a56d214f_22.png)

And we can see how we're going to use our priors to come up with our posterior distribution。

 our ultimate guess that we're going to have， which is the left hand side of this equation。

 The probability of H1， one of our hypotheses， given the data that we saw。

 and that's going to be the X。 And we're going to base that off of the probability of the data that we had。

 given that we are working with the hypothesis of H1。 So H1 being 0。5。

 what is the probability of getting three heads， given that we have a fair coin。



![](img/4315ce0ce96127076fa24132a56d214f_24.png)

![](img/4315ce0ce96127076fa24132a56d214f_25.png)

![](img/4315ce0ce96127076fa24132a56d214f_26.png)

![](img/4315ce0ce96127076fa24132a56d214f_27.png)

![](img/4315ce0ce96127076fa24132a56d214f_28.png)

![](img/4315ce0ce96127076fa24132a56d214f_29.png)

![](img/4315ce0ce96127076fa24132a56d214f_30.png)

So that's the data， the probability given the data。

 and then we're going to multiply that by our prior distribution and then we that prior distribution again。

 we just have set to 5050 and that will all be over the probability of the data being。



![](img/4315ce0ce96127076fa24132a56d214f_32.png)

![](img/4315ce0ce96127076fa24132a56d214f_33.png)

![](img/4315ce0ce96127076fa24132a56d214f_34.png)

Chosesn over all possible hypotheses， don't worry about the denominator just yet it's not going to be important in terms of determining the likelihood ratio。



![](img/4315ce0ce96127076fa24132a56d214f_36.png)

![](img/4315ce0ce96127076fa24132a56d214f_37.png)

So this will translate to the ratio we just saw of probability of the data that we have given H1 over the probability of the data given H2。

 the only difference here is that we would actually be also factoring in the prior probabilities so here it's 5050 so 0。

5 over 0。5 just cancels out to 1， but if we imagine the example we gave where we're pulling from the general public。



![](img/4315ce0ce96127076fa24132a56d214f_39.png)

![](img/4315ce0ce96127076fa24132a56d214f_40.png)

![](img/4315ce0ce96127076fa24132a56d214f_41.png)

![](img/4315ce0ce96127076fa24132a56d214f_42.png)

We may have 0。99 over 0。1， which will require a pretty large value in your denominator in order to say that the 0。

7 was more likely。

![](img/4315ce0ce96127076fa24132a56d214f_44.png)

![](img/4315ce0ce96127076fa24132a56d214f_45.png)

![](img/4315ce0ce96127076fa24132a56d214f_46.png)

So that's how that prior distribution really comes into play。



![](img/4315ce0ce96127076fa24132a56d214f_48.png)

So our priors， as we just mentioned。

![](img/4315ce0ce96127076fa24132a56d214f_50.png)

Those prior distributions are multiplied by the likelihood ratio。

 which we defined a few slides prior， and that likelihood ratio does not depend on the priors。

 That's just according to the data that we had to see the likelihood of getting。



![](img/4315ce0ce96127076fa24132a56d214f_52.png)

![](img/4315ce0ce96127076fa24132a56d214f_53.png)

![](img/4315ce0ce96127076fa24132a56d214f_54.png)

Each set of data getting three heads， given the coin of choice。



![](img/4315ce0ce96127076fa24132a56d214f_56.png)

And that likelihood ratio will tell us how we should update those priors。

 so we're going to multiply our priors in reaction to seeing the given set of data。

 and that will give us our posterior distribution。

![](img/4315ce0ce96127076fa24132a56d214f_58.png)

![](img/4315ce0ce96127076fa24132a56d214f_59.png)

![](img/4315ce0ce96127076fa24132a56d214f_60.png)

So what do we go over in this section？We discuss some of the basics of hypothesis testing with the alternative and nu hypotheses。



![](img/4315ce0ce96127076fa24132a56d214f_62.png)

![](img/4315ce0ce96127076fa24132a56d214f_63.png)

We showed how the Bayesian form of hypothesis testing and how it will depend on the prior distributions along with the likelihood ratio of our null。

 an alternative given our data。

![](img/4315ce0ce96127076fa24132a56d214f_65.png)

![](img/4315ce0ce96127076fa24132a56d214f_66.png)

And then finally， we use coinintass example to bring home the Bayesian form of hypothesis testing。



![](img/4315ce0ce96127076fa24132a56d214f_68.png)

![](img/4315ce0ce96127076fa24132a56d214f_69.png)

So next section， we will continue to talk about hypothesis testing and how that comes into play with frequentist approaches。



![](img/4315ce0ce96127076fa24132a56d214f_71.png)

![](img/4315ce0ce96127076fa24132a56d214f_72.png)