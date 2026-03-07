# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p01 P1 马尔可夫决策过程基础 -BV1YsZHBZEyM_p1-

Okay， see if this works。try it different。嗯。How about this。Okay cool。Okay so。On Wednesday。

 we had our first lecture， which is like， you know， more general introduction。

 And there were a couple of like math equations。 And some of you were like asking questions and and trying to be serious about it。

 And I was like， you know， don't take those seriously because it's in the intro slides。

 But from now on， if you have questions about math， definitely ask。 Okay， so from now on。

 all the math are supposed to be serious。 though， you know。

 there will be parts that will be hand wavy。 And I'll explain it when I do so。😊，Okay。

 so we start with planning you know， as mentioned in R L in general。

 you have this notion of planning versus learning where planning is the computational problem。

 given a MP specification， how do you actually compute for the optimal policy among other objects of interest that you may want to know。

 Okay， so and we always start with planning because planning is the foundation for learning。

 So get to the learning part， you know， later， But first。

 we need to build a foundation to think about planning。 And as usual， start with the you know。

 finance a small stay space like those kind of like toy settings。😊，Okay， so。You know， as I mentioned。

 you know， on Wednesday， like our style in this course is like。

 we're just gonna throw like mathematical definitions at you。 And then we start to do proofs。 Okay。

 so here we go。😊，So for most part， especially in the first half of this course。

 we're gonna be considering the infinite horizonoriz discounted NP。

 So basically NP for markov decision processes have many like subtle variants well be mostly considering two variants。

 One is the infinite horizon discounted setting。 This is the one that is used most in practice。

 but well also consider the socal finite horizon variant which will be used much more in the second half of this course。

 but even in the first half like sometimes like mention that formulation and in fact。

 the first reading homework， which is which you can find on the course website。

 you don't need to submit anything， but I encourage you to go through it over the weekend and we'll talk about it next week when we meet there like we ask you to think about what happens in these like so called finite horizon setting。

 But for now we focus on the infinite horizon setting where typically NP specified by five elements。

 You have a space space。😊，The space of the possible states that you can occupy the action space A。

 So typically， for convenience will assume that you have a you know so called like a uniform action space。

 which is at every state， you are faced with the same number of the the exactly same set of options that you can choose from in those states。

 Now in practice， a lot of cases， you have state specific actions， for example。

 if you're playing video game and they say， oh， I want to you know。

 swing my eggs and cut down a tree， right， like that action makes no sense unless you have the eggs already like equipped at your hand。

 So you have like these natural situations where actions are stay specific。 But the majority if。

 if I should say probably like all of the theory which do like naturally and pretty easily extend to the setting of state specific actions。

 So for convenience， we're just going to assume that theres a uniform action space。😊，Okay， so。

 and as a comment for， you know， I think I gave enough warnings for people who may feel uncomfortable with math on Wednesday。

 So here is the opposite。 I'm gonna give a warning to people who are too comfortable with math。 Okay。

 so one combination we're gonna use for the majority of the course is that we're going gonna consider discrete and finite spaces。

 Both day space and action space。😊，Okay， now， a lot of people， once they read the sentence。

 they think that， oh， you're not actually gonna address continuous audio。 You're not gonna address。

 you know， practical settings with continuous state spaces。 That's not the case。 Okay。

 so as we will see， what happens later is that we're gonna address， so。At the beginning。

 when we talk about finite and small states。 What do we mean What do we even mean by small， by small。

 we mean that when we eventually get to the these complexity guarantees like computational complexity or sample complexity。

 we're gonna pay complexities that scales with the number of states， right， for example。

 if you if you think about the dynamic programming algorithm we talk about on Wednesday。

 you need to enumerate through all the states， right， So therefore， to finish your algorithm。

 at least you need to go through the state 1 by one。 So your computational complexity。

 at least scales linearly with number of states。Now， later。

 we're going to consider the settings where the number of states is huge and enormous。

 And in your complexity guarantees， the number of states is not allowed to appear。😡，Okay。

 so although we still assume finite spaces like this cardinality。

 the size of those spaces are not allowed to appear in your in your guarantees。 So naturally。

 those settings will actually encourage you to think about and employ and analyze algorithms that are designed for the so- calledled continuous case。

And in fact， if you think about the real continuous case that you use in practice， right。

 So you have like a setting like state spaces that where the state is represented by。

 say a real vector。 Well in your actual computer， there's nothing and that is like a real vector。

 Like everything is like a flow point， which is eventually finite， right。

 So if you think about like image as an input， Well image is just like， you know。

 however many finite pixels。 Each pixel can take a value between 0 and 2，5。

5 in each of the three channels is enormous， but eventually is finite。😊。

So assuming finiteers actually allow us to get like， circumvent a lot of the。Burden， I would say。

 like compared to actually employing a continuous setting。

 because if you start with the continuous setting， a lot of the measure theore stuff comes in。

 which are really like orthogonal to the stuff we want to investigate in this course。

 So I just essentially circumvent that， But without losing anything that is like practically relevant。

Okay， so that's kind of， you know， if if your， if your background is from con theory or like if you've taken like too many calculus classes or like analysis classes。

 this may make you uncomfortable， but this is this is how we do in this course。Okay。😊。

And then we have the transition function P or the transition dynamics。

 transition probabilities and so on， like many names。

 that map state actions to this symbol is what we is a our notation for probability simplex。 Okay。

 so for any finite set like capital delta of the set is the set of all possible probability distributions over the set。

 right， So if you have a finite set， as you can imagine。

 you can represent any distribution as just the vector over the set。

 whose entries are always not negative and sum up to one。

 right So think about this delta of S just being the space of all possible such vectors。😊，Okay。

 so what this says is like not nothing too My just says that the transition function P gives you the next day distribution whenever you ask。

 what's the next day distribution for is for any particular state action pair。Okay。And。

And in in addition， we have the reward function R that gives you a real number for any state action pair。

 So this is the reward you get。Okay， so for now， a lot of cases for simplicity。

 we're gonna assume deterministic reward functions。 And for， and in reality。

 you may encounter stochastic reward functions， reward functions that doesn't depend on state action pair。

 but maybe sometimes the current state， sometimes the next state， sometimes all of it。

 and and so on and so forth。 And we' will see that for the majority of the algorithms and settings。

 analysis we do。 like these details basically don't matter。

 Like it's eventually you get the same thing。 So we will have like brief comment on that。

 whenever we need it。 But most part， we're gonna stuck with this combination。😊，Okay。

 and then we have a discount factor that is a number that is generally between 0 and 1。

 And if you remember that's to make sure that when you sum up all the rewards from time step 1 to infinity。

 you get something finite because you you discount them with a geometric sequence。Okay。

 so once you have all of these， in fact， all you need is the first four。

 you don't even need the last one。 Then you can actually roll out a random trajectory in this N P as we call it。

 right， So how do you specify how do you roll out trajectory。 Well， first。

 you need to tell me where do you start。 So this is like externally given。 ands say。

 let's say we start from some particular start S1 Okay then agent makes decision it takes some action a1。

 it receive reward R1， So here if if we're actually being serious about deterministic reward function。

 this should be the equal， But you know， more generally， if you have stochastic reward。

 you just sample generate a stochastic reward R1。 then you transition to the next date S2。

 So so this is a sample from right， So given any S1 given any S A。😊。

P output a a distribution of states。 So P of S 1 A1 should be treated as a distribution of estate。

 right， And whenever you have a distribution， you can just sample from it。So when you sample from it。

 you actually get a realization which is like a state。😡，So sometimes to make it more clear。

 we also write it this way， which is a dot。😡，S 1 A1， right。

 So the dot here is just making an emphasis that this thing is a distribution of states。

 And when you sample from it， you get a state。Okay。And now you're in S2。

 then you can the agent is agents turn to take action A2。 and then you get rewarder 2。

 And then again， you ask the transition probabilities。 like， I mean。

 S2 A2 what's the next a distribution， You get distribution。

 You sample state S3 from it and so on so forth。 And this process just goes on indefinitely。

 So you get an infinitely long trajectory。Okay， any questions so far。OK。So now so how do we you know。

 we have these trajectories。 And if you remember， like for most part of our real。

 we care about getting a good policy。 So how good is good， right。

 how do we measure goodness of policies。 What we care about what we call a return or value or utility。

 there are many names or expected return So， so here this is informal。

 I would say this is this expectation is informal and lacks a few elements which will specify later。

 But generally speaking， what you want to do is that you look at the reward。

 the random rewards you get a long trajectory， right， and you sum them up with this factor。

 So you have this gamma to the power of t-1 and be careful about the letters。

 gamma versus R whenever the it's unclear。 you can always ask， okay。😊，So for the first time。

 step T equals one， you don't have any discounting because gamma to the power 0 is just one。

 And then you have gamma， gamma square， gammas Q and on so forth。 Okay， when you sum them up。

That's still random variableable because your reward can be random。 Your and the reward。

 even if a reward is not random， reward depend on state。

 the state themselves can be random due to the random state transitions。

 And sometimes the way you take actions can also be random。 So in general。

 this is a big random variable。So we take expectation of that to turn that into a single， you know。

 well defined scalar and say， this is the thing we want to optimize。

 This is often called the expected return。Okay， or like expect a discounted return for the specific setting。

Okay， so now， as I mentioned， this notation is actually bad and poorly defined because in order to take expectation。

 you need things inside the expectation to have a well defined distribution， right？

 But if I just give you MP and says， what's the distribution of the sum of rewards。

 you can't tell me it's undefined。Because if you look at the like the last slide。Ohoops。

This trajectory。😊，The distribution of this trajectory actually。

 so a distribution of a certain object can be equivalently described by the generative process that generates the generates the。

 the object， right， So here I'm actually describing the。

 this distribution and this random trajectory distribution using a generative process。

But as you can see， like there are two things here that are， you know unspecified。 First。

 I said this starts from some state as one。 which state you need to tell me。Right。

 and the other thing is that whenever you take an agent takes an action， it can always choose from。

 you know， some like one of the， any of the actions。 So this is also unspecified。 Also， a 2， a 3。

 A 4。Right， so， so therefore， you don't have a well defined distribution of trajectories unless you fix all these unspecified elements。

O。So therefore， we're going to do that， right， So the value， this value depends on where you start。

 the initial state， as well as how you act， how you choose actions。So， yeah， we'll。

 we'll do the more formal notation later on。 But for now。

 one thing we're gonna assume is that we're typically gonna gonna assume that the rewards are bounded and often non negative。

 So it has range0 to R max。Okay， so here is something that is a little， you know。

 a little subtle is that if you look at many practical scenarios。

 you may actually want to introduce negative rewards。

 which are often naturally interpreted as some kind of penalty。 Okay， but here I'm not allowing that。

 But this is not without loss of generality。 because whenever you have as long as your reward are bounded。

 whenever you have negative rewards。 You can always like redeffinine a reward function to shift them to the positive side。

 Actually， this is， you know， one of the you know， homework questions in the first reading homework that you'll be looking at。

 We'll talk about it later on。😊，Okay， so once we assume bounding this， there's a question。

 can we actually derive a range for the infinite sum of discounted rewards， And， in fact。

 I can get rid of the expectation and claim that actually this even this random variable。

 the just that the expected sum of discounted rewards is already bounded。Okay。

 what's the lower bound， That should be obvious。0， right。

 because all the R's are 0 and the discount factors are also 0。 So， you know， clearly。

 it's not going to be negative and0 is attainable because if you just assign all the rewards to be 0。

 you get a 0。Okay， so what's the upper bound？😡，Right， because this is。

 So because everything is now negative， right？ So how to assign the reward R T to make this。

 to maximize this term。All of them should be R max， right， So therefore。

 all you need to calculate is just the discounted sum of rewards when all the rewards are R max。

 because this is R max， you can just take it out of the sum。

 right Then you just need to calculate this the sum of a geometric sequence。😡。

And for geometric sequence with the ratio less than  one， and you start with one。

 there is a formula that tells you that the infinite sum is one over the1 minus the ratio。😡，Right。

 so here the ratio is gamma， So you get。One never ones Gaa。Okay， so this term。

 R max over woman iskama would here again and again， like in our analysis。

 because this is the range of the value， the range of the return。And this particular term。

 one overness gamma is also have significance。 It's often called the effective horizon。

 because this kind of plays the role of， you know， how many steps do you look ahead in finite horizon settings。

Right， so， you know， think about this way， Right， So suppose my， So heres a。a crude analogy。

 suppose my reward， my definition of return looks like this。

 It's just the plain sum of rewards without discounting。

 and reward each reward is still between 0 and Rax。Okay。And I， but， but I only sum。

 some sum things up over a final horizon of capital H steps。

So then what's the boness of this variable？😡，What's the range。0， so lower bound is clearly0。

 What's the upper bound。HR max， right， because each step you can get R max， you have H step。

 So this HR R max。 So if you， if you do this comparison， you get0。HR max， right， now。

 if you compare these two， as you can imagine， as you can see。

 like H placed like one over woman gamma placed the role of H over there。Okay。Okay， so。

 so now let's let's answer this question here， Right， So we want to actually formalize the， the。

 the notation over there to make sure that is a well defined distribution so that we can comfortably add an expectation around it。

 And for that， we need to specify two things。 The starting state that's easy to specify。

 just say you start from somewhere。 But what's more tricky is how do you specify how action。

 how agents take actions。😊，Okay， so for the most part。

 we're gonna consider or like a simple way of describing the the agent's decision making strategy is to consider a deterministic policy。

 Actually， this is a determine like if I actually fully expand。

 this is a deterministic mark of stationary policy。 and map stay to actions right。

 So we've seen that in the stochastic shortest past example that you take you choose one of the actions based on the current state。

 So your decision making strategy can be described by such a mapping。 the map stays to actions。

 If you imagine this like tableular representation， if the say space is finite。

 you can express your policy as a table where the first the first column is all possible states and the second column is like each state。

 which action do you want to choose Okay， and that table is a deterministic mark of policy。😊，Okay。

 and when you plug this into that generative process for the for the trajectory。

 what it says is that at any state， at any time step T， you're facing state S， Now。

 in the previous slide I said， the agent will choose A somehow。

 right But now if you say the agent is gonna to choose actions according to policy pi。

 Well that means that what what the agent does is that it will plug S into pi， right。

 and pi maps the state to an action So get an action out。😡，And they just take that action。

 So A equals pi of Sd。Okay。Now， this is the simplest form of policy。 Now。

 sometimes we are also going to consider more general form of policies。

 which are random or stochastic policies。 But still， like in this case。

 it's Markov and and and stationary。 In that case， the policy has the form pi that map states to a distribution of actions。

 So we're using this simplex notation again。So in this case， given NST。

Given any S pi pi of S tells you a distribution interactions。

 and the way you actually choose the action A is to sample from that distribution。😡，Okay。Now。

 I have to mention that this is not even the most general form of decision making strategy because in general。

 you can so so this way of doing things is called stationary。

 because it only look at what the state is it doesn't actually care about what the current time step is。

 So if you step into a state early on， and then later come back to the state， you know。

 in a later time step， the distribution of reactions you have， it is still exactly the same。

 It's not allowed to change right But if you do allow it to change。

 which is to say the will additionally take timesstep T as additional variable can depend on that's called a nonstationary policy。

 or you can even have a fully history dependent policy that look at looks like all the all the state actions you've visited so far and make a decision based on that。

Okay， but for at the beginning of the course， we won't need those general form of policies。

 So we're mostly going to restrict ourselves to these like relatively simple form of policies。Okay。

 so。Once you have these， right， So now we talk about how to formalize where you start and formalize the how you specify in Asian behavior。

 now we can comfortably design specify the distribution and then put a proper expectation out of it。

 right So here that says so here with these two additional elements that I'm starting from particular state S。

 And I'm gonna take all actions according to policy pi。

 it I have a well defined distribution for the entire you state action reward state action reward。

 the entire sequence so that I can put expectation over it。 Okay。

 and because of the dependence when I。Define a notation for the symbol。

 I need to reflect the dependence on the initial state。Right， as well as。你诶。Oops。The initial state。

 as well as the policy， right， And theyre reflected on the。嗯。On the left hand side。

 right that you have pi over here， which is the superscript。 and as over here。

 which is the argument to the function。Okay， now I have to say， like。

 even this notation is not really mathematically。Like个。Like super rigorous。

 according to the normal mathematical conventions， because you use the conditional operator here。

 is as if you have like distribution over these and you're conditioning on particular realization。

 but really what's happening is that which you should think about is that the initial state and the policy pi they are they are elements that fully specify distribution。

 right， So sometimes like if you have like a parameterized the distribution。

 you have some free parameters。 once you define those parameters。

 you have a well defined distribution like know think about like exponential family distribution that things like that。

 So these actually you know know it's more like is playing those rows。

 So sometimes to better reflect that we may use things like this， subscript pi。

 which means that pi is actually you're not actually conditioning on pi because pi is not a random variable like pi is part of what specify the distribution。

 So we put that as the superscript sub that all happens same for initial state。

 but it's just like convention that some。😊，Now this notation gets settled down。

 So we're going use that， You know， that's that's okay。Another convention。

 which is also gonna be super confusing。 And I hope you'll get used to it gradually， is that。

 you know， if you， if you write on， if you look at the notation system of a standard probability course。

 right， you would have things like capital letters correspond to random variables and lowercase letters correspond to the realizations。

😊，Right， or like constant symbols， right， So you have things like。

Probability of x equals x is something， right， So here X is a random variable。

 and X is a particular element。 And you see what's the probability that this random variable happens to like the realization happens to be that particular constant。

So here， as you can see， the kind of R navigation system I'm using don't really have that much capital letters when I define those variables。

 So the convention is， this is the way you read it。 is that。

All the states are actions that has a time step sub。Are most， in most cases， Okay。

 there are exceptions。 In most cases， they are treated as random variables。

And states and actions without a time step sub are treated as as like concrete realizations。Okay。

They're， of course， like。Like places where that actually become inconvenient So where we're going to do something else。

 but， but that's the general rule。Okay， so therefore， if you look at this conditional over here。

 it actually fits the form of condition on a particular random variable takes on a particular value。

😊，Okay， any questions so far。Okay， and by the way， this V pi is a very important object in R L。

 It's called value function， or sometimes a state value function。

It tells you they expect a return when you follow a particular policy starting from a particular state S。

😡，Okay， so now the。Now， in the next slide， we're going to actually look at this function and ask。

 you know， how do you actually compute it。Okay， or what what important， what properties does satisfy。

 So this leads us to this one of the foundational results in in R。

 and it's called the Bel my equation。 Okay， so this is a huge like wall of the equations。

 which may be a little bit scary。 But what I'm gonna ask you to do is that ignore the evation in the middle for a bit and just look at what the equation looks like。

 And then I walk through the des。 Okay， so what does the equation looks like。

 So equation says like V P of S equals what。 so skip over this and look at over here。😊，首么看第一。

Look at over here。 So what it says is that， well， imagine what's happening， right。

 you're in state S and you're going to take actions according to policy pi and you're going to collect all the rewards along the way and calculate the expectation。

Well， after state S， you're going to take action， What's the action you're going to take？😡。

What's the immediate action you're going to take？😡，Pi of S， right。

 Because that's exactly what it means for taking actions， according to policy pi。

 So you see pi of S over here。 right， So you're in state S。 Now。

 pi tells you that you should take action pi of S。 Now you collect your first immediate reward。

 which is just R of S pi of S。Correct。Okay， that accounts for the first reward。

 And then what happens。You're in a stay， you take an action， you get a reward， what happens next。😡。

Transition， right， random transition。 You're going transition to some next state。 Okay。

 so this is what happens， right。😡，So。This is a transition part， right。

 So this is actually essentially taking an expectation with respect to the transition probabilities。

 right， because given state S， you're taking action A equals pi of S。

 Then P of this tells you what's the next state distribution。Right， for each possible S prime。

 this is the probability that you actually land in that particular state S prime。Now。

 once you're in S prime， what do you do， Well you just repeat the process， right。

 You're gonna take action according to pi， get a reward and so on so forth。 But from there own words。

 that's exactly essentially the definition of v pi。 Okay， so therefore， you get v pi of S prime。

 So this is the this is the next state you're you're getting at。 Okay， so then you get this equation。

 V pi of S equals immediate reward plus discount factor times times the expectation of the value function evaluate at the next state with respect to the transition probabilities。

Okay， so here is a maybe another way that I like to write it。

 which is v pi of s equals R of s pi of s。 This part is the same plus gamma expectation as prime sampled from P of S pi of S。

V pi S prime。Okay， so。This line is just a different way of writing that line that， you know， you。

 you're just rewriting that line by expanding the expectation as a weight is sum， right。

 Or alternatively， there's another vectorized notation， which we'll talk about later。

 But these are just like， you know， different ways to write on the same equation。Okay。

 so therefore Bel equation is this important， recursive， like sort of a， you know。

 if you use modern day like fancy machine learning terminologies。

 this is kind of like a self consistent self consistency relationship， right。

 that my prediction for future return today。😊，Is equal to the immediate reward I get today。

 Plus the future reward I'm going predict for tomorrow。Right so so this is kind of like a。

 know temporal consistency。And also， as we will see。

 this relationship actually allows for a simple close form， you know。

 competition method for actually calculating V pie。Okay， so now let's go through the variation， so。嗯。

You know the。Because I'm gonna。 So this is， this is called a Bel equation for policy valuation。

 One thing to realize and emphasize before we do the derivations is that。You know。

 oftentimes you think of our L as computing for the optimal policy。

 And this equation has nothing to do with that。Okay， so like in previous semesters， there。

 there are often students who pointed to like， you know， why is this optimal so and so forth。

 This has nothing to do with optimality。 This is this is asking the question。

 you give me a policy pie， which is a decision making strategy。

 which is a certain behavior of the Asian。 I just tell you how good it is。

If you give me a good policy， you will see like a high value of V pie。 If you give me a bad policy。

 you will see a low value of V pie。And as you can imagine。

 this can form the basis for later optimization because if you're able to compute V Pi for different policies。

 you may be able to actually choose the one that has the highest V。😊，Okay， roughly speaking。

 not exactly what we're going to do， but just as a， you know， anticipation of why this can be useful。

Okay， so let's go through the and there will be another equation that's actually talking about directly talking about a policy my like my completely off for policy。

 But for laziness， I'm not gonna do the proof there。

 and will only give you intuitions because that proof is much more involved。

 And I don't think you get much out of it。 Then as a price I pay I want to go through the proofs。

 go to go through this proof like more carefully。Okay， so let's do it。

 So the first line is what is just the definition of。The like value function。Right。

V pi of S is you start with as take all actionss according into pi discount of sum of reward from times step 1 to all the way to infinity。

 correct。Okay， so what does the second term what does the second thing do。

What what it does is basically just， you have an infinite sum of rewards。

 I just take out the first term and then leave the rest。😡，Okay， so as you can see。

 So here the summation index starts from 2 T equals 2 instead of t equal 1 because I've taken the R1 out。

Okay， good。So now again， ask， what's the expectation of bar1？😡，Right， in， in fact。

 R1 in our simplified assumption is a deterministic quantity， right， Because if I know S1 is S。

 if I know you take actions according to pi。You would know that this is exactly R1。

 right R of s pi of s。😡，And by the way， this is exactly why when you have stochastic reward or whatever。

 it doesn't matter because even if R1 is stochastic。

 you just define the expectation here to be an equivalent deterministic reward and put it over here。

😡，So that's why， you know， at least for planning purposes。

 if I just assume that we have deteristic reward， everything is the same because for other cases。

 you can always reduce them to this case。Okay， so you have that。And then， you have。This。

Particular term。 okay， you want to handle that。Okay。So now the way I'm going to do it， which is。

 I guess it can be useful to write out an intermediate step。😊，So this is equal to。

 or I'm just talking about this particular term is equal to the expectation。😊。

Subation t equals 2 to infinity。 I'm not gonna write out the discounted sum of rewards over here。

 condition now。 So previously it it's only condition on S1 equals S。Equals S。

 Now I'm also additionally condition on S2。😡，Okay， and then I take another expectation outside。Okay。

 so here they， they asked to， I'm not actually not specifying its realization。 So as to remember。

 like， it's treated as a random variable。Okay， so what I'm doing here。😡。

Why do you see two expectations？😡，四楼的。Tower property or law of total expectation。Right。

 so what I'm doing is I additionally condition on additional variable， right， So before I do that。

 right， the expectation of the second term is just a well defined number。Okay， so it's。

 it's a constant。 It's a deterministic quantity。 There's nothing random about it because all the randomness is marginalized out by the expectation operator。

Right， however， when I introduce the additional conditional variable by condition on S 2。

 now it suddenly becomes a random variable because it's a function of S 2， because S2 is random。

 So the entire thing inside the outer expectation， which is。This part is some function of S2。😡。

Right so it's a random variable。 It has the random randomness at mass2。

And for it to be equal to the left hand side。😡，You need to take another expectation to expectation to marginalize out the randomness of F2。

 Right， So this is a lot of expect， a lot of total expectation or the tower property。O。So。Now。

 what happens is that now what you see is that now this is some F of S 2。

 Then you take expectation of that。 Well outside， you still need to condition now S 1 equals S。

 right？ So actually， yeah， so the。The condition， the condition still needs to be capped。

 So I guess I'll put pi over here。 So the so the conditioning S1 given S needs to appear both in the in the inner expectation as well as the outer expectation。

Okay， so then the second， then the next line， what it does is that it's just calculating out that outer expectation。

 right， So the outer expectation， you know， you have something that is a function of S2。

 and like the way I can calculate this is to enumerate all possible value of S2。

 let's say the enumeration variable is S prime。Okay， and given S prime and I can ask。

 what's the probability of seeing S 2 equals S prime with respect to the outer expectation。😡。

So it's asking what's the probability of seeing s prime， given that in S1， I'm mean state s。

 and I'm going to take action according to pi。😡，Right， what's the probability， Well。

 that's exactly given by the。transransition， probably方式。Right， given that in step 1， I may state S。

 I'm going take action。According to Pi。What's the probability that S2 equals S prime？ Well。

 this is the probability。Okay。So this line is just calculating the outer expectation。

Any questions so far？O。So now what happens。 So inside over here， I also did a little trick。

 which is to， you know， if you look at the infinite sum over there， we start with t equals 2。

 So the very first discounting is gamma to the2-1。 You have a factor of gamma， right， So it's gamma。

 gamma square， gamma cube and so on so forth。 because we've left out the very first reward。

 So all the remaining terms， they share the same discount factor。

 like they share the same factor of gamma。😊，So I'm extracting that out。😡，So here， instead of t -1。

 I have t -2。O。And here's the most， like， in some sense。

 the most important step in this proof or how we actually use the mark of property。 is from here。

 as you can see， what I did is I I just cross out this conditioning。 I cross out S1 equals S。😊。

And why can I do that， Well， that's because if you look at the sum of rewards over here。

 it starts the first reward you look at is reward R2。😡，Okay， it's asking。

 what's the expected sum of reward from R 2 to R 3， R 4 and so on of worth。

And what I'm conditioning on， I'm conditioning on that I know in time step1， I'm mean state S。

 in time step 2， I mean S prime。😡，And then like， you know， things evolve on。

But because we're in a Mark of state process， we have this mark of property that all the future evolution。

 once you condition on the current state， is independent of the history。Right。

Because you take action and you say， oh， what's the next distribution。

 Well you plugging S 2 and pi of S 2 again you ask and you that tells you。

 what's the probability of S 3， right， And then ask you， what's the probability of S 4。

 Well you plug S 3 into pi， You get a 3， And then you ask the transition probability。

 What's the distribution of S 4 and so on so forth。So once you know what S2 is。

 you no longer need the knowledge of S1。😡，Okay， so this way you can use the mark of property to basically get rid of S1 equals S。

Okay， that leaves you this expression over here。😡，Okay， so then the further next line。😡。

What we do is that we take the gamma， we take that out。Okay， and then we。

 we rearrange the or essentially redefine the time index， right， So here we're starting from time。

 time equals 2。The first discount factor is just one。Then R 2。

 given that S 2 is in some S prime and so on so forth。

But you see like everything here starts with two。😡。

How about we just rename it and call it time step one？😡，Right， it's the same thing。 So we。

 we actually call this time step1。 Then you have gamma T-1 like R T is still like， you know。

 you start from R 1。 Then S 2 equals S prime becomes S 1 equals S prime。Okay。

 why do we do that renaming。Why do we rename it that way？Exactly， we want to get a recursion， right？

😡，If you look at this box over here， well it looks exactly like the box we start with。😡。

And the only difference is that we're just considering a different starting state as prime。

So there the starting state as S here， the starting state as S prime。Okay， so therefore。

 given that we've defined the value function to be that for any possible starting state。

 well this has to be equal to v pi of s prime just by definition。😡，Okay。So then， you。

 you end up with this property。So one thing that on the mention is that this nice， clean expression。

 which you won't get in most， in most of the other variants of market decision processes。

 are actually very specific to the geometric discounting。Right。

 so the geometrically discounting actually has this sort of a self similarity property that。Now。

 basically。Let's say you have this jump， like exponentially decaying curve。

Right so this is like a gamma t -1， this is T。So what we're doing is that we're actually separating out the first rewardwork。

 So like were we're separatepar out the t equals one and then look at the remaining curve for like T equals t greater than or equals to 2。

Okay， but this exponential curve has the property that if you shift things the to the beginning and then amplify it。

 it looks exactly like。The original curve you start with。😡。

And this is actually reflected in these steps。😡，Right， so at the beginning， you have one gamma。

 you know， you have a。You have one gamma gamma square， gamma cube， gamma fourth and so on so forth。

 right？ And then we say， okay， we're gonna to consider the first reward and all the remaining separately。

 right， But all the remaining terms they share the one factor of gamma。 We extract out that gamma。

 You get one gamma gamma square gamma Q， do da do。 Well。

 this part is just exactly similar to the first sequence that we start with。

And this is specific in the sense that there are many other ways to define discounting， right？

 So as long as youre， you know， you， you the， the sum of these factors at each time step sum up to a finite value。

 you can define discounting in that way。But if you define it with a generally like arbitrary。

 like the hang curve， it may not have this like self similarity structure。And in that case。

 the value function you defined may need to be like time dependent。 That is， you know， you know。

 my value function， you know， we to， to tell how many。

What's the value of the state from time step 1 versus starting from time step 5， Actually。

 the answer may be different。Okay。Okay， any question about the Bway equation over here？I dids。

I wouldn't say it's harder well。There are two different problems。 So in some sense。

 like it's not really exactly comparable。What we'll see is that。How do I put it？So I think okay。

 I think what you can say is that representation wise。

 it it takes more bit to represent the value function in， say， final， right， because here。

 the value function is only a function of state Once you specify the policy。 So for each state。

 you have a number。So the number of like real values you need to store is like the number of states。

 But for a finite horizon problem。 for each time step。

 you have a different mapping from states to ashes。 So to specify the value function。

 you need number states by horizon。 that many like real values to actually represent a value function。

 But in terms of the actual computational complexity First。

 I would say they're not really comparable。 And second， I would say they are actually。

 in some sense similar because later we'll talk about value duration。 Well。

 it turns out that value duration in infinite horizon discounted setting has an exact interpretation of like actually calculating the finite horizon approximation of the problem。

 So in in that as they're like the same thing。😊，Okay。

 so it it's not that one is more difficult than the other。Right， you don't。 You don't。 You don't。

 You don't explicitly use that in the in in your algorithm， but you do benefit like。Right。Right。

 and and I don't think you， yeah， yeah， you're right。 We're not really leveraging that property。开始。

Here you say a little bit louder。Okay， so let me actually let me write it more properly。

See I think that that's also a very key step in the。So what we have is v pi of S equals expectation。

Alright pi over here。 So R 1， we separate out T equals 2 Infinity gamma t -1。 R T。 did I get it。

 right， yes。Given S1 equals S right， So what we did。 So So this is where you start。Okay。

 and then we use a law of total expectation。 We get another E pie over here。

 and then we condition on。S 2， but don't specify realization。 And then given S 1 equals S。 Okay， you。

 you need to copy S 1 equals S here because you start with like a conditional expectation。

 So that condition needs to be carry around like everywhere。

 like because like you normally don't see that in the definition of law of expectation。

 because you often start with an unconditional expectation。 Then you， you don't， you don't have this。

 But whatever is in the original definition。 It needs to be repeated like everywhere。Okay。Okay。

 so now that I've written it。 Okay， so now I can say， this is equal to， well。

 this is just some function of F S 2。 So F is like just a placeholder to say that this is a function of S 2。

 right， So one way to write it is to say I can write， this is just equal of pi。 F S2。

 given S 1 equals S。Right。Then to calculate this thing。

 if I know what's the conditional distribution of S2， given S1 equals S。

 I can calculate this expectation。😡，Well， you just ask。

 what is the condition distribution of S2 given S1， Whats tell it's it's being told you by the。The。

 the transition probabilities， right， So this is S prime P of S prime given。Or okay。

 I can write it even more like formally， say this is P pi。

So under the distribution of trajectory generated by policy pi， when you start from S1 equals S。

 it always has a。Probability， it always tells you a particular distribution of S 2。

 So let's just use that。And F S prime， right， so this is。

This is like a strict rewriting of the earlier line。😡，Right。And then you just need to ask yourself。

 what is this， Well， this is given by the transition probabilities。This is P of S prime， given S。

Pi of S， just by the generative process of how， how the trajectory is generated。Okay。

So is there still a question or this is good。Who who ask the questionO good good。开始。

Was like the only reason that we。医疗的。Kin kind of a factor。It yeah。

 this kind factor is purely for convenience。 It's purely to enable this what we call a stationary value function。

 right， So it like， as you can imagine， like， you can imagine a trivial case when you have a finite horizon objective where things is definitely not stationary。

 right， So suppose you have a finite horizon problem。😊。

Every single state gives you every single state， every single action gives you the same reward of one。

😡，Okay， so， but， but your， but your definition of return is like summation T equals 1 to H R sub。

Well， it says like you you， you start from the start of the trajectory。

 then you take action and run to state， take action and run to state。

 you evolve for H sets and then cut。Okay， then your return is just like all of this。The。

 the sum of these reward wars。And I ask you， what's the value function when you find yourself somewhere in the middle of the trajectory。

 you're in particular state S， what do you think is the sum of the reward in the future。

Can you answer that question？You can answer that question because you need to ask me。

 how many remaining steps do I have left。😡，Right， if I'm at the very beginning of the process。

 I just started while there are H steps left。 So the total reward is just H。

 because I assume each reward is one。But if I'm already at the very end of the process。

 there's only one last step left， then my total reward in the future is just one。😡，So naturally。

 as you can imagine， if you have a finite horizon objective。

 the value function becomes a stay becomes time dependent。Or sometimes as we recall it like nont。

 nont is like often get confused with other concepts。

 So maybe even more accurate term is called time， time in homogeneous that then， you know。

 is it different from time to time。But by using the geometric discounting。

 what's the nice thing is that you always have infinite time number of time steps ahead of you unlike like a finite horizon。

 like the number of steps in front of you keeps shrinking。

 like you have a countdown as you move forward。 So here。

 because we have infinite number of steps ahead of time。 however。

 number of steps you you progress forward， they're always infinite infinitely more ahead of time。

 Furthermore， due to this self similarity structure of the geometric decay。

 like whatever lies in front of you， they look similar to you know， a few steps ago。

 like the scenery in front of you always look the same。Okay。

 so that like the main reason is this mathematical of convenience。 Now。

 one thing is that in a lot of the cases with these different settings of finite horizon in and infinite horizon。

 And I think like either in the reading homework or in the first homework， probably reading homework。

 there's， there's some， some question I ask you to do that is that you can often approximate one with another。

😊，Okay， so if you have an infinite horizon discounted setting。

 you can often approximate with finite horizon by looking ahead far enough and then do a truncation over there。

 and then absorb the discount factor into the definition of reward。

 and you make the reward function like time time dependent， right， then you。

 you convert it to a finite horizon problem with some small approximation error。

 And similarly for finite horizon。 there's also way， let's say there。

 there's so- calledled adding absorbing state。 And then you expand your state space to include time stamp as a variable。

 And then just use a gamma that is extremely close to one。 Then you。

 you can always go back and forth with each other。So， so， so， but given that they are all。

 in some sense roughly similar。Well， we， we use one that is， you know， give you clean results。Now。

 this this factor does have some practical interpretations， especially economy。 So， for example。

 like， if you assume that your economy has a constant inflation rate。And， but。

 but your model doesn't like when you talk about how you sell things， you buy things。

 you incur cost you get， you get money， you earn money and so on so forth。

 You don't want to explicitly account for that in your transition dynamics。

 you can put that outside as like the discount factor。 So in some of the rare cases。

 like discount factor does have a practical interpretation。 But in like。In the R community， it it。

 it almost never has like a real reason。 It's just for convenience。Okay， any other question？Okay。

 cool， so。So， here we are。The by equation for policy evaluation。 Now， in the very last line。

 I rewrite in a further just a form that is will be convenient for in some of the cases。

 So these different variations of forms are what we're gonna use like interchangeably from now onwards。

 But here， what we do is that we're treating V pi So V pi parent do is just emphasizing that we're actually treating this as is a function and sometimes because our state space is finite。

 we're gonna interchangeably like treat a function also as a real vector。😊，Right if you remember。

 I said this before， like， oh， we have a probably distribution over a finite space。

 Well we can always treat that also as a vector that has non negative entries some up to one and also so forth。

 right， whenever you have a function of a finite space， we can always treat that as a vector。

 Like what's the order of coordinates， It doesn't matter。 as long as you know。

 you systematically define a particular like you know order and always stick to that right。

 So once you do that， you can actually rewrite expectation because this is really just taking expectation of value function with respect to the transition probabilities right。

 So any expectation is actually can be written as the dot product between the distribution as a vector and the function you're taking expectation of as another vector。

😊，Right，Because when you take do product， what you do is that you enumerate over all the coordinates。

 multiply the entries and sum things up， which is exactly what you do in expectation。And here。

 this is also why like the particular order you use over the state space doesn't matter because as long as like these two order is consistent。

 they always give you the same answer。Okay。So。So here， once you have this。

 we get something like really nice。So the other thing to notice is that。

This is an equation for a particular starting state S。Okay。

And if we consider all possible starting state， each unique starting state will give us a different equation。

😡，RightBecause you actually need that because you can't compute V pi S just using this single equation because you want to know the left hand side V pi for a particular S on the right hand side。

 you have V pi again。😡，Who tells you this， right？ You don't know the answer to the V of S prime on the right hand side。

However， when you。You know gather all these equations。

 What you have is that you will have S equations in total and how many unknowns do you have。😡。

How many unknown do you have？We're solving for V。😡，S， right， because we want to know V pi。 And again。

 whenever you have a finite function， think of it as a vector， right， And what's the dimensionality。

 the dimensionality is the number of states。 So you have S equations and as unknowns。

 So that actually is like， you know， it give you some hope that if the equation is like， you know。

 well condition as also so forth， maybe this uniquely defines the the the solution。😊，Right， so。

 and let me emphasize this， this。 So this equation。For now。

 is a consequence of the definition of value function。 right， We started with this。

So this is a consequence， which may said that like the value function always satisfies this kind of recursive relationship。

But for now， we have not shown uniqueness。 That is， for now。

 there could be other solutions to this equation That is not the value function。Okay。

 because we have not shown uniqueness。Right， so that is like if you。

 if you treat this as some a general unknown and say and replace this also with F of S。

 F of S prime and you say。What is， what is F that can possibly satisfy this equation。

 We know that V pie is a solution。But there could be other possible solutions too。

 given what we know so far。What I'm going to show you in the next slide is that this is not going to be the case。

 Vp will be the only solution to this set of equations。

What that means is that at least in the finite state and finite action case。

 the bema equation becomes an alternative definition to value function， right， because both。

 you know， uniquely specify a particular function。Okay， so that's why， you know。

 in sometimes in papers， we say how we define value functions。

 We actually define it directly using Bel equation。 We don't talk about the discounted sum of return。

 that's the reason。Okay， so how do we get uniqueness， Well， recall that this is the very last line。

 It's like a virtualized version of Bama equation for a single S， right， And really。

 what we want to consider is that we want to consider as different equations like altogether as a like a system of equations。

😊，So the reason that we write it in this vectorized form is that we actually want to further making it even more vectorized in in fact。

 turning into a matrix form。😡，So what I'm going to do is that。 So imagine that you have a。

 you have a。😊，Right， so you have the。Right， so you have this。

 But really like you should think of that has as some S prime and so on so forth。

 So you enumerate all the password states。 and each state will give you equation。

 you're thinking about like this whole rectangle of like equations。😊，Right， now。

 instead of like S different equations， I'm gonna write it as a single matrix equation。 right。

 So what'm gonna to do is that I'm gonna treat V pi as the vector as a asal vector， which is just。

 you know， the collection of the left hand side as a column vector。😊，Okay， and again。

 the order is any systematic order of states that you decide as long as it's consistently used across in all places。

😡，Similarly， I'm going to define an R pi vector， which is R of S pi of S for any state right。

 for any state， R of S pi of S gives you a number， right。

 Just fill that number for every single state and collect them while this correspond to this column。

Right。So then as you can see， like our all these S different scalar equations is already being transformed into a form of v pi as a vector equals R pi as a vector plus something。

Okay， so with the something， well you， we still need to handle this particular term。 But here。

 notice that it's a dot product。With two components。😡。

But only one of them depends on the state S on that show that shows up on the left hand side。

 Which part depends on S， which part doesn't。The transition probably is changes which each S， right。

 But the right hand side， but the right part doesn't。 It's V pi。 I mean。

 here is like maybe a little twisty because V pi is a value function。 It's a function of state。

 But here， when we treat that as an entire function， this function itself。

Has nothing to do with the state。 right， Think of it as a vector。 The vector itself is a。

 here is is is a constant vector over here。 Right， So， for example， here。

 when you have S prime of v of S prime， you also dotted with v pi dot and this v pi dot and this v pi dot。

 They are exactly the same vector。O。So now what you do， what you do is that on the right hand side。

 you have this。Each row has a different vector dot with the same vector。😡，Right。

 so what you can do is that you can actually stack these。Vectctors as a matrix， right， So basically。

 what happens that when you have like by convention。

 we typically think of all vectors as column vectors， right， But when you're doing dot product。

 like when you're doing U V dot product， This is really U transpose V， right。

 So you're actually using a row vector to multiply a column vector。So here the value function。

 V pi is treated as a value factor， value treated as a column vector。

 but the transition probabilities is essentially being transposed due to the dark product。

And each equation， you have a different row vector， so what you do is that you stack them up。😡，Right。

 so you have each row has a different row vector when you step when you stack them up。

 you get a matrix。So the matrix is this。😊，Which is literally each row is the row vector。

 which is the transition probability transpose into a row vector。 you stack all of them up。😡，Okay。

And by the way， what is this matrix， Well， this matrix is actually， if you have。

 if you have seen like Markov chains， you know that MP are essentially an extension of Mark of chains。

 It's not exactly a Mark of chains。 But once you fix the policy。

You actually have a fixed transition rule between states， right， Because once I'm in state S。

 now the only degree of freedom， which is what action you need to take。

 is already specified the policy。 So the next state distribution is now fixed with that distribution is this distribution。

 right， given any S， I would tell you a next state distribution。 So once youve fixed the policy。

 the mark curve chain the NP actually collapses to Mark curve chain and the transition matrix of the micro curve chain is this matrix。

Okay。So one thing， again， this is yet another place where the R O convention differs from standard math is that if you study。

 if you take course in mark of chains， typically the way you write down the matrix is that the future state is on the rows and the current state is on the columns。

 But here where the other where the other way around。 So we have the。😊。

Kmera stage on the rows in the future state on the columns。 So if you're used to the， you know， the。

 the markov chain notation， like we're up to a transpose。

 And there's actually a good reason for that because in Markov chains。

 typically you use transition matrix to describe the evolution of the distribution。Right。

 and in order to pass a distribution， you know， you start from the initial distribution and you calculate what's the future step distribution。

 you need to multiply the matrix。 But in a way that， you know， if you have the， you know， P。

 let's say P0 is your is your initial state distribution as a vector。

 So that would represent the current state， right， And when you multiply it with a transition probabilities。

 So this should be the current state。And this should be the future state。

That will give you the evolution of the marginal distribution for stays over time。

 But here we're not doing that。 We're doing the other way around。

 We're taking itsplication of a value function in the future。

So actually taking this value function expectation of future value。You exactly need to like。

 you know， transpose this。And there's something actually even like deeper and interesting about it is that this like value function view versus state distribution view are in a strict mathematical sense。

 has a particular duality to each other。 And this duality is actually reflected by this transpoive matrix。

 and that duality will talk about it， exactly like maybe 2，3 lectures later later。

 When we talk about the linear programming formulation of MP。😊，Okay， so we have P pie。

 so once we have that。😡，We get this nice， very， very。啊。

Concise form of byma equation as a matrix equation。 V pi equals R pi plus gamma p pi times v pi。

 So here P pi is this is this S by S matrix。 So you have an S by S matrix multiply a S by one matrix S by one vector。

😊，Okay。Okay， so can someone tell me like what kind of equation do you get over here。

 What's the most outstanding characteristics of this matrix equation。It's linear， yes。Right。

 all you see is like the， you have to realize that we're actually solving for V pie， right。

 So V pie is the unknown。 P pie and R pi are essentially known。 I mean。

 they're not directly given to you， but you're given R。

 You're given P and you're given pi and calculating these are trivial。

You can calculate them and prepare them as a constant vector here， as a constant matrix over here。

And now you're actually up to solve for V Pi。 V Pi is your unknown。But in this equation。

 the unknown only appears as itself or is like linear transformation。So we get a linear equation。😡。

Okay， so how do you solve the linear equations， Well you move the right hand side， the unknowns。

 you move the unknowns to the same side。 So here I is the identity matrix of the appropriate dimensions。

 right， S by S over here。 And you have I minusa P pi V pi equals R pi。😊，Okay， what do you do next？

You take it Ams， right？😡，That's it。Except that you should ask a question。Is that an invertible。

 right， So that's， that's a question。 Like， you can only do this if this is invertible。

 But the nice thing is that if it is invertible， it also solve our uniqueness problem。😊，Right。

Because when you have a system of equations and the matrix over here is invertible。

 then it has a unique solution。😡，Right， so it will。

 it will address the problem that I left in the in the previous slide that in the previous derivation。

 we only show that Belba equation is a consequence。

 is a property of the definition of value function， but it's not an equivalent definition yet。

But here， if we show that V P， the be equation has only a single solution。

And VP satisfied the Belelma equation。 Then V is the single solution to Bma equation。Okay。

So we need to show that I minus gaa P pi is actually invertible。

So I think we still have a little bit of time。 So let me try to do that over here。

 and we may need to like revisit this since we're running out of time next Wednesday。

 So we want to show I minus Gamma P pi is invertible。

So what are conditions that you can think of for proving invertability of a matrix？So the said again？

Possitive definite。 Well， this is not even a symmetric matrix。

 So things like PD D is not necessarily a good idea to use。 What else。Great。

 so that's actually like a condition that very few people。

 like people think about like eigenvalues non，0 determinant and so on and so forth。

 all these like very advanced conditions。 But here we're actually gonna use。😊。

A very primitive one that it says for any x that is non zero。 So here x again。

 like in this particular setting， like all vectors。

 matrices should have the same dimensionality as like a number of states right。

 So X is any S dimensional vector for any vector that is not a0 vector。

 We should have I minus gamma P pi of x。That is non zero。So if we quite show that， this is inver。😡。

Okay。So how do I do that？What we're going to do is that we're going to look at I minus gamma P pi of。

A， so I'm going to ignore that， you know。And， and， and well。

 so I think one thing you maybe think about is like， you know， I minusma P pie。 Well， so here。

 the only thing that is complicated is P pie， right。

 and it's defined from that mark of change to be the transition matrix and blah， blah， blah， So like。

 what properties do you need remember。😊，For P pie， for for this proof to hold。

 So it turns out that all you need to remember is that this P pie is a matrix whose row sum。You know。

 row sum equals one， and is non negative。Right， so Ppa is this transition matrix Probabilities that each row is a distribution of the next states。

 So always the member， always elements are non negative， and each row sum up to one。

 This is the only property you need for this matrix to be invertible。O。So how do we do it？ Well。

 so you get this。 So we're gonna show that we're going to show that the。Infinite norm of this。Is。

I put a is greater than 0。 So what is infinite norm for any vector V。

The infinite worm is just the max over since here we use S as coordinates， so V of S。

So for any vector， take the absolute value of each coordinate and take the maximum value。

 That's the infinite norm。OK。So， you know。When you deal with norms in linear algebra。

 the most standard norm you have deal with a lot of times is probably L2 norm right， or Euclidean。

 Euclidean norm。 But you will see that actually in R L。

 whenever you actually need like the standard vector norms， L infinity L 1 is much， much。

 much more common， especially in the very early part of this course。 Okay。

 L1 will talk about later on。Okay， so I don't have time。 So I just do a quick sketch。

 and then we can do this properly later next week。 So this is what this is just x minus gamma P pi of x。

 if it or not。Right？Now， by triangular inequal， I can get x infinitefin norm minus gamma。😊，P pi of x。

Infinite norm。呃， it's greater than你过去。Okay， so this is a consequence of infinite norm being a norm。

 so any norm will satisfy the triangular inequ qualities。Okay， and then this part。 So what is P pi X。

 right？ So this is essentially if you remember， when we do in the Bel equation， we have P pi V。

 So that's actually just taking expectation of V pie with respect to the transition distributions。

So P P X， similarly， you're treating x as some kind of a function。

 And your each element in P P X is taking the expectation of X using different distributions。

But an expectation essentially can be viewed as a weighted average。

And then what you know is that weighted average can never exceed the maximum。

 So this you get greater than equal。 Sorry， this particular thing is less than or equal to。

Ace infinite norm。RightBecause P pi of X， you have x。You have P pie。 So P pie over here。

 So basically， youre trying all different kinds of way to do weighted combination of x。

 But all of them are averages， and averages can never exceed the maximum element in x。

So you have this and when you plug in， you get y minus sma x infinitefin norm。

And we start with x being a non zero vector。 So its infinite norm can't be 0。

 and gamma is less than  one。 So you get this is。鬼事站子。Okay。

 I'm out of time and we'll go over this briefly again next Wednesday。

 And there's a reading homework on the website， which will also， you know。

 go through it and we'll talk about it next week。answer very。

Because when you mentioned about as a case， you said the value function is a time。 Yeah。

 for that case， the state must include the time。 no no no it's other way around。

 Either the value function is。The value function。No。

 so you have to define value function in a way that includes time as additional input。

 Or if you don't want to do that， you can include T into the， you need to augment the state space。

 right， your new augment this state space is like the original state comma T。 Then in that case。

 you have like if you define things like properly like introduce a absorbing state and so on so forth。

 Then you can recover a notion value function that only depend on state。

 But the state there is actually the original state and T。 So T is there anyway。

 Yeah that augmented state space we don't have。Yeah， yeah yeah。

 because tea is already in the definition of state， yeah yeah。姉さん。哦，是是。

Do you have a pen or something？Does anyone？