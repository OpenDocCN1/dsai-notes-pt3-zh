# 【普林斯顿】强化学习基础 ECE524（Foundations of Reinforcement Learning，2024） p07 P07 Introduction to Exploration -BV1a2frYfEk4_p7-

In the last lecture， we talk about the similar to setting or gene model。

I think the simulator is setting the most important thing is we have a simulator so we can query any state action and step H pair and then we get a next date and the reward as a feedback so we talk about we spend the most time focused on the first algorithm called value equation。

In this course，我 just是。As's a shortage called a VI。 And at the very end of the last lecture。

 we talk about an R algorithm called Q learning。The major difference is in the value tradition。

 we kind of do the batch update。 Well in the Q learning。

 we kind like trying to do the online update or Earth or like incremental update。

 This is like we collect all the data and we do one pass of update。

 This is like as long as we collect one data， we do a new update to it。

So today we will be a little bit more concrete on the pure learning algorithm and。

And and we will talk about the results of what we can get for Q learning。

So we'll talk about the formal algorithm。So cuy algorithm need to input a sequence。As we said。

 last time， it's like the。Which is like the learning race。Which is a sequence of alpha T。

That is t from one to infinity。Essentially， alpha T is trade off like how many fractions we trust the previous Q value。

 that is one minus alpha T fraction。 and alpha T times the new update。 So this is。

 you can think this is like sequence of learning rate。

 And we will talk about how we choose this learning rate at the very end。

So in terms of the main algorithm， we first initialize。With a。With Q H。Zero S。

You can initialize to be0， or actually you can initialize to be anything。For any S H。Thatice。

 I will just initially assign some value to the Q value， Q value function。

Then kill learning algorithm iteratively during the following。That is 4 T from one。2哒 da哒。

And then inside the loop， we say4 H。一口 to one。To capital H。For all。State action。In this step。We will。

 basically。Quord a simulator。This S A H。And the important thing is now we only get one samples of an next states。

And then we will do the following update。That is。Q H。是。I say。s equal to1 minus alpha T。

 This is like the same update we said last time that is a1 minus alpha T times the previous Q value。

Plus，阿尔法 T。Time is the new update。Okay， this is for all state action pair。Then we will also say。

 for all state。In this stuff。Just do。E，H T S。Equal to。Max a of a。Q H T S， S。So the。

 the indent is the same。 Like， so the the this follow is inside the two follow up here。

So what we essentially have is like the four algorithm。

 which the key step is what we talked about last time where we do the incremental updates that we will basically assign Q value to be 1 minus alpha fraction of the previous Q value plus the alpha fraction of the new update。

And the remaining thing is just after we get in a Q value。

 we will calculate the V value that's equal to the max of the Q value taking over action。

So you can think this algorithm kind of combine this sample next states with the update together。

 Well instead of like cur a VI value， we have a first phase that is collecting data and then second phase like doing updates。

So I want to make a few comments about the algorithm。

The first important thing is that note in this algorithm。

 we no longer explicitly constructed the transition。So this is some difference。

 I think in the classical literature， it calls model based versus model free。

I think this separation is。In some sense， a bit like in the high level。

 it's not like a very mathematical， but basically how like the conceptual ideas， like saying this。

 this approach is like you construct a model。Like construct model means you construct what is the P hat。

 What is a reward， Like you directly estimate what is transition， What is the reward。 And this， this。

 this model free means you don't construct the model。So if you're using this definition。

 you can think this value transition algorithm is actually a model based algorithm because in the first phase we can directly construct what is transition probability。

 Well this Q learning algorithm， we actually we never construct what is transition and the transition like the learning transition part is kind of implicit in this incremental update here so we don't directly construct model and this is like a model free algorithm。

 so Q learning is model free。So if youre saying like this seems like too artificial like what is the mathematical difference between those two style of algorithm？

We can actually use the， we can actually use the space complex it to differentiate these two kinds of algorithm。

So in a space complexity， in terms of super， that is how， like how many。Digits you need to a for。

Fish algorithm。Like the value algorithm， because we need to estimate the transition。

 So it's roughly at least of order h。S squared。Because at each step。

 we will estimate directly construct a transition and use transition to do like this matrix vector multi。

Well， you know cure learning。We only use the H SA space。The reason is。Now。

 all we need to store in the algorithm is just this Q value。 Well， Q value only has the S A H。

Different numbers， different numbers in the table。So you can think this is a sublinear in the model size。

By model size， I mean， like the number of parameters you have。

 this is like precisely the number of parameter， roughly the number of parameter up to some constant。

 Well this is like sublinear in the number of parameters。 So that's why it's called like model free。

The second point I want to comment it out is I want to say the sample complexity。

Of Q learning and VI。So in terms of value tu。We already say were like talk about the value of value in the last lecture。

 which was al tda of。H to the forest S A over epsilon square。In terms of Q learning。

 you can do a similar analysis。 We will give a little bit sketch。Like like immediately。

 But the result is， you can essentially prove that sampleity is something like this。

It's H to the fifth。Of S over epsilon squared。So we'll not talk about the formal proof about this result。

 but I just want to say Ki learning can essentially achieve very similar result to value tu。

 but with slightly worse。H dependency。So sample in terms of sample wise， actually。

 by doing this incremental update， you can， you can more or less imagine this is not as efficient as as like a previous value algorithm。

 which you kind of collect all the data and use all the data simultaneously。

 Well here you can like you， you use the data in the beginning and then you throw data out。

 And then you collect new data。 So in essence sense， like you don't。

 you don't like utilize the the power of like each sample to its maximum。

So that's why it has a like slightly worse h depend。

 And we' will also talk about the intuition why it has slightly worse。

But I just want to also say you can think this is as a trade off like I kind of allow slightly worth some public。

 but I kind of like have better。Space complexity， where we talk about it。

And we will actually also have better computation in the online setting。

So we haven't talked about online setting yet， but we will talk about it today。

 and so so far we talk about only simulator setting in a simulator setting value。

 kind of collect the data in the very beginning and only do one path of dynamic programming So this is a computation is fine。

 but in the online setting， value need to do multiple paths of bioma automatic equation and in that case is very slow So you can essentially think every time Q learning need to do one incremental updates。

 this VI need to do like whole path of like dynamic programming So that's why in the online setting actually computation of Q learning is also better。

So I guess I will not formally like go to all the proof about the Q Y you can also achieve that if somehow I would just point out some key steps to let you know。

 like。Like how how this thing happens。So in order to do analysis for the key learning。

 I think the most important thing is we look at these key steps we have。

 so let's just copy the key key update。Which is a QTH。I say。Equal to1 minus r for T。Q， H。2 -1。I say。

Plus， alpha法 T。RH。S A and plus V H-1 average H plus1。T-1 and S S T prime。

So we say this is like a previous Q value。And this is like the new update。S time tea。

Or at at iteration T。So this direct formula is a little bit difficult to analyze。

 but you can think one very straightforward way to analyze this update is。

You can like recursively expand it out。 This Q value is again equal to 1 minus alpha t -1 fraction of a Q Q T -2。

 And plus this thing times alpha T-1 of the update at a T -1 step。

 So you can recursively expand this Q value out。 and you can actually equivalently have another form of this Q value。

 You can return as something like this。 R H。SA。Plus。Smation of I from one to T。伽mmaT。I。

And V H plus one。I-1。S I prime。Essentially， it's weighted sum of all previous values and like previous value operates on like previous samples。

 So you can imagine like you just expanded everything。

 expanded this entireq value out from t -1 to t -2 t -2 t t-3。 So eventually。

 everything happens in the first term kind like goes away。

 And all you have is a bunch of summation of the second term。 and second term。

 And because all the all the alpha and this this reward is the same。

 So reward sumation together equal to one。 And while this thing is what remains。

 Its like weighted sum of this value。And we will see。 And by calculation。

 you can actually get that gama I TI。It's equal to alpha I times the product。J equal to I plus 1，2 T。

1 minus alpha of J。And this summation。I from 0 to T。GmaTI。Is equal to one。Okay。

So what I'm saying is just starting from this recursible equation。

You can prove you can do some calculation essentially， by expanding out this previous Q value。

And then eventually， youre getting this is you can be， you can be viewed as a weighted sum of the。

 of all the updates。 And well the weights we can， we can do the calculation of weights in this way and the weights sum to one。

So we will compare this to the value creation。Where we know the better tradition。

 we're doing the following updates on a Belma automatic equation。

That the Q value is equal to R plus T hat， which is our estimate。And then V plus one hat。SA。

And you can essentially expand out what is the definition of P hat。

 which is using an empirical frequency to estimate the transition probability。

 which is equal to RHSA。Plus。Smation， I from  one to n。And one over n。V H plus one。Hat。S I prime。

So this is a a value tradition。So we notice if we compare those two update equations。

 they are like two different。So one Francis。Now we're doing like a weighted sound。

The first difference we're doing， let's say。This is like。equal this is like sum with equal weight。

 But here like we can potentially have like different ways。 we can either favor in the later ones。

 favor in later updates， or we can either favor in the previous updates。 Like basically。

 we have the flexibility of choosing our learning rates。

 which can tune like what is the ways we put here。And the second difference is。We actually note here。

Like， this is just using。The hat， which is our estimate of value after we collecting all the data。

 But here is the value at the ice iteration。 So Q learning。Use this value。At。Previous it。

So in that sense， this v hat is basically calculated after you collect all the data。

 So this v hat is reasonably accurate。 Well， here， the value is like used at a previous it。

 So you can think like the V H plus11， for example。

 this is like the value you calculated at the first iterate。 And in that case。

 you only observe one trajectory or1 data。 And in that kind of scenario。

 clearly this is like not very accurate。😊，So， V H plus1， I。Is not accurate。For small eye。

So this is where like in terms of Q learning， we have a little bit more。

Complexity we need to deal with。So we'll talk about the next thing is how are were going to choose。

伽马器。Like how how to choose our weights。So essentially， we have like two conflicting。Part。

 we want to handle for。For this gamma IT。The first one is， we want to。Have gamarti to put more ways。

On values。Of later updates。This is because， as we said。

 the V VH plus 1 I is not ever very accurate for small I。

 So we essentially want the gama to put more weight on the value which like at at later tus。

 So to reduce the biasers。So ideally， for example， we just put a probability  one or the weights  one on the very last it rate。

 And in this way， like， we have the smallest bias。However。

 we should not do that because the second thing is we want to gamma to be spread out。

We should not like focus all the weight on one single sample。

 because single sample is like a statistical sample， and it has a lot of like a noise。

So we want the gamma T to be uniform in some sense。To reduce reduce the variance。

This is like the variance part。So basically， we can think the ideal choice would be something。

Which we will put a lot of weight on the later， later updates。

 And so the previous iteries have smaller value and later iteries have like higher。

igh higherigher weights。 But on the other hand， we should not just focus on one update because it has a lot of noise。

 So we should still like， make it relatively spread out。Any question about this。

 like a bias variance trade off principle in this Q value， Q learning part。

So now like we have some like intuitive idea of how we choose gammar here and then we talk about some specific value。

So our baseline， we look at alpha T。Equal to one over。

This is one very simple way you can compute and you can actually use our formula for gamma IT。

 and you can compute the ways。Gmma T1 is actually equal to gamma T2 always equal to gamma T T。

And this is equal to one over t。So this corresponds to the uniform weight。That is。

 if I choose learning rate equal to1 over t。诶。We actually happens to be the uniform ways。

 And this is the part essentially we are very good at variance。

 but somehow we are not very good at dealing with fires。Actually。

 it did this rage does not give good。Good sample complexity。Because of。Bs。So as we said。

 we want to tune this a little bit towards favoring the later part of the updates。

 and by favoring later parts of the updates， that means。We need to。

 we need to basically increase the learning rate。 by increase the learning rate， that is。

 we kind of put more emphasis on the later updates than the previous Q value。

So it turns out theoretically， you can prove the learning rates which achieve this sample complexity。

Is something like a。阿尔法 t is equal to。Like h plus one。Over H plus T。Which you can think is roughly。

In the order of H over T。This is like a better choice。So you can think high level is。

 and this is something like essentially， you put more weights on the later。Later， tours。

So this is like roughly similar to， like， put。Relatively uniform ways。On the latest。

1 over h fraction of data。And because we need to dealing with this bio varianceance trade off。

 So that's why we essentially need to ignore some to some extent。

 ignore the earlier part of the data。 So that's why were not that simple efficient。

 We essentially pay some additional H factor because we are not doing uniform weighting。

 We're doing some more aggressive weighting towards like a later updates。

This essentially is the reason why we have like slightly worse edge dependence。

 but just remember we still have like better space complexity and also the combination complexity。

Computition complexity， I think we said in a similar setting， we cannot see it。

 but in the online set setting later， we will actually see it online setting is in the exploration setting。

 I think the reason is because in the simulation setting。

 we essentially just collect all the data and then we do one path of planning。

 that is a Bel opt equation。 Well， in the online setting that is we we can no longer sweep over all the data action。

 we actually will talk about immediately about like what is the set setting。

 But but the main takeaway is there when we do the value。

 we actually need to collect one trajectories and then do one path of Belma opt equation。

 And then collect one traject we do another path of Bel equation。 Well， in the Q learning。

 we just collect one trajectory and do one path of this incremental updates。

 So that's why you can do a lot faster than than that value。

So I just want before we move on to the next setting。

 where we just do a slightly summary of the simulator setting。So specifically。

 we talk about the non stationary transition case。Where by non stationary。

 we mean we can like assume PY is not necessarily equal to P2。 Its not necessarily equal to PN。

They can be equal， but we don't really require it to be equal， so it can be like different。

And then we just talk about two algorithm。Essentially we kind of already summarize there。

 we talk about the model based。That is VI and model free。That is secure learning。

Where the most important guarantees we talk about is the sample complexity。

 which this one is O tilda H to the fourth S A over Epsilon square。And space。This is H S squared。

Well， in terms of Q learning， our sub complex is OTda。H to the fifth。S a over epsilon square。

 slightly worse。And while the space we can save some space by doing model free that we no longer suffer S square dependence。

 we only pay S dependency。And we will also talk about later in the。

 in the like lower bound session or fundamental limit， there is a lower bound。Or like information。

 theoretical lower bound。 Information， theoretical lower bound basically says because by our assumption of the model。

 we kind of consume each state next states and reward like randomly generated。

 So theres always the statistical signal like noise in it and algorithm in the worst case。

 like cannot really tell which one is the optimal policy because of those noise。 So that is。

 we will see like。In the worst case， like essentially any algorithm in the worst case。

Needs to pay at least this amount of samples。To learn the optimal policy well。

So we'll discuss this topic after we talk about exploration setting or online setting today。

So this essentially says no algorithm。Can do better than this。In the worst case。

So this more or less conclude that。VIH。Almost achieved the。

We call it mini maxax optimal sample complexityity。By almost means up to some log factor。

Like here we have the Oda here， while the lower bounds will prove in the class does not have the lock vector。

But more or less in this class， we don't really care about lock factor。

 So we would just say V I can like already achieve our goal of getting the。

 this is the best algorithm in this setting in terms of sum。 like you。

 you cannot beat value in terms of sum in the worst case。Okay。

 so any questions so far about those emit setting。Now we will move on to talk about the next topic。

 which is the online reinforcement learning。Or we also call it exploration setting。So basically。

 we talk about this is like more challenging setting that we no longer assume the simulator。So first。

 what is the online reinforcement setting？So just remember how we're going to interact with the MDP。

The protocol of interacting with MDP is like we have the S1。And we go to。R 1。Sorry， we go to the。

 we have A1。The first action， and both of them simultaneously determines the the reward you receive at the first half。

 and both of them determines。Like， what is transition probability go to the next states。Okay。

Like something like this。Yeah。So the protocol in the online reinforcement setting。

This we were just observe the initial states。And then， for。H equal to one to capital H。Agents。Takes。

Action。H。And then， the environment。Transition to the next states。SH plus one。Andend the reward。

Arrange。And the most important thing here is in the。In the online reinforcement setting。

 we only we just basically reset to initial states。And we only allow。

 like after we play the entire trajectory， then we can go back to initial states and then we can do everything again。

So， so in the online reinforcement it's like more challenging in the sense it's like basically we will play the entire trajectory。

So this is like a biggest difference between the simulator。And I。Is that in a simulator。

 you can basically choose。Both state and action。Well， in the online reinforcement learning。

 you're essentially like playing a real game or like you're kind of doing a robot。

 you always like reset to initial states and essentially all you can do is you just choose the action sequence。

You no longer have the freedom to choose the states。This is like the major difference。

 you can think this is like more so is' also how we play the game， like when we die。

 we go back to the initial states and we play the game again。

So this also mostly affect how we're going to track the data。

So one very important thing is in a simulator setting。

 we can just basically use a very simple strategy to collect data that is we will sweep。Over。

Or state action pair。Essentially in the value algorithm is we kind of query the simulator for all state action pair and then we get next states and this is basically done and our data collection from there is like a very good。

However， in online reinforcement， we can no longer do that because we can no longer。

Like just for free， set to any states。So in this case， just simply like reach some states。

By yourself。May not be an easy task。For example， imagine you're playing like super Mariio and some states its in like a last chapter and by reaching there it's already not very easy。

 like you need to do some complicated strategies so that you can eventually go to the last chapter of a game。

So one important question we will handle in the online reinforcement learning。Is how。To efficiently。

Collect。Data。In a sense， like we want to collect the informative data。

We're basically in a similarulator setting as long as we sweep through all the state action。

 we're collecting informative data， well in the online reinforcement machine。

 this is no longer that clear。And we were actually given an example showing why this is actually a nontrial question。

 or this is like an interesting question。So we're talking about the failure。Of random exploration。

EMDP。so what is a random exploration？So the first idea to collect the data is here in a similar setting because we can choose all the state action。

 so we just sweep through all the state action pair。 Well， in the online reinforcement。

 although I cannot choose state， but like by random exploration。

 that means like basically every time I just choose action randomly like every time every time when I take action。

This means like。I have step。So this would be some naive idea。

 I would try to see if if the data we collected in this way is like a comprehensive。

 is like it will give me a lot of information。So it turns out this random exploration strategy in MDP is like highly ineffective。

It may suffer from some like。This is highly effective。This may suffer from some A to the power of H。

 some complexityity。So this thing might suffer something like that is exponential in a horizon。

 So basically， for anything that has a long horizon， like， for example，20 or something， this， this。

 this entire magnet kind like is really screw。 Like you cannot use this。

 this way to do collect data very effectively。 So we will talk about why this is true。 Like we。

 we basically just construct some hard instance。So that we show for this hard instance。This。

 this algorithm is like a very bad。So to show this， we constructed structure a hard instance。

Har instance in our literature is actually pretty famous。

 a lot of later like hard instances like based on this， it's called compatorial log。By the way。

 I also want to emphasize this is this is like hard instance， only for random exploration。

 So later well actually have better algorithms so that it can basically， this is no longer hard。

 we we can basically solve this problem。 So this is this is like different from this inform theoretical lower bounds。

 This lower bound says like no algorithm can do better than this。

 but this lower bound essentially says this algorithm is not good。

 but other algorithm can can be good。So we look at this comm lock。Commentter lock is an MDP。

 it iss a two state MDP。And let's say， with with a actions。

So the MDP is actually a deterministic MDP。We don't even need randomness to。

 to like essentially break this random exploration algorithm。

So we look at the MK only has two states。So at every step we have like S0 and S1。

 those are the two statess。Maybe let's use。Superscript。So that to make it different。 This is not。

 this is not talking about step。 This is like basically in the first step。

 I have two states that S 0 and S 1。 This is like T equal to1。And then the transitions go as follows。

 that is if I'm at S zero states at first days。Then no matter what I did。 So basically。

 whatever action I take， I'm always going to lens in S 0 in the second step。

 This is like t equal to 2。Well， in the， if I'm in the S1 states。

There's only one particular action that's going to land me into the S1 in the next step。

That's called A1 star。And for whatever to action。That's not here。 that That is not a one star。

 So we just write this as an a。Minus a1 star。So that is all the remaining action。

 I'm going to go to the S 0。So this is essentially。

 we're gonna duplicate this structure for T times for H times。So when we add this states。

 whatever action I take， I'm going to land in this state as well， and if I'm at this S1 states。

And there's another action I take， a two star that will land me here and whatever other action I take will goes back to S0。

So we essentially have this structure again and again。Till the very last step。T equal to3。

Until at the very end， that is T equal to H。A H-1 star。And this is a subtract to A H-1 star。

So this is like the transition， and then we will set up the reward。Reward is basically everywhere。

 reward is0， and only if I reach these states。We will receive a reward of one。S1 at。T阔腿 H。

So only at the very last step， if I go to S1， I got to reward 1， otherwise I always got a reward0。

This basically can be realized that if you really very strict about the reward has to be a state action function。

 and basically saying that at the very last step， whatever action you take， you get a reward of one。

 otherwise。Youve got real zero。So we can see this transition has a very special structure that is。😊。

Only if you take precisely a1， a 1 star， A3， A2 star， a 3 star。So， this is basically the。

The property of this comm lock， and we have the optimal policy。So the optimal policy is。拍 H。S0。

 which can be anything。It doesn't really matter。And the important thing is a P H S1。Must be。A H star。

Okay。And this is the optimalimum policy。And when we choose this optimal policy， you。

 what you will get is the value of pi star。有个galaxy equal to one。

So this is the only case you will get one reward， and if you precisely choose the action sequence that is a1 star。

 A2 star， A3 throw。Kill the， the very end。For whatever， every other sequence。

You've got to reward zero。So in that case， you basically has no signal。

So you don't really know what is the optimal trajectory in that case。

So let's talk about a random exploration， what a random exploration will do。

So random exploration essentially try H， as we said by different definition。

 we will try AH uniformly at a random。So basically。

 this algorithm will not be very good until it kind of tried precisely this action sequence。

Try this a  one star， A 2 star。And da da till AH star。And until you feel like basically sampled。

This precisely sequence， then you will realize this is like the optimal policy。 And then you。

 you can you find optimal policy。 And like every time before that。

 it doesn't really know what is the optimal policy。

So it's never very difficult to compute that the probability of precisely sample this action sequence is something like a。

1 over a to the edge。So this is essentially the whole reason that is basically we need。

At least a to the omega H。Samples。Or by samples here， we means like trajectories。

To find the optimal policy。Which you can even make an Epsilon optimal policy because here is just a difference between 0 and 1。

到。Why' is not A to the H？呃。I think this is like slightly weaker。

 I'm just claiming some weaker statement。AA to the omega A to H。

 you're essentially saying exponent has to be H。 but here I'm saying exponent can be h over2 or something。

But basically， this is the key idea that is。Like reinforcement because it has temporal correlation。

 So the if you do random exploration， especially for some long horizon。

 the the probability of sample， exactly one of the very good policies like very， very low。

 So that's why you're， if you just do some random exploration without using any like smart algorithm or like smart information。

 then essentially， you will pay something exponential in the horizon， which is like。

People urgent consider like a curse of horizon or something like that。

And you can go back to convince yourself this algorithm is this claim is essentially also true。

So we're talking about this is like a purely random exploration。

 but you can also think about you can do like a。Essentially， random exploration。And then。

Vendom exploration first。And then do like value。 or like you do something like Epsilon greedy。

Version of v。Like by Epson greed means within one minus。With one minus epsilon probability。

 you do value， with epsilon probability， you do some random action。

But the whole idea is the same as long as you don't use any information to do this exploration。

 like you as long as you try to action randomly， like Epson greedty。

 essentially with epsilon probability， you try action randomly。 As long as you try action randomly。

 you will suffer from this like。Hard instance， essentially， that would not work。

Or it doesn't matter value or Q learning。So basically this is also one of the very important distinction between theory and I would say like in Pakistan a lot of people just blindly used the epsilon greed algorithm。

 but can you already see it' like epsilon greed is not a principle algorithm that can solve any challenging exploration scenario。

 at least even for tabs I think this is like a bad algorithm。

 this can only deal with those games where。Where like， basically。

 it doesn't really require any exploration。 Like it cannot deal with this hard instance。

 They can only deal with probably some easy instance of MP that that does not require much exploration。

So as a side note， it turns out like people did a lot of experiments on Atari games and they actually show that Epsilon greedy seems like a。

Perform reasonably well compared to other sophisticated exploration algorithm。

 But later there are also some analysis basically it says a large set of Atari games does not require like complicated exploration。

 Basically， you can just do random action and that still work。

But what we hear is like we want to solve for all the MDP so that there are some like challenging setting。

 it won't work。And we'll talk about how to make it work。

So essentially we need some like a smarter algorithm to do exploration。

Exploration is essentially collected data， and whenever we talk about exploration。

 people also talk about the essentially the exploration versus exploitation tradeoff。

So it turns out the key idea in reinforcement learning of handling the exploration。

Is called optimism。So I actually introduce this most important idea。

We'll introduce this most important idea in this lecture and the next lecture。

So if we really want to talk about the exploration and exploitation trade off。

It's better we started with some like a simpler model so that we can talk about what is the algorithm and what is phenomena there。

So it turns out in the literature， there's a field which kind of started this trade off for a very long time。

 That is the multi arm bandage。Essentially， the first model we introduce in this lecture。

And this entire literature kind of really focus on this trade off and optimism is is a key idea。

 which we borrow from。Okay没。The key idea we borrow from this literature。

I still recall what is the multiam bandit。 Okay， that is we have like a banded machine with eight different arms。

1，2， kill a。The protocol of like Martin Ben goes follows。That's for T。From one to capital T。

The learner picks an arm。IT。I T is in。basicallysically the action set。

And then Lner observed a stochastic reward。All right T。

We noted this here the reward stocaping stochastic is important because we no longer have the transition。

 The previous argument in MDP， we can study theive reward is because usually transition is much harder to learn than the stochastic reward。

 but here because we have no transition so we have to like again say the reward is stochastic。

So we say have some normalization condition。Where we say I。Is always in 0 to 1。

 That is the stochastic reward is always bounded in some 0 to1。 And we have some expected reward。

Of I， expectation of I。 That is a。Random reward I'm going to receive for Iar is equal to。Little eye。

This is expected or work。So we'll talk about two slightly different goals。

 but both of them are like like standard goals in the this multi arm literature。 First。

 let's first talk what is best arm best arm is just defined as AI I star is equal to agon Max。I of R。

Essentially， this is the arm that achieved the highest expected reward。

 and this is the arm we eventually want to find。So there are two kinds of goals。The first goal。

Or sometimes we call it pack or sample company nicely。皆様様はこ。We essentially only want to find the。

The Epsilon optimal， Epsilom optimal arm。I had。So that。By defining the optimal arm。

 we see the reward expected reward of I hat need to be greater equal to I star。The best arm。

Subtracted by epsilon。 So we at most tolerate some epsilon difference。

And sometimes we also okay with not only just identifying an arm that we can also O with like identify a distribution D。

eppsilon optimal distribution D。So， that。The expectation。Of this reward， I， I sampled from D。

It's greater or equal to I star。Subtracted by Epsilon。 This is， we also find。

 Like if even if you don't I identify a single arm。

 but if you can see a distribution and we say in expectation， this is good。 This is。

 I'm also okay withers。And there is a second type of goal。A multi on bandit。

Which you can think this is like a stronger。Objective， which we want to achieve low regret。

Where the regret is define as follows。We they regrets？Up to iteration T。

 this is the number of iteration T。Its equal to the。Best rewarder you can of achieve。T times I star。

 This is like the。Best expected to reward your kind of truth。And I subtracted the。

Expect a reward you receive by picking your arm sequence。IT。So， this is essentially the。

IEx her rewards。If always playing the optimal arm。And this is the expected reward to receive。

By the learner。And the regret is very intuitive by its name。

 basically it says if a regret is very large， youll have a lot of regret。

 if a regret is small then then basically you don't regret much of not playing optimally。

So I just want to say this because we have normalization reward is in0 to1。

 So the regret skating is always like in0 to T。So regret' it。Regret it' never going to be。

Greater than you。 So basically， whatever you， if you trip some linear regret。

 and that's already like a trivial regret， that that doesn't say anything。 that that's like very bad。

 So in the， the non trivial regret it' like we want to say subline or like a square root T or something like that。

So we make， we， we kind of noted that the most important difference between goal 1 and goal 2。

 goal 1 essentially says。Player can play anything。As long。有序。

Eventually identified the epsilom optimalim arm。Don't really care about in the middle like what you are playing。

 you can play poorly， but as long as in the end you identify an optimal arm， this is good。However。

 in a goal2， you can think the second goal is like more difficult because the learner。好 the player。

Needs to。Find the good arm。Which is similar to the best on identification phase。But also needs to。

Do the。Play reasonably well。In most steps。So you cannot just play some like a terrible strategy in previous steps。

 And in the end， you realize what is I are。 In that case， you can like pay some order tea regret。

 which is like not what you want。So you can think this is like what we want to do in exploration。

And this is like what we do in exploitation。So the goal of regret actually naturally reflects the tradeoff between exploration versus exploitation。

So in reinforcement learning， although so far we only talk about exploration。

 like we never talk about the regret that we're okay with the sample capacity。

 but it turns out because they select like a sequential structure and we talked already talk about random exploration doesn't work。

So it turns out the idea developed for this balancing exploration， exploitation。

 the optimism actually is very useful in reinforcement mode learning。So that is in the multi arm Ben。

 We will talk more about how we're gonna balance explorationation。

 exploitation and motivates the optimism。 And then we will talk about how to apply the algorithm。

 the optimism principle to。To reinforcement learning。

