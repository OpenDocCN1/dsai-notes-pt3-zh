# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p71 26_t检验.zh_en -BV1r483zbEzN_p71-

So I've talked about the hypothesis testing。 Well， there's a really cool thing that occurred at the Guinness brewreweery in Dublin。



![](img/aa0befe10384b65d10ccd936859c0d71_1.png)

Basically， there is an issue with the normal distribution。And this guy。

 William Cley Gossett discovered that if he were to modify that and created what he called the T test that he would have a bias that is occurring from the normal distribution which is really important to make Guinness。

 which is such a wonderful wonderful tasting beer now at the time that was considered a proprietary trade secret。

 so important that they could not afford to publish it and let their competitors know。

 so William Cley Gossett decided to publish it under the name student and so it was published as the student tea test and it was not revealed that it was a Guinness trade secret and that they were using statistics and experimental design to make the best bear in the world until decades later and then he was kind of given credit for this well after his death so if you actually remember those old Guinness commercials where the guys were going brilliant brilliant and they had like little cartoon characters well one of those was Arthur。



![](img/aa0befe10384b65d10ccd936859c0d71_3.png)

![](img/aa0befe10384b65d10ccd936859c0d71_4.png)

Ginness and the other one was William Cley Gossett。



![](img/aa0befe10384b65d10ccd936859c0d71_6.png)

We're going to show you what the test is right so basically what William Cley Gossett said is depending upon the number in the size of the distribution。

 and I'm going to get rid of this axis here we'll just use。



![](img/aa0befe10384b65d10ccd936859c0d71_8.png)

![](img/aa0befe10384b65d10ccd936859c0d71_9.png)

We'll make it center it around zero here， right？

![](img/aa0befe10384b65d10ccd936859c0d71_11.png)

And so what he determined was that as you get larger and larger N。

 it begins to approximate the normal distribution。 So when you get about 30 or so， you know。

 you can feel comfortable with just going with the normal distribution is probably not that that far off。

 but otherwise your distribution， right。

![](img/aa0befe10384b65d10ccd936859c0d71_13.png)

Might take a slightly wider or fatter tail to it。

![](img/aa0befe10384b65d10ccd936859c0d71_15.png)

RightAnd it just depended upon how many was in your sample and so the T。



![](img/aa0befe10384b65d10ccd936859c0d71_17.png)

![](img/aa0befe10384b65d10ccd936859c0d71_18.png)

Test statistic is is written down as the sample average you collect from your sample minus whatever the mean is you hypothesize it to be divided by the standard deviation。

Of that X bar。And so according to the central limit theorem。

 that would be the standard deviation of x divided by the square root of n。



![](img/aa0befe10384b65d10ccd936859c0d71_20.png)

![](img/aa0befe10384b65d10ccd936859c0d71_21.png)

And then there's an important parameter here， which is degrees。



![](img/aa0befe10384b65d10ccd936859c0d71_23.png)

Of freedom。And that is always n minus1 for this particular test。

 Now the t distribution is always centered to zero。

 now notice if I have a value of a sample meaning and I subtract what I think it is。

 if I'm right on I'm at zero that's the ideal value is the most likely value right and then it's scaled by that standard deviation So what I've done is I've converted this into this area here。

 but now the distribution I'm comparing it to when I'm estimating probabilities is now this t distribution and it's going to use a single parameter which is degrees of freedom。



![](img/aa0befe10384b65d10ccd936859c0d71_25.png)

![](img/aa0befe10384b65d10ccd936859c0d71_26.png)

![](img/aa0befe10384b65d10ccd936859c0d71_27.png)

![](img/aa0befe10384b65d10ccd936859c0d71_28.png)

![](img/aa0befe10384b65d10ccd936859c0d71_29.png)

![](img/aa0befe10384b65d10ccd936859c0d71_30.png)

![](img/aa0befe10384b65d10ccd936859c0d71_31.png)

And that's going to be equivalent to n minus1， so you take your data sample。

 you transform it into a test statistic T， and then you're going to reference it against the T distribution。



![](img/aa0befe10384b65d10ccd936859c0d71_33.png)

![](img/aa0befe10384b65d10ccd936859c0d71_34.png)

As you go forward， so in this particular case， right， if I use the example that we just did before。



![](img/aa0befe10384b65d10ccd936859c0d71_36.png)

We would have T。Equal to 650 was my sample， minus707 was what we hypothesized it to be。

 and then our standard deviation was well， 60。1， but I guess I can write it out here。

 it was if you recall 425 divided by the square root of 50。

 which all of that ends up equaling negative 57。

![](img/aa0befe10384b65d10ccd936859c0d71_38.png)

![](img/aa0befe10384b65d10ccd936859c0d71_39.png)

![](img/aa0befe10384b65d10ccd936859c0d71_40.png)

![](img/aa0befe10384b65d10ccd936859c0d71_41.png)

![](img/aa0befe10384b65d10ccd936859c0d71_42.png)

Over 60。1， which ends up being equal to negative0 point。



![](img/aa0befe10384b65d10ccd936859c0d71_44.png)

9，4，8，4。

![](img/aa0befe10384b65d10ccd936859c0d71_46.png)

Okay， and then using the T distribution， right， where does that occur。

 it occurs somewhere around here。 So when we do the the。



![](img/aa0befe10384b65d10ccd936859c0d71_48.png)

![](img/aa0befe10384b65d10ccd936859c0d71_49.png)

The same little。

![](img/aa0befe10384b65d10ccd936859c0d71_51.png)

When we do the same integral from negative infinity to T now of f of x。

 we have degrees of freedom n minus1， so that is 49 is our parameter。



![](img/aa0befe10384b65d10ccd936859c0d71_53.png)

![](img/aa0befe10384b65d10ccd936859c0d71_54.png)

![](img/aa0befe10384b65d10ccd936859c0d71_55.png)

We end up getting a P value。Of。

![](img/aa0befe10384b65d10ccd936859c0d71_57.png)

0。1738 and again you can try that out in the R script right so again。

 we don't have enough observation of the tail to reject that hypothesis we would conclude that things are still fine。



![](img/aa0befe10384b65d10ccd936859c0d71_59.png)

![](img/aa0befe10384b65d10ccd936859c0d71_60.png)

![](img/aa0befe10384b65d10ccd936859c0d71_61.png)

For that。

![](img/aa0befe10384b65d10ccd936859c0d71_63.png)

If I had 600 followers。If， right， I observed 600 followers。



![](img/aa0befe10384b65d10ccd936859c0d71_65.png)

![](img/aa0befe10384b65d10ccd936859c0d71_66.png)

Then my T would be 600 minus707。

![](img/aa0befe10384b65d10ccd936859c0d71_68.png)

Over 425 square root of 50。 That value is now going to be。



![](img/aa0befe10384b65d10ccd936859c0d71_70.png)

Negative 1。78。

![](img/aa0befe10384b65d10ccd936859c0d71_72.png)

And when you run that， then the P value for that is going to end up equaling 0。0406。

 and I would encourage you to play around with that to see that notice I had to have a higher threshold under the T distribution than I did under the normal in this particular case。



![](img/aa0befe10384b65d10ccd936859c0d71_74.png)

![](img/aa0befe10384b65d10ccd936859c0d71_75.png)

![](img/aa0befe10384b65d10ccd936859c0d71_76.png)

![](img/aa0befe10384b65d10ccd936859c0d71_77.png)

We do have a variation for this， and that is where we want to do what is called the two sample。



![](img/aa0befe10384b65d10ccd936859c0d71_79.png)

T test。

![](img/aa0befe10384b65d10ccd936859c0d71_81.png)

Now the two sample T test is done when I'm going to observe data points from one population one sample and data points from a second sample and I want to compare them to say。

 hey are they the same or are they different right so now in this case I'm going to have not just one x bar but I'm going to have the x bar from sample one I'm going to have the x bar from sample2 and so what we do is we formulate this a little bit differently so first of all the hypothesis that we're testing is that the average for the first sample is the same as the average for the second sample。



![](img/aa0befe10384b65d10ccd936859c0d71_83.png)

![](img/aa0befe10384b65d10ccd936859c0d71_84.png)

![](img/aa0befe10384b65d10ccd936859c0d71_85.png)

![](img/aa0befe10384b65d10ccd936859c0d71_86.png)

![](img/aa0befe10384b65d10ccd936859c0d71_87.png)

And know the alternative， however you want to set it up， we can make it just that they're different。



![](img/aa0befe10384b65d10ccd936859c0d71_89.png)

![](img/aa0befe10384b65d10ccd936859c0d71_90.png)

Okay， so the way I set this sample up is my T statistic is now if I were to subtract this from both sides。

 right？

![](img/aa0befe10384b65d10ccd936859c0d71_92.png)

This becomes the value that I'm hypothesizing is0。 So when I do my T test。

 I'm going to have x1 bar minus x2。

![](img/aa0befe10384b65d10ccd936859c0d71_94.png)

Minus0， so I don't have to put that minus0， right， but we can just for completeness here。And then。

In below， I'm going to have a pooled standard deviation， right， a pooled standard deviation。



![](img/aa0befe10384b65d10ccd936859c0d71_96.png)

Well， what is that pool standard deviation， It looks very much like this。 X1 minus x2。



![](img/aa0befe10384b65d10ccd936859c0d71_98.png)

Over the square root。Of。Anwan。-1。S1 squared over。

![](img/aa0befe10384b65d10ccd936859c0d71_100.png)

Sorry， plus。

![](img/aa0befe10384b65d10ccd936859c0d71_102.png)

And 2 minus-1 S2 squared all over n1 plus n。2-2。😔。

![](img/aa0befe10384b65d10ccd936859c0d71_104.png)

OkayNow this is pooling the standard deviation， so I'm waiting the standard deviation of the variance of the first sample by the number that was in it。

 I'm waiting the variance of the second sample by the number was in it。

 and then I'm dividing it by the total number of observations。

 So this becomes a weighted average of the variances then I take the square root to get to that pooled standard deviation underneath the x1 bar minus x2 bar right and so that gives me my two sample T test。



![](img/aa0befe10384b65d10ccd936859c0d71_106.png)

![](img/aa0befe10384b65d10ccd936859c0d71_107.png)

![](img/aa0befe10384b65d10ccd936859c0d71_108.png)

![](img/aa0befe10384b65d10ccd936859c0d71_109.png)

![](img/aa0befe10384b65d10ccd936859c0d71_110.png)

Statistic， and then I compare that test statistic the same way that I was against the reference distribution。

 So here's an example。

![](img/aa0befe10384b65d10ccd936859c0d71_112.png)

![](img/aa0befe10384b65d10ccd936859c0d71_113.png)

Right so in the example。The salary？

![](img/aa0befe10384b65d10ccd936859c0d71_115.png)

Difer。Between。

![](img/aa0befe10384b65d10ccd936859c0d71_117.png)

Public。And private。

![](img/aa0befe10384b65d10ccd936859c0d71_119.png)

Schools。Does salary differ between public and private schools so in this example， we have 35 private。



![](img/aa0befe10384b65d10ccd936859c0d71_121.png)

![](img/aa0befe10384b65d10ccd936859c0d71_122.png)

Schools， right， and the average。

![](img/aa0befe10384b65d10ccd936859c0d71_124.png)

The average salary for private。

![](img/aa0befe10384b65d10ccd936859c0d71_126.png)

Was。

![](img/aa0befe10384b65d10ccd936859c0d71_128.png)

88。19 k per year and the standard deviation。

![](img/aa0befe10384b65d10ccd936859c0d71_130.png)

In the private schools was 26。21 k。

![](img/aa0befe10384b65d10ccd936859c0d71_132.png)

And then we have 30 public schools。

![](img/aa0befe10384b65d10ccd936859c0d71_134.png)

Teachers that we were looking at。

![](img/aa0befe10384b65d10ccd936859c0d71_136.png)

And we have X public。

![](img/aa0befe10384b65d10ccd936859c0d71_138.png)

73。18。Standard deviation in the public schools。Was。23。



![](img/aa0befe10384b65d10ccd936859c0d71_140.png)

。95 k。Right and so what I would like you to do is take this formula， pause the video。

 and then try and work that out on your own， and then come back and then look at the answer。



![](img/aa0befe10384b65d10ccd936859c0d71_142.png)

![](img/aa0befe10384b65d10ccd936859c0d71_143.png)

I'm assuming that you have positive video and you have worked that out on your own。

 so now we'll go through the solution。

![](img/aa0befe10384b65d10ccd936859c0d71_145.png)

![](img/aa0befe10384b65d10ccd936859c0d71_146.png)

So our hypothesis is。That x。Sorry， it is that。The mean of one is equal to the mean of  two。

 That's our first step。 We've set up the hypothesis to say they are the same。



![](img/aa0befe10384b65d10ccd936859c0d71_148.png)

![](img/aa0befe10384b65d10ccd936859c0d71_149.png)

The alternative is。That they are different， okay？

![](img/aa0befe10384b65d10ccd936859c0d71_151.png)

🤧U。

![](img/aa0befe10384b65d10ccd936859c0d71_153.png)

We're putting the burden of proof on， you know，' let's assume they're the same and see if there's enough information to cause us to conclude something different。

 that's the way we set up the problem。

![](img/aa0befe10384b65d10ccd936859c0d71_155.png)

![](img/aa0befe10384b65d10ccd936859c0d71_156.png)

So now the T statistic is going to be。

![](img/aa0befe10384b65d10ccd936859c0d71_158.png)

Our formula right here。 So x1 is we'll make the private school you know， x1 is going to be 88。



![](img/aa0befe10384b65d10ccd936859c0d71_160.png)

019 minus。

![](img/aa0befe10384b65d10ccd936859c0d71_162.png)

2， which is 73。18。And then that's going to be over。



![](img/aa0befe10384b65d10ccd936859c0d71_164.png)

呃。35。

![](img/aa0befe10384b65d10ccd936859c0d71_166.png)

in-1 times the variance， which is going to be。26。21 squared。Plus 30 minus1 times the variance here。

 23。95 squared all over 35 plus 30 minus2 the denominator。



![](img/aa0befe10384b65d10ccd936859c0d71_168.png)

![](img/aa0befe10384b65d10ccd936859c0d71_169.png)

And what that's going to give me is a statistic of negative 2。395。 And when we compare that into the。



![](img/aa0befe10384b65d10ccd936859c0d71_171.png)

![](img/aa0befe10384b65d10ccd936859c0d71_172.png)

You know，Into the tail here。Right。

![](img/aa0befe10384b65d10ccd936859c0d71_174.png)

![](img/aa0befe10384b65d10ccd936859c0d71_175.png)

Negative 2。395 right， what you're going to find is the P value。



![](img/aa0befe10384b65d10ccd936859c0d71_177.png)

Is。😔。

![](img/aa0befe10384b65d10ccd936859c0d71_179.png)

0。0196， and so that is going to be less than 0。05 and so that's going to cause us to reject that hypothesis。

 the null hypothesis， that they're the same and conclude in favor of the alternate that they're different。



![](img/aa0befe10384b65d10ccd936859c0d71_181.png)

![](img/aa0befe10384b65d10ccd936859c0d71_182.png)

![](img/aa0befe10384b65d10ccd936859c0d71_183.png)

![](img/aa0befe10384b65d10ccd936859c0d71_184.png)

Now， there is an important point here， and that is you'll sometimes hear people talk about whether or not you're going to do a one tail。



![](img/aa0befe10384b65d10ccd936859c0d71_186.png)

![](img/aa0befe10384b65d10ccd936859c0d71_187.png)

Or two tail。Test。Now。I don't particularly like this distinction。

 but it is common in statistics and you'll hear this a lot。 And so the idea is a one tail test。



![](img/aa0befe10384b65d10ccd936859c0d71_189.png)

is only going to be looking at。The probability in one direction， right。

 So it's going to compare this idea that there's no difference。

To the ones greater or one's less right or sorry this will be ones less。

 You could also do a version of this。Where one would be greater， right。

 So you're going to look at at not even going to consider that。 So in the case of， you know， of here。

 we're looking to see if they're different。 This is perfectly correct。

 But if we're going to say under the condition that the alternative was that。



![](img/aa0befe10384b65d10ccd936859c0d71_191.png)

![](img/aa0befe10384b65d10ccd936859c0d71_192.png)

Private teachers make less than public school teachers。 Well。

 we wouldn't even consider that because it's obvious， right。

're we're not even going to consider stuff that's looking here right So you're only looking at the condition to one side right So like。

 hey， we know that private school teachers are making more than public school teachers on average。

 but is it statistically significant。 So we're really only going to look at one tail And that means that that that area here has to be less than 0。

05 right， That's what you would do here。 with the two tail tests when it's different。



![](img/aa0befe10384b65d10ccd936859c0d71_194.png)

![](img/aa0befe10384b65d10ccd936859c0d71_195.png)

Is you're splitting that 0。05 between both sides。 and so now the threshold here， like this would be。

Righti。You know from here， this would be right to this point would be a probability of 0。05。Here。

 you're looking at。Point probability of point。025 and then there's another one here right P0。

025 that together makes 0。05。 So what you're doing in a two tails test is you're kind of making sure that that the threshold for difference is a little bit stricter right than it is here。

 if you have some reason to believe that it's only above or below。

 then you kind of like have a a less strict threshold for where that occurs。



![](img/aa0befe10384b65d10ccd936859c0d71_197.png)

There's one last thing that I want to introduce， and that is that of a confidence interval and so with。



![](img/aa0befe10384b65d10ccd936859c0d71_199.png)

With a confidence interval。I like to derive it slightly different than you've probably see in your book。

 So if you look at this test statistic as x bar minus the mean over。诶。

S divided by the square root of n。And if I multiply both sides by S divided by square root of n。

 I get T。S squared of n。Equals x minus mu 0。And so then if I add mu 0 to both sides and I subtract t from both sides。

 I'll get mu 0 equals x sorry bar minus t。S over the square root of n。Okay。

 and what that's saying is that here。If I have a sufficient difference here， right。

 So given that you've scaled it by the S square like the bigger that difference is， it affects T。

 It's pushing it further out into one tail or the other， right， one tail or the other， right？

 And so if I say， well， what value of T is going to is going to hit a particular threshold right。

 Can I do that。 Well， the answer is yes， you can。 by by doing this algebra。

 I can say that a mean that occurs around my sample with this width， right？ So here is， here is my。

Here is what I sampled， right， That's x bar。And so if I go out here。Ti。

S over square root of n or this direction T S over squared of n， right。

 And I get some sort of interval here then。That T is going to be based upon whatever confidence interval you're looking at。

 right， It's going to be based on。Am I looking at the t value that gives me 5% level of rejection。

 am I going to be looking at a t that gives me a 1% level of rejection what am I looking at that's going to affect the width of of this thing because it's going to affect the width of t S over the squared of n is based on your data so as I shrink or expand that right then with that level of confidence I can be sure that the real value of mu is somewhere in that interval you don't know it perfectly。

Now， what's interesting about this example here is if I were to give you an example like。You know。

 mu。Sorry。😔，Mu 0 was 7，0，7。 and I want to construct a confidence interval about this。 Well。

 I can say that that mu。Is going to be equal to 707 plus or minus the width of T。

Times 425 over the square root of 50， right， I'm just using this formula。

For a confidence interval right here。I have added plus or minus to show the width either way。

All right， so I have this confidence interval then。

When I find the inverse t corresponding to a probability of know P value of 0。05。

 where is that value right， so if I were to integrate negative infinity up to some question mark。

Such that F of x， Dx is going to equal 0。05。 What is that value， right？ What you end up getting is2。

0，0，9，6。So when I put that back in here and I get 707 plus or minus 2。0096425 over squared to 50。

What I end up with is 707 plus or minus。120。7770。Which gives me an interval of 586。2。2，8。27。

8 and what that's telling me is the real mean right of followers is somewhere within that range based on whatever I've gotten as a sample。

 and that's how you're using a confidence interval。

The one kind of test you can do with confidence intervals which is similar to the two sample T test is if I construct a confidence interval around sample1 right so I construct a confidence interval using just the private school data and then I construct a confidence interval to using just the public school data if they overlap。

 it's possible that the mean could be in the intersection of the overlap。If they don't overlap。

 then it's not possible the real mean can be in an intersection。

 and so that's how we can say that they are statistically different。

