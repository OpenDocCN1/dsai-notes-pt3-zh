# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p20 Lecture_20_Reinforcement_Learning_MDPs.zh_en -BV1Z2cUefE4A_p20-

All right。That's going to get annoying hang on me。啊。As't。あ月。好。All right， that's much better now。T。

All right good afternoon everyone sore sorry good morning what am I saying we're gonna go ahead and get started for today today we're going to think about a whole new kind of machine learning known as reinforcement learning we briefly mentioned it on Monday when we were talking about chat GT and how it's trained it's trained using something like reinforcement learning so what is this thing cards on the table today is gonna be sort of like a fun lighter lecture because you do have an exam tomorrow and so I didn't want to like put yeah thank you I want to put like know some heavy crap on you guys today that being said we are gonna start with what I didn't finish on Monday which is slightly heavier hey you have an exam tomorrow and then the homework comes out the day after that so you have that to look forward to this is the time in the semester where it's important to start being mindful of your grace day usage remember you are responsible for keeping track of your own grace days we sent out some information about that with the first grade summary but since then。

You have to count how many of you've used and if you run out。

 then we're going to start applying the late day penalty if you don't have any more grace days and you submit late。

Okay so where do we leave off on Monday I briefly showed you some of the more advanced variations of stochastic gradient descent。

 I wanted to make sure you just sort of heard those words before。

 but we have a little bit extra time at the beginning of today's lecture so I figured I could just sort of step through the intuition of some of these more advanced variants of SGD。

😡，This is a slightly more complete picture of how training in the real world for these deep learning models works right we sort of have a pretraining procedure instead of a random initialization and then we fine tune our parameters with respect to whatever specific fine tuning task we're interested in optimizing for so we're computing the gradient with respect to this sort of fine tuning objective if you will。

 but this update here is still a bit simplistic or a bit naive and it suffers from well lots of problems a few that we'll highlight here with some of the variations of stochastic gradient design。

The first is what we call momentum and this is the one that I mentioned has like a very sort of nice like physical or real corollary。

 let me show you how the math plays out first the idea is we introduce some sort of like decay or it's sometimes called like a forgetting rate or a decay parameter here and the idea is that when we go to take a step。

In this update line here。We're still stepping in the direction opposite our gradient plus some fraction。

 some small amount， well I say small， usually that beta is something like 0。9 or even 0。99。

 so heavily influenced by our previous gradient direction and magnitude crucially as well。😡。

Another bit of bookkeeping here in order to sort of make this math work out。

 you have to define sort of negative first gradient， if you will。

 this notation you'll see a few more times this is a zero elementwise product with all of my parameters is just saying I have a big zero vector or big zero matrix that is the same size as my parameter vector or my parameter matrix so my negative first gradient is all zeros。

😡，And what is the effect of this， well again we can step through these pictures。

 the idea is that if I'm at some location and my previous gradient step was very， very large。😡。

And that means intuitively， I'm probably very far away from some local minima。

 like the gradient is large when you're far away from some critical point。And if that's the case。

 even if my next step， my gradient were， I don't know。

 slightly smaller or pointing in some other direction。

 I might remember that previously just one iteration before I was sort of very far from a local minima and I might want to keep moving in that direction I might want to retain some of my momentum of this ball rolling through my surface to potentially break out of bad local minima。

 potentially break into bad local minima too there's no guarantees that this works。

 but it has sort of some nice like intuition behind it and empirically it does a reasonable job and we'll see sort of this play out on a slightly more realistic surface in just a moment。

 but the idea is that this is just another way of sort of dealing with nonconvexity or just sort of trying to like apply。

Clever， arguably clever， heuristics to try and deal with these incredibly non convex lost surfaces。

All right， so momentum is the first adaptation the next adaptation this is a little bit less intuitive。

 this is what's known as root mean square propagation。

 sort of a non-intuitive name and the idea if you look at the update rule here。

 let's start down here， the big idea is that we're going to have a different step size for each parameter and so what we're doing is again。

 we're taking an elementwise dot product between our gradient and something where now if we sort of work backwards。

😊，This matrix ST is going to have a different value。For every one of my parameters。

 so I'm going to be moving a different amount with respect to my different parameters。😡，Again。

 if we just sort of work through the math here， we have this sort of decay or forgetting parameter that says you should take into account how much of a step size sort of difference you are using in previous iterations and add to it。

😡，The square。Of your current gradients magnitude。 So again。

 this is element wise squaring my gradient。 So clearly。

The step size that is specific to each parameter is going to be related to the square of that parameter's gradient。

😡，How so though， well， if you look at now the update rule again。😡。

I'm taking the square root and dividing by it。 So intuitively。

 what this is saying is that if the gradient for some parameter is very， very large。

 Im going square root it get a big number。 that's just to sort and then square root it just to make it positive。

 And then I'm going to divide。😊，My step size for that parameter by a very large number。

 it's kind of weird that saying if the gradient for some parameter is very big。

 I'm going to take a small step in that direction and conversely if the gradient for some parameter is very small。

 I'm going to actually divide by a smaller number and potentially take a bigger step in that direction。

😡，Well why might we want to do that All right well here's a cute little animation there's a lot going on here and so I'm just going to like talk you through it one component at a time。

 The first thing to look at is the shape of the objective function It kind of looks like a。😡。

Like a weird bent taco， right， And the thing to note is that at initialization。

 the gradient is very big along the like。Taco shell direction and very sort of shallow along this long axis here。

So let's look at first what SGD does SGD does right SGD kind of does this thing where it like takes steps in the direction where the gradient is largest and it never really moves in the direction where the gradient is small that's because if the gradient is small in some direction。

 I'm not really moving that way I'm moving sort of infinitesimally or almost imperceptibly slowly along the small direction and I'm taking big steps along the large direction。

😡，And this is sort of exacerbated now if you look at both the green and the purple dots。

 those are both sort of momentum based methods， their variant of momentum。

 and this sort of exacerbated when you add momentum in right they swing back and forth along the direction where the gradient is steep。

 but they also well they have a hard time finding the direction where I actually want to be moving because my initial gradient in that direction is small。

😡，And now if you look at these sort of other three methods here， at a grad， add a delta and RMS Pro。

 these are all， again， variants of RMS Pro where they're doing sort of this parameterwise step size。

😡，And they are able to realize， okay the gradient is very steep in that one direction。

 so let me normalize my step size in that direction。

 let me not take a huge step in that direction and instead let me take sort of larger steps in the direction where the gradient is initially small and that's what allows it to sort of find this cliff and run off to the actual sort of desired minimum here。

😡，But if you're watching this animation， something happens near the end， just happened there。😡。

Give it a second to reload。Eventually the momentumbased methods do actually find that direction and then run off even faster than well everything except at Dlta I would Im pretty sure they end up catching at of delta if you extend this sort of figure a little further and so there is something to be said for like okay momentum isn't great but it will eventually find the right thing and once it does once it finds that sort of very downhill direction it'll take its momentum and run downhill and so naturally this raises the question why can't we have both why can't we sort of quickly find the right direction to move in using RMS prop and then accelerate our movement in that direction with momentum and that's exactly what people did。

That gives us sort of the most popular variant of stochastic gradient descent this is like the default optimizer and most deep learning libraries known as Adam and it really just smashes these two ideas together we're combining notions of momentum here i'm highlighting that in the yellow with notions of。

Paraameter based step sizes or RMS prop again highlighted in the blue there's a slight variation here note that like my computation for momentum it's in terms of like this decay parameter now where I'm taking some sort of like linear average between my current gradient and my previous gradients as opposed to just sort of adding in some small fraction that's like a really minute difference maybe the one sort of piece of bookkeeping here is that there's like some normalization going on of the momentum and the step size adjustments this is one minus beta2 and one minus beta 1 to the power of T so we're normalizing it by how many steps we've taken this is like a de biasing thing it doesn't actually。

I would argue it doesn't necessarily have a huge impact。

 but this is how the original algorithm is presented and's how it's typically implemented here。😡。

Okay， so this is just wrapping up what we briefly introduced on Monday， let me stop here。

 what questions about these SGD variants do you have before I move on for today？Yes。

previous gradient you the gradient gradient that GT1 include G yeah this is a really great observation so this is the other big change that I forgot to highlight here instead of adding Gt minus1 i'm adding mt minus1 and m minus1 depends on Gt minus1 and Gt minus2 and Gt minus3 and so on and so forth so i'm saving not just the previous gradient but increasingly smaller amounts。

Of even older gradients so each sort of previous gradient like Gt minus2 sort of appears in mt -1。

 but with two factors of beta1 in front of it， so it's slowly decaying I'm slowly forgetting about older gradients and waiting newer gradients heavier more heavily。

 but there is still some component of previous gradients in there so that's a really great observation as well。

😡，Yes。😊，talking they're knowing like one area or one direction a gradient center。好。

I would argue that， like。So the claim here is that like if all of the parameters sort of vary in roughly the same scale。

 like they're uniform in some sense， there's no like massive discrepancy ingredients along any particular dimension。

 then atom is sort of just going to learn to move equally in all dimensions which is exactly what SGD would do and so I think there's。

There's maybe very few， you can maybe adversararily construct some sort of loss surface where SGD does better。

 but like。I struggle to imagine a case where you would want to use SGD over at。嗯。

guaranteears for how Adam better they are all like。😊。

All of the theoretical guarantees for any of the gradient descent variants。

 they either only apply to like convex loss surfaces or like require。Frankly。

 like very unrealistic assumptions so like this is like a trend in what I would say like is machine learning research people love to like make theoretical guarantees。

 but like。😊，You have to make all these like ridiculously simplifying assumptions and so like yes。

 there are theoretical guarantees， are they particularly meaningful， no。

 I think the reason we use at is like the empirical performance。

All this stuff about Lichitz constantss and I don't know。Yeah， yeah。

 there are even more variants on top of Adam there's a thing called Adam W which is like Adam with some sort of weight based regularization baked into the gradient updates that's that's actually what GP is trained on those are sort of。

😊，I don't know， not particularly interesting， they don't add any like intuition and outside the scope of this course。

All right， so。We talked about on Monday。An interesting technique you can use when your sort of task。

 your machine learning task doesn't have these like nice tidy right answers right like when there is some notion of like subjectivity or not even just subjectivity。

 but like open endedness to the task，😡，The like canonical setup of supervised learning where you have like targets or labels that you're trying to get your machine learning algorithm to replicate that kind of goes out the window right and so we introduced this new idea of reinforcement learning。

😡，So let's talk about it like what the heck is reinforcement learning and I think one of the ways that we can conceptualize reinforcement learning is by looking at the kinds of data that we learn from in this particular setting right so in a supervised learning setting in a supervised learning paradigm we have these sort of features X's and we have you know labels or targets Y that are either real valued or categorical。

In reinforcement learning， the kind of data that we're learning from look fundamentally different。

 right？😡，We're going to。Represent these kinds of problems using the following data tuples。

 we're going to have state spaces that describe the state of some natural environment， the world。

 whatever your problem setting might be we're going to have actions so you're going to imagine your machine learner your algorithm is some agent that can act in this state space and then based on the actions that it takes in some state it's going to receive a real value reward that tells it good job or bad job was your response to this prompt a good one or was it crap。

😡，So that's going to be the kind of data that we're going to learn from there are lots of problems not just sort of like you know large language model based or chatbot based that fall into this paradigm。

 here's like the canonical reinforcement learning problem。😡，It's reallyally funny， yeah， like。

I've been giving this lecture for so long that like since I've put this picture in my slides like this company has like gone like bankrupt and its founders have opened a new self-driving car company I don't know if it's still based in Pittsburgh but anyway this was a previous self-driving car company known as Argo pictures like not super far from my house。

 so I used to see these cars driving around my house all the time not so much anymore。Yeah。😊，B。

 I think I just saw them in spreading anger。Oh really， did they get purchased by someone？是。

Maybe they rebranded under a different they have Yeah。

 I'm pretty sure they they might have gone under or maybe they were acquired maybe I'm misreming that。

Regardless， anyway， I will say in general， I think autonomous vehicles have kind of。Well。

 haven't had the success that they're。Backers might have originally hoped。

 but the idea is that this is like a very prototypical reinforcement learning problem right the state space for this problem could be some description of like the road。

 all of the various， you street signs， other vehicles。

 some way of representing all of the information that you know you or I take in when we're driving a vehicle the actions that you can take the actions that your algorithm can take or like the actions that you know you and I can take in a car。

 turn left， turn right， turn our headlights on， turn our signals on。Use your signals， you know。

 stuff like that and then the rewards， well that's an interesting question。

 but like it could be how quickly do I get to where I'm going， Did I arrive in one piece。

 Was it a pleasant ride， Did I， you know， break any traffic laws， things like that。诶。

Here's another really sort of canonical example involving robotics or automatons like this cute little guy。

 if you look down here， you can see this might have gone down because again， this is from like 20。😊。

2018， 2019 maybe you can buy these things for the low low price of $74。

500 and it's like really cute it'll do backfs and it'll like navigate like treacherous terrain and like despite being very cute。

 it has all these very practical uses of like you know exploring dangerous environments and like looking for I don't know。

 resources or targets in some environment that is otherwise not not traversible by humans。

A bit more of an abstract one， but again， a very sort of classic reinforcement learning setting is one of financial markets where you can imagine describing your state as the price of all the various stocks。

 bonds， commodities， options， everything that you could buy。

 your actions are buying or selling those bonds and your rewards are actual rewards， like real money。

 and so this is a very popular， or I guess it used to be a very popular application for reinforcement learning a little less so nowadays。

And I think one of the most at least like famous or well known examples of reinforcement learning are these game playing agents right so again some number of years ago。

😡，I really got to update these slides， I keep saying that some number of years ago。呃。

Open AI came out with a goplay reinforcement learning agent known as Alphago and it had sort of like remarkable sort of unprecedented success at playing this really complicated game of go now since then。

 you know like they've moved on to like other arguably more interesting tasks like like poker and Starcraft and dota。

 all these things that involve like hidden information and teamplay and sort of lots of variants of games。

 but like，I really do think there's an underappreciated aspect to like， you know。

 these game playing agents， people are like， oh， like。

 why do I care that it can like play this game really well， I think like。😊，This is。Broadly speaking。

 reinforcement learning is like one area of machine learning where we can actually like stand to learn something about reality from these agents and what do I mean by that well I have a brief sort of clip from this like really excellent documentary that I want to share with you all let me not do it on my iPad。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_1.png)

Instead。Let me do this。From my laptop here。And so I apologize we were struggling to get the audio working for the Zoom folks。

 so for those of you on Zoom I encourage you to mute me for a little bit here， go to this link。

Start it at。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_3.png)

That timestamp there。And then I'll call you or you'll notice when the movie stops on the slides and you can rejoin us here。

 hopefully this works。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_5.png)

Gen。都不错。都就对。第一。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_7.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_8.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_9.png)

你这样我理确，我。你好呢个。The friend we want。呃真可。Yeah， control。Yeah， that's an exciting folks。

 I think we sing in original rules together。That's the time move that you take those for。诶。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_11.png)

好的。好吧。The professional comment almost analysisly said that19 human failure chosen7。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_13.png)

So I putting around in Albet to see what Alphago thought。And I'm going actually agree with that。

A said there that one in100 probability that move that7 would have been played by human plan。

 So it knew that this was extremely unlikely。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_15.png)

It went beyond this human guide and it came up with something new and and creative and different。

I you very much。我是年已万面。That's the way it works moving down a few months or。At the same time。

 I'm lacking on the fact that they aren't confused， right。

 and that is an interesting moment but everyone else confused use。

 who is not confused right beside the machine。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_17.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_18.png)

放 leader分。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_20.png)

In fact in fact。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_22.png)

啊。系。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_24.png)

And我。我开始。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_26.png)

嗯。对。그 평 굉장히 참。Now you thinkあワトのま。It是 more than票面。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_28.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_29.png)

但么SE的目。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_31.png)

I think something change。Maybe for you， my is bad。Don talk geopolitics and something small that happens here that little of that。

Hours down down the road and different part of the board gain kind of a turnized access at that moment。

This move is very special because when zip move， all the don play before。

 it work together and connect into network everything。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_33.png)

It dance me。I audio here。Os。All right， so what do I like about that particular scene， I think like。

Much like with。Sort of the narrative around large language models。

 people tend to get a little out of hand about like。

You know the flowery language around emergent properties and like creativity and like true brilliance。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_35.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_36.png)

In some sense， it really is just doing probability calculations， but because it's not sort of。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_38.png)

Handcuffed by what we as a human is telling it the right answer is， like in supervised learning。

 it has the opportunity to show us patterns or。You know， strings of actions that。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_40.png)

Are well represented or like have high reward under its probability model that we as humans might not have considered。

😡，I don't want to like。Play， you know。Grumpy old scientist here， but like。

I think that we can talk about these things in like a truly sort of like respectful way without getting a little too like over our skis with the flowery language here。

 my point is that reinforcement learning systems like Alpha Go and like sort of all of these other applications。

 you know， have a lot to tell us about how the world actually works in a way that isn't just us telling the machine what the right answer is。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_42.png)

Okay， so。Back to class what we're going to spend today and next week talking about is how you can build up reinforcement learning agents like Alphago we're going to break this up into sort of nice digestible chunks today we're going to largely spend the rest of the lecture focusing on defining the problem sort of talking about what the objective function is talking about like what the structure of our data is and then next week we're going to spend the lectures developing algorithms to solve these kinds of reinforcement learning problems we're going to talk about value and policy iteration on Monday and then Q learning and a little bit of deep Q learning on Wednesday。

😡。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_44.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_45.png)

Okay， so next we're actually going to start to introduce this problem before I move on and now is as good as time as any。

 let me stop and take some questions， what questions do you all have about any of this stuff before we dive into the more cat class spec of it。

😡。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_47.png)

嗯。Are there any cases where we would objectively never want to use reinforcement learning？



![](img/7cc39c59d7185df54ac7dfd39f5294b5_49.png)

啊。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_51.png)

It's really hard to like speak in absolutes。I would say most cases where。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_53.png)

There is sort of a known ground truth and the reason we're applying machine learning is simply to scale up our inference。

Those are probably not the right cases for reinforcement learning， so like you know。

Predicting images of cats versus dogs。You can formulate that as a reinforcement learning problem。

 It would be a bit strange when like really the purpose of applying machine learning to such problems is that like。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_55.png)

I don't want to sit here and click cat or dog for 10 billion images， I want a machine to do it。

 let me get a you know machine learning a typical classifier to do that。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_57.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_58.png)

All right， so let's talk a little bit about how the components we need。😡。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_60.png)

In order to define a reinforcement learning problem and we're going to break this into two components。

 so the first the stuff on this slide， this is a set of things you have to define before you can even set out to solve a reinforcement learning problem。

 the two big ones。😡。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_62.png)

Every reinforcement learning has something known as a state space。

 this is like analogous to the feature space for a typical classified typical supervised setting this is the set of all possible states that you could see the set of all possible realizations of the environment the world so you know all possible road conditions for your autonomous vehicles all possible goboard game states for Algo and stuff like that and then the other component of this is the action space so this is all possible actions that your agent could take crucially this is all possible actions your agent could take in any state so it doesn't have to be the case that you can take every action in every state but if this is an action that you could take in some state then it lives inside your action space so like you know in certain go boards a move might be illegal whereas in other go boards it might be legal so any legal move on any board state lives inside your action space here。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_64.png)

![](img/7cc39c59d7185df54ac7dfd39f5294b5_65.png)

All right in addition to these two things we have to define two functions。

 these are sort of a bit more abstract but they are sort of crucial components of a reinforcement learning problem。

 the first is what's known as a reward function， and this is basically if I take some action in some state。

 how good was that action， how much reward， how much money。

 how you know many percentage points did I increase my likelihood to win by。

 lots of different ways to define reward functions。

 but you have to specify what you're trying to sort of maximize here。

And the other is a transition function， this is if I take some action in a given state。

 how does that affect the state of the world， what state do I end up in next。

 how do I transition from one state to the next state？😡。

All right and for both of these there are going to be two variants you can imagine stochastic or random rewards or deterministic or fixed rewards for the most part we're going to consider deterministic rewards we'll see why in the math a little bit later but both are an option and again it really depends on what you think is a better model for your environment in some particular environments like financial markets the reward might be deterministic I know that if I sell one share of this stock at this price I am going make back this much money 100% of the time but in others it's easy to model the rewards or it's more appropriate to model the rewards as random just because there's some sort of like fundamental unknowability in the world right like if I turn my car wheel some amount in this particular state of the world well I sure hope that I go where I'm intending to but maybe。

I veer a little bit off in one way or the other because there was some component that I wasn't like accurately accounting for。

Similarly， we can have stochastic or random transitions and sorry or deterministic transitions again let's think of an analogy here like if you're playing the game of go and I make a particular move I know 100% of the time that the next board state is going to look like the previous board state with one more stone where I put it but。

😊，For other environments like self driving car one。

 actions may not always sort of have the same outcome depending on random factors yeah。

things like your award been disaster， then your transition。

 your transition function will also involve。Not necessarily， you can mix and match。

 you can have say deterministic rewards and stochastic transitions like the stock market。

 you know I think like people would say yes， when I sell a particular stock at a price。

 my reward will be deterministic， but I have no real ability to model how that's going to affect stock prices on the next day。

 that's typically modeled using some sort of random process。Is there another question over here？Okay。

 so you've defined all of these things for your given reinforcement learning problem。😡。

What actually are we solving for So the thing that we are trying to sort of get our model to return to us the thing the output of a reinforcement learning agent is something known as a policy this is some function that maps states that maps crucially every possible state to some action this is basically telling me if I find myself in this state of the world what is the best thing for me to do that's the optimal policy for right now we're going say that you know any function that maps states to actions that's a policy。

😡，And our goal， like I said， is going to be to solve for the optimal policy given the components we defined on the previous slide。

Something very closely related to this notion of a policy is what's known as a value function。

 so this is sort of an abstract idea and again crucially you don't define this this is。😡。

Some function of or rather some it comes naturally out of how you define the components on the previous slide and what policy you're trying to compute the value of so the value function is specific to a given policy pi and the idea is it tells us how good being in some state and executing or following the policy pi is so this is again going to be a function that maps every state to some real value number and it says if I am in this state of the world and following my policy pi。

😡，Well how good is that going to be what is my sort of expected or you know actual return if nothing is random。

 what is my expected total reward going to be for that policy and the connection here is that the optimal policy maximizes the value function in every state the best thing I can do in every state is achieve the most possible reward sort of going forward and so the claim here。

 the connection is that the optimal policy can be solved for by first computing this value function and maximizing it and that's going to be the approach for many of the algorithms that we talk about next week。

 but before we get that sorry before we get to that let's see some examples of these components at play here。

😡，All right， so let's take a look at our first ridiculously simplified reinforce reinforcement learning problem right so this is a very classic reinforcement learning setup known as like a grid world exactly what it sounds like my states form some grid specifically my state space here is all empty spaces in the grid。

 you can think of this as like。😡，I don't know， a really dumb maze that you're trying to navigate a robot through where there's like a pillar in the middle of your maze and you're trying to get to the exit。

 which is a plus one and you're trying to avoid。Some fiery pit， which is the minus one。

The actions you can take are up down， left and right will say that。😡。

But transitions are deterministic， so if you take the up action and there is an open state above you。

 you end up there， if you try and take the up action and it's blocked either by a wall or this pillar。

 you stay where you walk。😡，Same for all of the other directions。And our reward function。

 I'm going to sort of define it in words， you can actually come up with the math。

 like you can describe this mathematically， but in words。

 our reward is going to be plus one for entering the state with plus one and minus one for entering the state with minus one。

😡，And we're going to say that these。2 special states plus 1 and -1 are what are known as terminal states。

 This is a frequent sort of component of reinforcement learning problems。

 Most reinforcement learning problems have a natural end state。 So think of like。😊，诶。

No one ever plays games of go to the actual end of the game of go， but like chess。

 chess has a natural end state where one player has one reinforce like autonomous vehicles。

 your natural end state might be I reached my destination from these terminal states。

 you can either imagine the game sort of looping forever in that state or the game ending and you restart back at some initial state no matter how you formalize it。

 the sort of idea is the same once I hit those terminal states。

 I'm not going to receive any more future rewards。Okay so given all this setup we can sort of examine policies and think about them in this setting right so here's a policy this is again some mapping for every crucially every non-teral state I don't need to specify what happens in a terminal state so this is some mapping of every non-terminal state to a valid action either up down left or right and the question that I want to spend a little bit of time thinking about and I'm going to ask you to spend a little bit of time thinking about in your first few poll questions is is this policy optimal where crucially I have not to find that word is this policy optimal and tell me what you think tell me why you think it is or isn't optimal。

😡，All right， so go ahead， take oh， I don't know， let's call it three minutes here。

 talk this one over with your neighbor， see if you can come to some sort of consensus and then we'll reconvene and see what you'all have to say。

Crucily， I should note， there is no toxic option for the second question。

 but you do have to put something to get credit， just put your name。

 put end slash it like whatever you want， it just can't be blank to get credit。Oh， yeah。

 let's all right， perfect three minutes， let's go ahead and talk about this so。😊。

I go to your responses oh I love this this is like one of those really great questions you are split 60% saying yes 40% saying no and I think one of the great things about this is that yeah it really is sort of open ended like I think both are defensible so let's take a look at some of those defenses。

😊，诶。Oh good people are putting their name who put my name， you put a joke， let's see。

It should always reach plus one total reward is always plus one and achieves the maximum reward。

 you will always get reward plus one。 the arrows never hit minus1。

 That's an interesting definition of optimal I like that one a little bit different， but yes。

 you're never going to get the negative reward is also sort of a good way of thinking about it So those seem like all defenses for yes。

 this is optimal。Let's see。Some other ones。There are more optimal ways， some always ways are optimal。

 but some ways are more optimal than others。 If we're defining optimal as shortest path。

 this does not guarantee it gets there with the least steps。 shortest path is the optimal path。

 Let's see here It might take a long time to reach the positive reward。 Yeah， okay。

 I think you guys have hit on the。We should go up at location 33。one，2。I think that you mean one。

3 perhaps I mean I don't know it is sort of ambiguous how we're defining these states I haven't really numbered them。

 but yeah I think you guys are sort of hitting on the two big possibilities here that yes。

 you can argue that this is optimal because we will always reach the maximum reward of plus one or no this is not optimal because we could reach the plus one faster given a different policy Yeah there's no assumption being made here about starting point whatsoever I guess I should clarify and say that。

Given some initial initial states， we could potentially reach the maximum reward faster。

 but you're right， if we always started this agent in the top left， for instance。

 then sure this policy would be optimal under both definitions。

 but it's not optimal for all possible initial states。

 and this leads us to sort of the crucial missing component for these reinforcement learning problems。

 which is that。😡，In most real world circumstances， we do have some value on reaching our higher rewards faster。

 You know， this has some like real world， like modeling translations。

 like this is typically how humans value rewards。 We value sort of like more immediate rewards higher and further out rewards less。

 I mean， this has， you know， like。😊，This is commonly the approach used to model like economic and financial markets and also mathematically having some sort of time decay for rewards is going to make the actual algorithms and optimization tractable and convergent so lots of good reasons for why we might want to prioritize speed here。

😊，Yeah。Let me show you a few different ways that we might do that， right？😡，So you can imagine。That。

Again， let's go back to the analogy here。😡，Excuse me。

Let's go back to the analogy here that this is like some robot navigating a maze， right， what robot？

Probably runs on like fuel or electricity， and that costs real world money， right so every。5 feet。

 every step your robot takes， it's going to cost you some amount of money。What if that money？

Is minus two units per step。Well， what this policy says is。

Your robot sucks you should try and trash it as quickly as possible， so let me I don't know。

 walk it into this like fiery pit because that will eat fewer costs than the cost of taking a step I don't know maybe your robot is really cheap to build and that's why it's so energy inefficient that's sort of a strange way of treating this penalty here's maybe a slightly more realistic one where again we're having some additive negative penalty per step to model these sort of like you know cost per step actions。

😡，But this one， I think achieves what many of you would claim to be the optimal policy here in that it will try to move as quickly as possible to the plus one reward here。

😡，Okay， so now let me show you how this is actually done。😡，What we're showing here is a。

Additive penalty that is not typically the way that we model these kinds of decay what we're going to use instead is a multiplicative penalty like I said that has its sort of roots in like how human psychology typically models rewards as well as financial markets and it is going to have the nice property of making a lot of the math sort of converge or be friendly before we talk about that let me just stop here really briefly are there any questions about this poll question or this example here。

😡，嗯。Is there a reason that we always see like one when I deserve her time where we would actually want and she is negative one？

I think。If you would ever actually want to achieve negative one。

 you should encode that as the higher reward like your reward function has to be some accurate depiction of how you value outcomes that's sort of crucial to like the fidelity of your reinforcement learning agent otherwise you could learn policies that。

😡，The reinforcement learning agent will always do what you tell it is best。

 and so you can encode that in different ways using the reward function。😡，Yeah。

Stop criteria on the flash the stopping criteria so the termination。

 the terminal states are either the plus one or the minus one If my agent ever ends up in one of those states。

 the run or the simulation ends and I can either。Go back to the beginning， pick a new initial state。

😡，Or how this is also occasionally modeled， I can remain in that state forever accruing zero reward the reason that terminal states can be modeled like that is because it means that once I hit a terminal state。

😡，All of my subsequent rewards are going to be zero and so it's about finding terminal states with high reward that's an effective way of modeling what we're going to go on and call infinite time horizons。

😡，Yeah。It never gets to a reward state。Then it will continue to accrue rewards of zero sort of infinitely and the idea is that as long as you have some positive reward somewhere in your state space。

Zero rewards forever is always going to be like less optimal than hitting the positive rewards。

I mean， that's what we're going to spend sort of Monday and Wednesday talking about but how can it actually find positive rewards？

We'll see a short example of that in a few slides here。

But let me first set up the problem so what we're going to define is what's known as a Markov decision process and this is like basically where our data for reinforcement learning problems come from and it's just sort of like an instantiation of the various components that we've defined already the idea is we have some initial state and from there。

😡，Sort of looping forever or just like going one time step at a time。My agent looks around。

Seize the state of the world that it's in and based on that state。

Takes an action defined by some policy pi， right， So pi here maps states S T to actions 80。

 Given those pairs， we can observe either a random or a deterministic reward。And then again。

 given those pairs of states and actions， we end up at some new state。

 either again deterministically or stochically， and we just keep doing this right so each pass through this for loop gives me one data point。

 it gives me a state action reward next state tuple if you will。

 and that's going to be the training data that I use to train my reinforcement learning agents。😡。

And at the end of this， you can either and this is where the infinite sort of time horizon thing comes in。

 you can either imagine sort of modeling this with like terminal states or you can imagine modeling this by saying if I hit a terminal state。

 then I just continually receive zero reward infinitely so that's why there are those two different approaches regardless the total reward at the end of some run is what we're going to call this。

😡，Infinite horizon time discounted， cumulative reward。 It's mouthful。

 but what we're saying is that this gamma here。Oops。Is my discount factor？And it's going to be。

Some quantity。Typically between zero and one， sometimes it can be exactly zero。

 and we'll talk about that a little later， but the idea is that I care about future rewards。

 some amount less than I care about immediate rewards going to give this kind of like inflation that is really kicking my butt right now。

Now， the crucial thing that this Markov decision process does is that it makes one major simplifying assumption。

😡，That makes inference in this setting tractable。 If you look at how I defined the state and the transition and reward functions。

😡，And you might have noticed this a few slides ago as well。

 They only depend on my current state and my current action。😡，They don't care how I got to my state。

 they don't care about what actions I took before my current time step。

All they care about is where am I now and what action did I take in that state and in many ways this is a sort of bad assumption or maybe a potentially flawed one in many real worldor settings like the sequence of states that I took to end up at some current state should affect my total reward。

😡，Again， you can imagine maybe modeling this as like。😡，呃。

You can maybe imagine the problem of like autonomous vehicles right like if I ended up at my destination state。

 but I took a really long circuitous route that cost me a lot of fuel or like really frustrated me because I sat in traffic or something like maybe that should affect my final reward not just you know those intermediate rewards the reason we do this is like I mentioned。

 it makes the modeling process。😡，Functionally possible tractable right like otherwise you might have sort of these exponentially growing dependencies on increasingly more states and actions。

 so we have to make some sort of simplifying assumption it's called the Markov assumption hence Markov decision processes like I said this is the design choice there are ways to sort of hack around this where like you can bake previous state information into your current representation of the state that's kind of cheating。

 but it's one way to get around this assumption again at the cost of sort of computational intractability here。

😡，Okay， so this is going to be where our data comes from。

 I want to take a minute and reflect a little bit on what makes reinforcement learning so different from our traditional supervised setting。

😡，And we can sort of think of a few key challenges here and this is sort of the big one we're not going to think about this on Monday。

 but we're going to think a lot about this on Wednesday in that loop that I was just showing you have to have some agent。

😡，That is。Sort of gathering its own data to learn from the data that it's learning from are these state action reward tus and those aren't just like given to you usually in some nice like cleaned training data set。

 you have to go out and gather that data。😡，The outcome of these actions or rewards。

 it could be random， which is already problematic， but you might not even know like how random。

Think about like playing the game go When I make some move， I have no idea like。

I can't even really begin to describe whether or not that move was good or bad。

 much less like how good or bad， mostly because that I don't really know how to play go。

 but like even for human experts like describing the like reward of a specific move can be like impossible and so we might call those unknown until you actually play out the game and see how impactful or how good a particular move was。

😡，And related to the point above is that like an action in some current state could be good or bad。

 but you're not going to find out until much further down the pipeline here and there's this very classic tradeoff in these kinds of settings where agents have to go and gather their own data that's known as the exploration exploitation tradeoff and I want to highlight that for you all with a little bit of an example here so this is like the classic I said that a few times this is really like one of the more classic reinforcement learning problems known as the multi-armed bandit problem。

😡，So bandits， you know，'re those things， they're traveling packeds， they have arms。

 they like to take your money， you know？These things， right？

And so we can actually model this particular setting using our reinforcement learning setup。

 so here's what we're going to imagine， we're going to imagine that there is a single state。

 that single state is you in front of three slot machines。😡。

Multiar bandit being a slot well a bandit being a slot machine。

 it's about to take your money and there are three of them multiarmed。

There are three actions you can take， you can pull arm one， you can pull arm two。

 you can pull arm three， regardless of which arm you pull， you find yourself back in the same state。

 staring at three slot machines。And the rewards you're going to receive are stochastic here。Now。

I would like to play a little game with you all。Before I do that。

I need you all to say something with me。Henry does not condone gambling in the classroom。Yes。

 good good This is not gambling because what I am going to give you is an opportunity to earn rewards at no cost you are not losing any money here so this is not really gambling。

 but I am going to need。😡，Say four volunteers。One， two。3。And one more。4， okay。

 we're going to go in that order。 You don't need to come down and I have us' actually pointing at your friend here。

 So what we're going to do。😡，Is I have concocted for you。

Some bandits that pay out chocolate coins because I had a bunch left over from our example previously so here's what I'm going to offer to you excuse me friend here I am going to allow you to pull three arms by telling me which square you would like me to uncover and I'm just gonna start from the top and uncover going down to get you started I have taken the liberty of pulling bandit one three times and I have received good I have received three chocolate coins so my friend which arm would you like to pull first two let's see what's behind。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_67.png)

Door number two。 Oh， it's two pieces of candy。 How do I， Oh gosh， move out of the way。 All right。

 let's put that up there。 All right， What would you like to pull next。Two again， all right。Oh oh。

 zero， how about now？Where would you like to go to？Three， three， behind door number three one， okay。

 okay， so you also get three pieces of candy。Here you go， all right。Don't spend it all in one place。

 All right， so let's go to volunteer number two。😡，So having seen what your peer upfront did。

Which arm would you like to pull next？Two as well， okay， let's see。Oh， zero。

I wouldn't put three zeros in a row right you could try again， what do you think。

 where do you want to go next？3。Oh， three visas of Ganddy， yo！One。

 really sure you sure you don't want to go back to three Oh okay， one， you' get one piece nice。

 all right， so you get four pieces of pandy。All right。Of course。Now， volunteer number three you。

Well you have some a bit of an advantage here， right， you have seen what your peers have done。

 you know a little bit more than they did， so I'm going to make this a little harder on you。😡。

Instead of pulling one arm at a time。You are going to have to tell me which two arms you would like to pull first。

 and I'm going to reveal them both to you before you get to make your third selection。😡。

So which two arms would you like to pull？One， one and two， one and two， okay。

 let's see what's behind one。Oh， a zero， okay， let me ask you this。

Before I show you what's behind door number two。😡，呃。

Would this extra information have changed your behavior in any way？Probably okay， okay。

 well let's see what's behind door number two Oh good at two Okay。

 so what would you like to pull for your last arm number one again。😡，Oh， okay， okay， not a zero。

 not a zero I really mean I didn't realize I put so many zeros here， all right， and lastly。

We volunteer number four。So much like。Your friend up there。

 you also have more information than before， so Im going to ask you to pull all three of your arms at once。

 so which three selections would you like to make？😡，2，4，3。 Okay， let's start with one here。Oh， zero。

 okay， let's see what's behind three here。Oh no， what another zero， okay， let me again stop here。

Would this extra information have changed your third selection？😡，No， you would still play arm three。

 I like that， and I think。Okay， well。Here's your constelation prize thank you very much for playing I've got a few more of these so if you want some you can come find me at the front of the room after class what have we seen from this example here but what I'm trying to highlight is that。

You have to gather information about the setting as you're going。

 and I bet for those of you who are sort of playing along or for those of you who are actually playing。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_69.png)

There was some temptation to like pull those unseen arms like， you know。

 when we first discovered that there was some like high reward under bandandit three。

 maybe like you wanted to learn more about what was going on， but there was some， I don't know。

 vague notion of safety with bandit one here，I will say because everyone always asks， let me。

Let me just go back a little bit here。去。

![](img/7cc39c59d7185df54ac7dfd39f5294b5_71.png)

I think if you guys had been a little bit more dedicated to the bit here。Oh。

 there were there there were some big ones。 Oh， there's another zero。 I think there's another oh。

 there's a four in there。 anyway， it's neither here nor there。 regardless。

 there is this tension that is the exploration exploitation trade off in reinforcement learning problems。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_73.png)

Okay， so let's talk a little bit more sort of quantitatively here。

 next we're going to think about what the actual objective function for reinforcement learning is。😡。

Like I said， our goal in reinforcement learning is to find optimal policies that is what is the best action I can take in every state and my claim and I'm not going to prove this。

 but it's not super difficult to sort of conceptualize。

 my claim is that the optimal policy is the one that optimizes the value function。

 that is if I'm taking the highest value action in every state if I'm taking the action that gives me the most expected sort of discounted total payoff in every state then I sort of stitch all of those actions together into a policy。

😡，So the question。Of finding an optimal policy boils down to computing what the value function is in every state。

 what the optimal value for every state is。SoWe're going to spend a lot of time thinking about that value function。

 we're going to start by sort of assuming deterministic everything that's going to give us the sort of easiest expression for this quantity。

 and then we're going to think about sort of deterministic variance。😡，If everything is deterministic。

 sorry we're going to think about stochastic variance next， if everything is deterministic。

 well then the value of being in some state S and executing the policy pi is just this discounted total reward of starting in some state S and executing policy pi forever what does that look like well I can write that as okay I'm in some initial state we'll call this S not and I know this is some state S。

😡，And I take my。Action defined by this initial state S or s not here and I get some deterministic reward capital R this is my reward function right so after I take this action in this state I end up at some new state what is that new state well that new state will call it maybe S1 this is my transition function my deterministic transition function delta。

😡，Of being in。My initial state and taking this action pi of s not。

 and that puts me in some new state S1 in this new state S1。

 I'm going to take another action dictated by my policy。😡，Hi of S1 here。

And this pair is going to give me some reward。 This is going to be the reward I get in the next time step for being after starting in S and executing the policy pi。

 except。This next reward is discounted by one factor of my discount rate gamma because I care a little bit less about it because it's coming to me one time step later。

And so on and so forth， down the line， you know， the reward I get in my next state S2。

 where S2 is the transition function applied to S1 and pi of S1。

The reward for taking the action high of S2 in this new state is going to be doubly discounted by two factors of gamma square。

So on and so forth right and I can write this as some infinite sum over time steps。

Where I have increasing powers of gamma times these rewards of。My， let's see， previous state。

 ST minus1 and the action I took。In that previous state。Does that close that？

And the action I take in this current state。Okay， and again。

 we're assuming some discount factor between zero and one here can be equal to zero if it's equal to zero that means I don't care at all about future rewards。

 it's kind of a weird modeling choice， but it is a valid one for sure。Okay。

 so this is how we can define the value for any given state。

Using my policy pi if everything is deterministic next I just want to show you the equation for the stochastic variant here we're going to say that my transitions are stochastic and my rewards are deterministic we typically think of deterministic rewards because if your rewards are stochastic like you just replace those capital R's with the expectation of your reward distribution and all of the math is the same so like it's not a particularly interesting twist the interesting twist comes in when my transitions are random instead and so for this again I'm just going to write this out sort of at a high level what we're saying is that this is an expectation with respect to my transition distribution now so I have some distribution over next states S prime。

😡，Action， S and A。And I can write this now as something very similar to before where I have my initial state。

😡，And the action I take in this initial state plus。Increasingly discounted。Future rewards。

Where now note that the rewards are still deterministic but。These state variables。Say。S1。And S2。

These are now going to be random variables that I'm going to have to contend with right because I don't know what the next state S1 is going to be。

 It's not always going to be the same if my transitions are stochastic and I don't know。😡。

S2 is going to be and so on and so forth so again。I can rewrite this as。An infinite sum。

Using the linearity of expectations， the linearity of expectations says that the expectation of a plus B is equal to the expectation of A plus the expectation of B。

😡，Sort of for any distribution over those two random variables here。

 so what I can say is now that this value function。Is， again。An infinite sum， but this infinite sum。

 let we actually also pull out。This gamma to the T factor here。

 this infinite sum is now a sum over expectations instead of deterministic rewards of R of ST。

H of ST。Okay， I'll stop here and give you guys a chance to catch up on Monday we're going to exploit this infinite sum structure to actually come up with a expression for the value function that will allow us to solve for it for right now I just wanted to highlight that you can write these value functions using infinite sums and then like I said on Monday we'll see how we can exploit that for a gain but right now let me stop here what questions do you have before I move on。

😡，Yeah， right here。发到你的手。No， so crucially， the value function is defined for every state S if I go to some other state like you know some non initial state。

😡，I'm just changing what s not is here。 So for many problems。

 there's not like a well defined initial state for like you know， games like go， yes。

 there's an initial state of an empty board， but for， you know。😡，Financial markets。

 I can drop you in at any time point， so there's not always a well defined notion of an initial state even。

😡，Yeah， right here。youYeah， that's exactly right because I have something that's random now I have to be taking expectations instead of just sort of deterministic everything on this slide。

SoThat's exactly right if I had stochastic rewards as well I could replace this capital R with expectation of my reward distribution as well and that's why that math is like not super interesting like if you think about the random variables being states like that's going to lead to sort of more complex math whereas like。

If I take an expectation over the reward distribution。

 I'm sort of replacing it with like another real value here。

Whereas the states are these sort of like discrete objects。啊。Yeah， stochastic。

 you can sort of replace with random like one for one。Yep。

Yeah assuming then the importantly body surroundeded for the next period and weeks that's right。

 this is a good point the policy pie needs to specify a valid action in understanding that's sort of a fundamental requirement of a policy。

And how could we to initialize the study degree？We're going to talk about that on Monday it's a really great question even the like concept of initialization is sort of a weird one like how are we going to solve for this we'll talk about that on Monday for right now I just want to give you a quick example of what a value function looks like and to do that。

😊，I'm going to use one of my favorite examples， which is oops， American football。

 I'm just going get this out of the way here for those of you who don't know。😊。

My team sucks my team is the New England Patriots we're terrible anyway。

 for those of you who don't know anything about American football。

 let me show you how the game works The objective of the game is you have the ball and you're trying to move the ball down the field towards your opponent's end zone and once you get close to their end zone you can either kick a field goal which is worth three points or you can score a touchdown。

Whi I don't know every other team except my team can seem to do you can score a touchdown which is worth seven points and there's this really weird thing where like if you're near your own end zoneone and you run it backwards you can score negative two points that is you can give your opponent two points and you might think I'm making these numbers up I'm not that's really how American football works so we can imagine computing a reward function or defining a reward function for this game like this I have this cute little grid world where the states 05 and6 are terminal states I get some reward for entering those states and let's just say my discount factor is 0。

9 here right。😊，All right， so what does this example allow us to do well it allows us to say like take a policy like this here's a strangelook policy right。

 but for any valid policy such as this one I can compute what the value function for that policy is so what might that look like well the easiest way to do this is to start with the terminal states if there are any and work backwards the value of being in any of these terminal states is always going to be zero like I'm just going to stay in them forever。

 I'm never going to get any more rewards right so the value of being in any of these terminal states is just zero。

😡，So working backwards from there， what is the value of being in this state， well， in this state。

 my policy says I go up， I get an immediate reward of three。

And then a future discounted reward of zero forever。

 I'm just sort of getting infinitely many copies of zero after that initial award of three。😡。

So my value for being in this state is just three。Similarly。

 my value for being in this state here is a very strange minus2 because I get an immediate reward of minus two for following my policy and then zero infinite rewards after that。

 infinitely many zero rewards after that。And then for these next two states， well， their value。

For these states here is just going to be， well， regardless of which state I'm in。

 I get an immediate reward of taking that action， I get an immediate reward of being in this state here and going right。

 I get an immediate reward of0 and same here I get an immediate reward of 0 for going left but then once I'm in those subsequent states。

 I know the value of being in that next state， let's say I'm looking at this example here。

 I know the value of being in the next state is three。

 so I'm going to get that three one time step later。

 which means the value here is three times my discount factor 0。9。😡，Or 2。7 and similarly。

The value of being in that state is minus 1。8。So this is how we can actually sort of manually compute value functions。

 but the big question that we'll revisit on Monday is。😡，Why on earth？

Wouldn't we just use this policy right this policy has this very nice property where the value function is just sort of increasing or decreasing。

😡，Powers of 0。9。Multiplily into seven。And you can show that this policy corresponds to the highest possible value for every state。

 and that's the relationship between our value functions and policies here。😡。

So the big question that we're going to think a lot about next week is。

How on earth do we go about learning these optimal policies？All right。

 that's all I had for you today， I will see some of you in my exam room tomorrow。

 the rest of you you'll be in some other exam room。

 don't forget to check piazza for which room you're in otherwise。😡。



![](img/7cc39c59d7185df54ac7dfd39f5294b5_75.png)