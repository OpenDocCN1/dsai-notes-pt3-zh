# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P31：30_特征工程实验解决方案（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

All right， welcome back to the feature engineeringing demo notebook。Now。

 there are going to be a lot of variables that we saw that had missing values going back to our original data frame。

 We're using data dot is nu just to show you step by step。

 It's always good to see how all your V Python functions are working。



![](img/4179310741c5b7580ad0055aefc8a9ca_1.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_2.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_3.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_4.png)

That's going to pass true or false on whether each one is nu when I run dot sum。



![](img/4179310741c5b7580ad0055aefc8a9ca_6.png)

Summing is going to sum across each one of the columns。

 but say a sum across rows for each one of the columns and the dot sum for true values it will be one for false values it will be zero。

 and when we sort these we can see that the bottom of the list are the values for which there are a lot of null values。



![](img/4179310741c5b7580ad0055aefc8a9ca_8.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_9.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_10.png)

So that's a good way to sort them out。And with that in mind and the amount of features that we're working with。

 we're going to shrink down to a smaller data set to get through the next steps of feature engineering to go through a little bit more clearly some of the steps that we should have in mind。



![](img/4179310741c5b7580ad0055aefc8a9ca_12.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_13.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_14.png)

So we say Df。 Lo， we want all of the rows。But we're only going to look at the columns that we add here。

 law area， overall qual， et cetera， and keep in mind that you would probably be trying to predict sales price right and that's the last column that we're pulling in here。



![](img/4179310741c5b7580ad0055aefc8a9ca_16.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_17.png)

We're going to use the dot De function and we can see for each one of these that there's almost a full count that we have almost every single value。

And then we can see the mean， the standard deviation， so on and so forth。 We did dot T。

 which will transpose our data set。

![](img/4179310741c5b7580ad0055aefc8a9ca_19.png)

Describe by itself is just going to flip that on its head with each column being a column and each row being the count mean or some other summary statistic。



![](img/4179310741c5b7580ad0055aefc8a9ca_21.png)

We can also look at the dot info and we can see again the nu null values and the different data types。



![](img/4179310741c5b7580ad0055aefc8a9ca_23.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_24.png)

We're going to fill all the null values with zero here。



![](img/4179310741c5b7580ad0055aefc8a9ca_26.png)

There's only one null value。 The garage cars。 I would say if you're going to fill values。

 make sure that it's something that's indicative of what actually is within the data set。

 We're quickly filling this in with0。 But you may want to do something like the medium。

 which here we see is one or the average， which is。



![](img/4179310741c5b7580ad0055aefc8a9ca_28.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_29.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_30.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_31.png)

。6 that might be a little dangerous because these are integers and full numbers， so maybe one。



![](img/4179310741c5b7580ad0055aefc8a9ca_33.png)

But here we're going to fill in with zero， it probably won't have much an effect。

 given that we're only filling in one value。

![](img/4179310741c5b7580ad0055aefc8a9ca_35.png)

And then once we do that， we see that we have no null values。



![](img/4179310741c5b7580ad0055aefc8a9ca_37.png)

Right before we had Gar Car 2924， now we have 2925。



![](img/4179310741c5b7580ad0055aefc8a9ca_39.png)

Now we're going to use our pairplot function that SNS has or Seaborn has available for us just on that smaller Df。



![](img/4179310741c5b7580ad0055aefc8a9ca_41.png)

And the questions that we have here is what do these plots tell us about the distribution of our target。

 our target here being the sale price。With that in minds， we also want to think about the plot。

 what do the plots tell us about the relationship between features and the target Now。

 going back to that first question， we saw sale price earlier in regards to its distribution。

 so we already know that this is again to show that it probably has a right skew and perhaps we want to do that transformation that we skipped over last time。



![](img/4179310741c5b7580ad0055aefc8a9ca_43.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_44.png)

We're going to see the relationship so the scatter plots are going to start to tell us whether there's a linear relationship between each one of the variables and the target column and perhaps whether we'd want to do some type of transformation in order to ensure there's a linear relationship with the transform variable and our target variable。



![](img/4179310741c5b7580ad0055aefc8a9ca_46.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_47.png)

And then what do these plots tell us about the relationship between various features。

 that's the last question we want to ensure that there's not too heavy of a multicollineity between each one of our features as that can throw off our interpretation of something like linear regression。

 which we'll talk about again a little bit later。

![](img/4179310741c5b7580ad0055aefc8a9ca_49.png)

Now we go down to the bottom and it's really small here， but this last row。Is referencing sale price。

So this is going to be our distribution， which we saw earlier。

 the one all the way in the bottom right corner。And that's going to specify that there's a little bit of a right skew。

We see here on the second column bottom row。That there's a bit of a curvature。

In the way there's a relationship between， I believe that's overall quality and sale price。

 so perhaps we want to take a polynomial function there， which we'll do later on。

And then in terms of multicolonarity， I don't see too many that are heavily correlated one with the other。

 there are some that maybe cause a bit of concern， but it's okay to have some multicolonarity when you're doing multiple regression。



![](img/4179310741c5b7580ad0055aefc8a9ca_51.png)

So now we want to separate out our sale price as the target variable。

 which is what we'll do when we do our actual modeling。

 We're not going to do any actual modeling here that we'll go over that in the next lecture。

 but these are those preprocessing steps。 So this will build your intuition to how you'll actually be able to jump in and you'll see that actually writing the code for modeling is usually the easiest of all the steps where 80% goes into the EDA and the feature engineering and so on and so forth。



![](img/4179310741c5b7580ad0055aefc8a9ca_53.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_54.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_55.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_56.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_57.png)

So now we're just looking at X X being each one of our features， Y now specifying sale price。

 which is our outcome variable。

![](img/4179310741c5b7580ad0055aefc8a9ca_59.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_60.png)

And let's work with adding a polynomial feature as well as interaction terms。

 So one of the first things when we look at the pair plot that I mentioned is that certain features like overall quality and greater living quality may have this if you look back at the bottom row have this kind of upward trend right and also with the1。

2，3，4，5，6。 So we have the second column and the six column where we see this large upward trajectory that's definitely not linear。

 So perhaps you'd want to do a transformation。

![](img/4179310741c5b7580ad0055aefc8a9ca_62.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_63.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_64.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_65.png)

So what we'll do is we'll create a copy of our original X so that we still have X available to us。

And all we have to do is square that column so we just。Run this code。 And now we have。

Our original column， overall quality， as well as O U O Q2， which is just overall quality squared。

 and then greater living area as well as GLA squared。



![](img/4179310741c5b7580ad0055aefc8a9ca_67.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_68.png)

Now， as is each feature is treated as an independent quantity。

 but there may be interaction effects in which the impact of one feature may be dependent on the current value of a different feature。

 so the example that we have here， there may be a higher premium for increasing overall quality for houses that were built more recently。



![](img/4179310741c5b7580ad0055aefc8a9ca_70.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_71.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_72.png)

So if you think about it， if such a premium exists。

 then you probably want overall quality by year built to help us capture this interaction between the two。



![](img/4179310741c5b7580ad0055aefc8a9ca_74.png)

The idea being something in 2000 with a higher quality should be。

Exponentialally more or multiplied more compared to something that's 1980 in higher quality， right。

 not just that linear relationships， but perhaps then being both higher would compound the amount of effect that it'll have on our sale price。



![](img/4179310741c5b7580ad0055aefc8a9ca_76.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_77.png)

So that's why I have the overall quality， overall quality times the year built。



![](img/4179310741c5b7580ad0055aefc8a9ca_79.png)

And that's going to be。Our new feature x3。

![](img/4179310741c5b7580ad0055aefc8a9ca_81.png)

We can also do overall quality per lotatt area， and it could be the idea being that you might get something like quality per square foot。



![](img/4179310741c5b7580ad0055aefc8a9ca_83.png)

Might be an indicator of。

![](img/4179310741c5b7580ad0055aefc8a9ca_85.png)

You know how well you can predict sale price as well。

 So these are two different ways of building feature interactions。

 So these are your basic feature engineering steps that you should keep in mind。

 And a lot of it's going to be built off your intuition about the problem that you're trying to solve。



![](img/4179310741c5b7580ad0055aefc8a9ca_87.png)

So the last thing that I want to go through before pausing is how to create。



![](img/4179310741c5b7580ad0055aefc8a9ca_89.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_90.png)

Categorical variables， how to input categorical variables as numerical features。



![](img/4179310741c5b7580ad0055aefc8a9ca_92.png)

So you can't just。Dump in a categorical variable， something that's an object。

 So what we have to do is what we saw in lecture is introduce dummy variables or use one hot encoding。



![](img/4179310741c5b7580ad0055aefc8a9ca_94.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_95.png)

So we'll first explore using the house style feature and we always want to ensure that there are enough。

 so it says here it's a good idea to check that there's going to be a。



![](img/4179310741c5b7580ad0055aefc8a9ca_97.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_98.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_99.png)

Reasonable representation of each one of our values within our categorical feature。



![](img/4179310741c5b7580ad0055aefc8a9ca_101.png)

So we're going to use the Val counts method that's available for Pada series。



![](img/4179310741c5b7580ad0055aefc8a9ca_103.png)

And we see that we have。1480 of one story， so on and so forth for each one of the values we deem there being eight values enough values to specify some type of predictive value moving forward。

 so all we want to do in order to get this one hot encoding， is run this function。

 which we briefly introduce in lecture。

![](img/4179310741c5b7580ad0055aefc8a9ca_105.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_106.png)

P D dot get dummies。Now if we ran pd。get dummies on our entire data frame。



![](img/4179310741c5b7580ad0055aefc8a9ca_108.png)

PD dot get dummies。On our entire data frame。

![](img/4179310741c5b7580ad0055aefc8a9ca_110.png)

Then it will actually come up， we see 303 different columns， originally we had， I believe。

 82 columns for every single column that is an object。



![](img/4179310741c5b7580ad0055aefc8a9ca_112.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_113.png)

It'll come up with a dummy variable， and we see here all the way to the right that for sale condition。

 they had sale condition partial sale condition， normal， sale condition family。

 so on and so forth for each one of the specific values。



![](img/4179310741c5b7580ad0055aefc8a9ca_115.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_116.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_117.png)

Here we are only looking at house style。And this is just a quick peek into what it would look like for the house style we had above。



![](img/4179310741c5b7580ad0055aefc8a9ca_119.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_120.png)

Where we see one story。Is going to have its own column now。

 and you see that we have ones for when it's one story and no matter what there's only going to be one1 and the rest will be zeros because this is representing the original column and the original column can only take on one of these values at each point。



![](img/4179310741c5b7580ad0055aefc8a9ca_122.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_123.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_124.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_125.png)

So as I said before， you can do PDd。ge dummies and get dummy variables for the entire data set for every single categorical feature。



![](img/4179310741c5b7580ad0055aefc8a9ca_127.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_128.png)

Now， we're going to look at the neighborhood counts。

 So this may be another column that we want to transform into a。



![](img/4179310741c5b7580ad0055aefc8a9ca_130.png)

嗯。

![](img/4179310741c5b7580ad0055aefc8a9ca_132.png)

One hot encoding， so we're going to take it from one column into X many columns。

 depending on the number of unique values。

![](img/4179310741c5b7580ad0055aefc8a9ca_134.png)

And for this category， we see that there's a couple of different values that have very low counts。

 and perhaps you want to group these all into its own category， so what we do here。



![](img/4179310741c5b7580ad0055aefc8a9ca_136.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_137.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_138.png)

Is we are saying N H counts。Such that NH counts is less than eight。Dot index。

 so let's just show you what that looks like。

![](img/4179310741c5b7580ad0055aefc8a9ca_140.png)

That is just bringing out Greens， GRN Hill and landmark。

 as those are the three values that have less than8。

 and that's what the dot index is just going to specify we want those index values。



![](img/4179310741c5b7580ad0055aefc8a9ca_142.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_143.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_144.png)

We turn that into a list so that now we have our list of values。



![](img/4179310741c5b7580ad0055aefc8a9ca_146.png)

And then we are transforming our original X4 neighborhood。



![](img/4179310741c5b7580ad0055aefc8a9ca_148.png)

Using the dot replace function。

![](img/4179310741c5b7580ad0055aefc8a9ca_150.png)

And what are we replacing or're replacing any value that falls into this list that we just specified？



![](img/4179310741c5b7580ad0055aefc8a9ca_152.png)

With the word other。And the reason for this is if we look at now。



![](img/4179310741c5b7580ad0055aefc8a9ca_154.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_155.png)

At our value counts。Sorry we want to use x4。

![](img/4179310741c5b7580ad0055aefc8a9ca_157.png)

You see that we have now other fall as 11 different values and it removes those low count values that we had earlier。



![](img/4179310741c5b7580ad0055aefc8a9ca_159.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_160.png)

Al right， we're going to take a break here， and in the next video we're going to do a brief introduction to some more complex types of feature engineering to kind of get the wheels turning and different options that are available to you as you try to come up with the best preprocess steps before feeding in your data into the model。



![](img/4179310741c5b7580ad0055aefc8a9ca_162.png)

![](img/4179310741c5b7580ad0055aefc8a9ca_163.png)