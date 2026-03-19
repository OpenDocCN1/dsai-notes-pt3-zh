# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p89 P89 Statistical Machine Learning Part 15 - Convex optimization, Lagrangian, dual -BV1VhbMzKEts_p89-

![](img/0ade3ec1f4395709011b731502c54a7a_0.png)

Now， I want to show you。How we can solve convex optimization problems at least sometimes with the Lag approach in convex optimization。

 this is a very， very generic approach that can help in many cases， not always。

 but in many cases and in particular it's also going to help us in support vector machines。

 this is why we are going to introduce the solar approach。



![](img/0ade3ec1f4395709011b731502c54a7a_2.png)

![](img/0ade3ec1f4395709011b731502c54a7a_3.png)

![](img/0ade3ec1f4395709011b731502c54a7a_4.png)

![](img/0ade3ec1f4395709011b731502c54a7a_5.png)

The literature on convex optimization is really huge and there exist particular lectures who for a whole semester try to identify how convex optimizationization problems look like。

 what are their properties， how to solve them， what are all the different constraints under which you can source them in a nice way。



![](img/0ade3ec1f4395709011b731502c54a7a_7.png)

![](img/0ade3ec1f4395709011b731502c54a7a_8.png)

![](img/0ade3ec1f4395709011b731502c54a7a_9.png)

I try to squeeze all of this in one lecture。I start with giving the intuition and start then with giving a couple of formal notations and definitions。

 however this is far from being exhaustive and this is all on a very high intuitive level so if you want to know any details you really need to look in the literature or you need to go to a specialized lecture on contextx optimization here we just do it so far that we can that we can in fact solve the SVM dual optimization problem。



![](img/0ade3ec1f4395709011b731502c54a7a_11.png)

![](img/0ade3ec1f4395709011b731502c54a7a_12.png)

![](img/0ade3ec1f4395709011b731502c54a7a_13.png)

![](img/0ade3ec1f4395709011b731502c54a7a_14.png)

Now， let's simply start。We are going to look at convex optimization problems。



![](img/0ade3ec1f4395709011b731502c54a7a_16.png)

And as I said here， what we're going to do is something like a recipe。 It sometimes works。

 and it sometimes doesn't work。

![](img/0ade3ec1f4395709011b731502c54a7a_18.png)

And in this presentation I make all kinds of niceness assumptions in particular。

 I assume that all the functions that we have are continuously differentiable and if the many of the statements still hold if this is not the case。

 but then the mathematical machinery has got much， much more heavy because we need to use convex geometry and this is much more involved then simply taking gradients of a function。

😊。

![](img/0ade3ec1f4395709011b731502c54a7a_20.png)

![](img/0ade3ec1f4395709011b731502c54a7a_21.png)

![](img/0ade3ec1f4395709011b731502c54a7a_22.png)

![](img/0ade3ec1f4395709011b731502c54a7a_23.png)

Speaking about gradients， here we are。

![](img/0ade3ec1f4395709011b731502c54a7a_25.png)

Let's simply recap what is the gradient of a function just to make sure that everybody really knows that if we have a function that F that goes from R D to R。

 the gradient of the function is the vector of partial derivatives。😊。



![](img/0ade3ec1f4395709011b731502c54a7a_27.png)

![](img/0ade3ec1f4395709011b731502c54a7a_28.png)

So in each coordinate， you can compute what is the derivative of the function with respect to this particular coordinate。

 For example here we have the partial of derivative with respect to x1。



![](img/0ade3ec1f4395709011b731502c54a7a_30.png)

![](img/0ade3ec1f4395709011b731502c54a7a_31.png)

And now we have sorry we haveD such coordinates for the D and so we haveD。



![](img/0ade3ec1f4395709011b731502c54a7a_33.png)