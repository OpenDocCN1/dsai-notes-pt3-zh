# 【凯尔大学】机器学习优化方法 ｜ Optimization Methods For Machine Learning And Engineering 2021 p40 P40_11.3_随机优化 -BV1C6SwBqEp7_p40-

![](img/27cec084e292179f9e352b4c0a3a60dc_0.png)

Now the last topic is stochastic optimization。In many cases。

 we don't have deterministic functions that we can just evaluate and always get there。



![](img/27cec084e292179f9e352b4c0a3a60dc_2.png)

Get the same output。

![](img/27cec084e292179f9e352b4c0a3a60dc_4.png)

Well， the problem is that oftentimes we are。Optimizing some real world process， for example。

And well we can。We can apply the same settings。But a real world process is often noisy and will not give us back the same result every time。

And there are no methods for optimizing in a setting where the evaluation comes up noisy。

And this is very handy and also in machine learning， this is now more and more used。

In machine learning， there is a popular term now Bayesian optimization。

And Bayesian optimization is the application of Gaussian processes to solve noisy functions and to optimize noisy functions。

So a picture says more than a thousand words， let's have a look at the right hand side here。Now。

Let me draw you a picture of what we initially start with。Initially we have。

A probability distribution for a function。So here we have some mean。The line in the middle。

 this is the mean。And then around that， we have like a tube of let's say。

 the 95% confidence interval。So。This here is。 This here is F of x。And this here is x。

And now if this were a noisy function， then we would assume that this is Gausian distributed。

 so then if I select， for example， this point here I make a cut。Yeah， a cut like this。

 Then what I would find is that the function。F of x。At this point it like a Gaussian distribution。

So here。This is X。Zero and let's see then this is also the x0。

And we would find a Gaussian distribution at this point。Okay。

 and if it would just be a noisy function， there would already be enough。

 so we have a mean for the function at every point and also we have a variance for the function at every point。

But now we let this express not only how noisy the function is， but we express also our own。

Un security are our own limited information， also by a probability distribution。

So now this not only expresses how little we know， it also expresses how noisy it is。

 it also expresses how little we know。And now by evaluating the function。

 we can reduce the uncertainty that we have。Now， let's say we evaluate this function。

At this  location here。And this is now this location here， we get a certain result。

 and then at this point our uncertainty is reduced now here。嗯。Now here。

 this confidence intervalver at this point would shrink down。Okay， and we can do the same。

At a couple of different vocations， so we evaluate here and we evaluate here and we evaluate here。

 and now you see how。In the original image， which is now the middle。

How the uncertainty is reduced at the places where we have evaluated the function。

And in the background， these col processes， they also use a curl function similar to what we saw for the SVM。

And the kernel function， it states how much I can trust the individual evaluations and how much each evaluation should impact its neighbors。

So if this should look like this， if I evaluate or if it should look like this if I evaluate。嗯。Okay。

 and now the trick of。Viasian optimization。Is to iteratively evaluate the function and then have a look at the remaining uncertainty to select the best point that I want to evaluate next。

And here the point with the star， the point with the star is where I want to evaluate next and this is because here I still have uncertainty so this could still contain a better solution。

 but also the mean that I expect at this point is better than。

The combination of the mean plus the remaining uncertainty is that I prefer to do the evaluation there。

So this is the expected utility of evaluating at a certain location。

 and I always here take the point of maximum utility。

 and then it is actually kind of similar to what we saw earlier with the lipsshs here and optimization。

For this expected utility， I can also combine it with cost。

 so if I know that a cost is more expensive for the evaluation at some location than at another。

 I can also integrate that back here in this expected utility。

And one area where this is used a lot is for hyperparmeter optimization in machine learning。

So imagine that you train a neural network and you train it with a certain set of hyperparameters。

 so how you parametermeterize dropout or how you parameterize the learning rate or also what do you use for stochastic gradient descent do you use？

A specialized technique like Adamom or RMSS Pro or something else。

 so there are a lot of choices that you make on top of the actual neural network architecture。

 so you have to select hyperparmeter。And the question is how do you get to the best type of parameters and you can do that by using Bayesian optimization where you try out the training of the neural network for a couple of iterations？

And then you see how fast the loss is dropping， and then you use that as an information for your Gasian process to do a search in the space of hyperparameters。

 but of course the training of a neural network is randomized。

 and therefore there is some noise to that process and therefore you need to use a stochastic optimization technique to optimize the hyperparameters of your learning method。

Okay。What we just saw， this was stochastic optimization in a more or less continuous setting。

 but there is also stochastic optimization in discrete or combinatorial settings。

And what we're looking at here is the so-called Monte Carlo research algorithm。

 and this became famous because it is at the very core of the Alphago system that was used just a few years ago to beat the world champion in the goal game。

And so Monte Carlo research， it came up。In 2006。And in the last years。

The technique was really mastered and also successfully combined with neural networks。

And in game settings that were considered really difficult before。

 Monte College research is now a state of the art technique。So。What do we see here。

 and just to give you some nomenclature， we have a tree and the tree represents a game situation。

So this could be with two players playing against each other。

 but it could also be a single player playing against the stochastic environment。

And the gaming situation is important because we can always reset。

We can reset to the start and then play out for the same situation once more and draw essentially from the same probability distribution or maybe even have a deterministic game environment。

 but we can reset the game。There are many。Tsearch algorithms。

And the main advantage of Monte Carlo research is one of the main advantages is that it only needs to have a forward simulation。

 so we don't need to do expensive backtracking steps in the tree we always reset to the very start and go from there so when we have arrived at some particular situation in our game tree when we are here。

 we never jump back just to the previous one which also would be。Difficult to or。

 tour tour tour do in it in them。In a stochastic environment。

 so this will probably mess up a lot of things。诶。And we always restart from the very top from the root of our game through。

So now we have our nodes and we call them I。And every node， it returns a reward RI。

But for this reward， we not only encounter the immediate reward that we get at this location。

 but we also count all the reward that is seen afterwards。So for example， if I'm in this。

 if I select this tree， and then the reward。It containstains also the reward from the second from two subsequent nodes。

Okay， and I can now produce statistics， I can now collect。嗯。呃。

Empirically how much the average rewardvolt was be every node， and I collected in RI。

B so this guy here， this is the empirical mean rewardt。ok。And furthermore。

 while I am playing or while I am searching in the tree。

 Im making a statistics by counting for every node。

 how often did I try it out and this is this in here？Now。

 how did people find the idea of mod college research。

 there was one big motivation going back in the past。

 the so- calledled channel shiftfting inequality， a famous and also rather old already inequality from。

Pro theory and this inequality tells us that if I have a random variable x and I make independent drawings from this random variable and the random variable has a mean mood。

Then there is an inequality that the distance between the。The mean drawing， the mean of the drawings。

 minus and the mean， so this would be like x bar， so the empirical mean minus mu， the actual mean。

 the distance between the two on the positive side larger than epsilon。

 the probability for that happening is smaller than then here this exponentialentiator。嗯。

We're not asking you about this in the exam， the entire lecture of today is excluded from the exam。

 and this is only to tell you why Monteclo research was tried out initially。

 this channel hefting inequality， it is true for any probability distribution。

So if we know there is a probability distribution with mean muu。

Then we know the channel everything bound to exist。And to be true。

 and it works for every probability distribution。And now the core idea is that we are in a stochastic setting。

And behind every branch that we can take。You know behindnd every branch。

 eye that we can take in the tree。What comes behind this branch， it has a mean reward RI。

 and the question is how can we bound this mean reward RI and the channel of5ing inequality gives us a way to bound。

For some error， Epsilom。The reward coming from that branch。

 and this is now used in Montecalo research。What Monclo research does， it has to balance。

Exploration and exploitation。So the exploration means I go into areas in the game tree where I haven't ever been before。

 or where I have sel been before where I can still discover new things。And the exploitation part。

 it means I go into areas of the search tree that have worked good in the past and why I want to refine my strategy。

So explorationation means go off， go somewhere new。

 exploitation means refine my strategy or even reap the reward by over and over playing the best solution that is known so far。

And you have to balance between the two。And in the lineage of these methods。

 this comes out of research into so called bandits。And which is very close to game theory。

 but you can think about this like a one armed bandit if you go into a casino in Las Vegas。

You have these slot machines， the one are bandits， and you have like 100 slot machines and you want to find out which slot machine is the best and then you want to play that on end。

The question is， how long do you look for the best slot machine and when do you stick to the best one you have found？

And when do you maybe change and say， well， maybe this isn't the best one after all。

🤧And on top of that。You can do this also with a limited budget。

 So if you have $100 dollars initially in coins or if you have $1000 initially in coins。

 how would that change your approach of finding the best slot machine versus playing then the best slot machine and this is the research into into socal banded settings and now。

Monticcalo research， it combines like the motivation from the channel 15 inequality with treese。O。

Now we start with some initial random baseline policy。

So there is a baseline policy and in the case of。For example， at the goal game。

 there were already existing algorithms before to playgo。

 and you could initially just pick one of them and say， well， this is my baseline policy。

And now you want to refine the baseline policy。And what you do is。

you build up the game tree and the game tree essentially is a statistics that tells you。

 if I pick this branch， what is my expected reward going into that branch？

And now in order to balance the exploration and the exploitation。

We are adding a bias to each of the branches。And the bias goes as follows。

We are estimating the value of the branch。By RI， which is the empirical reward that we have seen so far。

 the empirical mean reward。And now we add the bias and the bias。

 it depends on how often I have visited the branch。

Compared to the parent where I'm sitting at right now。

 so I'm sitting here and this is the parent and I am considering this guy and I'm considering this guy。

And now we have this。This bias， which is motivated by the channel 15ing inequality。

 and that tells me that I should go that I have a less of a positive bias for branches that were visited often。

So if I've been oftentimes in a certain branch， if this N I here to speak。

Then I don't give it an exploration bias， however， when I've been independent the parent quite often comparatively。

 then the exploration bias now increases。Okay， and there is a constancy and I can use that to switch between。

 or I can balance how exploration， happy I am in my approach。

And now what happens is for Monte Collegelo research。

 we iteratively play the game and when we are in an area of the game tree that we know。

 then we will always choose the action that has the best estimated value。

 so RI plus the exploration bias and it will always pick the one that works best。

When I am at the edge or where I have actions that I have never played before in the game tree。

 then I will randomly or with my baseline policy。Pick one of those that I haven't played so far and then do a rollout。

 the rollout means with the baseline policy play until the end of the game。And afterwards。

I will add exactly one new node to the game， so here I played I've played with my rollout。

 I've played the rollout with the best policy and now I'm adding exactly one no。

Notode for every iteration of the game and do a backt where I'm updating all of the nodes that have been encountered during this particular。

Okay， and so over and over， I repeat this and the algorithm it will balance our exploration and exploitation。

 it will quickly converge to a couple of areas in the tree that look promising， but the more I play。

 it will also include some other areas of the tree that is now starting to explore as spot。

So it balances the refinement of the good strategies and the exploration of totally new game strategies。

And this is at the very heart of Alphago and this now works also for the Go game where I can have hundreds of actions that are possible in parallel and what Alphago did on top is it applied a pruning so instead of having 200 possible plays there were then maybe only tens or a couple of dozen actions available for every branch of the game train this was helping a lot and the second was the baseline policy now was also improved and based on a neural network。

And that way， the combination of Monte Carlo research with neural networks helped in beating the world champion in the Gogi。

