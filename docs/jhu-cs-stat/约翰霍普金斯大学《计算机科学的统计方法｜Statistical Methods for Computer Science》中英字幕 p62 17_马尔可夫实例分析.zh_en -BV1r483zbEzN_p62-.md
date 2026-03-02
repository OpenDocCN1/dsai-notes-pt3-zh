# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p62 17_马尔可夫实例分析.zh_en -BV1r483zbEzN_p62-

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_0.png)

All right， we're still talking about Markov's theorem。

 so in previous video I went over proof of Markov's theorem and now we're going to do some examples。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_2.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_3.png)

So。We'll start with。Example。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_5.png)

So let's say R equals the weight of a random person。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_7.png)

So suppose the expected value of R equals 100。 I know that's probably not a realistic weight。

 but the math is easier。 so expected value of is 100。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_9.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_10.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_11.png)

The probability。That you would then find R greater than or equal to 200。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_13.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_14.png)

So what's the likelihood that you're going to find somebody that's greater than 200？



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_16.png)

Pounds in this situation that is going to be less than or equal to the expected value of R。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_18.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_19.png)

Divided by a。Ex value of R divided by a。 So in this case， that would be 100。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_21.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_22.png)

Divided by 200。And so we would say that the probability is less than or equal to。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_24.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_25.png)

Well， I guess not that one。 We would then say that the probability R is greater than or equal to 200。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_27.png)

Is less than or equal to 0。5。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_29.png)

Okay。muchuch lower than the probability red my shirt。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_31.png)

So with the corollary， so with the corollary。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_33.png)

We can also use the corollary。So in that situation。

 the probability that r is greater than or equal to 200。

In this case is equivalent to the probability。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_35.png)

That R is greater than or equal to。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_37.png)

Two times the expected value of r。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_39.png)

See why the math is easy right， so two times the expected value of R is we know that's going to be less than or equal to 1 over C6。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_41.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_42.png)

1 over C。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_44.png)

So in this case， we see that that2 is the C from the corollary。

 so the probability that R is going to be greater than or equal to 200 is equal to sorry it is。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_46.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_47.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_48.png)

Less than or equal to1 over 2 which is the same as 0。5。

 just depends on whether you're really a millennial or not， because you see like people my age。

 we like to think of fractions as our friends because it actually makes the math a lot easier but millennials like you'all learn how to use calculators in school and so now you just don't even understand what a fraction means and it's really sad to me。

 but that's okay。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_50.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_51.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_52.png)

Okay， we're going to do another example。😊。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_54.png)

So sometimes we'll use we'll find data that is an exponential random variable。

 So an exponential random variable is often used for inner arrival times。

 So you'll see that if you look at people coming to a bank teller actually I guess you guys all use ATMs and online banking these days。

 but assume you go back in time and you actually walk into the bank to go to the teller to get your money or do whatever you got to do。

 you'll find that the inner arrival time， there'll be a rush of people that'll all show up and get in line just in front of you and that'll happen like within seconds boom boom boom and then there'll be this long period of time before the guy comes in line behind you right And so you'll see that the distribution kind of has this skewness I'll just write it up over here where you see that the data has a lot of values are going to be very。

 very small very short times in between。 But then occasionally you'll get one of these long values out here and you have this huge skewness into the data。

 So that's the example classic example of a rare event。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_56.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_57.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_58.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_59.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_60.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_61.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_62.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_63.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_64.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_65.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_66.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_67.png)

So if I do an example here where I'm going to say that x is exponential。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_69.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_70.png)

X is exponential， and I'll make lambda the parameter of that exponential equal to one。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_72.png)

Then。Then basically what I'm saying is the probability。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_74.png)

That x。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_76.png)

Is going to be greater than。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_78.png)

Or equal to some value a。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_80.png)

Is going to be less than or equal to the expected value of x over a。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_82.png)

Expected value of x over a。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_84.png)

Right。And so then because lambda equals 1， we know that the expected value in this distribution exponential。

 we know that for an exponential distribution， the mean value is one。

 So what that tells me is that the probability that x is going to be greater than or equal to some value A is less than or equal to 1。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_86.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_87.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_88.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_89.png)

Over that value， a。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_91.png)

RightAnd so that would be an upper bound then on the probability of observing a particular value。

 So you want to know， well， what's the likelihood， the probability that somebody is going to be in my waiting time is going to wait longer than some value here。

 what's the probability that somebody is going to wait an extraordinarily long time before they get served at my bank。

 Well， the probability that somebody's going to have to wait longer than like， say。

 15 minutes is going to be one over 15 minutes if that's indeed the average time for somebody to go through a bank。

 So that's an example of how you would use that and identify an upper limit。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_93.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_94.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_95.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_96.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_97.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_98.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_99.png)

Here's another example。Say， we have。X。Is uniform？Next is uniform and it's uniform over the range negative 4 to4。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_101.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_102.png)

Then the question is， what's the probability？

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_104.png)

That x is going to be greater than or equal to3 on this uniform distribution well。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_106.png)

The probability。Probability。That。X is going to be greater than or equal to 3。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_108.png)

Is less than or equal to the expected value。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_110.png)

Of this。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_112.png)

Divided by。Divided by。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_114.png)

3。And that is going to be equal to， so that's basically saying that value right and following the same formula we wrote up here。

 it's the expected value of the absolute value of x over  three。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_116.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_117.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_118.png)

And so the expected value there is going to be 2。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_120.png)

Over。3， right， because you expected the is what we end up having。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_122.png)

Probability。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_124.png)

That。😔，X is greater than and or equal to 3。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_126.png)

Is going to equal。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_128.png)

1 half。The probability that the absolute value of x。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_130.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_131.png)

Is greater than or equal to3。RightAnd so then that would equal one half times。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_133.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_134.png)

Two thirds。Would equal one third。So the probability。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_136.png)

That x is greater than or equal to 3。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_138.png)

Is going to be less than or equal to one half times two third。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_140.png)

Wder。Okay， so what we've done for the uniform is it's easier for us to say， hey。

 if I look at it's a uniform distribution 0 to 4， right。

 we know that the expected value there would be halfway through， which would be 2， because otherwise。

 I'm gonna get a 0。 And it's gonna be kind of weird。

 So that's why we retreat it in absolute values for uniform distribution。

 especially when it's symmetric， right， But you kind of just want to look at the positive in the negative side and combine those as we've done here for the uniform。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_142.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_143.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_144.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_145.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_146.png)

。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_148.png)

So there's another corollary I'll introduce and then one more example。

 so the other corollary we're going to introduce is。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_150.png)

If。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_152.png)

So if for R less than or equal to u， for some u in the set of real numbers。

 then for all xs less than u。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_154.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_155.png)

The probability。Of x being greater than or equal to 3， sorry。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_157.png)

So if R is less than or equal to u for some u in the set of real numbers， then for all x less than u。

 the probability that R， this random number is going to be less than or equal to value x is equal to the probability of u minus R。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_159.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_160.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_161.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_162.png)

Greater than or equal to u minus x。And you'll see that in this situation， U minus R。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_164.png)

Is always。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_166.png)

Always。Non negative。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_168.png)

Right， it's always known negative。 So that means I can apply Markov theorem to this problem。

 and I can say that the expected value。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_170.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_171.png)

Of。U minus R。Divided by u minus x。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_173.png)

Is equal then- so I can apply Markov's theorem there is equal to U because u is constant。

 right I can use the linearity of expectation to say u。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_175.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_176.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_177.png)

Minus the expected value of R。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_179.png)

Over u minus x。And so then I have a corollary。 and what that allows me to do is our last example here on this is R。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_181.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_182.png)

Let's say r equals the score。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_184.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_185.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_186.png)

R is a score of a random student。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_188.png)

And the max score。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_190.png)

equals 100。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_192.png)

And let's suppose one more thing that the expected value of R is going to equal 75。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_194.png)

It's a low performing class， I think that should be higher， but it's good for you。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_196.png)

So。What's the probability？The probability。That x is less than or equal to 50。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_198.png)

Hopefully， that's not you。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_200.png)

Well， we can say that that is going to equal u minus the expected value。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_202.png)

Over u minus x。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_204.png)

And so then that would end up equaling 100 minus 75。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_206.png)

Over。100-50。And then， that ends up equaling。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_208.png)

25 over 50 or one half because fractions are your friends， the math is easier that way。 right。

 So what this allows us to do is if we're looking for a rare event where typically grades are。

 are centered around， you know， the 80s with some 90s and 70s thrown in there。

 So then what's the rare event that something is very much smaller right than than that area。

 So we can then use this corollary of Markov's theorem to be able to say the rare event of getting something smaller。

 Okay So what we've what we've just been talking about of the last two videos。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_210.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_211.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_212.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_213.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_214.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_215.png)

Has been the likelihood of seeing a rare event and what that can do to your estimation because it's skewed right if we remember from the exponential distribution。

 we even have this memoryless property， which basically means you cannot judge future events based on what's happened in the past so we kind of have a prediction problem So when we're trying to predict the likelihood of a rare event and evaluate probabilities with these skewed distributions it or these extreme values。

 it can be very difficult or problematic and so what Markov's theorem does is it allows us to at least place an upper limit on the probability so that we can actually then draw some sort of decisions on on the risk we're going to be exposed in these situations。



![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_217.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_218.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_219.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_220.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_221.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_222.png)