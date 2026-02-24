# 宾夕法尼亚大学《人工智能和机器学习基础（AI、数据科学、机器学习）AI and Machine Learning Essentials with Python》 p63 28_04_01_方差估计-有偏与无偏第二部分.zh_en -BV16f421Q72q_p63-

Let's now see whether or not the estimator that we designed for the variance is biased。Okay。

 so that's right。 The expectation of our estimate， which is one over n。Some I from one to end。

X I minus x bar to the power 2。Okay， this would be expectation of1 over n。

Let me just open the square here。 So that would be X squared plus x bar squared minus2 X x bar。

And remember expectation is a linear operator expectation and sum always exchange from each other expectation of a sum of things would be the sum of their expectation。

 so this would be written as 1 over n sum i from 1 to n E of X squared。Plus。

 now explore squared is the same term in all the sums in this sum。

 So that would be just expectation of。Export a squared n and n cancel minus。2。😔，Times harm。😔。

Expectation。Of1 over n， some I from one to n。X I X bar。Okay， now X I is are I Id。

 So expectation of X I squares， all of them are the same。 so I can just write the first term as。



![](img/f072d0107e099ca97a751a4b908c6a8e_1.png)

Expectation of， let's say， x squared or expectation of x squared plus expectation of x bar squared。

inus two times expectation。 Now， here in this sum at the top。



![](img/f072d0107e099ca97a751a4b908c6a8e_3.png)

All the sums have the same term X bar， so X bar would be just factor out。

 so that would be expectation of x bar times1 over n sum X Is i from 1 to n。



![](img/f072d0107e099ca97a751a4b908c6a8e_5.png)

But furthermore， note that this the average of Xs is denoted by x bar， right。

 so this would be just expectation。Of x1 squared minus expectation of x power squared。

-2 times expectation of x bar squared， which gives me the expectation of xon squared minus expectation of x bar squared。

Now， I need to compute each of these terms。Okay。Let me just open app parenthees。

 remember that for any random variable y。ExThe variance of y。 So variance of any random variable Y。

 So y here is a generic random variable。 the variance of y would always be equal to the expectation。

That's just a known formula of y is squared minus expectation of y to the power 2。 Okay。

 this is a formula that holds for any random variable y， So the variance。

Is computed from this formula。 So in this sense， let me just compute the variance。A。Of x1。

And related to the parameters。That we have the variance of x1。 remember。

 is essentially sigma squared。 so it's the variance of the data and is' given by expectation of x1 squared。



![](img/f072d0107e099ca97a751a4b908c6a8e_7.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_8.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_9.png)

Minus。Expectation of x1 to the power 2。 Okay， expectation of x1 is the mean of the population。

 So this would be just expectation of x1 is squared minus mu squared， right？ So this means that if。

 if you note here， expectation of x1 squared is just the variance plus mu squared。

 So sigma squared plus mu squared。

![](img/f072d0107e099ca97a751a4b908c6a8e_11.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_12.png)

Okay。And you can just repeat the same thing for。

![](img/f072d0107e099ca97a751a4b908c6a8e_14.png)

For exp。So， expectation of squared。

![](img/f072d0107e099ca97a751a4b908c6a8e_16.png)

Would be equal to the variance of x bar。

![](img/f072d0107e099ca97a751a4b908c6a8e_18.png)

Plus E of x squared。 Okay， now for x bar， we already know everything。

 So the variance of x we have computed before， it was remember。

 sigma squared over n and E the expectation of X bar， remember。



![](img/f072d0107e099ca97a751a4b908c6a8e_20.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_21.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_22.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_23.png)

Xpo was anumbas estimator of mu。 So expectation of x was exactly mu。

 And this we had computed before So as sigma squared over n plus mu squared。

 So let me just plug in these values here。 So expectation of x and squared would be sigma squared。



![](img/f072d0107e099ca97a751a4b908c6a8e_25.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_26.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_27.png)

Plus muu squared， an expectation of x squared would be sigma squared over n。Plus mu squared。 Okay。

 so in the end。So the difference here would be sigma squared times 1 minus1。So， as you see here， the。

Expectation of。Or estimating member dispo sigma2 bar or estimate for the for the value of the variance in expectation is not exactly equal to the variance。

 It's not exactly equal to sigma squared。 is it is equal to sigma squared times a factor 1-1-1 over n。



![](img/f072d0107e099ca97a751a4b908c6a8e_29.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_30.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_31.png)

So in other words， the estimator that we design is a biased estimator。



![](img/f072d0107e099ca97a751a4b908c6a8e_33.png)

Okay。So what is the bias of our estimate or expectation。Of sigma。2 bo。Ex want to X then。

Minus sigma squared， as we computed， was sigma squared。Times 1 minus-1 over n minus sigma squared。

 And that would give me as minus sigma squared over n。 Okay， so it's nonze。

 So there is a bias here that my variable has， okay。However， so my estimator is a bias estimator。

 but there is a simple。

![](img/f072d0107e099ca97a751a4b908c6a8e_35.png)

Very simple tweak that I can do to my estimator to make it unbiased。



![](img/f072d0107e099ca97a751a4b908c6a8e_37.png)

Okay， can any of you think of what that very simple tweak it is。

 So expectation of my estimator here is is the exact value that I have one it sigma squared。

 but there is a factor1 minus-1 over n that's multiplied to it。Somehow， if I want to make it onbi。

 I have to somehow get rid of this factor， so I have to tweak my  estimateator a bit such that this factor goes away。

And in this case， there is a simple tweak that I can do I can just。this remove this factor。

 take this factor to the other side。So if I normalize my estimator by this factor 1 -1 over n。

 then the resulting estimator would be on biased。

![](img/f072d0107e099ca97a751a4b908c6a8e_39.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_40.png)

So let me just write this here， so a sigma expectation of sigma squared bar。

The estimator that I have designed so far。Is 1-1 over n s squared。

 So all I'm saying is that take this factor and bring it to the other side okay。

So this means that if I normalize。My estimator by this value，1-1 over n。

So Im dividing both sides by 1 minus1 square， and then this factor will go away essentially， right。

And this new estimate， this value here。An expectation would be exactly would give me exactly s squared。

 which is essentially unbied。So what is my final estimator， which is onbied。

 is the previous estimator that I designed。1 over n X I minus x bar to the power 2 divided by this factor here。

1 minus1 over n， right， which gives me。1， n -1。Some I from one to n。X， I minus x bar to the power 2。

So that's the final estimator that I can design for estimating the variance from data and this estimator is unbied。

 Now， let's see intuitively where this n minus-1 came from okay now。The main point here is this。

 remember。The value of the variance was expectation of X I minus essentially mu to the power2。

And we estimated it by 1 minus1 over n， sum i from 1 to n。X， I minus。First， I mean， we had two steps。

 right， So it was X I minus mu to the power too。And then we said that look mu can be also estimated by X bar right So replacing mu by X bar is where a bias will be created because once you approximate。

A muu with data itself that creates a bias here。And essentially， just to remove this bias us。

 we need to essentially normalize by1 over n minus by essentially once you replace mu by， I mean。

 as a statistician say once you replace mu by x bar you essentially are removing one degree of freedom from this problem and the number of three parameters that you have for this problem。

 now changes from n to essentially n minus-1 and essentially once you normalize by n minus-1。

 you would be able to obtain an n bias estimator for those of you who have heard about degrees of freedom。

 this is the interpretation， if you haven't heard about degrees of freedom before， no worries。

 I mean this is just your own bias estimator that you see here。Okay。

 now so we we found a very good way to estimate the variance s sigma hatta squared by thisumbbi estimator that you see here。

😊。

![](img/f072d0107e099ca97a751a4b908c6a8e_42.png)

Remember， we wanted to estimate the variance because in our confidence bound calculations we had the variance term and we didn't know essentially how to estimate it from the now we know right so what was the formula for the confidence bound so。



![](img/f072d0107e099ca97a751a4b908c6a8e_44.png)

![](img/f072d0107e099ca97a751a4b908c6a8e_45.png)

So 100 times1 minus alpha percent confidence bound for estimating the the mean of a population was the following so。



![](img/f072d0107e099ca97a751a4b908c6a8e_47.png)

The average。Or the sample mean minus Z alpha over2。Times sigma over square root。

 n that was the confidence interval and x bar plus z all over over 2 times sigma over squared root n。

 right。Now， we have a good way to estimate sigma， right， so sigma。Squared hat。

 which was an estimator for the variance。Is estimated by 1 over n minus1， some i from 1 to n。Hang。😔。

X I minus x bar to the power 2。 So the value of sigma can be estimated by the square root of this quantity here。

 Okay， so let me just take a square root。Here。And that would give me an estimator for。

The value of sigma， okay。So I have to just replace this here。Okay。So my finite confidence bound。

My final confidence bound， which is completely computable from data， would be the phone。 so expire。

inus Z alpha over 2。 I need to estimate sigma by sigma hat。This is computed from data。

 as you see here。Oh。And then x bar plus z off over 2。Sh Moha over squared。Right。

 and Sigma hat is this estimate from data that we have completed。



![](img/f072d0107e099ca97a751a4b908c6a8e_49.png)