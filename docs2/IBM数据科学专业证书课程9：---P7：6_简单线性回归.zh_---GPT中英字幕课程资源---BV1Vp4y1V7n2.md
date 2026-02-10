# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P7：6_简单线性回归.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

Hello and welcome。 In this video， we'll be covering linear regression。

 You don't need to know any linear algebra to understand topics in linear regression。😊。



![](img/5cc5fa07698be71068f7dc9ab34ea734_1.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_2.png)

This high level introduction will give you enough background information on linear regression to be able to use it effectively on your own problems。

 So let's get started。

![](img/5cc5fa07698be71068f7dc9ab34ea734_4.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_5.png)

Let's take a look at this data set。 It's related to the CO2 emission of different cars。

 It includes engine size， cylinders， fuel consumption and CO2 emissions for various car models。



![](img/5cc5fa07698be71068f7dc9ab34ea734_7.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_8.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_9.png)

The question is， given this data set， can we predict the CO2 emission of a car using another field such as engine size。



![](img/5cc5fa07698be71068f7dc9ab34ea734_11.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_12.png)

Quite simply， yes。We can use linear regression to predict a continuous value。

 such as CO2 emission by using other variables。 Linear regression is the approximation of a linear model used to describe the relationship between two or more variables。

😊。

![](img/5cc5fa07698be71068f7dc9ab34ea734_14.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_15.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_16.png)

In simple linear regression， there are two variables。

 a dependent variable and an independent variable。

![](img/5cc5fa07698be71068f7dc9ab34ea734_18.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_19.png)

The key point in the linear regression is that our dependent value should be continuous and cannot be a discrete value。

 However， the independent variables can be measured on either a categorical or continuous measurement scale。



![](img/5cc5fa07698be71068f7dc9ab34ea734_21.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_22.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_23.png)

There are two types of linear regression models。 They are simple regression and multiple regression。

 Simple linear regression is when one independent variable is used to estimate a dependent variable。

 For example， predicting CO2 emission using the engine size variable。

 When more than one independent variable is present。

 the process is called multiple linear regression。 For example。

 predicting CO2 emission using engine size and cylinders of cars。

 Our focus in this video is on simple linear regression。



![](img/5cc5fa07698be71068f7dc9ab34ea734_25.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_26.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_27.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_28.png)

Now， let's see how linear regression works。Okay， so let's look at our data again。



![](img/5cc5fa07698be71068f7dc9ab34ea734_30.png)

To understand linear regression， we can plot our variables here。

 We show engine size as an independent variable and emission as the target value that we would like to predict。

A scatter plot clearly shows the relation between variables where changes in one variable explain or possibly cause changes in the other variable。

Also， it indicates that these variables are linearly related。With linear regression。

 you can fit a line through the data。For instance， as the engine size increases， so do the emissions。

With linear regression， you can model the relationship of these variables。

 A good model can be used to predict what the approximate emission of each car is。

How do we use this line for prediction now？Let us assume for a moment that the line is a good fit of the data。

 We can use it to predict the emission of an unknown car。 For example。

 for a sample car with engine size 2。4， you can find the emission is 214。Now。

 let's talk about what the fitting line actually is。



![](img/5cc5fa07698be71068f7dc9ab34ea734_32.png)

We're going to predict the target value Y in our case。

 using the independent variable engine size represented by x1。



![](img/5cc5fa07698be71068f7dc9ab34ea734_34.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_35.png)

The fit line is shown traditionally as a polynomial in a simple regression problem， a single X。

 the form of the model would be theta 0 plus theta 1 x 1。



![](img/5cc5fa07698be71068f7dc9ab34ea734_37.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_38.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_39.png)

In this equation， Y hat is the dependent variable or the predicted value。

 and x1 is the independent variable。

![](img/5cc5fa07698be71068f7dc9ab34ea734_41.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_42.png)

Theta 0 and theta 1 are the parameters of the line that we must adjust。



![](img/5cc5fa07698be71068f7dc9ab34ea734_44.png)

Theta 1 is known as the slope or gradient of the fitting line， and theta 0 is known as the intercept。



![](img/5cc5fa07698be71068f7dc9ab34ea734_46.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_47.png)

Theta 0 and theta 1 are also called the coefficients of the linear equation。



![](img/5cc5fa07698be71068f7dc9ab34ea734_49.png)

You can interpret this equation as Y hat being a function of x1 or Y hat being dependent of x1。



![](img/5cc5fa07698be71068f7dc9ab34ea734_51.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_52.png)

Now， the questions are， how would you draw a line through the points and how do you determine which line fits best？



![](img/5cc5fa07698be71068f7dc9ab34ea734_54.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_55.png)

Linear regression estimates the coefficients of the line。

 This means we must calculate theta 0 and theta 1 to find the best line to fit the data。



![](img/5cc5fa07698be71068f7dc9ab34ea734_57.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_58.png)

This line would best estimate the emission of the unknown data points。



![](img/5cc5fa07698be71068f7dc9ab34ea734_60.png)

Let's see how we can find this line or to be more precise how we can adjust the parameters to make the line the best fit for the data。



![](img/5cc5fa07698be71068f7dc9ab34ea734_62.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_63.png)

For a moment， let's assume we've already found the best fit line for our data。 Now。

 let's go through all the points and check how well they align with this line。



![](img/5cc5fa07698be71068f7dc9ab34ea734_65.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_66.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_67.png)

Best fit here means that if we have， for instance， a car with engine size x1 equals 5。4。

 and actual CO2 equals 250， its CO2 should be predicted very close to the actual value。

 which is y equals 250 based on historical data。

![](img/5cc5fa07698be71068f7dc9ab34ea734_69.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_70.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_71.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_72.png)

But if we use the fit line， or better to say， using our polynomial with known parameters to predict the CO2 emission。

 it will return Y hat equals 340。

![](img/5cc5fa07698be71068f7dc9ab34ea734_74.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_75.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_76.png)

Now， if you compare the actual value of the emission of the car with what we've predicted using our model。

 you will find out that we have a 90 unit error。 This means our prediction line is not accurate。



![](img/5cc5fa07698be71068f7dc9ab34ea734_78.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_79.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_80.png)

This error is also called the residual error。 So we can say the error is the distance from the data point to the fitted regression line。



![](img/5cc5fa07698be71068f7dc9ab34ea734_82.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_83.png)

The mean of all residual errors shows how poorly the line fits with the whole dataset set。



![](img/5cc5fa07698be71068f7dc9ab34ea734_85.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_86.png)

Mathematically， it can be shown by the equation mean squared error shown as MSE。



![](img/5cc5fa07698be71068f7dc9ab34ea734_88.png)

Our objective is to find a line where the mean of all these errors is minimized。 In other words。

 the mean error of the prediction using the fit line should be minimized。



![](img/5cc5fa07698be71068f7dc9ab34ea734_90.png)

Let's re it more technically。The objective of linear regression is to minimize this M E equation。

 and to minimize it， we should find the best parameters。 theta 0 and theta 1。 Now。

 the question is how to find theta 0 and theta 1 in such a way that it minimizes this error。



![](img/5cc5fa07698be71068f7dc9ab34ea734_92.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_93.png)

How can we find such a perfect line？

![](img/5cc5fa07698be71068f7dc9ab34ea734_95.png)

Or said another way。 How should we find the best parameters for our line。



![](img/5cc5fa07698be71068f7dc9ab34ea734_97.png)

Should we move the line a lot randomly and calculate the MSE value every time and choose the minimum1。

 Not really， actually， we have two options here， option 1。

 we can use a mathematic approach or option 2， we can use an optimization approach。



![](img/5cc5fa07698be71068f7dc9ab34ea734_99.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_100.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_101.png)

Let's see how we can easily use a mathematic formula to find the theta 0 and theta 1。



![](img/5cc5fa07698be71068f7dc9ab34ea734_103.png)

As mentioned before， theta 0 and theta 1 in the simple linear regression are the coefficients of the fit line。

 We can use a simple equation to estimate these coefficients。



![](img/5cc5fa07698be71068f7dc9ab34ea734_105.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_106.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_107.png)

That is， given that it's a simple linear regression with only two parameters and knowing that theta 0 and theta 1 are the intercept and slope of the line。

 we can estimate them directly from our data。

![](img/5cc5fa07698be71068f7dc9ab34ea734_109.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_110.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_111.png)

It requires that we calculate the mean of the independent and dependent or target columns from the data set。



![](img/5cc5fa07698be71068f7dc9ab34ea734_113.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_114.png)

Notice that all of the data must be available to traverse and calculate the parameters。



![](img/5cc5fa07698be71068f7dc9ab34ea734_116.png)

It can be shown that the intercept and slope can be calculated using these equations。



![](img/5cc5fa07698be71068f7dc9ab34ea734_118.png)

We can start off by estimating the value for theta 1。 This is how you can find the slope of a line。

 based on the data。X bar is the average value for the engine size in our data set。

Please consider that we have nine rows here， rows zero to eight。First。

 we calculate the average of x1 and average of y。Then we plug it into the slope equation to find theta 1。

The X， I and Y， I in the equation refer to the fact that we need to repeat these calculations across all values in our data set。

 and I refers to the Ih value of X or Y。Applying all values， we find theta 1 equals 39。

 It is our second parameter。 It is used to calculate the first parameter。

 which is the intercept of the line。Now we can plug theta 1 into the line equation to find theta 0。

It is easily calculated that theta 0 equals 125。74。

So these are the two parameters for the line where theta0 is also called the bias coefficient and theta 1 is the coefficient for the CO2 admission column。

As a side note， you really don't need to remember the formula for calculating these parameters。

 as most of the libraries used for machine learning in Python。

 R and Scala can easily find these parameters for you。

 but it's always good to understand how it works。Now we can write down the polynomial of the line。

So we know how to find the best fit for our data and its equation。Now， the question is。

 how can we use it to predict the emission of a new car based on its engine size？



![](img/5cc5fa07698be71068f7dc9ab34ea734_120.png)

After we found the parameters of the linear equation。

 making predictions is as simple as solving the equation for a specific set of inputs。



![](img/5cc5fa07698be71068f7dc9ab34ea734_122.png)

Imagine we are predicting CO2 emission or Y from engine size or X for the automobile in record number9。



![](img/5cc5fa07698be71068f7dc9ab34ea734_124.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_125.png)

Our linear regression model representation for this problem would be y hat equals theta 0 plus theta 1 x1。



![](img/5cc5fa07698be71068f7dc9ab34ea734_127.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_128.png)

Or if we map it to our data， it would be CO2 emission equals theta0 plus theta 1 engine size。



![](img/5cc5fa07698be71068f7dc9ab34ea734_130.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_131.png)

As we saw， we confined finde theta0， theta 1 using the equations that we just talked about。



![](img/5cc5fa07698be71068f7dc9ab34ea734_133.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_134.png)

Once found， we can plug in the equation of the linear model。 For example。

 let's use theta 0 equals 125， and theta 1 equals 39。



![](img/5cc5fa07698be71068f7dc9ab34ea734_136.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_137.png)

So we can rewrite the linear model as CO2 emission equals 125 plus 39 engine size。



![](img/5cc5fa07698be71068f7dc9ab34ea734_139.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_140.png)

Now， let's plug in the ninth row of our data set and calculate the CO2 emission for a car with an engine size of 2。

4。

![](img/5cc5fa07698be71068f7dc9ab34ea734_142.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_143.png)

So CO2 emission equals 125 plus 39 times 2。4。

![](img/5cc5fa07698be71068f7dc9ab34ea734_145.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_146.png)

Therefore， we can predict that the CO2 emission for this specific car would be 218。6。



![](img/5cc5fa07698be71068f7dc9ab34ea734_148.png)

Let's talk a bit about why linear regression is so useful。 Quite simply。

 it is the most basic regression to use and understand。 In fact。

 one reason why linear regression is so useful is that it's fast。



![](img/5cc5fa07698be71068f7dc9ab34ea734_150.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_151.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_152.png)

It also doesn't require tuning of parameters。 So something like tuning the K parameter in K nearest neighbors or the learning rate in neural networks isn't something to worry about。



![](img/5cc5fa07698be71068f7dc9ab34ea734_154.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_155.png)

Linear regression is also easy to understand and highly interpretable。

 Thanks for watching this video。

![](img/5cc5fa07698be71068f7dc9ab34ea734_157.png)

![](img/5cc5fa07698be71068f7dc9ab34ea734_158.png)