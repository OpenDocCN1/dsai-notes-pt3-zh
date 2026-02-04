# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P73：24_偏差-方差权衡第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's talk about the biophering's trade off and its relationship to complexity and error。

 as well as overfitting versus underfitting。Now the learning goals for this section will be a quick recap on model complexity versus model error。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_1.png)

We'll define the termsbi and variance and discuss their relationship to model complexity。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_3.png)

We'll then discuss different sources of model error and how that relates to bias invaris。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_5.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_6.png)

And then finally， we'll discuss the bias variance trade off， how that relates to complexity。

 and how we can find the optimal balance between bias variance and complexity versus error。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_8.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_9.png)

So from last time， we recall when building a model， we want training and test errors to be small。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_11.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_12.png)

Right at the middle of this curve so we discussed how if we were too far out to the right then we probably have too complex of a model and then we end up with a training error that's very small because on our training set we can continue to reduce error。

 but on our test set our error is very large。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_14.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_15.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_16.png)

On the other hand， if we're all the way out to the left。

 then both our training error and our test error will ultimately be large。

 so we want to see on our test set can we continually decrease the error by making it more complex？



![](img/7e3bd8ae9243ced201e50e84ba13af4d_18.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_19.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_20.png)

And besides just coming up with a more or less complex model。

 there's also the idea of regularization， which I'm just going to talk to now。

 but we will have a whole video on this after this coming video on bias andvariance。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_22.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_23.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_24.png)

Now， coming back to our polynomial function that we saw earlier。

 this problem can be framed as a choice between different model complexities。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_26.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_27.png)

To recap， our goal here is to fit a polynomial model to each one of our sample points。

 these blue dots。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_29.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_30.png)

And something that we have here that we generally don't have is also the true function。

 which is going to be shown here in blue。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_32.png)

The model can involve polynomials of different degrees， first order， fourth order， 15th order。

 and the air function will continuously decrease as we increase our model order if we're just looking how well we can fit exactly to each one of our sample points。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_34.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_35.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_36.png)

Even though this is actually deviating from our actual underlying function。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_38.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_39.png)

So another way to find the best model is to ask， how well is it actually going to generalize？



![](img/7e3bd8ae9243ced201e50e84ba13af4d_41.png)

When we look out to the lefts， we are probably doing poor at both training and predicting because our model is too simple。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_43.png)

In the middle， this is the just right area because we're getting a low error in terms of training as well as predicting for our holdout set。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_45.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_46.png)

And then finally out to the right， we may do well on training because we fit exactly to each one of the data points。

 but when we get a new data point that will probably be somewhere along the lines of this blue line。

 we'll do a poor job of predicting that value。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_48.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_49.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_50.png)

Now， I want you to keep this in mind as we begin to define the terms bias andvariance in the next slide。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_52.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_53.png)

So here we see a graph that's going to show us。Bs versus variance with low and high bias and low and high variance。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_55.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_56.png)

And starting off with bias， bias is just going to be a tendency to miss。

 So we look at the bottom left corner， then we see that。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_58.png)

We are in the high bias， low variance， so we are consistent。

 but we are consistently missing our target。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_60.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_61.png)

That's our tendency to miss。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_63.png)

Variance is going to be the tendency to be inconsistent， and that's going to be the top right。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_65.png)

T right is going to be low bias。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_67.png)

But high variance， so low bias means you won't have the tendency to miss。

 but you'll be fairly inconsistent。And we are times going to hit our target。

 but we're kind of all over the place here。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_69.png)

Ideally， we want to be in this top left outcome where we have highly consistent predictions that are also close to perfect on average。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_71.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_72.png)

And we want to think about this tendency of our models。

 expectation of out of sample behavior over many training set samples。

 so something like cross validation would refer to our tendency to have high or low variance。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_74.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_75.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_76.png)

As well as high low bias， given our holdout sets， so that's going to allow us to understand whether or not we have high bias。

 high variance， both， high or both low。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_78.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_79.png)

So when we create a model， we have three essential ways by which our models can produce errors in their predictions The models can just be wrong。

 This will generally refer to models that are not doing well in identifying the relationship between our feature and our outcome variables。

 This will generally be a bias model， where our predictions are fairly consistent but due to the model choice not properly defining the relationship between the X and y variable。

 we are consistently getting the wrong prediction。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_81.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_82.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_83.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_84.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_85.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_86.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_87.png)

Now， our model can also be unstable and this will generally relate to models with high variance。

 and we can think to models that are too perfectly identifying the relationship between x and Y so it's actually incorporating。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_89.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_90.png)

Random noise， besides for the actual underlying function。

 And in that effort to perfectly define that relationship， they become unstable in their predictions。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_92.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_93.png)

And then finally there's just unavoidable randomness all our models are going to depend on real world data。

 where there will always be a level of randomness within each one of our data points that we collect that cannot be perfectly predicted。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_95.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_96.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_97.png)

The idea is to find a model that finds the actual relationship while avoiding accidentally trying to incorporate this information that is just random noise。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_99.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_100.png)

Now let's dive deeper into each one of these different causes of the error for our modeling。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_102.png)

First， we're going to discuss high bias， and this will be the tendency for our model to miss the true values when trying to predict。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_104.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_105.png)

Now this will happen due to either missing information or overly simplistic models。

 think we are biased to the simplicity of our model or we are biased to the misrepresentation of our data given that missing data。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_107.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_108.png)

And this will happen when we miss the real patterns all the other。

 and we can associate high bias with the concept of underfitting。

 or there not being enough complexity in our model。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_110.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_111.png)

Now we look at high variances and this will be the tendency for our predictions to fluctuate dramatically。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_113.png)

And this is generally characterized by very high sensitivity of our output to small changes in our input。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_115.png)

If you think about our overfit models that were too complex。

 we notice how a slight change in our x values can end up with a drastically different outcome given the high fluctuation of our model of。

 say， a polynomial 15 model。

![](img/7e3bd8ae9243ced201e50e84ba13af4d_117.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_118.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_119.png)

So if you think about variance variance will thus be associated with overfitting our training model。

 bias is going to be underfitting or bias to a simple model。

 overfitting will be associated with variance where we'll have this high fluctuation within our model。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_121.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_122.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_123.png)

![](img/7e3bd8ae9243ced201e50e84ba13af4d_124.png)

And at the end of the day， we must keep in mind that we will never be able to perfectly model the very large majority of real world data。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_126.png)

We thus must be comfortable with some measure of error and even the best possible models。



![](img/7e3bd8ae9243ced201e50e84ba13af4d_128.png)