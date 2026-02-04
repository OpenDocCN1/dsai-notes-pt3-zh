# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P58：9_线性回归演示（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome back。We're going to continue with the notebook here going into actually implementing linear regression。

 we're going to bring in a bunch of different functions from SKLn， so from SKLn。

 linearar model we brought in linear regression， which will match up to what we saw in lecture in regards to actually implementing linear regression。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_1.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_2.png)

We have SK Learn dot metrics we're going to import the R2 score so that we can come up with a score for how well we are explaining our variants using linear regression。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_4.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_5.png)

From Scalar。 model selection， we're going to bring in a train test split that's going to allow us to take our data and split it out into what we will train our linear Russianon in order to find our parameters。

And a test set to see how well given new data we were able to fit to our training data。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_7.png)

And then finally， we're going to bring in some preprocessing， which we learned in our first course。

 such as the standard Scalar in order to get them all on the same scale。

 as well as polynomial features which allow you to add degree2 and some interaction terms as well。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_9.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_10.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_11.png)

So the first thing that we're going to do is initiate this linear regression object。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_13.png)

So we can pass in hyperparameter。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_15.png)

In two here， and you see I'm having those all pull up， such as whether I want to fit the intercept。

 whether we're going to normalize by defaults， so on and so forth。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_17.png)

We're just going to use the default values and set that linear Russian object equal to LR。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_19.png)

This object is going to be an from SK learn it's going to be a predictor。

 predictors just means that it's going to have a predict method once you fit that value。

 once you fit that object here LR to an X， your features and a Y， your outcome variable。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_21.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_22.png)

So， I initiate LR。We're then going to reinitiate our Boston data frame。

 so we're just calling that again to clean up any changes that we made with the box Cos， etc。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_24.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_25.png)

We're going to create what's going to be our X and y variable。

 so our input and output in regards to our model， we're going to set the y column equal to here we're just calling it to the string。

 which is our medium value。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_27.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_28.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_29.png)

And then we say x is equal to our data frame with that value dropped。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_31.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_32.png)

Access equals 1 is specifying that we want a column dropped。

 and then y is just going to be equal to that data frame， but specifically just that column。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_34.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_35.png)

So we can look at y， that's just going to be that column if we look at x。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_37.png)

It's going to be the remaining columns of your data frame。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_39.png)

Now we're going to come up with another SK learnn object。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_41.png)

Here's going to be the polynomial features we're going to pass in degree equals 2。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_43.png)

Include bias equals false。 That's going to just say。

 if you recall when we used polynomial features earlier， I believe we did it in the。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_45.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_46.png)

In our transformations notebook。That will by default output just a column of just ones。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_48.png)

And that's supposed to be the bias term， we're just going to remove that because the linear regression is going to come up with that term on its own。

 that beta not， it's going to come up with that value on its own。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_50.png)

So we said degree equals for two。And now we have our before we had a predictor object with linear regression。

 here we have a transformer object， which allows us to transform our data。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_52.png)

So we don't need to pass it in X and a Y， we can just pass it in X。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_54.png)

So we take our data frame that we see here。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_56.png)

We say P F， that's our objects that we now know is supposed to transform our current variables into squares of itself。

 as well as interactions between each term。 So it'll we also have CRM times Z N， CRIM times Indus。

 so on and so forth。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_58.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_59.png)

So we're going to have a bunch more columns。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_61.png)

And then we're going to set x underscore P F equal to these new sets of columns。

 So it's actually going to output as an array。 So to look at what that actually came out to be。

 I'm going to show you X。Pf。tOh we have the shape underneath， let's just look at now it's an array。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_63.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_64.png)

The original。Data frame that we had for X was equal to 506 rows by 13 columns。

 Now we shall have a lot more columns。 We see our 104 columns to account for all of the squaring of each variable and the interaction between each and unique variable。

😊。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_66.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_67.png)

So now we have XPF， that's going to be the new X values that we are working with。With now 104 rows。

We're going to split， that's including all of the data。

 we're going to split that into a train set where we're actually going to learn our parameters from and a test set to see how well our learned parameters actually performed on new data。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_69.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_70.png)

So in order to do that， we run train test split。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_72.png)

We pass in our X variable， our new X PF， our Y variable， which is the outcome variable med V。

 the medium value。 How big do we want our test set to be。

 So how much are we going to hold out We say 30% and the other 70% will be used for training those parameters and then finally we set a random state because it's going to pull out a random 30% of the values for the test set We want it to be the same random amount So we set the random state here。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_74.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_75.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_76.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_77.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_78.png)

So now we have four different variables that's going to output x train， x test， Y train and Y test。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_80.png)

We want to bring down our X train。So now we have xtrain。

 which is what the x values that we're going to use to train our linear regression model。

We're going to use the standard scalar to transform that X train。 So you're following along。

 we started with X。 we took the polynomial features to get that to x to degree2。

 so we ended up with those 104 columns。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_82.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_83.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_84.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_85.png)

We then split that into an X train and an X test。 We only care about X train。

 which is a subset of the X PF。 so we can look at。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_87.png)

X train dot shape。And we see that's 354， and that's just because it's 70% of our original XPF。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_89.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_90.png)

So for that， we're going to use the standard Scalar， which is another transformer object。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_92.png)

We use， we set that equal to S， again， we use the fit transform method。

 and we pass in x train and that will calculate given our x train those 354 rows。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_94.png)

And 104 columns for each one of those columns。 What is the mean value。

 What is the standard deviation and subtract the mean and divide by that standard deviation。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_96.png)

And then we set the standardized version of x train equal to x train S。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_98.png)

And that should add the same shape as before。 Just now。

 the variables rather than being on different scales， they're now all on the same scale。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_100.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_101.png)

So let's think about what transformation we probably want to do next we're doing a ton of transformations here before we get to our linear regression。

 we discussed how we want to bring our Y variable to a normal distribution。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_103.png)

So we're going to use the boxcos that we defined earlier。We pass in why train。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_105.png)

Whi is the subset of just 354 rows， it's just one column because the y is just one column we only want to test on our y train。

 we're only learning our parameters from our x train and Y train。

 so we're only going to do our transformations there first。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_107.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_108.png)

So from that， remember when we run boxcos， we get two outputs。Both the actual transformed values。

 which is going to be index zero of our output here。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_110.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_111.png)

As well as the lambda value that we have learned， that parameter that we learned given our data in order to come up with a normal distribution。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_113.png)

So we run this。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_115.png)

And we have。Our new transform version of the outcome variable。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_117.png)

As well as La2， which is just going to be for that training set。

 what the lambda value you see it's slightly different before。

 because we're only working on a subset of the data in order to come up with a normal distribution。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_119.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_120.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_121.png)

And we should have 354 different values for our Y that should match up with our X train。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_123.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_124.png)

So now we have the X train that we ultimately want， as well as our transformed y variable。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_126.png)

And we are going to fit using our linear regression that we have defined before。

 so if you call all the way up here。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_128.png)

We defined。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_130.png)

Look at the top of the screen， LR equals this linear regression object， which is a predictor。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_132.png)

For a predictor， we need to pass in both the X。And the why。

And that will fit our linear regression to that x and Y， so then it learns the parameters。

We want to see how well these new parameters are going to do on our test set。So for the test set。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_134.png)

We want to make sure that we transform that as well according to how we transform the train set。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_136.png)

If you recall before we split， we did the polynomial features that's fine to do before actually doing your train test split。

When you're doing your standard scalar。You have to do that after doing your trade test split。

If you imagine that you're trying to come up with the parameters for what your standard scalar would be。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_138.png)

And you just have your test set， imagine your test set was just one value。

 you wouldnt be able to come up with the mean and standard deviation in order to normalize that test set。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_140.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_141.png)

So you have to use the mean and standard deviation that was originally defined on our training set。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_143.png)

So we're going to use S， which was defined before。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_145.png)

And then fit to our X train， but rather than running fit transform。

 we're just going to transform using the fit that we defined on our training set。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_147.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_148.png)

So that's going to adjust our X test to this X test S。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_150.png)

And then our predictions will be the linear regression model we call dot predict because it's a predictor。

 it has the predict function， and this will come up with the actual predictions。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_152.png)

And this should be the same shape as the 30% of our test set。 So if you recall x tests。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_154.png)

S， the shape。We see that that is going to be 152 rows。

 so we should have 152 predicted values for y pre B， so y pre。



![](img/dd2cad16dc77b1c7c8a964d9d61594a9_156.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_157.png)

BC dot shape。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_159.png)

We see，152。Now we're going to stop here and when we come back we will do the inverse transform as well as looking at the R2 square to quickly close out the rest of this Jupiter notebook。

 I'll see you there， Thank you。

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_161.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_162.png)

![](img/dd2cad16dc77b1c7c8a964d9d61594a9_163.png)