# Stanford CS221 ｜ Autumn 2025 p05 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 5： Search I [fPESauMaJYA] [BV1XuPrzwEes_p5]

![](img/28706a52a35d5b12b48dc455709b218d_0.png)

![](img/28706a52a35d5b12b48dc455709b218d_1.png)

Alright， let's begin。 So last week， we talked about machine learning。And just recall。

 the learning algorithm is something that takes train data。

 which is input output pairs and returns a predictor。

 and the predictor is the thing you go out into real world， which takes inputs and outputs outputs。

 and for regression， that output is a number for classification。

 that output is one of K options or a class or a label。So that's what we did in machine learning。

Now if you go back to the first lecture， recall call the ingredients of intelligence。

 we have perception， reasoning， action and learning。

 so a predictor really covers this latter bottom part。

 so it's basically reflexively mapping percepts to actions and we're learning this mapping directly。

So if you think about the neural nets that we were learning， even if it's deep。

 probably it's feet forward and it's fast。Now many problems in the real world do require reasoning。

 thinking， problem solving， planning， these are all related concepts。

 if you want to solve a hard math problem or solve big hard program challenge。

 these clearly are not reflexive operations， if you look at it and then you output the answer。

So this week's lecture is going to be about search。

 Search is one form of this type of reasoning when the world is deterministic。

So as a few concrete examples， finding a sequence of moves to solve a Rubi cube。

 I guess if you're a RubikQ expert， maybe this is reflex for you。

 but for most people this requires a fair amount of search and problem solving or finding the shortest path from point A to point B。

 this is going to be something that you explore in your homework This something requires planning。

 you have to figure out your route and then you go down the route rather than just looking at where you are and just making a spontaneous decision。

So now you might wonder， okay， it's 2025， why are we talking about search because wasn't the point that symbolic AI actually started in 1950s and they were all about search。

 how you can solve checkers， general problem solving and so on and that didn't really pan out so why we bothering with this。

 shouldn't we just go all in on deep learning， so is it relevant today。

So I want to pull a quote from this famous essay by Rich Sun， which is At Tori War winner。

 developed a lot of the foundations of reinforcement learning called a Bi lesson。

 which I think has become a little bit of a kind of folklore。

 it's a short essay you guys should go read it， it has some you I think useful perspectives。

And in the essay， basically， it says that。General methods that leverage computation are ultimately the most effective and by a large margin。

 So it really rich is pushing back against doing a lot of handcrafting priors because once you have general methods and you have compute that it sort of washes away any sort of prior knowledge。

 Now， I mean， that's that's true in some limit， there's obviously cases place in a time and place for a prior knowledge as well。

But putting that aside。He also says that the two methods that seem to scale arbitrarily in this way are search and learning。

So he calls out search and learning are really kind of these pillars that if you believe in the bitter lesson。

 are the things that you should pay attention to。And that's why we're talking about search。

 So search is increasingly important。 Think about test time， computing and language models。

 which we'll touch on in a bit later。 These are cases where you actually just need to do a bunch of compute at test time and you need to organize that compute somehow。

The only thing is that search alone， the point from the 50 is that search alone cannot do this。

 you also need to learn learning， but now the last decade has told us how to do learn。

 learning and have now we have really powerful models and if you can couple them with search which people are starting to do more。

 then you have a really powerful combination and you can tackle some of the most challenging problems。

Okay， so that's the motivation， feel free to interrupt or ask questions。Here，What is search。

 great question。 I'm going to define it more narrowly。 The rest of this。

lecture is going to be about more of the nuts and bolts and how you do search。

And hopefully it'll become clear。So let's formalize search using this abstraction called a search problem。

So we'll do this through examples， so these are going to be fairly to， simple examples。

And so the first example is this。So imagine you have a street with blocks numbered  one through n。

 so n is6 here。So each of these grid lines is a block。

And walking from block I to block I plus1 takes one minute。

And or you have this magic tram that you can take from that goes from I to2 times I。

 and it takes two minutes。Okay so the question is， how do you travel from？One to n。

 which is six in the least amount of time。Now， some of you are probably already solving this and thinking about strategies。

 I want you to actually stop doing that。Because that's not the point of a search problem。

 The point of a search problem is to formalize。Convert this national layer description into code so that you can have a general method that can solve these problems。

 Again， remember the bitter lesson， we want general techniques that can solve any sort of search problem that you kind of handed。

Okay， I mean， if you solve it， too， that's great for you。

 But' we're going to have algorithms that solve this。 and we'll see if you're right。Okay。

 so we're going to define a search problem that's going to be parameterized by the number of locations and the problem is going to have a start state。

So the start state is this member。Of the search column that tells you what state you start at。

 So the state that you start out is one。And the problem also has a function called successors。

 which you pass in any given state， and it tells you where you can go， essentially。

And so let's look at this， okay？So one thing you can do is you can walk。Okay。

 so if you're at state a particular state， one。So you can take the action， which is walk。

 it costs one， so one minute I'm translating cost to be time here。And then where you end up。

 you get dubbed into state plus one。So you go from I to I plus1， right？

And this check is just to make sure you don't walk off the face of the earth。

 the world stops at numb locations。Okay， so you can also take a tramp。 So here the action is tram。

The cost is two， it takes two minutes to take this tram。And you end up in state two times state。Okay。

So successors is the list of possible steps， so a step consists， each step consists of the action。

 which is just a label， the cost of that action， and where do you get dumped into the next state。

So in this case， both walking and tram takes you to state two。But in general。

 they obviously will do different things。Okay， so we have start say， we have successors。

 and the final function that is part of the problem formulation is the function is end。

So there is and takes arbitrary state and returns whether you've reached the destination and the search is done。

 so here we're just checking， did you get to the number of locations or not？And in this case。

 the answer is obviously false because we just started。Okay， so in general。

 a search problem has the following components。 You have a start state。

That returns initial state successors that specifies。What you can do， which includes the actions。

 their costs， the resulting states that you end up in， and finally we have is end。

 which takes a state and returns whether state is an end state。

 any questions about what a search problem is？O。So now we're given a search problem。

 what are we trying to do？The objective is to find a solution which is a sequence of actions that minimizes the total cost。

So here's a possible solution for n equals 10， so you walk to state  two。

 you take the tram to state  four， you walk to state5， you take the tram to state 10。Okay。

And this solution。嗯。Has cost 6。Because that's one plus2 plus1 plus2 is6。Okay。

So this is one possible solution， there are many other solutions you can walk all the way to 10。

 that would be a cost of 10。And no， is this the best solution？

How many of you think this is the best solution？How many of you don't think this is not the best solution？

HOkay， well。Evenly split， so we will see。Okay。So remember， it doesn't matter。

 we're going to be lazy and have the algorithm solve it for us so you don't have to work that hard。

 The thing you have to get is make sure that your search problem is defined properly and then you're good to go。

Okay， so let's do a slightly more complicated example to just show you what states are really about。

So suppose the magic Tra requires tickets， and we only have a fixed number of tickets。Of course。

 this tram is probably in high demand， so we're not going to let anyone just get on the tram。

So how do we change the search problem to incorporate this constraint？Okay， so let's see。

 what can we do here？So the state so far just captures where we are， the current location。Okay。

 but we also need to keep track of the number of tickets we have。So what we're going to do。

If you're going to define another search problem， limited travel search problem and。

Which is going to be parameterized by the number of locations and the number of tickets you start out with。

And now the SA said。I iss this going to be the structure travel state that has a location with one and tickets equals the number of tickets that you started with。

So states can be composite things， they don't have the integers， they can be strains。

 in general in the implementation， states are going to be any sort of hashable object。Okay。

 so what do successors look like now。So now the successors takes the travel state and has to return a list of things to do。

So there's only two things you can do， you can walk or you can take the tram。

You can always walk because you don't need tickets to walk and this is walk has cost one and the new state is this travel stay where the location has bumped up by one and you still have the same number of tickets。

Because walking doesn't take tickets。And now， the second part of this is you can take the tram。

And the tram costs to， you end up in the location two times the location， and then oops this wrapped。

's okay。Hopefully is that。Okay。Okay， it looks like it's not going to unwrap。 Okay， there we go。

 but that's probably too small。 Is that too small。Okay， let me make it bigger。 So anyway。

 this is tickets minus-1。So we。Expended one ticket to take the tram， but as a result。

 we're in location two times location。Now， there's one thing that we need to do here。

And what is that？嗯嗯。So there is a check here that we need。To make sure that we actually have tickets。

You can only add the successor if you have non zero number of tickets。Otherwise。

 it's the same problem， you just end up decating counter and you can have minus three tickets and you go on。

So this is what I mean by get your search problem definition correct， because if you don't。

 then the algorithm is going to find a way to cheat sort of game your system。

 is you can call it this reward hacking if you want。嗯。Okay。So successors are walk to location two。

 and you still have one ticket or take the tram to location two and you have zero tickets。Okay。

 and is end is。Just have you reached a destination？

And notice that it doesn't look at the number of tickets。Which means that。

There are possibly more than one end state。RightBecause you can have zero tickets left， location。

 goes unlocked with zero tickets， one ticket， two tickets， and so on。O。So in general。

 the state is a really important notion when we talk about search problems and also MDPs and then games。

The state contains any information that's needed to evaluate future actions， costs and successors。

Okay。So as another example， suppose we put another constraint。

 There are a lot of rules in the city here。 If you can't take the tram twice in a row。

So how if you want to enforce this constraint？The state needs to contain enough information so you can even properly assess it。

The current state that we don't， we only know our current location and the number of tickets we have。

 and that's not enough。What we have to do is we have to add to the state。

 which is another field in the state structure， whether the last action was taking the tram。

Because if we know that， then if we last took the tram， we can't take the tram。

And if don't we didn't take the tram， then we can take the tram。Okay。

So there's just going to be kind of this game you have to play where you take essentially like word problems and you have to map them onto this type of structure。

 what is the say what are the successors costs and actions？So now you can ask well。

 you know why do I have to think about it， I thought the goal idea is I don't have to think。

 why don't we just include everything into the state， like the entire history of where we've been。

 and surely that's enough information to evaluate the validity of actions and states and successors。

You could do that。But as we'll see later， some algorithms。

 such as dynamic programming scale in the number of states。

So if you have a million states or exponential number of states。

 then your algorithm is going to be really， really slow。So， in general。

You want to keep the number of states small。Okay， so so far。We focus on modeling。

So what modelley means here is representing the problem formally。So there's no doubt in our mind。

What a solution looks like， and that solution in code should correspond to your intuitive idea of what a good solution is。

Now， the thing is that as you build up these search problems with more and more constraints。

 maybe you were clever and solved the first transportation problem， but now if I tell you， well。

 how do I go to one to 100 and you can't use take the tram twice and you also have three tickets。

' I would be very shocked if someone immediately came up with the answer in their head。Right。

But the point is who cares， we have written it down formally。

 and now we're just going to pass it off to a learning。Not a learning， an algorithm。Okay。

 any questions about modeling， search problems？Trains， magic trams。Yeah。

 do you use some protocols for example？The progress for。problems for example。The the easiest one。

We have the problem just to reach with walking or training。And without something。

 how we understand this can be solve。佢五符。So think。So I think the question is。

 if you look at the easiest problem and you add constraints， how do you know this is useful。

 or I mean， generally when you're trying to solve a problem。

 whether it be machine learning or search， either you or someone comes to you with a problem a description of a problem。

And you have to translate into something that's more formal that process of modeling is often lossy。

 sometimes you don't get all the constraints right。

 and of course this is a sort of idealize a setting。

 but you have to basically make some sort of lossy modeling assumptions to get into a tractable form there that the algorithms can operate on you can't really have your search algorithms operate on just like a kind of vague description。

Okay， so we said we don't care， but okay， now we have to care about it because we actually do want to solve these search problems and if you know who's going to do it except for us。

So let's start by solving this problem exactly。 Okay， we really want the minimum cost solution。

 Later， I'll show you how you can cut corners if you're short on time。So remember the goal。

 given a search problem which defines states， actions， costs， and is end。

I want to find a sequence of actions that minimizes the total cost。

So exhaustive search just says simply try all the possibilities， all possible sequence of actions。

And take the one that's best。Okay this wall， this should work。

Now there are many ways to enumerate all solutions we're going to choose one particular formulation that will allow us to effortlessly generalize the dynamic programming and this will be also the formulation that generalizes to Mark off decision processes。

 reinforcement learning games and so on so bear with me why I introduce what might seem a little bit more machinery than we need。

 it's because we're trying to think a little bit farther ahead。😊。

So the key definition here is future cost。So a future cost is a function that takes a state。

And is the cost of the minimum cost solution from that state to the end state？Okay。

 so here's a picture， let me actually draw this on the board。So。In general， you have a start state。

 and just for now， I'll assume that there's one end state， there could be multiple end states。

And in general。From the starting state。There might be multiple actions， the best way to I think。

 understand this is in terms of a graph where these actions could lead to other states and and so on and so forth。

 and here's a random state here。So let's call it S。

And the future cost is there could be millions of states here。 The future cost is， if I started here。

You know what is the total cost， the best total cost of getting to the end。

And future cost is something that you can apply to any given function， you can apply to the start。

 if you apply it to the start， that gives you the solution to the problem。Okay。

So how do you compute this future cost？Well， let's take it step by step。So in life。

 if you have to solve a really hard problem。What do you do？You have to take a first step， right。

 no matter what solution there has to be a first step。 Okay， so let's start here。Well。

 there's actually， okay。You know， many potential first steps here that you could take。

Let me just do this。So I'm going to use S prime to denote。The successors。And。

And then what I'm going to do is I'm going to say this is someone else's problem。 Like。

 if I've computed the future cost from S prime to end。Then I can just piggy back off of that and say。

 well， I could have gone here with some cost。And then。Over here。

 I'm going to put maybe some swiggly thing。 and this is the future。Cost of S prime。Okay。

 so one particular route is take this action and up here and then do the optimal thing to the end。

Or I can take this action， do the optimal thing to the end。

Or I can take this action and do the optimal thing to the end， right？And。

You know which one is the Opim one？Well， it's whatever one minimizes the cost overall all possible future successors。

So the cost of this is cost plus future cost， the cost of this is this cost plus this。

 the cost of this action is this one plus that。And what we're going to do is we're simply going to take the minimum over that。

 right So just writing out the pseudo code for this recurrence。

The future cost of a state is the minimum over all possible successors。

And for each successor I look at it's the immediate cost of that's taking that action。

 plus the future cost from wherever I ended up to an end state。Okay。

 let me pause there if to address any questions。こ。嗯。Okay， how many of you are good with us？O， okay。

So let's go through an example here， and we're going to look at our familiar travel search problem。

And we're going to implement this exhaustive search function here。

I'm going to implement four algorithms today， and for each one I'm going to keep track of number explores。

 so this is a number of states that we've looked at and that'll give us an idea of time complexity。

So we're going to define this helper function called future solution。

 It's essentially the future cost function， but instead of just returning a number。

 it returns a solution which remember also contains the cost and that's because we don't just care about solving the problem in returning a number Oh 42 is a cost Well。

 you know what do I do What actions do I take you also need the sequence of actions and that's encompass in the solution。

Okay， so。I'm going to start at the start state， and I'm going to call this futurist solution function。

And what I'm going to do， I've explored a state， and I'm going to check， did I get to the end。

 so I haven't got to the end yet， so then I'm going to look at the possible successors， Waqua Tram。

And then I'm going to consider for each of the successor， there's a which is taking the first step。

 which is walk。 and then I'm going to recurse。If you call future solution on。First step state。

 which is two。Okay， so I'm going to recurse， that's going to take me to stay two in this recurrence。

 and then I'm going to look at the successors， I can walk a tram， and then I' going to consider walk。

 and I'm going to recurse。And then。I'm going to do this again。 and eventually， I read。

Arrive at an end state。And at the end state。The solution is。What's the future cost of Ed？0。

 because I'm at the end， and I don't need to do anything。 I'm， you know， it doesn't cost me anything。

 And the steps is 0。 I don't need to do anything。 Okay， so that's the base case。Now I。

 I pop back up and。I here I'm just going it's going to be hard to follow all the details。

 but I just want to give you the kind of rush shape of this。Actually。

 let me just skip out of this because this is probably not。

 you can follow this a trace through this in your know when you study this afterwards。

 but hopefully the recurrence is clear。So let me just kind of go through this。 So at each state。

 if you're not at the end state， you look at all the possible successors。

 So these are these things coming out。 And then for each successor。

 you recursively call future solution， which gives you these。

And then what I'm doing is I'm going to just choose the best solution。

 which is the one that has the smallest cost。At each state。Okay， so in the end。I got walk， walk。

 walk。Which has a cost of three as the best solution here。And I explored nine states as a result。O。

So， okay， these numbers are out of data。 I had five states before， but now， nonetheless。

 the number of states explored9 is larger than the total number of states， which is4。

Which means that we are exploring some states more than once。So we'll come back to this later。Okay。

 any questions about exhaustive search yeah？How good co that。

Does that become an issue with sort of staco flow。Yeah， yeah。

 so the question is how long is a recursion going to be？So it is。

Basically the length of your solution and in the worst case。

 it's infinite because if you have cycles and you go around。

 I will come back to that point a little bit later。But for now。

 let's just assume that's not that bad。Okay， so let's try some larger problems here。

 So let's try 10 locations。If I do exhaustive search， so remember， this is a question I asked， like。

 is that is walk tram walk tram the optimal solution？And it turns out to be。Yes。

In that it got cost of six which is optimal， it turns out to be multiple optimal solutions。

 you could also walk， walk， walk， walk， tram。So thats the minimum cost solution doesn't have to be unique。

 but the minimum cost obviously is unique。So。Here's another one， 17 locations now。Now。

 you see the number of。Explore states growing quite fast， right， and in fact。

 it is going to grow in general exponentially with the number of locations you have。嗯。

And which means that the time complexity of doing exhaustive search is worst case exponential in the number of states。

So this is pretty bad news right， because even if you have， let's just say 100 states， 100 locations。

It's going to take， you， I don't know the exact number。

 but it' going be a it's probably not going to terminate anytime soon。Okay， so that's kind of rough。

 What about the memory complexity。So the good news is that the memory is linear in the length of the solution。

And it's basically what you have to keep track of is this it's done sort of implicitly through the stack in the recurrence is where basically the stack represents the path that you've took to a particular state。

ok。So now coming back to this earlier question， we are assuming that we can't have cycles。

Because what happens if you can go from state A to B to C even back A？

Is that you'll notice that this function， as I've written it， won't actually terminate。Because。

Eventually， oh， you go back to A and then you go to B，C，A， BC，A， BCA， and it just never ends。Well。

 it ends when you run out of memory， but mathematically。

 it doesn't end and it iss also not well defined。So next week we'll see how value it for Markov decision processes actually gets around this and allows for cycles。

Actually， I， I'll show you。Better than， I'll show you Wednesday how you can get around this as well with uniform Co。

But in the meantime， what you can do is。We can， here's a trick。

You can add the number of steps into the state。Okay， so this eliminates all cycles。

Because you're always。Moving forward in time。So if you go A to B to C to A。

 now that A is going to be different because you've taken a different number of steps。

So that's how one way you can break cycles。Now， you have to。

It still doesn't prevent the infinite looping。 You have to separately define I end to be true when the number of steps exceed some threshold。

So now you're counting steps， you can say like after 100 steps。That's it， I'm no more。

And then you can define in， let's say， infinite cost if you're exceeding the threshold just to say that those states are essentially no good。

Yeah我。The first solution that you're supposed to get to is also the threshold。

 I there a way to set that threshold so that we know that we might a solution Yeah。

 so the question is， basically how did you set the threshold Because it's possible that the optimal solution might be beyond this threshold。

嗯。There's no general answer to this except for just look at the problem and figure out what you need to do。

 generally， when the costs are， positive。You can have， essentially。

 if you look at the number of states and think that should be a pretty good upper bound。 I mean。

 it probably can be very loose。Sometimes if you have negative costs， the optimal answer is actually。

 if you find a technically， if you find a negative cycle。

 you just keep on going around and then your cost goes down and down and down but that's sort of degenerate。

 if you detect that then you just return minus infinity。Yeah。

Thoset the ease function and't necessarily have to do fine。So。Yeah， so the question is。

 is the end function have to also now determine whether it's successful or failure， Yes， morally。

 the way I've sort of implemented this again is a little bit of a trick where you say is end is just going to return Boolean。

 is it true or false and then I'm going to put it on the successor function to say like if I'm entering an end that say that is bad。

 meaning that I'm exceeding the threshold， then I'm going to give a cost of infinite there？Now。

 when you're doing the， we're always trying to find and remember find the minimum cost solution。

 so infinity is not going to be the minimum cost solution if there's another solution。

So I'm sort of like hacking the framework to incorporate all these constraints。

 but this is part of the game here is that the states cost framework is fairly flexible and it's kind of a game to figure out how to pack various constraints into this。

Okay， so。This 238，337 is not great， and it's going to get worse。

 so how can we improve on the efficiency of exhaustive search？Any ideas？Before the fastest dollars。

然高。他早。The suggestion is to compare the current result with the previous result。 Well， I mean。

 the current approach， let's see。I mean， does do that comparison when through this minimum。

 So I am trying to find the， the。The cost theres a solution that minimizes the cost。

The Smith is doing a comparison。So， you know， any ideas， any other ideas， yeah。

Great like the lookout table。 So before you compute the future cost， you might get the。

T because youve it computed before I it， yeah so so the suggestion here is you make a lookup table and you see if you've computed the future cost for a given state and if you have。

 then don't do it again。 Yeah so that's exactly what we're going to do。

And the term for this is called it dynamic programming。And the term might find it strange。

 but it comes from actually the '50s， Richard Bellman， to pioneer Def Markov decision Pro。

 which we'll look at next week， introduce this term。

And the word dynamic means that it's sequential decision making， multiple actions over time。

 It's dynamic。 There's a temporal aspect to it。And programming just means optimization。

 You're trying to find the minimum cost solution， for example。It's not programming doesn't mean。

Your白ython O。There's many ways to talk about dynamic programming the way I'm going to introduce it。

 which is to have the minimum change from what we've already done is essentially。

 I think about just exhaustive search plus cacheing。And this is also known in some circle。

 it's called memorization。And you recall that backtracking search or exhaustive search explores some states more than once。

And dynamic programming says， well， if you're a solid estate， don't do it again。Okay。

 so here's what we're going to do。 It's going to be the dynamicyn program function。

 It's going to be identical to exhaustive search， except for I'm going to introduce。😊。

Three lines of code， I think。Okay， they're going to be marked new。

 So the first thing is that we're going to cache solutions for each state。So for each day。

 I'm going to cache the solution that we've computed so far。And then in this recurrence。

 the first thing I'm going to do is check if the state is already in the cache and if it's already in the cache and I just return it。

And。The second thing where I guess the third change is down here is after I compute the best solution。

 I'm just going to cache it。Everything else， all of this is identical。 if you don't believe it。

 you can do a diff yourself。Okay， so again， the three changes introduce the cache。

 check if there's a cache。If， if。If there's a state and a cache。And then at the end。

 put it in cache if it's not there。Okay。Actually， this design pattern is so prevalent that you can even write a Python decorator that says at memorize it。

 it would wrap your function and memorize it， but we didn't do that just to make it more transparent。

Okay， so I ran this and at the end you can see what the cache looks like， it has for every state。

 the future action。 So this is actually kind of nice because not only did you solve the problem for you know the start state。

 but you can look at all the solutions， the future solutions from every state so for one。

 remember the cost is six from two， it's five from3， you walk walk tram。From  five。

 it's just taking the tram from even from 6。It's walk， walk， walk。

 and I guess the rest of the way it's walking because otherwise you overshoot。Okay。Yeah。

attached schools the best solution。Yes， the cash store is the best solution。From each state。

Where did it make that？So the question is， where did it make the comparison to know that it's the best solution？

So if you remember， this is inherited from the exhaustive search。

 so here I'm looking at all possible successors。And。YouI'm accumulating all the solutions。

 and here I do the minimum。By key。 So here I for every solution。

 I'm taking its cost and just taking the minimum。So this is one way to write it。

 I think which is a bit more functional， you could have also written it。

 you loop over and you do the explicit like if cost is less than the best so far then update that。

 which is a bit more procedural way of doing this。 This I find a little bit more elegant。

 but it's the same thing。O。Are we good with？Demp programming。So let's try some larger problems out。

 so now I have 17。Now the number of explored states should be identical to the number of actual states here because。

I'm not exploring a state more than once。I can go up to 100 now and I can compute it for 100。

 So let's just look at the solution。 So it's walk， walk， tram， tram， tram， walk， tram， tram。Okay。

So it kind of makes sense。One thing that's actually kind of fun about these search problems is that you can define these problems。

 and then you look at the solution。 and intuitively， you can kind of see what you're supposed to do。

 right， like you kind of want to。😊，Get in position to take these trams so that you hop by powers of two。

 but you don't want to overshoot so then you have to kind of line up exactly where it is。

 but in general you can think about this as like a fairly difficult reasoning problem and you have to think through all the different possibilities So know one of the things actually as nice as that you can just solve these problems and you look at the solution and you look at it as like oh。

 that's kind of clever because it might not be as obvious is just like doing a bunch of walks and then taking the tram。

Okay， so let's discuss， when would you want to use dynamic programming。

 Hopefully I've sold the dynamicyn programs like， oh， wow。

 exponential improvement in time complexity。 that's great。😊，So not quite so fast。

 there's some caveats here。One fact about life is that memory is more precious than time。 Well。

 life meaning computer life， I guess。😊，You can always run a program for longer。

But memory doesn't grow。Right， so if。You want to run D programming and it's going to take memory total number of states。

And your computer only has so much memory in it。 And once you fill it updated。

 you just can't run dynamic programming at all。I mean， you can do things like a write to disk。

 but that gets really slow and you don't want to do that。Okay。

 so that's when you can use the news dynamic program is when the number of states is。Actually fits。

So if your number of states is like a trillion， probably not you shouldn't do dynamic programming。

So okay， now the question is that you can do diamond proaneine。

When does it actually provide speedups over exhaustive search。

And the intuition here is that it's useful when essentially there's a lot of ways to reach a given state。

If every action takes you to a new state。Then you might as well do exhaust search because essentially the cache is always you're going to have a cash miss。

So maybe I'll just draw two pictures here。So。If your situation looks like that where you have your start state。

 and then basically all your solutions look like this。They're all independent。

Then should you do dynamicyn programming here？No， right？Whereas if you have your。

Let's say you have your state and then。So typically you might see these kind of lattice patterns where at each state you can essentially。

嗯。You know， go。Like this， then you should use dynamic programming here because the total number of states is like know。

Itsly linear， but the number of paths through this is exponential。Okay。

 so there are many ways to reach a state that means the dynamic parameter is going to have leverage。

嗯。So unfortunately， a lot of problems actually do look like this later。

 we'll see that if you generating from a language model。

 essentially it kind of looks like that because every sequence is kind of unique。

We'll come back to you later。Okay， so dynamic programming is just exhaustive search plus caching。

 and remember exhaustive search， the key idea is future cost。

 which defines its a recurrence and it allows you to break down a problem into some problemsblem。

And then。You should use item programming when the number of states fits in memory and there's a lot of ways to go between states。

Yeah。Memory that， like exhaustive search was engineer to。嗯。

final forward is linear to the slide of this。Those two are。好了。いとします。So just to repeat。

 so the memory complexity of exhaustive search is essentially the length of the longer solution and the memory complexity of dynamic programming is a number of states。

And so the question， if both are you know， linear， then。You know what is the speed of advantagetage？

If they're both are linear， you probably should- which is the case， I think in these cases。

 then you should use dynamic programming because a linear memory means that dynamic programming is essentially going to be linear or maybe quadratic time。

 whereas exhaustive search can be exponential time still。Okay， so let's move on。Okay， so so far。

 we've computed the exact minimum cost solution。And the time complexity is at least the number of states。

 if you're doing dynamic programming it the number of states， if you're doing exhaust search。

 it could be exponential in that。So large number。 So what if the state contains the set of locations？

So remember， the state is the information you need to be able to assess the validity of the solution or even determine what the costs and actions are。

And sometimes you need to store the set of location if you need to remember all the places you've been so far so you don't repeat the location or something。

There's also what if it was the sequence of words generated so far？

There's a lot of sequences of words， right， so you're not going to cache all of them。So in that case。

Exact search is going to be intractable。And so now we have to move to approximate search。

And the key idea is that we're just going to hourlistically look at a subset of actions。

And as a result， we might miss something， but。Oh， w， we can't do anything about it。

 There's no guarantees here。So this is now we're entering the realm of just heuristics。

 but often these heuristics can work well in practice。

 your mileage will depend on your exact problem setting。Okay， so I'm going to look at two algorithms。

 best of N and beam search。Okay， so these are going to be fairly simple ideas here。

So the simplest idea is to just choose random actions until we reach end state。

 do this n times and take the best solution。 That's best of that。

You might have heard Be Anne somewhere and' like， oh， what is that F ya。 No， that's， that's it。Okay。

 so let's do this example here， travel problem with 10 locations。

I'm going to take this opportunity to define some forward looking terminology。So， our policy。

Is a function that maps a state to an action。It can be be termministic， it can be random。Okay。

We usually see policies in reinforcement learning， but we can actually talk about policies in search as well。

 because search is actually going to be a special case of Markov decision processes。

 which are the thing that you do in reinforcement learning。Okay， so a policy map state to action。

 So let's start at state 1。And let's define a uniform policy， which is one particular policy。

 what it does。Is。Given a state， it looks at the possible successors。

 and it just chooses one uniform layer at random。Pty simple， and so every time you call it。

 you might get a different answer。So sometimes you get walk， sometimes you get tram， hopefully。

You get roughly half and half。Okay， so that's our policy。Now we can apply a policy。

From the SAte to an end state to get a solution。 And that's what I'm going to call a rollout。 again。

 borrowing terminology from reinforcement learning。Okay。

 so rollout you start a state while we're not at the end。

 and I also have this capped so that just in case you infinite loop or something。

 I'm going to take a step。According to the policy。And I'm going to just keep track of the steps and I'm going to advance the state。

 so I took this step now state is going to be two， and so as I go through this。

 I'm going to take the tram， take the tram， take walk， walk。Okay。So now I'm at the end。

And now I have this solution which that has sampled， which is tram， tram， tram， walk， walk。

 has cost of eight。Okay， I'm going to roll out again。Now I has6。 Okay， I guess I got lucky。

 and I got the minimum cost solution。 Ro out again。 less lucky。 again 9。 Okay， so you get the idea。

 I just roll out a bunch of solutions， randomly trying actions。

 And then I'm just gonna take the best one。😊，And this is captured in this best of n function。

 which essentially just。You know， Ro does a bunch of rollouts。嗯。Just roll out， roll out， roll out。

 roll out， roll out。 Let's jump here。And then。I'm going to just choose the best solution。

 which has cost six。Okay。Okay， so the guarantee here is that as an n goes infinity。

 So the number of rollouts you do。The solution won't actually converge to the minimum cost solution。

 assumingum your policy tries has positive probability on all the actions。

So this is kind of nice because。You know， it says there is a way to get to the minimum cost solution。

 Now， the bad news is that this could take exponentially long。 So N might have to be you know。

 like centilion or something。Okay， the other nice thing about Best event is that is embarrassingly parallel。

 so if you have1 thousand machines， you can just go farm out your search to each of the thousand machines。

 they don't have to talk to each other to just explore independently。

 and at the end of the day you gather all the you see which one has found the best solution。

So its simplicity and the parallelism is actually why we actually talk about it and it's not as bad as it might seem。

Also， if the policy is informed， then it actually can be pretty reasonable right now。

 the policy is just choosing actions at random， which is probably not the best。

 but later we'll see you can define the policy to be a language model。

 which actually is pretty informed and then best event is a pretty good baseline。

So also lens to wives to。certainly。So you cut the length to make a pillows。What this。In to what。

I Carlo like you。好的。なって。So yeah， the idea of best event is parallel。From the starting state。

 you just roll out multiple trajectories to the end。You just take the bus。Okay。

 any other questions about best event？Yeah。あという。But I assume that each of the ground will take a good time is complete。

 So if we can try to ferilize。いし。So the observation is that different paths are going to be different lengths。

And are there any synchronization issues， there's no synchronization issues because a worker that's rolling out if it ends early。

 is just going on to the next one and try it again， they don't have to communicate with each other。

It's going to be actually the point might be more relevant for beam search。

 So hold on to that thought。Okay， so let's talk about beam search here。

 How many of you have seen beam search before。Okay， only is a small number of you。 Okay。

 so the idea is， is not to。You know， you know， complicated。

 So the essence of algorithm is I'm going to keep track of a set of。Beam with harsh。

 which is a number， let's say， 100 solutions。From that come from the starting state。

I'm going to consider all possible actions from each of these partial solutions。

 evaluate their costs and then keep the beam with okay so the term beam comes from well。

 the analogy is like you have you're in the driving in the dark and you have your beam and that's basically what you see So as you advance the car。

 your beam kind of shifts， but it's always narrow， exhaustive search is that I guess I don't know it daytime or you have light everywhere you can you see everything but know when you're driving in the dark you only see a little bit in front of you。

嗯。Okay， so let me， before I go into the code， I want to just maybe draw a picture to。

Give you the outlines of what this looks like。Okay， so the idea is you have your start。Sarling state。

And then you start by considering， let's say， your beam。With。Is is two。

That means you're going to only keep track of two things。If being with War one。

 that would just be the greedy algorithm。So you start， and maybe there's three actions。Okay。

So you consider these three actions and well three is greater than two， so one of them has to go。

 so maybe this has a cost of5，2 and three， you're trying to find a minimum cost path so you say sorry。

 we can of keep track of you we have a budget okay then you move on to these and you consider possible actions from here。

So now you have six different candidates to choose from。And you're going to evaluate them。

 And then you're going to choose the the best to。 Actually。

 let me just leave this there for concreteness。 and let me just exc out that。 Okay。

 so you're going to take the top two。 So maybe， maybe it's this one and this one， okay so。Okay。

 so then you cross that out and then now two survive at every step。

 and now you're going to try different actions。嗯。Maybe you have four this time。

 and then you take the top two and then cross out the ones that don't survive and so on and so forth。

So this is a schematic of what beamM search is doing， and at the end。

 you basically have two trajectories。Pas through this graph。

 which then you take the best one and you return that。Yeah。If one reaches that earlier。Okay。

 so now you re up the synchronization thing， so suppose that this is an end， this is an end state。😊。

So now， but this one hasn't ended。 So you're just going to continue marching along in the implementation I show。

 we're just going to hold on to that。We just sort of like pass this along。

 we don't expand it anymore， but we just keep it in the candidate list。Okay。

 so let's look at the code for this。 Oh， yeah。Re supplement。あの？So the question is。

 what happens when nodes loop back， or you end up in infinite cycles？

You can what we're going to do is we're going to have a max steps that allows you to essentially。

 you can start looping， but we're only allowing you to do it for 10 steps。Okay， so beam search。

I'm going to start with。This variable called candidates。

 and this is at every iteration of the algorithm， I'm going to keep track of a list of solutions and these are partial solutions that go from the SART state to the current SAP。

To some state， I guess。Okay， so I'm going to take a number of steps。Max steps forward。

 So every solution has to sort of complete in max steps。 Otherwise， we're just not going consider it。

 Okay， so I'm going to build up a new set of candidates。 So this is， suppose I'm here， so。Cada thats。

And this is going to be new candidate。So I'm at a particular point。

 I want to build the next generation， so to speak。So for each of the existing candidates。

I get the last state。And I'm going to check is at the end if it is， then I just keep it there。嗯。

Otherwise， I'm going to try all the possible successors。

And all I do is just append the current candidate steps with the successor step。O。U。

So I do this for all the candidates。 Let's see。 this does get a little bit。 Okay， so in this case。

 in the tram problem， new candidates， I have two candidates， one is walk， one is tram。

And then I look at this， I sort。The candidates buy cost。Which is going to be walk tram。

 and then I'm going to prune。Here the beam width is， I believe it was two， and I had two candidates。

 so nothing gets chopped off， so I'm going to continue。 So now I'm step step one。

 my candidates include these two。I'm going to consider new candidates。IJust gonna jump here。

 So now I have。You know， a number of four candidates。And with cost 2，3，3，4。And I'm going to sort。

 and I'm going to prune。So I only keep the two candidates with lowest cost， two and three。

And I saw it broken and ties a little bit arbitrarily here。Okay。So hopefully you get the idea。

 so I step， step step， and at each point in time， I only have two candidates。

And this one has gone to step state6， this one has gone to state 10。Okay， so at the end of the day。

My candidates， I have one with Co 6， one with cost 9。That make it to the end。And。

And then I'm just going to return the best。 So candidate0 is the best one。

So one side effective beam search is that you not only get the minimum cost path， but you get。

 or rather， you get an approximation of a minimum cost path。

 you also get an approximation of a second best and the third best up to the number of beam so you can get a little bit of sense of the alternatives here。

Okay， any questions about beam search Yeah Yeah， I guess also related to the same thing again when you complete a half that。

Talp is one。sEn or do you mean。あやぱ。So Jo say we had to one of those threads that terminates at the end set。

Now does my other I say get to right so the question is this one ended and suppose I have two more here beam with this too。

 so do I keep basically is this one of them and the others in this implementationation this would we got X out if you want yeah it doesn't really matter that much I mean you could give special cases and say。

 well， let's just put it off to the side but but typically typically you would just you can just add。

Because that allows you to automatically compare this with others。

 because just because it finished doesn't mean it's better。

 you might actually still want to throw this out。ok。Any other questions about beamMsearch？有。

The width。What's a good beam with？10。No， I mean， the honest answer is， I mean。

 it depends on your problem， your budget。I mean， I've seen anything from like 2 to 3 to like 1000。

 so it really。I guess it depends， but on the war of like 10， I think is actually reasonable。

 at least in language settings。beamam search has also related particle filtering for tracking and probabilistic models。

 and there you can get like thousands of equivalently thousands of particles。Yeah， should state to。

And if the want this a alive as an even higher cost of the end， to just stop is。

 that's not be doing any better。So I think the question is。

If you got here and you got like a cost of six， and this is already eight。

 so then you just get rid of that。So that's a good question， so if all your costs are non negative。

Then you can just stop there。And you can prune early。In general。

 you not you might have negative costs in which case you can't， because this。

 you might drop that down to four later。Yeah， so depends on your problem。Okay。

 so justs a few notes about beam search。 So like I said before， if beam is search is one。

 then this is also called greedy search。As beam width goes to infinity。

 then beam search becomes exhaustive search。 you're basically not throwing anything away。

This is a bad idea。Because not only are you doing exhaustive search。

 but you're also scaling the memory exponentially as well。Terrible idea。Beam search is deterministic。

 whereas。You know， best event is not that's storcchastic there is also I do a satochastic version called particle filtering。

 which I'm not sure we'll get to in this class， but feel free to look it up。

Beth of N incorporates a policy as a prior beam search just uses a cost directly。

So depending on if you have a good policy to sort of guide the search， you can use best event。

Otherwise， if you don't， then you can use beam search。

 particle filtering also allows you to have a policy as a prior。

TheBest event is generally simpler and more paralyizable than that beam search， so anyway。

 those are some reasons both are used pretty commonly so it depends on what you're trying to do。Okay。

 so， so a final example is I'm going to talk about a test time compute in language model。

 So this is going to be exercise in showing how much more real world setting can be。😊。

Aapptted to the search problems that we've been talking about。

 there is a bit more complexity here because you have to do some geneticgans to get know hyface language models to behave。

 but hopefully won't be too bad。 So remember a language model is in the language of multiclass classification is just a multiclass classification probabilistic classifier that takes as input a prompt and gives you a distribution of the next token。

 So you can think about the next token as the set of classes。

 there just happens to be probably 100000 classes， but mathematically。

 it's exactly the same thing that we saw last week。

Sometimes you have a verifier that takes a response。And Anna prompt， I guess。

 and returns a Boolean does this response is correct or not？

So a typical setup here is that the prompt is like a math problem。

 your language model is going to generate a solution to that math problem。

 and then you have a verifier that checks whether that solution was correct or not。

And your goal is to produce a response that passes a airifier and also is likely under the language model。

So the idea of test time compute， which I mean， has been around for a while。

 but I think it really got popularized in the public eye due to Open A01 series is instead of just sampling one answer in general。

 let's try to expandend more compute to get a better answer。

So a very simple way to do this is best event sampling。 Now， I think most people。

 when they think test time to compute， they think chain of thought and other things。

 that's absolutely one way to go。 but best event is actually a pretty。

It's a thing that people actually do a lot。 There's this paper of many papers。

 which shows that best event sampling。Actually works surprisingly well so you can use a small model。

 do best event sampling a lot。 and you can then that's competitive with a much larger model。Okay。

 so let's cast this as a search problem。OkaySo to define a search problem。

 remember we have to define what the states and actions and costs are。

 so the state is going to be a string which is a prompt that was given plus the prefix of the response that we've generated so far。

The action is going to be。Predict the next token。And the cost is going to be the negative log probability of the next token。

OkaySo because we want to minimize cost， that's going to be。

 we want that to be equivalent to maximizing imp probabilitybability。And then if there's a verifier。

 I'm going to use this hack and say， well， I get them three minus 100 costs if the verifier succeeds。

Okay， so this is going to this is an example with a very。

 very small log model that runs on my laptop。 So we're not gonna to do anything too crazy here。

 So I've taken define a language model search problem。

 The prompt is prerenency 3 plus 7 times and all this does is I'm going to use thequin 3 0。

6 billion parameter language model。 I'm going to define a tokenizer and load a model from you know I can face。

 And so we have to first define what a policy is to use best event。 you need some sort of policy。

 We're going to use a language model policy。😊，And the start state is just going to be the prompt。U。

And what the policy does is it。Generates a bunch of successors。 Okay。

 so let's look at what successors looks like。 This is inside， the problem statement。

I'm going to convert that state into a set of tokens。

This is because the language models speak in tokens， not which are integers rather than strings。

I'm going to compute the probabilities， I'm going to skip the all the details here。

 but you can read this is hopefully a connection to the previous lecture where're used to doing things like Somax I'm going to just take the top K。

You knowPro， so these are the probabilities， these are the token indices。

And then I'm going to build a successor for each of these tokens。

 so I have an action with a particular cost minus the log probe。

 and then the new state is going to be whatever， so this I think all this is is out of space。

And then if it's a complete sentence and it contains a number that I'm going to give you of one plus minus 100 bonus so once all is done。

 I have a bunch of successors， so one successor just added a space。

 this one added a space friend X square root a， and you see the cost of these。

 nothing has produced a valid sentence。I don't get the minus 100 bonus。Okay。

 so those are the successors。And if I take the costs and I convert them into probabilities。

 I can sample from。This probability distribution。And I get return to a particular successor。 Okay。

 so this is a language model policy。 It's generate to these successors， take the cost。

 compute the probabilities and sample according to probabilities， and get a particular successor。

Okay， so that's one step。Allright， so now I can do best of n and best of n。

 remember just runs the LM policy using this rollout， so I rollout once。

 so each step in the rollout is a peny a new token so I have space I have two and I have closing parentheses and because this is a well-form expression I get minus 100。

And so remember， low cost is good。 Okay， so that's one solution。

If I look at all the possible solutions， I have this， I have this。

 there often are can be duplicates because again， you're sampling independently。

 so there's some chance you're going to hit the same high probability solutions。

 but sometimes I get a5， sometimes I get a5。 okay so in this case。

 I'm going to choose the best solution， which is going to be3 plus 7 times 2。Okay。

 so I chose this solution， and that's the result of best event sampling。Okay。

 so in practice you wouldn't implement things this way。

 you would do a lot of tricks to speed up inference。

 but this is just an illustrative example of how I think we're connecting very classic search with more modern language models。

Okay so just to summarize， we've introduced search problems which formally defines the state's actions and costs where objective is to find a solution which is a sequence of actions that minimizes a total cost。

 we looked at a bunch of different algorithms if you're really particular and want exact solutions you can do exhaustive search。

 but that is generally exponential time， you can do caching which gives you dynamic programming。

 which can give you exponential fast speedups， but you have to fit the number of states into memory and then we also have best of n。

 which is like throwing NAts in parallel or beam search which is like that car beam。

 which allows you to find hopefully good solutions but both of these are heuristic and sometimes they might fail and you have to just be aware of that。

Again， the synergy between search and learning， I think， is rather interesting。

 So you can think about the costs are learned from data。

So the costs in the language model example were the language model probabilities。

 which is obviously all kind of machine learning supervised learning on large amounts of data。

 and then the idea of search where it plugs in is you're trying to find the best solution given these costs。

 and I think this is generally a pretty good recipe for building kind of robust systems in AI。

Next time we're going to revisit what happens when there are cycles this time we just said， well。

 look at a maximum number of steps and just give up。

 but there's actually going to be some nice things you can do and we'll see that on Wednesday。Okay。



![](img/28706a52a35d5b12b48dc455709b218d_3.png)