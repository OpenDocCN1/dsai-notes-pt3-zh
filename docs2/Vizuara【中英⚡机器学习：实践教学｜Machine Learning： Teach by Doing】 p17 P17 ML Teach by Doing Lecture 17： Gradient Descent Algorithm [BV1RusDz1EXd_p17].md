# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p17 P17 ML Teach by Doing Lecture 17： Gradient Descent Algorithm [BV1RusDz1EXd_p17]

Hello everyone， welcome to the lecturec 17 of the Ma Learning Tea by Doing Project。

This is a very important lecture because in this lecture we are going to learn about one of the most important machine learning algorithms。

 which is called as gradient descent。

![](img/7648337066528a139861044bd3e05a70_1.png)

![](img/7648337066528a139861044bd3e05a70_2.png)

Unlike other courses， I am not going to start directly from the mathematical formula。



![](img/7648337066528a139861044bd3e05a70_4.png)

I am first going to visually make you understand why this algorithm works in the first place。

 the motivation and the intuition behind this algorithm and the visual introduction of how this algorithm works。



![](img/7648337066528a139861044bd3e05a70_6.png)

![](img/7648337066528a139861044bd3e05a70_7.png)

![](img/7648337066528a139861044bd3e05a70_8.png)

Then when we come to the mathematical algorithm itself， you will understand it much， much better。

I actually spent quite a bit of time making the format for this lecture。

So that we have Python coding also in this lecture and we have a lot of visual elements so that you never forget what gradient descent is。



![](img/7648337066528a139861044bd3e05a70_10.png)

Okay， so this is also the part three of our series on logistic regression in the previous parts we have defined the hypothesis class。



![](img/7648337066528a139861044bd3e05a70_12.png)

For a logistic regression。Which is the sigmoid hypothesis。



![](img/7648337066528a139861044bd3e05a70_14.png)

Then。

![](img/7648337066528a139861044bd3e05a70_16.png)

We have also defined the。Loss function in the previous lecture。Which was the cross entropis。그ick。

So in this particular lecture。The main idea which we are going to explore is how to find that theta。



![](img/7648337066528a139861044bd3e05a70_18.png)

For the linear classifier， which minimizes our loss function。



![](img/7648337066528a139861044bd3e05a70_20.png)

Remember that the loss function is L and L is a function of my hypothesis h and the true values yi and H in turn is a function of theta。

So how do we find the theta which minimizes the loss function？To answer this question。

 we will answer one more question。 Let's say if there is any function F。



![](img/7648337066528a139861044bd3e05a70_22.png)

Let's say there is any function f of theta。

![](img/7648337066528a139861044bd3e05a70_24.png)

How to find the theta， which minimizes。

![](img/7648337066528a139861044bd3e05a70_26.png)

F， so how to find theta star， which minimizes F。

![](img/7648337066528a139861044bd3e05a70_28.png)

This is where gradient descent comes into the picture people working in the fields of optimization have done so much work on gradient descent that now is the time when you must be thinking why did we formulate machine learning as an optimization problem the reason we did that is because we can define the loss function and then we can optimize the loss function using gradient descent。



![](img/7648337066528a139861044bd3e05a70_30.png)

![](img/7648337066528a139861044bd3e05a70_31.png)

Based on which so much work has already been done in the past。So。

 essentially we converted the machine learning problem to an optimization problem and since we have so many techniques to solve that optimization problem。

 we are now in comfortable territory。

![](img/7648337066528a139861044bd3e05a70_33.png)

![](img/7648337066528a139861044bd3e05a70_34.png)

So let us learn about gradient descent。

![](img/7648337066528a139861044bd3e05a70_36.png)

And。What it really means。The one thing which you need to know throughout this particular lecture。

 which I am going to write in a different color here so that we can come back to it again。



![](img/7648337066528a139861044bd3e05a70_38.png)

![](img/7648337066528a139861044bd3e05a70_39.png)

Is that a gradient of a function？Graaddient of a function。Gs。The direction of steepest ascent。

I will further explain what it means。 but for now， just keep this in mind。

 this is the intuition behind。What is a gradient of a function and this works in all dimensions。

 not just in one dimensional two dimension， but any dimension。



![](img/7648337066528a139861044bd3e05a70_41.png)

Okay， so let us look at a practical demo。

![](img/7648337066528a139861044bd3e05a70_43.png)

First， we are going to look at it in one dimension and then we are going to move to two dimensions。

Remember that the aim is that let's say there is a loss function F。

We want to find that particular theta， which minimizes F。



![](img/7648337066528a139861044bd3e05a70_45.png)

So， my goal in this section is for is to show you why gradient descent is so intuitive and why it is quite obvious that this is the correct algorithm which will work。

And I am deliberately showing this to you through a practical demonstration so that you will never forget it。



![](img/7648337066528a139861044bd3e05a70_47.png)

![](img/7648337066528a139861044bd3e05a70_48.png)

So let us say in one dimension， the function f， which we consider is f of x is equal to x squared。

Let's say this is the loss function in one dimension。And our aim is to find that particular X。



![](img/7648337066528a139861044bd3e05a70_50.png)

Find that particular X。Which minimizes F。

![](img/7648337066528a139861044bd3e05a70_52.png)

Correct， that is the goal which we have now we know that we know how this plot looks like， right？



![](img/7648337066528a139861044bd3e05a70_54.png)

Let's say。We know that all of us know this is a parabola which looks something like this。

The origin is0，0 commma 0。Correct， this is x， and this is F。

Which is equal to x square Now the main thing here is that lets say you had no understanding of how this plot looks like visually。



![](img/7648337066528a139861044bd3e05a70_56.png)

![](img/7648337066528a139861044bd3e05a70_57.png)

All you have is this function。

![](img/7648337066528a139861044bd3e05a70_59.png)

And this may happen for complex functions right we would not know the visual nature of all functions so imagine that you have no clue about this plot I am just showing this right now for demonstration purposes but imagine you had no clue how this plot actually looks like。



![](img/7648337066528a139861044bd3e05a70_61.png)

![](img/7648337066528a139861044bd3e05a70_62.png)

![](img/7648337066528a139861044bd3e05a70_63.png)

Then and also imagine that you are the first person in the world who are task to find the X which minimize SF。



![](img/7648337066528a139861044bd3e05a70_65.png)

![](img/7648337066528a139861044bd3e05a70_66.png)

How would you go about solving this problem？Imagine you are living in a time when gradient descent was not invented。



![](img/7648337066528a139861044bd3e05a70_68.png)

You only have this function and you want to find the x which minimizes this function。

 how would you go about it？

![](img/7648337066528a139861044bd3e05a70_70.png)

![](img/7648337066528a139861044bd3e05a70_71.png)

Okay， the step one， which probably you might do as any person is par with a random guess。



![](img/7648337066528a139861044bd3e05a70_73.png)

This is quite easy， right， and anyone can do this。Start with the random guess。Let's say。

 I start with the。Let's say start with an next one whose actual value is equal to 9。



![](img/7648337066528a139861044bd3e05a70_75.png)

In the plot， that X1 appears somewhere over here。

![](img/7648337066528a139861044bd3e05a70_77.png)

![](img/7648337066528a139861044bd3e05a70_78.png)

So let's say this is my first guess which I have made。



![](img/7648337066528a139861044bd3e05a70_80.png)

X1 is equal to 9。

![](img/7648337066528a139861044bd3e05a70_82.png)

Now you only know that the value at x1 value of f at x1 is equal to 81。



![](img/7648337066528a139861044bd3e05a70_84.png)

You do not know whether this is a minimum value or whether there are other values which exist。



![](img/7648337066528a139861044bd3e05a70_86.png)

Other values of x for which f might be even lower， you don't know that at this moment。



![](img/7648337066528a139861044bd3e05a70_88.png)

All you know is that you have started with x and you have found out that the f is at1 now what do you do next？



![](img/7648337066528a139861044bd3e05a70_90.png)

![](img/7648337066528a139861044bd3e05a70_91.png)

You want to find a different point after this point correct。

 but you want to move in a direction which gives you a lower value of if you cannot keep on finding these values or you cannot keep on guessing random values of x。



![](img/7648337066528a139861044bd3e05a70_93.png)

In the step 2， we want to move in a direction which actually decreases f from 81 to a value hopefully lower than that。



![](img/7648337066528a139861044bd3e05a70_95.png)

And this is where we remember what we saw about the intuition behind a gradient。

 remember that the gradient of a function always gives the direction of steepest ascent。



![](img/7648337066528a139861044bd3e05a70_97.png)

![](img/7648337066528a139861044bd3e05a70_98.png)

![](img/7648337066528a139861044bd3e05a70_99.png)

So in this case， since it's one dimension， the gradient is also equal to slope。

Since its one dimension， the gradient is the slope of the function。



![](img/7648337066528a139861044bd3e05a70_101.png)

And the gradient gives us the direction of the steepest ascent。



![](img/7648337066528a139861044bd3e05a70_103.png)

Let me actually give you one more layer of intuition。

Imagine that you are blindfolded and you are on a cliff， but the cliff is just one dimension。

 you can move either left or you can move to the right and you want to get to the lowest point of that cliff。

So， right now our situation is that we have evaluated one point on the cliff and you have seen that the value is 81 now you don't know whether to go to the left or whether to go to the right。

Intuitively， so what you check is that。You check that going left。



![](img/7648337066528a139861044bd3e05a70_105.png)

Means that the ground is sloping downwards， so you are at a particular location on the ground and you in。



![](img/7648337066528a139861044bd3e05a70_107.png)