# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P56：P56 StatsLearning Lect10d 120213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

So our next topic is boostosting。AndBosting is a relatively new method as well。

 and similar to bag and random forest， it gives prediction models at are averages over trees。

But there's a fundamental difference， random forest and bagging。

 the trees that are averaged are all equivalent and the aver is just used to reduce variances with boosting it's a sequential method and each of the trees that's added into the mix is added to improve on the performance of the previous collection of trees so that's a fundamental difference。

We look at first boosting for regression trees， it's simpler to explain there and we just think of it as a sequential algorithm and the bottom line is with boosting what we do is we keep on foot trees to the residuals and so we improve the fit and so we can describe that very easily here。

 we start off and we try to build a function f of x。



![](img/e89daee6b3d613ba284cf6f18f087920_1.png)

![](img/e89daee6b3d613ba284cf6f18f087920_2.png)

![](img/e89daee6b3d613ba284cf6f18f087920_3.png)

![](img/e89daee6b3d613ba284cf6f18f087920_4.png)

![](img/e89daee6b3d613ba284cf6f18f087920_5.png)

Which is going to be an average of trees， and this is evaluated at some point x。

 so we think of it as a function。

![](img/e89daee6b3d613ba284cf6f18f087920_7.png)

![](img/e89daee6b3d613ba284cf6f18f087920_8.png)

It'll start over zero and the residuals will just be the data observations Yi。



![](img/e89daee6b3d613ba284cf6f18f087920_10.png)

And what we're going to do is sequentially。

![](img/e89daee6b3d613ba284cf6f18f087920_12.png)

Going from B， going from1 up to capital B， we'll just keep on going。

 we're going to fit a tree with D splits， in other words D plus1 terminal notes to the training data X and R where R is the current residual。

 initially the residuals are just the observations。



![](img/e89daee6b3d613ba284cf6f18f087920_14.png)

![](img/e89daee6b3d613ba284cf6f18f087920_15.png)

![](img/e89daee6b3d613ba284cf6f18f087920_16.png)

![](img/e89daee6b3d613ba284cf6f18f087920_17.png)

So we build a relatively small tree to the residuals and then we're going to update the function by adding that tree into our current model。

 so our current model starts over zero and now repeatedly we're going to add in the tree that we've just grown and when we add it in we actually shrink it down by a factor lambda。



![](img/e89daee6b3d613ba284cf6f18f087920_19.png)

![](img/e89daee6b3d613ba284cf6f18f087920_20.png)

![](img/e89daee6b3d613ba284cf6f18f087920_21.png)

![](img/e89daee6b3d613ba284cf6f18f087920_22.png)

So there's these two components grow in a tree to the residuals and then adding in some shrununkken of it into your current model the lamb is pretty small right it's like we're going to see about 0。

01 for example as a value lambda so really shrinking down okay and then of course you update the residuals because the residuals will change by a corresponding amount。



![](img/e89daee6b3d613ba284cf6f18f087920_24.png)

![](img/e89daee6b3d613ba284cf6f18f087920_25.png)

![](img/e89daee6b3d613ba284cf6f18f087920_26.png)

![](img/e89daee6b3d613ba284cf6f18f087920_27.png)

And so you keep on doing that gr to the residuals， add it into your function， down the residuals。

 and continue it。

![](img/e89daee6b3d613ba284cf6f18f087920_29.png)

And you can see at the end of the day your model， your boosted model has this form。

 it's a sum of shrunken trees， all B of them growing to the data Now these trees are not independent of each other like they were in random forest and boosting because each tree was growing to the residuals left over from the previous collection of trees。



![](img/e89daee6b3d613ba284cf6f18f087920_31.png)

![](img/e89daee6b3d613ba284cf6f18f087920_32.png)

![](img/e89daee6b3d613ba284cf6f18f087920_33.png)

![](img/e89daee6b3d613ba284cf6f18f087920_34.png)

Okay， so what's the idea behind this procedure， well for a single tree。

 we can fit it large tree of the data and if you fit the data hard with a large tree， we can overfit。

So in contrast to the idea of boosting is to learn more slowly， so we start with why。

 we build a tree to y and it can sometimes be a small tree， but rather than accept the full tree。

 we shrink it back by a lot， by for example， factor 0。01。And then we take residuals and repeat。

 so the idea being that instead of to avoid overfitting， we're going to fit very slowly。

And at each stage， try to pick up a small piece of the signal with the next tree。

So instead of trying to grab a lot of signal with a large amount of fittingning。

 we're going it fits very slowly in small parts， shrinking each time in order to。

To approximate the signal without overfitting and as a nice consequence is we don't actually have to grow very large trees as we did in random forest。

 quite often smaller trees fit in this slow sequential manner will be very effective。

Booosting also works for classification and it's similar in spirit， but it's slightly more complex。

 so we're not going to go in detail here， and in fact we don't go into more detail in the textbook。

 but there's a detail section in our other textbook elements of statistical learning in chapter 10。

 and you can learn about how boosting works for classification。



![](img/e89daee6b3d613ba284cf6f18f087920_36.png)

![](img/e89daee6b3d613ba284cf6f18f087920_37.png)

![](img/e89daee6b3d613ba284cf6f18f087920_38.png)

![](img/e89daee6b3d613ba284cf6f18f087920_39.png)

![](img/e89daee6b3d613ba284cf6f18f087920_40.png)

It doesnn't stop you using boostosting for classification。

 there's the R package GBM which we use in the exercises and the examples and we'll use in the R session and that handles a variety of regression and classification problems。



![](img/e89daee6b3d613ba284cf6f18f087920_42.png)

![](img/e89daee6b3d613ba284cf6f18f087920_43.png)

Okay， so let's see the results of boosting for the gene expression data。



![](img/e89daee6b3d613ba284cf6f18f087920_45.png)

These are test errors， the orange curve is boosting depth one。

 so what that means is actually each tree's got a single split， sometimes called a stump so a very。

 very simple tree。

![](img/e89daee6b3d613ba284cf6f18f087920_47.png)

Which again， might seem a little crazy， but we're going to use 5，000 of them。

 and when they're using in this sequential slow fitting way， it actually does quite well。

 the error is about7 or 8% random force。

![](img/e89daee6b3d613ba284cf6f18f087920_49.png)

Oh sorry， ran a forest or a little higher here they're about 12 or 13%。嗯。



![](img/e89daee6b3d613ba284cf6f18f087920_51.png)

Using a depth2 tree， which means two splits。We do maybe a little worse than the simple stump model。



![](img/e89daee6b3d613ba284cf6f18f087920_53.png)

So again， it's quite striking that a very， very simple model applied in a slow and sequential way at the end of it we get an ensemble that actually predicts very well So Robert it seems like the depth of the tree that you use in boosting becomes a tuning parameter。



![](img/e89daee6b3d613ba284cf6f18f087920_55.png)

![](img/e89daee6b3d613ba284cf6f18f087920_56.png)

![](img/e89daee6b3d613ba284cf6f18f087920_57.png)

Exactly， well， thank you for the leading to the next slide， which is。



![](img/e89daee6b3d613ba284cf6f18f087920_59.png)

The turningning parameters， so there's a bunch of turningning parameters，revor to just mention one。

 the depth， know let me just put them all up。

![](img/e89daee6b3d613ba284cf6f18f087920_61.png)

So well， the third one here I've written is what Treors mentioned the number of splits of the tree。

Is a tuning parameter？呃，对。The depth is called something D is if D is one， it's simply a stump。

 which we saw was successful in the previous example。 And if we D is larger。

 it allows that the interaction between predictors。

 So typically when tries a few values of D maybe be d equals one to。

4 and8 that might be a typical example depending on the size of your data set and the number of predictors if D is one each little tree caninvolve a single variable right so it's actually an additive function of single variables so there's no interactions allowed and if D equals two it can involve at most two variables right so there's pairwise interactions interesting。

So that's one tuning parameter。The number of trees is also tuning parameter。

Unlike in random forests with a number of trees。You just went far enough so that you。



![](img/e89daee6b3d613ba284cf6f18f087920_63.png)

T you stop it getting the benefit of averaging right I think it's still the case that the number of trees is not a hugely important parameter it's possible to overfit。

 but it takes， I think a very large number to typically start to cause overfitting and here we see we're up to 5000 in and that much is really happening yet terms of overfitting I think it especially depends on the problem。



![](img/e89daee6b3d613ba284cf6f18f087920_65.png)

![](img/e89daee6b3d613ba284cf6f18f087920_66.png)

![](img/e89daee6b3d613ba284cf6f18f087920_67.png)

In some problems， you'll see the curves really going up。

 but with classification problems it often just levels out like that。



![](img/e89daee6b3d613ba284cf6f18f087920_69.png)

So the other one is the shrinkage parameter， remember every time we grow a tree。

 we don't accept the full tree rather we shrink it back by a quite small fraction and typically 0。

01 to 0。001 are the choices one uses。So these。These three tuning parameters。

One can just try a few values of each one。And look at the cross validation error over the grid to choose。

We've got good sets of parameters。

![](img/e89daee6b3d613ba284cf6f18f087920_71.png)

HereSo I have a couple more examples here actually from our earlier data mining book。

 this is the California H data。

![](img/e89daee6b3d613ba284cf6f18f087920_73.png)

Looking at the housing prices and。We have the。The test error here is a function of number of trees for a number of methods we've talked about。

Random force M equals 2 have to remember how many variables there are。

 we have to look our in chapter 10 15 of our book to。



![](img/e89daee6b3d613ba284cf6f18f087920_75.png)

![](img/e89daee6b3d613ba284cf6f18f087920_76.png)

To check that， but the using random force with only two variables allowed at each split gives you an error of about 0。

39。

![](img/e89daee6b3d613ba284cf6f18f087920_78.png)

![](img/e89daee6b3d613ba284cf6f18f087920_79.png)

Random forest with more splits improved things a bit GBM。



![](img/e89daee6b3d613ba284cf6f18f087920_81.png)

Graandient Boing machine， this is the R package that does boosting that's we'll see in the lab with depth4 and eight trees are doing somewhat better。



![](img/e89daee6b3d613ba284cf6f18f087920_83.png)

![](img/e89daee6b3d613ba284cf6f18f087920_84.png)

![](img/e89daee6b3d613ba284cf6f18f087920_85.png)

Looks like it looks like they're still on their way down as well， exactly。

 so maybe in this example one should have run even more trees。



![](img/e89daee6b3d613ba284cf6f18f087920_87.png)

Another example， this is a spam data from our the earlier book chapter 15。

 this is again a two class problem。

![](img/e89daee6b3d613ba284cf6f18f087920_89.png)

![](img/e89daee6b3d613ba284cf6f18f087920_90.png)

WithAbout 50 predictors， what do we have here？Well， let's first。

 another case where a single tree is really not very good right。

 we've even truncated a scale here because they're going on at somewhere above 7% single tree。



![](img/e89daee6b3d613ba284cf6f18f087920_92.png)

![](img/e89daee6b3d613ba284cf6f18f087920_93.png)

Bgging as we bag， we level off at around5。 a half percent。



![](img/e89daee6b3d613ba284cf6f18f087920_95.png)

Random force。Probably using the default of the square root of P as the number of predictors to selected every node has an error。

 reduces that by。

![](img/e89daee6b3d613ba284cf6f18f087920_97.png)

The scale is pretty compressed half of percent。

![](img/e89daee6b3d613ba284cf6f18f087920_99.png)

And then boosting five no trees gets another， maybe half percent。



![](img/e89daee6b3d613ba284cf6f18f087920_101.png)

So these two methods are quite good and they're， I think we've seen a lot of examples that're pretty comparable when you're say performance。



![](img/e89daee6b3d613ba284cf6f18f087920_103.png)

Those look like they might be quite two different curves。

 but actually if you do the proper statistical test， they they are not significantly different。



![](img/e89daee6b3d613ba284cf6f18f087920_105.png)

![](img/e89daee6b3d613ba284cf6f18f087920_106.png)

Okay， this actually last topic， variable， the importance of variables。

 how do you measure importance of variables in trees and bagging， boosting them？



![](img/e89daee6b3d613ba284cf6f18f087920_108.png)

![](img/e89daee6b3d613ba284cf6f18f087920_109.png)

In random forest， well， there's no single parameter no coefficient with the standard error you can refer to because trees use variables in multiple places right and every time you split a variable could participate in the split。



![](img/e89daee6b3d613ba284cf6f18f087920_111.png)

![](img/e89daee6b3d613ba284cf6f18f087920_112.png)

So what's done in bagging random forest is we one records the。The total。

Drop in RSS for a given predictor over all splits in the tree。

 so if we look at all the possible sps we look to see why the variable was involved in that split。

 if it was， we measure how much it dropped the RSS and then thiss average over all the trees。



![](img/e89daee6b3d613ba284cf6f18f087920_114.png)

![](img/e89daee6b3d613ba284cf6f18f087920_115.png)

![](img/e89daee6b3d613ba284cf6f18f087920_116.png)

So the higher， the better。

![](img/e89daee6b3d613ba284cf6f18f087920_118.png)

And。A similar thing with Gite indexex for classification trees。



![](img/e89daee6b3d613ba284cf6f18f087920_120.png)

So what you get is essentially a qualitative ranking。

 this is the variable importance for the heart data and you can see the Ehelium stress test is at a very importance of 100。

 things are usually normalized so that the top variable has 100 and then you can see the other variables are indicated here in terms of their importance from calcium down to。



![](img/e89daee6b3d613ba284cf6f18f087920_122.png)

![](img/e89daee6b3d613ba284cf6f18f087920_123.png)

![](img/e89daee6b3d613ba284cf6f18f087920_124.png)

![](img/e89daee6b3d613ba284cf6f18f087920_125.png)

Varis of lower importance。 So these variable importance plots are quite an important part of the random forest toolkit。

 also used in boosting。 the same plot is used in boosting。



![](img/e89daee6b3d613ba284cf6f18f087920_127.png)

![](img/e89daee6b3d613ba284cf6f18f087920_128.png)

![](img/e89daee6b3d613ba284cf6f18f087920_129.png)

So to summarize， we've talked about decision trees and using ensembles of trees。

On the plus side they're simple and interpretable when they're small。

 but as we've seen in the examples we've seen in other examples that they're often not very competitive in terms of prediction error。

 so some newer methods， bagging random forest and boosting use trees in combination as an ensemble。



![](img/e89daee6b3d613ba284cf6f18f087920_131.png)

![](img/e89daee6b3d613ba284cf6f18f087920_132.png)

And in the process they can prove predictionary quite considerably。

And the result is that the last two methods we talked about。

 random forest and boosting are really among the state of the art techniques for supervised learning。



![](img/e89daee6b3d613ba284cf6f18f087920_134.png)

![](img/e89daee6b3d613ba284cf6f18f087920_135.png)

So if you're interested in prediction and really just prediction performance。

 they're very good techniques。For interpretation， as we've seen， they're more challenging。

