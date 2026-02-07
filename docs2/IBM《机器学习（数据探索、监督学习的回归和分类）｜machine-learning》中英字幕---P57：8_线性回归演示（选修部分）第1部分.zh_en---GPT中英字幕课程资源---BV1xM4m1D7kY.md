# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P57：8_线性回归演示（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/0f5f8241b7900b44bbb6c570197d8c0d_0.png)

Welcome to our first notebook in course，2。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_2.png)

InThis notebook， we're going to combine a demonstration， as well as a lab。

 We begin by demonstrating the basic regression setup。

 and then we will follow up with two lab exercises In this notebook。

 we will run a simple linear regression using SK learn。

 We will apply transformations to make our target variable more normally distributed for regression。

 and then we will show you how to apply the inverse transformations to be able to use these in a regression context。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_4.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_5.png)

So we're going to first import some of the libraries that we'll use throughout， we have seen nuumpy。

 pandas and Nepllib。ppl before。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_7.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_8.png)

We're also pulling in from our helper Python file， which you see here。

 the Helper Python file is just a file that's specific to this notebook that we're working with。

 and we're pulling out some of the functions above， such as plot exponential data。

 plot square normal data and then in the cell that we're on now。

 we're also going to pull in this function， Boston data frame。

 which is going to output a panda's data frame， which we are going to use for our regression。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_10.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_11.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_12.png)

So we set Boston data equal to a panvas data frame。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_14.png)

We say dot head。And we are able to look at the first 15 values。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_16.png)

First 15 rows。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_18.png)

And the value that we're trying to predict is going to be this last column， which is MEDV。

 which stands for median value of the household in a certain area。

 and the rest of the columns are just going to be different features that we will use in order to predict this outcome variable。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_20.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_21.png)

So how can we determine normality of this column？Making our target variable normally distributed often will lead to better results。

 Now， I don't want anyone to get confused。 It is not necessary for linear regression for the outcome variable to be normally distributed。

 It may help which we're going to see later on that it does here， and it's worth trying。

 but it's not necessary， what is necessary for linear regression。 is that our。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_23.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_24.png)

Errors are normally distributed。So don't confuse the two or conflate the two as we are adjusting this outcome variable。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_26.png)

So coming back to adjusting our outcome variable， if our target is not normally distributed。

 we can apply a transformation to it， and as we've seen in the past course， once we do that。

 we can also fit our regression to predict those transform values。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_28.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_29.png)

So how can we tell if our target is normally distributed to start？

There's two ways of doing so we can look at the data itself and see if a histogram looks normally distributed as well as running a statistical test。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_31.png)

So I'm doing this visually。We just pull out the column that we want to specify， which was ME DV。

 and we run dot Het using the pandas built in plotting functionality。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_33.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_34.png)

And because of this right tale， we'll probably assume that we're not working with a normally distributed data here。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_36.png)

We could also pull in from sippi。t。 M stats the normal test。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_38.png)

Also known as Di Diia Goino's K squared tests， which you could look up， the idea being that。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_40.png)

We don't want to get into Beijing versus frequent district debates， but we're working with。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_42.png)

Frequ within the frequentous realm here， this is a statistical test that tests whether a distribution is normally distributed or not。

So this test is going to output a P value。The higher this P value is。

The closer the distribution is to normal。 so remember extreme P values， meaning very。

 very low P values means that we will reject the null。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_44.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_45.png)

Higher P values。Will mean that it is closer to one。

 and therefore we would not reject the me hypothesis。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_47.png)

So therefore， our null hypothesis here is going to be that we have a normally distributed data。

 and if we have a very small P value， then we would reject that null and say we don't have a normally distributed data。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_49.png)

So let's run the normal test on our values。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_51.png)

Sorry， I didn't run this cell just before。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_53.png)

And we see that we have a P value 1。7 times E。To the negative 20。

 so this is just essentially saying news。9 decal19 zeros before that one， so it's 0。0000， et cetera。

 so this is very far from a normal distribution。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_55.png)

And we would reject our null hypothesis of a normal distribution。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_57.png)

So linear regression is going to assume normally distributed residuals again， like I said。

 not the y variable， but the residuals， and that can be aided by transforming our y variable。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_59.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_60.png)

So let's try some common transformations to help us get to why being normally distributed。

 we have the log transformation taking the square root of the values and then finally the box cost transformation。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_62.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_63.png)

So first we're going to try the log transformation。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_65.png)

So just to see what that looks like in general， what we would hope for。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_67.png)

We're going to plot exponential data， this is going to be log normal data set。

 So once you take the log of this data。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_69.png)

This is our data variable， which is just going to be plot exponential data。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_71.png)

If we took the log， we would end up with a histogram that looks much more normally distributed。

So if you see data that look similar to what we have above with the plot exponential data with all these values very close to the minimum and then a tail trailing off。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_73.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_74.png)

Then we would probably suffice with the log transformation。So let's see how that works。

 we're going to take use NP。lo。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_76.png)

And apply that to our column， Bostondata。 medianvalue。

And now we have a new column or a new array that's just the log mediumn value。Right， and a series。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_78.png)

We can take the histogram using the built in pandas functionality。

 It looks a little bit closer to normal。 It doesn't have that long tail。

 but still probably not quite。 we'll run our normal test， and we see we don't have 19 zeros。

 but we still have a very low P value and we would probably reject the null that we are working with something close to normal distribution。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_80.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_81.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_82.png)

So for the exercise we then want to do a square root transformation。

 this is another transformation that maybe can take non normally distributed data and make it into normally distributed data。

So as we did before， we're going to take the。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_84.png)

Toy data， which is the perfect example of where we would end up square rooting it。

 and we would have this。If you think about what this is， this is just a normal distribution squared。

 so some of our higher values would end up being bigger outliers throughout and when we take the square root。

 we end up with a normally distributed data set。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_86.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_87.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_88.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_89.png)

So let's apply the square root transformation to our target variable that we're working with。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_91.png)

All we have to do is we're going to set SQrRT underscore M V。

 that's going to be the variable set to the Pada series。

 which is just the square root of our current target column。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_93.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_94.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_95.png)

And plot that histogram。Still probable， I mean this is probably less so than the log seem to be a normally distributed data set。

 we can run our normal test as well， and we have four zeros again before our three。

 so again there would be a very low P value and we reject the null of a normally distributed column over here。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_97.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_98.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_99.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_100.png)

Finally， we have the box cost transformation and this is a parameterized transformation。

 if you recall when we talked about parametric versus non parametric models。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_102.png)

When we have a parametric models， we have a set specific amount of parameters that we're trying to come up with。

 so here it's just going to be the lambmbda value。To get us as close to a normal distribution as possible。

 the box Gs transformation is defined as take the boxcox of y。

 which is going to be y to the power of this lambda minus1 divided by lambda。

You can think of this as a generalization of the square root， so for the square root function。

 the lambda value would have been around 0。5 again it would't divide by 0。

5 but it be the square root is just a value to the power of 0。5。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_104.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_105.png)

Instead we're going to allow the lambda to vary and it's going to find the lambda that gets us closest to having a normal distribution。

 so that's the beauty behind the boxcos transformation。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_107.png)

So we're going to import the boxcox transformation from sippi。 stats。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_109.png)

We're going to run that transformation。On our data。

 similar to how we applied the log and the square root。And the results。

 and I'm going to run this real quick。And the result's going to give us two outputs。

 so you can see BC results。As two outputs， the first output is just going to be。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_111.png)

The actual transforms array。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_113.png)

And then the second one's going to be the lambda that was used。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_115.png)

So we can run that it's actually right below， we see the 0。2 rather than 0。

5 is going to be the exponent that we use。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_117.png)

We can look at our original histogram and then the boxcox version of our histogram。

 it looks a lot more normally distributed， we can run the normal test。

 our P value is higher than our 0。05 threshold， so this time we do not reject the null of a normally distributed data set that we are working with and we are going to assume that we have something that's close enough to a normal distribution。



![](img/0f5f8241b7900b44bbb6c570197d8c0d_119.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_120.png)

So we're going to stop here and in the next lesson we will continue in this notebook and talk about working with regression with our new transform variable。

 Thank you。

![](img/0f5f8241b7900b44bbb6c570197d8c0d_122.png)

![](img/0f5f8241b7900b44bbb6c570197d8c0d_123.png)