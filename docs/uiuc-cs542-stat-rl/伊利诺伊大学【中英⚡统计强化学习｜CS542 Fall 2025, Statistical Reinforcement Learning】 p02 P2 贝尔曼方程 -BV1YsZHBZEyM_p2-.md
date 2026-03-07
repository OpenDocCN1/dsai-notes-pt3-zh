# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p02 P2 贝尔曼方程 -BV1YsZHBZEyM_p2-

嗯。Okay， let's start。So， so there's the first reading homework。

 We'll see if we have time at the end of today。 If not， we'll talk about it on on Friday。

 but we'll continue with the lecture contents from last time。

 So last time we introduced the Belman equation for policy evaluation。 if you give me any policy pie。

 by the way， one thing I did mention is that in the derivations here， everything is。We're。

 we're only considering policy in the form of deterministic policy。 The map states to actions。 Now。

 this equation can be pretty straightforwardly also generalized to policies that take a randomized action。

 given any state， so。You know， the， the， the situation will be very similar。

 So the only difference is that here you get a prime。 and in the front。

 youll get another summation that， you know， just do a weight is sum， you know， essentially。

 you calculate expectation， according to the， the probability of actions given by your policy。

 by a given x。So at the end of the day， like a very， a very similar equation hostse。

 you still have this。 But whenever you have pi of S。

 you just need to replace that with the expectation of the quantity with respect to the distribution of reactions given by your policy。

 So to some extent， we also use the abbreations sometimes like。Oftentimes， I write this way。

 R of S pi， first of all， like whenever you see pi。

 But where you expect an action and you see a state in the front， of course。

 it's always the case that you want to plug the state into that policy A pie to get an action。

 And second， I often use this notation as a unified notation to mean， for example。

 in a if your pi is a stochastic policy。 This means you take expectation with respect to the random action。

And you have R of assay over here。Okay， and as you can see。

 if your pie is a determinedmin state policy， what we see on the top is just a special case of this。

 right， That's when your， your， your policy put a point mass on a single action。

 then the expectation is just evaluating the function inside on that particular action and all the bio equation。

 everything holdsse when you have a， when you have a stochastic policies。😊，Okay。

 so then we talked about how you can have the， how you can actually calculate the value function by solving for this linear linear system of equations。

 And the key question is whether the。是。Whether the， the matrix over here is actually invertible。

 So we went to。we went to do a proof trying to prove that this Ima P I minus gamma P pi is always inverable。

 And as I mentioned， the only thing you need to remember is that P pi is this essentially a transition matrix of the mark of chain induced by the policy pi that satisfies the following that every all elements in P pie is not negative。

 And each row sum up to one。 right， So this is the only。

 that is each row represents a probability distribution over states。

 And this is the only property you need in order to prove that this matrix is invertable。

And the way we prove it is to show that for any x vector that is now zero。

 when you multiply the matrix on the left of this vector， you get a vector that is also now0。

 And to show that the vector is now0， we introduced this infinite norm。

 which is just measuring the largest absolute value of you know。

 or of or coordinates of your of your vector， This is a valid norm。And。

 and what we do is that we first multiply the X inside and then use tri in quality to isolate out a x infinite or。

 And then gamma times p pi of x。 right， Then we use an argument that says that P pi X。Right。

 so you have P pi of x。We， we argue that P pi X infinite norm is always provideded by x infinite norm。

 right， So we give this intuition that essentially P pi X is just different ways to do linear to do convex average of the coordinates of x and average can never exceed the maximum。

 But if you want to write it， you know， carefully。 So essentially what you have is the following。

 right， So let's say I have P1 to P N。 And this is probably distribution and I have x1 to x n。

 which is the different coordinates of x， right， So then then what you have is that every entry of P pi of x。

 right， so。😊，The result is this is P pie X。 for each entry is just the do product or the product with between a row vector and P pie。

 which we know is a distribution with X。Right， so therefore。

 every entry in PY X takes the takes the form of P， I， X， I and summation over I。

So suppose like I is the index of the coordinates of x。Right then。We can now ask， what's the。

 can we upper bound be， the absolute value of this quantity， right， So if we can upper bound this。

 regardless of what your distribution P is， then every single， every single element here， you know。

 in every single coordinate of P X is just like different， a different distribution。

 like a different distribution represented as a row vector product you know， multiplied with X。Okay。

 so then this is what。 well， what I can do is that I can always push。The absolute value inside。

 right， So this is an upper bound。And because P Is， there are probabilities。 They are not negative。

 I can further push the absolute value into x。Right。

 and this is further less than or equal to summation over I P of。Max I X I， right， So for every X I。

 I replace upper bound X's absolute value with the maximum absolute value across all I。😊，Okay。

And what I get is that， or actually to avoid confusion， I use J here， Okay。

 so to avoid confusion with the index I in the front。😊，Okay， now that term becomes independent of I。

 so I can do this， right， I can take the， the X term， like outside the summation。And with this。

 what is sum of P over I。Is one because P I， I just said， is a probably distribution， right。

 And so this is one times。 what is this。Sorry it's not one。 It， it's something we is define。

 It's the infinite norm of x， right， So we define it before。 this is infinite norm of x， right， So。

 and， and if each， if each element of an if each element of a vector is upper bounded by something。

 then the infinite norm of this vector is also upper bounded by the same thing， right， So therefore。

 we establish that P P X infinite norm is upper bounded by x infinite norm。😊。

RightThen you have an extra gamma in the front， which shrinks the second term。

 And eventually you get this， which shows that this thing is invertible。Okay。

So as I mentioned before， like， you know， especially in the tabular part of the analysis。

 the L1 L infinitefinity norms are like way more useful than L2 norms。

 You probably won't even see L2 norm for a long time in this course up until like very almost the very end of of the course。

 you will see L2 norm again。 But for most of our part， you need to get used to you know。

 working with L infinitefin norm。 And very soon well see also L1 norm play a role。

 which is the dual norm of L infinitefin norm。😊，Okay， any question about this proof？Okay， so， and I。

 as I alluded to last time， this proof not only tells you that this matrix inver in is in always invertible。

 So， so from here to here， this is a valid implication。

 It also tells you that this set of equations has a unique solution。 So therefore。

 bound equation is a equivalent definition to the definition of value functions。Okay。

 so value function satisfy by my equation。 Any solution to the Bel equation is the value function。

Okay， so now。So this is the equation for policy evaluation。

 We'll talk about the optimal equation in just a bit。 But before then。

 there is something very important about the solution that I need to talk about。 that is actually。

 sorry。 So this is the stochastic case that that that I okay， let's let's go over this first。

 So this is the generalization to the stochastic case that I was talking about。

 I did I didn't actually， yeah， yeah， I forgot that I write it formally down。

 So in the stochastic case you have essentially you have a similar generalization。

 which says so previously， you have V pi of s equals R of S pi， right， R of s pi of S， right？

 And if you remember the first reward you get is just ask yourself。 if you start from states S。😊。

And we want to know what's the discounted sum of rewards will get， you know。

 in the long run in expectation。 Then we， we split that into the first reward and everything you know。

 that remains， right， And you ask yourself， what's the first reward。 Well。

 we know that the first reward is deterministically R of S pi of S。Now， if your action is randomized。

 your first reward may be random， but you can still ask yourself what is the expected value of the first reward。

 right， And apparently， the first reward is this。Because the only thing that is random now for the first reward you get is that the action is random。

😡，And the action is distributed according to the policy you take。😡，Right。

So you take expectation of the reward function。 That's very natural， right。

 And then you have the transition to the next state。 But again， in this case， the transition。

 you just ask yourself， given that I'm in state as。And I'm and I'm。I'm taken action。

 according to policy pi。 What is the distribution over to the next state。😡，Okay。

 so in the in the when you have a deterministic policy， well， that's just the first take like。

 you know， fix the action to be the action taken by policy pi and then ask the transition function to tell you what's the next distribution。

NowHere in the more general case， when your policy has a gives you a distribution of access。

 Well then it's just like marginalized out that action as well， right， So you have a。

So if you look at here， I have a， I have a， but I have a summation over a。

 So a is essentially being being like marginalized out。

 That is whenever I look at next state S prime， I'm encounter state S。

 I ask what's the probability I end up being like S prime， I look at all possible actions and and。

 and basically calculate what's the probability， I choose that action。

 And then like given that I choose that action， what's the probability。

 I will end up with the target state S prime。Right， so， so it like that， that gives you the。

 the probably。 Again， this is a generalization from the from the。from the， I say the， theistic case。

And in fact， you can actually write this like in a more general manner， which is something like here。

 right， So basically like there， there's a even more general form of B equation that that essentially says if your immediate reward is R。

 you get a ga gamma V pi of S prime。😊，An expectation。 and you get R S prime S and under policy pi。

Right so the right hand side is essentially says， you know， if you're in state S。

 you're running policy pi， that will just give you some distribution of a reward and next state S prime。

Okay， and then just take R plus gamma v pi of S prime and then take expectation of that。

 That is equal to v pi of S。 That's just the the Bel equation。 And the， the above。

 like all these different， more concrete expressions are essentially just the， you know。

 the specialization of this equation under different simplification assumptions。😊，Okay。And again。

 like the matrix form still hose that we introduced in the previous slide hose。

 you just need to define your transition probabilities as well the transition matrix P pi。

 as well as the reward vector R pi know in this more generalized fashion that accounts for the stochastic policies。

Okay， so。As I mentioned， I'll be using。This R of S pi and P of S prime given S pie as a shorthand for not only the deterministic case。

 but also the stochastic case。 And also， this will save us， you know， you know。

 you don't want to write like， you know， R of S pi pi per S like all the time because you will see that like you will。

 you will see two， you know， two occurrences of S like all the time。

 So we just like do this shorthand and get rid of one of the S。Okay。So， so homework 0。

 we'll talk about later。 So1，1 matrix you notice that plays a central role in in defining the solution to byma equation as a alternative definition to value function is this matrix I minusma P pi inverse。

Right， so it turns out that this this matrix has very special interpretations inside M P。

 So here I multiplied with my1 minuschema just as a normalization factor。 This doesn't really。

 you know， doesn't really have any real significance。😊。

Well it turns out that what happens is that each row。Of this matrix。 So first of all。

 Ima P pi is a S by S matrix。Right， so it's inverse。 is's also S by S matrix。And if I look at a row。

 a particular row of this matrix， I get a row vector。O。Now， it turns out that this rule vector。

 once you multiply it with one minus gamma， is always a distribution in the sense that it's not negative and sum up to one。

😡，Okay， and furthermore， you can actually write down this distribution as this。Okay， so。

 so this is the。So， so here the superscript depends on pi the policy as well as S。 So this。

 this particular s is like we have this we have this big matrix。 And we're looking at the。

 the row index by S。 Okay， so you get this， this vector。 this vector， we call it the P pi comma S。

 And okay， to define this vector， We can just look at ask ourselves for any column index S prime。

 What is the entry there。And the entry is。This。Okay。

 so it turns out that what what essentially happens is that is essentially a mixture of you know。

 distributions called D T pi S， where D T P S is what D T P S is basically the T step distribution over states。

 given that I start with state in I start from a particular state S。

 which is the state that I'm using as the row index。 And you have a distribution。

 then then you can ask， you know， what's the property for for， for any particular state S prime。Okay。

 so and this quantity is called the normalized。 often we don't say normalized。

 but it's often called a discounted state occupancy。 So if're taken like a mark of chain you know。

 you've seen like mark of chains before you probably be familiar with the notion of occupancy or station distribution and so on。

 So this is like a related concept。 But unlike in mark of chains。

 you talk about this asymptotic behavior where like you run the chain for infinity and like what's the distribution over there。

 So here as you can see， like when we take when we look at the discounted setting and。

 there is a lot of emphasis on transient behavior that is， you know， we look at the immediate reward。

 we want to optimize that。 then we also want to optimize the future reward。

 But the more future it is like the heavier discount we assign to it。 So so therefore。

 like when you actually you know， evolve the chain to infinity， you're actually you know， you know。

 whatever your behavior there， like we actually don't care。 We care a lot about。You know， how like。

 you know， the first step distribution， second step distribution and and so on so forth。对。So。

 so basically， you start from， remember， whenever I say I start from S and I have a policy pie。

It gives you a well defined distribution over the entire trajectoryreasury。😡，Right。

 and the trajectory is actually a combinatorial object。

 The trajectory is a big random variable that is state action， state action。

 state action and on so forth。 right， But whenever So it's a big joint distribution。

 So for this join distribution action actually zoom into any single variable and ask。

 what's the marginal distribution over there。 So here I'm basically ask under that bit join distribution。

 what is the marginal distribution of the T step state。😊，So that gives you a particular distribution。

😡，Okay， so this is the distribution over here。 Then you mix this distribution together， you know。

 using this gamma discounting。 And that final mixture distribution is what is D P S。

 So that is what appears in this matrix I minus gamma P pi inverse up to the normalization factor。

So below， I'll give you several ways to sort of interpret or kind of understand why this is the case。

 like some of， some of these are not really proofs， but really like just the different ways to。

 to to， to， to rewrite the thing。 And then you'll see like all different ways of rewriting the thing。

 like a coincide and， and give you some intuition for why this is the case。Okay， so here's the。

 here's one way to write it， right， so。So remember。

 V pi of S is just the expectation of the discounted sum of rewards。 When you start from S。

 you execute quality pi right？ But well， this is not the original definition。

 The original definition should be like this。Right。

 so the original definition has the expectation outside。

But now I'm pushing it inside because of what， because of linearity of expectation， right， So。

 so what it says is that instead of。Sum up all the random rewards along trajectory and then take expectation with respect to the randomness of the entire trajectory。

 I can look at the the， the， the expected rewards at each particular time step。

And just take that expectation and and then sum that expected rewards across different time steps。

So I can always do that。😡，Right， now， when you pull that out， what you get is gamma t -1。

 So now here you just have the definition， right， P pi of S T equals S prime given S1 equals S times the reward at that state。

So because this is by definition the distribution of S sorry。

 the distribution of S T that you see over here。Right， so， and。

And what we know is that this is equal to v pi。 So this should be equal to v pi of S。

 So this should be equal to I minus gamma P pi inverse R pi。 Now， now。

 what I can do is I can do E S transpose。 So E S is this unit vector that has all zeros。

 And there's one at the index at the coordinate index by S。Right， so。

 so this should be equal to this。 So these things must be equal to each other。

RightSo why they are equal to each other well。😡，Well。

 what you see is that what you can do is that you can just expand Im Gamma P pie inverse。😡，Right， so。

 so here I'm not giving a fool proof， but you probably know that。不知道啊。So。So， so how do you。

 how do you make sense of this， Right？ So we know that if you have one over1 minus x for x less than one。

 can you expand this as an infinite series。What is the expansion？Right， so it's a one plus x plus。

X square plus all the way to infinity， Right， in fact， like we， we actually calculate the the。

 you know， one plus gamma plus gamma square and so on so forth。

 When we calculate the geometric sequence， the sum of a geometric sequence， you get the left side。😊。

Right， now this is the scalar version。 Well turns out that the generalization for the for the matrix version that so there。

 this expansion only holds if x is less than one， right， But here。

 like we have something similar because the， the fact that P pi is a transition matrix means that is matrix spectrum is like less than one。

 you know， speakingea a in in a loose sense。 And then you multiply it with gamma。

 So it's kind of like， it's a matrix that is in some sense， like less than one。😊，Okay。

 so a similar expansion also holds。 So what you get is summation of the discount factor times P raised to different powers。

Okay， and as we mentioned in the last time， P pie is the transition matrix of a。

 of the market of chain induced by the policy pi。 Now， if you have a。

 if you have a transition matrix of a market of chain and you raise it power。

 what is the meaning of this matrix。Does anyone know？It's the N step like transition， right。

 Like for example， So P itself is is essentially this conditional distribution。 That is。

 if currently I'm mean say S， what's the distribution for the next time step。Right。

 but when you raise it to the power， ends power， let's say you raise it to the square。 Now。

 it essentially it this like it' essentially like a similar concept。 But。

 but you can like jump forward for multiple time steps。 for example， like if you have P square。 Well。

 you still get a matrix that looks like a transition matrix in the sense that every row sum up to one。

 But now it describes a distribution。 that is， if currently I'm in state as two steps later which state I be。

And if I raise it to the third power， it's currently I mean state S in after three steps。

 what's the distribution now be？😡，So this is the meaning of P pie race to the power。

 and if you look at it， like it exactly correspond to this distribution described over here。😡，Okay。

as I， as I mentioned here。 So this is not really approved， like this is like。

 if you already know some of the basic concepts in Markov chains。

 you will see that this way of expanding， expanding I minus by P pi inverse exactly correspond to how you rewrite V pi of S in this particular form。

O。And we'll see that this this discounted occupancy D P of S plays a very important role in R O。

 especially like we won't really， we well run into it from time to time。

 but not that frequently early on， but later， especially when we start to deal with function approximation。

 large state spaces and so on。 this distribution like plays extremely important roles。Okay。

 any questions so far？O， okay。third line。This one。Okay。Right。Well。

 so you want to calculate this thing， right？And what you can do is that。 so here like。

 essentially you， you， had to say。Yeah， we're not Oh， sorry。 Actually， I think it's atypo。

 So this should be S prime。Does that make sense， Does Does that look correct now。because the S prime。

 because this is essentially taking expectation， right， In with respect to a distribution of S T。

 And so I'm using S prime as the summation index。 So here you have S prime。

 here it should also be S prime。Okay， so we'll come back to this。To this quantity later。

 when we actually need it and， and we will see that that， you know。

 what kind of roles it plays later。 But for now， it's kind of like more of like a， a。Sort of like。

 you know， help you familiarize with this concept that， you know， we actually already run in。

 run into it in some fashion。It won't be like immediately useful for now。Okay。

 so so far we've been talking about the Bama equation for policy valuation， right， So this is a。

 you give me a policy， whether it's good or bad， The question of computing value function is just to tell you how good it is。

😊，Okay， but of course， like we want to improve。 we want to actually find the optimal policy in this problem。

So there's a very fundamental result， which I won't again。 So this as I mentioned。

 So this part about automatic involves like much more subtle and technical proofs than the policy evaluation case。

 So here Ill be skipping some of the complicated proofs and only giving intuitions and one of the most fundamental results in Mps is that in the setting we consider here。

 infinite horizon discount andps。 there always exists a stationary and determiningministic market policy that is for all starting state simultaneously。

 Okay， so we'll see what that means in a moment。 So in particular， if you。

 if you see the value function， right， So we see V pie of S， right， So this how good your policy is。

 when you start from policy S。 sorry， when you start from state ads。😊，Right。

 so let's say you fix a particular state S。And then say， what's the optimal policy， Okay， well。

 so here， Op is clearly defined， right， You just find the policy that has among all possible policies that gives you the highest value over here。

Okay。But here's the thing。 Now， what if I， I change the state to some S prime， right？

 So I also do this process that say I find the policy that that give me the highest value for another starting state S prime。

Okay， now this policy over here may not be the output policy that optimized the optimize for the starting state S。

Okay， so in fact， it turns out that in general， in infinitefin Hizon discount NP。

 you can have multiple optimal policies。And， and you can have all kinds of like weird policies that that can be optimal。

 But here， what it says is that there always exists。

 It says that among all possible optimal policies， there is always one that is not only optimal for a particular state S。

 but is also optimal for all other possible state as as prime as well。Okay， and furthermore， it's。

 it's also deterministic。 So you actually don't need randomization over here。 You。

 Your auto policy only takes action based on current state， and it doesn't need any randomness。Okay。

 so。We actually see， you know， once we see the about opt equation。

 itll give you more intuition for why the optimal policy takes this form and why there can be other ways of。

 you know， other optimal policies that doesn't take this form。

 So we'll just leave this theorem here until we see the more we see the about equations。😡，Okay。

 so what we do what we're gonna do is that we let pi star to denote。Such a policy， which is optimal。

 Okay， so again， like， so here， note that this is an existential statement。

 It doesn't say anything about uniqueness。And， in fact， given an NP， in general。

 you can have multiple policies that are optimal。 And even if you require these conditions that is stationary that is mark of that is deterministic。

 That is， you have pi star maps S to a。 So here when， whenever we say pi star。

 we just say pick any one of those optimal policies and fix that。Okay。

And then what happens is that you can ask yourself， Pisari is a policy。😡，So I can。

 I can plug that into the definition of value function or the about equation for policy valuation and ask ourselves like。

 what's the value function for that policy， Well， it gives me a particular value function， right。

 So it's a function over states。 So I use a shorthand to define the function as the star because it's something that is like。

 you know， some kind it's a unique property of of the MP。😊，In fact。

 was what happens is that in general MP， you can have multiple optimal policies。

 but the optimal value function is unique。Okay， so like you can have different ways that achieve automatically。

 But when you translate them into like V pi star， they always give you exactly the same V star。

And this V star satisfies the Belelman optimize equation。Okay。

 so this is like closer to the equation than you see in the first。

 you saw in the in the first introductory slides。 we talk about using dynamic programming to solve or shortest path。

 right， So and， and we give some intuition here why this equation makes sense。 right。

 So it says like， okay， I make state S， I want to know if I behave optimal starting from the state。😊。

In long run， what's the optimal expected， What's the highest possible expected return I can obtain as a consequence。

Right， so that's the， you know， if， if you think about it， that's the， that's the。

 that's the what what we we we star as means。Right， so then on the right hand side。

 essentially what you what you do is that you say， okay， I'm in state S。

 Now I'm faced with like multiple immediate actions that I can choose from。Right。

So like if there are like several different actions， I can consider each one of them。

 So let's say Ive fixed an arbitrary one of them， a particular A。Okay。

 then are reason about the consequence of taking that a action A。 So I asked myself。

 what's the what if I just say， I just take action A here。

And then I'll transition to what I'll transition to I'll get some reward and then transition to some S prime。

 like randomly， right， And from now there on， I'm also。

 I'm going to behave optimally to and and to as much reward as possible expectation for the remaining time steps。

Okay。Now。Once I do that， I can reason about what's the total expectation what I I obtain over here。

 Then if I list all possible actions。Then I can choose from me immediately and compare the long term optimal value across the different options。

 And I do take a maximum over here。 That should be， by definition。

 the optimal value I obtain at state S。Okay。So therefore， like the question becomes， once I。

 once I commit to an immediate action A that I take from state S。

 what's the long term optimal value I can obtain from there on。😡，Okay。

 so this is what's inside this parentheies。 Okay， so as usual。Once I commit to a particular action A。

 the immediate reward is R of S。 right， So this part， you have no control of。

Because you've already committed to action A， this the environment already give you our of essay。

Okay， so after that， what happens？You take an action A state S， you and， and what happens next。

You have a random state transition， right， So because you've committed to action A， this transition。

 like the system draws S prime from the transition distribution given by S A is also not up。

 you know， not controlled by you， because you've already committed the first action。

 The next time you regain control is how you choose the next action， right。

 Everything that happens in between is governed by the system dynamics。Is out of your control， right。

 So these two things are just basically they they， they， they will happen regardless。

 like what you want to do。Okay， now you're in S prime and your and from the your own words。

 you're supposed to act optimally。Okay， so here again。

 like we see this idea of like writing down recursive equation。

 That is we already define V star to be the optimal value function of this problem， which represents。

 you know， if I mean instead as in the long run， how much total reward I can obtain， you know。

 maximally so I can just plug that in V star S prime and and， and finish this equation。Okay。

 so as a result， we get a recursive equation that is similar to the。

 the B equation for policy evaluation。Okay， so this is kind of like， you know， again。

 this is not proof， but just a give you some intuition for。

For why the Bel of finite equation makes sense and why it characterize the optimal value you can obtain in this problem。

Okay， so here is the question。 So， so we actually need to answer a couple questions today and also the on Friday。

 one is similar to my question for policy evaluation。 That is， is this a。Does。

 does this equation has have a unique solution， Right， So again， if so。

 we willll see that this equation is also alternative definition to the optimal value function。

 That's the， I don't think we'll get to that today。 But that's the question we we need to answer。

 And the answer is， yes， this this equation has a unique solution。And the other question is。

 recall that when we say we pursue optimality， eventually we want to output a policy。Right。

 but even if somehow you're able to solve this the set of equations。

 Well because there's one equation for every starting state S， right。

 So even if you're able to solve this equation for a particular stars sorry。

 even even if you are able to solve this equation， which means that you get this V star as a vector over states。

 It doesn't tell you how to behave。 It doesn't tell you like， what's the right action to take。😊，Okay。

 what's the optimal policy， Well， you need a policy that tells you what action to take under different states。

😡，Okay， but now look at this equation and look at the reasoning how we sort of like intuitively get this equation。

Like， does it tell like if you already know V star， how would you actually take actions？😡，Right。

 so if you remember like the， the， the kind of reasoning we the intuition we give for this equation is to say。

 well， if I'm mean state S， I want to achieve the optimal long termm reward， what do I do， Well。

 let's consider each possible action I have available immediately for each action， if I commit to it。

 but then behave optimal from their own words。 This is the total value I would get。

And among all of them， like， I take the max， which is the optimal value I have for the current state。

So now， like， let's say you get V star of S or V star as a function for any possible state。

 You're now in a random state S。 What's the action you should take。😡，Anyone， any guess？Right。

 so it like I said， like you list all the options， evaluate their long term total rewards and you max them to get an offer value。

 Well， what's the action you should take。The Arc Max over here。Right。

 so this is also gives you a intuition for why。 So， so basically， the claim is that。呃。

Like for any state。Whatever action that achieves the max over here is the is an optimal action that you can take。

Okay， and how do you calculate it？ Well， if you have soft V star。😡，Well， you know this guy as well。

So you can calculate this quantity for every possible action。

So you calculate each of them and see whatever achieves the maximum value across the immediate actions available to you。

 And that action is the best action you should take at the state。Right， so that's the optimal policy。

 Once you take that action， you transition to next state。 Well， you need to take an action again。

 Well， again， in that new state， you calculate this term for every possible action for that new state。

 and then you choose the action that maximizes the right hand side and again and again。Okay。Right。

 right。 So， so remember， here we're in the planning setting。 So you know everything。

 You know the reward function。 You know the transition matrix， you know everything， right。

 So therefore， so here， like， remember， everything is computational。 So the， the。

 the statement I just made is this is， is that if， if you are able to solve this equation to get V star。

😊，Then you can just plug in over here， Then you can evaluate this this expression for every possible action A for whatever state you're in and whatever action that maximize this whole expression is the optimal action for your state。

Question。So so wearing in this standard setting where everything， right， you see like here。

 the transition matrix is also time independent。They they're always like in the standard infinite horizon discounted setting。

 everything is time independent， right， So not only the so there， there are two parts to it。

 one is how do you define the problem。 So we define the problem to be such that the transition transition dynamics as well as as rewards are all time independent。

And then you get consequences， which are the value function for any policy。

 as long as your policy itself is time independent。 right， Your。

 let's see what we call stationary and mark of policies。 That is your。

 your policy is just mapping from states to actions or distribution reaction。

 As long as that's the case， all your policy specific value functions like the pie。

 They are also time independent。 right， So this is the consequence of this some self similarity like structure of the geometric discounting that we talked about last time。

 And here so here we will see as， the。Similarly， the optimal value function itself is also time independent。

 You know， for a similar reason， although we didn't improve over here。Okay， so the， the， the， the。

 the B equation， the time independence of， of of v pie。 we， we did prove like in。

 in the previous lecture。In the final horizon set， it makes more sense to talk about like time dependent transition probabilities and reward function and so on。

 But we'll get to， get to it later。O。Now， as you as you remember， sorry， as I just said before。

 like when I give you intuition for you know， how you should get the optimal action and also forth。

 I repeatedly mentioned this whole expression after Max over a。Right， so almost to the extent。

 I feel like it's very inconvenient that we probably need a notation for it。 And here we go。

 We need a notation for it。 So we define this whole thing after max of max over a。

 we call it a Q star of S A， right， because this whole expression is a function of the state your a。

And whatever action that is under consideration that you essentially tentatively commit to。Right。

 so you're in state as， you wonder which action you need to take you should take Well you consider each one of them and evaluate each one's value。

 So you need to tently commit to each action。 So whenever。

 whatever action you commit to that defines。Like a value for you on the right hand side after max over a。

 So we call this this， the the， the value of this as a function of by A called that Q star value。

Okay， and as I mentioned， like Qstar has this definition that is essentially the optimal expected reward you will get when you start from state S。

 But the first action， you just choose an arbitrary action would actually you choose。 Well。

 this argument tells you， right， So you plug in an action over here。

 it could be a sub optimal action。 Well， you just accept it that that you're taking this action in the first step。

But in the long run， afterwards， you're gonna always take optimal actions from their own wordss。

 right， Because here you're in state S， you're forced to take whatever action Ill tell you to take in the first step。

 But starting from S prime， I'm plugging V star， which means that afterwards， I'm behaving optimally。

😡，And what is the total value you get over there， right， So this is the definition of Q star essay。

So as I mentioned before， like the action the optimal policy is just you know。

 take an arc maxax over Q star。So this also tells you like， in a way， why， you know， why。

 you know it's not approved again， like， but， but but you know。

 it it helps explain why the optimal policies is deterministic and and and stationary while you like Q star is a function of S A Well you just need to take action to maximize it while you can always just take action according to an S。

 Okay， on the other hand， it also tell you why in general， optimal policies are not unique。 Okay。

 so so when can like can， can you see like in what circumstances do you have multiple optimal policies。

Yeah， so if， if this arc max is not unique， when you have ties， right， So for us the same as。

 you can have multiple actions that share exactly the same Q star and all of them maybe like are optimal。

That in that case， whatever action you choose doesn't matter like you're always optimal。Furthermore。

 you don't even need to commit to a single action。 You can actually choose the distribution of reactions as long as your distribution of reactions is supported only on those optimal actions。

 That also works。😡，And even furthermore， that is why like you don't even need to be a market policy。

 So the the form of policies we've been discussing so far is always like， oh。

 you can only choose actions based on states like you choose either a state action or distribution reactions。

 but you only choose them based on the current state。

 which means that if you run into the same state twice in two different trajectories and things that happen before you arrive in that state could look very different。

 But then if your policy satises this form， your policy must choose exactly the same action or exactly the same action distribution。

Okay， but actually， like if you want to achieve optimality。

 your policy doesn't need to take that form。😡，Okay。

 so let's say if you have a state where you have multiple actions that have the that all achieve the optimal value。

 then you can just， depending on how you arrive at the state， sometimes choose one of the actions。

 sometimes choose the other action。 So you can generally have a very complicated history dependent policy。

 but it's still optimal。And in fact， here is a trivial example。

 Suppose you have a process where the rewards are always0。

All the rewards are always a constant for any state action pair。Now， what's the optimal policy。

Anything is awful， right because your total reward is always that constant reward divided by1 to minus gamma。

😡，So any behavior is optimal， even if your behavior doesn't， doesn't satisfy this particular format。

 right， whatever action choices you do is always optimal。Okay， so， so this is why like， you know。

 if you keep that if you keep that example in mind。

 it should be immediately obvious that the optimal policy is generally not unique。 So in general。

 like if you study machine learning right So like whenever you see a max and you have am。

 aax is often this thing that is very fragile and sensitive Its like like when you have tie break like like everything。

 everything like is okay。 But if you just increase one of the item value a little bit immediately。

 like only one of them is a optimal choice and everything else like doesn't work right So so this aax is not unique doesn't have this nice unique。

 uniqueness property and so on so forth。 But on the other hand， again， like the same example。

 let's just make the example simple， let's say all reward are zero。

 right we just said that in that case， all policies are are optimal。

 So you just you just don't have uniqueness at all。 But clearly vstar that。Example is unique。 right。

 What is the start in that example。If you all your immediate words are 0。The V star is also0， right？

 And as you can see， like whatever kind of behavior you take。

 you ask what's the expected total rewards you get from any initial state， It's always 0。

So like that， you know， in some sense， like the this max value is like a much more stable object than the arc max。

快审。But like。History， dependent。Okay， I don't understand how that could ever be。It's not more optimal。

 Like， if you're optimal， you're optimal， right， you're optimal， in a sense， like what。

 what is the notion of the optimal， The notion of is this。It is that you have you have your policy。

 You evaluate this policy specific value function， which is like V pi。

 and you find it to be equal to v star。 Then you're off。RightBecause。Well。

 I I didn't write this down， Right， We said that this， you know。

 the kind of optimal policy we talk about in in this in the planning setting is simultaneously optimal for all starting stage。

 which means that for any S， for any pi， we have the pi star of。啊。

Of S is greater than equal to v pi of S， right， regardless of you have a。

 you have a single policy pi star that regardless of your behavior is。

 And regardless which star state you pick， I'm always like no worse than you in terms of the long term return。

 I can obtain from this starting state from this particular starting state。And， and so， maybe。

 so I I think what you're asking is like， you have a hard time imagining why you can choose a random action。

 Like， as I said， like， it's not more optimal。 It's just equally optimal。Right， so。

 so that's the first thing。 Like you can't have more optimal。 If I'm more optimal than you。

 then I'm optimal and you're suboptimal right， And and if you want an intuitive example， Okay。

 I scared people say， like， I won't give example， But I will， whenever it comes to mind， right。

 Think about a great world， right， Let's say you're in here， you want to end up here， right。

 And what is the optimal sequence of actions， well， you can do anything right， as long as each step。

 you either go right or go down whenever， like like whenever you're not hitting a wall。

 we know that it's optimal。Right， well， so in fact， you can just， as you can。

 So how many total steps you get， you get1，2，3，4， right， And if you add discounting， like， you know。

 it's a little bit less than 4。 But you get the idea。 Okay， so what is optimal behavior here。

 while there are many ways to do optimal， for example。

 as long as I'm not running to a wall in the right direction or in the down direction。

 I can assign any probability distribution over them。 and I can take actions accordingly。

So I get a randomized policy and still optimal。Does that make sense？啊没拿。No， like that。

 that's what this what this theorem says。 The theorem says that even if there like there are cases。

 actually nontri and interesting cases where there exists stochastic a stochastic op policies。

 But even when that's the case， you can always find a deterministic open policy。 For example， here。

 like， you can just always go right first and go down that's， that's deterministic and it's optimal。

but there are multiple one of them， like you can first go down first and then go right。

 that's also optimal。😡，Okay， any， any okay。So， oh， okay， so so where we were before all of these。

 we were talking about this  Q star value， right， So we defined this new quantity Q star so that we can conveniently。

 you know， refer to this expression on the right hand side， because once we solve V star。

 we still need to use first calculate Q star from V star。 and then take arguments over that。

 or as we call it gratify over a Q star to obtain the optimal policy。😊，And。You know。You know， so。

 so so far， we're talking about planning setting。 but， you know， as you know， like this is RL course。

 So later we'll call talk about learning setting。 So in the learning setting。

 you don't have access to the transition probabilities。So in the planning setting。

 we do have access to this so we can easily compute this， but in the learning setting。

 we don't have it。 So in that case， if you solve for V star， you can' easily get Q star。

So as it turns out in R， like a lot of times when we try to obtain optimal policy through Belman opt equation。

 it's actually better to directly solve for Q star And Q star itself also satisfy say variant of the Belman opt equation as shown over here。

 right， So it's actually the a similar。 essentially it's a its a it follows exactly the same intuition as the version for V star。

 So remember， Q star is asking the question。 What's the long term total you would get。

 when you start from state S。😊，Your first action is。Fix to whatever action I tell you to take。

Afterwards， you behave optimally。Right。So because your first action is fixed。

 your immediate word is fixed。 Your first transition is also fixed。 So these are out of your control。

 right， But then you end up state S prime。And as I mentioned。

 like the definition of Q star says that afterwards， you need to behave optimally。

 So essentially here。You should have the star of S prime。like essentially inside the expectation。

 you should plug in V star of Spir。开始。Okay， okay， so I think you're talking about a different setting like because I think what you're talking about is more of like a game theore setting where like like you're talking about like a football gatekeeper trying to guess where the the other teams like player is going to shoot like direction is is the other like his opponent trying to shoot the football。

 But let me just say that you're actually I think that setting is more of like a game theoretical like mini setting。

 There's a notion of avers or like know worst case reasoning over there。

 And there like is kind of like know like it's kind of like you toss a coin。

 And I try to guess right， but maybe you're actually not to the coin like very know purely randomly maybe you're doing some trick that I don't know that like whatever like I try to form a guess like maybe you can like secretly like change your。

😊，your coin。 But if I'm allowed to make a randomized guess， I can always say， oh。

 I think it's half half。 and you know let's say I get a random number generator。

 like I can always guarantee that I hit I guess correctly like half of the time。

 So there like there is a notion of aver So the difference is that in NP setting the standard MB setting we talk about is the environment is fully stochastic。

 the environment itself doesn't have this aversarial component to it。 So you don't have this notion。

 So in those kind of mini max games， essentially like you can appeal to concepts like a。

 And you say like in general， there may not exist like pure strategy。

 but there always like a mixed strategy， which means that sometimes the only optimal policy is randomized。

 But here are things are different because of the lack of aversarial component。

 There are extensions of MP is to handle like two player like zero sum games or。😊，General。

 like these game theoretic settings。 And， of course， in those settings。

 like you will need like optimal policies， general may be required to include some randomness in it。

可是。Can't depend on。Yeah， so， so that like， so yeah I think what you're saying is that you're， you're。

 you're introverting。 what I saying is that somehow the evolution， like like。

 maybe you're just saying in a different way that the evolution of the system is not a。Right。

 so essentially， like that's encoded over here， right， The transition probabilities。

 Now once I'm in state S， I'm taking national A， the transition dynamics are fixed。

 Like the system itself can't like， you know， do something that is like bad to you or something like that。

 There are different formulations， for example。There are sort of like worstcase versions of of this formulation thats that that is。

 for example， if you imagine a like a nature， right， So how you would formulate that kind of problem。

 Well， I can formulate it as every time I'm in state A S， I take action A。

 then maybe there's some possible set of states that the system can transition to and the system like behaves like asly try to choose like the worst state for my policy or something like that。

RightSo then there like you get into like these you know。

 into these kind of like aver settings and more like game theoretical like settings。

 But here is a welldefin distribution。 So it does it lacks this advers component So you don't need these like game theoreticalore concepts like know the optimal strategy needs to randomize itself。

 No， here like you can fully determineize your strategy and still be okay。

 But that's an interesting point because much later on when we talk about know learning from data。

 right， So when you're learning from data。 So here we're actually just doing computation with full knowledge of the system。

 But when you're learning from data， your data may not provide， you know。

 all possible knowledge of the system。 And maybe all you can get is let's say from the data。

 I can infer that maybe the system like looks could look like I can like let's say in the start。

 I don't know what what the system look like， I have a very big possible set of systems。😊。

That are all plausible。 But once I see the data， maybe I can rule out a large part of them。

 but still I have uncertainty set。😡，And in that case， maybe I can say， okay。

 like I have to deal with this uncertainty。 What do I do， I can do kind like a mini max。

 I can do kind of like a robust solution。 That is like。

 I imagine the nature is true things things like aly。 in in that said。

 I still want my policy to behave very well with respect to the worst case choice。

 I'm imagining in nature to be like anniversary or like malicious。 So in that case。

 you will see that actually， although you're dealing with the MP because of the uncertainty introduced by limited data and limited information about the system。

 you can end up with optimal policy or optimal in the sense of， you know， under the knowledge。

 you know， like optimal policy can be actually randomized。

 But that's like a far more like advanced topic than what we're talking about today。

When you have full knowledge in MP， everything is， you know， fully specified。

 The environment is not acting against you。 So the optimal policy is always。

 there always exists a deterministic optimal policy。O。So。

 so I didn't finish the intuition for the Q star equation。 So you have  Q star this equation。

 So in principle， here you should have V star of S prime。

 But if you have an equation that looks like this， which is Q star S A equals R of S A plus expectation of V star of S prime。

 Now， you like， you know， you need to solve for Q star。 But then you end up relying on V star。Okay。

 so that's very inconvenient。 Like， but it turns out that V star and Q star have this very simple relationship。

 right， So the optimal value of v star for a particular state is just the maximum value of a Q star when you maximize over all the possible actions。

😊，So when you substitute V star S with the Q star expression。

 you get a self contained set of equations where Q star is the only unknown variables and are the only unknown variables。

 and they appear on both sides of the equation。Right and similar to before， So for this V star。

 we have S unknown nodes and S equations。Here we have Q star。 We have S times a unknown those， right。

 but we also have S times a different equations because every single S A gives you a different equation。

 So again， that gives hope that you know， they these equations in either case have unique solutions as it turns out to be indeed。

 the case。 But that's something we will prove on Friday。😊，Okay， so like as I mentioned before。

 because of the convenience that this equation brings you that once you get  Q star。

 you immediately get the optimal policy。 But if you get V star。

 you need to go through this extra step of computing the Q star and the optimal policy。 So in R。

 we often deal with  Q star much more often than deal with V star。

 So if you want to like compute for the optimal policy by solving Bel automatic equations。

 typically is the Q star version of the Bel automatic equations， we're talking about。

 although like the way to solve these equations， their properties are very， very， very similar。 So。

 you know， once you understand， you know， one of them， your understanding。

 typically translate to the other。😊，Okay， any questions so far？Okay， cool。 So， you know。

 we will talk about how you actually solve this equation where along the way will actually prove its uniqueness on Friday。

 But for now， let's say we， let's go briefly over the。😊，The the ring homework that assign， right。

 So the。So the first question of the of the homework says that if you have MP。

And let's say we just define new MP where everything else is the same。

 But the new MP reward function is different。And they。

 it differs from the old M B's reward function by constant C。 So here are the constant。

 when I say constant， what I mean， I mean， this quantity is independent of the state action pairs。

 right， for any state action pair， the difference is always the same。Okay， then。

 then we ask the question， what is the relationship between the value function defining one MP for a particular policy and the value function of the same policy。

 But defining this other MP， What's their relationship。Has anyone thought about this？Right。

 so you always differed by a constant。 Right， So you have， for any S， this is S plus1 over sorry。

 C1 over gam。 No over1 minus gamma。Right， so essentially。

 what happens is that you're adding a background reward C every time step that regardless of what you do。

 like， so， so like you can imagine yourself first in this R prime MP， right。

 and you have some policy， you get some reward。Now， what happens when you're in the like RMDP。

 So essentially， like you can simulate like things in the you can run trajecties in the M prime MP。

 but still simulate what happens in the RMDP by saying， oh。

 in addition to the R primary what I get at every time step， regardless of what I do。

 I just receive a C units of reward。Okay， so then like regardless of your value function is in M prime。

 where reward function is R prime iss value your value function in M for the same policy iss just the the value function in M prime plus a constant。

 So here constant is C over one gamma。Right， so as a consequence， it basically doesn't change at all。

 The order of how good different policies are。 And， in fact， even their differences are not changed。

So this tells you that really， like whenever you have a MP， you have a reward function。

 if you shift the reward function by constant， you're not actually changing anything in terms of optimality or in terms of how good one policy is versus another。

And in fact， like this fact， like this is a， you know， clear mathematical fact。 It。

 it also has this consequence in So so basically， it's a very it also has this interpretation in economics。

 right， So economics， you talk about things like what you call it like opportunity cost， right。

 So you know， when you're facing with a decision making scenario which you should look at is really not the absolute amount that you get for each different option。

 right， So if there's an option that says if you take this option， you lose $100。

 Does that mean that you shouldn't take it。😊，Well， of course not， because what if the alternative。

 like you can choose， you will lose like $1000， right， So you just choose between them and say， oh。

 lose $100 is not that bad compared to the other option。 So eventually， it's about like， you know。

 like comparing the relative value of different options。

 So therefore the absolute amount you get doesn't really matter that much。

 So that's a reason why you can hear like whatever your reward function is。

 you can always add a constant。 And it still like， if you solve the new MP。

 the optimal policy is still optimal for the original MP。Okay， and this is also why we。

 we can say that we assume that rewards are between 0 and R max。

 And that's a assumption for convenience。 That is because if you have negative reward。

 as long as your reward are bounded， which is a which which is a assumption。

 let's say your reverse line in minus R max and plus an R max， Well。

 I can always just add an R max to all possible reward。

 then you get a new MP that is equivalent in terms of the policy。

 but your new MP does not have any negative rewards。Okay， does that make sense？Okay。

 so then we also the second question ask you to think about finite horizon MP， right。

 So as I mentioned for finite horizon MP， all you need to change。

 you can still keep the definition as a PR。 You don't need discount factor anymore。

 But all you need to change is to change the notion of expected return from the discounted sum of infinite words to a plane sum of finite words over finite horizon right。

 You say like I want to optimize this， right， and also typically in finite horizon。

 you have an initial state distribution， which weote as the0 over here。 and。😊，So here you。

 you will see that so in general， as I mentioned last time， your optimal policy。

 your optimal value function， the value functions and so on。

 all these like quantities derived from the NP， They become time dependent in final horizon formulations。

 right， So if you remember the， the example I gave， like， if every step， whatever you do。

 you just get a reward of one， What's your value function。😊。

Or your value function is equal to the number of time steps remain。 That remains， right。

 So it naturally becomes a time dependent quantity。But now you can ask the same question， like。

 can I also assume without less generallyity that my rewards are not negative。And the answer is yes。

 right， Because， again， like whatever your。If your reward is has negative component。

 but it's bounded， I can always just add a constant to the reward function to make it non negative。

And what that did is that if you add a C to each reward。

 you're just adding C times H to the total reach。So therefore。

 like it really doesn't change anything about optimality。Okay， so。

 so here's the more interesting example。 And this is a formulation that we wouldn't really。Actually。

 you know， formally characterized mathematically。 but it's actually the most natural setting you would actually encounter in practice。

 And I've seen like even experienced researchers fall into traps and confusions and misconceptions about this kind of formulations。

 which is， in reality， the more common setting， is that you have something that looks like a finite horizon MP where you start from some state。

 But your trajectory will end some time。 But in the， in the standard finite horizon setting。

 iss assume that。😊，O your trajectories。Have exactly the same length H。

 You start from the starting state。 You play H steps。 It ends。Right。

 but if you think about many problems。 So like in old school R terminologies。

An the environment where you start from some starting state and execute some time steps。

 And then there's a notion of termination of the task is often called episodic tasks。

 So like in there like trajectory is often often called an episode。 Okay， so， for example。

 like chess or go， right， you start from the in chess。

 there's a standard initial board configuration in the game of goal。

 you start with the empty board and you play， you play， you play at the end， there's say， oh。

 like weve play to the end， right， either in chess， It's a tie or a checkmate or in go。

 like you just have no extra room to play the game ends So this episodic episodic task。

 But if you think about like a board games like chess and go。 What's the fixed trajectory。😊。

It's not fixed， right， The number of moves it takes to finish a game is typically a variable。

 It depends on your policy。Okay， so therefore this is the most the common form of。

Kind of like an MDP setting you would run into in practice， right， So that is。

 you have some starting state and you roll out trarejectasories。 And at some point， you。

Run into a special state， which we call a terminal state。 And you just cut the trajectoryache there。

Right，Even if you think about navigation task in like a great world， right。

 you start from starting state and you want to go to the an state。 You， you， you take some paths。

 Once you reach the goal state， you cut the trajectory there because whatever you do afterwards doesn't make any sense。

 You've reached your goal， right， Why do I care about what happens and afterwards。

so this is the most standard setting you， you would actually run into practice。

 and you can still define either discounted or undiscounted some of rewards over here。 But here。

 H is now a variable。 It can depend on your policy。 It can depend on the starting state。

 It can also depending on the trajectory randomness。 So the。

 the number of steps you have in this particular trajectory。 is now a variable H。Okay。

 but here is kind of like the sort of like dilemma or kind of like un counterintuitive part。

 which is， as I mentioned， you can use these kind of formulation to naturally formulate problems like shortest path。

 right， So if you're in a grid world， you start from certain state， theres some go state。

 and you want say find me a policy that reaches the go as fast as possible。

 If you look at how this is typically formulated in you know， standard code base。

 What they do is that you give the agent a -1 penalty each time step。😊，Okay。

 every time step before it reaches the goal， you get -1。😡，So if you。

 even if you don't have discount factor， then once you reach the goal。

 the total reward you get is just minus the number of time steps。So if you maximize that。

 you naturally minimize the number of steps it takes to reach it a goal， which makes a lot of sense。

And then people would say that in this case， your reward function is minus-1 per time step。

 It's a constant。😡，Right。It's a constant across the entire state space。

 regardless of what what state you're in every time step， you incur -1 reward。

But now here's the question。 So it seems like， so if the lessons from earlier examples still host。

 it says that in MDP， you can always arbitrarily shift the reward by any constant and you can shift the negative rewards to positive。

 But in this case， if you shift the negative reward to constant reward。Right。

 what it means is that now， if every time step I get a reward of plus one。

And I want to maximize where I'm reward。 Well what's the optimal strategy。Yeah。

 the overall strategy is like keeping a circle。 Like you。

 you never want to go to the goal because the goal state means you're dead。

 You want to live as much as possible。Right， so it totally changed the incentive。

 It totally changed the optimal policy， which means that here you cannot change the。

Or change the reward function by a by you know， Arrbitrarily by shifting them by constant。Okay。

But whats even more confusing， which is the last part。 And I think after that were done today。

 it turns out that if if you have a， you know， these what we so calledled indefinite horizon Mps。

 which are where you raw trajectories and the treasury ends by some criteria and your trajectory length like maybe a variable。

 So if that's the case， But if your trajectory length is always bounded by some constant H0。

 then you can always convert indefinite horizon MP into equivalent finite horizon MP。

 like in particular， by adding absorbing state， right， for example。

 if you're in a if you're in a grid world， let's say you can you know。

 let's say like going circle is like forbidden or something。

 So you start from here and you go to the end state。

 But let's say you have different path that takes different time steps to go to the final state。

 But the total length of the path is bounded by say 100 or something。 So what you do is。😊。

Sa you add a additional dummy state over here。 And whenever you finish early。

 Let's say you finish at H less than H 0， there's still time steps left to make sure all your trajectories have exactly the same length。

 What you do is I just send the agent to the dummy state and let it loop over here and you get a zero reward each time step。

So this is a very standard way to convert between indefinite horizon problems to finite horizon problem。

 where essentially it's like a zero padding to make sure all your trajectory have exactly the same length。

Okay， so this is a very standard operation。 But here's the interesting thing。 If this is possible。

 it means that we can convert indefinite horizon problems into finite horizon problems。😊。

And we know that finite horizon problems， you can always shift the rewards by constant。

But why is it the case that in the indefinite horizon problem， we cannot shift rewards by constant。

 What's going around here。You cannot。 you're also adding to exactly， right。 So previously。

 when we say like each time step you get a -1 there we're in the indefinite horizon formulation where we don't have this dummy state。

Right， so there we say， oh， my reward function is a constant。

But once you convert it in the finite horizon setting and get this and adding this dummy state to pad 0 to make sure all horizon alternate batteriesies have exactly the same length from the starting state we define。

 then like as you see， like here， they are only dummy state and it takes no effect if the reverse are 0。

RightSo once you introduce these zero reward， your reward function is not a constant anymore。😡。

Before you reach the go state， reward is minus-1 for the go state， reward is 0。

So here you have a finite horizon problem。 You can shift the rewards by constant now。

 but whatever you shift the -1， you should also shift the same amount for 0。 right。

 If you shift the -1 to1， that says， oh， each time you're alive， you get a bonus。

 you get a positive reward plus  one。 Well does that incentivize you to stay in the grid world forever without reaching a goal。

 it doesn't， because if that becomes one， what does 0 becomes。😡，It becomes two， right。

 because you need to add plus two everywhere。😡，So it says that， oh。

 like every step before you reach the goal， you get a plus one reward。 But once you reach the goal。

 there's a delicious meal there that every time step you enjoy even more rewards。

 So that still incentivize you to go to the go place as soon as possible。

 So this makes everything consistent because you know now you can now shift the reward by constant。

 but because of this new dummy state， it's now like it's now you your reward function is no longer constant across the state space anymore。

 So that still preserve the automatic behavior of the original MP when you do the shift of rewards。😊。

