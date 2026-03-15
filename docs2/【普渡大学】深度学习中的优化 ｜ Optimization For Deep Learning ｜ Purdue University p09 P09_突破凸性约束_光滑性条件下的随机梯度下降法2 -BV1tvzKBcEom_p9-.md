# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p09 P09_突破凸性约束_光滑性条件下的随机梯度下降法2 -BV1tvzKBcEom_p9-

🎼，🎼Yeah。Welcome back。 So we， we were talking about how we can study gradientian descent and nasto gradient descent performance on non conx function。

😊，And we argue thatputness is a condition we need， given the fact that we are focusing on the norm of the gradient as our convergence notion。

In this video， I， I w to talk a little bit about another benefit of a smoothness。

 which provides a new perspective for us when we talk about Gary anden。

So we talked about getting and， I would say from two perspectives so far。 First。

 we talked about it from the perspective fixed point calculation。

 which basically said that finding a stationary point is equivalent to finding fixed points of another function。



![](img/7a1e10fb70685b449942d5ad94b55684_1.png)

A national algorithm is fixed monitoring， which happens to be Gary and decent。



![](img/7a1e10fb70685b449942d5ad94b55684_3.png)

![](img/7a1e10fb70685b449942d5ad94b55684_4.png)

We also talked about the fact that gradient descent means that we are locally following the direction of descent。

 So locally， we are minimizing the function。 So therefore it is it is a good idea， to explore。



![](img/7a1e10fb70685b449942d5ad94b55684_6.png)

Now here's another perspective， thanks to smoothness。



![](img/7a1e10fb70685b449942d5ad94b55684_8.png)

Okay， which I think is is a is a very nice way for us to。

 to think about how to develop better and more general。Algorithms。



![](img/7a1e10fb70685b449942d5ad94b55684_10.png)

So consider minimizing a function F iteratively。 And that's typically what we do。 For instance。

 SD and and Garycent， right。哦。What we desire is that we always keep making the solution better。

What does that mean if I'm minimizing the function。

 I want to make sure that the function value at W T plus1 is always。



![](img/7a1e10fb70685b449942d5ad94b55684_12.png)

![](img/7a1e10fb70685b449942d5ad94b55684_13.png)

Lower than the function value at W T。The current solution。 Okay。

 so this is basically saying that we want our method to satisfy the decent property。



![](img/7a1e10fb70685b449942d5ad94b55684_15.png)

对。Ideally， we also want to go one step further。 So we want to even maximize the progress。

That we are making。 So by that， I mean， let's define this function to be the progress function。

 The amount of progress that I'm going to make if I go from W T。

 the current solution to the next solution。 W T plus1。

 So I want to find the next solution such that this progress is， is maximize okay。So to do this。

 there is a very nice recipe， which is called majorurization minimization。

When you are minimizing a loss function or equivalently minorization， maximization。

 when you are maximizing， let's say， profit， utility or reward。 Okay。

 and the names are just what the procedure is。 So it means that if youre。



![](img/7a1e10fb70685b449942d5ad94b55684_17.png)

![](img/7a1e10fb70685b449942d5ad94b55684_18.png)

Aiming to minimize the function。You iteratively majorize the function。

 meaning that find an upper bond on the function and minimize that instead。

 and you keep you keep doing this for a certain number of iteration until it converges。



![](img/7a1e10fb70685b449942d5ad94b55684_20.png)

For maximization。Instead， what you do， you minorize the function。

 you find the lower bound under the function。And then you you maximize that instead。

 And if you do this iteratively， hopefully you'll find a good solution。

So we're going to talk about this procedure here。A little bit more in in more details。

 And we're going to talk about the connection to go in the descent and see how we can leverage that to。

 as I mentioned， develop more advanced algorithms。

![](img/7a1e10fb70685b449942d5ad94b55684_22.png)

Right。So as I said， we want to maximize with the progress and we will do so through a thgate upper bond。

 So this is the minor the majorization step that I talk about。

So we we assume that we have an upper bond on the function。Which has the following properties。

The first property is that the upper bone is tied at the current solution。Okay。

The second probability is that it is an upper bond。Okay， mean it is always。

It always lies above the function value。 So， for instance， if this is my function F。



![](img/7a1e10fb70685b449942d5ad94b55684_24.png)

F of W。This is a valid。Tourggate function。

![](img/7a1e10fb70685b449942d5ad94b55684_26.png)

And let's call his deputy。Lets call it W stuff。The minimizer。 Okay， so as we can see here。

 U T is touching the the function and。 So it is tight。 It always lies above the function。

 So it's an upper bound。 And the last property。

![](img/7a1e10fb70685b449942d5ad94b55684_28.png)

It's something that we want to be satisfied。Is that the law the。

 the the bond or the the surrogate function is simple to minimize， okay。Because as I mentioned。

 the procedure is to minimize this sorogate function iteratively。 So this is a better be simple okay。

And what will happen hopefully， is that as you。As you resort to this procedure。

 you're going to find other upper bounds。Such that when you minimize them。



![](img/7a1e10fb70685b449942d5ad94b55684_30.png)

Iteratively， you're gonna convertverse to the minimizer of the original function。 Okay， so therefore。

 what's our majorization， minimization procedure。

![](img/7a1e10fb70685b449942d5ad94b55684_32.png)

Every time you find the minimizer of the， of the。Of the surgate function。

 And then you update the surrogate。To go from the current surrogate U to the next surrogate。

 U plus fund， such that the new surrogate also satisfies this city property。

 Me it is a valid upper bond。 It is tight。

![](img/7a1e10fb70685b449942d5ad94b55684_34.png)

![](img/7a1e10fb70685b449942d5ad94b55684_35.png)

At the current solution， and also it is simple to minimize。Now this seems like a mathematical。

 very mathematical and broad algorithm。 and in fact。

 there are many examples of this algorithm that you may have seen in your other courses。

 for instance， the Kme algorithm， which is perhaps one of the most famous algorithms when you talk about clustering problems。

Also provides learning problems where you want to work in categoriesize。

ADa into different categories or clusters。 and you only have access to basically feature vectors。

 You don't know the labels。InAnother instance is the famous expectation maximization algorithm。

 is which is very useful when you want to determine the parameters of mixture models。

 such as Gaussian mixture models。Now， our goal is to show that gate in descent is also of an example of meization minimization algorithm。



![](img/7a1e10fb70685b449942d5ad94b55684_37.png)

When the function is smooth。

![](img/7a1e10fb70685b449942d5ad94b55684_39.png)

Right。So first， let's talk about void those specific properties。

 And the idea is that with those properties， we actually have a guarantee on the amount of progress we are making。

Essentially， we ensure that we always are making progress。

 Our algorithm satisfies the decent property。 Therefore， it should converge to a， to a nice solution。

 okay。So， so let's see， let's see this a little bit more mathematically。

 So this is the definition of our progress function。

It was the progress I was making if I go from with the current solution the to the next solution W plus1 now using the fact that our surrogate function is basically an upper bound on the function。

 I can replace this term with this term to find a lower bond on the progress again。

 we want to find a lower bound on progress to make sure that we are always making progress right and that lower bond hopefully is a non trivial lower bound。

So this is why we need the upper bound property。Okay， now I claim that we can again。

 lower one this with this line。Because。W T is the minimizer of。Youty。Okay， so。Therefore。By sorry。

 the ability T plus one。Is the minimizer of U。 So by by changing the ability plus to D ability。

 I again get another lower one。And finally， I can use the tightest property。This is nothing but F T。

So this line is actually an anequality， not inequality， but that's okay。Okay。

 and therefore I'm I'm going to arrive at the function value at WT minus the function value WT。

 And that's basically 0。 What does this mean， It means that I'm always making progress。Right， why？

 Because the conclusion is that。F of w is always。Large than F of W T plus1。

 So I have the decent property。

![](img/7a1e10fb70685b449942d5ad94b55684_41.png)

Okay。Now， if we also assume that the loss is bonded from below。

 which is not a bad assumption at the end of the day， we are minimizing a function。

 So if it's not bonded from below， the minimizeizer is， is basically the minimum value is infinity。

 minus infinity。

![](img/7a1e10fb70685b449942d5ad94b55684_43.png)

So if you make this assumption。Given that we are always reducing the function value。

 were going to converge eventually。对。So it will converge or stop at a stationary point eventually。

But this doesn't say how many traditions you have to on your algorithms to find let's say。

 an approximate solution。This is called。Point of time analysis， or known as synthetictical analysis。

 An example of that is basically the tolerance we've talked about so far in the course， okay。



![](img/7a1e10fb70685b449942d5ad94b55684_45.png)

All right。Now let's talk about why gradientian decent is an example of majorurization minimization procedure。

And the idea is that thanks to a smoothness， we have a natural upper bond on the function。

Which happens to be convex quadratic。Therefore， it is easy to minimize。

So basically thanks to the smoothness， we can find this nice sorogate function that satisfies all of those3D properties that we needed。

So we should be able to minimize the function that are smooth quite easily by using majorurization minimization。

对。So again， by smoothness， we have a convex quadratic upper one on the loss。

W you can use it to be our surrogate function， essentially our surrogate function is something like this。

Is F at WT。So this is basically a constant term。This is a linear term。

And this is a con quadratic term。 Okay， so this term is going to look something like that。Now。

 let's check that this satisfies our properties。 First of all， it is tight at WT Y。

Because if I set w to be WT， this term， the first this term becomes 0， this term also vanishes。

So it's easy to say it this tota WT。It is also always an upper bond on the function。

Because our function is a smooth。And this upper bound is strongly convex。 Okay。

 so it's very easy to optimize。 Okay， now， recall algorithm or majorurization immization purposes procedure。

 The idea was that you basically update your solutions by minimizing the circuit function。

Given that my function is a strong economics function。

All I need to do to find this minimizer is to take the gradientian and set it equal to Brazil。

So essentially， you have to do this。If you take the gradient is going to be something like this。

 the constant term， the gradient is 0， the linear term， the gradient is basically the slope。

 and then finally the guarantee of a quaratic function is going to be something like this。



![](img/7a1e10fb70685b449942d5ad94b55684_47.png)

Now， if you do some rearranging。The solution， W is going to be W T minus1 over L times the gradient。

And this is something we saw before， right This is exactly gradientian descent with learning rate of1 over L。

 right， So essentially the， the version of Gaian descent for which we we that theorying。Okay。

More generally。 So therefore， this result shows that gradient with step size is an instance of the meurization minimization algorithm。

 And， in fact， any gradient decent method。With the step size， which is smaller than 1 over L。

 is also an instance of majorurization minimization。Because that will also result in。



![](img/7a1e10fb70685b449942d5ad94b55684_49.png)

An upper bond on the function。Good。So essentially， what will happen is that you're gonna change this。

都呃。V over to Eha。So if EO is less than one where L。This term will be larger than L over 2。 Therefore。

 it is still a valid upper bond。

![](img/7a1e10fb70685b449942d5ad94b55684_51.png)

![](img/7a1e10fb70685b449942d5ad94b55684_52.png)

All right。Now， this is nice because this provides a recipe to design more general algorithms。Okay。



![](img/7a1e10fb70685b449942d5ad94b55684_54.png)

So， for instance， one thing we've been avoiding so far in the course is scenarios where we have。

Some constraints in our optimization problem， okay。And this is very important。

 especially in deep optimization。 when not only you care about how your。

 your discipline model performance in terms of， let's say。

 the the training accuracy and test accuracy。 But maybe you also have some other criteria in mind。

 For instance， how robust your method is。Maybe what's the memorization tendency of your of your model and things of that nature that we will talk about in this course in in future lectures。

对。To handle it， all we need to do is to again， consider the memurization immization problem or the memorization minimization perspective to get the understand and say that。

 hey， I had this。Come with quarterly upper bond that I was minimizing。

 Not that I have let's say some constraint。I performed the minimization over my constrained set。

 okay。Now， this update happens to be exactly the update for another method。

 which is called projection gradient projected gradient and descent。

 meaning you are still following the direction of disscent。

 But given that the resultant solution may be infeible。



![](img/7a1e10fb70685b449942d5ad94b55684_56.png)

After making the progress， you project back to your constrain set to ensure that the E threat remains feasible。

 Okay， so these two are essentially identical。

![](img/7a1e10fb70685b449942d5ad94b55684_58.png)

![](img/7a1e10fb70685b449942d5ad94b55684_59.png)

对。So beyond handling the constraints， sometimes it's useful to use different notions of distance。

 What do I mean by that。When I look at this upper pond， I have a Euclidean norm square here。



![](img/7a1e10fb70685b449942d5ad94b55684_61.png)

Sometimes it is useful to replace this Euclidean norm。With another distance or another divergence。

 okay。For instance says El1 norm。Or the the version。

 things like that that we will talk a little bit more in this course。 Okay， so essentially。

 you can consider the following algorithm。Everything is identical to the previous equation， except。

I'm changing the Euclidean distance square。To can look at abstract notions of diversions。

 something that captures how similar W and WT R。

![](img/7a1e10fb70685b449942d5ad94b55684_63.png)

A very famous example of this is。

![](img/7a1e10fb70685b449942d5ad94b55684_65.png)

Called mirror descent。 And that is very， very useful when W， the parameter that you' are optimizing。

Is a probability vector。One example of this is in reinforcement learning。

 where your policy essentially provides the probability。



![](img/7a1e10fb70685b449942d5ad94b55684_67.png)

Of selecting actions， okay。In that case。When you change the Eucidean norm to something else。

You can get much， much faster performance。Because essentially， what you' are doing。

 youre exploiting the structure that W belong is a probability vector and belongs to the probability simplex。

 and you won't be able to leverage that structure by using the Euclidean norm。



![](img/7a1e10fb70685b449942d5ad94b55684_69.png)

Good。Now， another extensions， again， facilitated by this meurization minimization view。

Is to replace this gradient with an arbitrary update vector。 So all I do again。Again， same thing。

 right， So I'm minimizing over a like a feasibility set。I have the constant term， this linear term。

 where now I have replaced the gradient with some update vector G。And then I have the other term。

 which again， you think of it as let's say Eucliidean enormous square， okay。



![](img/7a1e10fb70685b449942d5ad94b55684_71.png)

Now， what， what are the examples of this， The examples are， for instance。

 when I replace the this the， the gradient。With a stochastic gradient。

So an example is a stochastic project at here in Anden。Okay。

Or a stochastic version of mirror descent。And things of that nature， okay。And finally。

This also provides a way to。To again， leverage the structures and potentially develop better surrogate functions。

 Okay， so the structure that we we talked about here was the the smoothness property that enabled us to find this nice convex quadratic upper bound on the function and leverage it here to apply basically majorurization minimization。

 But if the function has other structures。

![](img/7a1e10fb70685b449942d5ad94b55684_73.png)

For instance， let's say we know that the second order with or the Htian has some nice properties。

 we may be able to leverage that to develop better storage gates and therefore develop better optimization algorithms。

Alright， so， so therefore， we see， we see that the smoothness is is noise because， first of all。

 it provides a way to。To approach。Understanding the performance of training algorithms when the function is non complexve。

And secondly， it provides a way to think of gradient decent differently and potentially leverage that to design more advanced all items。



![](img/7a1e10fb70685b449942d5ad94b55684_75.png)

Now， in the next lecture， we're going to focus on the the proof of the terms we stated for S GD and getting in the send are non noncoms。

 but smooth functions。I'll see you next time。