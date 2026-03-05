# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p16 P16 CS-E4740 Laplacian Matrix of FL Network -BV1cojRzDEfQ_p16-

So now that we have discussed the basic building blocks of a federated learning network。

I want to discuss one very useful way to characterize。

Federated learning network and this way of reing or characterizing a federated learning network facilitates the analysis a lot so we can using this so this representation is called Laplaceian matrix。

Using this Lalastia matrix， we can often say a lot about the behavior of federated learning systems like how long do I need to run a federated learning algorithm such that it delivers reasonable reasonably accurate model parameters or something and or how robust is a federated learning system like if 10% of the nodes fail or 10% of the communication links knocked out by some unintentional or intentional event。

Will the algorithms still work， Many of these questions can be answered by looking at the properties of a specific matrix。

 which is called the laplian matrix。 And the laplian matrix is naturally as associated with a。

 with an undirected graph。 So remember， each federated learning network comes with an undirected graph。

This graph is has undirected edges， and each edge has a weight， A I， I prime。 So A I。

 I prime is the edge weight between for an edge between node I and I prime。

And then we define the laplacea matrix element bias for each edge。

 we have a negative of diagonal element。 So this here is an off diagonal element of the matrix of the laplacea matrix and on the main diagonal we have the the sum of all the edge weights that are connected to node I。

 So this is actually the weighted node degree。 So if you remember the definition of the weighted node degree。

 This is what is here on on the main diagonal for node I。

 So node I corresponds to the main diagonal entry I I。I column， I throw of the La plaster matrix。

 and it holds there the sum of all edge of all edge weights of the neighbors。

 So connected to the neighbors， which is exactly the weighted no degree。And 0 otherwise。 So if。

 if there is no edge between two nodes， I and I prime the corresponding of diagonal entry is 0。

 So this non0ro pattern， if we look at an example here for a plasma matrix。

 this this or0 pattern captures the absence of an edge。 So in the here in the third row。

 second column， there is no edge between node 2 and node 3。 So there's a 0。



![](img/5f892a255627a646fb370a7946ac939f_1.png)

![](img/5f892a255627a646fb370a7946ac939f_2.png)

![](img/5f892a255627a646fb370a7946ac939f_3.png)

Whereas in the second row， first column， which means between node 2 and1， there is an edge。

 So that's why here is -1 because this we assume need to indicate this more clearly。

 this is a unit weight graph。 So each edge has weight1。



![](img/5f892a255627a646fb370a7946ac939f_5.png)

And in the main diagonal， we have the， the weighted degrees。 So， for example。

 node 1 is the first main diagonal entry has two edges coming out of it with unit weight。

 So the sum is 2。 Note 2 is the second element in the main diagonal has one edge with unit weight。

 So the degree is one and similar to the third node。



![](img/5f892a255627a646fb370a7946ac939f_7.png)

![](img/5f892a255627a646fb370a7946ac939f_8.png)

嗯。So， this is a very。Straightfor way to construct the matrix。

 to construct the oplast matrix for each graph。

![](img/5f892a255627a646fb370a7946ac939f_10.png)

And it turns out that this lapplaceian matrix has many useful properties that tell us a lot about the structure of a federated learning network。

 So let's start with the most obvious properties。 First of all， it's， it's symmetric。

 And this follows from the definition of， of the lapplacein matrix and the fact that the edges are undirected。

 So there is no direction。 There's no orientation of the edges。



![](img/5f892a255627a646fb370a7946ac939f_12.png)

The second very important property is that the Laplace matrix is always positive semideinite。

 so when compute this quadratic form for any vector W with suitable dimension。

 so since the Laplace matrix is n by n where n is the number of nodes in the federated learning network。



![](img/5f892a255627a646fb370a7946ac939f_14.png)

![](img/5f892a255627a646fb370a7946ac939f_15.png)

![](img/5f892a255627a646fb370a7946ac939f_16.png)

This quantity is non negative， and this has a lot of consequences。

 useful consequences about the properties of this Laplaceian matrix。

 So for any positive semi defite property for any positive semi defite matrix， symmetric matrix。



![](img/5f892a255627a646fb370a7946ac939f_18.png)

We have an eigenvalue decomposition， which we will discuss in a second and moreover。

 but what is special about this Laplace matrix that it is related to the variation of a vector。

 So let's say this vector W here carries carries values that are assigned to the the nodes of of a federated learning network。

 So this vector w is obtained by stacking values that we assigned to each node of the federated learning network。



![](img/5f892a255627a646fb370a7946ac939f_20.png)

And it turns out that this quadratic form is exactly the same as the sum overall all hwise differences so this is a form of variation。

 so we call this total variation within this course。



![](img/5f892a255627a646fb370a7946ac939f_22.png)

Which is very nice， so。A matrix algebraic construct like this quadratic form tells us something about the variation of model parameters across the federated learning network。

 So this already hints at the usefulness of the properties of a laplaceia matrix regarding federated learning algorithms that use this term here as a regularizer。

 So that's the main conceptual bridge between graph Lalastia matrix and federated learning algorithms that we will study later on because this federated learning algorithms use exactly this term here or this quantity here。

 total variation as a regularizer for model training。



![](img/5f892a255627a646fb370a7946ac939f_24.png)

Yeah。Okay， so let's continue with the properties。 It's， it gets more and more exciting。

 So it's not only symmetric or because it's symmetric and positive semiite， it has。😊。



![](img/5f892a255627a646fb370a7946ac939f_26.png)

An eigenvalue decomposition， a very distinct eigenvalue a very nice eigenvalue decomposition。

 So we can write it as the sum of rank1 matrices。😊。

So each component here in this sum is weighted with a rank 1 matrix， and the weights here。

 this lambdache are the eigenvalues of the Laplaceian matrix。

 and these vectors u superscriptche are the eigenvectors。

 the corresponding eigenves of the graph Laplaceian matrix。



![](img/5f892a255627a646fb370a7946ac939f_28.png)

So these vectors can be chosen to be orthonmal， so we can find orthonmal eigen vectors。

Such that this equality is valid， such that this identity holds。



![](img/5f892a255627a646fb370a7946ac939f_30.png)

![](img/5f892a255627a646fb370a7946ac939f_31.png)

And it's typically very nice to work with autonmal eigenvectors because they have zero in a product so they don't interfere in some sense。



![](img/5f892a255627a646fb370a7946ac939f_33.png)

And the eigenvalues， since the graphroplastian is a positive semifinite matrix。

 these eigenvalues are non negativeative， so they are all larger or equal than 0 and in particular for the graphroplast matrix we know exactly that the first that the smallest eigenvalue is0。

Is0。 and you， you can find the ion vector for the0 and value by using the same。

 the same real number for each node， because if you， if you。



![](img/5f892a255627a646fb370a7946ac939f_35.png)

Insert here a vector W that has the same value at each node。 These differences vanish。

 So this becomes 0 for all hs。 and this whole sum becomes 0。

 So there's one vector for which this quadratic form is 0。

 and this reflects the the fact that there's one ironvalue。 There must be one eigenvalue。



![](img/5f892a255627a646fb370a7946ac939f_37.png)

![](img/5f892a255627a646fb370a7946ac939f_38.png)

Equal to zero。And on the other end， we can upbound these eigenvalues by the maximum node degree。

 so you see already here you see also how the graph structure。

 the network structure by this maximum node degree is tied to the eigenvalues of the graphlalastian matrix so this。



![](img/5f892a255627a646fb370a7946ac939f_40.png)

Any iron value is。Up a pounded。By the two times the， the maximum load degree。



![](img/5f892a255627a646fb370a7946ac939f_42.png)

![](img/5f892a255627a646fb370a7946ac939f_43.png)

，Okay， so。What is more， we can also read off a lot of a lot about the cluster structure from thisellaplace matrix in particular。

 if the federated learning network consists of K connected components。

 So let's say the graph splits into K components and there is no connection between any of these two different components。

 but each components itself is connected。Then it turns out that there is not only one  value equal to 0 in this ordered list of  values。

But there are K exactly the number of connected components is also the number of ordered eig values equal to0。

That is quite interesting。 So we can read off this。

 let's call it dimensionality of the of the zeroig value。 So in mathematical terms。

 this is the geometric multiplicity。Of this iron value is equal to the number of components in this federated learning network。

And we can also characterize each component， or we can identify each component by an eigen vector。

 so we can find eigen vectors for this zero evalue， which are exactly the indicators。😊。



![](img/5f892a255627a646fb370a7946ac939f_45.png)

![](img/5f892a255627a646fb370a7946ac939f_46.png)

The indicator functions for this class for this component。 So for each of these eigenvalue。

 we can construct an eigen vector that is0 for all nodes。

 not in the corresponding component and non0 only for the nodes in this component。

So this is quite interesting when we want to find clusters because if we would know this indicator function。

 we can find all the nodes that belong to the same cluster simply by testing is the corresponding entry of this vector for a node is it zero which means it means it doesn't belong to the cluster or is it not zero which means it belongs to the cluster。

 so this this is the basic idea behind spectral clustering， spectral craft clustering methods。

 they use this eigenvectors。They try to find these eigenvectors to construct these eigenvectors that basically tell us what the clusters are in the network。

🤧And an important consequence of this property is that I want to highlight that this Lada2。

 this second eigenvalue in this ordered list of eigenvalues according to their multiplicities。

 so there might be several eigenvalues having the same name。

 but they are accounted for several times， depending on their multiplicity。



![](img/5f892a255627a646fb370a7946ac939f_48.png)

![](img/5f892a255627a646fb370a7946ac939f_49.png)

And if the second entry， the second eigenvalue in this list is larger than0。

 if and only if this second eigenvalue is larger than0， the entire graph is connected。

 so we find a path between any pair of nodes。However， if this second eigenvalue is also 0。

 this means that the whole network splits into at least into two different two components that are not connected。

 So it's disconnected。 So this this is one one beautiful result of spectraltrograph theory。

 So a graph is an undirected graph is connected。 if and only if this second eigenvalue。

 a second smallest eigenvalue lamb but 2 is larger than 0。



![](img/5f892a255627a646fb370a7946ac939f_51.png)

![](img/5f892a255627a646fb370a7946ac939f_52.png)

Okay。