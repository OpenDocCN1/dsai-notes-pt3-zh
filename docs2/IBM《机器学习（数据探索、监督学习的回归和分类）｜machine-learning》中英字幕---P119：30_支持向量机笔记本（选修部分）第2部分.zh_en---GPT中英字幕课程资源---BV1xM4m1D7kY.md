# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P119：30_支持向量机笔记本（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/473ee5946d3b0a649553904dac590c9f_0.png)

All right now let's walk through part two， where we're going to actually create our linear decision boundary。

Now our goal is to look at the decision boundary of a linear SVC classifier using our data set。

Now we're going to fit a linear support vector Ma classifier using our X with just two dimensions and our Y。

We're then going to pick 300 samples from our X and get the corresponding y values for each one of those 300 samples and store them in variables X color and Y color。

 and this is because our original data sets could be too large when we actually want to plot this out within our two dimensional frame。

We're then going to modify Y color so that it's red instead of1 and yellow instead of zero。

 so we're switching them back to their actual strings。

 and that will allow us to also color code our graphs。

We're then going to add a scatter plot of our X colors columns using the keyword arguments color equals y color。

 using those colors that we just discussed。

![](img/473ee5946d3b0a649553904dac590c9f_2.png)

And then we're going to use this code that we have below in order to come up with this contour plot that will show given each one of our two variables which we'll have on the X and Y axis。

 what is going to be our prediction。

![](img/473ee5946d3b0a649553904dac590c9f_4.png)

So I'm going to break that out step by step first I'm going to run this code here。



![](img/473ee5946d3b0a649553904dac590c9f_6.png)

![](img/473ee5946d3b0a649553904dac590c9f_7.png)

And then we're going to break this out step by step。So。



![](img/473ee5946d3b0a649553904dac590c9f_9.png)

We see at the end that we produced this plot where we have the classifier being that red line and below that line we classified as red wine and above that line we classified as white wine。

 so how do we get there。

![](img/473ee5946d3b0a649553904dac590c9f_11.png)

The first thing that we wanted to do。Is first initiate our model， so we run LSVC。

 and then we fit it on every single value in our training set。RightOn X and Y， again。

 we're not having a holdouts here， so we're fitting on every single model， every single data point。

 so we have the best fit possible for our model。We're then going to get our sample of just 300 of those rows。

 As discussed， we only want a small sample because otherwise this plot below would have been overcrowded。

We're then going to use that x color， which is just a sample of 300 points。And set R。Our white color。

To just the same exact values with that same index that we just identified。



![](img/473ee5946d3b0a649553904dac590c9f_13.png)

So now our X color and Y color will match up。

![](img/473ee5946d3b0a649553904dac590c9f_15.png)

Then as mentioned， we're going to take that Y color。



![](img/473ee5946d3b0a649553904dac590c9f_17.png)

And map Lambda R。That's just saying R is going to be our input。

We're going to call it red if that value is equal to one。

And then we'll call it yellow if it's anything else， which will just be zero。

 So now we've mapped our Y color from ones and zeros to reds and yellows。

We're then going to initiate our bounding box using PLT do axes。



![](img/473ee5946d3b0a649553904dac590c9f_19.png)

And then we're just going to plot our scatter plot of the two values using x dot scatter。

And then we call X color， which is。A features。And we're saying all of our rows and just the first column that's going to be our x axis。

And all of our rows and the second column， that's going to be our Y axis。



![](img/473ee5946d3b0a649553904dac590c9f_21.png)

And then for that， we're going to also identify the colors。

 which is going to be our labels here as red or yellow， using that Y color that we just identified。



![](img/473ee5946d3b0a649553904dac590c9f_23.png)

![](img/473ee5946d3b0a649553904dac590c9f_24.png)

So at this point， if we just plotted that out。

![](img/473ee5946d3b0a649553904dac590c9f_26.png)

Let's copy this above。

![](img/473ee5946d3b0a649553904dac590c9f_28.png)

We just had the scatter plot without our line that would be separating those two out。

And now we want to see how do we come up with a linear separator on this plot？



![](img/473ee5946d3b0a649553904dac590c9f_30.png)

And that's where all of this code that we have above starts to come into play。



![](img/473ee5946d3b0a649553904dac590c9f_32.png)

So the first thing that we do， when we call NP dot range0 to 1。005 counting point。

005 is just we have that many。

![](img/473ee5946d3b0a649553904dac590c9f_34.png)

![](img/473ee5946d3b0a649553904dac590c9f_35.png)

![](img/473ee5946d3b0a649553904dac590c9f_36.png)

Values， let's just show this above。You see that we have values counting from zero to  one。

 counting by 0。005， and we don't include that last value。



![](img/473ee5946d3b0a649553904dac590c9f_38.png)

![](img/473ee5946d3b0a649553904dac590c9f_39.png)

So we have that for both our X axis and our Y axis。



![](img/473ee5946d3b0a649553904dac590c9f_41.png)

We're then going to pass that into something called the NP。meshgrid。



![](img/473ee5946d3b0a649553904dac590c9f_43.png)

Now I'm going to show you what that X，x and Yy data outputs look like。



![](img/473ee5946d3b0a649553904dac590c9f_45.png)

We have here this Xx， which is just going to be。

![](img/473ee5946d3b0a649553904dac590c9f_47.png)

For every single y variable， we will repeat that x multiple times。



![](img/473ee5946d3b0a649553904dac590c9f_49.png)

So you see that each one of these rows are exactly the same。

And then we'll see that each one of these y's are exactly the same。Again， on different axes。

 and that will allow us to look across this grid。 So if we look back at our scatter plot above。

 we can imagine that being a grid of ranging from 0 to 1， counting by 0。005。

 where you can look at each one of these different x and y values。



![](img/473ee5946d3b0a649553904dac590c9f_51.png)

![](img/473ee5946d3b0a649553904dac590c9f_52.png)

And seeing what the actual outcome will be for each one of those X and Y values。



![](img/473ee5946d3b0a649553904dac590c9f_54.png)

![](img/473ee5946d3b0a649553904dac590c9f_55.png)

So now that we have this grouping of all these different x and y values ranging from0 to 1 on the x axis and0 to 1 on the y axis。



![](img/473ee5946d3b0a649553904dac590c9f_57.png)

We then are going to use this ral function to just have that all in one long array。



![](img/473ee5946d3b0a649553904dac590c9f_59.png)

So I can see atyy。ravel。And you see。For Yy dot ravel and X X dot ral。

 you'll just have all the values multiple times we can look at the shape that's actually be really big。

Because it's going to be each one of those values that we had from zero to one。

For every single value of y， so that we can check for every single value of x and every single value of y。



![](img/473ee5946d3b0a649553904dac590c9f_61.png)

And then what should make this all clear is when we put this all into a data frame。And get our grid。



![](img/473ee5946d3b0a649553904dac590c9f_63.png)

![](img/473ee5946d3b0a649553904dac590c9f_64.png)

This may take just a second。We see that we have now this will be every single value at the0 of x and every single value of y。

 and each of those x's and y's are meant to represent a fictional amount of either acidity。



![](img/473ee5946d3b0a649553904dac590c9f_66.png)

![](img/473ee5946d3b0a649553904dac590c9f_67.png)

We have to look of either acidity or total sulfur dioxide。



![](img/473ee5946d3b0a649553904dac590c9f_69.png)

And for every single one of those values， and remember， those values were scaled between0 and 1。

 So we're looking through all the different possible values between0 and1。



![](img/473ee5946d3b0a649553904dac590c9f_71.png)

And then we're actually going to predict on this data frame for every single one of these potential values for0 or1。

 what the linear SVC that we learned on our X and Y would have predicted。



![](img/473ee5946d3b0a649553904dac590c9f_73.png)

So that's where we see LSVC dot predicts on our X grid， which is just that data frame。



![](img/473ee5946d3b0a649553904dac590c9f_75.png)

And then where you are reshaping that so that it's the same shape as our Xx dot shape。So originally。

 it'll just be a single array。We can look at our。Why we'll have to call it like this。Pull us out。



![](img/473ee5946d3b0a649553904dac590c9f_77.png)

We see that this is just going to be a single array。



![](img/473ee5946d3b0a649553904dac590c9f_79.png)

And then when we call reshape to Xx dot shape。

![](img/473ee5946d3b0a649553904dac590c9f_81.png)

Is now going to be that same shape as Xx as well as YY。



![](img/473ee5946d3b0a649553904dac590c9f_83.png)

And when we run our contour graph， we can call X， X， Y， Y。And then for each one of those x's and y's。

 we can pass in what the prediction is。And that's what that allows us to do。

 So now we have our X our Y， as well as our prediction。



![](img/473ee5946d3b0a649553904dac590c9f_85.png)

And then when we run this on top， we end up。With our decision boundary。

Where we get each one of our predictions and to the lower end we have。

 and they're just going to predict either ones or zeros right because that's going to be what our linear SVC is going to predict and it's going to map the ones giving our color map as red ours and our zeros as yellow。

So that's how we end up with our contour plot on top。



![](img/473ee5946d3b0a649553904dac590c9f_87.png)

So now we know how to create this contour plot on top of a scatter plot given our decision boundary。



![](img/473ee5946d3b0a649553904dac590c9f_89.png)

And from here， we'll learn how to also look at using what we just using the graph we just explained。

 how to look at different Gaussian kernels as well as different hyperparameter to see the effects of regularization versus not regularizing our different models that we're going to use。

 All right， I'll see you in the next video。

![](img/473ee5946d3b0a649553904dac590c9f_91.png)

![](img/473ee5946d3b0a649553904dac590c9f_92.png)

![](img/473ee5946d3b0a649553904dac590c9f_93.png)

![](img/473ee5946d3b0a649553904dac590c9f_94.png)