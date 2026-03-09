# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p09 P09_3.1_图卷积网络的训练与损失优化 -BV1WZUKBmEQA_p9-

。

![](img/b76d46ab77b15edb0c461b3861cb2da0_1.png)

Welcome to session three， so in today's session we're going to learn about GNNs how we can train them and how to design GNN models。

 what are the building components or the building blocks and operations of the GNN layer and at the beginning。

 so we're going to start with a reminder and overview of the past few lectures。

 what we covered so far and we will you know take a step by step approach into debunking the training of GCNs。



![](img/b76d46ab77b15edb0c461b3861cb2da0_3.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_4.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_5.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_6.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_7.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_8.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_9.png)

So this is the first part and the second part also we're gonna to expand on that a little bit and then I'm going to give you an overview of the GNN layer operations and define a few of them great so let's get started right away if you guys remember in the very first lecture we introduced the particular notions and definitions that are important including the the importance of the matrix of a graph the types of graphs。

 the different learning tasks worth the edgebased learning we have nodebased learning we have graph- based learning in lecture two。

 we learned about node embedding so how can we basically learn the embeddings of a node in a graph and also how to embed particular graphs for example。

 so node embeddings are very powerful because we're learning how to represent the graph itself the entire graph or。

😊。

![](img/b76d46ab77b15edb0c461b3861cb2da0_11.png)

Of graphs in a very compact way okay so representation learning is very important and this is what we have covered so we covered the trajectory from basically machine learning to deep learning and ultimately to graph neural networks particularly graph convolutional networks okay so what we have seen so far is that the node embedding whether the feature embedding is based on message passing so the generalized message passing propagation rule aims to update these embeddings so how can we update these embeddings in a GCN layer so this is based on two steps the first step is we rely on aggregating information from the node itself or myself in my neighbors all right so we take a node and we aggregate information from its neighbors。

If we do two layers here so we're going to aggregate information from the first starting with the furthest neighbors and going all the way up to this you know and particular node okay so there is also the process of self-agggregation that we talked about and we discussed different variance in lecture2 and after aggregating we have the second step so the second step we transform the aggregated representation or the aggregated embedding so we apply a transformation that is learnable and this is what we called omega in our in our mathematical formalization so this is a learnable。

Transformation and we can call it also mapping。Allright so the generalized propagation rule is defined basically these are the embeddings of all nodes in the graph in the layer K plus one and it is a function of the previous the embeddings and the previous you know in the layer okay and it takes also as input the topology or the adjacency matrix of the graph okay so the adjacency matrix of the graph now we have also seen quickly the update rule so the node embedding update rule that is based on this equation so in this equation we have we first do a self-encoding as I mentioned so you apply you know the transformation to the embedding of the node N in layer K okay and we transform it or map it through this omega K and in this case we have the。



![](img/b76d46ab77b15edb0c461b3861cb2da0_13.png)

omega K or the same transformation applied to the node itself in its neighbors okay so in the second part here we have the aggregation of the neighbors so after we aggregate we add also a bias so this bias accounts for you know data shifts and or you know shifts in pictures and representation so we can of course get rid of the bias or include it in the omega in a compact form as we do for support vector machines or any kind of supervised classifier or regression model so we can simply combine the data with the omega K in a single a matrix or a single entity but here we separate them out and we show that we can actually account for bias in the data transformation that we have so now after we do the aggregation we aggregate and transform and we have the bias right so we apply an active。

function so this is you know the nu linearity that we introduce so here so far all this part right here is actually a linear okay so now this is a linear mapping or a linear combination aggregation and transformation of the original of the original features of these notes of the notess in the graph but once we do once we apply this a this a is actually what introduces nulineity into our neural network okay so it's applied to all of these aggregated and transform features so we went over this in detail and in lecture2 and after that we generalize this to。



![](img/b76d46ab77b15edb0c461b3861cb2da0_15.png)

Basically multiple nodes so we can have this update rule applied to all node embedding simultaneously and this is a nice mathematical you know like equation to write because here we can see that we can update all together and yeah so now after this we we looked at basically these the hops so we talked about the receptive field and the different layer so each layer presents basically a ring okay so this is layer2 layer one etc cea。

 so one hop neighborhood two hop neighborhood etc cea。

 so we explore neighborhoods and we expand our graph and the notes neighborhood defines the computation graph over which we aggregate and transform embedding so it's called a computation graph here so because we have。



![](img/b76d46ab77b15edb0c461b3861cb2da0_17.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_18.png)

Basically， if we look at these neighbors， we're going to start， so this graph。

 let me use a different color。So this graph right here。

Okay that's not very different so here so this graph is the computation graph of this node Okay so here to update the node。

Embbedding of， you know， here， let's say H K plus one of node I， right， So this is node I。

 We need to take into account the self embedding and all neighbors。 So this presents a。

Computation graph over which we're going to collect you know all these embeddings right we're going to transform them collect them aggregate them transform them and optimize them of course so there is an optimization process that is happening behind the scenes and we're going talk about this in a bit so keep that in mind okay cool so what is the ultimate goal now so remember guys we wanted to learn embeddings we wanted to learn good embeddings for these you know like a feature for these notes starting with the original feature representation and we said that the original features may not be very good so our goal is to learn basically these embeddings and we hope that these learned embeddings in the final layer so if we have k big K layer so we want that we hope that Hk in the final k layer will be very simple。



![](img/b76d46ab77b15edb0c461b3861cb2da0_20.png)

And very representative they will allow us to perform or solve downstream learning tasks including regression and classification Okay cool now we have also seen so let me take one step back so you guys can see that we're going backwards so here's like a back prop to the to the to the first lecture so in the first lecture I have introduced the three different learning tasks like note classification and we have also edge based prediction or link prediction and whole graph entire graph classification or regression okay so we can do supervised learning here so。



![](img/b76d46ab77b15edb0c461b3861cb2da0_22.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_23.png)

In this figure， if you guys remember this figure from the first lecture。We mentioned that okay。

 so we can easily use GNNs to do classification to classify a node from using the node embeddings and the node embeddings are here。

 so basically。So the question that we asked at the time is like how do we how do we estimate or learn these node embeddings Okay how do we actually do that and in lecture two we explained okay here are the rules to update the embeddings so we looked at how to update these embeddings all right and then today we will look at how we actually optimize them which is very important because updating if you're updating using the message passing or the message propagation all right using the local neighbors and all these values then eventually you need to kind of learn all these mapping functions you need to learn the omegas right and then you need to learn the beta vectors。

 the biases assigned like。That we need to kind of co estimate with these sorry with these parameters。

 okay， so we have a beta here。All right， so all these parameters we need to kind of optimize them right because of you know like we need to get we need to learn these embeddings so now let's look at this if you guys remember so this is you know。

Here we have the sigmoid function that will give us the final the label of node n and beta here is actually it's very it's different from the other beta of the the bias that we added for the node embeddings。

 this bias is the learner the learner bias so beta K here actually belongs to R it's a scalar and the omega here is the classifier or the learner parameters parameters okay the learner parameters for example。

 the classifier for using multilayer perceptron it's the mapping layer the weights of the MLP layer that we added that we added here okay so this equation is very important because what actually defined。



![](img/b76d46ab77b15edb0c461b3861cb2da0_25.png)

s is what we call here。 So I'm going to move it。 Let's move it a little bit up， okay。

So it defines what we call all the overhead， the head sorry the head of the prediction in the network。

 so the head of the prediction in the network so this is a node level prediction hat so a node level prediction hat it means that once I get my embedding okay so once I get my embeddings I'm going to feed them into a response another network or another you know small network parameterized by WK and beta K and here these two parameters they allow me to map this HK onto the final classifier so this is exactly what we do in linear and nonlinear classification so if you guys remember the pre in the preminaries section this is how we formalize a typical linear or nonlinear you know classification problem so we need to。

in ofLearn these parameters and by solving these parameters。

 we're going to get the final outputs Okay， so what are the parameters to learn。

 So this is a very important question， So I want you guys to think about。



![](img/b76d46ab77b15edb0c461b3861cb2da0_27.png)

This whole network， okay。And。including the prediction hat that we introduced here and you take a minute and you try to write down all the parameters that we need to learn okay so let's take a minute and think about all the learnable parameters that we need to optimize okay to be to get the final predicted label。

Why hat of note n and then we will compare it， of course。

 up with the ground truth for the final evaluation。 So to get this， you know predicted。



![](img/b76d46ab77b15edb0c461b3861cb2da0_29.png)

Output， okay？We need to optimize。

![](img/b76d46ab77b15edb0c461b3861cb2da0_31.png)

What exactly？So you can write them down one and two。

 and so you can write articulate them in terms of variables。Or in terms of yeah。

 so so let's look at this H and B so very good so we have here first we need to optimize the embeddings。

 right？So we need to optimize the embeddings。 So the embeddings， to optimize the embeddings。

 we need to basically。

![](img/b76d46ab77b15edb0c461b3861cb2da0_33.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_34.png)

So let's look at this so we need to optimize the h right so the h for each layer k for each layer k right so now to optimize this we will mathematically we need to look at the propagation rules So remember this will have this has two different components so we have the omega right1 to omega big K and we have also the beta1 to big beta K and these are here。



![](img/b76d46ab77b15edb0c461b3861cb2da0_36.png)

H that dimensional so yeah， so these are the two elements so we have biases。

And also the parameters or the weights， the weights of the transformation， okay， so the weights。

So the weights and the biases these are for you know the transformation that we are applying to the embeddings right so we're transforming them we're mapping them onto use sub spaces。

 as I explained before， so we need to optimize the embeddings and we need to optimize the learner parameters。



![](img/b76d46ab77b15edb0c461b3861cb2da0_38.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_39.png)

Okay， so what are the learner parameters here so we have two we have the omega K or WK here and the beta K which is a scalar so these these are different so this is an omega。

K here called and the scalar value beta K and this is a vector so this is the omega K here and we have hk okay okay and this will give us that this element right here which is calculated over there we add the bias and then we apply the sigmoid so you guys can see that we have loads of parameters to learn so we have parameters here to learn for each layer these are mapping you know big mappings that we're learning a lot of ways's a lot of biases in on top of that we add the learner parameters okay。



![](img/b76d46ab77b15edb0c461b3861cb2da0_41.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_42.png)

So now for edge prediction it's the same thing so for edge prediction how about you know like to learn so for the edge sorry let's look at this so for the edge prediction we have also a different hat so here this is called the edge level prediction hat so once we learn the。



![](img/b76d46ab77b15edb0c461b3861cb2da0_44.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_45.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_46.png)

Embbeddings of two nodes node M and node n for example。

 so this is node let's say M right here and this is node n and by calculating simply a similarity measure between them between these embeddings these learned embeddings and the final layer okay so here we should actually if we want to put the final layer should add a k here okay so if we want to make that precise and and calculating the dot product tells us about quantifies the similarity between these so as we quantify the similarity between these two embeddings we are able to kind of you know derive the existing of a link or another an edge so we can apply a sigmoid function to that and this will give us something between you know zero and1 so if it's very close to one it means well there is a link there is an edge between these two and if it's like close to zero then these are not actually。



![](img/b76d46ab77b15edb0c461b3861cb2da0_48.png)

Connect it so it's empty。Cool， now here what we have， so we have the embedding of。



![](img/b76d46ab77b15edb0c461b3861cb2da0_50.png)

Note， you know， M， and we have the embedding of node。

And and we do the dot product between them and we get this value。

 apply the sigmoid and activation function and that gives us the the final you know label that we want for this whether it's zero or1 Okay good so now the next question is that we understand that we have things to optimize right so we have all these guys to optimize we have the embeddings we have the learner parameters and we have all the transformations omega1 to omega K in addition to their biases so now the question is how to learn and optimize these parameters okay how do we actually。



![](img/b76d46ab77b15edb0c461b3861cb2da0_52.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_53.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_54.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_55.png)

Learn them。

![](img/b76d46ab77b15edb0c461b3861cb2da0_57.png)

So。This is important so if you have taken any machine learning course。

 you would know the answer so the answer starts with。A loss function。

All right so first you know after we design you design you to design your GCN layer and after you design your GCN layer with its components so we're going to see that in a bit in the other sections of this session so right here we're going to focus first on key components of the GCN layer and then we need to define a loss function to optimize and by optimizing our loss function minimizing our loss function we will be able to get the final optimal or suboptimal parameters okay some good solutions of all these parameters that we want to optimize okay。

So first we need to define a neighborhood aggregation function and we have seen a few and we'll see a few more examples later about how to aggregate because this is a very active research area in GA and so it's an active research area there are lots of variants and lots of alternatives and each one of them has each method has pros and cons and learning how to aggregate is what makes basically what makes use of the graph right because at the end we're taking you know a graph and。

We are identifying the closest nodes and based on these neighbors or these closest nodes we're doing an integration or an aggregation of their embeddings right so without this topology without this kind of local neighborhood we move back to a conventional deep learning model okay so this is very important now let's move next so the next thing after we define a neighborhood aggregation function we need to define the building blocks of a GCN layer or a GNN layer so here we by building blocks we mean we mean operations like how to aggregate the linear transformation the type of non nonlinearity that we want to introduce is a sigmoid a really a max you know like a 10h for example right so there are different types of nonlinear activation functions that we can use so we need to predeefine that and additionally we can add other things or other you know。

I think Bso we'll learn about that later。So now next which is the corrupt of this whole you know like learning paradigm or graphph neural network is like to define the loss and the loss is important for you know any optimization or machine learning problem so we need to define our loss function and for example we can use here you know binary multiclass cross entropy for classification and the least squares or or the mean squared error for regression so whether you dream classification regression and for classification the output will be passed through a sigmoid or softmax then we apply the cross entropy so here in this just a note in this section we will examine only supervised node and graph-based classification or regression but in a similar way we can adapt such formalization and steps to other learning tasks so we want such as for example edge prediction or unsupervised tasks so these are easy to kind of know adapt if you understand。



![](img/b76d46ab77b15edb0c461b3861cb2da0_59.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_60.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_61.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_62.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_63.png)

These fundamentals okay so now after we define the loss functions so here we will move next so we need to kind of define the prediction head okay so the prediction head is actually connected to the loss function itself so because you're doing we're doing graph based learning GN so you need to define your learning task so you have either note level prediction edge level or graph or you can combine all of these so that's even higher level but。



![](img/b76d46ab77b15edb0c461b3861cb2da0_65.png)

Here this prediction head will include additional hyperparameters or parameters I explained as I explained later earlier。

 sorry so we have， for example， the beta and the W or omega encoding the classifier bias and weights to learn okay so if you want to classify you need to add that and this is exactly what we talked about where is it so we need to zoom yes right here so this is the and our goal the loss function here if we want to use a simple loss so let's say we can do a cross entropy loss okay between simply the y and predicted and the y and ground truth label and sum of course we need to normalize with respect to all you know training notes okay so we can use a cross entropy loss here between the y hat n and the y hat n is right here so we can get it over there this is our prediction。



![](img/b76d46ab77b15edb0c461b3861cb2da0_67.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_68.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_69.png)

By the mapping of the learned embedding through W and beta。



![](img/b76d46ab77b15edb0c461b3861cb2da0_71.png)

All right， now， so going back to this。 now number 5 is。

Optimizing the loss so now that we have defined our loss function okay our prediction had that we're going to add to the GM to take these learned embeddings and map them onto a target output like Hawaii a label a target label or a target score for regression problems now we need to optimize the loss and to optimize the loss we're going to optimize the loss over embeddings and additional hyperparameter so the classifier weights and biases for example。

 like with learner weights if you're doing supervised learning and over the embeddings okay during the training on the training samples so we're going to use the training samples to optimize our loss as we do in you know conventional Ml and we can use usually we use you know gradient descent for example。

 the stochastic gradient descent regulars better is this better option so we can use stochastic gradient descent okay so here and when optimizing just to recall。

for the optimization we have different substeps and I assume that most of you know this so first you need to compute calculate the loss during the forward pass and then we calculate or compute the gradient of the loss using the chain rule during the backward pass so the forward pass you calculate your loss then you do your gradient and then here you use the update gradient rule or network rule to update the parameters so if you have your parameters。

 the total parameters let's call theta the parameters set storing the GACN you know like parameters and the learner or the prediction head parameters so all parameters will be stacked or like into a single theta vector and here if we have T。

So this is iteration T so if we use gradient descent so we take the theta t minus1 that was learned estimated in the previous iteration and then this is just simple gradient descent right and then we basically subtract the learning so this is a learning rate so all of you must know this okay so it's a learning rate and then we have the gradient of the loss with respect to the parameters theta T minus1 okay so this is the update rule and this is simple gradient descent okay so we try to kind of if this is our loss so let me。



![](img/b76d46ab77b15edb0c461b3861cb2da0_73.png)

So let's say maybe I'll draw something different so maybe something like this okay。

 so this is our loss we have theta here and if you have L of theta right。



![](img/b76d46ab77b15edb0c461b3861cb2da0_75.png)

We will start off with a first initialization， let's say theta  zero theta zero so that's the first iteration here and then you're going to go down over you know like down this basically loss function using gradient descent until we get to the optimal theta that's called it here theta store okay so that's a local optimum of course。

 especially if function is noncomvex or your loss is noncomvex but that's the overview or the gist of it of gradient descent and optimization so。



![](img/b76d46ab77b15edb0c461b3861cb2da0_77.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_78.png)

This first。Just to summarize these the first four elements。

They are based on definitions all right so you need to define predeefine all these or in your design okay of your TNN and then you do your optimization list okay cool。



![](img/b76d46ab77b15edb0c461b3861cb2da0_80.png)

Now let's take an example， I think it would be very exciting to see how this actually works。

 so now in this example we're going to look at a node multi。😊。



![](img/b76d46ab77b15edb0c461b3861cb2da0_82.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_83.png)

Regression。Okay， so a multi regression problem。A note multi regression problem using vanilla GCA。

So here I'm using this simple propagation rule that we also visited in lecture2。

 but we can use any kind of propagation rule without loss of generality this will apply to any propagation rule but for the sakeout for simplicity I will I'm using this one right here and what we have so this is the these are this is the learnable parameter so this is the mega I remove the bias here but of course we can add the bias so this is the transformation the transformation。

Prameterters or weights， okay that we will apply to the embeddings to transform。

The embeddings transformation weights and we have this is the the adjacency matrix so we have n by n adjacency matrix here and is a number of samples or nodes。

 we have D features so D features so it's D by n x stores for each sample here x stores the。

The initial feature vector， okay， the initialization of our embeddings， which we call H0。

 and then we have additionally the scores the targets score so。

Each node every node here so node I will have a set of C scores Okay so we have it's n times C so here we have C scores to store which means for example in this graph so here each node is annotated has an original measured or observed set of features that we want of course to transform through our network using the mappings through different layers right so that's how we want and the aggregation rules but additionally each node has a set of scores so for example。

These set of scores could be different numbers so 0。20。8 so this one will have 0。70。

5 etc cetera so here if we have two scores right so you're gonna have C scores stored here and this y will define the vector the feature vector right sorry this score vector for node I okay so this is for node so we can for node I if this is node node I now when we do the the the the propagation or the message propagation so remember guys we do self of course self aggregation here so in this case we are it's included in the I this is for self aggregation。

As explained in the previous lecture and then we start we have three layers so we have the first ring so this is layer one layer two layer three and we do we propagate these you know basically embeddings all the way down to to the to the I right here so this propagation rule applies as I mentioned aggregation transformation and non nonlinear activation okay so now we have this element new so the multiple scores so the goal here is to。

Train a network using these training notes。😡，And then we want to test it on unseen node。

 so we're going to have a node。Coming in， arriving at some point。And this note will have also its。

 you know， feature vectors， Okay， so it's features it's x here right here， so it's called。

So acts of node， you know， test。Okay so we'll have features。

 however we don't have the label so we don't know not the labels here so we're doing regression so we don't actually know the scores so our goal is to predict these C scores okay our goal is to predict the C scores for this node so to do so we need to train our model we need to do all of this okay so here as you guys can see we defined the neighborhood aggregation the building blocks is actually very simple we only aggregate and transform we have nonlinearity also using a function a that for example we can take the simple re or sigoid nonlinearity that we apply there are different kinds of nonlinearities we can apply and we have a loss function that we will define now so we need to look at our loss function so let's move up next so we actually reached here okay so now。



![](img/b76d46ab77b15edb0c461b3861cb2da0_85.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_86.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_87.png)

Minder。

![](img/b76d46ab77b15edb0c461b3861cb2da0_89.png)

So what we want to do guys is a nonlinear multi regression so nonlinear because we have if you remember in the review notes we call this app right so these are transformed features so our GNN。

Or GC Claire。Created， transformed。Features in a use space or in an ultimate space and this is what we call the embeddings the final embeddings right so in layer K this is the final layer。

Final layer。So now in this final layer。😊。

![](img/b76d46ab77b15edb0c461b3861cb2da0_91.png)

What we need to we need to kind of use these embeddings to optimize a loss function。

 so let's say we define a loss here， so let's take it one step at a time。



![](img/b76d46ab77b15edb0c461b3861cb2da0_93.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_94.png)

So with the final loss function， this loss function minimizes you know squared distance between the transform features in the target score so this is exactly the a typical or conventional formalization of a multire model okay so we haven't changed anything here。

 the only thing that we did is we plugged in the learned embes and the final layer of the GCN model okay so HK goes in here and this is how we calculate HK using the propagation rule right and you can trace it backwards to the very first you know so we're going to have an a multiple transformations and guided by the topology of the graph guided by the topology and periized by different layerwise or layer specific transformations all the way up。



![](img/b76d46ab77b15edb0c461b3861cb2da0_96.png)

2K minus1 okay so this hK requires the learning of all of these omegas right all of these mappings and here basically what we are doing is like we're we're taking the regression model so this is the regression model transformation the W and the W has this dimensionality so let's start from the beginning so we have here。

HK belongs to n times DK n is the number of nodes， right in our graph。

And then we have the final embeddings and the embeddings have dimensionality decay so this is a dimensionality of an embedding okay and the final layer so it will have DK elements or DK values here and then on the other hand we have our multi linear mapping。

Function okay regression matrix where for each you know of these basically vectors we are mapping as I explained before so we're by through this multiplication we' we're mapping you know all of these nodes onto onto a particular you know score so we're predicting the score for each of these nodes through a shared mapping so this is a shared mapping for score one so we have one score here and we have C scores and by doing this multiplication so the first one we get us this predicted value right and then for the first score and then if we do for the last score so we take this one again and we multiply by the last score we're gonna get this element right so we're predicting the y hat so we're predicting for each node okay so let's do it for each node we are predicting its。

Target scores Y hat okay so this gives us eventually a final matrix and this final matrix here we will have n times C so n times C matrix and in this n times C matrix we will store all the predicted scores for all nodes in the training graph。

 So we're storing we're actually predicting all these values Okay so right here for this particular graph Now let's look at this again So here what do we have。

 we have the predicted scores so we do the mapping we get the predicted scores and we compare them against the ground truth So as we compare them against the ground truth we were gonna we will this will define our actually loss function。

 So here y hat this is y hat and our L of theta is define like this So y hat the matrix Okay minus the ground truth scores and this is we're going to minimize this。



![](img/b76d46ab77b15edb0c461b3861cb2da0_98.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_99.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_100.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_101.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_102.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_103.png)

Over theta Okay， so the theta stores all network parameters。 So what are the parameters here。

 So if we write them down。

![](img/b76d46ab77b15edb0c461b3861cb2da0_105.png)

We're going to have the W of course， so here we have this matrix and we will have so that's the prediction head right in the learner parameters plus plus others okay other parameters of the Gna so this is for the learner prediction head。

And we're going to have a set of parameters for the network。

 the GNN parameters and using this propagation rule， we only have omegas okay。

 so we sim things so we're going to put all of them here so from mega1。



![](img/b76d46ab77b15edb0c461b3861cb2da0_107.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_108.png)

O米ga 2。All the way down to the final here， transformation k minus1 that will map you know layer k minus1。

 the features in layer k minus1 or the embeddings to the embeddings in the case layer okay。

 so we generate HK and this is how we get our input。



![](img/b76d46ab77b15edb0c461b3861cb2da0_110.png)

Features to the multi regression model that we have right here so you guys can see so things are simple they look simple。

 but the theta here is huge okay， so it's a huge optimization space that we have。



![](img/b76d46ab77b15edb0c461b3861cb2da0_112.png)

So basically to get this HK we need to optimize all the mappings from layer to layer from rank to rank in the graph and additionally we need to optimize the regression you know kind of transformation so it's a lot of parameters and this is why graph neural networks or deep learning are very heavy to train because you have all these you know high dimensional parameters that you want to optimize and here you have DK times C youll have different dimensions for each of the omega right for your transformations so we have multiple parameters to optimize now once we get the theta star the optimal parameter right so after the optimal we will we will be able to we're gonna get all these you know hats optimized you know final ones okay or maybe it's better to say if they are optimal we're gonna put a star for the optimal right and that's how we will actually。



![](img/b76d46ab77b15edb0c461b3861cb2da0_114.png)

cThe HK here。 so we're going to get the embeddings。

 Everything will be expressed and calculated in the network。 Okay。

 no we have seen we tick multiple boxes。 so let's look back so we have defined all of these the loss。



![](img/b76d46ab77b15edb0c461b3861cb2da0_116.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_117.png)

And now the last step is the optimization so we're going to look at the final step now we define our loss function。

 we formalize our problem， we define our propagation rule。

 we define our layer operations and we formalize everything mathematically beautifully and now we need to optimize our loss so our goal is to actually do this minimization and。



![](img/b76d46ab77b15edb0c461b3861cb2da0_119.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_120.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_121.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_122.png)

To optimize theta。 So how are we going to optimize theta。



![](img/b76d46ab77b15edb0c461b3861cb2da0_124.png)

Now we've come to the final step of the training of a GNN model， which is the optimization。

 so in the optimization we will you know use， for example。

 gradientding descent or stochastic gradientding descent。And what I want you to do here， guys is。

To take a minute to think about。This， I want to actually imagine this。 All right。

 so I want you to kind of simulate this。In your brain， what is actually happening here。

 what is learnable， what is fixed， what is， what are the update rules。

 So I want you to kind of simulateimilate the changes that happen to this graph。😡，Okay， right here。

And this one okay so this， you know， this is， you know basically here we're going to plot the two so two scores。

 so we will assume that we have two scores， so C will be equal to two so we have two target。

Outputs of the network and our multiline regression problem so we have the first the optimizer。

 the optimizer iteration so here i'm gonna to keep it simple so i'm not going to go into details and talk about epochs and stuff like that so i'm going simplify things and we're going to talk about these later on more advanced kind of tools that we will use but right here we have our gradientcent rule very simple we have the parameters we want to update the parameters and get the theta here T and this update rule we're going to use it starting with T you know the first iteration to the final iteration big T right here and this is when we have you know kind of you know the optimum hopefully theta star okay so we're going to stop there and our loss has convert so usually when you have a loss function remember。

So if we plot the L of theta， okay， and these are the number of iterations。



![](img/b76d46ab77b15edb0c461b3861cb2da0_126.png)

So if I zoom here a little bit so we're going have something like it so the loss at the beginning when we have a theta first you know like theta zero will have a very large loss and somehow you know as we optimize the loss will start to stabilize and you can see here that the loss is stable so we can actually stop the optimization so it's not moving anymore and then different ways of stopping this so we're not so they're very simple actually so you can set the number of iterations or if the change in the loss is not big anymore which means it's stable right so the gradient is flat here like you don't have any changes in your loss so then you can stop right your' optimizer so this is you know in terms of optimization so let's do the simulation here so。



![](img/b76d46ab77b15edb0c461b3861cb2da0_128.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_129.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_130.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_131.png)

So there is a beautiful reminder I want you to recall from also the previous lectures。

 so what we have seen in lecture too is that through the optimization we aim to find an ultimate an ultimate low dimensional representation space so this ultimate space is a much simpler manifold like linear models can work well on the final embedding okay so which means when we have our final embedding HK。



![](img/b76d46ab77b15edb0c461b3861cb2da0_133.png)

When we apply a linear multi regressiongress model thingss should work there Okay。

 so a linear model will fit the data nicely compared to the original data which is highly non nonlinear and complex Okay so this is basically in this space So this kind of influences or expresses what should be happening in this space as we optimize okay now the second thing I want you to think about what happens to the graph itself what is learnable in what is fixed so let's take few minutes here guys so i'm going to pause and I want you to make a drawing and simulate this and think about these values。

 so let me explain here one one more thing so these are the predicted values Okay so here this is the why for example for the first why。



![](img/b76d46ab77b15edb0c461b3861cb2da0_135.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_136.png)

For node I， okay， so it's called for node I。The Y hat。 and then we have。

The ground truth for node I so this is ground truth and this is prediction okay by the network so every time the network will predict why this you know basically okay based on the embeddings that we're learning based on two hyperparmeters that we're optimizing two big ones I mean there are lots of hyperparmeters but mainly the w and the omegas that control the HK all right Co so let's take here just a few minutes and I would like you to simulate this and make drawings and imagine the changes in the values what happens in the predictions here when we start off in what happens to other stuff right so what is what is actually being updated and what is fixed in all of these elements all right and then you can also make a drawing here of an initial distribution of the data so this is the input right and then we have the output right here。



![](img/b76d46ab77b15edb0c461b3861cb2da0_138.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_139.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_140.png)

As a Y axis。And I want to make a drawing okay that shows what is actually happening。



![](img/b76d46ab77b15edb0c461b3861cb2da0_142.png)

So。Okay， so let's imagine together so first I would like to remind you guys that each vector here represents the embedding the learned embedding and the final layer layer K of node I for example Okay so we have note I here all right now let's start from the beginning first。

If we look at these embeddings at the very first iteration so we will randomly initialize this so that's the first thing so let's so let's take one step back so first let me ask a question so here what is learnable and what is fixed so number one。

The fixed elements， what is fixed？The fixed elements include the a， which means this graph， okay。

 these edges right here， they are fixed， they do not move。Also the why the why ground truth， okay。

 it's also fixed so these two。Are fixed here so what is moving what is dynamic about this network is the embeddings Okay。

 so we are learning the embeddings Okay， of course here we're going to have the x at the beginning。

 so i'm not showing the first flare so x is equal to h zero right so。



![](img/b76d46ab77b15edb0c461b3861cb2da0_144.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_145.png)

Sorry so yeah so h is equal to h zero it will be included。

 but here we' i'm not showing it because I wanted to focus on the final layer why i'm focusing on the representation or the embeddings learned in the final layer because we're going to use these to do the the class the regression right for as to input into the prediction head all right now。

The the embeddings are learnable so this is learnable so we need to update this these need to be updated also the predictions they are learnable so they need to get updated so let's start with the bit from the beginning so let's say for example at the ground truth here i'm going to put two values i'm going to put here for example one five23 and 65 okay so i'm going to repeat this one5 os。

So these are the ground truth values so we have two values okay2，3 and then we have6。

5 and we want to predict these okay so we want to predict these values through optimize by optimizing the the model over the embeddings and all the parameters on the training set so these blue notes all of these are our training notes Okay so we have here training notes and these are our training notes all right now for the embeddings because they are learnable we need to kind of。

Initialize right so we need to do some initialization and to initialize them we need to initialize of course omega1 to omega k minus1 okay so all of these need to get randomly initialize or there are different ways it's a big research topic but let's say we randomly set the values of the omegas that will give us the k the final K through the propagation rule right so if you remember through the propagation rule we're going to get this final hk so here we need to initialize all of these omega so after we initialize them。



![](img/b76d46ab77b15edb0c461b3861cb2da0_147.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_148.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_149.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_150.png)

We're going to have eight values right here so we're going to have some。

 you know kind of different values all right of our embeddings for each node and these are random values right so somehow because at the beginning the network is not learning anything the omegas these omegas these mappings。

 these feature transformations or embedding transformations that completely random okay so they're not going to give you something we're going to be happy with so when we plot the values when we project these vectors so now we're going to do some projection here so let's take different colors so we're going to take this color okay so here when we project these vectors onto this space and show the relationship with respect to y so let's say you know each sample here will have different values okay and we're going to have maybe something like this so this is you know。

 I don't know。Something really funky so the first embedding will not maybe make sense。

 so this is one single score and if you have a different score of course you're going to have you know a very。

A very interesting relationship with respect to that score So here let's say we have you know a single score in we want to plot these embeddings so in the beginning you're going to see something a bit fununkky a bit random maybe unstructured so I should maybe make it a bit more kind of spread out so oops I change color I should not change color so here yeah so something like that so something that is not very reasonable okay so these embeddings are not good because they are because they are generated by a random transformation although we are using remember we are using the graph structure to do the aggregation right based on neighbors the graph structure may be good and it is fixed so it's not random here still the transformation of these embeddings is random so we're gonna have something completely random and then as we optimize as we optimize。

Things will start to make sense so first let's look at the second variable what happens to our our y here so first we're going to have a very large error so if we do so let me redraw this okay。

So here we want to put our loss function， so like here， so this is our loss。And at the beginning。

 our loss function of theta， the first theta if we have the first you know theta is zero right we're gonna to have really very high loss so everything is messed up it means like we're not were not predicting well so we may have seven here we may have eight there15 you know23 so the error will be very large because the distance between the predicted vector and the ground truth one will be very high so your loss is very high here and as you optimize your theta so you're going start from you know like of theta zero and then you're going to move down and you're going to have you know as you iterate you're going to have a better theta at some point t right so you're going to have you know a decreased loss right here so this loss is very nicely decreased and you can see that somehow you started over this optimization right you started to get very good values so hopefully at the。

End of your iteration where your loss stabilizes and you have your theta big T。

 So after T iterations， your HK right here will will have will will kind of。

Have a very good representation of your data so it will transform your complex data so let's say the original data that we had maybe looked like this So we plot the H0 which is here ground truth right so the H0 is the x so let's do that using different colors right here so I want you to imagine this too okay。

So the original data maybe has something like this。Okay， so here this is the original data。



![](img/b76d46ab77b15edb0c461b3861cb2da0_152.png)

And when I say original data， it means we have。We plotted here H zero。

 which is equal to x the original features right the original embeddings so we can easily kind of you know maybe。

Have an nonlinear model fit to this， right？However， we want to transform remember。

 our goal is to transform everything onto a new representation space where we use the new representations or the new embeddings where linear models can work so using Hk。

 what do we expect here we expect that these embeddings now so i'm going to use the same color Hk after optimizing the model at this stage we have a very good representation there。

 so basically when we plot the。You know， the embeddings of the final layer of all our training node。

 okay， these are the training nodes， right？And we predict a particular score now we can easily fit。



![](img/b76d46ab77b15edb0c461b3861cb2da0_154.png)

A linear model。 and this linear model right here。This linear model is parameterized by the matrix W that we have here。



![](img/b76d46ab77b15edb0c461b3861cb2da0_156.png)

Okay， so that's our matrix w that transform that fits in the data that's our regression model and if we have of course multiple scores we can add other scores as you know illustrated in。



![](img/b76d46ab77b15edb0c461b3861cb2da0_158.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_159.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_160.png)

The preliminary lecture so it's not too difficult to do so you can imagine you have a second score with different distribution and now if you're gonna write the values so what kind of values we'll have here hopefully if we optimize and we got a good you know optimization of our loss function and a good estimation of our parameters theta star for T the final iteration T then we're gonna to have very good prediction so the predicted value here versus the ground through should be very close so maybe we'll have a 0。

8 will have a four here we have I don't know maybe 2。1 3。

56 well maybe nine here we made a big error here somehow for some reason we need to understand and debunk basically diagnose the training why we made these errors okay good so this is the overview and I hope it is kind of clear and there was there is a lot of background music I would say that we cannot hear here the optimize。



![](img/b76d46ab77b15edb0c461b3861cb2da0_162.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_163.png)

for me is like a conductor right like it's not just it's the conductor that kind of manages all this kind of orchestra。

 the orchestra is basically all these players， all these neurons that trying to kind of get out the right tone get out the right tone it means optimize the right W for each neuron we want to get the right weight right the very optimal weight and imagine all these neurons。

 each one of them getting a note out and this note if you combine all of these together right you're going to get the final tone or melody that you want the perfect one that is very close to your ground truth right so your optimizer is like a conductor and you have the composer which is you know。

All these neurons that trying to compose their own tones and optimize their parameters and it's a huge orchestra if you think about it because you have millions of parameters and you know thousands and sometimes thousands and thousands of neurons that trying to fine tune and get the right activation and the right value for you to be able to finally get this you know simple vector out here isn't that amazing right so so yeah so that's you know that's you know how we do optimization here and now let's look go back to this to this you know table so basically we optimize the loss now we got our theta star right after it after several iterations training on minimizing the error over the training sample so here it's the Y train minus the Y hat train okay so of course we're using the data set。



![](img/b76d46ab77b15edb0c461b3861cb2da0_165.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_166.png)

イ。

![](img/b76d46ab77b15edb0c461b3861cb2da0_168.png)

Then we're going to compute the so we did all these updates and now we need to do the testing Okay。

 so we need to test so the next step will be to test our network so let me remove this from here。



![](img/b76d46ab77b15edb0c461b3861cb2da0_170.png)

OrActually maybe keep it over there so just for the notes， okay， let's keep it。



![](img/b76d46ab77b15edb0c461b3861cb2da0_172.png)

All right， so testing now here is a question for you guys。



![](img/b76d46ab77b15edb0c461b3861cb2da0_174.png)

How do we do the testing here。We have basically a new note coming in， so this is a new note。

We want to predict for this new node， Okay， so a new node arrives and we want to predict it's。

Target scores， okay， so it's a multi regression problem。

Have multiple scores we have C scores to predict here。And these C scores now the the。

Testing node comes with its X test， which is the feature。

 the original features right X test so we have the feature we have you know the node itself and we have the the scores are missing so we need to predict the scores Now the key question here。

First， the first thing because the node will come isolated so it will have its own kind of you know embed not embedding original feature and it will be isolated from this so one idea is to try to connect the testing node to other nodes okay so we can use for example the dot product or a similarity measure to connect it and see that well based on the closest you know we select the K nearest neighbors okay so here we connect it to two nodes and you can or we have a threshold maybe so we need a strategy to connect the node so we connected the node and you can see that we added it to our graph right now。

The question here is， how can we predict。The scores of the note。Remember guys the prediction had。

 so I want you to。You know just take a minute and think about it if you have taken notes or you can go back and check you know the beginning of this video and see all the equations that we've written down hopefully you're taking notes and you should be able to derive that by yourself okay without me revealing the the results do or the next steps so here I give you a hints so we can connect let's say we connected the node and then what we want to do is we want to predict the why so how can we do that now that we have trained our network。

We have learned all the parameters， we have learned the theta， so we have our theta star。

That is that has the， you know， the set of omega1 to。Omega k minus1。

And then also the multi linear regression matrix， all of these optimized。

How can we do the prediction so let's take a minute。

 I want you to kind of pause and take a minute and think about this and write it down。

So here first after connecting the node let's look at the solution so it's actually very simple so the first step is to as a forward pass through the TNN layers and the prediction hat so first we need to forward pass or pass the original features so the original features are these guys okay so the features of the test node so we take its feature vector and we pass it through the GCN layers which means the omega mappings right to get the final embedding of the testing node so this is what we call the inductive node embedding so we're inducing the node embedding we're inferring the node embedding and we pass the original x0 right of test。



![](img/b76d46ab77b15edb0c461b3861cb2da0_176.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_177.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_178.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_179.png)

![](img/b76d46ab77b15edb0c461b3861cb2da0_180.png)

Through the all the optimized， you know network mappings， right in this case。

 using the simple naive GCN right model。K -1。 And then this will give us the H K for the test node。

 right， So we're gonna to get the embedding of the test node。

 And once we get the embedding of the test node。 So this is the test node。 Okay， so this is the test。

Note and we have its embedding right， we're going to simply map it or project it using the W。

 So this will give us。You know the W star here the optimize multi regression mapping right and then when we do this multiplication we will get simply our predicted scores right here so we get our predicted to so here we pass it through the final MLP layer or the prediction slash our right if we do mP or multilayer perceptionceptron or the prediction had to be more accurate okay the prediction。

Head， okay， good。 now we get the predicted values right here。

 So these are the predicted values Y hat or node test。 Okay， so it's a vector and it has， you know。

 C values。 So C。Outputs or see output scores I' would say output scores。

 and we hope that these will be close to the ground truth。 So this is， you know the ground truth。

 So now we reveal the ground truth because we want to evaluate the model So after we predict we need to evaluate and to evaluate we can simply calculate the MSE the either the mae。

 the mean absolute error。 So the mean absolute error would be you know y minus y hat for node。

 for example， the testing node I Okay so we take a simple。



![](img/b76d46ab77b15edb0c461b3861cb2da0_182.png)

A difference here or we take the mean squared error where we actually we squared this okay？Great。

 so these two different evaluation measures that we can use to evaluate the quality of our prediction and if we do very well at predicting you know the values right here。

 so now we can look at the ground truth that we have and we compare our prediction and we see we can then evaluate okay we can evaluate the generalizability。

 generalizability of our model。

![](img/b76d46ab77b15edb0c461b3861cb2da0_184.png)

Our GNN model。Okay， two unseen data points， okay， so the data points here are actually nodes。

All right， cool now。😊。

![](img/b76d46ab77b15edb0c461b3861cb2da0_186.png)

I'm going to ask you a question also another question before we hit the second part。

 but I'm going to leave you with this and then we will hit the second part。



![](img/b76d46ab77b15edb0c461b3861cb2da0_188.png)