# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P128：39_决策树笔记本（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

All right， welcome back for questiontion 3 here， where we will be fitting our first decision tree classifier here we are doing so with no set limits on our maximum depth。

 our features or our leaves。😊，And then after that， we want to determine how many nodes are present and what's the depth of this now very large tree since we're not setting any maximum depth。

 putting any pruning features， etc。And then using this tree。

 we want to measure the prediction error in the train and our test data sets。

 And we want to think if we allow for no pruning， what do you think is going to happen based on。



![](img/273e043cc228cc62d68db0f56c458552_1.png)

![](img/273e043cc228cc62d68db0f56c458552_2.png)

Us fitting such a deep tree on the differences in our predictionctionary between our test and our train set。

So the first thing that we're going to do is import our decision tree classifier， we set Dt。

 we initiate our class equal to decision tree classifier random state here equal to 42。

 there is a bit of randomness when you're creating a decision tree classifier。

 the reason being that if two different splits have the same，Information gain。

 it'll be random which one it ends up choosing， and then we call DT dot fit on our Xtrain and our Y train。

So now we have a fit model。And in order， and again， this is without any pruning。

 this is just max step is none， so on and so forth。When we want to see the number of nodes。

 we can call DT dot tree， which is now going to be an attribute of our decision tree of our classifier that we initiated。



![](img/273e043cc228cc62d68db0f56c458552_4.png)

![](img/273e043cc228cc62d68db0f56c458552_5.png)

And that attribute。

![](img/273e043cc228cc62d68db0f56c458552_7.png)

So you see， we call that twice， we'll have available both the node count as well as the max depth。



![](img/273e043cc228cc62d68db0f56c458552_9.png)

So you run this and we see that there are 171 nodes present in our full decision tree。

And that it goes 22 levels deep right， so we recall lecture at each split we add on another level。



![](img/273e043cc228cc62d68db0f56c458552_11.png)

Now we're going to create a function to return different error metrics， the accuracy score。

 the precision score， the recall score， as well as the F1 score。



![](img/273e043cc228cc62d68db0f56c458552_13.png)

So all we do is we're going to create this function where we pass in Y true and Y pre。

As well as the label here being。

![](img/273e043cc228cc62d68db0f56c458552_15.png)

If we look back down over here when we call it。

![](img/273e043cc228cc62d68db0f56c458552_17.png)

Being either the test or the train set。So I'm just going to add on that label。



![](img/273e043cc228cc62d68db0f56c458552_19.png)

We set accuracy and now we're using a panda series so the index is going to be accuracy for。

 and then we're just going to call the accuracy score for y true and y pre。

 then for precision we call the precision score for the same values。

 the recall score and the F1 score。

![](img/273e043cc228cc62d68db0f56c458552_21.png)

So each one of these will have the indices that we have here to the left， which are our keys。

 and then the column name is just going to be our label， one we call that measure error。



![](img/273e043cc228cc62d68db0f56c458552_23.png)

On our actual data。

![](img/273e043cc228cc62d68db0f56c458552_25.png)

We then are going to actually create our Ytrain prediction by calling DT。

 which is fitted on our training set and calling DT。predt Xtrain。

 so now we have the predictions for the training set。

 and then we call DT do predictdt on our X test so that we have our predictions for our test set。



![](img/273e043cc228cc62d68db0f56c458552_27.png)

We're then going to take each of these。And get their measure error。

 So we're using that mesh error function that we just defined。Passing in why train and why train pre。

 So why train of actual values。 why train pre are our predictions。 This is going to be our label。

 It's going to be our training set， and then we call measure error for our test set as well。

And then we cancatenate these two together and we're saying we're catnating across the columns。



![](img/273e043cc228cc62d68db0f56c458552_29.png)

And when we run this。

![](img/273e043cc228cc62d68db0f56c458552_31.png)

We can see our accuracy for both the train and test set。

 our precision for both the train and test set recall and F1 score。

 and we see this incredibly high recall， most of these values are already fairly high。

 but we see how incredibly well we're doing on our training set because we allowed it to completely overfit to our training set and that's what would be expected when you don't have when you train and test on the same set。



![](img/273e043cc228cc62d68db0f56c458552_33.png)

![](img/273e043cc228cc62d68db0f56c458552_34.png)

And thats this gap between the train and test errors generally indicate that you may have overfit slightly。



![](img/273e043cc228cc62d68db0f56c458552_36.png)

![](img/273e043cc228cc62d68db0f56c458552_37.png)

So here in question four。What we're asked to do is use gridd search with cross validation and find a decision tree that performs well on the test set。

So now we want to ensure that we're doing well on a test set rather than just letting it not prune at all and have that maximum depth。



![](img/273e043cc228cc62d68db0f56c458552_39.png)

So we're going to use a different variable name for this decision tree so that we'll be able to differentiate between the two。



![](img/273e043cc228cc62d68db0f56c458552_41.png)

![](img/273e043cc228cc62d68db0f56c458552_42.png)

And we will again want to determine for this optimal decision tree。

 the number of nodes and the depth of this tree， as well as coming up with all the measure errors that we just saw for the train and test set that we defined using that function above。



![](img/273e043cc228cc62d68db0f56c458552_44.png)

![](img/273e043cc228cc62d68db0f56c458552_45.png)

So here we're going to import grid search CV to allow us to search through each one of these different hyperparmeters that we may want to search through。

We're going to use our parameter grid。And that's just going to be passed into our grid search and it's going to be a dictionary where the keys are going to be different hyperparameter that are available in our function。

 so these are available in our decision tree classifier。



![](img/273e043cc228cc62d68db0f56c458552_47.png)

![](img/273e043cc228cc62d68db0f56c458552_48.png)

![](img/273e043cc228cc62d68db0f56c458552_49.png)

So if we were to go into our decision tree classifier。



![](img/273e043cc228cc62d68db0f56c458552_51.png)

We'd see that we have something called max depth as one of the hyperparameter。

 and we have something called。

![](img/273e043cc228cc62d68db0f56c458552_53.png)

Max features here has one of the parameters as well， hyperparameters。



![](img/273e043cc228cc62d68db0f56c458552_55.png)

So we have to make sure that those names match up。 We pass in a list of values。

 So here it's going to be a range of one through the max depth that we just calculated。

Plus one so that we're able to include the last one counting by two。

 And then this is also going to be using the decision tree we just classified and the number of features that we can use are going to be up to the number of features that were used there。

 General， this is going to be all the features if we didn't prune at all。



![](img/273e043cc228cc62d68db0f56c458552_57.png)

We then set our grid search object。 We call it G R。 We pass in as our model。

 the decision tree classifier， the only thing that we're initiating is the random state。

 I remove this comma that I just put in。 the parameters grids of the different parameters that we're going to search through are going to be equal to that dictionary that we defined up here。



![](img/273e043cc228cc62d68db0f56c458552_59.png)

![](img/273e043cc228cc62d68db0f56c458552_60.png)

![](img/273e043cc228cc62d68db0f56c458552_61.png)

We want to optimize on accuracy here， we can choose different scoring on which we want to optimize end jobs equals negative one is just saying how much do you want to parallelze this process。

 negative one just means as much as possible。

![](img/273e043cc228cc62d68db0f56c458552_63.png)

![](img/273e043cc228cc62d68db0f56c458552_64.png)

![](img/273e043cc228cc62d68db0f56c458552_65.png)

Once we have our grid search CV， we're then going to fit it on our X train and Y train。

 it'll take just a second as it runs through each one of these different max steps and max features。



![](img/273e043cc228cc62d68db0f56c458552_67.png)

![](img/273e043cc228cc62d68db0f56c458552_68.png)

And once we do that， we have our best estimator， which we're going to call here， dot best estimator。

 which will be essentially the same as the object that we had before in terms of it being fit。

 except now with the optimal values for each one of our hyperparameters。



![](img/273e043cc228cc62d68db0f56c458552_70.png)

And then we can see what the tree is and from there， what the note count is。

 as well as the max depth。

![](img/273e043cc228cc62d68db0f56c458552_72.png)

So we see now that we use 99。

![](img/273e043cc228cc62d68db0f56c458552_74.png)

Rather than the 171 nodes， and our depth is now 7 rather than 22。 So we have a much smaller tree。



![](img/273e043cc228cc62d68db0f56c458552_76.png)

![](img/273e043cc228cc62d68db0f56c458552_77.png)

Then we're going to use the same steps in order to come up with our predictions for both our train and test set。

 so we call GR dot predict on our X train GR dot predict on our X test and then pass that into。



![](img/273e043cc228cc62d68db0f56c458552_79.png)

![](img/273e043cc228cc62d68db0f56c458552_80.png)

What we pass in here with the concatenated Pada series that are the output for both the measure errors that we call on our Y train。

 as well as the measure errors that we call on our Y test。



![](img/273e043cc228cc62d68db0f56c458552_82.png)

![](img/273e043cc228cc62d68db0f56c458552_83.png)

![](img/273e043cc228cc62d68db0f56c458552_84.png)

So you run this and we can look at the solution and we see that the training set did a bit worse。

 but across most of them， I think for accuracy maybe not as much。

 but for most of them we see an improvement improvement， an improvement in precision。

 I believe it's the same for recall and an improvement in our F1 score。



![](img/273e043cc228cc62d68db0f56c458552_86.png)

So that closes out question number four， when we come back， we will go into question number five。

 where we'll perform decision tree regression in order to predict residual sugar rather than a classification problem。



![](img/273e043cc228cc62d68db0f56c458552_88.png)

All right， I'll see you there。

![](img/273e043cc228cc62d68db0f56c458552_90.png)

![](img/273e043cc228cc62d68db0f56c458552_91.png)