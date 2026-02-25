# 康奈尔大学《应用机器学习 CS 5787_ Applied Machine Learning 2020》中英字幕（deepseek p08 -08-Lecture 3. Part 1_ Optimization and Calculus.zh_en -BV12udzYvEFM_p8-

。

![](img/9949a8982856d3528863331614605a3f_1.png)

Hi and welcome back to Applied Machine learning Lecture with me。In lecture1。

 we saw what was machine learning and we looked at different approaches to machine learning。

 which included supervised learning， unsupervised learning and reinforcement learning。

 and then in lecture2 we looked at supervised learning more closely and we saw what was the structure of a supervised learning problem and what were the components of a supervised learning algorithm。

In this lecture， I want to now define our first supervised learning algorithm。

 which is going to be linear regression。We use linear regression as an example in the previous lecture。

 but we always we used an implementation that was created for us already and in this lecture we are going to define linear regression from scratch。

But before we do that， we are going to need a few tools from the field of optimization。

And in this the beginning of this lecture， I want to also start by providing a background on certain concepts from calculus and optimization that will be useful defining for defining the algorithms that we're going to be using in the rest of this lecture。



![](img/9949a8982856d3528863331614605a3f_3.png)

So again， the first part of this lecture is going to be a review of certain important concepts from calculus and how they relate to optimization。



![](img/9949a8982856d3528863331614605a3f_5.png)

Before I begin， I want to again remind you about the structure of a supervised learning task and the structure of a supervised learning algorithm。

Essentially， if we want to apply supervised learning to a certain task。

 we want to first collect a data set， a label data set of examples that show certain behavior。

That we want the algorithm to have。 And then we define a learning algorithm that the computer uses in order to extract。

Signal from this data set and use it to define a predictive model and the predictive model is something that we can use for useful tasks。

 such as prediction and other tasks as well。And this learning algorithm internally。

 it is also made up of several components。 These include the model class。

 the objective and the optimizer。The model class is the set of all the possible models that we're going to consider。

 for example this could be the set of all linear models and we're going to look for a predictive model within this model class。

The objective is a function that defines a score for how well a certain model in our class is how well does it fit the data。

 and an optimizer is an algorithm that chooses a model class which fits the data well。

 according to what our objective is saying。

![](img/9949a8982856d3528863331614605a3f_7.png)

Now， a little bit more formally， the optimizer has the following structure。

Here we have defined the function that the optimizer performs a little bit more formally。

Here the optimizer essentially is trying to find the function。

 the model within the model class that we're interested in again。

 this could be the set of linear models and this could be one particular linear model and it's trying to find the model with the best possible objective value or in other words the lowest possible loss value。

An example of what j could be is the mean squared error， so for example。

 the mean squared error would look at the difference between the output of F and an input X and the actual target that we want the model to output and if the output of the model on the input X is similar to the target y。

 then we say that the model has a good fit on this training example。

 and the model will have overall if this is true for all the training examples。

 then the model will have a low loss。

![](img/9949a8982856d3528863331614605a3f_9.png)

In this video we will use as a running example， a quadratic function。

Here I am defining what a quadratic function is， and in the first cell I am importing the usual libraries that we're going to use。

 which include Ny and Matplotlibb for visualization。

And here I am simply defining a one dimensional quadratic function。

 which is a function of a scalar input theta， and here I am taking theta， I'm multiplying it by two。

 subtracting one， and then I'm bring it to the power of two。

 which means that the output of this function will involve a term thats theta taken to the power2。

 which is what makes it a quadratic function。We can easily visualize this function and it looks as follows here I've taken a set of values for this a set of thetas which which I've taken 10 samples of theta within this interval between minus 0。

2 and1， and I've computed the value of the quadratic function any each of these points。

And visualizing these values， we obtain this nice blue curve。

 which has distinctive shape of a codedratic function， it has a minimum here at around 0。

5 and again it has this smooth rate of change that's characteristic of a quadratic function as you would expect。



![](img/9949a8982856d3528863331614605a3f_11.png)

Now， in order to start to define the concepts from optimization that we are going to need。

 we will start by revisiting and mentioning a key concept in calculus that will be necessary for defining the algorithms that we're going to look at。

 and this is the derivative。If you're not familiar with what is a derivative。

 I encourage you to review。Materials on the derivative from a first year calculus course。

 but for the purposes of this lecture， you can think of the derivative denoted as follows。

 this is the derivative of F with respect to its parameter theta evaluated at a point theta sub0。

We will， you can think of this as， as。In a few ways。

 one way of interpreting this value is the slope of the tangent at the point that at the point theta 0。

 so we are looking at the tangent line to the curve f at the point the is 0 and the derivative will equal to the slope of the function at this line。

Another way of looking at the derivative is the instantaneous rate of change of the function at the point theta0。

And of course there are many other ways of looking at derivatives， there is a formal definition。

 but for the purposes of understanding these algorithms， we are going to stick with this intuition。



![](img/9949a8982856d3528863331614605a3f_13.png)

To make it a little bit more concrete here， I'm going to plot the few derivatives for the quadratic function。

 first I'm defining a function that outputs the derivative at any point theta。

Here this is just the expression for the derivative that they obtained using standard rules in calculus。

And now I am computing the derivative at the value of when theta equals to0。

 I'm also putting here the value of the function at theta equals0。

 and here in this line I'm visualizing the derivative and it happens to be exactly the slope the tangent of the tangent line of the line that's tangent to the curve at the point theta0。

Theta equals 0。And also in other words， this is also the instantaneous rate of change of the function at this point。

So again， this matches the intuition that we saw earlier here I'm going to plot a few more derivatives again。

 these are all the tangents did these correspond to the slopes of the tangents of the。



![](img/9949a8982856d3528863331614605a3f_15.png)

how this curve and here have also I've also shown the derivative at 0。5。

 which is the minimum of this quadratic function。 And you see here that this is a flat line which has a slope of0 and as you would expect from standard calculus the slope of the well。

 first of all the，The value of the derivative at the minimum of the function equals0。

 and this can be seen intuitively as the slope of the tangent or the rate of change of the function being0 at the minimum of the function。

 this is an important fact about the minimum of functions。

 the fact again being that the derivative of a function at its minimum equals0。

This is an important fact that will be useful later on and again I would encourage you to review this concept from a first year or calculus course it's not。

 if you feel like you need a little bit more intuition and understanding of as to why this is。



![](img/9949a8982856d3528863331614605a3f_17.png)

Now， the functions that we are going to consider in this lecture are going to be more complicated than the quadratic function that you just saw。

We quadratic functions're going to be working with functions of many variables。

 and the input to these functions is going to be a d dimensionsional vector for some arbitrary dimension D。

And the extension of a derivative to these multivariate functions or one possible extension is called the partial derivative denoted as follows。

Again， you do not need to know the formal definition of this。

 although it will be useful to fully understand the material that will come later。

 but it's not strictly necessary again the simple intuitive definition of this what a partial derivative is is that it is simply the regular derivative of a function when of a multivariate function。

When all the inputs except the Jth1 are fixed to some arbitrary value that's specified here within theta 0。

So we are going to fix all the other d minus1 inputs to f to some value。

 and we are going to take the derivative of this function with respect to theta J。

And that is the intuition of what is a partial derivative。



![](img/9949a8982856d3528863331614605a3f_19.png)

Now， the partial derivative is useful for defining another important concept that we're going to be using a lot。

 which is called the gradient。 The gradient can be thought of another way of extending the derivative to multivariate function functions。

 so the gradient of the function of a multivariate function F with respect to its parameters theta and evaluated at a point theta 0。

Is given by is as follows and this is a vector， this is a d dimensionsal vector whose components are the partial derivatives of the function with respect to to each of its input so here the second component of the vector is the partial derivative of F with respect to its second input theta 2。

嗯。I am going to give an intuition for what the gradient is and why it's important using a few examples。

 and I encourage you to review again material from calculus if you are interested in a more formal definition how of what is the gradient and。

And in various properties of the gradient。

![](img/9949a8982856d3528863331614605a3f_21.png)

In order to give you an example of a gradient， we need a multivariate function， and for this。

 I am going to define a two dimensional extension of our a quadratic function that we saw earlier。



![](img/9949a8982856d3528863331614605a3f_23.png)

So here this is a two dimensional quaretic function and it's a function of two inputs。

 theta 0 and theta1， these are each scalar， and so the input to quadtic function  to d is two dimensional。

And these are here I'm mentioning a few technicalities about the implementation of this function。

 but the key line that you need to look at is this one where I'm defining what the function is。

And essentially I'm taking each of these two parameters， I am applying an defined transformation。

 and then I'm taking the result of the power 2， so this expression here involves theta 1 to the power2。

 theta 0 to the power 2， and this is what makes it a two dimensional quadratic function。



![](img/9949a8982856d3528863331614605a3f_25.png)

We can visualize this function as follows using the concept of a level curve。

So here I have a two dimensional plot and the x and y axes here correspond to our two variables of theta 0 and theta 1。

So for each combination of x and y， or in other words， for each combination of theta0 and theta 1。

 I can go on this plot and I can see here， for example， minus1 and 2。

 the value of the function is specified by what's on the plot in this area。

And inside inside this plot， I haven't shown every possible value of that the function can take。

 I have only shown a small number of values which are defined by these ellipses and these are called level curves essentially the idea of a level curve is that the function takes four takes the value4 at all the points along this level curve so all the combinations of theta 0 and theta 1 which if you draw the line this combination of theta 0 and theta 1 falls on this inner inner ellipse for all of these combinations of theta 0 and theta 1。

 the function will take the value 4。And similarly， along this second ellipse。

 the function takes the value 8 and then 12 and 20 and so forth。So these are called level curves。

 They are analogous to one to。To what one would see on a topological map of an area with mountains or hills or valleys。

 essentially if you've ever used the topological map。

 the topological map will show lines that on the map are all on the same altitude。

 so let's say they're all at1000 meters and another line will correspond to all the points that are at 1100 meters you can view this plot in the same way where these different points correspond to the altitude of that point which is defined by the quadratic function。

And so the minimum of the function here is at the middle we're looking at a valley。

 and as we expand from the valley， the function takes higher and higher values。

 which are given by these curves。And again， each curve shows the set of points that exactly has the value 24 in this example。

Again， if you're not familiar with the concept of level curves。

 I encourage you to look at a second or third year calculus course。

NowNow that we have this visualization of a two dimensional querytic function。

 let's visualize the gradient for these functions here I am defining the equivalent of derivative for this two dimensional querytic function。

 which is a gradient。

![](img/9949a8982856d3528863331614605a3f_27.png)

![](img/9949a8982856d3528863331614605a3f_28.png)

And again， the main line to look at is here and again here this is the at each point。

 Theta 0 and theta 1， I will have a two dimensional vector。

Whi along the first dimension will be the partial derivative with respect to theta 0 which is here and along the second dimension along the other dimension it will be the derivative with respect to theta 1。

 you can see that this is indeed the partial derivative with respect to theta 0 by looking at the original expression since this is the partial derivative we can take theta 1 as a fixed constant and so this term disappears and now we're only left with the derivative of this term with respect to theta 0 which corresponds to to number to this expression here。



![](img/9949a8982856d3528863331614605a3f_30.png)

And now we can visualize the gradient using by combining it with the plot that we just saw earlier。



![](img/9949a8982856d3528863331614605a3f_32.png)

So here I have selected three points， they're given by the following arrays。

 these are the coordinates of the points along along each point。

 the coordinates of each point along theta 0， these are the coordinates of each point along theta 1。

 and here I'm computing the derivative along each of these points。

 this is the set of or I should say the gradient， this is the set of gradients。

And here I'm visualizing this gradient this level on this plot which contains the level curves。

 and the three points at which I'm computing the gradient are these little blue dots that you should be able to see here and the gradient is it defines the following arrows that you see here。

So technically these arrows are not exactly the gradient they're one minus the gradient。

 so they're basically the gradient that was flipped to point in the other direction。

 the actual gradient would be the same arrow but pointing in this direction。

 but for us since we want to minimize this function。

 I will tell you in a moment why it's interesting to look at this point to look at minus the gradient。

Again， as I said earlier， each gradient is a vector and since it's a vector we can visualize it via an arrow。

 it's a two dimensional， it's this two dimensional arrow here or this arrow in two dimensional space。

And we can immediately make a few observations about these vectors。

The first observation is that they are all pointing inwards closer towards the minimum of the function。

Because this is a quadratic function， everything that's going to be inside of this level curve is going to be smaller than this for this one it 20 and in every case the green is pointing towards a direction in which the function becomes smaller。

Furthermore， you can even show using simple calculus that this arrow is pointing towards the direction at which the function decreases most steeply at this point。

So if you think of this as being a valley， then this arrow is pointing towards the direction where the slope of the valley decreases the fastest。

 so if you were to drop a ball here， the ball would fall along this line because this is where the pull of gravity would be stronger。

And finally， another useful observation is that these arrows are always perpendicular to the level curves on which they sit。

Again， this is a basic fact about gradients that you can learn in a second or third year calculus course。

 but you can see here easily visually that these arrows are pointing towards the inside of each level curve and they're perpendicular in the sense that if we were to draw the tangent to this level curve here that touches this dot。

 the tangent would be perpendicular to the vector。So these are a few basic intuitions about gradients。

And we are now going to use these intuitions in order to define a really important algorithm in machine learning。

 which is called gradient descent。

![](img/9949a8982856d3528863331614605a3f_34.png)

Creating disscent is a very common optimization algorithm， perhaps the most common。

 and it is widely used in all areas of machine learning to solve optimization problems like the one we saw earlier at the very beginning of this video。

And the intuition of creating the is really simple。If we want to find the minimum of a function。

 we start at some point at some value that this function can take。

 and then we repeatedly follow the gradient along the direction which minimizes the value of the function until we reach a minimum。



![](img/9949a8982856d3528863331614605a3f_36.png)

So here in this example you can see that if we were to start at this point。

 this arrow which1 minus the gradient which is1 times the gradient。

 would be pointing towards the direction at which the function decreases the fastest and so if we keep following this arrow in this direction we will be decreasing the function。

 then eventually we're going to hit a different point where the value of the function will be smaller。

 then we will follow the gradient again again again and so forth until we approach this center of this curve which contains the minimum。

Let me give you an example of what this means， but before I give an example。

 let's just define gradient descent a little bit more formally， using mathematical notation。

 gradient descent is essentially applying the following rules。

 the following rule many times for some number of iterations which are indexed here by the variable I。



![](img/9949a8982856d3528863331614605a3f_38.png)

So we start at some initial gate， guess that it's theta  zero of the parameters。

 and we repeatedly apply this rule where here。In here we take the gradient and we scale it by a step size alpha。

 which is how far along this direction we want to go。

 and then we combine this term with our current estimate of the parameters to obtain a a new set of parameters to which we move from our previous point。

If I were to define this in code， it would look something like this。

 we start with an initial guess for what theta is。And then we keep performing this update rule。

 which you see here， and we keep applying this rule until we are at a point where the function is no longer decreasing。

 which is this thing here， so essentially until the change between two consecutive iterations is sufficiently small。

 we keep applying this rule again is an analog of this rule， we take the previous value of apologies。

 we take the previous value of theta and we take the gradient。

 we multiply it by the step size along which is the distance that we want to take and we keep repeating this process。



![](img/9949a8982856d3528863331614605a3f_40.png)

![](img/9949a8982856d3528863331614605a3f_41.png)

Here I define this algorithm in Ccode， but it's just as easy to implement it in Ny， in fact。

 it's almost exactly as it looked like in the previous slide。

Here I have defined a few parameters such as the conversionvergence threshold and the step size。

 and I've initialized the values of theta to a certain value and again while the function is still converging。

 I keep repeating this rule that you saw on a previous slide。

 this line is exactly the same as pseudo code and the only additional the only additional lines that are added here are these two in which I'm storing the points and the gradients that you see here and that we visit as we search for the minimum of this function。

Now， in order to get a real intuition about this， let's look at the result of applying this algorithm。



![](img/9949a8982856d3528863331614605a3f_43.png)

So here in the earlier slides， I have pre computeuted an optimization process and now I'm visualizing it。

So I initially started at this point here， which is somewhere around minus minus 2 and 3 and this is one of the points that we had our in our earlier slide and you can see here the gradient at this point and now I am repeatedly or starting at this point I have computed this vector which is one minus the gradient and then I have taken a certain step along this direction which brings me to this point here。

Now that I'm at this point， I again compute this direction of steepest descent。

 which is obtained directly from the gradient， and I take a step step in this direction， I am here。

 then I take another step， another step， another step。

 another step I keep until I reach somewhere that's really close to the minimum of the function。

So this is a visual example of the trajectory that a gradient descent algorithm would take。

And as you can see here， it does indeed get us closer to the minimum。



![](img/9949a8982856d3528863331614605a3f_45.png)

You can also play with this code to see the values to see the results of changing different parameters of this algorithm here I can change the step size from 2 times 10 to the minus1 to 10 to the minus1。

I just reran this algorithm and now if I go back here and I visualize it。



![](img/9949a8982856d3528863331614605a3f_47.png)

I obtain a different trajectory。 You can see that now I have many more points that we are still taking the same trajectory。

 but we're taking more steps to reach because at each step I'm making a little bit more I'm making less progress than I used to we can make this even a little bit more extreme and make the step size tend to the power minus2 and now if I again revvisualize that trajectory I get a very。

 very， very， very slow movement。 In fact at the end it becomes so slow that it doesn't even reach the minimum so this is this shows the effect of using a learning rate that might be a little bit too small。



![](img/9949a8982856d3528863331614605a3f_49.png)

![](img/9949a8982856d3528863331614605a3f_50.png)

![](img/9949a8982856d3528863331614605a3f_51.png)

I can also increase the learning rate。 I can make it something bigger， perhaps I will make it。

Three times 10 to the 1。

![](img/9949a8982856d3528863331614605a3f_53.png)

Now I just reend this algorithm， I can revisualize this and now you can see the trajectory here we're taking a much bigger step。

 we slightly overshoot， we end up here and then we take this trajectory but it still brings us closer to our final point。



![](img/9949a8982856d3528863331614605a3f_55.png)

![](img/9949a8982856d3528863331614605a3f_56.png)

I can keep doing this， I can further increase the gradient。



![](img/9949a8982856d3528863331614605a3f_58.png)

And I can re visualualize this。And now you see that we are overshooting even more， we're going here。

 here， here， here， here， and now our arch trajectory becomes a little bit chaotic， and in a sense。

 we're slightly wasting movement because each step is too large and we're overstepping a little bit。



![](img/9949a8982856d3528863331614605a3f_60.png)

To make it a little bit more extreme。

![](img/9949a8982856d3528863331614605a3f_62.png)

Increase the gradient size the step size even more。

 which makes the algorithm not even converge because at every time step here， I'm at every step。

 I'm overshooting the value of this。I'm basically jumping all the way across this。

This this region where the minimum is and I'm going to the other side and I'm just stepping back and forth and we're not really converging so this is what it looks like when your step size is too large。



![](img/9949a8982856d3528863331614605a3f_64.png)

And again， if we set this to something more reasonable， we have a better trajectory。



![](img/9949a8982856d3528863331614605a3f_66.png)

![](img/9949a8982856d3528863331614605a3f_67.png)

And finally， the outcome of using a smaller convergence threshold is that we are going to be taking a little bit more steps here that are small and we are reaching closer to the one。



![](img/9949a8982856d3528863331614605a3f_69.png)

![](img/9949a8982856d3528863331614605a3f_70.png)

So hopefully this definition of green descent will hopefully understand it at an intuitive level and I。

I encourage you to play with this code on your own and again。

 get a better intuitive feeling for what gradient descent does and how it works。

Now in the rest of this lecture， we are going to use gradient descent and apply it to the kinds of models that we saw earlier to obtain our first supervised learning algorithm。



![](img/9949a8982856d3528863331614605a3f_72.png)