# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P80：31_递归特征消除.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's briefly touch on another means of feature selection outside of just using LASA。

 namely we're going to work with recursive feature elimination or RFE。



![](img/f42f03d149c03752aa943a78a9d53119_1.png)

![](img/f42f03d149c03752aa943a78a9d53119_2.png)

An RFE is going to be the tool that SKLn provides to do feature selection recursively and automatically。



![](img/f42f03d149c03752aa943a78a9d53119_4.png)

So the way that it works is that it'll first be choosing a model。

 we as the users will have to choose which model we want to limit the features of。



![](img/f42f03d149c03752aa943a78a9d53119_6.png)

We will then explicitly define how many features we want to end up with for that feature。



![](img/f42f03d149c03752aa943a78a9d53119_8.png)

And RFE will then repeatedly run the model that'll measure the different feature importances and recursively remove less important features。



![](img/f42f03d149c03752aa943a78a9d53119_10.png)

![](img/f42f03d149c03752aa943a78a9d53119_11.png)

The way that it does this in SKL learn is that the model that we choose to pass through must either have an attribute for coefficients or for feature importance。



![](img/f42f03d149c03752aa943a78a9d53119_13.png)

![](img/f42f03d149c03752aa943a78a9d53119_14.png)

And then the RFE will then eliminate the smallest value for the value for coefficients or for the feature importances。



![](img/f42f03d149c03752aa943a78a9d53119_16.png)

![](img/f42f03d149c03752aa943a78a9d53119_17.png)

An important note is that with this in mind， we must ensure that we first scale our data if we're going to do something like linear regression so that each one of the coefficients that our linear regression learns are going to be measured on that same scale。



![](img/f42f03d149c03752aa943a78a9d53119_19.png)

![](img/f42f03d149c03752aa943a78a9d53119_20.png)

![](img/f42f03d149c03752aa943a78a9d53119_21.png)

So how do we use this in SKLearn， the first thing that we're going to want to do is import the class containing our feature selection method。

 so from SKLarn。 feature selection we import RF， that's just going to be the name of our SK learnearn object。



![](img/f42f03d149c03752aa943a78a9d53119_23.png)

![](img/f42f03d149c03752aa943a78a9d53119_24.png)

![](img/f42f03d149c03752aa943a78a9d53119_25.png)

As we do with our SK learn objects， we're going to initiate the class。

 we're going to set it equal to RFE mod， and we're going to pass in first。

 we will need an actual model， that model which we have ES EST。

 can either be a linear Russian object， a laso object or even a random forest are more complex object。

 as long as that object， as long as that model has feature importances or it has coefficients in order for RFE to recursively eliminate the smallest value。



![](img/f42f03d149c03752aa943a78a9d53119_27.png)

![](img/f42f03d149c03752aa943a78a9d53119_28.png)

![](img/f42f03d149c03752aa943a78a9d53119_29.png)

![](img/f42f03d149c03752aa943a78a9d53119_30.png)

![](img/f42f03d149c03752aa943a78a9d53119_31.png)

![](img/f42f03d149c03752aa943a78a9d53119_32.png)

![](img/f42f03d149c03752aa943a78a9d53119_33.png)

And then we also want to preefine how many features we ultimately want to keep within our model。



![](img/f42f03d149c03752aa943a78a9d53119_35.png)

We then fit the instance on the data and then predict the expected value， so RFE mod。

 which we initiated before， it has the model built in right that's the EST。

 which is either a linear regression， lassso or something more complicated such as random force。



![](img/f42f03d149c03752aa943a78a9d53119_37.png)

![](img/f42f03d149c03752aa943a78a9d53119_38.png)

![](img/f42f03d149c03752aa943a78a9d53119_39.png)

So we're able to fit that and it's going to fit that model to X train and Y train。

 and then we can also ultimately predict given some X test and what it'll do is it'll fit according to the number of features that we want to ultimately keep at the end of the day。



![](img/f42f03d149c03752aa943a78a9d53119_41.png)

![](img/f42f03d149c03752aa943a78a9d53119_42.png)

![](img/f42f03d149c03752aa943a78a9d53119_43.png)

![](img/f42f03d149c03752aa943a78a9d53119_44.png)

And then another class that's available to us is RFEC CVV。



![](img/f42f03d149c03752aa943a78a9d53119_46.png)

And that class， rather than doing feature elimination by looking at feature importance。

 will also incorporate cross validation to ensure that we are doing well on each one of our holdout sets and saying as we eliminate features。

 which one will actually affect the value or our error on that holdout set。



![](img/f42f03d149c03752aa943a78a9d53119_48.png)

![](img/f42f03d149c03752aa943a78a9d53119_49.png)

![](img/f42f03d149c03752aa943a78a9d53119_50.png)

![](img/f42f03d149c03752aa943a78a9d53119_51.png)

So to recap in this section。We reminded ourselves about the idea and the relationship between model complexity and error。

 we started off by recapping the importance of having that hold out set as we want to ensure that。



![](img/f42f03d149c03752aa943a78a9d53119_53.png)

![](img/f42f03d149c03752aa943a78a9d53119_54.png)

![](img/f42f03d149c03752aa943a78a9d53119_55.png)

We as we increase our complexity， we're not also increasing our air。

 so we want to ensure that as we increase complexity， we're also able to generalize well to new data。



![](img/f42f03d149c03752aa943a78a9d53119_57.png)

![](img/f42f03d149c03752aa943a78a9d53119_58.png)

We discuss regularization as an approach to overfitting。

 so introduce how regularizations gives us a means to take a complex model and appropriately tune it to ensure that we have the correct level of complexity on our holdoutset。



![](img/f42f03d149c03752aa943a78a9d53119_60.png)

![](img/f42f03d149c03752aa943a78a9d53119_61.png)

![](img/f42f03d149c03752aa943a78a9d53119_62.png)

We discussed some。

![](img/f42f03d149c03752aa943a78a9d53119_64.png)

Basic approaches to regularization， including Rige， Lasso and El net again。

 each of these just tuning that hyperparmeter of alpha or lambda and then also to keep in mind that moving forward we will use the same technique when we work with much more complex models to ensure that we are also able to reduce complexity using regularization。



![](img/f42f03d149c03752aa943a78a9d53119_66.png)

![](img/f42f03d149c03752aa943a78a9d53119_67.png)

![](img/f42f03d149c03752aa943a78a9d53119_68.png)

![](img/f42f03d149c03752aa943a78a9d53119_69.png)

And then finally， we introduced recursive feature elimination in order to take any model no matter how complex and easily eliminating less important features。



![](img/f42f03d149c03752aa943a78a9d53119_71.png)

![](img/f42f03d149c03752aa943a78a9d53119_72.png)

That closes out our section here after this， we will move into a notebook to go over everything we just learned。

 and I look forward to seeing you there。

![](img/f42f03d149c03752aa943a78a9d53119_74.png)

![](img/f42f03d149c03752aa943a78a9d53119_75.png)