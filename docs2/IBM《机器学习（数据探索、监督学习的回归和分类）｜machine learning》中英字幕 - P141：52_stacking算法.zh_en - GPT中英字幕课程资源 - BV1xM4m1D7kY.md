# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P141：52_stacking算法.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Finally， let's discuss one last ensemble method， namely stacking。



![](img/10a175b3e613e881653c8cfca09f4450_1.png)

Here our base learners can be anything。Here we see we have logistic regression。

 support vector machines and random forest as each of our base learners。

 So there's no bias here towards needing to use a decision tree。



![](img/10a175b3e613e881653c8cfca09f4450_3.png)

![](img/10a175b3e613e881653c8cfca09f4450_4.png)

We can even pass in as we see here， that random force， which is an ensemble method in itself。

The idea is to fit several algorithms to our training set and use their predictions or their scores of each of these individual based learners as a new training set。

 These become our meta featuresature， each one of the outputs of each of these base learners。

 and then we pass those through to one final classifier called our metaclassifier to come up with a single prediction。



![](img/10a175b3e613e881653c8cfca09f4450_6.png)

![](img/10a175b3e613e881653c8cfca09f4450_7.png)

![](img/10a175b3e613e881653c8cfca09f4450_8.png)

![](img/10a175b3e613e881653c8cfca09f4450_9.png)

![](img/10a175b3e613e881653c8cfca09f4450_10.png)

And you can think about this last step， this aggregation step。

 similar to what we've done with our other ensemble methods in regards to bringing together all the different votes。



![](img/10a175b3e613e881653c8cfca09f4450_12.png)

![](img/10a175b3e613e881653c8cfca09f4450_13.png)

Now， in a way， this is very similar to bagging， but without the need to bootstrap or to limit to decision trees。



![](img/10a175b3e613e881653c8cfca09f4450_15.png)

And instead we trained several different algorithms。



![](img/10a175b3e613e881653c8cfca09f4450_17.png)

And we can think of this as testing many different assumptions on our data set。

 so we're not held to just the assumptions needed for decision trees or any other model。



![](img/10a175b3e613e881653c8cfca09f4450_19.png)

![](img/10a175b3e613e881653c8cfca09f4450_20.png)

And the output of those algorithms are， again， are new features。



![](img/10a175b3e613e881653c8cfca09f4450_22.png)

To be fed into that final aggregation task。Into that final classifier。

 so we see we go from our labeled data。

![](img/10a175b3e613e881653c8cfca09f4450_24.png)

Run it through our logistic regression， we come up with our meta features and then we can use those meta features as input to either a voting class or one final classification method。



![](img/10a175b3e613e881653c8cfca09f4450_26.png)

![](img/10a175b3e613e881653c8cfca09f4450_27.png)

![](img/10a175b3e613e881653c8cfca09f4450_28.png)

So what would this final metaclassifier look like？

![](img/10a175b3e613e881653c8cfca09f4450_30.png)

One option is we can do a majority vote， as we discussed or await weighted vote。

 as we did with our other ensemble methods。

![](img/10a175b3e613e881653c8cfca09f4450_32.png)

Now we want to note that in order to optimize the meta step parameters so to optimize each of the parameters for our base learners。

 we need to be careful and scientific about our approach。



![](img/10a175b3e613e881653c8cfca09f4450_34.png)

![](img/10a175b3e613e881653c8cfca09f4450_35.png)

![](img/10a175b3e613e881653c8cfca09f4450_36.png)

What do I mean by that， I mean that we need a holdout and a test set for our base learners as well。



![](img/10a175b3e613e881653c8cfca09f4450_38.png)

We can't just have a hold out for our final classification method。

 but in order to properly learn the parameters for each of our base learners。

 we need to ensure we have a hold out for those as well。



![](img/10a175b3e613e881653c8cfca09f4450_40.png)

![](img/10a175b3e613e881653c8cfca09f4450_41.png)

And with that， we want to be aware that such models can get pretty complex pretty quickly。



![](img/10a175b3e613e881653c8cfca09f4450_43.png)

And as usual higher complexity generally means that we are more likely to overfit。

 so we want to be aware of this and be sure that whatever is done is going to generalize well outside the data。

 so again we need to ensure that we have the proper holdout sets。



![](img/10a175b3e613e881653c8cfca09f4450_45.png)

![](img/10a175b3e613e881653c8cfca09f4450_46.png)

![](img/10a175b3e613e881653c8cfca09f4450_47.png)

And finally， as we hinted at， that final metaclassifier does not necessarily need to just be a vote or a weighted vote。

 but it can even be its own model。

![](img/10a175b3e613e881653c8cfca09f4450_49.png)

![](img/10a175b3e613e881653c8cfca09f4450_50.png)

We could run a linear regression at that last step or logistic regression support vector machines or random force using the output of each of these base learners as the input into that final learner。



![](img/10a175b3e613e881653c8cfca09f4450_52.png)

![](img/10a175b3e613e881653c8cfca09f4450_53.png)

![](img/10a175b3e613e881653c8cfca09f4450_54.png)

So how do we do this in practice？

![](img/10a175b3e613e881653c8cfca09f4450_56.png)

First， as usual， we want to import our class containing our classification method here being the voting classifier。



![](img/10a175b3e613e881653c8cfca09f4450_58.png)

We're then going to create an instance of our class and pass in our hyperparameter。



![](img/10a175b3e613e881653c8cfca09f4450_60.png)

We see here this estimator list， that should be an actual list of fitted models。

 so we should have already learned all of our different hyperparameter as well as all of our different parameters on a certain training set to come up with our different models。

 that logistic regression， the random force and so on that we're going to combine using this voting classifier。



![](img/10a175b3e613e881653c8cfca09f4450_62.png)

![](img/10a175b3e613e881653c8cfca09f4450_63.png)

![](img/10a175b3e613e881653c8cfca09f4450_64.png)

![](img/10a175b3e613e881653c8cfca09f4450_65.png)

![](img/10a175b3e613e881653c8cfca09f4450_66.png)

Another thing to note， another hyper parameterameter that's available is going to be。

 how do you want to vote？

![](img/10a175b3e613e881653c8cfca09f4450_68.png)

Now， so far， we've discussed voting as hard voting。

 which is just taking whatever the output of the classes。

 So if we have random force us and we have logistic regression and those both predicts one than we would vote one rather than just taking ones or zeroes。

 we can also output probabilities for many of these models。



![](img/10a175b3e613e881653c8cfca09f4450_70.png)

![](img/10a175b3e613e881653c8cfca09f4450_71.png)

![](img/10a175b3e613e881653c8cfca09f4450_72.png)

And if we do that， rather than just taking a vote， we can take the average of each of those probabilities。

 and that would be called soft voting。

![](img/10a175b3e613e881653c8cfca09f4450_74.png)

And then if we have a certain model that's very certain that it should be either 0 or one class。

 we allow that to have more weight。 So that's going to be the soft voting。

 And the way that we pass that in that hyperpar called voting， and we can either pass soft or hard。

 and we'll see that in our notebook， we're actually going to use soft voting。



![](img/10a175b3e613e881653c8cfca09f4450_76.png)

![](img/10a175b3e613e881653c8cfca09f4450_77.png)

![](img/10a175b3e613e881653c8cfca09f4450_78.png)

![](img/10a175b3e613e881653c8cfca09f4450_79.png)

We're then going to fit the instance as we've done before。

 so all we have to do is called VC do fit on our training set and then predict on our test set。



![](img/10a175b3e613e881653c8cfca09f4450_81.png)

![](img/10a175b3e613e881653c8cfca09f4450_82.png)

And then as usual there's a regression option， all we have to do is use voting agressor if we want to use regression。



![](img/10a175b3e613e881653c8cfca09f4450_84.png)

And then another important note is that the stacking classifier。

 which is actually somewhat newer to SK learn， will work similarly。

 but will allow us to have a different final classifier besides voting in order to come up with that final prediction。



![](img/10a175b3e613e881653c8cfca09f4450_86.png)

![](img/10a175b3e613e881653c8cfca09f4450_87.png)

![](img/10a175b3e613e881653c8cfca09f4450_88.png)

So in order to do that， we pass in our estimator list and as you see here。

 we also pass in that hyperpremeter the final estimator。

 and by default it's actually logistic regression， but you can pass in any type of model without any fit in order to come up in order to decide how we're going to end up coming up with that final prediction。



![](img/10a175b3e613e881653c8cfca09f4450_90.png)

![](img/10a175b3e613e881653c8cfca09f4450_91.png)

Now let's recap what we learned here in this section。



![](img/10a175b3e613e881653c8cfca09f4450_93.png)

In this section， we discussed the boosting approach to combining models。

 with the main idea with boosting being to build off of prior mistakes of our weak learners。



![](img/10a175b3e613e881653c8cfca09f4450_95.png)

![](img/10a175b3e613e881653c8cfca09f4450_96.png)

We then discuss the types of boosting models， namely gradient boosting and adddibu。

 and how addbu was one of the first boosting methods used， but can be easily skewed by outliers。



![](img/10a175b3e613e881653c8cfca09f4450_98.png)

![](img/10a175b3e613e881653c8cfca09f4450_99.png)

And this became clear when we looked at the different loss functions used for each of the boosting methods。



![](img/10a175b3e613e881653c8cfca09f4450_101.png)

And finally， we showed how we can combine heterogeneous classifiers using our stacking method。

 which took many different classifier outputs。

![](img/10a175b3e613e881653c8cfca09f4450_103.png)

![](img/10a175b3e613e881653c8cfca09f4450_104.png)

And aggregated them by using them as input to one final classification method。



![](img/10a175b3e613e881653c8cfca09f4450_106.png)

Some can get a note in regards to further reading。

![](img/10a175b3e613e881653c8cfca09f4450_108.png)

XG boostts is another popular boosting algorithm that's not insyit learned。

 but has its own library and for more information， I would say read the documents that we have here。

 and it's going to be essentially gradient boosting but with a bit of parallelization which will allow you to speed up how fast you're able to fit your model and as we'll see in the notebook which is going to be our next video that may take a very long time so it may be worth looking into XG boost as well。



![](img/10a175b3e613e881653c8cfca09f4450_110.png)

![](img/10a175b3e613e881653c8cfca09f4450_111.png)

![](img/10a175b3e613e881653c8cfca09f4450_112.png)

All right， with that， we'll move into our notebook， I'll see you there。



![](img/10a175b3e613e881653c8cfca09f4450_114.png)

![](img/10a175b3e613e881653c8cfca09f4450_115.png)