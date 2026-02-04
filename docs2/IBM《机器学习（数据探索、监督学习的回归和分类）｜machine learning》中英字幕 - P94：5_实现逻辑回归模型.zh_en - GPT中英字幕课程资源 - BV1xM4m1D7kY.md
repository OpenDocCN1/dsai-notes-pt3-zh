# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P94：5_实现逻辑回归模型.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's take a step back and see how we can fit a logistic regression model using Scalar。



![](img/bb179f0d418b6227caabe4575ecbc566_1.png)

First we want to import our model， so from SK Learnear about linearar model。

 we import logistic regression。

![](img/bb179f0d418b6227caabe4575ecbc566_3.png)

![](img/bb179f0d418b6227caabe4575ecbc566_4.png)

We're then we're going to want to instantiate the class so we say LR that's going to be our object is equal to logistic regression。

 that's going to be what we imported just before and we are passing in these hyperparameters for regularization so we specify that regularization to avoid overfitting and we are using specifically the L2 norm which we learned earlier that's just going to be our coefficiention squared and then our C is going to be that regularization constant but here it's going to be essentially the inverse of that lambda that we learned before。

 so a higher C actually means less penalty。

![](img/bb179f0d418b6227caabe4575ecbc566_6.png)

![](img/bb179f0d418b6227caabe4575ecbc566_7.png)

![](img/bb179f0d418b6227caabe4575ecbc566_8.png)

![](img/bb179f0d418b6227caabe4575ecbc566_9.png)

We're then going to fit our model using our training set， we have our X train for our features。

 our Y train for our labels， and we come up with the fit。



![](img/bb179f0d418b6227caabe4575ecbc566_11.png)

![](img/bb179f0d418b6227caabe4575ecbc566_12.png)

And then we are able to also get our prediction values by passing in to LR。

predict once LR has been fit， our X test， our holdout set， so we come up with our prediction。



![](img/bb179f0d418b6227caabe4575ecbc566_14.png)

![](img/bb179f0d418b6227caabe4575ecbc566_15.png)

Then as we did with linear regression we can also call the coF underscore attribute to view each one of our coefficients。

 I do want to note at this point that if you want P values for either logistic or linear regression coefficients。

 I would suggest also looking into using the stats models package。

 which is better for statistical inference， but not quite as seamless as SK learn for general machine learning。



![](img/bb179f0d418b6227caabe4575ecbc566_17.png)

![](img/bb179f0d418b6227caabe4575ecbc566_18.png)

![](img/bb179f0d418b6227caabe4575ecbc566_19.png)

![](img/bb179f0d418b6227caabe4575ecbc566_20.png)

![](img/bb179f0d418b6227caabe4575ecbc566_21.png)

Another thing is that SKLn is going to come with this Knight cross validation method。

 which allows us to try several parameters very easily。

 and then once it exhausts a search on CV split set。

 it refits a model with the best choice of parameters similar to what we did with grid search CV。



![](img/bb179f0d418b6227caabe4575ecbc566_23.png)

![](img/bb179f0d418b6227caabe4575ecbc566_24.png)

![](img/bb179f0d418b6227caabe4575ecbc566_25.png)

![](img/bb179f0d418b6227caabe4575ecbc566_26.png)

Now logistic regression and classification in general has many applications。

 other applications besides just customer churn that we can use logistic regression for include maybe we want to predict customer spending and we can reframe the question is how likely is a customer to be a top 5% spender using previous purchase data for customer engagement we can predict which customers are most likely to engage in the next six months？



![](img/bb179f0d418b6227caabe4575ecbc566_28.png)

![](img/bb179f0d418b6227caabe4575ecbc566_29.png)

![](img/bb179f0d418b6227caabe4575ecbc566_30.png)

![](img/bb179f0d418b6227caabe4575ecbc566_31.png)

![](img/bb179f0d418b6227caabe4575ecbc566_32.png)

![](img/bb179f0d418b6227caabe4575ecbc566_33.png)

In E-commerce， we can predict which transactions are fraudulent using customer characteristics such as location。

 IP address， etc， and within finance and risk evaluation。

 we can predict whether a loan will default or not default。



![](img/bb179f0d418b6227caabe4575ecbc566_35.png)

![](img/bb179f0d418b6227caabe4575ecbc566_36.png)

![](img/bb179f0d418b6227caabe4575ecbc566_37.png)

And we want to keep in mind this idea of interpretation versus prediction。

 in addition to just prediction of predicting the labels。



![](img/bb179f0d418b6227caabe4575ecbc566_39.png)

![](img/bb179f0d418b6227caabe4575ecbc566_40.png)

We may want to evaluate the importance of each factor in influencing our outcomes recall how we learned that coefficients being larger still have interpretive values to them to each one of these coefficients。

 just rather than increasing our outcome variable by beta units when we're trying to do linear regression with a unit change in x it will increase the log odds by beta units with a unit change in x。

 still giving us an idea of the influence of beta of x on our outcome variable。



![](img/bb179f0d418b6227caabe4575ecbc566_42.png)

![](img/bb179f0d418b6227caabe4575ecbc566_43.png)

![](img/bb179f0d418b6227caabe4575ecbc566_44.png)

![](img/bb179f0d418b6227caabe4575ecbc566_45.png)

![](img/bb179f0d418b6227caabe4575ecbc566_46.png)

![](img/bb179f0d418b6227caabe4575ecbc566_47.png)

So to recap in this section， we introduced logistic regression as our first classification algorithm。

 outputting the probabilities of different classes。



![](img/bb179f0d418b6227caabe4575ecbc566_49.png)

We then showed the differences between linear regression and logistic regression。

 as well as showing how the two tie together。

![](img/bb179f0d418b6227caabe4575ecbc566_51.png)

And then we closed out to show how we can actually use logistic regression to predict the class with our customer churn example。

 as well as looking through how to do that with SKLn and discussing some other examples for which you may want to use logistic regression or other classifiers。



![](img/bb179f0d418b6227caabe4575ecbc566_53.png)

![](img/bb179f0d418b6227caabe4575ecbc566_54.png)

![](img/bb179f0d418b6227caabe4575ecbc566_55.png)

In the next video， we'll discuss the important topic of choosing the correct classification error metrics。

 and I look forward to seeing you there。

![](img/bb179f0d418b6227caabe4575ecbc566_57.png)

![](img/bb179f0d418b6227caabe4575ecbc566_58.png)

![](img/bb179f0d418b6227caabe4575ecbc566_59.png)