# 【加州大学圣地亚哥分校】使用Python进行数据科学中的概率与统计--Probability-and-Statistics-in-Data-Science-p43-11-03-03-大数定律的弱形式--BV1gJFDzkEPg_p43-

Hello and welcome back。In the previous lectures， we talked about Malov and Chebyev's inequality。

 and now we would like to apply them to get the weak law of large numbers。

So first a little bit of motivation so probability theory is based on the fact that sample averages converge to their expectation we've seen this in the definition of probability and definition of expectation they reflect real expectation what we think we see as an average so more specifically if we flip many fair coins then a fraction of heads that we'll see will converge to1 half and if we're all many dice then the average value will converge to 3。

5 but so far it was just intuition we just said oh that should be the case if I flip many coins then I should get roughly half and what we want to do now is make it more rigorous and see why that is the case so first let's define the sample mean so if we observe a sequence x1 up to xn we're going to use the abbreviation x superscript n to den this sequencer just。

AbbreviWe've actually used this in the past as well。

And the mean which we will den note by x this vector xn bar is just the average of all the values of x1 up to xn so it's the sum x1 plus x2 up to xn normalized by the number of samples which is n so for example if n is4 and we take four samples and x4 is 3142 then the average of this x4 vector is going to be the sum 3 plus 1 plus 4 plus 2 which is 10 divided by 4 which is 2。

5 so the average of these four samples is just 2。5 Now what we're doing is we're taking n samples from a distribution and therefore what we willll get is a sequence not of xn of small xn actual numbers but we have a sequence of random variables x1 up to xn which will still denote by x superscript n like that。

And the sample mean is now the average of this random vector x1 up to xn。

 so it's the sum of x1 plus x to those all those n random numbers normalized by n and this now note that this Xn average is the random variable and it's the sample mean that will observe it's a random mean depending that depends whose value depends on the samples that we get。

Okay， and what we would like to do is we like to say that the average of the sample mean is very close to what it should be。

 namely if all of these have mean mu， then it's close to me。Okay， so just。To specify this precisely。

 let's talk about independent samples， so if we have independent random variables with the same distribution。

 then we call them independent， identically distributed or IID independent identically distributed。

 for example， if we have independent Bernoulli 0。3 randomino variables。

 then we said that we have IID Brnoulli 。3 random variables or just we said we have IID random variables because the identical。

 each of them has the same distribution， beernoulli 0。3 and independent Swol。So more specifically。

 suppose that x1 x to x3， suppose we're told it II do Bernoli 。3， what does that mean。

 that means that each of the Xi is Bernoli 。3 and each of them is independent of all the others。

And in particular， what that would mean is that if that's the case， if x1 x2 x3 or Brurnoulli 0。3。

 then the probability that x1 is1 x2 is 0 and x3 is 1 is just because by dependence。

 it's the product of the probabilities and because each of them is Brnoulli 0。3 it's going to be 0。

3 times 0。7 because this one is 0 times 0。3 which is 0。 063。

Okay so so now we can talk about the recall of large numbers and what does it said。

 it says that if you have a sequence x1 up to xn which you call red denote by x n。

 so if a sequence of n IidD samples from a distribution with finite mean mu and finite standard deviation sigma okay if that's the case so all of them we have n samples from the same distribution with mean mu and standard deviation sigma then as the number of sample goes to infinity。

 then the average xn approaches mu。In the sense that the probability that the sample mean differs from the mean mu by any given amount goes to0 as n increases so more specifically what I't mean。

 so x and average is the sample mean x is a random variable and what it says is the probability that the sample mean that will observe differs from mu。

In absolute value by more than epsilon， that probability is at most the variance of the distribution。

To give it。Most the divided by this epsilon square times 1 over n。So what you can see is that Sn。

Increases， this will go to0， so it it says that just want to make sure we understand。

 so we have a sample xon up to xn， the sample from the same distribution with mean mu and standard deviation sigma then the probability that the average will differ from the mean by more than any amount epsilon is that most the variance divided by epsilon square it will this probability will increase as epsilon so we want the average to close to mu by epsilon square times1 of variance so we can n large enough。

To make sure that this quantity is and as small as we want。

So we will say that XN converges in probability we'll discuss this more formally to mu。

 but we don't need to understand this definition to understand the weak law large numbers which again just says that the probability that the average will differ from the from the mean by more than any amount is this quantity here which is an increases goes down to zero so what we're going to do is we're going to give an example of using this law and then we're going to prove it and then we're going to give yet another example so let's start with the example and of course we haven't yet visited the 2016 presidential elections or maybe it's time so suppose you try to predict the outcome of the election and more specifically maybe you try to see how many people or what fraction of the people are going to vote for Donald Trump so you poll 100。

000 people。And let's assume that every person votes for Trump independently of all others with probabilityP。

 so every person that's you sample is independent of others and votes for Trump with the same probabilityP。

Okay， then we want to bound the probability that we are off， we're trying to estimate P。

 we want to bound the probability that we off from P by more than 1%。

 namely that we get p plus minus 1%。So the weak law log normally tells us that the probability that the average that we'll get for the number of people who are going to vote for Trump minus mu and mu here is P is going to be bigger than epsilon is less than equal to sigma square over epsilon squared times 1 over n。

 that's the general weak law log number and we applied here and here。The variance。

 when we pull each person is。They have a probability P voting for Trump and one minus p for not voting for Trump and as we know this is a Bernolia rhinover whose variance is p times 1 minus p and p times 1 minus p as we have said is at most one quarter。

 so sigma squares at most one quarter so therefore the probability that the average of 100。

000 people because that's how many people with sample minus p is bigger than 0。

01 that's a tolerance that we are wondering about， so were sampling we are sampling we're checking every person we devoted for Trump or not we're adding every percent that voted for Trump。

 take the average。And that's this number here probably that it differs on p by more than 0。

01% is going to be at most sigma square， which as we saw is at most a quarter divided by this quantity epsilon square。

 so 0。01 square and by n so what we have here is one quarter and this 0。

01 square will give us 10000 here in the numerator so it's going to be one over10 divided by 4 which is one over 40 or 2。

5%。So we see that the probability that will be off by more than 1% is at most 2。5%。

 which may be not so bad。And notice that if we poll more people。

 then the probability that will be off by more than 1% would decrease like that。

Okay so now that we have seen an example of the weak lo large number which is written again here。

 the probability that the average differs from the mean by more than epsilon is at most the variance divided by epsilon square divided by n notice that it behaves in the right way if the variance increases then the probability that will be off from the mean by any given number it will increase and also if we want。

To be more accurate then epsilon has to decrease， and therefore the probability that will be off by more than epsilon will increase。

And also as and the number of sample increases， the probability decreases so now we want to prove this and then we'll do another example。

 so the proof of this equation the probability that xn minus mu is bigger than equal to epsilon is at most sigma square over n epsilon square。

Is actually quite simple， so again， recall that x1 x2 and so on I we finite mu and sigma and the sample mean is xn which is 1 over n。

Time summation of Xi， and I'm justbbrevibbre abbreviating the sum from my equals to one f2 n by just the sum。

Okay， so what is the expected value of the mean so the mean is a random variable and what is its expectation。

 the expected value of the mean is the expected value of the average， which is one over in sum X。

And we can take one over n out， so it's 1 over n and then we can take the expectation inside a sum by the linear of expectation。

 so it's one over n summation of the expectation of X。But each X we're told has mean mu。

 same mean mu， so it's one over n summation of mu and there are n of them， so this gives us mu。

 so the expectation of the average is just mu which is not surprising we took n samples each with mean mu so the mu mean of the average is also mu and what is the variance。

 the variance of Xn is the variance of again the average one over n summation X。

But so the one over end comes out。And we have one of the variance of the summation X。

 but now the Xs are independent， see the IID and the first I stands for independent。

 so the variance of the summation is summation of the variances。

 so it's one over n summation of the variances and each has a variance of sigma。

So it's going to be one over n square times n sigma or1 over n squared times n sigma square sorry。

 which is sigma squared over n。So the nice thing is that the variance is added linearly。

 so they gave us n times sigma squared but we normalized by n squared， so the variance of the mean。

 as we see now decreases with n， so we observe that what we get is that the average will always have the same mean mu。

 but the variance of the average will decrease。Like sigma square over n。

 And now we can use Cheby sheev's inequality， which tool tells that for epsilon。

 the probability that xn minus its mean will be bigger than epsilon。

 Okay so this is our random variable， it's mean is mu as we calculate it。

 and the probability that is going to be bigger than equal to epsilon by chby's inequality is that most the variance of xn of the average of xn divided by epsilon square。

 but the average decreases with n like that。 So it's at most sigma square over n divided by epsilon squared。

 that's just straight chby she's inequality。 And you can see that as n increases。

 this probability that will be off by any given amount will go down。 so it' n goes to infinity。

 this will go down to 0。 So this is the simple proof of the weaker of large number。

 which which is quite important because we don't need to assume anything about the random variabless。

 just anything about the distribution。 just the Iod and mean and standard deviation sigma so。

So we're going to look at sensors and ask the opposite question rather than saying here's the number of measurements we have what is the error that we get we'll say if we want to give an error。

 how many measurements do we need to take so suppose we are trying to measure a temperature and we do it by using n sensors and each sensor has makes some mistake so each of them reads the temperature as t plus Z and that's the temperature that it reads with Z some noise which has zero mean and variance less than equal to2 so we'll get the noise plus I'm sorry the real temperature plus noise which has zero mean and some variance and the question is how many sensors do we need in order to estimate the temperature to within half a degree with probability bigger than 95%。

So again we'll use the weakl large numbers， it says that if we take the average of all these measurements。

 then the probability that the average will differ from the mean by more than epsilon in our case more than 0。

5 will be at most the variance which is 2 divided by this epsilon square 。

5 square and then again divided by the number of samples that we take so in our case the probability that the average temperature will differ from its mean and notice that the mean because z is 0 mean then the mean of ti is the same as t。

 so the probability that the average of all the temperatures will differ from t by more than 0。

5 by the weakl large numbers at most the variance which is 2。Divided by Epon Square。

 which is a quarter。Because this is epsilon。And divided by n okay and what we want to do is we want to make sure that this is less than 5% so that the probability will be sorry the error probability is at most 5% so that the probability of being correct will be at least 95%。

Okay， so if we want that to happen， we need to make sure that n is at least。

2 divided by quarter and divided by 0。05， which is 2 times 4 times 20， which is 160。

 so if we have 160 sensors， then we can guarantee that the probability will be at most of by more than half percent is smaller than 5% or the probability that will be within 0。

5% is at least 95%。Okay， so the probability will be within plus minus half of a degree is at least 95%。

Right and notice that the rec large numbers can be generalized so the same proof works where instead of each random variable have the same mean and the same standard deviation。

 we can have different means and different standard deviations。

 we just let the mean of the whole samples be the summation of mui divided by n just the average of the muI。

And the mean of the variance be one over n time summation of the variances， summ sigma i square。

 and then we can use the exact same proof to see that even in this small general case。

 the probability that the average will differ from mu this mu that we defined here by more than epon will be this sigma square summation of the sigma I divided and divided by n divided by epson square and by n so the recall of large numbers actually applies a little more broadly。

All right， so I want just want to end this presentation by describing convergence in probability which is actually what we have proven。

 but we didn't give it a name because I just won' to keep it as simple as possible。

 so if you have a sequence x1 x2 of random variables and then we said that this sequence convergeence in probability to another random variable y。

If the probability that Xn， this re variable differs from y by any fixed amount decreases to 0 with n。

 almost more specifically for every delta。Bigger than0， the probability that x n minus y。

 this n random variable will differ from y。By more than delta goes down to0 with n。

 or more specifically for every delta bigger than0。

 that's what's written here now'm just making this spot more precise for every epsilon bigger than0 there is an n such that for n bigger than that the probability that x n minus y is bigger than equal to delta that probability is less than epsilon。

 so what we want is that if someone gives you any epsilon and delta the probability that xn。

So fall sufficiently large n， the probability that Xn differs from y by more than delta that probability is less than epsilon。

 it can make any of them go down spicy one so if that happens we said that the sequence xn converges to y in probability and what we have shown with the weak of large numbers is that we have shown that sorry we have shown that the average the sample average xn converges in probability to the mean。

 so that's what we have shown although we didn't use the terminology so with that we talked about the weak of large numbers and what we want to do next is we want to provide stronger bounds what we have shown now via the churn of bound and the moment generating functions。



![](img/3a95ff1285fa6d0918d1fd84d696a156_1.png)

See you then。

![](img/3a95ff1285fa6d0918d1fd84d696a156_3.png)