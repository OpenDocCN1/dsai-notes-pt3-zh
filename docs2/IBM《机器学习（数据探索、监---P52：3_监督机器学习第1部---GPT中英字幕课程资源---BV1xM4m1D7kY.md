# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P52：3_监督机器学习第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this section， we're going to cover different approaches in regards to supervised machine learning。

 namely the tradeoff between interpretation and prediction。

Now let's go over the learning goals for this section in this section we're going to discuss how our approaches may differ depending on our objectives。

 if it's interpretation， then we'd be understanding the mechanism of our model better versus just prediction where we may not have as strong of an understanding of the underlying model。

 but we optimize for the prediction results。

![](img/8d89efa9105623a9b7bab865eec967a1_1.png)

![](img/8d89efa9105623a9b7bab865eec967a1_2.png)

![](img/8d89efa9105623a9b7bab865eec967a1_3.png)

![](img/8d89efa9105623a9b7bab865eec967a1_4.png)

![](img/8d89efa9105623a9b7bab865eec967a1_5.png)

We will then make this differentiation clear with an example。And finally。

 we will close with some further takeaways when understanding our machine learning framework that we've been going over。



![](img/8d89efa9105623a9b7bab865eec967a1_7.png)

![](img/8d89efa9105623a9b7bab865eec967a1_8.png)

So what do we mean about this difference between our objective being interpretation versus prediction？



![](img/8d89efa9105623a9b7bab865eec967a1_10.png)

Starting with interpretation as our primary objective。

 we're going to be training our model with a focus of finding insights about our data。



![](img/8d89efa9105623a9b7bab865eec967a1_12.png)

![](img/8d89efa9105623a9b7bab865eec967a1_13.png)

In the interpretation approach， we look to our parameters to provide insight into our system。

Generally， this will give us an idea of the different features that are providing the most value in predicting our outcome variable。

 so our focus here is trying to understand the underlying difference in features that are going to affect our outcome variable。



![](img/8d89efa9105623a9b7bab865eec967a1_15.png)

![](img/8d89efa9105623a9b7bab865eec967a1_16.png)

![](img/8d89efa9105623a9b7bab865eec967a1_17.png)

So common workflow is gather X and Y data。

![](img/8d89efa9105623a9b7bab865eec967a1_19.png)

Train our model to learn the parameters that gives the best prediction I。e。

 minimize the loss for our function。

![](img/8d89efa9105623a9b7bab865eec967a1_21.png)

![](img/8d89efa9105623a9b7bab865eec967a1_22.png)

But our focus will be on the parameters themselves rather than the best prediction。

 so while we are indeed finding that best prediction。

 we may choose a less complex model to actually learn。

 so we're optimizing for a specific model with high interpretability rather than a model that may have high prediction power but low interpretability。

 since high interpretability is going to be our focus。



![](img/8d89efa9105623a9b7bab865eec967a1_24.png)

![](img/8d89efa9105623a9b7bab865eec967a1_25.png)

![](img/8d89efa9105623a9b7bab865eec967a1_26.png)

![](img/8d89efa9105623a9b7bab865eec967a1_27.png)

![](img/8d89efa9105623a9b7bab865eec967a1_28.png)

Some examples would include。Customer demographics versus sales data。

 where we care more about the loyalty by segments。

![](img/8d89efa9105623a9b7bab865eec967a1_30.png)

![](img/8d89efa9105623a9b7bab865eec967a1_31.png)

In other words， what's driving sales rather than focusing on predicting what the future sales will be？



![](img/8d89efa9105623a9b7bab865eec967a1_33.png)

Or it could be to figure out the right safety features that will prevent accidents so how can we adjust our safety features to prevent as many accidents as possible。

 rather than just trying to predict how many accidents a certain car will have。

 which would be important its own right， but different in regards to our interpretation versus prediction tradeoff。



![](img/8d89efa9105623a9b7bab865eec967a1_35.png)

![](img/8d89efa9105623a9b7bab865eec967a1_36.png)

![](img/8d89efa9105623a9b7bab865eec967a1_37.png)

![](img/8d89efa9105623a9b7bab865eec967a1_38.png)

Or it could be the effect of our marketing budget on movie revenue。

 so we all know how much should we spend on our marketing budget。

 what is its effectiveness rather than just trying to guess what a certain movie will actually have in boxed office revenue。

 which again is important in its own right but there's going to be a tradeoff in the models that we choose。



![](img/8d89efa9105623a9b7bab865eec967a1_40.png)

![](img/8d89efa9105623a9b7bab865eec967a1_41.png)

![](img/8d89efa9105623a9b7bab865eec967a1_42.png)

![](img/8d89efa9105623a9b7bab865eec967a1_43.png)

Now how do we think of this in regards to prediction？

So while the interpretation objective focused on the output of the parameters。



![](img/8d89efa9105623a9b7bab865eec967a1_45.png)

With the prediction approach， we're focusing just on how well our predictions will do compared to the actual values。



![](img/8d89efa9105623a9b7bab865eec967a1_47.png)

![](img/8d89efa9105623a9b7bab865eec967a1_48.png)

So the focus will be just on comparing the values of YP。

 our predicted values to why our actual values。

![](img/8d89efa9105623a9b7bab865eec967a1_50.png)

![](img/8d89efa9105623a9b7bab865eec967a1_51.png)

The focus here will be on performance metrics， this will just be some quantitative measure of the closeness between YP。

 again， our predicted values and our actual values。



![](img/8d89efa9105623a9b7bab865eec967a1_53.png)

![](img/8d89efa9105623a9b7bab865eec967a1_54.png)

Without focusing on interpretability， we risk having a black box model。



![](img/8d89efa9105623a9b7bab865eec967a1_56.png)

Now this will happen often when we move to more complicated models like deep learning。



![](img/8d89efa9105623a9b7bab865eec967a1_58.png)

InSome cases， all we care about is coming up with the best prediction。

 and it's possible we don't understand exactly why our model works。

 but it scores much better in regards to our different performance metrics。



![](img/8d89efa9105623a9b7bab865eec967a1_60.png)

![](img/8d89efa9105623a9b7bab865eec967a1_61.png)

![](img/8d89efa9105623a9b7bab865eec967a1_62.png)

So some examples where we'd want to focus more on prediction。



![](img/8d89efa9105623a9b7bab865eec967a1_64.png)

We may not care to have or have the power to control many of the features for customer churn。

 all we care about is correctly predicting the likelihood of a certain customer to churn。



![](img/8d89efa9105623a9b7bab865eec967a1_66.png)

![](img/8d89efa9105623a9b7bab865eec967a1_67.png)

![](img/8d89efa9105623a9b7bab865eec967a1_68.png)

When predicting whether a certain customer will default。

 we will care much more about getting it right than getting the underlying interpretation。



![](img/8d89efa9105623a9b7bab865eec967a1_70.png)

![](img/8d89efa9105623a9b7bab865eec967a1_71.png)

And then given past purchase history， what we can predict is just the future purchases。

 and that may be more important than trying to figure out what the underlying factor is in regards to figuring out those future purchases。



![](img/8d89efa9105623a9b7bab865eec967a1_73.png)

![](img/8d89efa9105623a9b7bab865eec967a1_74.png)

![](img/8d89efa9105623a9b7bab865eec967a1_75.png)

Now， for all of these examples， we obviously would love to have interpretability of the underlying model。



![](img/8d89efa9105623a9b7bab865eec967a1_77.png)

But if we think back to the interpretability examples just a slide ago。

 we obviously also wanted good prediction for those。



![](img/8d89efa9105623a9b7bab865eec967a1_79.png)

The idea is that there's often going to be a tradeoff and when you're using supervised machine learning for your own business example。

 you'll have to think between choosing between a model that has high interpretability and a high level of prediction。

 and that will have to be defined by your given business objective。



![](img/8d89efa9105623a9b7bab865eec967a1_81.png)

![](img/8d89efa9105623a9b7bab865eec967a1_82.png)

![](img/8d89efa9105623a9b7bab865eec967a1_83.png)

![](img/8d89efa9105623a9b7bab865eec967a1_84.png)

![](img/8d89efa9105623a9b7bab865eec967a1_85.png)