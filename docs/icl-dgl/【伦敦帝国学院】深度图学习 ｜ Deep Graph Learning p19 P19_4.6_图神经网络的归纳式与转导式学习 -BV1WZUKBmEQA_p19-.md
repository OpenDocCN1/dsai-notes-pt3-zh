# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p19 P19_4.6_图神经网络的归纳式与转导式学习 -BV1WZUKBmEQA_p19-

![](img/3174610bc579d5320ebdb00a864c0267_0.png)

So now we reach the last part of this lecture which is basically the learning paradigm or the training paradigm that we can use to train our neural networks right so there is there are two approaches so so far in all previous lectures。

We only have explored the inductive setting all right。

 so the inductive setting is conventional in many kind of you know machine learning and deep learning models so the key idea is that you train you have a training data that is independent completely independent from the testing data。

 so there is an independent here so first。Train。So let me write it down。So here first。

Maybe Eric can write it this way， so first train。Model on train set。On the train。Se and second test。

On the test set， okay？So these are two separate steps， these are separate steps。



![](img/3174610bc579d5320ebdb00a864c0267_2.png)

Now。In in another example， what we could possibly do is to train and test at the same time。

 so for example， let's see at this you know in the in the a figure here。

We have node classification task in an inductive setting so are giving a set of eye training graphs we have different training graphs and the node labels orange and sign colors are no so we have the known of course when we have training data we know all the labels of the training samples okay so in this case because well we're not doing other types of training and if you have training data with with missing or some unlabeled samples we call that semiupervised learning and there is there is a a discussion between different researchers arguing that semiupervised is sort of transductive but I would like to call you know semisupervised learning is when you have training semisupervised learning when。

Training you can have training samples， training samples can be unlabeled。

So you can have some training samples with no labels and that's still fine but you will have your test you know samples independent okay so and and so after training basically here you are giving a test graph and you can assign or predict the label for each node on this test graph for example okay so this is one way of doing it now the transductive setting is very different and a transductive setting。

We build a graph with all training and testing samples at the same time。

 So my adjacency matrix of the adjacency matrix of the graph will have， you know。

 training samples T R plus T S plus testing samples。 So the node all node will be combined together。

 Okay， so it's a huge graph that is a union， you know， that has a train A test。

 but it's not just a union these are actually connected。 So it's plus， you know。

 there there they're both connected。 Okay， so it's all of them together connected。 So。

Maybe I could end so all of them connected Okay， so here look， this is a testing node。

And our goal is to predict on this， but to train our network will evaluate the loss on the label training samples because the training samples are labeled so we can minimize our loss function on the training testing sample okay so L of w we have here the iterations and we optimize the loss on the training and by optimizing the loss of the training so remember we have all these embeddings so we are also updating the embeddings for the for the testing nodes so these embeddings are being updated for the testing node and the training so during the training we minimize the loss over all training sample so all training nodes and actually what happens is that by the end of the training we will have our embedding so by of the testing node so lets me use a different color here so as we reach the end of the training we have already predicted the labels and predicted the embedding so。

Exactly the labels of these points because we are co learning so basically when you have transductive a transductive learning paradigm you train and test simultaneously so you train。



![](img/3174610bc579d5320ebdb00a864c0267_4.png)

And test jointly so they're done together Okay so here in node classification in transductive setting。

 there is one large graph in which some of the nodes have labels So these notess are actually the training notes and the others here these are the testing So this is the right definition So this should be the test data and this should be the train data otherwise we will mix it up with semiupervised learning all right so we train the model to predict the known labels correctly which are of the known labels of the training。



![](img/3174610bc579d5320ebdb00a864c0267_6.png)

![](img/3174610bc579d5320ebdb00a864c0267_7.png)

N notes， okay， and then examine the prediction on the un labels。Of the tests。

 so this examining the prediction， this is to evaluate the generalizability。



![](img/3174610bc579d5320ebdb00a864c0267_9.png)

Evaluate the。General light。Visibility。

![](img/3174610bc579d5320ebdb00a864c0267_11.png)

Of our model。Allright so these are two different paradigms and what we're going to see now is like how can we basically move from an inductive setting to a transductive one so a transductive one to inductive is easy you can partition the graph and you can separate them out so I can take all the question mark notes and put them in a single graph right so I do partitioning and then I can move directly from at transductive setting to an inductive setting and the idea that now that we have seen all the node update rules using an inductive setting so how can we do that for the transductive learnings actually is very simple it's not difficult so here first before we move into that let's look at the pros and the cons of inductive in transductive learning so you can see that we have a lot of happy faces for you know the inductive learning transductive is really costly because you need to train on everybody and you model the relationship include the testing sample。



![](img/3174610bc579d5320ebdb00a864c0267_13.png)

![](img/3174610bc579d5320ebdb00a864c0267_14.png)

![](img/3174610bc579d5320ebdb00a864c0267_15.png)

![](img/3174610bc579d5320ebdb00a864c0267_16.png)

When you train your model so let's look at that so first we learn so in inductive learning we so let me use this color。

 we learn the rule a rule， a universal rule that maps a graph or a few of its elements right for example nodes or nodes and edges to a target output Y and then we apply this rule to a new data so this allows the model like we can generalize the model and apply it to many other new data samples and a transductive learning it doesn't actually produce a rule that merely a labeling of the unknown outputs which are here let me write them down is these are the test nodes right？

And the second thing is that okay， so now。😊，One drawback for the inductive learning is that we cannot access the original features of the testing samples during the training so the testing sample may have a distribution like this。

 so this is the testing。And then if we have of the features and then maybe the training is like this right so what happens here we have what we call a covariate shift a domain shift this is a domain fracture called okay so it's a domain fracture between train and test data so when you have this domain fracture right you have the samples are drawn from different distributions the original distributions are different then your inductive learning setting may may fail or struggle to generalize like it won't give you good predictions on these samples so think about learning a you know like you have different samples right here so triangles and you know for example。

Let's say circles， but when you do the testing， the testing has a different distribution so you have some triangles here in some circles there。

 So actually the real line is over here。 So you have what we call a domain fracture in distribution in this case you know your your black model it will give you wrong prediction on the blue ones so it's really not good So what happens when you do transductive learning the good news and this is I think one of the main strength of transductive learning is that it considers both labeled and unlabeled data at the same time。

 So it has the advantage of you know seeing the patterns in the testing samples which helps makes decisions so which means we can model the relationship we will build a graph okay that kind of connects all these points together so let's put this maybe a good graph will have something like this and then。



![](img/3174610bc579d5320ebdb00a864c0267_18.png)

Here sparse connections here， so what happens in this graph that at the same time we're able to look at the distribution of the testing of the original data okay not the labels。

 the original features so we want to predict the labels and for example or scores and regression or classification tasks but the good news is that we don't wait until the testing stage to look at the distribution of the testing we actually can access the distribution of all these you know all these original features of all testing samples that we want to predict so all of these will be accessible to us at the beginning。

 the start of the optimization so we can know if we have a shift in in the distributions we can fix this problem better okay so co-learning together you're accessing the testing data distribution during the training time and then you're testing to do the prediction of the labels on the nodes all right？



![](img/3174610bc579d5320ebdb00a864c0267_20.png)

![](img/3174610bc579d5320ebdb00a864c0267_21.png)

![](img/3174610bc579d5320ebdb00a864c0267_22.png)

![](img/3174610bc579d5320ebdb00a864c0267_23.png)

![](img/3174610bc579d5320ebdb00a864c0267_24.png)

![](img/3174610bc579d5320ebdb00a864c0267_25.png)

So。Another thing is that for inductive learning the good news we don't need to store the testing nodes and their original features in memory so the testing samples will come after the training and you know it takes a split second like to kind of do the inference or the testing and getting the final predicted labels so it's not costly on the other hand the transductive learning is it requires a lot of high memory you know like to store all the information about training and testing nodes so it is memory costly and then it may it also requires a higher computational time because when you do message passing now you're doing message passing between all testing nodes and training at the same time so your graph is huge so it's going to be really you know like。



![](img/3174610bc579d5320ebdb00a864c0267_27.png)

![](img/3174610bc579d5320ebdb00a864c0267_28.png)

![](img/3174610bc579d5320ebdb00a864c0267_29.png)

Computationally expensive all right now the last thing here。

 the good news about inductive learning that you test the train model on unseen notes and as you have new notes coming in。



![](img/3174610bc579d5320ebdb00a864c0267_31.png)

So I want to add a new node or a new graph I can test it immediately so here every time I have a new node coming in I can test immediately right so we have seen that is thanks to the weight sharing so in inductive learning this makes you know the GNNs or GCNs generalizable to any kind of node with any neighborhood size and this is a power of GNN that we have seen before now what happens what happens if I add a node here so if I have a test node right here。



![](img/3174610bc579d5320ebdb00a864c0267_33.png)

How can I classify this node so in a transductive setting you need to build the relationship between this node and all other nodes and see whether they are connected or not they are similar or not。

 so the problem with transductive learning you're learning how to label this node not by applying a rule but by kind of co-opimizing so you need to retrain the whole model from scratch and this is really time consuming so not practical in real- time applications because as you have new testing samples coming in。



![](img/3174610bc579d5320ebdb00a864c0267_35.png)

![](img/3174610bc579d5320ebdb00a864c0267_36.png)

![](img/3174610bc579d5320ebdb00a864c0267_37.png)

You need to retrain the whole model from scratch， you need to rebuild the whole graph。😡。

Retrain it because to test， you need to co train so you train。And test。Jointly。So to test。

 you need to retrain and that's a very big disadvantage， I would say。

 of transductive learning paradigms。

![](img/3174610bc579d5320ebdb00a864c0267_39.png)

All right， so now let's look at how we generalize for example。

 inductive how we can transform an inductive node classification to a transductive one all right so this is the formula that we have seen before this is the update rule so here what we have we have a for example。

And you coming note。And this node we want to basically predict the the you know like we want to predict the label of this node。

 so it's very easy， we can feed in this node through the network。

 you can feed in the original embedding， you pass it forward as I explained before。

And then as you pass it forward you will get the H you know of the final layer of this node that's called node test right and then you'll pass it through this kind of sigmoid function that will allow you to get the label for this node a Y test so it's actually not difficult so it's very easy and you can see your beta is actually scalar so this is beta K we have the mapping weight and this is the transformation matrix of all nodes so we have all node stacked here so we can put all nodes but we can also apply it to a single node generalizes to single node and we have seen the format it's not difficult so if you have a bunch of also testing nodes you can stack them together so these will be your testing nodes here so you will have multiple testing nodes that you stack them together and testing nodes for example okay and test nodes and this is a one vector that we added there and yeah so the dimensionality is consistent and we will。

Get basically a value right here and this value will apply a sigmoid function to basically get the probability and the final label of this kind of testing sample or a set of testing samples if we have many testing samples in blue all right so these guys cool now this is an inductive note classification now if we have a transductive one。



![](img/3174610bc579d5320ebdb00a864c0267_41.png)

![](img/3174610bc579d5320ebdb00a864c0267_42.png)

So inductive learning， what happens is actually we will mask out so we'll have here we will learn these embeddings so let's say these are two。

You know we will mask the labels of these guys so when we do the optimization we will not optimize on these guys because we don't have their labels we want to predict their labels okay so it's the same thing just you know when you do the transective note classification we need to get。

We need to get the labels of these two guys at the same time so here in this formalization that we tweaked a little bit mathematical update rule for the classification right so in this matrix form we take all these node so we have node one for example so these are two nodes that we want to test right so in this case the size of this will be these are the test nodes right and then here the size here will be the test nodes。

And this is a multiplication， so what happens is that we're going to you know apply this to all the test node so we have the embeddings that we learned right of the test nodes and we co-learned because these are updated throughout the whole graph through the message passing so first we have the embedding the original features of the test node and also the train node so these are the train node let me color them for you guys。

So my train node we have four training nodes and their original embeddings and we have two testing nodes and their original embeddings and as we move them through the GNN layers we get the updated embeddings right so we know how to do that in detail and now we want to predict the label so how to predict the label we just pass it through the sigmoid function so this sigmoid function and as you get guys can see when we add this up this will give us a horizontalarrow row vector and we multiply the beta K by this you know one vector transpose so we're going to get also another you know the transform vector here plus the bias。

And we apply a sigmoid function， so this sigmoid function， the bold sigmoid function。

 it applies the function independently to every element of the row of the input a vector so of the row input vector and so what we're going to get basically is an n n output so y here。

Y belongs to R big n with n is。Number of test notes of test。Noes。

In G in the whole graph okay so if we have two nodes， for example。

 we're going get two you know like two values here final two values that we will apply the activation function to that for classification and we're going get the final labels predicted for these two nodes all right so that's how it works it's actually very simple so you can easily do that so it's the same thing so here we're optimizing over these。

 but in the optim in an inductive learning we consider that everybody is kind of you know has its label but we do some masking and the optimization because when we have the testing nodes we don't know these labels so we will not use it to kind of evaluate our loss our our classification loss views cross entropy cross entropy will be evaluated only on the pink。



![](img/3174610bc579d5320ebdb00a864c0267_44.png)

![](img/3174610bc579d5320ebdb00a864c0267_45.png)

![](img/3174610bc579d5320ebdb00a864c0267_46.png)

![](img/3174610bc579d5320ebdb00a864c0267_47.png)

Ground truth training notes because we're optimizing and then later on for evaluation this is for so let me write it here so we optimize over those。

Over train。And we。Evaluate。The model generalizability over a test。

By checking the why hat here of test sample and also versus the ground truth the why test ground truth all right so that's for evaluation and this is for the training and optimization that we usually do。



![](img/3174610bc579d5320ebdb00a864c0267_49.png)

All right， so。One question for reflection so how to batch notess in a transductive learning paradigm so this shouldn't be too difficult if you guys think about the approaches we have seen you can also design a GCN model that does not note classification the GCN model or GN model different layers it can be trained in an inductive way and transductive way and you can compare the results of the inductive training versus the transductive training on the same you know input you have a fixed train set fixed test set you can also add validation if you want。

 but yeah so basically you can compare these two learning paradigms and in terms of batching you can try to elicit or like adopt the same batching strategy for fair comparison between these two learning paradigms all right sounds good so that's all in I think as just a recap of this lecture you guys can。



![](img/3174610bc579d5320ebdb00a864c0267_51.png)

![](img/3174610bc579d5320ebdb00a864c0267_52.png)

![](img/3174610bc579d5320ebdb00a864c0267_53.png)

![](img/3174610bc579d5320ebdb00a864c0267_54.png)

Try to kind of you know， maybe sit down after watching these videos and try to recall every single thing that we learned today and it would be a good recall exercise。

 the different concepts that you know you remember。



![](img/3174610bc579d5320ebdb00a864c0267_56.png)

![](img/3174610bc579d5320ebdb00a864c0267_57.png)

![](img/3174610bc579d5320ebdb00a864c0267_58.png)

![](img/3174610bc579d5320ebdb00a864c0267_59.png)