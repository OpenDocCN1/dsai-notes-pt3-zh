# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P46：-046-Statistical Learning_ 6.R.3 Model Selection and Cross-Validation.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/7fea33d677987254ee64fc1e2ed231db_0.png)

Okay， wellll we back again， we in our session on model selection。We've seen best subsets regression。

 forward stepwise regression， and we've seen how to use a validation set to do model selection。

 as well as using the built in CP statistic that's recorded by rig subsets。

Now we're going to use cross validation， which is one of our preferred methods for doing a model selection。

 and we'll use tenfold cross validation。And once again。

 we're using our our markdown session so we can record text and the R commands at the same time。

 and at the end of it all we'll be able to produce a nice document showing what we've done。

So let's look at the the script and， and see how we do this。Okay， so theses our our markdown code。

 This is a second level heading。 So model selection by cross validation。 And as I said。

 we're going to use ten0fold cross validation。

![](img/7fea33d677987254ee64fc1e2ed231db_2.png)

![](img/7fea33d677987254ee64fc1e2ed231db_3.png)

And it's really easy。 And， you know。

![](img/7fea33d677987254ee64fc1e2ed231db_5.png)

Pep， you， you can write functions for doing this， but it's so easy to do that it's actually good just to know how to do it on the fly。



![](img/7fea33d677987254ee64fc1e2ed231db_7.png)

![](img/7fea33d677987254ee64fc1e2ed231db_8.png)

So we'll set a random number Cd just like we did before， we'll use a different one this time。

 so we'll set the seed to be 11。

![](img/7fea33d677987254ee64fc1e2ed231db_10.png)

And so。You we going to sample from the numbers1 to 10。



![](img/7fea33d677987254ee64fc1e2ed231db_12.png)

Each observation is going to be assigned a fold number in the  ten folds。



![](img/7fea33d677987254ee64fc1e2ed231db_14.png)

So。

![](img/7fea33d677987254ee64fc1e2ed231db_16.png)

We're going to sample from the numbers 1 to 10， so we create a vector 1 to 10 of length the number of rows of hitters。



![](img/7fea33d677987254ee64fc1e2ed231db_18.png)

Okay。So that'll try and make an equal number of ones。

 the equal number of twos up to equal number of tens。



![](img/7fea33d677987254ee64fc1e2ed231db_20.png)

![](img/7fea33d677987254ee64fc1e2ed231db_21.png)

And then we're going to random basically shuffle that。 And that's what the sample command does， yeah。



![](img/7fea33d677987254ee64fc1e2ed231db_23.png)

， so we do that。 and then if we look at it。

![](img/7fea33d677987254ee64fc1e2ed231db_25.png)

Theres our random assignment of folds to each of the observations in hitters。



![](img/7fea33d677987254ee64fc1e2ed231db_27.png)

And if we tabulate that， these are just numbers between1 and 10。



![](img/7fea33d677987254ee64fc1e2ed231db_29.png)

You'll see， it's pretty balanced。Couldn't be exactly balanced with a sample size of 2，63。

 but as close as can be。 So there either。

![](img/7fea33d677987254ee64fc1e2ed231db_31.png)

![](img/7fea33d677987254ee64fc1e2ed231db_32.png)

26 or 27 in in each fold。In each fold。

![](img/7fea33d677987254ee64fc1e2ed231db_34.png)

Okay， so we make now a matrix for our errors and it's going to have 10 rows and 19 columns because they're 19 variables。

 are they going to be 19 subsets。

![](img/7fea33d677987254ee64fc1e2ed231db_36.png)

![](img/7fea33d677987254ee64fc1e2ed231db_37.png)

And 10 rows for each of the ten folds。

![](img/7fea33d677987254ee64fc1e2ed231db_39.png)

And so now we're going to go through a double loop。And so we go for k equals 1 in 10。



![](img/7fea33d677987254ee64fc1e2ed231db_41.png)

And now we fit a rig subsets model。

![](img/7fea33d677987254ee64fc1e2ed231db_43.png)

With salary is a response。

![](img/7fea33d677987254ee64fc1e2ed231db_45.png)

And the training data is going to be all the observations whose fold I is not equal to K。



![](img/7fea33d677987254ee64fc1e2ed231db_47.png)

For the this ca fold， we're gonna train on all the observations。 but those in the ca fold， okay。



![](img/7fea33d677987254ee64fc1e2ed231db_49.png)

![](img/7fea33d677987254ee64fc1e2ed231db_50.png)

So。Having done that， we only need to do that once。 and now we're going to go and look at each of the subsets in in that trained model。

 So now we go through our loop for i equals 1 to 19。



![](img/7fea33d677987254ee64fc1e2ed231db_52.png)

![](img/7fea33d677987254ee64fc1e2ed231db_53.png)

And now we can use our predict method that we just made and when I say predict method Im in it because we wrote our predict function in a way that the generic predict understands。

 and so we just call predict and the first argument is best on foot which is a re subset object and so the generic function predict knows to find the method which was called predict reg subsets。



![](img/7fea33d677987254ee64fc1e2ed231db_55.png)

![](img/7fea33d677987254ee64fc1e2ed231db_56.png)

![](img/7fea33d677987254ee64fc1e2ed231db_57.png)

![](img/7fea33d677987254ee64fc1e2ed231db_58.png)

![](img/7fea33d677987254ee64fc1e2ed231db_59.png)

And now we're going to make predictions at those observations whose folds fold I is equal to K。

 right？ So those were the guys that were left out。

![](img/7fea33d677987254ee64fc1e2ed231db_61.png)

![](img/7fea33d677987254ee64fc1e2ed231db_62.png)

![](img/7fea33d677987254ee64fc1e2ed231db_63.png)

And we doing it for each subset size M I。

![](img/7fea33d677987254ee64fc1e2ed231db_65.png)

Which is given to our predict function by I D。So we make our predictions and then we compute the mean squared error of the predictions and assign that into the krow of our CV errors。



![](img/7fea33d677987254ee64fc1e2ed231db_67.png)

![](img/7fea33d677987254ee64fc1e2ed231db_68.png)

And we do that for， for all the I and for O K。 And that's done already。 Well， actually， it's not。



![](img/7fea33d677987254ee64fc1e2ed231db_70.png)

![](img/7fea33d677987254ee64fc1e2ed231db_71.png)

Now it's done。So that was pretty quick that was in 19。 No， it was fit in 10 models。

 so it's not so bad but making predictions for 19 different sub models of each。



![](img/7fea33d677987254ee64fc1e2ed231db_73.png)

![](img/7fea33d677987254ee64fc1e2ed231db_74.png)

![](img/7fea33d677987254ee64fc1e2ed231db_75.png)

嗯。We now process our output matrix。 So， first of all。



![](img/7fea33d677987254ee64fc1e2ed231db_77.png)

We use the apply function to the columns。 So we take the column means。



![](img/7fea33d677987254ee64fc1e2ed231db_79.png)

RightBecause there were 10 rows and each row was the the mean squared error for a particular fold。

 But we want to average those。 So we average down the columns。

 and then we use square root to get the root mean squared error。



![](img/7fea33d677987254ee64fc1e2ed231db_81.png)

![](img/7fea33d677987254ee64fc1e2ed231db_82.png)

![](img/7fea33d677987254ee64fc1e2ed231db_83.png)

And now we can make a plot of that。And so there's our tenfold cross validation curve。

It's not quite as jumpy as the validation curve because this is averaged over the full training set。

 the errors are computed over the full training set。



![](img/7fea33d677987254ee64fc1e2ed231db_85.png)

![](img/7fea33d677987254ee64fc1e2ed231db_86.png)

But， of course， in done fold by fold， but then averaged。 So it's a little bit smoother。

 And this seems to favor models of size 11 or 12。

![](img/7fea33d677987254ee64fc1e2ed231db_88.png)

![](img/7fea33d677987254ee64fc1e2ed231db_89.png)