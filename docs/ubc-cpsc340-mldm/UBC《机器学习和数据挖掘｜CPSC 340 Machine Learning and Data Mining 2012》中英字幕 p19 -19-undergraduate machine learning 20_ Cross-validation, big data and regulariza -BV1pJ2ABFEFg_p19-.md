# UBC《机器学习和数据挖掘｜CPSC 340 Machine Learning and Data Mining 2012》中英字幕 p19 -19-undergraduate machine learning 20_ Cross-validation, big data and regulariza -BV1pJ2ABFEFg_p19-

Going to be poorly conditioned。 So when you try to invert it， it's going to give you an NN。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_1.png)

Not a number。 your program is going to crash。 Most likely。

 if you try to invert a very large matrix without conditioning it。And so some folks。

Decided to hack this in the 70s， and they decided to introduce。What they call a regular risea。

And in fact， that's where the term comes from， you are trying to regularize。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_3.png)

The problem， you're trying to make it。Nice here。Making it more regular。

And that's essentially what they did is they just added a small element to the diagonal of the matrix to each element in the diagonal。

 That's a simple hack that I think any coder would come up with if they tried to invert a matrix。

What they discovered though， was that this hack actually ended up giving better predictions。

If you knew how to choose the delta。And so that led to a lot of such as can， many papers。嗯。

A lot more than I will cover here。It turns out。That another alternative way to come up with this is to instead of thinking of。

 let's hack the solution to get a better behave solution。

 it's rather you construct a different cost function。

And then you prove that the optimum for that cost function is actually to this。

So like the question you asked earlier， we start with a cost function。

 we differentiated it equal to zero， and then we get these thetas that are better behaved。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_5.png)

So the ridge will be a better behaved theta because it has this diagram。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_7.png)

一。Actually， gives better predictions， as you will soon see， because it actually subsumes。

Maximum likelihood，1 delta is equal to 0。So it cannot do worse than maximum life。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_9.png)

Provided you have the right deal。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_11.png)

And how we proved this， again， J of Theta。It's equal to y minus x theta， transpose y minus x theta。

If we take the derivative。It's a derivative of this guy plus deelta squared theta transpose theta。

And I'm getting bored of killing these guyses。Sadly。

 you can't get bored of doing these guys because you're gonna be doing them。😔。

But trust me that this is two x trans eggs。Theta plus2 x transpo y。Last two delta squared。Eer。

And you can just now group terms and say that this is2 times x transpo x。Last deelta square。

 because I have deelta square theta， if I multiply anything times the identity。

 I still have deelta square theta， the identity。Is that entity operator so to speak？

And I need to do the identity so that the dimension of this is the same as the dimension of this。

If this is D by D， this identity has to be of size d by D。Invert。Frans all。

I'm getting ahead of myself。诶。It's been tidy。I'm getting tired here。A plus 2 x trans plus y。

 and if you're equ to 0， you get essentially what we had before。Its my data there。这什么？Okay。

 and so if we equ to zero， we had the theta range。Is equal to x transpose x。Plus deellta squared I。

-1 h transpo y。 So it's exactly the same as maximum likelihood， except it has that deelta square。

Here's one thing for you guys to practice。What would be the solution if I replace the matrix x by the SVD X？

Okay， so。And when you replace it by the SPVD of X， you actually learn that what Ridge does is it gets rid of the small liigenvalues。

It has a very nice property。 So get rid of the。Literal details。I'll leave that for the midterm。

好 right。So。Geting a repeat questions of。I have to move on。装备有。是。え器。Allright， so。

What I want to do next is I want to think this is the objective。 Okay。

 so the objective now has two components。 It has。A component that is what we have from these squares。

 so it has this blue guy， which is from these squares， and it has this new guy。

 let's call it the green guy， and that's the regular rise。Now。

 what this is saying is that in order to minimize J。

 my goal is to minimize J to have as little cost as possible， to minimize J， I need to minimize both。

 I need to minimize blue and I need to minimize green。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_13.png)

![](img/d03b3ed437fa5ab186f6ca802a565b3f_14.png)

But sometimes minimizing blue will be increasing。Green。And vice versa。

 So the theta that minimizes blue is not a theta that minimizes green。

 The theta that minimizes green has to be theta equals 0。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_16.png)

Because if you want to make J as small as possible， just choose t equals 0 and you get。

Blue disappears。But if theta is 0， then then the blue term will be y transpase y。

 and y transpose y could be a very high value。So there is a tradeoff between these two terms。

 We need to find a theta that minimizes one and minimizes the other。

An alternative way to formulate this。Is to say that we want if this helps you guys think of an arbitrary function。

 It's an unknown function。 we don't need to know it。

 but you could think of it as one of a doubtive if it helps。

But essentially what we wanted trying to do， we minimizing。There's likelihood。Subject。Two。

 this constraint。Subject to the theta transport theta being small， being smaller than some。

Constant that depends on Delta。Wehich shall call T of death。So you want to minimize y minus x theta。

But you also want to make sure that that product of the two theta transpose theta theta squared is small。

Let's look at an example in 2D。And truly。Theta， the vector in bold is just theta 1 and theta 2。嗯。

If I have the function， I'm going to JR for regular riseor。If I have this function， theta trans the。

And want I already know that this function looks like。It's a。Looks like this。And Theta1 and Theta 2。

And if I want to find this equation， the contour plots of constant height， so I'm interested。

If I want the curves。The curves at which the height above the ground is the same。

Then I just need to look at the equation， delta squared theta transpose theta。Is equal to a constant。

And that just gives me， I can subsume。So I can just write this as theta 1， theta2。

Times theta 1 times theta 2。Equal to the constant。Times。The deelta minus2。

 which is still you can think of it， the whole thing is still a cost。In terms of feet。

And so this is just theta 1 square plus。Pta2 is square。一个。Some cost。

Now that's the equation of a circle。Okay， x squared plus by squareical radius squared。

And so the contours。If you think of the contours as what we observe here at the bottom。

 they're all circles。The circle center the origin。That's the shape of the first component。

The other guy。Is kind of。There' other guy here。Will'll be over here。This guy is JR。

And I'm going to call this other guy JL for the likelihood。

That other guy will be some Gaussian around， so some sorry not Gaussian， but。Some cup around here。

The minimum of8， because if you differentiate JL andequ to zero， you get the minimum。

 which happens to be the least squares。So this is the theta of the squares。That's the location。

And that's the same as the feet of maximum likelihood。Which。Has two components。

Now it's also a quadratic because there's a theta1 or theta 2， but in this case there's cross terms。

So if you expand this guy here。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_18.png)

You will get something of the form a times theta 1 squared plus B times theta 2 squared plus C times theta 1 plus B times theta 2 plus e equal to 0。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_20.png)

That's the equation of a problem。 No problem。 It's the word ellipse。What did you get。First。

Times theta 1， the2。Oh yeah， missed one。Because I did this。And it had negative。And。Ilauded it。And it。

Look like。A plane， a bent plane。 twisted plane。And when。TheSs were different。

 So when theta1 was positive and theta was negative or the other way around。It went。Now。

 trust me that that's a quadratic form， it cannot be negative。I can go over your work later。

 but it's not going to be negative。 It's going to be。We're going to get a。

JL is positive I can you JL is positive and。If you expand it just like I did for a circle。

 you'll get the equation of an nullipse。I will go over your work， but mark my words。

 you will get an eipse。Okay， so this will have some contour plots。That when I plot the contour plots。

They will look like this。Something like that。Now drawing it 3D is very hard， as you can see。

 so I'm going to now forget about these cups and I'm only going to look at the plane。

 so I'm only going to plot the contour plots next。Okay。All right， so we have theta1。We have The too。

We have this green guy， and we know that the contour plots are circles centered at the origin。

Some more circles than others。And we know that the ellipse。The blue term。Will be ellipsis。

 we don't know what they are， but let's just pick a point arbitrarily。

 let's say that they're centered here。All right。不是。Now。We know that the center。Of the blue guys。

 this point here。Which has this coordinates。Fta 1。Ml。And C2 ML， this point here is the minimum of JL。

Right， because it's。By definition， it's。The point that goes down。Of lowest height。Now。

 we also know that's when delta squared is equal to0。Okay because1 delta squared is equal to0。

 the second term vanish。We also know。That if we let the delta squared go to infinity。

 then the second term will basically have much more importance than the first term。

So the first term y minus x theta times 1 minus x theta， that might be， say 100。

And if deelta squared is 10 million， then the only way you're going to minimize J is by making theta very tiny。

And so。If Delta。Gost to infinity if you have a very large delta。

And the reason why I squared this because I want to emphasize that I want that weighting deellta basically balances。

Your desire to have small theaters and your desire to fit the data。

And that balance I just wanted to be positive， that's why I was the Discoriental。Now。

 what happens for a different delta that is not zero？And so let's pick a nice color for that。

That would be a good cover。Bread again。s pick。 No， we already have bread。Purple。

 let's go look purple。Purple， we just called our Dlta violets purple close。Okay。

 so I will make the following claim。The optimum。Will be the point the optimum for any delta。

Would be the point where。The two curves， the ellipses and the circles are parallel where the contour plots are parallel。

The gradient， by definition is perpendicular to the contour plots。

 So another way to say this is that the gradients are colon。

And that's the starting point for the whole field of convex optimization。Which I don't attack here。

 but you can discover about it in fourth year in fourth year this is a essentially where the optimization course will get started。

The simplex algorithm of zone is derived using this intuition。Why is that point a solution？

Becauses I'm going to argue it the following way。Let's say that I choose that point。Okay。

 let's say that I。Chaanged the likelihood。So I can。Actually。

 let's say that I don't want to change the likelihoodli。 So I want to keep。

I want to look at another point where the likelihood is the same。 All these other points。

Give me the same high jail。So the height of all these purple points is the same because they're all in the same contour plot for jail。

They all have the same height in terms of JL。However。

If I move from this point to this point or even just to this point here。My blue has increased。Okay。

Sorry， my grain has increased。So if I move to any other blue point。If I keep the blue fixed。

And I move by keeping it fixed。 So for the same blue， I always get a bigger green。

So for any blue of the same height， the best green I can get。Is this guy？

Let's make the argument now with an orange。Lets now I assume I want to hold the green fixed and I choose different points。

Say the green is not changing， it's all the same height。

 but every time I deviate from that optimal point。My blue will increase。Okay， so because。You know。

 these guys increase outward。So。If I deviate from that point。

 either the likelihood or the regulariz will increase。

So I should avoid deviations and I should stick to that point。That is true for this point。

So actually， let's stick with orange。Yeah it's going to site an。We discarded that name。

It will be true for this point。And it will be true for all the points where the curves intersect。

Let's put one more， so one more circle would be。Maybe like this。

So here again will be this point here。So we had this point， this point。

 oh I forgot that it was sayingan。Too many colors。Okay， so。

It's always these points where they're proud。Now， how many points do we have。

But hes work towards where two things can have。The contours。

 there's an infinitefinity number of points。Because there is an infinity number of possible values that Delta could take between0 and infinity。

For each of those values。We get a curve that looks like this。When we increase Dlta， theus go to zero。

Each delta gives us a point in that blue line that can curve。And each of those is a solution。

I'm going to interrupt this now briefly to show you。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_22.png)

Because now I think I can。Describe to you。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_24.png)

![](img/d03b3ed437fa5ab186f6ca802a565b3f_25.png)

要玩。With L1 regularization， on the other hand。A regular isza is not circles。But it's those four lines。

So which give rise to that diamond shape。So it's always diamonds。Many of these diamonds。

When the point at which these guys will be。The point of deviation then。A hang on。 to maximize this。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_27.png)

And then I can make exactly the same argument。That if I did the8 here， I'm increasing。

The regular riser， if I deviate this way， I'm increasing the likelihood。 So the optimal point。

 then it's this point。 The difference here is that because I have now a diamond。

The intersection will often be one of the axises， one of the corners。Okay so if you have a diamond。嗯。

Circle。You， it's very。Very roundly will the circle。嗯。

It may happen that you will have a likelihood that will be like this that。Interssect。It there。

 but most often with hyper probability， you will touch one of the corners。

And when you attach the corner。One variable is equal to0。

 and that's why a lot of these variables will be equal to0。

So this picture allows you to sort of see intuitively why this is a bar regular riseor。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_29.png)

你果他不。The section is not at the board。If it's not one of the corners。

 or judge just basically is that the data is telling you that none of the theta should be zero。

 and that's also good because it might be that you have a thousand genes and it might be true that each of those thousand genes is actually important。

If that's the case， then that's the case。たのこれトラク。It， it can happen。Last year， I gave a data set。

A medical data set for people to practice as a homework。 And by chance。

 it actually was the case that。It didn't hit the corns。 So there was a bit of。That was a lesson。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_31.png)

You could choose a regular license。の。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_33.png)

Could you to regularize that So if you find something of a situation where you're knocking at a corner。

 could use a regularizer as a different slope？You could， yeah。

 you could then try to do different games。 Yeah theres there's as many regularizers as students in this room out there。

This is the most popular。These two that I've shown you the L2 and L1 are the most popular。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_35.png)

Okay， so that's the picture thats kind of illustrating what this is。

 So then the only question that remains now。 and then this is another plot that basically shows you。

 Let's assume that this is。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_37.png)

For arguments sake， it doesn't matter what this function is， but let's say that it's。One of a deelta。

Then basically， as you increase delta theta goes to zero and different thes go to zero at different speed。

 and that makes sense because if you look at this diagram。

 you can see that theta 2 is going to zero much quicker than。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_39.png)

Fer one。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_41.png)

Both are going to zero， but some are going fast。And then they don't。

 unfortunately they don't go and stay at zero， but with LaS you actually- and this is real data。

 by the way， this is actually from a from that prostate cancer study。呃。They go to zero。

 but in this case， this is the optimal。In that study they also found the optimal Dlta。

 it's described in this book which is on of course website online。

 and they find that the optimal delta is that delta， in which case only one of the thetas are zero。

 but with the lasso， many of the thetas are zero with the sparse L1 solution。I wondering。

 what is Ellen cowball was that？Cardiic volumeer。I was wonderingMost of them are pretty obvious about that oh。

 I don't remember of them， but the example is here。Yeah， in this book， they explain every。

I have known what they were， but I don't remember exactly what each of them is。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_43.png)

Okay。This is also called shrinkage because you're shrinking the featuresus。

 So the basin is called the shrinkage。Now， Ri is actually what you would get。 So we've seen that。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_45.png)

Lase squares is the solution that you would get if you just do maximum likelihood。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_47.png)

But we've known， we now know that there's two ways of learning maximum likelihood。

 and then there's the baesian way。Maximal likelihood just uses the likelihood。

 basins use of prior and the likelihood。And then for Bayesians， it's about normalizing。

 it's about integrating whereas。The frequent guysise that use only the likelihood。

 it's all about optimization， finding the best data。When you do maximum likelihood。

 you get as a solution least squares。When you do the Bayesian estimate。Under a suitable prior。

 you get a rich。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_49.png)

That's basically， but then the basin will also have other properties。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_51.png)

How do we do the basin？This is something that I gave you as a homework exercise。

 even though the solution is posted online， I still wanted you to go over it。

 it's a tedious thing that I don't want to go over in class。But basically。

 what you do is to get the Bayesian， you want the posterior of theta。

 and so you multiply the prior of theta times。The likelihood。

 so the likelihood is the same as what we had before， but now I'm going to use a Gaussian prior。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_53.png)

If I multiply the Gaussian pum the Gaussian likelihood， and you probably all have seen this by now。

 there's this completing squares thing which is very tedious to do， but very important。

 you would then discover the following thing， the likelihood the posterior is also Gaus。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_55.png)

More importantly。That's just algebra， I'm not going to go into that， that's kind of tedious。

More importantly is that if you choose a particular prior， a prior that has zero mean。

 So you now your prior is saying。I believe the theta should be zero。

So now you can think of it as a prior。My preference is that the theus be0。

And my preference is that the variance of the thetas be no bigger than tau squared。

So you've made that prior。 and at that prior， you do all that completing squares。

 normalizing trickery， which is the same as what you do for the beta binomial model。

And it's the same as what you do every time Bayesians always。Prior times likelihood。

 you group terms and then the group terms look like a distribution that you know。

 and then you just read off Wikipedia the normalization cost。And you're done。That's pretty much it。

 That's what we call it has' a word。 It has the technical term for this conjugate analysis。

 but it's just basically that。When you do this。You get。

That the mean of that posterior is just a rage estimate。So we recovered the ridge。Where in this case。

 lambda is just equal to the ratio of sigma squared divided by top squared。

What's the dimensions of data？

![](img/d03b3ed437fa5ab186f6ca802a565b3f_57.png)

Theta is D by one， it's always D by one。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_59.png)

In regression， it's always D by1。 There's D inputs， D， D weights feet。Fate。When we call sigma and we。

Sigmas came。No no no no。😊，You're confusing。 thanks here。

 Can you take the determinant of non square matrices。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_61.png)

I'm inclined to say no。Unless there is some sort of funky definition of the determinant up there。

 like the SPD。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_63.png)

そ。Is this sort of saying that retro regression is sort of equivalent to Bayian learning under some。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_65.png)

This is saying exactly that indeed rate regression is equal to the mean of the posterior。

 the mean of the basin solution。So if you did base。

If you never knew about rid a maximum likelihood and all of that garbage， and all you knew was bayes。

That you have a Gaussian cry and you have a Gaussian likelihood， you would get a good answer。

You'd get。The rich。However， we have already seen。This is the lecture materials from last week we're going。

 but since then we've learned that this is another thing called the last suit。

Which is an L1 regularizer。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_67.png)

So it starts doing retro regression right， and we don't know about Beijing。

We don't know any reason concept。不。Do making content。No。If you just get to me， you're not being ba。

A Bayesian wants to estimate the full thing， the posterior。For a basins。

 there's no such thing as one only theta。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_69.png)

The mean is that。But Bas the saying there is not one true theta。

 there's many thes weighted by probabilities。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_71.png)

The seatta that has the highest probability is the mean。Because I Gaussian a symmetric。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_73.png)

And that will be important for the following thing。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_75.png)

So we know that the posterior mean is given by the rich。

 but then there is also an expression for the posterior variant because a whole， we have a Gasian。

 and so for a Gasian， we need the mean and the variance in order to describe。

 we need those two moments。Now， if you want to do predictions and here comes the difference between the frequentest and the basin way。

For a Bayesian， making a prediction。Its equivalent to。Integrating out。P of Y and theta。

So basically given a new data point at star and given all your previous data。X comm y。

So end data points， in other words， inputs， output pairs。If you want to make a prediction。

 you have to integrate out theta overall thes。So you have P of y comma theta given x。

And given sigma squared and given the data。And the Theta， so you need to integrate all these guys。

And then you do the factorization。Then to go to the next line， the bottom line。

 I'm just doing conditioning。And the fact that the posterior is not a function of future axis。

So I just dropped future access。So the basic solution is marginalized， basically。

you want to make a prediction， you need to marginalize， so in other words。

 I want to make a prediction， I have many thetas an infinite number of thetas， in fact。

 theyll have a weight， which is the posterior probability。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_77.png)

![](img/d03b3ed437fa5ab186f6ca802a565b3f_78.png)

And so what I do is for each the， I make a prediction and I weight that prediction by the posterior height。

That's what that integral means。I'm multiplying。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_80.png)

posterior。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_82.png)

This is given the date。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_84.png)

So， it's a Gaussian。So basically， with my posterior， suppose I have。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_86.png)

Suppose my posterior only has two values， so in the discrete case。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_88.png)

01， and then this is say 0。2， it is a 0。8 and if I want to make a prediction of what the coin will be。

 I would wait， I would say it's 0 with probability 0。2 and it's 1 with probability 0。8。

So I would multiply those two because essentially that's what I'm doing。

 The first term is the likelihood， but I'm waiting each of the predictions。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_90.png)

![](img/d03b3ed437fa5ab186f6ca802a565b3f_91.png)

，So let's look at what the weight of frequent do。The frequentists， as we saw the likelihood。😊。

You basically say that Y hat is just equal to x star。Trusspa speed。Okay， so that's the prediction。

And then the variance of that prediction is just sigma squared。 it's just a single prediction。

The basins are not saying that。 The basins are saying， it's going to be。Many thes。

 and we're going to sum over all the possible thes in this case are infinite thes。

 and each of those terms which are of this form， will be multily weighted by the posteror。

So and this is essentially a marginalization。We're just writing。And because Bay it's out of the view。

That when you make a prediction。That prediction should be independent of the parameters you have。

 it should be robust。If you made a small mistake in estimating this guy。

 the new predictions will be bad， whereas basins， they kind of hedge and they have many theaterus and they make many predictions。

 This idea of ensemble learning is very important。 The idea of using many predictors with what people call ensemble learning is sort of was crucial in。

In about any of the big competitions on data over the last decade。Okay。

 quick advanced thing that I will just mention。If you marginalize。

This is actually equal to a Gaussian over y with mean x star transpose theta and variance sigma squared。

When the posterior is a delta function。At。Ml。The deelta function。

I don't know if you guys have seen it before， it's just a spike。It's just one spike at a point。

It's just a bar thing。Because if you integrate with respect to the delta function。

 if you have a function here。You multiply that Gaussian times the spike and you're summing over arttheus。

 it's only when that Gaussian is over the spike。And the spike is defined to have area1。

 that's one of the properties of the deelta function， or it's also called the direct function。

 so that's the only one that you're going to pick。 So the deelta function is just basically sampling。

At that point。That just。Is that just not the same as taking a Gaussian and having the variance go to zero？

That's correct。 If you take a Gaussian in the variance coast to Syria， you also get a spike。

But basically， it's just saying that maximum likelihood believes that there's only one solution。

 The basins， on the other hand。They believe that you need to multiply two Ga seats。

And integrate multiplying to Gaussians and summing it is three pages of algebra。

 So I'm not going to bore you with that。 I leave that as an exercise for students in 5，40。

 If you take 5，40， you will encounter that。 So the sigma and the prediction given by maximum likelihood。

 Is it the same sigma。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_93.png)

From before is it？The green sigma is always the same thing， the same quantity。

 so then the deviation of oh the difference， yeah， you just hit on the really important thing here。

 the very important thing here is indeed what you just said。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_95.png)

That。The variance here is given by this， the variance here is given by this。That's the。In a way。

 if you use I mean， the mean is also different because the theta maximum likelihood is the least squares。

 whereas the theta n is the rid。 So Bayesian is a bit better because it's using the rid。

 whereas maximum likelihood is using the。These squares， were just not as good。嗯。

It's still left for me to tell you how to get Delta squared。 But what we already know， though。

 is that。The other thing is that the basin is adding an extra term。To the variance。

 what that VN is proportional to the data is the inverse over the data。

 So its basically an inverse over your data matrix。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_97.png)

And so what that does。Is that the predictions of the mean tend to look the same， but the variance。

 the confidence intervals of base。Are different。They have a data dependent term。

 This VM depends on the input data。OnOn the training data。 and because of that， where you have data。

 the variance is low， where you don't have data， the variance is high。

 you should only be confident where you have data。That， again， is extremely important。

 If you're going to be betting out there， you want to know when you。Have a safe bed。

And you only have side beds where you've seen that。So for this1 D case。嗯。IVN。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_99.png)

I'm just trying to see why。嗯。How fast it gets bigger， does it get bigger with an x squared？Well。

 yeah， yeah， because it's given this Vn is proportional to x transpose x inverse。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_101.png)

So you could take two points and you can do by hand a little exercise that will tell you how it shows。

 but because you're dividing by the inverse of where the data is。

 it shrinks where the data is and it amplifies away from the data。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_103.png)

And that's why one reason why we bother to put Pri， that's another reason for using regular Iis。

We get prior modeling because。This is very important so in I do a lot of work with user interfaces。

 I do a lot of work with recommended systems out there。

 I have a company in Palo Alto that does recommendation its so on without other folks and。

Already sold one to CNN， which is now powering CNN， in fact， if you go to CNN website。

 it's a company developed by some folks that took a similar course to this one here a few years ago。

And sort of understanding the variance is very important。

Because if I want to decide where to gather new knowledge， I need to again， know。

This exploration exploitation thing， I want to gather knowledge when my uncertainty is high。

 but also want to gather knowledge when I know the mean is doing well。

There's a problem also in AI called reinforcement learning。

 and this is sort of the basis to attack that problem。And that's very important in。

All sorts of things， like if you want to schedule when to admit a patient or delay a patient。

 those techniques are used to schedule that kind of。

When to let the patient into the hospital to take measurements and when not。

 you have to rely on techniques like those。So there's a lot of very good work on operations research with the South of Business School and hospitals。

 Pe Can Agency and so on。I'm tryinging to do that。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_105.png)

Last thing。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_107.png)

And then I think we need to stop because'm。We're probably just tired。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_109.png)

Is I need to tell you how to choose the delta squared。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_111.png)

![](img/d03b3ed437fa5ab186f6ca802a565b3f_112.png)

![](img/d03b3ed437fa5ab186f6ca802a565b3f_113.png)

Okay， how to choose the deelta squared。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_115.png)

And I'm not going to go into the nonlinear section。 I'll probably go into it a bit later。

 but this this part is important。Now， the technique that I'm gonna to show you is one of。

The project is tied too。Unfortunately， it's。二十よ。Oh yes there。Projectors will be down for。

another two minutes or so so。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_117.png)

You guys want to take a practice， is it？哦。Yeah， take take a break。 You you have individual questions。

 I'll take those now。可せで。回复啊。That no。他。Yeah。I electricity signals the one of。ISee to you。

Follow tomorrow night。上。I。quiet。Its。你对方出来。你你先买出。 you get。But the。Of is the important。think。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_119.png)

Yeah。tell me today you choice to gun。 choose the keys and you your sight to be business。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_121.png)

三你。なじ。didn't formal。らのや。方讲。关。Yeah。Actually，요。So of course therell be moment。

 which means everything with common。 point down the slide on the slide and。Okay。And。Yeah always on。

Yeahいや。Yeah。Yeah。In one day camera will be top provided hands。つ。I。아。I here。はい。

I like accept by core products but。Yeah。Can you tell me。I。Do want a contradict predict。

We received all order restaurants。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_123.png)

It。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_125.png)

How many days。It。Yeah。inquiry free。Lett my just that。 you want to make some in order。

 not information that make make you false stone。Where for。ま。そな。Yeah。You wait like a quarter of that。

That。And then you， then you're not doing it。And give me out。And essentially more。 Yeah。그。Where。Yeah。

开始咩。Yeah。今天送冰天。Yeah。The and。Yeah。Scan of height arch see site。Yeah。I。Yeah。Theyt myself。Yeah，So。

Can speak。No，Well。Okay。I see。你出放。So essentially what we're doing is we take。いちゃん？全实话全。

And then we're waiting。Yeah。I wonder the afternoon。I。Yeah。The more。目前是。其他权。How is this solution。25。

 America。Yeah。뭐。So I think。It job a big X， big accident。 they big an that。

 get the feed that might use want to。 And it seems well。 I don't know more problem。不到。Sure， I is try。

前呢。Yeah。です。I do this time when I business standard all only。It imaginary situation maybe。Okay。

Don agree。I。你你英点系。Yeah I by。呢个系。冇。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_127.png)

I that very far about how。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_129.png)

So。Yeah。I。The hotel， guest room。没有。Yeah。I am told that it go。I know is。Many buy many。So question。

Ks going the hard。There find。Yeah。啊。は在。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_131.png)

开嘅。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_133.png)

Yeah。I cook white。And。Yeah。我手啲。Yeah。They want those。も。210。Just。Let's finish this for tonight。

How do we do， how do we come up with a good delta， So we're going to try a technique called cross validation and cross validation comes in many flavors and shapes。

 and I'm going to give you the simplest form of cross validation first。In the simplest form。

 what you do is the following。You have training data。And this will be pairs x1， y1。X2， y2， and so on。

 up to x and。Why n。But in addition， you also have test data。Here is the trick。

You learn with the training data and you never look at the test data because if you look at the test data。

 you're get cheatty。Okay。You will learn to predict the test data。

 but when you're given the real test， you will fail。

Okay so you need to try you have to it's important to be honest here because otherwise you get the wrong testament。

And the test data say it's x n plus1。Y and+1。All the way， let's say K data points。

So we break our data into two sets， one for training， one for testing。

 and you can split it in half say。So for now， let's use the simplest form。

 which is just what they id。Once we do that。We don't know which is the best delta。

 so we're just going to pick a bunch of values。So in my case here， I decided to choose 0。1，1， 10， 50。

 100。I'm sort of picking like a log scale， and then I'm adding a few more when I think it might be the right delta。

Of course beforehand I don't know that， I don't know what's the range of a good delta。

 all I can do is guess that it might be a few of those values。

 and then if I see that I have one of them is a very good one。

 then I might add a few more values there and redo it。So in a sense。

 we are doing optimization we're searching for the good deta。

It's possible to automate this procedure as well。 And in order to automate this procedure。

 the variance of those estimates is essential because essentially。

 we use those variances to decide what's the next best delta to check。But anyway， but for now。

 let's assume that we just pick a bunch of deltas by hand。What we do then。

 so you choose the delta now for each of the delta values。You will fit the model。So。

 the procedure is。Choose Delta。Say deelta equal to2。Then you compute the theta bridge。

Which is equal to x transpase x。Plus two squared。I minus1 x transpose y。You。Computer why。Train。

Which is basically the matrix x times theta rate， the predictions on the training data。

Let's say that all this is x comm a y。And all this data， I'm going to call it。X star， comma y star。

And then。Then your computer predictions。On the test data。Which is equal to x。Start times theta。A。

And then we compute the errors。So the training error is just。Y minus it's the prediction。

For all the indices in the train， which is I I equal1。To air。And then this is for i equal n plus 1。

All the way to N plus K。So we compute the error on the training set and the the squared  errorss on the test set。

Using the predictions from the training set and prediction project。

Or we computing the air of each point？We sum in the errors of each point in the training set。

 and then after we sum the errors for each point in the test set。Okay， so remember。

 least squares means the sum of squared error， so each point has a squared error。

And so we sum all the errors。I'm computing the two separately。

 I first do it for the training data using the prediction of training data。

 and then I do it for the test date。So I'm checking how well can I predict the training vector and how well can I predict a test date？

Now。Let us assume。I just came up with these red numbers， by the way， I just pulled this off my head。

Let's assume that when you do this。When you compute those errors。

 that the answers that you get are the ones that I'm showing here in Grand。

 like 1 and2 and 10 and 11 so。So the next question then is， based on those red。Numbers。

How do we pick Delta？There are many ways of doing this。

 There's really more ways than I'm going to describe， but I'm going to describe just two。

One is called the pessimistic view。Or it's called a worst case analysis。

 which is the one that sort of you assume that nature is out to get。The min marks。

This is now a decision theory problem， this is the problem that an agent。

 an individual or a robot or a dog or whatever， has to confront in order to decide what to do。

So we use the wordag to describe this。This being that is called machine that's doing a decision。

In worst case analysis， you try to minimize the worst that could happen。

So imagine you have two babies。And you have a cake。

And each want and the cake sliced and you want to make sure that they don't cry because one got a bigger piece when you're cutting the cake。

 so what's the solution to the problem？This size。嗯。What's that one cut in the other one？Yeah。

You let one baby cut the cake and then the other baby chooses。

Because the one that's cutting the cake knows that no my sister will screw me。

 so I'm going to try to cut it right in the middle。Because if I cut a small one and a big one。

 she's going to attack a big one。And so you're minimizing the worst situation。

You can't do better than a half。It's impossible to do better than half that cake。

 so you might just well minimize。This is basically what in science is also called the Nash equilibrium。

When two agents are minimizing the worst that could happen。

 they're doing something called best response， if all agents。

 like of all of you do that in solving a problem， we will all conge to a point of equilibrium where you don't want to deviate。

 it has to be a half， any deviation will and dis balance us。And that gave Nash a Nobel Prize。ok。

In the worst case， then what we do is we pick the max。 We look at the worst situation。

Let's go back to purple。The worst situation would be， say 111。1920。And1。Does。So you worried。

Think of this as betting in the stock exchanges。 I think of the training set as the profits this week and the test set as the profits next。

Or how much money you're going to lose this week and then how much money you're going to lose next week。

You don't want to have something where you only lose a little bit of money。

 Just imagine there's a recession。 So you， you going to make money。

' just trying to minimize your losses。You know， you know。

 it's better to not have very little minimization in one day。

 And then the next week completely collapse。You kind of want to balance these two。And in fact。

 you want to deal with the worst guides。And so if you want to deal with the worst case。

 then the best is to choose。Delta squared equal to 10。Oh， what am I saying， sorry。

I didn't do it this year because I。A TA doing this， but actually in previous years， I let people。

Vote。And often， most students tend to like。嗯。我了为。I'm tired。道是是 one。Most students do tend to pick。

Delta equal to 1 or delta equal to 10 and 50。 So they do what makes sense。

 So it choose delta equal to  one because it has the lowest。Worst case。

An alternative is to compute the average， which in this case would be。51。诶。

Whatever 21 divided by two。And。10。5。即。即系。And whatever this is。

And then youll pick the lowest of the average。And so you could either pick this or you could pick this。

 and then you might then decide to do something smart that is both low average and out of all the low average pick the ones that's the least worst case。

 so you might then pick this。So you end up picking Delta。Square equal to10。

Which one is the right one？That's up to you， that depends how much risk you want to take。Part just。

好的。とめ。The min Max is delta squaret equal to one。It's the least of the maxa。The max。

 the maxes are 111，19，20 and 1000。 and the list of the max is 11。

 So you picked out this Scical 2 one。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_135.png)

And that's cross validation。Now， there are some refinements to this。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_137.png)

Because people tend to cheat， even when they try not to cheat。

And it's because they do this and they don't unlike something， and then they decide to change theta。

And they look， you know， they start looking at the test set。And so to deal with this， what。

Some honest folks then have to do is create a third data set。So you break your data into three sets。

And we call them training， test and validation。And then you can do cross validation with the test。

And you never look at validation。You only look at validation。

An hour before you have to hand in the report。Because then you will know， truly。

How well you're doing？Because otherwise。You know， you can still play this game and you can learn to do very well on the test set as well。

 but then on the third day。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_139.png)

You do back poorly again。Every time you look at the data to you。

You've already seen something about the data that will help you。

So it's always good to have a data set that you never see。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_141.png)

There's other games。 I'm not going to go into this。 now。 this will be more like the topic。

Of when you do the assignments where you can do different things like there's the sort of thing that's very common。

 That's this called。K fold cross validation。 in this case， there's a diagram here showing you5 fold。

 And that basically tells you the picture。 you train on the white ones and you test on the red。

 and then you cycle through them。 and then you take the average of。TheThe five arrows。

That's also a good strategy。

![](img/d03b3ed437fa5ab186f6ca802a565b3f_143.png)

But let's forget about this5 full class validation for now。

 the important thing is the analysis of the data。And the analysis is this is not about math。

And you' don't。I mean， for most of the techniques I teach in the course， I think as practitioners。

 unless you're doing research in which case you do need to know the math。

 if you go on to do research， but if you just going to be if you go in words say for aritia。

 and all you want to do is take their clothes， whatever bunch of variables and try to predict which clothes will have more of oh my God。

 that's so cute， if that's your variable that you're predicting。

 then which is actually quite lucrative， if you can predict which for which clothes。

Customers will get really excited。 Then you are in business。 already employees， I believe。

 lots of workers to just do that kind of analysis。 Look at Pinterest。

And look at many variables and try to predict whether someone's going to buy that cute top or not。嗯。

And a lot of it could be automated。 I don't know if they do automate it or not。Certainly。L Lemon。

 I think is a bit smart about this。 The gap is definitely the big companies in the US they're definitely smart about machine learning。

 they're definitely trying to maximize the pen for the buck。So。You will be able to use。

Like neural nets and random forests， you can。 there's two boxes out there。 There's like。

 there's side kits and so on。 You don't need to code these things。 You just download the software。

 However， the software has three parameters， like Delta square。And so in a sense。

 this is the most important part of the course， because when you download that software。

 you're going to need to know how to set those parameters and you need to know the meaning of what they do。

AndSo next this slide and the next one I feel is the most important for practitioners moving on。

 and here are the things to remember， if you increase the regular is deelta squared。

Then your train error gets worse。That makes sense because the total error is two things， train error。

 the likelihood， and the regular riseor。If you're increasing Delta you。You're going up。

You're going down into circles in the middle， but you're actually getting a worse likelihood。

So your training areas going up as you increased out。However， the test error goes down。

So there is a sweet spot， and that's what we find by cross validation。

 Cross validation is giving us the sweet spot。😊，Of which the。

The worst case in this case is minimized。We want to do well not only on training， but also on tests。

 It doesn't help to do very well on the training。But then。

The next day you make a bigger error than you would have made if you had。

Afforded a little bit more errant training。First you want to minimize errors in the future。

Minimizing errors in the future is what we call good generalization。

 You want models that will generalize to new situations to the future。

Another technical term that we use is for the same thing is we don't want models that overfit。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_145.png)

Now， here are the important lessons。In this case， I will take a quadratic function。Okay， a quadratic。

 X， Y。And then in order to generate data from the model， I'm going to generate synthetic data。

 and then the way I'm going to do it is I'm going to pick a bunch of x's。Maybe on a grid。Like。

 for example， in Python， you'd say I want x to be 0， 0。1， 0。2，0。3， all the way up to one。

And then for each x， you evaluate this quadratic here。You choose a particular value。 I don't know。

 you might say let's pick theta not equal1， Theta 1， equal2 and theta2。

So just pick these values randomly or whatever。这是。Those are the just the true， the true theaters。

For which you're going to generate data。And then what you do is for each of these aes。

You plug them into this formula， and that gives you this height。

It's precisely the height of the line， and this is why hat。Oh， the question of this line。

And then you add noise to it。 You add noise to each of the axises。And the noise is just。

With mean 0 and variance sigma squared。 So it will be something like oops。You'll have a point here。

 maybe a point here， a point here， the point here。And so on。 so you basically you're generating data。

Okay， so that's how we generate data。 So you use the true model。

 you use the probability to generate data。And then what we're going。

 then the exercise I'm going to do is I'm going to see now， if I can。

And the reason why I'm using a model to generate data is because now I do know the true model。

 In this case， I do know the truth。You know， in your typical situation in life， you just give data。

 you don't know what the true model is， you need to try to figure out what a good model。

 but in this case， I know what the true model is， It's a quadact。

That was the model from which I generated a date。Now。

 let's assume that I choose a model now that is Y hat。Equal thehita no。Plus。

 x times theta 1 plus x times theta 2。So I choose that model。AndBut in this case。

 I forget that I know theus and I'm going to try to learn the theus。

 so I'm going to assume that all I have is x and y， and I'm going to learn the theus。

But I do have the right model。 I have a catratic。And the true model is a quadratic。

 so the models agree。So I use， I don't know， rich or list square， whatever to。To learn C。

Once I have learned theta， I look at the。The mean squared errors again。

 which is just the average of y minus y hat squared。And then divide it by a number of date。

The average era。And this is what I find， and I actually I did this with this is the exercise。

 what I didn't do this， actually， this is part of something called a PMTK toolbox。

Which if you go to Kevin Murphy's website。You can find there Kevin Murphy used to be a professor here。

 he's now working at Google and he actually has a very nice book in machine learning。

 I don't recommend that for this course， I do recommend after the course because after the course you'll be able to read it right before。

But it's bit advanced。It's definitely the textbook for 5，40。 It's an excellent textbook。Okay， so。

If you do this exercise and then I fit this model to the data and I vary the number of data。

 so I repeat this experiment many times。 I repeat the experiment with zero data， 25 data， 50 data。

 75 data，100 datas are okay， different numbers of data。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_147.png)

And I study， how does the error vary as a function of the number of data？

I learned the following things。First。Neither my training error nor my test error go to zero。Ever。

And they don't go to zero because the quadratic cannot go straight through each point。

 there is always going to be a arrow。Okay， so we'd always。We're always making these small errors。

Those， those we can't escape。That is inherently， the system has noise。

 and we're going to pay for noise。 So there's always this minimum。Error， which is due to noise。

So that's the first thing。If。Lessson one。If you download some software and you try in your data。

 and the error is0。You might be doing something not k， you need to really think of what's going on。

The other thing is the training error。Might be really low in this case， well this is the situation。

 a training error is really small for that number of date。

 but what happens is that you're overfitting the date。At that stage。As the data increases。

The training error tends to converge more to that expected thing that should be the lowest that you can make which is the black curve and the test error goes down in this case the convergence is very quick right after just a couple of 25 data points。

We've got line。This is when the model that you choose has the same complexity as the model。That。嗯。

That we will learn。That generated a date。Let's assume now that I'm going to use a simpler mo。

 So I'm going to use。Theta n plus x， theta1。In other words。My data。

My data was generated according to a quadratic function， this was the true data。And instead。

 I'm going to use a prediction。That is the line。Okay。

 so you can see the problem of trying to fit a quadratic data with a line。

 it's impossible to go through all the points。And so even if you get more points。

 it's not going to get better。Okay。Now， lesson two。If you keep adding more and more data。

 if you get more customer data coming in and results are not improving。Time to change the model。

Time to try something a bit more complex。Especially because you've been careful。

 you did cross validation， you see that your train error and you test error about the same height。

 so you know you've balanced the two  errorss。But it's not going down。It's always a high error。

 you need a better model and in science， this is where we like in terms of building like models of the brain and so on。

 this is where we are right now。 we use very simple。嗯。

The current neural networks that we have are very simple， very few parameters。

 it's only now that there is this big thing of the Google network where they use huge numbers of parameters and we finally are getting to the point at which we're escaping this problem。

 I would say that right now in terms of building the brain we're here。Our models are too simple。

Tror is high if you don't。Another noise if you don't have this black line。

When I built my neural nets。Theyre not able to see。My models are incapable of recognizing objects。

You have to use your prediction somehow。Do an experiment。You basically。

 you're trying to achieve a task。 and the model is not giving it a task。

Or maybe my profits are still too low。And I have some reason to believe that I should be able to get a higher profit。

In my case， I believe I have reason to believe that this computer will one day be able to see as well as I see。

And the only reason I believe that is because。Well。

All of you are capable of seeing as well or better than me， in fact。

If the biological evidence exists， then I believe that I happen to achieve my best。So。

They will surpasses。Not there yet。Okay， this is when the model is too simple。

And you think about the brain。 and we have billions of neurons。Typically， our models have 10 of 10。

000 parameters。Finally。What I might do is I might choose a predictor that is theta node plus x1。

X times。Theta 1 plus x squared times theta 2 plus。All the way to X14， Theta 14。

 and this was Kevin shows that Kevin or Matt Matt was a student that took this course and developed the toolbox。

嗯。And she does not do math to cognitive science with me as a college student。Very bright。

So which is now a very complex model。A polynomial of the 14 is a very squily model。

So if you have only a couple data in the quadratic。Your polynomial of the Gr 14 is going to do this。

So。On the training， which is those three points， the error is 0 because the line goes straight through the point。

 So the training error is 0。You're doing well。On the test， though， you do really badly。

 as you can see， that red curve is really high， you can do unboundly poorly。By doing this。

 so if your model is very complex。You're doing what we in this case， say overfitting。

And so how can we stop the model from overfitting？We can just simply add more。Data。

Because as the date increases。And make it。This polynomial might go crazy out here。

 but when it comes here。😔，Where the data is。It's constrained by the date。

 it only has so much curva and so it can't jump off within the date。 So you get a nice fit there。

But the cost of it is that you need a lot more data。

When you hear about all this stuff that's going on on that is very relevant to us。

 computer scientists， as we embark in the century， there's this whole talk about big data and data and so on。

 and you hear these companies and blogs going that we just need more data， more data。嗯。

That might be so， but then you need to have a very complex model。And it might be that you need。

A class that is a lot bigger than all of Amazon's computing in order to be able。

To deal with the problem。An alternative。To're doing this when you have a lot of data。I。

One way to control complexity is just by increasing。An alternative。

 when you have a polynomial of degree 14， this is the same example。

Let's assume we're doing rich regression to estimate a theta， in other words， we have。Basically。

 the rich cost。No nonlinear regression with basis with polynomials is still linear regression。

 We just need to reinterpret the axis。As。This guy5hi， they still inputs， we get to observe the x's。

 so we observe x14， x to the power 13 and so on。And so this is just the same as rage and we solve for theta once we have the matrix phi。

 this is just game， just linear regression。But when we choose Delta。Without increasing the data。

So we just use a few points like I'm showing these points that we have here。

We can choose the Al to balance the training in the test error。And by choosing Dlta to this knob。

 you can under if you have a too tiny delta。You overfit。

Your training area is small because the curve is almost going through all the points。In the training。

 these blue points are all training date， so you're overfitting。If。Your deelta is too large。You know。

 you're just forcing。What you're doing is by making Delta large， you're saying。

 I want many of these thes to go to 0。 And so what's that going to do is going to get rid of these。

Some of these features。And so you're going back to a polynomial law degree。So when you choose Delta。

 you basically are choosing the degree of the polynomial automatically。

And then there's two ways to do this， either you choose Delta or you just do cross validation with a polynomial of degree1。

 a polynomial of degree 2 and3 and 4 and so on， but are better ways to just choose Delta because it's also applicable in other settings。

So。A regular isa can give you the right generalization balanceas。

 increasingas the data is always a good thing， but it's not the only way to do it。

If you're smart about how you do regularization， you can get very good performance with few data points and sometimes you don't have a lot of data。

If I'm doing clinical studies， you know I don't have much data about patients， so for healthcare。

 which is one of the fastest， what I think was going to be one of the greatest applications of machine learning over the next decade。

 you won't have that much data。For some applications。For that application。

 we're going to have a lot of data because as soon as medical records get digitized and we have access to everyone's medical records。

 there's going to be lots of data out there。😊，For good and evil applications。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_149.png)

With this like with the this cost function， we。Where it seems like we're。

Uimalizing all the weights the same。Like I noticed you crossed out maybe yeah there's no reason why one should go to0。

 That's correct。 You're right。 You depend on the data。 Yeah。

 what you can do is you can be a bit smart and you can use a different delta for each degree of the polynomial so you can use higher deltas。

For higher order terms and smaller deltas。If you believe that that's the right prior。Typically。

 you just choose the same delta in。Tuneit and as you can see in this example。It works pretty well。

本都是哪。不まよ。So all the slides are uploaded except for， I mean， I'm rewriting this， but this is already。

This is I wrote this last week and I gave it to Matt。 there's an upload。 Oh。

 I need to upload that tonight。So there's only one lecture that I haven't uploaded and that was today。

 so I need to get back to my office。The last lecture was sort of today's because I didn't finish it。

So the parts and regression is the only thing I havent uploaded。Give me a chance to get back to Mars。

When is the midterm up to， because you reviewed a lot of stuff we've just done recently。

 I reviewed everything from last week。 The midterm is up to。诶。

Everything up to what I taught today early today。 And there's a reason because if you study for。



![](img/d03b3ed437fa5ab186f6ca802a565b3f_151.png)