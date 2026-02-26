# 斯坦福大学《社会和经济网络：建模与分析｜Social and Economic Networks： Models and Analysis》中英字幕 p78 78_07_07_7-7-线性二次模型.zh_en -BV1v1421U7Nk_p78-

![](img/9a403a06236059de5cd3c3268cf0501e_0.png)

Okay， folks we're back and let's have a look at one other game with continuum of action so people can take a whole series of different actions。

 not just0 or1。

![](img/9a403a06236059de5cd3c3268cf0501e_2.png)

And this is going to be one with complements， strategic complements。

 and it's a linear quadratic model and so it's got a very simple structure to the payoff。

 which allows for a simple closed form solution。

![](img/9a403a06236059de5cd3c3268cf0501e_4.png)

So this comes out of a paper by Baluister Calvamal and Zu in 2006， and the structure of the game。

 the payoffs are very simple and tractable。In particular。

 when we think of a given individual taking near action Xi。

Other actions are taking other people are taking actions x minus I。

 let's let X i be greater than equal to  zero， so I'm taking some real value to action。

And the utility that people get， we can see why it's called linear quadratic。

 so it's going to be increasing in my own action just linearly。And quadraically。

 there's going to be a cost， so eventually I don't want to take too much action because I'm going to pay for that in terms of X squared。

But there's also the strategic complement aspect， so what I also do is I look at different friends and I wait them。

 so I have some weight I on J。And what I get is some product of our actions。

 So if other individuals are taking really high actions。

 then that gives me an incentive to take higher actions。

 I get a payoff a bonus from taking higher actions when other people take high actions， okay。

So the full model that they have in allows us also for some global substitutes and so forth。

 but let's focus in on this essential aspect of the model， which is the linear quadratic aspect。

 which is that I get a positive payoff from my direct action I get some negative cost and then which is quadratic and then a bonus in terms of what other individuals are doing and strategic compliments so the nice thing about this is in this quadratic form。

 it's going to be easy to figure out how what's my best action given what other people are doing。

 and then to solve for an ash equilibrium in this world is fairly easy。

 we'll be able to find a set of actions such that everybody is best responding to everybody else willll be able to solve that as a function of the network in a really clean and simple form。



![](img/9a403a06236059de5cd3c3268cf0501e_6.png)

Okay， so we've got this payoff and we want to figure out what's the best X I in response to what other people are doing。

 So when I say x minus I， this is the vector of the actions for everybody else besides I。

So if you maximize this function。With respect to X。

 just take the derivative of this and set it equal to zero right so if you want to maximize this function。

 what's the maximizing action， just set the derivative of this thing with respect to so take D U I D X set that equal to zero and that gives you the maximizer here and so we've got a nice function that's going to be necessary and sufficient in this case so when we go through and solve this when we look at the first order conditions taking the derivative we get an a minus a B X so the two comes down cancels the two and then some of Wj Wj Xj has to be equal to zero so X is just has a nice form where what you're doing is you're weighting things by a over B and you have something which is positive the respond。

To the amount of activity that your neighbors take So the more activity your neighbors take。

 the more you want to take and so you're getting benefits that are proportional to a and benefits proportional to how much action your neighbors are taking and then you're paying a cost relative to be。

 and so we get this benefits in the numerator over the cost and that modulates exactly what the right X is so we've got a best response。

 what I should do in response to what everybody else is and then an equilibrium is just going to be solving this set of equations simultaneously so everybody wants to be taking the action in response to to everybody else。



![](img/9a403a06236059de5cd3c3268cf0501e_8.png)

![](img/9a403a06236059de5cd3c3268cf0501e_9.png)

So to solve for all of these simultaneously， what we've got is if we write this down as a vector now。

 x1 through xn， it's a function of everybody else and waits on what everyone else is doing。

 You can rewrite this as a vector X is equal to alpha times G of x right？

 So we've got our x1 through X N。And that's equal to a vector。 Everybody is taking action， A over B。

 A over B。Plus。A matrix times the actions。Where this matrix has entry in the IJth entry has WIJ over B。

 right？So you can rewrite this in this form。And what that says is now this is an easily solved equation。

 right， So we've got a linear equation in terms of x and the G where the matrix that we're working with in terms of the network is now just these weights。

 these WIjs， but divided through by B， which is the relative cost of the action。

 so we've got a nice simple form here。 And if we want to solve this then。



![](img/9a403a06236059de5cd3c3268cf0501e_11.png)

You know， you could rewrite this， so rewriting this and we could substitute it， okay。

 x is equal to this， so substitute in this expression， put it in for x。

And then do that repeatedly what you're going to get is alpha plus g times alpha plus g times alpha plus g and so forth。

 And if you look at that， you can write that as a sum of g to the K where k is greater than zero times this alpha vector so one way to solve for what x is is going to say it's equal to this infinite sum。

And what that means is that this G is going to have to converge in terms of summing。 Otherwise。

 you're going to get an expression which explodes and the equilibrium is not going to be well defined。

 Now， just in terms of understanding that the equilibrium structure。We're getting a feedback here。

 right？ So the more action my friends take the more action I want to take and so forth。

 And so for that to work。 Well， it has to be that these weights that I put on other people are small enough relative to the cost。

 the B so that I don't want to take an infinite action。



![](img/9a403a06236059de5cd3c3268cf0501e_13.png)

And so that's going to make sure that this thing has to converge where remember this these entries here are the relative weights compared to the bees。

 and if those are small enough， then the single will converge if they get too big。

 then there won't be a nice solution。

![](img/9a403a06236059de5cd3c3268cf0501e_15.png)

Now another way to solve this is just to write this as x times I minus G。Is equal to alpha or sorry。

 I minus g times x is equal to alpha， and then that means that x is equal to alpha times I minus G inverse。

Down here， so I got this reverse， the alpha should be here。



![](img/9a403a06236059de5cd3c3268cf0501e_17.png)

So you could have x is equal to I minus g inverse times alpha if this thing's invertible and this thing being invertible is the same condition that you need for this thing to converge。

 okay？

![](img/9a403a06236059de5cd3c3268cf0501e_19.png)

So we have a very nice solution。 We can find X now directly as a function of the parameters of the game。

 the A and Bs and this G matrix， which is the Wjs and the B's。 So we have a very simple game。

 it ends up giving a nice solution where we can calculate the actions of every player as a function of the network structure and the payoff structure。

 Now if a is equal to0， then we end up with x equals G X。 So then it's just a unit eigenvector。

 So then we end up with a solution， which is just an eigenvector calculation。



![](img/9a403a06236059de5cd3c3268cf0501e_21.png)

![](img/9a403a06236059de5cd3c3268cf0501e_22.png)

![](img/9a403a06236059de5cd3c3268cf0501e_23.png)

![](img/9a403a06236059de5cd3c3268cf0501e_24.png)

![](img/9a403a06236059de5cd3c3268cf0501e_25.png)

![](img/9a403a06236059de5cd3c3268cf0501e_26.png)

Okay， so what's nice about this model， the actions are related to the network structure。

 we get higher neighbors actions， higher own action， higher own action， higher neighbors action。

 so we get these feedbacks， so in order for a solution we need the B to be large enough and or the WIJ is to be small enough so that this actually converges but once it does then there's a very nice prediction and what's interesting is this relates back to our centrality measures so let's have a look at this so we've got our solution that we can write X in either of these forms。



![](img/9a403a06236059de5cd3c3268cf0501e_28.png)

Recall that Boniic centrality looked like a calculation which was very similar to this。

 it looked like counting paths of different length from eyes to different Js and then summing over all possible path lengths。

 according to some weight， that's exactly the calculation we're doing here。



![](img/9a403a06236059de5cd3c3268cf0501e_30.png)

![](img/9a403a06236059de5cd3c3268cf0501e_31.png)

And alternatively， we wrote Botic centrality looked like an I minus g to the minus1 times G times1。

And so if we write boes centrality in these manners， then we can rewrite the X's。



![](img/9a403a06236059de5cd3c3268cf0501e_33.png)

So we've got the x's look like this， Bo system centrality looks like this。

 so alternative representation of the x。Is that x is equal to1 plus the botic centrality times a over B。

So， in fact， what we can say is the action that any individual will take in one of these linear quadratic games of complementarities。

Is something which is proportional to their boes centrality。 So higher bonuses centrality。

 higher actions。Okay， so we've got everybody takes an action A over B to begin with。

 which is just sort of what they would do in isolation with no network。

 and then the extra network effect adds in these complementities and how much extra action they get here depends on their boide centrality in a network。



![](img/9a403a06236059de5cd3c3268cf0501e_35.png)

![](img/9a403a06236059de5cd3c3268cf0501e_36.png)

Okay。So we get a natural feedback in complementarities。 The actions relate to the total feedback。

 centrality tells us relative number of weighted influences from one node to another that captures the complementities and why is that working。

 So again， know these things we're measuring sort of how much do I get influence from other people from other from their friends and so forth。

 That's exactly what's happening here， How much does their action influence my friends actions。

 which then influences my action and what do the feedbacks look like。



![](img/9a403a06236059de5cd3c3268cf0501e_38.png)

![](img/9a403a06236059de5cd3c3268cf0501e_39.png)

![](img/9a403a06236059de5cd3c3268cf0501e_40.png)

![](img/9a403a06236059de5cd3c3268cf0501e_41.png)

![](img/9a403a06236059de5cd3c3268cf0501e_42.png)

Okay， so we've got this nice solution。 So the beauty of their model is that you end up with a very simple expression for X。

 This scales with A over B。 So this is just multiplying everywhere so we can just rescale and eliminate that So if we think about the GIJ is equal to WIJ over B。

 let's think of a simple world where you either connect it to an individual or not。

 And then effectively the main thing is you know who you're connected to and what's the size of B and then that will give us a calculation and you can directly estimate these things。



![](img/9a403a06236059de5cd3c3268cf0501e_44.png)

So for instance， if we do that calculation， you can do that calculation here's on one network for which they did these calculations。

 you can do it in different settings， so you know depending on whether what B is， if B is 10。

 that's sort of relatively high cost to taking actions。

 then what do you get you get that person in the center position takes an action of 1。75。

 this person takes an action of 1。88， this takes 1。

72 these people are all right this is going to be a 1。72。1。88。1。88。

So depending on how many neighbors you have and how central you are in this case the highest action ends up being for these individuals in this position if you rescale the B and change the B to a different level you get slightly different numbers basically here you can redo that for B equals five so if you lower the cost people's actions go up and in more than doubles and it's more than doubling because you're getting a feedback so everybody wants to put in a higher action but that means that their neighbors want to take higher actions was that even increases there more so if you hadn't been doing this with the with the neighbor feedback you know just taking the cost in half would have doubled the action now with the feedback we get an extra effect and indeed for this particular example you're still going to get similar structure but much higher actions So what's nice about this model is it gives us predictions of exactly who。

s going to take which actions as a function of their position in a network and now we've got something which begins to give us some feeling for why Boed centrality might be an interesting centrality measure。

 it's coming out and it's giving us some idea of what the feedback is in complementarities and in games of strategic complementities that can be important。



![](img/9a403a06236059de5cd3c3268cf0501e_46.png)

Okay， so that takes us through another game with this kind of feedback Now you know the nice part about this is it allows one to do calculations in terms of a simple network measure。

 it's going to be more difficult if we want to add in a lot of heterogeneity among nodes and have different nodes。

 have different preferences， but we can enrich these models in ways that allows us then to take them to data and indeed people have been starting to work with these models and starting to do analyses of what predicted behavior looks like as a function of the network and then actually seeing whether that gives us some insight into what's happening in different settings。



![](img/9a403a06236059de5cd3c3268cf0501e_48.png)

![](img/9a403a06236059de5cd3c3268cf0501e_49.png)

![](img/9a403a06236059de5cd3c3268cf0501e_50.png)