# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P149：60_不平衡类简介.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this next set of videos， we'll begin to hone in on best practices when performing classification on unbalance classes。

Now let's discuss some learning goals for this section。



![](img/970c8c8f18dc6e53b0e04043688f057e_1.png)

In this section， we'll quickly discuss some common issues that arise when we're working with unbalanced classes。



![](img/970c8c8f18dc6e53b0e04043688f057e_3.png)

We'll then discuss some approaches to dealing with unbalanced data at a higher level。



![](img/970c8c8f18dc6e53b0e04043688f057e_5.png)

And with this in mind， we'll mainly be discussing the pros and cons of ups。

 down sampling and resampling to get a balanced data set。

 and we'll discuss what each of these terms mean in just a bit。



![](img/970c8c8f18dc6e53b0e04043688f057e_7.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_8.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_9.png)

So we want to start off by coming back and thinking deeper about our cases with highly unbalanced classes。



![](img/970c8c8f18dc6e53b0e04043688f057e_11.png)

So we see here this example where we have 99% of our cases being in a certain class。



![](img/970c8c8f18dc6e53b0e04043688f057e_13.png)

And with this example in mind， we want to keep in consideration that although we have these different metrics to help measure error for unbalanced classes and can even run a grid search on different hyperpara with a scoring function other than accuracy。

 the classifiers themselves， in order to learn the actual parameters and decisions are built to optimize accuracy specifically。

 they are built to get as many correct as possible， no matter the class。😊。



![](img/970c8c8f18dc6e53b0e04043688f057e_15.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_16.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_17.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_18.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_19.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_20.png)

And hence， they'll often perform poorly on underrepresented classes。

 so this is the problem that we're going to be trying to solve。



![](img/970c8c8f18dc6e53b0e04043688f057e_22.png)

So what are some actual solutions to dealing with this problem of unbalanced data sets？



![](img/970c8c8f18dc6e53b0e04043688f057e_24.png)

The idea should be to try and find a way to actually balance our data set before fitting our model。



![](img/970c8c8f18dc6e53b0e04043688f057e_26.png)

So one option is to downs sampleample。And down sampling here means only taking as many of the larger class of our majority class as there are available of our smaller class。

 of our minority class。 So you see here， we have a lot of the majority class。

 only six of the minority class， so we randomly select only six from our majority class so that we are now working with a balanced data set。

😊。

![](img/970c8c8f18dc6e53b0e04043688f057e_28.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_29.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_30.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_31.png)

Now， up sampling is essentially creating copies of the row of smaller outcome until we have a balance sample。

 So we now， rather than trying to bring down that majority class to 6。

 we try to bring up that minority class to 18。

![](img/970c8c8f18dc6e53b0e04043688f057e_33.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_34.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_35.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_36.png)

So we come up with duplicates of that minority class until we have a balance between majority and minority class。

 And then we end up with this balanced data set that we can use to later on fit our model。



![](img/970c8c8f18dc6e53b0e04043688f057e_38.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_39.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_40.png)

And then finally， we can even do a mix of the two。In this example。



![](img/970c8c8f18dc6e53b0e04043688f057e_42.png)

We are going to be resampling。 so we talked about ups， down sampling。

 Now we're talking about resampling。

![](img/970c8c8f18dc6e53b0e04043688f057e_44.png)

We have six of the minority class， 18 of the majority class。

 and let's say we choose here to try to bring each of those classes to 10。



![](img/970c8c8f18dc6e53b0e04043688f057e_46.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_47.png)

We will then limit the value of that larger class by randomly sampling out 10 of those values。

 and then we can increase the values of that minority class by coming up with duplicates of four those values。

 And then we have a bound class where the size of both the majority and minority class are now equal to 10。



![](img/970c8c8f18dc6e53b0e04043688f057e_49.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_50.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_51.png)

With this in mind in the next video， we will hone in a bit further on the pros and cons of each one of these different methods。



![](img/970c8c8f18dc6e53b0e04043688f057e_53.png)

![](img/970c8c8f18dc6e53b0e04043688f057e_54.png)