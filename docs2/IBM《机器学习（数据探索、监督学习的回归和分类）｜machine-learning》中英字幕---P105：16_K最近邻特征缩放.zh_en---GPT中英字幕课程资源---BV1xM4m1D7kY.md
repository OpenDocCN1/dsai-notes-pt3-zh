# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P105：16_K最近邻特征缩放.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's take what we discussed in that last video in regards to pros and cons and see how that relates to linear regression。

 and this will hold for logistic regression as well。



![](img/3a829ea320039d6464e70afa49369ce2_1.png)

Now， model fitting is going to be relatively slow for linear regression since we're conducting a search for what those best parameters are。

Whereas Can near neighbors is going to be relatively fast， since all we have to do is store the data。

 that's going to be our fit。 We just store the data with its labels， and later on。

 we can use that to predict which labels are closest。



![](img/3a829ea320039d6464e70afa49369ce2_3.png)

![](img/3a829ea320039d6464e70afa49369ce2_4.png)

Once the model is fit， linear regression costs basically nothing。

 It's just a short sequence of parameters。 It's just going to have to remember the coefficients that determine the line or the hyperplane in higher dimension space。

 So it's to be very memory efficient。

![](img/3a829ea320039d6464e70afa49369ce2_6.png)

On the other hand， Ka nearest neighbors need to remember all of the points。

 need to remember the entire training set， so it's going to be very memory intensive。



![](img/3a829ea320039d6464e70afa49369ce2_8.png)

And finally， prediction for linear regressiongion is simply a linear combination of our vectors。

 so it's going to be very fast， whereas Canius neighbors needs to determine which points are closest。



![](img/3a829ea320039d6464e70afa49369ce2_10.png)

![](img/3a829ea320039d6464e70afa49369ce2_11.png)

So that's going to have to compute several different distances from each one of the points。

 which can take some time， so it'll take a bit longer to actually perform prediction。



![](img/3a829ea320039d6464e70afa49369ce2_13.png)

![](img/3a829ea320039d6464e70afa49369ce2_14.png)

Now let's take a look at the syntax for actually creating a KNN classification model。

 so the first thing that we're going to want to do is import the KNN classifier from SK learnn here we see that we're importing from SK learnn。

 neighbors， the K neighborighs classifier。

![](img/3a829ea320039d6464e70afa49369ce2_16.png)

Then as we've done before， we're going to create an instance of the class。 When we do so。

 we need to pass in the hyperparameter that we want to pass through Here we are setting n neighbors equals to3。



![](img/3a829ea320039d6464e70afa49369ce2_18.png)

And neighbors is going to be that K that we're trying to decide on so we can pass in the certain value of K。

 How many neighbors do we want to use in order to see which values are closest。

There are other parameters obviously that are available here we're letting them set to the default。

 but you should be aware of the defaults such as that we will be using uniform weighting。

 So if we have k equal to3 or measuring each one of those three closest neighbors with the same amount of weight and in terms of similarity in terms of that distance metric by default。

 it will use the Euclidean distance and you could read more about the default settings for each parameter in the documentation and Id always suggest doing so whenever you're introduced a new model。



![](img/3a829ea320039d6464e70afa49369ce2_20.png)

The next thing that we're going to do is fit to our training set as we've done with our other models。

 so we say can and then dot fit。

![](img/3a829ea320039d6464e70afa49369ce2_22.png)

And we pass in our X train and Y train。

![](img/3a829ea320039d6464e70afa49369ce2_24.png)

And then we can predict on our test set， calling once it's already been fit。

 K&N dot predicts on our test set， and we set that equal to Y predict and those will be our predicted values。



![](img/3a829ea320039d6464e70afa49369ce2_26.png)

Now the methods fit and predict and fit and transform as well will be seen again and again in this course。

And I just want to highlight here， we see for models。

 so when we're trying to predict or we'll call them predictors since they have this predict method so that fit predict method that we just saw。

We are generally going to pass into the fit， both an X and a y set。

 so we're fitting to the x and the y so that we can predict the different y。



![](img/3a829ea320039d6464e70afa49369ce2_28.png)

![](img/3a829ea320039d6464e70afa49369ce2_29.png)

And then for transformations， when we're doing fit， transform。

 and we'll call those transformers because they have the transform method。



![](img/3a829ea320039d6464e70afa49369ce2_31.png)

We generally are going to be passing in just a single value。

 such as what we do with standard Scalar where we just pass in the X。

 or if we're going to do one hot en codingd where we just pass in the X。

 and then we can get our transformed variable。

![](img/3a829ea320039d6464e70afa49369ce2_33.png)

![](img/3a829ea320039d6464e70afa49369ce2_34.png)

Now， if you're interested in doing the same thing for regression。

 all you have to do is replace K neighbor's classifier with K neighbor's regressor and ensure that your Y train set and your Y test set are both going to be continuous values。

 and everything else stay the same。

![](img/3a829ea320039d6464e70afa49369ce2_36.png)

![](img/3a829ea320039d6464e70afa49369ce2_37.png)

So now let's recap what we've learned here in regards to K nearest neighbors in this section。

 we discuss the K nearest neighbors approach for classification and how it to simply take that majority vote amongst the K value that we chose。

 So if we chose K equals 3 and two of our closest neighbors are churned versus one not churning we predict that that new customer would churn since two churned and one did not in regards to the closest neighbors。



![](img/3a829ea320039d6464e70afa49369ce2_39.png)

![](img/3a829ea320039d6464e70afa49369ce2_40.png)

![](img/3a829ea320039d6464e70afa49369ce2_41.png)

![](img/3a829ea320039d6464e70afa49369ce2_42.png)

![](img/3a829ea320039d6464e70afa49369ce2_43.png)

We discussed the K&N decision boundary and how different Ks will influence what that boundary actually looks like。

A high K will mean a high bias with the extreme being that what we saw with k equal to the number of data points。

 and when we have that it would just predict what the majority class was。

And a low would mean high value variance， so with the extreme being K equals 1。

 and we just choose the closest neighbor， even if it happens to be an outlier。



![](img/3a829ea320039d6464e70afa49369ce2_45.png)

![](img/3a829ea320039d6464e70afa49369ce2_46.png)

We highlighted the distance measurements， the most popular being the Euclidean and Manhattan distances。

 as well as the importance of feature scaling to ensure that no one feature had too much or too little influence on our prediction。



![](img/3a829ea320039d6464e70afa49369ce2_48.png)

Then finally， we discussed the implementation of KNN for both classification and regression using SKalL。



![](img/3a829ea320039d6464e70afa49369ce2_50.png)

![](img/3a829ea320039d6464e70afa49369ce2_51.png)

Now we'll take what we just discussed in lecture and begin to apply it in our notebook for Can nearest neighbors All right。

 thank you。

![](img/3a829ea320039d6464e70afa49369ce2_53.png)

![](img/3a829ea320039d6464e70afa49369ce2_54.png)