# 康奈尔大学《深度生成模型Deep Generative Models (Cornell Tech CS 6785, Spring 2023) 》中英字幕 - P17：-17-Lecture 17_ Probabilistic Reasoning.zh_en - GPT中英字幕课程资源 - BV1az421q7Vf

Our last lecture so this lecture is going to be a little bit more high level again it will not focus on any particular generative modeling family it will cover a special topic in generative modeling which I call for ballistic reasoning so just to set some context。



![](img/efacaa41a9b1dd88577527a2fdf4d965_1.png)

We saw in the first part of the course， various types of gene modeling families that each can solve。

Various subsets of these three tasks， which include generation， density estimation。

 and unsupervised representation learning。

![](img/efacaa41a9b1dd88577527a2fdf4d965_3.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_4.png)

So the models that we saw were tools for solving these very specific tasks and use cases。



![](img/efacaa41a9b1dd88577527a2fdf4d965_6.png)

In this lecture， I want to in a sense， step back and。

And show you how these tools that we have learned in the class can be used for solving various types of broader modeling problems in machine learning and how they can be instances of what I call prolistic reasoning which is a way of thinking about machine learning and a way of approaching machine learning problems okay so in other words。

 I want to。

![](img/efacaa41a9b1dd88577527a2fdf4d965_8.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_9.png)

Show you how the things， how the concepts we have learned in the class can be used to think about machine learning in a new way。

 So this is why I'm saying this lecture might be a little bit higher level and philosophical。

 but there is also going to be a lot of interesting concrete examples and important classical algorithms that I will use as running examples。



![](img/efacaa41a9b1dd88577527a2fdf4d965_11.png)

。Okay， so the outline is， first of all， I want to start with a high level。



![](img/efacaa41a9b1dd88577527a2fdf4d965_13.png)

Explanation of what I mean by this idea of probabilistic reasoning， probabilistic modeling。

 what is the probabilistic approach in machine learning。

 and then I want to draw connections between that and deep generative models and show you how deep learning and deep generative models can be tools for improving the way we can do probabilistic reasoning。



![](img/efacaa41a9b1dd88577527a2fdf4d965_15.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_16.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_17.png)

And yeah， I guess how can they improve probabilistic modeling and also probabilistic entrance。

 which are two tasks that i'm going to define and I want to conclude by mentioning probabilistic programming。

 which is a set of。

![](img/efacaa41a9b1dd88577527a2fdf4d965_19.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_20.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_21.png)

Programming frameworks that allow implementing this high levell strategy。

 this high-le approach of proistic reasoning。

![](img/efacaa41a9b1dd88577527a2fdf4d965_23.png)

So that's the plan for today for this lecture and I want to start with a motivating example so here is an example to start the class let's say that we have this problem and by the way this is this is the problem that we started with at the very very beginning of the course in the very first lecture it's this problem of trying to model the difficulty of the class and given various data about the class such as grades for example let's say you wanted to given a data set of grades you want to classify which classes are hard which classes are not。



![](img/efacaa41a9b1dd88577527a2fdf4d965_25.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_26.png)

So there's two different ways of approaching this using machine learning。



![](img/efacaa41a9b1dd88577527a2fdf4d965_28.png)

One approach， which is maybe the classical approach that one would first try is the discriminative approach where we try to build a model of the difficulty of the class given various data。

This can be something like a logistic regression or a feed forward neural net and then we parameterize this model using some sort of algorithm based on we we。



![](img/efacaa41a9b1dd88577527a2fdf4d965_30.png)

We parametermetized this model using。Any of the approaches I just mentioned。

 and then we can train it using supervised learning。

 assuming we have a data set of difficulties and various kinds of or some data set of labels and and input pairs。

 but we treat this model as a black box， we just collect data and we fit whatever black box model we have。



![](img/efacaa41a9b1dd88577527a2fdf4d965_32.png)

This is more of a。Black box， discriminative， connectionist way of thinking about it。



![](img/efacaa41a9b1dd88577527a2fdf4d965_34.png)

A different approach would be to try to build some structured generative model that contains our prior knowledge about the domain that we're trying to model and then use that to make predictions。



![](img/efacaa41a9b1dd88577527a2fdf4d965_36.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_37.png)

So we could encode some probabilistic model， some generative model of the difficulty and the data。

 and then use base rule。To form the posterior probability over difficulty and use that to make prediction。

And the second approach is the one that I want to explore in more detail in this lecture。



![](img/efacaa41a9b1dd88577527a2fdf4d965_39.png)

Here is the example of this approach that we saw oh sorry there's a question on on the zoom about the slides yes I will do that right after this lecture I will upload the remaining three I think lectures there are too missing for the slides。



![](img/efacaa41a9b1dd88577527a2fdf4d965_41.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_42.png)

Thank you for your patience there。Okay， so the an example of what I mean by a structured generative model is the following type of Bayesian network。

 so here we can we have the difficulty of the class。

 which is the thing that we want to model and we also have some other variables and the crucial thing about this model is that we use our prior knowledge about how these different types of data are are。



![](img/efacaa41a9b1dd88577527a2fdf4d965_44.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_45.png)

How they interact with each other to create a structured model that incorporates their prior knowledge。

 So， for example， we know that if we have the grade and then if we have the SAT data of the of the。

Of the student they're not directly correlated they're indirectly correlated by some kind of latent factor which may be the intelligence variable and if we have another variable which is the letter or how much praise the student got then this does not directly correlate to the difficulty of the class it correlates with it indirectly via this creative variable right so we can encode all of these structure we can encode all of these structural information has a Bay as the graph presenting a Bayian network and then this can be either fit to data or some of these parametersm rules can be chosen from prior knowledge there's various ways of combining prior knowledge and data and in the end it gives a probabilistic model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_47.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_48.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_49.png)

So first of all， it also tells the story of how the data was generated right so initially the class had some difficulty a student is takinging a class。

 the class has some level of difficulty based on that they get a grade and then based on the grade they get a letter right so this tells a story。

😊。

![](img/efacaa41a9b1dd88577527a2fdf4d965_51.png)

And it also defines a probability distribution that factorizes in some form here。

 it factorizes according to the Bayesian network， and so for example。

 if we have any two variables here or any subset of these variables and say we have the letter。

 we have the grade， we have the SAT， then using the theory of Bayian neural of Bayesian networks。

 we can predict， for example， the difficulty from these other variables by leveraging the structure of the model and using the correct formula for this probability out the model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_53.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_54.png)

So I guess my point here is that this is a more expressive approach than or this is maybe a more complicated。

 a more sophisticated approach than just fitting a black box model that predicts difficulty given the other variables。

 it involves more work， but the advantage is that by thinking about the data that we're trying to model using using structured probabilities。

 we can have an alternative approach which can have benefits over the black box approach because it allows us to specify prior knowledge。

 and if this prior knowledge is correct， for example。

 if the dependencies in this neural network are correct。

 then we might be able to do much better using less data because we are able to specify the correct inductive biases into the model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_56.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_57.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_58.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_59.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_60.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_61.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_62.png)

Right， so this is an example of the probabilistic approach to solving a machine learning model based on our prior knowledge and via the specification of various inductive biases that we might have。



![](img/efacaa41a9b1dd88577527a2fdf4d965_64.png)

So more generally， this approach is an example of or this example is a special case of a more general approach to solving probabilistic models。

 sorry to solving problems in machine learning using probabilistic models which you can call it different ways you can call it probabilistic modeling。

 you can call it probabilistic reasoning， it's an example of a particular principled way of thinking about how to approach a machine learning problem。



![](img/efacaa41a9b1dd88577527a2fdf4d965_66.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_67.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_68.png)

And there is this。There's this Bayesian statistician whose last name was B who created a graph or a flowchar that describes precisely the reasoning framework that I have just described。

 this is called boxes Huux's loop and the idea of B loop is that whenever you approach any kind of machine learning problem that you're interested in you should try to follow this multistep approach that I just sketched so in particular。

 let's say that we have to solve we want to solve some kind of problem。



![](img/efacaa41a9b1dd88577527a2fdf4d965_70.png)

We start by building a model， so we formulate a model based on our knowledge of the problem structure。

Then depending on the model family that we have defined， we choose some。

Inference and learning algorithms for this problem and often these are general techniques which can apply to most models that we have defined。

 so these techniques can be something like the racialial inference or Markerov chain Monte Carlo。



![](img/efacaa41a9b1dd88577527a2fdf4d965_72.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_73.png)

We apply these methods， we examine the results of these of these。



![](img/efacaa41a9b1dd88577527a2fdf4d965_75.png)

Of these algorithms， we examine the results of learning and doing inference。

 so when I say we infer hidden quantities。We can infer the parameters of the model or we can form posterior distribution or the parameters of the model。

 or we can form a distribution over the latent variables that we're interested in and then we run them against against some heldout data set。

 we observe the performance on the data so we can criticize the model。

 we compare it against the data， and then if we're happy with the results。

 we stop the process here and if not we keep going and iterating on the model that we're trying to build here so maybe we try to fit one probabilistic model it doesn't work well。

 it is missing some it doesn't capture certain things that we think it should capture then we can add we can update the model we can add an extra set of variables maybe or add an extra set of priors。

 then again we run training for example， with the data network from the previous。



![](img/efacaa41a9b1dd88577527a2fdf4d965_77.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_78.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_79.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_80.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_81.png)

Maybe we realize that we're missing some importantly variable or maybe we realize that some connection。

 some sort of edges is wrong， then we can edit these things and we can go back and forth in a loop and iterate on our probabilistic model until we have something that we're happy with。



![](img/efacaa41a9b1dd88577527a2fdf4d965_83.png)

Okay， so。This is B loop let's look at another example of boxes loop， which is more。

Realistic or which is going to be introducing a very common algorithm called LDA or latent differentially allocation。



![](img/efacaa41a9b1dd88577527a2fdf4d965_85.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_86.png)

In this example， let's say that our ask or yeah let's say the task that we're interested in is to understand the topics in a set of documents。

 so for example here on this slide I have a paper on computational genomics and if you look at the at the the words you can see that the words come from a set of。

Categories， so here I have some set of words that are in。In pink which refer to biology。

 there's organism survive life， there's a set of words that which are in yellow， these are genes。

 genomes， sequence， genetic so the words in yellow have to do with genetics and then there's a set of words in blue which are things like computer predictions。

 computer analysis， numbers， so these are the words that have to do with computers and computation and what this shows is that in this document there are three sets of topics there's a genetics topic。

 a biology topic and a computer topic and its words represent a mixture of words coming from these topics。



![](img/efacaa41a9b1dd88577527a2fdf4d965_88.png)

And a very common task in natural language processing is to， given a set of documents。

 we want to learn automatically what is this document about。

 what are the main topics which are being covered in a certain document。This is a very。

 very common task。

![](img/efacaa41a9b1dd88577527a2fdf4d965_90.png)

Again it's called topic modeling let me give you an example here of what I mean by topic modeling when we say topic modeling it means that given a corpus of documents we want to identify a common set of topics which are shared。

Across all these documents， so here I have four topics yellow is genetics pink is life blue is computer and there's another green one which was not found in。

🎼Which is not found in this example， but it could be found in other documents。

 This one sounds like neuroscience， brain， neuron nerve。

 and the goal of topic modeling is to assign to each document within a corpus a。Instead of。topic嗯。嗯。

Instead of topic proportions。So how much of how many words or how present is the computer topic。

 how present is the biology topic， so we assign a percentage。

That indicates the importance of each topic， and then we assign each word in the document to one of these topics。

Okay， so in this case， you can see that in this document。

 it is mostly yellow and pink with a little bit of blue， so it's mostly about genes and biology and。

A little bit about computers。 and we can figure this out by identifying the latent。

The latent topic of each word and then counting how many words of each topic there are。So again。

 this is the task we want to find， we want to。We want to automatically from data learn three things。

 we want to learn these topics， we want to learn the topic proportions and the assignments of words to different topics。

This is what we want to learn， but in our data set we don't have any of this。



![](img/efacaa41a9b1dd88577527a2fdf4d965_92.png)

We only have the raw text documents。The task of topic modeling is to fill in these topics we basically want to choose what the topics are。

 we want to populate these with words。And then for each document， we want to draw this histogram。

Of topic proportions and then assign words to different topics here。

So this is the task of topic modeling。Any questions about this task？

This is something that you find a lot in NLP。And the reason I'm introducing this task is。

In part to give you another example of how this herbabilistic way of thinking about machine learning problems can be applied here。

Right， so here my task is to somehow from data infer all of these unobserved quantities。

The problem seems very， very underspecified， how can I possibly do that？Well。

 one way in which we can do this is by specifying a structured probabilistic model。

 so we apply boxes loop， we specify a model where all these things that I have to。



![](img/efacaa41a9b1dd88577527a2fdf4d965_94.png)

Discover are latent variables， but they're connected together by some kind of precise structured pbabilistic form。

 and then I try to infer them from data。

![](img/efacaa41a9b1dd88577527a2fdf4d965_96.png)

Using various techniques that we have seen in the class。Right， so。The problem is underspecified。

 but I can add。Structure I can make this problem well specified or much better specified by。

Applying boxes loop， defining a model which incorporates my understanding about how these different things。



![](img/efacaa41a9b1dd88577527a2fdf4d965_98.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_99.png)

Re how these different latent quantities are constrained and how they relate to each other and how how constrained they are and then I can solve this problem and uncover these。



![](img/efacaa41a9b1dd88577527a2fdf4d965_101.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_102.png)

嗯。Quantities that I'm interested in as latent variables in my model。And that's going to be， again。

 another example of realistic reasoning in boxes loop。



![](img/efacaa41a9b1dd88577527a2fdf4d965_104.png)

So the particular model that is widely used for this task is called latent duration racial allocation this is a model that was proposed by David Bligh and in around 2003 I think has something like 50。

000 citations。This is one of the most famous models。

 one of the most famous probabilistic models in machine learning。

And it is a again a probabilistic latent variable model which has mostly unobserved variables。

 so here this， don't worry if you don't understand the way this graph works I'll explain in a second。

 but this is something called plate notation and essentially each circle here corresponds to a set of variables and the only observed variables is this。



![](img/efacaa41a9b1dd88577527a2fdf4d965_106.png)

Is this one， it's this shaded circle and everything else， for example。

 the topics that we want to discover， the document proportions。

 the assignment of words to document these are all unobserved latent variables that we're going to try to learn and the model will specify how the latent variables relate to each other and to the observed variables。



![](img/efacaa41a9b1dd88577527a2fdf4d965_108.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_109.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_110.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_111.png)

🤧In particular， the model defines a probability distribution via the following story or via the following generative process。

 by the way， this is a generative model right because it it doesn't represent a distribution of y given x it represents a distribution of all of the data that we have given some late variables so this model will tell the following story for how the data is generated and。

Then when I learn the model， I will try to infer the most likely parameters of the story which could have generated the data the story goes as follows。

Let's say I have a corpus of documents。And there are some topics。

 so first I have to draw what I have to create these topics。

 so somewhere in in the space of latent events there is a generation event of the word distribution。

So for each topic K for each topic K and by the way K is one thing that I do have to specify。

 so number the number of topics I have to specify， but for each topic I draw at random some distribution over words。

And by the way， there's the racial， so beta is a vector of。Probabilities over words， so it's say。

It's a categorical distribution over a vocabulary so the beta tells us the probability that this word occurs in this topic and yeah this is a categorical distribution and it's drawn from a dely don't worry if you don't know if you don't know what itly just think of a dely as a distribution over categorical distributions that's really what it is distribution over categorical distributions so we draw a。



![](img/efacaa41a9b1dd88577527a2fdf4d965_113.png)

cateategorical distribution beta for each topic and now we generate the documents for each document。

 I generate some set of topic proportions， which is another categorical distribution it's a it's a percentage that tells me。

What's the percentage of words that will come from？



![](img/efacaa41a9b1dd88577527a2fdf4d965_115.png)

Science， what percentage of words will come from the computer topic。

 what percentage will be genetics， etter。So for each document I draw proportions and now I can draw the words for each word and again I have to specify that there is going to be n words in this document well in fact we know there are n words because the number of words is observed so for each word I draw a topic。

Index。From this set of topic proportions， right， so each word will come from。

From a topic and the distribution of topic is given by theta。

 so therefore to generate that word topic， I sample the index of the topic from theta and then I sample the actual word from the。

From the word distribution for the topic that was just sampled。



![](img/efacaa41a9b1dd88577527a2fdf4d965_117.png)

Right， so at stage one。For this particular word， let's say I draw the topic ID biology。

 so now at step two I will draw at random a word that's relevant to biology。

Okay and that's the generative story for how the for how the words have been generated and in particular it defines a probabilistic model it defines latent variable model。

 what it says is that given that I have a word， so this word has been sampled from a from an index。



![](img/efacaa41a9b1dd88577527a2fdf4d965_119.png)

From a topic index and from a topic distribution the topic index was this was sampled from the topic proportions and then the topic proportions themselves and the vocabulary for each topic were sampled from a the prior so this defines a probability distribution by defining this story I have defined the functional form for each of these。

For each of these。Affectors。And now the cool thing is that given that I have this ballistic model with。

A set of。With with with with a set of variables and a functional form for each variable。

 I can now apply all of the techniques from late the variable inference that we have seen in order to。

Infer these these parameters this approach is kind of similar to a mixture of Gaussians or Gaussian mixture models let's say in Gaussian mixture models。

 I have some I want to learn some clusters， but I don't know what the clusters are。

 so I just assume that the。Alllocs of。Words to the cluster memberships are latent variables。

 the positions of the clusters are latent variables and then I do something like EM to optimize over these latent variables to figure out what the latent clusters are right that's what we do with Gaussian mixture models here you can think of this as a more sophisticated way of the same idea where all the quantities that I'm interested in are latent variables but I specify how they're related to each other and then I find their most likely assignments that could have generated the data。



![](img/efacaa41a9b1dd88577527a2fdf4d965_121.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_122.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_123.png)

So this is latent thely allocation。Now how do I actually find these latent variables well we have seen in this class a lot of techniques for this in practice what you might want to do is either apply a variation inference which means that we take this latent variable model and now this is just the same type of latent variable model that we've worked with in earlier lectures we have an observed X which are the words an then late variable Z are all these topic memberships that weve been interested in so we can form the elbow and we can learn an approximate posterior of of Q of Z given。

X where now the leading variables are the topic memberships and the word allocations。

Then we fit that we fit this using variational inference and this gives us an answer now the particular details of this are of course a little bit tricky。

 but this is the high level approach or another approach that we could do here is to consider the true posterior as being。



![](img/efacaa41a9b1dd88577527a2fdf4d965_125.png)

I guess we can apply in cC if you view the。If you view the。

This is a latent variable model where our I sort view this as an energy based model where these are the latent variables that you。

Where these are the variables that we want to model。

 then you can apply the same techniques that we have seen in the context of energy based models to draw samples from this distribution。

Until we have something that we are that we are。So we could basically start and Markov and an MCmC chain over these latent variables and run it for a very long time and this will give us。

Samples from the true poststerior。Which we can then use as an answer to any probabilistic query that we might have。

So my point here is that。Yeah。I guess the the reason why I introduced latent the racial allocation is one this is an important algorithm and two again it is an instance of this。

Approach where we solve a machine learning problem by specifying a model where the things that we're interested in are latent quantities。

 and then we use the tools that we have learned in the class to solve this model。

 infer these latent quantities and get the answer that we want。Right， so。



![](img/efacaa41a9b1dd88577527a2fdf4d965_127.png)

Yeah， and then I guess I'll just end this section on。



![](img/efacaa41a9b1dd88577527a2fdf4d965_129.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_130.png)

Trying to explain what probabilistic reasoning is with kind of this last slide where I want to summarize what I said earlier by identify by I guess again breaking out the。



![](img/efacaa41a9b1dd88577527a2fdf4d965_132.png)

The task of prolistic reasoning into three steps， which can be seen as representation inference and learning。

So if you want to solve any task using。The framework of probabilistic reasoning。

There are three problems that we will have to solve。 One is representation。 How do we represent the。

The data that we're working with as coming from a probabilistic model， how do we define that model。

 then given that we have defined the model， how do we do some sort of inference in that model。

 how do we ask the model for questions about missing quantities and then yeah how do we also learn the model from data if we're not Bayesian then we want to do some kind of parameter learning here。

So these are three problems that you usually find in ababilistic model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_134.png)

不。So。This was。And。

![](img/efacaa41a9b1dd88577527a2fdf4d965_136.png)

An introduction。 and an example of。What is probabilistic modeling， what that case？



![](img/efacaa41a9b1dd88577527a2fdf4d965_138.png)

Next， I want to talk about some connections between degenerative model and this probabilistic modeling approach that we just。



![](img/efacaa41a9b1dd88577527a2fdf4d965_140.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_141.png)

Mentioned。

![](img/efacaa41a9b1dd88577527a2fdf4d965_143.png)

Okay， so。Oh。The idea of。Yeah。Proistic reasoning and all these neogenerative modeling techniques that we learned in class are very closely connected。



![](img/efacaa41a9b1dd88577527a2fdf4d965_145.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_146.png)

First。Well， the first way in which they're connected is that they are in a an instance of the probabilistic approach right when we try to define models like latent variable models variational runrs or regress models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_148.png)

We started by first defining a probability over the data， then we introduced the learning algorithms。



![](img/efacaa41a9b1dd88577527a2fdf4d965_150.png)

And， and then we。Applily these algorithms and we observed samples from the model。

 we evaluated these samples using various techniques。

 either we either look at the log likelihood of the model or we looked at the quality of the samples directly。

 but these three steps can be seen as an instances of boxes define a model。

Run inference and observe the results and keep and then if we're not if we're not happy with the samples or the performance of the model for some reason we go back and we iterate we propose a different model so in a sense。

In this class when we。Looked at our first set of geneative modeling families。

 we did an instance of boxes loop， and in that sense。

 deep generative models are a special case of this more general approach to。Solving machine learning。

Even general models are an instance of the prolistic approach。

Givegenerative models can also be used to improve。Teciques from probabilistic modeling。In fact。

 we can use deep geneative models as building blocks within the kinds ofbilistic models that I just showed you as an example。

 we can compose them with Bayesian networks or we can compose them with latent variable models like latent the allocation to make these models stronger that's one example that I want to give you next。



![](img/efacaa41a9b1dd88577527a2fdf4d965_152.png)

And we can also use deep neural networks to and ideas from deepgen models。

 we can use them to improve and scale learning and inference in classical methods from probabilistic reasoning so that's another example that I want to give you in the next section of the class。



![](img/efacaa41a9b1dd88577527a2fdf4d965_154.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_155.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_156.png)

So as an example of how we might compose ideas from probabilistic methods and deep genre models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_158.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_159.png)

Let's look at this example of what I call deep Gaussian mixture models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_161.png)

Let's say that we're interested in modeling the following data set。So this is。

 I'm going to call this the star data set。You can see that this is a data set that is clearly a mixture of five components。

 but these components aren't just。

![](img/efacaa41a9b1dd88577527a2fdf4d965_163.png)

Gaausian clusters like there normally are when we do Gaussian mixture models。

 they have this moon shape， so it kind of looks like a like a starfish or let's say a star I'm going to call this the star data set。



![](img/efacaa41a9b1dd88577527a2fdf4d965_165.png)

And we can try to fit different types of generative models to this data set。



![](img/efacaa41a9b1dd88577527a2fdf4d965_167.png)

One type of model that we all know and that we could fit is a Gaussian mixture model。

But the problem with so again， I'm a gas mixture model I have。



![](img/efacaa41a9b1dd88577527a2fdf4d965_169.png)

Lnt variables which are categorical and the data within each cluster x given its cluster Z is coming from a Gaussian distribution。

The problem with this model when we applied on the star data set is that the actual data is not gaption。

The branches of the star have this curved shape so' you can't fit them well with a Gaussian。

So in the end， what you might end up doing is to fit a small is to fit several Gaussians within each branch to capture its。

Good。Twisting shape。So here there's two of them， there's two of them that I fit to this branch。

 etctera。

![](img/efacaa41a9b1dd88577527a2fdf4d965_171.png)

嗯。So as you can see， gastro mixture from models aren't a good fit for。The data is too complex。

 data is actually non Gaussian， it's not a mixture of Gaussian。

 it's a mixture of something more complicated so it doesn't this is not a great fit。

Something else that we could do is we could try to fit a variational。How to encoder to this data。



![](img/efacaa41a9b1dd88577527a2fdf4d965_173.png)

Here。

![](img/efacaa41a9b1dd88577527a2fdf4d965_175.png)

I guess in a variation autoenr， we don't assume。well， we in a virtual Outr。

 we have a lot of flexibility so we can start with some Gaussian Z。

 but then the Gaussian Z can get rempped in some very complicated way and if I draw samples from the variation autoenr。

 it can look highly non Gaussian。But in practice， if I do this。

It still doesn't give me a great answer。 It doesn't give me great。Results， so this is。

I guess and figure see， I have the results of。嗯。Fitting a V and what you see here in purple are the density regions of the V。

 so let's say you fit the V and then you draw samples from it。

 then the purple points are the heat map of where the samples are。

And you can see that these purple regions， they do in general overlap with the branches of the star。

 but there's also regions like here and here where they go beyond where the star is。

 it doesn't perfectly fit the shape， it's still too diffuse。

So IVE is not a perfect model for this data set， is also not a perfect model for this data set。

The best results we get come from combining these different sets of models。

 they come from combining gassian mixture models and variational。



![](img/efacaa41a9b1dd88577527a2fdf4d965_177.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_178.png)

Auttoenrs。And the model that we use here is that we have a mixture of five Gaussians but。

In each well sorry not if forget we have a mixture of five Vs essentially。

 so we still specify a fixed number of clusters， so these are the red orange。

 green and all the other clusters， but then within each cluster we don't fit a Gaussian fit we fit a variational autoencor。

And this makes much more sense right I clearly have a mixture of five components。

 I can see that from looking at the data then。Why do I not just fit a mixture of five components？

But the shape of each component is very strange it's hard for me to specify so then instead of specifying it as a Gaussian which is wrong。

 let me specified as this kind of。Flexible approximator， which is the D。Okay。

 so specifically the way the GMM be。Method works is that there is still a latent variable Z like in the the Gausian mixture model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_180.png)

Which specifies to which cluster does each point map but then。With。Oh yeah。

 and then there is a latent variable U。Which is sampled from a Gaussian。

That's specified by the indicator variable ZI so this part here， this is just a standard Gaussian。

 a standard mixture of Gaussian but。Now the output of the model will not be U itself。

 now we're going to learn we're going to fit a VE on each UI。

 so the X will then be a reparmetized version of U。Right， so this part here is the。

Gussian mixture model and this part here is the V。And the way that the data works is that we the way this model works is that we first。

Take samples from a Gaussian mixture model， and then we pass the each component into a VE。

 So the samples of the Gaussian mixture model， they correspond to the latent space of the VE。

 or in other words， you could also think of。This as being a VAE with a Gaian mixture prior。

There could also be a different way of looking at it。Right。

 so when I fit Pve with a Gaussian mixture prior， now I can get much better result。

 I can get much better results。And I can fit the star。Um。

So this is an example of how classical probabilistic models and。



![](img/efacaa41a9b1dd88577527a2fdf4d965_182.png)

Deep gene models can be composed。

![](img/efacaa41a9b1dd88577527a2fdf4d965_184.png)

Again， this is the model that we have just defined one question though， is how do we fit this model？



![](img/efacaa41a9b1dd88577527a2fdf4d965_186.png)

Right， so I have specified something which seems like a sensible。



![](img/efacaa41a9b1dd88577527a2fdf4d965_188.png)

Process for generating the data， I still have to define algorithms for learning this model。

And the way that we could do this is again， by using a lot of the tools that we have seen in the class。

 for example， variational inference。So this is our model note that if we know the ZI。Then we can fit。

 so first of all， we have two sets of latent variables z and U。

And the observation here is that if we know Z， then we can fit U。

Using variational inference like in the right if I have ZI， then I know。

I know the membership of each point。To a cluster and then within each cluster it's just a E so once the memberships of points to clusters are fixed。

 I can just fit the variational out on coder to that data。



![](img/efacaa41a9b1dd88577527a2fdf4d965_190.png)

And conversely， if I know。The UI。Then I can fit the Z like in like in a GMM。

 if I can do posterior inference in the DE and get the UI， then the UI are just。

The points over which I have a mixture of Gaussians and I can fit the Z。

I can assign memberships of points to latent Gaussian mixtures using EM so I can solve UI。

 I can find UI for a fixed。So yeah， for proof fix。

![](img/efacaa41a9b1dd88577527a2fdf4d965_192.png)

For a fixed UI I can fit the Z like in a Gaussian extra model and so the way that these models can can be fit is by。

Is by this iterative process， which is。Also， a little bit like the EM process， where we。

Clap one set of variables， fit the other， clamp that。

 fit the first set of variables and we keep going back and forth this could be one way of solving this this model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_194.png)

Yes。Any questions on deep mix for models？

![](img/efacaa41a9b1dd88577527a2fdf4d965_196.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_197.png)

Yeah。Anyway， I personally think this is a cool example of how。

Of how we can do more of how we can have more powerful model by combining。



![](img/efacaa41a9b1dd88577527a2fdf4d965_199.png)

Ideas from degenerative models and ideas from classical probabilistic models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_201.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_202.png)

So here's one more example， which I think is fun， which i'll keep really short let's say that you have a data set of。

Let's say you have a data set of video frames， so here this is a scientific data set that was studied in the same taper where researchers have been filming a mouse moving in a cage and they want to understand something about the behavior of that mouse。



![](img/efacaa41a9b1dd88577527a2fdf4d965_204.png)

If we could somehow futureurize what the mouse is doing。

 let's say if we could know that right now the mouse is sleeping or right now the mouse is running or and now the mouse is eating。

 if I could have a discrete state， then I could build a model over these discrete futureized states to。

 for example。

![](img/efacaa41a9b1dd88577527a2fdf4d965_206.png)

Learn the probability that the mouse switches from one activity to the other or that you know if there's some external factors that are coming in。

 how do these influence the probability of what the mouse will do next。

 those are the kinds of things I could study if I had the clear state definition but here I don't I just have video frames。

 but I still want to learn a model of the behavior of the mouse given given these raw video frames。



![](img/efacaa41a9b1dd88577527a2fdf4d965_208.png)

So。Classical proistic models are not really good when they're not that effective when presented with raw unstructured data like images like like pixels or video frames。

 but degenrative models are。So how about we combine them again here？



![](img/efacaa41a9b1dd88577527a2fdf4d965_210.png)

Given each frame。Given each frame。I can。😊，Try to learn a latent representation using unsupervised techniques。

 for example， using a variational outenr right like I guess one approach I could do here is I could train a variational outenr for each frame and then infer its latent state and a latent state。



![](img/efacaa41a9b1dd88577527a2fdf4d965_212.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_213.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_214.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_215.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_216.png)

ho group together different states of the mouse right if if these videos if these video frames are sufficiently different from when the mouse is sleeping or running。

 then it should cluster the state of the mouse into different parts of the input space。



![](img/efacaa41a9b1dd88577527a2fdf4d965_218.png)

Sorry different parts of the latent variable space and so all the frames where the mouse is sleeping should be clustered together in latent space all the frames where it's running should be clustered in a different part of latent space。

 and so by applying unsupervised learning we can。

![](img/efacaa41a9b1dd88577527a2fdf4d965_220.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_221.png)

We can discover these states automatically and that's the hope。Of this step。

 so we can assume that each Xt has some latent representation UT that is given to us。



![](img/efacaa41a9b1dd88577527a2fdf4d965_223.png)

By some kind of parameterized Gaussian。Model。Bake interview。

🤧But then I said that I also want to learn something about the behavior of the mouse。

 so I also want to learn I guess there's there's a lot of structure now these images are not completely disconnected from each other they're clearly they're consecutive consecutive frames in a video so I can clearly。



![](img/efacaa41a9b1dd88577527a2fdf4d965_225.png)

There's clearly some additional structure they I can use here。And this particular。



![](img/efacaa41a9b1dd88577527a2fdf4d965_227.png)

Structure is the fact that similar frames should have similar representations。

And so now that I have a representation of each trained in latent space。



![](img/efacaa41a9b1dd88577527a2fdf4d965_229.png)

I can also model the evolution of this。Lnt state using。

Classical techniques in probabilistic modeling。

![](img/efacaa41a9b1dd88577527a2fdf4d965_231.png)

For example， I can assume a linear dynamics model over these latent states。

 so this is something that is also called a columnman filter。Or in other words。

 what this assumes is that the dynamics are evolving smoothly。

 so the frames are changing smoothly and the dynamics are evolving smoothly according to some process。



![](img/efacaa41a9b1dd88577527a2fdf4d965_233.png)

Right， and furthermore， given that I ultimately want to discover and model latent discrete states that describe what the mouse is doing。



![](img/efacaa41a9b1dd88577527a2fdf4d965_235.png)

I can then add an extra discrete state。To the to the latent。

Representations right so essentially this is the same model as I had in my earlier slide except that it has a temporal component。

UFT right so here in the third step I have I take these use and then I perform Gaussian I effectively learn what looks like a Gaussian mixture model over them。

And in the end， if I look at these discrete dynamics， if I look at these discrete states。

 I get a set of interpretable variables that can be used to cluster states where the mouth where the mouse is for example。

 running right so there are some states here where。



![](img/efacaa41a9b1dd88577527a2fdf4d965_237.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_238.png)

So this， for example， in this picture， all of the yellow。诶。Frains are ones where the mouse goes from。

 I guess。It's it states where the mouse starts running essentially。

 so by using this combination of classical methods that call them the filtering in。



![](img/efacaa41a9b1dd88577527a2fdf4d965_240.png)

Cluing， combined with ease。These researchers were able to。



![](img/efacaa41a9b1dd88577527a2fdf4d965_242.png)

Discover some interesting facts about this data set， about this interesting scientific data set。

So this was my second example of how degenerative models and classical models in probabilistic reasoning can be combined together。



![](img/efacaa41a9b1dd88577527a2fdf4d965_244.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_245.png)

嗯。So both of these examples were ways of improving modeling using neural networks I also want to talk about how we can improve inference。

 how we can improve our ability to learn models using neuralNes。



![](img/efacaa41a9b1dd88577527a2fdf4d965_247.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_248.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_249.png)

And here again， I have two examples。So the first example that I have is。Is is。

So this involves latent variable models。Let's see that we have some sort of latent variable model。

Let's say I have some late variable Z and some。X condition on Z。For example。

 this could be a Gaussian mixture model like you see here。

 or this could be a more complex mixture model where let's say the data is non Gaussian。

 but it comes from some other distribution。How do we normally？Learn session model。

So the classical approach and this is what people did for many decades up until the。



![](img/efacaa41a9b1dd88577527a2fdf4d965_251.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_252.png)

To 2010s。The classical approach would have been to apply techniques like em expectation maximization or mean field variational inference。

 which is another classical technique， so these can be seen as ways of running。



![](img/efacaa41a9b1dd88577527a2fdf4d965_254.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_255.png)

As ways of running。诶。These can be both genes as special cases of variational interest。



![](img/efacaa41a9b1dd88577527a2fdf4d965_257.png)

And these techniques work by inspecting the structure of the model P。



![](img/efacaa41a9b1dd88577527a2fdf4d965_259.png)

And they use it to form a particular form for Q of Z given x that has a particular structure which is derived from from our。



![](img/efacaa41a9b1dd88577527a2fdf4d965_261.png)

Formulas for P of Z given x and then we perform a certain optimization process for deriving updates for Q for example expectation maximization is an example of this classical approach it only works if we know the trueopester of P of Z given x which which is something we happen to know when we have a mixture of Gaussians。

 but when we have a more complicated distribution we might not know that。



![](img/efacaa41a9b1dd88577527a2fdf4d965_263.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_264.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_265.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_266.png)

So these classical approaches would only work for certain types of variabless for certain types of models where Pmz given x is no and so again this has a lot of limitations these classical approaches and variation infants only work for certain models and even if we could apply these techniques they require a lot of。



![](img/efacaa41a9b1dd88577527a2fdf4d965_268.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_269.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_270.png)

Manual work for。Diving the updates for the approximate posterior queue， let's say， for example。

 that you want to run EM。

![](img/efacaa41a9b1dd88577527a2fdf4d965_272.png)

When you used。I guess you've probably seen EM for gas mixture models in an introductory machine learning class。

 but in order to get those formulas for EM。To derive them correctly requires about a page of math for and that's for the simplest version of Gasstrian mixture models if you have a slightly more complicated version of Gasstrian mixture models where let's say you have a Bayesian prior on the parameters。



![](img/efacaa41a9b1dd88577527a2fdf4d965_274.png)

Of the Gaussians and you help say。

![](img/efacaa41a9b1dd88577527a2fdf4d965_276.png)

A the prior on your categorical， then it takes 10 pages of math to derive the EM updates。

 so it's actually very complicated to perform inference in many types of machine learning models。

 even ones that are reasonably simple。

![](img/efacaa41a9b1dd88577527a2fdf4d965_278.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_279.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_280.png)

嗯。

![](img/efacaa41a9b1dd88577527a2fdf4d965_282.png)

This is a bug。Deep learning can come to the rescue here。

And this is something that was proposed around you know， 2010， 2012。

 1314 researchers have started applying techniques from general well。

 I guess from from deep learning from they have started to apply a lot of techniques that we have seen in this class in order to solve。



![](img/efacaa41a9b1dd88577527a2fdf4d965_284.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_285.png)

Problems of this form in a more general and in a black box way。

 so there's there's this idea of black box creationial inference， which is really interesting。

 let's say that we have a。The same kind of latent variable model。

 and let's say that it doesn't fall in a nice class of models for which we can apply EM or mean field variational inference。

Or let's say that it does， let's say this is a mixture of Gaussians。

 but we put some extrava priors and so now the updates， EM updates are really hard to derive。

 and it would take us 10 pages of math to do that。Well， instead。

 we can apply in a very straightforward way the techniques we have seen in the class， for example。

 we can apply the reinforce estimator to learn this model in a completely black box way。



![](img/efacaa41a9b1dd88577527a2fdf4d965_287.png)

All right， so what I mean by this is that we can just apply a variational inference and instead of trying to derive。

Precise manual updates for Q of z given x， we can instead consider parameterizing Q of z given x by some kind of black box neural network and we just try to fit。

 we know that our goal is to ultimately fit the true posterior。

 but we're not going to bother deriving math we're not going to bother choosing a particular parametric form for Q for which the math updates are tractable。

 we will just make Q a black box neuralNe and we will optimize this Q using reinforce or using other grain estimators if they're applicable to just fit the approximate posterior as well as we can。



![](img/efacaa41a9b1dd88577527a2fdf4d965_289.png)

And so this was in a sense， the idea of black box variation。

The idea is just given any probabilistic model。Apply， apply。Reinforced out of the box。

And in practice this works， in practice， we can use reinforce and all of these ideas we have seen in our lectures on BeEs to learn a lot of classical models in probabilistic。

And in the fuel ofophilistic MLl， various mixtures of distributions。

 mixtures of Gaussians with more complex sps， mixtures of other model families。

 so any P of x for which we can compute the joint can be solved using a black box approach where we just fit anyq of Z given x using reinforcefor。



![](img/efacaa41a9b1dd88577527a2fdf4d965_291.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_292.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_293.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_294.png)

And this could even work better than other approaches because if。



![](img/efacaa41a9b1dd88577527a2fdf4d965_296.png)

The true P ofc given x is intractable， but we choose to approximate it with a sufficiently flexible neural net。

 then we might get a better estimate for the elbow and we might get a better answer from this inference technique。

And another advantage is that we could apply these techniques using a lot of the frameworks exist using which exist in machine learning。

 we could just code this up in Tensorflow and Pytororch and we could run this on GPUs to optimize large instances of these models and this is something we get all for free by leveraging neural networks in gender models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_298.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_299.png)

So this is one idea， another fun idea is that of implicit models。So remember we saw when we saw GNs。

 I said that GNs are implicit models because they're only defined over samples。

 because they're only defined the other samples。

![](img/efacaa41a9b1dd88577527a2fdf4d965_301.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_302.png)

We never write down an explicit form for what the distribution is。

 which is draw samples and the samples implicitly define the distribution。Well。

 the idea of implicit models is to go beyond just images and to apply this to any sort of data。



![](img/efacaa41a9b1dd88577527a2fdf4d965_304.png)

For example， here is an application of this idea， it's an application of implicit modeling to a data set of。

Populations of prey and predators， so let's say wolves and rabbits in some ecological zone。



![](img/efacaa41a9b1dd88577527a2fdf4d965_306.png)

There's a classic model in ecology called the Lo carvoltro equations。

 so these are differential equations， which starting from some initial。



![](img/efacaa41a9b1dd88577527a2fdf4d965_308.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_309.png)

Numbers of。Pray and population describe how they evolve。

 So here x is the number of pre and what this。

![](img/efacaa41a9b1dd88577527a2fdf4d965_311.png)

What this equation is saying is that the rate at which。The number of prey， let's say。

 number of rabbits increases this derivative is larger if you have more prey。

 so if you have more animals。Then their rate of increase just you know， if there's more of them。

 there's more of them to breed， so the rate at which the population increases。



![](img/efacaa41a9b1dd88577527a2fdf4d965_313.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_314.png)

Increases itself when you have more animals and it also decreases when you have more predators。

 so adding more predators in the system slows down the growth of。



![](img/efacaa41a9b1dd88577527a2fdf4d965_316.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_317.png)

Of of。呃呃。Of the animals which are being played upon。



![](img/efacaa41a9b1dd88577527a2fdf4d965_319.png)

And so this is an implicit model because it doesn't define a probability。

 but it defines ways of sampling from the distribution even an initial set of conditions which can be random so if I at random choose a number of prey and predators I can run these differential equations to get samples of how the population of say in this case these are links and rabbits。



![](img/efacaa41a9b1dd88577527a2fdf4d965_321.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_322.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_323.png)

I can get samples of how these two populations evolve starting from any initial conditions。

But this is still a model because it does have three parameters alpha beta alpha gamma that I would want to learn。

 but I can't learn them using black box variational inference in my previous slide because I can't really this is not a this is not a model for which I can write down a probability so what do I do then well it looks kind of like a GN I have a process for drawing samples can I use ideas from GNs to learn these models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_325.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_326.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_327.png)

Well， it turns out that yes。So let's say that we wanted to learn。

An approximate posterior to this distribution， so I have some parameters。Theta in this model。

And I want to learn a posterior distribution over that。

 so in a sense I'm being Bayesian because I have a probability over my model parameters。



![](img/efacaa41a9b1dd88577527a2fdf4d965_329.png)

But let's say in general， I have some latent variable model that is defined only implicitly。

 it has some it has some parameters the， it has some parameters it has some latent variable to。

 and I want to learn these。One approach to do this could be to apply variational inference and learn the elbow。

And if I just do the evation of graal inference。I can transform it into this form。

 which is the ratio of distributions。Now again， if I knew what P is and if I knew what yeah。

 if I could write down a formula for P， then I could apply a black box variational inference and just parameterize cube by a neuralNe and try to fit this。

 but now I can because I don't have a formula for P so what do we do well if we can estimate this ratio of distributions then we can still optimize the elbow。

By trying to optimize this ratio。

![](img/efacaa41a9b1dd88577527a2fdf4d965_331.png)

And how do I optimize how do I learn this log ratio？

this well this is where the idea of GNs come in remember I said that when GN tries to discriminate the samples from two distributions。

 it implicitly learns ratio probability the log ratio of these two distributions。



![](img/efacaa41a9b1dd88577527a2fdf4d965_333.png)

And so if I were to train my discriminator， which I'm going to call R。

 if I were to train this on sample x z theta that come from the distribution P and on distribution Q。



![](img/efacaa41a9b1dd88577527a2fdf4d965_335.png)

The optimal R that's optimizing this subjective is precisely the log ratio of these two distributions。

 This is what we derived in our very first lecture on GNs。



![](img/efacaa41a9b1dd88577527a2fdf4d965_337.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_338.png)

And so if I can learn this discriminator。Then I can just plug it into my elbow。

 I can plug I can plug r star into my elbow and now I can optimize R star over theta as opposed to optimizing the actual elbow so in a sense this is like again right I have a P and I have a Q。

I can。Train my discriminator to get an estimate of the ratio。Which gives me an estimate of the elbow。

 And now that I have fixed the。Discriminator， I can take。

Steps on P or Q I can update these two distributions to go into the direction I want。

 which is to maximize the elbow now I've updated my generator I stopped that I fixed my discriminator。

I again update the ratio and I can keep optimizing the elbow like this。

So I think this is really interesting because it shows that the idea of GN can be used to optimize arbitrary probabilistic models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_340.png)

Including especially ones that are defined implicitly。



![](img/efacaa41a9b1dd88577527a2fdf4d965_342.png)

And I guess once we do this procedure， once we finish updating P and once we finish updating Q。

 in the end， we will have a distribution Q of theta。

 which is going to be an approximate Bayesian theerior over the parameters。

 and we can read out the likely value of the parameters from that。Okay。Again。

 I think this is a cool example and a cool idea and again my point here is that the many techniques that we have seen in this class。

 including reinforce and variational inference and GNs。

 they go beyond just generating3D images they can be used to improve statistical inference throughout machine learning and statistics。



![](img/efacaa41a9b1dd88577527a2fdf4d965_344.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_345.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_346.png)

Yes。Okay， so these were two examples of how generative models and neuralNes can improve our ability to specify models over data。

 and I also gave you two examples of how neural nets and generative models can be used to improve our ability to fit and learn these models。

I want to end with an example and work with a topic called probilistic programming。



![](img/efacaa41a9b1dd88577527a2fdf4d965_348.png)

Which goes a little bit into how these models could be trained and learned。



![](img/efacaa41a9b1dd88577527a2fdf4d965_350.png)

In practice， how these how all of these ideas could be implemented in software， that is， in a sense。

 the goal of probabilistic programming。

![](img/efacaa41a9b1dd88577527a2fdf4d965_352.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_353.png)

So probillistic programming is this technique for。

![](img/efacaa41a9b1dd88577527a2fdf4d965_355.png)

Defining probabilistic models using very general types of computer programs。



![](img/efacaa41a9b1dd88577527a2fdf4d965_357.png)

は。So as I said earlier， the idea of box's loop and the idea of probabilistic reasoning is that we have three steps we start by specifying the model。

 then we specify the inference algorithms， we learn the algorithms we execute the algorithms we learn the model and then we critique the model and we go back to the beginning well probabilistic programming probillistic programming is a field which tries to develop。



![](img/efacaa41a9b1dd88577527a2fdf4d965_359.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_360.png)

Software frameworks。For implementing all of these steps。



![](img/efacaa41a9b1dd88577527a2fdf4d965_362.png)

So。At the modeling stage。Yeah。Probilistic programming languages。

these are frameworks which allow you to specify a model kind of like the Locavoltre equations or the GMMM plus VE model or the LDA model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_364.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_365.png)

Probilistic programming languages allow you to specify these using very general types of。



![](img/efacaa41a9b1dd88577527a2fdf4d965_367.png)

Code and programming languages。For example， in this。

Class I defined most of my models using the notation of probability and in the case of ofvol of the lock ofvol equations i use differential equations to define the model so there's at least two different ways of defining a model that we have seen the most general way of defining a model would be using computer code using something like a cururing machine or using kind of the formalisms we have for defining computer programs in fact there is this notion of compability and the most general model that I could have is。

One that is， well， I guess any computational process can define a model and what probabilistic programming languages provide are very general ways of specifying these probabilistic models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_369.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_370.png)

So what do I mean by general what could be more general than language probability well for example you could have logic you could have four loops and control loops。

 you could have you could write arbitrary code but this code manipulates random variables and at the end it produces either samples or it produces some kind of formula but essentially the process of going from randomness to samples can be described using arbitrary computer code and the programming a probabilistic programming language provides primitives for describing how you go from noise to some sort of。



![](img/efacaa41a9b1dd88577527a2fdf4d965_372.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_373.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_374.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_375.png)

Samples or distribution over samples。And again， these frameworks will be very flexible。



![](img/efacaa41a9b1dd88577527a2fdf4d965_377.png)

And so there are many examples of prolistic programming languages out there maybe you've heard about some of them so Stan is an older one that's very famous Edward is one that i'm going to give as an example a little bit later and then Pyro is one that's used in Py that is a very modern one that is based on top of Pytorch。

And so these methods provide a lot of useful primitives， for example， probability distributions。

 you can have a probability distribution class or object in your programming language and then you can use these primitives to define distributions and you can also use other types of primitives like for example。

 variational inference or MCMC， you have a lot of tools and libraries that can help you automate inference because once you have specified the model using a probabilistic programming language。

 then you want to get answers from your model， you want to fit it to data or you want to do visual inference in the model and what what these languages provide are tools and frameworks which help you run variational inference。

 help you run MCMC。

![](img/efacaa41a9b1dd88577527a2fdf4d965_379.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_380.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_381.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_382.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_383.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_384.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_385.png)

嗯。And the field of prolistic programming is really interesting because they。



![](img/efacaa41a9b1dd88577527a2fdf4d965_387.png)

It provides a way， I guess it holds the promise of making this idea of。



![](img/efacaa41a9b1dd88577527a2fdf4d965_389.png)

哦。Implementing boxes loop。

![](img/efacaa41a9b1dd88577527a2fdf4d965_391.png)

And applying probilistic reasoning。These languages can help make that approach very accessible。



![](img/efacaa41a9b1dd88577527a2fdf4d965_393.png)

And if the vision of these prolistic programming languages is successful。

 we would be in a world where any analyst or any scientist or anybody who's trying to solve a problem only uses high level language to specify a model of how the data behaves。



![](img/efacaa41a9b1dd88577527a2fdf4d965_395.png)

We given some latent factors， so let's say they just specify the story of LD using that simple type of pseudocode that I had in my first slide and then the programming language takes in that model and it automates inference it automates。



![](img/efacaa41a9b1dd88577527a2fdf4d965_397.png)

Learning it spits out an answer， it helps you critique the data， critique the model。



![](img/efacaa41a9b1dd88577527a2fdf4d965_399.png)

Yeah， this is these are the tools and this is the vision that programming languages are building towards and if this vision is successful。

 then this could enable。

![](img/efacaa41a9b1dd88577527a2fdf4d965_401.png)

Analysts and researchers with relatively little machine learning experience to solve complex data modeling problems in a principle probabilistic way。



![](img/efacaa41a9b1dd88577527a2fdf4d965_403.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_404.png)

This is my kind of one slide explaining probabilistic programming and again I want to draw connections between deep geneative models and deep learning and this field of forbilistic programming。



![](img/efacaa41a9b1dd88577527a2fdf4d965_406.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_407.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_408.png)

All of these。Tecniques that we have learned in the class can be used to improve。

Proalistic programming。As well。So for example， we can specify the model using deep neural networks。

 right we could be。We could be using neural nets as part of our basic primitives for specifying distributions or specifying probabilistic models。



![](img/efacaa41a9b1dd88577527a2fdf4d965_410.png)

We could also use neural networks to accelerate inference， for example。

 implicit variational inference in black box variational inference。

 these are techniques that you might find implemented in programming in probabilistic programming languages and you can use them you can call them as a black box to solve some kind of problem that you might have and also the probabilistic programming languages tend to use existing software and hardware acceleration frameworks so they're usually built on top of libraries like TensorF or Pytorch and they can facilitate。



![](img/efacaa41a9b1dd88577527a2fdf4d965_412.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_413.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_414.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_415.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_416.png)

Executing inference on a larger scale。

![](img/efacaa41a9b1dd88577527a2fdf4d965_418.png)

So just to make things complete， this is my last slide on proistic programming。

 one interesting and early example of a deep programming deep realisticistic programming language was Edward from David Blythes group and Edward。



![](img/efacaa41a9b1dd88577527a2fdf4d965_420.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_421.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_422.png)

Essentially， it lets you specify probabilistic programs or probabilistic models as tensorflow computational graphs where you have some random variables right and then the task of doing inference is completely taken care of in Tensorflow so you have your model P be a computational graph in tensorflow and then at inference time you specify an approximate inference。



![](img/efacaa41a9b1dd88577527a2fdf4d965_424.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_425.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_426.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_427.png)

You specify an approximate posterior Q as another tensorflow graph and then this。

The EdwardWword engine automates learning Q given P and well it automates spitting P&q jointly using variational inference and it can automate a lot of other useful tasks like representation learning inference sampling。



![](img/efacaa41a9b1dd88577527a2fdf4d965_429.png)

And just to give you an idea of how a probabilistic program might look like。

 this is an example of implementing latent deishly allocation。

 which was one of the first examples we started with， so this is latent deishly allocation in Edward。



![](img/efacaa41a9b1dd88577527a2fdf4d965_431.png)

And you can see that we choose some so here the variable names are a bit different。

 but one of these variables are so I guess these are the。

The topic proportions and the topic allocations。Sorry， the word document assignments。

Sorry the word topic assignment and the no sorry phi is the probability of each word under each topic and theta is the probability theta is the mixture of topics for each document right so you can see we have the same set of variables and then Z is the topic of a certain word in a certain document in W is the index of the word so you can see that we just defined this same story that I had in pseudo code on my slide using simple Python and tensorflow which almost looks like pseudocode and now that you have defined this model it gives you a computational graph you can plug it into the engine with a few other。

Components that help you automate an inference and then you run the engine and the engine gives you an answer to what the topics and what the clusters are。



![](img/efacaa41a9b1dd88577527a2fdf4d965_433.png)

Okay， in this case， i'll just end the lecture by summarizing things one last time I would say that this course was on generative models。

 but generative models are a special case of a。

![](img/efacaa41a9b1dd88577527a2fdf4d965_435.png)

More broader。Subfield of machine learning called probabilistic machine learning you know sometimes there's connectionist people talk about connectionist machine learning people talk about like rules based or symbolic AI symbolic machine learning so these are all big directions within m and AI proistic is an probabilistic m is。



![](img/efacaa41a9b1dd88577527a2fdf4d965_437.png)

Another one of these big directions and the course and the algorithms in this course were all special cases of this more general probabilistic theme。



![](img/efacaa41a9b1dd88577527a2fdf4d965_439.png)

And this approach to solving machine learning problems is really interesting because it provides a principled way of specifying our prior knowledge and it also naturally provides a systematic way of approaching and solving problems via boxes loop and via the separation of any problem in these three tasks which are relatively distinct from each other。



![](img/efacaa41a9b1dd88577527a2fdf4d965_441.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_442.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_443.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_444.png)

Um， and not only are the methods of this class instances of prolistic reasoning。

 they can also be used to improve algorithms for prolistic reasoning。



![](img/efacaa41a9b1dd88577527a2fdf4d965_446.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_447.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_448.png)

Across a wide range of probilistic models。For example。

 we can use neural nets to better combine we can compose neural nets with classical probabilistic models to get the best of both worlds。

 for example， if we have data that is semistructured so we have some unstructured components like video frames and we have some structured components like discrete states that we want to learn we can use classical probabilistic models for the structured part and we can compose them with。



![](img/efacaa41a9b1dd88577527a2fdf4d965_450.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_451.png)

![](img/efacaa41a9b1dd88577527a2fdf4d965_452.png)

Expressive neural networks for the unstructured part。

 so for the video and the images and then the latent states is still a structured variable that we get to interpret and by combining the best of both worlds we can apply。

The probabilistic reasoning approach to new type of data that normally would have been hard to work with。



![](img/efacaa41a9b1dd88577527a2fdf4d965_454.png)

And also neural networks can speed up various classical inference and learning algorithms and they can be used to。



![](img/efacaa41a9b1dd88577527a2fdf4d965_456.png)

Learn models which otherwise would have been really hard to learn。



![](img/efacaa41a9b1dd88577527a2fdf4d965_458.png)

And in practice， all of these tools can be implemented within the framework of probabilistic programming。



![](img/efacaa41a9b1dd88577527a2fdf4d965_460.png)