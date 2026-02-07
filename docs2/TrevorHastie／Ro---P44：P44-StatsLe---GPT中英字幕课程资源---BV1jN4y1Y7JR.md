# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P44：P44 StatsLearning Lect10 R modelselection C 111213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/cab5e093444de73369d5851ac0399ae1_0.png)

Okay， wellll we back again， we in our session on model selection。We've seen best regression。

 forward stepwise regression， and we've seen how to use a validation set to do model selection。

 as well as using the built in CP statistic that's recorded by RE subsets。

Now we're going to use cross validation， which is one of our preferred methods for doing a model selection。

 and we'll use tenfold cross validation。And once again。

 we're using our our markdown session so we can record text and the R commands at the same time。

 and at the end of it all we'll be able to produce a nice document showing what we've done。

So let's look at the script and see how we do this。Okay， so theses our our markdown code。

 This is a second level heading， so model selection by cross validation。 and as I said。

 we're going to use ten0fold cross validation。

![](img/cab5e093444de73369d5851ac0399ae1_2.png)

![](img/cab5e093444de73369d5851ac0399ae1_3.png)

And it's really easy。 And， you know。

![](img/cab5e093444de73369d5851ac0399ae1_5.png)

know， you can write functions for doing this， but it's so easy to do that it's actually good just to know how to do it on the fly。



![](img/cab5e093444de73369d5851ac0399ae1_7.png)

![](img/cab5e093444de73369d5851ac0399ae1_8.png)

So we'll set a random number Cd just like we did before， we'll use a different one this time。

 so we'll set the Cd to be 11。

![](img/cab5e093444de73369d5851ac0399ae1_10.png)

And so。

![](img/cab5e093444de73369d5851ac0399ae1_12.png)

Yeah we're going to sample from the numbers one to 10。

Each observation is going to be assigned a fold number in the  ten folds。



![](img/cab5e093444de73369d5851ac0399ae1_14.png)

So。

![](img/cab5e093444de73369d5851ac0399ae1_16.png)

We're going to sample from the numbers 1 to 10， so we create a vector 1 to 10 of length the number of rows of hitters。



![](img/cab5e093444de73369d5851ac0399ae1_18.png)

Okay。So that'll try and make an equal number of ones。

 the equal number of twos up to equal number of tens。



![](img/cab5e093444de73369d5851ac0399ae1_20.png)

![](img/cab5e093444de73369d5851ac0399ae1_21.png)

And， and then we're going to random basically shuffle that。 And that's what the sample command does。

 yeah。

![](img/cab5e093444de73369d5851ac0399ae1_23.png)

Okay， so we do that。 And then if we look at it。

![](img/cab5e093444de73369d5851ac0399ae1_25.png)

There is our random assignment of folds to each of the observations in hitters。



![](img/cab5e093444de73369d5851ac0399ae1_27.png)

And if we tabulate that， these are just numbers between1 and 10。



![](img/cab5e093444de73369d5851ac0399ae1_29.png)

You'll see， it's pretty balanced。Couldn't be exactly balanced with a sample size of 2，63。

 but as close as can be。 So there either。

![](img/cab5e093444de73369d5851ac0399ae1_31.png)

![](img/cab5e093444de73369d5851ac0399ae1_32.png)

26 or 27 in in each fold。In each fold。

![](img/cab5e093444de73369d5851ac0399ae1_34.png)

Okay， so we make now a matrix for our errors and it's going to have 10 rows and 19 columns because they're 19 variables。

 are they going to be 19 subsets。

![](img/cab5e093444de73369d5851ac0399ae1_36.png)

![](img/cab5e093444de73369d5851ac0399ae1_37.png)

And 10 rows for each of the ten folds。

![](img/cab5e093444de73369d5851ac0399ae1_39.png)

And so now we're going to go through a double loop。And so we go for k equals1 in 10。



![](img/cab5e093444de73369d5851ac0399ae1_41.png)

And now we fit a rig subset model。

![](img/cab5e093444de73369d5851ac0399ae1_43.png)

With salary is a response。

![](img/cab5e093444de73369d5851ac0399ae1_45.png)

And the training data is going to be all the observations whose fold ID is not equal to K。



![](img/cab5e093444de73369d5851ac0399ae1_47.png)

![](img/cab5e093444de73369d5851ac0399ae1_48.png)

For this ca fold， we're going to train on all the observations but those in the ca fold okay。



![](img/cab5e093444de73369d5851ac0399ae1_50.png)

So。Having done that， we only need to do that once and now we're going to go and look at each of the subsets in that trained model。

 so now we go through our loop for i equals 1 to 19。



![](img/cab5e093444de73369d5851ac0399ae1_52.png)

![](img/cab5e093444de73369d5851ac0399ae1_53.png)

And now we can use our predict method that we just made and when I say predict method Im in it because we wrote our predict function in a way that the generic predict understands。

 and so we just call predictic and the first argument is best on foot which is a re subset object and so the generic function predict knows to find the method which was called predict do reg subsets。



![](img/cab5e093444de73369d5851ac0399ae1_55.png)

![](img/cab5e093444de73369d5851ac0399ae1_56.png)

![](img/cab5e093444de73369d5851ac0399ae1_57.png)

![](img/cab5e093444de73369d5851ac0399ae1_58.png)

![](img/cab5e093444de73369d5851ac0399ae1_59.png)

![](img/cab5e093444de73369d5851ac0399ae1_60.png)

And now we're going to make predictions at those observations whose fold I is equal to K right So those were the guys that were left out。



![](img/cab5e093444de73369d5851ac0399ae1_62.png)

![](img/cab5e093444de73369d5851ac0399ae1_63.png)

And we doing it for each subset size A am I。

![](img/cab5e093444de73369d5851ac0399ae1_65.png)

Which is given to our predict function by I D。So we make our predictions and then we compute the mean squared error of the predictions and assign that into the krow of our CV errors。



![](img/cab5e093444de73369d5851ac0399ae1_67.png)

![](img/cab5e093444de73369d5851ac0399ae1_68.png)

And we do that for， for all the I and for O K。 And that's done already。 Well， actually， it's not。



![](img/cab5e093444de73369d5851ac0399ae1_70.png)

![](img/cab5e093444de73369d5851ac0399ae1_71.png)

Now it's done。So that was pretty quick that was in 19。 No it was put in 10 models。

 so it's not so bad but making predictions for 19 different sub models of each。



![](img/cab5e093444de73369d5851ac0399ae1_73.png)

![](img/cab5e093444de73369d5851ac0399ae1_74.png)

![](img/cab5e093444de73369d5851ac0399ae1_75.png)

We now process our output matrix so first of all。

![](img/cab5e093444de73369d5851ac0399ae1_77.png)

We use the apply function to the columns。 So we take the column means。



![](img/cab5e093444de73369d5851ac0399ae1_79.png)

Because there were 10 rows and each row was the mean squared error for a particular fold。

 but we want to average those so we average down the columns and then we use square root to get the root mean squared error。



![](img/cab5e093444de73369d5851ac0399ae1_81.png)

![](img/cab5e093444de73369d5851ac0399ae1_82.png)

![](img/cab5e093444de73369d5851ac0399ae1_83.png)

And now we can make a plot of that。And so there's our tenfold cross validation curve。



![](img/cab5e093444de73369d5851ac0399ae1_85.png)

It's not quite as jumpy as the validation curve because this is averaged over the full training set。

 the errors are computed over the full training set。



![](img/cab5e093444de73369d5851ac0399ae1_87.png)

![](img/cab5e093444de73369d5851ac0399ae1_88.png)

But， of course， in done fold by fold， but then averaged。 So it's a little bit smoother。

 And this seems to favor models of size 11 or 12。

![](img/cab5e093444de73369d5851ac0399ae1_90.png)

![](img/cab5e093444de73369d5851ac0399ae1_91.png)