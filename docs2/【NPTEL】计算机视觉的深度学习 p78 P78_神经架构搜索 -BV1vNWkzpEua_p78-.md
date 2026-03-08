# 【NPTEL】计算机视觉的深度学习 p78 P78_神经架构搜索 -BV1vNWkzpEua_p78-

![](img/a445ac7c384a21d8e14f71f5be52e3ef_0.png)

As the last advanced topic for this week。We will talk about neural architecture search。

 another contemporary topic。That deals with。Searching for the right neural network architecture for a given problem。

It it should straight away appeal to you that this is a very important problem considering the various hyperparameters that one has in designing neural networks。

To get a better understanding of why we need this。We have seen over the duration of this course that accuracy and performance has improved with better design of architectures。

And this often requires human experts to spend hundreds of hours on arbitrary training and testing and hyperparammedic tu。

This in fact， doesn' not even mean that the entire space of possible architectures has been searched exhaustively to find the right architecture。

Often， researchers use architectures that were proposed earlier and adapt a few elements to arrive at an architecture for a given problem。

That brings the question。Can we adopt a systematic and automatic way of learning high performance model architectures？

And the solution that we' are going to talk about is neural architecture search。

Neural architecture search， perhaps not in the same name， has been around for some time。

In very early phases。One would use evolutionary algorithms such as say genetic algorithms to be able to design neural network architectures。

 this led to exploration of random search for architectures or even bayesian optimization for architectures and hyperparameter tuning over the last decade。

Over the last two to three years neural architecture search has emerged as an independent important problem；

 it primarily started with searching for these architectures using principles from reinforcement learning。

The general problem set up in NAS for neural architecture search is given by。

You have a search space which defines the space of all possible possible architectures that you want to look for for a given problem。

You have a search strategy to look for an architecture within the search space。

 often the search space can be extremely large。And we need a performance estimation strategy。

To try to estimate a per an architectures performance。

Using standard training and validation performance could be computationally expensive。

To be able to try various kinds of architectures so this also needs to be chosen carefully。

 so you have a search space， a search strategy which results in an architecture whose performance is estimated based on the performance estimate the search strategy looks further a newer architecture and this loop continues until a desired performance is met on a consistent basis。

As we just mentioned。The search space of NAS methods are extremely important。

 so how is the search space defined？One can view neural networks as a function that transforms input variables to output variables through a series of operations。

So， if you look at neural networks as computational graphs， recall the lecture we had earlier。

 each neural network node represents a tensor。And is associated with an operation on its parent nodes I。

So， you can say that the computation at a node k is given by Z superscript K is the operation at k of its parent nodes IK。

What are the operations？The operations could be convolutions， pooling， activation functions。

 or even energy operations like concatenation or elementwise addition or simple addition so on and so forth。

NASspace is generally a subspace of this general definition of neural architectures。

So what kind of search spaces do NA methods use？Broadly speaking。

 one could divide this into two kinds。A global space versus a cell based search space。

In a global search space， the method allows any kind of an architecture。

 so you have a large degree of freedom in arranging the operations。

You have a set of allowed operations such as convolutions， pooling， dense layers。

 global average pooling with different hyperparameter settings like number of filters， filter width。

 filter height， so on and so forth。But there are also a few constraints that are specified。

 for example， you may not want to start the neural network with pooling as the first operation。

You may not want to have dense layers before the first set of convolution operations。

 so on and so forth。In global search， the issue is that the search space is a bit rigid and it could be impractical to scale and transfer considering the extensiveness of this search space。

On the other hand， cell basedase search space， which was first introduced in this work in 200 in CBPR of 2018。

 they introduced a method called NASNe。😊，The idea here is that a lot of handcrafted architectures are actually designed with repetitions of specific structures。

We have seen residual blocks in renets， this idea is taken forward here by defining a cell structure。

And constructing a network architecture by repeating the cell structure。What is a cell。

 you could look at it as a small directed acyclic graph that represents a transformation or a series of transformations。

In NASNet， which was the method introduced in CVPR of 2018。The method learns two kinds of cells。

 a normal cell where the dimension of the input and the output of that transformation is retained。

 example would be convolution。And then a reduction cell where the output feature map has width and height reduced。

 for instance， like pooling operations。Here is an example of a global search space where you could have a chain structured search space as given below。

 where given an input， you have a series of operations and the operations have to be searched for from your search space from your universe of operations。

And another variant is where you have a skip connection in your chain structured cell space。

On the other hand， in a cell based search space。An architecture template is defined for example here you see an input which first goes through a normal cell then a reduction cell then a normal cell。

 a reduction cell then a normal cell and softmax。In very simple terms。

 you could assume that this normal cell was convolution plus batchum and reduction cell could have been pooling。

😊，In a standard Alexnet context， but now in NASnet。

 each of these cells is searched for within within a universe of operations。So。

 here is the reduction cell of one of the architectures of NASNnet called NASnet a。

 where you see five blocks with different kinds of operations that have been mentioned on each block which is obtained after the architecture search。

As we just mentioned some time ago。The space of。Neural architecture search became popular in 2017 with the introduction of NAS through reinforcement learning。

While we have not covered reinforcement reinforcement learning as a topic in this course。

We will speak at a very high level to explain how this NAS method works。

So this method proposes the use of a controller。Whi proposes a child architecture and the controller is implemented as in recurrent neural network or an RNN。

Which outputs a sequence of tokens that configure the network architecture。The controller。

RNN is trained similar to a reinforcement learning task using a popular algorithm called reinforcefor which uses Monte Carlo policy gradients。

The action space in this case is the list of tokens for defining a child network。

The reward is the accuracy of the child network and the loss is the reinforce loss given by the step。

Since we have not covered reinforcement learning in this course。

 we won't go further deeper than this， but if you are interested you can read this paper for more details。

Here is the schematic you have the controller which samples an architecture with probability BPP you train a child network with that architecture to get an accuracy which is here a reward in the context of reinforcement learning and then the policy gradient is computed to update the controller RNN here is an example of how the controller RNN works which is trained using reinforce。

So you can see that at each step of the Rronn across different layers。

 multiple hyperparameters such as number of filters， filter height， filter width。

 stride height and stride width are predicted for that layer。

 which is then passed on to the next layer whose number of filters filter height。

 and other hyperparameters are predicted。So， the prediction could be something like 371236 where the first parameter says the filter height。

 the next one gives the filter width， the stride height。

 the stride width the number of filters so on and so forth one of the limitations of NAS based methods is that when you view your entire search base as a graph with each path as a certain sequence of operations which could be an architecture。

Each of these parts are looked at and trained independently to be able to find which architecture suits a particular task。

So， given the overall search space， the path 1，23 which could be say a convolution followed by a pooling and a path 1。

2 4 which could be convolution followed by a batch for instances。

Each of these are trained independently and their performances are assessed to see which of those operations or sequence of operations suits for a given task。

A recent method called Eness proposed in ICML of 2018 asks the question can we treat all model trajectories as subgraphs of a single directed acyclgraph？

The answer is yes and efficient shows a way to do this by sharing parameters across the child models。

So， in this case， if what you see here is a super graph of all possible sequences of operations。

Each architecture。Becomes a subgraph or a trajectory in this graph。

So you could look at these red arrows here as one sequence of operations corresponding to one architecture and that sequence of operations is decided by an RNN controller which is trained using reinforcement learning。

How is this trained， the weights of the controller and that the weights corresponding to the chosen path are trained in an alternate manner and this leads to the final training and they show that this approach gives about 2。

89% testerer on the Saran data set which is close to state of the art and took less than 16 hours to search for the right architecture。

which is significantly lesser than other NASB models。

 especially NASB models based on reinforcement learning can take many days to search for the right architecture。

One other observation to point out here is a lot of the state of the art models today in classification。

 in detection are all based on architectures。Obtained through neural architecture search。

A more recent development。😊，Called dots or differentiable architecture search was proposed in ICLR of 2019。

And the key idea here was to define。The search space using a set of binary variables on the operations so your。

Output of a layer Z K is now an operation O multiplied by a binary variable into in terms of the input variables Z I from the previous layer。

The key insight in this approach is that until this method in all methods。

 you could either have an operation or not have an operation。

But this method says why don't we relax this and make alpha something that is learnable and hence it relaxes this categorical choice of choosing an operation as a softm over all possible operations so the operation is not just binary in terms of its existence。

 it is now a softm that you have over the space of all possible operations。

 this allows us to back propagate through the choice of the operation itself。

What does this mean how do you train？So in dots。An alternating bilevel optimization method is proposed similar to efficient mass where in the first iteration the model parameters w of a specific architecture is trained by minimizing loss on a training set。

And in the second step， the structural parameters alpha which weight each of your operations are learned using by minimizing another loss on a validation set。

 which is defined this way where w sta star alpha is the minimum loss of w on the train set。

 so you use those weights to be able to get a validation loss。

Which is then used to minimize the value of alpha。So。

 the final architecture is chosen based on the sequence of operations that maximizes alpha。

Or the operation at that step that gives you the maximum alpha。

This is an elegant solution that makes all parameters differentiable and entire and thus the entire architecture search as a differentiable procedure。

Other considerations that have been looked at in the NAS community is architecture transferability。

If we learn an architecture through a NAS method on sar 10， how well does it transfer to imagine it？

And research has shown that a lot of contemporary NAS methods deliver fairly well on this count where an architecture trained on Sear 10 also does well reasonably on Inet as well as on other datasets and tasks while this discussion on NAS was intended to be brief。

Keeping in view the scope of this course。Let's discuss a few future directions and open problems in NAS。

One of the first issues is search efficiency。As I just mentioned。

Trying to perform NAS using reinforcement learning can create a training overhead of many days on standard GPU architecture how do you improve the search becomes an important problem？

A different perspective is to also move towards less constrained search spaces one way you could improve your search efficiency is to constrain your search space more。

 but now we also don' not want to constrain the search space more to be able to explore better architectures。

Designing efficient architectures such as those we get after pruning or after quantization or probably finding the lottery ticket using NAS could also be an interesting direction of this space。

Another important direction is a joint optimization of all components of a deep learning pipeline。

 not just the architecture。We could also talk about what data augmentation to use。

 what activation functions to use， what optimizers to use and so on and so forth so including。

All of that， the NAS search pipeline would be an interesting future task in this space。Finally。

 designing architectures for multimodal tasks such as vision language tasks could also be a very important and useful direction。

Before we conclude this lecture。There is also an interesting observation by a few researchers about the curious case of random search。

In this work in TriI 2019， researchers observed that when one randomly searched for a neural network architecture。

The difference in accuracy was not too much between using random search。

 reinforcement learning or evolutionary algorithms。

And this leads to an important conversation as to whether we really need neural architecture search。

This observation was also seconded by a couple of other papers which showed that random search and a random wiring of neural networks can perform to a reasonable extent。

In contrast to what was observed earlier in terms of searching neural network architectures。

This leaves an interesting and open question for the community。😊。

The recommended readings for this lecture are once again a very nice blog article by Lillian Wine or neural architecture Search。

And these two survey papers on neural architecture search if you need more information。



![](img/a445ac7c384a21d8e14f71f5be52e3ef_2.png)