# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p18 P18 ML Teach by Doing Lecture 18： Logistic Regression from the ground up [BV1RusDz1EXd_p18]

Hello everyone， welcome to the day 18 of the Mach Learning teach by doinging project。



![](img/2b260802cb87f9d09683d595fd90fa8f_1.png)

In this particular lecture， we will put all the pieces of the puzzle together。

For logistic regression。

![](img/2b260802cb87f9d09683d595fd90fa8f_3.png)

Up till now， we have looked at defining the sigmoid hypothesis。

Defining the cross entropy loss function， and in the last lecture we also looked at gradient descent and how it works。

We now have all the toolkit， which is needed。To implement the entire logistic regression from start to end from scratch。

When you go for coding interviews or machine learning job interviews。

There is a question which interviewers typically like to ask where they ask you to implement the entire logistic regression from scratch。

And many candidates are not able to do it because their foundations of logistic regression are not clear。

They know how to just use the logistic regression command。

 which is provided by Python psychit learn package， but they don't know the implementation behind it。

 nor do they know the mathematics behind it。Today we will not just learn the mathematics。

 but we will learn in the coding also。We will do both of these things so that whenever someone asks you this question you are comfortable with the foundations from scratch entirely and you will also able to code the logistic regression from scratch in Python this lecture will assume some basic knowledge of matis。



![](img/2b260802cb87f9d09683d595fd90fa8f_5.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_6.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_7.png)

And some very basic knowledge of linear algebra。And when I come to that part I'll also let you know that what all knowledge you need and if you don't have that you might need to revise your concepts but it comes up at very small portions so do not worry about it you can still follow through with the entire lecture。



![](img/2b260802cb87f9d09683d595fd90fa8f_9.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_10.png)

So to those who are joining this for the first time， here is the problem at hand we have。

On the x axis。Let's say we are measuring the whisker length。

Of the particular animal and in the on the y axis we have ear flapappiness index。



![](img/2b260802cb87f9d09683d595fd90fa8f_12.png)

So let's say we have two types of animals， dogs and cats。



![](img/2b260802cb87f9d09683d595fd90fa8f_14.png)

And we collect data for both of them， so for dogs， their ear flapappiness will typically be higher。

And their whisk length would be lower， but for cats， they would lie hopefully somewhere here。



![](img/2b260802cb87f9d09683d595fd90fa8f_16.png)

The goal of this particular exercise or the goal of logistic regression is to find。



![](img/2b260802cb87f9d09683d595fd90fa8f_18.png)

The best possible hypothesis or find the best linear classifier。



![](img/2b260802cb87f9d09683d595fd90fa8f_20.png)

Which separates these two types of data sets。

![](img/2b260802cb87f9d09683d595fd90fa8f_22.png)

The linear classifier itself is given by three variables， theta 1 theta 2 and theta node。

 so its like theta 1 x1 plus theta 2 x2 plus theta node。And this is X1。And this is x2。

In linear algebra setting， this is also sometimes referred to as theta transpose x plus theta n。

Where theta transpose is just theta 1， theta 2， and x1 is just x1 x2。



![](img/2b260802cb87f9d09683d595fd90fa8f_24.png)

Plus， they turn out。So the ultimate goal is to find the optimal theta 1， theta 2 and theta node。

 which best separate these two types of data sets。

![](img/2b260802cb87f9d09683d595fd90fa8f_26.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_27.png)

Earlier we tried the perceptron approach and we tried the random linear classifier approach。



![](img/2b260802cb87f9d09683d595fd90fa8f_29.png)

But for logistic regression or for most of the machine learning algorithms。

 which we learn henceforth， they use something called ML L as optimization。



![](img/2b260802cb87f9d09683d595fd90fa8f_31.png)

So essentially， we will be using an optimization approach here。

 which we also motivated two to three lectures earlier。

What this means is that we will define a loss function and then we will try to find out。



![](img/2b260802cb87f9d09683d595fd90fa8f_33.png)

The parameters theta 1 theta 2 and theta n which minimize that loss function。

 that is what we will be doing。

![](img/2b260802cb87f9d09683d595fd90fa8f_35.png)

So。Let's say the objective function is J of theta。Which is。

1 by n where n is the number of data points。And L is the loss function。

 and usually the loss function is the difference between the guess。And the actual value。嗯。

When we move to advanced machine learning algorithms， we also have a regularization term here。

But for the sake of simplicity， I will not be considering the regularization term in this particular tutorial and we will just look at the loss function。

 so the goal is to find that particular theta star which minimizes J。



![](img/2b260802cb87f9d09683d595fd90fa8f_37.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_38.png)

Or which in turn minimizes this particular loss function。The guess is made by our hypothesis class。

And we looked at this hypothesis， which is also called as the sigmoid hypothesis。



![](img/2b260802cb87f9d09683d595fd90fa8f_40.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_41.png)

So let us come to these two functions which we have already learned in the previous class L。



![](img/2b260802cb87f9d09683d595fd90fa8f_43.png)

Is the cross entropy loss for logistic regression？And it is defined as follows。



![](img/2b260802cb87f9d09683d595fd90fa8f_45.png)

Let me write the definitions in pink color so L is the difference between the guess which is the hypothesis h of theta and y which is the actual label and that is given by negative of。



![](img/2b260802cb87f9d09683d595fd90fa8f_47.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_48.png)

Why multiplied by a log of。Hdge theta plus。1 minus y multiplied by log of1 minus h。



![](img/2b260802cb87f9d09683d595fd90fa8f_50.png)

This is the cross entropy loss function。

![](img/2b260802cb87f9d09683d595fd90fa8f_52.png)

Which we defined in the two lectures back。Now you must be thinking what is the hypothesis and the hypothesis class also we have defined in one of the previous lectures。



![](img/2b260802cb87f9d09683d595fd90fa8f_54.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_55.png)

And H of theta is the sigmoid function。

![](img/2b260802cb87f9d09683d595fd90fa8f_57.png)

H of theta。Is the sigmoid function which is given by1 upon1 plus e is 2 minus theta transpose x。



![](img/2b260802cb87f9d09683d595fd90fa8f_59.png)

For this derivative right now or for this derivative which I am going to do。

 I am not going to be using theta not because it will just make things a bit more complex。

But in the hands on demonstration， which is the part two of this lecture。

 I will show you exactly how we can deal with theta not。



![](img/2b260802cb87f9d09683d595fd90fa8f_61.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_62.png)

Okay， so now we have the loss function L， we know the formula for the loss function and we know the formula for the hypothesis class。

 so let let us put both L as well as h in j and see what this function actually looks like。



![](img/2b260802cb87f9d09683d595fd90fa8f_64.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_65.png)

So now when I put L and H in G of theta， it looks like this。



![](img/2b260802cb87f9d09683d595fd90fa8f_67.png)

J of theta is equal to minus1 by n。

![](img/2b260802cb87f9d09683d595fd90fa8f_69.png)

Sigma， I goes from one to n。Y I。Logo。Sigma of theta transpose Xi。



![](img/2b260802cb87f9d09683d595fd90fa8f_71.png)

Plus。1 minus Y I。Into logger。When minus sigma。Theta transpo side。



![](img/2b260802cb87f9d09683d595fd90fa8f_73.png)

Let me mark this。

![](img/2b260802cb87f9d09683d595fd90fa8f_75.png)

Objective function are the loss function which I want to minimize。



![](img/2b260802cb87f9d09683d595fd90fa8f_77.png)

What I have done is that I have just taken this loss function。

 the cross entropy loss and the hypothesis and plugged it here。



![](img/2b260802cb87f9d09683d595fd90fa8f_79.png)

![](img/2b260802cb87f9d09683d595fd90fa8f_80.png)

The edge theta replaced with this sigmoid function。



![](img/2b260802cb87f9d09683d595fd90fa8f_82.png)

So it turns out that this is our loss function which we need to minimize。



![](img/2b260802cb87f9d09683d595fd90fa8f_84.png)

So this is the step1。We want to find theta star， which minimizes J。

You see how we have converted the logistic loss into an optimization problem now it is no longer a machine learning problem now it comes down to mathematics that's it thats why people tell you that to master machine learning you need to master optimization and statistics。

Because when you formulate a problem as an optimization problem。

 it looks something like this and now you want to find theta star which minimizes J。



![](img/2b260802cb87f9d09683d595fd90fa8f_86.png)

So this is step1。Now let us look at step number two。

 which we have already prepared for in our toolkit。It is implementing gradient descent。



![](img/2b260802cb87f9d09683d595fd90fa8f_88.png)

And remember what gradient descent was gradient descent updates the theta value so it starts with some theta which we don't know and then it updates it based on the step size and the gradient of the function at that particular theta。



![](img/2b260802cb87f9d09683d595fd90fa8f_90.png)

So this is the step size。And this is the gradient of that function at that particular theta。



![](img/2b260802cb87f9d09683d595fd90fa8f_92.png)

So in order to implement gradient descent， we will need to find the gradient of this。



![](img/2b260802cb87f9d09683d595fd90fa8f_94.png)