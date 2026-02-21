# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p112 27_处理类别不平衡.zh_en [BV1Jr421w7wL_p112]

🎼。

![](img/f268cfe5205f9775b3cf632d66c27552_1.png)

In classification problems， it's common to have many more observations for one class than for other classes。

 this is known as class imbalance。

![](img/f268cfe5205f9775b3cf632d66c27552_3.png)

You saw this when you looked at predicting whether a taxi trip would have a toll or not。

 trips without out tolls， outnumber trips with tolls 20 to 1 in the January data set。



![](img/f268cfe5205f9775b3cf632d66c27552_5.png)

![](img/f268cfe5205f9775b3cf632d66c27552_6.png)

In this video， you will use classification metrics to determine if a class imbalance is affecting model performance。

Use under sampling to reduce class imbalance in the training data。

And train classification models with undersampled data to improve minority class performance。



![](img/f268cfe5205f9775b3cf632d66c27552_8.png)

The taxi data shows a clear class imbalance between trips with tolls and trips without。

 You've previously seen that models trained with this data had high accuracies。

 but poor performance when predicting the minority class。



![](img/f268cfe5205f9775b3cf632d66c27552_10.png)

![](img/f268cfe5205f9775b3cf632d66c27552_11.png)

![](img/f268cfe5205f9775b3cf632d66c27552_12.png)

Those models were created without data validation or test sets。



![](img/f268cfe5205f9775b3cf632d66c27552_14.png)

Let's recreate those models by first holding back 20% of the data for final testing。

And changing the true false values for the was toldll paid predictor to easier to understand categories。



![](img/f268cfe5205f9775b3cf632d66c27552_16.png)

![](img/f268cfe5205f9775b3cf632d66c27552_17.png)

As with the previous models， select only the pickup and drop off location predictors。



![](img/f268cfe5205f9775b3cf632d66c27552_19.png)

This time， however， instead of using no validation， you'll use fivefold cross validation。



![](img/f268cfe5205f9775b3cf632d66c27552_21.png)

Let's train logistic regression and medium KNN models。



![](img/f268cfe5205f9775b3cf632d66c27552_23.png)

The false negative rate or FNR shows how often the model fails to predict a toll。



![](img/f268cfe5205f9775b3cf632d66c27552_25.png)

The logistic regression model misses almost 90% of the tolls。The K and N model does much better。

 But remember， K and N models require all the training data to make predictions so they can have high storage requirements。



![](img/f268cfe5205f9775b3cf632d66c27552_27.png)

Next， let's train an SVM model， which does not require all the data to be stored。



![](img/f268cfe5205f9775b3cf632d66c27552_29.png)

In this case， a fineine Gaussian kernel SVM model produces results on par with those of the KNN model。

This model isn't bad。 It correctly predicts no toll， with over 99% accuracy。



![](img/f268cfe5205f9775b3cf632d66c27552_31.png)

But it still misses about three tolls out of every 20。



![](img/f268cfe5205f9775b3cf632d66c27552_33.png)

One technique to handle imbalanced classes is to under or over samplele the training data。

Under samplingampling the data involves removing data points from the majority class。 In this case。

 trips with no tolls。Now the model can be trained with a more even focus on each class。

Oversampling involves duplicating or synthesizing more data points in the minority class。

Since you must be careful with this approach to avoid adding duplicate data to the test and validation sets。

 itll be covered in a later reading。

![](img/f268cfe5205f9775b3cf632d66c27552_35.png)

One way to use under sampling to improve minority class performance is with a randomly undersled or RUSS boosted tree ensemble。



![](img/f268cfe5205f9775b3cf632d66c27552_37.png)

This model performs the undersamp automatically as part of the training。



![](img/f268cfe5205f9775b3cf632d66c27552_39.png)

While the overall accuracy is lower than the SVM model， the false negative rate is below 10%。



![](img/f268cfe5205f9775b3cf632d66c27552_41.png)

If this level of performance still isn't sufficient， or if you want to try other types of models。

 you can manually under samplele the training data。

 Start by dividing the training data into two tables based on the value of was toll paid。



![](img/f268cfe5205f9775b3cf632d66c27552_43.png)

![](img/f268cfe5205f9775b3cf632d66c27552_44.png)

There are about 8000 trips with tolls in the training data。

 So let's sample 10000 of the trips without tolls to create a more balanced set。

Use the function data sample with the replaceplace F option to avoid duplicate data in the new training set。

Combine the two tables。And check the distribution。Now use this data set to train a new model。

Start a new session in the classification learner app with the undersampled data set。

Use the same predictors and validation methods as before。Let's start with a medium K N N model。

 It yields a false negative rate， below 3%。

![](img/f268cfe5205f9775b3cf632d66c27552_46.png)

The fine Gaussian SVM model worked well before and required less storage。 So let's try it again。

Its false negative rate is below 2%。

![](img/f268cfe5205f9775b3cf632d66c27552_48.png)

These models perform well， but they were trained with a different distribution of classes than the actual data。



![](img/f268cfe5205f9775b3cf632d66c27552_50.png)

Will they perform as well on new data。

![](img/f268cfe5205f9775b3cf632d66c27552_52.png)

You can check the models on the test data you split off earlier to make sure they generalize to new observations。



![](img/f268cfe5205f9775b3cf632d66c27552_54.png)

In this video， you used automatic and manual under samplingling of the majority class to train models to perform well when the data set had a large class imbalance。

You also use the false negative rate as the metric to optimize instead of the overall accuracy。

 which enabled you to tailor the training process to your data set。 Good work。😊。



![](img/f268cfe5205f9775b3cf632d66c27552_56.png)

。