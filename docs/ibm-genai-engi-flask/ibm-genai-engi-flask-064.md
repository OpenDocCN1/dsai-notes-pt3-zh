# 064：IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p64 6_简单线性回归.zh_en -BV1NAq6Y9E7z_p64-

Hello and welcome。 In this video， we'll be covering linear regression。

 You don't need to know any linear algebra to understand topics in linear regression。😊。

This high level introduction will give you enough background information on linear regression to be able to use it effectively on your own problems。

 So let's get started。

![](img/1741bd5aa93824828b1428ddbbc62b95_1.png)

Let's take a look at this data set。 It's related to the CO2 emission of different cars。

 It includes engine size， cylinders， fuel consumption and CO2 emissions for various car models。

The question is， given this data set， can we predict the CO2 emission of a car using another field such as engine size？

Quite simply， yes。We can use linear regression to predict a continuous value。

 such as CO2 emission by using other variables。 Linear regression is the approximation of a linear model used to describe the relationship between two or more variables。

😊，In simple linear regression， there are two variables。

 a dependent variable and an independent variable。The key point in the linear regression is that our dependent value should be continuous and cannot be a discrete value。

 However， the independent variables can be measured on either a categorical or continuous measurement scale。



![](img/1741bd5aa93824828b1428ddbbc62b95_3.png)

There are two types of linear regression models。 They are simple regression and multiple regression。

 Sple linear regression is when one independent variable is used to estimate a dependent variable。

 For example， predicting CO2 emission using the engine size variable。

 when more than one independent variable is present。

 The process is called multiple linear regression。 For example。

 predicting CO2 emission using engine size and cylinders of cars。

 Our focus in this video is on simple linear regression。



![](img/1741bd5aa93824828b1428ddbbc62b95_5.png)

Now， let's see how linear regression works。Okay， so let's look at our data again。



![](img/1741bd5aa93824828b1428ddbbc62b95_7.png)

To understand linear regression， we comp plot our variables here。

 We show engine size as an independent variable and emission as the target value that we would like to predict。

A scatter plot clearly shows the relation between variables where changes in one variable explain or possibly cause changes in the other variable。

Also， it indicates that these variables are linearly related。With linear regression。

 you can fit a line through the data。For instance， as the engine size increases， so do the emissions。

With linear regression， you can model the relationship of these variables。

 a good model can be used to predict what the approximate emission of each car is。

How do we use this line for prediction now？Let us assume for a moment that the line is a good fit of the data。

 We can use it to predict the emission of an unknown car。 For example。

 for a sample car with engine size 2。4， you can find the emission is 214。



![](img/1741bd5aa93824828b1428ddbbc62b95_9.png)

Now let's talk about what the fitting line actually is。

We're going to predict the target value Y in our case。

 using the independent variable engine size represented by x1。

The fit line is shown traditionally as a polynomial in a simple regression problem， a single X。

 the form of the model would be theta 0 plus theta 1 x 1。In this equation。

 Y hat is the dependent variable or the predicted value， and x1 is the independent variable。

Theta 0 and theta 1 are the parameters of the line that we must adjust。

Theta 1 is known as the slope or gradient of the fitting line， and theta 0 is known as the intercept。

Theta 0 and theta 1 are also called the coefficients of the linear equation。

You can interpret this equation as Y hat being a function of x1 or Y hat being dependent of x1。Now。

 the questions are， how would you draw a line through the points and how do you determine which line fits best？

Linear regression estimates the coefficients of the line。

 This means we must calculate theta 0 and theta 1 to find the best line to fit the data。

This line would best estimate the emission of the unknown data points。

Let's see how we can find this line or to be more precise how we can adjust the parameters to make the line the best fit for the data。



![](img/1741bd5aa93824828b1428ddbbc62b95_11.png)

For a moment， let's assume we've already found the best fit line for our data。 Now。

 let's go through all the points and check how well they align with this line。

Best fit here means that if we have， for instance， a car with engine size x1 equals 5。4。

 and actual CO2 equals 250， its CO2 should be predicted very close to the actual value。

 which is y equals 250 based on historical data。But if we use the fit line， or better to say。

 using our polynomial with known parameters to predict the CO2 emission。

 it will return Y hat equals 340。Now， if you compare the actual value of the emission of the car with what we've predicted using our model。

 you will find out that we have a 90 unit error。 This means our prediction line is not accurate。

This error is also called the residual error， so we can say the error is the distance from the data point to the fitted regression line。

The mean of all residual errors shows how poorly the line fits with the whole dataset set。

Mathematically， it can be shown by the equation mean squared error， shown as MSE。

Our objective is to find a line where the mean of all these errors is minimized。 In other words。

 the mean error of the prediction using the fit line should be minimized。

Let's reword it more technically。The objective of linear regression is to minimize this M S E equation。

 and to minimize it， we should find the best parameters。 theta 0 and theta 1。 Now， the question is。

 how to find theta 0 and theta 1 in such a way that it minimizes this error。

 How can we find such a perfect line。Or said another way。

 How should we find the best parameters for our line。

Should we move the line a lot randomly and calculate the MSE value every time and choose the minimum one。

 Not really， actually， we have two options here， option1。

 we can use a mathematic approach or option two， we can use an optimization approach。



![](img/1741bd5aa93824828b1428ddbbc62b95_13.png)

Let's see how we can easily use a mathematic formula to find the theta 0 and theta 1。

As mentioned before， theta 0 and theta 1 in the simple linear regression are the coefficients of the fit line。

 We can use a simple equation to estimate these coefficients。That is。

 given that it's a simple linear regression with only two parameters and knowing that theta 0 and theta 1 are the intercept and slope of the line。

 we can estimate them directly from our data。It requires that we calculate the mean of the independent and dependent or target columns from the data set。

Notice that all of the data must be available to traverse and calculate the parameters。

It can be shown that the intercept and slope can be calculated using these equations。

We can start off by estimating the value for theta 1。

 This is how you can find the slope of a line based on the data。

X bar is the average value for the engine size in our data set。

Please consider that we have nine rows here， rows0 to8。First。

 we calculate the average of x1 and average of y。

![](img/1741bd5aa93824828b1428ddbbc62b95_15.png)

Then we plug it into the slope equation to find theta 1。The X， I and Y。

 I in the equation refer to the fact that we need to repeat these calculations across all values in our data set。

 and I refers to the Ih value of X or Y。Applying all values， we find theta 1 equals 39。

 It is our second parameter。 It is used to calculate the first parameter。

 which is the intercept of the line。Now we can plug theta 1 into the line equation to find theta 0。

It is easily calculated that theta 0 equals 125。74。So these are the two parameters for the line。

 where theta0 is also called the bias coefficient and theta 1 is the coefficient for the CO2 admission column。

As a side note， you really don't need to remember the formula for calculating these parameters。

 as most of the libraries used for machine learning in Python。

 R and Scala can easily find these parameters for you。

 but it's always good to understand how it works。Now we can write down the polynomial of the line。

So we know how to find the best fit for our data and its equation。Now the question is。

 how can we use it to predict the emission of a new car based on its engine size？



![](img/1741bd5aa93824828b1428ddbbc62b95_17.png)

After we found the parameters of the linear equation。

 making predictions is as simple as solving the equation for a specific set of inputs。

Imagine we are predicting CO2 emission or Y from engine size or X for the automobile in record number9。

Our linear regression model representation for this problem would be y hat equals theta0 plus theta 1 x1。

Or if we map it to our data set， it would be CO2 emission equals theta 0 plus theta 1 engine size。

As we saw， we confined find theta0， theta 1 using the equations that we just talked about。Once found。

 we can plug in the equation of the linear model。 For example， let's use theta 0 equals 125。

 and theta 1 equals 39。So we can rewrite the linear model as CO2 emission equals 125 plus 39 engine size。

Now， let's plug in the ninth row of our data and calculate the CO2 emission for a car with an engine size of 2。

4。So CO2 emission equals 125 plus 39 times 2。4。Therefore。

 we can predict that the CO2 emission for this specific car would be 218。6。



![](img/1741bd5aa93824828b1428ddbbc62b95_19.png)

Let's talk a bit about why linear regression is so useful。 Quite simply。

 it is the most basic regression to use and understand。 In fact。

 one reason why linear regression is so useful is that it's fast。

It also doesn't require tuning of parameters。 So something like tuning the K parameter in K nearest neighbors or the learning rate in neural networks isn't something to worry about。

Linear regression is also easy to understand， and highly interpretable。

Thanks for watching this video。

![](img/1741bd5aa93824828b1428ddbbc62b95_21.png)