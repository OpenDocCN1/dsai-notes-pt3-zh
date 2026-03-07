# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p62 P62 Recitation 11 Semi-supervised and Active Learning Apr 2 -BV1Lcnhz1E7P_p62-

So I think we'll probably get started。So today we're going to be talking about semiupervised learning some more。

 and in particular， we're going to look at these two graph based algorithms that Nina mentioned in class but didn't talk about the details of。

嗯。And I guess at the end， we'll also see just a little bit about active learning。

 one of these methods has like a nice active learning extension。

And so last time I was using the chalkboard and I found it was taking a really long time to get through material。

 so I made slides this time because we have a lot of content to cover， but I think it should be good。

😊，So we're going to start by just reviewing what Seupervised learning is and when we expect it to help us。

 and then we're going to talk about these two algorithms。

 one is called graphphmin cut and the other is called harmonic energy minimization。

 and both names sound kind of intense but the intuitive ideas behind the algorithms are really simple。

 and they get their names from the algorithms that they used to actually compute certain quantities and so the thing I want you to take from the recitation is like mostly the motivation for the algorithms and that there exist efficient implementations but it's not super important that you have the details of how to implement them。

😊，So we'll talk about graphing cut and harmonic energy minimization。

And then we'll look at an extension of harmonic energy minimization that lets you do active learning。

 so when you get a query and expert for labels for new points。😊。

And that there's time after we can have questions either about the topics now or for the homework。

Or projects。So。So just to remind you in the semiupervised framework we're still in this like packC setting where you have some data distribution D which tells you how likely you are to observe different input feature vectors and how likely different x's are and there's some true labeling function C star that we don't know and this is a map that takes as input feature vectors and spits out class labels so for a concrete example you can imagine that the data distribution is a distribution over images and then C star is a function maps and image to like an English word that describes what's in it。

And the way our learning algorithm gets its data is first。

 we draw an IID sample from the data distribution and we give that to the expert。

 and then the expert goes and it somehow knows this true labeling function。

 and so it labels each of the examples for us。😊，And then since the algorithm。

 a bunch of pairs of samples of input feature vectors together with the labels that they're assigned。

And if we stopped here， this would be just regular supervised learning right so you just have some sort of examples of inputs and outputs and you try to learn a function that sort of closely fits those。

But in semiupervised learning， we also get an additional sample of purely unlabeled data。

 so this just comes directly from the data distribution， but we never ask the expert to label it。

 and the reason why we don't ask the expert to label it is because that might be time consuming or expensive。

 so we might have access to a lot of unlabeled data。

 but we want to avoid sort of having someone sit down and label it all。And so just for notation。

 I'm going to use M sub L to denote the number of labeled examples that we have。

 M sub U to denote the number of labeled examples。M is just going to be the total number of examples。

 So typically also ML is a much smaller number than M。

 you have a lot more unlabeled data than labeled data。😊。

so then the next thing that we talked about in class was， when does unlabeled data actually help you？

if you think about it， the EnL data only tells you something about the data distribution。

 so if I see a lot of examples in one region of the space that tells me， oh。

 there's high probability here and if some other region of the space is empty that means that the data distribution has no probability there。

😊，But that's a bit unsettling because we actually care about estimating the target function C。

 which is a relationship between inputs and their labels right so this is kind of a discrepancy between what we have access to and what we'd like to estimate。

And so for semiupervised learning to be successful。

 we need for there to be some relationship between the data distribution D and the true La function C star。

😊，And so we saw a couple of different ways of making this relationship or making assumptions about that relationship in class。

 so the simplest one was this large margin separating assumption。

 so there we assume that the data had a linear separator and moreover that that linear separator had a margin gamma。

😊，And so if you think about what that means is it says that you know there's some linear separator and on all the positive examples are on one side and all the negative examples are on the other side。

 but more than that you know that there's like a band of width two gamma on either side of that linear separator so that you'll never see an example。

 never see an example there and so that means that the data distribution can't put any probability mass on that margin。

 so this gives you a relationship between D and C star。😊，And。

We also had a couple of other ones about like having multiple views and having like。

Each view be independent of the other given the class label。

But today what we're going to assume is that。😊，If you have two similar points。

 we're going to be really concrete about how we measure similarity， but for now just at a high level。

 if you have two similar points， they should have the same label。So can you see why this is a？😊。

Relationship between the data distribution and the true labeling function。

You think of how the distribution is constrained。We make this assumption。😀。😊，So。

I guess it's not so it constrains what the data distribution is allowed to do， right。

 So if the labeling function C star gives different labels to nearby points in instant space。

It must be true that data distribution doesn't put any weight there because if it did。

 then we could see examples where our assumptions is being violated。

So somehow this is a bit like a margin condition， but it's a little bit weaker and more probabilistic。

😊，But the intuitive idea here is that somehow the data distribution separates the classes from one another。

According to our， however， we're going to measure similarity。

So are there any questions until this point？No。Cool。

So both algorithms that we're going to talk about follow like exactly the same general strategy。

 and so what we're going to do is we're to try to come up with like a formal way of describing that high levell assumption that similar points should have similar labels and then once we have sort of like a formal way of talking about this。

 we can design algorithms that can compute labelings for data points that sort of。😊。

Do the best job at satisfying those assumptions so the first thing is we're going to need to fix some way of measuring similarities。

 so we suppose that we have a similarity function S that takes in a pair of input vectors and it tells you how similar they are so it's a big number if they're very similar and it's going to be a small number if they're different。

😊，嗯。And so like an example of a similarity function here would be like radio basis functions。

 so you could take the distance between the two points and then take E to the minus。

So you have to do a little bit of a trick to make it， so it's big when they're close and small。

 when they're far away。But so once we have that similarity function。

 we're going to construct a graph。😊，where the nodes of the graph are inputs X1 through XM。

 and so this contains both labeled examples and the unlabeled ones。

 so in this sort of toy picture we have two labeled examples， one positive and one negative。

 and then there's two unlabeled data points in the top right in the bottom left。

And we're going to go and we're going to add a bunch of edges to this graph and it's going to be a weighted graph and the edge between any pair of nodes is going to be weighted just by the similarity of of those two data points。

 so in this example I've used like thicker lines to note high weights and thin lines to note small weights and so the two nodes on the top there have high similarity and the two nodes on the bottom have high similarity but for any other pair of nodes they have low similarity because they have these little tiny skinny lines。

😊，And。O and then what our goal is going to be is we want to find a labeling for the unlabeled data points like so we're going to try to substitute in the labels so that the new labeling respects are like similar points have the same label intuition。

 So somehow in this example， it seems like the top unlabeled node should be a plus because it's very similar to a positive example and the bottom one should be negative because it's very similar to a negative example。

😊，嗯。But we're going to see next sort of one way of formalizing this。This kind of idea。

But there other questions about how this graph is constructed and what everything means？If you had。

So let's say your examples x1 through xM are binary feature vectors。

 so they take values plus minus or0 and 1。 What do you think a reasonable similarity function might be？

So you have two same length sequences of bits， and you want to say how similar they are。Yeah。

 that would be a good idea， right， And that corresponds to counting how many bits they agree on。

 right So so that's one example you could use if your future vectors had like binary binary inputs。

 And if you had continuous。😊，Features， then you can use something like the radio basis function。

 or you could design domain specific similarity functions。Okay。

 so graphph Me cut is the first algorithm we're going to talk about。

 and it only works for binary classification， so if you want to have more classes。

 you can come up with a similar idea， but it's not going to be computationally efficient to compute the answers。

😊，And so what we're going to do， like the really rough idea is that we want to assign labels to the unlabeled data。

😊，So that if you loop over or some over the entire data set。

 when you look at pairs of positive examples and negative examples after we've added in our own labels。

 you want to minimize the total similarity between them。

So somehow this is minimizing the amount that our assumption is violated。

 so I'm going to look at every positive example and I'm going to compare it with every negative example。

 and if all of those similarities are small then they've done a good job。

 but if one of them has a really high similarity that means that somehow I'm violating my assumptions because I have found two data points that have different labels。

 but they're very similar to one another。😊，How does that make sense？Yep。嗯。Okay。

 and so now we're going to sort of think of a way to express this idea in terms of graph properties and things that we know how to compute about graphs。

😊，So the rest of the talk is sort of like how to express this idea in terms of graph theory and then algorithms for computing this thing。

😊，So I guess。The word cut in the name Min cut comes from this idea of graph cuts。

And so graph credit is really simple， you just take the nodes in your graph。😊。

