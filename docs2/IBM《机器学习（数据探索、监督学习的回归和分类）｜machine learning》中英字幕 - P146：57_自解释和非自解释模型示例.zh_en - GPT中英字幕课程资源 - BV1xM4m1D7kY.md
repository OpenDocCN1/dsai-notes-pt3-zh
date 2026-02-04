# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P146：57_自解释和非自解释模型示例.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/8e9c6d0e90ea9621d4fe47afa326febb_0.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_1.png)

Welcome to examples of self interpretable and non self interpretable models。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_3.png)

After watching this video， you will be able to list typical models with different interpret abilitiesities and describe the two main types of model interpretation methods。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_5.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_6.png)

Linear models are probably the most widely used predictive models due to their simplicity and effectiveness。

 especially in the financial industry。

![](img/8e9c6d0e90ea9621d4fe47afa326febb_8.png)

Their structure is simple， with just a linear combination of features that predict values。

 as such linear model prediction outcomes often require minimal effort to understand。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_10.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_11.png)

For example， suppose we have a house price prediction linear regression。

 we can easily predict the price of a house by adding features such as its number of rooms。

 which is positively correlated， the associated high school ranking is negatively correlated。

 meaning that the closer a school is rated to number one， the more it will cost。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_13.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_14.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_15.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_16.png)

One side note is that even a linear model can become difficult to understand if it includes too many features。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_18.png)

Sometimes even more than just 10 features is too complicated to be self- interpretable。

 an effective way to make it easier to understand is to use feature selection methods such as Lasso regression analysis。

 so that the model only includes important features。

 thus both increasing interpretability and decreasing the risk of overfitting。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_20.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_21.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_22.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_23.png)

Tree models such as decision trees are another popular self interpretable type of model；

 the main characteristic of tree models is they mimic humans reasoning process via creating a set of if then else rules。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_25.png)

For example， if a house has more than four rooms and if its associated school is within the top 10。

 then its estimated house price is $850，000。 However， like linear models。

 big tree models with large widths and depths also become difficult to understand and prone to suffer from overfitting。

 tree pruning is one way to reduce the size of the generated trees。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_27.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_28.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_29.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_30.png)

The K nearest neighbor model or K and N can also be considered a self interpretable model if the feature spaces can be comprehensible and kept small。

 For example， supposeose we want to predict the price of a house with four rooms and its associated high school ranking is 10th。

A trained KNN model predicts the price of house zero to be $855。

000 based on the average of three of its neighbors。

Such a prediction process is consistent with our intuition and common sense。

 as we will also check for similar houses sold in the neighborhood as baselines。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_32.png)

Also， like linear and tree models， K and N models can become difficult to understand if the feature space is large。

 we can reduce the number of neighbor instances and features to simplify K andN and make it more interpretable。

 Now let's see an example of a non self interpretable model。

 Suppose we have a random forest containing 250 different trees with 150 total features。

 Each tree is built based on a randomly selected subset of features and data。

 Each tree generates its own prediction。 For example， one or zero。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_34.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_35.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_36.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_37.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_38.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_39.png)

The model's final prediction outcome is based on a voting of all 250 trees；

 it is not feasible for a model consumer to review each tree and find out the common rule sets shared among each of the 250 trees to figure out how the final ensemble decision was generated。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_41.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_42.png)

As such， the random forest model is considered a non self interpretable model。

There are many other non self interpretable models。

 such as linear support vector machines and deep neural networks。 For those complex models。

 we will probably need extra effort to explain and understand their predictions。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_44.png)

![](img/8e9c6d0e90ea9621d4fe47afa326febb_45.png)

In general， model interpretation methods can be divided into two categories。

 intrinsic and post hoc In methods are mainly applied to self interpretable models such as linear models。

 tree models and KNN。Although these models are natively highly interpretable。

 they may also become complex if too many features are included。

 thus the main goal of intrinsic methods is to simplify the model using methods like regularization or pruning。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_47.png)

For non self interpretable models， such as random forest， nonlinear SVM， and deep neural networks。

 we need to apply auxiliary explanation methods to understand their predictions after the models have been trained。

In this video， you learned that simple linear tree or KNN models are normally self interpretable models。

 complex models such as large ensemble models or SVM are normally non self interpretable models。



![](img/8e9c6d0e90ea9621d4fe47afa326febb_49.png)

And there are two main types of interpretation methods， such as intrinsic methods。

 which are used with models that are self interpretable。

 Post ho methods are used to interpret models that are trained with black box models。 In other words。

 models that are non self interpretable。

![](img/8e9c6d0e90ea9621d4fe47afa326febb_51.png)