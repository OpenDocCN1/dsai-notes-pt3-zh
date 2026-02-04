# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P152：63_建模方法：随机和合成过采样.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_0.png)

In this video， we're going to focus on the idea of over samplingling。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_2.png)

And we've seen this before， and this concept here is again。

 to try and increase the size of our minority class so that is similar to size of our majority class。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_4.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_5.png)

So what we touched on the last videos basically comes down to this idea of random oversampling。

So this is going to be the simplest approach and what we do is that we just randomly resample with replacement the rows from our minority class。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_7.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_8.png)

And here there's no concern for where these points lie in space and whether certain points will be more or less indicative of the cluster of the actual minority class。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_10.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_11.png)

And this random overampling will work best for categorical data。

 where our features distance from other samples may not have as much interpretive underlying similarity。

 so we don't have to worry about whether or not there's a cluster and whether we're trying to define that cluster as correctly when we're working with categorical data。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_13.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_14.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_15.png)

Now another approach would be to synthetically oversample。

 so this time we're actually creating new samples of that minority class that don't yet exist。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_17.png)

So the first step is going to be to start with one of the points in that minority class。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_19.png)

We then choose one of the can nearest neighbors， we just choose one of them to start。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_21.png)

And we see here that we have chosen whatever it is between X Z I and X I。

 So X I is are minority class。 X Z I is one of those canaries neighbors。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_23.png)

And then we create a new point randomly。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_25.png)

Between that line connecting the two points so we see this x new where it can be anywhere in between X I and X ZI。

And then we repeat this for each one of the number of neighbors that we have set out。

 so if we haves K neighbors equal to three， then we do this for the three nearest neighbors。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_27.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_28.png)

Now there's two main approaches for the synthetic oversampling。

Both base off of this K nearest neighbors as its foundation。

One of them is going to be smoke and the other is going to be Addison。

 so we'll start here with smoke。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_30.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_31.png)

Now let's start with smoke S is going to be short for a synthetic minority over sampling technique。

 and it can be broken down into different subsets。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_33.png)

So the first subset is going to be regular smoke where we connect the minority class points to any neighbors。

 even those of other classes， as long as they are nearest neighbors。

 and then we use those connecting lines that we just discussed to randomly generate our new points somewhere in between those connecting lines。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_35.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_36.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_37.png)

We then have borderline smoke。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_39.png)

Where we have to first classify our points as outliers safe or in danger。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_41.png)

Where outliers will refer to those points where all neighbors are from a different class。

 so we start off with a point from a minority class and we look at let's say three neighbors。

 if we set our K neighbors equal to three and all three of those neighbors are from a different class。

 that would be an outlier。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_43.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_44.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_45.png)

We then have safe， which refers to those values for which all neighbors are from the same class。

 so if again we have our three neighbors and we're looking at a minority class point。

All three of the points nearby are all from the same class。

And then in danger where at least half of the nearest neighbors are from the same class。

 but they're not all from the same class， so two out of our three are from the same class there。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_47.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_48.png)

So we can break down borderline into two different types， we have borderline 1。

 where we connect minority endanger points， only two minority points。

 and then use those connections to generate our new samples。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_50.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_51.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_52.png)

And then we have borderline2 smoke， where we connect minority endanger points to whatever is nearby。

 no matter what the class is。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_54.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_55.png)

And then finally， we have SVM Smote， which uses an underlying support vector machine classifier to find support vectors and then uses that to generate samples considering those support vectors。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_57.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_58.png)

For both borderline and SVM smoke， a neighborhood is defined using the parameter M neighbors to decide the number of neighbors to use to decide whether sample in danger。

 whether it's safe or whether it's an outlier。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_60.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_61.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_62.png)

Now Addison or adaptive synthetic sampling works very similarly to smoke。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_64.png)

It starts off again by looking at the classes in the neighborhood of each minority point。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_66.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_67.png)

However， the number of samples generated for each point is going to be proportional to the number of samples which are not from the same class as that point in a given neighborhood。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_69.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_70.png)

Therefore， with Addison， more samples will be generated in the area that the nearest neighbor rule is not respected。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_72.png)

Thus putting more weight on values that would have been originally misclassified。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_74.png)

Now， all these are going to be motivated by Can nearest neighbors。

 but these oversampling techniques will help with any classification for which balance is an issue。



![](img/28764e6e6fdb2b0be165fe67d7b82b2e_76.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_77.png)

So we discussed random oversampling， different versions of Smote as well as Addison offer oversling in our next video we will go over different technical methods available for undersling Allright。

 I'll see you there。

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_79.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_80.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_81.png)

![](img/28764e6e6fdb2b0be165fe67d7b82b2e_82.png)