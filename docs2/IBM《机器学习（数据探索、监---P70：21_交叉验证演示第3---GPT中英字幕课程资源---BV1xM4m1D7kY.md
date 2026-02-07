# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P70：21_交叉验证演示第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_0.png)

Welcome back to the notebook， in this section we're going to discuss hyperparameter tuning。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_2.png)

As a quick recap， hyperparameters versus parameters。

 the hyperparameter is going to be parts of our model that we as users will actually tune ourselves。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_4.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_5.png)

Versus parameters， which will be learned by the model using machine learning。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_7.png)

Now how do we come up with these hyperparameter in order to optimize the model performance？



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_9.png)

The way that we do this is going to be hyperparameter tuning。

 and that's going to involve using cross validation。 So multiple train test splits。

 as we just did in order to determine which hyperparameters are most likely to generalize well for an outside sample。

 So like we saw in lecture we had that curve in regards to the complexity versus the error。

 we want to find that perfect part of the curve， so we'll test many different hyperparameters to see which one of those hyperparameters will lead to the right level of complexity to minimize our error on a holdoutet。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_11.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_12.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_13.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_14.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_15.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_16.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_17.png)

So generally speaking， tuning those hyperparameter will increase or decrease the level of complexity of your model。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_19.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_20.png)

So a quick introduction to a function that we're going to use here， the Ge space。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_22.png)

The Geome space is just going to be here。 we say， one through 1000。

 And the number of values you want is equal to 4。 It's just that every single value in between will be a multiple of the prior value。

 So 10 is 10 times 1 and 100 is 10 times 10，100，10 times 100。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_24.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_25.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_26.png)

You can think of this in the same way NP do。Gome space， and I can say one comma 27， comma 4。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_28.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_29.png)

And you see that each one's three times the prior value。

So here we're going to create 10 values starting with1 times e to the negative 9。

1 times 10 to the power of negative 9， which just going to be 0。00。

 that many zeros1 up until just one itself。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_31.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_32.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_33.png)

So we see that that this is to the negative nine， negative8， negative7。

 so on and so forth till we get to 0。01。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_35.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_36.png)

0。1 and then just one。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_38.png)

So we have not yet introduced Laso and all I mentioned before and all you need to know here is that。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_40.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_41.png)

Changing this alpha value within Lasso。 So we're going to use this Lasso model。

 and we're going to initiate the same way we do with linear regression。

 and we're going to pass in this argument to alpha。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_43.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_44.png)

For each one of the alphas that we defined before。All you need to know is that the higher the alpha is。

 the less complex your model is。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_46.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_47.png)

The lower the alpha is， the more complex it is， and the closer it is to regular linear regression。

 And this will become even clearer as we go through the outputs of the actual coefficients for each one of our features that we have in our data set。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_49.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_50.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_51.png)

So we're starting off with scores is equal to a blank list and the coefficients is equal to a blank list and what we're going to want to do is actually see which one of our different alpha values is going to lead to the highest score for our holdoutset。

 so that's going to allow us to look through each one of these hyperparameters each of them being an alpha and see how much do we need to limit the complexity of our model。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_53.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_54.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_55.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_56.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_57.png)

So we for every alpha， initiate our lastso model。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_59.png)

We're then going to run our estimator， create our estimator using pipeline。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_61.png)

Now we'll get into this later as well， but it's very important whenever you're doing Lasso or Rige regression。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_63.png)

And we'll show you rid regression in a second that you scale your data first。

 always have to scale your data， otherwise the model will not work optimally。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_65.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_66.png)

So we scale it， then we run Lasso regression， so similar to the pipeline that we saw above。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_68.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_69.png)

And then we just get our predictions using cross valveel predicts。We pass in our estimator， our x。

 our y， and how we want to do cross validation。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_71.png)

And then we get our two score and a pen net to our scores。

 So we're going to do that for each one of our alphas。 So I'm going to run this。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_73.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_74.png)

And then we can look at for each one of our alphas what our score was， so this is very。

 this is the most complex of the models and this is the least complex， and we see that it performed。

 it has a pretty flat curve in regards to how much lowering complexity is actually helping in regards to our holdout set。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_76.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_77.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_78.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_79.png)

So。Just to make clear how we are actually making it more or less complex of a model。

 If we look at the coefficients for very little。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_81.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_82.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_83.png)

Alphas is for those that will reduce complexity much less。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_85.png)

You see that our coefficients are all different numerical values， whereas if I do alpha equals1。

 which is much higher alpha value， so much less complexity。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_87.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_88.png)

We end up removing many of our coefficients， right these coefficients are each going to relate to a feature。

 and we have removed those features essentially from our prediction values。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_90.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_91.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_92.png)

And I'm going to plot this and we're going to be able to see the trade off between higher complexity and our error rate。

 and we see that at's say level fairly level throughout。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_94.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_95.png)

So we probably do not need as much regularization as we're just working with plain Lasso with just the standard scalealar we're going to see in a second as we end up with many more features。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_97.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_98.png)

Using something like polynomial features， how we'll need to actually reduce the complexity and probably remove many of these actual interaction terms or squared values。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_100.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_101.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_102.png)

So that's what we're doing in this next exercise now we're going to add polynomial features to this pipeline。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_104.png)

We're then going to rerun the cross validation using the polynomial features added。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_106.png)

Now pipelines are going to input from first to last。

 and we discussed now we're adding on another step to our pipeline。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_108.png)

And let's think about the order that would make sense to add polynomial features to the data。

In the sequence， to add them in the appropriate place in the pipeline。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_110.png)

So if you think about it。Now， there's a little bit of an argument here。 but on one side。

 if you standardize first， then you will end up with negative and positive values for values that may have all been positive。

 therefore， changing all of your interaction terms。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_112.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_113.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_114.png)

Also， you're going to bring be bringing them down to much smaller scale， so rather than。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_116.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_117.png)

The first value times a second value both being above one and therefore increasing that value even more。

 if you scale it down to values that or maybe 0。5 and two， we're actually reducing that value。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_119.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_120.png)

So that's on one end of the argument why we would want to do polynomial features first and then scale it down。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_122.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_123.png)

Also on top of that， scaling it second will also ensure that each one of them are on the same scale at the end。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_125.png)

On the other hand， you may want to know the interaction between the scale data so that you'll be able to see just in regards to how much one varies from the mean。

 what will be the interaction versus the squared of those values。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_127.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_128.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_129.png)

But we're going to stick here with just the polynomial features first。

 which is generally regarded as best practice。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_131.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_132.png)

We're going to initiate our polynomial features object。

We're going to start off with a blank list of scores as we did before。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_134.png)

We're going to have our list of alphas and then for each one of those alphas。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_136.png)

We're going to do the same as we did in regards to initiating our Lasso objects。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_138.png)

Now I do want to say that we have this max iteration， which we didn't discuss before。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_140.png)

The idea being that when you're working with Lasso regression。

 it's actually going to work with radiant descent， which we haven't introduced yet。

 the idea is for it to get to the optimal value， it's essentially running in the back end what you can think of as a for loop as it gets closer and closer to the correct value。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_142.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_143.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_144.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_145.png)

And it's going to do that in small little steps。 and if you don't have enough iterations and the default here is not enough iterations。

 then it won't get to that optimal value。 So that's why we have to set the max iterations。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_147.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_148.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_149.png)

We're then creating our estimator object， which starts with the polynomial features， then scales it。

 and then pass that through to our Lasso regression。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_151.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_152.png)

We're then going to come up with predictions。By just running cross valve predicts。

 passing in our estimator our X and our Y， and then we're going to get our new score。

 and we're going to append each one of these scores。 Now， running this will take about 30 seconds。

 Also note that you will probably get a warning， giving the max iterations that we have here。

 that it hasn't converged， but we tested this on the back end to ensure that the numbers are fairly close to the actual optimal value。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_154.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_155.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_156.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_157.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_158.png)

So I'm going to take a break here and we'll come back as soon as this is done running。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_160.png)

Okay， now our functions have ran， and we can look at for each one of our alpha values。

 what our different scores were。 And we see starting off with very little。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_162.png)

With very little alphas， so very high complexities。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_164.png)

That we may not be generalizing well。 We see with a little bit more。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_166.png)

A little bit higher of an alpha， then we are generalizing better。

 and then as that alpha gets even higher， we may have reached our peak。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_168.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_169.png)

So to look at this graph。We would say that at this 0。01。

 we probably got our optimal value in regards to the hyperparmeter that will generalize well to new data coming in。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_171.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_172.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_173.png)

So with that， we can then use that hyper parametermeter to train our actual model。

 so we're going to set our best estimator equal to this pipeline where a polynomial features degree equals 2。

 then scaling and then using the alpha that we found was the best value with 0。01。

 and we can fit that we'd see what the score was here for the best estimator。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_175.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_176.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_177.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_178.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_179.png)

Which will be built in and it will be by default the R2 score。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_181.png)

And。When we are looking at that， we have to keep in mind also that we are training and scoring on the same data set。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_183.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_184.png)

So generally speaking， as usual， we probably want to have a holdout set。

 but this is just to show us how much of our variation we were actually able to cover given the model that we used。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_186.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_187.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_188.png)

And then when we look at the coefficients， because we use the Lasso regression and we added this。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_190.png)

Alpha term， we actually removed many of these features， as you see。

 a lot of them essentially zeroed out。

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_192.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_193.png)

So I'm going to take a stop here and then when we come back we will come to Ridge regression to see how we can run through the same process and then how we can ultimately string these all together into again。

 a succinct couple of lines of code Allright， I'll see there。



![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_195.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_196.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_197.png)

![](img/c8a7bdd9cbfec409cc42a6afdd8bab32_198.png)