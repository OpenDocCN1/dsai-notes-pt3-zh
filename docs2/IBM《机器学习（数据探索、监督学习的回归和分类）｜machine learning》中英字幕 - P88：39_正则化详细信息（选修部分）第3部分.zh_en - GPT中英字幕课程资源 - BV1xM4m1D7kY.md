# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P88：39_正则化详细信息（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/176e1a59db003165d346401f94420beb_0.png)

Welcome back to our solutions in our labs in this section we're going to look at another alpha value for LaSso。



![](img/176e1a59db003165d346401f94420beb_2.png)

We're going to see how well that's going to perform on a holdout set。



![](img/176e1a59db003165d346401f94420beb_4.png)

And then compare that to linear regression。

![](img/176e1a59db003165d346401f94420beb_6.png)

Check the R2 score for each and see which one has a higher R 2 score。

 and then we will also look at in part 3 which one is going to have a smaller magnitude of coefficients。

 as well as which ones going to have less overall coefficients。



![](img/176e1a59db003165d346401f94420beb_8.png)

![](img/176e1a59db003165d346401f94420beb_9.png)

![](img/176e1a59db003165d346401f94420beb_10.png)

And hopefully already， you have in mind that Lasso should be reducing the magnitude of these coefficients。

 as well as bringing down the number of nonzero coefficients that we have in our resulting model。



![](img/176e1a59db003165d346401f94420beb_12.png)

![](img/176e1a59db003165d346401f94420beb_13.png)

So first， we're going to initiate our object。

![](img/176e1a59db003165d346401f94420beb_15.png)

Lasts 001 is just going to be equal to a lasso regression， well with an alpha equal to 0。001。



![](img/176e1a59db003165d346401f94420beb_17.png)

We are increasing the max iterations from its default When we have a smaller alpha value。

 it can happen that we are not able to get to the optimal solution。

 We briefly touched on the fact that Lasso takes longer because it uses something called gradient descent to step through until it gets to the optimal solution。



![](img/176e1a59db003165d346401f94420beb_19.png)

![](img/176e1a59db003165d346401f94420beb_20.png)

![](img/176e1a59db003165d346401f94420beb_21.png)

![](img/176e1a59db003165d346401f94420beb_22.png)

So we want to ensure that we have enough steps to get to that optimal solution。

 otherwise it could end up stopping short of that optimal solution and not converging and when that happens。

 you will probably get a warning that you are not able to converge。



![](img/176e1a59db003165d346401f94420beb_24.png)

![](img/176e1a59db003165d346401f94420beb_25.png)

![](img/176e1a59db003165d346401f94420beb_26.png)

We're going to set X train S to our fit transformed version of X train using S。

 right we're fit transforming it to the standard scalar。



![](img/176e1a59db003165d346401f94420beb_28.png)

![](img/176e1a59db003165d346401f94420beb_29.png)

We're then going to take that X train S。

![](img/176e1a59db003165d346401f94420beb_31.png)

As well as our Y train， and we're going to fit our new Lasso regression to our training set。



![](img/176e1a59db003165d346401f94420beb_33.png)

We're then going to transform our X test。

![](img/176e1a59db003165d346401f94420beb_35.png)

We're going to use Sdo transform， not fit transform， but just transform。



![](img/176e1a59db003165d346401f94420beb_37.png)

![](img/176e1a59db003165d346401f94420beb_38.png)

And then we are going to use that as input to our prediction in order to get the predictions on our test set。



![](img/176e1a59db003165d346401f94420beb_40.png)

We can then get the Arc2 score for our predictions versus our test set。

 and we will print that out and you'll see that once we run all of the code here。



![](img/176e1a59db003165d346401f94420beb_42.png)

![](img/176e1a59db003165d346401f94420beb_43.png)

Part two was to do the same thing for linear regressiong。

 so we initiate our linear regression objects， we fit it to our training set using our standardized version of X train。



![](img/176e1a59db003165d346401f94420beb_45.png)

![](img/176e1a59db003165d346401f94420beb_46.png)

We then predict using the standardized versions of the X test that we defined up above over here。



![](img/176e1a59db003165d346401f94420beb_48.png)

![](img/176e1a59db003165d346401f94420beb_49.png)

And then we're going to print out the R2 score。For our linear regression， which is just going to be。



![](img/176e1a59db003165d346401f94420beb_51.png)

The YP out hour and our original outcome variable。

![](img/176e1a59db003165d346401f94420beb_53.png)

We're then also going to use the same code that we used above to see the magnitude of our coefficients by taking the absolute value and the sum of each one of those absolute values。



![](img/176e1a59db003165d346401f94420beb_55.png)

![](img/176e1a59db003165d346401f94420beb_56.png)

And then we're going to see how many of our values are non zero。

 so first we're going to do it for Laso， then we're going to do it for linear regression。



![](img/176e1a59db003165d346401f94420beb_58.png)

![](img/176e1a59db003165d346401f94420beb_59.png)

So let's look at these results。It's iterating through so it takes just a second。

 and then we see the R2 score for Lasso was 0。868。

![](img/176e1a59db003165d346401f94420beb_61.png)

![](img/176e1a59db003165d346401f94420beb_62.png)

And the R2 score for linear Russian was 0。855。

![](img/176e1a59db003165d346401f94420beb_64.png)

So on the holdout set。Lasso did a better job of explaining the additional variation。



![](img/176e1a59db003165d346401f94420beb_66.png)

We then see the magnitude of the lessso coefficients is 436。



![](img/176e1a59db003165d346401f94420beb_68.png)

Compared to the magnitude of the coefficients for linear regression。

 which was nearly triple that at 1185。

![](img/176e1a59db003165d346401f94420beb_70.png)

![](img/176e1a59db003165d346401f94420beb_71.png)

And then we see that there's 89 non zero coefficients。



![](img/176e1a59db003165d346401f94420beb_73.png)

And 104 coefficients for the linear regression。So we see how we are able to reduce the complexity of the model。

 reduce the number of coefficients， reduce the magnitude of those coefficients。



![](img/176e1a59db003165d346401f94420beb_75.png)

![](img/176e1a59db003165d346401f94420beb_76.png)

And come up with a solution that's doing a better job of explaining variation on our holdout set。



![](img/176e1a59db003165d346401f94420beb_78.png)

So there's that idea of。

![](img/176e1a59db003165d346401f94420beb_80.png)

Bringing down the variance of our model in order for it to generalize better on new data。



![](img/176e1a59db003165d346401f94420beb_82.png)

Now let's quickly introduce the same concept using Rige regression we have gone through this before we saw that Lasso and Ridge have a similar formulation。

 so we're just going to import the Ridge regression object。



![](img/176e1a59db003165d346401f94420beb_84.png)

![](img/176e1a59db003165d346401f94420beb_85.png)

![](img/176e1a59db003165d346401f94420beb_86.png)

We're then going to fit a ridge to 0。001 using that same alpha。

 Now that alpha doesn't necessarily translate。 So don't think that just because they have the same alpha。

 they will have the same regular。 Again， now we are recognizing on the coefficient squared。

 so it could have a different effect。 and we may want to loop through different values of alpha。

 But here we're just going to look at 0。001。

![](img/176e1a59db003165d346401f94420beb_88.png)

![](img/176e1a59db003165d346401f94420beb_89.png)

![](img/176e1a59db003165d346401f94420beb_90.png)

![](img/176e1a59db003165d346401f94420beb_91.png)

We're going to do the same fit transform using our standard Scalar。



![](img/176e1a59db003165d346401f94420beb_93.png)

We're then going to fit our ridge model， which is just R to our X train S and our Y train。

 we have our X test S using the S dot transform。

![](img/176e1a59db003165d346401f94420beb_95.png)

![](img/176e1a59db003165d346401f94420beb_96.png)

And then we can come up with our predictions for using R on our test set。



![](img/176e1a59db003165d346401f94420beb_98.png)

![](img/176e1a59db003165d346401f94420beb_99.png)

Now you want to see the coefficients for R。And we see that we have all these coefficients。

 We want to remind that we're working with the same alpha as above by just calling Lasso we see the alpha value。

 and then we can look at the Lasso coefficients， and we see that we have a ton more zeros。



![](img/176e1a59db003165d346401f94420beb_101.png)

![](img/176e1a59db003165d346401f94420beb_102.png)

![](img/176e1a59db003165d346401f94420beb_103.png)

And again， those zeros are due to the fact that we are using Lasso。

 Lasso by default will almost always zero more values than Ri will。



![](img/176e1a59db003165d346401f94420beb_105.png)

![](img/176e1a59db003165d346401f94420beb_106.png)

We're then going to look at both the magnitude of our coefficients as well as the number that are zeroed out。



![](img/176e1a59db003165d346401f94420beb_108.png)

And as expected for Ridge， we had more values， in fact we didn't zero any values compared to the number of values that we zero about or we have left at our non zeroro for Laso。



![](img/176e1a59db003165d346401f94420beb_110.png)

![](img/176e1a59db003165d346401f94420beb_111.png)

![](img/176e1a59db003165d346401f94420beb_112.png)

And in this particular。Version of Ridge and Lasso， we see that the magnitude was higher。

 We ran first Ridge first， the magnitude was higher for Ridge， and we had a simpler model for Lasso。



![](img/176e1a59db003165d346401f94420beb_114.png)

![](img/176e1a59db003165d346401f94420beb_115.png)

![](img/176e1a59db003165d346401f94420beb_116.png)

So。Here， Laso is providing stronger overall regularization than ridge for this particular alpha again。

 this is not always necessarily true， it will depend on your features。

 but we are able to test it using the methods that we see above。



![](img/176e1a59db003165d346401f94420beb_118.png)

![](img/176e1a59db003165d346401f94420beb_119.png)

![](img/176e1a59db003165d346401f94420beb_120.png)

But then just going to look at the R2 score for each， the first one is the R2 score for ridge。

 the second one is the R2 score for Lasso， again Lasso is doing a better job of generalizing。

 but this will obviously depend on the alphas chosen and you can iterate through different alphas to see if certain values work better。



![](img/176e1a59db003165d346401f94420beb_122.png)

![](img/176e1a59db003165d346401f94420beb_123.png)

![](img/176e1a59db003165d346401f94420beb_124.png)

![](img/176e1a59db003165d346401f94420beb_125.png)

Now， does it matter when you scale， so we've been honing in on the fact that first。

 and we've discussed why， but first you want to do your transformation on your training set。



![](img/176e1a59db003165d346401f94420beb_127.png)

![](img/176e1a59db003165d346401f94420beb_128.png)

![](img/176e1a59db003165d346401f94420beb_129.png)

You' fit and transform on your training set， then just transform on your test set。



![](img/176e1a59db003165d346401f94420beb_131.png)

Here we're to see if we did plain linear regression。

 So here we're actually taking a standard scaled version first。



![](img/176e1a59db003165d346401f94420beb_133.png)

Then running linear regression， and we get the R2 score is 0。58。



![](img/176e1a59db003165d346401f94420beb_135.png)

And then in this version， we're doing it， as we said。

 where we should do our scaling our fit transform first， then our transform so if we look here。



![](img/176e1a59db003165d346401f94420beb_137.png)

![](img/176e1a59db003165d346401f94420beb_138.png)

This is already having the fit transform done for us。

 and that's going to be the same values for both the train and test set。



![](img/176e1a59db003165d346401f94420beb_140.png)

![](img/176e1a59db003165d346401f94420beb_141.png)

Here we're only using the train set in order to come up with our mean and standard deviation rather than the full data set。



![](img/176e1a59db003165d346401f94420beb_143.png)

And then we transform our test set using those values。

 but we see here that we end up with the same R2 score。



![](img/176e1a59db003165d346401f94420beb_145.png)

![](img/176e1a59db003165d346401f94420beb_146.png)

The conclusion that we want to take away here， that we want to hone in on is that yes。

 it will be the same when you're working with plain vanilla linear aggression。



![](img/176e1a59db003165d346401f94420beb_148.png)

![](img/176e1a59db003165d346401f94420beb_149.png)

But as soon as you work with other models where the。

Coics will matter in our cost score and we introduce things such as regularization。

 we may end up with different R2 scores or different predictions given when we actually fit and transform our data。



![](img/176e1a59db003165d346401f94420beb_151.png)

![](img/176e1a59db003165d346401f94420beb_152.png)

![](img/176e1a59db003165d346401f94420beb_153.png)

So to make this clear， imagine I just changed this to a lasso regression。



![](img/176e1a59db003165d346401f94420beb_155.png)

And I changed this till the lastso regression。

![](img/176e1a59db003165d346401f94420beb_157.png)

We'll see。That using the entire data set to come up with our standard deviation。



![](img/176e1a59db003165d346401f94420beb_159.png)

And our mean will come up with a different prediction than using just our training set to come up with those values。

 They'll be very similar because the mean and standard deviation should be fairly similar。

 but they will be different。

![](img/176e1a59db003165d346401f94420beb_161.png)

![](img/176e1a59db003165d346401f94420beb_162.png)

![](img/176e1a59db003165d346401f94420beb_163.png)

So again， when you're working with most models， you want to run D。



![](img/176e1a59db003165d346401f94420beb_165.png)

Fit transform only on your training set and then the transform。



![](img/176e1a59db003165d346401f94420beb_167.png)

On just your test set， not the fit transform。That concludes this lab。 Thank you for joining me。

 And that also concludes course 2， and I look forward to seeing you and applying all of this for all the different models in course 3。

 Thank you。😊。

![](img/176e1a59db003165d346401f94420beb_169.png)

![](img/176e1a59db003165d346401f94420beb_170.png)

![](img/176e1a59db003165d346401f94420beb_171.png)