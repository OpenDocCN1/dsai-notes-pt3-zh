# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p24 P24 Lecture 24： Regression Recap for Interviews [BV1RusDz1EXd_p24]

Hello everyone， welcome to the next session or the next lecture of the machine learning Tea by Doing project。

Up till now， we have looked at several lectures for regression。And I thought it would be a good。

Learning opportunity to make a separate lecture， which。

Describes the summary of the important things in the regression and also gives a recap of whatever we have learned so far。

This will be useful if you are preparing for interviews instead of going through all the lectures separately。

 you can go through this concise lecture to revise your concepts。

So let us start we will be looking at four things especially。

 we will be looking at ordinarily square， we will be looking at regularization。

 then we will be looking at gradient descent and stochastic gradient descent and finally we will be looking at training versus generalization error。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_1.png)

So let's start with the problem at hand in the first place。

 the linear regression problem looks something like this。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_3.png)

We have X， Y pairs。And we have to find。TheThat hypothesis。

Wwhich not only classifies the training data， not classifier or should not use the classifierifies。

 which not only has a good prediction on the training data。

 but it has a good prediction on the test data as well。So。

 in the case of one dimensions the hypothesis might look like this。

 so the general form of the hypothesis y is equal to theta transpose x plus theta not and the main world which is used throughout regression is predict so we are really interested in predicting new things if we have been given the data of whether up till now we have to predict the weather at a future time point。

If we have been given the data of stock prices， let's say all of these points are stock price data and if I give you a new x point here which is the input can you predict the stock price at that particular data so the key word in the regression is prediction so it is very different from classification in that sense so this is our hypothesis class。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_5.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_6.png)

Our loss function is。The squared loss。Which is basically the hypothesis。

Minus the actual whole square。And summation were all the points。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_8.png)

And analytically， this loss is also represented as。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_10.png)

And。Of theta comma theta n is equal to sigma， i goes from1 to n。呃。Theta transpose X， X。

 I plus theta n minus Y I。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_12.png)

The whole square。Basically we find the hypothesis prediction and the true value we subtract it and take a least square summation for all the points in our data set that is the loss function。

One more thing which is frequently asked in interviews is。

Why do we use a squared loss function and why not a modulus loss function？



![](img/e65ab669abb5b4b5cc5a58340642d6d5_14.png)

So the key difference between these two is that the modulus loss function looks something like this and the square loss function looks something like this。

 the reason we don't use the modulus is that this this is not differentiable at x equal to 0。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_16.png)

Not differentiable and generally it does not have good properties。So that's why。

So this is moduls of x and this is equal to x square that's why x square is used and modululus of x is not generally used in the regression for loss function。

Definition because the absolute function is not differentiable at x equal to 0。

 very key point to remember okay now let's move to the objective function。

 so the case one is no regularization。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_18.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_19.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_20.png)

The case1 is no regularization where the objective function J。Then just becomes our loss function。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_22.png)

Which is equal to sigma， Y should add one by n here。When by n， I goes from one to n。

Theta transpose X plus theta n。Minus y I， the whole square。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_24.png)

The main idea here is that we want to find the theta and the。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_26.png)

Theta node， which is also called as theta node theta star and theta node star。

 these are the optimal values which minimize J。Now， it turns out that。

This particular problem of finding the minima of this square draw in regression is also called as the ordinary。

L square。This is also called as the ordinary least square problem。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_28.png)

And the beauty of this problem is that。So it's also called OLS。

And the beauty of this problem is that。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_30.png)

It has a closed form analytical solution。Which is not true for many machine learning algorithms。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_32.png)

And this is how the closed form solution looks like。

 So first we have to find we have to define new mates， So we define a W matrix like this。

 We first have a column of ones。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_34.png)

This is let's say my first point， X1。This is my second point dot dot dot this is my last point X n I am doing this for the case of one dimension。

 then we define another vector called St which is the target values and that just a collection of y1 to yn。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_36.png)

The main thing here to remember is w has this augmented called as the augmented matrix because it has this column of ones。

 the reason this one is there is so that theta can be defined like this theta 0 dot dot dot theta 1 and theta n。

 so this offset value。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_38.png)

This offset value。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_40.png)

Is incorporated。In a single vector and that's why we have these columns of near。

If there are more dimensions then it will just be added in the rows。

 so remember the rows here is one training data point so one the row。

Is one training data point the second row is the second training data point etca。

 but you have this column of ones。That's why I always remember the dimensions the first row is the first training data point。

 second row is the second training data point， etcter。Once these vectors are defined。

 it turns out that once you find the gradient of this loss function with respect to theta and with respect to theta not。

 and if you define J in terms of matrixes instead of a vectorized summation。

 it turns out that the optimal theta star is given by this formula。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_42.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_43.png)

W transpose W inverse， W transpose T。This is the beauty of the OLS because it's a closed form solution。

So we are lucky in this case， this look won't keep on happening for other machine learning algorithms。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_45.png)

Now， it turns out that。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_47.png)

Although we are lucky here to have a closed form solution there are still problems with respect to the solution and this is often asked in interviews。

 the first problem is that this matrix if you look it has the dimensions of D by D。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_49.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_50.png)

So， if you are in one dimensions or two dimensions it is fine the inverse is very easy to compute。

 but lets say if if we do a feature transformation to a 15 dimension matrix。

 so the time it takes to inverse a matrix is of the order of d cube。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_52.png)

So if d is equal to1， then the time is order of1， but if d is equal to。10。

 so d is equal to 1 time is order of 1， but if d is equal to 10。

 then the time it takes to universe this matrix is of the order of  thousand。

So it takes thousand times more amount of time to calculate this in and that's a big problem for us。

Because。The reason it' is a big problem is because it will take a huge amount of computational time to calculate this inverse in the first place。

And we don't want that。

![](img/e65ab669abb5b4b5cc5a58340642d6d5_54.png)

So that is the problem of the closed form OLS solution and that is the reason why we move to the second thing which we are going to look at today that is called as regularization。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_56.png)

Well， another problem here is that what if the inverse does not exist？

So it turns out that if the input features are correlated with each other， so for example。

 if one input is one comma2 second is two comma4 third is three comma。6。

 these are clearly correlated with each other。 these inputs so you can find。

One input based or another input etcter。 So the thing is if the input vectors are correlated with each other。

 then it turns out that it's very difficult to take the inverse。 In fact。

 the inverse of that particular matrix does not exist So what do we do in that particular case So now we move towards regularization and regularization actually solves two problems for us the first problem which it solves is that it prevents overfitting。



![](img/e65ab669abb5b4b5cc5a58340642d6d5_58.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_59.png)

![](img/e65ab669abb5b4b5cc5a58340642d6d5_60.png)

And remember， this can be asked in interviews， why do we use？

