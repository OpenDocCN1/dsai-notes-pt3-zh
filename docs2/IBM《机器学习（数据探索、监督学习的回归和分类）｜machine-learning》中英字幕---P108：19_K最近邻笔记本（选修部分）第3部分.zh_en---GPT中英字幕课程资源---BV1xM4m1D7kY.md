# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P108：19_K最近邻笔记本（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Allright， let's get started with question number four now that we have our preprocess data and that preprocessed data encoded and scaled accordingly。

 we now want to split it up into our features and our target variables and that's just going to be all of our values besides for the churn value and then our target variable will be that churn value。



![](img/c5a28d261316d48ae10768633c59d107_1.png)

![](img/c5a28d261316d48ae10768633c59d107_2.png)

We're then going to split those the features and our target into our training and test sets so that we can train on a certain X and Y and test on a certain X and Y。



![](img/c5a28d261316d48ae10768633c59d107_4.png)

And then we're going to estimate a k nearest neighbor's model using K equals 3。

 we're going to examine all of our different error metrics。

 as well as looking at our confusion matrix to see where we may have guessed incorrectly and where we may have gone wrong。



![](img/c5a28d261316d48ae10768633c59d107_6.png)

So the first thing that we want to do is import our train test split function from our model selection。

We're then also going to import our K neighbors classifier from SKL do neighbors。

 and then from SK learn do metrics， we're going to pull in our confusion matrix， our accuracy score。

 our F1 score， and then this classification report， which we'll see in just a second。

 which gives us all these scores across each one of our different labels。

 and we'll see what that looks like in just a couple of cells。

So first we're going to split up our data into their x and y values。

 so we just have y is equal to the turn value column and then the x is equal to every other value besides for churn value。



![](img/c5a28d261316d48ae10768633c59d107_8.png)

We're then going to use our train test split， pass in our X and Y values。

 set our holdout set equal to 40%， and that will output our four values， our x train， our X test。

 our Y train and our Y test。

![](img/c5a28d261316d48ae10768633c59d107_10.png)

So we're going to run that。 Now we have all the。Xtrains and X tests that we need。



![](img/c5a28d261316d48ae10768633c59d107_12.png)

We're then going to initiate our K neighbor's classifier with the K equal to3。

Which is the argument we pass in here。We're then going to fit that model to our training set。

 our X train and our Y train。

![](img/c5a28d261316d48ae10768633c59d107_14.png)

And then as we've done with our other models， we can predict on our test set and then start to see how well we were able to perform on our holdout set。

In order to see how well we performed， the error metrics that we're going to look at here are going to be all within this classification report。

 and we'll see this as soon as I run this cell， as well as looking at the accuracy score and the F1 score。

 which are included， but we'll see those separately as well。



![](img/c5a28d261316d48ae10768633c59d107_16.png)

![](img/c5a28d261316d48ae10768633c59d107_17.png)

So what this does is for every single one of our labels here we only have two。

 so rather than saying for the positive or for the negative。

 it's saying for each one of our different values， what was our precision， recall F1 score。

 and then also the support will just give us the number of values in regards to that label。



![](img/c5a28d261316d48ae10768633c59d107_19.png)

![](img/c5a28d261316d48ae10768633c59d107_20.png)

So we see zero， which is that they did not churn。We were able to get for that 0。9 precision。

 so if our precision is 90%， that means out of all those that we predicted that they would not churn。

 we got 90% of those correct。For recall， we got 92%。

 so those for all those that were actually not churned， we predict 92% of them。And then our F1 score。

 and that's again， just using the nu churn as the positive value。And then we see all of the same for。



![](img/c5a28d261316d48ae10768633c59d107_22.png)

The prediction that they did churn right with the value equal to one。

 and we see that is those are much lower values， and then we see that that is a bit of an imbalance data set where we have many fewer of the amount of people that actually did not or did churn compared to did not churn。

 which was 2048。

![](img/c5a28d261316d48ae10768633c59d107_24.png)

We then have our overall accuracy at 86%。 Our macro average will just take the average of each one of these different values that we predicted。

 and our weighted average will take that average except putting more weight towards here our0。

 according to the amount of support， the amount of zeros that they were in our actual test set。



![](img/c5a28d261316d48ae10768633c59d107_26.png)

![](img/c5a28d261316d48ae10768633c59d107_27.png)

The next thing that we're going to want to do is we're going to actually look at our confusion matrix now I want to pull out what that confusion matrix looks like on its own before I put it into this heat map。



![](img/c5a28d261316d48ae10768633c59d107_29.png)

![](img/c5a28d261316d48ae10768633c59d107_30.png)

And we have here on the rows are going to be the actual。Negative。

Those are the actual zeros and the actual ones of the actual not churn versus the actual churn。

And then we have the predicted values on each one of the columns。

So the first column 1880 and 216 are going to be predicted not churn versus the predicted churn will be the 168 and 554。



![](img/c5a28d261316d48ae10768633c59d107_32.png)

![](img/c5a28d261316d48ae10768633c59d107_33.png)

So first we initiate。Our access， our bounding box。And we're using PLT do subplots。

 which will output both the figure， which will give us all the information about our visualization as well as the ax。

 which is just that bounding box。 We set the figure size to 12 by 12。We then say that we want this x。

 what do we want to put into that bounding box， we're going to put in this heat map。

So we put in this heat map。And we pass into our confusion matrix。

Our Y test and our YP as we've done above， and this will give this output that we see here。



![](img/c5a28d261316d48ae10768633c59d107_35.png)

And we're going to annotate it with all the actual numbers， which are the 1880， 168， 216 and 554。

 and then there's just different arguments in order to specify exactly how we want our heat map to look。



![](img/c5a28d261316d48ae10768633c59d107_37.png)

![](img/c5a28d261316d48ae10768633c59d107_38.png)

We're then going to pass in these labels， not churn and churn， and we pass that into our ax。

For our X tick labels and our Y tick labels。

![](img/c5a28d261316d48ae10768633c59d107_40.png)

And then we're also going to say， and I'm going to print this out to make this clear that the rows are going to be our ground truth。

 whereas our columns are going to be our prediction。



![](img/c5a28d261316d48ae10768633c59d107_42.png)

![](img/c5a28d261316d48ae10768633c59d107_43.png)

So we see that for not churn。 We got 1880 of these predicted correctly when the ground truth was。

Not churn。 Then we see that1 hundred and 68 out of the ground truth。 That was not churn。

 We Grace 1880 were actually not churn， and 1 and 68 were churn。 So we got 1 68 incorrect。

 Each one of these blues being the incorrect values。

 So we can see the proportions of how well we are able to predict churn versus not churn here。



![](img/c5a28d261316d48ae10768633c59d107_45.png)

![](img/c5a28d261316d48ae10768633c59d107_46.png)

So moving on to question number five。We're going to use the same split of training in test samples。

 but this time we're going to increase K25 and see how this affects each one of our errormetrics。



![](img/c5a28d261316d48ae10768633c59d107_48.png)

![](img/c5a28d261316d48ae10768633c59d107_49.png)

So now we have number of neighbors equals to five。

![](img/c5a28d261316d48ae10768633c59d107_51.png)

We're going to pass an X train and Y train， predict on our X test and run all of our same reports。



![](img/c5a28d261316d48ae10768633c59d107_53.png)

We see some increases。In our precision， recall an F1 score for our churned values。



![](img/c5a28d261316d48ae10768633c59d107_55.png)

And we see a bit of an increase in accuracy as well as a slight increase on our F1 score。



![](img/c5a28d261316d48ae10768633c59d107_57.png)

Right， the Fthon score was before 0。74， now bumped up to 0。76。



![](img/c5a28d261316d48ae10768633c59d107_59.png)

And then again， we can just plot that confusion matrix using all the same functionality that we did before。

 and we see across a diagonal that we did better on both the not churn with 1889 versus the 1880 as well as the values for churn where we have 573 versus the 554。



![](img/c5a28d261316d48ae10768633c59d107_61.png)

![](img/c5a28d261316d48ae10768633c59d107_62.png)

![](img/c5a28d261316d48ae10768633c59d107_63.png)

![](img/c5a28d261316d48ae10768633c59d107_64.png)

![](img/c5a28d261316d48ae10768633c59d107_65.png)

Finally， we have in question number6， we want to determine the right value for k。

 so we talked about this elbow during lecture， so we're going to check different K values ranging from 1 to 40 to see what's the best value for K and we're going to focus here we have to choose our errormetric So we're going to choose the F1 score as well as our error right when we create these charts。



![](img/c5a28d261316d48ae10768633c59d107_67.png)

![](img/c5a28d261316d48ae10768633c59d107_68.png)

![](img/c5a28d261316d48ae10768633c59d107_69.png)

So how are we going to go about doing this？We're going to have a blank list of F1 scores as well as error rates。

We're then going to do 4K in our range from 1 to 40 right。

 so we're taking every single possible value of k。

![](img/c5a28d261316d48ae10768633c59d107_71.png)

We run a for loop， and then we just keep initiating this KNN classifier。

And each time we pass in our new value of k。 And then once we do that， we can run predicts。

Check out what our F1 score is。Append that to our F1 scores。

 check out what our error was by doing1 minus our accuracy and append that to our error rates。

 and then we'll have a list for every single one of the ks what our actual F1 score and our error rates were。



![](img/c5a28d261316d48ae10768633c59d107_73.png)

![](img/c5a28d261316d48ae10768633c59d107_74.png)

And then we're going to dump those each into different data frames with our columns equal to K being whatever that value is for K。

 as well as the F1 score for that specific K， as well as the same thing for each one of our error rates。



![](img/c5a28d261316d48ae10768633c59d107_76.png)

![](img/c5a28d261316d48ae10768633c59d107_77.png)

![](img/c5a28d261316d48ae10768633c59d107_78.png)

So now we can look at the results that we all get for the F1 results， for example。



![](img/c5a28d261316d48ae10768633c59d107_80.png)

And we see for each K， we have a different F1 score and then for our error results。



![](img/c5a28d261316d48ae10768633c59d107_82.png)

We will see something very similar。Now， what we want to do is plot these out and see where do we have that elbow for the F1 score。

 Wheres it， the maximum for the error rate， Where is it at its minimum。



![](img/c5a28d261316d48ae10768633c59d107_84.png)

So we just run this here and all we're doing is we're doing F1 results。



![](img/c5a28d261316d48ae10768633c59d107_86.png)

And we're setting our index decay。We're just setting this K as its index。 And when we run dot plot。

 it's just going to be each one of the different values so then we can just have our line plot across each one of our different values。



![](img/c5a28d261316d48ae10768633c59d107_88.png)

![](img/c5a28d261316d48ae10768633c59d107_89.png)

And we're setting the color equal， we have this colors palette that we brought in earlier。

 it's just going to be a specific color， as well as our figure size and just the width of our line。



![](img/c5a28d261316d48ae10768633c59d107_91.png)

![](img/c5a28d261316d48ae10768633c59d107_92.png)

And then we're just going to give it an X label and a Y label。

 set our ticks where we want each one of our ticks， and give it a title。

 and we're also going to save this figure so that we can have it for later。



![](img/c5a28d261316d48ae10768633c59d107_94.png)

![](img/c5a28d261316d48ae10768633c59d107_95.png)

So we run this and we can see that as we increase K。We start to get better and better F1 scores。

 and that somewhat plateaus around the 1920 mark over here。

 if you look at the 1920 on the tick marks。

![](img/c5a28d261316d48ae10768633c59d107_97.png)

And then we can do the same and just run it that same exact code。

 except now passing in the error results。

![](img/c5a28d261316d48ae10768633c59d107_99.png)

And we can see again， around the 21 mark is where we get those best results。

 and after that we start to get a higher and higher error rate。

And that's how we'd optimize and choose which K is best in regards to how well it's going to do on each one of the holdout sets。

That closes out our discussion on our lab on Can nearest neighborighs and I look forward to seeing you back in lecture。



![](img/c5a28d261316d48ae10768633c59d107_101.png)

![](img/c5a28d261316d48ae10768633c59d107_102.png)