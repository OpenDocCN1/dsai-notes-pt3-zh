# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p36 P36 贝尔曼秩 -BV1YsZHBZEyM_p36-

Okay， let's start。 So we've seeing the。we've seen the analysis of our max in the last lecture。

 So this is like the happener setting right and。The immediate like next question is。

 can we do it like more journal？Okay。嗯。You， especially when you have like， you know， large functions。

 large say spaces with function approximation， which is like more likely what you run into a practice。

 Now， I mentioned this before that if you look at most standard。Algorithm people use nowadays。

 almost none of them would solve the like。Like combination lock that we give at the beginning。

 But apparently， like， you know， that example will be trivial trivially solved by， you know。

 something like a standard like depth for search or or even a star， which you know。

 we now know is essentially。Like very similar to Rm。Okay， so， so which makes you wonder like。

 you know if。As well see today， like we can establish a。

 we can establish a theory for exploration of general function approximation， but apparently。

 there will be difficulties in translating the theoretical algorithms。

 analysis and insights into practice。😊，Okay， so， you know。

 that's one thing like I hope you to notice is like， you know， as we like try to establish this and。

 and we'll see like there are still like limitations of the theory that actually tells you know why exploration is so hard in practice that we just don't have like an off the shelf algorithm that you can just sort it at at different problems that it just solve these like sparse would hard explore problem。

 like， you know， immediately。😊，Okay， so let's start。So this is slide。

 So like if you really think about it， like so， so this is。Like in old school R O。

 like people say that R O has three core challenges where you have how to put it， so。

It's it's really about three core challenges in online， right， So where you need long term planning。

 So we started there at the very beginning of the class when we started talking about planning。

 valuation， you know， right， like how to optimize long term returns， right。

 So this is the first challenge。😊，And sometimes people call it a， you know， the。

 the so calledled a temporal credit assignment problem， where it's like when you play chess。

 you play many moves。 And let's say you win at the end of the day。 Like which move or maybe you lose。

 Okay， maybe you lose the game。Now， it could be very well that all your moves are done right。

 and only one of the moves was bad。😡，And that that single bad move could just cost you the whole game。

The question is， after you play the game， how do you know like which move was right and which move was wrong？

Okay， so this is called the temporal credit assignment。 Credit is like， you know。

 whether you win or lose at the end， assignment is like。I won。 I lost because I did this earlier。

 So this is a credit assignment problem。 Temp says that， well， there's a sequential。 Like。

 there's a time aspect to it that you take decisions in like in a sequential manner。

 So it's called temporal credit assignment。 Okay， and now we know that basically， like in。

 we have all the right tools to answer these questions， right， you know， Q functions and and。

 and you know， value functions about my equation and on so forth。 right。

 So that's where we started in this course。Right， and then for a long time。

 we actually didn't care about exploration， right， especially in online R。

 We only look at long term planning， like， you know， planning。

 together with large say spaces that require generalization， right。

 So when we did this theions for the Q and all of that。 we're essentially like， you know。

 handling these two。 And and this， this topic has been like study for a long time。

 like in the old R literature it's no under the notion of approximate dynamic programming， right。

 you know， nowadays， it's pretty much what the R is about。😊，Under the hand， you can also study。

 So this is what we did recently where we say， okay， we want to do。

Handle MPs where you have large where you have finance more， sorry。

 where you need to do long term planning。 But we also want to do good exploration。

So the RMX analysis exactly fit into the combination of these two concepts。😡，At the same time。

 we didn't do this thing in this class， but you can also ignore long term planning and only ask you how can you do generalization and exploration at the same time while ignoring the long term planning aspect。

 so this will be connection bandits。Right， so you have one short decision making problem。

 So you don't have like long horizon decision making。

 but then you maybe you have a large contact space and you need to do exploration。

 So this is out of the scope of our work。 but of our course。 But this is being studied。

 So really like what has been missing for quite some time in the community was like， you know。

 like if you think about the core of online， It should be like all of these three elements together。

 right， you want a single theoretical framework that like handles challenging problem that involves all three elements。

The thing is that for each of the elements， we kind of know the key idea of like know what's going on。

 And for example， we want to solve longterm planning use dynamic programming based on Bel equation for generalization。

 know we have supervised learning。 know we introduce functional approximation And the key concept that eventually will go into our bound is things like statistical complexity like V dimension or in our class if you have a finite function class。

 just pay the logarithmic size of the function class So that's the statistical dimension or complexity。

 And for exploration， we just introduced optimism in face of uncertainty that helps you exploring band or tableular NDP。

😊，The thing is that you know， once you put all these ideas and concept together。

 it still doesn't quite tell you you know how you should actually explore or when is exploration even feasible when you have all three challenges together。

Okay， so this is an example where we showed that so this is like a variant of combination log。

 where it's not finite horizon， but like infinite horizon。

 where if you remember our finite horizon version is like， if you take the wrong action。

 you go to the bad chain， right， So in this version of the combination log。

 I think this is the one that appeared originally in Shata thesis is like if you ever take a wrong action。

 you go back to the original state。 So it's similar construction。 Okay， and someone as like。

 I think on the on that day as like whether this is real。 And so theres a kind of semi real example。

😊，Let me see。 Can I。Okay， yeah， so this is the the freeway。 one of the art games。

 So youre this little yellow chicken here。 You， your goal is to cross the street to get a big red reward at the other side of the street。

 But if you ever run into a car， you get killed and immediately send back。

 youre sent back to the your starting point。 And if you think like this is basically a version of the this problem。

 And without any reward hacking without any kind of trick。

 if you just let the thing explore on its own。 this is like the training process。 Okay。

 so you do random exploration。 You take actions randomly。

 You just get killed again again and again again。😊。

Like if if check if you get lucky after a long time， long time， you see once you reach the end。

 you say， oh， there's a reward there。 Okay， but before you do that。

 if all you do is to random take ashes and get killed and potentially you get a negative negative reward because of that。

 What do you learn about the environment。 All you learn about this environment is they say， oh。

 the street is so so dangerous。 If I try to cross the street。

 I get killed and it's painful and it's awful。 Why not I just stay over here and not move at all。

That's the logical conclusion， right， Like， you know。

 who knows there's a big reward at the other side of the street。 Theres a red dot there。

 but does that mean anything， It it's unclear， right。

So and this is also like maybe one time that you can use to reflect on， you know。

 as a sort of practical problems。 like you can solve it in many different ways。

 Like one way as we will try to thinking about it is to think of it as like really hard exploration problem。

 and we try to solve it from scratch。 But in practice。

 you may say maybe we gonna solve this with additional side formation， right。

 So maybe as a human player， you play other games。 you do some transfer learning。

 you have some basic concepts of how games are designed。 So maybe you can guess like， oh。

 maybe that red dot is like really something rewarding。

 So let's try cross the street and see what awaits us on the other side of the street， right。

 So there are different ways that you can solve this。 But in our context， we will say， okay。

 let's just try to solve these kind of hard problems。😊，Okay。

 so and previously we already know that in the tableular setting， exploration is possible， right。

 and particular， sample complexity depends on among other things， the number states。😊。

AndAnd apparently this is not like scalable if you have like a really large state spaces。

 we know that you can't afford to pay the number of states in the sample complexity guarantee。Okay。

 but now we， we have studied。RL in large safe spaces in the offline part， right？ So how did we。

Handle large state spaces there and avoid paying number of stays in our guarantee。 What did we do。

Right，So suppose this is the offline row， right， Like let's say you have a large， huge state space。

 you get some data and you want to compute a good policy。 What do you do to avoid paying ads。

Abstraction is the like， yeah， abstraction is one way， right。

 abstracttraction is something a special case of what what's the more general。thing you do。Funal pro。

 right， So abstraction is a special case of function pro。 So by using function pro。

 you hope that your function space， say captures the， you know。

 let's say Q star or whatever you want to learn。 And we know that that's typically not enough。

 you need like the assume complete。 But that's fine。 And then in that case。

 instead of pay number of states， you pay like， say log F。

 which is like the statistical complexity of your function class， right， And if you think about it。

 it really subsumes and generalize the tableular case， right， because in the tableular case。😊。

Implicitly we're using implicitly， we're basically still doing functional prosrbation。😡。

It's just that our function class is the space of all possible functions over this state action space。

 right， So tablecase is kind of like F is equal to R to the S times a， right。

 or or maybe like0 to V max。😊，To R time S times a， right， the space of all。

 you think about all like you can even view it as like a special case of linear function pro。

 right because you have one hot feature as you， you have one hot feature where for each state action pair。

 there is a feature that is only equals that that that equals one that that is only activeed for that feature right。

 So we're essentially implicitly working with this function class。 Now。

 by using a standard disization and parameter counting argument。

 what is the effective log size of this class。😊，So suppose you discretize the number of possible values into a discreted grid。

 what's the log size of this class？Should be pretty straightforward。Yeah， S times A log log。

 like something like the log， the， the disretization resolution， right， But。

 but the main term is S times A。So one way to think about it is that if you see S times a in the offline analysis in the table analysis。

 you can basically view that as the instantiation of log F of general function approximation。

So to summarize in the offline case， we basically say， okay， to handle large state spaces， we。

We use function approximation， and we pay log F， and that will replace S times A。Or sometimes S。

 but anyway。O。So then the question is like， maybe we can do something similar here。 right。

 So we're gonna still use function。 We're gonna also use function transformation in on R and hope that instead of S。

 maybe we pay log F here and get a guarantee like this。Okay， so so that's kind of like， you know。

 without thinking about， you know you know， what algorithm we use。

 without thinking about what kind of model and assumption you're making going to make。

 we're first like just imagine like at the end of the day。

 what the kind of ideal of theoretical guarantees we want to arrive at。😡，Okay。Right， so that's。

 you know， the， the kind of question were on answer， right， So now。

 now to make that a little bit more formal， as I mentioned， will'll gradually。

 I think starting today， we're gonna be exclusively thinking about finite horizon MP。 Okay。

 so this will be a switch， because that's just much easier to think about when it comes to online exploration。

 so。😊，So for each episode， we are they seeing for H times H equals 1，2，3，4 and all the way to H。

 And at each time step， you observe a state or its feature。 So here I'm using x。

 although previous we use S。 You don't really。 it's just a convention problem。

 I have x in the set of sides。 So you have you have state or it's feature X right。

 in choosing an action。 And for now， let's say it's it's finite。😊，And they receive a reward。

And so on so forth， right And and then we know that the initial state is drawn from the initial state distribution or without loss of generality。

 let's say assume that we have a fixed known determine say initial state because because that's always without loss of generality because if you have like a real state distribution。

 you can always add a dummy state at a dummy time step at the beginning。

 And let's say in that dummy time step， time step 0， I have a fixed state。

 and there's only one action there。 and it transitions to the real initial state distribution， right。

 So either way， it's fine。😊，Okay， so， and then we know that starting from H equals 2。

 your next data X is sampled from the transition dynamics， right。

 And the reward is given by the reward function as so on so forth。 Okay。

 so all the standard MP formulation， which I didn't write out here， right。

 and So in this particular case， let's say we take the same setting as fitted Q where we say。

 let's say we have the function function class F that realize this  Q star because here like you remember。

 go， our goal is to actually learn the optimal policy。

 And if you use model if you use value based R chances are you want to learn  Q star and then induce this security policy。

 right。😊，Okay， so and this is just like， you know motivizing example like maybe in reality。

 F correspond to a parameterized class that correspond to a your dad or something。

 But for our analysis， again， like we're just gonna in the final analysis。

 we're just gonna assume finite that class and we pay log gap。😊，Okay。So again， like you know。

 at the end of the day， the kind of guarantee you want is with high probability。

 you find a policy pi that is epsilom optimal。What kind of guarantee is this？

Is this a regret guarantee or a sample complexity guarantee？We talk about these two concepts like。

 like， it's a sample called guarantee。 right， because it says at the end of the day。

 I'm not asking you to give me guarantee on the performance of intermediate pies that you use in exploration。

 right and。Right， so this is the sample complexity guarantee that ideally you would want， right。

 So you want previously you would pay polynomial in number of states。

 actions horizon when we like log one over deelta。 So here， like the goal is basically say。

 we drop S。 And we know we can't completely drop it。 So instead of just dropping S。

 we're gonna replace it with like log F。😊，Okay， does that make sense？

So this is kind of like the goal we want to achieve。Any question about this goal？Anyone。Good， cool。

Oh， so this is just saying like if you have the analysis well see if your f is continuous。

 you can use VC dimension， which is the standard measure of complexity for continuous function classes。

 So this is what you would learn if you take another s learning theory course like at the very beginning。

 you will use just the finite class and you pay law cardinality as we do here。

 But that's like you know the first two like youll do that within the first two weeks。

 And after that， you will study all kinds of more advanced measure like V dimension。

 rather about complexity， log covering number， which we'll talk about later in this in a week or so and many other more advanced measures of complexity but we're not gonna do that here。

😊，Okay， so and I've a news for you。 Okay， so this is impossible。Okay。

 so what we just said is actually impossible。 No algorithm。 And this is the information thetic。

 which means that no possible algorithm in the world can achieve this kind of guarantee。Okay。

 so let's look at the， let's look at the the， the proof of the lower bound。 Okay。

 so the lower bound is actually turns out to be extremely simple in terms of the construction。

 So it's just like exponential tree。 Okay， let's say you have two actions and it just like a bifurcating tree。

 So with like a non trivial horizon age。 We know the number of states you get And the number of nodes you get at the end is exponential。

 right， to the age。😊，And we design it such that only one path leads you to a good reward and all other path leads you to no reward。

Okay， and the other thing that you should notice is that。

 if you've taken like something that is related to theoretical computer science。

 you know that in lower bound construction， no single instance is hard。Okay。

 so if you have an instance where like this node is the best， well。

 I have an algorithm that just gives tells you to take this path。😡。

That algorithm achieves the algorithm policy with zero sample complexity。Okay， so in terms of like。

 you know， theoretical computer science thinking， no single instance is hard。

 What's hard is always a family of problems。Okay， when you have family problems。

 you don't know which one is which。But let's say the nature of the anniversary chooses the worst case problem for you。

 Okay， then it becomes hard， right， So here is as well。

 like really what we're joining is a family of problems where。

It has exponentially many different instances where every instance differs by you know which node is the right node to look at。

Okay， and you don't know like which instance you're facing to begin with。

 your algorithm needs to figure that out by interacting with the environment。😡，Right。

So suppose this is the only like thing you have， right， let's say， you know。

 sometimes the reward is over here， maybe sometimes the reward is here and so on and so forth。

 And all those possibilities exist。Which means that the family contains literally two to the age different instances。

Right， so now imagine what you can do， right， So all you can do is just take a path and look at the reward。

😡，And chances are that for the very first path you take， there's no reward。😡，Okay。

 but what can you conclude from that？😡，The only thing you can conclude is that within those two to the age instances。

😡，The instance that says there's a reward here is excluded。😡，Okay。

 but all other possible instances remain feasible。Right？What would you do next。

 What would you do next？You choose another path， right。

 And chances are you don't get any reward at all again。 And again， you only exclude another instance。

 right， So basically， if you think about what happens is like the the dynamics before you reach the end is completely known。

Right， so the only unknown is the final like reward。Right， so essentially。

 this is a multi bandit with exponentially many arms。 You have no choice。

 but basically to try each of them one by one。 Okay， and their are formal proofs。

 like these information theoretical lower bound mathematically turns out to be a little bit tricky to establish。

 I have references for you that you can look up if youre interested。 But basically， intuitively。

 like the sample has to scale with the number of states with the number of arms。

 which here is equal to2 to the age， correct。Okay， now。So， so this is what we have above。

 And further if you， instead of doing， you know， plus one or0 reward。

 if you do something like Bnoli have as the bad reward and Bernoulli have plus epsilon as the good reward。

 you can sharpen the lower bound to， you know， number arms over Epsil square。

 So you can introduce Epsilon into your into your lower bound。 Okay， but that's not consequential。

Okay， so does that prove our？😡，What we said earlier。Right。

 we say that this is impossible to achieve in a complexity that is polynomial in all of these quantities。

We have number of actions small。 H is moderate， right，2 H， but we get a complexity that is2 to the H。

 Okay， so does that construction already prove this claim。To is not polynomial。 so you can't do it。

 right， So， so you， you think it proves it。Yeah， we， we haven't talked about F， right。

 So you need to like。You're supposed to introduce function approximation for me。😡。

And that function approximation at the minimum needs to realize Q star。😡，Okay， so what。

 what's often happening when you notice these lower lower bound constructions is that， well。

 if you say you have to give me a Q star， you have give me an F that is like small in size。

 small in the sense of like， its logarithmic size is small and has to realize Q star know that we now have a family of problems。

 like each problem have a different Q star。If you say Q star should be realized always。

 then it means like for every instance， the problem is their Q star should be found in your function class。

😡，Okay。So what may end up happening and we'll see whether that's the case is that after you try to construct such a function class that satisfies all like satisfi the realizability for all your problem instances in your problem。

 you may figure you may realize that this function class gets so large。 maybe like for example。

 log F itself is to do age。😡，Okay， so if that's the case。

 then do you have the claim that this is impossible。😡，No， right。

 because you are allowed to depend polynomly on all these quantities。

 So if the final thing is to do the H， but one of them is also to do the H。

 that exponential explained away by the exponential nature of one of these parameters。😡，Right。

 so the key。So the key thing that remains to be shown in this proof is to show that I can give you an F。

It satisfies this property。😡，But its log size is not exponential。 It's still polynomial。Okay。

 then that won't explain away the2 to the H sample onplexy。

 which means that this is really gonna be impossible。Okay。

And it turns out that that construction is just so easy to。Right。

 what remain to show is that function approximation does not help。

As it turns out that construction was super trivial to construct。 Okay。

 so this is what your construction is。 right， So basically， what happens is that， you know， like for。

 for each problem instance， for example， this instance says that the plus one is here。 Okay。

 it has a Q function， right， like at the last level， the Q function is basically like， you know。

 where the plus one is。 And if you know that the Q function for all previous level is also known because there's only a unique pass over here。

 So the Q function is only plus one， when youre in a state action that leads to this pass。😊，Right。

 so we can basically represent the whole Q function using the reward function at the end。Okay。

 now each problem in， has its own Q star。And just aggregate all of them together and make that a function class。

😡，Okay， now realizability， Q star in F is trivially satisfy， right。

 Because really what we need is Q star of M。Is a F， right， for all M。

In this family of all possible problems， right， for each possible problem， instance。

 the corresponding Q star is always in F。 Then when we run the algorithm from the sort of upper bound point of view。

 we say， oh， like if you give me this F， Q star in F is always guaranteed to be satisfied。Okay。

 now how many functions are there in F？😡，To today age， what is log size？😡，H。破れ到没有？Okay。

So it doesn't help right So well the logic here is that in the lower bound proof。

 when you say no algorithm can solve this family of problems。 now， you're basically thinking like。

 you know， you're not really thinking about， oh， some general algorithm， like you fit Q or whatever。

 You're saying like whatever algorithm that is allowed to even specialize。 for example。

 that algorithm only works for solving this family of problems that doesn't work anywhere else。 Well。

 that's even okay。 You need to consider those algorithms as well， right， So basically implicitly。

 you're assuming that the algorithm knows that it's dealing with this family of problems。Right。

 but if that's the case， this function class is automatically given when you know that you're dealing with this function。

 this family of problems， right， So the algorithm can totally leverage this function class already。

 It doesn't need you to give it。 It already basically has it。

But that doesn't change the fact that it's dealing essentially with a material embedded with exponentially many arms。

 This function class itself is completely uninformative。Okay， so the lower bound is still there。Okay。

 and what you can do is that you can try to add Belman Comps。 I'm not gonna go into detail here。

 But if you do that that version where like， you know。

 you have a separate G class where that realizes the Belman update for any F。Yeah， theres， again。

 like a very simple construction showing that you can have a small G that always satis this。

 And the G is also un informative。 Okay， so even if you require this and says like。

 I'm also happy to pay for log G。😊，You know lower bound is still there。Okay。Okay， so。

So what what this is really saying， right？ So if you think about it， what's happening is that。嗯。

Really， what's happening is that。Like， I want you to think about like， again。

 like connect to what we learn in， what we learn in offline around， right， so。In off。

 what happens is that especially if you remember the kind of coverage based analysis we have， right？

 So you， you like during data collection， you use some policy to。You know， collect data。Well。

 that helps you learn about other policies， for example。

 through of policy evaluation for whatever policy that is covered on your data。😡，But here。

 if you think about it， if you use a policy to collect data， you have data from here。

Does that cover any other policy？😡，It doesn't， right because for another model that take a different paths。

 their state distribution have completely no overlap。😡。

And you can find exponentially such strike distributions。

 and all of them have nothing to do with each other。😡，Okay。So this is the problem。

 This is saying that beyond the assumption that F is small， like in log size。

 you also need to make some additional assumptions。About， you know。This is sufficient condition。

 but there's a more general principle and after that。 But the sufficient condition is something like。

 maybe you can say， oh， all these。For when you use different policies。

 the state distribution induced by these exponentially many different policies are not completely separate from each other。

 They， you know， share some degree like of overlap or have something in common， right。

 something like that。 like without this kind of additional assumptions。

 we basically already see that exploration is hopeless。Okay。Okay， so if you think about it， like。

 you know，1， one thing is you know， is kind of a intuition is like this， right。

 So so instead of like a situation like this， youd rather being a situation like this where when you take different policies。

 you can relatively like diffuse distributions and they have something shared in common。

 And let's say if you explore with this policy。 Well this policy is already automatically learned。

 right， So then when you further explore， you only explore know other part。

 you don't need to explore separately for each policy。

 because then you just need to enumerate over every single possible policy And we know that the size of the policy class is generally also like exponential。

Okay。Right， so now we did is that okay， so what we really want is like a general condition， right。

 But in order to develop that general condition， we really like is to first look at what are existing。

😊，Problems that people find that it is actually solvable， right？

 And then we look at those problems and say， okay， what what are。

 is there something in common among like all these different problems。

And then you gonna we can maybe extract some commonality and establish a general principle。 right。

 So the very first thing we know is tractable is like finite tabular N DP， right。

 where the complexity measure， which is like， you know， it。

 it is tractable when the number of states is small。😊，Right。Well。

 it turns out that if you actually do state abstraction。It's also attractiveable。 And more。

 you can do Q star relevant abstraction。 You don't even need to do by simulation。 Okay。

 so in that case， you can also do exploration。 and， you know， your， the。

 your complexity will depend on the number of like abstract states。Okay， so furthermore， like。

 you know， for control theory， you have these linear dynamical systems。 So typically。

 you have the system that evolve like， you know， your state is now a real vector and it involves like you know。

 X A T plus like B U， maybe plus some noise。 right， So it's kind of like your， your， your。

 your state vector evolve by matrix modification。 Well turns out that there like exploration on guarantee is also obtainable where the complexity measure is the number of like variables。

 So this that's kind of like the linear dimension of your， of your vector。😊，Okay， but you know。

 none of these， you already touched on the case where you actually have really high dimensional observations and you need function transformation like neural net and whatnot。

 right， Well turns out that there's a family of problems that again。

 like people identified around 2016 that says if if you're in these visual grid world。 Okay。

 so this is actually one of the benchmarks DL used at that time。

 I think it's called mamo or something from MR， where basically you have a grid world。

 But you rendered it in Minecraft。😊，Okay， so， so essentially。

 you're playing in like simple grid world like in the left。

 But your agent isn't told which grid you're in。 Okay， so instead。

 you render the whole thing a minecraft Minecraft engine。

 And what the agencies is like this first person view。Okay。

 so now you can like basically abstract it a little bit。 Let's say， for example。

 let's assume that although generally you get a pump D P。

 which will you know type more at the end of the semester。

 but let's assume that the image observation， you get is the Marovia。

 potentially you can recover the grid I D out of those images。

 but no one tells you how to decode that。 So all you see is just image。 Okay。

 and maybe the image is also like， you know， noisy， like in the same grid， you。

 you get some like noisy image， like it's not always exactly the same image， right。

 But as you can see， like， although this is a problem with like a very high dimensional observation space。

😊，It has a very nice， low dimensional structure that the number of possible like latent states you can be in。

 which is like basically the grid， like the the different grids you're in is actually limited。

 that's kind of like bottleneck。 Okay， so， and， and， and this is。

 I think it really getting to the heart of the integration we're trying to give， right。

 So in this problem， although the kind of data， the raw state distribution you're seeing。

 is a distribution of images， which look like crazy。 But really， if you think about it。

 whenever you take a policy in this world， you can。😊。

Decomose or understand the distribution for images you see in the following way that says first。

 let me ask what kind of occupancy am I inducing over the grid world。😡，Right。

 and I know that each grid will give me a different distribution of images。

 So my final data distribution is basically the distribution in the grid road。

 combined with that like emission， like how the game engine will render image for each grid。Right。

 and it turns out that， you know， if you formalize that。 So nowadays。

 this kind of problem is called a block andDP block， like， which says that， you know。

 there's some underlying block structure there。 And， and it was shown to be solvable。

 at least at that time， that was before I did this work。 They show that this is solvable。

 If you have the underlying dynamics is deterministic。

 And one of the main original motivation for the work I did here。 which we're gonna talk about today。

 it is was first to relax that two stochastic dynamics。

 But it turns out we ended up like discovering some principles that are much more general。😊，Okay。

 so forget about the right that one。 But there is another one that we actually study。

 So this is another canonical example that will see much， much more in the upcoming weeks。

 So this is called it has very similar structure to this。 Actually。

 I think this is a special case of this。 Okay， so this is called a low rank MP。😊。

This is also becoming an extremely important model in recent R theory literature。

 especially in online R。 So it says that you have very large say space。 That's okay， okay。

 but it says that， okay， when you write down the transition matrix。

 we know it it says S A by S matrix， right。So we assume that this matrix has a low rank factorization。

Okay， so basically， you can think of that as like， you know， if you start from S to times a。

 what you can do is that you can first， let's say first maps to one of the let's say Z is is the latent variable that where the number of possible values Z can take is equal to the the low rank dimension of this factorization。

 right， And the final state you draw is condition on Z， which given by this matrix。

 condition on each possible value of Z， which correspond to a row here。

 this gives you a distribution over the。The actual next state you see。Right。

 so basically here you can think of Z as the。Grid， right， given an image and you take an action。

 we know that the image maps to a， you know， grid state。

 And given the grid state and the grid and the action you take。

 we know which next grid you end up with。 And given that next grid。

 like the game engine will render certain distribution or images for you。Okay， so therefore。

 this is essentially a more general version of that。😡，Okay， so we didn't know at the time。

 but it turns out that when your NP also has this structure， it is also tractable for exploration。

Okay。So， you know， this work that we that I did 2017， which gives。

 I think even like as being extended by many afterwards。 But still it。

 it is still a framework that gives you one of the most general statistical guarantees in online row。

 Okay， so what did is that we， we developed。 We is we defined a new notion of complexity called a Belman rank。

😊，That basically， whenever you have a large NP， you have a function class。

 I define Belman rank for you。 Okay， now you can examine how large it is in all of these special cases。

 And each special case， Belman rank can be bounded by the。

 the correct measure of difficulty in each of these settings。 right， So， for example。

 in this linear control systems， Belmon rank will be bounded polynomally by the dimensionality of the state vector in this slow rank problem。

 Bel rank will be bounded literally just by the rank and so on so forth。 Okay， So therefore。

 the the idea is that then the hope is that then we know that previously hour ago。

 where you only introduced log F that's impossible to achieve。😊，Now。

 what we show is that if you additionally also allow， say。

 I'm also allowing myself to depend polynomally on the Bummer rank。

 then we do have algorithms that give you sample polynommal sample complexity guarantee for any general online or problem whenever a Ber rank is low。

 and that's the kind of hour that we're going to talk about。😡，Okay， any questions so far。Okay， so。你呃。

Now。Let's dive straight into it。 right， So really， like the two questions we need the answer from now on is what is the definition of Burma rank。

Actually， it maybe three questions， One is this definition。

 two is why do we even expect it to be low， for example， in some of the settings we're familiar with。

😡，And it's really like you know， what's the right algorithm that can actually exploit this structure？

Maybe4 is the analysis of that worth， Okay， maybe four points。 Okay， but really like it's like。

 what is about my rank why small。 And then whats the algorithm though， man。

 how do you get the guarantee。So I think we'll mostly answer the first question today and get started with the algorithm and the very simplified version of the analysis。

 I'll do more like。You know， you know， a more property analysis on Friday。Okay。

 so what's the Bmer rank， Okay， so so。To define Belmon rank。

 it turns out that we basically need to define a notion of we define a matrix。

 but we'll start with something that we're familiar with。 Okay， so this is basically the Bel error。

 right， So if you remember， like in the Bel error in in the final horizon setting is T F minus TF。

 right， It measures to what extent in infinite horizon discount setting is like to what extent your any function F violates the Bel automatic equation。

😊，Right， and this is basically is very is its version for final horizonon setting， right。

 So you have F。 Imagine like this F is supposed to be Q star。Right。

 then it says like Q star for a state action pair should be equal to should be equal to what should be equal to the reward you get from this state action pair。

 right， So I'm having expectation of reward， given the previous state action pair right reward here。

 Plus， this is a finite horizon。 So we don't need a discount factor。 plus what Mac expectation。

Over the transition probabilities。TheWhatever Q star for the next day。😡，And then if f equals  Q star。

 the finite horizon version of  Q star， this will be 0。😡，Right，Because the。

 because this term and this term will be literally equal。

 And that's literally the Belman of equation。 right， So when you take their difference。

 that's kind of like a measure of violation of， to what extent F violates the Belman equation。 right。

 So that's the Belman error。Okay。Now， the second thing。So we introduced this average bemonaire。

 which is the linear combination of the bemonaire over some distribution over state action peers。

Okay， so。Inside over here， this is just about error， right？ at a state action here。

 And what you do here is that you take a distribution of state action。

 you take the expectation of that with respect to some state action distribution。

 And instead of explicitly writing out what state action distribution it is。

 I'm saying that I'm talking about a state action distribution induced by running some other policy pie。

All the way to this time step。Okay， so the other thing is that for finite horizon setting for a function。

 you like for things like B and error or for just by value function。

 you have different definitions for different time step。Right。

 so here we're talking a particular time step H， but then H can be like in 1，2，3。

 all the way to big H。 Okay， and for this particular state H。

 one way to generate a natural state action distribution is to start from the true initial state distribution。

 run some policy。And you arrive at time step H， and you look at basically our notion of like。

 you know， state action occupancy induced by that policy at this time step。 right， So， so therefore。

 like this notion of average pulmonary is defined by three elements。 First H。

 the the time step we're considering F， the function you' are examining。 you know， you know。

 is it really  Q star or not。 Let's look at how large this is， right， So this function is examining。

 And third， a policy pi that induced distributions。Okay。

 so what this pie does is that you take actions from first time step all the way to times7 H。

 for the last time step， there's a little bit of trickiness。 We'll get to that later。

 but ignore it for now。 you， you take all the way， take actions according to this policy all the way to that time step that naturally induces the state action distribution。

 You use that to combine linearly these errors， okay。Now， this version of B error。

 if you if you remember， okay， so we know that Q star has zero B error for all state action pair。

 Let me ask you a question。 Suppose this policy induces the state action occupancy that has nonze probability on all state action pairs at at at this level。

 okay。If this is0， if this whole average pulmonary is 0， does that mean that at this level？😡。

This candidate F has zero and error everywhere。😡，You shake your head， why not？Right， right， right。

 exactly， right， because we're doing a linear combination。 Remember。

 we're doing linear combination without taking absolute value or square。😡。

So it can be positive somewhere and negative somewhere else。

 And as long as the linear combination coefficient， which is basically this distribution。

 just align with those error signs， they can like naturally just like， you know。

 cancel with each other and disappear。😡，where have you seen this version of Baire？😡。

Like that's positive negative cancelslation thing。 I've told you guys。

 So that's why maybe you have an impression。😊，Okay， I will tell you， like we， we。

 we learned that in marginalized important sampling， marginalizing important sampling。

 we also work with。These kind of bone errors。 And turns out that marginalized important and has a close connection to these kind of methods。

 Although that's one is offline。 this one is online。Okay。

But but that's one thing very important to remember because you know。

 this is the this is the average bone error like it's， it's。

If you just have exploratory occupancy and you say， oh， this is0， that doesn't do much。

Because basically， it's only one constraint， like in the tap setting。

 if you want domin error to be 0 everywhere And at this level， you need S times a constraint。

 This is only one。😡，Okay， so therefore， as you can imagine， what would you want if you want to say。

 I want to like， remember， if you ensure that pulmonary is small on all states at all levels。

 you basically get Q star。😡，Right， so that's what we're gonna do like in our algorithm。

 We're trying to learn an enough that has by an error that is small on， on all levels。

 And if it's tableular， like as a tableular example， it's gonna to be small for all states。

 So what you can like if， if every time you can only enforce that this is small for some distribution。

😡，What can you do to achieve that goal？😡，Absolute value， no。That's an interesting idea。

 So that actually basically connects to marginalized important assembly。

 That's what we literally did over there。 right， Your important sample to create different like weightings and hoping that they gradually confin you know what your F can do and eventually you remove all those possible know。

 positive negative cancellations。😊，But remember， in all R row。

 we did important sampling because we can't collect new data。 So here， instead of important sampling。

 what address address thing you can do。So important sampling， basically the idea is to。

 create different weighting or essentially different distributions。Right， so here were in on。

 we can just use different policies to collect different data。

 and we know different policies will give us different distribution of states。

 and each policy induce one distribution， which gives give us one constraint， right？

 So that's essentially what our algorithm is going to do。

 our algorithm is going every time use a policy to collect some data and then enforce this as a constraint that is this thing has to be you know small after threshold。

 and then it tries to， then the key exploration is to say， okay。

 next time which policy should I use to collect data。

Right so that's the key question we're going answer。 But once you know how to do that。

 you collect more data， you add another constraint and you add another another constraint and so on so forth。

 Okay， so， so and that's that's what the algorithm as a。

Spoiler head of ourselves with the algorithm Mo2， which is related to this definition。Okay。

 but now let's just keep our in mind that because Q star has the Obama error in a pointwise manner。

 it also has this average B error under all possible distributions induced by whatever policy you care about。

😡，Because the linear combination of zeros is20。😡，Okay。So now what you do is that conceptually。

 you never actually write on this matrix in the algorithm。

 but conceptually for the purpose of definition， for fixed time step H， you consider this gigantic。

 exponentially large matrix。 so the number of columns is the number of functions in your function class。

Okay， and remember， each function， those functions are supposed to be candidate for your Q star。

 right， You don't know which one is Q star。 But I realizing believe， one of them is Q star。

If that's the case， if you take their greedy policies， one of those will be pi star。😡，Right。

 so on the， on the rows， we're considering this induced greedy policy class。

 which is basically for each F in the function class， in the value function class。

 we induce this greedy policy。😊，And we put all these grid policy together as a policy class。

 So the size of that is equal to the size of that。Right。

 so then you get a doubleubling exponential like it's the exponential by exponential matrix。

 It's huge。RightAnd for each。Term here that you put in the matrix is exactly that average bowaire。

Right， is the expect， iss the expected。 iss the average common error of the function。

 Can they function on the column under the distribution generated by the policy on the row。Okay。Okay。

 so now what's about my rank。 Well， it's simple。 Bel my rank is just a。The。

 the linear algebra breaker rank of this matrix。Okay， is that simple。So。

 and and note that we have H such matrices because we're now in the final horizon setting。

 Everything is gonna be time dependent。 So Ber rank is just like taking an upper bond of the rank。

 the the the highest possible rank across all H matrices。Okay。So we'll see this definition in a bit。

 But let me first show you know， why do we expect it to be small， right。

 like to show that the bmerang is small， basically， it suffices to show that you can decompose them。

 right， You can decompose this matrix into the product between a tall matrix and a fat matrix and the matching dimension would be the rank。

Okay， so now note that this is generally like a exponential by exponential matrix。

 So without any further structures， without further assumptions。

 you shouldn't expect it to be has small rank， right， In fact， if like as should be the case。

 If you look at that exponential tree example and if you calculate its average moment error matrix。

 you pretty much see a diagonal structure and your rank will be like exponential。

But that should be the case because we know that problem is not solvable。

So his bomb rank can be small。Okay， if if that problem has small bumer rank。

 then we're doomed because then even if you put the Bumer rank into your sample compress guarantee。

 no algorithm has can achieve that。Okay， now for the have case， why its small。

 It turns out that to be really easy， right， Because we know that so if you remember what we talk about。

 like the， this is the definition of bomber rank， right， So you can write it as， as I mentioned。

 roughly speaking， you mentioned you can write it as X H。

A H sample from the occupancy measure induced by the policy。Right， let me use the right color。Right。

 and then the B error， I'm just gonna write F minus SF here， right， and the。And or maybe even X H。

Age。Right， so this was was the the exact intuition I'm given you right。

 that essentially what happens is that youre row in with this blue pi policy that creates a occupancy measure over your scale action space。

 right， And you're combining your error linearly using this distribution。😊，Now。

 whenever you have an expectation， it can always be written as the do product between two vectors。

 like this vector and this vector。RightAnd this vector basically becomes。The row vector here。😡。

And this vector becomes the column vector here。Okay， then you have to decomposition。Okay。

 another way to see like to show this decomposition is basically to show that for any entry in this matrix。

😊，嗯。Absolutely H F pi。And this actually will be useful。 Well So let's talk about it。

 It can always be decomposed as the product of two vectors。

 I'm not sure I'm gonna use the same notation as later。 But one vector only depends on F。

And the other vector only depends on part。 Okay， if you can show this decomposition。

 then it's equivalent to this matrix factororization。Right。

 because essentially if you think about it， like when you， like you have the entry here。

 when you move up and down。And if this still holds。

 then it says that the entry here in this columns is equal to well， always the same F vector。

 do product with different blue vectors。😡，Right， and the same thing， if you move left and right。

 this decomposition tells you that it should be always the same blue vector。

 but different red vectors。So equivalently to show that this is a low rank。

 you can equivalently just not even write on the matrix。

 but just do a pointwise decomverator like this。 But the key is that when you write this as the do product between two things。

 one vector can only depend on pi， but not F， the other vector can only depend on F， but not pi。😡。

Okay， does that make sense？And if you look at here， this form， that's exactly it。 right。

 One vector is the occupancy over state action space induced by pi。 This only depends on pi， not F。

This is the bow error of F on each C action here。 Like in the table case。

 you get a state action dimensional vector。 Actually， there's a little bit of trickiness here。

 It turns out to be state dimensional， but ignore F for now。

 But this is a vector that only depends on F， but not pi。 So you have that decomposition。

And the ranki is bounded by number of states。Okay， so so this is a kind of like a trivial example showing you how。

 you know， Belma rank， although you are looking at the rank of an exponentially large matrix。

 But when your problem has additional structures， it can actually be bounded by something。

 and that is much smaller。Now， this is another example that I alluded to earlier。

 right So if you have this visual grid world， the boomumer rank is bounded by the number of latent states or the number of grids you have。

😊，Oh。Roughly speaking， what happens is that， you know， your policy will induce。 So。

 so let's say the top row is the these grid states and bottom row correspond to the rendered images。

 right， So these are the actual states you see。 We assume that these render images are Markovvian。

 like they can actually say you say like deco latent states。 Okay， so now if you remember。

 like the bone error operates on the states you see， right， So it's the。

 is the F like roughly speaking is the temporal consistency of your candidate function F， right。

 is this prediction for todays state consistent with tomorrow states。😊。

So it's operating on these two states right， is this prediction for this state consistent with the prediction for this state。

 but it's operating on the raw like the rendered image space。😡，Right。And the same way。

 the B air can be always written as the do product between the distribution induced over the states here。

 like the occupancy do product with the Bmanai air for every state action pair。 right。

 So that's the tablet decomposition。 But if we use that decomposition。

 then all you can prove is that the rank is still only bounded by number of states。 But here。

 the number of raw states， which is number of possible images， is huge。Okay， however。

 when your problem has the structure， you can leverage structure to decompose this。

 decompose that error in a different way。 So what you can do is that you can decompose it at this node。

 So what happens is that whatever policy you have， it will induce the distribution over the grid world over the grid states。

Right， and here for the average you have， you can always first take a expectation with respect to condition on each latent state。

 Okay， so you basically summarize that into a vector whose length is the number of latent states。

 So you can do like you can do a decomposition there。 So I'm not going into detail here。

 But I think in the homework， probably in the last homework。

 you should be run into a similar calculation in low rank MP that tells you to show that the occupancy measure you get in low rank NP。

 always have like a low dimension representation。 Well that's pretty much the same spirit as here。😊。

Okay。Okay， so the Q star rev and abstractions can also should be bounded。

 I'm not going over the here。 but that's roughly the idea。 Okay。

 so that answers the very first question， which is why Belma rank is bounded like in these problems。

Any question before we move on？快审。Yeah， if， if you have like a exponential tree without additional structure。

 no problem， no， no， no hope。 Well， I mean， there's the information theore bomb， right。

 So you have the tree， But you can introduce other like if， if all you have is that problem。

 you can introduce other other properties to make it。It it's not that that problem is not solvable。

 You can introduce additional assumptions。 Like， for example， if you have abstractions， right。

 So if you remember， like， I， I made this comment， like when we have the。嗯。When we have the this。

 right， So we have the combination log。 I made a comment。 I don't know how many of you remember。

 but that this problem is essentially the byim abstraction of the exponential tree。Where essentially。

 if you think about the exponential tree， that looks like this。Okay。Like。

 suppose the only reward is here。 plus one。 So here in the in the combination log。

 you also have the good chain that gives you plus one。Essential。

 what happens is that you're grouping all these bad states to this bad chain。Okay。

 so now if someone tells you that oh heres an abstraction。

 the number of abstract state is small and it's like a realizable and whatnot right so essentially it's giving you additional site information about the like that helps you go from here to here。

😡，Another way to think about it is that if someone give you that abstraction。

 then within those exponentially possible different instances。

 a lot of the instances have to be ruled out。 So you're not dealing with that whole space of possibilities。

 You're doing a much smaller space of possibilities。 However， with。

 without those additional assumptions， the tree is just always hopeless。Yeah。Okay。

 now it comes to algorithm right， so you know having a measure is certainly nice。

 but if it's just a definition without an algorithm that I can actually exploit it。

 it's nothing So we need the algorithm。So algorithm， it's not new algorithm anymore。

 I guess it's what I did this in 2016 is almost 10 years。 It never changed the title of this slide。

 So this is the old algorithm okay。😊， okay。So now one thing to notice is that here。

 the algorithm I've been giving is a purely information the algorithm。

 So you can imagine that basically we're saying we have， so like in these problems， especially in R。

 you basically have this。 You have two different resources。

 where you have two different complexities。 you really need pay。 One is statistical complexity。

 simple complexity， regret balance on so forth。 The other one is computational。😊，Right， so is like。

 for example， in exploration in R Mac， R max， we also have this， right。

 Its like between two episodes， you have to do some computation。

 and there you actually have to do a planning step to figure out what's the right policy to use in the next time step。

Okay， so here in this algorithm， what we're going to do is that I'm going to assume that you have infinite amount of compute。

😡，And all I want to do is to get the tightest to possible statistical guarantee。😡。

As it turns out that actually competition in this problem is actually very hard。

 And we talk about that that I think， on Friday。But for now， basically。

 the idea is that especially if we assume that our function class is finite， as you will see， like。

 you know， I'm basically gonna do something like enumerate over all possible functions。😊。

But if you think about the computational cost of that。

 like basically that's going to cost like a exponential amount of compute。😡，But for now。

 we're not going to worry about computation and just say， can we get a statistical guarantee first？😡。

Okay。So it turns out that this is a version space algorithm and。

I'm gonna first introduce a simplified version of the algorithm with some simplified。

 unrealistic assumptions to first help you understand why it leverages B my rank， okay， so。

For each iteration。Okay， so what it does is that。So what what it does is that it。

 it maintains a version space。 Okay， so you can think of this version space as a start with F。

 your function class。 Then as we mentioned， gradually。

 you will collect data and enforce those about error constraints， right。

 Those will help you eliminate some functions。 If you see a function that incurs a large average be error。

 You know that function cant be Q star。😊，So you get rid of that function。😡。

And as your estimation keeps going and going， the number of functions that are still plausible that still survive will become smaller and smaller and smaller。

And at each iteration T， F sub T is basically that space of functions that are still plausibly Q star。

😡，Okay， does that make sense？😡，Okay， so now at each step at the beginning of each it。

 so remember each generation， basically the only thing we need to determine is like what policy are you going to use in this iteration to collect some data。

😡，Okay， so， and this is what we compute at the very beginning， right。

 So what we do is that among those functions that still survive。 So F T， remember。

 those are the surviving functions of them still look perfectly possible to be  Q star。

You picked one。So for each of them， F， you plug in the initial state。And max over action。😡，OK。

 so someone tell me supposeuppose F equals Q star。😡，What is this quantity？😡，If F S Q star。

 you evaluate at the initial state。What is that？😡，Jy， what。Yes， JS， right。

 so that's basically the optimal return you can achieve in this problem。😡。

But that is if F equals Q star。😡，But what I'm doing is that like， okay。

 so like Q star is one of these guys。 I don't know which one yet For each of them。 I'm gonna ask。

 well， you say you're a Q star。 Tell me， what do you think is the true optimal expected return for this problem。

 Well， everyone gives me a number。Okay， then what I'm going to do is I'm going to pick the one that gives me the highest number。

😡，And remember who gave me that。 Okay， so the the person who， the function I gave me that number。

 I call it F T。Okay， what is this doing？😡，This is an instantiation of a principle we just talked about last time。

😡，What is this。Yes， well what do we call it？😡，Optimism in face of uncertainty。Okay， well。

 why is that， Well， Because you know that because because Q star is among them。

 like think of this as bidding process， Everyone bids， right， So Q star bit the correct J high star。

Okay， but someone may bid higher。😡，And you always pick the highest the guy。 So whoever you picked。😡。

Their predicted value will be at least。J P star and possibly higher。

So this is optimism in face of authority。 You're acting based on optimism。Like J Star。

 like the actual Q star tell you you can win $100 in this game。 And someone tell me， no， no， no。

 like， believe me， you can earn $200。 I say， great， Like。

 I'm gonna try whatever you suggest because I think I can win $200。 But what is that。

 That's optimism。You're believing something that is better than reality。😡，Okay。

 so then what you do is that given this optimistic value function F T， you extract its。Grey policy排挤。

Okay， now as you can see， I'm turning the colors of these quantities， right。

 So when we are looking at different candidates within FT。

 we're treating them as candidate functions。😊，That for like Q star， right。

 So we eliminate based on average carbon error later and also forth。

 But then when I pick out that optimistic value function and turn that into a policy and to collect data。

 it becomes blue because now it plays the role of like， you know。

 data collection policy that induce those state action distributions。😊，Okay。

 like if you think about the B error matrix， now we're like picking someone in the column。

 but then like flipping that and treating that as a policy that plays that is now on the row index。😡。

Okay。Okay， so now there are two things can happening。 One is that you so here， as， as I said。

 I'm ignoring all possible statistical slackness。 That is whenever you estimate something。

 I assume for now， we deal with the with later。 But for now。

 I'm assuming you can always estimate something perfectly accurately。 Okay， so then when you。

 you can just roll out mono trarejectories of this policy。Right。

 and let's say say we assume you can estimate it perfectly。 So then you get J T subt not supert。

 right， So what you do is that you compare that with the prediction at the beginning。 Okay。

 So if it's greater than or equal to the prediction， you're done。 Why is that。😊，Sorry。Yes。

 this would only happen for Hstar， right or only happen if your initial prediction is JP star。Right。

 and maybe you have like， a， yeah， okay， yeah， so。Well。

 this is because we know that this is optimistic， right， VFT。Which is the maximum value here。

 we know that it is greater than equal to J pi star。😡。

So if your policy achieve something that is at least equal to。

 that's the only possibility that is equal to that。😡，You're as good as Pi star。😡。

At least for the initial state distribution， which is the only thing we'll care about。😡，We're down。

Right。And then but otherwise， you'll keep exploring。😡，Okay， now before we see how we explore。

 what is this？😡，Well， this is also the same we see in the RMX algorithm。😡。

This is explore or terminate。😡，RightIf you're remembering R max， we have said that， oh。

 I can guarantee that you have a driving force for keep exploration。

 but only if you are not optimal yet。😡，If you're optimal。

 I can't guarantee that you can explore anymore， but you should be happy。😡，Same team here。

And as you can imagine later in the analysis， we're going to use the fact that assume that you're actually subop more and use that as the driving force for showing that you're doing exploration。

😡，Okay， so what you do is that then you can use this policy to collect data and form estimate for this entire role。

 right， So there's some like subtlety we'll address next， but roughly speaking。

 like the average moment error， like。All of them share the same distribution right。

 so therefore you can use the same data set to estimate the average o error for different candidate app。

😡，Okay。And all you need is to pay a union bond over all possible different apps， which is log F。Okay。

So then again， like in reality， you can only estimate to a certain accuracy and pay a polynommal sample complexity。

 But for now， let's just assume that you can estimate everything perfectly accurately。Okay。

 so then then you will see that many of some of them are 0， which means that they're still plausible。

 right， You didn't witness any error。 But if you see anyone with a non zero average development error。

 what do you know。What do you know about these functions？They are definitely not Q star。

 So you get rid of them。 Okay， so if it is non zero， you say okay， they're not。😡，Okay。

 and what you do is that you shrink your version space。😡，So then what you know and， okay， okay。

 so now once you shrink your version space in the next it， when you go back。

 you will presumably compute different optimistic function because now you have a smaller version space。

And you keep doing it， right。 So in that case， you find a different exploration policy。

 this is a different policy。 And again， you explore an entire row。

 you collect data to estimate entire row。 And again。

 you find something that is whatever entries that are non0， you get rid of them。

 Then your version space become even smaller and smaller and smaller。Okay。

 so that's just how the algorithm Mos。😡，Okay， so let me， there's one， maybe one or two more minutes。

 Let me show you how in this ideal case， you immediately like。Okay。

 so we basically need to show two things， Right， So it's like， you know。

 how many data do you need to estimate， do you need to estimate this role， right。

 But here we're not even worrying about that。 But the next thing。

 which is the more important thing is how many times do you need to go， right。

 How many different policy do you explore with。Okay， so because these two things combine together。

 multiply together is the final sample complexity。Okay。

 what I'm going to show you is that in the last minute or two is that the number of iterations you can go here is literally bounded by Bmer rank。

😡，Okay， so why is that？Well， the reason is， actually， I don't know if I have time， but let me try to。

呃 give a。呃。Give it give it intuition。So basically， if you have a。Basically。

 if you have a done sum iteration， you will notice that all the F that has survived。

 all the columns you have not excluded。 It should have all zeros。

Right in the yellow rows that you have explored， because if there's not zero。

 you should have like already eliminated it。Okay， so what you can show， and I'll briefly show that。

 I'll go over that more carefully next is that every round。Everyver round。

 youre guaranteed that your new road that you explored， you will find some。

You will find some previous surviving F that has non zero。😡，Ha nonze average boneaire。Okay。

 so for example， previously here， all these entries are possible。 They have zero error so far。

 Then you are guaranteed that the next step， some of them will show up with non zero error。Okay。

 so what does that mean， that means that every new row is linearly independent about the previous rows。

😡，Right， because because you can prove by contradiction。

 if it is linearly dependent of all the previous rows。

 you can express the new row with the linear combination of the previous rows。

But the previous rows on this entry have all zeros。 You give me a new non0。

 You can linearly combine zeros into a non0。Okay， so what does that say to the sub matrix that only consisted of the yellow rows。

It has full rack， full row rack。Right， but we know that any sub matrix of a bigger matrix。

Their rank cannot exceed the bigger matrix theory。 So what's the maximum number。

 the rank for the euro row。Development rank。Okay， so therefore。

 after Belma ranked number of iterations， you just have to stop。Okay， with two caveats。

 One is that there's one such matrix per time step。 What we're gonna show is that in each iteration。

 at least in one of the time step， you will increase the rank by one。 So eventually。

 the number of iteration is like B rank times H。 But that's not so important。

 And the second thing is like。What is the， why is it that you can always find a nonzero entry。 Okay。

 well it turns out that if you're not optimal and down yet after that round。

You can definitely say that one of the entries is now 0。 And you know， so one of the F。

Will have non zero。 Well which F Well exactly that optimistic F。

Because if you remember that optimistic app。If you're not optimal。

 that optimistic app is overpromising you， it says that you can get something better than JPI star。

 but when you run its policy， it's giving you something that is worse。😡，So there's a discrepancy。😡。

Right， whatever it says is not delivering whatever it actually does is not delivering the value it it。

 it promises you。 And when you decompose this error， you will show that this gap， which is。

 this is optimistic value it promises。 This is the actual value it delivers。

 The difference is exactly equal to the average verai error of itself on the distribution it induces。

Okay， so if this is0 non0， one of these guys has to be non0。And I'll be done with one last comment。

This identity。😡，I's the finite horizon version of identity that I have emphasized countless number of times。

 This is that。This is that thing we talk about， right， So when you have a function。

 we have an arbitrary Q function， you use that to predict the value at the initial state。

 You compare to its real value。 that， that error can always be decomposed as the average common error of the function under the distribution rest it is self induced。

Okay， so that's why I said， like if you remember two identity from this course is the performance difference of Emma and this error decomposition of Emma。

