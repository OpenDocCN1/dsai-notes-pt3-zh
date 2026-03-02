# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p66 21_中心极限定理应用实例.zh_en -BV1r483zbEzN_p66-

![](img/94c61d397da5a688e33c4c1d78125209_0.png)

Yeah。So you're just exposed to the central limit theorem in a previous video and we saw that how we could use the central limit theorem to kind of get an estimate of what's required sample size in order to have a certain level of confidence on the accuracy of a measure。



![](img/94c61d397da5a688e33c4c1d78125209_2.png)

![](img/94c61d397da5a688e33c4c1d78125209_3.png)

![](img/94c61d397da5a688e33c4c1d78125209_4.png)

Well there's another really powerful application for the central limit theorem as well and that it helps us take data from any distribution and understand the distribution so that we can then begin to do hypothesis testing or we can then become predictive so if you recall the central limit theorem stated that if I take data from any any distribution。

 it can be a highly skewed distribution like the exponential or it could just be the normal distribution。

 but when I start taking these values， if I take multiple observations and I add them up。

 subtract them from the number of observations times the true mean。

 and I divide that by the standard deviation times squared of n。



![](img/94c61d397da5a688e33c4c1d78125209_6.png)

Then that value tends towards a standard normal distribution。

 So what that means is if I start taking observations。

 and I get enough of them as n tends towards infinity or it gets larger and larger。

 then what ends up happening is that that number， regardless of its original distribution。



![](img/94c61d397da5a688e33c4c1d78125209_8.png)

We now know that it could be normal， and if we know it's normal。

 we can draw normal probability distribution， then we can begin to do inference about the nature that data has' it changed。

 what's it likely to do。

![](img/94c61d397da5a688e33c4c1d78125209_10.png)

![](img/94c61d397da5a688e33c4c1d78125209_11.png)

So in an example， let's say I take a sample。

![](img/94c61d397da5a688e33c4c1d78125209_13.png)

![](img/94c61d397da5a688e33c4c1d78125209_14.png)

Of Twitter users。

![](img/94c61d397da5a688e33c4c1d78125209_16.png)

And they are in an online。

![](img/94c61d397da5a688e33c4c1d78125209_18.png)

Debate。

![](img/94c61d397da5a688e33c4c1d78125209_20.png)

![](img/94c61d397da5a688e33c4c1d78125209_21.png)

And the sample includes 31 users。And they're mean。

![](img/94c61d397da5a688e33c4c1d78125209_23.png)

They mean。

![](img/94c61d397da5a688e33c4c1d78125209_25.png)

呃。Friend follower account。

![](img/94c61d397da5a688e33c4c1d78125209_27.png)

Was。

![](img/94c61d397da5a688e33c4c1d78125209_29.png)

1，2，4，1。87。

![](img/94c61d397da5a688e33c4c1d78125209_31.png)

Right。And the standard deviation， standard deviation。



![](img/94c61d397da5a688e33c4c1d78125209_33.png)

Was。😔，201，7。51。

![](img/94c61d397da5a688e33c4c1d78125209_35.png)

What is the statistical distribution， What is the。

![](img/94c61d397da5a688e33c4c1d78125209_37.png)

Statistical distribution。

![](img/94c61d397da5a688e33c4c1d78125209_39.png)

What is that statistical distribution。

![](img/94c61d397da5a688e33c4c1d78125209_41.png)

Well。What I can tell you is with the central limit theorem， the mean。



![](img/94c61d397da5a688e33c4c1d78125209_43.png)

Of。The average， the mean of the average， so every time I'm going to take a sample of 31 users。

 the mean of that average is going to be the same thing as the mean of the original distribution。

 which we know is 1241。87。

![](img/94c61d397da5a688e33c4c1d78125209_45.png)

![](img/94c61d397da5a688e33c4c1d78125209_46.png)

![](img/94c61d397da5a688e33c4c1d78125209_47.png)

Okay。The standard deviation of the average， so I've taken 31 users。



![](img/94c61d397da5a688e33c4c1d78125209_49.png)

And then I take the next group of 31 users and I compare and the next group of 31 users and compare them now I've just taken 93 samples。



![](img/94c61d397da5a688e33c4c1d78125209_51.png)

![](img/94c61d397da5a688e33c4c1d78125209_52.png)

But I have three averages。 So I have three of these numbers， the x bars。 right。

 So the standard deviation of that the averages。

![](img/94c61d397da5a688e33c4c1d78125209_54.png)

![](img/94c61d397da5a688e33c4c1d78125209_55.png)

Is going to be equal to the standard deviation。Of x divided by the square root of n。So in this case。

 the standard deviation of all these numbers is 2017。51， but that square root of n。



![](img/94c61d397da5a688e33c4c1d78125209_57.png)

![](img/94c61d397da5a688e33c4c1d78125209_58.png)

There's 31 users in each sample， and so then that is going to equal 362。



![](img/94c61d397da5a688e33c4c1d78125209_60.png)

![](img/94c61d397da5a688e33c4c1d78125209_61.png)

。35。H62。35。

![](img/94c61d397da5a688e33c4c1d78125209_63.png)

So given the above distribution。

![](img/94c61d397da5a688e33c4c1d78125209_65.png)

![](img/94c61d397da5a688e33c4c1d78125209_66.png)

Given the above distribution， what is probably their future sample？



![](img/94c61d397da5a688e33c4c1d78125209_68.png)

What have a mean？

![](img/94c61d397da5a688e33c4c1d78125209_70.png)

What it mean。Friend follow count。

![](img/94c61d397da5a688e33c4c1d78125209_72.png)

Greater than 2000。 what's probably would it be greater than 2000？



![](img/94c61d397da5a688e33c4c1d78125209_74.png)

So what we can do is we can see greater than 2000， so we know that when I run in a probability distribution。

 I'm saying what's the probability it's less than 2000， so I have to again look at my shirt， right。

 something happened。

![](img/94c61d397da5a688e33c4c1d78125209_76.png)

![](img/94c61d397da5a688e33c4c1d78125209_77.png)

![](img/94c61d397da5a688e33c4c1d78125209_78.png)

Minus the probability that it was。Less than 2000。given the mean is one， two，4，1。



![](img/94c61d397da5a688e33c4c1d78125209_80.png)

![](img/94c61d397da5a688e33c4c1d78125209_81.png)

And the standard deviation is。362。35， so you can go to Excel and you can use one minus norm disk。

2000， 1241。87，362。35 comma 1。

![](img/94c61d397da5a688e33c4c1d78125209_83.png)

![](img/94c61d397da5a688e33c4c1d78125209_84.png)

![](img/94c61d397da5a688e33c4c1d78125209_85.png)

And you can get the value or you can go into R and you can use your you know the lecture we did on how you use R to calculate distribution under normal the density under a normal distribution to calculate probability and you will find。



![](img/94c61d397da5a688e33c4c1d78125209_87.png)

![](img/94c61d397da5a688e33c4c1d78125209_88.png)

![](img/94c61d397da5a688e33c4c1d78125209_89.png)

0。01。

![](img/94c61d397da5a688e33c4c1d78125209_91.png)

8ight，2。0，7，6，8 as you know， you can round it to however you like。

 if you don't remember how to actually calculate this。

 I'm going to ask you to go and revise the video lecture on the use of R for calculating distributions。

 I believe that was module 5 that you should have seen that。



![](img/94c61d397da5a688e33c4c1d78125209_93.png)

![](img/94c61d397da5a688e33c4c1d78125209_94.png)

![](img/94c61d397da5a688e33c4c1d78125209_95.png)

![](img/94c61d397da5a688e33c4c1d78125209_96.png)

But what we've done is even though I don't know what the distribution of friendend follower account is。

 I know that it's skewed right， I know that there are some people you know like Kim Kardashian。

 you know T Swizzle， Katie Perry， Justin Bieber， the Donald Obama。

 these guys have like tons and tons of follower account and there's other guys like Ian McCulllough。

 Tony Johnson right， many of you in this class that have very， very few friendend follower accounts。

 so it's very， very skewed and there's a lot more of us that have very few than have very large so that's a skewed distribution。



![](img/94c61d397da5a688e33c4c1d78125209_98.png)

![](img/94c61d397da5a688e33c4c1d78125209_99.png)

![](img/94c61d397da5a688e33c4c1d78125209_100.png)

![](img/94c61d397da5a688e33c4c1d78125209_101.png)

![](img/94c61d397da5a688e33c4c1d78125209_102.png)

![](img/94c61d397da5a688e33c4c1d78125209_103.png)

![](img/94c61d397da5a688e33c4c1d78125209_104.png)

Even though I know that that's problematic， I can't really accurately measure that。



![](img/94c61d397da5a688e33c4c1d78125209_106.png)

What the central limit theorem allows me to do is if I take enough people in a sample。

 which we usually as a rule of thumbs， say 30 or more， that's why you saw 31。



![](img/94c61d397da5a688e33c4c1d78125209_108.png)

![](img/94c61d397da5a688e33c4c1d78125209_109.png)

If we see 30 or more， then we know that the mean of the average of those 30。



![](img/94c61d397da5a688e33c4c1d78125209_111.png)

Is the same as the mean of the overall population。 We know that the standard deviation。



![](img/94c61d397da5a688e33c4c1d78125209_113.png)

Of the sample is the same as the standard deviation of the overall population divided by the square root of how many we put into that sample。

 and most importantly though， is we know that that follows a normal distribution。



![](img/94c61d397da5a688e33c4c1d78125209_115.png)

![](img/94c61d397da5a688e33c4c1d78125209_116.png)

![](img/94c61d397da5a688e33c4c1d78125209_117.png)

And the advantage of it following a normal distribution means that we can now make inference about the data。

 and that's what makes it the most popular probably one of the most powerful limit theorems that we have in all statistics。

 because it allows us to then begin to take any problem。



![](img/94c61d397da5a688e33c4c1d78125209_119.png)

![](img/94c61d397da5a688e33c4c1d78125209_120.png)

And when we want to if we can frame it where I have n。

Whatever the samples are that I'm measuring is somehow greater than 30。



![](img/94c61d397da5a688e33c4c1d78125209_122.png)

Then I can take a sample and I can calculate x bar and I can calculate the standard deviation of x bar。

 and then I can take a normal distribution。

![](img/94c61d397da5a688e33c4c1d78125209_124.png)

![](img/94c61d397da5a688e33c4c1d78125209_125.png)

And I can know where should that x bar likely be， it should be somewhere in， you know。

 here's the real mean。

![](img/94c61d397da5a688e33c4c1d78125209_127.png)

![](img/94c61d397da5a688e33c4c1d78125209_128.png)

But it should be somewhere in here。 And if I see oh there's my X bar。

 I have no reason to reject that。 But if I see an X bar that's way out here， hey。

 something's very strange out here in this part of the number line that doesn't look like the rest of them。

 maybe something's changed， Maybe something's different。 There's a statistical anomaly， right。

 But I need the central limit theorem in order to be able to do that。

 And the key things you just have to remember， is when you are going to be using the central limit theorem。

 the mean。

![](img/94c61d397da5a688e33c4c1d78125209_130.png)

![](img/94c61d397da5a688e33c4c1d78125209_131.png)

![](img/94c61d397da5a688e33c4c1d78125209_132.png)

![](img/94c61d397da5a688e33c4c1d78125209_133.png)

![](img/94c61d397da5a688e33c4c1d78125209_134.png)

Of x bar equals the mean of x。

![](img/94c61d397da5a688e33c4c1d78125209_136.png)

The standard deviation of x bar equals the standard deviation of x over the square root of n。



![](img/94c61d397da5a688e33c4c1d78125209_138.png)

![](img/94c61d397da5a688e33c4c1d78125209_139.png)

That is the most important part that you need to keep track of from the central limit theorem。



![](img/94c61d397da5a688e33c4c1d78125209_141.png)