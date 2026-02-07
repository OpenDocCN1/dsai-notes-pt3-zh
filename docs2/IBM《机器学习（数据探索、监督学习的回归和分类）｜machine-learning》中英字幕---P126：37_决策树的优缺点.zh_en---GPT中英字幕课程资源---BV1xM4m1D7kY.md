# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P126：37_决策树的优缺点.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So decision trees tend to have high variance， that is they tend to overfit。



![](img/f068b768ed49501cdf72692c51c6fcdc_1.png)

Now， since it doesn't make any strong assumptions such as linearly separable classes。

 it tends to find structures that explain the training set too well。

 so small changes in data end up greatly affecting the prediction。

 and the model doesn't end up generalizing outside of that set。



![](img/f068b768ed49501cdf72692c51c6fcdc_3.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_4.png)

So one solution is to impose a max depth to help prune our trees。

 and this allows for our tree to only make a certain amount of splits。



![](img/f068b768ed49501cdf72692c51c6fcdc_6.png)

So let's say we set our max depth equal to two。We would now have a prune tree that only has this depth of two。

 We see we cut off some leaf nodes。

![](img/f068b768ed49501cdf72692c51c6fcdc_8.png)

And we will now instead assign a predicted class to the majority class of that higher up node。



![](img/f068b768ed49501cdf72692c51c6fcdc_10.png)

But we can keep pruning， and it doesn't have to be defined by the depth of the tree。

 we don't have to say max depth equals to there's other ways to prune our tree。



![](img/f068b768ed49501cdf72692c51c6fcdc_12.png)

So there can be other criteria， such as a threshold of classification error。

 something like if this leaf is correctly classified。



![](img/f068b768ed49501cdf72692c51c6fcdc_14.png)

For 95% of its samples， then that is enough， we shouldn't do any further splitting。

Other types of pruning that we can do is we can also decide a certain threshold of information gain。

 so we need to get a certain amount of information gain to continue splitting。



![](img/f068b768ed49501cdf72692c51c6fcdc_16.png)

Or we can have a minimum amount of rows in a subset at which we're no longer allowing further splits。

 so you can imagine if it's down to three different nodes， three different rows in that node。

 we wouldn't want to do a further split into two leaf nodes of values of two and one and one and the other。

 We just say the majority class for that three， given that there's a minimum of three within each leaf。



![](img/f068b768ed49501cdf72692c51c6fcdc_18.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_19.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_20.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_21.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_22.png)

So some strengths of decision trees that we want to keep in mind here。

Is that since it's a sequence of questions and answers。

 it turns out that it will be very easy to interpret， as well as to visualize。

 assuming that we don't have too large a tree， too large a tree can get a bit more complex。

 But even for those， we can look at the roots where those larger decisions remained。



![](img/f068b768ed49501cdf72692c51c6fcdc_24.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_25.png)

And as mentioned earlier in business， interpretability of a solution is a huge advantage。

And with a decision tree， for example， if we go back to our customer churn example。

 if we had a customer that is the subset。 So again。

 we're subsetting our data subset that pays over a certain amount per month。



![](img/f068b768ed49501cdf72692c51c6fcdc_27.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_28.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_29.png)

And then within that subset， we find another subset that also uses a certain low amount of gigabytes from month given our threshold so they pay a lot。



![](img/f068b768ed49501cdf72692c51c6fcdc_31.png)

Given our thresholds， but they use very little gigabytes using our thresholds。

 maybe they are more likely to churn。 And that's easy to explain to a higher up or toever is helping you make this decision。



![](img/f068b768ed49501cdf72692c51c6fcdc_33.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_34.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_35.png)

Also， it's pretty easy to use it with various types of data。

The algorithm will fairly easily turn any of your features into binary features on its own。



![](img/f068b768ed49501cdf72692c51c6fcdc_37.png)

And then as opposed to the distance or linear based algorithms， there's no scaling required。



![](img/f068b768ed49501cdf72692c51c6fcdc_39.png)

Scaling would simply change the question at the nodes， but the ordering of those values。

 if we scaled them would remain the same， so it have no impact on creating those splits。



![](img/f068b768ed49501cdf72692c51c6fcdc_41.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_42.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_43.png)

So how do we do this in practice in SK learn as usual first we're going to import the class。

 so from SKlearn。tree， we import our decision tree classifier。



![](img/f068b768ed49501cdf72692c51c6fcdc_45.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_46.png)

We then create an instance of the class， so we set。

 we initiate that class decisionary classifier with his hyper parameters and set that equal to DC。



![](img/f068b768ed49501cdf72692c51c6fcdc_48.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_49.png)

And we have our different tree parameters here。 We have here some hyperparameters help regular this equation。

 We have that our first our splitting criterion is going to be genie。

 and we have the options of genie versus entropy。

![](img/f068b768ed49501cdf72692c51c6fcdc_51.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_52.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_53.png)

We can also set the max of features that we want to look at when we're doing our split。

 This allows for a little bit less of overfitting when it's not allowed to look at every single feature。

 it can only look at 10 features at a time every time it does a split。



![](img/f068b768ed49501cdf72692c51c6fcdc_55.png)

And then here you see that we also use the max depth of the tree equal to five so that we can't create a tree greater than five layers deep。



![](img/f068b768ed49501cdf72692c51c6fcdc_57.png)

We're then going to fit the instance on the data and then predict that expected value。

 So same as before we call that。

![](img/f068b768ed49501cdf72692c51c6fcdc_59.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_60.png)

Initiated model DTC， we call DTC。fit on our training data。

 and then we come up with our predictions on our holdoutet。



![](img/f068b768ed49501cdf72692c51c6fcdc_62.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_63.png)

And then as we've done with other algorithms， we want to tune those parameters using cross validation。

 And then also， if you want to do regression rather than decision tree classifier。

 you just have to use decision tree agressor。 and I'll have many of the same hyper parameters。

 The main difference is going to be that the outcome variable will be continuous rather than having certain classes。



![](img/f068b768ed49501cdf72692c51c6fcdc_65.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_66.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_67.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_68.png)

So to recap this section on decision trees， we went through a brief overview of classification problems。

 where the ones we looked at so far were either linear in logistic regression and support vector machines or took a lot of computational power to create a prediction with that came nearest neighbors algorithm。



![](img/f068b768ed49501cdf72692c51c6fcdc_70.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_71.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_72.png)

We then introduced the concept of the decision tree and how to use that for classification。



![](img/f068b768ed49501cdf72692c51c6fcdc_74.png)

We got an understanding of how we should split our decision tree using entropy and information gain to help us decide where our split should actually be。



![](img/f068b768ed49501cdf72692c51c6fcdc_76.png)

And finally， we discuss the importance of pruning decision trees to address overfitting since decision trees are very prone to overfitting。



![](img/f068b768ed49501cdf72692c51c6fcdc_78.png)

At this point， we'll now dive into our lab and gain a deeper understanding of using decision trees in practice。

 All right， I'll see you there。

![](img/f068b768ed49501cdf72692c51c6fcdc_80.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_81.png)

![](img/f068b768ed49501cdf72692c51c6fcdc_82.png)