# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p40 P40 可预测状态表示 -BV1YsZHBZEyM_p40-

Guess what you do restart us。Okay， very last。Oh， I think that works。

Very last lecture of the semester。Just came back from the New's craziness。And。啊。Hello hello， O， O。

 cool， so。😊，Very last topic， which will be a little bit different and orthogonal to what we've been talking about throughout the semester。

 But before that， after today's class， I will have to leave immediately。

 there's a talk upstairs by Philo Thomas， my my speaker and my long term friend from UMass。

 his advisor is Andy Bardo， who together Wang touring award with which for the contributions to reinforcement learning last year。

 So today he's talking about some philosophical aspect of machine learning R L and and you know。

 and today's era。 Okay， so but so we'll talk about so throughout the semester， we' being。😊，Hello。

 hello， okay。 throughout the semester， we're been making essentially the mark of assumption。 right。

 So assume that whenever we talk about R， like you always start with like state action， reward。

 state action， reward， nursingty， right， But you realize that for most of the practical problem you run into the。

 the very， the very assumption that you're given like a state is like entirely questionable。

 And that guess to this。😊，🤧嗯。C formulation of partially ob system。

 And we'll see if we have time to talk a little bit about a predictived representation。

 which is very different and unique view of partially observable systems that that is a a part of the RL literature。

😊，Okay， so you know， we see partial obsservability essentially everywhere right。

 so especially nowadays like when we use large language models to model text sequences。

 if you think about each letter or each token as an observation what clarity this system is highly nonmark of right like there's no way that you can predict future tokens just based on the past token。

 just based on the current token you of course need a lot of like context from the like from the whole history。

 like you know， from the very beginning of the article all the way onto like you know at this point。

😊，Right and this is also like， you know， in video prediction， like the， you know。

 when you try to predict the the next frame in a game， you know。

 even approximately like this is not Markov， right， for example。

 like there are a lot of like moving objects in this game。And if you only see the current frame。

 you wouldn't even be able to tell like which direction those objects are moving into。😡，Okay。

 so now in Ontario games， I think it's pretty common that people use the past four frames because the game is so reactive and actually short memory that you can basically make it approximately mark of with these kind of settings。

😊，Okay， so a more prominent example is in robotics。 This is called slam。

 Does' anybody know what's the。Like， what's the full name of Slam， What does Slam stand for。

Anyone no。Okay， SlamM stands for Simultaneous localization and mapping。😊，Okay。

 so basically the idea is that you have a robot， you have sensors， right， You don't have state。

 all you see is sensors， right， if you imagine a robot like you're just walking randomly in a building。

 it may get into two rooms where where in the interior look identical。So in that case。

 like whatever these sees， the robot sees， the sensor readings are indistinguishable between these two rooms。

 but clearly its underlying state is different。Right， so then there's this problem。 Now。

 so you have like actually two intertwined problem。 One is estimate which state you' are actually in。

 right， But then like。How do we even talk about state when your robot only has sensor readings。

 right， So in the task of a navigation， you can confident talk about state if you have a map of the world or map of the building。

 right， And you guys say， my state is in this location in the map。

 But what if you also don't have the map。So you actually have two these two taskss you need to jointly solve。

 which is creating a map of the building， as well as use the current sequence of sensor readings to tell which room you're in。

 So we will see later like you know in the language of Po D piece。

 This is essentially estimating the system dynamics。

 as well as figuring out your current belief state theyre like or your current state representation they are actually you know intertwined in an interleave task。

 you can't solve one of them alone， you need to solve them jointly。Okay， so as usual for this course。

 we would like to start way to make it louder。喂 hello hello。😊，We would like to make it you know。

 mathematical。 So so let's say we。😊，Assume that we have some observation space O。 And for as usual。

 gonna assume that it's finite discrete。There's action space A for most of a discussion today。

 we're gonna admit the ashes because like most of the concepts are well defined。

 and you can already discuss a lot of them even without actions。

 So for many of the examples I will be given like you。

 think about it in the in the case of uncontrolled system without ashes。😊，Okay。

 and you have some initial configuration， which is analogous to the initial state distribution MDP。

 and you just draw a sequence。 if you don't have actions。

 you just draw a sequence of like observations，01，0203 and so on and so forth。

 and the whole thing is random， meaning that if you restart again and draw another sequence。

 the sequence may be different。😊，Okay。So this is essentially a partially observable system。

 like very generally defined。 And we know that Markup system is a special case that。😊。

In Markov system， in this case， it basically becomes a Markov chain。 that is whenever the you have。

 you satisfy this criteria， right that says。You know， whenever you look at a distribution of future。

 So tau is some time step that you know， that that is the current time step。

 And this is the joint distribution of some like K length future observation sequence。

This is your history。 This is all the observation you have seen so far。

AndWhen the future distribution condition on history is equal to future distribution condition on just the current observation。

 You have a markov system。 And in that case， we say that Otao is a state。 Okay。

 so you can also use the this kind of limitation。 So this symbol means independence。

 and this is a conditional independence。 This is future and history are conditionally independent condition on the current observation。

 Okay， so then you have a then then you have a markov system。😊，Okay， so， you know。

 one thing is that if you think about it， like a Markov system。

 assuming that your system is Markov in this particular context is actually extremely strong assumption。

 And you can see that simply by some parameter counting argument， for example。

 if you actually have a markov chain。 let's say you。

 let's say you have this you start with this general formulation that just says my system just emits a random sequence of observations。

 Okay， and then I add on top of that says my system is Markov。😊，Okay。

 then how many parameters do you need to specify the system。Well。

 essentially you can specify the system by telling me about its transition matrix。😊，Right。

 and probably also the initial distribution。 But that's even minor， even more minor， right。

 And how many， roughly speaking， how many parameters do you need to specify the transition matrix。

 How many。O square， right， because it' is a O by O matrix， right， So here O is state。

 So it's also S by S。Okay， so roughly speaking， that's the order。 Now。

 imagine you remove the mark of the assumption。😊，And have an arbitrary system。

 Let's say it's up to length L or some particular length。

 How many parameters do you need to specify a general， partially observed system。O to the L。

 right because essentially， there there are different ways to do it。

 One is say we're basically talking about a generic。

 completely general distribution over the entire sequence。

 So if you think about a sequence up to length L， then the the， the， the distribution。

 you have a distribution over O to the L different possible sequences。

 And all those numbers can be set like in abitarily freely。

Another way to look at it is that actually so here implicitly it already saying that essentially any partially observed system can be transformed into a market system if you define a history as。

😊，Right， because any like imagine like you can always sample from a partially observed system if you're given this function。

 which is given arbitrary history， including an empty history。

 it tells you what's the conditional distribution over the next observation。😊，If you have that。

 you can sample the next observation and then condition on the you can sample the first observation。

 condition on the first observation， sample the second one， condition on the first two。

 sample the third one and so on and so forth。😊，Okay。

 now I actually have to explain that in past semesters， but hopefully nowadays。

 people know what that sampling process is called。 What is that called nowadays， especially in AOMs。

😡，You sample the next observation repeatedly， sample the next observation。

 given all the historical observations， append to that and then keep doing what is that called？

Autoregressive， right， autoregressive sampling， yeah。So actually。

 yeah now in in the era of Ls is actually a great time to talk about like this stuff。 Okay。

 so so therefore you mention like you have order O to the L free parameters compared to O to the square。

 right， So which means that Markov is very restrictive and if you want to on the other hand。

 what it also means is that if you want to remove the markov assumption， A， like， for example。

 in you know in LMs in text modeling many situations， Markov is a terrible assumption。

 But if you want to remove it without introducing something something else。

 it's certainly intractable， even if your observation space is financeable。😊，Right。

 so in the markup setting， if observation space， in that case， it is stay space is fine and small。

 We know everything is tractable， but without it， it， it's not。Okay。Okay， so so therefore。

 we needed some structures， we needed some structures to capture the kind of partially observed system that we observed in practice。

RightAnd the example structure that mostly they're having studied so far is to assume that there's a small and finite latent state space so this is where we get to the latent variable models。

 right using slam as an example right So if you think about at every location。

 you have a sensor reading， you can have very rich different possible sequence of kind of sensor readings but if you look at the underlying latent state。

 Well， this is just like the building。 and you can just being one of these rooms and that's it right So there are all these like real world problems where the if you look at the sequence of sensor readings it's highly complex and there are a lot of exponentially many possibilities。

 but if you look at the underlying latent state， it's very limited and highly structured So in these cases。

 like it makes a lot of sense to introduce the latent state assumption to essentially regularize or put additional regularity constraints the systems so that learning becomes tractable。

😊，Right， so， and we can in do that to our definition earlier， right。

 So we still have the observation space O action space A again， like I'm gonna mostly ignore it。 Now。

 we say that there's this latent state space Z， for example， in the slam example。

 that's just the true location。😊，And then in this case。

 you realize that if the observation space is small and the latent state space is small。

 the whole process can be specified again by polynomial number of parameters。

 not exponential anymore， right because you can say this is the standard latent variable models。

 essentially， this is an HMM hidden market of models。 If you add an action at a reward。

 this become partially observed NP or palm DP， right， So you have latent state transition。

 So this is kind of correspond to if you if I mean this system。 if I'm mean this true location。

 I have the robot move in that direction， move forward a little bit。

 why I transition to a new physics location。 and maybe I have a certain orientation。

 that this is the what we call emission process。 So the is kind of like the sensor readings。

 the camera。😊，Like generous the observation you receive based on your true underlying latent state。

And in the general formulation， like， for example， in L M， sorry， in pump D and HM Ms。

 both the latent transition T and the emission process E can be stochastic。

 So it allows for like noisy sensor readings。😊，Okay。So。I'll skip some of these。 Oh。

 so here is something interesting。 There is some myth about H M Ms and Poty P。 And remember。

 we have someone from control background， you， right。No， not you， okay。Oh okay， you okay。

 So this is the slide where like the control students in my class always disagree the hardest。

 like I don't think there's disagreement， but there's just like different views。 So here's the thing。

 typically， as I mentioned， like in robotic settings。

 partial observability can often stem from noisy sensors， right。

 even like there are some cases where if you have perfect sensor。

 you can know exactly where your state is， but like， for example， you have GPS。 Okay。

 and let's say you're in a setting where your current state is the your current state is just your physical location。

 like long to like know， attitude， whatever。 right， And just like X Y coordinate on on the globe。

 and you have GPS， if you assume that GPS give you the exact location， you have the state。😊。

But you know that GPS is not， is not accurate， right？ And in fact， like underlying。

 whenever your phone or whatever receive the GPS second one tells you your location。

 underlying is running some common future， which is essentially like trying to calculate the belief state like trying to already like dennoise the the sensor observations to infer what the true location is right。

 So oftentimes， like， I think people think about， oh。

 we have partial observability as at least in these settings， because sensors are noisy。😊。

 there is some true underlying word state， and the more noisy the sensors are。

 the more partial viability I get。😡，Okay， now this makes perfect sense from a， you know。

 robotics kind of point of view。 I will see where this disagreement is。Okay， now mathematically。

 you can like， you know， go and see， say that， okay。

 can we translate that into something mathematical into a mathematical concrete claim that says。

 suppose we just have a underlying N DP or underlying mark chain。😊。

And we just vary the emission function， right， So this is kind of like saying， I have the robot。

 the hardware， the environment， everything doesn't change， Its just changes sensor。😡。

and then it will be tempting to say that if my emission process loses more information about the underlying state。

 I get a more partially observable process。😡，Okay。Of course。

 this is not really nailed down to like a precise mathematical you know， claim。

 but I think it's concrete enough that I think you get the idea。

The claim is that depending on how you define partial observability。

 especially how I have defined it implicitly in previous slides， this is actually not true。

 strictly not true。😊，Okay， so here's the thing。😊，Suppose your emission process so noisy that it drops all the information there is in the underlying state。

😡，Okay， do you still have a partially obsservivable process？😡，Well。

 you just have a process that every time step， you see an independent。In uninative。

 noisy observation。And if you see like how I defined Mark of Mark Mark of y before。

 it's this condition that says。The few the condition distribution of future observations given past。

It is equal to the constitutional distribution of future， given the current。 Now。

 with uninformative observations， that obviously holds。Okay， so you have a fullyier mark system。Okay。

 so now you know where's this disagreement， right， So like I've even seen like RO people。

 is like this is nonsense。 like clearly you have like partial observability。

 I think what you what we mean is like what do we think of the ground truth right So for robotics。

 your ground truth is like real world。 your grounded in the real world。

 and you want to accomplish certain task in the real world， right and the noisier。

 the worst sensors you get。 it strictly impairs your ability to decode the true true state and to accomplish that task。

 So in a sense， there is definitely a monoity that the worst sensors you get。 you know。

 somehow like the best policy you can achieve based on those sensors become worse。 however。

 this is different from how we define partial obsservability in a statistical sense。

 right So the definition I have before， the underlying philosophy in this case is kind。😊。

It's from a very RO and a statistics point of view。

 it's like not a hardware point of view that says as RO person， I don't do hardware。

 you give me the hardware。 So if you have fixed your design of the sensor。

 I treat that as whatever it is。😡，Now， my goal is not to say， I'm gonna。Handle the task。

 accomplishlish the real world task perfectly。 I may not be able to do that。

 I do whatever the best I can do， given whatever crappy sensors you've given me。

RightAnd if you given me me completely uninform sensorenss， there's nothing I can do。

 and I'm happy because then there's no， I don't have any job to do。Like， I can just go back tell you。

 like， change your sensor。 Like before you give me good sensors， I'll just like。

Take a rest and lie on the beach and do nothing so in that case。

 I claim that the system is Markov So from our point of view。

 like the whole point is whether there's partial observability。

 at least defining a statistical sense is whether to predict future。

 whether it helps iss not whether you can or cannot predict future in an absolute sense is relative sense is whether there's additional information in the history that helps you better predict future compared to just rely on the current observation。

 if there is there's partial observability， otherwise it' not And this is also like in a sense。

 very practical if you think about algorithm design point of view， right。

 So suppose you have crappy observations， but they happen to be Markov。

 then whether there' partial observability， what what directly dictate whether you would invoke these complex like partial observable palm concepts in your algorithm design or whether you need to design additional history futures or not。

So I think this definition， actually， you know。Perfectly matches， you know。

 these kind of practical decisions you have to make If you have crappy sensors。

 but it happens to be Markov。 Well， you just do run Markov algorithm。

 There's nothing else you can do by looking into the history。Okay， so that's one thing。

I'll skip this， which is a little bit okay。Okay， so sorry， give me a second。Okay。

 so enough about formulation。 let's talk about something concrete， right？ So like， okay。

 suppose you have a partially obable system。 you want to do some learning。

 You want to do some modeling。 You want to learn a good policy and whatnot What's the key challenge。

 Well， one of the major challenge here is how to come up with stable representation。 So for example。

 in text prediction。 like suppose you're using like nowadays everyone use transformer。

 But if you're using like a recurrent neural net， then essentially。

 what you neural net does is like it passes over the past。

 the past tokens and come up with a compact fixed length hidden vector summary。

 like essentially embedding of all your previous text， right， So even transformer gives you that。😊。

RightSo for SlamM， you map the history of sensor readings to like essentially a distribution over like you try to decode to the best you can。

 the physical location， it often comes with some uncertainty around it。😊，Okay， so this。

 this backgs the question like， you know， when we have a partially observed system。

 what do we even mean by state， right？ So like you may think about state as， oh， if we have a latent。

 we have a definition of latent state， the latent state is a state。 We'll see like， that's not true。

 But note that latent state is essentially introduced as an additional structural assumption， right。

 we could just talk about the partially of observed system。In。

 in terms of its entire distribution over the observation sequence without even mentioning the notion of latent state。

 So in that case， when we say， okay， the state of the system， a compact of the state of the system。

 what do you even mean。Okay， so here is a precise definition。 So state。

 and this is something that it may challenging you。 like it's， it's kind of subtle。

 but it's very easy to make mistakes。 We'll see a kind of a couple of examples。 So， first of all。

 State is a function。 State is not a variable。 State is not a value。 State is a function。

State is a function that maps history。 So here is H。 This is like to sum space。 Okay。

 and it satisfy this， right， so here I use T。 you know， like there's some real。

 really weird convention here。 So I'm using I'm using Tau as the current time step。

 I'm using H as history。 I'm using T as future。 because this is like weird convention andRrs。

 but bear with that for a minute。😊，So what you need is basically the kind of conditional independence that you've already seen before right but the more general version that says the conditional distribution for future given history should be equal to the distribution for future。

 given fee， whatever you propose as a state， the function fee of H。

 that is p extract information in H， all the information that is relevant for predicting future。

 it may throw away like information that is irrelevant for predicting future。

 as long as your p satisfy this condition， p can be called a state。😊，Right， so in that case。

 when you have a Markov system， what is a state， what is fee， Well fee is just taken in our history。

 D everything before just keeps the last observation。s that's a mapping， right， and that's a state。

开始。No， no， no， so because because because fee operates on H， right。

 So whatever information there is in fee of H is strictly less than like not strictly。

 but generally less than H。 So you can predict T better than H。 So it's always one side did。😡。

So by sufficient， it basically says like they match。😡，Like if you think about inequality。

 one thing you can think about is like， for example， the uncertainty about T， right。

 you can measure that by like entropy or whatnot。 If you measure by entropy。

 this is always less than which way direction。 Yes。

 it's less than or equal to because you can you can always make the， by definition。

 you make the best prediction here。 What this just says like， well， this makes。

 this matches the best you can do。 So then is say equality。😊，Okay。

 so that's what sufficient statistics mean。 Sic statistics often means just like you you， you， you。

 you have a function of something that throw away some irrelevant information that for the purpose of the job you care about。

 it does equally good job。 So that's a sufficient statistics。Right。

 for like a exponential family distribution， like， you know， some， some of this moment is a。

Sufficient statistics， that is for this distribution。 You only need to know its moment。

 It fully determines the full distribution。 right， So that's the kind of by similar idea。Okay。

 so this is actually where if like like mistakes are made the most。

 so what are functions that are state right so for any system there' is always a function that is always state。

 what is it？😊，It should be very trivial by definition。Identity mapping， right。

 Just maps history to itself。Of course， it will satisfy the definition of state。 Like if， if， if。

 if P is， if p of H， sorry， if p of H is equal to H。嗯。Then， of course， this holds， right。

 So this also goes to what I was saying。 Any partially observed system can always be translated to a markov system if you treat state treat history as state。

 right， because the， because with the distribution over the next history。

 while condition on the state， the history， you predict the next observation and then append it to your old history。

 your history grows like one lens longer。😊，Okay，Hisory itself。

 it turns out that there is another one。 Okay， there is another function that you can define。 Well。

 that function will be dependent on the particular system you talk about。

 but there is a generic way of defining a function that is always a state。😊，try。Okay， what is it？

Of all future。 Okay， is that because you work on something in your project that is related or you learn that。

They talk about this or this is like from Sttocaastic processes or what？Conciouss that， okay。

 interesting。 Yeah， yeah， so， so this stuff， the PSR stuff has a very strong connection to a lot of things going on in stoing processes。

 you know， market of chains， like， you know， the theres intersection between the two。😊，Okay， now。

 so from practical point of view， when you think about latent variable models。

 there's this very common， very important concept called believe state。 Okay。

 so belief state is the conventional the posterior over latent state， given history。

 So this is always a state。 okay so so and this is exactly like， for example。

 in slam what you calculate， for example， what you use in common future。 So in general。

 note that with noisy sensors with noisy emission probabilities。 given a history of the observations。

 you can never precisely pinned down the exactly latent state at a time。

 So the best you can do is to form a posterior distribution。 Okay。

 so it is like I'm not exactly sure which room you're in。

 maybe you're in room 101 for 20% of the probability。

 maybe you're in room two in like with 80% probability。

 that's the best you can do and that posterior distribution。

 if you do have the latent state structure is a state in a sense that when。😊。

Predict what's going to happen in the future。Condition on the latent on the belief state is enough。

Right， so this immediately gives you like， some of the。some of the results in Po DP， for example。

 if you have a partially observ MDP， we we know that optimal policy。

 there always exists optimal policy that it only depends on the belief state。😊。

Because that's all you need to reason about what's going to happen in the future。Okay。

 so now here are interesting things。 N things that are clearly enough state， but people call state。

 Okay， so we'll see。 so first of all， like it's observation， right， So， for example， in ari。

 all these like pixel based games when you see a screen， is's really an observation。

 It's not a state。😊，And now I've basically given up at some point。

 like I think when I started as a faculty， I was still fighting this uphill battle。

 It like this is not a state。 This is the observation。

 And then never in different talks about that as like But there is some very concrete meaning that this is not a state。

 for example， I recently wrote a like blog post as well as a paper that is not intended for publication about it is that if you think about state resetting right So in a simulator。

 you can always reset to a previous state right， So suppose someone gives you a game frame and say。

 please set the simulator to this state， I want to keep sim from their owns。 Can you do that。😊。

No one can do that， right？ So what you need， How， what do you need to actually reset to a state to keep simulation forward。

 You need a dump of the Ram configuration at the， you know， at at that plane， like this。

 this mirror observation is clearly not enough， right， So it it doesn't support， you know。

 setting the simulator to a particular configuration and and， and， and keep s onwards。

Here's the interesting thing。 So what about the hidden state， right？

 So suppose you have this robotic setting。 So this is the most confusing one。

 Supp you have this robotic setting where you have noisy sensors。 Okay。

 and let's say when you let's say we model it as a latent variable model like HMM。

 And let's say the trajectories， you have the observations， which is the noisy sensor readings。

 But you also like at least the it exists that you have all these ground truth latent state。

 which is like the real world locations， right， conceptually， at least they exist。

 Why like say at any point， you have the noisy sensor readings。

 and there's also the corresponding true like world state。😊，Is that a state？Okay， good。

 But now let me tell you that is satisfy the mark of assumption。 Oh no， Okay。

 so at least in the sense that condition on the true latent state。

 the future observation and past observation are indeed conditionally independent。Okay。

 so it's latent state。 the precise value of latent state a state。The answer is no。 but， but。

 but what what's the reason， Why is it not a state。No， that's not。

 So when we talk about whether it's a state or not。

 you can imagine that it's orthogonal to whether you know the system dynamics， right， For example。

 in order to precisely calculate belief state， you also need to know the food dynamics。

 So that's like two separate questions。No， you can。If you have the latent state。

 you can do latent state transition and emission and transition emission， you can predict the future。

 Actually， it， it gives you that a capability。😊，Yes， it's not a function of history， right， so。

That's why I said， like this is maybe the counterintuitive part of the definition that fee is a function of history。

 of the observable history is whatever maximum useful information you can extract from the observation history itself。

The true value of latent stage。First of all， mathematically， it doesn't exist。 Okay。

 so mathematically， when we just talk about a distribution。

 we can just talk about the distribution of observables。 then there's no true value of latent state。

 Okay， now like when you roll out a trajectory， let's say in a simulator。

 you can generate that true latent state。 But that state， as I said。

 like when you only given the observables， the best you can do is to decode a posterior。

 you will have some uncertainty。😊，But that true value of Le state is giving you the full certainty。

 It has additional。Information， privilege information that you are not supposed to have access to。

 This is not a state because it's not computable from the， from the observable history。😡，Okay。

 so that's why， you know， this is also， it's also related to what I said。 like， you know， the。

 the roboticists view versus the， you know， statistics view of what it means to be a state。So yeah。

 so right， I think I think people would agree that the term state is obviously overloaded， right。

 but at least in RL， like in the old school way and borrow terms from statistics。

 state has this extremely precise and crisp meaning is a sufficient status of observable history。😊。

Okay， that's what we agreed about， yeah。Like for other thing。

 like the thing that if you don't call that， like， what do you call it。

 Like s studies of a history is like too long。TPs in state automated。No。

 MP is perfectly fit into this。 It's a special case of this。But but in the MDP setting like this。

 because there is so much structure， the notion of state coincide with many other different notions so that you may think that oh we're thinking of that notion of state。

 but it's actually thinking about Po DP make this like crystal clear like like with all these notions。

 they overlap in they coincide in the MP， which is a super special case。

 but when it's not a special case， all these notions start to differ。

 And you have to ask yourself like which version of the state do you mean So that's why we have this notion of like world of state where state is a colal name。

 but people adopt it all the time， but in the context latent variable models is it means that the precise value of of the latent variable model。

Okay， there's also agent state， which is like， for example， you have a transformer， you have an R&N。

 whatever it computes a state if your agent is good enough。

 you may argue that it should you should have it probably has approximate notion state。😊，Okay。

 so issues with latent variable models。So typically。

 like the way to learn them is E M expectation maximization。 Now， E M has a lot of issues。

 Like it's not really MLE It's only approximate its subject to local optimum。 And more deeply。

 there's something， I guess， philosophical okay， so this from here on。

 there's a little bit of philosophy here。 So which is really a driving force for studying what I'm gonna introduce in。

 is that latent state is really on grounded object， right， So as I mentioned， like really。

 we introduce latent state to help impose structural assumptions on the observable distribution。

 right， but really， what we're talking about， we're just talking about that observation distribution。

😊，RightAnd introducing latetnt state is just saying that among those whole space of like exponential degree of freedom of all possible distribution。

 we're only interested in like a particular very small subspace。

 and we use latent variables to help us express subspace。But in principle， and you will see。

 there might be ways to just talk about that subspace。

 leverages properties without ever talking about the latent state。😡，Okay。

 and and because later say basically doesn't really exist， right like。You know。

 there is if you go to you know the philosophy level of like talking about idealism versus materialism and so on。

 you could like someone would say like， for example， maybe maybe we're all in the matrix world right。

 everything is just illusion and but there's something still real right。

 to be is to be perceived and that that that like I still have my sensory motor experience。

 Well this is real for me， whether it's generated from some real ground physical world or it's just some like electro signal from like a matrix like machine。

 I don't know right， But I pretend that it' generated from a real physical world where where the physics laws that we know as we know at least in the regime or interesting apply and so on so forth。

 because they're useful， they're useful to help me reason about my sensory motor experience。😊。

For me to think about what's going to happen in the future and for my decision making。

 Not that they're really real， right so。So therefore， this is the question。 And then this is the。

 I guess the get to the technical part iss actually interesting。 So it turns out。

 and this is what this particular subject URL talks about is it turns out there's a way to leverage the latent state structure without ever mentioning the word latent or hidden even once。

😊，Okay， so that you only work with observables。And this is the part。Okay， any questions so far。

 so I'll get into this more technical part of the slides。O。

So in order to not talk about that so let's talk about the there's this definition of system dynamics matrix again。

 like if you study that you probably have seen a version of that in control theory。

 like Han matrix and all of that。😊，So， so again， we're thinking about just the simpleimst case。

 you have a， you have a， you have a stochastic system that is partially observed。

 and each time step you receive one of the a random observation that come from a finite discrete space。

 right So here I'm just using like， say weather prediction as an example。 Of course。

 in real weather prediction。 You just you don't just rely on historical data like this。

 but this is just a toy example， right， So every day you receive observation that can be like sunny raining and so on。

 Like there are a couple possibilities。 You just have a sequence of these。

 you want to make predictions。 And let's assume that maybe there's a small number of latent states that generate this process。

😊，Okay。😊，So what you do is that you define this infinite by infinite matrix。

Where the indices on the row and on the columns are basically short sequences of varying length。

 So epsilon here correspond to the empty sequence。And here you have length  one sequence。

 length 2 sequence， length 3， and always to infinity。Okay。

 so the the sequence on the rows correspond to future。 the sequence on the column correspond to past。

 and you have an entry here。 What you do is that you just combine the past event and future events。

 cancate them together， you get just a longer sequence， right？

 and in any of these like you know partial observed systems in the uncontrolled case。

 if I give you a sequence of observations， it always has a probability。 right， just like like。

 let's say here just says if I just observe a sequence of observations from the initial configuration is random。

 Well， there's a probability that the first three symbols observation I get is precisely snowy。

 sunny raining right， you have that probability。 Just put that there。😊，Okay。

 then you fill the entire matrix with these probabilities。Okay。

 so this is called a system that it makes matrix。嗯。

Now it turns out that this matrix tells you everything about the system。😡，Right， in fact。

 even the very first row or the first column already tells you everything。

Because we've said that really from an observable point of view。

 the only thing that matters for a system is just the distribution over observation sequences。

 And if you care about what's the probability of a distribution。

 what's what's the probability of a given sequence， Well。

 you just look it up either here or here and look at what's the probability right So either you can treat it as past and there's no future or there's no future。

 there's no past and that whole sequence is in the future either way it would work So actually。

 this this matrix has a lot of redundancies。Okay。So we have this matrix。OK。Now。

 we'll talk about redundancy next。 but for now， you can show that if this system is actually generated by HM with a small number of latent states。

 let's say N。 It turns out that the rank， just the standard matrix rank of this matrix is literally bounded by n。

Okay。And I'll not to approve I'll not to detail proof here， but the kind of proof if you remember。

 like this is kind of like a similar strategies as we did in the Belman rank stuff is like for any pair of column and row indices。

 You look at the entry here， which is the probability of history and future con together。

 you show that it can be written as the do product between two vectors where one only depends on history and one only depends on future right。

 And like this， this is the the do product because it's sum Asian Z and you basically it's the do product between this as a vector over Z。

 This as a vector over Z。😊，Right。So， and， it turns out that this and one thing you realize is that this part。

 if you， if you turn that into a condition， like conditional of this given age。

 is basically belief state。Okay， so this vector is proportional to belief state。

 If you divide that by probably of H is the belief state。

 And this is a condition that it state what the future distribution。Okay。

 so this gives you a way to talk about。 So in the future when， whenever you say， okay。

 dealing with general partially system is clearly intractable。 I want to inject， you know。

 inductive biases and structures。 I'm happy with latent state assumptions as a structure。 Well。

 you don't need to talk about within state anymore。

 You can just say I assume that the system dynamics matrix of my system has a low rank。😊，Okay。

 so this， this way， like this matrix only has observables。

 It doesn't even have the notion of latent state。 Everything is of observable probabilities。Okay， so。

 as it turns out， systems with rank N is slightly more powerful than H M S with N states。

 There are some weird， very corner case systems that have a bounded rank N。

 But if you need to model it as HMM， you need infinite many states。

 But so there's some weirdness there。 But in practice， that difference almost never matters。

 So I'm not mention that。 but but just keep it in mind。 So for practical purposes， roughly speaking。

 you can think of rank N。 like this rank n assumption roughly equivalent to like having N latent states。

Okay， so the other thing is that this definition automatically gets rid of all the redundancies。

 right， So when you have HMM within latent states， it doesn't really necessarily like like some of the latent states may be dummy。

 like some of the latent states may never be used or there may be a way to reduce the number of late states So that's also why you know。

 latent state is like ungrounded object It like it's not clear that you' have done like minimization that that your latent representation is actually the most succinct。

 But if you talk about this So that is to say with the same observable behavior you can model it with many。

 many， infinitely， many different you know， latent variable models So， for example。

 you can have dummy states And even for the same number of late states。

 you can permate the label of the latent state and so on so forth。

 there are many different ways to model the same observable sequence。

 But when we are talking about the rank of this matrix。😊，There's no ambiguity whatsoever。

 There's just one rank。Whatever it is， it is， it is that。

 So there's no all the ambiguity and redundancy goes away。Okay， so。

 and it turns out that so what what this is going to is this literature I alluded to earlier called predictive state representations。

 which is a way in the R literature that handles the the partial obability in a way different from latent variable models。

 And what it does is that if you can estimate some of the entries in this matrix。

 It does those two things simultaneously。 One is learn the system dynamics and two is coming up with compact and useful state representations。

 right， So these are the two interleave tasks that， like， for example， in Sla。😊，Okay。

 so now for latent variable models， this is kind of like coming like estimating the emission and latent transitions。

 And then if you have that， you'll be able to compute believe state。

 which is a compact summary of history。😊，Right， so because history is like varying lens。

 is's very difficult to work with。 But if you think about belief state， it's a fixed lens。

 real value vector。 It's much easier to work with。So we'll be able to do things like that here。

 And it turns out that the only two properties of this matrix you need to you need two very simple properties of this infinite by infinite matrix。

 The first property I already told you that is's a rank。Okay。

 and in order to derive all the learning algorithm， everything， you just need one more property。O。

So we're talking about this probably now。 So let's say we pick up a random sequence over here and there's this probably of this sequence。

Okay， remember， this whole matrix has tons of redundancy。In fact。

 this very entry will repeat a number of times in this matrix。How many times does it repeat？R， yes。

 up to one。Plus one， okay， because see， like what we did is that we take the the column index as pass。

 take the row index as future， concatet them together and ask what's the join probability of the entire sequence。

 But when you ask about the join probably of the entire sequence。

 there's no future and then past anymore。Right which means that you can cut things in the middle arbitrarily and split the what's considered past。

 what's considered future arbitrarily， and they will all give the same answer。

So you can split it here。 So you have empty past all future， one step past two future。

 two past one future or all past no future。Right， so it exactly repeats four times。

 which is number less plus one。And they are aligned in this roughly speaking， it's not exactly。

 but roughly speaking， anti diagonal direction。Okay。

 so there is a mathematical term for matrices with the structure is like。

Have you learned that from the course， which is called a Han matrix。😊，O。😊。

And turns out that this is all you need。 You need a hand matrix。 You need a you need a low reness。

 and we're ready to talk about like learning algorithms in ways to compute state compactly。Okay。

 or we're ready， so okay。😊，So， okay， so let me try。 Okay， so PSRs used to be a very obscure and very。

High interest bar topic。 It seems like super complicated and so on。 I'm trying to tell you how。

You can just understand it in one slide。😡，IfIf you focus， okay， so let's try， so。

If a matrix has certain rank。 So here for now， let's say it's rank 3， just arbitrary in the number。

 Let's say rank 3。Then we know that you can always find like three rows。

That are maximally linearly independent。Right， but it may not be like， for simplicity。

 I'm just picking those like length one sequence， but it may be like， you know， this， this。

 this or this， this， this， like there are many choices， but I'm fixing one of the choices， okay。

And and maybe in the real system， these three are actually nearly dependent on each other。

 So just let an example。 Okay， so if you have these maximally linearly independent rows。

 like what happens to the other rows。There are always any other role in the matrix is always a linear combination of these rows。

 correct？Right， okay， so good， great。Wehan was there， okay。

So what I'm telling you now is actually the， the parameter that actually specify dynamic system。

 Okay， so remember in prompt or HMMs to specify system。

 I need to tell you the lant transition and the emission function。😊，So， here。

Like matrixrices like this are well specify the full system。 Okay， so what are they。

 So you take the indices of those green rows， the max literally independent rows。

 And for each observation， a pen this is pre pen， Prepen the observation to every single event in your rows。

 right， So maybe your rows has a less one event， a less two event， then after a pen into it。

 you have a less two event， less three event and so on。 right， just a pen。

 like see a pen the sunny observation to every to all the indices of your green rows。 Okay。

 now you get these purple rows。 and by the thing which just talk about。😊。

Each row here is always a linear combination of the green rows。

Which means that you can have a matrix。 So here are 3 by3 matrix that compute the purple rows from the green rows。

Right。Okay， so that's that's it。 Now， you do that for every single observation。Right， for let's say。

 for raining observation， you prepare that to all the green indices。

 you get these and then define new matrix that compute these。😊，Okay。And。In addition。

 you also look at the， the， the， the green vector over there。

 which is the column in the green rows that correspond to empty history。Okay。

 that's actually analogous to the initial latent state distribution。

 It defines the initial configuration of the system。😊，Okay， so now here is the magic time。

What I will show you is that with these matrices and that green vector。

 suppose I know these quantities。I can make any prediction about the system。Okay， so remember。

 a system is basically specified by saying， if I have the capability to say。

 give me arbitrary sequence of observations， I can tell you its probability。 Then I'm done。 right。

 So I just need to have that that capability。😊，So let's say we try to do that， right。

 So let's say we， we choose a length 2 sequence and say， what's his probability。Now。

 the only thing you have is I have this green vector。 I have these matrices。

 I need to be able to compute that from these model parameters， which I claim to be model parameters。

Okay， are ready？Okay， let's go。So the first thing you do is that you look at the first observation in the query sequence。

 The first observation is sunny， right， So you just start with the green vector。

 multiply the B Sun matrix， Okay， which you get， you get the purple vector， right by definition。

 because the B sunny matrix， flip the green rows to the purple rows。😊，Okay。Now。

I claim that you can find the purple vector in the green rows again。Why is that。Now。

 note that how do I get the how do I get the indices of the of the purple rows。

They are are the indices of the green rose， but like with a sunny observation。

 like prepaned to each one of them。Okay， so where can you find this vector in the green rows。

Under sunny， right， So， so here， this is kind of like saying there's empty past。

 but all of these are future。But I can cut the， I can say， okay。

 I consider this as the current hand step。They have a shared past， which is day one sunny。

 and that's my design because I picked these purple indices this precise way that they share the same observation which is sunny right and then the rest indices exactly are the indices of the green rows。

😡，And this is an leveragingaging Hanquiness。Right， so these two are exactly the same vector。

So this is what happens whenever you multiply a matrix， you go down and by highness。

 you can move back to the green rows。😡，Okay。Okay， then you do it again。 right。

 the second observation is rainy。 You multiply that by rainy。 Okay。

 you get to the purple rows over here。 they correspond to raining。 And again， here is theres。

 So if you look at the events correspond to these， This is day  one， sunny， day 2 rainy。

 and then the green row index。 day 2 raining， the green row index。

 day 2 rainy in the green row index， right， So instead of like thinking， oh， I'm still in day 1。

 now I move to day 2。😊，Now， sunny and rain all become past。And future is， again， the。

 the green disease。Okay， oh， I forgot。 There's one last parameter you need。 So we're almost there。

 right？ So how do you get。That entry there， which is the probability from the， from the。

 from the vector we currently have。II forgot there's one additional parameter you need。

 So think about what parameter would give you that， given the， the， the， the。

 the vector would currently have the purple vector。So remember。

 any row can be expressed as a linear combination of the green rows。

 So we just need a vector that express the very first row using the green rows。Okay。

 so that vector will just give you that entry， which is the probability we need。

 given the purple vector。O， so in in HM Ms， if you think about how do you cap compute the。

The marginal probably of observation， which you do is that when you use latent state。

 you do a lot of computation。 Eventually， at the final step。

 you will marginalize out the latent state， you will multiply a like essentially all one vector。

 So that be infinitefinly essentially play the role of that all one vector。

 So all these computation actually， you can find their correspondence in like like latent variable model computations。

 But it's like it's just more generalized and it doesn't rely on notion of latent state。😊，Okay。

 so this is the general prediction rule。 If you care about the probability of a general observation sequence。

 what you do is that you start from the initial green vector Moified by the corresponding B matrices for each observation。

 eventually compute what we call the normalization vector。 And thats it。😊，Okay， so and furthermore。

 like if you want a state reation， I guess I will talk about it next。Basically。

 if at any like before you compute this normalization constraint， the vector you get。

 it contains the magnitude of this prediction， which means that your vector becomes smaller and smaller and smaller。

 but its direction。 if you normalize by the probability。

 its direction is basically a good state representation。Okay。Now。

 so I just convince you that these simple assumptions allows you to express the system using a small number parameters so that you can make arbitrary predictions using these parameters。

 And now the question is， how do we learn it， right？ Well， it turns out that。😊，Like， you know。

 the the key matrices， like you can learn the be infinity and grain like in similar ways。

 but the the the really key things you need to learn are these B matrices。Right， well。

 these are the matrices that。Linially convert some rows to some other rows。

And all those rows are just some observable probabilities。 So here is something super simple。

 Just you， you also pick some maximally linearly independent columns。Okay。

 estimate those probabilities just by observing many， many sequences and then do a linear regression。

 listen。Okay， so那 thats。😊，So this is pretty shocking。 if you think about like， you know。

 in pump D P in latent variable models， like E M is a practically very useful algorithm。

 but it's extremely hard to get， you know， computationally efficient algorithm that has asymptotic you know。

 consistency guarantees。 But this guarantee is like trivial。Okay， because in the limit。

 when you have like even number of trajectories， apparently。

 all these probably frequency estimation will become accurate。 and you do a matrix inversion。 That's。

Now。One thing here that is hidden is that so suppose you run this algorithm。

 it turns out there are some big hyperpar you need。 I didn't tell you， what are the hyperparameter。

Like， if you were to implement this algorithm， you actually run into issues。

 Like there are something that you wouldn't know exactly how to choose， given the practical problem。

Exactly， right。 So I said that these green rows and also the columns。

 they are maximally linearly independent。 How do you know whether certain rows of a matrix are maximally linearly independent。

 Well， you need the whole matrix to tell that。 But the whole matrix is unknown， right， and。

 and also estimating the probably a very long sequences is very difficult。

 So it's kind of like a chicken and egg， you， you wouldn't know them， like。

 if you don't know the entire system already。Right， so that's in some。

 in some literature iss called the discovery problem。 Its not completely solved。

 but there is something you can do。 For example， you can use as large。

Sas and set of green rows and as many columns as possible。 But then you do some SVD， to long。

 some low rank projection and then do linear regression after that。 Okay， so not go into detail here。

 But this is called a spectral algorithm for learning Ps。

Then you can show that as long as you use a large enough set that contains the maximally linearly dependent rows and and columns。

 And when you do SVD and you drop the smaller singular values， use the right rank parameter there。

 like it's still consistent algorithm。Okay， so now this literature is called predictive state representation。

 as I mentioned， like it because precisely this。 So it turns out that so remember。

 like in in L sorry in H M M's palm D P， the compact sta representation is the belief state， right。

 Posterior over latent state given history， right， So that's something like super useful that summarizes the history into a real valued fixed length vector。

 So here essentially implicitly， we're doing something similar。 However。

 remember that we don't have the notion of latent state。 We can't even mention latent state。

 We need to use something else。😊，So it turns out that in the prediction process of using the PSR model。

 the silver representation is this， given any history， so the T。

 the green tea is the set of events in those green rows。

 You can think of those as characteristic events of the system。😊，Okay。

 so the state is always the prediction of those future events。

And we're using that as a state representation。😡，And here's an example that I always use every year。

 So suppose suppose suppose here， all I can see is observations is like， for example， like。

 like whether you guys have shown up in the class and so on and so forth。 Okay。

 let's say the latest variable is whether you have finished your project report。😊，Okay。

 so maybe like let's say we're in the due date。 And there's this latent variable that I'm not seeing。

 I want to predict like， think about， you know， what in the future and so。

 So one way to represent the state is to say， okay。

 what's my guess of the latent variable is whether you have finished your report。 right， Okay， say。

 okay， the procedure over that is a state of summarizes my guess of you know。

 what you have been doing。😊，Alternatively， I can say I can， for each one of you。

 I can predict your future grades。Okay， because the grade you earn is directly associated with whether you have complete your report on the due date。

 See like if you think about it， like the， the， the， the the。

 the future operation actually contains information of the latent state。Okay。

 so this gets back to the question， which you are like， you already know the answer。

 talking about you So it's like， what's a the other trivial function that is always state， right。

So remember， something is a state。 If condition on this something。

 the prediction of future is equal to the prediction， given the precise history。😊，Okay。

 so here is something crazy。 What if this something is the prediction of all possible future events。

Right， then when you make predictionition given on that。

 you're just reading off the predictiondition from your like from from this fee， right。

 So essentially this saying， okay， I've seen history。 I'm asking which state I'm mean。

 I say I'm in a state such that the you know， the probably a future happening。 A is this。

 The probably a future happening。 B is this。 I give you all the future predictions。

 I say this is the state。 I mean。Right， and then whenever you ask， what's the po of， you know。

 that future， it would say， well， it's already in my state representation。Now， at first glance。

 this is utterly useless because before when say， oh， we is use history estate。 Well。

 like that's exponential that that you know， the thing you know grows exponentially with the length of history。

 but at least it's finite。 But here you're saying like， oh。

 you should use like infinitely length state representation。

 Well that at first glance it seems utterly useless。But what's the key observation。

The key observation here is essentially saying that， well， of course it's useless because in general。

 nothing is tractable if you don't inject any assumption。😡。

But if you're happy with latent state assumptions， what it turns out is that all those infinitely many predictions。

 they' are actually correlated。 They're actually linearly some way dependent on each other。 that。

 in fact， if your matrix system dynamics matrix has rang in or your your latent variable model has number of latent states bounded by n。

 then among all those infinite predictions， you can just pick n of them。😊。

And all other predictions will always be a linear combination of those and characteristic predictions or the prediction of those what I call characteristic events。

 So those events in the in PR literature is called like core future or coret or minimally coret。

 Like there's something， some， some terminology for that。😊，Okay。

 so immediately based on this observation， you collapse the infinite dimension state representation to a finite and very concrete small set。

 So whenever we talk about what my state， you say， okay。

 look at what the prediction over these particular future observable events。

 My prediction with those events are my state。 And in fact。

 mathematic can show that under certain you full rank condition。

 if your latent variable model is not degenerate and so and so worse。

 this representationation can be literally written as a linear transformation of your belief state。

 So they which makes sense like they contain the same amount of information。😊，Okay。

Ill skip this part。 And it turns out that so if you remember this is our prediction rule right。

 that is be infinity times all the B matrices and times the initial B star is that initial green vector。

 So it turns out that if you have HMM without having this predictive interpretation。

 you can also write down these matrices in a similar fashion where the initial green vector is the initial latetnt state distribution these B matrices correspond to latetnt transition times the diagonal of of the of emissions and the final B infinity is the normalization vector。

 which is all one。 So then you can fit the HM prediction rule also in that。

 and the in in some part of the literature like like this general idea has been discovered and rediscovered numerous times across different disciplines。

 but different disciplines like focus on different things sometimes given different interpretations。

 for example， early。😊，AndThere is a line of work called Observable operator models that actually emphasize these prediction rules and parameterization。

 but not as much as the predictive state interpretation of what everything is doing。

 as well as the learning algorithm and so on。😊，There's also like in C S related field。

 there's also a study called weighted finite automata， which is very related。 By the way。

 like a lot of the things we studied， like including earlier concepts， actually。

 there's deep connection with like automata theory in theoretical computer science。

 So like another example， if you remember is by simulation。

 by simulation is a concept from automata theory。 because this is all thinking about finite state machines。

 dynamicyal system， state transitions and all that。😊，Okay， so。So yeah。

 this is like like a weird example where its it can be it can be represented by PSR waves a low rank。

 but if you represent as a HMM， you need infinite number of states。

 This is where you basically draw something like a sine curve and turns out that so and the number here it's just a binary system and the number here represents the probability that you're gonna see one versus0 in the next observation condition on the history or something like that and it turns out that you can represent the system using just a rank two PR model but you can set the like the period of the system arbitarily so that if you set the period of the system to be like a irrational fraction of the period of the sine waves or what not like you can get like like a never recurring sort of system。

😊，That is hard to be modeled by Iman。 So this is the corner case I was talking about。 But again。

 like for practical purposes， like just ignore ignore ignore net。

 this is pretty much just pure of mathematical interest。As a final thing。

 So we mostly talk about unconttrorolled systems。 and there are like ways to generalize this to control settings。

 So in the control settings。 So remember， like a lot of their we did was based on this observation that you can fully specify system by simply asking。

 what's the probability of a arbitrary observation sequence right， now in the control setting。

 you need to be able to ask similar questions。 So it turns out that the the corresponding question you need to ask is if I were to take action sequence。

 a0， blah， blah， blah， what is the probability of observing observations O1 all the way to OL。😊，Okay。

Now， if you think about it， like I think many people have this like misconception is like if you look at it in the first glance。

 it looks like if I can only answer these questions。

 it looks like I can only reason about what we call open loop policies So in control。

 you have these open loop policies that is I preplan a sequence of actions and whatever action I take down the road cannot depend on the random observation or state I see that actually occur in the system。

 So this is called open loop policies。 So this actually gives you the flavor of open loop policies。

 but it's not it's a completely general description of the system that you can reason about the consequence of close loop policies even based on that。

 Well， the reason is because like here is specific very concrete sequence of observations So essentially it's kind of likem first I'm taking a0。

 I'm observing1。 and and I'm basically taking a1 condition on01 and0 and so on so forth。😊，Wai。

 this is something that y， I'm not sure you， you， you appreciate。And， and just the terminology issue。

 like why we use T S test。 So when we think about conditionals in in this control system， the。

 the general way to represent a conditional prediction。 So in the uncontrolled case。

 the condition prediction is just control distribution of future observations given past observations right。

 So interestingly， in the controlled case， there are some asymmetry here。

 is that the actions in the future and in the past are treated differently， right。

 because all the actions in the past， there are basically whatever has happened。

 They're not really that different from the observations because they're just historical path。

 therere， therere just historical facts。😊，But for the actions in the future。

 there's something different。 Like， you're saying， okay， I mean。

 this past where I've taken certain actions that shapes the current state。

 But I'm trying to reason about the future。 So I'm asking the question。

 if I were to take these actions would happen， right。

 So this is kind of like thinking about probing the system using different stimulus or different kind of you know input signals。

 So， so so in that case， like at least when you write things down formally。

 the the actions in the past is just combined with the history。

 But actually in the future are are not there。 So， it need to be separated。😊，嗯ん。Okay。

 so as a final point， this thing actually didn't get mainstream because the algorithm is a moment matching algorithm is sensitive to model mismatch。

 It doesn't really leverage the power of compute and optimization But still。

 like this is a very elegant idea that gives you some really great insights into what partial obability means and how can like reason about and so on。

 And in fact， in recent modern RL literature for P Dps。

 A lot of the P Dp works that I included in the project and reference list。

 the underlying idea and assumptions are actually closely related to this PR idea。

 So like a lot of the finite sample guarantees we see in P D P nowadays are are strongly inspired by the PSR work。

 And I don't know。 So Rich sudden gave a talk in nerves this year about like know。

 his vision of oak architecture for you know。😊，Achieving general intelligence in some way。

 So I didn't watch that talk yet。 but I've seen his similar talks in the past。 Hes a like。

 I think at least some of the components of what he's been thinking about as a general， promising。

 very general architecture， actually also take inspiration from the PR literature。

 So that's why like， you know， I feel like it's useful to to talk about this and introduce the idea。

 especially given that once you you know， unpack it is not that complicated are hard to understand。

Okay， that's it。 And， thanks everyone for going with me through the semester and really enjoyed it。

 I have your wrong。 But if anything comes up， we can contact me by email， okay。😊。

