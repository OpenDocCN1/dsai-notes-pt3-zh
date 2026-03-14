# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p14 P14_雅可比矩阵_02_02_01 -BV1wnYDzmEdV_p14-

![](img/956208ad1c4e50573c4e7e1e5ff2b971_0.png)

Previously， we saw that we can differentiate functions of multiple variables and that it isn't much harder than the Uniivariate calculus we met at the start of the course in this video we're going to introduce the Jacobian which brings in some of the ideas from linear algebra to build these partial derivatives into something particularly useful。

😊，The concept of the Jacobian can be applied to a variety of different problems。

 but in the context of getting started with optimization and machine learning。

 there is a particular scenario that comes up a lot。

 which is the Jacobian of a single function of many variables。😊，In short。

 if you have a function of many variables， So F of x1， x2， x3， et cetera。

 then the Jacobian is simply a vector where each entry is the partial derivative of F with respect to each one of those variables in turn。

 By convention， we write this as a row vector rather than a column vector for reasons that will become clear later in the course。

Let's start by looking at a nice， simple function to see just how straightforward building a Jacobian can be。

 Consider the function。F of X， Y and Z equals x squared Y plus 3 Z。To build the Jacobium。

 we just find each of the partial derivatives of the function one by one， so we've got。

D F by D X is going to equal， we're just differentiating with respect to x。

 so we get2 x Y when we treat everything else as confidence。

The F by D Y is going to equal just x squared and D F by D Z。🤢，Is just going to be。

 So this thing's just a constant。 and the Z disappears。 So we just get the number 3。 Now。

 bringing all of those together， we just end up with。A Jacobian。Ze。Which is just gonna be。2 X， Y。

X squared。3e。So what does this tell us？😡，We now have an algebraic expression for a vector。

 which when we give it a specific X， Y， Z coordinate。

 will return a vector pointing in the direction of steepest slope of this function。😊。

The vector for this particular function has a constant contribution in the Z direction。

 which does not depend on the location selected。 For example， at the point 000。

 we can see that our Jacobian is just going to be J of 000 iss just going to be well0。0 again。

 But the number 3 over here。So we can see that our Jacobbian is a vector of length3 pointing directly in the Z direction。

 Some of the numerical methods that we will discuss later in this course requires to calculate Jacobbians in hundreds of dimensions。

 However， even for the 3D example， we just solved graphical representation is already quite difficult。

 So we are now going to drop down to two dimensions so that we can actually see what's going on here。

 but to keep things interesting， we're going to look at a particularly complicated but rather attractive function。

So here is the equation that we're going to plot。But I'm showing it to you briefly just so that you can see that even though it is a bit of a monster。

 I hope you would agree that just with the tools we've seen so far。

 we really could calculate the partial derivatives of this thing。

 but you wouldn't really learn anything new from grinding through this Instead I'm going to show you the results graphically。

 So here is this function with the X axis is horizontal and the y axis is vertical and the colors are indicating the value of Z with the bright region suggesting high values and the dark region suggesting low values。

😊，Because of the nature of this particular function。

 I know that nothing interesting happens outside of the regions shown here so we can forget about it for now。

😊，Although this plot is fairly clear， our intuition about the gradient is a bit lacking in this format。

 so let's briefly make things 3D， where the values of Z are now also represented by the height。😊。

So as we said at the start of the video， the Jacobian is simply a vector that we can calculate for each location on this plot。

 which points in the direction of the steepest uphill slope。Furthermore， the steeper the slope。

 the greater the magnitude of the Jacobian at that point。

 hold the image of this 3D space in your mind as we now go back to 2D。

 and rather than showing all of the grid points I used to plot the graph。

 let's instead convert to a contour plot where just like a map of actual mountains。

 we will draw lines along the regions of the same height， which for us means the same value of Z。😊。

This removes a lot of the clutter from the plot， which is useful for the final step that I'd like to show you。

 which will be adding lots of Jacobbian vectors on top of our contour plot。 However。

 before I do that， let's take a look at these four points and see if your intuition is now in tune by guessing which one will have the Jacobbian with the largest magnitude Overlaying the Jacobbian vector field。

 we can see that they are clearly all pointing uphill away from the low dark regions and towards the high bright regions。

 Also， we see that where contour lines are tightly packed。

 this is where we find our largest Jacobbian vectors such as at point A。

 whereas at the peaks of the mountains and at the bottom of the valleys or even out on the wide flat plains。

 our gradients and therefore our Jacobbians are small。😊。

My hope is that this clear two dimensional example will give you the confidence to trust the maths when we come up against much higher dimensional problems later in the course。

 See you then。😊。