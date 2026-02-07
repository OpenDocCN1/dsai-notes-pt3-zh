# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P61：12_训练集和测试集分割第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So let's go through a breakdown of how we work with our training data as well as our test data。

 we start off with our training data。

![](img/ece5c8018bcf98ffd317229142e1d546_1.png)

![](img/ece5c8018bcf98ffd317229142e1d546_2.png)

Within our training data， we have a Xtrain and Ytrain。

 which will just be our features would be Xtrain and our outcome variable would be Ytrain。

 we fit a model to learn the parameters given our labeled data set using this dot fit。

 which will be just the normal practice as you use all of your SK learn models which will see we have seen in linear regression and we will continue to see throughout。



![](img/ece5c8018bcf98ffd317229142e1d546_4.png)

![](img/ece5c8018bcf98ffd317229142e1d546_5.png)

![](img/ece5c8018bcf98ffd317229142e1d546_6.png)

![](img/ece5c8018bcf98ffd317229142e1d546_7.png)

And that will give us our model that will define the parameters for the relationship between our X。

 our features， and our outcome variable。

![](img/ece5c8018bcf98ffd317229142e1d546_9.png)

![](img/ece5c8018bcf98ffd317229142e1d546_10.png)

Next we check our test data。

![](img/ece5c8018bcf98ffd317229142e1d546_12.png)

We pass in our X test from our testta into our model that has learned these parameters。

 and then we can use that to predict what the outcome variable would be for our X test as if there were no labels for this X test。



![](img/ece5c8018bcf98ffd317229142e1d546_14.png)

![](img/ece5c8018bcf98ffd317229142e1d546_15.png)

![](img/ece5c8018bcf98ffd317229142e1d546_16.png)

And that will give us a prediction for each one of these individual values in our test set。



![](img/ece5c8018bcf98ffd317229142e1d546_18.png)

![](img/ece5c8018bcf98ffd317229142e1d546_19.png)

We can then compare that since this again is just historical data to the actual values given our X test set。



![](img/ece5c8018bcf98ffd317229142e1d546_21.png)

And then we can evaluate our errormetric between why test and why predict。



![](img/ece5c8018bcf98ffd317229142e1d546_23.png)

And come up with our test error for a given model， assuming that we were looking at some data that we have never seen before。



![](img/ece5c8018bcf98ffd317229142e1d546_25.png)

![](img/ece5c8018bcf98ffd317229142e1d546_26.png)

Now let's go over the syntax thatll be needed in order to run your train test split within Python。



![](img/ece5c8018bcf98ffd317229142e1d546_28.png)

The first thing that we're going to want to do is from SK learnearn。t model selection。

 we're going to want to import the train test split function。



![](img/ece5c8018bcf98ffd317229142e1d546_30.png)

![](img/ece5c8018bcf98ffd317229142e1d546_31.png)

![](img/ece5c8018bcf98ffd317229142e1d546_32.png)

And then it's as simple as running train test split on our data here we're splitting the data and putting 30% into the test set that's going to be the argument test size is equal to 0。

3， will specify what percentage of your data you want to hold out for your test set。

 you can also pass in an actual numerical value， if it's between 0 and1。

 they'll know it's a percentage if it's some other value then they will put that exact value as your test size。



![](img/ece5c8018bcf98ffd317229142e1d546_34.png)

![](img/ece5c8018bcf98ffd317229142e1d546_35.png)

![](img/ece5c8018bcf98ffd317229142e1d546_36.png)

![](img/ece5c8018bcf98ffd317229142e1d546_37.png)

![](img/ece5c8018bcf98ffd317229142e1d546_38.png)

Also here we just have data and that's going to split into train and test。

If we had here instead X comma Y， so X being R features Y being our outcome variable。

 we would actually split this into four different values with so we pass into train test split X comma Y comma test size equals 0。

3， and the output would be four different values x train。



![](img/ece5c8018bcf98ffd317229142e1d546_40.png)

![](img/ece5c8018bcf98ffd317229142e1d546_41.png)

![](img/ece5c8018bcf98ffd317229142e1d546_42.png)

![](img/ece5c8018bcf98ffd317229142e1d546_43.png)

X test。And then why train and then Y test， so you'd want to have on the left side of train test split four values。

 which we'll see as we get into the notebook。

![](img/ece5c8018bcf98ffd317229142e1d546_45.png)

![](img/ece5c8018bcf98ffd317229142e1d546_46.png)

Now there are also other methods for splitting data we have the shuffle split here which will allow you to come up with multiple different splits rather than just one split of train and test you can have four different train and test splits。

 so it could be the last 30% the middle 30% or a random 30% each one being a different holdout set there's also a stratified shuffle split which will allow you to also ensure that there's no bias in your outcome variable Now what do I mean by that perhaps your data set has let's say it's medical and it's between one if they are diagnosed with cancer and zero if they're not 99% of the population or more probably will not be diagnosed with cancer or as 1% will we want to maintain that 99% to 1% split in our test and train set using that stratified shuffle split will ensure that we maintain that 99% to one。



![](img/ece5c8018bcf98ffd317229142e1d546_48.png)

![](img/ece5c8018bcf98ffd317229142e1d546_49.png)

![](img/ece5c8018bcf98ffd317229142e1d546_50.png)

![](img/ece5c8018bcf98ffd317229142e1d546_51.png)

![](img/ece5c8018bcf98ffd317229142e1d546_52.png)

![](img/ece5c8018bcf98ffd317229142e1d546_53.png)

![](img/ece5c8018bcf98ffd317229142e1d546_54.png)

![](img/ece5c8018bcf98ffd317229142e1d546_55.png)

![](img/ece5c8018bcf98ffd317229142e1d546_56.png)

![](img/ece5c8018bcf98ffd317229142e1d546_57.png)

![](img/ece5c8018bcf98ffd317229142e1d546_58.png)

![](img/ece5c8018bcf98ffd317229142e1d546_59.png)

Percent split moving forward。All right， with all that in mind。

 we're going to move to a notebook in order to see the details of how we can use train test split in practice。

 thank you。

![](img/ece5c8018bcf98ffd317229142e1d546_61.png)

![](img/ece5c8018bcf98ffd317229142e1d546_62.png)