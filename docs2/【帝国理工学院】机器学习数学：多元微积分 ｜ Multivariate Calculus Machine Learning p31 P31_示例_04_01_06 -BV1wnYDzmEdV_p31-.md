# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p31 P31_示例_04_01_06 -BV1wnYDzmEdV_p31-

![](img/825d258d5260f9a286e475af9e93b2e9_0.png)

In this video we're going to put our understanding of power series to the test by looking at two interesting examples first off。

 we're going to build a McLain series expansion of the cosine function。😊。

Cosine is the epitome of a well behaved function， as it is certainly continuous everywhere。

 as well as being infinitely differentiable。 As we're building a McLaron series。

 we're going to want to find out everything about the function at the point x equals 0。

 So let's start by doing some differentiation。😊，And what we get。

 if you remember from earlier in the course is this cyclic pattern of cosines and ss positive and negative。

 which takes us back to the cosine again after four steps。

 If we now evaluate this derivative at the point x equals 0。

 we see that the cosine terms are either one or minus-1 and the sine terms are all0。

 This must mean from a power series perspective， that every other term will have a0 coefficient。

 notice that these zeros will occur whenever we differentiate an odd number of times。

 which means that all the odd powers of x like x to the 1 x cubed x to the 5， etc ceter。

 will all be absent from the series。 The even powers of x are all what we call even functions。

 which means that they are all symmetrical around the vertical x。 Just like cosines。

 So we can now bring back our general expression from the McLaan series and just start writing out the terms。

 The icing on the cake is that at this point。😊，We just noticed that we can build a neat summation notation。

 which fully describes this series without having to write out all the terms。

Notice that this expression doesn't even contain any reference to cosine as all that we need to know is captured by the -1 to the power of n。

 which just keeps flipping from negative to positive and negative again。

 Now that we've done all the hard work， we can simply ask our computer to plot this sequence of increasingly accurate McLaran series。

 which hopefully， starting from a horizontal line at y equals1， well line up with your expectations。

😊，Notice that outside of a region of fairly close to the point x equals 0。

 the approximation explodes off and becomes useless。 By the time we get our 16th order approximation。

 we've pretty much nailed the region shown in our graph here。 although just outside of these axes。

 the function would also be growing hugely positive。

 So you must always be careful when handling series approximations that， you know。

 the domain in which it's acceptable In the second example。

 we're going to take a look at the function F of x equals1 over x， which， of course， looks like this。

😊，It's a nice， simple function。 But notice the discontinuity at x equals 0。

 This is absolutely not a well behaveved function。 In fact。

 it's so badly behaved that when we even try and build the zeroth order approximation。

 we immediately run into problems because we have to perform the operation one divided by 0。

 which is not defined。 And if you try to ask your computer to do this。

 It may give you back the answer N， which stands for not a number。

 So we're going to need to try a different angle of attack。 Clearly。

 we aren't going to have much luck at the point x equals0。 So why not try going somewhere else。

 anywhere else。 Let's look at the point x equals1。 Certainly。

 it passes the first test of being able to evaluate the function at this point。 However。

 moving away from x equals0 means that we're now going to need to use the Taylor series instead of the McLaran series。

 So we now need to find a few derivatives of the function and see if we can spot a pattern。😊。

When we evaluate these functions at the point x equals1。

 hopefully you'll recognize that we get a sequence of factorials emerging。

 just as we did when deriving the power series formula in the first place。

 So if we now substitute these values into our Taylor series formula。

 the factorial terms will cancel and all we are left with is a sum of x minus-1 to the power of n terms with alternating signs。

 which we can simplify to this neat summation notation。 So once again。

 let's now pass this formula to the computer and ask it to plot a sequence of improving approximations。

 starting as ever with a horizontal line。 But this time。

 starting at the height of the function at x equals1。😊。

🎼There are several really interesting features of this particular example which tell you interesting things about the power series more generally。

 Firstly， the approximations ignore the asymptote going straight across it。 And furthermore。

 the region of the function where x is less than zero is not described at all by the approximations。

 Secondly， although the function is gradually improving for larger values of x。

 you can see the tail wildly flailing around as the sign of each additional term flips from positive to negative and back again。

 I hope these two examples have made it clear both how the Taylor series manages to reconstruct well behavehad functions like cosine x。

 But also why they can struggle to deal with something badly behaved like one over x。

 As we bring this video to a close， let's now watch an action replay of these two sequences of improving approximations。

 In the next video， we're going to talk briefly about what it means to linearize a function and see how this relates to the Taylor series analysis that we've seen so far。

 See you then。😊。

![](img/825d258d5260f9a286e475af9e93b2e9_2.png)