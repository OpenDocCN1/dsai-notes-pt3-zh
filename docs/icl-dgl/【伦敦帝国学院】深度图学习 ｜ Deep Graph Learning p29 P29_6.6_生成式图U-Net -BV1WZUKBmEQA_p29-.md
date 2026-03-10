# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p29 P29_6.6_生成式图U-Net -BV1WZUKBmEQA_p29-

About units and we will wrap up with the unit and a few kind of evaluation measures that I will mention。

 and there are lots of things to explore in terms of evaluating the quality of the generated data and it's ongoing sorry area of research。



![](img/82409922a4da6bb9efb239871dbc2d9d_1.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_2.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_3.png)

Now we're going to look at a new kind of or a different kind of an encoder encoder network。

 which is the unit so if you guys have taken any course in deep learning you may have learned about。

You know units and how they work so here the idea is actually very simple what I explained earlier that we do have an an encoder and decoder network so here in this case we have an encoder decoder network we have an input GS and output graph TT so a unit is an auto encodeder which means it's self supervised。

😊。

![](img/82409922a4da6bb9efb239871dbc2d9d_5.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_6.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_7.png)

Model， so what it does， it takes。

![](img/82409922a4da6bb9efb239871dbc2d9d_9.png)

Here the graph unit was first proposed in 2019， which extends the the unit model， so it extends。

The unit。Model to graphs。 All right， so first we have it's a self reconstruction。Problem。

 which means you have， for example， the G here and you reconstruct it through the decoding and the goal is to minimize the distance between G and G tilll there the reconstructed data so it's a self reconstructionconstruct loss。

 so here self reconstruction loss okay or self generation loss。So why this is important。

 it's important because when we do the encoding so this is the encoding here。

 so when we do the encoding process we will learn the embedding of the graph so we'll learn a very compact representation of the graph at this level in the embedding space so this is the latent。

Ebedding space。So in a typical unit we don't constrain the embedding to follow a normal distribution。

 so here it's actually based on the data that we're having based on the training sample that we have G1 to for example。

 GN or bigN here okay so it's data driven or data dependent but and there are lots of variations。

 but anyway so the idea is that we want to encode this graph。

By including this graph through this you know through these layers right here that we're going to go over quickly。

 we will learn an embedding and by learning that representation of the graph we can then de it back and reconstruct the graph itself okay so here we want to minimize between the reconstructing graph by the decoder。

Of the embedding or the learned representation in the latent embedding space and then and versus the grant through original one all right。

 so it's an encodeder decoder network。And what it what it it has has different operations is composed of different operations so the first one we have learned so we know what the GCN is we're just doing node embeddings here we're updating these node embeddings based on a message propagation rule or the update rule for the embeddings that we use with attention or there are different variations we have seen okay so we have different GCN layers you can see them here in the graph right。

And then we have additional operation， so we have an operation that is graph pullinging or GPol so we're pulling twice after each GCN layer we're doing GPol and in the decoder after each GCN layer we're doing a an un unpooling graph unping so we're unpooling here so what we're gonna to learn now is how how these pooling and unping layers work and machine and CNNNs it's basically sampling downsling and up sampling so how to how to downs a graph and how to ups a graph and this is what they have introduced in the paper so they're tried to definearels to these downsling and up samplingling techniques so a graph pullinging pullinging is actually down you down sample somehow down sample all right and here the unpuling up。



![](img/82409922a4da6bb9efb239871dbc2d9d_11.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_12.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_13.png)

Sample okay so yeah， so this is the the view of a unit we call it the unit because it has this kind of shape a U shape right and here we add the skip connections so these skip connections have been first have been introduced in。



![](img/82409922a4da6bb9efb239871dbc2d9d_15.png)

Units and then we have also residual networks with the residual connections and so yeah so these are basically they we the original feature maps they do concatenation。

 but we're not going to go into these details。But let's look at the most important part here so we know what a graph convolutional networker layer is now let's look at how we're down sampling in the encoding process using GPP and how we are upsling in the decoder you know function using unpool G unpool so first for the proposed graph pooling。



![](img/82409922a4da6bb9efb239871dbc2d9d_17.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_18.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_19.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_20.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_21.png)

So here is's actually very simple so if you guys look at this block you can easily follow the mathematics you can derive these equations by yourself so I'm not going to go over them in detail so these are beautifully beautifully explained in the figure and in the figure here in the figure caption they take you know a four by five matrix and four is the number of nodes five is the number of features so these are the features right and you have nodes here。



![](img/82409922a4da6bb9efb239871dbc2d9d_23.png)

So okay， so so what they're doing here， they're trying to pull。

The the to do the graph pooling and as you guys can see in the graph pooling。

 we started with a graph that has many nodes and we ended with a graph that has only。



![](img/82409922a4da6bb9efb239871dbc2d9d_25.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_26.png)

You know two nodes， right， so this is the pool graph。

So now how are we going to do the G pooling here to minimize sequentially you know to go。

 for example from four nodes to two nodes here， so here we went from this graph right to four and four with the G unpoing we went the G pooling we went down to two etca。

 etc okay so let's look at this example， so here。

![](img/82409922a4da6bb9efb239871dbc2d9d_28.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_29.png)

First we take the matrix so our goal is to reduce the number of nodes from four to two nodes so here we have two nodes right and then we will have a two by two matrix so originally the adjacency matrix was four by four because we have four nodes so we updated we have pulled two matrixrices we pulled the feature node feature matrix right so D is here is the number of features right the size of the feature embedding and we pulled also the graph topologies so we pulled both a and X and these this beautiful illustration。



![](img/82409922a4da6bb9efb239871dbc2d9d_31.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_32.png)

Who follows these equations， all right？So first， what we do， we do a projection of the matrix。

 so we learn a projection vector so this vector right here。

We will do a projection of every single node。Using this learnable vector so we have a learnable vector P so this is our learnable vector and then we normalize it by the normal P so we divide all you know like after we do the the multiplication we're going to have a representation for every single nodes so we're going to have for each node we're going have a value right 0。

200。8 etc ce so these are the number of nodes so why here it belongs so why belongs to R and with n the number of nodes put n number of nodes all right so we have n values for every single node in the original graph and this is a compact representation of the node that we obtain through the projection so we projected every single node embedding all right so let's do this way each node embedding is projected using a projection vector or integrated using an integration and information integration vector so we have seen this we have seen that the multiplication of a matrix。

Vor has different meanings we can call diffusion projection information integration right so here in the paper they called projection so it's a trainable vector that we're learning p and has five values so we have five。

It has yeah so it's the dimension of the features P belongs to RG so these is the number of features and then what we're going to have after this projection we're going to get a compact representation of each node embedding so the node embedding here is reduced into a single value over there all right now after that what happens is that we're going to see that each node has a different value embedding value single value in this y vector so this is an embedding of all nodes so single value so next the idea is that we want to select the nodes with the highest value。

Highest values so we will select basically the node with the highest scores and record their indices in the top K node selection stage。

 So here the top K we for example find that these two nodes have the highest value 0。8 and 0。

9 so we will mark them so we will select these nodes and now what we're going to do we will find these nodes and the original xl matrix so we will identify them so we will retrieve their rows the first node and the。

Third and we will construct you know our smaller matrix that has only these two nodes right so now we have only two nodes the notes that have the highest emdding value。

 the most important ones we consider them as the most important ones okay so now we get the x tilde X tilde here is basically a selection of rows and the original matrix so we only retrieve these rows right here okay and we got them over there so it's actually very easy and then what we do we do an element wise multiplication。



![](img/82409922a4da6bb9efb239871dbc2d9d_34.png)

So XL here has K times D， so it's k times d all right。

 so k times D the y vector our y vector tilde is actually we apply the so how do we get that so we apply the sigmoid to these two values so here we're basically casting these into between0 and1 to make sure that we either select or not select okay so now we transform these values so it will have k values so here it's k times1 and we multiply it actually here I should put so they use C here for the number of so I can put it here K so C here is equal to K so this is the selected nodes Okay so maybe they use a different notation that's fine so and then we're going have。

Sorry， actually it's deep right so let me just fix this。

Okay is the selected note one C is actually C is actually the number of features right so this is the number of features what we call D so here D is equal to c is the features so we transpose it so this should belong to d times one so if we transpose one times D and you guys can see that now we can do element wise multiplication between these two matrices so this one is basically this product right here by the transpose of one is to make sure that we're getting a matrix and we can do element wise multiplication for you know the most important for for waiting the most important features okay so we do elementwise element by element and after doing that we retrieve the matrix so this is this will get us the final updated matrix XL plus one of the new cold graph。

And we do the same for a， so for a is so simple， we just retrieve the rows and using the indices and we only keep。

 for example， here we retrieve these nodes， right？So we only keep their connectivities and we're going get here an A2 by two AL plus one two by two and this will be the matrix of their retreat graph so these operations are actually very simple you guys can go over them one by one again but it shouldn't be difficult and the idea is that we want so the idea of this transformation is this projection is we want to compactly learned how to weigh each node and if we find then we select the nodes with the highest weights and then we will down sample or pull our graph shrink our graph based on these most important nodes by selecting sequentially the most important nodes and the most important so here for example we selected let me find them so these guys so these are the most important nodes that we pooled and then from these actually we pulled only these two guys were pulled because these are most important which are these ones okay so you can see that we're pulling you know different graphs and then we're going reconstruct。



![](img/82409922a4da6bb9efb239871dbc2d9d_36.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_37.png)

So this is the pooling process and it's actually simple and it obeys to these beautiful。



![](img/82409922a4da6bb9efb239871dbc2d9d_39.png)

You know operations that are have a good logic and rationale between behind them Now the last part is the graph un'm pullinging which is the most simple part in a G unit or graph unit so remember guys now when we had the pullinging in the encoder now we want to do the unpooling so first we unpo and we apply a Gcn layer to update the notes so the idea is actually very simple so let me actually take this。



![](img/82409922a4da6bb9efb239871dbc2d9d_41.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_42.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_43.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_44.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_45.png)

Copy right， and then I'm going to paste it here。

![](img/82409922a4da6bb9efb239871dbc2d9d_47.png)

Oh actually it's right okay so I don't need to do that as actually well it in this example。

 so in this example we did the pooling right so we did the pooling。And then we apply to GCN。

And now we need to unpo so to unpool is so simple。 So basically here what they propose is that。

The original graph has seven nodes so that these seven nodes are downsled using the GPPol layer resulting in a coarsed graph with four nodes okay？

And position information of selected nodes， we have the index。

 we know which nodes have been selected in the index the here the IDX okay。

 they are stored in the IDX vector and then。

![](img/82409922a4da6bb9efb239871dbc2d9d_49.png)

The corresponding G and Po layer uses the position information to reconstruct the original graph structure by using empty feature vectors of the unselected node so it's so simple you go here you know that these have been deleted so you put them you restore them back but you put empty features so remember guys we're learning how to embed the graphs so it's all about learning these embeddings so here we put them and we put empty features all of them are zeros right。



![](img/82409922a4da6bb9efb239871dbc2d9d_51.png)

And then what happens when I restore through the GM pool when we add the features of these nodes and reconnect them based on the matrix a so a is fixed of course so we can easily reconnect right so we can restore the a also right now what we we're going to do is apply a GCN layer and this is the key idea so once I restore these two guys。



![](img/82409922a4da6bb9efb239871dbc2d9d_53.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_54.png)

Now I need to apply a GCN layer and a GCN layer or update。The embedding of these two notes。

Update so this is the key sorry so yeah so this is the key idea is that once we apply a GcN layer here these values will change they are not zeros anymore they will be updated according to our propagation rule the propagation rule that will use in our computational graph etc cetera etc cea so。

Basically the idea is so simple is to kind of put them back put a bunch of zeros right chose 0000 and then update them through back through a GCN layer and when you do that actually you're optimizeimizing this loss so an autoenr so I'll explain in a bit we're optimizing a loss in such a way that all these GCNs and the Gpo where all of these will be optimized so everything is optimized and learnable and this is thanks to our loss function so let's look at this。



![](img/82409922a4da6bb9efb239871dbc2d9d_56.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_57.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_58.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_59.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_60.png)

So actually graph Uni has been used in different generative tasks。

 so for example here it has been used in a graph super resolution network GSR net published in 2018 so how can we use graph unit for super resolving graph so you guys can have a read of the paper but you can also you know think about now that I have reconstructed the same graph which has you know three four nodees so this is the input brain graph now how can I you know keep on unpooling until you know to superreol so add。

New edges。And note， so basically you can think about a way of upgrading or extending。

You know G unit or graph unit to you know generate not only so once you have this generated properly reconstructed properly。

 you can you can keep on up sampling or un pullinging until you get。In a new way， of course。

 until you get a new graph， so there are different ways here， but you can see here this is our unit。

And it's a self supervised learning so we have a reconstruction a graph auto encoder block。

 but we can add maybe other blocks， maybe add so maybe。Add。And you block。

For super resolution okay to make sure that we can increase the dimensionality of the nodes and the edges in the graph now how to generate new graph so let's so you may think or you may say。

 okay， so now we have a graph auto encodeder we're just regenerating the same thing。

 but how can we generate a new graph using you know graph unit， for example。

 so this is a good question。

![](img/82409922a4da6bb9efb239871dbc2d9d_62.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_63.png)

And you may think about it。 So let's first start with。



![](img/82409922a4da6bb9efb239871dbc2d9d_65.png)

The problem that we're having so we're having a graph here， Okay， so this is our graph。

And we want to reconstruct it， so in this case， let's say。

Reconstruct the same graph so ideally it would be the same all right。

 so let's call this graph G and this is graph G tilll the reconstructed all right。

 so that we will okay， so maybe I'll call G and then。You know， ideally， this will be close to。

Paste oops to this one。Complicate all right so to the ground truth the G right so this is a ground truth but maybe we have some mistakes we have made some mistakes so maybe we added these two connections right and maybe we remove this one Okay so the the prediction is not very very good here but still you know that's maybe our prediction here after training self reconstruction after our training the network so how do you train the network first。

We have， of course， you know GCN G pool right， So these have parameters。

 we have multiple layers right we we we kind of stack them。 So let's call these。Operations they have。

A theta。 So here we're going to call this。A theta parameter， so this is the total set of parameters。

 so we have F encoder and it has parameters theta。All right。

 so it takes in Gi and theta and then it outputs Z I here。

 so this is our embedding of the graph and then here we have an F。

Decoder of course we have GcN layers and we have simple you know G unpo which is not very learnable I mean this is not learnable。

 but let's call this alsoso phi the the parameters of the decoder layers all these layers all the parameters and here we go so phi all right so now what is the final output what is how do we calculate G tilde so G tilde is equal to。

This one， okay， so the F decoder so the F decoder actually here made a mistake takess Z I okay。

 so it's F。Decoder。The embedding that we learned here， the graph embedding of graph GI。

Given the parameters fine。And let's say we have optimized these。 so I'm going to put a star there。

 and now let's write it again。 So Im want to write it again。 So here what is Z I， So F decoder of。

And I will rewrite Z I Z I is actually equal you guys see this diagram。Is the output of F encoder。

 so it's F。Encodeder of the original input graph GI。Given the parameters theta， right？And then here。

Given the parameters phi star， and let's put star there。Alright。

 so you can see it's a composition of two functions so G is F decoder of you know of F encoder right of G given all the parameters all right so we're composing two functions and this is how we optimize so now we can write our loss so the loss。



![](img/82409922a4da6bb9efb239871dbc2d9d_67.png)

How do we write the loss function so it's basically we want to minimize over theta and phi of this whole thing okay。

And let's put it， let's make it small。Minus the ground truth。

Okay so this is actually Gi tillde the predicted one and we can use different losses here。

 but this is an example of a loss to optimize and as we optimize a set of parameters of the encoder and the decoder as we optimize these we are able to reconstruct the same graph very well and this will be very close so maybe we'll make less mistakes all right now let's go back to the question what's our question how to generate new graphs okay so you can take for example the embedding of this graph so let's say this is graph GI I take it embedding Z I。



![](img/82409922a4da6bb9efb239871dbc2d9d_69.png)

So one idea is to perturb it a little bit so I can add a small noise and epsilon right。

 so drawn from a prior distribution P of epsilon right？

And then by adding this random noise with random values， I'm going to get a new Z。

 so let's call it Z， you know I。You know， okay， so that I， for example。

I'm going to call it a different one， so here。Double indexing， Okay， Z I1。 Allright。

 so this Z I1 is a vector。 Now what I can do is。And put this vector。Pass this vector。

 do a pass of the vector through the decoder and it will give me。

 it will give me basically a new graph。AComp a new graph so we're going to generate a new graph and here will be the same number of nodes probably because we have the same number of nodes。

 one two three，45 one，2， three，4， five and this is our graph okay so you can see that we have you know generated a new graph。

And hopefully this new graph will fit the distribution of the original data and this is the distribution。

 for example， of the P data， the original data and the red one is the generated data okay。

Generate it。Data。All right or generated graphs so we can do the same here so we can take you know add another epsilon another perturbation and by adding another perturbation we're going to get Z I for example K or you know P so we'll have many many perturbations and we can have thousands and thousands of samples you know created and every time we pass this through the decoder right so this passes through the decoder so F。

Decode Z， I P。By star， so we're going to get a new graph G。

IP predicted and this will be a new graph that we predict Okay， cool。

 so that's how we do generation here。 And so now there is another question so I want to ask before。



![](img/82409922a4da6bb9efb239871dbc2d9d_71.png)

I show you the solution， so I want you guys take a few minutes and think about this and if you're watching the video maybe you can pause。

So how to generalize graph unit to a target graph with also edge attributes。So we have now we want。

 let's say we don't want to predict only the topology and， you know， reconstruct the。

The original features like basically recover the same graph right so with with its features an topology so imagine if we have also edge features so we're going to have for example edge features right here so all of these will have attributes how can we you know extend graph unit to accommodate that accommodate edge features。



![](img/82409922a4da6bb9efb239871dbc2d9d_73.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_74.png)

So。Let's look at the answer， so the answer has been proposed in a research paper。

 so note at disentanglement variational auto Enr published in 2020。



![](img/82409922a4da6bb9efb239871dbc2d9d_76.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_77.png)

And actually the solution is very simple and very intuitive， so what do we have here guys？😊。



![](img/82409922a4da6bb9efb239871dbc2d9d_79.png)

Let's look at this together， so we have the input feature matrix。

 the graph apology encoded in the a matrix and the edge feature tensor so here we're using the tensor and the goal is to generate f prime G prime and E prime so if we're doing this in a supervised way which means we're having you know so here in this example you can have a target graph so this would be a different target graph。

Target graph and you can have also the same graph if you're doing self reconstructioncon so this is supervised learning and this is self-supervised learning okay so you can have this work on different scenarios depending on the loss if you want self reconstructioncon you do G minus G tilde right so this is you know let's write it here G minus G tilde the same graph and for this one you do G target minus G tilde right so the the target graph from the input。



![](img/82409922a4da6bb9efb239871dbc2d9d_81.png)

So and this one will be of course expressed as a function of some。

 you know the original graph and some set of parameters data， including encoder the encoder。

 this is the total transformation that transformation that includes the encoder and decoder transformations right。

 so it includes F encode and also FDcode。

![](img/82409922a4da6bb9efb239871dbc2d9d_83.png)

Alright， so now here。It's actually very simple so first you have a node encoder so giving the features we learn how to embed them so we learn how to embed the F given the edges the adjac the edge and the features together we learned how to embed the graph itself so this is the topology this is the A matrix right and here giving the edge alone features we learn how to embed the edge feature features into Z so here we're learning three representations。

 one of you know how to embed the feature vector of the graph how to an embedding a single embedding of the graph itself the topology which is the adjacency。

And the un embedding of the edge attributes of the whole graph。

 So the graph is so these guys are collapsed onto a single vector And here this is the vector that is embeds this whole matrix。

 This is the vector that embeds this whole tensor， and this is the vector that embeds this whole graph and we have seen using GCn we can embed graphs。

 Okay now one thing to learn here is that we want to learn also the distribution of the Z so。

Z F will be drawn or sampled。From a particular distribution so the green one here so let's do green so this is sampled from a distribution with you know like a mean mu f and then standard deviation sigma f and these are learnable so we want to learn these two so these are learnable hyperparameters now for the you know the Z is the same here so it's you know Z。

G for the graph is sampled from muG Sigma G right and then the last one which is this one is sampled from a distribution of you know mean mu E and sigma。

All right， so these are all hyperparameters that we want to learn so learnable hyperparameters it kind of increases。

The dimensionality of the problem but yeah so we want to learn these and once we learn them we learn the distribution of each and then we can easily sample so once we learn these we get the embeddings and then for generating new samples is's very simple we pass these through the decoder right so the node decoder and the edge decoder and we can get easily the e prime F prime and we can reconstruct the graph using these two。

Using the decodder function so we have here the Qfi as we have seen before these are our encoding functions right and then these are the decoder functions and then we can produce the decod network according to the that now very easily if you sample from these distributions so how can we create new samples you just need to sample from these distributions so and if I sample if I randomly sample so let me write it down let's write it down so if I sample a use that new Z F sampled from。



![](img/82409922a4da6bb9efb239871dbc2d9d_85.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_86.png)

And mu F sigma F， right， And I pass this through the decoder， P theta， right。

 we're gonna get a new graph。 So and same here for Z said G and Z E。

 So we sample from their respective distributions。 And we pass them through the edge decoder。

 And we're gonna get the E pass them through the node decoder。

 And we're gonna get the basically the node features， right。

 So that's how we experience actually very simple。 And you guys can also write it down neatly shouldn't be difficult。



![](img/82409922a4da6bb9efb239871dbc2d9d_88.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_89.png)

![](img/82409922a4da6bb9efb239871dbc2d9d_90.png)