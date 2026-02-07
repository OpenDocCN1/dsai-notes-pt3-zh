# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P71：22_交叉验证演示第4部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/668a3323f550c1acad133d71c2180c8d_0.png)

Welcome back to our notebook。 Here， we're going to briefly introduce Ridgege regression。 Now， again。

 we haven't gone through the math of Rige and Lasser regression。

 All we need to know is that these are two different forms of reducing the complexity of the original linear regression model。



![](img/668a3323f550c1acad133d71c2180c8d_2.png)

So that's all we'll know for now we'll get deeper into the math and lecture。



![](img/668a3323f550c1acad133d71c2180c8d_4.png)

Now， as before before passing through to our new model here being the Rige regression。

 we're going to create our polynomial features object。



![](img/668a3323f550c1acad133d71c2180c8d_6.png)

![](img/668a3323f550c1acad133d71c2180c8d_7.png)

We're going to have certain alphas that we're going to search through。



![](img/668a3323f550c1acad133d71c2180c8d_9.png)

And we're going to initiate just blank scores that we will append as we get the scores for each one of our ridge regressions。

 Given the different hyper parametersa that we're passing through。 So， again。

 our goal is to find the optimal hyper parametersa， so that it generalizes well to new data。

 So we don't want it to be too complex， but we don't want it to be a minimal amount of complexity。

 We want that just right region。 And order do that by doing cross validation And seeing for each one of these alphas。



![](img/668a3323f550c1acad133d71c2180c8d_11.png)

![](img/668a3323f550c1acad133d71c2180c8d_12.png)

![](img/668a3323f550c1acad133d71c2180c8d_13.png)

Either reducing complexity a ton or just a bit， where's the right balance in regards to complexity to minimize the error on our holdout sets？



![](img/668a3323f550c1acad133d71c2180c8d_15.png)

![](img/668a3323f550c1acad133d71c2180c8d_16.png)

So we're doing four alpha in our alphas。

![](img/668a3323f550c1acad133d71c2180c8d_18.png)

We run our Rige regression， and for each one， we pass in this hyperparameter of our alpha。



![](img/668a3323f550c1acad133d71c2180c8d_20.png)

We also are passing in this max iteration to ensure that it'll converge as we discussed。



![](img/668a3323f550c1acad133d71c2180c8d_22.png)

![](img/668a3323f550c1acad133d71c2180c8d_23.png)

And we will initiate our estimator object again using a pipeline of polynomial features。

 the standard scalar， and then ultimately our ridge regression， which we defined above。

 and then we will get our predictions using the cross valve predict on each one of our holdout sets and then we can see the R2 scores for each and a pen that on our scores。



![](img/668a3323f550c1acad133d71c2180c8d_25.png)

![](img/668a3323f550c1acad133d71c2180c8d_26.png)

And then we'll plot in order to see how the alphas versus the scores。

 how that's going to increase or decrease our R2 score as we increase or decrease our complexity using these alphas。



![](img/668a3323f550c1acad133d71c2180c8d_28.png)

![](img/668a3323f550c1acad133d71c2180c8d_29.png)

![](img/668a3323f550c1acad133d71c2180c8d_30.png)

So recall that a lower alpha means more complexity。



![](img/668a3323f550c1acad133d71c2180c8d_32.png)

So we see all the way here to the left with the much lower alpha。

 we are not getting as high of an R2 score， but as we increase the alpha and reduce the complexity。

 we have this optimal point around 0。75。 So that would be the optimal hyperparameter。

 Anything to the right of that is probably not complex enough。



![](img/668a3323f550c1acad133d71c2180c8d_34.png)

![](img/668a3323f550c1acad133d71c2180c8d_35.png)

![](img/668a3323f550c1acad133d71c2180c8d_36.png)

![](img/668a3323f550c1acad133d71c2180c8d_37.png)

So we have that just right point at around 。75。

![](img/668a3323f550c1acad133d71c2180c8d_39.png)

And our conclusion that we can get from this from both of these curves。

 having this upper trajectory and then this downward slope。



![](img/668a3323f550c1acad133d71c2180c8d_41.png)

![](img/668a3323f550c1acad133d71c2180c8d_42.png)

Is that using。This alpha value， in order to reduce complexity， again， no complexity。 I mean。

 no alpha value at all would be essentially the same as linear regression。

 So we can see that as we reduce complexity slightly。

 we are actually able to improve how well we are able to generalize our model。😊。



![](img/668a3323f550c1acad133d71c2180c8d_44.png)

![](img/668a3323f550c1acad133d71c2180c8d_45.png)

So reducing complexity， even on a simple model such as linear regression。

 is doing well in regards to optimizing how well we will perform on our holdout sets。



![](img/668a3323f550c1acad133d71c2180c8d_47.png)

Now I want to go over how we can look at some feature importance， so looking at interpretability。



![](img/668a3323f550c1acad133d71c2180c8d_49.png)

![](img/668a3323f550c1acad133d71c2180c8d_50.png)

So what is important whenever we want to look at interpretability for something like linear regression。

 we need to ensure that all of our features are on the same scale。

 If you think about one of them being values between 0 and 5 and the other one being values between  10000 and 100000 for trying to predict how much a unit change of 0 to 5 will affect median value。

 a one unit change will probably have a larger effect。

 whereas a one unit change in values between 10000 and 100000 will have a very little effect on the overall median value of our households。



![](img/668a3323f550c1acad133d71c2180c8d_52.png)

![](img/668a3323f550c1acad133d71c2180c8d_53.png)

![](img/668a3323f550c1acad133d71c2180c8d_54.png)

![](img/668a3323f550c1acad133d71c2180c8d_55.png)

![](img/668a3323f550c1acad133d71c2180c8d_56.png)

![](img/668a3323f550c1acad133d71c2180c8d_57.png)

So what we want to do is bring those all down to the same scale so that our coefficients are actually measuring for one unit change in standard deviation so as it varies。

In accordance to the variation built into that feature。

 how much will that affect our median household value， so now they're all on the same scale。

 the larger that coefficient is， the more important that feature can be seen in regards to predicting the median household value。



![](img/668a3323f550c1acad133d71c2180c8d_59.png)

![](img/668a3323f550c1acad133d71c2180c8d_60.png)

![](img/668a3323f550c1acad133d71c2180c8d_61.png)

![](img/668a3323f550c1acad133d71c2180c8d_62.png)

So the way that we're going to do that is again， first standardize the data。

We're then going to fit and predict on the entire data set。

 so we're going to get our training set is going because we don't care as much about prediction here。

 but rather interpretability， we want to bring in all of our training data。



![](img/668a3323f550c1acad133d71c2180c8d_64.png)

![](img/668a3323f550c1acad133d71c2180c8d_65.png)

And then we're going to see which one of our values have the largest coefficients。



![](img/668a3323f550c1acad133d71c2180c8d_67.png)

Now， in order to do this， we're going to have to run this code that we see here。

 and I'll explain that clearly as we go through the code in just a couple of cells。



![](img/668a3323f550c1acad133d71c2180c8d_69.png)

![](img/668a3323f550c1acad133d71c2180c8d_70.png)

So we have our best hyperpammeter with less with。

![](img/668a3323f550c1acad133d71c2180c8d_72.png)

Laso with alpha equal to 0。01， we create our pipeline where we create our polynomial features。

 so we're going to have a ton of new features as we square each one of our features as well as creating all of the interaction terms between each one of our features。



![](img/668a3323f550c1acad133d71c2180c8d_74.png)

![](img/668a3323f550c1acad133d71c2180c8d_75.png)

![](img/668a3323f550c1acad133d71c2180c8d_76.png)

And then we're going to scale it， so they're all in the same scale。

And then we're going to fit the X and Y。 Again， we don't care as much about prediction as much as we care about we've already gotten。

 right， the 0。01 is going to be our optimal value in regards to how well we will perform on a holdout set。

 Now we want to see what the actual interpretability of that output will be。



![](img/668a3323f550c1acad133d71c2180c8d_78.png)

So we're fitting on the entire training set to get the coefficients fit across as much data as possible。

 We'll look at the score here that won't be as important。



![](img/668a3323f550c1acad133d71c2180c8d_80.png)

![](img/668a3323f550c1acad133d71c2180c8d_81.png)

And then we're going to look at each one of the feature importance using the code that we see above。



![](img/668a3323f550c1acad133d71c2180c8d_83.png)

So step by step。

![](img/668a3323f550c1acad133d71c2180c8d_85.png)

When we run。

![](img/668a3323f550c1acad133d71c2180c8d_87.png)

Best estimator。Here， let's pull this all out。

![](img/668a3323f550c1acad133d71c2180c8d_89.png)

So I promised you that later on we would take from the pipeline the actual names。



![](img/668a3323f550c1acad133d71c2180c8d_91.png)

And we will actually make use of each of these names that we pass through。

 rather than just passing through perhaps polynomial features or our standard scalealar。

 or whatever our object is that we are passing through the pipeline。

 If we want to access a portion of the pipeline， then we have to take our best estimator。

 which is equal to this pipeline that we have fit before。



![](img/668a3323f550c1acad133d71c2180c8d_93.png)

![](img/668a3323f550c1acad133d71c2180c8d_94.png)

![](img/668a3323f550c1acad133d71c2180c8d_95.png)

![](img/668a3323f550c1acad133d71c2180c8d_96.png)

And call out dot named steps。And that dot named steps allow us to access a dictionary where we can look at different attributes of each of these subsets of our pipeline。

 So each one of these subsets could be either the polynomial features or the standard scalar。

 or if we want the coefficients， we can pull it from the Lasso here。



![](img/668a3323f550c1acad133d71c2180c8d_98.png)

![](img/668a3323f550c1acad133d71c2180c8d_99.png)

![](img/668a3323f550c1acad133d71c2180c8d_100.png)

![](img/668a3323f550c1acad133d71c2180c8d_101.png)

So we do best estimator dot named steps， we're pulling out the polynomial features here。



![](img/668a3323f550c1acad133d71c2180c8d_103.png)

And we're calling this function called get feature names。



![](img/668a3323f550c1acad133d71c2180c8d_105.png)

And that's going to allow us to get the。

![](img/668a3323f550c1acad133d71c2180c8d_107.png)

X， not X 1， X 2， X 3， and those values squared。 so that we'll be able to look back and see which one of our values actually ended up having the highest feature importance。



![](img/668a3323f550c1acad133d71c2180c8d_109.png)

So you see here， I'm pulling out all the names where we have crime。

 and then we have crime squared and then crime time zone and so on and so forth。



![](img/668a3323f550c1acad133d71c2180c8d_111.png)

![](img/668a3323f550c1acad133d71c2180c8d_112.png)

So this allows us to see each one of our new features that we created using the polynomial features。



![](img/668a3323f550c1acad133d71c2180c8d_114.png)

![](img/668a3323f550c1acad133d71c2180c8d_115.png)

Then we also want to pull out the coefficients that we learned with our model。



![](img/668a3323f550c1acad133d71c2180c8d_117.png)

So I'm going to copy this again， we use that dot name steps。

And we say that we want to pull from the Lasso regression。

 The Lasso regression is going to be the portion of our pipeline that contains the attribute of coefficients。



![](img/668a3323f550c1acad133d71c2180c8d_119.png)

![](img/668a3323f550c1acad133d71c2180c8d_120.png)

And we see a coefficient for each one of those values that we just saw laid out with our polynomial features。



![](img/668a3323f550c1acad133d71c2180c8d_122.png)

We're going to zip those two together so that for each one of those features。

 it is perfectly aligned with each one of these coefficients。So that's going to be this zip function。

 and then we're going to pass it into a data frame and call that data frame DF importances。

So what does our DF importances look like now？

![](img/668a3323f550c1acad133d71c2180c8d_124.png)

It's now the first column is going to be each one of our feature names。

 and our second column is going to be the magnitude of that coefficient。



![](img/668a3323f550c1acad133d71c2180c8d_126.png)

![](img/668a3323f550c1acad133d71c2180c8d_127.png)

We're then going to sort our values so we can see the highest negative and the highest positive values in regards to which variation affected our predicted outcome the most。



![](img/668a3323f550c1acad133d71c2180c8d_129.png)

![](img/668a3323f550c1acad133d71c2180c8d_130.png)

And then we see the interaction between number of rooms and the tax rate has actually very negative effects。

Whereas we'd actually have to， we can actually pull out the。

Boston description that we defined earlier。To see each one of these different column names。

 if we are more curious。

![](img/668a3323f550c1acad133d71c2180c8d_132.png)

So， we had that。Rad times PT ratio， which is going to be the index of accessibility to raial highways to PT ratio。

 the people teacher ratio by town that probably will not。

 it's a little bit confusing to think that that would have such a large effect。

 we may want to test removing this as we have so many more features at this point we're now working with 104 features or we can say maybe there is that effect and dive deeper in。



![](img/668a3323f550c1acad133d71c2180c8d_134.png)

![](img/668a3323f550c1acad133d71c2180c8d_135.png)

![](img/668a3323f550c1acad133d71c2180c8d_136.png)

![](img/668a3323f550c1acad133d71c2180c8d_137.png)

![](img/668a3323f550c1acad133d71c2180c8d_138.png)

And then the other thing that we can look at here is that room squared。

 so as the number of rooms increases， that's going to have more and more value in regards to how much we would predict the outcome variable that we're looking at。



![](img/668a3323f550c1acad133d71c2180c8d_140.png)

![](img/668a3323f550c1acad133d71c2180c8d_141.png)

![](img/668a3323f550c1acad133d71c2180c8d_142.png)

Al right， that closes out this section in regards to looking at feature importance and getting a quick peek at Ri regression in the next section we will go over grid search CV。

 which will allow us to do this for loop through all of these difference hyperparas in a much more succinct fashion。



![](img/668a3323f550c1acad133d71c2180c8d_144.png)

![](img/668a3323f550c1acad133d71c2180c8d_145.png)

![](img/668a3323f550c1acad133d71c2180c8d_146.png)

![](img/668a3323f550c1acad133d71c2180c8d_147.png)

![](img/668a3323f550c1acad133d71c2180c8d_148.png)