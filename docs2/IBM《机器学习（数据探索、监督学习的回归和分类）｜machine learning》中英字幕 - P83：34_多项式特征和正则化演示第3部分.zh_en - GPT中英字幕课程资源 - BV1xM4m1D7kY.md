# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P83：34_多项式特征和正则化演示第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/2bc5a947b5483bb7a89139cb197a71fd_0.png)

Welcome to part 6 of our notebook Here we're going to introduce the different regularization techniques。

 namely Ridge， Lasso and Elastic net。

![](img/2bc5a947b5483bb7a89139cb197a71fd_2.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_3.png)

If you recall starting here with the Ridge， Ridge is going to use the L2 normalization to reduce the magnitude of the coefficients。



![](img/2bc5a947b5483bb7a89139cb197a71fd_5.png)

It does so by adding extra cost to the cost function， by squaring each one of those coefficients。



![](img/2bc5a947b5483bb7a89139cb197a71fd_7.png)

And this can be helpful in situations where there is high variance。

 if you recall if there's high variance， that's high complexity and reducing the size of the coefficients will reduce the complexity and reduce our variance。



![](img/2bc5a947b5483bb7a89139cb197a71fd_9.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_10.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_11.png)

The regular functions in SKLear each to contained versions that have cross validation built in。



![](img/2bc5a947b5483bb7a89139cb197a71fd_13.png)

So what does this mean if you recall when we talked about cross validation in the cross validation notebook。

 we had this option of grid search CV， which went through many different hyperparameters for a given model。



![](img/2bc5a947b5483bb7a89139cb197a71fd_15.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_16.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_17.png)

And then it also did train test split 4。 however many you want to craft validate on so we could have four splits。

5 splits and so on， and then find which one of the hyperparameter performed best on average across each one of these splits。

 So for grid search C， we have to specify what the model is。 Here。

 we are specifying it right off the bat by just calling Ridge C。

 So that's the same as grid search C with Ridge as the model that we're working with。



![](img/2bc5a947b5483bb7a89139cb197a71fd_19.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_20.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_21.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_22.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_23.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_24.png)

So from SK Learn that linearar model， we import Ridge CV。



![](img/2bc5a947b5483bb7a89139cb197a71fd_26.png)

We're then going to say what the alpha values are that we're going to loop through。



![](img/2bc5a947b5483bb7a89139cb197a71fd_28.png)

And then all we have to do is call this rich CV。We pass in for Red CV。

 the hyperparmeter that we want to loop over， which is the alphas。



![](img/2bc5a947b5483bb7a89139cb197a71fd_30.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_31.png)

We say that we want four train and test splits。And then。



![](img/2bc5a947b5483bb7a89139cb197a71fd_33.png)

Through doing that， we are initiating our objects， we can then fit that to our training set。

 to our X train and our Y train。

![](img/2bc5a947b5483bb7a89139cb197a71fd_35.png)

And then we can use that root mean squared error that we defined earlier in the notebook to see given that fitted model to x train and Y train。

 how well is it able to predict according to the actual values for our test set。



![](img/2bc5a947b5483bb7a89139cb197a71fd_37.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_38.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_39.png)

We'll then have the root mean squared error， we can also call from red CV the actual alpha value。



![](img/2bc5a947b5483bb7a89139cb197a71fd_41.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_42.png)

Wwhich is going to be one of these values which optimizes the model on each one of the holdout sets。

 so we run this and we see that 10 was the ideal alpha value and that's the root mean squared error is now 32。

205。

![](img/2bc5a947b5483bb7a89139cb197a71fd_44.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_45.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_46.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_47.png)

In part 7， much like R CV， there's also going to be Lassso CVv。



![](img/2bc5a947b5483bb7a89139cb197a71fd_49.png)

And that function is just going to use the L1 regularization function。

 as well as the cross validation that we have talked about。



![](img/2bc5a947b5483bb7a89139cb197a71fd_51.png)

If you call L1 regularization is just taking the absolute value of those coefficients。

 so again reducing those coefficients， but this time selectively shrinking some of those coefficients。

 effectively performing feature elimination。

![](img/2bc5a947b5483bb7a89139cb197a71fd_53.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_54.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_55.png)

Similarly， there's also going to be elastic net function with cross validation built in。

 and for that we just call Elastic nett CV， and this is can combine the L2 and the L1 regularization。



![](img/2bc5a947b5483bb7a89139cb197a71fd_57.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_58.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_59.png)

So what we're going to do here is fit a Laso model using cross validation and determine the opt value for alpha。

 as well as the root mean squared error for that optimal value of alpha。



![](img/2bc5a947b5483bb7a89139cb197a71fd_61.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_62.png)

We also want to note that alpha may be different from the rid model because it's going to depend on the coefficients。

 so first it's lambda times the coefficient squared versus lambda times the absolute value of those coefficients。

 you may want to iterate through different alpha values in order to come up with optimal model。



![](img/2bc5a947b5483bb7a89139cb197a71fd_64.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_65.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_66.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_67.png)

In regards to figuring out which alpha values to choose。

 I would just say use a certain number of values， see if the largest value is clearly the best every single time。

 then you need to increase it by a lot until you find a range of values where you can hone in so you keep increasing or decreasing according to whether or not you are stuck on the lowest or highest values in your list until you hone in onto a value that seems close to the optimum value。



![](img/2bc5a947b5483bb7a89139cb197a71fd_69.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_70.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_71.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_72.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_73.png)

So here we're going to use the values that we see here ranging from 0。005 up to 140。



![](img/2bc5a947b5483bb7a89139cb197a71fd_75.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_76.png)

We're setting alphas 2 to that array。

![](img/2bc5a947b5483bb7a89139cb197a71fd_78.png)

We're passing that into alphas。For La OCV， we also have to say that we want some max iterations。



![](img/2bc5a947b5483bb7a89139cb197a71fd_80.png)

The reason for that。 And if you recall， and I'm actually going to run it now before I continue to explain。

 because sometimes it takes a bit to run is that under the hood Rige will actually perform a lot quicker than Lasso。

 And that's just due to the optimization method that it uses。

 Lasso was forced to use gradient descent， which may take a bit longer。



![](img/2bc5a947b5483bb7a89139cb197a71fd_82.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_83.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_84.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_85.png)

And for that reason， we have to say that we have to say how many iterations it'll take before it stops in case it doesn't hit enough iterations to the point that it's able to converge。

 This doesn't make sense yet。 Don't worry about it。

 All that matters that it'll take longer for Laso and we'll learn more about gradient descent in later courses。



![](img/2bc5a947b5483bb7a89139cb197a71fd_87.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_88.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_89.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_90.png)

So here we see it shows the value of 120， and it has an error， a root mean squared error of 37，010。



![](img/2bc5a947b5483bb7a89139cb197a71fd_92.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_93.png)

We're also going to see how many of these features is able to eliminate and we see that out of the 251 coefficients。



![](img/2bc5a947b5483bb7a89139cb197a71fd_95.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_96.png)

This is the total coefficients。Only 102 were non zero。



![](img/2bc5a947b5483bb7a89139cb197a71fd_98.png)

So we reduce more than half of the coefficients。Now， finally。

 we're going to perform this using elastic net。 If you recall。

 elasticastic net is going to take our landda value and attribute a portion of it to。



![](img/2bc5a947b5483bb7a89139cb197a71fd_100.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_101.png)

To your ridge， to your coefficient squared and a portion of it to the absolute value of your coefficients in terms of that cost function。



![](img/2bc5a947b5483bb7a89139cb197a71fd_103.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_104.png)

So here we're going to take  nine values between 0。1 and 0。

9 for that alpha value that will wait where that lambda value will fall。



![](img/2bc5a947b5483bb7a89139cb197a71fd_106.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_107.png)

So 0。1 will be a lot of weight on the ridge， whereas 0。9 will be a lot of weight on the Lasso。



![](img/2bc5a947b5483bb7a89139cb197a71fd_109.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_110.png)

We call elastic net， we pass in Als 2。

![](img/2bc5a947b5483bb7a89139cb197a71fd_112.png)

We're then going to use the L1 ratios。

![](img/2bc5a947b5483bb7a89139cb197a71fd_114.png)

That we just defined up here。So the Als 2 is what we defined up here， right。

 It's going to be these alphas。

![](img/2bc5a947b5483bb7a89139cb197a71fd_116.png)

Then we're going to use the L and ratio， so we have to iterate over many more values。

 so I'm actually going to start running this now。

![](img/2bc5a947b5483bb7a89139cb197a71fd_118.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_119.png)

And then we're going to come up again， so this is going to fit the model。



![](img/2bc5a947b5483bb7a89139cb197a71fd_121.png)

And then we can fit that to the Y test and the predicted value for elastic net。

 So elastic net was similar to what we saw with Rige and with Lassso。

 just with an extra hyperparameter of the L1 ratio。



![](img/2bc5a947b5483bb7a89139cb197a71fd_123.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_124.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_125.png)

So now we're going to compare the root mean squared to error for each one of the models that we created。

 we had the linear regression， the ridge regression， the Lasso and the elastic net。



![](img/2bc5a947b5483bb7a89139cb197a71fd_127.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_128.png)

We're just going to create a series of the root mean squared error and the index is going to be these labels。

 linear， ridge， Lasso and elastic net in the correct order。

 so we're just creating a series out of this。

![](img/2bc5a947b5483bb7a89139cb197a71fd_130.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_131.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_132.png)

We're putting it into a data frame。And then by default。

 that data frame will have a column called zero， we're just going to rename that root mean squared error。

 and then we can see the root mean squared error for each one of our models。

 and we see that regularization drastically improved our root mean squared error。



![](img/2bc5a947b5483bb7a89139cb197a71fd_134.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_135.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_136.png)

By reducing it by significant amounts。

![](img/2bc5a947b5483bb7a89139cb197a71fd_138.png)

And in this case， elasticnet did slightly better than Ridge， and they both did better than Lasso。

 and that will just depend on checking the model and again， what you want to get out of the model。

 whether you want to reduce a lot of the coefficients and do feature selection。

 then you'd still want to do Lasso if you want it to run very quickly， you'd want to use Ridge。

 and if you want to find that optimal balance， you may want to use elastic net。



![](img/2bc5a947b5483bb7a89139cb197a71fd_140.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_141.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_142.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_143.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_144.png)

Finally， all we do here is similar to what we did above with linear regression。

 where we just plot the predicted values versus the actual values。

 We're just going to do it here for each one of our models。



![](img/2bc5a947b5483bb7a89139cb197a71fd_146.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_147.png)

So we have our labels are equal to Rige， Lasso and elastic net， and the different models。

 These are the actual models that we created that were already fit。

 So recall that we've already fit these models。 So they're able to predict the actual values later on。

 So if we look at elastic net C。 This is equal to this elastic net C。

 which has already been fitted to the X train and Y train and has already found the optimal alphas and L1 ratios。

😊。

![](img/2bc5a947b5483bb7a89139cb197a71fd_149.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_150.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_151.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_152.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_153.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_154.png)

So it's going to say four mod and La in zipping these models and labels together。

 so we're zipping them together and essentially accessing them as a list of tuples where each tuple is going to be a model as well as a label。

 so we will then do a dot plot using the act that we initiated up here。



![](img/2bc5a947b5483bb7a89139cb197a71fd_156.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_157.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_158.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_159.png)

And we will plot our Y test， which is the actual value versus the predicted value。



![](img/2bc5a947b5483bb7a89139cb197a71fd_161.png)

That model being first Ridge CV， then Las O CVV， then elastic nett CV。

 and we're able to label each one according to the label because we zip them together so that ridG CV is aligned with Ridge and Las O CVV with LaSso。



![](img/2bc5a947b5483bb7a89139cb197a71fd_163.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_164.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_165.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_166.png)

We're then going to call our legends and everything else that we've done in the past。



![](img/2bc5a947b5483bb7a89139cb197a71fd_168.png)

And we're just going to have。Our different predicted values versus the actual values plotted on the X Y graph。



![](img/2bc5a947b5483bb7a89139cb197a71fd_170.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_171.png)

Doesn't provide much extra information here。 I would say it would be much more worth it to look at the root mean squared error in order to see how well we were able to predict using each one of these models。



![](img/2bc5a947b5483bb7a89139cb197a71fd_173.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_174.png)

So that closes out our section in regards to our regularization demo。 After this。

 we're going to do one more lecture in regards to regularization to get a deeper insight into how it actually works。

 And then you will have some exercises to perform using regularization as well。 All right。

 I'll see you there。

![](img/2bc5a947b5483bb7a89139cb197a71fd_176.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_177.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_178.png)

![](img/2bc5a947b5483bb7a89139cb197a71fd_179.png)