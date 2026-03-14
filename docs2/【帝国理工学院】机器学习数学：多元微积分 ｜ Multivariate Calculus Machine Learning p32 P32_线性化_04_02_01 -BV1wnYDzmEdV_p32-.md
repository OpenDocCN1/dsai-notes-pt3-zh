# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p32 P32_线性化_04_02_01 -BV1wnYDzmEdV_p32-

![](img/d5aacb4da9e0a7700e15998be6ff8e80_0.png)

In this session， we're just going to take what we've learned about Taylor series so far and reframe it to a form that will help us understand the expected error in an approximation。

 So as we've already seen， we can build up a sequence of gradually improving approximations to functions by adding higher power terms。

 All I'm going to do now is change the notation of some of the terms。

 So if we take our first order approximation as an example。

 what this expression is saying to us is starting from the height F of P。 As you move away from P。

 your corresponding change in height is equal to your distance away from P。

 times the gradient of your function at P。😊，So in a sense。

 rather than using gradient equals rise over run， we are just rearranging to rise equals gradient times run。

😡，You are ultimately going to use your approximation to evaluate the function near P。

 as you must already know about it at P。😡，So I'm now going to say that our distance from p。

 which we currently call x minus p， we will now call delta p to signify that it represents a small step size away from p。

 and we can also recast x now in terms of P saying that X is just p plus delta P finally it actually is now time to say goodbye to P as in our first order approximation everything is actually in terms of P so all I'm going to do is swap all the p's for x's as this is the form that people would usually expect to see it in。

😊，I'm going to do it all at once to make it as painless as possible。😡。

I haven't changed anything conceptually， I've just written an X everywhere where we used to have a P。

 and we can now of course， also rewrite our Taylor series expression in this new form with just X and deelta X So we're in good shape to talk about approximations what I now want to know is when I use the first order approximation instead of evaluating the base function How big should I expect the error to be。

😡，You can see， for example， that the gap between the white and green lines grows as we move along the x axis away from the point x。

 Well， one way to think about it is that we know our function can be exactly represented by this infinitely long series。

 So although we won't be able to evaluate all of the terms。

 we do know that the next term along ie the first term that we ignore when we're using our first order approximation has a delta x squared in it。

 This means that if we can say that deelta x is a small number。

 then deelta x squared must be a really small number。

 and simply deelta x cubed must be a ridiculously small number So we can now rewrite our first order approximation to include an error term。

 which we just say is on the order of delta x squared or equally that it is second order accurate。

 This process of taking a function and ignoring the terms above delta x is referred to as linearization。

 And I hope it's now clear to you why that's the case。 taken。😊。

Some potentially very nasty function and just approximated it with a straight line。

 The last idea that I'm going to share with you in this video is perhaps the most interesting as it brings us right back to our rise over run approximation that we met at the beginning of the course。

 the green line is our first order Taylor series approximation to the function at the point X。

 which is， of course， also the tangent to the curve at X。 But let's now add another line。

 which is the approximation to the gradient at x using our rise over run method with a second point deelta x away。

 We use this forward difference method to help us build the definition of a derivative at the beginning of the course。

 and we noticed that as deelta X goes to0， the approximation becomes exact。😊，However。

 what happens if deelta x does not go to 0 and the second point remains some finite distance away from x。

 Well， your calculated gradient will now contain an error， And once again。

 we can rearrange the full tail series to work out how big we'd expect that error to be with a bit of slightly fiddly algebra。

 we can rearrange this the expression such that the gradient term F dash of x is isolated on the left hand side。

 because the series is infinite。 This is still an exact expression for the gradient to x。

 but what we get on the right hand side is something that looks suspiciously like the rise over run expression plus a collection of higher order terms。

 If we notice that the first of the higher order terms has a delta x in it。

 We know that we can now lump them altogether and say that using the rise over run method between two points with a finite separation will give us an approximation to the gradient that contains an error proportional to delta x or more。

😊，Simply per the four difference method is first order accurate。 That's all for this video。

 It might seem a little odd to go to all that trouble just to get an idea of the error in an approximation。

 but it turns out to be a hugely important concept when。

 as is typical we ask computers to solve numerically rather than analytically。 See you next time。



![](img/d5aacb4da9e0a7700e15998be6ff8e80_2.png)