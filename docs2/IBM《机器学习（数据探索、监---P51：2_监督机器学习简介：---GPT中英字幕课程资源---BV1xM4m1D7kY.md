# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P51：2_监督机器学习简介：机器学习类型第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's make clear this difference between parameters and hyperparameters。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_1.png)

Our fit parameters and you'll see this fit term come into play as we learn to code our machine learning models。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_3.png)

Involves a aspect of the model which we will estimate using the data such as our linear regression coefficients。

 right those are going to be our fit parameters。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_5.png)

Before fitting our model to our X and Y though， we must make certain decisions regarding the model itself。

 so before doing any fitting to the data， we are making some decisions about that model itself。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_7.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_8.png)

And these decisions。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_10.png)

Are going to be what lead to how hyperpara come about This will allow us to tweak a given model in ways that are not directly learned by the model itself。

 and these tweaks will usually aid in optimizing that model's power。😡。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_12.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_13.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_14.png)

Now within supervised learning。There's going to be another common split into two categories。

 depending on the outcome variable that we are trying to predict。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_16.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_17.png)

On one hand， we have regression， and now regression does not just refer to linear regression。

 but rather refers to any time we're trying to predict a numeric value。

 examplesles of this would be coming up with models to predict stock price to predict the box office revenue or even a location。

 assuming we're trying to predict the X and Y coordinates of that location。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_19.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_20.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_21.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_22.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_23.png)

And then the other。Grouping that we'd be talking about and within supervised learning would be classification。

 and this is when our outcome variable is categorical。 So again。

 both of these depend on what our outcome variable is that we're trying to predict。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_25.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_26.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_27.png)

And in this example， we would include stuff such as face recognition。

 where we are predicting which particular person's face we have in a picture。

 our customer churn example where we are predicting whether customer will churn or not churn。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_29.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_30.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_31.png)

And predicting which word would come next in a sentence。

 as you often see when beginning a search in Google， these each have a categorical outcome。

 so that's regression versus classification。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_33.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_34.png)

And all this in regards to supervised machine learning can be contained in the equation we see here。

 which gives the machine learning framework for all supervised machine learning models。

 we have an input X。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_36.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_37.png)

An output of predicted Y's given a particular x and some machine learning model that generates a prediction by learning the appropriate parameters omega。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_39.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_40.png)

So what is the process by which we learn the correct parameters？

Data scientists will train the model to find the best parameters by looking at past data。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_42.png)

Each observation X is going to relate to some outcome variable y。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_44.png)

The more of these values we have， the better the machine learning model can learn the parameters that define this relationship between the features in X and the outcome variables Y。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_46.png)

Once we have trained on our past data as we get new observations such as new customers in our churn example。

We can use our past experience to model the probability of these new customers churning。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_48.png)

We feed these values into our model。With our learn parameters from our training set to come up with predictions YP。

And we have a prediction for each new customer。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_50.png)

Now， in practice， we would not want to train on all past customers。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_52.png)

As a very complex model can actually pick up on the pattern。

 such as if a customer has been a member for three months， has a $30 per month subscription。

 and his name is Daniel Mandeel， he will churn right。

 that'll be overly specific but a complex model can learn something that specific。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_54.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_55.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_56.png)

What we would want to do is have something that can generalize better when new data comes in。

 so we would train on just a subset of our old data and optimize our results on a holdout set that hasn't been trained to see how it'll perform in the real worlds before putting our model into production。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_58.png)

And this will be an idea that we'll delve into deeper called test and Tra splits。

 which we'll talk about within this course。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_60.png)

So what is the mechanism that is driving the updating of our parameters as new data comes in。

 you see at the bottom of these bullets we have introduced。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_62.png)

This new term， the lost term， and we have this function， J of Y and Y P。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_64.png)

Most models are going to define some quantitative score for how good our predictions are。

And if we look at this loss function， this J of y and YP。

 the output would actually be some quantitative measure of how close our YP。

 our prediction was to y the actual values。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_66.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_67.png)

And given our features X and the outcome variable Y。

 the update rule will determine how to update our parameters。

 typically trying to find those parameters that will minimize that loss function。

 minimize the error between y and。

![](img/2d2be6fee23bf01ce7c75314878a1c4d_69.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_70.png)

Our prediction， which is coming from F of our parameters and our input。

So that closes out our introduction to superviseed machine learning and the next section we'll cover different approaches to supervise machine learning。

 namely differentiating between whether our goals are to focus on interpretation or prediction Thank you。



![](img/2d2be6fee23bf01ce7c75314878a1c4d_72.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_73.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_74.png)

![](img/2d2be6fee23bf01ce7c75314878a1c4d_75.png)