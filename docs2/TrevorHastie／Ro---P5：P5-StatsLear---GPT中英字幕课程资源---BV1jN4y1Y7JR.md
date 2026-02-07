# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P5：P5 StatsLearning Lect3 4c 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/238893ed01c7527bcf8e78d89b65889d_0.png)

Okay， so we've seen a variety of different models from linear models。

 which are rather simple and easy to work with and interpret two more complex models like nearest neighbor Ain and thin plate sps。



![](img/238893ed01c7527bcf8e78d89b65889d_2.png)

![](img/238893ed01c7527bcf8e78d89b65889d_3.png)

And we need to know how to decide amongst these models。

 and so we need a way of assessing model accuracy and when is a model adequate and when may we improve it。



![](img/238893ed01c7527bcf8e78d89b65889d_5.png)

![](img/238893ed01c7527bcf8e78d89b65889d_6.png)

![](img/238893ed01c7527bcf8e78d89b65889d_7.png)

Okay， so suppose we have a model F hat of X that's been put to some training data。

 and we will denote the training data by TR， and that consists of N data pairs X I， Y I。



![](img/238893ed01c7527bcf8e78d89b65889d_9.png)

![](img/238893ed01c7527bcf8e78d89b65889d_10.png)

And remember， X， the notation of Xi means the Ih observation。



![](img/238893ed01c7527bcf8e78d89b65889d_12.png)

![](img/238893ed01c7527bcf8e78d89b65889d_13.png)

And x may be a vector， so it may have a bunch of components。 Y I is is typically a single Y a scalar。



![](img/238893ed01c7527bcf8e78d89b65889d_15.png)

![](img/238893ed01c7527bcf8e78d89b65889d_16.png)

And we want to see our wellness model performs。Well。

 we could compute the average squared prediction error over the training data。



![](img/238893ed01c7527bcf8e78d89b65889d_18.png)

So that means we take our y， the observed y， we subtract from it F hat of x。



![](img/238893ed01c7527bcf8e78d89b65889d_20.png)

![](img/238893ed01c7527bcf8e78d89b65889d_21.png)

We square the difference to get rid of the sign， and we just average those over all the training data。



![](img/238893ed01c7527bcf8e78d89b65889d_23.png)

Well， as you may imagine， this may be biased towards more overfi models。

 right We saw with that thin place sp。 We could fit the training data。 exactly。

 We could make this mean squared error subtrain。 We could make it 0。



![](img/238893ed01c7527bcf8e78d89b65889d_25.png)

![](img/238893ed01c7527bcf8e78d89b65889d_26.png)

![](img/238893ed01c7527bcf8e78d89b65889d_27.png)

Instead， we should have possible computed using a fresh test data set which we'll call TE。

 so that's an additional say M data pairs X I， Y I different from the training set。

 and then we compute the similar quantity which we'll call mean squared error subTE。



![](img/238893ed01c7527bcf8e78d89b65889d_29.png)

![](img/238893ed01c7527bcf8e78d89b65889d_30.png)

![](img/238893ed01c7527bcf8e78d89b65889d_31.png)

And that may be a better reflection of the performance of our model。



![](img/238893ed01c7527bcf8e78d89b65889d_33.png)

![](img/238893ed01c7527bcf8e78d89b65889d_34.png)

Okay， so。Now I'm going to show you some examples。 Weve got back to one dimensional function fitting in。



![](img/238893ed01c7527bcf8e78d89b65889d_36.png)

In the left hand panel， we see the black curve， which is actually simulated。

 so it's a generating curve。 that's a true function that we want to estimate。



![](img/238893ed01c7527bcf8e78d89b65889d_38.png)

![](img/238893ed01c7527bcf8e78d89b65889d_39.png)

The points are data points generated from that curve with error。



![](img/238893ed01c7527bcf8e78d89b65889d_41.png)

And then we actually see， you have to look carefully in the plot。

 we see three different models fit to these data is the orange model。😊。



![](img/238893ed01c7527bcf8e78d89b65889d_43.png)

![](img/238893ed01c7527bcf8e78d89b65889d_44.png)

The blue model and the green model， and they ordered in complexity。

 The orange model is a linear model。

![](img/238893ed01c7527bcf8e78d89b65889d_46.png)

The blue model is a more flexible model， maybe some kind of spline。



![](img/238893ed01c7527bcf8e78d89b65889d_48.png)

One dimensional version of the thin plate sp。 And then the green one is a much more flexible version of that。

 that you can see it gets closer to the data。

![](img/238893ed01c7527bcf8e78d89b65889d_50.png)

![](img/238893ed01c7527bcf8e78d89b65889d_51.png)

![](img/238893ed01c7527bcf8e78d89b65889d_52.png)

Now， since this is a。Simulated example， we can compute the mean squared error on a very large population of test data。



![](img/238893ed01c7527bcf8e78d89b65889d_54.png)

And so in the right hand plot， we plot the mean squared error。😊。



![](img/238893ed01c7527bcf8e78d89b65889d_56.png)

For this large population of test data， and that's the red curve。



![](img/238893ed01c7527bcf8e78d89b65889d_58.png)

And you'll notice。

![](img/238893ed01c7527bcf8e78d89b65889d_60.png)

That。It starts off high。

![](img/238893ed01c7527bcf8e78d89b65889d_62.png)

For the very rigid model。It drops down and becomes quite low。😮。



![](img/238893ed01c7527bcf8e78d89b65889d_64.png)

For the in between model， but then for the more flexible model， it starts increasing again。



![](img/238893ed01c7527bcf8e78d89b65889d_66.png)

Of course， the mean squared error on the training data that's the gray curve。

 just keeps on decreasing because the more flexible the model， the closer it gets to the data point。



![](img/238893ed01c7527bcf8e78d89b65889d_68.png)

![](img/238893ed01c7527bcf8e78d89b65889d_69.png)

But for the mean squared error on the test data， we can see there's kind of a magic point。

 which is the point at which it minimizes the mean squared error。



![](img/238893ed01c7527bcf8e78d89b65889d_71.png)

![](img/238893ed01c7527bcf8e78d89b65889d_72.png)

And in this case that's this point over here and it turns out it's pretty much spot on for our middle。

 the medium flexible model in this figure， and if you look closely at the plot you'll see that the blue curve actually gets fairly close to the black curve okay。



![](img/238893ed01c7527bcf8e78d89b65889d_74.png)

![](img/238893ed01c7527bcf8e78d89b65889d_75.png)

![](img/238893ed01c7527bcf8e78d89b65889d_76.png)

![](img/238893ed01c7527bcf8e78d89b65889d_77.png)

Again， because this is a simulation model， the horizontal dotted line is the mean squared error that the true function makes。



![](img/238893ed01c7527bcf8e78d89b65889d_79.png)

![](img/238893ed01c7527bcf8e78d89b65889d_80.png)

For data from this population， and of course， that is the irreducible error。

 which we call the variant of epsilon。

![](img/238893ed01c7527bcf8e78d89b65889d_82.png)

![](img/238893ed01c7527bcf8e78d89b65889d_83.png)

Here's another example of the same kind， but here the two functions actually very smooth。😊。



![](img/238893ed01c7527bcf8e78d89b65889d_85.png)

![](img/238893ed01c7527bcf8e78d89b65889d_86.png)

Same setup。Well now we see that the mean squared error， the linear model does pretty well。

 the best model is not much different from the linear model。

 and the Wiiggly one of course is over 15 again and so it's making big prediction errors。



![](img/238893ed01c7527bcf8e78d89b65889d_88.png)

![](img/238893ed01c7527bcf8e78d89b65889d_89.png)

![](img/238893ed01c7527bcf8e78d89b65889d_90.png)

The training error， again， keeps on going down。

![](img/238893ed01c7527bcf8e78d89b65889d_92.png)

And finally， years'sza。Quite a wiggggly true function on the left。



![](img/238893ed01c7527bcf8e78d89b65889d_94.png)

The linear model does a really lousy job。The。

![](img/238893ed01c7527bcf8e78d89b65889d_96.png)

The most flexible model does about the best， the blue model and the green model are good。

 pretty close together in terms of the means squared error on the test data。



![](img/238893ed01c7527bcf8e78d89b65889d_98.png)

![](img/238893ed01c7527bcf8e78d89b65889d_99.png)

So。I think this drums home the point again， the training meansque error just keeps on going down。



![](img/238893ed01c7527bcf8e78d89b65889d_101.png)

So this drums home the point that if we want to have a model that has good prediction error。



![](img/238893ed01c7527bcf8e78d89b65889d_103.png)

And that's measured here in terms of mean squared。

![](img/238893ed01c7527bcf8e78d89b65889d_105.png)

Predictionre on the test data。We'd like to be able to estimate this curve and one way you can do that。

 the red curve， you can do that is to have a heldout test data that you can value the performance of your different models on the test data and we're going to talk about ways of doing this later on in the course。



![](img/238893ed01c7527bcf8e78d89b65889d_107.png)

![](img/238893ed01c7527bcf8e78d89b65889d_108.png)

![](img/238893ed01c7527bcf8e78d89b65889d_109.png)

![](img/238893ed01c7527bcf8e78d89b65889d_110.png)

I want to tell you about a。

![](img/238893ed01c7527bcf8e78d89b65889d_112.png)

One aspect of this， which is called a biovariance tradeoff。



![](img/238893ed01c7527bcf8e78d89b65889d_114.png)

So again， we've got an F hat of x， which is fit to the training data。And let's say x0。

 y0 is a test observation drawn from the population。

 and we're going to evaluate the model at the single test observation。



![](img/238893ed01c7527bcf8e78d89b65889d_116.png)

![](img/238893ed01c7527bcf8e78d89b65889d_117.png)

![](img/238893ed01c7527bcf8e78d89b65889d_118.png)

Okay。And then's suppose the true model is。

![](img/238893ed01c7527bcf8e78d89b65889d_120.png)

Given by the function F again， where F is the regression function or the conditional expectation in the population。



![](img/238893ed01c7527bcf8e78d89b65889d_122.png)

So let's look at the expected prediction error between F hat at x0。



![](img/238893ed01c7527bcf8e78d89b65889d_124.png)

So that's the predicted model， the fitted model on the training data evaluated at the new point x node and see how what the expected distance is from the test point y is0。



![](img/238893ed01c7527bcf8e78d89b65889d_126.png)

![](img/238893ed01c7527bcf8e78d89b65889d_127.png)

![](img/238893ed01c7527bcf8e78d89b65889d_128.png)

So this expectation averages over the variability of the new Y0。

 as well as the variability that went into the training set used to build F hat。



![](img/238893ed01c7527bcf8e78d89b65889d_130.png)

![](img/238893ed01c7527bcf8e78d89b65889d_131.png)

So it turns out that we can break this。

![](img/238893ed01c7527bcf8e78d89b65889d_133.png)

We， we can break up this expression into three pieces， exactly。



![](img/238893ed01c7527bcf8e78d89b65889d_135.png)

The one piece is， again， the irreducible error that comes from the random variation in the new test point y0 about the true function F。



![](img/238893ed01c7527bcf8e78d89b65889d_137.png)

![](img/238893ed01c7527bcf8e78d89b65889d_138.png)

But these other two pieces。Break up the reducible part of the error。

 what we called the reducible part before， into two components。



![](img/238893ed01c7527bcf8e78d89b65889d_140.png)

![](img/238893ed01c7527bcf8e78d89b65889d_141.png)

One is called the variance of F hat。And that's a variance that comes from。



![](img/238893ed01c7527bcf8e78d89b65889d_143.png)

Having different training sets， If I got a new training set and I fit my model again。

 I have a different function I。 And so as I。

![](img/238893ed01c7527bcf8e78d89b65889d_145.png)

Where， if I were to look at many， many different training sets。

 there would be variability in my prediction at X 0。



![](img/238893ed01c7527bcf8e78d89b65889d_147.png)

And then a quantity called the bias of F hat。 and what the bias is is the difference between the average。



![](img/238893ed01c7527bcf8e78d89b65889d_149.png)

![](img/238893ed01c7527bcf8e78d89b65889d_150.png)

Prediction at Xnt averaged over all these different training sets and the true effort at Xnt。



![](img/238893ed01c7527bcf8e78d89b65889d_152.png)

And what you have is typically as the flexibility of Ffa increases。

 its variance increases because it's going after the individual training set that you've provided。

 which will of course be different from the next training set。



![](img/238893ed01c7527bcf8e78d89b65889d_154.png)

![](img/238893ed01c7527bcf8e78d89b65889d_155.png)

![](img/238893ed01c7527bcf8e78d89b65889d_156.png)

But its bias decreases。So choosing the flexibility based on average test error amounts to what we call a bias variance trade off。



![](img/238893ed01c7527bcf8e78d89b65889d_158.png)

![](img/238893ed01c7527bcf8e78d89b65889d_159.png)

This will come up a lot in in in future parts of the course。



![](img/238893ed01c7527bcf8e78d89b65889d_161.png)

For those three examples， we see the biospher in straight off。 again， in this plot。

 the red curve is the mean squared error in the test data。



![](img/238893ed01c7527bcf8e78d89b65889d_163.png)

![](img/238893ed01c7527bcf8e78d89b65889d_164.png)

And then below it， we have the two components of that mean squared error。

 the two important components which are the bias and the variance。



![](img/238893ed01c7527bcf8e78d89b65889d_166.png)

![](img/238893ed01c7527bcf8e78d89b65889d_167.png)

And。In the in the left plot， we've got the， the the bias decrease in and then flattening off as we get more flexible and the variance increase in。

 And when you add those two components， you get the U shape curve。



![](img/238893ed01c7527bcf8e78d89b65889d_169.png)

![](img/238893ed01c7527bcf8e78d89b65889d_170.png)

![](img/238893ed01c7527bcf8e78d89b65889d_171.png)

And in the middle and last plots that correspond to the other two examples。



![](img/238893ed01c7527bcf8e78d89b65889d_173.png)

The same decomposition is given and because the nature of that problem changed。

 the trade off is changing。

![](img/238893ed01c7527bcf8e78d89b65889d_175.png)

![](img/238893ed01c7527bcf8e78d89b65889d_176.png)

Okay， so we've seen now that choosing the amount of flexibility of a model amounts to a biospherance trade off。

 and depending on the problem， we might want to make that trade off in a different place。



![](img/238893ed01c7527bcf8e78d89b65889d_178.png)

![](img/238893ed01c7527bcf8e78d89b65889d_179.png)

![](img/238893ed01c7527bcf8e78d89b65889d_180.png)

And we can use a validation set or left our data to help us make that choice。

 but that's the choice that needs to be made to select the model。



![](img/238893ed01c7527bcf8e78d89b65889d_182.png)

![](img/238893ed01c7527bcf8e78d89b65889d_183.png)

Now， we've been addressing this in terms of regression problems in the next segment。

 we're going to see how all this works for classification problems。



![](img/238893ed01c7527bcf8e78d89b65889d_185.png)

![](img/238893ed01c7527bcf8e78d89b65889d_186.png)