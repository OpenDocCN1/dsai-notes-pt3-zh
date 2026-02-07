# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P38：P38 StatsLearning Lect8h 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/06b0eaa8a1391310919577feca9d1848_0.png)

嗯。And we just said this that one drawback of ridge regression it doesn't actually select variables and set things to zero when as you said。

 in situations like that previous picture。

![](img/06b0eaa8a1391310919577feca9d1848_2.png)

![](img/06b0eaa8a1391310919577feca9d1848_3.png)

Where things are small， it be nice if they could just say these are zero， we can forget about them。

So the Laso is a more recent technique for shrinking coefficients and regression。

 it looks very much like Rige regression but with one change。

 so here's the lastO criterion again we have the RSS。



![](img/06b0eaa8a1391310919577feca9d1848_5.png)

![](img/06b0eaa8a1391310919577feca9d1848_6.png)

As before。

![](img/06b0eaa8a1391310919577feca9d1848_8.png)

Now we have a penalty， whereas before the penalty was a sum of the squares of the coefficients。

 a sum of the absolute values the coefficients。So it's a shrinkage towards zero using an absolute value rather than assem of squares。



![](img/06b0eaa8a1391310919577feca9d1848_10.png)

And this is called an L1 penalty in by analogy to the L2 penalty， the L1 penalty is just。

So some of the absolute values。It's a norm， but it's called the L1 norm rather than the L2 norm。



![](img/06b0eaa8a1391310919577feca9d1848_12.png)

So what's the effect of changing this from a square to an absolute value。

 it's actually a small change， but it's quite important。



![](img/06b0eaa8a1391310919577feca9d1848_14.png)

嗯。Turs out that。

![](img/06b0eaa8a1391310919577feca9d1848_16.png)

The lasso， like the ridge shrinks toward zero。But it has the effect of actually setting variables。

 the coefficients of variables exactly equal to zero when lambmbda is large enough。



![](img/06b0eaa8a1391310919577feca9d1848_18.png)

So it's neat， it shrinks， but also it does subset selection in a similar way to best subset selection。

 so it'll set coefficients to zero exactly if that feature is not important and Lambda is large enough。

So we say that this a term for this it's called sparsity。

 so the last several years was called sparse models。

Models which only involve a subset of the variables。



![](img/06b0eaa8a1391310919577feca9d1848_20.png)

And again， it it's a function of this tuning parameter Lada， which， as in rigid graph。

 we have to choose somehow。

![](img/06b0eaa8a1391310919577feca9d1848_22.png)

And we'll do so by cross validation。So wow， the last seems like a really good idea。

 so clever I wonder who came up with it Rob thanks so Danielle was trying to embarrass me。

 so this is actually a paper that I wrote in 1996 and it's become at the time actually it was published and didn't get a lot of attention but。



![](img/06b0eaa8a1391310919577feca9d1848_24.png)

In the last about 10 years or so it's become a very hot topic both in statistics and computer science and other areas。

 and there's been a lot of work in sparsity in general。

 not just in regression but the use of L1 pen in a lot of different areas。

 I think one reason for it's popularity now is computation。

This computation is actually this is what's called a convex optimization。

 so that's good news and there's a lot of work in convex optimization。

 especially in the last 10 or so years and along with sort the progress in convex optimization and fast computation。

 fast computers。

![](img/06b0eaa8a1391310919577feca9d1848_26.png)

People can solve this problem now， alaso for very large values of P&N。

And this has actually just been a fun thing that I've even seen like when I started grad school。

 you know there was like one approach that sadtisticians were using to fit this model and this was a famous paper that had just come out when I started and it was written by Rob and Trevor and a few other people at Stanford and statistics and then a new paper came out with a better idea and then 20 more papers came out with better ideas for how to fit this model and this has suddenly become something that anyone can solve on their laptop no matter how big your data is basically and so it's just become an incredibly useful tool in a way that it even wasn't when I started grad school so we'll talk about GLMNet which is in our library which we use a lot in this book in the book in the course and will show you how you can solve a problem like solve the lastso using GLMnet in R。



![](img/06b0eaa8a1391310919577feca9d1848_28.png)

![](img/06b0eaa8a1391310919577feca9d1848_29.png)

![](img/06b0eaa8a1391310919577feca9d1848_30.png)

![](img/06b0eaa8a1391310919577feca9d1848_31.png)

Again， with the numbers of variables might be in the tens of thousands， you can solve it in。

On a standard desktop computer in less than a minute。

 so we'll talk about the computation later on in the course。



![](img/06b0eaa8a1391310919577feca9d1848_33.png)

But let's foresee what it looks like in this same example now， so again， the credit data set。

And replying。

![](img/06b0eaa8a1391310919577feca9d1848_35.png)

The standardized coefficients is a function of lambda for the lastO。Again。

 we haven't talked about how to choose Lada and that's going to be important。

 We use cross foundation， but let's for now look at the solutions as a function of Lambda for all vis of lambda。



![](img/06b0eaa8a1391310919577feca9d1848_37.png)

![](img/06b0eaa8a1391310919577feca9d1848_38.png)

And now you can see， again， when lambda is small。

![](img/06b0eaa8a1391310919577feca9d1848_40.png)

We get essentially the full least squares estimates。 Well lamb to 0， we get exactly least squares。

 If I plotted this all the way to the left。

![](img/06b0eaa8a1391310919577feca9d1848_42.png)

And I was an increased lambda would get shrinkage。

![](img/06b0eaa8a1391310919577feca9d1848_44.png)

As we do for Rige regression， but something special happens at this point， for example， here。



![](img/06b0eaa8a1391310919577feca9d1848_46.png)

Beyond this point， all these gray variables are exactly the coefficients are exactly zero。



![](img/06b0eaa8a1391310919577feca9d1848_48.png)

Whereas for regression they were small， but they weren't zero。

 so it's actually we can tell it tells us。

![](img/06b0eaa8a1391310919577feca9d1848_50.png)

You can throw away all these variables at this point and just retain these three， the blue。

 red and orange。Similar， this plot shows you the sampling thing in the other direction。

So it's a combination of both shrinkage。And selection of of variables。



![](img/06b0eaa8a1391310919577feca9d1848_52.png)

And so one thing that's worth mentioning is that in a lot of applications。

 selecting variables is actually really important because， you know， let's say I'm working with。



![](img/06b0eaa8a1391310919577feca9d1848_54.png)

A doctor who wants to come up with a really good way to test for some particular disease and he might start out by getting 30。

000 gene expression measurements for patients with this type of disease so he starts out with P equals 30。

000 and he wants to find a really great model that can be used to test for this disease。

 but when push comes to shove and he's actually going to use this test in the clinic。

 he doesn't want to test that involves all 30，000 genes because a test like that would be too expensive it just wouldn't be feasible to actually use but if he can get a test that works really well that only and involve six or eight or 25 genes that could be a real breakthrough in testing for this disease。

 and so just from a practical perspective， the Laso is just hugely useful because it allows us to efficiently find these types of sparse models that involves just a really small subset of the features be my personal salesman。



![](img/06b0eaa8a1391310919577feca9d1848_56.png)

![](img/06b0eaa8a1391310919577feca9d1848_57.png)

![](img/06b0eaa8a1391310919577feca9d1848_58.png)

![](img/06b0eaa8a1391310919577feca9d1848_59.png)

![](img/06b0eaa8a1391310919577feca9d1848_60.png)

![](img/06b0eaa8a1391310919577feca9d1848_61.png)

![](img/06b0eaa8a1391310919577feca9d1848_62.png)

![](img/06b0eaa8a1391310919577feca9d1848_63.png)

![](img/06b0eaa8a1391310919577feca9d1848_64.png)

![](img/06b0eaa8a1391310919577feca9d1848_65.png)

doing a good job， but seriously I mean and Danielle was right I myself I use a lastso in schools and projects here at the medical school。

 and it's very satisfying you to apply it and to see it helping scientists to find the signal in their data and come up with interpretable subsets among their。



![](img/06b0eaa8a1391310919577feca9d1848_67.png)

![](img/06b0eaa8a1391310919577feca9d1848_68.png)

![](img/06b0eaa8a1391310919577feca9d1848_69.png)

![](img/06b0eaa8a1391310919577feca9d1848_70.png)

The thousands of features they present to me。So。At this point it might seem like like magic。

 why is it that this using absolute value penalty gives us the sparsity property。

 why do we get exactly zero and I'm going to show you that in the picture， so let's think about that。



![](img/06b0eaa8a1391310919577feca9d1848_72.png)

![](img/06b0eaa8a1391310919577feca9d1848_73.png)

![](img/06b0eaa8a1391310919577feca9d1848_74.png)

First of all， we can formulate the problem in an equivalent way rather than putting a penalty。

Then before I had the RSS plus lambda times the sum of the absolute values。

An equivalent way to say the Laso is to pose the LaO problems to say minimize the RSS。

With a constraint。A budget on the total L1 norm of the coefficients。

So this is an equivalent problem in the sense that if you give me a budget S。

 there's a Lada in the previous formulation that corresponds to the same problem and vice versa。



![](img/06b0eaa8a1391310919577feca9d1848_76.png)

And by the way， if that looks like a total mystery。

 if you can reach back to your distant or not so distant past。

 if you ever took AP calculus and you saw LaGrange multipliers in high school。

 this is really something that you might have truly seen in high school calculus a long time ago but for simpler types of problems and this is just a more complex application of that same idea in a way that it's bound form is to me more intuitive than the Lagrange form because think of this way。

 suppose that you do fully squares and you get a certain answer and I tell you and let's suppose that some of the absolute values your coefficient is10。



![](img/06b0eaa8a1391310919577feca9d1848_78.png)

![](img/06b0eaa8a1391310919577feca9d1848_79.png)

![](img/06b0eaa8a1391310919577feca9d1848_80.png)

![](img/06b0eaa8a1391310919577feca9d1848_81.png)

![](img/06b0eaa8a1391310919577feca9d1848_82.png)

![](img/06b0eaa8a1391310919577feca9d1848_83.png)

So you give me an answer and I say， well， actually。I want to。

 I want to make your your budget smaller。 You've spent too much coefficient。 So rather than 10。

 I want to give you a budget of maybe five。

![](img/06b0eaa8a1391310919577feca9d1848_85.png)

![](img/06b0eaa8a1391310919577feca9d1848_86.png)

So now I ask you to solve the same problem but you're not allowed to use the coefficients as large as you want the total budget you have is five and that's the bound here so the lastso was giving you a budget on that total L Nor you can spend and within within that budget you have to fit as well as possible and as that budget gets smaller and smaller the coefficients gets smaller and smaller if the budget is zero。



![](img/06b0eaa8a1391310919577feca9d1848_88.png)

![](img/06b0eaa8a1391310919577feca9d1848_89.png)

![](img/06b0eaa8a1391310919577feca9d1848_90.png)

![](img/06b0eaa8a1391310919577feca9d1848_91.png)

The coefficients have to be zero。

![](img/06b0eaa8a1391310919577feca9d1848_93.png)

If the budget is large enough you're free to use fully squares， but in between。

 the budget's going to trade off。

![](img/06b0eaa8a1391310919577feca9d1848_95.png)

The size the coefficients where they fit。

![](img/06b0eaa8a1391310919577feca9d1848_97.png)

So I think it's quite an intuitive way of looking at these problems。For richge regression。

 you get exactly the same analogy， but now the budget is in terms of the sum squares。 So， again。

 this is equivalent to the。

![](img/06b0eaa8a1391310919577feca9d1848_99.png)

The Lagrange formulation for Rirration we saw earlier。



![](img/06b0eaa8a1391310919577feca9d1848_101.png)

But the reason we all want to bring this up is this following picture， which。Helps to explain why。

The lastso gives sparsity， so on the right is Rige regression。

And on the left is the Laso I guess thiss a bit more mathy than most things in this course。

 but hang in there and I think if you do there'll be some payoffs。This picture is Ri regression。

 So what's going on here is， first of all， P is 2。 So there's two coefficients。



![](img/06b0eaa8a1391310919577feca9d1848_103.png)

And I've indicated here the full squares estimate， so if there was no penalty。

 I just did least squares on the two variables， I'll call the solution beta hat。

 and that's this point。

![](img/06b0eaa8a1391310919577feca9d1848_105.png)

And now the sums of squares。In the RSS。The contours of that function。



![](img/06b0eaa8a1391310919577feca9d1848_107.png)

It's lowest here because that's the least squares estimate， but now as I move away。

 if I think of this as maybe a serial bowl and I slice the serial bowl， here are the contours。

 so here's the value which RSS is a bigger value， this next contour is a higher contour of RSS。

 so these are the contours of RSS as I move away from the minimum。



![](img/06b0eaa8a1391310919577feca9d1848_109.png)

![](img/06b0eaa8a1391310919577feca9d1848_110.png)

And。😔，This is the constraint region remember in Ri regression and this formulation here says。

 you have a budget。

![](img/06b0eaa8a1391310919577feca9d1848_112.png)

On the total sum squares of the be。So the budget is the。



![](img/06b0eaa8a1391310919577feca9d1848_114.png)

The radius of a circle， right？And here I have a fixed budgetm so。In words。

 the ridge problem says finally the first place these contours hit the constraint region。



![](img/06b0eaa8a1391310919577feca9d1848_116.png)

![](img/06b0eaa8a1391310919577feca9d1848_117.png)

In other words， find me the smallest RSs you can get。



![](img/06b0eaa8a1391310919577feca9d1848_119.png)

嗯。Within the budget defined by this circle。

![](img/06b0eaa8a1391310919577feca9d1848_121.png)

That's Ri regression。 And the solution in this picture is right here。

So this is the ridge estimates for this budget and the data。

 this particular data and the data is determine the shape of these contours and the location of betaha。

So。

![](img/06b0eaa8a1391310919577feca9d1848_123.png)

Riddge regressionion says finally the first place the contours hit this constraint region。

 it's this solution， and you can see because the constraint region， the sum of squares is a circle。



![](img/06b0eaa8a1391310919577feca9d1848_125.png)

![](img/06b0eaa8a1391310919577feca9d1848_126.png)

This is where the sum of squares of。Beta 1 and beta 2 is less than a budget。 It's a circle， right。

 And unless you're very lucky that you're not going to hit exactly at a place where。



![](img/06b0eaa8a1391310919577feca9d1848_128.png)

![](img/06b0eaa8a1391310919577feca9d1848_129.png)

One or the other is zero。Now let's move over to the Laso， same picture， least squares。

 same thing that the sum of squares function is the same， all the same up here。

 but the constraint region is now the sum of the absolute values。



![](img/06b0eaa8a1391310919577feca9d1848_131.png)

![](img/06b0eaa8a1391310919577feca9d1848_132.png)

So rather than a circle， it's a diamond。A diamond has corners。

So in this picture I've hit this corner and now I get a place where beta is beta 1 hat is 0。

 so here's the last O estimate。

![](img/06b0eaa8a1391310919577feca9d1848_134.png)

So I was to summarize the absolute values give you a constraint region that has sharp corners and high dimensions you have。



![](img/06b0eaa8a1391310919577feca9d1848_136.png)

Edges and corners。And along an edge or corner， if you hit there， you get a zero。So。

This is geometrically why you get sparsity in the Lasso。



![](img/06b0eaa8a1391310919577feca9d1848_138.png)

![](img/06b0eaa8a1391310919577feca9d1848_139.png)

So here's， oh， sorry。Here's our case。 first of all， the returning the example where we had 50。



![](img/06b0eaa8a1391310919577feca9d1848_141.png)

It there 45 variables and they all had non zero coefficients。



![](img/06b0eaa8a1391310919577feca9d1848_143.png)

So now I'm looking at。

![](img/06b0eaa8a1391310919577feca9d1848_145.png)

Comparing。The Lasso to Ridge。So on the left picture。

 for the last so we see the bias variance and mean square error as a function of lambda。



![](img/06b0eaa8a1391310919577feca9d1848_147.png)

And the right， we've superimposed the biased variance andmen error of ridger grasp with the broken line and the lasal。

And we can see that overall， so again， the solid line here from mean square Air is the last so the broken line is ridge。



![](img/06b0eaa8a1391310919577feca9d1848_149.png)

They're very similar ridges a little better， perhaps。



![](img/06b0eaa8a1391310919577feca9d1848_151.png)

We don't do much better。 We don't do better at all with the lastso here。

 And the reason is is that we've got the true model is not sparse。 The true model actually involves。



![](img/06b0eaa8a1391310919577feca9d1848_153.png)

![](img/06b0eaa8a1391310919577feca9d1848_154.png)

45 variables， all of which have been given non zero coefficients in the population。



![](img/06b0eaa8a1391310919577feca9d1848_156.png)

So it's not surprising that we don't do better than Ridge in this case and one thing we should mention is on this right hand panel the x axis is something we haven't seen before。

 which is the r squared on the training data and the reason we have that x axis is because in this figure on the right hand side we're plotting both ridge regression and the laso so it wouldn't make sense to show rid regression and the laso with lambda on the x axis because the lambda means two different things for those two models so when we look at r squared on the training data on the x axis that's kind of a universally sensible thing to measure regardless of what the type of model is。



![](img/06b0eaa8a1391310919577feca9d1848_158.png)

![](img/06b0eaa8a1391310919577feca9d1848_159.png)

![](img/06b0eaa8a1391310919577feca9d1848_160.png)

![](img/06b0eaa8a1391310919577feca9d1848_161.png)

![](img/06b0eaa8a1391310919577feca9d1848_162.png)

![](img/06b0eaa8a1391310919577feca9d1848_163.png)

![](img/06b0eaa8a1391310919577feca9d1848_164.png)

You must have drawn this picture in a book， Yeah， I made this picture because it's a beauty thank you。

 yeah。

![](img/06b0eaa8a1391310919577feca9d1848_166.png)

Okay， I would have missed that detail otherwise， okay。



![](img/06b0eaa8a1391310919577feca9d1848_168.png)

Now， here's a situation where we do we do perform better with the Laso。

 And this is a case where now in the population， only two of the predictors have nonzero coefficient。

 So the previous situation was。

![](img/06b0eaa8a1391310919577feca9d1848_170.png)

![](img/06b0eaa8a1391310919577feca9d1848_171.png)

Was dense or non sparse。 This situation is sparse。 there's only two predictors in the true model that are non zero coefficients。



![](img/06b0eaa8a1391310919577feca9d1848_173.png)

![](img/06b0eaa8a1391310919577feca9d1848_174.png)

And now we can see what happens well。

![](img/06b0eaa8a1391310919577feca9d1848_176.png)

The lastso mean square error here is minimized for quite a large value of lambda。



![](img/06b0eaa8a1391310919577feca9d1848_178.png)

Because it wants to make the model sparse as it needs to， there's only two non zero coefficients。



![](img/06b0eaa8a1391310919577feca9d1848_180.png)

And now when we compare the La Otra Rige。Remember， ridge is the broken line。



![](img/06b0eaa8a1391310919577feca9d1848_182.png)

And the lastso is a solid line。You can see we do quite here's the last mean square error and there's Rige。



![](img/06b0eaa8a1391310919577feca9d1848_184.png)

Is here。

![](img/06b0eaa8a1391310919577feca9d1848_186.png)

You can see we're doing quite a bit better using the Laso in this situation。

 and again it's not surprising， the true model is sparse。

 so it pays to use a technique which encourages sparse models coming out of its estimation whereas。



![](img/06b0eaa8a1391310919577feca9d1848_188.png)

![](img/06b0eaa8a1391310919577feca9d1848_189.png)

![](img/06b0eaa8a1391310919577feca9d1848_190.png)

With Rige you don't get a sparse model， we get a dense model。



![](img/06b0eaa8a1391310919577feca9d1848_192.png)

So in conclusion， comparing these two techniques， as is usually the case in most things in statistics and science in general。

There's no rule that there's no simple rule that means that you always use one technique over another。

 it depends， you always hear that from sideians， it depends well。It depends on the situation。

In this particular case。If the true model is quite dense。

 most predictors are not have non-zero coefficients， we expect to do better with Rige。

 If the true model is quite sparse， only a few coefficients have are non-zero。

 then the lastso can be expected to do better。 Of course we don't know that usually we hope actually that things are sparse because life is simpler then。

 but going into a data analysis we have no idea whether the true number of coefficients。

 non-zero coefficients is large or small。

![](img/06b0eaa8a1391310919577feca9d1848_194.png)

So we have we use。

![](img/06b0eaa8a1391310919577feca9d1848_196.png)

It's typically good to apply both methods and use cross validation to determine the best model coming out of each method。

 and then compare the cross validated error for the two methods。



![](img/06b0eaa8a1391310919577feca9d1848_198.png)