# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p35 P35 Rmax探索 -BV1YsZHBZEyM_p35-

Okay， let's start， so。So last time we talk about online R and the。

 the the sort of formulations right， and you have sample complexity and require bound and how they sometimes like con convert back and forth between each other。

 And today we'll get into， you know， really concrete。

 How do you actually achieve the kind of guarantees starting with the tableular setting。

 So that the algorithm we'll be talking about is called R max and。😊，呃。The RX algorithm。

 we'll see how it gets its name just in a minute。U。So just a setup， right。

 So we have so we have Tular NP。 So we have the NP。😊，Now， as you， as you see， like to talk about O R。

 it's， it's most convenient to think about the。To think about the finite horizon setting， right。

 So but later we'll completely switch to finite horizon settings。 But for now。

 just for convenience so that we can reuse some of our results before I'm gonna like imagine this convenience setup where its kind of like you get all the convenience from both finite horizon and infinite horizon discounted setting where you assume that there's some initial state distribution we care about and it's still in the infinite horizon discounted setting。

 But the environment has certain properties that within at most H steps。

 you always hit absorbing state that represents the determination of a particular episode。 right。

 So in this way， like every time you roll out a trajectory。

 the trajectory is always finitely long and only has H step。

 you don't need to roll all the way to infinity。😊，Okay。

 so this way we can we still have our standard like。

Interaction protocol where round you pick a policy， you draw out a trajectory。

 and then you learn from it， you update your policy。

 You draw out another trajectory and so on so forth。 At the same time。

 we can use all the airbounds and， and， and things like that that we have established before。

 as we see， like they， they can our earlier tableular analysis is immediately useful when。

 when it comes to proving the exploration results。😊，Okay， so just to remind everybody。 So the， the。

 the protocol is that just as we exactly said last time for T equals 1，2，3 all the way to big H。 we。

 you know， you decide on。pi T。 So the algorithm chooses pi T and roll out。Tjectary。Djecty， using。P T。

 right， and that's your data， right。 And then you just keep updating like this。 And for this one。

 we're gonna prove a sample complexity result， which means eventually。

 I'll show you that you can get a good policy after certain number of iterations。 Okay。

 so well show that well get an ail optimal policy。 after。😊，After。😊，AT equals apoli number of states。

 number of actions， effective horizon。1ner rhxon and log1 over delta。Okay。Okay。

 so I I'll show you the algorithm that achieves that。 and I'll talk about the algorithm right now。

Okay， so this is the， this is the goal。 And by the way， this algorithm is very old。

 and the sample complexity guarantee it gives you is pretty loose compared to more later tighter bounds and state of the art algorithms。

 And you will see like certain aspects of the algorithm is very how to say crude。

 like not not really tight up in various ways。 But it will see like tighter。

 much tighter bounds later on in a general model called linear NP that that that that gives like a lot of improvement already and applies to more general class of problems。

 So for here， I choose this one because it's relatively simple and it sort of like gives you the right intuition for how like exploration is actually done。

😊，Okay。So， so therefore， bear with it that the， the bounds will be generally like not。

 not super like super tight compared to what you can possibly achieve with smarter algorithms。Okay。

 so what' is this algorithm right， So in order to tell you the algorithm。

 I don't need to tell you two things。 One is one is based on the data。

 how do you decide the acceleration policy for the next run。😡，Right， and the second。

 what's the second thing I need to tell you。😡，喂。How do you do update， Well。

 that the that's the update。The update is like you get one more trajectory。

 You use all the trajectory so far to compute the policy you， you will use in the next round。Right。

 so if I give you this， you can just keep generating tasies like all the way to big T。

But to specify the algorithm， I still need like another element。

 Like what's the other element of the algorithm。No， the algorithm。

 initial state is a part of the environment。What does the algorithm need to do。

 So the sample con guarantee says that eventually you need to recommend a good policy。

RightSo there's the the other element is like at the end of the day， once you get all the data。

 like how do you come up with the policy？Okay， as we will see， however， for this algorithm。

 these two are not separate。 Like your next policy eventually will automatically become good。Okay。

 so therefore Im， I'm only gonna tell you， like， how do you get pie tea。Okay。

 so how do you get pie T， so what the algorithm， so the R max algorithm。😡。

It maintains some quantity that should look quite familiar。NA and NA S prime。Okay， for convenience。

 I'm gonna assume like reward is known。 If you need to estimate reward is， it's no problem。 Like。

 as you know， for MP is typically the difficulties in dealing with like learning transitions。

 like reward handling unknown reward is usually very trivial。 Okay。

 so N SA literally is the number of times。we see。You know。SA。In data。Right， so so far。

 I have some true referies and。I've hit a particular state action pair certain number of times。

 I'm just using N of essay to as the counter for that。Okay， and as you can imagine。

 what is an SA as prime？😡，Well it's like whenever I see S A。

 what's the number of times that the next state is S prime。 iss that simple。 Okay。

 so now if you divide them， you divide this by this， This is the empirical frequency， right。

 the empirical transition probability that you estimate from data。Okay， so a lot of the。

 what our our max algorithm does will look very similar to the naive tableular analysis we did very early on。

 right， We're just using the， the data to build a estimated MP。Okay。

 but Rax does a little bit of tweak to that。 And that tweak alone leads to。L leads to you know。

 exploration guarantees。O。So， so this is。ASimilar。Okay， and then。So the Rx takes a hyperparameter。😡。

M， which is a integer， positive integer， which will specify later。

 And what it does is that it will build MP and the at round it will build NP。

 And the optimal policy for that NP is the policy you will use next。Okay。

 so thereforem is suffice as to just。Tell you that MPP。 So what it does is that now to define that。

 you need a definition of K， K is a set。Cha a set of sed action pairs。

Search that N of S A is equal to M。Okay， so， so here the capital K stands for no。Okay。

 and here you may wonder why it's equal to M not greater than equal to M。

 So the way we update those counters， theres something slightly special。😊。

Just to deal with some technical technicalities with concentration inequalities。 That is。

 we only increase the counter before it hits the threshold M。Okay， so once it hits the threshold M。

 we stop we stop recording any data coming from this state action Shamp。

Because M is meant to be a threshold that tells us， oh。

 now you have enough data points for the state action pair that your reward estimation。

 if reward is uncertain， and more importantly， the transition estimation is not accurate enough。Okay。

 that that the error is so small that roughly speaking， I can like those errors are。

I can tolerate those errors， right， Well， roughly speaking。

 I can pretend that those errors didn't exist so that I've actually properly learned the transition for the state action pair。

So once we hit that， we don't。Like， you know， in practice， you would think that you want， you know。

 more and more samples。 But if you remember when we introduced concentration in qualities at the very beginning。

 we said that you can only apply whole things if the number of samples is a deterministic quantity。

 Or if it's random， It's randomness cannot correlate with the outcome of the earlier samples。 right。

 So， so basically this， this is only to make sure that's the case。Okay， so to。

 to make sure that hop applies。 I mean， in practice， you probably will and should use more data。

 Like， it doesn't seem really should hurt in practice。 But， you know， just for theory， like。

 we're gonna assume that， okay。So then you have this known set and you estimated MP as the following。

 So I have an estimated MP M known hat。 Okay， so it as the same state space， action space。Apparently。

 you have the。You will have the。How to say the， the estimated transition probabilities and the and the reward。

 Well， now， even if we assume that the reward is so reward is。

 although we assume that reward is known， It turns out that you wouldn't directly use the true reward function。

 You actually manipulate it somehow。 Okay， and this factor。 Okay， so we don't only need these。

 like for this MP， we don't， we don't need to include， for example， initial state distribution。

 because we know that for table NP， you can compute a policy that is optimal for all initial state distribution。

 right， So we just write down these and then we can。

Then the pi T plus  one is just the pi M head K star。Okay， so basically， like， let's say， so far。

 like currently I've collected teeth trajectory。 I have T trajectory so far。

 I use all of them to compute all these quantities above。 And then like， I have this M K hat。

 And then its out policy will be my exploration policy for the next run。O。

So one thing to keep in mind is that although this is kept implicit that like the all these quantities over here。

They change over time， right， like the， the encounters， this known set， the estimated MP。

 They differ at each time step。 Oh， sorry， at each round。 as T increases。

 all these quantity equal will keep changing。Right， and whenever we write that we write them down。

 we imp them mean that we're talking about the value of these variables at a particular snapshot。

 like time round T。😡，O。So is the algorithm clear。 Oh， sorry， I haven't tell you like。

 how to define these。 But once I define these based on the data so far。

 the algorithm should be clear， right， Any questions so far。Yeah， case empty set to begin with。

 right， So this is the number of state action pairs where you've already accumulated enough data。

 right。 So if naively think about exploration， basically， you want to make sure。

Like you may naively think it's not quite like that， but it not it's so different from that。

 but roughly speaking can think of the goal of exploration is to make sure that all state a pairs belong to this known set。

😡，Right， so if you， and if you use a not so smart exploration strategy。

 you may accumulate a lot of data for certain state action。

 but may never visit some other state action。 right， So that's bad。

 So the goal of exploration is to encourage the algorithm。

 Try to include the more and more state action in the set。Yeah yeah。

 so I haven't defined these for you， right？So to finish the specification of the algorithm。

 all I need to tell you is what is pi K hat and what is RK。 And in particular。

 you will see what happens when K is empty at the very beginning。Okay。

 so it turns out what happens is that it will define the transition for state action pairs in K and outside K differently。

 And outside K basically， So for state action outside K， basically。

 those are state action pairs where I don't have enough data。Right。

 so even if either I have completely zero data， as you said， or maybe I have small amount data。

 But even if I have data， the the amount is so small that basically， I don't trust it。

 So like this is the part where this algorithm is very crude and not really smart is that it has this very black and white notion of known versus unknown。

 where later algorithm doesn't have this black white notion。

 Like you can use concentration in quality to construct Comp intervals where the level of knownness should be like a smoothly changing you know。

 quantity that increases as your number samples increase， right， the level of knownness。 But here。

 this is like very crude， but it also makes things simple。 Okay。

 so the definition is that the following。 So P K。Which is the transition。AHa as prime given S is。

Well， N S。A。S prime NA， if S a。In， right， So this part is shouldn't be surprising。

 If I have enough data， I just create the empirical estimate。

 estimated probability as if it were the true probability。Okay。Now。Otherwise， for stay action pair。

 you don't know。I assign self loop to it。Okay， so， so basically。

 this is saying that S prime is only gets one probability if S1 equals S。

 So you assume the dynamics is a self loop。Okay， this may sound weird。

 but it'll make more sense when you see how reward is tweaked。So for the reward function。

 even if you know the true reward function， as I said， you won't directly use it。

 You only use the true reward function if for state action here that is known。😡，Okay。

 so if your reward is also unknown and you estimate it from data iss going to be similar for state action impaired that is known。

 you take the average of the sample reward。😡，应开。Now。The key thing is here。😡。

For an essay that is outside the known area。The reward is Rax。 And this is where it getses name。O。

So see， like， what happens is that for the action impaired that is known。

 you use the true reward or maybe the estimated reward and the empirically estimated transition probabilities。

 because you feel like they are trustworthy， because you have enough samples that they are pretty accurate。

And outside that， what are we doing for any state action here。 So can someone tell me this。

In this particular NP that we construct。What's the Q value。

 What's the Q star value for state action pair outside K？V max， right。

 Because once you're in this state action impaired， your immediate reward is R max。

 and it goes back to the state。Right， and in the state， the best action you can take is， again。

 take this action again， you get R max。 You go back to the state again and so on and so forth。

So therefore， what this algorithm does is that it assigns maximum possible value for any state action impaired that is unknown。

Right， so if you imagine like a diagram， let's say。

 let's say you have MP that start from some initial state。

 And let's say this is roughly the region of state space that you can reach， okay。

And let's say currently you have data that covers this part。😡，Right。

 let's say all these state action pairs in this yellow region reaches the threshold。 They are no。

 Okay， so what does the algorithm do to encourage you to explore。 Well what it does is that it says。

 oh， like all state actions in this region has maximum possible value。Okay， like， okay。

 before you do that， because here you lack data or sometimes you have zero data， right。

 If you say I just estimated empirical M DP from that data。

 that NP sometimes is not even well defined。But however。

 by simplyclaiming that like I have the self loop with R X word， I now have a complete NP first。😡。

And second， for all these the action pairs with without sufficient data yet。

 they get maximum possible value。Therefore， there's a natural incentive。

For the greedy a policy in this NP to try to go to there。Right， now， heres something interesting。

 There are two cases where you wouldn't want to go there。Okay， and then they're interrelated。

 But let me say that anyway。 So the first case is， for example。

 suppose there is a policy that only visit the yellow part。

 only visit the yellow region that already achieves V max。Okay， then maybe by tiebreaking， you can。

 you， you， you， you still choose this one。 So， okay， so you don't explore。Okay。

 so then you don't explore， but is that a problem？😡，Why is that not a problem？Yeah。

 Vmax is the best possible value you can ever achieve。 How can you complain， You optimal。O。

That's one possibility。 The other possibility where you wouldn't just try to go right is that suppose so。

 so so far， when I'm doing that reasoning， I'm kind of like implicitly assuming that everything is deterministic And whenever there's a state。

 if it's reachable， you can always reach it with 100% time and so on。 But remember。

 we're dealing with a stochastic MP， right， So it could be possible that。Like there could be a state。

嗯。Like down here。Let me see。There could be a state down here where there is only a probabilistic pass towards there。

 right。 So， for example， maybe this state can only be reached from its you know， previous state。

 but the transition probably to the state is extremely small。Okay。

 let's say exponentially small or extremely close to 0。Okay， so in that case， as you can imagine。

 whatever exploration strategy you use as long as you start from the initial state。

 it's very hard to collect data from such state。Okay。So then it also seems like you're doomed。

 You will never collect enough data from that state， given reasonable amount of data。However。

 does that matter？So the claim is that that doesn't matter。 Like。

 it's completely okay that you don't have enough data from such states， why。Right。

 so the the as you say， as you said， like when you。

 so imagine even imagine you're using the optimal policy， right， So if regardless of what you do。

 the probability of ending up in the state is extremely small。

 It means that your behavior and the value you obtain from the state onwards contribute extremely little to the expected return at the initial state distribution。

So you don't need to learn how to。😡，Okay， so this is a beautiful part of it。

 is like if you think about actually thinking about。😊，Actually。

 exhaustively reach all possible state action pairs and collect enough data for every single state action。

That's generally impossible if you have states that are just very hard to reach。

 no matter what you do。But if you change the goal a little bit by saying。

 all I need is a good policy for that particular initial state distribution。

Then it beautiful that dilemma， right， So either you contribute a lot to my return。

 then you should be easy to reach。 Then I can reach you and explore you。😡。

Or you're extremely hard to reach。 Then you don't matter。

 I don't care about collecting data from you。 Okay， In that case， even if you assign Vm over here。

 when you back up the value， this Vm， although it can be much higher than the actual value you achieve here。

 when you back it up， it will come it will increase the value for a policy starting from initial state distribution by only a very little amount。

 So in that case， it could also be possible that some policy that that doesn't explore that lives in the yellow region already still outperforms a policy that explores。

But in that case， it's also fine。O。So this is a kind of a sort of a little bit of a shit of a thinking。

 Like previously， when I'm talking about like high level， I was always talking about， oh。

 you try to explore all state action pairs and get all the data。 Well， in reality。

 like it turns out that you shouldn't do that。 If you do that。

 there are later works that explicitly study that kind of setting。 And as you can imagine。

 you typically need stronger assumptions。 For example。

 you need a socal reachability assumption that says whenever a state that is reachable。

 the probability of reaching there should be lower bounded by some nonze value right and you depend your sample complexity will depend inversely on that value because well。

 you just set up your goal to be collecting data from those states。

 But as it turns out collecting data from all states is a stronger and much more difficult goal that learning a good policy for fixed initial state distribution。

😊，Okay。Any a question about the intuition and what the algorithm does and so on。开审。why do we？

这 something。That something bigger。Well， so but because we because in our setup。

 we assume that all rewards are between 0 and one， right， And therefore。

 the maximum possible value is already R max over one minus gamma， right。

 So this is already the maximum possible value for， for a node。Okay， so， I mean。

 but that's a good question。 So， okay， so first of all， this is R max。 But， but you see like it's。

 it's combined with the self loop， right， So as we said， together。

 these imp that for any S A not in K Q star of S a in the M K head model is already V Max right。

 So it's， it's not just smart max， because this R max is amplified by the self loop。😊，Okay。

 so the V max is equal to sorry， V max is R max over。W as gamma。Right now嗯。As it turns out。

You can change this to something else if you have additional side knowledge about this MDP。😡。

For for this value， as it turns out later， we only need one single property for this value。 Okay。

 so the only property we need for this value， I think it's correct。

 is that it should be greater than equal to Qs， the true Q star in the true in the true N D P as long as that's the case。

 Like， for example， if you know a tighter upper bound of the true Q star， you can use that instead。

Okay， and this is what we called， and， and here， this single inequality is one of the most fundamental principles that people use to achieve to to achieve proable exploration in online in R L bandit and。

 and， and many areas， this is called optimism。 Okay， so maybe we mentioned this before。

 This is optimism in in in face of uncertainty for any S A that I don't know in face of uncertainty。

 I assign a value to it that is guaranteed to be larger than is true value。Okay。

 and if you can achieve that， it'll drive exploration。一手。So in UC B， I I think the， the。

 the analogy in UC B for band is is that in band is， you compute upper complex interval， right。

 So that is always like with high probability， that is also guaranteed to be greater than the true main of the reward。

 by definition。 What that's the same thing。😊，And we'll see so as I mentioned， like。

 this is a very crude and like algorithm that gives you loose bound。 Later。

 we'll actually literally see the in linear NP。 We have the algorithm that literally extends like linear UB for bandits。

 but extend to linear NP， okay。😊，Okay， any questions so far？And if you remember。

 like I mentioned like when I asked the question， like for the accommodation log， can you solve it。

 what kind of algorithm you can solve it I mentioned like you can solve it with depth for search。

 You can also solve it with a star So for those who still remember what a star does。

 So A star search requires a heuristic function for the node that you haven't expanded yet， right？

 and。😊，That heistic function needs to set condition for a star to be like consistent method。

 Does anyone remember what that condition is。No one。So A star typically is talked about in the。

 in the language of cost， which is like a negative reward， right， So we。

 we talk about reward maximization URL in search。 you typically talk about the cost of minimization。

 So I'll tell you A star is consistent if the heuristic function is a lower bound of the true cost to go for those nodes。

Okay， what is that， that is exactly this。So A star is an algorithm that uses optimism in face of uncertainty。

Okay， so because there you have， you flip the sign， you minimize cost。

 So lower than the true optimal cost for those nodes。

Like when you translate it into the language of reward means a size of value that is higher than the true optimal value for those nodes。

OK。😊，That's why like， I said， I said， like， like R max。

 when you apply to a deterministic NP and to some degree， when you。

It basically is a special case of of a star， which is a particular like trivial cost function。

 hereistic function。Okay， so let's。That's the。That's the呃。不是实。That's kind by the， the。

 the description of the algorithm and some intuition。 So let's now get to the analysis。So。呃。

So the kind of analysis we have here is。You know， we have two。 so far， we have two models， right。

 So we have。M， the true MDDP。And M， K， M， K hat， which is our estimated， like estimated。

optimisticistic， I will call it that way。Optimistic MP。Okay。

 now for the purpose of the empirical s analysis， it'll be very useful to introduce a third MP。

 which is like the expected version of M K had。 the empirical MP we build。 Okay， so M， K is S A P， K。

 R， K， gamma。😊，Or P， K of an S prime given S A is defined as similar to before， but。

For no state action pair。You use the。Use the true transition probability。And for outside， it's。

It's the sorry。For outside， it still self flu。So in our case， when the reward function is known。

 the reward is the same is the same as before。 Okay， so basically。

 this this M PMM K that only appears in the analysis is exactly the same as M K， except that。

 So here， instead of using an empirical empirical estimation。

 you replace that with the true transition probabilities。O。Okay， so why do we introduce this， Well。

 these three models have a interesting relationship， okay， so。So for the known region and。

For state action pair in the known region and for state action pair outside the known region。

 we have the true MP。 Well that's just by equal M。 I mean。

 like your dynamics here is exactly the same as the true MP。 Okay， so for the for for the true MP。

 of course， is equal to M。Okay， now we have M K。 So M K。

 this property is that within the true within the known region。

 is transition probably is exactly equal to the true dynamics by definition。

 But outside its a self loop with R max reward。Okay， with。R max。Okay。

 now we have our actual model we use in the algorithm。

 So for the state action impaired that is known， we don't have the exact true transition probabilities。

 but we're using an empirical estimate from a sufficient amount of data。 So in that case。

 you can say that this is approximately equal to end。

 And we can establish that approximation error using concentration inities。

 And exactly the kind of table analysis that we did before。Right。Now， outside， you have a self loop。

With R max reward。Right， and， and you can see like why we introduce this， right， because。You know。

 eventually， we're gonna do some kind of analysis that says， oh。

 my learned model is very close to the true model。 Therefore， I can compute a good policy because。

 because like my model is like very accurate， right， And if you remember。

 that's what we did in the tableular setting in the earlier tableular analysis that assumes that we have sufficient amount of data for every single state action pair。

😊，Then you can establish that the true NP and our NP is so close that when you do policy evaluation。

 when you do policy optimization， all the results， you know， everything works up to some epson error。

😊，Okay， however， if you directly try to establish that kind of guarantee between M and M M hat。

 it doesn't work。Right， because M and M hat is only close to each other for those state action pairs that you have enough data。

For those state actionmps where you don't have enough data。 Well， M has this true dynamics。

 but your Mk had just have some weird imagined like selflo dynamics。

 They're not really close to each other in a like in a you know。

 like in the earlier table analysis with established that the M had an M they are close to each other in every single state action pair。

😡， but we didn't have that here between M and M had before you collect data from all state action here。

😡，However， in this diagram， there are two MP。Which are indeed universally。

 uniformly close to each other in every single state action pair。 Which pair of NP satisfied that。

Yes， right。 M K and M K had because for known area。MK has true dynamics。

 M K had has approximately true dynamics outside， By definition， they are both exactly the same。

So these two NP are uniformly close to each other。 so we can immediately use our earlier tableular analysis to establish all kinds of similarity results between M K N and M K N。

Okay， and then you can， you can use that to then bridge between that and M and Mk afterwards。😡，Okay。

 so。So therefore， like as you can imagine。The， as we mentioned before。

 a lot of times in our our analysis is typically just two parts。 One is a concentration analysis。

 and then some error proagation analysis。 right， So that's what we did in the in the offline setting。

 It turns out that the online is not too different either。Okay， so， so we first。

Established concentration。So what can， what we can say is that for any S A。In K， okay。

 let me say in this way at any round T。For any S A in K。 now， this K， remember。

 this K implicitly depends on T， right， Because K actually expands as you have more and more trajecties。

Okay， now for any of this， we have a。P of S minus。呃P hat。K of。SA。Well， in that case。

 P had K is just using the empirical frequency estimated from data， right。

 and we' compare that to the true probability。 And we have the TV error bound。

And this part is exactly the same。As the table analysis。 So I'm just copying from there。Okay。

 so if you don't don't remember how to do it， like just the。Just look at the T node。 Okay。

 so just look at the T analysis notes。 This part is exactly the same as before。O。

So here's the question， right， so。As I mentioned， you when you apply honess in quality。

 it can be very tricky if the number of samples you get is a random variable or like the samples you get is like dynamic like。

 you know， you may decide that you know when to stop and so on so forth。 like， for example。

 like already Im although I'm making this claim。 but in each round。

 which state action pair is in K is like uncertain， right。

 like which state action pair is in K is a random fact。

 like like this property is random Like for fixed state action pair in round T 0。

 it may or may not be in K。 And that totally depends on the random realization of the trajectories in that particular round。

Okay， so this like， for example， like in some wrong。

 like if I'm looking at a particular state action in some run， this essay may not even， you know。

You may not have even received enough samples。 And， you know。

 then this claim is kind of like meaningless， right， So that should like， you know。

 ring some alarms in you。 And you should be actual。

 like whenever you face these kind of like setting situations。

 you should be extra careful about you know， why you can actually apply hard things in quality。Right。

 so if you think about it， this is kind of like saying that， oh。

 if I have enough samples at this round for this state action pair。

 then I can establish this guarantee。But then I'm conditioning this very fact that I have enough samples。

 which is a random property of the data so far。 So potentially。

 it has the risk of screwing the distribution of data because I'm conditioning on a fact that is a property of data。

Okay， so does that make sense， Okay， so you like at least you should have some concern about that。

Now， fortunately， that's not a concern here。😡，When you establish this bound。

 this is the most standard application of Hings。Okay。

 so here is an interesting way to think about it。 that tells you why you don't need to worry about this。

 okay。So in this particular example， you really don't need to worry about this。 Okay， so。

 and this is why exactly we set up a threshold M， which is the deterministic quality ahead of the time。

Okay， so to tell you， like to， to show that why this is not a problem。

 Let me give you a simplified example。 Okay， so the example goes like this。

You suppose suppose like we're just in a bandit setting or let's say you just have a random variable X。

 Okay， and X maybe like Bernoulli or is a real value。 It doesn't matter。 Okay， so you draw X 1， X 2。

 bh， blah and draw up to some X N， okay。But and， and then you， you draw some number of samples。 Okay。

 and let's say， like in each round， you draw a sequence of samples。

 But the number of samples you draw maybe be a stopping time。

That is maybe you're looking at all the previous samples and you decide when do you want to stop。😡。

Okay， so in that case， if you take the average of these X 1。

2 X A N and want to say that that is close to the true main， hope thing doesn't apply。Period。

 it doesn't apply。Okay。However， let's like mimic the the above situation。

 Let's say you have a prior determined integer M。And then when n is greater than M。

You claim that x1 plus。X M divided by M is close to true x by holding okay， and when。And less than M。

 you don't make。Plalay。Okay， as you can see， this is very similar tool what we're doing above。😡。

Right。Now， the claim is that this is totally fine。 You can just apply Hing here as if M is a fixed number。

😡，Okay， so why is that。 So here is a like， maybe interesting way of thinking about it。

 So the interesting way of thinking about it is that before you run the algorithm。 So in this case。

 the algorithm simply is like drawing samples and deciding when to stop。Right。

 so sometimes it will stop before n reaches M。 Sometimes it will stop after N goes over M。

And whether like this happens is actually a random event， right， So makes you wonder， oh。

 I'm condition on this event。 Then is this still true。Okay。

 so here is an interesting way with thinking about it。 Let's say before the issue round。You。

 as someone who is simulating this algorithm， secretly。Secretly， draw X 1， X 2， bhh， bh， X， M， X。

 M plus1 all the way to infinity。 Okay， you draw infinitefinly many like random draws of X and put it on the side。

Okay， now， if you look at the first M of them。Hting always supplies。Right， because you get。

 you can just ignore everything else。 And you say for the first M of them， the average of them is。

 of course， close to the true expectation by Hodi。 That always holds。Because like all the。

 these am variables are always drawn。 whether they're drawn or not are not decided by the randomness of the algorithm or whatnot。

Okay， now with these already drawn， you can use them and then simulate the algorithm deterministically。

 So when the algorithm runs， the algorithm says， give me an X 1， you give it an X1 here。

 the one that you already draw。 Okay， then the algorithm decides whether it wants to stop or not。

 right， and let's say the algorithm doesn't stop。 Let's say， give me another draw。 Well。

 you just give this X 2 to it instead of drawing something fresh from random。Okay， as you can see。

 like， this is completely equivalent to the very like the usual interpretation of how the algorithm is wrong。

Right， but then when the algorithm says， okay， now I stop。I make this claim。 Well。

 that particular claim is basically about this claim that is like， you know。

 where you have drawn every priori。Okay， so， so the claim that the algorithm wants to make over there is。

 is now like a deterministic consequence of something that happens in your pre like pre run draw of all those random variables。

 Like there， there are different terms。 people call it。 Like sometimes people。

 people call this concept like a tape。Where you first draw all the randomness。

 the algorithm needs on the side。 And then given that。

 the algorithm becomes completely detererministic。Right。

 and then whenever you make certain concentration in quality claims。

 you're making claim on this tape。 You're not making claim on the algorithm。

 And then whenever the algorithm needs certain concentration facts。

 they just directly use the facts over here。 They don't make any concentration in quality claims by them。

 by their by themselves。Okay， so in this way， like。

 this is a very clean way to show you that why like here。

 although it seems like you're conditioning on a random fact。

 you can still like directly apply host as this。Well， so like， that's what I'm saying， right。

 This is like。Because of this technicality， Rax is design in a way such that。

When you you only get M data points and when you get new data points after that， you throw them away。

Because of exactly this reason， because of this concern so that you can apply you know。

 concentration in quality in the most standard way。Now。

 in later works when you have when you require randomization， learning never stops。

 You have to keep updating。 So in that case， you deal with， you deal with it in a different way。 you。

 you。Use these so called like， you know， in a way， like you can actually you need to unit bound over time。

Okay， if you need the amount over time， then it also guarantees that your， your。

Concentrating quality always ho， but you pay an extra factor。Okay。Okay， so this is kind of like。

 you know， it's a subtle day， but it's kind of important。Okay， so now if you call this epsilon P。

Okay， so let's say we call this。Quantity。Right， and， you know， back to our setting， right。

 So what's the， what's the kind of right imagination， Right。

 The imagination is that for every state as， you imagine that someone has drawn like more than enough number of random next state and store it somewhere like in the tape。

😊，Right， and whenever you run the algorithm， when you say， oh， I need to draw a trajectory。 Okay。

 you see the first date， you take an action and say， give me a random next date。

 It goes to the cache for that state action pair and take the next unused random next date and give that random state to you。

Right， so in that way， like from your point of view， when you run the algorithm。

 you can tell the difference between this kind of like first draw all the store。

 draw everything and store everything in a cache and then just give things in the cache to you versus like drawing random state like in a fresh way on the fly。

 So like distributionally， like these two things are completely equivalent。However。

 like in terms of concentration and quality， it allows you to claim that， you know。

 these kind of things host like in very clean。Okay。Okay， so now given that this is Eon P。

 there are a few things we can claim immediately， for example， for。Let me see。 Where is that。呃。Right。

 so we have。JM K of pi， minus J。JM K hat of pi。Is always less than or equal to V max times epsil from P Y minus gamma。

And also is the case that VM K star minus VM K headstar。Infinite norm is less than。V max， epsilon P。

1 minus gamma。 Okay， so these two inequalities directly come from the earlier table analysis。

 right that tells us that if you have two MP whose transitional reward are eson Rps on P close to each other uniformly here。

 we don't haveson R， but its easy to add that。 Then for any fixed policy their evaluation for the policy will be similar up to some below up factor。

 and also their optimal value functions will also be similar up to some below up factor。 Okay。

 so these are direct consequences what what we did early on in the table analysis。Okay。

 so now we're gonna do is to use that to is establish the fact that you actually do good exploration and your exploration will terminate in polynomial number of rounds。

 And that's the key， that's， that's the key key analysis， okay。😊。

So now to in order to perform that analysis。What we're going to do is to show that。嗯。Let me see。J。

Mie。Minus let me say JM， K pi。呃。For， so here you have for all pi。 So here， we also have for all pi。

 JM K minus JM K pi is。Less than or equal to。V max times。Probability under true M。escape。K chao。呃。

Okay， so I need to explain what this quantity is。 So what this quantity says is。

 is under the true MP dynamics。 when you execute the policy。

 What's the probability that this escape event happens。

 So what escape means that remember Tao is just the trajectory and escape Tau means that there exists a time step A H such that S H A H is not in K。

 right， That is in this trajectory， you actually visit the state action pair outside the known region。

Okay， and that is what that is exploration。😡，RightBecause if you can frequently guarantee that。

 then your counters will keep growing going up。😡，Right， however， like。

 let it's not gonna be that good。 But imagine every single trajectory you visit a new state action pair or you you。

 you， you're guaranteed to visit a state action pair where that is outside K。Imagine。

 that's the case。How many trajectories can you collect at most？😡，So， so remember。

 like a state action pair is known if you collect M data points for that state action pair。Right。

 now， every time you visit a state action pair that is unknown， you increase that counter by one。

So if ever trajectory， you are guaranteed to visit a new state action pair。

 how many total trajectories can you have？😡，M times S times a。That's the sample complexity。😡，Right。

 because if that keeps happening at some point， all your counters are full。

You can't keep going anymore。😡，Okay， and then you have to stop。😡，Okay， so therefore， that's the goal。

 So now in reality， what happens is that you can guarantee that you visit a new an unknown essay every time。

 But what will show is that the probability。Of visiting a state action impaired that is unknown is non trivial。

Right， so if this property is non trivial， then roughly speaking， on average。You know。

 every one over this probability introduies， you will increase the counter by one。😡，Right。

 so then roughly speaking， the total sample complexity will be S times a times M times one over this probability。

Right up to some like random fluctuations that you need to deal with here using concentration ins。O。

たせ構。I know the meaning of this。So that this is a， this is a， this is an indicator。 indicator。 So。

 so Tao is a trajectory， right， So， and， and here in， in this notation。

 Tao is a just random trajectory drawn from the true MP using the policy pie， right。

 and escape pie is one if。😊，This happens。Right， and and know that so here， the S。

 H A H is part of the Tao trajectory。Is that， is that that clear， right。

 So your ta trajectory is like S 0， A 0， S1， S A 1 and so on so forth。

 If any of the pair you run into in this trajectory is out is outside the known area then this escape function equals  one。

 otherwise is 0。So， so this is really the probability that you just increase the counter by one。Okay。

Okay， so。那呃。So this is the one of the key properties。呃。So be we'll prove that later。

 So let's first see， like， how can we use that to establish the final guarantee。

 And then we'll come back to this property afterwards。Okay， so as I mentioned。

 this is what we're gonna try to establish that says like， you know， once we have this。

 once we have this property， we're gonna try to show that in every round for the pie that you use。😊。

This probably is large。Okay， then you have non trivial。

 non trivial probability of increasing the counter。Okay， so， however， there's a problem， right。

 So you can't guarantee always guarantee that a counter will increase， right， Because， for example。

 if all the counters are already full， there's no way that you can further increase anymore。

So that the counter will increase with nontri probability comes with a condition。

 And this condition is what we call iss called explorer。Or terminate。Okay， if you remember。

 like we also said that there are cases where you， like， for example。

 if there are state action repairs that are very hard to reach， you may just not explore it。

 But in all those cases where you decided that you stop acceleration is always the case that you're already optimal。

Okay， so therefore， the kind of guarantee we we're gonna establish here that says。In every round。

 either you're already optimal， Then you should be happy。 You're done。

Or the exploration probability will be non trivial。So that's the claim。Okay。Now。

 by the very definition， what's， what does so what you can do is that you can start with the with the condition that Epson V max。

 So here I'm normalizing epsilon by saying that by saying that basically。

 this is the sub automatic gap is less than J pi JM star minus JM pi M。Kay headstar。Okay。

 I'm starting with this condition。 Why， Because if this condition doesn't hold， Well。

 I claim that this is my optimal guarantee。Right， because if if this doesn't hold。

 then this is greater than equal to。 and pi M K hat is has star is the policy I'm using in the next round。

 Well， if， if you flip the sign here， this just says that this policy is near optimal。O。So。

 so therefore， this is the claim， either I'm already optimal and I'm done or I will explore。

 So therefore， now I'm proving that or part， which means that I'm not optimal yet。 So therefore。

 I can use this as a condition for my later derivations。 Does that make sense。😡，Okay。

 so that like the， the very fact that I'm not near optimal yet will become a driving force for my exploration。

 Without that driving force， I'm not guaranteed to keep exploring。O。So with that， okay？Now。

 it turns out that the very first step is one of the key steps。 Okay。

 so the key step is less than or equal to。JM， okay， so let me be a little slower here。

 So this is equal to JM pi M star minus JM。派 k hat。Right， because this is the definition of JM star。

 right， This is the optimal policy in the true NP。 Then you evaluate that in the true NP。Okay。

 and your subult frommatic app is always with respect to this guy。 This is the optimal performance。

Right。Now。Here's a claim。 actually， by itself， it needs some proof。

 but I think it should be intuitive once you see that less than or equal to。JM。Pie。And sorry， JM K。

Pi M star JM。Okay， so this is the key step。 So what I'm doing is here here， as you can see。

 this term is intact。 I didn't change that。The only thing I change is from M to M K， right。

 The policy also didn't change。Okay， so the claim here is。Why this ho is for all pi。

 JM pi is less than JM K pi。Okay， so why is that？ Well， that's exactly how we define the MP， right？

 So if you think about what， what M K is M K for any state action pair that is inside the K。

 it has exactly the same reward and transition as the true M。😊，Whenever it's outside。

M K has selflo with Rm reward。So as you can imagine， whenever you run any policy。If you。

 before you hit any state action impaired that is outside K that is outside K。

 the probability of the partial trajectory you see will be exactly the same before M and M K。

 you can't even distinguish between these two MP。 Okay。

 but as soon as you hit a state action that is unknown in M K。

 youre you immediately get the maximum possible reward。In the true M， you'll get something。😡，Okay。

 which one has higher value。MKS higher value。Okay， so this needs like， you know， more rigorous proof。

 But I think intuitively， you can understand that why any policy M K always have higher value or equal equal equal value compared to in M。

And this is exactly optimism。Okay。So， okay， now then what you do is that。

This is further less than or equal to JM K。 I can further relax that to JM K star。Minus。JM P M， K。

 Headstar。Okay， so why can I do this relaxation。So this relaxation。

 I'm only changing M pi M star to M K pi M K star。 Why is that。By definition pi。

 this policy is optimal for this MP， right， because here I'm not evaluating on M anymore。

 I'm evaluating everything under M K。O。😊，So， now。So what is this， Well， this is just the JM K star。

 right？ So you can think of it as the optimal value value function in M K evaluated at the initial state distribution。

 right， minus JM pi K head star。 Okay， less than or equal equal to now we said that you know。

 when the two and DP are uniformly close to each other。

 their optimal value function will be also similar。 Okay。

 which means that the optimal value in JM K is gonna be similar to optimal value in。JM K hat， okay。

 JM pi K hat star plus some like the error between these two， which is this guy。 Okay。

 let's call that Eilon prime。 Okay， I'm just gonna put Epson prime over here。O。

Because so so here like after， like after this， there will be several times where we go back and forth between M K and M K hat。

 And because they' are uniformly close to each other， like。

 we can always pay a little bit of price that Abpsilon prime to always go back and forth like between M K and M K M K had。

 you know， as much as you like。Okay， and this is。Okay。

 we're going to do that again because this is just the JM K hat of pi M K。

Hat star minus JM pi K hat star plus epsil。 So this is equal。

 So I'm just writing the optimal value in that MVP as。In that MDP。

 the policy of its own alpha policy。Okay， now by using the previous property again。

 I can keep this policy unchanged and only change the subsequent MP from M K head to M K。Okay。

 so this part it may feel a little bit like， you know， messy and dizzy。 But really。

 what we're doing is just going back and forth between M K and M K hat。 like roughly speaking。

 if you're like， if you can't like。Clean this up like right now。

 just always think of M K and M M K head as roughly the same thing。 Okay。

 so you can always go back and forth between them。Okay， so you have。

 you pay another Epon prime minus JM pi K。Hat。Okay， so this is the final formula we want， right？

 So if you see like， why do we want this is that we want the same policy。 Okay。

 why is this policy important， Well， this is the policy that we're going to explore with。😡，Right。

So you want that to appear。 and more of it's the same policy but in different MPs。😡，Okay。

 and the NP is the M K versus M， but we have。This。Property in the top。Right。

 that says that associate the difference between the difference between these values with this crucial probability that we eventually care to bound to lower bound。

RightAnd in particular， the later form is exactly this form where pi is the policy you will use to explore in the next round。

😡，So then the probability here is literally in the next round when you explore what's the probability you can hit an unknown state action pair。

Right。Then you directly use this。Use that。That。In quality and get。哦呃。Right。This is less than。

Les than or equal to V max。Times。Probability in M， when you execute this policy pi M K head star。

 which is your exploration policy escape。K of Tao。And this is the key quantity that we care about。😡。

Plus 2 Eson prime。Okay， so this is directly applying that。

 that Lamo that we haven't shown established yet， but apply it over here。O。

So now the very final step is to basically we want this thing to be large。Right。

 we want this thing to be large。 Now， it has a less than greater than equal to。 you see like event。

 like go all the way up。 What is greater than equal to。 What is greater than equal to this guy。Right。

 but however， it's not directly greater than equal to that guy。

 You have an extra term here at some Prime。Okay， so therefore， in order to show that。

This probably is sufficiently large。 You need this thing to be small， much small， like not much。

 but substantially smaller than what is there on the left hand side。 right， So let me。

 let me copy the left hand side here。 So the left hand side is just epsilon V max。Right。

So this is eventually the inequality we get。Right， so now what you wish is that basically you wish to Epson prime is less than or equal to。

Let's say we assign half of the left hand side to it。 Right， So if this is the case。

 you move the right hand side， the two epson prime to， to here。

You still have half of epsilon times V max left。That's still good enough。 If that's the case。

 then you immediately have。Probability of。Escaping is greater than epsilom over2。OK。😊。

And why can you do that， Well， if you remember， our algorithm has a hyperparameter that we haven't set yet。

 What is that hyperparameter。M， right， numberumb of samples。 What does M determine。

M determines the accuracy， the error of your transition probably estimations， which in turn。

 determines Epon Prime。Right， Epon Prime is driven Epson P。 Epon P is determined by M。So basically。

 that final bound tells you how to set M。You want to set M to be small enough。 you， you。

 you want M to be large enough so that Eon P is small enough so that Epon prime is small enough。

So that Abpsilom prime。Satifies this。Okay， where remember。

 epsilon here is our final automatic bound right， Because we start with this explorer terminate argument that says when you stop exploration。

 well， this is the guarantee you have So this epsilon here is literally the final optimal guarantee we can give right When we say finally。

 we say oh， here's our sample complexity guarantee to achieve an epsilon optimal policy here I'm actually normalized the epsilon by you know。

 essentially dividing the sub by Vm just to make epsilon like dimension less quantity。

 That's why it's proportional to probabilities。 Okay。

 to achieve either I'm already optimal and near optimal。 And by that， I mean this， right。

 So this is the epsilon that will appear in the sample complexity statements。 right。

 so in the guarantee that says， oh， I can guarantee my when I stop when I stop exploring my policy is this much near optimal。

😊，Now how many samples do you need， Well how many samples do I need depend on M。Right， depends on M。

 What does M depends on M depends on Well， M is set in a way that actually depends on this e value。O。

So， and through the earlier bounds， like you know， the number of states， number of actions。

 those quantities also enter here。 also， sorry， not number of states， but， you know。

 things like horizon and， and so on so forth。 you know。

 they all enter through this chain of inequalities。Okay， so then you have。

 you fully specify the algorithm。 M is now set as a， as a concrete value。

 It's no longer a free onset hyperparmeter anymore。 And you establish the final guarantee。O。Now呃。

Let me see。 So now this is basically the， there's still a few cavebies。 I'll comment on that later。

 But there's a big thing that we haven't solve yet， which is thelemma， right， which is。The。

 how to say the weather。When you have two MP so for any policy pi。

 GM pi minus G K pi is bounded by this escaping probability。 Okay。

 so I will not give you the exact proof， but I think there will be a。Again。

 like you using something they that we already know to sort of give you an night。

 like it is proof is not too difficult。 It's a little bit messy。

 but it's really conceptually not that difficult。 And you can to to look at the notes yourself。

 But I want to give you a sense of why this is true using the tools that we already established。Okay。

So what we want you bound is that we want you bound。JM pi minus JM K pi。Okay， so what is that， Well。

 this is JM pi minus you can say expectation of S from D 0， a from pi。QM， K pi S A。Right。

 because if you， if you're given like QM K pi， this is how you would compute JM K pi， right。

 Just plugging the initial state distribution。Okay。Now， does， does anyone remember， like。

 if there's one error propagation。Like lemma， you should remember from this entire course。

 it should be how to transform this one。You have the true J pie。

 Let's say we now treat M as the true environment。 You have the true J pie minus。

Some other Q functions， expectation and initial state distribution。

 How can you transform this difference。It's equal to what。

You should have something expectation under some distribution。Does anyone remember？Sorry。No， no， no。

 it's the other one。 Like， if you remember two identities。

 one of them is the performance difference lemma， but this one is different。 performance lemma， like。

 remember， performance difference lemma starts as you know， J pi prime minus J pi。

 So it's in the same NP， but two different policies。 So this is the other way around。

 you have the same policy， but two different NP。 or really what you should think of is you just have the true performance in of a policy。

 But for the same policy， youre using approximate Q function to evaluate how good it is at initial distribution。

😊，Yes， yes， good。 So someone still remember， okay so。😊，When you use like。

 so here just treat this as arbitrary Q。 Okay， when you use approximate Q to evaluate J pi at initial state distribution。

 is error is exactly equal to the Belman error of this guy under the discounted occupancy of policy pi in the true M DP。

Okay， so let me add this because I think the sign is maybe a little off。 but that will make it right。

 This is equal to one over one is gamma expectation S A from D pi。

 So D pi here is defined with respect to the true NP。The Belman Air， Q M， K pi minus T pi。

 This is the Belman operator in the true NDP， Q M， K pi。Okay。Now。Like， what is this， Well。

 this is just the reward and reward and and， and transition， right， expectation on transition。

 So I guess'm short time， I will say here， but remember。😊，嗯。Remember， Q。QM， K pi is equal to TM。

 K pi Q pi， right， So Q M K pi is always the fixed point of its own Bel operator。Right， and again。

 like go， how is this operator defined Whats defined by R K plus gamma expectation as prime from。P。

 K SA as also forth。Okay， now， as you can see， what happens is that for any state action pair that is inside K。

 remember， M and M K has exactly the same dynamics。So there are R K in that， in， for those days。

 R K is equal to R。 P， K is equal to P。So the Belmont operator's behavior for those state action pairs are also exactly the same。

So for those action pair， like QM K pi has no Belmon error under its own operator。Right。

 that's always the case。 But because in those state action pairs。

 the reward and transition are the same， it will also have no b error。

Under the true government operator。Okay， where， where in which state actions will that dominant operator be non0 or could be non0。

Not in K， right， So therefore， like when you sum this， you can write it as summation over S。

 DM pi S times。Now， you can basically only sum over S A。 that is not in K。Right。

 and times like you may have some nonze obaire。Right？Now， you like。

 so I think we need an upper bound， right。 So yeah， we need the upper bound at right。

 So we start with the value difference， and we need the upper bound at right。 Well， what is this。

This is the amount of probability。 Like like this is why the actual proof doesn't use this because it。

 it has this discounted it introduce discounting in here， which is a little bit like annoying。

 But if if you ignore the discount factor and those some these。

 this is basically how much probability that pi would actually put on the state dash pairs outside K。

And this is what we want to show want roughly speaking， what we want to show up。

 what we want to show up in the bound， right， And here， this is the about error。

 You can always bound it with like， like a constant multiple of V max。Okay， so。Like basically， like。

 you know， this， this error of the composition Lamma that we， that we， we already know already like。

 you know， gives you like something similar。 I think you can actually establish a bond like this。

 but it'll be probably lose by factor of age or something。 But still， like even just by this。

 you can already establish like a similar result。😊，Okay。And thats it。

 this is basically the foolproof sketch of Rmax。 and I hope。你看着。Kind of get it。Okay。

 so we'll talk about something else next week。 Okay， and that's it。

So the complexity bound is S times a times M。 Well。

 roughly speaking times one over the probability itself is like epon over 2， right。

 Epilon is basically the your like the the， the relative。The。

 the relative sub of that you wish to reach， right？

 But then M is also gonna be determined by S A and Epsilon。 So that's why this is a sub bound。

 because eventually， you will get epsilon cube。 because M is the M comes from the just estimation concentration in qualities。

 right， So that complexity is the standard rate one of Eson square。

 But then you have an actual epsilon over here。😊，And the other thing we。

 we didn't handle is that this is also a rough calculation because it assumes that because I can hit a new S with probably one over epsilon。

 I'm just doing that rough calculation that says， oh， then every one of epsilon I can hit a new one。

 but that's only an expectation。 That's not what really happens。 So you actually you need， but。

 but you can basically use a concentration in qualities here to show。😊。

