# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p15 P15 ML Teach by Doing Lecture 15： Logistic Regression Part 1 [BV1RusDz1EXd_p15]

Hello everyone， welcomel to the day 15。Of the machine learning teach by doing project。In this day。

 we have three agendas。The first thing which we are going to look at is this idea of solving machine learning problems using optimization。



![](img/b72759c852a9d1037b5b0a93f6644054_1.png)

The second thing which we are going to look at is introduction to the concept of logistic regression。

And the third thing which we are going to look at is。This s function。

 what it really means and why it is so important for logistic regression。In fact。

 in many modern ML algorithms。

![](img/b72759c852a9d1037b5b0a93f6644054_3.png)

Sigmoid function is routinely deployed， so this particular lecture will also serve as a very nice visual introduction。



![](img/b72759c852a9d1037b5b0a93f6644054_5.png)

![](img/b72759c852a9d1037b5b0a93f6644054_6.png)

To what the sigmoid function really represents。So let's start with the first aspect which is solving ML using optimization。



![](img/b72759c852a9d1037b5b0a93f6644054_8.png)

So if you think of the perceptron algorithm。Or even the random linear classifier algorithm。

 someone needed to think of this algorithms， so they came from our intuition。呃。But what if。

We want to solve complex ML problems so every time we want to construct new algorithms。

 we cannot rely on human intuition right what we need is a machinery。What do we need as a machinery？



![](img/b72759c852a9d1037b5b0a93f6644054_10.png)

That will derive。

![](img/b72759c852a9d1037b5b0a93f6644054_12.png)

呃。Or that will come up with ML algorithms。For any problem。So we need a machinery or a methodology。

Which will help us derive an ML algorithm for any problem Perceptron of course， was a genius idea。

 it was a brilliant way of updating the theta and theta node。

But what if we cannot come up with such algorithms each time？



![](img/b72759c852a9d1037b5b0a93f6644054_14.png)

We need to dev techniques or methodologies， which can help us to find ML algorithms or any given problem。



![](img/b72759c852a9d1037b5b0a93f6644054_16.png)

And that's the reason why machine learning practitioners。



![](img/b72759c852a9d1037b5b0a93f6644054_18.png)

呃。Turn ML problems。Into an optimization problem。So optimization is a field is a mathematical field。

 which is basically advanced very rapidly。 and there are so many。



![](img/b72759c852a9d1037b5b0a93f6644054_20.png)

![](img/b72759c852a9d1037b5b0a93f6644054_21.png)

Techniques which you already have in the domain of optimization。



![](img/b72759c852a9d1037b5b0a93f6644054_23.png)

So if we can think of an ML problem as an optimization problem。

 we can use all of those techniques to basically solve an ML problem。



![](img/b72759c852a9d1037b5b0a93f6644054_25.png)

What is meant by optimization problem essentially， let us look at the next part， which is。



![](img/b72759c852a9d1037b5b0a93f6644054_27.png)

![](img/b72759c852a9d1037b5b0a93f6644054_28.png)

Ml as optimization。

![](img/b72759c852a9d1037b5b0a93f6644054_30.png)

So optimization essentially means there is a function which you want to optimize。So， for example， if。

I want to book an Uber。The way the Uber algorithm works is that based on my location。

 based on which drivers are close to me based on the ratings of those drivers。

Based on my willingness to pay， Uber will assign me the best possible driver。

That is an optimization problem。And the function here。

 which Uber is trying to optimize for is assigning me the best driver。

So optimization problems we encounter every day in our day to day lives when we want to go from place A to place B。

 we probably want to choose the travel route which leads to minimum possible time right that is an optim problem we are optimizing for time here。

So essentially in any kind of optimization problem， there is a function which is called J。

Which we need to optimize and that J depends on theta， which are parameters。



![](img/b72759c852a9d1037b5b0a93f6644054_32.png)

So in terms of ML。This J will be the loss function。



![](img/b72759c852a9d1037b5b0a93f6644054_34.png)

Which we want to minimize。

![](img/b72759c852a9d1037b5b0a93f6644054_36.png)

And theta are the parameters。 So such as if you think of。

Or rather if those j is not exactly the loss function， I will come back to it for now。

 let us call J as the objective function。So J is the objective function， which we want to optimize。

Theta is the parameter。 So if we looked at linear separator theta where the parameters of the linear separator like theta 1 x1 plus theta 2 x2。

plus theta not equal to 0， if we look at this， then the parameters are。



![](img/b72759c852a9d1037b5b0a93f6644054_38.png)

![](img/b72759c852a9d1037b5b0a93f6644054_39.png)

Theta 1， Theta 2， and theta node。And J is the objective function。



![](img/b72759c852a9d1037b5b0a93f6644054_41.png)

So the optimization problem essentially is this。

![](img/b72759c852a9d1037b5b0a93f6644054_43.png)

The optimization problem。Is to find。He does bad。That minimizes J。



![](img/b72759c852a9d1037b5b0a93f6644054_45.png)

So think of the positive and negative points which we had and we found the linear classifier。



![](img/b72759c852a9d1037b5b0a93f6644054_47.png)

The objective in optimization is to find the theta1 theta 2 and theta node so that in that particular example。

 the loss which it makes on predictions is reduced。

This is the simple definition of the optimization problem now you may be thinking what is this objective function。



![](img/b72759c852a9d1037b5b0a93f6644054_49.png)

And what does it look like for machine learning problems？



![](img/b72759c852a9d1037b5b0a93f6644054_51.png)

So in any machine learning problem， the objective function typically looks like this。

First Im going to write it in words and then I am going to write it in mathematical formula。

 so the objective function G of theta is always the summation of the loss on training data。



![](img/b72759c852a9d1037b5b0a93f6644054_53.png)

![](img/b72759c852a9d1037b5b0a93f6644054_54.png)

![](img/b72759c852a9d1037b5b0a93f6644054_55.png)

So we want to minimize the loss on training data。

![](img/b72759c852a9d1037b5b0a93f6644054_57.png)

Plus。There is an additional term which is called as regularizer。



![](img/b72759c852a9d1037b5b0a93f6644054_59.png)

We will learn more about this just in a moment， but regularizer actually helps us to。



![](img/b72759c852a9d1037b5b0a93f6644054_61.png)

Minimize。Or reduce loss on test data。

![](img/b72759c852a9d1037b5b0a93f6644054_63.png)

So as we saw it is not enough to just make sure that the loss on training data is minimized。

 we need to make sure that when any new data point is given the machine learning algorithm which we had makes very less mistakes on new data points as well so we need to minimize loss on test data as well and for that a technique called regularization is used。



![](img/b72759c852a9d1037b5b0a93f6644054_65.png)

![](img/b72759c852a9d1037b5b0a93f6644054_66.png)

![](img/b72759c852a9d1037b5b0a93f6644054_67.png)

![](img/b72759c852a9d1037b5b0a93f6644054_68.png)

![](img/b72759c852a9d1037b5b0a93f6644054_69.png)

So let us see what this sumation looks like mathematically mathematically this just looks like one by n。

 which is the number of data points sigma i goes from one to n。L， which is my loss function， H。

This is my hypothesis。

![](img/b72759c852a9d1037b5b0a93f6644054_71.png)

So basically， this is the loss function。

![](img/b72759c852a9d1037b5b0a93f6644054_73.png)

嗯。This is the loss function averaged。For all the endpoint， so I' am dividing it by n。

Then this edge is the is our guess。And this y is the actual value。Basically。

 this just means that you take your hypothesis， you make the guess。

And then you find the error between the guess and the actual value。

 that is the loss function and we just take the average of the loss function over all the training data。



![](img/b72759c852a9d1037b5b0a93f6644054_75.png)

哦。And the regularizer。Looks like this Lada into R of theta。



![](img/b72759c852a9d1037b5b0a93f6644054_77.png)

So this lambda is the hyperparmeter。 And remember， we saw this in the random。



![](img/b72759c852a9d1037b5b0a93f6644054_79.png)

randomand linear classifier algorithm or lambda we randomly chose to be equal to like 100 variations or 100 iterations。

So lambda is the hyperparmeter。

![](img/b72759c852a9d1037b5b0a93f6644054_81.png)

And this is called as the regularization function。

![](img/b72759c852a9d1037b5b0a93f6644054_83.png)

So or we can just call it regular here。You can think of the regularizer as putting a penalty。



![](img/b72759c852a9d1037b5b0a93f6644054_85.png)

On our thes。

![](img/b72759c852a9d1037b5b0a93f6644054_87.png)

So it says that the reason we put a penalty here is that we are telling the algorithm is don' not try to perfectly or to super accurately fit the data。

 dont try super hard to fit the data。Because that might lead to an overfitting problem。

or try to keep the algorithm or try to keep the optimal solution simple don't try to overfit that is what we are telling in this regularizer this is brilliantly summed up in this MITs visual so if you look at this particular data。



![](img/b72759c852a9d1037b5b0a93f6644054_89.png)

![](img/b72759c852a9d1037b5b0a93f6644054_90.png)

Let's say the black dots are the positive data and the hollow dots are the negative data let us compare to hypothesis h1 and h2 here look at h1 h1 perfectly goes through all the points and it separates the。



![](img/b72759c852a9d1037b5b0a93f6644054_92.png)