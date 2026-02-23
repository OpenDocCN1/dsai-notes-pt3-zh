# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p90 5_回归介绍.zh_en [BV1Jr421w7wL_p90]

🎼，Previously， you learned that regression models predict the continuous value of a response feature using the values of one or more predictors。



![](img/49269a831cfb3278593a7074beb3f869_1.png)

A variety of regression models are available， and the one you choose will depend on your data and the question you're trying to answer。



![](img/49269a831cfb3278593a7074beb3f869_3.png)

![](img/49269a831cfb3278593a7074beb3f869_4.png)

In this video， you'll learn more about the common linear， polynomial， and tree regression models。

 including how they work and how they are trained。

![](img/49269a831cfb3278593a7074beb3f869_6.png)

Let's start with linear regression。In general， a linear regression model predicts a response value。

By multiplying predictor values。By a set of coefficients。

It is also common to include an additive term called the intercept or bias。



![](img/49269a831cfb3278593a7074beb3f869_8.png)

Although regression typically includes multiple predictor variables。

 to help illustrate the concepts for now， let's look at an example with only one predictor。



![](img/49269a831cfb3278593a7074beb3f869_10.png)

Here， the predictor variable is displayed along the x axis。

 and the response variable is on the y axis。For example。

 let's say you want to estimate how long a taxi trip will take based on its distance。Here。

 the data points represent the data with the trip distance on the X axis and the trip duration on the y axis。

A first attempt at regression may be to find a line that captures the trends seen in this plot。

However， there are many possible lines that could reasonably capture a trend。



![](img/49269a831cfb3278593a7074beb3f869_12.png)

So how are the coefficient values chosen for a given model and data set？



![](img/49269a831cfb3278593a7074beb3f869_14.png)

To start， consider the difference between an observed response value and the value predicted by your model。



![](img/49269a831cfb3278593a7074beb3f869_16.png)

![](img/49269a831cfb3278593a7074beb3f869_17.png)

This is known as the residual。Larger residuals corresponded larger errors。



![](img/49269a831cfb3278593a7074beb3f869_19.png)

While smaller residuals mean smaller errors and thus better predictions。



![](img/49269a831cfb3278593a7074beb3f869_21.png)

Additionally， positive residuals indicate that the observed value is greater than the predicted value。



![](img/49269a831cfb3278593a7074beb3f869_23.png)

While negative residuals indicate the opposite。

![](img/49269a831cfb3278593a7074beb3f869_25.png)

To get an idea of how a model performs over the entire training data set。

 you could average all the residuals。

![](img/49269a831cfb3278593a7074beb3f869_27.png)

However， positive and negative residuals would cancel and result in a small average。

 even if your model is poor。

![](img/49269a831cfb3278593a7074beb3f869_29.png)

So to address this problem， the residuals are instead squared before the average。

 ensuring that all values are positive。

![](img/49269a831cfb3278593a7074beb3f869_31.png)

This process of squaring each individual residual and then taking the average of the squared errors results in the mean squared error of your model。

 or MSE for short。

![](img/49269a831cfb3278593a7074beb3f869_33.png)

![](img/49269a831cfb3278593a7074beb3f869_34.png)

Now you can see that the best linear regression model is the line that gives the smallest mean squared error。



![](img/49269a831cfb3278593a7074beb3f869_36.png)

![](img/49269a831cfb3278593a7074beb3f869_37.png)

When you train the model， you find the coefficients that minimize this value。

While the exact process is a little complicated， MatLp functions automatically take care of it for you。



![](img/49269a831cfb3278593a7074beb3f869_39.png)

Once training is complete， a linear regression model provides an equation that uses the predictor value from a new observation。

To estimate the value of the response。In this case。

 that means being able to predict a trip's duration from its distance。



![](img/49269a831cfb3278593a7074beb3f869_41.png)

Linear regression models have several advantages。 They can be trained quickly。

 They are easy to understand， even for non data scientists。 They are easy to visualize。



![](img/49269a831cfb3278593a7074beb3f869_43.png)

And they offer fast prediction times since they only use basic math。However。

 when you need to predict more complex behaviors， a simple linear model may not be sufficient。



![](img/49269a831cfb3278593a7074beb3f869_45.png)

For instance， when the trend no longer follows a simple straight line。



![](img/49269a831cfb3278593a7074beb3f869_47.png)

It's common to fit a polynomial equation， such as a quadratic to your data。

This is done by including an additional x squared term in your formula。

Now there is an additional term that accounts for the curvature of the line。

But the process of training your model is the same as with a straight line。And in the end。

 the result is a parabola with the smallest mean squared error for the given data。

It's possible to add even more terms beyond quadratic， such as X cubed and so on。

This is known as polynomial regression， and adding these higher order terms can help capture more complex behaviors。



![](img/49269a831cfb3278593a7074beb3f869_49.png)

But before you move on， here's a quick question， iss fitting a polynomial equation still considered linear regression？



![](img/49269a831cfb3278593a7074beb3f869_51.png)

Polynomial regression is just a special case of linear regression。

 where each polynomial term is technically a new predictor variable。To the algorithm。

 this equation is essentially the same as considering two unique predictor variables。



![](img/49269a831cfb3278593a7074beb3f869_53.png)

Furthermore， just like how polynomial terms can be generated by multiplying a variable with itself。



![](img/49269a831cfb3278593a7074beb3f869_55.png)

New terms can also be created by multiplying different variables together。

These additional predictor variables are called interaction terms。



![](img/49269a831cfb3278593a7074beb3f869_57.png)

Interaction terms should be included when the response variable depends on the combined product of predictors。

 in addition to just their individual values。

![](img/49269a831cfb3278593a7074beb3f869_59.png)

For example。A trip's duration depends on the distance。But also the taxi's average speed。Therefore。

By including an interaction term between distance and speed， the model's accuracy can be increased。



![](img/49269a831cfb3278593a7074beb3f869_61.png)

![](img/49269a831cfb3278593a7074beb3f869_62.png)

But what happens when linear regression is insufficient？In this case。

 you can use nonlinear regression。

![](img/49269a831cfb3278593a7074beb3f869_64.png)

There are several types of nonlinear regression models that use entirely different approaches to predict response variables。



![](img/49269a831cfb3278593a7074beb3f869_66.png)

Some other common algorithms in data science are decision trees。

 Gaussian process regression and support vector machines。

The last two are similar to linear regression and that they draw predictions from a continuous equation。

However， their training process and underlying algorithms are more complex。



![](img/49269a831cfb3278593a7074beb3f869_68.png)

Decision trees， on the other hand， are a common and highly adaptable type of model that can perform both regression and classification。



![](img/49269a831cfb3278593a7074beb3f869_70.png)

![](img/49269a831cfb3278593a7074beb3f869_71.png)

So how do they work？Essentially， they ask a series of true false questions about predictor variables in order to group data with similar response variables。



![](img/49269a831cfb3278593a7074beb3f869_73.png)

It's similar， for example， to how you might predict the duration of an upcoming drive from JFK Airport to Times Square。



![](img/49269a831cfb3278593a7074beb3f869_75.png)

Beginning with a data set of previous trip durations for that route。

 you might predict the upcoming duration using the average value。

But notice that there's a lot of variability in a data set that isn't yet accounted for。



![](img/49269a831cfb3278593a7074beb3f869_77.png)

Therefore， you can use questions to divide the data into two groups。For instance。

 which of these trips were taken on a weekend。

![](img/49269a831cfb3278593a7074beb3f869_79.png)

This then provides two average durations to choose from for a prediction。

But there's still variability within the two subsets of data。 so the next question could be。

 was the trip taken during rush hour？

![](img/49269a831cfb3278593a7074beb3f869_81.png)

![](img/49269a831cfb3278593a7074beb3f869_82.png)

This further splits your data and again strengthens the prediction by providing yet another estimated duration that depends on the conditions of the upcoming trip。



![](img/49269a831cfb3278593a7074beb3f869_84.png)

This process of subdividing your data， according to a series of true false questions。

 continues until there's minimal variability within each subset。



![](img/49269a831cfb3278593a7074beb3f869_86.png)

![](img/49269a831cfb3278593a7074beb3f869_87.png)

After the model is trained， to make a prediction， simply follow an upcoming trip as the data point through the series of questions until you end at a representative average duration。



![](img/49269a831cfb3278593a7074beb3f869_89.png)

For instance， let's say it's a weekday。And it's rush hour。 But it's not a holiday。

This example tree model is simple compared to what is possible with large data sets。



![](img/49269a831cfb3278593a7074beb3f869_91.png)

It contains just three splits。And four predictions， which are called leaves。



![](img/49269a831cfb3278593a7074beb3f869_93.png)

However， for large data sets with lots of features。

 tree models can become quite complex with thousands of splits and leaves。



![](img/49269a831cfb3278593a7074beb3f869_95.png)

![](img/49269a831cfb3278593a7074beb3f869_96.png)

Fortunately， the splitting process is handled automatically during training of the model。

Although you do have to set some initial parameters。

 such as the maximum number of splits in order to limit the tree's growth。



![](img/49269a831cfb3278593a7074beb3f869_98.png)

This in turn affects which questions are asked and in what order， which then affects the final model。



![](img/49269a831cfb3278593a7074beb3f869_100.png)

In this video you learned about several options when choosing a regression model Next。

 you'll learn how to use these models and choose one that's appropriate for your application。



![](img/49269a831cfb3278593a7074beb3f869_102.png)

![](img/49269a831cfb3278593a7074beb3f869_103.png)