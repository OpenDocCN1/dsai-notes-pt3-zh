# 【NPTEL】计算机视觉的深度学习 p85 P85_梯度下降及其变体 - 第二部分 -BV1vNWkzpEua_p85-

![](img/dbb43acb3984c71cb9ea7aedf1f31986_0.png)

Let's now try to analyze we've seen gradient descent， we have now seen at least one or two methods。

 momentum based gradient descent， me momentum based gradient descent。

 which can help you improve gradient descent training。

What are the pros and cons of greater disscent you've seen so far？For every parameter update。

 gradient descent passes the entire de descent we already saw that it computes the gradients。

 it keeps aggregating the gradients and then takes the average， we called it an epoch。

So gradient descent passes the entire data set and it's hence called batch gradient descent。

And the advantages of Bsgian descent is theoretically speaking， from an optimization standpoint。

 the conditions of convergence are well understood。😊。

And many acceleration techniques there are improvements from an optimization perspective。

 such as conjugate gradient operate very well in the batch gradient descent setting。

 once again it's called batch gradient descent because you're waiting for entire batch of data points to get completed。

 take all of these gradients， average them and then make an update。

So the disadvantage of badge gradient descent is it can be computationally slow for the same reason。

 especially if you're training data set high。Say 10，000 data points or 1 million data points。

 you're going to wait for passing through all of them before making an update。Imagine it。

 which is a computer vision challenge。it's a very commonly used dataset set ambition has today about 14 million samples and one iteration over all of those 14 million samples can be very slow to wait for one parameter。

That brings us to a very popular approach known as stochastic gradient disscenter。

Sttochastic gradient decent， SGD stands for。You randomly shuffle your training data set。

And update your parameters after gradients are computed for each training example。

So you randomly shuffle and pick one data point forward， propagate it， compute the error。

Compute the gradient。Update all your parameters right away before propagating your next data point。

 so here is your algorithmic difference with gradient descent。The third。The third step here。

 sorry this step five here on this algorithm was outside the fork loop in gradient descent。

 you did or you went through every data point， accumulated all your gradients。

 and then made the parameter plate。Whereas intochastic gradient descent。

 that step of updating a parameters goes inside the form， which means for every data point。

 you want to make a parameter。IfThis is going to be faster。

 let's see a few pros and cons for stochastic gradient descent too。

 but before we go there were going to talk about a acid which lies in between which is known as mini batch stochastic gradient descent。

 what is mini batch stochastic gradient descent？Mini batch stochastic gradient descent。

 as the name says， is you take a mini batch of training examples。Don't just take one， don't take all。

 take 20 examples from your training data set。Forward， propagate all of them。

 compute all the outputs， compute all the errors， compute all the gradients。

 and then take the average of those 20 gradients alone and update your parameters。

Why do we need this it's possible that if you keep updating a gradient with every sample it may give you random directions one data point will tell you go like this。

 this is where Himalaya's lowest point is there another data point will tell you another step youll just be taking different exact steps。

you traverse to the surface， if you listen to every data points ir。

Averaging gives you a better sense of a gradient direction that is consistent across a few more data points。

This mini batchch version of stochastic gradient descent is the default option for training neural networks today。

 often today when people say they use SCD， they actually mean mini batch SD。Remember。

 mini batch SGD with bad size to V1 is your SGD itself。But typically people use larger batch sizes。

 200， so on and so forth to compute these gradients。So algorithmically speaking。

The applying update once again went out of the loop， but this time you're not going to compute。

You're not going to aggregate gradients for the entire training dataset set。

 but only for one mini batch， which you doote as B mini。

 and you're only going to aggregate the gradients and average the gradient only for that mini batch in the al。

Let's try to see an illustration of stochastic gradient descent。

This is once again con plot of an error surface， let's try to see how its to cast this。

You can see it progressing towards the minimum， remember the minimum is the blue surface。

As it goes closer to the minimum， it seems to oscillate。Do the ocillations remind you of something？

Momentum， maybe。Promentum also had similar oscillations when it reached the minimum。

Here is an illustration of mini batch SDGV。Once again， the same at surface， let's see if。

Btching data points and computing the gradient helped us a little bit。

You do see here the oscillations have mild reduced for many batchs of HGD when compared to HGD。

 but the batch size here was just two， you could probably see lesser oscillations when you keep increasing the batch size because then you're not going to vacate based on every data points gradient。

 but you're going to batch them across a larger set of data points before you update your parameters。

What are the pros and cons of stochastic gradient descent when you compare it to batch gradient descent。

 let's try to understand this。The advantages of stochastic gradient descent， which。

Far by far outnumber its disadvantages， it's usually much faster than batch learning when you train neural networks。

Why is that so it's simply because there is a lot of redundancy in batch learning。

Because if you have one million data points in your data while training your neural network model。

Then。😊，Many of these data points may give you similar information。

 you probably don't need to wait for all of them to give you you the gradient and then average。

Even if you take hundred of them， maybe you're going to get some sense of where the gradient is for that particular iteration and move forward in that direction。

 so you're exploiting the redundancy in data to go much faster than standard batch gradient descent。

It also often results in better solutions， this may seem a little countertuitive。

Because you would think that， by。Using the entire batch。It could be computationally slow。

 but that's the ideal way to do it， then why does stochastic gradient descent？better solutions。

The reason is。Sttoastic gradient descent is a noisy version of gradient descent。

What do we mean by that We mean that。You are only taking 20 data points。

 let's assume the mini batch size was 20， you're taking just 20 data points， getting the gradient。

You keep moving along those directions。So it's like asking， once again， you're traversing Himalayas。

If if you ask dozen people。Assuming that you had infinite computation。On infinite access to people。

 if you ask thousand0 people and they are told you go in a particular direction。

 you probably can rely on that direction。If you ask three two people and ask them what direction they're go in。

 maybe they may get it wrong。Which means that when you ask a smaller set of people。

 you may oscillate， you may take one direction than somebody else else you go in another the direction。

 you keep moving around and fluctuating a little bit。

 but you eventually get there because between across all of these people they may point you in the direction in expectation you would get there but。

There may be fluctuations along the way。But this noisy updates of stochastic gradient descent is what could actually help you in escaping local minima。

 bad local minima or savggy points。😊，Because of these rising updates you may avoid salary points and probably get to better local minimum over time。

 that's what researchers have been able to understand from how HGVS performed in the learning。

Sttochasticulating in decent is also useful for tracking changes， what do we mean？

If you have a new set of data points that come in， it's very easy to update which is 20 data points rather than have to run an entire repo with 1 million plus 20 data points so remember in batch gradient descent。

 you have to recompute the gradient for all the data points before you make your next move but in stochastic gradient descent。

 if new data points come， that's what we mean by tracking changes here。

 you can easily update the system and keep moving。What about disadvantages？

Disadvantages of stochastic gradient descent is that the noise in stochastic gradient weight updatess can lead to no convergence。

To this day， sometimes remember， as we said that because of the complexity of the error surface。

Where you initialize your weights is very important。As to where which local minima you conver to。

So often today in practice， if in the first few iterations you find too much fluctuations in your error。

 people often simply change the initialization and try again。

Which means noise and S weight updates can lead to no convergence。

 but the solution is fairly simple if in the first few iterations things are not going well for you。

 just stop， go back and start at a different location and start all over again it's fairly a simple solution。

This can also be controlled using learning rate。If the gradient you know is noisy。

 don't use a high learning rate。So it can also be controlled using a learning rate。

 but then identifying a proper learning rate can be a problem fixed on。

And that's the problem we want to talk about next。How do you choose a learning grade？We said that。

Moomton was one way to artificially inject a learning rate into the system。Because it's effectively。

 if the momentum of the previous step and the current gradient aligned。

 it's almost like you had a high welding rate in those directions。😊，In general， though。

 if learning rate is too small， it can take a long time to converge。

 if the learning rate is too large， the gradients can explode。

Now how do you choose a learning rate in practice， assuming we don't use momentum。

 how do you choose a learning rate in practice？One simple option is name linear a search。

You just keep your learning rate to be constant throughout the process， just fix it。

 just use the same learning rate across all your righterations until you reach convergence。

Or you could use unnealing based methods。Unlink based methods are methods where you gradually reduce the learning rate over time using some formula that you come up with let's see a couple of them now one of them is known as step decay where you reduce the learning rate after every Nhytrationations or if certain degenerative conditions are met for example。

 if the current error is more than the previous error which should not happen when you do gradient descent you expect that the current error should always be lesser than the previous error。

 but when you do stochastic gradient descent，And not be guaranteed because you're using really 20 data points to inside your gradient。

So what you can do is keep reducing your learning rate after every M aggressions。So。

That's one simple approach the idea here is that as you keep training over iterations in apos you're probably getting closer to your minima and when you get very close to your minima you want to take small steps so that you reach a minima and don't overshoot it that's the reason for reducing the learning rate over time that's called step decay。

Another popular option is known as exponential dating。In exponential decay。

 you set an initial learning rate called alpha n， and then alpha is equal to alpha n to the power minus kt where alpha。

Alphanon and K are hyperparameters and t is an iteration number。

 so you start with a learning grid alphanon and keep progressively reducing it exponentially in this particular form over every few iterationrations because P is an iteration number here as the iteration number increases a learning rate automatically starts falling down。

You can also use a simple 1 by 3dk formulalar where you start with an alpha n。

 an alpha at a particular time step can be given by alpha n by 1 plus kt。

 where alpha and Kr hyperparmeters and T is an itration number。All of these。

 as you can see are heuristics， we're just saying let's just do one of these and maybe it'll work。

 can we do something better？Can we be more aware of what a neural network is doing and accordingly choose a learning rate rather than have these。

Google tools that。We fix irrespective what the network is doing。Is there a way to do this， Yes。

 there are a few methods which we're going to discuss now。

One of the earliest methods in this context was known as adaptive gradient or al。

A has a simple intuition as to。The fact that sparse but important features may often have small gradient when compared to others and learning could be slow in that direction。

In our case， features means dimensions of weights， rather a subset of weights。

 so you have your entire space of weights， a subset of weights。Wwhichch change only once a while。

 so let's assume that there are certain weight that could keep do not change with every mini batch in mini batch as but change only once a while。

 they may change by a small amount， but that amount is important because they only change once in a while。

Spasse features could be important and learning could be slow in this direction because the gradients could be small in that direction。

So a simple thought then is， why should the learning rate be the same for every gradient？

In your dual framework， once again， remember that the gradient is a vector。Of。

The derivatives of the loss with respect to every rate in your neural network。

Why should you use the same learning rate for all of them？

Why can't you use a different learning rate for each of these weight？So what you do in undergrad is。

You accumulate the squared gradients as a running sum。 R T is a quantity that holds。

Running sum of squared gradients once again， keep in mind that the gradient is in deelta theta D is simply gradient that's a parameter update and that's a vector of the gradient with respect to every weight in the neural network。

So for each of those weights， you maintain a running sum of the gradient squares and then your parameter update states Theta t plus 1 is going to be theta t minus alpha which is your learning rate divided by delta plus root Rt delta theta T。

 delta theta T is your gradient in your current time step。Now， why does this address this intuition？

Delta here is simply used for numerical stability。 You just set it to be a value like 10 power -6 or 10 -7 so that you don't face a divide by 0 error in case Rt0。

 you don't want a divide by0 error when you compute。 So that's the reason you have a deta here。

 But otherwise what this is doing is。When R is small。It is going to be a very small value。

This is going to become large。Or rather， the learning rate for that weight is going to become large。

When RT is large， the learning rate will become small。We are saying that for one of few weeks if。

If your gradient was large。Give it a small learning rate and for one of your ways。

 if your gradient is small， then give it a larger learning rate。

This seems to fit with the intuition that we have so far and the nice part now is this kind of an approach because RT is maintained for each gradient or each weight individually。

This automatically takes care of。Changing the learning rate for each weight differently。

Let's try to understand this from a simple example。So we do understand that when your error surface。

 these are con plots， when your con plots are spherical。Things are easier， it's easier to converge。

When your concrete plots get elliptical is where your oscillations can occur。

Another important property of elliptical conduct plots is that there are certain dimensions where the change can be rapid。

A certain dimensions where the change could be rather small。

 which is what elliptical basically means。So if you see this example here， which denotes。

 let's assume the gradient and the corresponding white e value。

 we are now saying here that if you look at one of these。

 let's look at the black frequent and predict irrelevant。

It simply states that all those values keep changing regularly。

 but they don't seem to be connected to the class output。

These are some values and they don't seem to be connected to the class output in this particular scenario or the output of what function you're modeling while there could be other values such as red and green which change only once a wide so you can see in 5 t2 it doesn't matter here as to what these quantities are and this is only an example so when phi T2 is1 we see that yt definitely becomes one when phi T2 becomes1 yt definitely becomes1 it doesn't matter when it's zero but when it is1 the output is definitely one similarly for phi T3 you see that when it's1 the output is definitely minus1。

So it looks like。This particular parameter changes only once a while， but when it changes。

 it makes an impact on the final decision。So this is a scenario that says that even if the gradient is small。

 but if it happens only once a while， let's give more weight to changes in those directions。

 in those weights。And that's what this algorithm does， so here is the algorithm。

So you aggregate the gradient， you update your gradient accumulation。

 so you initialize your gradient accumulation in a parameter called Rt minus1 which is equal to0。

And you update your gradient accumulation to be Rt is equal to rt minus1 plus gra D at t square accumulating the squared gradients。

 and then this is the formula one a small observation here which is probably not clear from this algorithm is this particular quantity on step nine is an relevant device product so which means。

And remember in this case that why alpha was a schener so far。RRT is a vector。

Root RRT will also be a vector。 So this entire alpha now。

 alpha by deellta plus R T will become a vector。 It's a vector of learning rates multiplied by a vector of gradients element twice multily。

It's sometimes also called Hadamama the hamama product is nothing but elementwise multiplication removal。

 it's not like dot product。In a dot product， you take element twice multiplication and then add them all up and get a scalar。

In Harammat product。You simply take elementwise multiplication and your output is still a vector you don't add the on okay that's the main difference and this operation here in step 9 is actually a Hadramar product and elementwise multiplication between two vectors There is one problem with the agra method。

Can you try this for the problem？The problem is that this gradient accumulation term Rt。

Is a running sound that simply keeps accumulating over iterations。

Wwhichhich means as you run more and more iterations。

 it will only keep increasing and get higher and higher and higher over time。

 which means this denominator is definitely going to get high over time for all the weight。

In particular， there are some of the weights for which gradients keep occurring in every iteration where the denoinated term can very quickly increase。

This will lead to a lower learning rate for those dimensions in the weights and learning may not happen along those directions。

RMS Pro， which was a method that came along the same time as agra。

Proposed a slightly different approach to this problem and said。

Let RTB a convex combination of Rt minus1 and delta theta table squared。

 what is a convex combination where you have a rh times one term plus1 minus rh times the other term。

 it's a linear combination where the two coefficients add up to1。So row rt plus1。

 row rt minus1 plus 1 minus0 delta theta t equal squared。

This now ensures that because of the rh and 1 minus rh。

 the sum cannot keep exploding and is now controlled。Think about it for a while as to why。

 and you'll get why this will not allowed you to explode。And now your theta t plus1 and theta。

 this entire expression is exactly the same as a。Here is the algorithm for RMs prop with only that change in the step where you have now the running some of the accumulated square gradient to be a convex combination monitored by a quantity called rh。

 which is known as the decay， the decay decayate designs how much you want to consider the previous squared gradient。

 why you get the current squared。Very similar to momentum， but in a different context。

The most popular algorithm that is used for training neural networks today for adapting learning Gs is known as Adamom or Adtive Moments。

Adaptive Mo uses a simple intuition。Of combining ideas of RMSMS prop and momentum in a way。

 let's see how that is done。While Rite and RMS Pro。Accumulate gradient of the squared gradient。Iem。

So while allgraide and RMS f accumulates the squared gradient。

 aom accumulates both the gradient and the squared gradient， ST accumulates the gradient。

 Rt accumulates the squared gradient just like RMS f。喂。You look at the final update equation here。

 the update says that theta d plus 1 is equal to theta minus alpha。ST by Delta plus R RRT。

I'll explain the tilde part in a moment， but let's first assume that there's no tilde let's just assume ST and RRT so what is this doing Al by delta plus root Rp is exactly the same that we saw in RMSMS and undergrad ST would have been the current gradient in undergrad and RMSMS Pro。

 but now ST is the running sum of the gradient。And what is the running sum of the gradient？我问的。

Remember， momentum was what you use the previous gradient。

 the previous gradient on and so forth using momentum term row1 is the momentum coefficient for us in this particular context。

That's why Adam can be looked at as a combination of。Am is prop and momentum。

Now coming to why is this tillor here， why not just ST and RT。

 is for a very simple reason of doing what is known as bias correction in the initial iterations。

In the initial iterations， if row 1 is set to a high value， which is what is typically done， row1。

 just like momentum， row1 could be set to something like 0。9 or something like that。

In your initial step Rt minus1 would be initialized to0 that's where rt minus-1 would start1 minus01 will make it a very small value because row1 is close to1。

 so which means the gradients will not have any impact on ST in the initial iterations until they add up so they may not be much traininging that happens in the initial its。

So what do we do for that， we say let ST tillilde be ST by 1 minus rh 1 poverty。

 similarly rt tilde be rt by 1 minus root2 party what does this do if row 1 is 0。9？

Remember 1 minus 0 minus 0。1， so ST by 0。1 will now increase it andfold。So I walk about Ford。

It was reduced here， it's now going to increase it by tenfold in the initial evaluation。

What happens in later iterations， we have P here P is the number of the iteration that you're talking about。

What happens here？Remember row1 is less than1， it's chosen to be 0。9 or something like that。

So robot party will keep reducing all the iterations， 0。9 into 0。9 is 0。

81 so it keeps as long as you have a value less than one as you raise it to the poverty。

 it's going to keep reducing。Which means this quantity in the denominator will keep reducing over iterations and sorry this is not the quantity of the denominator that roll party will keep reducing to0 and1 minus over roll poverty will get closer to1 over the iterations。

 which means after a few iterations， ST tilde will become ST RT tilde will become I。

So the step of bias correction was only to handle the initial epo where the gradient may not have a significant impact。

This is your Adamom algorithm， it's simply a summary of what we just said these are the two steps。

 you update a first movement estimatement which is the gradient second moment estimatement which is the squared gradient you maintain a running sum of both。

Correct for biases and do your update the key thing in the update is you do not have the gradient here because the gradient is subsumed into ST。

That summarizes the various methods of improving gradient descent while draining neural networks。

So some of the issues that we saw are plateaus and flat regions， local minima and saddle points。

 other issues that we will see as we go forward are vanishing and exploding gradients as neural networks become deeper and deeper。

 the gradients that propagate from the last layer to the first layer can keep vanishing or exploding。

That can cause what are known as cliffs in the error surface， we will see this a bit later。

Other challenges that could happen is sheer ill conditioning of the matrix of weights or the loss functions or the gradients that you're dealing with。

Please look at this link here to understand what this means。

You face a you could face a problem of inexact gradients。

 the gradients numerically may not be computed properly， for example。

 finding if a gradient is zero is not trivial because numerically attaining zero while training is not possible。

 you have to ensure that you manage it in some way。

 but in general numerical issues in gradients could also cause problems。

There could be poor correspondence between local and global structure。

 which means you have a global error surface and you want to get to the global minimum。

 but the local region in which you are in may not really correspond with that global structure you will be stuck with trying to handle the undulations in that local structure。

Choosing learning rate and other hyperparameters like the momentum hyperparameter or the decay rate are also problems to deal with。

The somebody。The error surface or cost surface in neural networks is often non quadratic， non convex。

 high dimensional。Potentially many minimalma and flat regions。

There are no strong guarantees that the network will converge to a good solution。

The convergence is stiff， swift。Or that convergence occurss at all。But it works。

ThisThis is an issue that's being investigated today， but it's。

ItTrave is that training neural networks with stochastic gradientism works and is being used around the world in several applications。

Here's your homework， you read up。Deep learning book chapter 8。

 at least the relevant sections in that， as well as you can also go through Stanford CS2319。

 this particular lecture on SGB。A few questions for you to take away is。

How to know if you are in a local Mimar or any other critical point on the loss surface。

 I didnt mention a few times that finding that or finding the convergence criterion is not trivial。

Let's ask that question for you to find before we answer。

Why is training deep neural networks using gradient descent and make square error a non convex optimization problem this is the first question that we started with this lecture with。

This is something for you to ponder upon and finally， if we assume a deep linear neural network。

 no activation functions at all。Would using gradient descent and main square error still be a non convex optimization problem when you train deep neural networks these are some questions to think about。



![](img/dbb43acb3984c71cb9ea7aedf1f31986_2.png)

And get all that。