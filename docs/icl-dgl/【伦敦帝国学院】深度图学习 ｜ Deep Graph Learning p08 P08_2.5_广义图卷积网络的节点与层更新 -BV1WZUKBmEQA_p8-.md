# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p08 P08_2.5_广义图卷积网络的节点与层更新 -BV1WZUKBmEQA_p8-

All right。Over back。So in this section， we're going to examine the note embedding update rules and we will go over this in detail。



![](img/b5860e808f9ad2c068642b1e8a2339af_1.png)

And we will wrap up with a simple example on graph classification。

 so let's start first with the the simple graph node base embedding so this is a simple graph CNN layer so when we use。



![](img/b5860e808f9ad2c068642b1e8a2339af_3.png)

When we try to embed these graphs so we have first the graph structure that we define。

 which is the a encoded by the a matrix， and we do have also here the node embeddings which are initialized using the original X features。

 so we have these embeddings for each node in the graph。

So next our goal is to learn a simple embedding of these nodes so we want to learn for each node n。

 we want to learn an embedding and H1 one is here it denotees the number of layers so this is a single transformation the first transformation number one and as we do that we will learn how to represent or embed each of these nodes by leveraging the graph structure and introducing also biases and nonlineity activation function A right here okay so this is very similar to a fully connected deep neural network。

 the network that I introduced at the beginning of the session and let's look at the difference here。

 so the notes the caption reads as follow so。

![](img/b5860e808f9ad2c068642b1e8a2339af_5.png)

Each note each note in the first hidden layer is updated by number one。

An aggregation rule where we aggregate the neighboring nodes to form a single vector， so for example。

 if we take， let me give an example here， so if we take node one all right and we want to get H1 for node one。

We need to aggregate the embeddings of you know the the neighbors of this node。

 so the a of n here actually it denotes the indices。Of。Neighbors。Of node n and in this case node one。

 So if we look at node one， we have three neighbors， so as we aggregate we add ups。

 which means we will take these three vectors and let's call them here you know so H0 of this you know node 4 plus H0 node5 and h03 Okay so we added them all up and we're gonna get a final aggregated vector here。

 let's call it tilde all right for this node and later on we will apply a linear transformation Okay so we apply a linear transformation omega0 So this aggregation happens here。

 but then we apply a linear transformation so we transform this vector h0 so through a。

Matrix omega02 learn， so we multiply it。And。This is the transformation so we're transforming the aggregated hidden embeddings of the neighbors of node1 in this example right and we are creating a new representation here okay so that's a new representation for the neighbors so here we can call it H1 this is you know for this current you know this current layer and this is for node1 but only the neighbors so these are for the neighbors all right and then we're going to add we need to apply the same linear transformation so the second part is to apply the same linear transformation omega0 to the original node so this is what happens here so basically we take this omega you know this mapping or transformation matrix and we apply it also to the local embedding of that we have right here so if we started with H0 so x1 here as the。

Original one， so I called it H zero because it's the original。The original features。

 so in this example it is x1 of node n and if we're using node one so we're going to put node one and you can see we're applying the same transformation。

So after that what happens is that we're going to add them up so we take the transformation H1 that was the output from my neighbors plus the self transformation from the node itself and these two okay so I can call it here myself all right and then these two we're going to add them up so we added them up here and this term and we will get it will get us a new vector let's call it this is the vector H。

One layer one of node n and here n is equal to one So of the first node so this is the final updated embedding the final updated embedding it takes into account the self embedding and transforms the self embedding of the previous layer and it aggregates the embeddings of the neighboring node so these are the two most important operations that we have and after that if we want to add a bias we can also add a bias if we think that you know we'll have some bias in the data so in the feature distribution so we can add a bias and this is basically adding these all these together with a bias beta zero and finally we apply the final non nonlinear activation function a such as relo and this is the activation function so relo just to recall relo is actually max f of x so if we write it down。

呃。All right， so this is the last part， so I'm going to expand so。Relo F of x equal max。0 x。

 all right， so now the last part， so after we take all this， so the last part is actually。This。

 you know。The final the update that we're going to have in the next layer， so this update is。

Described here so this process is repeated at consecutive layers and in this example we will have different parameters for each layer so remember we're learning the omega here。

 the first omega zero we're gonna have omega1 here for the second layers so it depends on the number of layers so after so many layers we're going to get this formula where we have you know the mapping from K to K plus1 this is the transformation linear transformation that we're learning and then we're doing the aggregation of the notes in the previous layer and we're updating the embedding so we propagate this we repeat this same basically operation over and over again to produce the final embedding at the end of the network all right so this is very also similar to simple deep learning but the key here is that we are using this structure of the graph the adjacency matrix to pick out to identify the neighbors and remember。



![](img/b5860e808f9ad2c068642b1e8a2339af_7.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_8.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_9.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_10.png)

The goal of the adjacency matrix is to tell us who my neighbors are if I take node I and I look up this column right it will tell us that I am connected only to this node right so that's called this node j so I have only one connection from I to J in this graph for example right so this matrix is so important because this column right here it returns it gives me I can get from it the indices all right of the neighbors the neighborhood the indices of the neighbors so of the neighborhood of node I okay so these are the indices of all nodes that connect to I in here will have J for example。



![](img/b5860e808f9ad2c068642b1e8a2339af_12.png)

All right now let's look at this in a more detailed way so like in a more kind of mathematical linear algebra way so I erase what I have what what I drew because we will have better representations here so the note embedding update rule so we have here the full。

😊。

![](img/b5860e808f9ad2c068642b1e8a2339af_14.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_15.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_16.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_17.png)

Proropagation rule Okay， so this is the embedding rule。

 but also this is the message propagation rule from one note to other node and then we have activation so we have basically the propagation let me add it here so this is。

The message propagation。All right， and it has two parts so this message propagation here has two parts。

 so let's summarize these mathematically。 So first we have a so we're going to start with this first part。

 which is the。

![](img/b5860e808f9ad2c068642b1e8a2339af_19.png)

Self。Self update。So you're going to update your own embedding。

 so we take basically the mapping matrix so mega K， so this is the mapping matrix of layer K。From K2。

 as I mentioned， this transformation it。Takes us from K to K plus one because here we want to get the update of the embedding at layer K plus one。

 so how are we going to calculate this So first we need to take to do a selftrans which means you know a self update so I take the HK of this node and we update it through we transform it through the omega K right so this is a transformation。

Allright， and now we have a second part， which is the。

So this this happens here so we have the Hk of n right and we multiply it by this matrix so this matrix is very important because what are the dimensionality of this matrix omega K so omega K basically defines a new space so we have the output embedding size so for example if we have we can have d prime times d so this is you know let's call it d actually the original so the output it should be dk plus one so that's the output the size of the output embedding and times input embedding size so the dimension of the input space。

 the input embedding space all right so this is the dimension of ga K and Hk will have the dimension dk times1 okay so it's a vector that we have the embedding of the node in the previous layer all right so once we do this multiplication we're gonna get the self update。

Which means I will update this value right here by doing this multiplication and I'll get。

 as I explained earlier， an updated okay， so here that's called H。You know。

 K plus one n and then self itself self update。 All right， now the second term is。Neighborhood。

Neighborhood update aggregation。So this is self aggregation you can think about it and this is neighborhood aggregation so here we take the neighbors so here aggregate it takes all neighbors you know of this you know of node n okay in the current layer so we identify all neighbors and we aggregate。

They theyre embedding so here basically we do an aggregation so let me explain the aggregation first so the aggregation takes these these embeddings hK for example。

 node for example， I hK node J and I and J。Are in neighborhood of n okay of note n so we add them up we're going to get an aggregated or summed up。

 you know like。Ebedding， so H itll become， let's put it K plus one and this is N and neighbors。

And then we need to transform them so I'm going transform this through mega so I'm going to transform the aggregated message through omega so this aggregation。

 let's look at it mathematical formula in detail here so basically we aggregate the embeddings across neighbors so this is called message aggregation a message aggregation across neighbors I'm going to use a different colors so here message aggregation across neighbors so we take all of these you know all embeddings of every single neighboring node M within the vicinity of N and we sum them up so that gives us a final vector and this is the vector and we apply mega so we transform it so now the linear transformation is important this transformation so the first part is basically aggregating across neighbors so we allow to kind of for self aggregation and neighborhood aggregation so this is where we leverage。



![](img/b5860e808f9ad2c068642b1e8a2339af_21.png)

Structure of the graph all right and then we apply what we call the transformation mapping the same thing that we've done in deep learning or in even in linear regression we learn the w right so we learn the mapping function for that node omega and then the node and also it's aggregated。

Neighbooring embedding so when we apply omega here。

 so I'm going to write it and let me try to keep the same color。The omega K。All right。

 so we multiply it by two things， so we multiply it by you know the what I called the H and self all right。

 okay。Actually， we should put here okay， so we can transform later。I'm going to put here K。

 all right。And then plus， okay， so we will add also H and neighborhood and E。

And we're going to transform both of them so is this transformation acts on both of them。

 so basically a combination acts on the combination of the self embedding and the neighborhood embedding all right and so let's look at that mathematically so here we have we go back to our equation so we this is the first part the self you know kind of aggregation or self updateate and then the second part we take the same omega K right and it has the same dimensionality so i'm going to kind of duplicate this all right。



![](img/b5860e808f9ad2c068642b1e8a2339af_23.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_24.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_25.png)

And then here we'll get the aggregated。This is the aggregated actually the HK of neighborhood in the node A and it's aggregated。

The aggregation across for neighbors sorry all right so we got there finally we got there so yeah so basically this is so important you can see that the transformation acts on on you know like on each node itself and its neighborhood so this is the action of the linear transformation and this is why it can act on any any node of any size because it's thanks to this aggregation this aggregation will allow us to create a mapping a transformation to transform。

😊。

![](img/b5860e808f9ad2c068642b1e8a2339af_27.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_28.png)

Any node？With any neighborhood size， with any N neighborhood。Size all right。

 because we're summing them all up right where we're kind of you know condensing them all into single vector。

 So now one thing that we need to add here is the dimensionality of course。

 so this dimension is d times one all right and then we transform it and then we're going to add a beta the beta here。

Should be of the dimension， so we're going to add it up so it should be also decay。

Times so here we have it so we have yeah so the final which of the dimension of this multiplication so what is the dimension of this block so it's actually these will cancel out so we'll have decay plus one。

And that's it So times one。 yeah， so it's a vector。

 so it has the size here of the beta K the biases will be the bias vector will be of the dimension of the output embedding a space and we will learn a bias for each。

For each embedding feature or dimension all right， so after we do that we apply the a so we we're going to apply the a for every single。



![](img/b5860e808f9ad2c068642b1e8a2339af_30.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_31.png)

At each position here， so when you get the final vector， so if we sum all of this up， all right。

 we're going to get a。

![](img/b5860e808f9ad2c068642b1e8a2339af_33.png)

And we apply it to the final vector here。Which belongs to art？

DK plus one times one and we apply the activation to each input individually and then we're going to get the final embedding the output embedding of the of note n right and it has been updated and this is basically the H。

It's the hk plus one for node and this guy right here so this is exactly how it works and you can see that you can understand the math beautifully it's not difficult to pin down and it' actually very intuitive because when you are updating the node embedding first thing and you you're going to consider so you're not looking at。



![](img/b5860e808f9ad2c068642b1e8a2339af_35.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_36.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_37.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_38.png)

The self embedding the individualistic you know approach where you just focus on yourself right so this has been the approach of deep learning and other conventional ml methods。

 but the new thing here is that this part this what makes。



![](img/b5860e808f9ad2c068642b1e8a2339af_40.png)

This layer， a graph based layer。 if we remove this。

We go back to a simple neural network or a simple MLP multilayer perceptron or fully connected network is a typical conventional deep learning model so this part is what makes this network you know graph base because we're doing the aggregation base on on the a matrix that we have and yeah so that's that's the difference between a simple ann neural network and an a GNN or a GCN here in particular good so now let's look at this in total so here and this example we have looked at the node you know like just the this rule。

 the update rule at the node level so it's a node embedding update rule now we're going look at the update rule for all nodes all right now so that this is also very simple so let me just move this a little bit if I can。

😊。

![](img/b5860e808f9ad2c068642b1e8a2339af_42.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_43.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_44.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_45.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_46.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_47.png)

So let me just。You guys bear with me a little bit。Here we go。

Because I don't want to lose this annotation。And we can put it here on this side。



![](img/b5860e808f9ad2c068642b1e8a2339af_49.png)

All right， and now we can get to this。A that we' all generalized across。



![](img/b5860e808f9ad2c068642b1e8a2339af_51.png)

All notes。 So let's see what happens when we do this across all notes。 Allright， so all notes。

 so it's very simple。 actually， we do stack the embedding。 So before we wrote this， you know。

 this formula for a single note now we need to kind of propagate it or like generalize it across all node so we can stack up all the embeddings so we can。



![](img/b5860e808f9ad2c068642b1e8a2339af_53.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_54.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_55.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_56.png)

Ororizdentally I vertically stack up all the embeddings here。

 so we put them side to side embedding of node one node two ettera。

 so we have the number of nodes right here in this H matrix so H belongs to dk plus1 times n okay so R dk plus one times n so number of nodes the output embedding size and then we're going to apply the same thing so we have the activation function so which is the a and we will have the beta but let's look at the aggregation so what has changed here so first。



![](img/b5860e808f9ad2c068642b1e8a2339af_58.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_59.png)

We're going to look at the the self encoding and the neighborhood encoding so for for the self encoding the first part here。

Let me just use a different。Color， so here we have the self encoding part and in the self encoding part。

 we have basically。

![](img/b5860e808f9ad2c068642b1e8a2339af_61.png)

This， you know， the transformation applied to all node embeddings， so we take all node embeddings。

 the H matrix here， which is HK。Actually， I flip the colors。

So here I will try to fix that in the notes guys if possible。

 so here this is actually this should be pink so I don't know if I can change this。

 so i'm going to make it pink。All right， and these guys are actually blue。

All right now things are a bit messed about， but you can see the order。

 so it's easy to see the order， this is the omega K。All right， and this is the H， actually the HK。

Cool and then we have the hk here again so in this part we do the same things just you know in this multiplication we are transforming the embedding of each node so we go over all notes and let's look at the dimensionality here so we have the dimensionality is。

DK plus1 times dk and then we have here input embedding size so dk times n。

 so the total size is actually this gives us Dk plus one times n okay so this is the first block so here omega K times hk so this is a dimensionality and we learn the self embedding for each node basically this is gives us the self updatedate for each node and we do the same for now the neighborhood encoding so now we encode the neighbors and what we add is remember guys we have the aggregation before for each node so。

If you look at this this tells us the neighborhood of a particular you know who is connected to who so this gives us an E of node for example n all right so this is node n over there and we've done this for each note individually now we're just stacking up all these neighborhoods right and these are。

This will give us the adjacency matrix by default fault or by definition。

 and we will do the aggregation here so this operation right here it does it aggregates the notes。

 you know the neighboring notes。For each。Notode okay and then we do the transformation through omega so let's look at the dimensionality here。

 so we have DK times n n times n so the output here should be D times sorry plus one there is plus one here。

 so let me write it again。

![](img/b5860e808f9ad2c068642b1e8a2339af_63.png)

Actually yeah it's decay that's correct it's the input size yep so d times one that's right and then this is the matrix that we're going to get and then we're going to multiply it again by Dk plus one d so this will give us also something of the order of you know like an R。

DK plus one times n all right， and yeah， so this is the output and now what we need to do is basically。

This will give us a matrix so here we need to do we need to create another matrix so we will take the biases so the aggregation self encoding and the neighborhood encoding is now generalized for all node and updated for all notess simultaneously through this amazing or nice compact propagation rule and what we're going to do is add the biases so to add the biases we're going we need to create also a vector of size you know D so we have。



![](img/b5860e808f9ad2c068642b1e8a2339af_65.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_66.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_67.png)

DK plus1 times1 times one times n so we need to get a matrix here。

 and this will give us something D plus1 times n allright， so the output here。

 the activation will be applied to a matrix of this size and that's why here we introduce the one so we can the one vector that is transposed so we can get build our bias matrix over here so we add everything up so we do the addition so we add everything up and then we apply the activation to each element of this matrix so each element will have an activation for example。

 max 0 x so if we do the relu activation we're going to remove all negative value So if you're going have for example。

 here an element x is equal to negative 0。5 and you do you know max0 x so that will give you0 because we will kind of you know like repress all and remove all the negative values right so that's an。

Tpe of activation that we use conventionally are very I would say commonly in neural networks now the size of the output now we can verify is it correct yeah it is so we have Dk plus one okay the dimension of the output manifold the learned new embedding space of dimension dk plus one for the K plus one layer in times and the number of nodes and now we have updated the the embeddings for all nodes each of these nodes you know every single node in the graph。



![](img/b5860e808f9ad2c068642b1e8a2339af_69.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_70.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_71.png)

These embeddings have been updated。Allright good so I think now we can move to the last example and in this final example we're gonna to look at classification。

 so what we want to do is to classify a graph so here we do a deep sequential node representation learning or embedding learning so we get the final embedding and the final layer and what happens next is very simple so we can basically train a neural network that maps these into you know like that goes through a new layer a new mapping function or classifier that is parameterized by a scalar not a vector now beta K and here omega K these are the parameters of the classifier so this could be for example so here it's a simple multilayer perceptron so it's a simple you know like kind of network so we connect everything so this part this classification block will be connected with the。

😊。

![](img/b5860e808f9ad2c068642b1e8a2339af_73.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_74.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_75.png)

With a whole graph， so once we get this， we were going to pass the embeddings， the HK plus one。

We will pass so the embeddings for the network， so let me just write it here， so we have the HK。

 so here HK pass it through a a neural own network。

That learns how to aggregate and then have activation and then have the final output so this is what we have seen at the very beginning of this lecture if you guys remember so you can have a look at that and this is a simple non nonlinear。

One layer， so non nonlinear。One layer neural network okay so you can do that and then we will learn these hyperparameters。

 we will learn the beta of this network the bias and we will learn also the mapping function which we call her WK and we can do the classification so the network output function so we input so this is the network the network output the final function in the network it will take in basically the learn parameters is the a and the X the feature matrix and it will learn。

How to map， you know like this， you know， the feature matrix that now should be a good representation okay。

 of the node of all notes of all samples。lash here nodes or of the whole graph right and then we will take this and we will map it through a a classifying function a classifier WK and add a bias and this will give us we can use the sigmoid loss to do a classification so I have also gone over this and if you guys check section three of you know the deep graph learning lecture1 so 1。

3 you will see this example so I go over it in detail but the last question that I asked if you remember at the end of the session is how are we going to learn this HK right so how can we how can we learn this and this is what we answered during this you know lecture by using you know message propagation and GCN layers on graphs and now that we have our HK basically we can simply do the learning we can learn this classifier by taking。



![](img/b5860e808f9ad2c068642b1e8a2339af_77.png)

This is actually the only WK， we have the beta K right here。



![](img/b5860e808f9ad2c068642b1e8a2339af_79.png)

This is you know the learned embedding so this is the hK and then when we do this and we normalize divide by the number of。

In this case， we have this should be。The number of。

So here if we are the number of nodes so this should be the number of nodes okay so this is the number of nodes in the graph and we can get we can easily get a final prediction for the graph so for example in this case if you sigmoid if you get something close to one so this let's say you have class0 and class one okay so two different classes so these are different classes and if you get a response of 0。

9 it means that you are very close to one so this sample this graph that has been embedded okay so all this graph that has been embedded into this matrix right will be classified。



![](img/b5860e808f9ad2c068642b1e8a2339af_81.png)

As you know one as class one and in this example， you can think about， for example。

 molecule so you can have a molecule and in that molecule you will basically to a type of molecule you can have。

 for example different types any kinds of graphs but I want you to think about different examples you guys can think about different examples so molecule here is a bit tricky because we may have different number of notes and this transformation right here may vary a little bit but so you can think about having a graph all of its node are embedded and then we want to kind of map that onto a target score and when we get the target score it will tell us the class al right cool so if you forgot this part please revisit this the last section in lecture1 so now we're going wrap up with a few variations like you know going over a few variations of this。



![](img/b5860e808f9ad2c068642b1e8a2339af_83.png)

Aggregation rules， so self aggregation and neighborhood aggregation or self encoding and neighboring codingding。

So first here， we have seen that this is what you know this is the conventional model that we introduced earlier。

 so we have so the eye here， this defines the eye hat that I introduce in the vanilla。GCN。

 so to wrap up， so this allows for self。Ebedding。Okay。😊，Update。And this allows for the。Neighborhood。

Aggregation， okay， so we you can think about this also as self aggregation。All right。

 and then once you do the aggregation you add them both because myself and my neighbors we both need to contribute to my personal update and my personal transformation through this kind of you know learned basically transformation or mapping omega K right so that's the idea now we can also add。



![](img/b5860e808f9ad2c068642b1e8a2339af_85.png)

AAnother。 so we could also add another。Vant here so we can add what we call a diagonal enhancement。

 so for the self。For the self aggregation。Or the self。Update， okay， we can add an epsilon K。

 so this is a value， this is a scalar。To learn。For each layer， okay？For each layer。Okay。

 so in this example， what does that mean， so think about it if you have a graph。Okay。

 and you think about all the neighbors that you have， so what you want to do eventually。

Is to update your node embedding， so。Note I wants to update it's X I right so if you're going to pay attention to your neighbors you' you're going to give a lot of attention to your neighbors right somehow this will can impact you know the or bias your your own original feature so this own my my feature representation will get really influenced and impacted by my neighbors so I want to kind of control this influence。

Okay so to control this influence first I need to make sure that I'm not alone so don't I don't remove this term so I'm not alone so I need to make sure that I'm not only relying on my neighbors if you remove this we're going go back to a which means I don't contribute to my own you know update which is not good right but at the same time if I want to kind of contribute more maybe I should add a weight here that will allow me to enhance my contribution to the contribution of my embedding to my update okay so here here this is a very important idea because it depends on your the quality of your neighbors it depends on also the structure the noise and the original matrix because if you have noise here and these two should not be connected somehow you included the wrong neighbor right so this kind of you know。

Regularization or enhancement allows us to pay more attention and give more confidence， you know。

 give more weight。And control。Okay， to the node itself。Which is something nice。

 you know so this is a hyperparameter that you can learn how much control do I want to give to the node so if I have a node like here like connected this way and maybe I have another node so these two nodes maybe should not have the same control so this one will have an epsilon K of you know maybe 0。

9 and this will have an epsilon。

![](img/b5860e808f9ad2c068642b1e8a2339af_87.png)

Okay， of you know， 0。7。 so this is another thing， so we can make the epsilon K depend。

On the node itself and this is another layer okay so you may say all nodes should not have the same control。

 but now we've taken the problem to a more computationally expensive space because every time you need to kind of estimate epsilon K for all nodes so you have n updates to do or n not even parameters to optimize and you know optimization requires the gradient descent with respect to the epsilon now it's not per layer。

 but now you're going to do it for each node which is you know very costly so let's maybe go back to our you know simple epsilon K which is which does not depend on the node position it only depends on。

The layer k， all right on the previous layer on the previous layer K and the goal is to update in the next layer K plus one。

So we can take we can further expand this idea and if we take this idea and we expand it further。

 then we're going to have this kind of equation so let's see so we can basically as the network gets deeper。



![](img/b5860e808f9ad2c068642b1e8a2339af_89.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_90.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_91.png)

We can treat the current note differently。From the aggregated neighbors by applying a different linear transformation S K here to the current node。

 so here basically the update rule。

![](img/b5860e808f9ad2c068642b1e8a2339af_93.png)

Have。Two different transformations and this is even more， this is more costly。So basically。

 we have a neighborhood。Okay， transformation。Rule， okay or mapping， so through by via。

Omega K that we want to learn and we have a self。Books。A self transformation。

Via a new mapping psyche。Right， so now we're learning how to basically update。

The HK here so if we have if we have HK for node n right and then we have all these neighboring nodes now my update rule here will be multiplied by Psi k and all these aggregated guys if I aggregate them all。

I'm going to multiply the aggregated version by a different mapping。

 so I'm going to transform them differently。リアおomeガ系。

So aggregate and transform them differently all these embeddings so now you can see that we disentangled the the self embedding and the neighborhood embedding so there is a space or a distance between me and my neighbors and here this may have pros and cons。

Cons definitely computationally expensive memory expensive computes expensive costly pro like advantages would involve you know giving also more control to this node and it original embedding and you know allowing the node this breaks a little bit the or recognizes a little bit the reductionist hypothesis that we made remember guys when we said that tell me who my neighbors are I'll tell you who you are so the neighborhood preservation so I don't want my neighbor I may not trust my neighbors very much so I want to learn my own embedding but somehow still learn from my neighbors right so that's the key principle or the rationale behind this so it's kind of you know taking some information integrating some information from your neighbors so you want to use your neighbors through the a matrix right but at the same time you don't want to you don't want to use。



![](img/b5860e808f9ad2c068642b1e8a2339af_95.png)

you know like in the same way transform them in the same way you want to transform yourself because maybe there are not very similar there are some noisy connections there so yeah so there this kind of challenges the the reduction is hypothesis of the neighborhood preservation and give some flexibility to the message passing on graph convolutional networks okay cool so now you can rewrite this mathematically and beautifully so you can put these two transformations together okay you can stack them up into this matrix and kind of gather things together and block matrices and we can define。

We can call this a total transformation omega prime K here and this is the final basically。え。🤢。

Generalized。

![](img/b5860e808f9ad2c068642b1e8a2339af_97.png)

Generalized propagation rule， all right。

![](img/b5860e808f9ad2c068642b1e8a2339af_99.png)

Good， so now one last thing。So graphraph neural GCNs， I would say like in particular are hot topics。

 so if you look at the website papers with code where we can find that graphph neural networks are actually very popular here。

 so especially。If we look， let me just。To the colors so here GCNs have become more popular since they are early inception in 2018 so with early papers so the proportion of papers that are actually you know that are actually using or developing GCNs are getting higher and higher and they're actually very popular compared to for example other types of graphs like graph transformers are becoming slightly popular graph attention networks。

 so all of these are are different variations or variants of GCNs right but still GCN is remains the most popular architecture because it's simple it's powerful and it is kind of very intuitive to so here you can see that also in terms of you know distribution we have。

A lot of graph learning so you know graph learning here。

 graph attention graph classification so these topics also are very hot topics in recently published outside would say state of the art methods from 2018 to 2024 including this year so graphs are extremely popular and there is a large body of research a growing body of research on this topic now if you also look at ICLL 2023 the open review data so this is a top conference and it's the international conference on learning representations and it's very it's a very challenging I' would say competitive class A1 international conference on machine learning and representation learning and or embedding right so that's all that these neural networks do a GCN they learn how to represent data right it's all about the building of these new subspaces。

Where you can represent data better so you can see that also graphph neural networks are very popular and they ranked third and fourth in 2022 and 2023 and here too you can see that you know in the 50 most appeared keywords GNNs are actually extremely popular so they ranked fourth after reinforcement learning as keywords deep learning and representation learning Co so now the last part of this is on you guys so you're going you'll try to kind of you know。



![](img/b5860e808f9ad2c068642b1e8a2339af_101.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_102.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_103.png)

![](img/b5860e808f9ad2c068642b1e8a2339af_104.png)

Take a few minutes I would say maybe take five minutes and try to remember all the things you know like squeeze your brains squeeze your memory and try to recall what we have seen in this lecture so whatever you remember is what stays with you but of course you can go over the lecture notess and like create your own summaries and create your own diagrams and summary maps so that's how you personalize and own your knowledge but the recall exercise is very beneficial because it allows you to kind of see whether you were able to kind of grasp these concepts and if you got them clearly all right。

Very cool， thanks。For attending。

![](img/b5860e808f9ad2c068642b1e8a2339af_106.png)