# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P55：6_线性回归简介第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this next section， we're going to go over our first model， linear regression。

So our learning goals for this section will cover。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_1.png)

Linear regression and understanding how that model is built。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_3.png)

Understanding modeling best practices in regards to how to choose our actual coefficients in order to fit our data。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_5.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_6.png)

And then finally， we'll discuss measuring errors and specifically the measuring errors that we'll be using for regression and linear regression specifically。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_8.png)

So in our introduction to linear regression， we will be working with this example that we see here。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_10.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_11.png)

Where we're trying to predict the box office revenue of a movie using the marketing budget only。

 so here to left we see a scatterplot of many movies from our data set where we have the labeling of what the actual box office revenue was。

 as well as our input variable， which is our marketing budget。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_13.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_14.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_15.png)

And what we're going to try to do is find a line of the form。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_17.png)

Y beta of x equals beta ns plus beta 1 x， so we see our model here。

 and we're trying to learn given our data set the optimal values for beta ns and beta 1。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_19.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_20.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_21.png)

Our target variable that we're trying to predict is going to be the box to office revenue。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_23.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_24.png)

Beta knots is going to be that first coefficient that we're trying to learn and that essentially is imagine that x is equal to zero。

 then our box office revenue would just be equal to this beta knot so if we had no marketing budget in this situation。

 what would be our box office revenue？

![](img/a9430d53e9baf1250ee3a14f7976cd4b_26.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_27.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_28.png)

Beta not beta 1 is going to be the coefficient of x and that's going to be the slope of our line。

 in other words for each extra dollar of budget spent。

 how much will our box office revenue go up so as we move to the right on the budget how much will we go up in the box office revenue？



![](img/a9430d53e9baf1250ee3a14f7976cd4b_30.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_31.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_32.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_33.png)

And then X is just going to be that one feature that we are working with。

 namely our marketing budget。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_35.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_36.png)

So we end up fitting this line。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_38.png)

And we're going to tell you now that this is the best line and it will be defined by certain values of beta n and beta 1。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_40.png)

Now， how did we get to this line， What we did is we minimize the cost function。

 Remember that function that was J of our predicted values and the actual values。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_42.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_43.png)

That was our loss function that we learned earlier on。What we did is we used that。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_45.png)

To find parameters beta and beta 1 that will minimize the distance between our prediction and the actual y values。

 so this line is the line that minimizes all the distances out of any other line that you can predict between each one of these dots and the line and the line being our predictions。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_47.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_48.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_49.png)

So you see under beta not that we came up with a value of 80 million。

 meaning that if our movie budget was zero， then our box office revenue would start off at 80 million。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_51.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_52.png)

And then for beta 1， we get the value of 0。6， so for every extra dollar of marketing。

 we increase the box office revenue by 0。6。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_54.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_55.png)

And with this line， we can predict what the box office revenue will be for a new movie。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_57.png)

So let's say that our marketing budget was 160 million。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_59.png)

Then we can use this in order to calculate 80 million plus 0。

6 times 160 million will get you approximately to 175 million。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_61.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_62.png)

Now let's analyze how we found the special line that is minimizing that cost function that we discussed。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_64.png)

Now for a given line， we will have predicted values。

 which are just going to be the values on the line itself。

 those would be our predictions as well as the ground truth from our training set and those are going to be the actual。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_66.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_67.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_68.png)

Budgets that we see here for all the different movies。

 and those are the different points on the scatter plot。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_70.png)

And for any value of x and y， we can then see our error by just subtracting our prediction by the actual value。

 as defined by these lines that are being drawn as I talk through this。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_72.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_73.png)

And we can think of this formula where y beta of x is the predicted value given our line。

 so all the points exactly on the line and yObs is the actual outcome variable。

 so those are again those different points on the scatter plot。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_75.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_76.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_77.png)

And using this for any movie， we can know the magnitude of our error in our predictions。

 the magnitude defined as the distance from that actual observation and the line that we predicted。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_79.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_80.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_81.png)

Let's now discuss the error function that we would actually try to minimize when doing linear regression。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_83.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_84.png)

So we see here the error formula for a given observation， similar to what we saw before。

 we have beta not ends， beta 1 of x as well， but that just replaces what we saw earlier in regards to this being a function of x minus the actual values。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_86.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_87.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_88.png)

Now， since this value can be negative。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_90.png)

We're more interested in a positive version that can actually tell us the magnitude so that the error being negative versus the error being positive between two different movies wouldn't cancel each other out。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_92.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_93.png)

So you can do something like the absolute value， which we call the L1 norm。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_95.png)

Or what's more commonly done is we can use the Euclidean distance。

 which will actually give us the length of each one of our lines between the actual outcome and the line that we predicted。

 so it'll give the magnitude of these lines by actual distance and this is called the L2 norm。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_97.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_98.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_99.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_100.png)

Now this is probably the most popular cost function for linear regression。

And we call it the mean squared error， which is pretty simple because it's the squared error for each one of the values divided by the number of values。

 so it's the average squared error。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_102.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_103.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_104.png)

And it gives us that average length of each one of those gray lines that we saw in the previous figure。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_106.png)

Now here the x's and Y's are given in the training set。

 and we're thinking of this as a function of beta not and beta 1。

 we're trying to optimize those values。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_108.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_109.png)

Such that we minimize the distance and we minimize this mean squared error。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_111.png)

And that will give us the best line。

![](img/a9430d53e9baf1250ee3a14f7976cd4b_113.png)

And this is ultimately that loss function J we are trying to optimize note the cost function will be written over 2M。

 so1 over 2M rather than the1 over M that we just saw earlier。

 and this is just due to ease of calculation when we're trying to minimize this squared error using calculus but minimizing this value versus minimizing1 over M will be exactly equivalent。



![](img/a9430d53e9baf1250ee3a14f7976cd4b_115.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_116.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_117.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_118.png)

![](img/a9430d53e9baf1250ee3a14f7976cd4b_119.png)