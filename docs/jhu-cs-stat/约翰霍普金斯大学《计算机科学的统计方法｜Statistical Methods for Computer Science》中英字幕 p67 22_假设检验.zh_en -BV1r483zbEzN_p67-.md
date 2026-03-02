# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p67 22_假设检验.zh_en -BV1r483zbEzN_p67-

![](img/6f911754f2a74a56bd7c3b534896f813_0.png)

So we've been talking about limit theorems， we've talked about Markoff。

 we've talked about Murphy's law， Chebiachev's central limit theorem。

 what this all is boiling down to is our ability to be able to do a hypothesis。



![](img/6f911754f2a74a56bd7c3b534896f813_2.png)

![](img/6f911754f2a74a56bd7c3b534896f813_3.png)

Test。We are going to statistically test to see is something significant is something different。

 and this becomes one of the most important concepts in modeling or in making predictions or in anomaly detection。



![](img/6f911754f2a74a56bd7c3b534896f813_5.png)

![](img/6f911754f2a74a56bd7c3b534896f813_6.png)

![](img/6f911754f2a74a56bd7c3b534896f813_7.png)

And so I'll motivate this with an example。

![](img/6f911754f2a74a56bd7c3b534896f813_9.png)

Suppose。We want to judge whether the average number of followers。



![](img/6f911754f2a74a56bd7c3b534896f813_11.png)

About Trump changes during a given week， because I think Trump is always good to study。



![](img/6f911754f2a74a56bd7c3b534896f813_13.png)

Don't care what your political views are， it's great。



![](img/6f911754f2a74a56bd7c3b534896f813_15.png)

![](img/6f911754f2a74a56bd7c3b534896f813_16.png)

![](img/6f911754f2a74a56bd7c3b534896f813_17.png)

![](img/6f911754f2a74a56bd7c3b534896f813_18.png)

So suppose we want to judge whether the average number of followers for users talking about Trump changes during a given week。



![](img/6f911754f2a74a56bd7c3b534896f813_20.png)

Right。We're going to conduct a hypothesis test right we want to know whether there's been a change。

 whether there's been a significant change， so there's been some level of activity that's like we consider baseline or we consider typical and has that fallen out of control right has that had a change？



![](img/6f911754f2a74a56bd7c3b534896f813_22.png)

![](img/6f911754f2a74a56bd7c3b534896f813_23.png)

![](img/6f911754f2a74a56bd7c3b534896f813_24.png)

![](img/6f911754f2a74a56bd7c3b534896f813_25.png)

So we need to understand about a hypothesis test， a hypothesis。



![](img/6f911754f2a74a56bd7c3b534896f813_27.png)

Test。

![](img/6f911754f2a74a56bd7c3b534896f813_29.png)

Involves。

![](img/6f911754f2a74a56bd7c3b534896f813_31.png)

2， hypotheses。2， hypotheses。

![](img/6f911754f2a74a56bd7c3b534896f813_33.png)

We usually call one the null。And then， the other。

![](img/6f911754f2a74a56bd7c3b534896f813_35.png)

The alternative。

![](img/6f911754f2a74a56bd7c3b534896f813_37.png)

Sometimes they'll call it the experimental hypothesis。

 so the standard study in psychology or in social science is you'll have a control group or a placebo。

 and that's the control group。

![](img/6f911754f2a74a56bd7c3b534896f813_39.png)

![](img/6f911754f2a74a56bd7c3b534896f813_40.png)

And then you'll have a condition where it's experimental where you've actually applied some sort of change and so what we want to test then when you collect data from the people that have the placebo or the baseline period or normal activity and then you've done some intervention like you've given somebody a drug or you've given some changes has happened in the environment now that's called the alternative or the experimental condition and you want to test。

 hey， has this different than what's normal or what's typical。



![](img/6f911754f2a74a56bd7c3b534896f813_42.png)

![](img/6f911754f2a74a56bd7c3b534896f813_43.png)

![](img/6f911754f2a74a56bd7c3b534896f813_44.png)

Okay。The null hypothesis is the one that we're going to test， right。

 The null hypothesis is the one we're going to test。 And the other thing I'll say is a hypothesis。

 hypothesis。

![](img/6f911754f2a74a56bd7c3b534896f813_46.png)

![](img/6f911754f2a74a56bd7c3b534896f813_47.png)

Theres a statement。

![](img/6f911754f2a74a56bd7c3b534896f813_49.png)

Something。

![](img/6f911754f2a74a56bd7c3b534896f813_51.png)

Is true。RightSo we're not going to say our hypothesis is there's no change right that our hypothesis is is something So we're not going to say our hypothesis is。



![](img/6f911754f2a74a56bd7c3b534896f813_53.png)

![](img/6f911754f2a74a56bd7c3b534896f813_54.png)

You know this is what's not happening right we're going to say that a hypothesis is it has to be definitive。

 it has to be this parameter equals this number or equals this value I'll give you an example。

 so what we would end up doing is we would say we would write the null hypothesis with a little zero there for null hypothesis。



![](img/6f911754f2a74a56bd7c3b534896f813_56.png)

![](img/6f911754f2a74a56bd7c3b534896f813_57.png)

And we would say that the mean。

![](img/6f911754f2a74a56bd7c3b534896f813_59.png)

Equals some value right， So if I want to say， hey， has the average number of followers changed。

 well what's the average followers， I look at Trump over over a period of like two or three months。

 What's his average number of followers， right？ That's what that number is right and my hypothesis is。



![](img/6f911754f2a74a56bd7c3b534896f813_61.png)

![](img/6f911754f2a74a56bd7c3b534896f813_62.png)

A statement， something is true。 So I'm saying that the average number of followers for Trump is blank。

 right， you know， maybe it's， you know，10000， right， That's the average number of followers。

 I'm not saying that it's it's not 11000 right， because there's infinite number of values。

 I'm saying that it is a specific number。 Mary may not be true， right。

 So a hypothesis is a statement that something is true。



![](img/6f911754f2a74a56bd7c3b534896f813_64.png)

![](img/6f911754f2a74a56bd7c3b534896f813_65.png)

![](img/6f911754f2a74a56bd7c3b534896f813_66.png)

![](img/6f911754f2a74a56bd7c3b534896f813_67.png)

![](img/6f911754f2a74a56bd7c3b534896f813_68.png)

诶。And so let me just say that this is going to be the same as whatever it was last month。



![](img/6f911754f2a74a56bd7c3b534896f813_70.png)

If I sample 50 users and。

![](img/6f911754f2a74a56bd7c3b534896f813_72.png)

So let's say a sample。

![](img/6f911754f2a74a56bd7c3b534896f813_74.png)

50 users。

![](img/6f911754f2a74a56bd7c3b534896f813_76.png)

Right， and the average followers。

![](img/6f911754f2a74a56bd7c3b534896f813_78.png)

I'm going to use different numbers here， average。Followers。Is 650。



![](img/6f911754f2a74a56bd7c3b534896f813_80.png)

And let's say last month， right， when I was looking at my baseline， last month。

 the mean was 707 right， that was what the baseline was last month。



![](img/6f911754f2a74a56bd7c3b534896f813_82.png)

![](img/6f911754f2a74a56bd7c3b534896f813_83.png)

And so if I look at 650， well， that's less than 707， does that mean he's lost followers？



![](img/6f911754f2a74a56bd7c3b534896f813_85.png)

![](img/6f911754f2a74a56bd7c3b534896f813_86.png)

Well， let's say I add that the observed。

![](img/6f911754f2a74a56bd7c3b534896f813_88.png)

The observed。Standard deviation。

![](img/6f911754f2a74a56bd7c3b534896f813_90.png)

Is equal to。425， okay， 425。

![](img/6f911754f2a74a56bd7c3b534896f813_92.png)

![](img/6f911754f2a74a56bd7c3b534896f813_93.png)

Then what I can use the central limit theorem to do is say my x bar is equal to。650。

I can say that the standard deviation of x bar is equal to S over the squared of n。

 which is 425 over square root of 50。

![](img/6f911754f2a74a56bd7c3b534896f813_95.png)

![](img/6f911754f2a74a56bd7c3b534896f813_96.png)

Which is going to equal 60。1。

![](img/6f911754f2a74a56bd7c3b534896f813_98.png)

So now I know that my ex is supposed to follow。my x bar is supposed to follow a normal distribution。

With a mean of 707。Standard deviation is 60。1。So then what is the probability that x？



![](img/6f911754f2a74a56bd7c3b534896f813_100.png)

Is less than 650。And when you then go back to R and you plug that into the equation。

 you'll end up finding that the probability is。

![](img/6f911754f2a74a56bd7c3b534896f813_102.png)

![](img/6f911754f2a74a56bd7c3b534896f813_103.png)

。17，1，5，1，7，1，5。

![](img/6f911754f2a74a56bd7c3b534896f813_105.png)

And so， then。That's telling us that if this was 707。650 falls here。

The probability in this area of the distribution is 0。1715， right。

 and I guess that is not far enough into the tail。

![](img/6f911754f2a74a56bd7c3b534896f813_107.png)

![](img/6f911754f2a74a56bd7c3b534896f813_108.png)

Out here。Where we would conclude that。

![](img/6f911754f2a74a56bd7c3b534896f813_110.png)

This data point does not match this distribution。 Now。

 if that data point does not match the distribution。



![](img/6f911754f2a74a56bd7c3b534896f813_112.png)

Well， the central limit theorem tells us that if。

![](img/6f911754f2a74a56bd7c3b534896f813_114.png)

If。

![](img/6f911754f2a74a56bd7c3b534896f813_116.png)

We take a sample of more than 30 people we've taken 50。



![](img/6f911754f2a74a56bd7c3b534896f813_118.png)

And we know the mean and the standard deviation。Right of what we've observed。

We can then calculate the the average， the sample， the average。

 and we know that that must be normally distributed。

 So if I know that that has to be normally distributed and this doesn't work。Well， that's not wrong。

 right the essential limit theorem is not wrong。 What has to be wrong is there has to be something different about the observation。

 right the mean。That statement of where the mean is。Must be incorrect。

And so if we have an observation that's way out here， like let's say it wasn't 650。

 but let's it was 600 followers and you can try doing that as well。 It was 600 followers。

 then you would see that that's further out in the tail， this probability is smaller under 0。05。



![](img/6f911754f2a74a56bd7c3b534896f813_120.png)

![](img/6f911754f2a74a56bd7c3b534896f813_121.png)

And now we're going to say I don't believe that that assumption is true if it's way out there and that's how you conduct a hypothesis test。

 So it's the central emthereorem that allows you to take a problem like this。

 convert it into a distribution that you understand and then you can calculate the area under the curve of the density function to determine what's the probability that this assumption holds with the data that you saw and if it doesn't match up。

 then you reject the null hypothesis and conclude that there has been a change。



![](img/6f911754f2a74a56bd7c3b534896f813_123.png)

![](img/6f911754f2a74a56bd7c3b534896f813_124.png)

![](img/6f911754f2a74a56bd7c3b534896f813_125.png)

![](img/6f911754f2a74a56bd7c3b534896f813_126.png)

![](img/6f911754f2a74a56bd7c3b534896f813_127.png)

![](img/6f911754f2a74a56bd7c3b534896f813_128.png)

But notice that we've set this up where the burden of proof is on the null hypothesis。

 we made a statement that this is what the mean is， and you have to prove that it's highly unlikely。

 you have to prove that it's highly unlikely。

![](img/6f911754f2a74a56bd7c3b534896f813_130.png)

![](img/6f911754f2a74a56bd7c3b534896f813_131.png)

![](img/6f911754f2a74a56bd7c3b534896f813_132.png)

And we do that by doing this probability， and we call that a P value。



![](img/6f911754f2a74a56bd7c3b534896f813_134.png)

P value。

![](img/6f911754f2a74a56bd7c3b534896f813_136.png)

Now that's the general basis of how the math works。

 Now there are some cultural practices that people in science like to use and it's somewhat nuanced。



![](img/6f911754f2a74a56bd7c3b534896f813_138.png)

![](img/6f911754f2a74a56bd7c3b534896f813_139.png)

Essentially， when the probability is is less than when probability is less than。



![](img/6f911754f2a74a56bd7c3b534896f813_141.png)

0。05， right， We're saying that。

![](img/6f911754f2a74a56bd7c3b534896f813_143.png)

If all of this is true， the likelihood you'd be out here is one in 20 times， right， one in 20 times。



![](img/6f911754f2a74a56bd7c3b534896f813_145.png)

So that means the one in 20 times you're going to make a mistake if you're rejecting the null hypothesis at that level but that's just how statistics works。

 we kind of set a confidence level as what we're comfortable with。

 and then that becomes our threshold for whether we reject the null hypothesis or not。



![](img/6f911754f2a74a56bd7c3b534896f813_147.png)

![](img/6f911754f2a74a56bd7c3b534896f813_148.png)

![](img/6f911754f2a74a56bd7c3b534896f813_149.png)

So a lot of people will say， I'm going to frame an alternative hypothesis。



![](img/6f911754f2a74a56bd7c3b534896f813_151.png)

And。They'll say， you know？

![](img/6f911754f2a74a56bd7c3b534896f813_153.png)

If you're the Donald， it's not possible for him to lose followers。 Why would that happen， right？

 So all he's looking at is to say the alternative is that I could have more。



![](img/6f911754f2a74a56bd7c3b534896f813_155.png)

Then 707 that I thought， right， That's the only possibility， right， Well， if that's the case。



![](img/6f911754f2a74a56bd7c3b534896f813_157.png)

![](img/6f911754f2a74a56bd7c3b534896f813_158.png)

And I got 650。 I'm done。 There's no change， right， because it's not possible you could have lost followers。

''s part of your alternative assumption。

![](img/6f911754f2a74a56bd7c3b534896f813_160.png)

So the only way we even continue with the test is if it was higher， like， 750 or 800。



![](img/6f911754f2a74a56bd7c3b534896f813_162.png)

![](img/6f911754f2a74a56bd7c3b534896f813_163.png)

Well， is that significantly higher to consider it a change In that case。

 the only values we're considering right from that 707 are ones that are higher。

 And so we're looking to see what is that threshold right。

 What is that limit or that threshold or that's going to be 0。05。



![](img/6f911754f2a74a56bd7c3b534896f813_165.png)

![](img/6f911754f2a74a56bd7c3b534896f813_166.png)

Right， but let's say you're in the Democratic National Committee。

 You might have an alternative hypothesis that it's not possible for Trump to gain any more than he has。

 I don't know why he has as many as he does。 The only possibility is that he's going to get less than。



![](img/6f911754f2a74a56bd7c3b534896f813_168.png)

![](img/6f911754f2a74a56bd7c3b534896f813_169.png)

Then 707 followers。 So as we add our you know Democratic ads and on stuff on TV have we significantly detracted his followers。

 well in that case。

![](img/6f911754f2a74a56bd7c3b534896f813_171.png)

![](img/6f911754f2a74a56bd7c3b534896f813_172.png)

![](img/6f911754f2a74a56bd7c3b534896f813_173.png)

If I had 800， well， I'm not even going to continue the test， right。

 because obviously it didn't lower the followers， what I want to know is。



![](img/6f911754f2a74a56bd7c3b534896f813_175.png)

![](img/6f911754f2a74a56bd7c3b534896f813_176.png)

Have I gone to this threshold where I'm looking for 0。05 down here right in the distribution？



![](img/6f911754f2a74a56bd7c3b534896f813_178.png)

So that's an assumption you're making in how you frame the alternative。



![](img/6f911754f2a74a56bd7c3b534896f813_180.png)

And it's basically you're going to say that I'm not even going to consider the possibility that it was on one side or the other。

 and that is a one tailed hypothesis test。 And so your threshold for 0。

05 when you're looking at that needs to be here or here depending on how you set up the test。

 The other one is just that you're going to say I don't know what's going to happen with the Donald。

 It's just going to be different。

![](img/6f911754f2a74a56bd7c3b534896f813_182.png)

![](img/6f911754f2a74a56bd7c3b534896f813_183.png)

![](img/6f911754f2a74a56bd7c3b534896f813_184.png)

![](img/6f911754f2a74a56bd7c3b534896f813_185.png)

Well， if it's just different， if that's how you framed it， well then。



![](img/6f911754f2a74a56bd7c3b534896f813_187.png)

You're going to split that 0。05 over here。Or over here， so you're looking for a value that is。

Greater than this number。Or less than this number， and that 0。5 is now split。



![](img/6f911754f2a74a56bd7c3b534896f813_189.png)

Between。

![](img/6f911754f2a74a56bd7c3b534896f813_191.png)

Both sides。What's the implication， Well， if I'm going to say。

 have we significantly degraded Trump's followers？

![](img/6f911754f2a74a56bd7c3b534896f813_193.png)

![](img/6f911754f2a74a56bd7c3b534896f813_194.png)

Well then I'm going to set my threshold right here right and let's say I get an observation at 0 or 600 followers right and it follows right here。

 if this is what I'm doing I'm trying to degrade him。

 I might conclude that I have significantly degraded him because I have passed that threshold。



![](img/6f911754f2a74a56bd7c3b534896f813_196.png)

But if I'm just looking to say， are they different， well， that number right0。

05 might be like right right here。 So maybe my value is here。

 and I'm not going to conclude that it's different right。

 that it's still within the possibility of normal values can see this probability of less than 650 is 0。

175。 If you change that to 600， you're going to see a number lower than 0。05 right。

 but not lower than 0。025。 So you're going to be right in that threshold。

 So depending on how you frame that alternative， you need more evidence to conclude that there has been a change。



![](img/6f911754f2a74a56bd7c3b534896f813_198.png)

![](img/6f911754f2a74a56bd7c3b534896f813_199.png)

![](img/6f911754f2a74a56bd7c3b534896f813_200.png)

![](img/6f911754f2a74a56bd7c3b534896f813_201.png)

![](img/6f911754f2a74a56bd7c3b534896f813_202.png)

![](img/6f911754f2a74a56bd7c3b534896f813_203.png)

![](img/6f911754f2a74a56bd7c3b534896f813_204.png)

![](img/6f911754f2a74a56bd7c3b534896f813_205.png)

RightAnd that's generally how hypothesis testing works。

 But the math is that we're making an assumption。

![](img/6f911754f2a74a56bd7c3b534896f813_207.png)

Assumption about a parameter of the distribution we making an assumption。



![](img/6f911754f2a74a56bd7c3b534896f813_209.png)

![](img/6f911754f2a74a56bd7c3b534896f813_210.png)

If that assumption is true， I guarantee you that when you do this math。

 you will find that the number should follow this distribution and if it's in the tail。

Something's wrong， not with math， but with your assumption。

 And that's how you reject the null hypothesis。

![](img/6f911754f2a74a56bd7c3b534896f813_212.png)

So I know that that's a little bit nuanced to suggest that you meditate on that a little bit a little while and in one of our follow on modules。

 we're going to go over this again and we're going to go into more detail on hypothesis testing。



![](img/6f911754f2a74a56bd7c3b534896f813_214.png)

![](img/6f911754f2a74a56bd7c3b534896f813_215.png)

![](img/6f911754f2a74a56bd7c3b534896f813_216.png)