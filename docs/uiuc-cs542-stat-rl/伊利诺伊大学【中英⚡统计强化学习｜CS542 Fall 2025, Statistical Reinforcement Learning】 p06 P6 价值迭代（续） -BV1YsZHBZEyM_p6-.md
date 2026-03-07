# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p06 P6 价值迭代（续） -BV1YsZHBZEyM_p6-

哎。Okay， so before， before we start contents， I just published the first homework。

 did people like receive the canvas notification。 Yes， okay， great。 So it's due in two weeks。Hello。

 okay， oh， so it's out of that。 Let me try this one。是Y it's not吃。helello ok ok呃 so呃。😊，So usually。

 it will be due before。On on， on a class day before class。

 and we'll try to add a an an hog office hour from T A like the week before the do and。Yeah。

 so for the details and please check the assignment。Okay。

 so last week we talked about a value algorithm， right。

 So it's just the very first algorithm for solving Belma optimal equations。

 which can also be used to solve Bel my equation for policy evaluation。

 by noticing that these equations are fixed point equations， right。

 you can write things as the fixed point of an operator。

 And because these operator have this so called contraction properties。

 You can just like repeatedly apply an operator to an arbitrary initialization and eventually just converge very quickly to the desired function。

😊，Okay， so that was the kind of proof that we used the other day。 And but today。

 I first to give you an alternative proof to valuation using a completely different strategy。 Okay。

 now the previous proof is like relatively rigorous。

 So so this one is's gonna be a little bit hand wavy in in certain steps。 but。

 but I want to share you that there's like this very different view to valuation that actually is up to those like hand wavy parts is completely elementary。

 And I don't even need to introduce the concept of contraction。😊。

And yet I can still like prove what I want。ok。So now this proof strategy works both for the。

Finally sorry， both for V Q like so previously， we we analyzed the the Q star based equation， right。

 So the Q star equals the T Q star。 we also said that we also write V star as the fixed point2 by abusing the notation T for this proof。

 I'm gonna do the V star version。 So you know， like for the v star version。

 you can also prove that the corresponding T operator is a contraction。 And then， you know。

 you have the same algorithm just it iteratively like repeatedly like applying the T operator。

 and and the proof is all the same。 So today what I'm gonna do is that I'm gonna okay。

 so I'm gonna like write down the algorithm for v star。

 And then use a very different way to analyze and prove is convergence。😊，Okay。

 so what's the algorithm again， So you have f 0。 Let's say we start with zero rationalization。

 So here， because we're analyzing the v version， the Q version will be very similar。

 but somehow like for this proof， it's a little bit more straightforward and intuitive for the V star version。

 which is why I'm choosing the V star version， Okay。

 and then for any K that's larger you just have Fk equals T fK-1。

 So this is was what value version is about And v star version of T operator is defined as for any f that is。

😊，Real value function over states。Well， TF is another real value function over states， right。

 So and what it is， this is max over a R of S A plus gamma expectationhoration as prime。😊，SA。

F S prime。Right so it's the same thing like it's just the right hand side of the Belma automatic equation for V star。

 but you replace the V star over here with your input function F。Okay， so， so this is the algorithm。

 Okay， now we want to prove its convergence。 That is how quickly FK converges to the star under our infinitefin norm。

 right， So what we're gonna。😊，So what we're going to do first is to write down a。Few iterations。

Of this algorithm and trying to observe like what is actually happening。 Okay。

 so what's the first equation。 First equation was just like F 0 is 0， right， You have the0 function。

Okay， what is F1？😡，So look at it over here。😊，Okay， so this is Tf， Now F0 is 0。 So what is F1？😡。

It's R， but there's a little bit more than R。F1 is actually a。呃。1位。What what is F1 of S。

 R is a function of B A， but F1 is a。 So here we're doing the V V version， right， So。

 so all the function are function of state。And， and what is the F1 what is F1。Right。

 so it's just like you you' plugging f equals 0 here。 So that goes away。 right。

 So all you have is the reward term。 But you're right， if we're doing the Q version。

 the first iteration would be R， right， because that's a value function of that's a function of state action pairs。

 And， and and the Q version， the operator doesn't have the max over here， but have the max over here。

 right， So the Q version， the first iteration is is R， But the V version， the first version。

 the first iteration is max over a R of S A。😊，Okay， so let's do one more， right。

 So you have a F2 of s， which is equal to。😊，Well you just plug it in， right。

 So you have max over a RA plus gamma and expectation S prime PA。Then you have a。F。

 which you you should plugging F1 over here， right， So what is here。

 while we just have max over a prime R of S prime a prime。Right？Correct。So， so I mean。

 I'm literally just like applying the， the， the operator like， you know， few times。

 and you can keep going and keep going and keep going。Okay。😊，So。What is this， Okay。

 so it turns out that so， so when we do the analysis based on the contraction， we。

 we always say is that we just get a sequence of functions， right。

 But those functions are generally like we don't really think about what those functions represent。

 Theyre just pretty much like arbitrary functions。The eventually。

 they will converge to Q star or V star。 That thing is like meaningful for this MP。

 But the sequence of functions that we obtain in the middle。

 like when we execute this algorithm is at least like in our previous analysis is pretty much meaningless。

 okay。😊，However， when you write it down in this way。

 I argue that these function you obtain along the way actually have some interpretable meanings in this NP。

Does anyone know like what these functions represent？Like I want。Exactly， right， So， so basically。

 the， the claim is the following。 The general claim is that。We can define the thing called define。

V pi H of s。As expectation。Submation T equals 1，2 H gamma T -1 R T S1 is S， and I'm using policy pi。

 Okay， so I can define this quantity， which is to say if I'm gonna execute take actions according to policy pi。

What and I'm starting from state S， right？ So we have the usual definition value function that only needs these two elements。

 which is the starting state and and the policy。 But that is usually defined with respect to the infinite sum of discount rewards。

Okay， so here I'm introducing additional factor， which is like say， no。

 I don't add up like everything all the way to infinity。

 I only add up like the first H steps of rewards。Okay， now， no， this is a well defined quantity。

 right？ now for this particular objective， when you have different policies， you have different。

 like this value， right。And I asked myself。Like， by all， like， among all possible ways of behaving。

 what is the behavior that gives me the largest value over here， right， so we can define。呃。V star。呃。

 of。H of S is defined as max over。All pie。嗯。V V pi H of S。O。And here in particular， here。

 this all pie includes non stationary policy。 So I will explain that later a little bit。 right。

 so this is what we talked about before。 if you remember。

 like when like we only have this mathematical convenience and elegance where everything is like stationary。

 that is time independent， right， because we have this infinite horizon discounted objective。

 So under infinite horizon discounted objective， your value function doesn't depend on time。

 your optimal policy doesn't depend on time， whether when you whenever you run into a state S。

 whether you run into the state at time step 1 versus time step 10。

 you should behave in the same way。😊，Okay， but， but here。

 because I'm changing into essentially a finite horizon objective。 right。

 So this is the sum of finite number menu rewards。 So the actual optimum policy to optimize the objective is actually non stationary。

 Basically， like you need to change your mapping from stage to actions differently。

 depending on how many time steps they that there there remains question。😊，Division of where。

 Where is division。Expect。Gmma t-1 R 17。O， yeah。Okay， so， so the claim。 So， so， so so far。

 this is just a definition。 and the claim is the following。Claim V star H。

 which is just the thing I defined over here， is equal to Fs sub H， which is the function。

That oftail along the way。Right， if you think about it， right。

 because F 0 is just saying like there are0 times there there like the number of remaining times F is 0。

 So H equals 0。 So you have nothing to earn， right， Re is 0。 So your value must be 0。Now。

 what's the optimal value， If you set H equals  one， or if H equals one， this is just asking。

 what's the maximum immediate reward you can get if you're in state S。 Well。

 then you just have one step to go。Right so you mount all the actions。

 you look at the rewards and you pick greed the maximum reward， which is F1。😡，What about sorry。

What about when there are two steps to go。Well， you， you essentially do this like， you know。

 like essentially dynamic programming right， you just first say， oh。

 if I run into some S prime in the second time step， what should I do？ Well， at that time。

 theres only one step remaining remaining， So I should just like pick the greed action that maximizes the reward over there for S prime because there。

 there's only one time step remaining。😡，Thenre not back off。To the first time Sap and say， okay。

What should I do over here instead a， instead a， as when there are two steps remaining。 Well。

 I look at all possible actions for each action， my total value will be the currentary word plus expected next value。

Right， so the optimal action is whatever I should choose over here。By the way。

 if you look at this equation， this equation also implicitly tells you why the optimal policy is time dependent。

 right， So because at time step， when there' is only one time step that remains。

 your optimal your optimal action is dictated by this agonax。😡，Right。

 but when you move one step forward one step earlier， your off action is dictated by this arc max。

And the two of them are generally different。Right，Because one of them consider two rewards。

 which has this， you know， one the the one of them only consider one step reward。

 which is completely myopic。 There will be no trade off between short term gain versus long term gain。

 But when you have these like two step rewards， you need to start to have that a little bit of that trade off right。

 So the kind of like behavior you would optimal behavior you expect out of that is generally like different。

O。So and and and this particular part， which is like this particular claim。

 is where I'm not like expanding a foolproof。 And so therefore like it's a bit hand wavy。

 but I hope like this calculation and intuitive explanation kind of like convinces you that this is essentially what happens。

Okay， does that make sense？Okay， so if so it turns out that if， if we accept this claim。

We can establish the convergence of value duration。Very easily。

 like using only elementary math without， without any， you know。

 introducing contraction properties and so on and so forth。Okay， so here's the thing。

So what this says is that。For any pi， now I restrict myself to policies that are stationary。 Okay。

 then I have V pi。😡，H less than or equal to v star of H。RightSo so because I just said that V star。

 I define it to be the optimal value under this particular objective。Right， so therefore。

 however you behave， you choose any other behavior。 You can't exceed the value you obtain over here。

Okay， does that make sense？So and here is the， here is the maybe a little bit and further。😊。

V pi star H is less than v star H。Okay， so， so this one is getting a little bit maybe。

Well get get get some of your， youre thinking for a while。 And， and it can be confusing， right。

 So what is pi star。 So pi star is this particular policy， which is。

One of the policies that maps states two actions。 right。

 So this is the optimal policy for the infinite horizon discounted objective。Right， so。

 so now some of you may be confused。 Its like， oh， this is the optimum policy。

 How can it be worse off than something else。😡，Well。

 it turns out the reason is because this policy is only optimal for the infinite horizon discounted objective When you consider what happens。

 what kind of behavior give you the maximum reward when you consider adding up rewards all the way to infinity。

However， whenever we have this comma H， we're considering a different objective function。😡。

We're considering what happens when you optimize for a finite number of rewards。😡，Right， so。

 for example， like if， if， if big H equals one， then all I'm saying is like， okay。

 among all possible behaviors， who can obtain。You know， the maximum immediate reward。Okay。

 so clearly， you know， it's going to be the action that just take the argumentgon X of R。Now。

 if you plug in that optimal policy for long term rewards， it's going to in general。

 get lower rewards under this objective if you only can what happens in the first step。😡，Okay。

 does that make sense？So therefore， you have， you have this in quality。

 which says you take the policy opt for infinite horizon discounted objective。

 but you evaluate it under different objective。 that， of course。

 like it's going to be suboptimal because。Because you are considering your objective。

But you're considering a policy that is not optimized for the objective you are currently considering。

😡，Okay。So you have that。Now。Well， we're also going to show。Is okay， so then。Furthermore。

This is less than equal to。V star。Okay， so V star is the。

 the value function that we've defined before， right。

 So the optimal value under the infinite horizon discounted objective。 So here。

 what happens is actually an objective switch。 We're actually changing the objective。 And why。

 while this particular step relies on the non。😊，Ngativity of reward， right。

 Because you define objective to be this way。Well， however， if I get rid of H。

 which is which is essentially this guy is essentially V star infinite。Right， because because our。

 the objective we're familiar with from the previous lectures。

 like how we define V star is essentially V star H， but set H to infinity。

RightBut because rewardwords are now negative， whenever you just add more rewards。

 like that's a strict again， like you never lose。😡。

RightSo if you compare the optimal value for shorter age versus a longer age， of course。

 the optimum value under longer age will have a larger value。

Because I I just have more rewards to collect。Okay， does that make sense？So， so this a in quality。

 like I' am having， although it's very simple， conceptually can be quite twisted， right。

 So the first thing quality， I'm comparing。😊，Two policies under the same objective。

 whereas one of them is the optimal policy， but not for this objective。 But then the second step。

 I'm actually switching between like two different objective functions。Okay， so this is one side。Now。

嗯。On the other hand， so what what do we want to do， right？ So what we have is that this guy is F H。

 right， So this V star H is just F H， which is some function we get along the way when we run value duration。

 right， And our goal is to show that as H increases， eventually。

 this function will converge to V star。😊，Okay， so what we have here in this particular equation in quality tells you that F H is always lower upper bound by Vi star。

Okay， so therefore， all I need to show is kind of like a sandwich result that shows that F H can also be lower bounded by V star up to some small value。

Then F H must be close to V star， you know， up to that small value， right。

 So what I want to show in addition is F H greater than equal to V star minus something。

And if this something is small， then， then F H is essentially sandwiched between V star and V star minus something。

 then this something will be the a bound on the distance between F H and V star。Okay。

 does that make sense？Okay， cool。 So， so how do we do that， right， So， and in order to show that。

While we start with Fh， which I said this is equal to v star of H。Right？And。This is。V star H。

 which is greater than or equal to。 We call， okay， we will now use this in quality。 V pi star of H。

Okay so actually so again this in quality keeps the objective function， but change the behavior。

 So here to obtain optimality because you have finite horizon objective in general。

 you need a time dependent policy， but here I'm saying okay。

 forget about that policy use the you know stationing policy that is optimal for the infinite horizon objective。

😡，Okay， what is that， Well， we is write it down。 This is the expectation under our pi star。

Which is mapping from states to， sumation t equals 1 to H。

 gamma t minus1 R T when I'm starting from S。Right， so this is a definition。Okay。

 now let's keep going。 So this is equal to。 So I'm gonna change it from here。

 So now I'm gonna write in this way。 Okay， so I'm writing this as first infinity。And as subtract。

Hi star t equals H plus 1， I guess gamma t -1。 So still infinity R T S1 S。Right， because the， the。

 the part of that is like after T H -1 will actually cancel out。 So when you take the difference。

 like really like it， it's equal to just only sum up the rewards for the first H time steps。😊，Okay。

 so what is the first ser？😡，Right， V star infinity or simply V star of S， right， So actually。

 because I， I wrote I S here。 So all of these should have an S。 Okay， so the first term， well。

 this is just our familiar definition of V star。V star of S。Okay。Now， remember。

 our goal here is to show that FHS is greater than not equal to V star v subtract something small。

 So we want to show that this thing is small。😡，Okay， why is it small。Well。

 because if you look at the discounting number here。

 the very first discount factor is evaluated when t equals H plus 1。

 So the very first discount factor is already gone to the H。So when H is actually big。

 all your rewards will be very， very heavily discounted。😡，RightSo in another words。

 I can write this term as a。Gamma to the H， expectation pi star。T H is1 to infinity gamma T -1。

 sorry， T minus H。Plus 1， I guess， or -1。 I don't know。慢点那慢点说，你OK。😡，RRT， S1 S。Okay， so essentially。

 I extract out that common discount discount factor， right。

 And then if you look at how discounting works inside for the very first T E T equals H plus1。

 H plus1 minus H -1。 So you have like discount starting from one。Right， so therefore。

 like once written this way， the， the discounting scheme inside the expectation is actually the discounting scheme that we're familiar with。

Right？And this part， we know that it is deterministically upper bounded by R max over woman as gamma。

Right， because history word is bounded。And because there's a negative sign。

Because there's a negative sign。 So if this is upper bound by this。

 then the whole thing is greater than equal to v star of S minus。R max， sorry， one over gamma。

 but this is term。 but there is also the gamma to the H term。Okay， so then we show that F H。

 this function is send。 So the， the final conclusion is that FH S is sandwiched between V V star。

Of S， and。V star of s minus gamma to the H。R max1 minus gamma。 So therefore。

 the distance between V H and FH and V star is infinite norm is upper bounded by this term。Okay。

 now if you look at this term， this is exactly the rate that you will get by the contraction argument。

Because contraction tells you that the。The distance between this guy and this guy。

 they shrink exponentially with the multiplicative ratio being gamma。 So however。

 many like iterations you get， like when you do H iterations。

 like the upper bound between their distance is proportional to gamma to the H times a factor。

 That is the initial distance。😊，O。So you， you see like once， once you accept this particular。

 this particular like claim， the， the rest of it is just like manipulating rewards， right。

 We're not even like using we didn't even bring up Bma equation。And in fact。

 like one of the homework questions， like it's of similar flavor。

 like you work on like a problem of similar flavor in the homework that you don't need to invoke bomb equation like you can。

 but typically you actually get worse results when you actually work through the B equation and the other bounds we introduce in these lectures Sore really this is telling you is that this is a different way of understanding value duration right。

 So essentially what value duration does is that it's actually trying to solve these finite horizon approximations to the infinite horizon discounted objective。

😊，So I'm first solving v star H for h equals 0， then based on the result of h equals 0 I solve for V star 1。

 then I solve for V star 2， V star 3， and so on so forth。😡，Right， and basically。

 the idea is that when the H is large enough。Then the optimal value you obtain for that finite horizon objective is not going to be too different from the optimal value for the infinite horizon objective。

 because the only difference are these tell rewards。That actually are heavily discounted。

Because the difference happened in the far future where all the rewards are heavily discounted by gamma to the age。

And some of all the infinite future rewards， like in total， they're still bounded。

 So so the difference can be largely ignored。 Okay， question。Oh， that's a great question。 So the。

 the proof， if you initialize it like differently， you will need a site different proof。 So， and。

 and you need to generalize the proof a little bit， right， Okay。

 so and I'll tell you like briefly how you do that。

 So what you do is I see here we defined V pi H in this way， right。

 only the first H steps of rewards。😊，If you were to initialize it differently。

 what you should do is that you should define it as this。😡，Here you plus the term gamma to the H F0。

 and in fact， like this is fully compatible with our current proof because our current proof is just a special case when F 0 is equal to 0。

😊，Right so if you is 0， then you can ignore。 But in general， whatever f0 you initialize over here。

 you just like plug that in。 So this is kind of like a terminal reward where like if you've taken like AI like more classical classic AI course that talks about search and planning。

 you know these kind of like search heuristic search methods that let's say you're searching like very large like exponentially branching tree。

 let's say you're doing like search like like chess or something you search over like a very shallow part of a tree。

 you can't go any further because it's out of your computational budget。

 What what you do is that at the end knows youre plugging some heuristic heuristic evaluation function to kind have an estimate or have a guess of like what the future value looks like this F0 is essentially like you the first few rewards are real and at the end youre plugging some like heuristic evaluation function that that you come up heuristically。

😊，But then all you need to do is to just adapt the proof based on this new measure。😡，Sorry。

 but based on this new definition of the finite horizon objective。

And it'll be actually an interesting exercise if you want to work it out afterwards。Okay。

And and one thing is that here， for example， we rely on the non negativity of the non negativity of the reward function to。

 to to to to get this step， right， So this step will be gone。 And and if you look at it。

 like there's something weird， right？ So eventually we get the sandwich result where on one side。

 theres directly F H bounded by V star。 So the kind of like lower bound and the upper bound the the proofs are asymmetric。

😊，Right， so most of our proofs are like are， are focusing on this part where this part is straightforward coming from the non negativity of the reward function。

 right， But as you remember， we said that the non negativity of rewards is an assumption without loss of generality that that assumption itself shouldn't be consequential。

😊，Okay， so in fact， like if you take them at a more general setting where your F 0 is something else。

 you actually see that on both hand sides， you need to do something similar to what we did for this part。

So actually， like this is merely like， you know， we have a simplified upper bound only because we assume the non negative reward。

 which gives you some like a little bit of convenience。

 But there is nothing like consequential about it。Okay。And another thing is that when you look at。

This， this like this process that I lay out here is precisely how you would solve for like optimal value function and do dynamic programming if you were to face a finite horizon problem。

😡，Right， suppose I have a finite horizon problem that says I only want to optimize just the literally summ of R T from T equals 1 to H。

Well what you do Well you do exactly this thing over here， right， you start from  zero。

 which is like what's the ultimate value function when h equals0。

 then you use that and then you figure out what is the ultimate value function when H equals one and you keep doing and you do exactly this thing except that gamma gamma will disappear。

😡，Right， and just keep doing this。 So this is literally like backward induction。

 You solve the equation like， you know， you， you solve the optimal value function，1。

1 layer at a time。Okay， and based on that argument。 So here's a quick question。

 If you have a finite horizon problem and you apply this value or dynamic programming algorithm。

 how many durations does does it take to converge。This is actually a trivial question。So。No。

 that that's precisely the answer。 I'm not looking for。 So。 yeah。

 So when we have the in our setting of infinite horizon discounted objective。

 we never converge exactly， right， we only like getting better and better and better approximations as we increase the number of time steps。

 right， So like like if I want apsilon epsilon close。 Basically。

 I need to set this guy to be epsilon and figure out what is the what is the value of H。

 Well turns out that value of H is roughly speaking log1 over epsilon over one minus something like that。

😊，Okay。So no， no， no， this is， this is not right。 So for， for this to be epsilon。

 we need we need H to be， which is the number of iterations to be this large。I'm asking like。

 if you actually have a finite horizon problem where like you literally want to optimize for this guy。

 Okay， there's no discount factor and you only account for each step of reward and you round the procedure that is you know。

 that is that is like literally written over here。 you start with0。 and then the first step rewards。

 then two step reward with gamma equals one and so on and so forth。

 like how many iterations do you need to do。Literally H， right， because there's only H steps。

 You start from the end one step at a time。 when you reach H， it ends right， So after H steps。

 like you get precisely the value function with no0 was sorry， no error whatsoever。

 You get a precise answer。😡，Okay， so let me finish this。 And， and this is another place where you。

 if you remember， when I introduced this。Like connection between finite horizon and infinite horizon objective。

 I said that wonderful woman as gamma plays the role of effective horizon。😊，Right。

 so we first established this connection by saying， oh。

 if you look at the boundness of the total the of the total value， you know， in one case。

 is R max over1 is gamma。 in the other case is R max times H。 So there's a match over there。😊。

But you can also see it over here， which is， you know to get absolutepsilon like to get an accurate result in the infinitefin horizon setting。

 you need the number of steps to be proportional to one of a one's gamma。

 whereas in the actual finite horizon setting， you get the precise result when just you just use like literally like H iterations。

😡，Okay， so， and。And this is also， you know， as I said。

 like one of the reasons I like this proof is that it really like uses none of the fancy mathematical concepts like contraction or whatever。

 like you know， the once you once you like accept this， which is like pretty intuitive。

 all the rest is just elementary math。Okay， there was a question。也。Yeah， yeah， like。

 if you want Abilom there there。Oh， yeah， yeah。 that's a good question。 So， so basically， the。

 the thing you solve for is age， right， like all of these are just constant。So， I mean， really。

 like it it shouldn't， I mean， basically just asking roughly speak， like ignore that constant part。

 Just ask yourself if you want gamma at the H to be like absilom level， what is the value of H。 Well。

 it turns out that it is actually log。I think one over Ragamma， one over Epsil， something like that。

Right， and and you can actually go back and work out yourself。

 and I think it's included in a nose that when gamma is very close to one。

 like this one is can be relaxed to this expression， which is a little bit more you know， how to say。

 a little bit more like clean。😊，Okay， and in fact， like one of the things you can do is that you can say。

 okay， what is gamma to the H when H is this expression， right， So this is。呃，干嘛区的。

1 minus gamma log1 over epsil， right， so you have that。I can write it as1 minus1 minus gamma。Right。

 so this is just gamma。Right， to the one of women is gamma to the log。Whyre of Abil。Right。Okay。

 so now I ask you， when Gamma is like really close to one， what is， what is this guy。

What is this guy， Can someone tell me， what is this guy。So it's related to E， but it's not quite E。

 So you get E。 if this is a plus sign， right， E is one plus x where x is small， right。

 when gamma is close to1， y minus gamma， think of it as something small， like x going to 0。

 So if you have one plus x to the one over x， you get E。😊，But what is 1 minus x to the1 of x。

1 over E， right， So exactly， right， So you get one over E， which is e to the -1。

 So E to the minus log1 over epsilon。And in fact， I think what is this， the。

 the it's like this is probably like a less than or equal to。 if I remember correctly。 and。

 and then what is this， Well like。Like the negative sign， you can just push it inside and just get a。

嗯。呃。Abspsilon over here， so this is just Abpsilom。Okay。Now， theres the in quality over here。

 But the idea is that when gamma is like really close to one。

 this in quality is like tied up to first order approximation。Okay， but， but you're right， like。

 you know， like if you， if you solve for this straightforwardly。

 you will get this in this inequ qualityality over here， which is like not directly connected to。

 you know， like the horizon that we're talking about。 But if you do a little bit of manipulation。

 like it it'll become like quite clear。O。OK。Let's see if this one is。Okay， so。Now。

 so this is the like we， we gave two proofs to value。

 So we're like near the end of this particular topic。 there's one final comment， right。

 So what we have shown so far， right， what we show is that if we do like let's say switch back to the Q version。

 let's say is this and F K。😊，T FK -1。 Then we know that F K will goes to Q star at a particular rate。

Right and for the B star version， is to say。Now。Why did we want to compute for Q star？😡。

Does anyone remember why we said that we want to compute for Q star？😡。

You want to find the actual policy， right， You， you want the optimal behavior。

 You don't want this like value function。 This value function is like useless。 Eventually。

 you want to be able to take good actions to get high rewards。😡。

RightSo it turns out that there was actually a question that we didn't answer。

 So what we said is that if you actually get Q star， then you can gratify over rate， you get pi star。

 which is pi Q star remember this thing is with define S for any f that is a function versus the action pairs。

 pi of of S is just agon x over a F of S So for any function。

 real value function over the action pairs， F pi sub f is just a gridtified policy。

we know that if you give me exactly Q star， I gratifier a read and get a policy and that policy is guaranteed to be optimal for the NDP。

😡，However， what we established is a like conversionverence result， right。

 So unlike the final horizon case where you can get exactly the function and then you can get the offflow policy exactly in the even horizon case。

 like all I can guarantee is that my function will be get closer and closer and closer and closer and closer。

😊，To the Q star。 But because I have finite compute。😡，I must stop at some finite duration。

 So I will have some Fk， which is like reasonably closed。To Q star right and this epsilon。

 like again， a similar to before， like for whatever epsilon you need。

 you can just use our previous bound to figure out what is the number K you need over here。😡，Right。

 but still， like all the best you can get is to guarantee that first like you make have some non zero value epsilon。

You get a finite IK that you know you need that many iterations。

 but you can never guarantee that FK is exactly Q star。😡，Then here's the question。

 what do you do then， we need a good policy。😡，Okay， so what would you do， Think about it。

Just any random idea。好。No， no， no， I'm not asking for analysis。

 I'm literally asking what you would do like now you've computed FK， but I'm asking you， okay。

 please take actions。😡，You need to turn that into a policy。😡，What would you do？Right， right， exactly。

 right， Because， because， like we know that if you get Q star。

The greedy policy with respectted is optimal。😡，We now have a function that is not quite Q star。

 but extremely close。So the very natural gas is， so let me put it in this way。For any app。

Over R of S。If F satisfies this。😡，Which is like the kind of guarantee we can get for baderation。😡。

I would guess that pie of v is a good policy。😡，But is that guaranteed？Well， we didn't know。 Okay。

 so this is the question that you should be asking like in this in this course， right， So in。

 in some of the previous theory course you've taken。

 like maybe like everything is about like asynotic， like conversiongence and so on。

 But in this course， everything is gonna be finite。 You know， so now this is still computational。

 but we have finite compute。 later will we have a high finite data。

 There will be all kinds of errors。 Like nothing you get will be perfect。 Everything has an error。

Okay， and and you need to be able to think about what happens when some error is present。

So here you have this problem。 All you can get is some F that is close to Q star。

 The most straightforward thing you do is still to gratify over it。😡。

Pretending that this F is as if it were Q star。😡，But now you know that it's not exactly a Q star。

 so probably this thing is not exactly optimal， but your hope is that it's approximately optimal where the optimal gap should be able to control it by Epsil。

😡，Okay， so the hope is to bound。Wang。Want to bond。So here's the thing。

 V star minus v pi F infinite norm。Okay， so think about this。

 So so things are getting a little bit twisty over here， right。

 So why do we care about this particular quantity， right？ So remember。

 V star is the optimalim value you can get in this environment。And what is V pi F。

 pi F is whatever policy you extract from here。 We don't know how good it is， we hope it's good。😡。

Right， so therefore we。We do V pi F， which is like， okay。

 tell me how good this policy is in this MDP， I'm asking for the policy specific value function for this particular policy。

😡，Now， we know that in general， it's going to be suboptimal。

 so it's not going to be as good as V star。😡，But then there's a difference。😡。

And I want you to know how large is the difference and hopefully small controlled by Epsilom。Okay。

 does that make sense？😡，Okay， so。It turns out that there' is a very simple bound。

 We will not give the proof over here because it will be a direct corollary to something that will prove later。

 So it turns out that this is provided by。嗯。Two apson y minus gamma。Okay。

 so this tells you that if you get epsilon to be small enough。

 you pay an extra factor and you can guarantee that your pi sub F is still near optimal。😡。

So this tells you that this procedure of gratify over a value function is kind of a， you know。

 it's not a super fragile like process。 It has some degree of robustness that that if like ideally you want to gratify over a Q star。

 but if the function you're gratifying over is not exactly Q star and you make a small error。

 that small error will be amplified， but it won't be a case where you make a tiny bit of error and you suddenly lose all of everything。

 that's not going to happen。😡，Okay。So we'll give the proof later。 But for now。

 I want to actually take this opportunity to just emphasize something that is， you know。

 mathematically not very sophisticated， but conceptually can be quite misleading misleading。

 right So if you look at this particular lemma over here。😊，There are two kinds。

 and let's focus on there are few different objects over here， right， So we have the F。😡。

Which is an arbitrary function。RightNow we have Q star， V star。

 which is like the optimal value function and the problem。😡，We also have pi of F。

 which is a policy extracted from some F。😡，And then we plug that into Vpi to get the policy specific value function for the sandDP。

😡，So what I want to really emphasize is that， you really want to distinguish you know。

 before we talk about policies， when we just talk about， you know， broadly speaking。

 like value function or things that look like value functions， there are two type of。

If I'm not like value function， like defining a more broad sense， one is like， you know。

 things like V star Q star。 So these are value functions that are actually defined in the NP。

 So these functions can be realized by doing some behavior in the NP。

 You look at what's the value function you get in that NP。

 So these value functions are like meaningful in the particular NP。Okay， on the other hand。

 you have all like these functions like F。😡，So here this is for any F that is a real value function over the action pair。

 So this F is arbitrary。Okay， so this f can be like meaningless for this NDP and may not be realized by any policy。

😡，For example， let's say my reward is bounded between 0 and 1 in this MP。

 So I know my value function is bounded between 0 and one over one is gamma。 right。

 But then like when I say， okay， I can， like according to like， you know。

 this scheme like implied here。 I can take an arbitrary function grafi over it and take action according to it。

 But the function F， I can take maybe it has negative value。😊。

Maybe it has value that is above the upper bound of the possible total rewards in this MDP。😡。

It doesn't matter， I can stealeww graittify of it and get a valid policy。Does that make sense？

So in this case， like F is arbitrary and not really bound to the MDP in any fashion。😡，Okay。

 but heres the， here's the thing。 But once you extract a policy from it。

 you get pi of F and they say， okay， I'm running in this MP。

 now you get a valid value function in this MP。Okay， so this VPF is now like confined in the NDP。😡。

Okay， so I think like one mistake， conceptual mistake that I often see people who first run into this often you know run into is that in this particular setting where like。

 say you get an arbitrary function F that is the approximation of  Q star。

 you gratify operator to get a policy。 then you evaluate the policy in the particular NDP。

 like you know， finally， you get v pi of F。many people can't really distinguish between what is the difference between F and V pi F。

😡，Okay， but these things are different。😡，And maybe let me give you another example。

 So suppose you have a NP where all the rewards are0。O， so what's the value function in this MP。

0 like， and it's regardless of your behavior， right。

 And it's regardless of whether you talk about V star or Q star， right。

 as long as your definition value function is the summation of discounted reward under some behavior。

 like that value function must be 0 in this MDP。😡，Okay， so across the symbol over here。

 which quantities must be zero in that MDDP？😡，Q star， yes。V star， yes。

And v pi of F right so anything V star， Q star v pi F。

 anything that is like you know V of some behavior that is defining this NDP must be just zero for this problem。

😡，But the app over here can be anything。😡，So F can be like infinity or whatever。

 you can have negative value， it can be 10，0， whatever。😡，Right， it's just an arbitrary function。

 And you can still take actions greatly according to this function。 It's just like whatever you do。

 you still get 0 when you actually run your policy in the NP。Okay， so that's like very important。

 but， you know， mathematically not sophisticated at all。

 but very important conceptual distinction that you need to keep in mind， like roughly speaking。

 there are two kind of functions。 One is functions that are generally not bound to the NP and something arbitrary。

 but the other kind of function are really like the valid value functions that live inside this MP。

Question。Right。Right， right， right。no， no there's no， there's no point of calculating the bound。

 Like this， like bounds like this are not for you to calculate。 This bound is an analysis。

 It's guarantee iss an guarantee for what happens you know， when you have an algorithm。 and。

 and I just tell you， like， like， give you a guarantee of how good your final policy is like。

 you know， a lot of the theoretical guarantees we， we， we， we prove in a state。

 they're not supposed to appear in your algorithm。So it's not that you， you calculate it。 Okay。

 so I'll tell you like， where you apply this bond， Right， So one particular example is where。

Let's say your wrong valuation， right， Your wrong valuation， you get these you get these functions。

 right， And for large enough K， you stop。 Okay， So now you have FK。

 But you know that FK is not Q star。😊，But you still have to get a policy out of it or just gratify over that FK。

 right？😡，Now I want to ask you to say， can you give me a guarantee for how good that FK is？😡。

What would you do Well you connect the analysis we've done so far together right the analysis like this or the previous contraction based analysis tells you that this is the V star version。

 but we're talking about the Q star version， but fK is close to Q star。

RightSo therefore the previous analysis well establish this condition for you for F equals FK。

With a particular value of epsilon， that is a function of how many durationerations you do。😡。

Well you plugging over here， so this is the final policy you output。😡。

Then this quantity gives you a guarantee for how good that final policy is。😡，Does that make sense？

Now， in that example I just gave， so sometimes there's this。Like I just said。

 as if there's a binary notion of there functions that are well definedfin in this NDP versus functions that do not。

 But in that particular example， there is actually some gray area because right because if you look at this。

 like our alternative proof tells you that these functions are not actually not arbitrary。

 theyre actually still like in some sense defined this NDP。

 but you just have to use a nonconventional objective function to define them。

 So that's that's a different story。 but but still like having this most of the time have this clear distinction between you know value function like functions that are bound to the MP realized as the value function for some policy for the NDP versus those are not and can be arbitrary is very。

 very helpful for this stage。Okay。Okay， any questions so far？reality we don't know。Yeah。

 we don't know。 So， so as I said， these are guarantees。 It's not something you calculate。

 you can tell close Right， right， I can tell you how your。

 the policy like extracted greatly from that function is This is exactly what what is bound。

 the other thing that is， you need to notice is that， you know。

 when we say something like X infinite norm。😊，This is max over x of I over all coordinates I。

 absolute value。Right， so we actually take two things。

 One is to take absolute value and then take maximum coordinates。Okay。嗯。Now。

 I claim that between these two， so I have this f minus  Q star infinitefin norm and have v star minus v pi F infinite norm。

😡，So in like， like each of them， I'm actually doing like these two things。

 which is take the function inside， take the absolute value for each element。

 and then take the max over the coordinates， which is like states or state action pairs。😊。

So here's the claim。 In one of the occasions， the absolute value is not actually doing anything。为什么？

😡，In the second one， right， because in the second one。😡。

V pi F is just some value function in this NDP， right。

 The value function for some behavior in the NDP， like by definition， V star。

 no other behavior can exceed the performance of the optimal policy。😡，So therefore。

 V star is always element wise greater than or equal to V pi F。😡，Right， so therefore。

 when we take this infinite norm， really， we're just taking a max。

 The absolute value is not doing anything because all elements are non negative。However。

 in the first like infinite norm， because F is arbitrary， so F can be above  Q star。

 it can be lower than the  Q star。 So when we say， oh， we want an F to be really close to Q star。

 really we need like an infinite norm that is like first take absolute value， then take max。😡，I mean。

 this is also related to my comment that you， one of them is actually a value function coning the NP。

 so it cannot exceed V star， but the other is just an arbitrary function question。😡。

RSSAF is also RSA。Not reverse。 like F， think of F as like arbitrary scoring function。 right。

 So for like the definition is literally over here。Right， for every S。

 you look at how F evaluates on the state for different actions and pick the action that maximizes the score。

 So F is just an arbitrary scoring function。小 here。

But but F is a function over that map states to action sorry。

 that map state action pairs to real values。😡，What's the question？Right。

And Q star is also like think of Q star also as a scoring function， right。

 So you have two scoring functions。 But when you compare their difference。

 you're not thinking about how you take actions based on them yet。

 You're simply just comparing those two scoring functions。😡，And if they're close， then you say， okay。

 now if you take actions according to these scoring functions， what's going to happen？😡，Right。

Then you get a stay value function， which is like dimension is like over is Rs。F for what？F，FK。

 So so this， okay， so I want to first say that this particular lemma， if you look at how it's stated。

 is completely general。 It applies to arbitrary F。 It's just that within the context of evaluation we've been talking about the way we're gonna apply this Lamma is to let F equals like the FK that we've seen before。

 But but it's gonna be the FK we' seen in the last lecture because that's for the Q star version for the V star version。

 It doesn't make sense。 You， You can't plug in the V star version of F K over here。

Does that make sense？Right， you're right， that's Qstar。YouYour， yeah， yeah， for FK the， the。

 the based on this alternative proof today。Like you， you can。

 you can extend the claim over here to the， to the。

 to the algorithm we announced on like last week for the Q function version。

 it's basically saying like you， you look ahead for H reward。

 and then like you figure out non stationary policy。 that is like， you know。

 like what you need to do。 But， but you only execute the policy for the first step。

If you think of if， if that makes sense， like， if you want to translate that over here。

 it's a little bit， it's a little bit。It's a little bit tricky， yeah。

But I think that's what you're referring to， right？Like， for example， if h equals one。

 if you only do wind duration， then itll be like you will be like taking actions just to maximize the immediate reward。

😡，Right，But then you evaluate it in the infinite horizon discounted objective where say， oh。

 you should， I'm gonna evaluate at how good you are in terms of like collecting like infinite menu rewards。

 So you will be pretty subopmal because you are very short sighted。That was the question。そそり。

Can we repeat。Like you can。 but like the first difficulty you need need you run into is that if you have if you have like even you have V star。

 you can't directly get pi star， right， But what you can do is that you can first convert V star to Q star。

 and then get the pi star。 but similarly， if you have an F that is close to V star。

 The very first thing you can do is to pretend that your F is v star。

 use the same procedure to convert it to the approximation of Q star。Okay， then plug in over here。

 And that analysis is very straightforward because I believe the conversion between V star and  Q star will preserve infinite norm。

 So whatever L in the norm you have between F and V star after that conversion。

 you get an approximation of Q star and the the error will will be just no larger。

So then this result is directly applicable。😡，But that's a good question And again。

 like I think you ask the second second little exercise you can do after class， Great。

 like two extra questions for you to do after class。😊，Okay， any questions？Okay。

So this is a value iteration。Now， in the planning part。

 we're going to introduce three fundamental algorithms， and value erosion is only one of them。😡。

The second。The， the second algorithm is called policy era。Okay， so what is policy duration， Well。

 as the name suggests， when we talk about value duration， what we get is a sequence of。😊。

Value functions。 So here again， like value functions are defining a broad fashion。

 It's not those like valid value functions the NP， but it's a。

 it's a sequence of approximations to the value functions。 But sometimes I just， you know。

 I'm not that strict。 when I say the word value function I don't always mean， like， you know。

 valid value function。 I mean， like anything that is treated as like maybe approximations to value function。

 I also just call that that way。 Okay， so。😊，Yeah， precisely because I sometimes use the words like in this ambiguous manner。

 I wanted to say that， you know， you should really like carefully distinguish between those two。

 two kinds of， you know， functions。 Okay， but as then but as the， but as we have seen so far。

 N R L when you're doing planning， It's really like there's this important interplay between you know。

 value functions or approximations to them and policies。And as the name suggests。

 policy iteration is again an iterative algorithm， but instead of getting a sequence of value functions。

 you get a sequence of policies。😡，Okay and。And similarly， you initialize the policy arbitrary。

 whatever policy you start with。And you do the following for for any K。

So what you need to do is that given the previous policy， I just need to specify a procedure to。

Calculate the next policy。😡，If I can do that， then I have the algorithm and the algorithm we just keep doing that。

😡，Okay。So how do I do that， So I start with the so each it in policy duration is consists of two steps。

 One is called a policy evaluation。We all is very familiar with this。 So we， what we。

 what we do is to calculate。Pi Q pi K minus1， right。

 So pi K minus1 is the previous policy we end up with， right， So let's say K equals one。

 Then we just look at Q pi 0， which is our initial policy。

 And What we do is that we do policy evaluation。 We just to ask ourselves how good this policy is and calculates Q function。

😊，And to remind everybody， Q function for a policy is this function that says if you start with a state。

 the first action， please take whatever action I tell you to do。

 but afterwards you take the actions according to the policy on the superscript。😡。

And what is the expected return you get for that particular starting state action impaired？😡，Okay。

And then the second step is called policy improvement。So。

 so and heres the where you will see RL gets crazy about。Subscripts and superscripts。

 pi K is defined as pi Q pi K -1。 So this thing is just this guy， and you gr I read。😊，Okay。

 does that make sense， so let's walk through this carefully again。

 so in the previous iteration you get a policy。😡，You don't want to want to generate the next policy。

 What you do is that you first evaluate how good this policy is and calculate its Q function。😡，Now。

 this Q function is just some function， real value function over the action pairs。

 which we can always gratify。😡，So we're gratified。You get a。Okay。

So is the algorithm specification clear？😊，So。😊，By the way， you know。

 for those who have seen some like， for example， modern and actually practical algorithms in like say D。

 the algorithm we're talking about is the foundation and basis for the majority of algorithm you see out there。

 For example， like， you may have heard of the notion of Q learning。

 Well Q learning is actually just the learning version of value duration。😊。

And the policy es algorithm over here， up to some small variant。

 this can be viewed as the prototype of popular algorithm like policy gradient or actual critic algorithms。

😡，So for those of you know， like in actor critic， you have a critic which is evaluating how good your policy is。

 which is essentially like approximating the policy valuation step。 And you have an actor。

 which is basically your policy。 and you keep improve that policy in the gradient direction to make it better。

 which basically is like a variant of this policy improvement step。😊，Okay。

 so all we learn over here will later be generalized to those like learning algorithm that you see in practice。

😡，Okay， so first of all。😡，啊。So this algorithm， right， you just get a sequence of policies。

 So what what we can， what we can do the， the， the claim。

 So we also want some kind of convergence result。So呃。There's a weaker claim and a stronger one。

 So we， we' actually go go to the first day， the weaker claim first。So the weaker claim states that。

For。For any K。啊。So now we have like so previously we have those like functions right that are supposed to approximate Q star or v star。

 and we can say its' distance to Q star or V star， whatever it's supposed to converge to like gradually shrinks over as you get more and more iterations。

😡，Okay， now I want you to use your imagination and， and think about what makes sense here。 So now I。

 I don't get those functions。 I only get a sequence of policies。

What kind of guarantee makes sense to talk about these policies？😡。

What kind of guarantees that you think are meaningful to state about these policies？😡。

The Q value of what and what and what？Right， so so at least this is where you start， right。

 So so these policy themselves， like you can't say， like， for example， you can't compare them to say。

 the optimal policy directly。😡，Right， you can say， oh。

 my distance to the optimal policy is shrinking。 Well， that doesn't make any sense because。

 first of all， these policies are very like， you should think of them as these like very discrete objects that it doesn't make sense to measure distance。

 like maybe you can have some kind of like0，1 distance。

 but it just doesn't doesnt doesn't make any sense over here， secondly。

 even if you say there's a meaningful way to measure distance between pi star and pi K。

 Remember that in general， MP， the optimal policy of pi star is not unique。Right。

 so it's then like which， which five star do you measure against right？ So therefore， like you。

 you don't want to talk about the guarantee at the policy level。

 You still want to convert it to the value like space to talk about guarantees， right。

 And what do we talk about， we， we talk about how good your policy is when you evaluate that in the MP。

😡，And you want this guy to be basically as high as possible。😡，Makes sense。Okay。So。

So the weaker guarantee states that。This is。Greater than or equal to。The pagonous。Okay。

 so basically you have these sequence of policies for each one of them， you can just ask， oh。

 how good is this policy， Well， you get this value function， which tells you how good this policy is。

 what's the total return you get for this policy from different starting state。😡，Now。

 for the next duration， you get a new policy， you ask the same question。

 and you compare the performance of these two policies and you realize that this policy duration algorithm has a very nice property called monotome policy improvementmp。

 which is to say like your new policy is not going to be worse than old policy in any state。

 and in fact。嗯。actually， this is a called。啊。There's a name for this thing it's called a monotome。

Policy。Improvement。Okay， and furthermore， if Pi k is not。呃。Sorry， pi k minus-1 is not pi star yet。

 So here I write not equal to it as if pi star is a fixed object， but really like you know。

The correct way to write it is like pi starts。 it's a set of all possible optimal policies and Pi came on as way。

 just not one of them。 Okay， so as long as this is the case that there exists。

 at least some starting state， such as the improvement is strict。

That you actually never get stuck and not improving。 You actually keep improving。

 at least in some starting state until you hit the optimal policy。😡。

 so this is the monotone policy improvement。呃，Let me see。

So well have an actually stronger convergence result， but we'll say that later。 Now。

 for this particular result， a immediate。😊，An an immediate consequence is that policy iteration will actually converge in finite number of iterations。

OkayAnd the reason is because because of this monotem policy improvement property。

 you know that the sequence of policies you get， like each one of them is a。

 you know stationary mark of deterministic policy， first of all， and second。😡，You will never repeat。

😡，Okay， so you will never run into the same policy twice in the sequence。

 because every policy value function is always greater than or equal to the previous value functions and also。

Ha has a nonze difference in at least one state。Therefore you cannot like。

 but the number of total deterministic markov policies in the NVP is finite because it's just a to the power of S。

😡，Okay， although that's an exponential number， let's still finite。

 So policyeration will actually converge in finite number steps。

 though if you actually ask for exact convergence， the number of iterations may be exponential。Okay。

 but we' actually establish something much stronger later。 But this is the first。

 first consequence of mono term policy improvement。 And the other thing。

 I'll mention the other thing。 and then we'll just conclude today's lecture， The other thing is that。

 you know， just to give you some intuition for why this。😊，This。

This algorithm actually makes some sense。Well， the first thing you check in this algorithm is that if pi k minus-1 is pi star。

 what's going to happen？😡，Okay， so if pi k minus1 is pi star， what is Q pi k minus1？😡。

It's coupon star， but we have a more。It's Q star， right， So we have a particular symbol for it。

 So Q pi。-1 is Q star。 then pi k is just gratify over that。 What is this， What is pi Q star？Sa loud。

It's pi star right， if you have the Q star greater if I already give you pi star， so therefore。

 whenever you hit pi star， you will stay there forever。😡，This is a good thing。

 right because this is kind of like saying if you think of this whole thing as an operator。😡。

That backs one policy to another at the minimum as a sanity check。

 the minimumly like you need that pi star is a fixed point this particular of this operator。😡，Okay。

But then like if you want to say something more， which is like in evaluation。

 we say that eventually you will converge to it because your operator is a contraction and so on and so forth。

 you need more analysis that we will'll talk about later and as I just mentioned。

 you don't want to do the analysis in the policy space because that space is discrete there's no real value things over there。

 it's hard to analyze， you want to transfer things to the value function space and you analyze from there。

😡，Okay， so we'll continue from we'll continue this on Friday， okay。Just to get true。

What would this thing I mean， I think we use it It just talked about it。So FHS said， no， no， no。

 I didn't talk about it。 I want to talk about the version of this when you're doing value duration for V star。

So like there's an analogy of that for this but。You need to do a little bit of adaptation and figure it out。

 But， but I I think， so like I think you can write it this way， right， So， so we define like。

 so here what we establish is that for the state version， FH S is equal to this， right。

 which is the optimal for this guy。 So eventually it it it depends on this guy。 So for the Q version。

 all you need to do is just to also conditional a1 equals a。😊。

And then define the cube high H S A over here in this way。 And then say max overall high。

 you get the Q star。 Then F H is equal to this， this one。Yeah， I have a question。

