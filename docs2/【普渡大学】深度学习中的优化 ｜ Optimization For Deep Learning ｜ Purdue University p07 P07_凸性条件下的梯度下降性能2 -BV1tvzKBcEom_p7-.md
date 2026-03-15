# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p07 P07_凸性条件下的梯度下降性能2 -BV1tvzKBcEom_p7-

🎼，🎼Yeah。Welcome back。 So we were talking about gradient descent algorithm， and we introduced it。

 and we were talking about this performance。😊，And if you remember we using our main proposition。

 we sort of were able to show that the accumulated subopality when you run the gradient is an algorithm can be bonded by something like this。

 right？ And we say that we desire this to grow gracefully with the total number of iterations。😊。

And this could happen if we have a control on how large the norm of these gradients are， okay。



![](img/d82193eb39707dace858b6b69305f2fe_1.png)

![](img/d82193eb39707dace858b6b69305f2fe_2.png)

And to make it formal， we're going to specifically focus on a class of functions。That for them。

 we can guarantee the norm of the gradient is uniformly bonded， the by some constant g。



![](img/d82193eb39707dace858b6b69305f2fe_4.png)

And that to us is basically the case of Gly functions。 So these。

 you can imagine that there are continuous functions that we have some control on their degree of continuity。

 Okay， so let's go first over the definition。 And then I'll try to build some intuition。 Alright。

 so here's our definition。 a function in F。

![](img/d82193eb39707dace858b6b69305f2fe_6.png)

Is G Lies， if and only if this inequality is satisfied。For some constant G and for all vectors。

 X and Y。 Okay， so what's the intuition here， we are essentially bonding the changes that could happen in the function value as a result of changing the input。

 Okay， so essentially， we have， if you will bonded sensitivity。

 We have a control on the degree of sensitivity。

![](img/d82193eb39707dace858b6b69305f2fe_8.png)

In other words， we have a control on the， the continuity of the function。 Okay。

 the larger this constant G E， which we call it the luis constant。If we change the input slightly。

 we're gonna see a larger change in the， in the function value。 And if G is a small。

In the extreme case， when g is equal to0。If I change the input。

 there is not going to be any significant change in the output。 Okay， for instance。

Let's consider the function F x equal to some constant。 Let's call it 3， okay。

So the difference between F， X and Fy。For any。Different Ex y is 0。 Okay， So in some sense。

 this is a function that is highly robust with respect to changes in the input。Now。

 let's get more in。 And another way to think of this definition is that we have a bonded slope。 Okay。

 so by rearranging。

![](img/d82193eb39707dace858b6b69305f2fe_10.png)

We can't think of this as a slope， right why？So if you recall from your callus courses。

 if I have a function here， F。

![](img/d82193eb39707dace858b6b69305f2fe_12.png)

this is the x axis， okay。So。

![](img/d82193eb39707dace858b6b69305f2fe_14.png)

A slope。Of the function can be defined as basically sort of the， the angle that that is forming。

 right， So so here， for instance， the flow is equal to one。 Okay， but if I consider。

A function that is more sensitive with respect to the changes in the input。 you expect to have。

 let's say。So let's say， this is my function， so。You expect to see a larger slope。 Okay。

 so for instance， here， the slope is equal to to。 So another way to think of lip systems is that it provides a bond on the slope。

 Okay， and the smaller it is， the smaller the slope， therefore。

 the less sensitive the function is with respect the changes in in the in the input， okay。

And think of this as a slope is also useful because a gradient is is nothing but basically a slope in higher dimension。

 right， So you should think of the norm of the gradient。As a slope。So， this is basically。

He's kind of。slope， okay。So therefore lipishness， if a function is lipes or Glipes。

 we we are saying that slope is bonded or the gradient norm is bonded uniformly by this constant G。

 so therefore you should be able to see that this is a definition that's going to be useful for us to leverage in our previous result。

And show that the accumulates of optimalology of the gradient is an algorithm grows gracefully with the total number of。

The the iterations。So as there is some here， a function is different。

 If the function is differentiable， we can say that it isipus if。

There exists a uniform bond on the norm of the gradient。



![](img/d82193eb39707dace858b6b69305f2fe_16.png)

Alright， so before going back to our discussion in descent。

 let's go over some examples of functions to see whether they're lipses or not， okay。



![](img/d82193eb39707dace858b6b69305f2fe_18.png)

![](img/d82193eb39707dace858b6b69305f2fe_19.png)

So first example is a square square root function。And we want to see whether the this is lipses or not。

 essentially has the bonded the slope or not。 when x belongs to this interval versus x belongs to to the second case。

 the interval between 0。5 and 5 okay。So let's see what do we expect。 Okay， so if I draw the。

 the square root is something like this。 So this is the function F of x。Ecal to a square of x。

This is the x axis。This is 0， and then let say this is1， et cetera， okay。So， as we can see here。



![](img/d82193eb39707dace858b6b69305f2fe_21.png)

Then x is approaching 0。Right。诶。They， this tangent line becomes a vertical line。Essentially。

 the slope is approaching infinity。 Okay， so here slope。Is equal to infinity。

 So we expect that when x is near 0， the function is not Lies because we cannot uniformly bond the。

 the norm of the gradient。 And that is indeed true， right。

 So the easiest way to calculate the Liis constant of any function is to calculate the gradient。

 In this case， is's a one dimensional function。 So we just have to find the derivative。

 What's the derivative of F。Just one over to a square of x。 And here。

 we can see that as x approaches 0。The gradientian approaches infinity。 Okay， so therefore。

 this case is not eipes function。 So the score root is not eipis function。

 when x belongs to this interval。 Okay， because we can get arbitrary close to to 0 here。



![](img/d82193eb39707dace858b6b69305f2fe_23.png)

On the other hand， for the second case。You can easily see that it T slipes。 Why。

 Because I can uniformly bond the gradient the end for all xes that belong to this interval。 Okay。

 so we can show that for all x belonging to the interval。5 and and1。The gradient is at most。1 over。

 so the gradient or the derivative in this case is is a decreasing function of x。

 So it is at most one over two times S square of 。5。 And this is some number， which is。

Which is bonded， right， So it's not infinity。 So therefore， in this case。

 the function is actually lipses，Alright， so the second case， the absolute value function。

 So let's first draw to see how this function looks。Okay。So here again。

 we we can determine whether it slip this or not by looking at the slope。

So here the slope is equal to 1。 here， the slope is equal to -1。Okay， so for all cases。

 the slope is bonded so。Here， I want to point out that the the function is not differentiable。

But that's， that's okay。 Okay， so for almost all point in in， for all point in in R。

 the slope is bonded。 Therefore， the the function is， is actually Lies， right， And again， you can。

 you can also show it mathematically， right， So what's the definition。

 The definition is the function is Lies。

![](img/d82193eb39707dace858b6b69305f2fe_25.png)

If this condition is， is satisfied。So for the absolute value。Function。

 this is nothing but saying that。This is less than one times itself。So therefore。

 this function is lipes with a constant with the lipses constant of one。Right right。

Now lets move on to the next example。So the exponential function。So it， it grows very fast with。

 with with X。 Okay， so what's the derivative， again。

 a simple approach to find thechi constant is typically to find the gradient。 Okay。

 so the gradient here。Is the exponential function itself。

 And here you can see that if there is no restriction on x， this can go to infinity。

As x goess to infinity。So in this case， the function is not Liches。 On the other hand。

 when I restrict x and say， hey， it belongs to to some close interval or close compact set。

 if you will， the neuro of the gradient or derivative in this case is actually bounded。

 In particular， this is an increasing function in x。 So F prime is less than equal to E to B。

 So therefore this is my dipps constant。 and is this is bounded。



![](img/d82193eb39707dace858b6b69305f2fe_27.png)

![](img/d82193eb39707dace858b6b69305f2fe_28.png)

![](img/d82193eb39707dace858b6b69305f2fe_29.png)

![](img/d82193eb39707dace858b6b69305f2fe_30.png)

All right。Now， I hope you you're seeing a pattern that sometimes the function may not be lipes globally。

 but if we consider the function locally， it may be lipes right and in fact。

 that's typically the case that for all practical regions of interest。

 we can assume that the functions or lipes at the cost of having a very。

 very large lipes constant and that could impact how loose the bonds that we are establishing are going to be for our training algorithms。



![](img/d82193eb39707dace858b6b69305f2fe_32.png)

![](img/d82193eb39707dace858b6b69305f2fe_33.png)

![](img/d82193eb39707dace858b6b69305f2fe_34.png)

Allright， so let's also go over to the last example again， So the square function。

It looks like something like this， plus the derivative。



![](img/d82193eb39707dace858b6b69305f2fe_36.png)

Is basically2 x， and it goes through infinity as x goes through infinity。



![](img/d82193eb39707dace858b6b69305f2fe_38.png)

So we cannot bond the derivative uniformly with some constant。 So in this case。

 the function is not Lies。 On the other hand， it will be lipes if we restrict the domain of the function to some close compact set。

Oh。In that case， F prime is basically less than equal to。To， to anyway， right。But therefore。

 when I receive it， the function becomes slipes。Alright。

 so hopefully these examples give you an idea of of what kind of functions are lipses。

 what kind of functions are not。 And the main idea is that functions that have a bonded good and norm。

 essentially， the slope is is bonded。 the are lipses。

 We have a quantify a way of talking about how sensitive the function is with respect to changes to its input。

And many times we can， if we put our focus to a specific interval， which is close and compact。

 we can。Assume that the function is actually leapes。

 despite some functions not satisfying the lipses condition globally。



![](img/d82193eb39707dace858b6b69305f2fe_40.png)

All right。

![](img/d82193eb39707dace858b6b69305f2fe_42.png)

With that， let's see and and talk about the implication for the gradient is an algorithm。 Okay。

 so now， in addition to convexity， we are imposing that our function is G Lies。 And again。

 the main idea is that we want to have a control on how large the gradient that we are observing as we run the gradient gradient is an algorithm become。

 okay。Now， let's also define this shorthand nousation D， which essentially captures。

How close to the initial to the to the optimal solution or one of the optimal solutions I am at initialization。

 Okay， so this is a measure of the error at initialization， essentially。So from our proposition。

 if you remember， we established this bond on the acculators optimal gradient and is an algorithm。

Now， by lipence， the following theoryem is going to become almost trivial。

 So if the function is Glipist and convex gradient descent， which if you recall。

 follow this specific update where we update our parameter by going to the opposite direction of the gradient while incorporating a specific learning rate E。



![](img/d82193eb39707dace858b6b69305f2fe_44.png)

![](img/d82193eb39707dace858b6b69305f2fe_45.png)

Is gonna satisfy for the following software gap。As long as I said the step size or or learning it to be something like this。

 Okay， so what's it bound。

![](img/d82193eb39707dace858b6b69305f2fe_47.png)

So， so basically， what I've done， I just plug in this E into this inequality and divided by， by T。

 Okay， And this gives me the following part。And the way to interpret it is to say that they are not the average。

So oalology。

![](img/d82193eb39707dace858b6b69305f2fe_49.png)

Is bounded by D G square of T。

![](img/d82193eb39707dace858b6b69305f2fe_51.png)

Okay， so let's see what the bond says。It says that on average。



![](img/d82193eb39707dace858b6b69305f2fe_53.png)

You're going to find the optimal solution。As you increase the。

 the total number of iterations capital T。 Okay， so as I run my algorithm more and more。

 I'm gonna find the optimal solution。 I'm gonna get k and k to the optimal solution。

 I'm gonna reduce the optimalality of my solutions， okay。

It also says that if you're further away from the initialization。

 you're going to have a larger bond because D appears in the numerator and similarly。

 if you optimizing a function that is more sensitive。You may need to。

 you're gonna potentially converge a store。 Okay， So if the function as a。



![](img/d82193eb39707dace858b6b69305f2fe_55.png)

Again， better condition， lower sensitivity， if you will。

 we should be able to optimize it more easily。

![](img/d82193eb39707dace858b6b69305f2fe_57.png)

Alright， so you may ask how we can calculate this step size or why we are calculating this step size。

Essentially， what will happen is that we're going to have， let's say， error。



![](img/d82193eb39707dace858b6b69305f2fe_59.png)

Lis than equal to some bond。And this bond is a function of E。So what we have done， basically。

 we have minimized。Dpon。As a function of Eta and find the best step size， if you will。

 we are find the best constant and step size。可。And this is a very simple optimization problem。

 So it turns out that the part as a function of E is is sort of equivalent to。

Minimizing aquatic function。So by just taking the gradient of that。

 you should be able to find this a subs。

![](img/d82193eb39707dace858b6b69305f2fe_61.png)

Bor。So let's talk about some some remarks。Essential。

 I first want to talk about how to output the solution。

 because the last result only tells us what's the average sub optimal multi gapap。 Allright。

 and in particular， I want to talk about three approaches。

 The first approach is typically what we do in practice， right？

 So we run the algorithm for a certain number of iterations， Let's say 100 iterations。

1000 iterations， etcter。 And we said our solution to be what we what is the last it。

 What's the last point we find after running the gradient is an algorithm， Okay。

 and the idea here is that in practice this should this tend to to enjoy better performance。

 meaning it tends to enjoy lower sub optimalality okay。



![](img/d82193eb39707dace858b6b69305f2fe_63.png)

嗯。One， if you will drawback of the analysis we presented in this course。

For gradientian descent is that we cannot guarantee whether the last solution is gonna be。

 is gonna enjoy the best performance or not。 So for that， we need a different analysis。

 more complicated one， if you will。😊，And that is beyond the scope of dis course。

 But the main idea is that the role of the step size becomes a lot more crucial。

 and we have to actually change the step size when we go from one iteration to the next okay。

 and this is something that we're going to talk about later in the course when we discuss the importance of learning re tuning when optimizing the models。

Alright。But there are two other solutions for which the analysis we presented actually lead to peruvability guarantees。

The first one is。Instead of opt to output in the last solution， what you do。

 you take the average of all the interests you've encountered when running gradientian descent。 Okay。

 so this is basically the solution we're going to output。



![](img/d82193eb39707dace858b6b69305f2fe_65.png)

No。Why is this a good idea。 Remember， we assume that our function is convex so we can leverage the convexity definition to show that this solution enjoys approvalable territory guarantee。

 So this is the bond we found。😊，On the average of the multi gap and it turns out， again。

 by using convexity here。This average so tiality is going be larger than basically the soity of the average solution。

 Okay， and here I'm just using the first definition of the convexity， convex functions， right。



![](img/d82193eb39707dace858b6b69305f2fe_67.png)

![](img/d82193eb39707dace858b6b69305f2fe_68.png)

If you recall， the definition was。For instance， f of lambda x plus 1 minus lambda y。

He is less than equal to lambda F of x。Plus，1 minus lambda。FO5。Okay， essentially， we are saying that。

The value of the function at midpoint here。Is lower。Then。



![](img/d82193eb39707dace858b6b69305f2fe_70.png)

The average of the function values。Right right， so therefore by conity。



![](img/d82193eb39707dace858b6b69305f2fe_72.png)

The taking the average of all its threats is going to be。

A solution that enjoys a approval bond on its suboptiology。

But I want to point out here that taking the average only makes sense。If your function is convex。

 Okay， so in practice， especially when it comes to optimizing deep models。

 this is not going to be something meaningful， okay。

And the idea is that if you have a non comicx function， let me show it here。

You may have two solutions that are globally optimal， but once you take the average。



![](img/d82193eb39707dace858b6b69305f2fe_74.png)

You may find a solution that is actually locally a maximum， a local maximum of the function。 Okay。

 so taking the average only makes sense if the function is noncomx where we're not gonna to encounter these cases that are always due to noncomity。



![](img/d82193eb39707dace858b6b69305f2fe_76.png)

All right， and the last way of outputting a solution is I would say， an approach that is preferable。

When you are stating。Theoretical guarantees， especially for non convictx functions。 Okay。

 so what we do here。We basically sample one of the it that we have encountered when we were running the gradient decent algorithm。

 uniform me as random。 So what that means is that。Let's say I run my gear that I 400 iterations。

To ask with this solution， I'm going to pick the first one with probably one over 100。



![](img/d82193eb39707dace858b6b69305f2fe_78.png)

Or I'm going to pick the second volume imp purely 1 over 100， etc ceter。



![](img/d82193eb39707dace858b6b69305f2fe_80.png)

No。On expectation， this random solution is gonna satisfy the same bond that we found before。 Okay。

 and the reason for that is that we are output putting the solution uniformly at random。

 So this expectation is exactly equal to the average sub of the multi。

And one idea behind this is that， as you increase T。

As you run your algorithms for more and more iterations， the the later its are going to be very。

 very similar。Therefore。It's going to be more likely that we select something that resembles the the later it reads。

So therefore， we're gonna sort of emulate the performance of the last it。

 which which we expect to be， to be better。

![](img/d82193eb39707dace858b6b69305f2fe_82.png)

![](img/d82193eb39707dace858b6b69305f2fe_83.png)

All right。So let's talk a little bit more about the bond that we， we found。 So again。

 the bond was that average sub optimality is less than D G over a square of T。 Now。

 I I want to talk about a few things。 First of all， it is sometimes useful to hide the constants。

 In this case， D and G。

![](img/d82193eb39707dace858b6b69305f2fe_85.png)

And you just focus on what's the rate at which the error goes to 0 with respect to the number of iterations。

 Okay， and in this case， we use what we call the O notation， right。

 So O notation just hides the constant and mainly focuses on the total number of iterations。

 if you will。 So in this case， the rate at which the the error goes to 0 is sort of one over square of T。



![](img/d82193eb39707dace858b6b69305f2fe_87.png)

And we call this a subly narrow rate。As we discussed in our optimization basics of optimization。

lectureture。AndAnother thing that I want to point out is the role or the regulating role that the learning rate plays。

 Okay， so the learning rate is proportional to D， but inversely proportional to G。

 So to to interpret this。We can think of E during the following。 if you're further away。

Atization from the optimal point。Eta has to be larger to make sure we converge faster。

 That's why D appears in the enummerator， right， So the further we are at initialization。

 the larger the step size has to be。On the other hand， the sharper the function is。

The more sensitive the function is。We have to be careful。With the， sort of the， the。

 the steps we are taking。 So we have to make sure that the steps we are taking are small so that we we converge。

 Okay， so that's why G appears in the denominator for the best constant of suicide。啊。Yeah。

One drawback of this slip size is that it depends on D。

 which is the sort of the error at initialization N G。So these two constants。

Are not necessarily known in practice。 For instance， D to know the。We have to sort of have an idea。

Where the opt is where the optimal solution is or where one of the optimal solution is located。 Okay。

 so this is a quantity that we don't know。 Therefore， we don't know the， right。

 That's why there has been a lot of development in the past few years to dev algorithms that are sort of adaptive。

 meaning that they can estimate these online quantities that are essential for the convergence of these algorithms on the fly as you are running running the algorithm。

And this is something we're going to talk about later on in the course。All right。

 so one other remark is that there is no implicit。 sorry， There is no explicit。嗯。

Dependence on the dimension。So we assume that W is a D dimensional vector。

 So if you have a neural network with100 million parameters， D is basically 100 million。No。

Here in the band。A small D doesn't show up at all。AndThis is very desire。

 It is a very desirable property of the greatness algorithm。

 That's why we call these kind of results， dimension free。Results。

To mean that there is no explicit dependent on on the dimension。 And indeed。

 there are algorithms in the optimization literature that are not dimension free。

Such as the ellipoid method。And this is one reason that we don't see them these classical optimization algorithms to be applied in machine learning and deepening optimization problem。

 given how larger scale the problem that we are facing are。And however。

 I want to point out that D typically finds this way implicitly。In the bond。And in this case。

 it finds its phase through G and D， okay。And the easy way to see this is， again。

 let's talk about the initial error， the difference between W and WS star。

 So these are the dimensional vector。 So if I assume that each coordinate is some constant。

Let's go to a small C。I should expect that。When it says D squared。



![](img/d82193eb39707dace858b6b69305f2fe_89.png)

Is your silver。Or if from1 to D。Of。The differences between the coordinates。 So W。

 the I coordinate of W I W 1 minus the I coordinate of W star a square。

 And if each coordinate is some constant， this is something like the。Cia square。Therefore。

These is basically proportional to a score of the。So although there is no explicit dependence on the dimension。

 there could be implicit dimension and dependence on the dimension through the constants。

 such as the initial error， as well as the Lies constant。All right。

It is also sometimes useful to think about iteration complexity。

When or describe the bond that we found through the lens of iterationeration complexity。

So this basically means that what should be the total number of iteration to find an epsilon accurate solution。

 Okay， so essentially what you do， you set this to be called to epsilon and do some rearranging to find the minimum number of iterations that you need to run your gradient in an algorithm such that the average of is at most epsilon because of your epsilon close to to a solution。

 And if you do so， this is what you're going to find。



![](img/d82193eb39707dace858b6b69305f2fe_91.png)

![](img/d82193eb39707dace858b6b69305f2fe_92.png)

And this is the way to use the own notation here。To hide the constant and say that the iteration complexity is basically one over epsilon a square。

Right。And the last remark is， so what we have done， we have provided an upper bond on the error。

 Okay， and you could ask whether this is a good upper bond or a bad upper bond。

Is the bone tight or not。So this is a question that is relevant to driving lower bonds， right？

 So what's the best that any algorithm。Can can do then optimizing a function。

If that algorithm has only access to let's say the gradient information。

You then in this one algorithm， maybe I can come up with a better algorithm。Okay。

It turns out for this class of function， convets and lipses。We can't do better in divorce case。

However， I want to point out that the practice is typically noisr。So we could， in practice。

 have algorithms that converge。Paaster than the is an algorithm。

And that's basically what motivates us to design algorithms。

 training algorithms to optimize deploy problems。More efficiently。



![](img/d82193eb39707dace858b6b69305f2fe_94.png)

So in the next lecture， we're going to talk about a variation of the gain in sin。

 which is more applicable to larger scale problem。 And that's a stochastic sin。

 I'll see you next time。