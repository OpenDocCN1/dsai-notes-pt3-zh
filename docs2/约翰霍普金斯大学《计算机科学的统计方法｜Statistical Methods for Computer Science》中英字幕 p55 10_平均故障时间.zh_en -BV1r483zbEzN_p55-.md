# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p55 10_平均故障时间.zh_en -BV1r483zbEzN_p55-

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_0.png)

So understanding expectation allows us to solve some problems a little bit more easily。

 so I'm going to give you a common example here， so an example is a system。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_2.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_3.png)

Faiils。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_5.png)

With。呃。With some sort of probability。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_7.png)

Probability。😔，Pi。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_9.png)

At each step。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_11.png)

Kam。They're mutually independent， so that means mutually。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_13.png)

Independent。So that means that whether it fails or not at time one doesn't affect whether it's going to fail or not at time two。

 so mutually independent。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_15.png)

嗯。And。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_17.png)

And this is known as a mean。Time。😔。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_19.png)

To fail。Or M T， T F problem。 mean time to failure problem。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_21.png)

Okay。So we will say that R， our random variable， is going to equal the step。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_23.png)

Wen。The first。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_25.png)

Failure。Occur。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_27.png)

So R is going to be the step when the first failure occurs。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_29.png)

So then the expected value。Of R， right， which is the expected step when the first failure occurs is going to be equal to。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_31.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_32.png)

The sum of。A。😔。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_34.png)

Equals 0。To infinity。And that will be a failure。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_36.png)

And the probability that。Or。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_38.png)

Is greater than I。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_40.png)

Okay。And so this is essentially the probability that there is no failure in the first R minus1 steps right so from step  zero to whatever。

 theres to r minus1， there's no failures。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_42.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_43.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_44.png)

Okay， so if we were to work this out， that is going to be equivalent。

 So I don't have to keep using the one there。 That's going to be equivalent to。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_46.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_47.png)

The probability。That no failure。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_49.png)

In step。Wn。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_51.png)

Times the probability that there's no failure。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_53.png)

In step。2u。😔，Right， and that's going to be。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_55.png)

Times。😔。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_57.png)

Probability， no failure。In step。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_59.png)

Ai。Okay。That's what that is。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_61.png)

And so。What is the is that probability right， that is basically going to be the sum as I goes from 0 to infinity of the probability of no failure。

 well， if the probability of a failure is P， the probability of no failure is 1 minus P。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_63.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_64.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_65.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_66.png)

And that can be raised to the eh power。 So when I is one， it's just that value。

 Then we're going to add to that too， right So that's going to be to the second power of P of 1 minus P times 1 minus P all the way up until we get to the Ih step。

 So this becomes that probability。 And so since。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_68.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_69.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_70.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_71.png)

Since。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_73.png)

1 minus p is less than1， right we're able to use a nice little identity here that says that that is going to be equal to1 over1 minus 1 minus p。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_75.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_76.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_77.png)

And so if we work that out， we are going to have one。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_79.png)

Over1 minus1 is 0 and the negative in that that makes it 1 over p right so the expected number of observations until we have a failure is 1 over p。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_81.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_82.png)

So。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_84.png)

If we have the probability of failure。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_86.png)

0。01 so there's a 1% likelihood of failure， right then。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_88.png)

Then the mean time to fail is going to be equal to 1 over P， which is 1 over001。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_90.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_91.png)

Which is equal to。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_93.png)

100。Observations， so if the probability of failure is one。

 then the mean the average time until you see the first failure is going to be 100。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_95.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_96.png)

，'ll give you another example here。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_98.png)

呃。King Henry VI。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_100.png)

Right， King Henry。The 8。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_102.png)

He he wants to get a son， and so he's going to keep having kids until he gets his air and so how many kids should we expect for him to have？



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_104.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_105.png)

Well， we can say that the probability of a girl。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_107.png)

Is going to be equal to12。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_109.png)

Okay。And hes going to quit。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_111.png)

When he gets a boy。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_113.png)

Quit when he gets a boy。So R we can treat。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_115.png)

As the number of girls。Until。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_117.png)

Until failure， right， when you get a boy。 And so we're going to assume that there's independent。

 So the fact that you had a girl doesn't mean you're genetically predisposed to have girls， right。

 We're just going to assume that each one is independent。 So now the expected value of R。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_119.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_120.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_121.png)

I going to then be equal to 1 over p。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_123.png)

And so the number of kids。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_125.png)

Right。Mean time to fail。Is going to be equal to one over one half， which equals 2。 right？

 So how many girls should he expect to have， right？

 So if we were going to take this step further and say。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_127.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_128.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_129.png)

How many girls。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_131.png)

Right， how many girls， Well， keep in mind that it's how many kids are you having until you get your first boy。

 right， So you'd be one less than that for how many girls you would expect to have。

 So that would then end up being the expected value of R。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_133.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_134.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_135.png)

us1， which is going to be， we already know two， minus1， one。

 so you'd expect to have one girl and then one boy。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_137.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_138.png)

呃。How many kids would you expect to have to have one of each？



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_140.png)

So。How many。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_142.png)

Kids。To have one of each。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_144.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_145.png)

So I want you to take the work that we have here， this meantime to failure your problem。

 I want you to take what I did here for girls， and I'd like you to pause the video and then try and work through that solution to see if you can come up with the correct answer。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_147.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_148.png)

I'm assuming you've paused the video and you have worked through this problem to come up with the correct answer。

 so now I'm going to do that so how many kids right so if the first kid is a boy first kid is a boy or a girl right？



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_150.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_151.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_152.png)

So first kid。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_154.png)

Is a boy。Or a girl。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_156.png)

And so then after the first kid is a boy or girl， then the expected value， right， then。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_158.png)

The expected value。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_160.png)

To get another one we know is two， right？

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_162.png)

So if I take the first kid as a boy， right， now the problem is just going to be how many kids would I likely have before I have another boy。

 right that's going to be two。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_164.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_165.png)

If the expected value is that I have a girl first， then how many until I have a girl again right or sorry。

 if I have a boy first， how many kids do I have to have until I get a girl right， would be two。

 if I have a girl first， how many kids would I have to have to get a boy would be two。

 So the answer would then end up being two。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_167.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_168.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_169.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_170.png)

Plus one for that first kid to have one of each。 So that ends up equaling three， right， So if I'm。

 if I'm going to say， how many kids do I have to have until I get the boy。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_172.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_173.png)

2， that's the same as the problem of how many kids would I have to have to have a girl，2， right。

 if I want to have one of each， while I have to have one。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_175.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_176.png)

And now I'm looking at saying， well， how many kids do I have to have to have the other sex。

 Well it's two， so that's where you get the one plus2 and you end up equaling three。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_178.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_179.png)

Okay。So hopefully you getting the idea of how we're using expectation。



![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_181.png)