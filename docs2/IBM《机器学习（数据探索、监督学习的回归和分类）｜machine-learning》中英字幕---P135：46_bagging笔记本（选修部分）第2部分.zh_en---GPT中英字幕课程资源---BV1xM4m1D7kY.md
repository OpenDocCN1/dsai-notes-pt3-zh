# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P135：46_bagging笔记本（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/4a9906896b6c7764f88ffcf625efa72b_0.png)

Welcome back for part three of our notebook here on Bagging。In this section。

 we're going to show how using random force， we can increase the number of trees。



![](img/4a9906896b6c7764f88ffcf625efa72b_2.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_3.png)

See the air decrease as we increase that number of trees up to a certain point。



![](img/4a9906896b6c7764f88ffcf625efa72b_5.png)

And then that air will eventually plateau as we discuss in lecture。

 and where at plateaus we can say that is enough trees to fit for our optimal model。Now。

 something to note is since the only thing changing for our model is the number of trees。

 this warm star argument can be used so that the model just adds more trees to that existing model each time。

 and we're going to use the set Rams method to update the number of trees on that initialized classifier and we'll see that in just a second。



![](img/4a9906896b6c7764f88ffcf625efa72b_7.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_8.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_9.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_10.png)

So， we。First， import our random force classifier from SK learnednda Ensemble。

We then initiate our object and we want to be getting our out of bag score。 that's that OB score。

 So we set that equal to true。 And if we recall that out of bag score is for each one of our decision trees。

 this set that it was not trained on checking that error。



![](img/4a9906896b6c7764f88ffcf625efa72b_12.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_13.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_14.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_15.png)

We're setting a random state。We're going to have that warm start as we just discussed equal to true。

 and since randomand For will be running things in parallel。

 we set the number of jobs equal to the maximum value by just setting it equal to negative one。

 as discussed in prior notebooks。

![](img/4a9906896b6c7764f88ffcf625efa72b_17.png)

So we want to track each one of our out of bag errors， so we're going to create an empty list here。



![](img/4a9906896b6c7764f88ffcf625efa72b_19.png)

And then we're going to loop through each one of these numbers of trees。

 so were going start with 15 and 20， 30， so on through each one of these numbers in our list here up until 400 trees to see where it kind of plateaus as we increase the number of trees。



![](img/4a9906896b6c7764f88ffcf625efa72b_21.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_22.png)

So we take our initialized object RF。

![](img/4a9906896b6c7764f88ffcf625efa72b_24.png)

And we call set parameterss， as we just discussed。 And the only thing that we continually update is this number of estimators。

 And we set that equal to wherever we are in our for loop for that number of trees。



![](img/4a9906896b6c7764f88ffcf625efa72b_26.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_27.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_28.png)

We can then fit it on our training set。We can then get our out of bag error by saying one minus that out of bag score。

 that's going to be an attribute available only if you set out of bag score equal to true。

 which we have。

![](img/4a9906896b6c7764f88ffcf625efa72b_30.png)

And then we're just going to store that。 So we pen that onto our empty list。

 and that's just going to be a series that has our number of trees as one of its indices and then the out of bag error for the other one of its indices。

 And then finally， we will concatenate all that into a data frame and set the index equal to number of trees。

 So we're going to run this。

![](img/4a9906896b6c7764f88ffcf625efa72b_32.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_33.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_34.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_35.png)

And it'll take just a second to run。And it should output as we see here。

A pandas data frame with the correlation， the respective out of bag error for each one of the number of trees。

 So we see 15 and 20， so on and so forth。 And we see that it's gradually decreasing。

 And then at around 100 to 1050， it seems to plateau。



![](img/4a9906896b6c7764f88ffcf625efa72b_37.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_38.png)

And we're also going to look at a graph。

![](img/4a9906896b6c7764f88ffcf625efa72b_40.png)

Here we're just going to。Call that data frame， call dot plot。

 and we're going to set marker equal to O。We're actually going to connect it with a line with the line width equal to five。



![](img/4a9906896b6c7764f88ffcf625efa72b_42.png)

And we're going to set our Y label to out of bag air， and when we run this。

 we can see that drop off in error。

![](img/4a9906896b6c7764f88ffcf625efa72b_44.png)

And then it's really at its low at around 100。 And it seems to somewhat go down。

 Something I do want to point out is be careful whenever you are creating a plot。

 This plot goes from 0。048 to 0。056。 So there's a really tiny difference in each one of these differences is 0。

002。 So there's really a minimal difference between each one of these errors once we get down to this lower point。



![](img/4a9906896b6c7764f88ffcf625efa72b_46.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_47.png)

And。At that with that juncture， you want to keep in mind that each one of these raw numbers。

 So these were really relatively close at 1001，50，200 and so on。



![](img/4a9906896b6c7764f88ffcf625efa72b_49.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_50.png)

Now we want to use that same practice for our extra trees classifier that we introduced in lecture as well。



![](img/4a9906896b6c7764f88ffcf625efa72b_52.png)

So here is going to be all the same steps。 Something that we need to do is set the bootsstrrap。



![](img/4a9906896b6c7764f88ffcf625efa72b_54.png)

Argument equal to true。And the reason why we do that is we won't be able to get that out of bag error unless we have。

 unless we're bootsshopping our model， that bootstrap means that we're taking a sample and that out of sample is going to be that out of bag。



![](img/4a9906896b6c7764f88ffcf625efa72b_56.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_57.png)

In general， the default is going to be Boraprap equals false for extra trees classifier。

 and then it will fit on the entire data set， and that will be allowed because this extra trees classifier is more about coming up with random splits than anything else。



![](img/4a9906896b6c7764f88ffcf625efa72b_59.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_60.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_61.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_62.png)

And then again， we set warm star equal to true， out of bag score equal to true。

 and again that will only work if the boott is true。

 and then the number of jobs is just as many jobs as it can run in parallel given your computer。



![](img/4a9906896b6c7764f88ffcf625efa72b_64.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_65.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_66.png)

We're then again going through that same syntax of setting an empty list of our out of bag air。



![](img/4a9906896b6c7764f88ffcf625efa72b_68.png)

We run a for loop through each one of these different numbers of trees。



![](img/4a9906896b6c7764f88ffcf625efa72b_70.png)

We set our parameters number of esimators equals to number of trees。



![](img/4a9906896b6c7764f88ffcf625efa72b_72.png)

Fitted on our X train and Y train。

![](img/4a9906896b6c7764f88ffcf625efa72b_74.png)

We get our new out of bag error by 1 minus EF00B underscore score。



![](img/4a9906896b6c7764f88ffcf625efa72b_76.png)

And then we app on that panda series with a number of trees and it's respective out of bag air。



![](img/4a9906896b6c7764f88ffcf625efa72b_78.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_79.png)

And then again， in the same fashion， we dump that into a data frame。



![](img/4a9906896b6c7764f88ffcf625efa72b_81.png)

So we run that。And we get again， our different errors。



![](img/4a9906896b6c7764f88ffcf625efa72b_83.png)

We're going to combine each one of these two data frames together so we can plot them together。



![](img/4a9906896b6c7764f88ffcf625efa72b_85.png)

So all we have to call is PDd。comca， put them each in a list and say we want to concatenate on the columns。



![](img/4a9906896b6c7764f88ffcf625efa72b_87.png)

When we run this， we see that we have our random forest column and our extra trees column with their respective errors。



![](img/4a9906896b6c7764f88ffcf625efa72b_89.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_90.png)

And then when we plot these out， we see for this specific example， and this is always the case。

 but it is generally most often the case that random force will perform a bit better。

 we see that random force does perform better across each one of the number of estimators with that line consistently that line of the error consistently below that of extra trees。



![](img/4a9906896b6c7764f88ffcf625efa72b_92.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_93.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_94.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_95.png)

So that closes out this section of walking through both the random forest and the extra trees。

 as well as seeing that plateau number。

![](img/4a9906896b6c7764f88ffcf625efa72b_97.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_98.png)

With that， we're going to move into selecting one of those better models and looking at each one of the error metrics for that model。

 Allright， I'll see you in the next video。

![](img/4a9906896b6c7764f88ffcf625efa72b_100.png)

![](img/4a9906896b6c7764f88ffcf625efa72b_101.png)