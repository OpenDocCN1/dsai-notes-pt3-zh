# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p02 1_基本计数原理.zh_en -BV1r483zbEzN_p2-

![](img/183c955caff35d424b55bf5ab9183cdf_0.png)

Hello， I'm Dr。 Ian McCllough from Johns Hopkins University and this is the first module in our course statisticaltistical methodsthods for Computer Science today we're going to be talking about counting。



![](img/183c955caff35d424b55bf5ab9183cdf_2.png)

![](img/183c955caff35d424b55bf5ab9183cdf_3.png)

Now you may wonder， well， I already know how to count， I learned that in kindergarten， well。

 let me use an example to help our problem to help motivate the discussion， so what is probability？😊。



![](img/183c955caff35d424b55bf5ab9183cdf_5.png)

![](img/183c955caff35d424b55bf5ab9183cdf_6.png)

Okay， so probability I'm going to define as number of successes。



![](img/183c955caff35d424b55bf5ab9183cdf_8.png)

Divided by number of possibilities。

![](img/183c955caff35d424b55bf5ab9183cdf_10.png)

All right， well， that's a little strange。 So let me give you an example。

 Let's say that I have a coin。

![](img/183c955caff35d424b55bf5ab9183cdf_12.png)

![](img/183c955caff35d424b55bf5ab9183cdf_13.png)

And there's heads on one side， tails on the other side。

 So what is the probability that when I flip a coin， I'm going to get heads。



![](img/183c955caff35d424b55bf5ab9183cdf_15.png)

Well， intuitively， we would say， well probability is 1 half or 50% or 0。5 as you like。

 so let me put that in the context of this definition I've given you， well。

 there is one choice which gives you success。

![](img/183c955caff35d424b55bf5ab9183cdf_17.png)

![](img/183c955caff35d424b55bf5ab9183cdf_18.png)

![](img/183c955caff35d424b55bf5ab9183cdf_19.png)

![](img/183c955caff35d424b55bf5ab9183cdf_20.png)

headads and there are two possibilities that you can have。

 which is heads or tails right so that gives us one over two so that is the probability of flipping ahead。

 Let me give you another example what if we had a dice right a six sided die and you know they've got like you know whatever the numbers are on here you know that they have right。



![](img/183c955caff35d424b55bf5ab9183cdf_22.png)

![](img/183c955caff35d424b55bf5ab9183cdf_23.png)

![](img/183c955caff35d424b55bf5ab9183cdf_24.png)

![](img/183c955caff35d424b55bf5ab9183cdf_25.png)

What's the probability of rolling a one on a six sided dice？



![](img/183c955caff35d424b55bf5ab9183cdf_27.png)

Well， again， intuitively， we know that that's one out of six。



![](img/183c955caff35d424b55bf5ab9183cdf_29.png)

What does that look like Well， one choice gives me success。Out of the possibilities of one，2，3，4，5，6。



![](img/183c955caff35d424b55bf5ab9183cdf_31.png)

![](img/183c955caff35d424b55bf5ab9183cdf_32.png)

Right what if I wanted to know the probability of getting a one or a two out of a six sided dice。

 Well， in that case， we would add a two to this numerator and the probability would become one or two。



![](img/183c955caff35d424b55bf5ab9183cdf_34.png)

![](img/183c955caff35d424b55bf5ab9183cdf_35.png)

Out of。A1，2 to six， and so now that is two possibilities or two success criteria out of six or one third。



![](img/183c955caff35d424b55bf5ab9183cdf_37.png)

![](img/183c955caff35d424b55bf5ab9183cdf_38.png)

Okay。U。

![](img/183c955caff35d424b55bf5ab9183cdf_40.png)

One more tricky example would be what if I have？Two die that I am looking at。



![](img/183c955caff35d424b55bf5ab9183cdf_42.png)

And I want to know what is the probability of rolling a。



![](img/183c955caff35d424b55bf5ab9183cdf_44.png)

Probability of rolling a2 right Well， now we have to say， well， what's the success criteria？



![](img/183c955caff35d424b55bf5ab9183cdf_46.png)

![](img/183c955caff35d424b55bf5ab9183cdf_47.png)

Well， it's still a two。But how many possibilities are there in the bottom now what I would like you to do at this point is pause the video。

 and I would like you to answer that question， and then you can hit resume。



![](img/183c955caff35d424b55bf5ab9183cdf_49.png)

![](img/183c955caff35d424b55bf5ab9183cdf_50.png)

![](img/183c955caff35d424b55bf5ab9183cdf_51.png)

I'm assuming you paused the video and now we're going to continue to solve this problem so how many possibilities are there for rolling two two sided dice well。

 you could have a one and a one that gives you two， you could have a one and a two。

 a one and a three， a one and a four。

![](img/183c955caff35d424b55bf5ab9183cdf_53.png)

![](img/183c955caff35d424b55bf5ab9183cdf_54.png)

![](img/183c955caff35d424b55bf5ab9183cdf_55.png)

One and a five， one and a six。

![](img/183c955caff35d424b55bf5ab9183cdf_57.png)

And then you could do a two and a1。Now notice we counted one2。



![](img/183c955caff35d424b55bf5ab9183cdf_59.png)

And we're doing2，1。 Well there's different because this means a one on the first die and a two on the second die。

 This means a two on the first die and a one on the second die。 So as we continue until we get to 6。

6。 If you've done this， you'll find that there are 36 combinations。



![](img/183c955caff35d424b55bf5ab9183cdf_61.png)

![](img/183c955caff35d424b55bf5ab9183cdf_62.png)

![](img/183c955caff35d424b55bf5ab9183cdf_63.png)

![](img/183c955caff35d424b55bf5ab9183cdf_64.png)

That go in the denominator。 and that would then give us two out of 36 or。



![](img/183c955caff35d424b55bf5ab9183cdf_66.png)

One out of 18。

![](img/183c955caff35d424b55bf5ab9183cdf_68.png)

Possiities or possible ways to get a two， a one on a one on a six sided dice。



![](img/183c955caff35d424b55bf5ab9183cdf_70.png)

What is the probability of？Getting a。

![](img/183c955caff35d424b55bf5ab9183cdf_72.png)

Seven on two dice。 again， I'd like you to pause the video， work out that problem。

 and then hit resume。

![](img/183c955caff35d424b55bf5ab9183cdf_74.png)

![](img/183c955caff35d424b55bf5ab9183cdf_75.png)

I'm assuming you've paused the video and you worked out this problem and the answer we get is that in order the number of ways in which you can get a7 is there's several right。

 you have the 1，6， you also have the2，5， the five，2。

 the 61 right so you end up with six different possibilities of rolling a7 out of 36 ways of rolling two dice。

 which ends up being 1，6。

![](img/183c955caff35d424b55bf5ab9183cdf_77.png)

![](img/183c955caff35d424b55bf5ab9183cdf_78.png)

![](img/183c955caff35d424b55bf5ab9183cdf_79.png)

![](img/183c955caff35d424b55bf5ab9183cdf_80.png)

![](img/183c955caff35d424b55bf5ab9183cdf_81.png)

Okay so what we've been talking about is in calculating probability。

 one of the key challenges we have is counting how many possible ways of achieving some state in whatever experiment you're doing。

 and so before we can begin a course and statistics。

 we need to make sure that we understand how to count the number of possibilities in order to kind of do these problems。



![](img/183c955caff35d424b55bf5ab9183cdf_83.png)

![](img/183c955caff35d424b55bf5ab9183cdf_84.png)

![](img/183c955caff35d424b55bf5ab9183cdf_85.png)

![](img/183c955caff35d424b55bf5ab9183cdf_86.png)

And that's what the module today is going to be focused on。



![](img/183c955caff35d424b55bf5ab9183cdf_88.png)

So what we're going to talk about then is the basic。



![](img/183c955caff35d424b55bf5ab9183cdf_90.png)

Princiipple。

![](img/183c955caff35d424b55bf5ab9183cdf_92.png)

Of counting。The basic principle of count。

![](img/183c955caff35d424b55bf5ab9183cdf_94.png)

And what the basic principle accounting says is if。😊，There are。M outcomes。For experiment。1an。



![](img/183c955caff35d424b55bf5ab9183cdf_96.png)

And。N outcomes。4 experiment。2。Then。There are。M times n。Outcomes。4 experiment。One and two。

 so the example here is when we have one dice， right。

 we have one sixth or six possible outcomes for rolling one dice when we have two dice。

M in this case is6， and in this case is 6。So， M times n。

Equals sex times6 equals 36 possible outcomes， so it is not necessary to enumerate it if we have the basic principle of counting。

