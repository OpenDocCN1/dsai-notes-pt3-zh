# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p28 P28 Lecture 02 Decision Tree Jan 13 -BV1Lcnhz1E7P_p28-

We're going to pretty much pick up where we left off last time。And as you recall。

 where we left off last time was talking about function approximation， which is。

Sort of at the core of many， many learning tasks。And in particular。

 we talked about in black function approximation as a very generic problem。

Where we have some set of instances， x。Some unknown target function。

 the one that we really wish we could learn， but nobody tells us what that function is instead。

 they give us a set of input output pairs of its input and output。

And then we have a set of hypotheses that we， a learner， are going to consider。

And last time we pretty much zoomed in on decision trees。

 which are the special case shown in blue here。Where we considered hypotheses that were decision trees。

 and then we had an algorithm that greedily grew the decision tree to try to fit the data。So。

If you step back and think about what that algorithm is doing。

It's really performing a kind of a search。Through the space of possible hypotheses。In fact。

 the algorithm that we talked about。Performed a greedy search starting with the empty tree and deciding to add some attribute at the root of that tree。

And then。Sored the training examples based on whatever attribute it chose。

And then sorting the examples based on that attribute might， if it's lucky。

 lead to leaf nodes in the tree which were pure， which had zero entropy。And therefore。

 we could stop growing the tree at that point because all of the examples are either positive or negative examples。

 there's no need to make further distinctions。 we can just label that leaf node positive or negative。

So we talked about that。Algorithm， and so the way I like to think of it is really that algorithm is searching around in the space of possible decision trees。

From short trees to increasingly intricate trees， until it finds one that's good enough。

That fits the data。Okay。So， in fact。I think。嗯。That。

Picture of learning algorithms as search algorithms fundamentally is really important。

 So I want to take a moment。 This is。As you'll see through the semester。

 I have three or four pictures that I carry around in my head to help me think about all machine learning algorithms。

 and really this is the most fundamental picture， so I want to draw it for you。

 we can draw it together。Let's use。Fear， color。I recommend blue for。My favorite color。ok。

So what's the big picture that we're talking about when we talk about function approximation。

 So you could think of， as we just saw in that previous picture。

You think of the space of all possible hypotheses。N。

 so this is a Venn diagram of possible hypotheses。 Here's one。 It's a decision tree。

Particular decision tree， That's a。A point in this hypothesis space。Here's another one。

Different decision tree。This is the space of all possible decision trees that the learner is considering。

And of course， each of these is just some function。I'll use shorthand。

 I'll draw very tiny circles that look like dots to you。Okay， so these are all。

 this is the Venn diagram of possible functions that our learner could consider。 And， of course。

 that's determined simply by the representation that it's using in this case， decision trees， but。

In this picture that I'm drawing。I could。Use the same picture to think about any。

Function approximation learning algorithm。It's just that I expanded a couple of those nodes to so that we could see there we can think about this as decision trees when we're thinking about our particular algorithm。

Okay， now， what else do we have in our big picture， Well， we have the instances， of course， the x's。

Remember， this set of hypotheses is just the set。Of functions。Let's call them H。

That map from x to some Y。And of course， in the case of decision trees。

 the X each x is some feature vector。 Remember， windy outlook， temperature， stuff like that。

And why is a boolean variable in the case of decision trees？啊。

So we could also think of the Venn diagram of all possible。X's inputs to these functions。Okay。So。

And of course， is the relationship between these two。Right each what do those functions do。

 What do those decision treats do。They label the points in X， positive and negative。

 That's what they do。Given a decision tree。We could apply that to every point in x。

 and we get a label for every possible。Example that we're trying to classify。If its a decision tree。

 for example， to classify days according to whether somebody's going to want to play tennis or not。

Then the x's are different days corresponding to different feature vectors。

 And we could apply any one of those decision trees to any of the。Any of these points in X。

 And it would label it positive and negative。 So let me just。Do it this way。

 Let me say for every decision tree hypothesis。There's some set of examples over here that it's going to label positive。

I'll say they're the ones inside that region。And the others， it's going to， of course。

 label negative， has to label them one way or the other。 It's a function。Defined over x。Okay。

 so this is the problem setting generically that we're talking about when we talk about function approximation。

We have a set of hypotheses that define functions over x。In the case of。We were talking about before。

 where why is just a boolean variable。We could call it1 or zero or we could call it positive or negative。

诶。And then for every hypothesis。It gives us a complete labeling of all the examples in X。Okay。

 so now how do we learn？ Well， of course， somebody comes by and tells us。诶。

That's a positive example there。They might tell us there's a negative example。You may tell some more。

 here's another negative example， here's another positive example。And if they told us that。

Then we might say， well， we're happy with this tree that I happen to have。啊。

Drawn out here because it happens to label all the positive examples。Positive。

And it happens to label those two known negative examples negative， and of course。

 that's what we want， right， we're trying to grow the tree that fits the data。

But the astute observer might notice that there could be other trees。That， of course。

 labels some other set of examples positive and negative， not necessarily the same as the first tree。

But that second tree might also happen。To label the four training examples correctly。And of course。

 there will be other less fortunate trees in age。That。

Really mislabel those four training examples that were provided and hopefully our learning algorithm won output one of those。

In fact， the way we defined the decision tree growing algorithm last time。

It's guaranteed that if there is a decision now， I have to be careful。It's not guaranteed。

It's a heuristic search algorithm。嗯。Even though we talked about what a beautiful thing entropy is and what a beautiful thing mutual information or synonymously information gain is。

嗯。We didn't prove because we can't that using that heuristic to grow the tree will necessarily converge to。

Perfect tree。啊。But I guess nevertheless， the following statement is true。啊。Even with that heuristic。

I guess if we keep growing the tree until we perfectly fit the data。

And if there exists a tree that fits the data。Then I'm pretty sure we'll get to it eventually because eventually we will grow。

 as somebody pointed out， last time we'll grow the complete tree。

