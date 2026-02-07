# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P17：16_逻辑回归与线性回归对比.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

![](img/a5a78ddd43e62524716c39605cdaa725_0.png)

Hello and welcome。In this video， we will learn the difference between linear regression and logistic regression。

 We go over linear regression and see why it cannot be used properly for some binary classification problems。

😊。

![](img/a5a78ddd43e62524716c39605cdaa725_2.png)

![](img/a5a78ddd43e62524716c39605cdaa725_3.png)

![](img/a5a78ddd43e62524716c39605cdaa725_4.png)

We also look at the sigmoid function， which is the main part of logistic regression。



![](img/a5a78ddd43e62524716c39605cdaa725_6.png)

Let's start。Let's look at the telecommunication data set again。

The goal of logistic regression is to build a model to predict the class of each customer and also the probability of each sample belonging to a class。



![](img/a5a78ddd43e62524716c39605cdaa725_8.png)

![](img/a5a78ddd43e62524716c39605cdaa725_9.png)

Ideally， we want to build a model Y hat that can estimate that the class of a customer is one。

 given its features is X。

![](img/a5a78ddd43e62524716c39605cdaa725_11.png)

![](img/a5a78ddd43e62524716c39605cdaa725_12.png)

I want to emphasize that why is the label's vector also called actual values that we would like to predict。

 and why hat is the vector of the predicted values by our model。



![](img/a5a78ddd43e62524716c39605cdaa725_14.png)

![](img/a5a78ddd43e62524716c39605cdaa725_15.png)

Mapping the class labels to integer numbers， can we use linear regression to solve this problem？



![](img/a5a78ddd43e62524716c39605cdaa725_17.png)

![](img/a5a78ddd43e62524716c39605cdaa725_18.png)

First， let's recall how linear regression works to better understand logistic regression。



![](img/a5a78ddd43e62524716c39605cdaa725_20.png)

Forget about the churn prediction for a minute and assume our goal is to predict the income of customers in the data set。



![](img/a5a78ddd43e62524716c39605cdaa725_22.png)

This means that instead of predicting churn， which is a categorical value， let's predict income。

 which is a continuous value。 so how can we do this？



![](img/a5a78ddd43e62524716c39605cdaa725_24.png)

![](img/a5a78ddd43e62524716c39605cdaa725_25.png)

Let's select an independent variable such as customer age and predict a dependent variable such as income。



![](img/a5a78ddd43e62524716c39605cdaa725_27.png)

![](img/a5a78ddd43e62524716c39605cdaa725_28.png)

Of course， we can have more features， but for the sake of simplicity。

 let's just take one feature here。 We can plot it and show age as an independent variable and income as the target value we would like to predict with linear regression。

 you can fit a line or polynomial through the data。

 We can find this line through training our model or calculating it mathematically based on the sample sets。

😊。

![](img/a5a78ddd43e62524716c39605cdaa725_30.png)

![](img/a5a78ddd43e62524716c39605cdaa725_31.png)

![](img/a5a78ddd43e62524716c39605cdaa725_32.png)

![](img/a5a78ddd43e62524716c39605cdaa725_33.png)

![](img/a5a78ddd43e62524716c39605cdaa725_34.png)

We'll say this is a straight line through the sample set。



![](img/a5a78ddd43e62524716c39605cdaa725_36.png)

This line has an equation shown as a plus B X1。 Now， use this line to predict the continuous value Y。

 That is， use this line to predict the income of an unknown customer based on his or her age。

 and it is done。What if we want to predict churn？

![](img/a5a78ddd43e62524716c39605cdaa725_38.png)

Can we use the same technique to predict a categorical field such as churnern， Okay， let's see。



![](img/a5a78ddd43e62524716c39605cdaa725_40.png)

Say we're given data on customer churn， and our goal this time is to predict the churn of customers based on their age。



![](img/a5a78ddd43e62524716c39605cdaa725_42.png)

![](img/a5a78ddd43e62524716c39605cdaa725_43.png)

We have a feature age denoted as X1 and a categorical feature churn with two classes， churn is yes。

 and churn is no。

![](img/a5a78ddd43e62524716c39605cdaa725_45.png)

![](img/a5a78ddd43e62524716c39605cdaa725_46.png)

As mentioned， we can map yes and no to interteger values 0 and 1。



![](img/a5a78ddd43e62524716c39605cdaa725_48.png)

How can we model it now， Well， graphically， we could represent our data with a scatter plot。

 But this time， we have only two values for the y axis。 In this plot。

 class 0 is denoted in red and class 1 is denoted in blue。

 Our goal here is to make a model based on existing data to predict if a new customer is red or blue。



![](img/a5a78ddd43e62524716c39605cdaa725_50.png)

![](img/a5a78ddd43e62524716c39605cdaa725_51.png)

![](img/a5a78ddd43e62524716c39605cdaa725_52.png)

Let's do the same technique that we use for linear regression here to see if we can solve the problem for a categorical attribute。

 such as churn。

![](img/a5a78ddd43e62524716c39605cdaa725_54.png)

![](img/a5a78ddd43e62524716c39605cdaa725_55.png)

With linear regression， you again can fit a polynomial through the data。

 which is shown traditionally as A plus B X。

![](img/a5a78ddd43e62524716c39605cdaa725_57.png)

![](img/a5a78ddd43e62524716c39605cdaa725_58.png)

This polynomial can also be shown traditionally as theta 0 plus theta 1 x1。



![](img/a5a78ddd43e62524716c39605cdaa725_60.png)

![](img/a5a78ddd43e62524716c39605cdaa725_61.png)

This line has two parameters， which are shown with vector theta。

 where the values of the vector are theta 0 and theta 1。



![](img/a5a78ddd43e62524716c39605cdaa725_63.png)

![](img/a5a78ddd43e62524716c39605cdaa725_64.png)

We can also show the equation of this line formally as theta transpose x。



![](img/a5a78ddd43e62524716c39605cdaa725_66.png)

And generally， we can show the equation for a multidimensional space as theta transpose x。

 where theta is the parameters of the line in two dimensional space or parameters of a plane in three dimensional space and so on。



![](img/a5a78ddd43e62524716c39605cdaa725_68.png)

![](img/a5a78ddd43e62524716c39605cdaa725_69.png)

![](img/a5a78ddd43e62524716c39605cdaa725_70.png)

As theta is a vector of parameters and is supposed to be multiplied by x。

 it is shown conventionally as transpose theta。

![](img/a5a78ddd43e62524716c39605cdaa725_72.png)

![](img/a5a78ddd43e62524716c39605cdaa725_73.png)

Theta is also called the weights factor orcons of the equation。

 with both these terms used interchangeably。

![](img/a5a78ddd43e62524716c39605cdaa725_75.png)

![](img/a5a78ddd43e62524716c39605cdaa725_76.png)

And X is the feature set， which represents a customer。



![](img/a5a78ddd43e62524716c39605cdaa725_78.png)

Anyway， given a data set， all the feature sets x theta parameters can be calculated through an optimization algorithm。

 or mathematically， which results in the equation of the fitting line。



![](img/a5a78ddd43e62524716c39605cdaa725_80.png)

![](img/a5a78ddd43e62524716c39605cdaa725_81.png)

![](img/a5a78ddd43e62524716c39605cdaa725_82.png)

For example， the parameters of this line are  minus1 and 0。1。

 and the equation for the line is minus1 plus 0。1 x1。



![](img/a5a78ddd43e62524716c39605cdaa725_84.png)

![](img/a5a78ddd43e62524716c39605cdaa725_85.png)

Now， we can use this regression line to predict the churn of the new customer。



![](img/a5a78ddd43e62524716c39605cdaa725_87.png)

For example， for our customer， or let's say a data point with x value of age equals 13。

 we can plug the value into the line formula， and the y value is calculated and returns a number。

 For instance， for P1。 we have theta transpose x equals minus1 plus 0。1 times x1。



![](img/a5a78ddd43e62524716c39605cdaa725_89.png)

![](img/a5a78ddd43e62524716c39605cdaa725_90.png)

![](img/a5a78ddd43e62524716c39605cdaa725_91.png)

![](img/a5a78ddd43e62524716c39605cdaa725_92.png)

![](img/a5a78ddd43e62524716c39605cdaa725_93.png)

Equals minus1 plus 0。1 times 13 equals 0。3。

![](img/a5a78ddd43e62524716c39605cdaa725_95.png)

![](img/a5a78ddd43e62524716c39605cdaa725_96.png)

We can show it on our graph。Now we can define a threshold here， for example， at 0。

5 to define the class。

![](img/a5a78ddd43e62524716c39605cdaa725_98.png)

![](img/a5a78ddd43e62524716c39605cdaa725_99.png)

So we write a rule here for our model Y hat， which allows us to separate class 0 from class 1。

 If the value of theta transpose x is less than 0。5， then the class is 0。 Otherwise。

 if the value of theta transpose x is more than 0。5 then the class is 1。



![](img/a5a78ddd43e62524716c39605cdaa725_101.png)

![](img/a5a78ddd43e62524716c39605cdaa725_102.png)

![](img/a5a78ddd43e62524716c39605cdaa725_103.png)

![](img/a5a78ddd43e62524716c39605cdaa725_104.png)

And because our customers' y value is less than the threshold。

 we can say it belongs to class 0 based on our model。



![](img/a5a78ddd43e62524716c39605cdaa725_106.png)

![](img/a5a78ddd43e62524716c39605cdaa725_107.png)

But there is one problem here。 What is the probability that this customer belongs to class 0。



![](img/a5a78ddd43e62524716c39605cdaa725_109.png)

As you can see， it's not the best model to solve this problem。



![](img/a5a78ddd43e62524716c39605cdaa725_111.png)

Also， there are some other issues which verify that linear regression is not the proper method for classification problems。



![](img/a5a78ddd43e62524716c39605cdaa725_113.png)

![](img/a5a78ddd43e62524716c39605cdaa725_114.png)

So as mentioned， if we use the regression line to calculate the class of a point。

 it always returns a number， such as 3 or negative 2 and so on。



![](img/a5a78ddd43e62524716c39605cdaa725_116.png)

![](img/a5a78ddd43e62524716c39605cdaa725_117.png)

Then we should use a threshold， for example， 0。5， to assign that point to either class of0 or1。



![](img/a5a78ddd43e62524716c39605cdaa725_119.png)

![](img/a5a78ddd43e62524716c39605cdaa725_120.png)

This threshold works as a step function that outputs 0 or1， regardless of how big or small。

 positive or negative the input is。

![](img/a5a78ddd43e62524716c39605cdaa725_122.png)

![](img/a5a78ddd43e62524716c39605cdaa725_123.png)

So using the threshold， we can find the class of a record。 Notice that in the step function。

 no matter how big the value is， as long as it's greater than 0。5， it simply equals 1。



![](img/a5a78ddd43e62524716c39605cdaa725_125.png)

![](img/a5a78ddd43e62524716c39605cdaa725_126.png)

![](img/a5a78ddd43e62524716c39605cdaa725_127.png)

And vice versa， regardless of how small the value y is， the output would be 0 if it is less than 0。5。



![](img/a5a78ddd43e62524716c39605cdaa725_129.png)

![](img/a5a78ddd43e62524716c39605cdaa725_130.png)

In other words， there is no difference between a customer who has a value of one or 1000。

 The outcome would be one。

![](img/a5a78ddd43e62524716c39605cdaa725_132.png)

Instead of having this step function， wouldn't it be nice if we had a smoother line。

 one that would project these values between 0 and 1。



![](img/a5a78ddd43e62524716c39605cdaa725_134.png)

![](img/a5a78ddd43e62524716c39605cdaa725_135.png)

Indeed， the existing method does not really give us the probability of a customer belonging to a clause。

 which is very desirable。

![](img/a5a78ddd43e62524716c39605cdaa725_137.png)

![](img/a5a78ddd43e62524716c39605cdaa725_138.png)

We need a method that can give us the probability of falling in a class as well。

 so what is the scientific solution here？

![](img/a5a78ddd43e62524716c39605cdaa725_140.png)

Well， if instead of using theta transpose X， we use a specific function called sigmoid。

 then sigmoid of theta transpose X gives us the probability of a point belonging to a class instead of the value of y directly。



![](img/a5a78ddd43e62524716c39605cdaa725_142.png)

![](img/a5a78ddd43e62524716c39605cdaa725_143.png)

![](img/a5a78ddd43e62524716c39605cdaa725_144.png)

I'll explain this sigmoid function in a second， but for now， please accept that it will do the trick。



![](img/a5a78ddd43e62524716c39605cdaa725_146.png)

Instead of calculating the value of theta transpose x directly。

 it returns the probability that a theta transpose x is very big or very small。



![](img/a5a78ddd43e62524716c39605cdaa725_148.png)

![](img/a5a78ddd43e62524716c39605cdaa725_149.png)

![](img/a5a78ddd43e62524716c39605cdaa725_150.png)

It always returns a value between 0 and 1， depending on how large the theta transpose x actually is。



![](img/a5a78ddd43e62524716c39605cdaa725_152.png)

Now， our model is sigmoid of theta transpose x， which represents the probability that the output is1 given x。



![](img/a5a78ddd43e62524716c39605cdaa725_154.png)

![](img/a5a78ddd43e62524716c39605cdaa725_155.png)

Now， the question is， what is the syigmoid function？



![](img/a5a78ddd43e62524716c39605cdaa725_157.png)

Let me explain in detail what sigmoid really is。

![](img/a5a78ddd43e62524716c39605cdaa725_159.png)

The sigmoid function， also called the logistic function。

 resembles the step function and is used by the following expression in the logistic regression。



![](img/a5a78ddd43e62524716c39605cdaa725_161.png)

![](img/a5a78ddd43e62524716c39605cdaa725_162.png)

The sigmoid function looks a bit complicated at first。

 but don't worry about remembering this equation。 It'll make sense to you， after working with it。



![](img/a5a78ddd43e62524716c39605cdaa725_164.png)

![](img/a5a78ddd43e62524716c39605cdaa725_165.png)

Notice that in the sigmoid equation， when theta transpose x gets very big。

 the e power minus theta transpose x in the denominator of the fraction becomes almost0。

 and the value of the sigmoid function gets closer to 1。



![](img/a5a78ddd43e62524716c39605cdaa725_167.png)

![](img/a5a78ddd43e62524716c39605cdaa725_168.png)

![](img/a5a78ddd43e62524716c39605cdaa725_169.png)

If theta transpose x is very small， the sigmoid function gets closer to 0。



![](img/a5a78ddd43e62524716c39605cdaa725_171.png)

![](img/a5a78ddd43e62524716c39605cdaa725_172.png)

Depicing on the insigmoid plot， when theta transpose X gets bigger。

 the value of the sigmoid function gets closer to 1。 And also。

 if the theta transpose x is very small， the sigmoid function gets closer to 0。

 So the sigmoid function's output is always between 0 and1。

 which makes it proper to interpret the results as probabilities。



![](img/a5a78ddd43e62524716c39605cdaa725_174.png)

![](img/a5a78ddd43e62524716c39605cdaa725_175.png)

It is obvious that when the outcome of the sigmoid function gets closer to 1。

 the probability of y equals 1， given x goes up， and in contrast。

 when the sigmoid value is closer to 0， the probability of y equals 1， given x is very small。

So what is the output of our model when we use the sigmoid function？



![](img/a5a78ddd43e62524716c39605cdaa725_177.png)

In logistic regression， we model the probability that an input x belongs to the default class y equals1。

 and we can write this formally as probability of y equals 1 given x。



![](img/a5a78ddd43e62524716c39605cdaa725_179.png)

![](img/a5a78ddd43e62524716c39605cdaa725_180.png)

We can also write probability of y belongs to class 0。

 given x is 1 minus probability of y equals1 given x。



![](img/a5a78ddd43e62524716c39605cdaa725_182.png)

![](img/a5a78ddd43e62524716c39605cdaa725_183.png)

For example， the probability of a customer staying with the company can be shown as probability of churn equals one。

 given a customer's income and age， which can be， for instance， 0。8。



![](img/a5a78ddd43e62524716c39605cdaa725_185.png)

![](img/a5a78ddd43e62524716c39605cdaa725_186.png)

And the probability of churn is 0 for the same customer。

 given a customer's income and age can be calculated as 1-0。8 equals 0。2。



![](img/a5a78ddd43e62524716c39605cdaa725_188.png)

![](img/a5a78ddd43e62524716c39605cdaa725_189.png)

![](img/a5a78ddd43e62524716c39605cdaa725_190.png)

So now our job is to train the model to set its parameter values in such a way that our model is a good estimate of probability of y equals1 given x。



![](img/a5a78ddd43e62524716c39605cdaa725_192.png)

![](img/a5a78ddd43e62524716c39605cdaa725_193.png)

In fact， this is what a good classifier model built by logistic regression is supposed to do for us。



![](img/a5a78ddd43e62524716c39605cdaa725_195.png)

![](img/a5a78ddd43e62524716c39605cdaa725_196.png)

Also， it should be a good estimate of probability of y belongs to class 0 given x that can be shown as1 minus sigmoid of theta transpose x。



![](img/a5a78ddd43e62524716c39605cdaa725_198.png)

![](img/a5a78ddd43e62524716c39605cdaa725_199.png)

Now， the question is， how can we achieve this。

![](img/a5a78ddd43e62524716c39605cdaa725_201.png)

We can find theta through the training process， so let's see what the training process is。



![](img/a5a78ddd43e62524716c39605cdaa725_203.png)

Step 1， initialize theta vector with random values， as with most machine learning algorithms。

 For example， -1 or 2。

![](img/a5a78ddd43e62524716c39605cdaa725_205.png)

![](img/a5a78ddd43e62524716c39605cdaa725_206.png)

Step 2， calculate the model output， which is sigmoid of theta transpose X for a sample customer in your training set。



![](img/a5a78ddd43e62524716c39605cdaa725_208.png)

![](img/a5a78ddd43e62524716c39605cdaa725_209.png)

X in theta transpose X is the feature vector values。 For example， the age and income of the customer。

 for instance，2 and 5。 and theta is the confidence or weight that you've set in the previous step。



![](img/a5a78ddd43e62524716c39605cdaa725_211.png)

![](img/a5a78ddd43e62524716c39605cdaa725_212.png)

![](img/a5a78ddd43e62524716c39605cdaa725_213.png)

The output of this equation is the prediction value。 In other words。

 the probability that the customer belongs to class1。



![](img/a5a78ddd43e62524716c39605cdaa725_215.png)

Step 3。Compare the output of our model Y hat， which could be a value of， let's say， 0。

7 with the actual label of the customer， which is， for example， one for churnd。

Then record the difference as our model's error for this customer， which would be 1 minus 0。7。

 which of course equals 0。3。This is the error for only one customer out of all the customers in the training set。

Step 4。Calculate the error for all customers， as we did in the previous steps and add up these errors。

The total error is the cost of your model and is calculated by the model's cost function。

The cost function， by the way， basically represents how to calculate the error of the model。

 which is the difference between the actual and the model's predicted values。

So the cost shows how poorly the model is estimating the customer's labels， therefore。

 the lower the cost， the better the model is at estimating the customer's labels correctly。

And so what we want to do is to try to minimize this cost。Step 5。

 But because the initial values for theta were chosen randomly。

 it's very likely that the cost function is very high。

 So we change the theta in such a way to hopefully reduce the total cost。Step 6。

After changing the values of theta， we go back to step 2。

Then we start another iteration and calculate the cost of the model again。

 And we keep doing those steps over and over， changing the values of theta each time until the cost is low enough。

So this brings up two questions first， how can we change the values of theta so that the cost is reduced across iterations？

And second， when should we stop the iterations。There are different ways to change the values of theta。

 but one of the most popular ways is gradient descent。Also。

 there are various ways to stop iterations， but essentially you stop training by calculating the accuracy of your model and stop it when it's satisfactory。

Thanks for watching this video。