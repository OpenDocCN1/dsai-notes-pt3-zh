# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P29：P29 StatsLearning Lect7e 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， so we're back some more discussions of the bootstrap。

 we saw an example of the bootstrap with the investments。



![](img/063695d28a0b00516d0922646f182d3f_1.png)

![](img/063695d28a0b00516d0922646f182d3f_2.png)

And now in general， we're going to talk about the bootstrap and think about it in more complex situations。

 so here's a schematic which I think is very useful actually it's due to David Friedman at Berkeley。

 it's the real world bootstrap worldview of the bootstrap。



![](img/063695d28a0b00516d0922646f182d3f_4.png)

![](img/063695d28a0b00516d0922646f182d3f_5.png)

![](img/063695d28a0b00516d0922646f182d3f_6.png)

So on the left， we have a cloud and ingredients。We're imagining well there's a population。

The tro a real population that。Am。

![](img/063695d28a0b00516d0922646f182d3f_8.png)

Gives our data， which I'm calling genetically Z observation Z1 through Z N。

 And from these like have training data right， that's our training data。 for example。

 in in the the investment example， we just saw this training data was a set of。



![](img/063695d28a0b00516d0922646f182d3f_10.png)

![](img/063695d28a0b00516d0922646f182d3f_11.png)

Investments， X， Y， X1。Y1，2， x。N whyn。But we'll that' going to call each of these pairs a Z。

 this is Z1 and up through Zn。

![](img/063695d28a0b00516d0922646f182d3f_13.png)

We imagined in that situation that we have a training data from a population of investments。



![](img/063695d28a0b00516d0922646f182d3f_15.png)

This is in the real world， right we have a training sample and from that training sample we derives。



![](img/063695d28a0b00516d0922646f182d3f_17.png)

A statistic and an estimate in that or a particular case， it was the， the alpha hat。

Which is the proportion of investments。The off will proportion investments for。For x。

 so this is a summary in the sense of what we did in the investment example for our training data。



![](img/063695d28a0b00516d0922646f182d3f_19.png)

And what we wanted to get was an idea of the standard error of alphapha hat。



![](img/063695d28a0b00516d0922646f182d3f_21.png)

Now and we made the point earlier that ideally， if we had access to the population。

 we could get more training data， we could simply grab more samples of training data from the population。

 more investments。

![](img/063695d28a0b00516d0922646f182d3f_23.png)

![](img/063695d28a0b00516d0922646f182d3f_24.png)

From the possible population investments， you mean like a new sample， the same size。

 exactly a new sample， and from the new sample， do the same analysis。

 get an estimate alpha hat and do that many times。

![](img/063695d28a0b00516d0922646f182d3f_26.png)

![](img/063695d28a0b00516d0922646f182d3f_27.png)

![](img/063695d28a0b00516d0922646f182d3f_28.png)

And we showed how you can do that on the computer in the previous example。

 but it made the point that not often can you actually do that in practice because you don't have access to the population。

 you can't get more training data typically what you have to work with is just your given training example。

 So the bootstrap， a way of thing of the bootstrap in the abstract is hey well。

 we don't have access to the population， let's replace the population which we don't have by。



![](img/063695d28a0b00516d0922646f182d3f_30.png)

![](img/063695d28a0b00516d0922646f182d3f_31.png)

![](img/063695d28a0b00516d0922646f182d3f_32.png)

![](img/063695d28a0b00516d0922646f182d3f_33.png)

P hat， which in the Botraraps case， is。

![](img/063695d28a0b00516d0922646f182d3f_35.png)

It's that the train sample itself， it's a population that has put probability one over n。



![](img/063695d28a0b00516d0922646f182d3f_37.png)

![](img/063695d28a0b00516d0922646f182d3f_38.png)

And being the sample size on each of the training points， so it says our guess for the population。

 which we don't have access to but we have from a training sample。



![](img/063695d28a0b00516d0922646f182d3f_40.png)

Is if we have no more information， we're going to say。

 with equal probability that a training point can come from。



![](img/063695d28a0b00516d0922646f182d3f_42.png)

The first point we saw， the second point we saw up to the endthrop point we saw。

 So that's we called P hat。

![](img/063695d28a0b00516d0922646f182d3f_44.png)

The empirical distribution function， that's another name for that。



![](img/063695d28a0b00516d0922646f182d3f_46.png)

Empirical distribution function。So when you draw from this empirical distribution function。

Not as sampling with replacement。And that's what the bootstrap does， right the samples。



![](img/063695d28a0b00516d0922646f182d3f_48.png)

We saw that we draw samples with her placement from the training sample。

 that's this random sampling here Pt giving Z star， this is not the bootstrap sample。

 remember we're going to use a superscript star to indicate a bootstrap sample as distinct st from a training sample which has no superscript。



![](img/063695d28a0b00516d0922646f182d3f_50.png)

![](img/063695d28a0b00516d0922646f182d3f_51.png)

![](img/063695d28a0b00516d0922646f182d3f_52.png)

So。

![](img/063695d28a0b00516d0922646f182d3f_54.png)

This is one bootstrap draw， that's a sample of size N from our training sample now。

 a bootstrap sample， giving us a bootstrap data。

![](img/063695d28a0b00516d0922646f182d3f_56.png)

And from that we drive the estimate， again， in this case， it's alpha。



![](img/063695d28a0b00516d0922646f182d3f_58.png)

![](img/063695d28a0b00516d0922646f182d3f_59.png)

And we call Alpha hat star。So bootsottrap sampling simply repeats this operation a few hundred times。

 say for each time we get a bootstrap sample of size N and we get a bootstrap。



![](img/063695d28a0b00516d0922646f182d3f_61.png)

![](img/063695d28a0b00516d0922646f182d3f_62.png)

Quantity alpha hat star。And then the standard Arab Alpha hat star are the bootsstrrap estimate of standard error of Alpha hat。



![](img/063695d28a0b00516d0922646f182d3f_64.png)

So there's nothing new here， we're simply describing what we already saw in more general terms。



![](img/063695d28a0b00516d0922646f182d3f_66.png)

But we can now think about how we carry this out in more complex situations。



![](img/063695d28a0b00516d0922646f182d3f_68.png)

![](img/063695d28a0b00516d0922646f182d3f_69.png)

So in general， we need to figure out how we can carry out bootststrrap sampling， for example。

 suppose we have a time series。

![](img/063695d28a0b00516d0922646f182d3f_71.png)

So。

![](img/063695d28a0b00516d0922646f182d3f_73.png)

Let's draw。The time axis here。And we have a series like for example， stock price。



![](img/063695d28a0b00516d0922646f182d3f_75.png)

And let's just draw some imaginary。Data。right。So this is。St let's called Y1。

 this is stock price at time1， stock price of time two， etc。And we want， for example。

 to predict the stock price from a given day for a given day from the previous day's stock price。

 So we'll fit a model， a regression model like we've seen to each each stock price as a function of the previous。



![](img/063695d28a0b00516d0922646f182d3f_77.png)

![](img/063695d28a0b00516d0922646f182d3f_78.png)

The stock place on the previous day。

![](img/063695d28a0b00516d0922646f182d3f_80.png)

Well， that's fine we can do that， we can do that by least squares。

But now we might imagine doing bootsshoprap sampling at the way we just described where we sample with replacement from the data。

 well one problem with that that's a significant problem is that the data are not independent， right？



![](img/063695d28a0b00516d0922646f182d3f_82.png)

![](img/063695d28a0b00516d0922646f182d3f_83.png)

![](img/063695d28a0b00516d0922646f182d3f_84.png)

There's correlation in the time series。We expect the stock price for a given day to be correlated with the stock price from the previous day。

 a matter of fact ifre to predict the stock price from a given day from the previous day。

 we hope there's correlation if they were independent the prediction wouldn't be very useful。



![](img/063695d28a0b00516d0922646f182d3f_86.png)

![](img/063695d28a0b00516d0922646f182d3f_87.png)

![](img/063695d28a0b00516d0922646f182d3f_88.png)

But this creates a problem for the bootstrap because in the previous。



![](img/063695d28a0b00516d0922646f182d3f_90.png)

In the schematic。We were， we were sampling here， or we assume that the sampling。



![](img/063695d28a0b00516d0922646f182d3f_92.png)

嗯。Was IID from the population but in this situation。

 that's not a reasonable assumption because the observations are not independent。 So in general。

 when you set up the bootstrap and arrange for the sampling you must figure out what parts of the data are independent。

 so one thing people do in a time series。

![](img/063695d28a0b00516d0922646f182d3f_94.png)

![](img/063695d28a0b00516d0922646f182d3f_95.png)

![](img/063695d28a0b00516d0922646f182d3f_96.png)

![](img/063695d28a0b00516d0922646f182d3f_97.png)

Because the observations are not independent to correlate across time as to use what's called the block Botrap。



![](img/063695d28a0b00516d0922646f182d3f_99.png)

The block bootstrap divides the data up into blocks。In between blocks。

 one assumes that things are independent。My spelling is not good okay so for example。

 if we use a block size of three， we might these be the first block， these three observations。

 these three be the second block， these be the next block。

 and now our sampling units are not the individual observations but the entire blocks so we would sample wither placement from all the blocks。



![](img/063695d28a0b00516d0922646f182d3f_101.png)

![](img/063695d28a0b00516d0922646f182d3f_102.png)

And then pace them together into a new time series。



![](img/063695d28a0b00516d0922646f182d3f_104.png)

Now is this guy's sample he might become the first block。Psych blocklock， etc cea。

 and then we past them together in order， and that becomes a bootstrap sample to which we apply the same the estimate in this case。

 a regression model。 So the point is you have to sample the things that are uncorrelated。



![](img/063695d28a0b00516d0922646f182d3f_106.png)

![](img/063695d28a0b00516d0922646f182d3f_107.png)

![](img/063695d28a0b00516d0922646f182d3f_108.png)

You have to range for find the parts the data that are uncorrelated。



![](img/063695d28a0b00516d0922646f182d3f_110.png)

And use that as the basis for bootstrap sampling In this case we use a block of size3 under the assumption that beyond a time lag of three。

 things are somewhat uncorrelated， but within a block we expect correlation。

 so we keep the blocks intact， sample them as units。That's called the block Botrap。



![](img/063695d28a0b00516d0922646f182d3f_112.png)

I say that here， okay。

![](img/063695d28a0b00516d0922646f182d3f_114.png)

So we talked about the bootstrap for standard errors and that the main use of the bootststrrap is to estimate the standard errors of an estimate like the alpha hat in our investment example。



![](img/063695d28a0b00516d0922646f182d3f_116.png)

![](img/063695d28a0b00516d0922646f182d3f_117.png)

Another very common use of the woodrap is for a confidence interval。So let's go back to。



![](img/063695d28a0b00516d0922646f182d3f_119.png)

Conferal for a premise， we go back to slide 29。And remember。

 this is that the histogram we got from the bootsstrroprap for the dev of alpha hat over bootststrrap sampling。



![](img/063695d28a0b00516d0922646f182d3f_121.png)

Thousand bootsrap samples。And if you look at this histogram。

 a reasonable way to derive a confidence interval is take the percentiles from this histogram。



![](img/063695d28a0b00516d0922646f182d3f_123.png)

![](img/063695d28a0b00516d0922646f182d3f_124.png)

I suppose I want a 0。9 conference interval。So that it contains a true value with probably 90%。

 makes sense to grab the fifth and 95th% quantile so lets。



![](img/063695d28a0b00516d0922646f182d3f_126.png)

![](img/063695d28a0b00516d0922646f182d3f_127.png)

儿子。Friing。F% point of this stogram。And the 95% point of that historyogram。

There's 1 thousand0 points here， so that actually the 5 percent point would be the 50th biggest and 950th biggest value of alpha。

 I mean smallest and biggest。

![](img/063695d28a0b00516d0922646f182d3f_129.png)

![](img/063695d28a0b00516d0922646f182d3f_130.png)

Seit that wrong sure they it's just like I。

![](img/063695d28a0b00516d0922646f182d3f_132.png)

Okay， so if we do that， that provides a confidences interval for alpha and what do we actually get。

 I've got that back on the slide。

![](img/063695d28a0b00516d0922646f182d3f_134.png)

Is that so 0。43 and 0。72。

![](img/063695d28a0b00516d0922646f182d3f_136.png)

So this is actually an appropriate confidence interval for alpha。



![](img/063695d28a0b00516d0922646f182d3f_138.png)

And remember， how to interpret this conference interval all。

 what this means is that if we were to repeat this experiment from the population many times。



![](img/063695d28a0b00516d0922646f182d3f_140.png)

![](img/063695d28a0b00516d0922646f182d3f_141.png)

We expect it would be the case that the conference interval that we obtained would contain the true value of alpha。



![](img/063695d28a0b00516d0922646f182d3f_143.png)

90% of the time， that's what a 90% comp。

![](img/063695d28a0b00516d0922646f182d3f_145.png)

Yes， we talked about that earlier。 This particular way of constructing interval is called a bootstrap percentile interval。

 And there's actually an entire field of in statistics to do with conference intervals in the bootsottrap。

 And theres many， many， many papers and books that have written about this topic。

 This bootstrap percentile interval is the simplest way of constructing a conference interval from the bootstrap。

 and it's very useful。You just use the histogram of bootstrap values themselves and use their percentiles。

So we've talked about the bootstrap， for standard errors and confidence intervals。



![](img/063695d28a0b00516d0922646f182d3f_147.png)

How about。Predictionary， like misclassification error we've seen in the course already。Well。

 the major tool we talked about for that was cross validation。let's think back across validation。

 how it worked。 We have K folds and K fold across validation。 We divide the data up into K parts。



![](img/063695d28a0b00516d0922646f182d3f_149.png)

![](img/063695d28a0b00516d0922646f182d3f_150.png)

Let's say five and I'll just draw this again。And remember what we did。

 here's our five parts created at random。

![](img/063695d28a0b00516d0922646f182d3f_152.png)

Kful Cross Foundation is like a member like a5 act play of Ks5。



![](img/063695d28a0b00516d0922646f182d3f_154.png)

At one stage of the play， these four are the training set， these four parts。



![](img/063695d28a0b00516d0922646f182d3f_156.png)

And the remaining fifth part。Is a validation part， said。



![](img/063695d28a0b00516d0922646f182d3f_158.png)

嗯。And cross validation fits to the four parts， fits a model。

 and then uses that model to predict the fifth part。 And then， and in turn， we then。



![](img/063695d28a0b00516d0922646f182d3f_160.png)

![](img/063695d28a0b00516d0922646f182d3f_161.png)

This guy gets to play the role of the validation set the next stage and this guy， et cetera。

 and there's just five stages。

![](img/063695d28a0b00516d0922646f182d3f_163.png)

But a crucial part of Cross validation was that when we do one stage like this。

 there's no overlap between the training set and the validation set。

 now the observations in one do not appear in the other。



![](img/063695d28a0b00516d0922646f182d3f_165.png)

![](img/063695d28a0b00516d0922646f182d3f_166.png)

And that's important because we're trying to an idea of test set error on new data。



![](img/063695d28a0b00516d0922646f182d3f_168.png)

So cross validation is taking a piece of data。

![](img/063695d28a0b00516d0922646f182d3f_170.png)

Separating it out from the training set， so when I fit on this data and predict on this data。

 this data is a sense new， it hasn't been seen by the training by the model trained on the first floor。



![](img/063695d28a0b00516d0922646f182d3f_172.png)

![](img/063695d28a0b00516d0922646f182d3f_173.png)

So there's a separation， a clean separation between training and validation。



![](img/063695d28a0b00516d0922646f182d3f_175.png)

Well， what if we're to try to use the Botrap estimate prediction error？Let's just draw。Again。

 the bootstrap sampling process， here's my training set。

And I'm going to draw samples wither placement from the training set， bootsshop samples。

 each one of the same size and a few hundred of them。Well。The first kind of obvious idea is to say。

 well， let's train on a bootstrap data set。Predict the original training set as my validation set。

I do that for each bootstrap sample， each bootstrap sample gets to play the role of the training set to fit。

 and then I'm going to predict my original training sample as my validation set。Well。

 there's a big problem with that。 And the problem is there's an overlap between the。

Bootrap data sets and the original data set。In particular。

 about two thirds of the original data points appear in each bootsstrrapap sample。

 and you should think about how to prove this。 It's not hard， but it's it's。

You'll find out that about two3 of these points。So the training set points are in the bootsstrrap sample。

This creates a problem because now when I when I'm I train here and then I do the prediction of a training set。

Two thirds are the points。Am。In this training set have already been seen by the model。

Because they're in the bootsotrap data set。 So on average。

 there's this two third overlap means that most of the training points are not novel。

So this is a big problem because the。嗯。Prediction error from this process be be will be biased downward。

 It'll be a lot lower than the actual prediction error because I'm predicting two thirds of the points I'm predicting I've already seen in the bootsottrap data set。

So this is not a good way of estimating predictionre。

I say that it underestimates a true predictionary quite dramatically。

Now you can the other way around you could train on the training set and use the bootstrap samples as the validation sets。

 it's even worse and you can think about why that is。

 so it's even worse in the sense it's going to be even more biased。



![](img/063695d28a0b00516d0922646f182d3f_177.png)

Well， how do you fix this problem？You can fix it by when you train on the Botrap sample and then predict the training sample。



![](img/063695d28a0b00516d0922646f182d3f_179.png)

Just recording the predictions for the points that did not occur in the Botrap sample。

 that was the points that are in actually novel points。



![](img/063695d28a0b00516d0922646f182d3f_181.png)

![](img/063695d28a0b00516d0922646f182d3f_182.png)

But then this gets quite complicated。 And in the end， it's really not worth it。 If you。

 if you push this idea to its its conclusion， you can get something which is about as good as cross validation。

 but it's much more complicated。 So our view is for。



![](img/063695d28a0b00516d0922646f182d3f_184.png)

![](img/063695d28a0b00516d0922646f182d3f_185.png)

![](img/063695d28a0b00516d0922646f182d3f_186.png)

For this particular problem， the cross foundation is。It's easier and better the thing we recommend。



![](img/063695d28a0b00516d0922646f182d3f_188.png)

If I can just interrupt Rob that actually brings up an interesting point a lot of the time we have simple methods you know like cross validation and then a new method comes along like using bootsottrap to estimate prediction error and we see it's quite a lot more complicated and you don't get much in return and so our general philosophy is if you can get the job done with a simple method it's far better than using a more complicated method just because it maybe looks sexy or whatever so keep it simple that's the idea。



![](img/063695d28a0b00516d0922646f182d3f_190.png)

![](img/063695d28a0b00516d0922646f182d3f_191.png)

![](img/063695d28a0b00516d0922646f182d3f_192.png)

![](img/063695d28a0b00516d0922646f182d3f_193.png)

![](img/063695d28a0b00516d0922646f182d3f_194.png)

![](img/063695d28a0b00516d0922646f182d3f_195.png)

![](img/063695d28a0b00516d0922646f182d3f_196.png)