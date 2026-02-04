# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P87：38_正则化详细信息（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/c5e77473cf60ceaa1a7e178c880358cb_0.png)

Now， we're going to start discussing Lasso and think back to our lecture。 And we have this question。

 what is different about Lasso versus regular linear regression When he saw this question。

 hopefully you realize quickly it all about the cost function where we are adding on to that cost function。

 the absolute value of the coefficients to limit the size of each one of those coefficients。



![](img/c5e77473cf60ceaa1a7e178c880358cb_2.png)

And then we had the question， is standardization more or less important with Laso versus linear Russian？

With linear regression， we won't have any penalization， according to the size of our coefficients。

 whereasas Lasso will have extra penalty if those coefficients are larger versus them being smaller。

 So the scale of our features are going to affect the scale of our coefficients。

And if we don't scale first。And put them all on the same scale。

 Then we end up having coefficients that are prone to the scale of each one of these features and therefore can be larger or smaller and therefore get penalized more or less。

According to the scale of each one of the features。

 So it's much more important to bring all those features on the same scale。



![](img/c5e77473cf60ceaa1a7e178c880358cb_4.png)

So we're going to import our Laso model， we're also going to bring in polynomial features。



![](img/c5e77473cf60ceaa1a7e178c880358cb_6.png)

We're going to initiate our polynomial features， objects。 Our degree is equal to 2。

 We've seen this before。 We say that we don't want to include the bias。

 That's just saying that we don't want to include the intercept term。 Now just。



![](img/c5e77473cf60ceaa1a7e178c880358cb_8.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_9.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_10.png)

Output a bunch of ones for that column and we'd learn a coefficient for all those ones。

 but we don't need that our Laso will take care of that automatically。



![](img/c5e77473cf60ceaa1a7e178c880358cb_12.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_13.png)

And then we call fit transform on our original X to come up with our polynomial transformed version of X。



![](img/c5e77473cf60ceaa1a7e178c880358cb_15.png)

And then we do our standardization by calling out that standard scalar that we defined earlier as S and calling fit transform on our polynomial features version of X。

And we state that as x polynomial x underscore Pf underscore S。



![](img/c5e77473cf60ceaa1a7e178c880358cb_17.png)

We're then going to use the default version of Lasso。

 so we're not going to pass in any hyperparameters。

And we set la equal to this default version of LaSso。

We' called fit on our polynomial transform plus the standard scale version of our x values with our Y。

 and then we can see the coefficients that it comes up with。



![](img/c5e77473cf60ceaa1a7e178c880358cb_19.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_20.png)

By defaults。The alpha value。Is going to be 1。0 here？



![](img/c5e77473cf60ceaa1a7e178c880358cb_22.png)

In this case， this is a fairly high alpha value and it ends up zeroing out a ton of our coefficients。

So high alpha value again is going to mean more regularization， which means a simpler model。



![](img/c5e77473cf60ceaa1a7e178c880358cb_24.png)

So now we want to compare the sum of the magnitude of our coefficients。

 which is just going to be the sum of the absolute values to see adding up all of the coefficients。

How large is that sum going to be， the larger that is， the more complex our model is？

And then we're also going to look at the number of coefficients that are equal to zero to see how many of our terms are zeroed out。

And we're going to do this for Lasso with alpha equal to 0。1。

 which is a smaller alpha versus an alpha of 1。 of1， which is a larger alpha。

 more regularization and should therefore be a less complex model。



![](img/c5e77473cf60ceaa1a7e178c880358cb_26.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_27.png)

Now， before doing that exercise， hopefully you thought to yourself。



![](img/c5e77473cf60ceaa1a7e178c880358cb_29.png)

Which one of these would have a greater magnitude and which one of these would we expect to have more zeros？



![](img/c5e77473cf60ceaa1a7e178c880358cb_31.png)

So hopefully you thought if the alpha is larger， then we are regularizing more。

 so we'd have smaller magnitude for a higher alpha as well as more zeros for a higher alpha。

 it'll zero out more values if we have in higher alpha and let's see this in practice。



![](img/c5e77473cf60ceaa1a7e178c880358cb_33.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_34.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_35.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_36.png)

So now we're setting last zero1。It's just going to be equal to alpha where the alpha is equal to 0。

1 rather than the default of one。 And then we're going to fit our。



![](img/c5e77473cf60ceaa1a7e178c880358cb_38.png)

Polynomial transforms standard scalar version of our X， as well as our y。



![](img/c5e77473cf60ceaa1a7e178c880358cb_40.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_41.png)

And then we're going to get the absolute value of each one of the coefficients。And take the sum。

 And that will give us the magnitude。

![](img/c5e77473cf60ceaa1a7e178c880358cb_43.png)

Then we're also going to say for each one of our coefficients， how many of them are not equal to0。

 theyll pass over true or false values that are the same size of the array。

 and then we sum that together each true valuableably equal to one。 and when we sum that together。

 then we end up having the number of coefficients that are nonzero。



![](img/c5e77473cf60ceaa1a7e178c880358cb_45.png)

So you run this and we see that we have a 23 coefficients that are non zero and our magnitude is 26。

13。

![](img/c5e77473cf60ceaa1a7e178c880358cb_47.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_48.png)

Just to pull this out to show you what this looks like。



![](img/c5e77473cf60ceaa1a7e178c880358cb_50.png)

We ended up with all true or falses。 and again， those chooses would be equal to one。

 So when we call not sum， we get the number 23， and that's just the number of values that are greater than 0 or not equal to 0。



![](img/c5e77473cf60ceaa1a7e178c880358cb_52.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_53.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_54.png)

Here we set alpha equal to one。 So now we have a higher alpha， more regularization。

 We run the same steps， and as expected， we have a lower magnitude of 8。

4 and less values that are not equal to 0， of only 7 values that are not equal to 0。



![](img/c5e77473cf60ceaa1a7e178c880358cb_56.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_57.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_58.png)

So more regularization， again meant。

![](img/c5e77473cf60ceaa1a7e178c880358cb_60.png)

Lower magnitude， as well as more zeros， less non zero values。In our coefficients。



![](img/c5e77473cf60ceaa1a7e178c880358cb_62.png)

Now let's calculate the R2 score of each one of our models。So we're in a run。

 we're going to import our2 score， and we are going to run our2 score on y as well as our predicted value for XPFSS。

 This last is the last that was defined up here， which had the default of 1。0。

 which was a fairly high regularization。

![](img/c5e77473cf60ceaa1a7e178c880358cb_64.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_65.png)

And we see that the R2 score is about 72。Now。Think to yourself， will regularization。

 ever increase model performance if we're evaluating on that same data that we trained on。

So the idea again， of regularization is to reduce the complexity。

 ensure that we don't overfit to our training set。So if we are ensuring that we're not overfitting to our training set。

 then we're reducing the how well we can fit to the actual training set。 Therefore， we will always。

 if we're testing and saying how well we able to predict on the same set that we trained。

 we will always get a lower value for our if we increase regularization。

The key with regularization is to see how well it will perform on holdout sets。A new sets coming in。

 which is generally going to be the problem that you're trying to solve。

 You'll never be trying to predict on the same values that you already have available to you。



![](img/c5e77473cf60ceaa1a7e178c880358cb_67.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_68.png)

So with that in mind， we want to introduce Tra test split。



![](img/c5e77473cf60ceaa1a7e178c880358cb_70.png)

We're going to call our train test split function。 We're going to pass in X PF。



![](img/c5e77473cf60ceaa1a7e178c880358cb_72.png)

And why？We're not calling in the scaled version because if you recall we can only scale on our training set。

 we can only fit our scaling to our training set， and then we can use that fit in order to transform our test set。



![](img/c5e77473cf60ceaa1a7e178c880358cb_74.png)

So we're using the polynomial transform， but not the standard scalar transform to get our X train。

 x test， Y train and Y test。

![](img/c5e77473cf60ceaa1a7e178c880358cb_76.png)

We're holding out 30% for testing。We're then going to run our fit transform and fit。

 so we only fit transform again on our training set。



![](img/c5e77473cf60ceaa1a7e178c880358cb_78.png)

We can then fit。Our last model that we defined on our new X train， standardized and our Y train。



![](img/c5e77473cf60ceaa1a7e178c880358cb_80.png)

We're then going to just transform。Our X test using the standard scalar。

 which has been fit to our X train。

![](img/c5e77473cf60ceaa1a7e178c880358cb_82.png)

And then we can come up with our predictions on our X test S on our standardized version of X test。



![](img/c5e77473cf60ceaa1a7e178c880358cb_84.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_85.png)

And then we can see the R2 score for our holdout set。And we run this。

 and we see a fairly low R2 score of 0。33。

![](img/c5e77473cf60ceaa1a7e178c880358cb_87.png)

Now， let's see the same steps for an alpha of 0。1。

![](img/c5e77473cf60ceaa1a7e178c880358cb_89.png)

We run this and we see an increased R2 score。

![](img/c5e77473cf60ceaa1a7e178c880358cb_91.png)

Which means that if we think between these two models， this one had high regularization。

 this one had lower regularization。

![](img/c5e77473cf60ceaa1a7e178c880358cb_93.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_94.png)

What would we think is the problem？With the above data set。



![](img/c5e77473cf60ceaa1a7e178c880358cb_96.png)

The problem would be that we included too much regularization。

 We have too much bias and we are not able to find the actual underlying relationship between X and Y。

So we have dumbed down our model too much。 We have reduced the complexity too much。 And again。

 the goal is to find this balance。

![](img/c5e77473cf60ceaa1a7e178c880358cb_98.png)

So let's take a break here， and in the next lesson we will try different values of alpha to try to hone in on what the optimal value for alpha will be in order to get a higher our two score or a higher whatever our metric is in regards to our whole outset。



![](img/c5e77473cf60ceaa1a7e178c880358cb_100.png)

![](img/c5e77473cf60ceaa1a7e178c880358cb_101.png)

All right， I'll see you there。

![](img/c5e77473cf60ceaa1a7e178c880358cb_103.png)