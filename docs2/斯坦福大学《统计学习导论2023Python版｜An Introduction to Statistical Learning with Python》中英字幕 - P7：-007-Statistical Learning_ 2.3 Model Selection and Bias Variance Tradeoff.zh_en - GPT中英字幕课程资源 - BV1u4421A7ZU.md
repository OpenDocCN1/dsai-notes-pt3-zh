# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P7：-007-Statistical Learning_ 2.3 Model Selection and Bias Variance Tradeoff.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

Okay， so we've seen a variety of different models from linear models。

 which are rather simple and easy to work with and interpret two more complex models like nearest neighbor Ain and thin plate splines。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_1.png)

And we need to know how to decide amongst these models。

 and so we need a way of assessing model accuracy and when is a model adequate and when may we improve it。

Okay， so suppose we have a model F hat of X that's been put to some training data。

 and we will denote the training data by TR， and that consists of n data pairs X I， Y I。And remember。

 X， the notation of Xi means the Ih observation。And x may be a vector。

 so it may have a bunch of components。 Y I is， is typically a single Y scalar。

And we want to see our wellness model performs。Well。

 we could compute the average squared prediction error over the training data。

So that means we take our y， the observed y， we subtract from it F hat of x。

We square the difference to get rid of the sign， and we just average those over all the training data。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_3.png)

Well， as you may imagine， this may be biased towards more overfoot models。 right。

 We saw with that thin place sp。 We could fit the training data exactly。

 We could make this mean squared error subtrain。 We could make it 0。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_5.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_6.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_7.png)

Instead， we should have possible computed using a fresh test data set which we'll call TE。

 so that's an additional say M data pairs X I， Y I different from the training set。

 and then we compute the similar quantity which well call mean squared error subTE。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_9.png)

And that may be a better reflection of the performance of our model。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_11.png)

Okay， so。Now I'm going to show you some examples。 We got back to one dimensional function fitting。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_13.png)

In the left hand panel we see the black curve which is actually simulated。

 so it's a generating curve， that's a true function that we want to estimate。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_15.png)

The points are data points generated from that curve with error。And then we actually see。

 you have to look carefully in the plot， we see three different models fit to these data is the orange model。

😊，The blue model and the green model， and they ordered in complexity。

 The orange model is a linear model。The blue model is a more flexible model。

 maybe some kind of spline。One dimensional version of the thin plate sp。

 And then the green one is a much more flexible version of that。

 that you can see it gets closer to the data。Now， since this is a。Simulated example。

 we can compute the mean squared error on a very large population of test data。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_17.png)

And so in the right hand plot， we plot the mean squared error。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_19.png)

For this large population of test data， and that's the red curve。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_21.png)

And you'll notice。That。It starts off high。For the very rigid model。

It drops down and becomes quite low。😡，For the in between model， but then for the more flexible model。

 it starts increasing again。Of course， the mean squared error on the training data that's the gray curve。

 just keeps on decreasing because the more flexible the model， the closer it gets to the data point。

But for the mean squared error on the test data， we can see this， there's kind of a magic point。

 which is the point at which it minimizes the mean squared error。😊，And in this case。

 that's this point over here。 and it turns out it's pretty much spot on for our middle。

 the medium flexible model in in this figure。 And if you look closely at the plot。

 you'll see that that the blue curve actually gets fairly close the to the black curve okay。Again。

 because this is a simulation model， the horizontal dotted line is the mean squared error that the true function makes。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_23.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_24.png)

For for data from this population。 And， of course， that is the irreducible error。

 which we call the variance of epsilon。

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_26.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_27.png)

Here's another example of the same kind， but here the true functions is actually very smooth。

Same setup。Well， now we see that the mean squared error， the linear model does pretty well。

 The best model is not much different from the linear model， and the Wiiggly one of course。

 is over 15 again。 and so it's making big prediction errors。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_29.png)

The training error again， keeps on going down。

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_31.png)

And finally， here's quite a wgggly true function on the left。

The linear model does a really lousy job。The most flexible model does about the best。

 The blue model and the green model of are pretty good。

 pretty close together in terms of the mean squared error on the test data。So。

I think this drums home the point again， the training meansque area just keeps on going down。

So this drums home the point that if we want to have a model that has good prediction error。

And that's measured here in terms of mean squared。Predictionre on the test data。

We'd like to be able to estimate this curve and one way you can do that， the red curve。

 you can do that is to have a heldout test data that you can value the performance of your different models on the test data。

 and we're going to talk about ways of doing this later on in the course。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_33.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_34.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_35.png)

I want to tell you about a。One aspect of this， which is called a biovariance trade off。So again。

 we've got a F hat of x， which is fit to the training data。And let's say x0。

 y 0 is is a test observation drawn from the population。

 and we're going to evaluate the model this test at the single test observation。Okay。

And then's suppose the true model is。Given by the function F again。

 where F is the regression function or the conditional expectation in the population。

So let's look at the expected prediction error between F hat at x0， so that's the predicted model。

 the fitted model on the training data evaluated at the New point x node and see how what the expected distance is from the test point y0。

So this expectation averages over the variability of the new Y0。

 as well as the variability that went into the training set used to build F hat。

So it turns out that we can break this。We， we， we can break up this expression into three pieces。

 exactly。The one piece is， again， the irreducible error that comes from the random variation in the new test point y0 about the true function F。

But these other two pieces。Break up the reducible part of the error。

 what we called the reducible part before into two components。One is called the variance of F hat。

And that's a variance that comes from。Having different training sets。

 If I got a new training set and I fit my model again， Id have a different function Air。 And so as I。

If I were to look at many， many different training sets。

 there would be variability in my prediction at x0。And then a quantity called the bias of F hat。

 and what the bias is is the difference between the average。

Prediction at Xnt averaged over all these different training sets and the true effort at Xnt。

And what you have is typically as the flexibility of Ffa increases。

 its variance increases because it's going after the individual training set that you've provided。

 which will of course be different from the next training set。But its bias decreases。

So choosing the flexibility based on average test error amounts to what we call a bias variance trade off。

This will come up a lot in in， in future parts of the course。For those three examples。

 we see the biospher in trade off。 again， in this plot。

 the red curve is the mean squared error in the test data。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_37.png)

And then below it， we have the two components of that mean squared error。

 the two important components which are the bias and the variance。And。In the， in the left plot。

 we've got the， the， the bias decrease in and then flattening off as we get more flexible and the variance increase in。

 And when you add those two components， you get the U shape curve。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_39.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_40.png)

And in the middle and last plots that correspond to the other two examples。

The same decomposition is given and because the nature of that problem changed。

 the trade off is changing。

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_42.png)

Okay， so we've seen now that choosing the amount of flexibility of a model amounts to a biosphereance trade off。

 and depending on the problem， we might want to make that trade off in a different place。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_44.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_45.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_46.png)

And we we can use the validation set or lift our data to help us make that choice。

 but' that's the choice that needs to be made to select the model。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_48.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_49.png)

Now， we've been addressing this in terms of regression problems in the next segment。

 we're going to see how all this works for classification problems。



![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_51.png)

![](img/1fd5348cf5bc6ab4e8c81978cee66a9e_52.png)