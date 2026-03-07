# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p05 P5 Clustering _5_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p5-

This was all those algorithms belong to the socalled supervised learning category where you know you have some inputs and outputs and you want to learn a function between those inputs and outputs。

And today， we will start a new topic which is called unsupervised learning。

 where you just have a bunch of inputs。And you want to learn the structure。In your input vectors。And。

Clustering is。One of the most popular unupervis。Learning topic， I would say。So。

Contents for today is that we will briefly discuss。The clustering problem。

What it means to do clustering， and then we will discuss two algorithms for clustering。

 the K means clusterings and the mixture of Gaussians， so there will be two algorithms for that。

And then we will see that somehow they are special cases of more general more general。😊。

Maximal likelihood estimation methods， which is called oops expectation maximization。

 so expectation maximization will be a general framework to do maxim likelihood estimation in certain models。

 And it turns out that came means algorithm a mixture of Gaussian。

E method for mixturechi of Gaussians are special cases for this。

 And then we will see another generalization of expectation maximization。

 which is called variational methods that。You can use in certain cases where you cannot use EM。Okay。

 so we will see the details of that bottom line is。

These are some maximum likelihood estimation methods that you can use in certain cases。

 and we will discuss what are those cases when you can use these approaches。Okay， but before that。

 let's start discussing clustering。Problems。So what is cluster setting？😊。

Clustering is a process of grouping set of objects。😊，Into classes of similar objects。

 So we somehow we want to group objects。 The difficulty is that even in the training set。

 we don't have class labels。 If we have class labels， we call it classification。

 If you don't have class labels， still， you want to do grouping with。

 then we call it problem clustering。And what we want is that inside those cluster or clusters。

 we want high intra class similarity， so those objects that belong to the same cluster。

 they should be similar to each other and those objects that are in different clusters。

 they should have low similarity。う。Okay， so one problem is that oh by the way the slides are on the website so you can just download them。

 print out and make your notess there too。 So the crossing is subjective。 So for example。

 if I have these S。Cracters， and I ask them to cluster them。

 Then you can do that in many different ways。So， for example， if one possible。

Cllustering is that Simpson's family could go to in one cluster。

 school employees to go to another cluster or females and males could go to other clusters。

 So if I just say that， hey， here is the data set， cluster that。

It's not a well defined problem because the clustering defines on the similarity that you also should。

Provide to us。Okay， the other thing is that。Sometimes it's for us humans。

 it's difficult to define what we mean on similar， but when we see similar things， we recognize them。

啊。So anyhow， what we will。Do is that we assume that there' is already a simity function or a distance function。

 someone gave that to you and we will just use that in our crossstand problem。Okay。

 so let's start discussing the k means clustering problem first。Not an algorithm。 so it's a problem。

 K means clusterstering problem。Here is the problem。

 so given a set of observations or feature vectors x1 x to xn。

 so they are say all d dimensional feature vectors。😊。

And we want to partition these n observations into case sets。

Let's denote this case sets with S1 S to Sk， so they are all sets of the feature vectors。

Such that we want to minimize the video cluster sum of squares where in this expression。

 mu I is the mean of the points in the set S I。 Okay， so you have a bunch of。😊，うさそ。

So we have a bunch of points。Feachature electors。We want to group them。Into sets， so this is Slam。

Say， this is S still。I don't know S3。S 4。Such that each set will have a mean vector。 So say this is。

Move on。 This is。Me too。This is smoothly。 So each set has a mean vector。Before， and we want that。

The distance is from each instance， each object to its cluster mean。

 you calculate this square distance， and we want this sum of squared to be minimum。

So you want to minimize。Over the possible set of locations such that this co function co function is minimum。

 Does it make sense so far。Very good。 So here is my first question how difficult is this problem？😊。

So what do you think？So the problem makes sense， right？So you have N instances， x1 x to x n。

 and you want to minimize over。All locationss。So you want to find those sets S1， S2， S3 S4。

That we minimize this。Gs function。So K is fixed beforehand K is fixed beforehand， right。

 So K K is fixed， say4 in our case。 K is fixed。So my question is how difficult this problem in the number of instances end。

Okay， let's start with this， how would you solve this problem？So here is this cost function。

 You can tell me any naive algorithm that comes to your mind。 just you see this cost function。

 we want to minimize this cost function over S set locations。 How would you do that。

Nmer the exactlyly very good。 So you could just。Count list all the possible allocations。

 set allocations。And see where its minimum。 The only problem is that there is exponential of many of those in the number of n。

So， and that would mean this problem is NP had if you cannot do something better。

The question is whether we can do something better or not。嗯。

So this is just the formal setting of the problem again。

We have N instances and we want to group them to say in this case。

 three classes such that these are the class centers that isd。

 some have squared Ukrainian distances the minimum。And one algorithm， you just do brute force。

The only issue is that。啊。We need。 We have n instances， K crosses it would be。

Experialial long list of possible allocations， if we want to count a minimum。

 its NP hard problem if we cannot do something better。So it turns out。

That this problem is indeed NP had。So， even。So we just started the very basic concept Adv learning in machine learning。

 and it turns out that's already N we had。Let's go home， we cannot do anything。

So but what does NP hardd means？It just means that in your problem class。

 there are difficult instances。 It doesn't mean that your life will always be that difficult， right。

 It's just if someone is cruel to you， it can give you a difficult instance that you cannot solve。

The other thing is。 so that's what NP is。 The other thing is that quite often we don't care to find the global optimum of this solution。

 if we find a good enough fund， then we are already happy with this。

 So that's what we are going to do。 So we have this cost function。 We have to accept。😊。

There are difficult instances that we cannot solve。

