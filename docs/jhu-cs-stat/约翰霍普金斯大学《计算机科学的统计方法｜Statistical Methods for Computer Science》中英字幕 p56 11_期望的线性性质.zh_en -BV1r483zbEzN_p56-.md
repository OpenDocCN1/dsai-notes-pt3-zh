# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p56 11_期望的线性性质.zh_en -BV1r483zbEzN_p56-

![](img/be8c6a0de1819219a1056e465a41a728_0.png)

All right， we're going to work another example。 we're going to move to more of a computer scienceency example。



![](img/be8c6a0de1819219a1056e465a41a728_2.png)

We'll say。

![](img/be8c6a0de1819219a1056e465a41a728_4.png)

Let D。Equal the delay。

![](img/be8c6a0de1819219a1056e465a41a728_6.png)

Of a packet。

![](img/be8c6a0de1819219a1056e465a41a728_8.png)

On a channel。

![](img/be8c6a0de1819219a1056e465a41a728_10.png)

Okay。And so。Now we're talking about time。

![](img/be8c6a0de1819219a1056e465a41a728_12.png)

So we're going to let f of x equal the probability that d equals the delay equals some fixed variable。

 and that will be。

![](img/be8c6a0de1819219a1056e465a41a728_14.png)

![](img/be8c6a0de1819219a1056e465a41a728_15.png)

The probability。

![](img/be8c6a0de1819219a1056e465a41a728_17.png)

Density function 4。D， okay。

![](img/be8c6a0de1819219a1056e465a41a728_19.png)

And let me draw that out， right。

![](img/be8c6a0de1819219a1056e465a41a728_21.png)

As we draw that out。This is。F of x。

![](img/be8c6a0de1819219a1056e465a41a728_23.png)

This is x。 we'll make that zero。 and so we have a function that looks something like this。

 And so in this particular case， cases of long。

![](img/be8c6a0de1819219a1056e465a41a728_25.png)

![](img/be8c6a0de1819219a1056e465a41a728_26.png)

Dewei。

![](img/be8c6a0de1819219a1056e465a41a728_28.png)

Is rare。So most of the delays， the high frequency here are very short delays。

 occasionally you'll get along the delay， but that's much less likely。



![](img/be8c6a0de1819219a1056e465a41a728_30.png)

![](img/be8c6a0de1819219a1056e465a41a728_31.png)

So if I run an experiment。

![](img/be8c6a0de1819219a1056e465a41a728_33.png)

![](img/be8c6a0de1819219a1056e465a41a728_34.png)

I'm going to run an experiment 100 times。

![](img/be8c6a0de1819219a1056e465a41a728_36.png)

And I'm going to estimate。

![](img/be8c6a0de1819219a1056e465a41a728_38.png)

The average latency。

![](img/be8c6a0de1819219a1056e465a41a728_40.png)

Sin right。嗯。

![](img/be8c6a0de1819219a1056e465a41a728_42.png)

Is equal to 10 milliseconds。 Average latency is equal to 10 milliseconds。



![](img/be8c6a0de1819219a1056e465a41a728_44.png)

And then I run the experiment again。

![](img/be8c6a0de1819219a1056e465a41a728_46.png)

![](img/be8c6a0de1819219a1056e465a41a728_47.png)

And I get 9。8 milliseconds， 9。8 milliseconds。

![](img/be8c6a0de1819219a1056e465a41a728_49.png)

So。Probability of this latency exceeding some value I， right？



![](img/be8c6a0de1819219a1056e465a41a728_51.png)

![](img/be8c6a0de1819219a1056e465a41a728_52.png)

We already know equals one over i。

![](img/be8c6a0de1819219a1056e465a41a728_54.png)

Okay。So the expected value。

![](img/be8c6a0de1819219a1056e465a41a728_56.png)

Of the latency is going to equal。

![](img/be8c6a0de1819219a1056e465a41a728_58.png)

I equals one。To infinity。

![](img/be8c6a0de1819219a1056e465a41a728_60.png)

呃。The probability。Greater than I。

![](img/be8c6a0de1819219a1056e465a41a728_62.png)

Okay。So that equals one to infinity of。

![](img/be8c6a0de1819219a1056e465a41a728_64.png)

1 over I。

![](img/be8c6a0de1819219a1056e465a41a728_66.png)

Okay， one over I。And。If we are to add that up， right。



![](img/be8c6a0de1819219a1056e465a41a728_68.png)

Then we end up because that eye is greater than one， then that's going to converge to infinity。



![](img/be8c6a0de1819219a1056e465a41a728_70.png)

![](img/be8c6a0de1819219a1056e465a41a728_71.png)

If， however。

![](img/be8c6a0de1819219a1056e465a41a728_73.png)

If， however。The probability that D greater than。

![](img/be8c6a0de1819219a1056e465a41a728_75.png)

A。

![](img/be8c6a0de1819219a1056e465a41a728_77.png)

Is equal to1 over i squared。Okay。

![](img/be8c6a0de1819219a1056e465a41a728_79.png)

Then we would have this situation where。

![](img/be8c6a0de1819219a1056e465a41a728_81.png)

Equals 1 to infinity。Of one over i squared。

![](img/be8c6a0de1819219a1056e465a41a728_83.png)

Which we know from a geometric sequence that that is roughly equal to less than or equal to2。



![](img/be8c6a0de1819219a1056e465a41a728_85.png)

![](img/be8c6a0de1819219a1056e465a41a728_86.png)

So the question is why， right？

![](img/be8c6a0de1819219a1056e465a41a728_88.png)

Right， why does this happen。

![](img/be8c6a0de1819219a1056e465a41a728_90.png)

So。When the issue is whenever you're doing something in this particular problem and you're sampling from something that is rare。

 the likelihood that when you run the experiment， right， here's the key part of this。

 the likelihood is that when you run an experiment， you're very unlikely to see the rare point。



![](img/be8c6a0de1819219a1056e465a41a728_92.png)

![](img/be8c6a0de1819219a1056e465a41a728_93.png)

![](img/be8c6a0de1819219a1056e465a41a728_94.png)

And that point that's way out here， you're unlikely to see it。



![](img/be8c6a0de1819219a1056e465a41a728_96.png)

And so。

![](img/be8c6a0de1819219a1056e465a41a728_98.png)

嗯。So if if you get it though， it just completely blows up the sum and it changes the entire distribution right so when you have rare events right。

 they can have they can be problematic， anything you're doing where you're you know calculating an expectation。



![](img/be8c6a0de1819219a1056e465a41a728_100.png)

![](img/be8c6a0de1819219a1056e465a41a728_101.png)

![](img/be8c6a0de1819219a1056e465a41a728_102.png)

Okay， we're going to change gears a little bit and we're going to talk now， so I'll put a line here。

 We're going to talk about the linearity of expectations， linearity。



![](img/be8c6a0de1819219a1056e465a41a728_104.png)

![](img/be8c6a0de1819219a1056e465a41a728_105.png)

![](img/be8c6a0de1819219a1056e465a41a728_106.png)

Of expectation。

![](img/be8c6a0de1819219a1056e465a41a728_108.png)

linearity of expectation， and so there's this theorem。



![](img/be8c6a0de1819219a1056e465a41a728_110.png)

Theorem。That basically says for any。

![](img/be8c6a0de1819219a1056e465a41a728_112.png)

Random variable， okay。

![](img/be8c6a0de1819219a1056e465a41a728_114.png)

R1。And R 2。

![](img/be8c6a0de1819219a1056e465a41a728_116.png)

On a probability space。

![](img/be8c6a0de1819219a1056e465a41a728_118.png)

S。Okay。The expected value of R1。

![](img/be8c6a0de1819219a1056e465a41a728_120.png)

Plus， R 2。

![](img/be8c6a0de1819219a1056e465a41a728_122.png)

Is equal to the expected value of r1。

![](img/be8c6a0de1819219a1056e465a41a728_124.png)

Plus。The expected value of r2。

![](img/be8c6a0de1819219a1056e465a41a728_126.png)

Okay。Expect value of R1 plus the expected value of R2。 So an example of that。



![](img/be8c6a0de1819219a1056e465a41a728_128.png)

Right， would be， let's say you're going to roll。

![](img/be8c6a0de1819219a1056e465a41a728_130.png)

Tudai。

![](img/be8c6a0de1819219a1056e465a41a728_132.png)

Right you're can roll two die，6 sided。

![](img/be8c6a0de1819219a1056e465a41a728_134.png)

Well， we know what's the expected value of the sum？



![](img/be8c6a0de1819219a1056e465a41a728_136.png)

The sum of Di。

![](img/be8c6a0de1819219a1056e465a41a728_138.png)

Dice。Is going to be equal to the expected value of the first roll plus the expected value of the second roll。

 we know from our previous example that the expected value of one six sided dice is 3。5。



![](img/be8c6a0de1819219a1056e465a41a728_140.png)

![](img/be8c6a0de1819219a1056e465a41a728_141.png)

Plus，3。5。

![](img/be8c6a0de1819219a1056e465a41a728_143.png)

Equals 7。Now， if you've ever played craps where you roll two dice， right， what gives you craps seven？

Why， because that's the expected value， that's the most likely outcome on average。

 when you keep rolling that dice， rolling that dice。

 the most common number that you're going to average is going to be 7。

 so you're more likely to roll a7 on that。

![](img/be8c6a0de1819219a1056e465a41a728_145.png)

![](img/be8c6a0de1819219a1056e465a41a728_146.png)

嗯。There is a corollary， right， so the corollary。

![](img/be8c6a0de1819219a1056e465a41a728_148.png)

I for all k。

![](img/be8c6a0de1819219a1056e465a41a728_150.png)

Yin。

![](img/be8c6a0de1819219a1056e465a41a728_152.png)

Sorry， in a sample space。

![](img/be8c6a0de1819219a1056e465a41a728_154.png)

And。And random variables。

![](img/be8c6a0de1819219a1056e465a41a728_156.png)

Awan。A two。RK。

![](img/be8c6a0de1819219a1056e465a41a728_158.png)

The expected value of R1。

![](img/be8c6a0de1819219a1056e465a41a728_160.png)

Plus， R2。Plus， R k。

![](img/be8c6a0de1819219a1056e465a41a728_162.png)

Equals the expected value of R1。

![](img/be8c6a0de1819219a1056e465a41a728_164.png)

Plus， the expected value。

![](img/be8c6a0de1819219a1056e465a41a728_166.png)

Or two。😔，Plus， the expected value of R。

![](img/be8c6a0de1819219a1056e465a41a728_168.png)

Right， so that is the linearity of expectations。 You want to get the expected value of a sum。

 You can just add up the individual components。 Now。

 one thing I'm going to point out is independence。

![](img/be8c6a0de1819219a1056e465a41a728_170.png)

![](img/be8c6a0de1819219a1056e465a41a728_171.png)

![](img/be8c6a0de1819219a1056e465a41a728_172.png)

Assumption。

![](img/be8c6a0de1819219a1056e465a41a728_174.png)

Is required。Independence assumption is required for this them to work for you to have linearity of expectations。

 So if the outcome of R2 depends somehow on the outcome of R1。

 then you can no longer use this linear out linearity of expectation and we'll find an example that。



![](img/be8c6a0de1819219a1056e465a41a728_176.png)

That does that a little bit later on in the lectures。

