# Stanford CS221 ｜ Autumn 2025 p10 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 10： Games I [SMOD_GiRzb8] [BV1XuPrzwEes_p10]

![](img/1b7f93357b0da0669b2a820f32659940_0.png)

So today's lecture is going to be about games。

![](img/1b7f93357b0da0669b2a820f32659940_2.png)

Remember last time we talked about Markov decision processes and reinforcement learning and the time before that we talked about search and games will complete our sort tour of the state based models and so let's dive in with an example。

 okay so we're going to play a game。This is called game one for lack of better term。

 so there are three bins here， A， B， and C。So you are going to choose one of the three bins。

And then I choose a number from that bin， and your goal is to maximize the chosen number。Okay。

 pretty straightforward。嗯。So。Let's do a poll， how many of you would choose A？Okay， a few。

 some people would choose A。 How many of you would choose B。Wait。

 I think some of you are voting twice， but okay， that's okay。

 maybe a stochastic policy and how many of you would you see？Okay， most of you would choose C， okay。

 so what should your strategy be？And as suppose， this is very ill defined。Right on purpose。

 And the whole point of games is that。Your strategy should depend on what I'm going to do。

And for example， if someone chose A， I might be linenient and I just give you 50。

 or I could be really trying to screw you over it and I'll give you minus 50。

So the challenge of games is that you don't know what the opponents going to do。

 So how do you guard against that I'm actually surprised more people didn't choose B。

 I guess you guys don't think I'm as adversarial as as I might be， but okay。So in MDPs。

 the agent is trying to maximize utility。And the environment is random and unknown。If it's not known。

 then we do reinforcement learning and it becomes known either implicitly or explicitly。In games。

 the agent is still trying to maximize the utility。

 but there is an opponent in the environment and thements opponent strategy is unknown。

Okay so here is the roadmap for today we're going to talk about modeling for a while， what's a game。

 we're going to see how we play a game and what the notion of game value is。

 and then we're going to look at a bunch of different recurrences that are going to help us understand the optimal values and optimal policies and then the last part of the lecture will be about how we speed things up either exactly or approximately。

Okay， so let's start with the notion of a game。 So the key object you should have in your head is a game tree。

 so I'm going to use this example throughout the lecture。

 so let me just draw on this on the board So the root of the tree is the starting state of the game and each edge that's coming out of a node are the particular actions that can be taken in this case。

 you can go ABC and。And then now it's you know my turn and I choose a number and that can either end in let me。

 Ill just leave the notes up there， so minus5 minus 50。U。1，3， or minus5，15。ok。

So every route to leaf path is a rollout or a trajectory or a game outcome of a game。And each node。

 a player has to make a decision。Some of the nodes are the agent making a decision and some of the nodes are an opponent making a decision。

Okay， so in this lecture and in this class in general we're going to focus on two player zero sum games。

 so what does that mean two player means that the number of players is two。

 usually this will be an opponent and an agent。And zero sum means that the utility of an agent is equal to the negative utility of the opponent。

So if you add those two things together， you get0。 Okay， that's why it's called0 sum。

 So in particular， if I get if you， the agent gets a utility of one。

 the opponent gets a utility of -1。And everyone you assume is trying to maximize their utility。

The total utility is  zero。Okay， so let's look at this example in more detail。

We can define this game formally， so a game formally has a start state as before。

 so this is just going to be the string root at each state I can call function to see if the game is over and that is end or whether it's a leaf node。

This is new， so at every state I also have a player function that tells me which is the player whose turn it is。

Okay， and that is in general going to be a property of the state。

 so the state knows which whose turn it is， and it's either going to be agent or op for opponent。

And then finally， each state is going to give me a set of successors。

 and I've written successors for our purposes here as a mapping from an action to a state。

 so taking action A takes me to state A。Okay， so let's do one other node here， so from state A。

 I'm not at the end。So A just to be clear as this one， actually， let me just write this。This end。

 so for a reference。Okay， and so so this is like changed choosing actions AC。 And this is one， two。

 just， I'm just gonna to label them。Its one， two。So the player at state A is up for opponent。

And the successors of this state are， the opponent can choose either action1 to get me to A1 or action 2 to give me to A2。

Okay， and if you're in A1， the game is over。And the utility is -50。Okay。

 so these functions I can call on any state， and that tells me what the utilities and the successors are。

Okay， so what's special about a game。 One is that。All the utility is at the end state。

So this is not a hard restriction， sometimes you have games that give you points during the middle and if the utility is a number of points。

 then that's fine， but usually I think in a game what matters at the end is whether who wins or not and or whether it's a draw。

And so even if you have a lot of points， you might still lose the game。

 and generally the utility is trying to capture what you want。

Okay so this is going to make things challenging， this is in the context of reinforcement learning。

 this is known as a sparse reward problem because you don't really know what's going to happen until you get to the very end。

 you might seem like you're doing really well and then everything crumbs。

And then the more important thing is that different players are in control of different states。

 So in Markov decision processes， we saw this a little bit。 Remember， there were。Agent control nodes。

 which are ones where the agent's trying to make a decision。

 and that goes to a chance node where the environment transitions to a successor state。

So now we're going to see many other types of nodes where the opponent is controlling some of the nodes now。

So just in terms of notation， a policy is still mapping from states to actions。

 so deterministic policy pi sub P of s is the action that a player P will take in state S。

And a sarcastic policy， which in general， we're going to assume。

Is this is going to be the probability that a player P takes an action A and state S。 Okay。

 and we'll see some examples of this。Okay。So here's another example of a game。

So this is a very simple called the having game， so I'm going to start with a number n。

 like let's say 11。And the agent and opponent are going to take turns。

Choosing actions and an action can be either decrementing n or replacing it with having it rounded out。

And the person who is left with zero wins。So what this might look like is so you start up。

And the starting state， n is 11， it's the agent's turn。

 so here we're seeing that the state marks whose turn it is explicitly as a field。

 the player here is obviously the agent the successors of this state are I can decrement and that takes me to this state where n is now 10 and its opponents turn or I can have where I take 11 divide by  two floor it and that gives me five。

And then here I haven't ended yet。Okay， so you can think about what is the optimal strategy here。

 I don't thinks it should be obvious unless you you're able to you do the mini max recurrence in your head。

 but this is just an example which we'll come back to。All right， so now you know what a game is。

The question is， do you have a consider discount where you're considering utility。

 so in this lecture we're going to assume all the utilities at the end。

Which means that there is just one number。And so discounting makes sense when you're accumulating rewards over time and you're discounting in the future。

 but there's only one number， so that's just the number， that's the utility。

So let's talk about game evaluation here。So given a game which we've defined and a policy for each player。

 the value of the game。Is expected utility overall possible rollouts。

 So this should be very familiar from MDPs where we define the value at a particular state of a policy is essentially what the expected utility is。

So let's look at a particular policy。 So we're still on this this game here， the game one。

 we're going to assume the agent always chooses eight。

And here because in general I'm going to consider satorcchastic policies。

 this is going to return the dictionary mapping each action to the probability of that action Okay so if I've met deter trimistic policy。

 I just see the action colon1 so with probability one I'm choosing a。The opponent， let's say。

 chooses randomly between one and two。So that's going to be represented by one has probability 0。

5 and 2 has probability 0。5。Okay。So now I'm just going to pack these policies into policies and that's going to determine the policies of all the players。

And now let's play the game。So gameplay is going to be given by the Simi function。

 which is very similar to what we've seen in search problems as well as for MDPs。

 and you start with a start state， and then while the game is not over you see whose turn it is。

And then you get the policy of that player， you pass in the state and you get a distribution over actions。

And then you sample an action given that distribution。And now once you've chosen action。

 the game dynamics take over and you look at the successors of that state。

 which remember is that mapping from action to successor state。

 and you pass into action and that gives you a new state。

And then you just keep track of all the steps。 So at the very end， you get a utility。

Which corresponds to a particular rollout。 So in this one， this case， I。

 that corresponds to choosing a。 And then the random policy is going to do a coin flip。

 and it happened to choose 2 here。 And that gave me a utility of 50。Okay， so that is one rollout。

And if I do it multiple times in average， you'll see that sometimes I get minus 50。

 sometimes I get 50。And the average of all of that is 15。嗯。

So now 15 is not the actual value of the game because there're sampling error I'm only trying it 20 times if you increase this number to。

 let's say a million， what do you think the mean utility will turn out to be？It should be zero。

 right， because half the time you're choosing minus 50 and half the time you're choosing 50。Okay。

 so can we compute the game value exactly without simulation and the answer is should hopefully be yes。

 because we can just define a recurrence to do this。

So I'm going to use this a picture to denote be a pictorial representation of what the recurrence is doing。

 so here schematically it represents at a particular state。

 I'm going the agent is going to move and then an opponent is going to move and then agent is going to move and so on。

And we're going to see variants of this。So given that， I can just define the recurrence as follows。

So V eval of S is going to be the game value at state S and with respect to the policies pi agent and pi up。

And then so if the I'm at an end state。Then I just returned the utility of that state。Okay。

 that's the base case。If it's the agent's turn to move。Then what I do is I look at all possible。

Actions。That the agent could take。 What is the probability of that agent taking that action。

And I recurse on what is the game value of the successor state？Okay。And then if as opponents turn。

 I basically have the same sum， some overall actions。

 the probability of the opponent takes action times the game value of the successor state。

The only difference is agent versus opponent here。Okay。

So this should hopefully seem familiar from MDPs where I also had a sum over actions and also a sum over successor states multiplied by the probability。

 so this is essentially doing a very similar calculation。So let's。You know。

 see how this looks like in code。 So this is V Eval。 If I'm at the end， I return the utility。

Otherwise， I see whose turn it is， get the player， look at the policy。

And then I'm just going to look over all the actions where for every action with probability prob。

I'm going to see where the game takes me if I take action in this particular state， what happens。

 and I'm going to recurse on the game value of the successor state multiply by the probability。

 and if I sum up all these values， then I get the expected value。

So this is just the same same but in code。All right。

 so one note is that this computation will be exact。But it could take exponential time。

So in particular， if at every node， you have two actions。And the game runs for 100 steps you。

Take two to the  hundred time， which is， which is not great， but。That's what it is。

So let's look at this example now， so here the agent always chooses a and the opponent is going to be this random policy that chooses one or two with each with probability half。

So conceptually what the recurrence is doing is that for every node from the bottom leaf to the top。

 it's going to compute a value which I've denoted in green here。So for this node。

 the value of this node is going to be 0。5 times minus 50 plus 0。5 times 50。

 that's going to Vp0 here it's 0。5 times 1 plus 05 times 3 that's going to be 2 and here it's 05 times minus5 plus 0。

5 times 15， that's going to be 5。And then finally， this is just going to be choosing the action according to policy。

 the policy always chooses a， so it's going to be1 times zero plus0 times 2 plus0 times5。

 which gives me zero here。So if I hand you a policy for an agent， a policy for an opponent in a game。

 you should be able to compute at the root node， what is the value of the game。

 which is the expected utility of the agent and remember zero sum which means that the expected utility of opponent is just minus that。

Okay， so summary。So value is the expected utility of the game of the agent。

We can simulate the game by just rolling out and average the utilities。

 And this provides us with a Monte Carlo estimate of the value。

 You can also compute the value exactly， but this could take exponential time。

 And this is analogous to policy evaluation in MP。 Remember， policy evaluation。

 You're given a policy of the agent。 You're also given the。Environment transition dynamics， which。

You can think about it as the opponent if you want， and then you're just computing the value。

So now you might wonder why would you ever do this because it takes exponential time and probably you wouldn't actually do this for game evaluation。

 you would just sample a bunch of rollouts and average and that'll be converge relatively quickly。

But we'll see later that you can always sampling doesn't won't work。Okay。

 so now we know how to evaluate a game， given fixed policies。

 let's try to actually compute optimal policies。So。So this is going to be called expectimax。

So instead of evaluating a fixed agent policy， we're going to find the optimal agent policy。

 but with respect to a fixed opponent。So the schematic looks like this。

 I'm going to use triangle to denote a max note where the agent is in control and a circle to denote a node where there is a fixed policy that's being run here。

So the agent goes first， then opponent， and then the agent and so on。So here。

 the expect x value of a state。I'm going to have a very similar recurrence。

 and the only thing that's changed is the part that's in red。Okay， but just to go through everything。

 if I'm at the end state， then I'm just going to return the utility， this is the base case。If。

It opponent's turn， then this is the same thing as before。

 I just consider the probability of the opponents policy taking various actions。

 use that to weight the value of the successors。And that， but if it's an agent's turn。

 instead of taking a sum over actions， I'm taking a max。

Because the agent wants to maximize the expected utility， so therefore I want to。

 the agent should choose the action that maximizes the game expected max value of a successor states。

Okay， so that's it。And you can see that for the expect max， you can't just sample。

m naiveively and get a muchco estimate because of this max。OkayWhen you have a sum。

 you can sample and that gives you unbiased estimate， Max， you can't。Okay。

 so let's see what this looks like。For our particular example。

 so I'm going to bring back this random policy which chooses one or two with probability half。

 so that corresponds to this opponent policy down here。And intuitively。Ex to Max basically says。

At the opponent node， I'm doing the same thing as before， I'm just averaging， but at a max node。

 I'm just going to take the maximum value in which case here it's a5。

 which is larger than zero or two。Okay， so some of you were doing expectax。

 the people who said I'm going to choose C。You probably thought I was just going to do a coin flip。

 so 15 seems pretty good， minus5， well hope that doesn't happen and you chose C。Okay， so in code。

 this is what this expectax looks like。Once you see these recurrences。

 theyre going to be very somewhat repetitive， but hopefully the marginal cost of understanding a new one should be going to zero。

So expect to max if the game is ending at a particular state， then just return the utility。

 otherwise see whose turn it is。And if it's an agent's turn。I'm going to remember。

 choose the action that maximizes utility， So I'm going to look at the next states。Here in this game。

 it's A B or C， I'm going to recurse and figure out what the expected max values of those states are。

And then I'm going to just choose the maximum one。Okay。

And then I'm not going to go so the opponent is the same thing as before。

 I've written it slightly differently but it just takes an average with respect to the opponent policy。

Okay， so the optimal action is to choose C in this case。Okay。

 so expectorax finds the optimal agent policy with respect to a fixed opponent policy。

 And this is analogous to value iteration and MP。 Game evaluation was analogous to policy evaluation。

 expect toax is analogous to value iteration。Okay。So so far。

 I haven't actually done anything interesting。 This is essentially all really MDPs， but just。

Describe in a game language。But now I'm going to do something different。

 and this is where I'm going to talk about minimax。So before the opponent policy was known。

 but the whole point of games is that we don't know the opponent's policy， so what should we do？

So there is a principle here that we can follow called miniimax。

And this is to assume that the opponent is out to get you。

 the opponent will play their best possible strategy and is going to minimize your utility。Okay。😊。

So here is the mini max recurrence that describes this principle。

 so now I have as before I have a upward triangle to denote where I'm taking a max in a downward triangle to denote where I'm taking a min so first the agent moves。

 that's a max， the opponent moves， that's a min， the agent moves， that's a max and so on。

And the recurrence is actually fairly simple， it's actually simpler than the other recurrences we've shown。

So the value， the mini max value of a state。Is if I'm the at the end， I get the utility。

 if I'm the agent， then I take the max overall actions of the mini max value of the success success states。

And if the opponent is taking a turn， then I take them in overall all actions。

Okay and that's why it's called minimax because I have Max and I have men。

So this is what it looks like for game one。So if I have these opponent nodes。

 which are now min nodes， then I take the min over minus 50 and 50， I get minus 50， take the min。

 I get1， take the min， I get minus5， and then the agent is going to choose the max over these min values。

 and the max is 1。So for those of you who chose mini Maxax chose B initially。

 you're probably brought any minimax in your head。And those of you who chose A， well。

 I don't have an explanation for that。All right， so this is what it looks like in cone。Mini maxax。

Compute the value， mini max value of a state。 If I'm at N， I return to utility here。

 I'm going to take a little bit of liberty， and I'm also going to return the associated action。

 not just the value， because I'm going to want to actually。Know what to do。

So whose turn it is it is I'm getting the player， I'm going to recurse on all possible next states。

And get a set of values。So that's going to be minus 51 and minus5。 and then if I'm the agent。

I'm going to take a max over all these values。And if I'm the opponent。

 I take a min over those values。And that's going to give me in this case。Action B。

 which gives me value1。So mini max value of a state is what the expected utility for the agent would be if the agent played optimally and maximized utility and the opponent played optimally and minimized the utility。

Okay， so let's see what happens with a having game now。So first of all。

I'm going to turn this minimax recurrence into a policy。And the way I do that is fairly simple。

A policy remember， takes a state。And returns a distribution over actions。

And so the policy is going to say， I'm going to take。The state。

 and I'm going to compute the mini max value。Of that state and associate action and just return that action。

Okay。And let's say I'm going to play the random policy。

The Brandon policy is just going to choose decrement or half each with probability half。Okay。

 so now when I simulate。I get something that looks like this。

So the agent decrement it now we're in 10 and now it's opponent's turn。

 the opponent decide to have now I'm in five agent is going to decrement opponent decrements agent is going to have and then。

The opponent is going to have to decrement and I get zero and now the age of wins。Okay。

 so this shouldn't be surprising because the agent should。Wow。Win if it's possible to win。Okay。

 so let's see what happens if I。I'm going to simulate 10 times。

And see what happens and the agent crushes the random policy， it wins every time。Okay。😊，嗯。So。

A few notes here。One is that the policy is。When you're actually using the minimax policy。

You are actually computing this recurrence at every state。Okay， and so here， just for fun。

I can show you for each of the first 11 states。What the mini Max value is。

So the mini max value is for 11 is one， which means that the agent will win assuming the agent plays optimally and even if the opponent plays optimally。

 and the best action is a decrement。This minus1。what does a minus1 mini maxax value mean？

So the opponent is guaranteed to win if the opponent plays optimally。

But doesn't mean that all hope is lost because if you're playing a weaker opponent。

 you might still win。And then on these states， the agent is going to win and then six， the opponent。

 if it plays out optimally， it's going to win and so on。Okay， so do what can I say here？

If the value is  one， the agent is guaranteed to win no matter what the opponent does。

 and we'll make this a bit formal later。And the value is minus-1。

 the opponent is guaranteed to win if they play optimally。ok。Okay， so a few notes。

 just as this is kind of a mor of an aside。 When the agent and opponent are playing optimally。

 this is known as perfect play。And you might have heard people saying， you know。

 checkers is solved or a game is solved， and what that means is that the outcome of the game under perfect play is known。

which means that we know the mini maxax value of the root， that's what solving a game means。

So there are some games which are strongly solved， which means that we know basically the mini max value for every single state。

 tech ta2， NiIm， Connect 4。Weekly solve means that from just the initial position。

 I know that what the mini Max is。And then there are also games that are unsolved， like chess and go。

So this is an important distinction between people think that chess and go are quote unquote solved because we have computers that can beat humans。

 but that could be true， but we don't know the main Max value of a node and we we don't have the optimal policy。

 we just have policies that are better than humans。Okay， to summarize here。The agent in miniax。

 the agent maximizes utility， opponent minimizes the utility。Unlike the Exp Act。

 there's no fixed policies given。Expected Max is only optimal with respect to a fixed policy。

 mini Maxs， as we'll see is agnostic to any sort of prior over what the opponent is doing。

And this is a part that is unique to games， there's no analogy to MDPs because MDPs we only max and average。

 we don't min。O。So this next part。Is going to be taking account of。

Well look at all these policies that we can compute and drawing some relationships between them。

 So this part is going to be a little bit more involved and well have to do a bit more thinking。

 but hopefully it'll be give you a lot more insight into the relationship between expect max and game values and and mini Max。

Okay， so so far what we've done is we computed these recurrences and recurrences give us policies。

 so the min Max， the mini max value， will give us the pi max。

 which is the optimal agent policy and pi min， which is the optimal opponent policy。Okay。

So these are basically， remember in mini Max we have min and max。

 and if we take the Arg min and AG max， that corresponds to the pi max and pi min。

We also could do expect X。And that gives us an expected max policy， I'm using parenthesesis 7 here。

 so pi 7 I'm going to assume is an arbitrary fixed policy that the opponent is playing and expect max 7 means I'm expect max with respect to pi 7。

Okay， so you have to be very careful when you talk about optimal policy。

 you always have to ask optimal with respect to what。

 because each optimal policy bakes in some assumptions about how the other player is playing。

So in minimax， we have that pi max is optimal against P min。Okay。

And we also have that P min is optimal against pi max because the min and max are symmetric。

And we know that expect max， the pi expect X 7 is optimal against whoever we're computing the expectax with respect to。

 which is pi 7。So what happens， so we have four policies here， we have pi min， pi max。

 pi expect max 7 and pi 7。And what happens when we play these policies against different policies？

So I'm going to use the notation V of a particular agent policy and a particular fixed opponent policy to be the value of a game when pi agent plays pi up。

Okay， and。We can play the policies against each other， so there's two Asian policies。

Pi max and pi expectorax， and then there's two opponent policies， P in and pi 7。

And for each cell here。I have a particular value， which is what happens when the row policy plays the column policy。

Okay， so the question is， is there any relationship between these values？

And let me actually just draw this on the board。As and I'll try to mark things off as we go。

 so we have。Pi max pi X X spec。Expect a max。Yeah。And then pi in。And Pi7。Okay。

And each of these has some value， and I'm trying to find the relationship between these values。Okay。

 so what can we say， there's three properties here。So the first property。

 remember is pi max is the best policy against pi Min。in particular。

 this is saying that this value is at least as great as if I had substituted any other agent。

In particular， this is the pi max policy。 if I substitute pi agent that does something else。

 it can only decrease the value。Okay， so using that fact。

Then we can conclude that V pi max is a pi min is greater or equal to this other policy。

 this is for all other policies， this is just another policy。

 So this right hand side is greater than less hand side。Okay， which means that。This holds。Okay。

 so this value is greater than that value。Okay。So second property。

 P Min is the best policy against Pm。Okay so that means if I'm an opponent。

 I shouldn't choose anything other than prime min if I want to minimize the utility。

This also another way to interpret this is that this provides a lower bound against any other opponent。

 which means that if I'm playing P Max，This plane the P Min is going to be the worst I do。

 If the opponent does something else， I can only get better。Okay， so meaning here， this。

 I'm guaranteed a one。RightIf the opponent does something different。

 like if the opponent happens to 15， then then you， I'm， I'm still gonna get。

I can't opponent choosing 15 is I'm going to decrease this one。

And it might go make it go up because if the opponent chooses three here， then I get a three here。

Okay。So applying this property， then I see that if I change the opponent's policy to something else。

 I can only increase the value。Okay， so which means that。

This this is the relationship between this number and that number。喂。

So this hopefully it should make sense if I'm at many， this mini max value。

 if I make the agent worse， then it's gonna to get smaller。 If I make the opponent worse。

 it's gonna to get bigger。So one important coreal area of this is that if the mini max value is one。

That means the agent is guaranteed to win no matter what the opponent does。 I claim this earlier。

 but now you can see formally why this is true， because if the agent does something else。

It's going to be at least one。And well， I guess in these games， there's only one。

 so it has to be one。And then so I'm guaranteed to win。

 that's why you can say with confidence that if you you playing the minimax policy and you return the value and it's one。

 then you're just guaranteed to win。Okay， so property3。

So remember what expect max7 is expect mass is optimal against pi7。

So one consequence of this is that。The mini max value is not optimal against if the opponent is known。

 so I mean just to understand this， so expect max is optimal against pi 7， which means if I change。

 expect this agent policy to be something else， in particular like pi max。

 which is just another policy。Then this can only go down。Okay， and you can see this here， expect max。

 remember was choosing C。And if I decided， well， I'm just going to play the mini max policy。

 I would choose B and two is worse than five。And this is because I'm assuming I'm playing pi 7。

 which is going to be the random policy。Okay， so based on that。This。

Pi max is Sap pi7 is going to be less or equal to this value here。So an important。

Realization is that you can actually do better than minimax if you know your opponent。

If you know you're playing a weak opponent， you can do all sorts of things that you wouldn't dare do if you're playing a really strong opponent。

Okay， so putting everything together。This is what we have。You know on the board。

 So the mini max value is。Is one。Um this。This value， if you play pi max against pi 7， that's a  two。

If you play expect X which will choose this branch against pi min， you're going to get minus5。

 and if you play expect x against pi 7， you're going to get5。

And it checks out that minus5 is less than1， which is less than two， which is less than5。

I think it's really cool how all of these values are actually kind of related together。Okay。

 so let's。Summarise。So when you think about optimality。

 you should also be very careful about what you're optimal with respect to。Miinni Maxax provides。

Two interpretations， One is that it is the optimal policy against。Pi Min。

 the worst possible opponent。However。Another way to think about it is a lower bound against any unknown opponent。

The way I've sort of introduced games is you don't know your policy。And I think that's。

 I generally like that interpretation better because it's。

 I think generally perhaps rare that you're going to get the absolute worst opponent。

 but you still want to use minimax when you want guarantees against anything that could happen。Okay。

 so now I'm going to talk about expected minim。 This is in some sense， going to be like a dessert。

 it's not that deep， but hopefully itll just give you another example of what you can do with recurrences。

So suppose you have this game。You have the three bins， ABC。And now you choose one of them。

 but now I'm going to flip a coin and if it's heads。

 then I'm going to move one bin to the left wrapping around。

 and I'm going to choose a number from that bin。 So if it's tails and I stick with the same bin。

And your goal is still is to choose the maximum to maximize the chosen number。So to model this game。

 we can just draw the game tree。I'm going to introduce a quote unquote， policy called coin。

 which chooses。One action with。Left with half and sorry。

 tails with half probability and heads with another half probability。

So what's happening here is that suppose you choose a。Then this is a fixed policy。

 that's why it's a circle。 I'm going to choose either heads or tails。And if it's heads。I move。

One to the left， and that I end up in C， which is why I have minus5 and 15。And then if I choose。

Heads， then I， sorry。If I， if I choose tails， then。I stay in the same bin and I have a here。

And if I choose B， then I either stay or move to the left。Say or move to the left。Okay， by now。

 hopefully if I gave you the tree， you should just be able to compute the value at the top。

 This is known as an expected mini max because there's expectations， there's。M's， and there's max。

 You have everything here。And。You know， I think it's pretty self explanatory。

 So the min nodes you min these nodes， you take the average and then at these max nodes， you max。

So here's the recurrence， there's three recursive cases now there if it's an agent's turn。

 you take the max， if there's opponent's turn， you take them in， and if there is the coins turn。

 then you compute the average weighted average with respect to pi coin。Okay so in general。

 you might imagine all sorts of different recurrences， hopefully this will unlock your imagination。

 so you might imagine more than two players， so in the PACman assignment。

 you're going to have a PAC man and multiple ghosts and you're going to have to reason about the multiple ghost。

 you can also have multiple agents in the setting， but in some sense it's all can be handled by this general recursion framework。

You can even do things like players can take extra turns or choosing who to go next or losing a turn。

And this is just because。All of this we're doing is transitioning。

 taking a state and transitioning to some successor state。

And the player who turn it is and baked into the state， and you can transition to any state you want。

Okay， so you know， if I you can brainstorm of。Game with some crazy rules with it。

 you can just define your recurrence like we've done before and you're off to the races。

So there are a few things that aren't covered by this kind of game treeree recurrence framework。

And this includes things like games with imperfect information。Such as poker or most card games。

 I think。 And the reason this is not。Included is that if you think about these game trees。

Everything passes through the state and the state has to have all the information。

 this is the distinctive property of MDPs and search problems and also these games。

So if you have different players with different。Information。

You you can't kind of represent this in the tree because you know。

 as you pass from a min to a max note， you there's no way to like。Bypass the state。

 if that makes sense。There's also， we're considering only zero sum games。

 but there are also non zero sum games， such as prisoners dilemma。

There's also collaborative games and so on。And there's also non term based games。

 So here it's turn based。 So someone takes a turn。 it's someone else's turn。

 someone else takes a turn。 And then there's some games like Rock paper scissors。

 which is simultaneously。If you did term based rocker paper scissors， that would be pretty boring。

Okay。So now we've concluded the modeling section of the lecture。

Now I'm going to focus on mini Maxs and try to speed it up。So let's talk about alphabeta pruny。

So let's revisit the basic mini maxax formulation， no dice， no weird stuff。

 it's just a classic minimax。Game。And so there are max nodes， min nodes， you max up the max nodes。

 you min add the min nodes。And now this takes exponential time in general。

exponentialponential in the depth， that is linear in the number of nodes。

 but the number of nodes can be exponential。So how can you speed this up？

The key behind this technique is a very classic technique from games called alphaphabeta pruning。

Is that you don't have to visit all the states。Before you know that some are just like not worth looking at。

Okay。So now the key is going to figure out how do we know when something is sub optimalmal if we don't even look at it。

It seems。Maybe a little bit kind of magical that you can just prune out parts of your tree。

Maybe there's like actually the optimal policy or optimal action sitting there。Who knows？

So to give an example of why this might be possible， consuming the following case。

Suppose you have two possible actions， A and B， and I tell you A can give you utility something between three and 5。

 I don't know what exactly， but something between three and  five。

And then B is going to deliver value between somewhere between 5 and 100。Okay。😊。

Which one would you choose？How many of you choose a？B。Okay。So why do you choose B， Well。

 it turns out you don't need to know what exact value or utility of A and B are。 You know that。A。

 no matter what happens， B will be better， or at least it' good。So there's this idea called。

Branch and bound， which is the general IDEDA principle， which are used in combatorial optimization。

 which says whenever you have you're going to maintain some intervals。

That keep track of where particular values might lie。

 And then you can prune out things where if you have an interval that。

 is strictly larger than some other interval。Okay， so here is an example。

Let's consider the following game tree。So I have。Let's imagine I'm searching， okay。

 so I'm do mini Mac search。 I do a depth first search traversal， so I come down here。

 I have a three and the five， take the min of three and5。 I get a three。 I go up here。

 And at this point， you know， this is I my best so far here is three and I come over here come down and find it two okay。

So what can I do at this point。Sorune I claim that I can prune this off and I don't need to explore anything over here。

And the reason is that the root is the max between3 and whatever is over here。

 this is min of two and some x。And this is going to be three， no matter what x is。

This can be a million。This is still going to be this， this is two， and this is going to be three。

 This could be minus a million。And then this is minus million， and this is still three。

Okay so in this particular situation， I've given you one example where hopefully you can convince yourself you don't need a look over here。

 no matter what this value is。Okay， so let me try to generalize that principle a bit more。嗯。

So in general。When we're doing。A search where computing Min Maxs。I'm gonna be add some note here。

And I'm going to。Intuititively， think about for every node， I'm going to have an interval or a bound。

And for the max nodes， I'm going to have a lower bound。And for the min node， I have a upper bound。

And this is because if I've discovered a 6， that max value can only increase。

 and here if I discover the eight， that number can only decrease。Okay， so on max nodes。

 I have these lower bounds。Mymin nodes have upper bounds all the way down for every node in the tree。

Now， think about where the Min Max value comes from。

It must have come from some leaf because I'm just taking max and mins of successor states。

And so there's some leaf that must have given rise to that value。

And so I'm going to talk about the optimal path is a path that's taken by these min and max policies to that leaf。

That is the thing I'm trying to find。Okay。And so this path needs to be within the lower and upper bounds that I have。

So which means that if。A node。Gives me balance that don't overlap。With every ancestor's balance。

 then I can prune that away。Okay， so for example， this is greater than6， less than 8。

 greater than three。 If this is somehow， let's say， less thanre equal to 2。

And then I can prune that away。Because this is greater than equal to three。

 and if the value of this is less or equal to2， then there's no way that this can be on the optimal path。

So the question is， can you prune this because this says it's greater than 6 and this says it's greater less than equal go to five。

 and the answer is yes。Because this interval does not overlap with this one。

 and I have to look at the entire anncetor stroke path。Okay。

 so let's do an example on the board here。喂你事。Here。And try to remember what9。 Okay， so have。3 nodes。

9，7。So notice that the tree doesn't have to have the same number of levels either， so six。3，4。

 some 9 to relieve。Whatops。Right。6。3，4。Seven， nine， and then over here，8 three。Okay。

 so suppose we're doing mini Maxax。Or alpha beta pruny。 So here。

Initially the intervals we don't know anything， so we're going to go over here。Come down here。

 Discover the9。So now at this point， I pop come up here and I say this has to be greater。At most 9。

Come over here。 I see that's a7。 I update that to be。Let's figure seven。

 actually this is just equal to seven because I explore everything， so now I come back here。Sorry。

I can't move this up anymore， but this is going to be， I'll just write it down here， at least seven。

So this is the alphalf。 So I forgot to say this， the。Let me just write this。 So each node。

So for the max nodes， I have alpha values。And the alpha values are going to be essentially lower bounds。

Lower bound on the value。 And then for these nodes， I have beta values， which are。Upper bounds。Okay。

 so here。This is greater equal7， come down here， I found a six。And I come up here，Most6。

So what does that mean， can I prune something？Should be over two， right？So in this case。

 I can actually prune out。I can just stop， I can just prune out everything here。

Because this is already greater than 7 if this is less than6， then no matter what happens over here。

 I can't actually change the value here。Okay， so then I come over here， greater equal 7。

 I find the eight。So this is now lesser E quota 8。Can I prune this？I can't， right。

 because these intervals still overlap。 So I don't have enough information。

 So I have to explore this。 I find thats a three。And then I have three。And then finally。

 update that to seven。Have done。So notice that alpha beta can be pretty powerful。Because。

It's not just pruning one node， you prune an entire subt。If you're lucky。Yeah， so the question is。

 does this work for expect max？The not the， let's see。 short answer is though is no。

 because when you have expectation， you have to consider all the possible things that could know happen。

You might still be able to do some alpha beta。 You can definitely do some pruning， I think。

There are cases maybe when。Like in expect max， if you have bounds on the utility。

 then you can still control how much even the utility could be， I have to think about this exactly。

 but that's a good question。How do I get the lower bound greaterd in equalta 7 here。

 Because when I saw this， this value of this sub is 7。So whenever I am at a node。

 I'm going through each of the children and updating the Mac。Yeah， so it's a top down recurrence。

 but you sort of go to the bottom and then you come up yeah。Okay， so how do you get lucky？

So let's talk about ordering。So the order in which you visit the successors of a state matters for how much you prune。

So for example， in this。Case that we saw before。 let's see。 So we had。So if we had three，5， two，10。

 then this 10 will get pruned。However， if we have two，1，3，5。Now， when you're computing this。

 you get a two， and when you go over here， this is greater you go to two， this is a three。

 so you won't be able to prune this。Okay。So in practice， what you want to do is to。

Go through the child node if you're at a max node， you want to go through the child nodes that are more likely to be large。

Because the larger they are， the tighter the bound is， and then the more you can prune。Okay。

 so if I were able to do this one first， three， first， rather than two， then I could have prune it。

 but not the other way around。So in practice， you can use a heuristic evaluation function。

 which we'll talk about shortly to order the children。You can decrease for max nodes。

 you order the children by decreasing value， and for the min nodes you order by increasing values。

In other words， you're really trying to find this optimal path， kind of guess the heuristic。

 and if you guess well， then you can be faster。So this is like just maybe a general comment。

We've seen many cases in this course where you can have exact algorithms still。

 even with a heuristic， and if your heuristic is good， for example， like in a star。

 if your heuristic is good， then it's great， you are very fast， and if your heuristic is bad。

 then you're not so fast but you're still correct。Okay， so to summarize alphabeta pruning。

 we speed up mini Maxax search。It's exact。And your。

Comp how much you save is going to be depend on your ordering and your problem。In general。

 it's still going to be exponential time。 So it's not like we've solved P equals MP。

And the intuition is that you want to order your actions to shrink the bounds as fast as possible。

Okay。So now let's talk about。Final thing for today is evaluation functions。

This is going to be an approximatexi way to speed up search。So here's the mini max recurrence again。

嗯。And。One the idea of an evaluation function is that you just say， forget search。

 I'm just going to take a wild guess， say how good is a state。Okay， so it is true that in a game。

 the only thing that matters who wins at the end， but nonetheless。

 you can still like if you're playing chess， you kind of know in some cases who's doing well and who's not doing well by just looking at it。

And so the evaluation function is trying to capture this prior knowledge about what might be good。

So in the case of chess， here is an example of a type of evaluation function you might have。

 so in general evaluation function is going to be a sum of different terms each term captures some intuitive property。

 think about as a feature if you want。So so you want a lot of pieces that's material。

 you want you mobility to be able to move you don't want mobility， King to be safe。

 you want to control the center of the board and so on and so forth and for material you might think that like well the number of kings I have versus the number King's opponent has kings are very important Queens are worth nine rooks are worth five。

And so on。Okay。So what do you do with an evaluation function？So you could just choose action that。

know， produces a state that gives you the highest evaluation function。This is， well。

 it depends on what the evaluation function you are， but if it's something like this。

 this is probably not going to be a very good chess player。

 it's just going to probably be too greedy and try to save your pieces and not really do very well。

But you can actually use an evaluation function and search。

And the way to do this is called depth limited search。And it basically says， take mini Max。

 I'm going to have a depth。Which is an integer， let's say，5。And say。

 I'm only going to search five steps。And then once if depth is zero。

 which meansve then I'm just going to call the evaluation function。I was like， okay。

 I'm not going to search anymore， Im just going。You know， vibe check and just give me a number。

And then ifm I still have search budget， if the depth is not zero， then when I recurse。

If I'm the agent， then the depth is D， and if I'm an opponent， the depth is t minus1。

And this is just to make sure that unit of depth corresponds to both agent and opponent going。

 so I don't subtract twice here。Okay， so that's that's basically it。

 Hopefully you've seen this is like the what sixth recurrence you've seen。

 So hopefully you're used to seeing these things。 There's no guarantees that you'll find the optimal policy。

 It's a complete heuristic and how effective it is is going to depend on how good your evaluation function is。

But the nice thing is that you have a bit of this kind of control。 the deeper you search， the more。

The less sensitive you are to the evaluation function being bad， whereas if you do a shallow search。

 your evaluation function better be good。Okay， evaluation function。

Prior knowledge that evaluates a state quickly。Do search to a certain depth and then use a value function。

 This is depth limited search and。And the analogy is。bit like。You know。

 future costs and search problems where you look a step forward and then you approximate。Okay。So to。

 to wrap up here， actually， one other note about evaluation functions， just to prime for next time。

 is that if you think about what does evaluation functions remind you of。

Maybe something in reinforcement learning。Yeah， so Q values or just more simply values， right。

Values are basically met。So Q values and reinforcement learning。

 let's just go with that since that's what you studied is a sort of approximation of the true value。

And so what this is going to。Allow us to think about is well。

 this evaluation function can also be learned。It can be learned from supervised data。

 it can be learned from reinforcement learning， and that's exactly what we're going to do next lecture is to learn the value Shi function。

Okay， but now to just summarize， so we've introduced games。Here。

 the agent is still trying to maximize utility， but the opponent strategies are unknown。

The mini max principle says， just assume the worst case the opponent is trying to get you and to minimize utility。

We define a bunch of different recurrences， given a game and a policy， we can do game evaluation。

 expect max， minim， expect minim， and you can imagine others expect mini mini expect max or whatever。

 whatever you want。And we look at two ways to speed things up， alpha beta pruning。

 which is exact and evaluation function， which is approximate。

And next time we're going to look at how you can do learning in the context of games and we're going to look at something called TD learning。



![](img/1b7f93357b0da0669b2a820f32659940_4.png)