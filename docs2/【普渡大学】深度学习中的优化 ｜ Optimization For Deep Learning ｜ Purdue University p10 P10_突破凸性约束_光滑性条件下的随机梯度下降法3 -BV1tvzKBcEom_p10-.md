# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p10 P10_突破凸性约束_光滑性条件下的随机梯度下降法3 -BV1tvzKBcEom_p10-

Welcome back。 So we were talking about the smooth functions and how useful they are in terms of studying the performance of optimization algorithms for noncoms problems and also the fact that smoothness helps us to understand gettingcent from a new perspective。

 a perspective that could be useful when designing new algorithms or more advanced algorithms。😊。

In this video， we're going to talk about the proof of the the tolerancence we have stated for functions that are smooth。

 but not necessarily convex， right， So recall， we said that if I denote the initials of optimality by Delta for gradientian descent。

 we have this a specific result。Which essentially says that the expected norm of the gradient is bonded。

By a certain bond。Which approaches0 with this rate。For the GD。

 we say that the expected gradientian norm again， is， is bounded by another bound。

 which approaches 0 at a slower rate。 Okay， so let's talk about the proof of this toorem。 So first。

 I'm gonna talk about the the proof of the first theor。

 And then we're gonna see what kind of modifications we need to make to that proof to prove the second termium。



![](img/297bb4bd5723b471a8e7c3e764f7c752_1.png)

。All right。So the key idea is， again， to study the amount of progress。We are making， and。

Our friend here is a Sness。 So we're going to leverage the fact that the function is as smooth okay。

In particular， as we saw in the previous lectures as a smoothness helps us to understand progress。

 Okay， so helps us to actually。

![](img/297bb4bd5723b471a8e7c3e764f7c752_3.png)

A study， the progress we are making。Because we have this very nice con qua upper point on the function。

So we can actually use that here。 So all I'm doing here， I'm using the definition of a smoothness。

Then。X is basically。W T and envoys。W T plus1。 again。

 the idea is that this helps me to understand the progress I'm making while running K， okay。

So this holds for any WT and WT plus1。These are not averageory， we are using this a specific update。

To go from one solution to the next one。So I'm going to leverage it here。 Okay， so in particular。

 I'm going to replace the difference between W T plus 1 and WT with Eta the learning rate times the gradient。

Okay， so that enables me to go to this， to this line。

So this difference is basically becomes just the gradient times the。The the learning rate， okay。

Now I'll do some rearranging。To， to basically find vastity coefficient of the get the Nor square and note that。

This inner product。Is basically。Normal square， so。If I let's say give what's the inner product of x and x。

 this is essentially saying that what x times x。 And that's x squared。

 So this is the norm of x is squared， okay。In this case， it is the gradient。Right， now， therefore。

 what does this result say it says that the progress。Is basically。

The norm of the gradientian square times another term。

So before proceeding with the rest of the proof， I want to a few remarks。So， first of all。

We see here that the progress depends on the norm of the gradient the square。What does that mean。

 It means that the larger the gradient， the more progress we are making， right， And this is。

 this is very， very nice。 So it means that if you are very far away from the the solution。So。

 let's say。That means order color。So let's say， this is a function you are。呃。Minimizing。

When I'm here。I'm going to make more progress。But then when I are approaching the solution。

 maybe I'm going to be a little bit more refined。In， in how I'm progressing。

 So the progress is going to automatically。诶。shrink。



![](img/297bb4bd5723b471a8e7c3e764f7c752_5.png)

As the norm of the gradient， it starts to go down。

![](img/297bb4bd5723b471a8e7c3e764f7c752_7.png)

Another important side note is related to to， to the role of the landing grade。

As long as the learning rate is less strictly less than 2 over L， we are guaranteed to make progress。



![](img/297bb4bd5723b471a8e7c3e764f7c752_9.png)

Okay。

![](img/297bb4bd5723b471a8e7c3e764f7c752_11.png)

And this is actually something which is which has been sort of observed in deep learning that and this is called the edge of instability because if the step size goes beyond this。

The optimization becomes ins stable， and you may end up actually maximizing the function， right。

 So you're not going to make any progress at all。 And it's been observed to be a relevant phenomenon when optimizing parameterss of a deploying models。



![](img/297bb4bd5723b471a8e7c3e764f7c752_13.png)

![](img/297bb4bd5723b471a8e7c3e764f7c752_14.png)

And the last side note here is that， okay， so we are talking about the progress。

 And as we mentioned before， we want to make sure that we are maximizing the progress， okay。



![](img/297bb4bd5723b471a8e7c3e764f7c752_16.png)

So if I treat the progress as a function of the learn rate。The maximum progress will happen。

V this slip is exactly one we're at。Okay， so this is a， this is a quaratic function。

 You can easily optimize it by taking the gradient analysis A called to 0， okay。And this is， indeed。

 the stepoid that appear in the statement of the proof。 So essentially。

The best constant access is1 word L， because that ensures we are making the the maximum progress in each situation。



![](img/297bb4bd5723b471a8e7c3e764f7c752_18.png)

Wetail the scan with the rest of the proof， and the risk is actually almost trivial。

 We're just going to do some rearranging。

![](img/297bb4bd5723b471a8e7c3e764f7c752_20.png)

And then take the average over time。This rearrrranging requires us to make this assumption。

Because we're going to divide by some factors， notably this part。And if this is。

 if the sepsis is larger than over L， this factor will be negative。 So therefore。

 the direction of our inequalities are not going to be the the way we want to be。



![](img/297bb4bd5723b471a8e7c3e764f7c752_22.png)

But after the arrangement and taking the average， we noticed the telescoping structure that I see here in the en numerator。

 So I have let's say f of w1 minus f of w2。Plus if of W 2。Minus F of W3 et Ctra。

So all of these terms in the middle will cancel。 And then I'm gonna be left with the first term。

 minus the last term。 Okay， so essentially something like this。 And this is something we saw before。

 as well。

![](img/297bb4bd5723b471a8e7c3e764f7c752_24.png)

Okay， now we're gonna note that whatever W T plus。

![](img/297bb4bd5723b471a8e7c3e764f7c752_26.png)

So this has to be capitality。Whatever the w T plus phone is。Its function value is。

More than the optimal function value。 So I can replace it with F at W star and get an upper bound。

And this is nothing but the initial。Suboptiity。That we define and appeared in the statement of theterium。

And with this， we with noting that we can， we can apply this， this fact。 we're gonna arrive to this。

To this bond， that holds for all learning rates that are strictly less than to over。

as long as it is a strictnt over L， this point is satisfied， this is a function of the layering rate。

We optimize it。To get the， the minimum bound。And it happens that the minimum is attain when the step size is1 over L。

 and therefore we're going to establish the statement stated results。Okay。

 so that's the proof of the first only。 Very， very easy。

 All that it required was for us to leverage its book。 and basically nothing。

 nothing more complicated than that。

![](img/297bb4bd5723b471a8e7c3e764f7c752_28.png)

Now， let's talk about the proof of the CD， CD method。

And it shouldn't be surprise that we're going follow a very similar approach。 Okay。

 so we're going to again use the smoothest to study the progress。

And then we're gonna leverage the update of the S GD algorithm instead of gradient and decent。

 Now things become a little bit more problematic or more more complicated than we do so because SGD by nature is a randomized algorithm。

So the random decisions we've made。In terms of selecting the mini meshes or or samples。

To find a stochastic gradient are going to determine the performance。So we need。

 in particular or more mathematically。The solution at time T WT。



![](img/297bb4bd5723b471a8e7c3e764f7c752_30.png)

And the sgons are random quantities。 So we need proper expectations。



![](img/297bb4bd5723b471a8e7c3e764f7c752_32.png)

Something we saw before when we talk about the proof of esttochastic in a sense on lipses and comics functions。



![](img/297bb4bd5723b471a8e7c3e764f7c752_34.png)

And therefore， we also need some assumptions on how good our estimators are。



![](img/297bb4bd5723b471a8e7c3e764f7c752_36.png)

In particular， we're going again asking that we have access to a stochastic ver oracle。

 which provides unbiased estimators of the true gradient with bounded variances。



![](img/297bb4bd5723b471a8e7c3e764f7c752_38.png)

And， finally。For the ease of analysis， we're going to assume that the samples are independent。

With this， we can easily carry out with the rest of the proof okay。So luck luck before。

 we go into condition。On on the current solution。Which， again。

 is equivalent to conditioning on the previous selection of the previous samples。

 And the reason for that is that I want to single out the impact of randomness arising from selection of。

Z T， the mini batch Im using at time T。And use the unvoyousness。

A property of my e stoastic filter or。So we're going to。

 we're going to take this conditional expectation。Again， I can use。linearity of expectation。

To change the order of expectation and inner product。And， finally。

The term here is nothing but the Gaian a WT， because I'm using an obious oracule。And finally。

 this is nothing but the norm of the gradientian x square。

Because I have gradientian inner product with itself。Okay。Right， so。This is。

 this is basically our way of handling this term。Okay， now we're gonna need to handle this term。

But we're going to use a similar approach，So。We're going to again， conditional ability。

We're gonna add subtract the gradientian。Again， because I want to leverage the fact that my。

A sacastic fersterule is onbi。And has monitored values。And again。

 this is something we saw before in the in the proof of SD for con and E functions。



![](img/297bb4bd5723b471a8e7c3e764f7c752_40.png)

So we， we're going to arrive to this point by using the unbiedness assumption of our oracle。And。

 finally。By noting that the oracle provides bond variance。We're going to arrive at this point。



![](img/297bb4bd5723b471a8e7c3e764f7c752_42.png)

All right。So what did we do， So we basically， we had some on the progress。 There were two terms。

That we are needed to handle them。And we did that by taking proper expectations， right。 Now。

 therefore， this is the result that we have the expected value of the function at the next solution。

Is bounded by the current function value。

![](img/297bb4bd5723b471a8e7c3e764f7c752_44.png)

Minus this term。

![](img/297bb4bd5723b471a8e7c3e764f7c752_46.png)

Plus， a third term。 the， the first term and the second terms are identical to what we saw when we were analyzing。

G and descend。And we basically use that to， to note。

As long as the s size is strictly distance over L， we are making progress。In this case， however。

 given that we we are using random estimators and given that this last term is not necessarily 0。



![](img/297bb4bd5723b471a8e7c3e764f7c752_48.png)

What will happen is that we're not going to have any guarantee on the expected progress anymore。

 So what does that mean， It means that if you run and you run S GD。



![](img/297bb4bd5723b471a8e7c3e764f7c752_50.png)

![](img/297bb4bd5723b471a8e7c3e764f7c752_51.png)

Maybe the next solution is actually worse than the previous one。That's why typically。

 there are some variations like this when you are minimizing。



![](img/297bb4bd5723b471a8e7c3e764f7c752_53.png)

The， the training loss。 So if， if this is the loss。And this is let's A T。Door ups and doorss。

 when we are using。Algorithms based on S GD， right so。Because we don't necessarily have any。

Any guarantee。On the， on the progress。Given that our algorithms are using these randomized operations。

To estimate the through gradient。Okay， so this is a side note， but after this。

 the rest is again identical to what we saw before。So we're going to take average over time。

Do so some rearranging。 Again， this requires that the step size is less than the。

E of instability to over。And then finally， we have to take expectation We speak to all of our random decisions。

 Okay， and this is the place we are gonna leverage the fact that our samples are independent。

To are of at this point，Now， here， again， we have two terms。



![](img/297bb4bd5723b471a8e7c3e764f7c752_55.png)

First term is identical to what we solve for getting the same。

 second term arise is because our oracle is not perfect and estimators have some variance。



![](img/297bb4bd5723b471a8e7c3e764f7c752_57.png)

Again， we know the telescoping structure in for the first term。

And the fact that I can replace the function value at W。T plus 1。With the initial of gap。

And then we're gonna arrive to this point。So this is a valid bond for all the step sizes。

That are a strictly lesson to over L。All that remains is to optimize this bound as a function of the learning rate。

And you can do so， I would say， easily。But the calculation is a little bit more involved。

 So I'm going to skip it in the lectures。

![](img/297bb4bd5723b471a8e7c3e764f7c752_59.png)

But if you do so， you're going to be able to find the exact size that we stated in the statement of the theoryorem。



![](img/297bb4bd5723b471a8e7c3e764f7c752_61.png)

Alright， so， so that's it。 So we successfully approved these two termsiums for the performance of the gradient and GD on functions that are smooth。

 but not necessary complexs。😊。

![](img/297bb4bd5723b471a8e7c3e764f7c752_63.png)

![](img/297bb4bd5723b471a8e7c3e764f7c752_64.png)

![](img/297bb4bd5723b471a8e7c3e764f7c752_65.png)

In the next lecture， we're going to talk about certain ways of strengthening。

SGD and it its guarantees， if you will。I'll see you next time。

