# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P67：-067-Statistical Learning_ 9.R.2 Nonlinear Support Vector Machine.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， so that was the linear support vector machine in the previous session now we're going to do the nonlinear support vector machine and again。

When fitting the support vector machine， the cost parameter is a tuning parameter that one would normally have to select。

 we're not going to do that in these sessions， but you can use cross validation to select that and that's done in the R sessions in the book。

 but we're not going to do that。So what we're going to do here is actually take an example from the more advanced textbook elements of statistical learning。

 which had a canonical example of dimension in two dimensions where the decision boundary was nonlinear。

😊，And we're going to use the kernel support vector machine to try and learn that boundary and so we're going to use that example so we can actually get the data for that example from the elements of statistical learning book and you can see we've got a load command and we're going to load directly from a URL which is the web page where these data live and so you can see the URL and the data is the mixture data it simulated data and so you see how to read data directly from a website。

so the data is loaded and now we can say names and we see that this is actually a list these data。

 It's got a number of components。ForFor the moment， the training data are x and y。

 and there's some other variables on there which we'll get to in a moment。Now， first of all。

 we've already created an X and Y for our previous examples。

 so I'm going to just get rid of those so that I can attach this list。Which which I've now done。

So let's plot the data。And there they are two dimensional data。 they seem to overlap quite a bit。

 but we'll see that there's something special in in the structure of these data。

We'll make a data frame with the response why and and we'll turn that into a factor and and just much like before。

 and now we'll fit a support vector machine， but here the kernel will be radial and we'll give a cost parameter of 5 and again we won't scale the data。

Okay。And so that's fit。 And so now we're going to create a grid as before and make predictions on the grid。

Now， these data they actually came supplied with with grid points。

 If you look down on the summary of of the on the names of that were on the the list。

There's two variables， px1 and px2。 and so these are。Grid of of values for each of the two variables。

 Okay， so we don't actually have to use our， our function that we created。

 We can just use the expand dot grid directly to create the grid of values。 And so we do that。

And like before， we will predict。The， the classification at each of the values on the grid。

And now we will plot and include the points and color the points according to the decision boundary。

And w， look at that。So you can see the decision boundary is non nonlinear now。And， and it， it's。

TheThe red points are the red regions largely to the top and the the black regions largely down below。

 we can put our data points in the plot and we see where the data lies。

And you can see that the the decision boundaries to， to a large extent， following where the data is。

 but in in a very non nonlinear way。Okay， let's see we。

 we can improve this plot a little bit further。 We'd actually like to。

Put in a curve that gives a decision boundary。And what we're going to do to do that is we're going to use the contour function。

Okay。嗯。On the data， on the， on the。Data frame is also a variable called Prob。

And actually gives these data was simulated and Prob gives a true probability of a plus one versus a minus one at every value on on the grid that we have here。

Okay， so we can do two things。 We're going use the contour function， and we're gonna。

 we're gonna plot the contour of probeb。At a half， which would be the true decision boundary for these data。

And then what we're going to do is we're going to。We're going to predict from our model。

 we're going to predict not just the class label， but we're going to predict the function itself。

 and we we'll get the decision boundary that's learned for these data by plotting the contour of that function。

 the zero contour because that function we classify a plus one if it's positive otherwise to minus1。

And so we're going to do that for each of these and include them on the plot。Okay。So。

The first one is， we'll just predict our foot on the grid。 Okay。

 but we tell it decision values equals 2 because we want to get that function。

 the actual function and not just the classification。And the way it returns that。

 it returns it as an attribute of the actual classified values。

 so we have to pull off that attribute。And so we use the attributes function that pulls of all the attributes。

 and then we access the one called decision。 And so now we have the function that we want。And we。

Once again， we have our grid。 Actually， we'd made it already。 We doesn't need to make it again， and。

We。We've got our classification again， so now we make the same plot as we had before。

We add our points again， and now we'll make a contour。And we use a contour function。

 and it it requires those two grid sequences as well。

 And then at once the function you want to contour in the form of a matrix。

And if you look at the dimensions of px1 and Px2， you'll see they 69 and 99。And this function。

 we're going to conduour it levels 0， and we're going to add it to the plot。And sure enough。

 you can see that tracks the decision boundary。 So that's a really handy way of plotting a nonlinear decision boundary in two dimensions。

And finally， we include the truth。Which is the contour of the probabilities。

 which we're gonna that's the fifth， the 。5 contour。

 which would be the decision boundary in terms of the， the probabilities。

 And so that's the true decision boundary or the， what's called the Bayes decision boundary。

So that's the ultimate one。 If we had large amounts of data we'd hope to be able to get very close to that。

 but you can see our nonlinear support vector machine has got pretty close to that。

 especially in the regions where we've got data。And so yeah。

 we've seen how to include these nonlinear boundaries in the plots。Okay。

 so we finished the session so once again we were using R markdown and where we've mixed an actual text with our R commands。

 the whole the two sessions on SVM are like that。 and at the end of it all we can use the function knit。

And it runs through all the code and produces a nice web document that summarizes。

All that we've done。 This is something you can share with your colleagues。 You can display it。

 You can put it on your own website， puts all the figures in and， you know， and。

 and shows exactly what you've done in all the plots， everything that we produced in somewhat。

It nice quality as well。 And so this， this is a document that you can save and， and， and distribute。

