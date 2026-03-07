# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p04 P4 价值迭代 -BV1YsZHBZEyM_p4-

Okay， let's start so。Last time， we ended with the。Projects are spring。

So last time we ended with the beman optimal equation for v star， right。

 so this is equals max over a。And for each action， you get the immediate reward plus gamma expectation。

The transition probabilities， V star of S prime。Right， and then we said that if you actually want to。

Get the outcome policy。 even after you solve for this equation and obtain the star。

 you would need to compute like。This particular part。

 evaluate for each action and then pick the maximum action。 thatll give you the optimal policy。

 So therefore in our， typically， we directly try to learn this quantity and we give it a new name called the Q star of S A is equal to。

 which is just this， And you can actually write on the version of bema equation that is only dependent on Q star。

 So you don't need to you know， talk about v star anymore。

 You can directly sample Q star and then gridified rate。 you get the optimal policy。

 So this is equal to well， is bema equation。 Well， basically what you do you just copy its definition。

 right， which is the right hand side， which is R of S A plus gamma expectation as prime。😊，S A， well。

 you would want to put V star S prime over here， but you want to make an equation only about Q star。

 So you ask yourself， how do you express V star as a function of Q star。

 And the answer is you just max over the actions。Right。

 so here I use a prime because the symbol A is already used。

 It's associated with the previous state or the current state S。 and then。

So here the S prime is the next state。 So I need another action over here。

 which correspond to the second action。 we're， we're considering over here。 Then you get the。

 So we also call this be opt equation。 It just the the version for Q star and similar to the V pie equation with saying previously。

 This is not each， each line is actually not a single equation。 right。

 So each line over here is you actually have a equation for every single state。

 So it's actually as different equations。 And for the。😊，For the second line。

 when you have the equation for Q star， it's also not a single equation。

 It's actually S times a different equations。Right。

 so and that gives you hope that you have essay unknowns and you have essay equations that maybe you can actually。

 maybe there's a hope that it has a unique solution， which will show that indeed it does。Okay， so。

Before we talk about how do we solve this equation， these equations， just some quick remark。

 this conversion that we implicitly use over here is the relationship between these two quantities。

 right， that once you get Q star， it's very easy to get V star because you just take maximum over actions。

Right， and once you get Q star， it's easy to get pi star。

 which is pi star of S is just pi sub Q star of S， so。This will be a shorthand that we define。

 So we have pi。 and the subscript is some function， real value function over state action pairs。

 We use this notation to mean the the greedy policy with respect to whatever function that is there in the subscript in particular。

 this means agon max。Over a Q star of S。Okay， so like if you。

 if you have another like pie sub something else， well， it just means that it's a different policy。

 Just argument X with respect to a different function。O。So呃。So this is the review。

 And now we're gonna talk about how do we actually solve these， which along the way， were also。

Help us prove some important properties of this bama equation。Okay， so， and as I mentioned。

 we'll actually just work on the Q star version， but very similar algorithm。

 very similar analysis applies to the V star version as well。Okay。So。

 and this is the classical algorithm called Val， which is can be viewed as a， you know。

 generally speaking dynamic programming algorithm。And in order to introduce the algorithm， were。

 what we're gonna to do is to introduce a very important concept in R called the Bman operator。

 So define。T。 So this is like a curly kind of tea in late tag。 you type like mass scale T。

 T is a mapping from。嗯。Real value functions over the action pairs。

 Like you give me a real value functions over the action pairs。

 such as Q star and maps this function to another function of the same four。Okay。

 so operators are basically like functions。 But in general， when we talk about functions。

 you have something that is like， you know， a single output。

 like either a real value output or something like a binary output or something like that。

 But if you're， if you have a function， whose output is another function， like， you know。

 sometimes this is referred to as an operator。Okay， so， and another thing that is worth mentioning。

 which is often confusing， is that when people see this。

 sometimes people assume that it's talking about a matrix of size S by a。Okay。

 so that's not what we mean over here。 So， first of all， like， if we actually mean a matrix， right。

 you have， when you write down like the， the field or the set of all possible mates of certain size。

 you write R M times N， right， And here M is like the number of rows and is the number of columns。

 So if we actually want to match that particular format， what we should have written is like。😊。

The size of S times the size of a， right， but we're not writing it over like that。

 We're writing R to the S A。 So we're basically saying R to the S A basically is like， so， so here。

 this thing we're treating is as a vector。Okay， whenever you see S times a in this course， its never。

 is's almost never like meant to be considered as a matrix。

 It's always meant to be considered as a long factor where you just enumerate over through all possible state action pairs。

Okay， just like when we say before， like when you look at V star V pie。

 like you can treat it as a function number states。 but alternatively。

 you can also treat it as a vector whose length is the number of states。

 And you just decide a particular systematic order， arbitrary order you know how you want to。

 you know， enumerate over the state space and same here。

 except that here we just like enumerate over all particular all possible combinations of states and actionss。

😊，Okay， this is never meant to be treated as a matrix。Okay， so what is this T operator， Well。

 in order to specify an operator， right， So how do we specify a function。

 Well a function is a mapping from something to something else， right， for。

 for some input variable to some output。 So in order to specify that， you just need to tell me。

 given an arbitrary input， what is the output。Correct。😊，So therefore， to specify the operator。

 I just need to tell you for any possible input F。Which is R times SA。

 which is like something that looks like the Q function。Or give me any function。That is， or general。

 you can also view it as any vector whose length is as times a。What is the output T of F？😡，Right。

 so if I give you particular definition for this output， which is also a function。

 I fully specify the operator for you。Correct。Okay， now this output itself is yet another function。😡。

Right，But just that it， it's a function over the action pair。 So to specify this function。

I can tell you， what is its value for any S A pair。Okay， does that make sense？So if I tell you this。

 this。Operator T is fully specified。Okay， what what is this。

 Whatre we're gonna to do is that basically we're gonna look at the right hand side of the Bma equation and just give it give it name。

 So we just said this is R of S plus gamma expectation as prime given P of S max over a prime。

 Okay so far， this is exactly the same as the right hand side of the Belelma equation for for Q star。

 and that's intentional because we we introduced this operator to rewrite the Belma equation bema alpha equation。

 and then later use this to analyze the equation and the corresponding algorithm。Okay。

 so that's why you know， we'll copy that。 So the only difference is that in the equation here。

 we have  Q star。 So here we'll just put F。Right， so F is whatever you sending as the input。 Okay。

 S prime a prime。O。So now once you have this， like， so I've defined the operator for you。

And why am I defining this operator， Well， because once you have this operator。

 the Belman automaticmatic equation。😡，That we have above。

Can be very concisely written as Q star equals T， Q star。RightBecause if I plugging F equals Q star。

 the right hand side will become exactly。😡，The right hand side of the Bma Op equation。Right。

 and for this equation to hold， the left hand side is Q star itself。 So you just have Q star。

 equals T Q star。This is just the con way of writing， writing the equation。Okay。And have， have， have。

 have， have anyone like saying equations of this form， Like， what do we call equations of this form。

Their fixed point equations， right， So equation of this form that says something is equal to something self up to some transformation。

 It is called a fixed point equation because this this quantity， like  Q star over here。

 it's called a fixed point of T， right， because in the sense that like if you start with Q star。

 And if you apply the operator T to this function， you get back the function itself。😊，Like。

 where else have you seen fixed point equations， There should be like an example that everyone knows。

I said that everyone should know because I listed that as a prerequisite for this course in the first class。

 so you should know it。Anyone。What kind of equation looks like a fixed point equation。Eigenvalue。

 right， like， I mean， up to the like maybe like if you want to fit exactly this， you need the。

 you need like it to be the eigenvalue corresponding eigenvalue 1， right， but it。

 it looks something like this， right， You start with the vector。

 You multiply the vector with the matrix。 You get back to the vector itself up to the eigen eigenvalue。

 Now what what what do we call that eigenvector。 That is a fixed point of the matrix。What's。

 what's the name for that vector， That is likes， let's say， if you have A V equals lambda v or like。

 you know， if lambda equals 1， this is what exactly fit our definition of fixed one equation。

 What do we call this vector V。It's abacterctor， right， So there's nothing tricky about this， okay。

Like， don't， don't expect。 like， I， I think I try to ask。

Ratherly preliminary and basic questions just to keep people involved， so。

Don't expect that I'm always asking like super， super tricky questions。

 Like many times I ask questions like that are very straightforward。Okay， so。So， and and again。

 like when I write it this way。 So if you look at above above， I'm writing the like as I said。

 like each line over here is actually a set of equations It multiple equations。

 And I'm writing it in the form of I specified the equation for every possible station pair。 So here。

 this is also actually S times a equations， right， but I'm actually specifying it about the。

 like essentially this is similar to the matrix form of the B equation for policy evaluation， right。

 So I'm I'm actually specifying that whole system of equation， Like like just you know。

 in one single line。😊，Right，Because on the left hand side， I have a whole function。

 or you can see that as vector on the right hand side is also a function， which is also a vector。

 And I'm saying these two vectors are equal to each other。

 which means that each coordinate is equal to each other。😊，Okay。Okay， and as as as a side note。

 So we won't analyze how you would learn or compute v star。 but the story is kind of similar。

 You just define the right hand side as some kind of operator that takes any function。

 you replace v star with that arbitrary input function and call the right hand side an operator that operates on that input function。

 And you also similarly write v star the equation as as a fixed point equation。 In fact。

 we often abuse the notation to write v star equals TV star。 Okay。

 because of the close connection between these two versions of opt equations。

 But clearly here the T here and T here there are different things。

 right because they they don't even have the same same like type。

 One is mapping from like Q function to Q function。

 The other is mapping like stay value function to stay value functions。

 But still like we often abuse the notation to call both T And how do you tell which one is which。😊。

When you look at the type of the function it applies to， if you see a stay value function over here。

 this is the state version， if you see a Q function over here。

 this is the state action valued version。😊，Okay， so we'll talk about how you extend the analysis and and so on later。

 But this is just the side note for now。Okay， so。You know， why does that help？😡，While also。

And it helps because we're gonna just use one of the most standard。

Ways to solve fixed spot equations in numerical analysis， which is like iterative methods。

 And this is the value duration algorithm or V I。Okay， so what's the validation algorithm。

 The algorithm goes like for。嗯。K equals。 So we first initialize。Let say， F0 to be a。

There or anything。So really， like， you know， for， for convenience。

 I'm gonna be concrete and specific and say we do a zero initialization。 But really， like it。

 it can be anything as long as its bounded。 and the analysis will be， will be similar。

And here I'm writing。I'm writing a zero vector here because like。

 I'm really assigning to it a zero function。 And this is a zero function over the state action space。

😊，Okay， then what you do is pretty simple for K equals 1，2。 blah， blah， blah。 You have F K equals T。

 F K-1。Okay， so what you do is that you just， you just start with an arbitrary function。

 typically like zero initialization， but zeros are。

 there's nothing special about the zero initialization just for convenience。

 And you just repeatedly apply the bump operator to this function。 Every time you apply。

 you apply the bump operator， you take in that function， you get another function out Right。

 So because they are the same format， you can plug in。

 plug it into the input to the bump operator again and again and again， you just keep going。😊。

And we're gonna show that eventually， this F K， when K， like， you know， becomes like really large。

 it will， let's say， let's say you do it for capital K runs。 So。

 and everywhere else is like small K is like the， the， the， the index。 if， if K is large enough。

 F K will converge to Q star like pretty fast。 Like with a particular convergence rate that we see。😊。

Okay。So this is the like the algorithm can be simply specified in this way。 And you know。

 it should be pretty obvious。 And in fact， like as I mentioned。

 like if you have taken numerical analysis， you should have seen like similar， similar things。

 right when you compute eigenvalue， especially for the leading sorry。

 when you compute the eigenvector， especially for the leading eigenvalue。

 This is also something you can do like repeatedly like you know， do the matrix multi。

 you need to do some normalization over there。 But when you keep doing it， eventually。

 like wherever you start as your vector， even with a random direction。

 it will converge to the like leading eigenvector direction at the end of the day。😊，Okay。So。So。

 we want to。We want to show convergence， right？ So convergence， meaning the， the claim is that。

 you know， we have like a。Much stronger。Claim because it's。

 it's gonna to be like a very specific convergence rate。 But for now。

 let's just say this become custone。Okay。So this is what we're going to prove next。

And you order to prove that。 And this is what we're going to do like for quite a few proofs that we're going to do from today onward in the next couple of lectures is that what we're going to do is that we're going introduce an important lemma。

And then like that basically split the proof into two parts。

 One is that we have to establish thelemma itself， and then we apply the lemma to prove the final results。

Okay， so here I'm going give you dilemma。 Thelemma is the one of the most important properties of。

 of the bomb operator。 So this is the apartment operator is a gamma contraction。Under El in Pero。

Okay， so this probably won't make。 let me write it more properly。 This writing is pretty bad。

It's a gaba contraction。Okay， so what does that mean， Well， mathematically。

 what it means that for any F， let's say F prime。嗯。Or maybe let's say ada。

 just prime is often associated with next state。 So of let me change here。

 What you do is that you apply T to both。Okay， and measure their distance。

 like measure how different they are。 And sorry， I didn't write over here。

 And which norm do you use to measure their distance well。Here it says infinite norms。

 You use infinite norm to measure their distance。You also measure your distance before you apply the operator。

😡，Again， using the same distance metric。Okay， and if it is satisfied that。😡。

After you apply the operator to both of them， the distance becomes smaller than before up to a multiplicative factor。

That it is less than one。 Here it is less than one because this the this going factor gamma。Okay。

Then we call this operator to have this contraction property。

 in particularly it's a gamma contraction because gamma is this multiplicative factor over here and it's under L infinite norm because L infinite norm is what you use to measure distance between functions。

Okay， so， so the second line is just a mathematical concrete mathematical definition for the first line。

 The first line is like a mathematical terminology for， you know， what we mean in the second line。

Okay， so therefore， like what we're going to do is that we're。

 we need to establish this dim and then use the le to prove converence。Okay。

 and also just to visualize things， what it means is that if you think about like your functions living in some。

 you know， because we also treat functions as vectors， right。

 So you can imagine visualize them in like some R D or you know。

 more more accurately R A So I can't visualize high dimensions。

 So maybe like just treat like two dimensions as a cartoon vector。 So you have F and F tuta， right。

 and you apply T T is an operator that maps one function to another。

 So an operator will just take your function from one place to one point in a space to another function。

 So this is maybe T F。 This is maybe TF tude。😊，O。And what this contraction probably says is that for your operator to be a contraction。

 it must follow that whatever two points you select as the starting point in the space。

 you measure the distance here， you measure the distance here。😡。

The distance here must be shorter than the distance over here up to a multiplated factor。Okay。

 that's kind of like the visualization。😊，And what we're gonna do is the order that we prove these things is that I I usually want to flip the order。

What I'm going to first do is to pretend that we've already established the dilemma。

 that is first assumed that the dilemma is true。 Now we use it to analyze the value region algorithm。

 After that， we're going to establish the lelemma。O。So if this Lama is true， like。

 how can we establish the value the convergence， Okay， so to， you know， to establish convergence。

 basically what I'm gonna do is that I'm gonna analyze Q star minus FK。😊，Okay， and。As you see。

 like here， we are always going to measure difference between functions using infinite norm。

 And for people who don't remember， infinite norm is。If you have a vector x。The infinite norm。

 let's say， is indeed like is max over I X I。 So I is the where enumerating over all possible coordinate of of X。

O， so you just look at all its。Element take absolute value and then take the maximum。

And then when it comes to compare two functions， what it means is that on every possible input。

 you calculate the difference between the two functions， take the absolute value and you say like。

 where they differ the most。And the amount that differ， they differ in that place。

 call you call that a measure of difference between the two functions。O。

So if we already have contraction， how do we do it？ Well。

 it turns out that this part is actually very simple because this is just equal to。us T FK -1。

 So I'm going to rewrite this difference over here。😡，嗯。Oh， by the way。

 if we want to show conversions， what kind of final result we want to show， right。

 we just want to show that this difference is small。 And in fact。

 it it becomes smaller and smaller and smaller as K increases。 And when K increases to infinity。

 you want this thing to become 0。😊，And better still， you want to have a finite。

 like convergence rate， like analysis that says for finite K。

 Can you like quantitatively control how small this， this difference is。Right。

So what we're going to do is that we're going to rewrite this difference。 So FK。

 by definition of the algorithm， is just T， the operator applied to the previous iteration of the algorithm。

Right， in the previous situation it's called F K-1。Okay， and as a spoiler。呃。

We said that we're going to treat the contraction property as if it's already established and going to use it。

 right， And if you look at here。The contraction property says that is for any two functions。

If you're measuring their difference。And the two functions look like they're both the T operator applied to something else。

 Then you can invoke the contraction level。Right or you can， you can invoke this property。

So we might want to do something similar。 So can I write it in the form。That corresponds to。

The left hand side of the。Contraction property。Right， because what， Because by definition of Q star。

Q star equals T Q star。Right？So， so therefore， like whenever I see Q star。

 I can always replace it with T Q star。So Q star I can replace this with T is Q star。Okay。

Then it follows the definition。Right， so because it follows the， the。

 the the format of the left hand side of the contraction property。

 when invoke the contraction property and just get gamma times Q star minus F K-1。What do we do next？

约死楼啫。You or you recursion or you just repeat this， right， Because you start with  Q star minus F K。

 where K is just some arbitrary index。 You end up with like one multip factor times k Q star minus F K-1。

 Like， there's nothing special about K versus K-1 as an index。

 So you can just keep doing this forever。 until you reach like F 0。Right， so this is less than bh。

 bh， b， less than gamma to the power of K Q star minus F 0。Okay， and if we use zero neutralization。

 this is just  Q star。 And Q star infinite norm is just like。

 what's an upper bound on the maximum value of Q star。

 And we already know that all discounted return is bounded by like R max or this is less than V max。

 which is defined as R max over1 minus gamma。Right， so whatever。

 like it's a constant independent of K。 So what really like controls convergence is really this gama to the K term。

 which is like like really like there are many different ways people call it like really。

 this is kind like is like exponentially decay like decaying like a geometric sequence。

 which is very fast。 But somehow optimization， sometimes people call this linear convergence。

 And I think like linear there means that and again。

 like this terminology comes from numerical analysis when they say， oh。

 when you converge like how accurate like how many digits can you get correctly， right？

 And like basically saying that the number of digits you get correctly。

 grows linearly with the number of with the number of iterations。

 But if you think about the accuracy you're getting， if you're getting n digits correctly。

 your error is like 10 to the minus number of digits。

 So your error is actually decaying like exponentially as shown over here so。😊。

So don't be surprised if you read from optimization literature that this is called linear convergence。

 though I think that's pretty confusing。 and I would still just call it like exponential convergence。

Okay， but anyway， like so。So you get this。 And this also tells you why the initialization F 0 doesn't matter。

Because so it only shows up in this constant。Right， if you choose something else。

 as long as it's bounded， you can always bound this term by triangular in quality。

 which is Q stars infinite norm plus F0 is infinite norm。

 So as long as you initialize to something that has reasonable infinite norm。

 like it's not gonna be a big deal。Any question about this proof？Now， I think。

A nice way to also understand this proof is also to visualize it， right。

 so we previously visualize the convertverse the， the contraction properties， right。

 So that says if you start with any F， you， let's say this is F 0。😊，And。When you get。

 this is T F1 is where you， sorry， it's T F 0， which is like F1。F1。

 and they differ by like when you apply T， you get T F 0， which is like F1， right。

 And the contraction property says that if you have another function， you apply T。

 you get somewhere that is like， you know， you get the the the T F and T F theilta like closer to each other。

 right， But here， essentially what happens in this proof is that for the other function。

 we're choosing a very special point， which is Q star。😊。

RightAnd the reason is because every time you apply T， you get back to yourself。

But you can still apply the contraction property， which hotel you that。

This distance is smaller than the earlier distance。So overall。

 this test must shrink like exponentially。As you do， more and more iterations。Okay。

And the other thing I need to comment on over here is that as I mentioned earlier。 So， first of all。

 I only gave you intuition for why Bman alpha equation holds， but it didn't give you a proof。

 So there's already that。 But also similar to before。

 it's relatively easy to establish that like Q star star V star sat these equations。 know。

 this is similar to know what we did before for V pi， right。

 we said that if you define value function to be the discounted sum of total。

 we know that value function V pi satisfies the equation。

 But we like until we show the invertability of that I minusma P pi matrix。

 we didn't prove that the equation for policy valuation has a unique solution。😊，Similar similar。

 similarly here， it's easy to establish that， you know。

 Q star and V star are the fixed point of these equations。

 but you know who knows whether they are the only unique fixed point。😡，But actually。

 if you look at the prove the analysis of this valuation algorithm。

 it already tells you that there's only one single fixed， unique solution to these to this equation。

 because when we did this proof。😊，What's the only property of Qstar that we used？😡。

Its the fixed point of key， right， or to， to say it more accurately is a fixed point of T。Right。

 as long as it's a fixed point， you know， like we said that fixed point， right。

 like it could be that there's Q star equals Q star。 Maybe there's something else。

 let's say called Q star tuta that is different from  Q star that also satisfy this equation。

 Who knows， right？ But as long as your a fixed point of T。This analysis holds， right。

 Because all we need is Q star equals T Q star。But then what this analysis says is that if you start from F0 arbitrarily。

 you run this algorithm， eventually you will converge to Q star。😡。

So then like it's impossible for Qs for T to have multiple fixed points。

 because if you have multiple fixed points， I have a deterministic sequence of functions。

 And I said that eventually this function is going converge to the fixed point  Q star。

 It can simultaneously converge to multiple points。

Right so the only like the only conclusion that wouldn't cause any conflicts is that there's only one single fixed point。

For for this operator。And this also established that also establish that the but of equations。Also。

 have a unique fixed point。Which is you， Q star。快审。Right， so that part is skip。 right， So it's。

 it's similar to the， the way you prove it is similar to the， So， as I said， that part is like， it's。

 it's， it's not， it's not difficult， but it's like very involved and complicated。 And I would say。

 at least I personally don't get much from it。 But if you remember how we did the。

Po B equation for policy evaluation， right？ We first defined V pi。So V， this object always exists。

Okay， then you say， oh， by the way， this function satisfied this property V pi equals you know。

 R R S pi plus like the。 Sorry， the equation for policy evaluation。 So when do it in this way。

 you know， the equation for policy evaluation automatically has a solution。😊，So here， okay， so here。

 if you want to follow that logic， you do kind of like。The， the， the。

 the more rigorous way of doing it is similar。 So what you do is that let's say for V star。

 you can define it in a similar way that says this is max over all policy pi a expectation over pi。呃。

Discounted R T S1 equals S。T equals one to infinite。And here pie， because we don't know that。

 you know， if， if you don't take if we don't know yet that， you know。

 the optimal policy take the form of like mark of deterministic policy。

 you can even allow the policy here to be all possible policies like all possible history， dependent。

 randomized policies。 So if you define the define the V star in this way， it always exist。Right。

 and then you use a similar strategy， as we showed before。

 to establish that the B opt equation is a consequence or property of this V star。

So then the B of my equation will always have at least one solution。Does that make sense？No。

 like if I write in this way， like right hand side is just literally a definition。

It it's not says like I write on equation that may or may not have a。

 So like if you write it as an equation that is like this kind of a fixed one where a function exists both on the left hand side or on and on the right hand side。

 Sometimes maybe may not have a solution。 something has multiple solutions and so on and so forth。

 But if it defined in this way。 right hand side doesn't have V star。

 The right hand side is like well defined。 You， you， you consider all possible ways of behaving。

 Each possible ways of behavior will give you a number， which is like how good it is。

 and just take max over all these numbers。 Well， eventually you just get a number。

You you assign that number to each state。 Then you get the definition of a visa。

So if you define B star in this way， like， it always exists。Okay， and then you in and， and。

 and what you need to do is to prove that the bowumman of themal equation。

 the recursive relationship is， is a property of this definition。So it's， it's the same。

 that's why I said it's the same template as the Belman equation for policy evaluation。

 That one is simpler， more intuitive and gives you whatever insight I think you need to need。

 You need to know。 So I went through that one more carefully。 This one is more involved。 I I don't。

 I really don't want to want to go over that。 But if you trust me that that's how you do it。😊，Okay。

 any questions so far？Yep。Ms。TQ start here。Satied。嗯哼。It feels like I must go from the right to the。

No， this， this operator is just defined in this way。 Again， this is the definition。

 What do you mean by the。operatorator is mapping from any function to another function。Right， so。

 so when you do it， it is like you take Q star as an input and a。TQ gives you another。Function。

 which is Q star。How to。So maybe， so maybe here is a like， I guess it's， it's。It's， again， like。

Like when you think about this equation， like it's， it's。

 it's similar to the equation for policy evaluation。 That is you， when we talk about like。

This equation， we're solving for this equation。 you should treat Q star as an unknown。😡。

Right it's not something like something you， you don't know yet。

 But this operator is something you know， right， This operator is like， like。

 forget about the definition of Q star。 forgetge about optimal， forget about anything else。

 If I give you the MP， which means R of S and P of S。 And Ill tell you， this is an operator。

 Is this operator well defined。😡，It is well defined， right。

 like I don't even have the concept of Q star， this operator exists independently。😡。

And similar to what I said， like it just happens to be the case that Q star is the fixed point or is a fixed point of this operator。

Right， so if Q star satisfied this bump automatic equation， you look at the right hand side。 Oh。

 this looks like the operator applied to Q star。 So then Q star is a fixed point of this operator。So。

 I don't know where you're getting stuck。 Maybe I'm guessing you're getting star stuck like just conceptually or mentally。

 like， does Q star exist first or does the operator exist first。But， but I mean。

 the definition here tells you that the this operator exists independent of， you know。

 the concept of Q star。If that helps。Question。So I don't know if you need to in invoke the definition of cost sequence or whatever。

 like， cause to me， like。To me， like this is a way part。 So， okay， Ca sequence and all of like， okay。

 so if， if I remember， like， you know， I， I， I said something like。

If you look at a perox I said a linear linear algebra and probability are the most important。

 calculus is less important， right， And I said， like， you know。

 I hate continuous spaces and all of that。 And things like， you know。

 like these two limits concepts involving like limits in in the limit of like， you know， infinity。

 they are also things that I don't like， or I think it's less important over here， right。

 So I think when you talk about co sequence and so on like you really talking about that， you know。

 limit behavior in the limit of like infinite number of iterations。😊，Like。

 when are you going to run an algorithm to infinite number of iterations？是。But， but as I said。

 like the， like， you know， okay， so as I mentioned earlier， like， I。

 I say that you should treat like the correct way to do this is to define Q star and V star like this way。

 So it， it existence happens first。Okay。Now， I'm not sure。

 So if there may be a way to do it to say if you define it in this way and you use the property of the operator to argue that it always exists。

 Like， maybe there's a， I don't know like probably something like the Bax fixed point The may give you that。

 I'm not exactly sure that if that， like， that's another plausible way to establish it。Okay。

 but but not through like。嗯。But not through this analysis。😡，Not through this proof， right。

 Because in this proof， we need to substitute F Q star with T Q star。

 So it already presumes that a fixed point exists。 So you can't use this result to show that。

Qstar exists。Right， so， so， yeah， maybe， I think， yeah， maybe that's。嗯。I see。

 So you're saying like in in the limit， you get， you get a function that is like a fixed point of the。

 of this operator。Okay， so。So we have this。 and， but we didn't finish the proof yet， right。

 what we are missing。Well， we didn't improve thelema。

 We didn't prove that the operator is got much contraction yet。Right， so we're going to do that。

So say that for any two functions， you measure the difference。

 and then you measure the difference after applying the T operator to both of them。

 and then you you show that it it's smaller。呃 one thing呃。Oh speakingking of this operator， one thing。

 there's a notational thing that I think is very important。

 And I think it also if you pay attention to this detail。

 it also helps you understand why its a operator in a like more intuitive and deeper sense is that you sometimes see people in the literature would write T F SA。

Okay， I strongly encourage you to not write like this。Because it's very easy to misread。

It as F of S A and then T。RightIt's it's as if you first evaluate F in some S and then apply something to what we should just give you a single number。

 a real number， and then you apply something to that。Right， but rather here what we what。

 what happens is that we first take the entire function as input， do some transformation to that。

 get another function。 and then we evaluate the final function at S。And what's very important。

 you know， there's a conceptual， like there are many difference here。 For example， like。

 if you think about T as a mapping from RA to RA， if you first evaluate S and F。

 you get a single scalear， it doesn't even match the input format of T， right。

 So there are these like very basic differences that to make that that interpretation。

 like not making any sense in the first place。 But if even if you ignore that。

 there's something that is conceptually important， which is So if， if you treat it in this way。

 it's like for this given F， when you ask what's the， what's the final T F on S。

 is's as if you only need the information of F on S。😊，Okay， as if like， if you。

 if you see it in in your first plan， that， that would be your first reaction。

But if you actually look at this definition， this is not the case， right？You apply T to F。

 and then you ask， what's the value on essay， So youll query a particular state action pair。

What information about F do you need？😡，While you query F over here。😡，And your query F on S prime。

 which is potentially different from S。And in particular。

 if your state action here has a distribution of states that is supported on many。

 many different states， then you may need like the information of F on many， many other states。

Rather than just F of SA itself。Okay， does that make sense。Right。

 so I think this really tells you like， you know， why， you know。

 sometimes people write in this way and they say， oh。

 you just read it in this way like T F then F S A。 But I think that really sets up the wrong mentality。

 right， like and so I like to write this way or you can use like square bracket or whatever。

 But the key thing is that you want to separate out F from S A to avoid the impression that you're just first evaluating F on S A and only take taking that one single real number of F。

 And that allows you to， to to， to define the outcome of T of TF of S A。 That's not the case。😊，Okay。

Okay， so dilemma。Prove of a contraction。So。So as usual， we start from the left hand side。

 T of F minus T of F tilde infinite norm， right， and F and F tilor are just two arbitrary functions over the action pairs。

So what we do what we just， So we want to bound this， right， So instead， I'm gonna bound。嗯。Oops。

I'm gonna bound the difference。 So previously， we see the difference between two function taking infinite norm。

 right， What is the infinite norm， Infin norm is just the。

 the function of the vector on every possible input。

 you take the absolute value and then take the max。 You want that to be upper bounded。

But if I can show you that。Every single coordinate。Has this absolute value bounded by something。

 Then the even Nor is naturally also bounded by the same thing。Right。

So I'm going to bound this instead。So then what we do is just to record the definition。

 The definition is R of S plus gamma expectation as prime P of S。maxax。Over a prime。

F of S prime a prime。Okay， so this is the。The first operator。

Minus RA minus gamma in expectation as prime。PSA。Max a prime。Have tude as prime a prime。O。

So what do you do first？You cancel the rewards， right， So this cancel。And then can combine something。

The expectation theyre， theyre with respect to the same expectation。 So you can just combine them。

 And there's a gamma factor， which we love， because we want that to show up on the right hand side so we can extract that out。

 So we have expectation of S prime。😊，P of S。Max over a prime F S prime a prime minus。

Max over a prime F tuta S prime a prime。Okay。So we have that。So this is an equal s。

 one thing I want to mention here is that I have two max over a prime。

 So although I call both of them a prime， they are actually different variables， right。

 So cause they're optimizing different functions。 So the。

 the a max that they achieves the maximum have may be different from the a mass over here。

 Although I I， I， I use the same a prime。😊，Okay。😊，So then what I'm going to do is that first， I can。

Push the the absolute value inside。Right，The absolute value of expectation is always less than or equal to the expectation of absolute value。

Right，And in fact， if want to be more， know， like sophisticated。

 There's like absolute values a Comx function。 And so when you push it inside。

 it's actually a form of ks。But that this should be pretty obvious because like when you take the expectation。

 like playing expectation， you have like positive and negative terms inside the expectation that may cancel out with each other。

 But when you push the absolute value inside， you turn all those values in like all the negative values into positive values。

 So you don't have any cancellation anymore， right， So it should be pretty obvious。😊，Okay。

 and then then what we do is going to do less than or equal to。Max over S prime， right， So we， we。

 we already used this property last time when we proved the invertability of I minus gamma P pi。

 right， when you have expectation， expectation can never exceed maximum。

So instead of taking inspection， I'm just gonna do something pretty crude。 right。

 I'm gonna to do the maximum a prime。Maxum。A prime。As prime Aproron。Okay。Further。

 this is less than or equal to gamma。So I claim that this is less than or equal to S prime a prime。

F prime。Okay， so this step is not established and it's not obvious。😡，Okay， but。

 but let me explain what I did over here， Right， So so here it' saying that， okay。

 I look at the maximum value between of F of reactions for fixed point state S prime and then the maximum value over F tuta of of F tuta。

 right， as I mentioned， like the， the， the action that maximize them may be different。😊，Right。

 and you compare the difference。So you actually compared the difference between F and F2 to。

 but evaluated at different actions。Okay， but now in the second equation， what I'm saying is that。

 oh， you can actually scan over all possible actions。

 but always compare the two functions at the same action。

 Look at their difference and take the worst case actions。 And it's the upper bound of that。Okay。

 so this is a non trivialal step， which we will establish you know， shortly afterwards。

 But if you have that， were I say that we're done。开始。Yeah， they are two different。 like， actually。

 like， yeah， this a prime， this a prime is generally like， you know， like if， if you want。

 I can call this a double prime。 and this is double prime。But because they're。

 they're separate in two terms。 I think it's acceptable that it it's also。

 you can also just write in the way I write it。 But。

 but if you really want to make avoid any confusion， you would write in this way。O。And。

 and the tricky thing here is that the arc max for this one is different from generally different from the arc max for this one。

 which is further different than the arc max for this one。Okay， but we still have this relationship。

Which， but again， take it for now。 if this host， I say we're dumb because what is this。

What is this expression？This is the even norm of。F minus f tilta。Right， you have gamma times。

TheF minus f tta。Which is sorry。Which is exactly the right head eye。Right， so there。

 therefore we're done up to that question mark。Okay， so now let me show you the question mark。

 And in fact， this， this question mark， there' is a separate max over S prime over here。

 We actually don't need to worry about that because in the sense that we're gonna establish is actually a stronger result than this line to this line because we're gonna show that for every fixed S prime。

 The expression here is upper bound by expression over here。 maxed over a prime。😊，Right， so if you。

 if you have this pointwise for every S prime， for every S prime， then you take max over here。

 take max over S prime over here， the， the， the relationship should still hold。Okay， so。

We want to show。Want to show。AF S prime。呃。Let's call。呃。呃。有的。We have a max。Over a prime。呃，F。

So I'm gonna put S prime from here input to a subscript， because now we're fixing S prime。

 So like when， when we establish this relationship， it's all about how do you maximizing。

 how do you max over actions。 The state is always fixed。

 So the fact that state is an input to the function is very not important over here。

 So I'm gonna just change the notation and put， put S prime temporarily down to the subscript just to。

 you know， make it less prominent。😊，Okay， so you have a prime minus F tilde。As prime。A tuta， sorry。

 you have a max over a here。Minus。Max over a prime here。And it's less than。Max a prime。FS prime。

 a prime。Minus f tuda S prime。April。O。And another way to say it is really like， so here like this。

 this result is ho when you treat F S prime and F S Prime tuta as to arbitrary real value function over the action space。

Yeah， maybe it's actually better to write it as like let's just call this G1 and maybe G and G2。Okay。

So how do you prove this， Well， again， like by， you know。

 I think this is best illustrated by visualization。Now， we're considering finite spaces。

 But for the purpose of this visualization， I'm gonna pretend that the action space is the is the is the is one dimensional like real axis。

 just for illustration purposes。 So the X axis is this action space。 And you have two functions。

 G and G prime。 Maybe G looks like this。 And I don't know。 G prime looks like this。😊。

Let's say this is a G。 This one is G sorry， not G prime G tta。Okay。

 so what is the left and side talking about， right？

 So left and side says find a maximum value for each function separately。

The first maximum value is over here。This is the max of G and this is the max of G Tota。

And measure their difference。Okay， and。You do this。呃。So this is that you care about。Right。

 but but how would we want to bound it， what we want to upper bound it with。

 what we want to upper bound it with is we're going to scan over all possible a prime。

And a measure that this end over here。Right， we want to measure the distance between the two functions。

嗯。Sorry。On any。On any fixed a prime right on the same vertical axis and say what's the difference over here。

 we scan over the entire input space and find the maximum value。😡。

And we claim that the latter is like greater than or equal to this difference。Okay。

 so now if you look at this figure。呃。Like， my claim is that there is a particular way to choose a prime such that this gap is guaranteed to be greater than this gap。

 Where would you choose this a prime。Arms of who。this is a spoiler okay。

 so if you look at it over here。RightSo the way I'm going to choose it。嗯。I's this one。Right。

 because this one， you get a gap of， you know。You get a gap of this large。

Which is clearly greater than or equal to this large。Right， and in fact。

 like thats a what to my next question is， okay， so this is the agon max of G。 But why is the G。

 right？ Like， as you can imagine， like， you know， So in this lemma。

 G and G Theta seems to be like completely symmetric。 They are on equal footing。😊，But clearly。

 like in this particular example， I can't choose it to be this one。Right， I I I。

I can choose it to be the argumentss of。Of of Gqda， because then I would get this gap over here。

Right， and depending on the shape of G， it could be very well the case that this gap is less than。

This gap。Right， so what makes the agonax of G more special than the agonmax of G Tilta。

Because G's peak value is higher than Gqta's peak value， right。

 So as long as you like you choose a prime to be the R max of the higher curve。

And then this will work。Right， so here's the way to prove it。 So without loss of generality， assume。

That max a prime G of a prime is greater than equal to max a prime G tilta a prime， right。

 Because G and G theilta are on equal footing， we can always assume that just like like one of one of thems maximum value will all be。

 will always be greater than or equal to the other， right， if this doesn't hold。

 we just swap the row of G and G theilta。 But if without loss of generally， we assume in this way。

 then it makes the situation align with our visualization over here。Right。

 so then the left hand side， which is this is just the。 And then also。

 let's call a star is the R max。 Let's see A star of G。Agon max a prime G of a prime。Right。

 so then this is。This is A G star。Right， then the first equation is just the G of A G star minus。

Max over a prime。G of apri。Right， the left hand side is this。

 And I don't need absolute value anymore because I've already assumed that the first term is greater than or equal to the second term。

 So I can take away the maximum absolute value。And then because I define A G star to be the arc max of G。

 So max over G is just G evaluated at the arc max。Right。

 and then this is a less than or equal to G of A G star minus。 So I want to relax this。

 What I'm gonna to do is I'm gonna relax this term。 right， So there's a minus sign here。

 So here this is the max。 So if I change like the where I evaluate G to any other action。

 it can only make this term。😊，Can only make this term smaller。And because there is a negative sign。

 it can only make the whole thing bigger。😡，Right， and where do I want to evaluate the action instead that。

AG star right A G star。And I said， this is less than。Max over a prime。呃，sorry， this is G two的。

 forgot got it。G， A prime minus G2 to a prime。我的。Okay。So this established the contraction property。

And we've already shown that once you have contraction。

 it gives you this convergence rate proof for the value ocean algorithm。Okay， so。呃。

So I think that's the main proofs we're gonna we're doing today。

 And we have a few just comments without any proofs。 I guess you probably had enough proof today。

 but， but just a few like side comments about this algorithm and a bunch of related properties。

 right， Okay， so remarks。So first of all， as I said， we。

 we can also write the automatic equation for V star。 as a fixed point equation。 And here。

 remember T is an aive notation。 It whatever the right hand side of the V star equation。

 you swap out the V star plug in an arbitrary like input function。 You define an operator out of it。

 And then you read the equation as a fixed point for。😊，RightAnd if you want to solve this equation。

 you do exactly the same thing。 You start with any arbitrary function over stay space。

 Just keep applying the T operator。Okay， and in convergence。

 and it can show exactly the same way that the T operator follows the it also satisfy the contraction property under infinite norm。

 But in this case， the infinite norm is the infinite norm in the R S space， not RA anymore。😊，Right。

But however， if you look at the proof， the proof is， is spirit almost identical。So that's why we， we。

 we won't really talk about this too much。 But the， the， the。

 the evaluation algorithm and the analysis， they're all very similar to what we have。

 what we have done。 If you want， like， you can do a little you know， exercise to， to see it yourself。

Okay， as a second point。We've seen this Belman。Bman equation for policy evaluation。Right。

 so this is the Bel equation for policy evaluation for V pie。 And the way we solve this say， oh。

 this is a linear equation。 we can move this left hand and then do matrixing version。😊，Now。

 as it turns out。You can also do the same thing。Define T pi for any f in R of S。T pi of F of S。

Is R pi plus gamma P pi F。Okay， so again you define an operator T pi that maps state value functions to stay value functions。

 So take arbitrary F as input。You get another function， which is like just the eal vector。

 which is on the right right hand side。 Okay， so can you guess why do we do that。Why do we do that？

If I define our operator T pi in this way。😡，What can you do with it？😡，Right。

 so so basically if you have this definition then。V派 equalsT派 v派。Right， so。

You can also write the Obama equation for policy evaluation as a fixed point。fixed point equation。

Okay， and guess what。 You can also establish T pie as a gamma contraction。

Which means instead of doing matrix inverse， you can also solve for V pi using a value duration like procedure。

 Start with any function。 but keep applying the operator。 But this time， the operator is not T。 Okay。

 it's T pi。 So the operator is simply take your vector over here。

 multiied with the transition matrix for policy pi times gamma time plus a the reward vector。

 Then you get a new new new function， keep doing that again and again and again again。😊。

 and this is also this T high also satisfy the contraction property。

 which means that it has basically almost the same kind of convergence behavior similar to the one we analyze over here。

😡，And just notation wise， note that the T operator doesn't have any superscript or whatever。

 So that operator is reserved for the optimality equation that that that operator describes the optimal behavior in this MP。

But T pie， remember， this is for a specific given policy。

 You give me a policy that describes a specific ways of taking ashes。 I tell you how good it is。

 So T pie is an operator that is generally different from the T operator。 And in fact。

 if you look at the form of this operator， This operator is actually a fine operator， right。

 So it involves a matrix operator matrix modification。

 which is a linear transformation up to an off centerer。😊，Okay， so this is the second。Second thing。

The third comment is that we've seen a a set of concepts like and definitions， right。

 we start with V pi。Which is the。Fix the。You know， the the v pi of S。And that satisfy the。呃Butman呃。

But my equation for policy valuation， right， Then we see V star of S。V star is TVV star。

We have Q star of S。Q star equals T， Q star。 Now， these are not quite the same。 You know， it's。

 again， this aive notation。 Do you see something that is missing over here。

You have V pi for any given pi。 You have V star。 You have Q star。WhatWhat are we missing？

We're missing Q high， right， So like for now， we're just going define it。

Without any of obvious reason other than just， you know， make things complete。

 But it turns out cubepi is a very important and useful concept later。 But for now。

 we're just gonna define it just to make this table complete。 right， So what is Q pi。 While Q pi。

 you can define it in two ways。' very similar to， you know， the V Pi case。

 So you can define it in a way that is。In terms of expected discounted reward， which is expectation。

 when you take action according to policy pi or I will be more specific later on。

 when you take actions according to pi， discounted sum of rewards sorry。T equals 1 to infinity。

 gamma t -1 R sub T S 1 is a。 The first action is a。And。You take the。 So here I'm writing a。

A two comm infinity， which is an arevation for action to action story all the way to。the。

 the all the possible actions all the way to infinity。 you take all those actions。

 according to policy pie。Right， you start with a particular state S。

 Your first action is forced to take action A。 but afterwards， you take actions according to5。

 So that will specify the entire behavior， the entire distribution of your trajectory。

 under that distribution， you take the expected sum of disc rewards。Okay。

 so this is one definition of Q pi of S similar to v pi， it also satis a。啊，标 my equation。😊。

S of R of S plus gamma expectation as prime P of。SA， right。

 So so let's let's walk through this and try to use your intuition to guess like what。

 what it should look like， right， So what is Q pi saying， Q pi saying that I mean as。

 I'm gonna take whatever action you tell me to for the first step。 But afterwards。

 I'm gonna take my the action According to the policy pi that is on the superscript。😊，Okay。

 so then less's reason about what's the total rewards I can get。 Well， because I mean S， I mean A。

 So the first reward is independent of pi It's just R of S because S and A are both fixed。

The transition as prime is also drawn from P of S A。 Again， S A are fixed。

 So this transition is also independent of pi。Okay， but from their own words， starting from S prime。

 I'm going to behave according to policy pi。 So what should I put over here。😡，Right， so we can。

 How about you express that as V first。V pi S prime， right， So this is v pi of S prime。Right。

 because from S prime onward， I'm gonna always take action according to pi andm asking myself。

 what's the expected return I'm gonna get from state S prime onwards。

 What we have a definition for that is called V pi。Right， but as usual。

 here we may want to make it an equation that is only about coupon， right， So therefore you need to。

Change V pi into a equation of into a a function of Q pi。 How do you do it。Okay。

 I'm gonna in the interest time， I'm gonna just do it myself。 So this is just。Sorry。Right。

Because Q pi is saying， oh， the， the first action I'm going to take it arbitrarily。

 like in whatever way you tell me to from the second action onwards。

 I'm always going to take take an action according to pi。😡。

V pi is saying that I always want to take actions according to pi。

 So there are differences basically like Q pi has its first action that is not fixed yet。Okay。

 and to align them to make them the same。 All you need to do is to take Q pi and to tell Q pi your first action。

 please also take according to pi。 Well， if you do that， you're no different from V pi。

 because V pi always take action according to pi。O。So， so this is the primary equation for Q pi。

 And as usual， as we have done like multiple times， you can define the right hand side as a。

Oma operator， again， we're gonna abuse notation called that T pi。 It's a。 It's a contraction。

 You can have a value to algorithm in has conversionence properties similar to what we did earlier today。

Okay。Okay， so， you know， and one thing you can do is to compare this。

Which is the about my equation for policy evaluation with。

Theman optimality equation and look at their difference， right。

 So the difference is that the optimal equation choose the action by taking max over a prime， right。

 It doesn't need you to tell it a behavior。 It， It doesn't need an input of a policy pie because it's computing for the optimality。

And it has this max of a prime， which is what gives it nonlinearity。And that's why like， you know。

 we， we， we don't， we can't do use like， you know， matrix inverse or， you know。

 something like that to solve the automatic equation because it's not a linear set of equations。

 It has a max in it that that， that breaks the linearity。In contrast。

 the B equation for policy evaluation。 This is a set of linear equations， right。

 And you don't have max。 And instead， because this is evaluating a particular given policy。

 So that policy。Must appear somewhere in the， in the equation， Right。

 Like the superscript pi here doesn't count because this is， if you think about it。

 this is kind of like the unknown know you're trying to solve from this equations。 right。

 The pi must appear somewhere else。Where does it apply， Where does it appear。

 Why it appear over here。In your action selection， instead of like choosing action， you know。

 as a max， like as a gratification， like as a maximum， which correspond to maximizing reward here。

 you're just choosing action according to， you know， how you total do right。

 And if you're choosing action according to pi， this equation evaluate how good pi is。😊，Okay。

 so that's for today and。That's it。 And I'll stay for a little longer for questions。 And otherwise。

 I'll see you on Wednesday。And I will upload today's this writing P D F to the course website。Con。

Cverence of this one， yes。Actually， for this part。Actually， we cannot directly say。

 I want to prove the convergence。 It should be。 I want to see if there can be a convergence because at this point。

 we don't know thats right， right it's only like the unique solution。

 that's exactly what I said like so for this prove to。

