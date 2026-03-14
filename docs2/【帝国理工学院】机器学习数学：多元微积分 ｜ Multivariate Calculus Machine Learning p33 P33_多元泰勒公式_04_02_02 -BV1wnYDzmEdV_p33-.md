# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p33 P33_多元泰勒公式_04_02_02 -BV1wnYDzmEdV_p33-

![](img/3e1eacdb9b4d309d1f698d01a386a0b5_0.png)

So far in this module， I've introduced you to the concept of power series and then shown you how we can use them to approximate functions。

We've also seen how power series can then be used to give you some indication of the size of the error that results from using these approximations。

 which is very useful when applying numerical methods。😊。

The last idea that we're going to very briefly look at on this topic is upgrading the power series from the onedimenional version that we've seen so far to its more general multivariate form。

 just to recap on the notational options from the previous video。

 We saw that we can reexpress the Taylor series from a form that emphasizes building the approximation of a function at a point P to a totally equivalent form that emphasizes using that function to evaluate other points。

 there is a small distance deelta X away just to make sure you can see that they're the same。

 we can write out the first four terms one above the other to make the comparison clear In this video。

 we are going to continue using the Delta X notation as it's more compact。

 which will come in handy when we're in higher dimensions。😊。

We won't be working through the multivariate Taylor series derivation in any detail as all I really want you to take away from this video is what a multidimensional power series will look like。

 both as an equation and in a graph。 So keeping in mind are onedi expression。

 let's start by looking at the twodisal case where F is now a function of the two variables X and Y。

 So our truncated Taylor series expressions will enable us to approximate the function at some nearby point X plus delta X Y plus delta Y。

😊，Let's look at the simple two dimensional Gaussian function。

 which many of you may be familiar with from studying the normal distribution in statistics。

 It's a nice， well behaved function with a simple maximum at the 。00。 Now。

 in a one dimensional analysis， our power series would give us an expression for a one dimensional function。

 However， in a two dimensional case。 Our power series would， of course。

 now give us a two dimensional function， which we would more intuitively refer to as a surface。😊。

Just as with the one dimensional case， our zeroth order approximation are simply the value of the function at that point applied everywhere。

Which means in 2D， this would just be a flat surface。

 so a zeroth order approximation at the peak would look like this。😊。

And a zeroth order approximation somewhere on the side of the bell would look a bit more like this。

This is fairly straightforward， but now let's think about the first order approximation drawing the analogy from the1D case again。

 the first order approximation should have a height and a gradient。

 So we're still expecting a straight surface， but this time it can be at an angle。 Now。

 if we are calculating it at the peak。 it wouldn't be a very exciting case as it's a toning point。

 and so the gradient is 0。 However， let's look again at the point on the side of the slope。😊。

Taking the first order approximation here gives us a surface with the same height and gradient at the point。

 Finally， let's look at the second order approximation for these two points。

 We're now expecting some kind of parabolic surface。 However， if I calculate it at the peak。

 nothing seems to appear。 but that's just because we've created a parabola inside our bell curve。

 So we need to look from underneath to even see it。😊，Finally。

 if we plot the second order approximation at the point on the side of the bell curve。

 you can see that we end up with some kind of interesting saddle function。

 but it's still fairly clear even by eye that the gradient and the curvature are matching up nicely at that point。

 although this approximation is evidently not useful outside of a fairly small region around the point。

😊，We're now going to take a look at how we would write expressions for these functions。

 So if we wanted to build a Taylor series expansion of the twodimensal function F at the point x comma y。

 and then use it to evaluate the function at the point x plus delta x comma Y comma delta Y our zeroth order approximation is just a flat surface with the same height as the function at our expansion point。

 The first order approximation incorporates the gradient information in the two directions。

 And once again， we are thinking about how rise equals the gradient times the run。

 notice here for compactness， I'm using the partial symbol with a subscript to signify a derivative respect to a certain variable。

 If we look now at the second order approximation。 we can see that the coefficient of one half still remains as per the one dimensional case。

 but now we have three terms， all of which our second derivatives。

 The first has been differentiated with respect to x twice the。With respect to Y twice。

 and the middle term has been differentiated with respect to each of X and Y。 Now， there are。

 of course， higher order terms， but we've already got more than enough to play with it。

So let's look again at the first order term。 It's the sum of the product of the first derivatives with the step sizes。

 but hopefully this will remind you of our discussion of the Jacobbian。

 So we can actually reexpress this as just the Jacobian。

 multiply by a vector containing deelta X and delta Y， which we can write as deelta bold x。

 where the bold x signifies a vector containing those two terms。 Finally。

 if we look at the second order term in the same way。

 and notice that these second derivatives can be collected into a matrix。

 which we've previously defined as our Hessian。 then to make the sum we need。

 we now have to multiply our delta x vector by the Hessian。 And then again。

 by the transpose of the deelta x vector， and that's it。😊，So we now have a nice。

 compact expression for the second order multivariate Taylor series expansion。

 which brings together so much of our calculus and linear algebra skills and makes use of the Jacobbian and Hessian concepts。

 which we defined earlier in the course。 And， of course。

 although we've been talking about the twodimensional case in this video so far。

 we could actually have any number of dimensions contained in our JH and deelta X terms。

 So this immediately generals from 2D to multidimensional hypersurfaces， which is pretty cool。

 See you in the next one。😊。

![](img/3e1eacdb9b4d309d1f698d01a386a0b5_2.png)