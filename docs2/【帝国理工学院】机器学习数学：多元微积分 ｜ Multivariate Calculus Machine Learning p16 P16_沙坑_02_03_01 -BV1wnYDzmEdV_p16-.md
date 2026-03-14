# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p16 P16_沙坑_02_03_01 -BV1wnYDzmEdV_p16-

![](img/f19af98452c28ff1247514d32d7c7142_0.png)

We've now seen that the Jacobian describes the gradient of a multivariable system and that if you calculate it for a scalar valued multivariable function。

 you get a row vector pointing up the direction of greater slope with a length proportional to the local steepness。

😊，In this video， I'm going to briefly introduce a kind of gradient playground to help you further develop your intuition on the Jacobian。

 which will also set you up for the following exercises。😊，In everyday language。

 we use the word optimization to describe the process of trying to make something as good as it can be In mathematics。

 optimization basically means the same thing as much of the research is dedicated to finding the input values to functions which correspond to either a maximum or a minimum of a system。

Examples of mathematical optimization in action in the real world include the planning of routes through busy cities。

 the scheduling of production in a factory， or strategy for selecting stocks when trading。😊。

If we go back to the simplest function we saw in the last section and we said that we wanted to find the location of the maximum。

 we could simply solve this system analytically by first building the Jacobian and then finding the values of x and Y。

 which make it equal to0。However。When the function gets a bit more complicated。

 finding the maximum or minimum can get a bit tricky。 if， as in this case。

 we still have an analytical expression， then we can at least still find the general expression for the Jacobian。

 but now simply setting it to 0 is not only much more complicated。

 but it also is not enough as this function has multiple locations with0 gradient。😊。

If we assume that all of the maxima and minimum of this function can be seen in the region that we're puttingttting here。

 then just looking at the surface plot of our function makes it very clear where the tallest peak and deepest trough are。

We refer to all the peaks as maxima， but in this case， we have a single tallest peak A。

 which we will call the global maximum， as well as several local maxima at C and E。 Similarlyly。

 we refer to all the troughs as minima， and we also have a single deepest point at D。

 which we call the global minimum， as well as a local minimum at point B。 All fairly straightforward。

 However， there's a very important point here。 that's perhaps so obvious that you might have missed it。

 Imagine standing on the surface with its hills and valleys。

 And we're trying to climb to the top of the highest peak。😊，That's no problem。 We just look around。

 spot the tourist mountain and walk straight towards it。 But what if we were walking at night。

 This would be much like the scenario where we didn't have a nice analytical expression for our function。

 So we simply aren't able to plot the whole function and look around。

 Perhaps each data point is the result of a weak long simulation on a supercomputer or maybe the outcome of an actual real world experiment。

😊，These nighttime scenarios very commonly arise in optimization and can be very challenging to solve。

 However， if we're lucky， we might find that using a torch。

 we can see the Jacobian vectors painted on road signs all around us。

 and each one would say peak this way。😊，We would have to remember that although the Jacobians all point uphill。

 they don't necessarily point to the top of the tallest hill and you could find yourself walking up to one of the local maxima at C or E。

 and even worse when you get there， you'll find that all of the road signs are pointing directly at you。

😡，This nighttime hill walkinging analogy is often used when discussing the problem of optimization。

 however， it does have some misleading features， such as the fact that when you're really evaluating a function。

 it's no problem to effectively transport all over the map by teleportation as you can try the function at many different places。

 but there's no need to evaluate everywhere in between and the calculation costs the same essentially。

 no matter how far apart the points are。😡，So we're not really walking。😡，Instead。

 we're going to switch to the analogy of a sand bit with an uneven base。In the following exercises。

 you're going to try to find the deepest point of a sand pit by measuring the depth at various points using a long stick。

 This is a very deep sand pitt。 So once you push the stick down to the bottom。

 there's no way to move it around sideways。 You just have to pull it out and try somewhere else。

Also crucially， just like our night walking scenario。

 you will have no idea what the peaks and troughs look like at the bottom of the pit because you can't see the sanders in the way。

As you work through the exercise， I'm hoping that you'll start to pick up on a few of the subtleties of optimization and hopefully leave you with a few new questions as well。

 See you next time and have fun in the sand pitt。

![](img/f19af98452c28ff1247514d32d7c7142_2.png)