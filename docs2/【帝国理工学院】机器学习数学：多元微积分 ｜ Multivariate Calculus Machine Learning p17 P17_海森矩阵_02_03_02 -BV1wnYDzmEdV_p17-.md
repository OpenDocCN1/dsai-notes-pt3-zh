# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p17 P17_海森矩阵_02_03_02 -BV1wnYDzmEdV_p17-

![](img/b7f0e2739afdedd1566652b7606fcb16_0.png)

So now that you've all spent some time playing in the sandpi。

 we can introduce an additional concept which relates to multivariate systems called the Hessian。😊。

In many ways， the hessian can be thought of as a simple extension of the Jacobian vector for the Jacobian。

 we collected together all of the first order derivatives of a function into a vector。

 Now we're going to collect all of the second order derivatives together into a matrix。

 which for a function of n variables would look like this。😊，However。

 this is one of those scenarios where using an abbreviated notation style comes in really handy。

 We saw in the previous module that we can just keep differentiating a function。

 using the same method to find higher and higher order derivatives Similarlyly for a partial derivative if you want to find the second derivative with respect to x1 then x2 it's as simple as just differentiating with respect to x1。

 assuming all the other variables are constant and then differentiating with respect to x2 again。

 assuming all the other variables are constant As you can see from this general form。

 our Hessian matrix will be an n by n square matrix where n is the number of variables in our function F。

Let's now take a look at a quick example。 It often makes life easier to find the Jacobian first and then differentiate its terms again to find the hessian。

 So for our function， F of X， Y and Z equals x squared Y Z。 So F of X， Y， Z equals X squared Y， Z。

 We're going to first build the Jacobian for this thing， which of course is going be。😊，J equals。

 So we've got differentiate with respect to X。 We get2 X， Y， Z。 differentiate with respect to Y。

 We're just gonna to get x squared Z and differentiate with respect to Z。X squared。hyhy。Now。

 using this， we can then think about differentiating again with respect to each of the variables。

 which will then give us our Hessian matrix。 So H is just going to equal。

 and we'll put a big bracket here。So we want to take this thing and differentiate it with respect to X again。

So we're going to get2 Y Z。 So the next term along。

 we're going to differentiate this thing with respect to why。2 x Z。 and again with respect to Z。2 x。

 y。Okay， now we'll take the next row and we'll say we're going to differentiate this thing with respect to x than y than Z。

 so you get2 x Z。We're going to differentiate the respect to y， so we're going to get nothing。

We're going to differentiate this thing with respect to Z， and we get x squared。 Lastly。

 take this term， make the last row， differentiate with respect to X。 We get 2 X， y。

And then with respect to Y， we get x squared。I'm with respect to Z。We get nothing。

So one thing to notice here is that our hessian matrix is symmetrical across the leading diagonal。

 So actually， once I'd worked out the top right region。

 I could just have written these directly in for the bottom left region。

 This will always be true if the function is continuous， meaning that it has no sudden step changes。

We could now simply pass our Hessian and X， Y， Z coordinate， and it will return a matrix of numbers。

 which hopefully tells us something about that point in the space。 In order to visualize this。

 we're going to have to drop down to two dimensions again。

 Consider the simple function F of x and y equals x squared plus y squared。😊。

Calculating the Jacobian and the Hessian are both fairly straightforward。

 and hopefully you could have visualized how this function would have looked in your head。 However。

 if you hadn't known what function we were dealing with and calculated the value of the Jacobian at the 。

00。 you'd have seen that the gradient vector was also 0。

 But how would you know whether this thing was a maximum or a minimum at that point。

You could of course go and check some other point and see if it was above or below。

 but this isn't very robust instead we can look at the Hessian。

 which in this simple case is no longer even a function of x or Y itss determinant is clearly just2 times 2 minus0 times 0。

 which is 4。😡，The power of the Hessian is firstly， that if its determinant is positive。

 we know we are dealing with either a maximum or a minimum。 Secondly。

 we then just look at the first term， which is sitting at the top left hand corner of the Hessian。

If this guy is also positive， we know we've got a minimum， as in this particular case。

 whereas if it's negative， we've got a maximum。Lastly。

 slightly modifying our function to include a minus sign and recalculating our Jacobbian and our hessian and our hessian determinant。

 we now see the third interesting case。 This time our hessian determinant is negative。

 so we know that we're not dealing with a maximum or a minimum， but clearly at this 。00。

 the gradient is flat， so what's going on。😊，Well， if you look at the animation。

 what we've got here is a location with zero gradient。

 but with slopes coming down towards it in one direction， but up towards it in the other。

 we call this kind of feature a saddle point and they can also cause a lot of confusion when searching for a peak。

😊，In the last module of this course， you're also going to see another way that the Hessian can help us with optimization。

 but for now we've simply got another tool to help you navigate the spi。 See you next time。



![](img/b7f0e2739afdedd1566652b7606fcb16_2.png)