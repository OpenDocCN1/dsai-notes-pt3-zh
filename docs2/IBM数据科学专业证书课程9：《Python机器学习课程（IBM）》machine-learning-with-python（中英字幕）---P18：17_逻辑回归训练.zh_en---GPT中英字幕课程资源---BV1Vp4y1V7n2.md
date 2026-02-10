# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P18：17_逻辑回归训练.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_0.png)

Hello and welcome In this video， we'll learn more about training a logistic regression model。 Also。

 we'll be discussing how to change the parameters of the model to better estimate the outcome。😊。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_2.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_3.png)

Finally， we talk about the cost function and gradient descent in logistic regression as a way to optimize the model。

 So let's start。😊。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_5.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_6.png)

The main objective of training and logistic regression is to change the parameters of the model so as to be the best estimation of the labels of the samples in the data set。

 For example， the customer churn。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_8.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_9.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_10.png)

How do we do that in brief， first， we have to look at the cost function and see what the relation is between the cost function and the parameters theta。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_12.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_13.png)

So we should formulate the cost function。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_15.png)

Then using the derivative of the cost function， we can find how to change the parameters to reduce the cost。

 or rather the error。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_17.png)

Let's dive into it to see how it works。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_19.png)

But before I explain it， I should highlight for you that it needs some basic mathematical background to understand it。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_21.png)

However， you shouldn't worry about it as most data science languages like Python。

 R and Scala have some packages or libraries that calculate these parameters for you。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_23.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_24.png)

So let's take a look at it。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_26.png)

Let's first find the cost function equation for a sample case To do this。

 we can use one of the customers in the churn problem。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_28.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_29.png)

There is normally a general equation for calculating the cost。

 The cost function is the difference between the actual values of y and our model output。 Y hat。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_31.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_32.png)

This is a general rule for most cost functions in machine learning。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_34.png)

We can show this as the cost of our model comparing it with actual labels。

 which is the difference between the predicted value of our model and actual value of the target field。

 where the predicted value of our model is sigmoid of theta transpose X。 Usually。

 the square of this equation is used because of the possibility of the negative result。

 And for the sake of simplicity， half of this value is considered as the cost function through the derivative process。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_36.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_37.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_38.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_39.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_40.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_41.png)

Now we can write the cost function for all the samples in our training set， for example。

 for all customers， we can write it as the average sum of the cost functions of all cases。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_43.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_44.png)

It is also called the mean squared error， and as it is a function of a parameter vector theta。

 it is shown as J of theta。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_46.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_47.png)

Okay， good。 We have the cost function。 Now， how do we find or set the best weights or parameters that minimize this cost function。

 The answer is we should calculate the minimum point of this cost function。

 and it'll show us the best parameters for our model。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_49.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_50.png)

Although we can find the minimum point of a function using the derivative of a function。

 there's not an easy way to find the global minimum point for such an equation。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_52.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_53.png)

Given this complexity， describing how to reach the global minimum for this equation is outside the scope of this video。

 So what is the solution。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_55.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_56.png)

Well， we should find another cost function instead， one which has the same behavior。

 but is easier to find its minimum point。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_58.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_59.png)

Let's plot the desirable cost function for our model。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_61.png)

Recall that our model is Y hat。 Our actual value is y， which equals 0 or 1。

 and our model tries to estimate it as we want to find a simple cost function for our model。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_63.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_64.png)

For a moment， assume that our desired value for y is one。

 This means our model is best if it estimates y equals1。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_66.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_67.png)

In this case， we need a cost function that returns zero if the outcome of our model is one。

 which is the same as the actual label。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_69.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_70.png)

And the cost should keep increasing as the outcome of our model gets farther from one。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_72.png)

And cost should be very large if the outcome of our model is close to 0。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_74.png)

We can see that the minus log function provides such a cost function for us。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_76.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_77.png)

It means if the actual value is one and the model also predicts one。

 the minus log function returns0 cost， but if the prediction is smaller than one。

 the minus log function returns a larger cost value。

 so we can use the minus log function for calculating the cost of our logistic regression model。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_79.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_80.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_81.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_82.png)

So if you recall， we previously noted that in general。

 it is difficult to calculate the derivative of the cost function。 Well。

 we can now change it with the minus log of our model。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_84.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_85.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_86.png)

We can easily prove that in the case that desirable y is one。

 the cost can be calculated as minus log Y hat。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_88.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_89.png)

And in the case that desirable y is 0， the cost can be calculated as minus log 1 minus y hat。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_91.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_92.png)

Now we can plug it into our total cost function and rewrite it as this function。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_94.png)

So this is the logistic regression cost function。 As you can see for yourself。

 it penalizes situations in which the class is0 and the model output is one and vice versa。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_96.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_97.png)

Remember， however， that Y hat does not return a class as output， but it's a value of 0 or 1。

 which should be assumed as a probability。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_99.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_100.png)

Now we can easily use this function to find the parameters of our model in such a way as to minimize the cost。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_102.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_103.png)

Okay， let's recap what we've done。Our objective was to find a model that best estimates the actual labels。

 Finding the best model means finding the best parameters theta for that model。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_105.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_106.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_107.png)

So the first question was， how do we find the best parameters for our model？



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_109.png)

Well， by finding and minimizing the cost function of our model， In other words。

 to minimize the J of theta we just defined。The next question is。

 how do we minimize the cost function？

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_111.png)

The answer is using an optimization approach， there are different optimization approaches。

 but we use one of the most famous and effective approaches here， gradient descent。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_113.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_114.png)

The next question is， what is gradient descent。Generally。

 gradient descent is an iterative approach to finding the minimum of a function。Specifically。

 in our case， gradient descent is a technique to use the derivative of a cost function to change the parameter values。

 to minimize the cost or error。 Let's see how it works。

The main objective of gradient descent is to change the parameter values so as to minimize the cost。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_116.png)

How can gradient descent do that， Think of the parameters or weights in our model to be in a two dimensional space。

 For example， theta 1， theta 2 for two feature sets， age and income。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_118.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_119.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_120.png)

Recall the cost function J that we discussed in the previous slides。

 We need to minimize the cost function J， which is a function of variables， theta 1 and theta 2。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_122.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_123.png)

So let's add a dimension for the observed cost or error J function。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_125.png)

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_126.png)

Let's assume that if we plot the cost function based on all possible values of theta 1， theta 2。

 we can see something like this。It represents the error value for different values of parameters。

 That is error， which is a function of the parameters。

 This is called your error curve or error bowl of your cost function。

Recall that we want to use this error bowl to find the best parameter values that result in minimizing the cost value。

Now， the question is， which point is the best point for your cost function？Yes。

 you should try to minimize your position on the error curve。So what should you do。

You have to find the minimum value of the cost by changing the parameters， but which way？

Will you add some value to your weights or deduct some value， and how much would that value be。

You can select random parameter values that locate a point on the bowl。

 You can think of our starting point being the yellow point。

You change the parameters by Delta theta 1 and Delta theta 2 and take one step on the surface。

Let's assume we go down one step in the bowl。As long as we're going downwards。

 we can go one more step。 The steeper the slope， the further we can step。

 and we can keep taking steps。As we approach the lowest point。

 the slope diminishes so we can take smaller steps until we reach a flat surface。

This is the minimum point of our curve and the optimum theta 1， theta 2。What are these steps， really。

 I mean， in which direction should we take these steps to make sure we descend and how big should the steps be。

To find the direction and size of these steps， in other words， to find how to update the parameters。

 you should calculate the gradient of the cost function at that point。

The gradient is the slope of the surface at every point。

 and the direction of the gradient is the direction of the greatest uphill。😊，Now the question is。

 how do we calculate the gradient of a cost function at a point？

If you select a random point on this surface， for example。

 the yellow point and take the partial derivative of J of theta with respect to each parameter at that point。

 it gives you the slope of the move for each parameter at that point。Now。

 if we move in the opposite direction of that slope。

 it guarantees that we go down in the error curve。 For example。

 if we calculate the derivative of J with respect to theta 1。

 we find out that it is a positive number。This indicates that function is increasing as theta1 increases。

 So to decrease J， we should move in the opposite direction。

This means to move in the direction of the negative derivative for theta 1， i。e。 slope。

We have to calculate it for other parameters as well at each step。

The gradient value also indicates how big of a step to take。 If the slope is large。

 we should take a large step because we're far from the minimum。 If the slope is small。

 we should take a smaller step。Gradient descent takes increasingly smaller steps towards the minimum with each iteration。

The partial derivative of the cost function J is calculated using this expression。

If you want to know how the derivative of the J function is calculated。

 you need to know the derivative concept， which is beyond our scope here。 But to be honest。

 you don't really need to remember all the details about it as you can easily use this equation to calculate the gradients。

So in a nutshell， this equation returns the slope of that point。

 and we should update the parameter in the opposite direction of the slope。

A vector of all these slopes is the gradient vector。

 and we can use this vector to change or update all the parameters。

We take the previous values of the parameters and subtract the error derivative。

 This results in the new parameters for theta that we know will decrease the cost。Also。

 we multiply the gradient value by a constant value M， which is called the learning rate。

 Learn rate gives us additional control on how fast we move on the surface。In sum。

 we can simply say gradient descent is like taking steps in the current direction of the slope。

 and the learning rate is like the length of the step you take。So these would be our new parameters。

 notice that it's an iterative operation and in each iteration。

 we update the parameters and minimize the cost until the algorithm converge is on an acceptable minimum。

Okay， let's recap what we've done to this point by going through the training algorithm again。

 step by step。

![](img/6e59001f6a1ca26fc1f0f9432951ae4b_128.png)

Step1， we initialize the parameters with random values。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_130.png)

Step  two， we feed the cost function with the training set and calculate the cost。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_132.png)

We expect a high error rate as the parameters are set randomly。



![](img/6e59001f6a1ca26fc1f0f9432951ae4b_134.png)

Step3， we calculate the gradient of the cost function。

 keeping in mind that we have to use a partial derivative。So to calculate the gradient vector。

 we need all the training data to feed the equation for each parameter。Of course。

 this is an expensive part of the algorithm， but there are some solutions for this。Step4。

 we update the weights with new parameter values。Step 5。

 here we go back to step 2 and feed the cost function again， which has new parameters。

As was explained earlier， we expect less error as we're going down the error surface。

 We continue this loop until we reach a short value of cost or some limited number of iterations。

Step 6， the parameter should be roughly found after some iterations。 This means the model is ready。

 and we can use it to predict the probability of a customer staying or leaving。

Thanks for watching this video。