# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p10 P10 线性规划 -BV1YsZHBZEyM_p10-

Okay， let's start。So today， I think we're closing up the planning section。

 And as we're gonna introduce the very last fundamental algorithm for solving MP。

 like in a computational sense， when you have finance small stage basis。

 And this is a linear programming。 Okay， the。You know。

 I didn't say that LP is required as a prerequisite。 So I'm not gonna assume that you know LP。

 but and and we're not really gonna use this a lot later on。

 but still is something nice to introduce but just like a quick few words on what is LP right So LP is basically saying that you're doing optimization So optimization typically you have some decision variable say x。

 which is let's say in is objective you want to optimize And like and you can have linear objective that's say a transpose x or a is a constant and given vector right So you want to say either maximize or minimize doesn't really different than much because it just like you can just flip the sign of the vector A And I don't know。

 But if if I just write this way apparently the optimal value is infinite you can just find a direction X that is has negative dot product with a and just shoot that all the way to infinity。

 So typically like there。Constraints that says such that， something like what is it。

 you can have things of the form。 I don't remember what's the typical convention for their the vectors。

 Oh， I see， like this is probably C， right， C， because this can have the meaning of something like cost。

 right， So you have a vector dot product with X where you can have like something like A X less than B。

 okay。And again， and， and this is inality constraints。

 And maybe you can also have additional equality constraints。 I don't know， like。

Like D X equals0 equals。like。I'm running out of words like something like that。 Okay， so。

 so basically， you have some constraint that combinefin the space of what call we call feasible solutions into some space。

 And the characterization of the space is given by some linear inequality constraints and some linear equality constraints。

Okay， so the inequality constraints is like you're in the space。 And then we， we。

 we put a few like hyper planss and to like surround a polyto and say， oh。

 you can only choose X from this polyto。 right， So the typical like visualization is something like。

 let's say you're in R 2 and。Maybe you can say I give， I give a few like lines and say， oh。

 you can only choose an X in this space。Right， and then you have a C， which is something like， oh。

 I want to optimize the Do up between X and X。 And maybe like， you know， you， you just find， oh。

 like this， this is the point that optimizes it。Okay，And if you have equality constraints。

 that it essentially reduces the dimensionality of the feasible space and so on so forth。

You guys are just to give a like a super， super。Super， super， like quick。

Like definition of linear programming。 And we're not gonna tell you like know how to solve it。

 because this is like totally the topic of a different class。

 and suffices to say that it's an extremely well studied area。

 And there there's a plethora of like different methods for solving it in polynomial time whenever。

 typically whenever you have it depends the complexity depends on the number of decision variables。

 So which is the dimensionality of x here。 Well， essentially like each coordinate of x is a separate decision variable。

 right， And it also depends on the number of constraints， which is like， you know。

 like I'm writing this in quality constraints in matrix form。

 But really like each row of a or each element of B correspond to a separate constraint。Right。

 and so the number of constraints， like typically M。

 So you just have to guarantee that N plus M is not too large。

 Then there there are many things that can solve solve optimization programs to retain this form。

So what we're going to show today in the first half of the lecture is that one way to solve MDPs is to actually rewrite it in a linear program。

Okay， so once we do that， we can just throw that thing into whatever early LP solvers and the LP solvers will take care of the rest of the work。

if you want to understand how LP solver works， you need to take optimization class。Okay。

 and there's something very interesting as we and， And this is， you know， in many like intro courses。

😊，People typically only teach value duration and， and， and。And policy duration。

 because linear programming， like the formulation doesn't get used a lot in empirical R。 but。

 but now， but especially early on， but more recently， there are more and more， you know。

 new algorithms that that draw some degree of inspirations from it。Okay。So let's， let's start。

 So here， so I'm gonna just write down literally a program and claim that it is solved for the。

For the for the MP， right， So， and for those who know LP， typically in LP， you have the。

 of course sort of the primal form or the dual form。 If you don't know about it， doesn't matter。

 Like， you know， we'll talk about it later， but。Theres the the。

 the typically what's called a primal form of the LP is the following。Okay， so like， okay。

 so what it does is that is software P star。 Okay， so what I'm gonna do is I'm gonna write down a linear program where all the parameters like the vector C over there。

 like the the a matrix， the B matrix， all of those you can just obtain from the transition matrices and the reward function of the NP。

 So you can literally just compute them one by one。 and you write down a linear program。

 and you can just throw it to now P solve。 And what we're gonna do is to show that oh， actually。

 by some reasoning an argument showing that the solution offer solution to this linear program is is indeed B star。

😊，Okay， so here as goes follows。 So V。 so our decision variable is V。

 And then because like eventually we wont get V star。 So V is anything that is R S， right。

 Because V star is also a function in M apps state to reals or a real value vector in S dimension space。

😊，Or maybe I should write anyway。 that that's not too different。 Okay， so we have the 0 transpose V。

D0 is any vector that is required to be。呃。No negative or a strictly positive on or on all starting state。

 Okay， and as you， and we've used this notation before。 So it。

 it's not obvious to see in the primal form。 But when we turn into dual form。

 we' will see that the0 indeed plays the role of like some kind of initial state distribution。 But。

 but it's not gonna be obvious in in this form。So， but， but for， for the primal form。

 all you need D0 to be is just any vector that。That is positive everywhere。For example。

 you can just use all once。 or if you want to normalize it to be like， like， you know。

 like the scaling of this vector doesn't actually doesn't change the optimality optimal solution of the program。

 right， So typically， we always， we always normalize it to be a better distribution。 So you can。

 for example， just play a uniform distribution of the stay space。 It doesn't matter。Okay。

 but let's subtract to constraints。😊，Okay， so far， by the way， so far。

 you should already feel that something is wrong。Kt me why I said。Yeah， exactly， right。

 We should be maximizing the value。 But now I'm writing minimizing over like this V。

 which is supposedly gonna be V star when we， when we have the optimal solution。 exactly， right。

 So this feel wrong。😊，And this is the one of the most counterintuitive aspect of the LP formulation of NP。

 or Wi。Okay， such that。 So we needed some constraints。 Otherwise。

 we can just like boost the value V to infinity and well get， oh， sorry， negative infinity。

 So we get negative infinity value。 So the constraints is something that looks like beel equation。

 but something slightly different。TV， okay， so you want to minimize the value of V。

Subject to the constraint that we satisfied this thing that looks like the be my optimality equation。

 But you have this inequality version。Okay， so as I mentioned。

 like we need to show that the optimal solution to the Se linearar program is indeed the。

Is indeed the V star。 That's one task。But actually， after I write down this。

 you should already question one thing。 Is this a linear program。Who said no。Well， so。Okay。

 so all you need is this equation to be like like like I I could be something like， okay， So。

 so if this were T pi， then we're we， we're good， right。

 because cause this will be like if V is like x， this is x greater than equal to， you know。

 this is like R pi plus gamma P pi X， right， So you can just move this， the move term combine term。

 and you have a linear constraint。😊，Right， because then like。

 then something like I minus S gumma P pi X greater than R pi。 I can just flip the sign。

We have minus。So then this is a， this is B。Okay， so the claim is that if it were like T pie。

 it would be like a linear program like straightforward because you can as long as basically like one rule of thumb to check is that as long as the all the operations that happens within the within your like constraints is like linear or a find。

 then you're fine。But this is not a linear constraint， why？Right。

 like the the of the operator is not nonlinear。 So what， what。

 what what element of it makes makes it nonlinear。The max， right， So we said like many times。

 like when we have the Belman policy specific Belman operator。

 that is a linear operator or more precisely afin operator because it's a matrix multiplication plus a constant offset。

 And therefore， like Belman equation for policy evaluation。

 we can solve them by just solving linear system， right， matrix in inversion。

 But the Belman equation， we can solve it by matrix inversion precisely because it's nonlinear。

 So why do I tell you that this is a linear program。 right， So that's the other question that is。

 well， it turns out there's a way to slightly expand and transform this program that immediately becomes linear。

 So we need to answer these two questions。😊，1， y opt is V star and two， Y this is LP。O。So。

 let me actually answer the second question first。 Okay， so why this is L P。 Well。

 written as this form， this is not the A a linear program。 So we need。

 because the constraints are not linear。 So we need to do a little bit massage over here。

 So let's write down。 So how many But before that， tell me how many。

 how many decision variables are here。S， right， because we're solving for V， right。

 And V is a estimational vector。 So we have estimation variables。 How many constraints are here。Also。

 S， right， Because again， V greater like the， the vector form the constraint is V greater than something。

 So number of functions is just the dimensionality of this， which is S again。

 So let's write on each constraint separately。 So each constraint is for any S。😊。

V of S greater than equal to and what is the definition of TV。 Well。

 this is the stay value version of the optimal operator， which if you remember。

 which is max over a R of S A plus gamma and expectation S prime P of S A。V of Sp。Okay。Thats good。

Okay， so here's the magic。This is equivalent too。And'm going to just erase this。

Or maybe what's the best way to do it， Let me write it in a different color。Okay케이。

So the claim that this is equivalent to for any A， and then I remove the max operator。Okay。

 so previously I have one single nonlinear constraint。

 which is for any S V S is greater than max over a。😊，And the claim is that this is equivalent too。😡。

That each constraint I now expanded into number of actions， multiple constraints。

Where each constraint and I say V of S is greater than equal to。 Now， here for each action。

 I have a constraint。 So I don't need to this max anymore。 It's just like for every A。

 V S is greater than this。And then you can see like they are equivalent， right。

 because if left hand side is greater than equal to the than greater than or equal to the right hand side。

 like， you know， the max over different values a of the right hand side。

 then it's just the same as saying I'm greater than equal greater than or equal to each one of you guys。

😊，Correct。RightBut now once you do that。😡，The right hand side is linear。😡。

RightBecause the expectation operator， remembered， expectation is just what。

Expectation like what makes the expectation like linear。

How do you rewrite expectations so that it is obviously linear。YouYou can have some。

 but with the vectorized operation。Well， that's the matrix form here here you only have like one distribution。

 so this is a dot product。😡，Right， so you can have dark product V and P the the P dot given S N。

 right， And this transition probably is there no。 This is a fixed vector。 It's a constant vector。

 V is the unknown。 So the dark product is linear， right， plus a constant。

 So the right hand side is totally a P and V。 So left hand side you also have V。

 you get a linear cluster。Okay， so basically， like。

 what happens is that you need to blow up the number of constraints into into S times a。

 Then they this makes a perfect。 this makes a perfect linear program。

So you have S descriptionion variables， S times a constraints， okay。

 but for the purposes of analysis， for conciseness。

 we typically do like you know right in that way with the understanding that if you really need to solve it。

 you need to expand in this for first。Okay， does that make sense？

So then we need to answer the other question is like why the optimal is V star。

 which has something to do with， you know， we have to answer this question is like why we're minimizing over values instead of like maximizing over。

Okay， so here is the claim。😊，So for any V。😡，That is greater than TV。

 which means that for any feasible V。😡，We have that V is greater than equal to V star point1。Okay。

 and this is the reason why it's， it's you're minimizing because what it shows is that all possible feasible points are actually pointwise above or equal to V star。

Okay， so typically， when we're saying we're maximizing values， we're。

 we're implicitly thinking about all possible value functions that can actually be realized in the N B by taking different behaviors。

And among those like valid value functions， V star is the one that is pointwise highest。Right。

 but here is the other way around that for any of you that satisfied this inequality。

 what we have is that actually， the majority of them are actually all invalid。

 They're illegal value functions。 Like most of those value functions。

 most of those functions cannot be realized as a， you know。

 true value function by some policy in your MP。And the only element that is realizable is V star itself。

 And it， it is also easy to verify that V star is in the space， why。The star set is by what？

Right by equality sign rightV star equalsTV star。😡，Right。

Because it it you like greater than equal to is allowed。 So if it's， if makes things equal。

 then you're good。 So we know that V star is an element in the space。

 All other elements is always like above V star。 So therefore。

 your objective function needs to push things down。 You ask， like。

 what's the lowest possible value of V within this feasible space。😊，Okay。

 and once you asked for that。 and this is also why you need the， this vector to be non negative。

 sorry， Str positive on O M， because if it misses a a state。

 then you have no incentive to push down the value in that state。

 So you need to like create incentive to push down the value for all states， then you。

 you actually find V star。Okay， so therefore if we can prove this， we're done。Okay。So to prove it。

 we actually need a interesting。呃。呃。A property of the Bman Op operator。

 which also holds for the policy specific operator， which is called a。Moticity。Moenoticity。Of T。

 that is for any， let's say， V and。You have two arbitrary vectors。

 V and V prime that satisfies V is element wise above V prime V prime。

Then you have TV is also element wise greater than TV prime。Okay。

 so this should be pretty obvious from the definition of the。The， the the operator， right。

 So plus gamma expectation as prime。P of S V of S prime。Right，Because like what it。

 what it says is that， well， if you replace V with something larger。

This whole thing cannot be smaller。Which is obvious， right。

 because the expectation preserves the order。Right， and then you have vma。 This is positive。

 It preserves the order。 You add a constant， doesn't change the order at all。

 Then you have a bunch of things that each of them gets potentially larger When you take the max。

 max operator also preserves the order。 That's it。Makes sense。Okay， so once we have that。😡。

We can do something interesting。So here。We，If we want to apply this property。

 we need to find two vectors that satisfy this。Okay。Like in our condition。

 we want to prove this based on this， right， So the left。

 the left side is like the conditions we start with。 The right side is the result we have。 Where。

 Where can we find like two vectors where one is above the other。喂。Yeah， the constrain。

 So who plays the role of V and who plays the role of V prime over here。76。Well， essentially。

 that's what's happening。 But， but I'm just asking you to literally read off from the， from， from。

 from the， from the blackboard。So basically v is v and v prime is。😡，TV， right， because this is your。

 this is your the only condition you have。Right， and it literally fits this form of V some vector is greater than equal to some other vector。

 So let's apply to it， right so。嗯。So think of this as a little lemma or tool you can use。

So what what this means is is that。Because any feasible V。

 we're talking about any feasible V that satisfy this， this means。TV is greater than equal to T TVV。

Right。Okay， so now。These two are just the same thing， right， So we chain them together。

So what that gives， what that gives is that V is greater than T TVV。

 I'm just gonna write it like T like square V。 Like this is not square。

 This is means this is a shorthand meaning that we apply the operator twice。Okay。

 what do we do there？What can you do here？是是是。Or maybe you can just repeat this wholesing， right。

 You just repeat the thing again because now you have another two vectors where one is above the other。

 right？ So therefore， you get TV is greater than equal to。T cube v。Okay。

 and then TV is also dominated by V。 So you further get V is greater than T3 V。Okay， dot dot dot。

 So this means that V is greater than equal to T and V for any n。😊，Okay。

 we want to prove that V is above the star。😡，There's just only one step left。 what is it？

How can I get V star out of this， Like here， everything you see is just V and T。

 Like you only have these two symbols。 How do you get V star out of this。😡，Someone。Limit。

precisely how do you get it？😡，Set n to infinity， right， because t infinity。

 when you start with an arbitrary vector V， applying the Bman automatic operator infinitefin number times。

 what do you get。😡，You got to be star。 That's literally value duration。 right。

 You're not actually running the value duration in the algorithm。

 but in the analysis is conceptually as if the analysis like conceptually runs the value algorithm here。

Right， and if you want to be formal， you need to like。

 argue that limit still preserve the order of things， right， So if you have like。

 you have a sequence where the， the order， you know， the order holds particular order， like。

 like inequality host for every single element， we know that when you take the limit。

 the order still holds。Right， so so I'm going to just write it。

So V is greater than equal go to infinity v， which is V star。在这。Okay。So this is the primal form。😡。

Now， the primal form itself is not really very informative。

But what's very interesting is that if you' are familiar with linear programming。

 you would know that every linear program has a dual form。😊，Okay。

 which is related to concept like shadow price and so on so forth。

 I'm not gonna really explain all of that。 As I said， this is totally a topic of different class。

 But the idea is that basically， the idea is that for linear program， there is a way to。

Translate into a seemingly completely different linear program。 But somehow their solutions are。

 you know， equivalent。 Or if you solve one， you know， the answer of the other。

 like they're in some sense， equivalent。 And during translation。

 what happens is that like each constraints you have here。

 what become a decision variable in the dual form and each decision variable you have here。

 what become a constraint in the dual form。 So the， the。

 the row of constraints and decision variables are gonna gonna like， you know， switch rows。Okay。

 and because as I said like a couple of times， we're not gonna tell you anything about linear program。

 all I'm gonna do is to take this LP， you know， which may which is this with the constraints expanded the form。

 and just mechanistically apply the textbook operations of how to induce a dual program from the from the a primal form and just write down the resulting linear program for you。

 Okay， and what will see， which is very interesting is that a dual program has very interesting interpretations and is much more insight for than the primal form you know。

 and and as we'll see， okay， so we'll just give you the result of the do form。😊，The dual form。

 once you apply that transformation is the following。You have max over ds times a。

D is greater than 0。 D transpose R。 So R is the reward vector， the reward function。

 which we view as an as a dimensional vector。So this is due a linear objective because D is the different variable and we're maximizing the do product between D and R。

😊，Okay， so r is the and R is a known vector。Okay， and with like， so here， like we're actually just。

 this should have been a constraint。 But， you know。

 these now negative constraints are typically just subsumed in the sub of of Max。

And this is also what you get in linear program， which is when。I think if I remember correctly。

 like whenever you get inequality constraints， then you get like these like non negative dis variables in in its2 form。

Okay， and then the constraints。Such that。So here， as I said。

 like previously we have S decision variables， S times a constraints， right。

 So here I have S times a decision variables。 How many constraints should I get？

How many constraints do I expect to get？S， right， because I said like。

 like the number of constraints and number of different variables are gonna like switch in in between primo and dual。

Okay， so the。The constraints is the following from summation over a， D of S A S。 So I I。

 I use this notation to represent a S dimensional vector where for each S its value is D of S A。

 but use sum over all a。Okay， so， so， so you have this。Equals。

Gmma P transpose D plus 1 minus gamma this0。Okay。Now。What I'm going to do is to just。

 I'm not going give you a， you know， strict proof of anything。

 but to give you some insights of how to interpret this。

 Can someone make a guess of what the meaning of D is here。You said as you said it。

 Can you say it loud。It's the occupancy， right， It's actually a state action occupancy。

 So if you remember， we have this V pi of S is that can actually be written as one of a woman's gamma expectation S the pi of R pi of S。

😊，Right， so it's like once you know the discarded occupancy， the。The value function， actually。

 like it the discounted occupancy is starting from some some starting state。 right。

 once you know the discounted occupancy is starting from some starting state， the。

 the value function， the value from this state is just the discounted occupancy top product with the reward function up to some normalization vector。

😊，Okay。So this is exactly over here。 And and so the logic over here is actually more intuitive than the primal form。

 right， So here， essentially if you think about it， if D is actually a discounted occupancy。

 then D dot R is literally the value they expected to return you would obtain。😊，Right。

 and among all possible。 So essentially what this dual form tells you is that among all possible discounted occupancy you can create in this MP by using different policies。

 each of them gives you a the discounted o D。 and among all these value occupancies。

 I choose the one that has the largest thought product with the reward function R。

 which is going to give me the highest expected return。Okay， does that make sense？And so therefore。

 like the key claim to establish here is that this constraint。😡，I'm going to write down the claim。

Any feasible。D， so feasible means that it satisfies the constraint over here。😡。

Any feasible D is equal to d pi for sum pi。That's the claim。 And if you remember D pi， you know。

 when we write D pi S， it means that the discounted occupancy induced from that particular initial state。

 But when we don't write S， it's typically because we have a predefined initial state distribution。

 And we're always defining occupancy with respect to that initial state distribution。

 And what distribution plays the role of initial state distribution here。 Can guess。D zero。

 of course， like it's over here。So it is like a D pi is defined with respect to the0 as the initial distribution。

Okay， so this is the key claim。 Once you have this claim。

 the fact that this is the right program to solve should be obvious。😡，O。Now， how do I show this。

 Well， I'm not gonna， as I said， I'm not giving give you the fool proof。

 I'm only gonna gonna do one way is that。呃呃。Prove。Partly， only a partly proof。

 I'm going to show you that any D pi。Satisfy is feasible。Okay。So。

 so this is missing in the other direction， which shows that only like there。

 there no there's no D pie that there's no feasible D that that cannot be realized by some D pi。

 I'm not gonna show you that part， although I'm gonna tell you a little bit about if I have an arbitrary D。

 how do I， you know， realize this D by some policy， like later on。But for now。

 I'm just going to show you that if I have some D pie， why it always satisfies this costtrain。Okay。

 so here's the a。😊，嗯。So if you remember what is D pi。 So D can be written in this form， D pi。 so。

 so here， D P is a distribution over state action pairs。 right。

 So this is a discounted occupancy for you know， we， we have the state version。

 We have the state action pair version there are similar。 It's just like slightly different。

 we can there's a， we can use a notation to write it。I'm gonna。

 I guess I'm gonna use the zero index here。 So gama to the T。

 I I don't have T minus-1 over here because I'm starting from T equals 0。

 Sometimes I think I probably should switch into switch to0 index like all everywhere。

 but I was just being too lazy to do that。 Okay， so I can write D T pi。 Okay， where。😊，D7 pi of。

S A is equal to expectation。When you have policy pi。呃。呃， what is itST equals SAT equalsA。

Given that the initial state at 0 is drawn from this zero。

So if you remember that this Sc mis is basically asking what's the marginal distribution for states or over state action pairs at each time step。

 you get those marginal distributions and just sum them up with this。Right， oh， I problem missing a。

Normalization factor here。 And we add a normalization factor so that this is a well defined distribution。

Okay。Sounds good。So I'm going to do this like pictorially Okay。

 so let's just write this as a picture， So this is how typically I think about it。😡。

So I think about it as。Why can I just write a rectangle properly。Chi。W。Com on。O， ok。Okay， so。

 so I think of it as like a stack of like distributions。 So you have d 0 pi， which is， by the way。

 okay， and you have D 1 pi。 You have a D2 pi and so on and so forth。Okay。

 and the three pi of S A S a。And El， okay， so so。What we're gonna do is that we're gonna start on the right hand side and show that is the。

It it the is the same as as the left。Okay。So， and， and you have discount factor，1， gamma。

 gamma square gamma cube and so on so forth。 So， so basically。

 the discount occupancy D P is just like adding all of these together with these coefficients up to the normalization factor。

 right。😊，Okay， so。So look at the equation over there， the constraint， like which。

 let's start from the right hand side。 Where does the D。

 this discounted like this decision variable D。 And here we're looking at the case where D equals D pi for some。

 for some pi。 Where does D appear。Where does disappear on the right hand side。

This be shouldt be like a harder question。I'm asking a trivial question。Com on。

I'm asking a literally trivial question。 Looking， look at this equation on the right hand side。

 where does D appear。The first term， right， gamma P pie D， right， in particular。

 you have this P transpo P transpose E term， right， So what is P transpose。Right。

 so P is you have P transpose。 So usually we write it as P of S A where this is。呃。

What is this is on row。 This is on column。 So after transpose is the other way around， right。

 So P transpose P S A。 So here you have the。So， so you have S A on the column index。

 and you have a S prime on the row index。 remember， this is a conditional distribution。😡，And if。

 and with D pi is another distribution。 So what happens when you multiply P。P transpose。

 which is the transition kernel of the NP with Dpi， which is the conditional distribution with D P。

 What do you get。Right， you can think about it like more carefully。 So basically。

 this is like for every。 So let's do it more carefully。

 So when you do the when you do the matrix multiplication is essentially every row。

 you take our product with D as a distribution。 So for now。

 like just think of D as a general distribution。 nothing special。 So let's do it。

 So this is sumation over what sumation over S a D pi S A， actually， let me just write P。

 which is like， let's think of of what happens when you have a general distribution P over here。

 So P is some distribution versus action pair。😊，PSA times。啊。啊呃。As prime， I say。Okay。

 so to give you a distribution， like clearly what it。

 what it does is that this is eventually a function of S prime， right。

 Because S A are being marginalized out。Right， so this is， this。

 this is something that is a function of S prime。 And my claim is that this is actually a distribution of S prime。

And given this expression， can you describe a generative process that describes how S prime can be sampled。

😡，How would you sample like， how would you sample from S prime。Sample from P S right。

 So you first sample an S A from P， then do what do you do。Condition on that， you sample S prime。

 right， So essentially， what you do is that you sample from S A。 and then condition on that。

 you sample an S prime from the conditional distribution。

 which is the transition distribution of the NP。 You get an S prime。 So essentially。

 what happens is that you're passing the distribution P over the transition dynamics。

And in particular， if SA is a distribution at the earlier time step。Then as prime。

 the distribution prime is precisely the next state distribution you would get。😡，Right， so。

So therefore。Like what happens is that we're multiplying D。

 So this is D actually up to one minus as gamma。 We're multiplying that with P transpose。

 which is like pass the the distribution over the transition dynamics。 And here is the claim。

 So what you would get is the following。So。If I start with the0 pi S。

 which is the zero step S distribution under my policy。 So it's just like an arbitrary distribution。

 When you pass over this transition dynamics， what would you get。And here's the claim。😡。

What you get is D1。Sorry， d pi 1 of S。Okay， does that make sense， right。

 Because here we're saying that， oh， if you have the marginal distribution of action pairs at time step 0。

 pass through the dynamics。What you get， what you get is that what would you what if you start from the same initial state distribution executing the same policy pi。

 the distribution you get at the second time step。 or here is like t equals 1 versus like t equals 0。

😡，Okay， and similarly， when you multiply P transpose to the one pi S， you should get the two pi of S。

And so on so forth。O。Does that make sense， Right， Because the thing is that I'm， I'm。

 I'm multiplying。The mixture of all distribution with P， P transpose。

 And because matrix modification is linear， I can just multiply each one of them and then sum of them up again。

Right。Okay， so the other thing is that we're actually multiplying with gamma P。

 So this is why like so here you have the coefficient one。 but when you get here， you have gamma。😊，嗯。

And here you have a gamma square and so on and so forth。Okay。So this is this term。

 And on the left hand side， we have this marginalization term， right， So if D equals D pi of S。

 what is the left hand side。When you sum over the variable A。When you have a distribution。

 join distribution for multiple variables， you sum up the probability over a particular variable。

 What are you doing。So say say that louder。 I think I'm hearing the right word。No， no。

 conditioning is not like condition。 This is part of what you need to do in conditioning。

Marginalization， right， So instead of the join distribution of S， by summing up A。

 I'm only carrying now the marginal distribution over apps。😡，Right， so if， if D equals D pi。

 the left hand side is actually just the is is actually just the。It's just the D pi of S。Right。

 and if you， if you look at over here， we're almost there， right。

 because if I fill this table with like， you know， D 0 pi S， D1 pi S。

 D 2 pi S and so on so forth and add them up with the correct， like discount factors。

 I should be getting D pi of S， which would be perfect。Right。Except that here I'm missing something。

 what I'm missing。😡，Just， just look at how you get from the left hand side to the right hand side。

 What am I missing。The first term， right， because every time you pass the distribution over the dynamics。

 time evolves by one's time step。There you have the initial step， which is t equals 0。

 or which is previously our t equals 1， that's just like 0 versus 1 indexing。😡。

The very first distribution I get on the right hand side is t equals 1。😡。

I never get t equals 0 because I can't evolve it from like t equals minus-1。😡，Right， so therefore。

 for the Ryan side to be equal to the actual D pi of S， What do I need to do。

 I need to add up a term。 What that term is。😡，D 0 pi S， right？ So this term is missing。

 So I need to add it， right， But what is the 0 pi of S That is youre executing policy pi。

 What's the first state distribution。 Well， that has nothing to do with pi。That's just the zero of S。

😡，Right。So you make it up over here。Okay。This is why NADI would satisfy this constraint。😡，And。

 and if you think about it， this constraint。 So we have the Belma equation for value functions that talks about the value functions being。

 you know， temporary consistent。 My prediction for long term value today is consistent with my prediction for tomorrow。

 This is also term a notion of temporal consistency， right。

 So essentially saying that I have this distributions that that that actually they correctly correspond to the distribution of an occupancy。

 which means that whatever my slice of the distribution for particular time step。

 when you evolve it with the transition dynamics of the MP。

 you correctly get the the the the the slice of the distribution for the next time step。Okay。

 and for this reason， equation equations of this form is also sometimes called the Belman flow equation。

The Bman flow equation of this form。 So， in fact， in the homework， so this。

 this equation is a policy agnostic。 It doesn't specify policy。 and indeed。

 it has actually has infinite many solutions。 it， as I said， it characterizeifies all possible D。

 you can possibly create in this MP， right， And in the homework， you will actually see in problem 3。

 There's a version of the Bman flow equation。 But for a specific policy。😊，For specific policy。

 there's something that is similar to here but there you only have。

 there's only one solution to that equation， which is the D for whatever policy you specify there。

Okay， so in both cases， you can broadly call them， you know， a form of thumb and flow equations。Okay。

So this is the the LP formulation now。One thing is that one thing interesting is that so suppose I solved this LP。

 So I get D star of S。Right， so let's say I solve the， the， the， the the optimality。

 the the optimal solution of this of this dual form。And the optimal solution is the star。

 Can you represent the star using notations that we already know。Think about it。W should be the star？

So， first of all， any D that is a solution is a is D pi for some pi。Right。

So what what's the pie you should use here。P star， which is pretty obvious， right。

 So this is D P star essay。 Actually， you can say D P D pi。De Pi star essay is an optimal solution。

This has something to do with whether your D0 is fully supported and， and so on so forth。Okay。

 so this is the first thing。 And the other thing is that once I solve for the star。😊，Like。

 that's not the end of the game， right， because the end of the game is that I want a optum policy from this result。

 right， So previously， when I get the star， what I can do is I can first convert it to Q star and then graify over that。

 I get optimalum policy。But here， how do I get the ultimate policy？😡，All I get is the star。

 which is the distribution number the action pairs。Okay so here is how you do it。Because this is the。

So D star is the discounted occupancy under the optimal policy pi star。Right。

 but what is the optimal policy， Pi star is the conditional distribution of a given S。

So you know the joint distribution over state actions under the optimal policy。

 How do you get the conditional distribution。Or like literally just conditioning， right？

 So therefore， once you software S A。WWhatch you can get is the following。7。Move it little further。

Pi star of a given an S。Right， actually also like just in general。

 like the this this does not have a unique solution， because if you remember like in MP in general。

 there can be multiple auto policies right， So even if you have the same state occupancy。

 the the actually the state occupancy can even be different。 So there， there's in general。

 like infinitely many different solutions。 And all you need to do is to find one of them。

 And whatever one you find， you actually get an corresponding auto policy out of it。

 but just doing conditioning。RightBecause this is just the draw distribution over S under the optimal policy divided by the partial distribution over S。

 So you get a conditional distribution of a given an s which should be precisely the optimal policy。

Okay。Okay， so。ThatThat's the end of the planning section。We're now gonna start really like the， the。

 the learning part of the lectures。 But given that we're doing a switch of topics。

 let's take a quick break and come back in， you know，2，3 minutes， okay。Yeah。

actually let address that after class， okay， so I don't think we have time to properly do that。😊。

Okay， so come back。So呃。So now we're done with the planning section。

 We're actually starting to talk about learning。 And remember， like this is the theory course。

 So we're like whenever we talk about learning， we need to talk about theoretical guarantee。

 sample complexities and so on。 So， and to prepare for that。

 we need to introduce some tools that you may have seen， like， for example。

 if you've taken a randomized algorithm or like other learning theory courses。

 like this should be your like best friend， like， you know， all the time。 this is called in general。

 like results of this kind。 It's called concentration inequ qualities。Okay。

 so basically what were interesting as a really cornerstone and foundation for learning theory theory。

 we need to talk about the conversions of the average of random variables。😊，Right。

 in the sense that like， for example， the simple the simplest setting is that if you draw a multiple I samples from a particular random variable。

 a particular distribution， you get a random variables that are I and from the same distribution。

 you take the average， And we know that under some mild conditions such as body moments and so on。

 in the limit in the in the in the limit of infinite infinite number of samples。

 the empirical mean is going converge to the true me。😊，Right， but。But first of all。

 that's a asynmptotic statement that you should have learned in your， you know。

 probability or statistics like undergrad level statistics course。 And that's insufficient for us。

 as you， as I mentioned， in this course， we're gonna care about everything in the finite set setting。

 like you have errors everywhere。 like we're not gonna， you know。

 allow for like this lazy claim that， oh， in the limit of infinite， everything is nice。Okay。

 so therefore we need something finite。 So what's the finite version of the claim that empirical main convers to the true main that you should have learned at undergrad level。

Central limit theorem。 So what does central limit theorem says， Like。

 forget about the condition under mild conditions or whatever。 What was the claim。

Can people remember the claim of the central limit theorem？Roughly the claim。😡。

So it's not about converge， but rather how you converge， what's the shape of the empirical mean。It。

 it follows the normal distribution， right， But however， so okay， actually。

 the central limit theorem is actually how we actually compute， for example。

 Comp intervals when you actually， for example， run experiments。

 empirical experiments in machine learning， statistics and whatever you do with data。😊。

Right typically what you do is that you calculate the mean， you calculate the standard error。

 which is like standard deviation， like divided by another factor that depends on sample size。

 And you plus minus something like two times the standard standard error and claim that this correspond to oh。

 like depending on what's the factor， like 2 versus 2。5 or whatever。 You have 90%，95%。

99% and so on so forth。 confidence intervals。😊，But thats actually like mathematically speaking。

 even if all the requirements like IDiness， boundiness， all of these holes。

 unless the original random variables themselves are Gaussian， then of course， the mean is Gaussian。

 but in general， if your original random variables are not Gaussian。

 central li theorem when applied to a finite sample setting is actually wrong。😊，Okay。

 because what central liism tells you is that the shape of the empirical mean will become exactly Gaussian when you have an infinite amount of data。

😡，So when you only have finite amount of data， the shape of your empirical main will only gradually becomes more and more closer and closer to Gaussian。

😡，Okay， so therefore， all those competitors intervals that we compute every day when we're doing experiments are actually approximate。

 They're just like good enough approximate that typically。

 unless your original distribution is so screwkewe and like crazy， has crazy shape。

 like long tail or whatever。 Most of the times they're。

 they're good enough that we can actually ignore the errors there。😊，But again， remember。

 we're doing theory in this course。 We can't really tolerate any， even slightest， you know， like。

 you know， like incorrectness in our theoretical statement。

So we need something that is like really strictly correct for finite samples that is beyond like central limit theory。

And here you go， concentration inequities。 This is exactly that。

 Think of this as the strictly correct version of central limit theorem， but for finite samples。Okay。

 non asynotic settings。So what's the claim here。 So， you know， you can have the。

 let's say let So here， So one of the basic version is called a H in quality。 There are many。

 many more and more advanced version that will gradually encounter later along the way。

 But for most of the basic uses， H things will take care of like most of what we need。😊，Okay。

 so what hot thing says is that if you have random variables， actually。

 I'm already stating a slightly general setting where these random variables are not even I D。

 All they， all you need is that they are independently distributed。

 They may not even be identically distributed。 Okay， so I D is a special case。And the， the crucial。

 the crucial assumption here is that it's bounded。 Okay。

 so every random variable is bounded between A and B。 almost surely， there is a side generalization。

 you can find in the notes where the bound is for each random variable can also be different。

 That doesn't actually， you know， change things very much。

 There is a straightforward generalization over here。😊，Okay， then I can have the empirical P sumal。

And empirical sum divided by number variables is just the empirical meaning。Now。

 what generalizes the trueing。 So when we can talk talk about empirical mean devs from the trueing when all your random variables are I D。

 right， But when those random variables are not identically distributed。

 the natural generalization of the true Ming is basically the like the sum of trueing， you know。

 take average。Okay， so if all the random variables are ID， then this would be just be Sho me。😡，Right。

So you say the probability of this difference is greater than some special T is upper bounded by this。

 which shrinks exponentially with the value of T。Okay。Now。

 this statement is actually in a very inconvenient form that usually we don't use it。

So the way we typically use it is that or alternatively。😡，We say with。With probability。Add。

Leasst1 minus delta。Okay， so what does， what the statement says， right。

 So what the statement says is that， you know， you have a random draw of and like。

 of of these like random variables。 You take the empirical me。

It is always possible that the empirical Ming is far， far， far from the far， far。

 far away from the Shumi， right， because everything is random。 Everything is possible。

So you can say like， oh， definitely my main is gonna be imping is gonna be within the true mean by some small error。

That you cannot say， you cannot say something for 100%。So all you can say is that， oh， like。

Like majority of the cases。The， the empirical me I get is very close to Chhuing。 And there are some。

 there are some like astronomically extreme， like small chances that I would just get very weird and very unlucky draws that my empirical me can be。

 you know， very far off。Okay， so this is what the statement。 right， So。

 so let's say T is some threshold。 and this is the error you get empirical mean minus2 meaning。😊。

That the probability that this should be an absolute value。

The probability that the error is greater than some threshold。

Like when your threshold is set to be like， you know， moderately large， it's gonna be very。

 very small。 So this is like， you know， a very， very unlucky event。 And hopefully。

 this probably is like extremely small。 Like point0001 something like that。 Think of it that way。

Okay， so， and， and claim in this form。 And we're gonna be using claim in this form throughout the entire rest of the semester is。

Is gonna be is is called a high probability statements。Okay。

 and we need to like be used to work with it。 So， and so the。

 the more common form that we're gonna use this is to say， okay。

 so this is this unlucky what we call failure probability。Failure。Probability。

And like all our learning algorithm guarantee will be in this form。 that's saying saying， oh。

 there's a tiny， tiny probability that everything is going to go wrong。Well。

 let's just exclude that and only think about what happens majority of the time。

 majority of the time， things are going to be okay， okay。

 and when when you stated is say with probability at least one minus deelta where deelta is this。

Things are going to be okay， right， So in the context over here。

 what does things are going to be okay mean， It means that things are empirical me and true meing are close to each other。

 right， So here you have greater than equal to， which means that they're far apart。

 That's the bad event。Right， so， but when you state in this form that says with probably at least one minus delta。

 you say things are good like S N over N minus expectation， S N。Over n is less than equal or less n。

Okay， well， actually the， what what you do is that the the， the T value and here。

 theyre not independent， right， Because given the T。

 the inequality dictates a particular value of the failure probability given over here。

 So if you want delta to be a free variable， which you can get is like the value of T when you just calculate what's the value of T that makes the right hand side。

 you know， particular delta。 right， And here is the most common form that we will get。

 which is B minus a square root1 over to n lo2 over delta。😊，Okay。

 so this is the most common form of hot quality that we're gonna use。However。

 one thing that you should be very careful about is。Like， people often get， like。

 people can be confused when they work with statements like this because it looks as if we're actually stating something deterministically。

Okay， that this is gonna be happen。 did be happening。 Well。

 that's actually not the case because it only happens with probably at least So， there's a， you know。

 that there's a， there's a statement before that that says this happens with probably at least one money doubt。

Okay。😊，Okay， so。I'll get a give to claim over here。 One is that。嗯。we actually， you know。

 later when we apply this to the to the setting， we。

 we'll look at a very simple example of like learning multiar bandits on Friday and it will you know see how how you actually apply this this result。

Okay。😊，But for now， one little exercise I can do is the following so this theorem over here actually comes from combining two results that is you have this okay。

😊，You have this greater than t or minus minus T。Okay， right， So cause， because。

So what's happening is that I have the probability upper bound。 you know。

 in the actual proof of the theorem， which you get is that you get like two statements。

 So here I'm just appravating。 So think of this host for when you have greater than equal to t over here and the same statement also holds when you have less than or equal to minus t over here。

 One says the probability that my empirical mean is above the true main by a lot is very small。

 Another says that the probability that my my empirical mean is below the true main by a lot is also small。

Okay。So。嗯。So if this is what you get。Okay， let me just。Let me paste it over here。Okay。

 so if this is what you get， which means let me just be even more explicit。嗯。

Greateater than equal to t。Probability。Less than or equal to T。

 less than the same expression minus T。Okay， so， and we know that the absolute value is greater than equal to T is equivalent to this and this simultaneously。

Right or like you know， or。😡，If either this happens or this happens。

 it means that the absolute value is greater than equal to T。Okay。那。

How did we get the statement over here？😡，From these two separate statements。Okay。

 so this is thing that you eventually get。 But before the very last step。

 you get these two statements。 How do you get the same， How do you get， you know。

 one combined statement out of these two。Union bound， right？So the， this is the one of the， you know。

 when you do with applied concentration inequalities。

 it's almost always used together with union bound。 So what is union bound， Union bound says。

So given given events。A and B。Probability。You know， probability of a union B is less than PA plus P。

 B。And you can have multiple events and then you take the union of all of them。

 as long as it finite is always， let areunded by the sum of the probabilities。Okay， and the。

 the really powerful aspect of the union bound is that union bounds is。

It doesn't require anything about the distribution， about the probability distribution。

 Like it doesn't require like， for example， the events to be independent or whatnot。 like it。

 it always， it always holds。Okay， and when we when we use it in together with concentration inalities。

 typically we use it in the case of， okay， so these events correspond to the kind of event we right over there。

 right， But when we talk about the kind of events we have in concentration inities。

 we have these like good events and bad events。 Good events means that empirical mean is within a range of the true mean。

 bad events means empirical mean is greater than like， you know， far off。 Okay， so。You know。

 make a guess like what kind of events we're gonna to put here as A and B。

 or we're going to use good events over here or bad events over here。Bad events， right。

 Because remember， those bad events。Are going to be assumed to be have very small probability。

RightAnd this means that each of these events is kind of like Delta， and this is like Delta prime。

Then what we get is that the union of bad events， which means that the probability of any of the bad events happening is provided by simply the sum of the number of small deltas。

So if you use Dlta is very， very small。 hopefully， the sum of them is still like reasonably small。

And typically， what happens is that we're gonna to first say， oh。

 we want this whole thing to be also small with probably like you know some like deelta。

 and then we split the delta into different like events over here in the union and then use that to back up like。

 you know， the the kind of statement we need to get for each event individually。😡，Okay。

 so this is exactly what happens over here right so how do you how do you you know when you have these two。

😊，So let me just write it。 So we like from here， how do you get the thing we do。

 We say probably you know， the the error is greater than equal to T。Is equal to probability。嗯。

That the error， so I'm going to just say error。R is greater than equal to T。As an event。Union。

A is less than minus T。Okay， so this is equal， right？So union means either of happening。😡，Right。

 either or both happening， right， And that's precisely the same as the。

 the absolute value is greater than equal to T。And then what you do is less than now go to probability of。

A greater than C。Plus， probability。A less than T， sorry， yeah， we're less than equal。 Okay。

 and then you already have these bounds over on the right hand side。 So you combine them。

 So that's how you get this。Multipliier of two over here。O。

So we will actually use a lot of union bounds。 like whenever you use concentration inequalities。

 It's almost guarantee that we're gonna use union bounds。 And we'll see how to。

 how to do it over there。 And gradually， you know， the， the the the。

 the actual workflow you will see in practice is that whenever you invoke a single concentration inequities。

 typically the way you remember them is。😊，Is this？Okay。

 this is with probably at least one minus deta， something like this happens。 Okay。

 you have another event。 you have another concentration in quality that says with probably at least one minus delta。

 something else happens。Okay， but then like often you need like this is a good thing。

 And here you have another good thing that is guaranteed by concentrating qualities。

 And for your algorithm to properly work， you need all those good things to happen。Okay， so。

What under the hood happens is that conceptually， you're translating all of these back to those。

Those expressions that says the probability of bad things happening over here is upper by Delta。

 The probability that bad things happens over there is upper by Delta and so on so forth。

 And altogether， you sum them up and say， oh， the total failure probability cannot exceed a certain level。

Okay， and then you use Uni bound over there。😡，So， but gradually， you will get like。

 but gradually you need to be get used to you know， how to directly work。

 work with the statement without even translating back to the original like statement of there。

 But whenever you get confused， think in this form can be very useful in helping， you know。

 you get get get out of the， you know， confusion。Okay， so that's it for， for today。

 And we'll see the application of this bandit on Friday。有。Yeah yeah yeah， this seems correct。

Really cute No， I think the subsequent for it。不认。Oh yeah， right， right， right。Just to。O。Yeah。

 I I kind of know that this。P is not really mathematically like there。 But no。

 it is mathematically there， right Ca because I think what we did is。

We we start from here to this step without the parents of these。Right， but literally like。

 so the summation over here of Okay， so we're talking about the me see。

 you have double summation summation over I first and summation over S tuda right。

 and then summation over tu S tuda。 let me think about it。 like time， something that is。😊，as to the。

I'm a little confused。 let me think about it。What's happening。

 I think since it is about still that the practices itself was here， but because it can be。

interchangeable， right， right。 So right。 So yeah yeah， precisely。 So I think what happens first。

 you push the gamma to the I inside the summation over here。

 Then you have the two summation over here。 just swap their order And once you swap your order。

 the inside is a summation over I， which has nothing to do with this then you do the parentheesis right And Yeah yeah。

 you're right。 So I think I I did the wrong thing over here because once you put the parentheesis here here。

 it doesn't make sense because you have a summation over S prime， which becomes a function of I。

 but then you have a S is something that is mean to be like marginalized out but。

