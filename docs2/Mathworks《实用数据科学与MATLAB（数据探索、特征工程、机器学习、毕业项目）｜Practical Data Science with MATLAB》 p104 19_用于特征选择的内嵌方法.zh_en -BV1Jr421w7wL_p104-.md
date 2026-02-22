# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p104 19_用于特征选择的内嵌方法.zh_en [BV1Jr421w7wL_p104]

🎼，So far， you've trained models on data sets with thousands of observations and fewer than 10 features。

The data sets you work with， however， won't always have substantially more observations than features。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_1.png)

For example， medical data sets can have many pieces of information recorded for a small number of patients。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_3.png)

When the number of features is comparable or even greater than the number of observations。

 then the data set is said to be high dimensional or wide。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_5.png)

Using high dimensional data when training can lead to complex models that overfit the data。

In the extreme case， you could create a model that exactly predicts the training data。

 but at the cost of generalizing poorly to new data。So what can you do？



![](img/e5ceaa86e12f83f0698f0522ad97f87e_7.png)

Your main tools for working with high dimensional data are feature selection and dimensionality reduction。

These concepts were introduced earlier in the specialization。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_9.png)

Remember， there are three types of feature selection methods。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_11.png)

Filter， wrapper， and embedded。

![](img/e5ceaa86e12f83f0698f0522ad97f87e_13.png)

Filter methods are applied before training a model and use the statistical properties of features to remove those with low predictive power。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_15.png)

Rrappper methods train multiple models using different combinations of features。

 and then select the features that produce the best model performance。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_17.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_18.png)

Finally， embedded methods perform feature selection as part of the model training。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_20.png)

The result is a model that emphasizes only the most useful features。In this video。

 you'll learn how to use an embedded method to determine which features to include in a model that predicts ovarian cancer in patients。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_22.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_23.png)

Let's start by loading the data。This data set has 4000 features that were identified by analyzing blood samples from 216 patients。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_25.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_26.png)

Right now， there are two variables in the workspace。

The predictor matrix contains the 4000 features for each patient。

 and the response variable has labels of cancer or normal to indicate which patients had cancer。

The goal is to train a binary classifier to predict these labels。First。

 split the data into a training and test set using CV partition。

You won't complete the final evaluation in this lesson。

 but it's a best practice to always set some data aside for testing the trained model。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_28.png)

Open the classificationification learner app。And select the predictor matrix with the training data。

Remember， this matrix has 4000 columns， so it may take a while to load。

Then select the response variable with training data from the workspace。

To see if a model is overfitting， you need to compare the performance with and without validation。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_30.png)

For now， select no validation and start the session。Choose a medium tree is the model。

And start the training。This model will use a maximum of 20 splits。The reported accuracy is 100%。

 But remember， this is without validation， meaning the model was evaluated using the same data it was trained on。

Now， let's compare the result with validation。

![](img/e5ceaa86e12f83f0698f0522ad97f87e_32.png)

Restart the session。And select the same data as before。This time。Choose 20fold cross validation。

Cross validation will help with this data set because there are very few observations。

There is no hard and fast rule for choosing the number of folds。

 but using10 or more with a small data set will help ensure that each fold is representative of the whole thing。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_34.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_35.png)

Once the data is loaded， train another medium tree model。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_37.png)

Notice the accuracy is now 83%， whereas the value without validation was 100%。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_39.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_40.png)

The performance of a model will almost always decrease with validation data。

 but a drop of 17% suggests the medium tree models overfitting the data。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_42.png)

Let's try to improve the model by removing the weakest predictors。

Decision trees include an embedded feature selection method that quantifies the relative importance of each predictor。

You can access this information by exporting the trained model to the workspace。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_44.png)

In the live script。Use the function predictor importance to return a vector of values。

A predictor is considered important if it helps the model。

 So if a predictor is used in multiple decision rules， its importance will be high。

An easy way to visualize the importance is with the function Paretto。

A Paretto chart will sort the data and display a bar graph of the most important predictors。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_46.png)

The y axis on the left shows the importance value of each bar。

And the labels along the X axis are the feature indices。

Above the bars is a line graph of the cumulative sum of the importance values。

The y axis on the right side， displays the percentage。

So you can see that these five features reach almost 97% of the combined predictor importance。

The Paretto function will only plot as many features as it takes to reach 95%。Therefore。

 this chart tells you that five of the 4000 features represent over 95% of the predictor importance。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_48.png)

Let's create a new predictor matrix that only contains these five features。

Remember that you can use a vector of indices to extract specific columns。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_50.png)

Next， return to the classification learner app and start a new session。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_52.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_53.png)

Select the new predictor matrix。And set the cross validation to 2fold， like before。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_55.png)

Choose a medium tree model。And start the training。The reported accuracy is now 95%。

 meaning the accuracy actually increased when using fewer features。

This confirms that the original model is overfitting， since the performance is better。

 even though the data is a fraction of its original size。With a different model or data set。

 the performance may not have increased。You'll find that the performance will often stay the same or even decrease slightly when removing features。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_57.png)

But this isn't necessarily a bad thing。Even if the accuracy decreased from 83% to， say，80%。

 it could still be a better choice because the data set is much smaller。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_59.png)

There are multiple benefits to using a smaller data set， such as lower memory requirements。

 faster training times and better interpretability。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_61.png)

And that's it。 You can now use an embedded feature selection method to improve models using high dimensional data。

This method was specific to decision trees， but there are other embedded methods for different types of models。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_63.png)

![](img/e5ceaa86e12f83f0698f0522ad97f87e_64.png)

As well as raper methods。And don't forget the filter methods and dimensionality reduction techniques that you've learned about previously。

No single method will work in every situation。 So try out different methods when working with a new data set。

Then you'll be able to get the best performance with only the features you need。



![](img/e5ceaa86e12f83f0698f0522ad97f87e_66.png)

。