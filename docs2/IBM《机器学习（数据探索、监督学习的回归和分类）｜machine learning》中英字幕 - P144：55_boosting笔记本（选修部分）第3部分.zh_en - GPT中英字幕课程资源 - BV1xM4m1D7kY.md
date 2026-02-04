# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P144：55_boosting笔记本（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_0.png)

Welcome back for question number six， I'm going to start quickly by running this code as it'll take a second to run。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_2.png)

But what we're doing here in question number six。Is we're going to fit a logistic regression with regularization。

 So we see here that we're using the L2 penalty。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_4.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_5.png)

We're then going to use our voting classifier to fit the logistic regression along with other different models that we you learned from before。

 something to note with the voting classifier， as well as the stacking classifier。

 which we mentioned in lecture。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_7.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_8.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_9.png)

When we use that in SKLarn， it will actually refit each of the models。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_11.png)

So if we're using something like a grid search， which we can actually pass into our voting classifier。

 it will take all the time it took for our original grid search to run。

 So be careful not to pass in two complex models， or if you do want to pass in complex models。

 just note that it'll take some time to run。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_13.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_14.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_15.png)

Then we're going to take the output from our voting classifier， determine the error as we did before。

 and then plot our confusion matrix as well。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_17.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_18.png)

So the first step is to create our logistic regression model。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_20.png)

As I had mentioned， this took a little bit long to run， something like 45 seconds a minute。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_22.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_23.png)

And we set our penalty to L2。 We just have our solver and our max iterations here。

 and we're going to talk more about gradient descent。

 but this is something along the lines of just finding that optimal solution step by step So it'll take a certain amount of iterations。

 a certain amount of steps to get to the proper solution to converge to that solution So we say that we need at least 500 iterations。

 And then we're going to fit that to our training set。 So our xtrain in our Y train。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_25.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_26.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_27.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_28.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_29.png)

Then we're going to see what our classification report was。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_31.png)

So first， we get our predictions from LRL2。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_33.png)

And we see that it did fairly well， not quite as well as our boosting， about 0。98 accuracy and 0。

98 across all of the averages macro and weighted。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_35.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_36.png)

We can look at the。Confusion matrix， in order to see where we got confused， and again。

 it's between classes one and two that are most likely to get confused。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_38.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_39.png)

And then what we're going to do here is we're going to combine two of our estimators and get that voting classifier in order to vote between the outputs of LRL2。

 as well as our GBC。 that's our original gradient boosted classifier that we learned with 400 different with 400 trees before we did our grid search。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_41.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_42.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_43.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_44.png)

And we're going to set boating here equal to soft。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_46.png)

So rather than hard， which would mean that we would output either one or0 according to the class that was predicted or going to output the probabilities and then average out the probabilities。

 So if G。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_48.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_49.png)

Predicted the class 1 with 70% certainty and。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_51.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_52.png)

LRL2 set a class zero with 100% certainty or0% certainty of class number one。

 then it would predict class zero because it has more weight towards that class。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_54.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_55.png)

We can then call Vc。fit on our training set and we'll run this。

 and this may take just a second to run as well as we have the LRL2 which took a while to run as well as the GBC which took a minute to run。

 so I'm going to pause it here and we'll come right back and then we'll see the outputs of each of these of our voting classifier when we get back。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_57.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_58.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_59.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_60.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_61.png)

So hopefully that only took about a minute or two for you to run。

 and we now have our VC our voting classifier fit on our training set。

 and we do want to note here that we are running this voting classifier and it should do better than either the gradient boosted classifier or the logistic regression that we had before or at least as well。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_63.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_64.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_65.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_66.png)

But what we always want to make sure of， especially once we get more and more complex。

 we can add on the stacking classifier or a more complex voting classifier。

 The first thing that we're going to want to do is first establish how well。

 how accurate do we need to be， Maybe we need to be 100% accurate。

 So we need to keep honing in to make sure that we get every single class correct。

 But if we don't need to be that accurate， We don't want to be spending mountains and mountains of time。

 trying to get that extra percentage in accuracy。 So be careful to first check that very simple model。

 see how well that performs and perhaps you're already done with your job there。

 and that should apply across any business decision you're making using data science。😊。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_68.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_69.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_70.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_71.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_72.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_73.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_74.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_75.png)

So we can get our prediction by calling Vc。predict as we do with any of our different models。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_77.png)

And then we can check our classification report， we see that we're back up to 0。99。

 essentially as good as the GC now that we're combining these two together。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_79.png)

And then， we can also。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_81.png)

Look at our confusion matrix and we see that we are doing even better in regards to classifying those once and twos correctly。



![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_83.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_84.png)

So that closes out our lab here on boosting and stacking and we get back to lecture。

 we will talk about working even more heavily with unbalanced classes and different solutions for that。

 All right， I'll see you there。

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_86.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_87.png)

![](img/1bb42b7c7aa21aa1da89f7ddcd9789fb_88.png)