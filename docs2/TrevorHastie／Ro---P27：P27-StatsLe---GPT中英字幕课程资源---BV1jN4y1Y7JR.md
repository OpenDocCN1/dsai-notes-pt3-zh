# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P27：P27 StatsLearning Lect7c 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/4010de8d995498c29a4cb8e7b3f2493f_0.png)

Okay， so we just talked about cross validation， which is an important technique for both regression and classification for getting an idea of test error and for assessing。

How complex a model to fit， for example， how many features to include in a model or the order of a polynomial。



![](img/4010de8d995498c29a4cb8e7b3f2493f_2.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_3.png)

And it's a very important technique， and sometimes with important techniques like this。

 it's a good idea to just see how you one might do it wrong。

And this is actually an era that we've seen people a way in which people use cross validation in。

In a wrong fashion， which can have actually very serious consequences。

 especially these days where you get very wide data sets and this next example is going to show you such a case。

 So we'll go go into detail of how one can do it wrong and how people use it wrong and we' try to avoid that error。

Hep you to avoid that error so let's think of a simple thought experiment， we've got 5，00 predictors。

 for example， in 50 samples， this is again a more and more commonly occurring case we have more predictors and samples。



![](img/4010de8d995498c29a4cb8e7b3f2493f_5.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_6.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_7.png)

And we have two classes we're trying to predict， okay？



![](img/4010de8d995498c29a4cb8e7b3f2493f_9.png)

And suppose we do the following， we've built a simple classifier in the following way。

 first of all we filter the predictors， find that the 100 predictors having the largest correlation on their own with the class labels。



![](img/4010de8d995498c29a4cb8e7b3f2493f_11.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_12.png)

So we're going to cherry pick here， we pick the top 100 predictors， keep them。

 and again they're chosen the basis of their correlation with the class labels on their own。

 and we throw away the remaining 4900 predictors okay。



![](img/4010de8d995498c29a4cb8e7b3f2493f_14.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_15.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_16.png)

And then we use 100 predictors we use them in a classifier。

 such as a log jump model using only of these 100 predictors and we omit the other 4900。



![](img/4010de8d995498c29a4cb8e7b3f2493f_18.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_19.png)

So if that's not unreasonable， we are building a classifier， for example。

 maybe we don't want to have to deal with 5，000 predictors， we just want a small number of them。



![](img/4010de8d995498c29a4cb8e7b3f2493f_21.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_22.png)

But the question we address here is， how do we get an idea of the test set error of this classifier cross validation？



![](img/4010de8d995498c29a4cb8e7b3f2493f_24.png)

Okay， thank you。

![](img/4010de8d995498c29a4cb8e7b3f2493f_26.png)

But how can we- I mean what's tempting is to say， well。

 let's just forget the fact that we filtered the predictors in step one。

 that we chose the 100 best among the 5，000。

![](img/4010de8d995498c29a4cb8e7b3f2493f_28.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_29.png)

Let's just pretend like we started in step two， that we started with the 100 predictors。



![](img/4010de8d995498c29a4cb8e7b3f2493f_31.png)

And that was our data， can we apply cross validation in step two， forgetting about step one。



![](img/4010de8d995498c29a4cb8e7b3f2493f_33.png)

Well， no， this is a serious error。

![](img/4010de8d995498c29a4cb8e7b3f2493f_35.png)

Why is it an error， well the problem is is that the procedure。

 the classifier has already seen the labels of the training data。



![](img/4010de8d995498c29a4cb8e7b3f2493f_37.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_38.png)

In step one right in choosing。

![](img/4010de8d995498c29a4cb8e7b3f2493f_40.png)

The best 100 predictors， it's looked at all the labels of all the samples。



![](img/4010de8d995498c29a4cb8e7b3f2493f_42.png)

So the predictors have already used。The full set of observations in the fitting when we chose those predictors。

 so that's a form of training。

![](img/4010de8d995498c29a4cb8e7b3f2493f_44.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_45.png)

And we can't ignore it in the validation process。So， the。



![](img/4010de8d995498c29a4cb8e7b3f2493f_47.png)

The point is we're not allowed to just start in step two and ignore the fact that we applied step one。



![](img/4010de8d995498c29a4cb8e7b3f2493f_49.png)

Why is that？this is something you should try yourself。

 you can simulate data with class labels having no correlation with the outcome so that with equal classes。

 the true test error is 50%。

![](img/4010de8d995498c29a4cb8e7b3f2493f_51.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_52.png)

But cross validation， they ignore step one will give you an error rate of zero。



![](img/4010de8d995498c29a4cb8e7b3f2493f_54.png)

So it's a serious， serious bias。

![](img/4010de8d995498c29a4cb8e7b3f2493f_56.png)

Cros validation telling you your classifier is perfect when in fact your classifier is the same with slipping a coin。



![](img/4010de8d995498c29a4cb8e7b3f2493f_58.png)

Okay。Think about why this happens if you if we。

![](img/4010de8d995498c29a4cb8e7b3f2493f_60.png)

Actually， we make the point more clearly if we increase the 5000 to maybe。



![](img/4010de8d995498c29a4cb8e7b3f2493f_62.png)

5 million predictors Supp we have 5 million predictors and 50 samples。

 and again there's no correlation in the population between the predictors and the class labels。



![](img/4010de8d995498c29a4cb8e7b3f2493f_64.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_65.png)

We go ahead and we pick the best 100 among those 5 million predictors。



![](img/4010de8d995498c29a4cb8e7b3f2493f_67.png)

We're going to find some very good looking predictors， despite the fact in the population。

 no predictor has correlation with the outcome in the data， if we look at the best among 5 million。

 we're going to find some very good predictors that look in the data like they have a lot of power for classifying。



![](img/4010de8d995498c29a4cb8e7b3f2493f_69.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_70.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_71.png)

If we then pretend like those were the predictions we started with those 100 cherry picked out of 5 million。



![](img/4010de8d995498c29a4cb8e7b3f2493f_73.png)

They're going to look very good to cross validation。



![](img/4010de8d995498c29a4cb8e7b3f2493f_75.png)

So we fooled cross validation by。

![](img/4010de8d995498c29a4cb8e7b3f2493f_77.png)

嗯。Leaving out the first filtering step and giving it a very cherry picked set of predictors in the second set。



![](img/4010de8d995498c29a4cb8e7b3f2493f_79.png)

This seems like it's， you know， it was done on purpose here， but actually in some genomic studies。

 researchers are faced with you know， tens of thousands of genes maybe and it's just hard to handle them。

 So they do some kind of screening in the beginning just to reduce the number of variables down to a manageable set。



![](img/4010de8d995498c29a4cb8e7b3f2493f_81.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_82.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_83.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_84.png)

You know， and， you know， and then forget about it afterwards。 But that leads to this kind of bias。



![](img/4010de8d995498c29a4cb8e7b3f2493f_86.png)

Right， so as I say here， this I think it's good to understand this by actually trying this yourself just in R。

 you've learned some R now， you can simulate a situation just like this where the true test error is 50%。



![](img/4010de8d995498c29a4cb8e7b3f2493f_88.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_89.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_90.png)

And you simulate a large number of predictors and apply cross foundation in step two and you'll see the error is actually very low。

 the CV error is low， and as Trevor mentioned this is not something we've made up。

 this is actually an error which commonly occurs in genomics in published papers in high profile journals。



![](img/4010de8d995498c29a4cb8e7b3f2493f_92.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_93.png)

So。

![](img/4010de8d995498c29a4cb8e7b3f2493f_95.png)

We told you the wrong way to do things， applying cross validation in step two， well。

 the right way is to apply cross validation to both steps。



![](img/4010de8d995498c29a4cb8e7b3f2493f_97.png)

So in this picture。

![](img/4010de8d995498c29a4cb8e7b3f2493f_99.png)

The next few pictures will make this clear。Here I've got the wrong way I just described。

So I've got my samples here and my predictors here。And now。



![](img/4010de8d995498c29a4cb8e7b3f2493f_101.png)

In this， in this。First approach， we first select the best set of predictors based on the correlation with the outcome that's over here。



![](img/4010de8d995498c29a4cb8e7b3f2493f_103.png)

嗯。And we keep these predictors。

![](img/4010de8d995498c29a4cb8e7b3f2493f_105.png)

And throw the rest away。And now in step two， we're going to apply cross Foundation。

 what does that mean we divide the data up into say five parts？



![](img/4010de8d995498c29a4cb8e7b3f2493f_107.png)

We apply our classifier to four parts and we predict the response in the left out part。



![](img/4010de8d995498c29a4cb8e7b3f2493f_109.png)

So again， this is wrong because the filtering step， which selected these predictors。

 has used the response variable for all the samples。



![](img/4010de8d995498c29a4cb8e7b3f2493f_111.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_112.png)

So this is the wrong way to do things。The right way。



![](img/4010de8d995498c29a4cb8e7b3f2493f_114.png)

Is as follows， we first， we define our folds， five folds cross validation。 before we do any fitting。

 we were moved。

![](img/4010de8d995498c29a4cb8e7b3f2493f_116.png)

One of the folds， all the data for that fold， the predictors and the response variable。



![](img/4010de8d995498c29a4cb8e7b3f2493f_118.png)

And now we can do whatever we want on the other four parts， we can filter and fit or however we want。



![](img/4010de8d995498c29a4cb8e7b3f2493f_120.png)

And when we finished our fitting， we then take the model and we predict the response for the left out part。



![](img/4010de8d995498c29a4cb8e7b3f2493f_122.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_123.png)

The key point being， though， that we we formed the folds before we。



![](img/4010de8d995498c29a4cb8e7b3f2493f_125.png)

Filter or do or fit to the data。In order that we're applying cross validation to the entire process。

 not just the second step。

![](img/4010de8d995498c29a4cb8e7b3f2493f_127.png)

So that's the right way to do it So in each of the four fifth swallows。

 we might screen off a different set of predictors each time， and we probably will。



![](img/4010de8d995498c29a4cb8e7b3f2493f_129.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_130.png)

And so that variability is going to get taken into accountant so this wrong way of doing cross validation is not something that we've made up it's it's actually something which I mentioned occurs in a lot of published papers and I've actually experienced it a number of times myself。



![](img/4010de8d995498c29a4cb8e7b3f2493f_132.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_133.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_134.png)

AF years ago， I was at a PhD oral in engineering here at Stanford。

And a lot of people in engineering are doing statistics as part of their work。

 This particular student was doing a。He was trying to predict heart disease from SNPps。

 SNPps are single base changes in the genome， so basically had a classification problem with。



![](img/4010de8d995498c29a4cb8e7b3f2493f_136.png)

I think about 100，000 predictors and to class response。



![](img/4010de8d995498c29a4cb8e7b3f2493f_138.png)

And he had done something very much like this， he had so many predictors he wanted to filter them。

 so he applied a filtering of some sort to the data set。



![](img/4010de8d995498c29a4cb8e7b3f2493f_140.png)

To reduce the 100，000 predictors， I think down to 1，000。

 and then he fits some sort of a model to the 1，000 predictors and he got an error rate of about 35%。

 I think。

![](img/4010de8d995498c29a4cb8e7b3f2493f_142.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_143.png)

Which doesn't sound that impressive， but for this particular area it was actually quite a low error rate。



![](img/4010de8d995498c29a4cb8e7b3f2493f_145.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_146.png)

嗯。And during the oral he presented this， and I said， actually， I think there's a problem with this。

 and I pointed out the fact that the point you've just seen that he actually had filtered the data。



![](img/4010de8d995498c29a4cb8e7b3f2493f_148.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_149.png)

And oh， sorry I didn't say that this give you have detail。

 he had applied cross validation in the second step， so he had filtered the data down to 1。

00 predictors。

![](img/4010de8d995498c29a4cb8e7b3f2493f_151.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_152.png)

He applied cross validation and the cross validation error rate was about 35% and he was quite happy and this was part of his presentation and I mentioned。

 well that doesn't look right to me because you。

![](img/4010de8d995498c29a4cb8e7b3f2493f_154.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_155.png)

They've done cross validation wrong in the way I just described。

He didn't agree and his supervisor didn't even agree who also I will not name the person wasn't he。

 wasn't you Well， the supervisor said， well， maybe you're right， but you're really being picky。

 you're splitting hairs hair it's not going to make much difference and I said， well。

 I think it might make a difference， you really have to go back and do it。



![](img/4010de8d995498c29a4cb8e7b3f2493f_157.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_158.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_159.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_160.png)

So a few months later， the student knocked at my door， my office paused。

He did pass because he had other things in the thesis which were reasonable。

 but a few months later he knocked on my door， came to my office。

 said I redid the experiment and the air rates now 50%， he was quite surprised and a bit upset。



![](img/4010de8d995498c29a4cb8e7b3f2493f_162.png)

But basically， it as I told you so， you know， that with a large number of predictors。

 if youve filter them， you've got to include that in your cross validation and if you don't。



![](img/4010de8d995498c29a4cb8e7b3f2493f_164.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_165.png)

You can incur a serious error in your cross validation estimate。



![](img/4010de8d995498c29a4cb8e7b3f2493f_167.png)

So。That was again， it happens and Trevor and I talk about this a lot and other people have written papers about this error。

 but people continue to make this error and cross validation so that's a big heads up and of course another heads up is not have Rob tips on on youral committee okay。



![](img/4010de8d995498c29a4cb8e7b3f2493f_169.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_170.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_171.png)

Okay so that completes our discussion across validation。

 we spent quite a bit of time on that shop because it's a very important technique for all the methods we'll see in this course。



![](img/4010de8d995498c29a4cb8e7b3f2493f_173.png)

![](img/4010de8d995498c29a4cb8e7b3f2493f_174.png)

In the next section， we'll talk about a closely related idea。

 but a different one called the Bostrrap。

![](img/4010de8d995498c29a4cb8e7b3f2493f_176.png)