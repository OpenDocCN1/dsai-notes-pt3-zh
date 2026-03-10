# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p13 P13_3.5_全局与局部聚合方法 -BV1WZUKBmEQA_p13-

So in this section we're going look at different variations of the aggregation function so so far we have seen two types of aggregation first the local aggregation where we aggregate the embeddings of a particular node so locally and this is a one-hop aggregation right here so this happens at the node level and we have also seen the global aggregation of the embeddings particular of all nodes in a graph and this will allow us to estimate the or learn the embedding of the whole graph HG and this happens at the global level at the graph level okay so we have two different types of aggregations local aggregation and global aggregation particularly if we want to do graph classification or regression or generation so we have seen different examples previously but there are this is an ongoing area of research and here you can see that。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_1.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_2.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_3.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_4.png)

Example， we can use mean aggregation in different types of normalized aggregation methods。

 so all of these methods that we're going to go over quickly now are basically they can be applied at a local level for aggregating neighboring embeddings of a particular node but also at the global level if you want to collapse or map a whole graph onto a single compact representation or embedding so the first one is the mean aggregation so so far previously we have seen that to update the embedding of a particular node from layer K to layer K plus1 we use the aggregation rule and the aggregation rule that we use is basically basically sums up the embeddings of all neighbors H and m neighbors of note N Now here we present a variant where we average the embeddings so instead of summing them up。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_6.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_7.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_8.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_9.png)

We average them by you know normalizing using the number of neighbors of note and right here。

 so this is a variant that allows us to create a normalized vector that is an average vector of all the embeddings of a particular node。

 so we will kind of simply average these instead of summing them up。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_11.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_12.png)

So the new GCN layer in this case will be updated in this way so because we have used this aggregation rule。

 we can easily you know write it in the matrix format and you can see that this this simply multiplies the adjacency matrix for our neighborhood aggregation the first term right here and normalizes it by the degree of the node so we divide by the degree of the node and this is what we are doing in this operation right here so you can you can use a simple example you can create a simple graph like this and index your nodes and then you can write this down and the update rule using the expanded form and using the matrix form now for the KiIP normalization。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_14.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_15.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_16.png)

So here as you guys have noticed previously we have only taken into account the number the degree of the node itself。

 the degree of node n okay in this case what we want to do we want to extend this to you know the neighboring nodes so we want to include the degree of the neighboring nodes so this is the degree of the neighboring nodes okay so the logic behind this is that the information coming from nodes with a very large number of neighbors should be down weighted since there are many there are many connections and they provide less unique information so we want to diversify the information and to do so basically we down way the information coming from neighbors with lots of connections okay so this happens by multiplying dividing by the degree of of the node or multiplying by the inverse and。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_18.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_19.png)

You guys can also see that this， if you use a simple， also graph。

A small graph and you you define different embeddings here you can easily so let's call let's look for example at the update rule for this node n and maybe we should connect it a bit more so i'm going to add an edge here and you can try this example on this small graph and compare so let's let me put the embeddings so we have here the embeddings right and compare the this formula the expanded formula with the compact one and you'll find that this is actually the aggregation process using the normalization so here we simply multiply the a matrix by D to the power 0。

5 negative 0。5 and negative 0。5 here and this is。This basically represents this port very easily。

 okay？Cool so now in addition to this so you guys can see there are different variance so sometimes we want to downwe the contribution of the node itself。

 so we did this normalization but later on we included the neighbors do now we can also do a different approach which is not based on normalization but the max pooling so we have seen max pooling before we use it to transform the node embeddings of a graph onto a single node embedding that represents the graph and this is for graph-based learning or prediction so here we can apply the same rule to the nodes in the graph so basically we can use max pooling at each node at the node level to update the node embedding so the max operator here will return the element wise maximum of the embeddings that our neighbors to edit and I have explained this in the previous video and detail like。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_21.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_22.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_23.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_24.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_25.png)

doesnn't mean to take element wise maximum so the maximum value for across all neighbors so actually it's very simple so you have a bunch of you know node embeddings these are my neighbors okay so all these guys are my neighbors and I look at the values right here and I'm going to take the max to do the max pooling so if we have for example 0。

58 and1 I'm going put eight right here okay so far the previous aggregation methods they consider only the neighbors of a particular node so they consider them either equally or in a way that depends on the graph apology like for example we take into account the degree of the node itself and also its neighbors。

😊。

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_27.png)

So this doesn't look or doesn't explore the relationship between the node embeddings themselves。

 so the node embeddings that we were learning can contribute somehow to the aggregation process。

So here。In this case we in this particular aggregation paradigm we're going to use attention so we're going to pay attention to important embedding dimensions in the aggregation process so in this case the aggregation will depend on both the node embeddings and also the local topology so the rule here is to first transform the embeddings and then pay attention so if you have guys。

Heard about attention before so attention is a very important concept that spanned the field of transformers there was a paper published a few years ago called attention is all you need and that paper is a landmark prime paper that started the process or the idea of adding attention layers into deep learning networks and also graphph neural networks so the idea is actually very simple here so first instead of aggregating then transforming the features we will first linearly transform the embeddings of a current node as follows so we will apply the embeddings to the we will apply the transformation omega K at layer K to the embeddings in that layer and then add the bias as we did before so here this will give us or produce h prime h prime is the transform embeddings okay so here we do the transformation of the embedding。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_29.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_30.png)

First， and this example shows this， this is from the chapter 13 in the textbook。

 Understanding deep learning by Simon Prince and in this chapter。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_32.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_33.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_34.png)

Basically in this section we go over the attention mechanism so so the idea is very simple first we start with our input data okay so we have our input data D by N so D is a number of original features and a number of samples or nodes in the graph and then we transform we apply our transformation so we have our transform feature matrix or these are the embeddings right here and then what we do we can combine these two the adjacency the adjacency including self connections so this is the a hat that we used before okay。

And this allows us to aggregate these to do the local aggregation guided by the topology of the graph so and this will give us basically the update。

 the output embedding and of course we need to have the activation function like right here okay so this is the activation function。

 the non nonlinearity that we have introduced so we have seen all of this before like the same concepts so next。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_36.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_37.png)

The the new idea here is to introduce what we call a similarity matrix， so this similarity matrix。

 it will allow us to learn or estimate a similarity okay， which we call a pre attentiontion。Matrix。

 a pre attentiontention matrix that will will encode that encodes basically the pair y similarity between different nodes。

 for example， node m and node n here okay so or we can read it the other way so MN so m and n and how do we actually calculate this preattention matrix or node to node similarity matrix so we take the learned embeddings that transformed embeddings h prime of node M and the transformed embedding of node n okay and we stack them together so we do this stacking and when we stack them so we have this vector right here and then what we we do is like we simply if we we need to define a5 vector layer K so this5 vector is a column vector that we transposed here and when we do this multiplication it give it will give us。

Single value so that value is a similarity values if we do basically phi is equal to one so we're going to simply average all the values here of both embeddings of two nodes node m and node n two neighboring nodes now phi is could be also learnable so we can optimize phi we can learn you know the similarity between these embedding so P phi can become a learnable parameter or a learnable mapping vector of these pairwise similarities that will allow us to you know learn the preattention matrix and not simply predeeffinine it in a fixed way so we can define the phi and we can learn the phi and mostly we do the learning of the phi because it gives us better similarity matrixrices okay so now this similarity matrix once we get the similarity matrix we need to define the final attention weights so now。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_39.png)

Basically what we've done here， we've taken the input data。

 we transformed it using our transformation right so we got the transformed input embedding so we have here the transform data and then what we do we apply a preattention to this to this data so we apply a pre attentiontention mechanism by multiplying the X prime by S so i'll explain how this is done so this is done basically through a soft mask function so the soft mask function takes as inputs the similarity matrix that we learned and the the a hat matrix right here and it will use the topology of the Aha to do the aggregation that is weighted by the similarity so now our aggregation will be weighted by the similarity that we have learned and this similarity basically is the preattention so the output。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_41.png)

The soft mask right here will give us the final attention mechanism that we will use to do the the aggregation of the transform features and then once we do the final aggregation then we will apply our nu nonlinearity over here so the steps are very similar to what we have seen before now this is called the graph attention network and let us see how this works so basically。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_43.png)

Now we take the transforms， so these are the transformed embeddings of the previous layer of layer K and we want to move from layer K to K plus one so this is the update rule that we have seen before but here there's a tweak where we add this soft mask function that takes in the similarity matrix okay that we have learned so it takes in our similarity matrix and from this similarity matrix we apply what we call an attention sorry a softm okay so the softm is applied separately to each column of the first argument which is the the S matrix so we apply the softm to each column of this matrix and we also set so for the second argument here so there is something that happens here I'll tell you about it in a second so here we apply the non nonlinearity。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_45.png)

Which is a soft Max。To S all right and then for the second argument。

 the second argument right here we will set we will replace zero to negative infinity so if we have in this a hat matrix if we have any disconnected nodes okay so for example these nodes these two nodes are disconnected so they're not connected in the graph so let's say note for example to and node4 okay so we have node two and4 they're not connected。

 they have a zero， they don't have a connection so we're going to replace this with negative infinity so why we're doing that we're doing that because this will ensure that the attention that we're learning doesn't go to none neighbors so it will only be focusing the attention will only take into account the immediate neighbors of the node and we will not care about nodes that are not connected to the current node for for the update of the embed。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_47.png)

Okay， so that's the the key idea here and after basically you do this multiplication so we need to。

Multiply s by we do an element wise multiplication of S by the A hat let's called infinity where we did this post processing okay。

 and then basically this will get us the A， the sigmoid apply to S。

Multiplied element wise multiplication by。诶。AtInfinity， Okay。

 so this will be the output of the soft mask。 And then the output of the soft mask。

 if we go back here is the attention that we have。 So it's the attention matrix。

 And now we're going to take the attention matrix and multiply it by。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_49.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_50.png)

X prime， which is the transformed embeddings or in the。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_52.png)

In the previous layer right here K right so these are transform embeddings here so we're going to do the elementwise multiplication。

 the matrix multiplication and apply a nonlinearity and get the final output so this is how we update basically the embeddings using an attention mechanism so the graph attention network combines both you know two mechanisms so the weights are both computed from the data so we have the weights that we're learning for the aggregation are calculated from the embeddings because we're using the attention similarity the prettension similarity matrix S and also based on the adjacency matrix or the graph aology because we are doing this elementwise multiplication right here to do the aggregation remember when multiply by a or you know like the inverse of DNA so the normalized versions of a so that's the aggregation process so here we're doing the S multiplication by a for aggregating。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_54.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_55.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_56.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_57.png)

And as presents a pre attentiontention， then we do this kind of sigmoid to we apply it to as the soft map to make sure that we know we cap the values at one and we zero the nonimportant values so we want our s to be sparse we don't want to keep the far away neighbors we want to focus on the locally strong similarities and the locally strong neighborhoods okay so as here with the sigmoid function becomes a sort of a sparse matrix so this sigmoid。

Sifies。As where we focus only on the mostly connected， you know， the connected。

The highly connected notes in the network， okay？So these are。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_59.png)

Strongly connected。 All right， cool， very good so that was it for the aggregation methods。

 So we have visited different aggregation methods that could be used at both local and global levels for node based aggregation and graph based aggregation。



![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_61.png)

![](img/2ba4fc49d7f395dcc54f592b3a7a46e8_62.png)