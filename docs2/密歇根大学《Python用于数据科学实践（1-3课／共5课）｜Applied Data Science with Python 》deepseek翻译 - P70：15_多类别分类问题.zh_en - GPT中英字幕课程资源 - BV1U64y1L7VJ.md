# 密歇根大学《Python用于数据科学实践（1-3课／共5课）｜Applied Data Science with Python 》deepseek翻译 - P70：15_多类别分类问题.zh_en - GPT中英字幕课程资源 - BV1U64y1L7VJ

![](img/c6013a93a49cf19b2ff65683656d598f_0.png)

In the examples we've used so far for classification。

 we've primarily focused on binary classification。Where the target value to be predicted was a binary value。

 it was either a positive or a negative class。In a lot of real world data sets。

The target value to be predicted is actually a category。 So， for example， in our fruit data set。

 there were four different categories of fruit to be predicted， not just two。

So how do we deal with this multi class classification situation with psychic learn？Well。

 fortunately， Psy learn makes it very easy。To learn multi class classification models。Essentially。

 it does this by converting a multi class classification problem into a series of binary problems。

What do I mean by that？Essentially， when you pass in a data set that has a categorical variable for the target value。

 so I can learn to text this automatically。And then， for each class。To be predicted。

PsychitLn creates one binary classifier that predicts that class against all the other classes。So。

 for example， in the fruit data set， there are four categories of fruit， so psit learn。u。

Learns four different binary classifiers。To predict a new data instance。What it then does is。

Takes that data instance， to be predicted。Whose labels to be predicted。

And runs it against each of the binary classifiers in turn。

 and the classifier that has the highest score is the one that。

Whose class it uses as the prediction value？So let's look at a specific example of multiclass classification with this fruit data set。

Here we simply pass in the normal data set that has the value from one to4 as the category of fruit to be predicted。

And we fit it exactly the same way that we would fit。Of。The model as if it were a binary problem。

And in general， if we're just， you know， fitting and then predicting。

All of this would be completely transparent， psychic Learn would simply do the right thing and it would learn multiple classes and it would predict multiple classes and we wouldn't really have to do much else。

However， we can get access to what's happening under the hood， as it were。

If we look at the coefficients and the intercepts of the linear models that result from fitting to the training data。

And this is what this example shows， so what we're doing here is fitting a linear support vector machine。

To the fruit training data。And if we look at the coefficient values。

We'll see that instead of just one pair of coefficients for a single。Linear model。Classifier。

 we actually get four values and these values correspond。

To the four classes of fruit in the training set。And so what PsychicLn has done here is it's created four binary classifiers。

 one for each class。And so you can see there are four pairs of coefficients here。

And there are also four。For intercept values。In this case。The first。

Pair of coefficients corresponds to a classifier that classifies apples。Versus the rest of the fruit。

And。So these pair of coefficients and this intercept。Define a straight line in this case it's this。

 so the apples in this visual are the red points。And so the coefficients of the Apple model define a decision boundary。

 a linear decision boundary。That's。Marked by this red line here。And if you plot it out。

 you'll see that indeed， it has an intercept of negative 3。It's， you know。

 you can actually compute for any data instance using this linear formula what itll predict either Apple or not an apple。

So if we take a specific example， something that has。A height of two and a width of six。

 so some query point here， for example。This is a linear classifier so we can take the coefficients。

This first pair of coefficients here and this first intercept value here。

And these form a linear classifier for apples versus not apples。So we can take the height feature。

Multiply it by the。First coefficient， take the width feature。Multiply it by the second。Coeicient。

 and then add in the third intercept feature this。This third bias term。

And so to predict whether this object that has height of two and width of6 is an apple。

 we simply compute this linear formula。It turns out that the value is positive。Po59。

 And so because that value is greater than or equal to 0。

 that indicates that the model is predicting that the object is indeed an apple。

 and that makes sense， because it's on this side。Of the Apple versus not Apple binary classifier decision boundary。

Similarly， we can take another object， say one who has a height of two and a width of two。

 so in this part of the space over here。And we can plug in those two feature values into the same Apple classifier。

And when we do that， it turns out that。The prediction value of the linear model in that case is negative 2。

3， and that's less than 0。Which。Is on this side of the decision boundary。

 And so the linear model for Apple versus not Apple here is predicting that。

That this object is not an apple。And so。Again， when psychit learn has to predict the class of a new object。

Potentially multiple classes。It will go through each of these binary classifiers in turn。And it will。

Predict the class whose classifier has the highest score for that。That instance。

