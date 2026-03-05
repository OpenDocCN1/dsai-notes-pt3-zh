# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p15 P15 CS-E4740 FL Network - Edges -BV1cojRzDEfQ_p15-

![](img/605be4e3d45db8ffdb224c4ce317d9c1_0.png)

Okay， so beside this node wise attributes， like the local models and the local loss functions。

 these are all attributes of node。Now we bring in edges or links in the Feerated learning network。

 So we model these links as undirected edges。 So some some of these devices or nodes I and I prime are connected by an undirected edge。

 So this edges denoted as a set that consists of the nodes that this edge connects and there is no order。

 So a set is an unordered collection of objects。 So this undirected。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_2.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_3.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_4.png)

Connection。And we also quantify the amount of similarity that an edge represents。

 So there is a non negative or a positive number assigned with each edge。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_6.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_7.png)

And the meaning depends on the usage， how we use a federated learning network。

 We will use a federated learning network to design federated learning algorithms。

 and these federated learning algorithms， then use the edges to couple the training of personal or local models。

 So if we have an edge between two devices or two nodes。

 then this means our federated learning algorithms will make sure or we'll try to have similar model parameters at those connected nodes。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_9.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_10.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_11.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_12.png)

These algorithms will be implemented by passing messages between those devices。

 So each each edge also represents or can represent a communication link and the edge weight could be interpreted as a channel capacity。

 So the larger the edge weight， the higher the channel capacity is that we use for for exchanging messages between the notess during the execution of a federated learning algorithm。

 We will talk more about federated learning algorithms and how they are implemented as message passing in one of our later sessions。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_14.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_15.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_16.png)

Okay。So it will also be useful to define some parameters of a federated learning network that characterize the connectivity。

So a qualitative parameter or a qualitative property of of a federated learning network with undirected graph is if it's connected。

 So if there is a path so we can follow the edges from any two nodes or between any two nodes。

 So from any given node。

![](img/605be4e3d45db8ffdb224c4ce317d9c1_18.png)

Following the links， we should be able to reach any other note。😡。

There's a very intuitive notion of connectedness。

![](img/605be4e3d45db8ffdb224c4ce317d9c1_20.png)

And then we say a component C of this graph G is a connected subgraph。

 So if we have a subset of nodes。

![](img/605be4e3d45db8ffdb224c4ce317d9c1_22.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_23.png)

Then this is a connected component， if。Each one， each pair of of nodes in this subset can be reached by edges that connect only nodes within this subset。

 And for some graphs， we have several different connected components。

 So there might be two subsets of nodes where there's no path in between them。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_25.png)

🤧。The neighborhood of a node is defined as all the other nodes that are connected by an edge to this node so no well what is important here is to remember that the neighborhood doesn't include the node itself。

 so the neighborhood of node I is a set of other nodes that are connected by an edge with node I。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_27.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_28.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_29.png)

Then we will also use the notion of a weighted note degree。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_31.png)

Which is the sum of all edge weights between a node and its neighbors。 So if。

 if an edge is connected， sorry， if a node is connected with many other nodes via high weight edges。

 then it has a high weighted node degree。Could be an indicator that this node is important in some sense。

And we will then also use a global characterization of the entire network。

 which is the maximum node degree。 So if we take the maximum of all weighted node degrees。

 we get the maximum node degree。 The maximum node degree is a global property of the entire federated learning network。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_33.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_34.png)

Whereas the weighted node degree is a local property。

 so tells us how the federated learning network looks around a given node eye。

 which might be useful in in certain cases we would not like to have a global view。

 but we only want to know how does the network look around locally around a node eye。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_36.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_37.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_38.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_39.png)

嗯。So here I'll show an example of a Feerated learning network that consists of two distinct components。

 so this whole federated learning network here consists of n equal to six nodes and the six nodes form two components so we have here one component C1 and another second component C2 and there is no connection between those two components。

 but within each component every node can reach every other node by some path following the edges。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_41.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_42.png)

🤧。So in this case， for this graph， we have a maximum node degree2。 for example。

 this node here has no degree2， and this is maximum。And the node degree for this one here is one。

 Yeah， it's， it's， I don't say weighted note degree because we assume here we have uniform edge weights。

 So sometimes we， we do not really know how to assign these quantitative measures of similarity。

 and then it might be a useful choice to just use uniform edge weight。

 So if we know if we decide that to， two nodes are similar or the， the devices。

 that train machine learning models at these nodes， They are similar。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_44.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_45.png)

Should be similar。

![](img/605be4e3d45db8ffdb224c4ce317d9c1_47.png)

Then we just use an edge with weight1， but sometimes for some applications we can say more。

 we also know how much similar they are， for example， if this node represents a weather station。

 then we could say the closer two weather stations are， the more similar their model should be。

And you will see this example using weather stations a lot in our assignments。



![](img/605be4e3d45db8ffdb224c4ce317d9c1_49.png)

![](img/605be4e3d45db8ffdb224c4ce317d9c1_50.png)

Yeah。