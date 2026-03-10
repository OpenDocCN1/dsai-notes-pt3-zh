# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p21 P21_5.2_图神经网络中的节点排列等变性 -BV1WZUKBmEQA_p21-

So for node permutation equivariance， let's start also with a reminder that is what is the definition of equivariance in Euclidean deep learning that applies to for example。

 images， so let's look at this definition。

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_1.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_2.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_3.png)

A function F of x， so this is our network， this is the function of the mapping function from in our network from the input to the output。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_5.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_6.png)

Of an image X is equivalentant to a transformation T of X if。the output。

 basically the output of the transformed image is equal to the transformation of the output of the image。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_8.png)

Okay， so let's read this mathematically， let's translate this。

 I mean let's illustrate this thematic formula， okay。😊，So first。

Let's imagine that we have a also a tree here， so this is I'm going to put。

A tree here so copy paste it Okay so we have a tree here。

 This is our image Now we're going to apply a transformation to the image， so this is X。

And we're going to translate it to the right so we're going to get t of x here so we apply transformation and then we're going to translate it here so after we translated the image now we need to do we need to first。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_10.png)

So here we have basically the transformation of image so we need to apply F so we're going to look at the F applied to the transformed image so here we're going to apply F network to the transformed image and let's say our network is a segmentation network so we want to segment this so basically when we doation here it means we're going to color the the tree so and we have identified the object。

 so this is actually F。Of T of x Okay so this is the output the segmentation of the transformed image now what we need to look at is the transformation。

Of the segmentation itself。 So here we take the original X and we have。So we're going to get F of x。

 so right here。So this is basically。F of x， okay？And now what happens。

 we're going to apply a transformation， the same transformation T。

Okay to F of x so when I translate it to the right I should exit the same image which means the translation of the output of the network is the same as the output of the translated input right so you guys can see here we have and this is the equality that we are after it's this one。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_12.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_13.png)

All right， so this is what it means that we have a function that is of an image act that is equivariant to particular transformation it needs satisfy this mathematical property and you can see here this is where the equality send from all right now next so this is the equivariance。

 the transformation equivariance in Nng learning。

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_15.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_16.png)

And if we summarize it quickly， so here F of x is equivariant to the transformation t of x if its output changes in the same way under the transformation as the input okay now the second one is that network for pixel image segmentation should be equivariant to transformations which means if I translate the image like here the tree。

 if I shift it or kind of rotate it， I should be able to you know dig it properly。

 so if I should be able to get the segmentation of the tree even following you know these transformations okay。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_18.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_19.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_20.png)

So。Now the third property is that if the image is which explains the same actually thing so it's a rewardwording of this so if the image is translated rotated war flipped so we have a particular transformation the network should return a segmentation has been transformed in the same way so the network should basically recognize that this tree has been formed and put you know like a transformed output okay so now the thing is like these properties are not very easy to stipulate in deep learning networks so we're not going to look at that so I'm sure if you guys are taking deep learning quis that should be covered in depth so how can we actually like these nice mathematical properties in variouss and equivaris and when training deep learning network such as CNNN so usually one trick is to use augmentation to rotate the images to translate apply multiple transformations to the original data so the network is trained。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_22.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_23.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_24.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_25.png)

To recognize such transformations， you know like during the learning of the mapping function。

 so that's one way augmentation。

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_27.png)

So now let's look at the node permutation equivariance in GNN so you guys can actually think about how this translates to dense and here instead of transformation equivariance we're going to have a permutation equivariance okay so considering all nodes in graph GCN computationation is permutation equivariant and this is actually means it means that each layer must be equivariant。

 each GCN layer or GNN layer so if we stack up layers right or have different block building blocks so each layer should be equivariant back to the permutations of node indices and this makes sense because if we want to do labeling if you want to do classification if you change the depth of the node the naming of the node it should not change its label right the label needs to be the same needs to remain the same right so if we permute the node indices the node embeddings at each。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_29.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_30.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_31.png)

will be permuted in the same way and basically mathematically this can be translated as follows so here if we apply the permutation the permutation to the embeddings of the previous oops of the previous layer hK right and here we have our adjacency matrix and this is these are the parameters of the transformation that we have。

 for example the linear transformation that we're learning the parameters of our network5hiK so if we transform。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_33.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_34.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_35.png)

The the input we should also have transformation or permutation of the embedding of the output and embedding。

 which is the output of this。Functioner of this particular layer， Okay。

 so the output of the layer here。Outputs。Then you embedding。

So if we basically permute the previous embedding that we're going to use to do the update rule。

 so the message update rule。We need also to update to permute this one okay so you can verify this actually this is not difficult it's the same property it's a similar property that we have with transformations and we can look at particular examples here we can expand on this a bit more okay so for node classification and edge prediction the output should be equivariant with respect to permutations of the node indexes because here we're doing for example as I said note classifications the label the node itself should not change if we change the indexing of the node and also the link itself right so the link between different indexing of pairs of nodes because an edge here connects to nodes right with particular indexing okay so as for the graph you know graph level test the final layer it aggregates information from across the graph so remember guys we need to we use different cooling methods to transform the。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_37.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_38.png)

of all nodes on the graphs So we have different nodes here on the graph right so this our graph。

 for example， we have different embedding so we need to kind of do a transformation to get the embedding the graph embedding H all right over there so here we have a final layer that does this aggregation across all across the whole graphs so the output we say the output is invariant to the order of nodes which means in this case we have an invariance property so if we aggregate we change the indexing of the node if we call this one234。

5 or differently so we have one to345 we should always get exactly you know the same basically embedding so the same output here all right so there would be node order permutation invariant and the output layer in graph classification so we have。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_40.png)

In this formula level four so achieves the following property with respect to permutation matrix so here simply it's very simple we'll still have the same output if we permute the matrix so we permute the final the node matrix that we have there so in this case so with with that permutation and with permutation we should have exactly the same output and this is this you know like mathematical translation of this okay。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_42.png)

Cool now for graphs， the good news， the take the takeaway message from this is that for graphs is possible to define networks that ensure equivaris and invariance properties to node permutations or node order permutations and this is something really nice to have in graph neural networks and make them very easily generalizable。

 which means you should not preserve the same ordering because we're looking at graphs at topologies so regardless of where you represent your graph into a matrix or you stack your features depending on the ordering of the node into the feature matrix your network will still recognize the local topology of the node and do all the learning operation including aggregation transformation。

 regardless of this ordering okay？

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_44.png)

Cool， so now let's have some problem solving here so。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_46.png)

This is you know a simple problem so we consider， for example。😊。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_48.png)

A and later。That。Outputs， you know that applies this date rule to the embedding so hk plus one is the output embedding of this graph layer that inputs the embedding of the previous layer in hk and then the at matrix a now。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_50.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_51.png)

Here is D times n so matrix containing the n node embeddings in its columns as n by n matrix theta is the bias vector omega is the weight matrix transformation matrix that we want to learn for these embeddings right at these aggregated embeddings is a new transformation now the notation here it indicates vertical concatenation of the mates hK and HK so we concatenate them vertically so we can actually。

Think about it， so if we do HK actually like this okay？So HKA right。

 and what we want to do is to show that layer is equivariant to permutations of the node order so that we have this mathematical formula okay。

So you guys， I would like you to also pause the video。

 take a few minutes to write this down and let's see if you can verify this it should be quite straightforward。

 I would say。

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_53.png)

So let's have a look at the solution so it's actually very straightforward so you know like here we start with this formula and then we simply converge to the final one so I won't go into this details are actually very simple detailed solution and the PDF link below the video all right so this was basically the node permutation invari and equivariance in GNN models and next we will look at the expressive power or the expressiveness of a GNN model how can we quantify that how can we measure the expressiveness or guarantee I would say more specifically the expressiveness of GNN models。



![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_55.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_56.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_57.png)

![](img/97ca43f91a3b5e83f6cbbebb2b10abeb_58.png)