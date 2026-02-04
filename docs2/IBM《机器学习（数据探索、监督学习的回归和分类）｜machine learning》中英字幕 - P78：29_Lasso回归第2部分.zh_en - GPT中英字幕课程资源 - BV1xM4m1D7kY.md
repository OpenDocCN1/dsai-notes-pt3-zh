# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P78：29_Lasso回归第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now I want to get into elastic net by first thinking about the question。

 how are we going to choose between our different models？



![](img/fdd602cfb623c407cc6f259e6c2b07d7_1.png)

As before， if our goal is going to be prediction accuracy。

 we can use validation to give us a means of figuring out which models and which hyperparameters are optimal on our holdouts。

 so how well will each one of our models actually generalize to new data。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_3.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_4.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_5.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_6.png)

If our goal is interpretability， Lasso has this extra bonus of eliminating features that are not as important。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_8.png)

Of course we also must be cautious on the other hand。

 as our model may truly depend on many of the features。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_10.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_11.png)

Also， if timing is a priority， we should also highlight that again。

 the ridge regression will be more computationally efficient。

 so things to keep in mind when deciding between ridge and Lasso。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_13.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_14.png)

Which one is going to do better on a holdout set？

![](img/fdd602cfb623c407cc6f259e6c2b07d7_16.png)

Which one is going to give you higher interpretability with Laso being able to？



![](img/fdd602cfb623c407cc6f259e6c2b07d7_18.png)

Get rid of many of the coefficients。 And then finally， with the ridge。

 we're able to come up with a more computationally efficient algorithm。 And also。

 you may want to penalize certain weights even higher， which the。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_20.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_21.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_22.png)

Rich regression will do for you。Now elastic net， as we see here in the formula。

 is a means of coming up with a hybrid approach between Ridge and Lasso。

 the idea here being that you have your lambmbda all the way out here to the left。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_24.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_25.png)

Decide the portion you want to penalize higher coefficients in general。

And then the alpha value that we see will represent the percentage that you attribute to the L2 and L1 weights to the ridge and regression weights。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_27.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_28.png)

Thus， we're introducing a third hybrid option besides Ridge and Lasso， which again。

 we should optimize using this cross validation method that we saw earlier to find these optimal hyperparameters。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_30.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_31.png)

So elasticasticnet again is going to be a mixture of Rige and lassso The idea is can we get the best of both worlds？



![](img/fdd602cfb623c407cc6f259e6c2b07d7_33.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_34.png)

And this mixture is going to be determined by here we have it written as lambda 1 and lambda 2。

 but again this is going to be some lambda value， which is going to give you the weight for how much you're going to penalize higher coefficients and then how much do you want to attribute that lambda to either the absolute value of the coefficients or the square of those coefficients。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_36.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_37.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_38.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_39.png)

And the resulting effects of using the elastic net will be assuming that you choose the correct lambmbdas will be the same where we have either underfitting。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_41.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_42.png)

Perfectly fitting or overfitting our underlying model。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_44.png)

And the goal here， or what we see here is that the two lambda values are equal。

 these obviously can be different depending which one you want to attribute more weight to。

 whether you want to attribute more weight to the square of the coefficients。

 the absolute value of the coefficients again with Lassso if you have more weight towards the absolute value。

 you'll be more likely to remove some of your coefficients， if you use the ridge。

 then you'll be more likely to penalize higher weights。



![](img/fdd602cfb623c407cc6f259e6c2b07d7_46.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_47.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_48.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_49.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_50.png)

![](img/fdd602cfb623c407cc6f259e6c2b07d7_51.png)