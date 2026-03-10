# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p24 P24_6.1_监督式生成图神经网络概述 -BV1WZUKBmEQA_p24-

![](img/b8bf2308d544e5c58829726646209d32_0.png)

In today's lecture we're going to explore together the landscape of generative graph neural networks。

 so this is a roadmap to a diverse pool of generative models with application to graphs so we will look at the taxonomy of graph neural networks and we'll have few examples so if you guys want to develop your knowledge at a deeper level on graph neural networks and their generative power we would dedicate I would say full course to this so this is really a very rich and a heavy research field so today i'm just giving you a snapshot of the field and not the whole of it but bits of it okay cool so let's get started with with the first part where I remind you of what we have done so far。



![](img/b8bf2308d544e5c58829726646209d32_2.png)

So previously we have looked at primarily the power of GNNs in classifying data and regressing data。

 so we looked at prediction predicting labels， predicting scores we looked also at you know like during this you know supervised classification or learning process we learn how to embed graphs how to discover patterns in graphs and how to do aggregation transformation so we've seen different operations that we use to classify or regress graphs so we have primarily focus on supervised learning and such as node classification and graph classification for so for example here we have an input graph an input graph G let's call it for example right and if we input G to FF is our neural network so this is the GNN neural network mapping function from you know like the whole mapping。

unFrom the first layer to the very last layer so that's the you know global mapping function this will give us an output label why okay so this is for our graph and this is the predicted one so let's put it like here and ideally we would want it to be close to the ground truths so this is a classification task it's supervised so we learn how to predict labels we have also seen the example where we're predicting multiple output scores so we have seen multiple multivariate regression and here you can see that we have many scores to predict so for example for this brain we want to predict the age of the brain we want to predict also the sex whether it's a brain of a female or male and we can also predict many other you know like many other scores related to the health of the brain or the state of the brain okay。

So given this brain we feed it into a graph neural network and we are able to predict all these scores together so so far this has been a very exciting journey we have covered different aspects。

 different properties including for example in various equivariance and expressiveness in the previous lecture and today we're going to look at the second aim。

 one of the main aims of GNS where can we use GNN so we can use GNN to learn the distribution of given graphs okay so we want to learn the distribution of given graphs and by learning the distribution of the real graphs for example。

 the brain graphs how the brain graphs are which from which distribution that are drawn from if we can approximate that then we can easily learn how to generate more novel graphs so for example generated target graph P from graph A and we're going to look at different examples or few examples I would say today okay。



![](img/b8bf2308d544e5c58829726646209d32_4.png)

![](img/b8bf2308d544e5c58829726646209d32_5.png)

![](img/b8bf2308d544e5c58829726646209d32_6.png)

So here from in this example we have the source graph so let's say the distribution of as you guys know this this graph doesn't have any any node features so we don't have any node features here still we have the topology so what we can do we can plot the connectivity weight。

 the weight or the distribution of these edges so if it's a weighted graph so we can have for example so let's say the source graph will have this kind of distribution right so。



![](img/b8bf2308d544e5c58829726646209d32_8.png)

Here。And then the target graph domain will have a different distribution all right。

 and our goal is actually if we want to generate in this domain if we want to generate data so we want to generate data。

In the target domain right given the source， given F source so given FG source we want to predict this graph。

 which is a G target okay so this is our prediction and ideally in a supervised framework here if we have the ground truth of the target we can calculate the distance between these two and see whether we have you know the same topity or not so we can evaluate the correctness of our prediction so let's say this is the distribution of the ground truth data so this is the distribution of the target data okay and then if we do our prediction and we have a good approximation of this distribution so maybe we will mimic it a little bit so we'll have an approximation that looks like this maybe okay so this is not too bad actually this is very close to that the ground truth distribution and this is what we our model has learned so our model has learned how to generate sample。

that fall you know under this distribution all right cool so now this is one I know it's a simple example。

 but we we will dig a bit deeper later and we'll look at how we we do the generation using different tactics and different approaches Okay so first let's start with。



![](img/b8bf2308d544e5c58829726646209d32_10.png)

![](img/b8bf2308d544e5c58829726646209d32_11.png)

![](img/b8bf2308d544e5c58829726646209d32_12.png)

The supervised generative GNN tasks and here of course。

 supervised means that we do have the target graph okay。

 so we know that this graph here corresponds to the source graph which is in the input space so we have two spaces here we have the input space let's write it down so here we have the input space okay so the input let's call it domain。

And we have the target domain so domain okay so if we don't have the the corresponding graph here we don't know we don't have a graph truth then we move from supervised to unsupervised or selfupervised and we will see a few examples later okay so now this is a generic task so which means do we what do we have here so we have first our input graph so this is the input graph。

And the input graph has the a matrix so of size n by n。

 so it's the size of the input we have here and notes the x the feature matrix。

 which has here the dimension of an input the input feature dimension for example D okay and then we have also graph edges so here we stack all the graph edges so E11 E12 so for example let me write it down。

So just for clarity so E11 so this is self-conction we can do E12 E13 etc。

 and then for each one right so we're going to put the the features of that edge so these are this is the feature the features or the attributes of edge for example。

 AIJ and you can see them here so these are basically edge attributes and we have note attributes in pink color all right now there is one thing I want to I want to point out before we go we explore the target domain which is you know like what we want to generate or what we want to project in the target domain given the input graph right so one way of representing the E is to basically represent it as a tensor so we have for example here this vector。



![](img/b8bf2308d544e5c58829726646209d32_14.png)

![](img/b8bf2308d544e5c58829726646209d32_15.png)

Okay， is。If we have notes I and J so as row and column and we pick this value so the vector that we read along this edge feature dimension is the same as this one so these are exactly the same so what we have done here is basically we flattened the tensor the edge attribute tensor so there are two different representations that we can use for the edge attributes so some papers or some you know like I would say formalization mathematical formalization they use the tensor and others they flatten it for to make it easier to do computations and matrix to matrix multiplications okay。



![](img/b8bf2308d544e5c58829726646209d32_17.png)

So now what do we have here so we have an input the input graph in our goal is to predict the output graph so the output graph you guys if you guys know this here we have more nodes of course we can have less nodes all right so you can you may want to grow a graph you may want to shrink a graph these two graphs could be completely different which means this graph is drawn from domain you know A and this is in domain B which means maybe the notes are not in correspondence maybe here I have a yellow node or an orange node and this node have no match has no match。



![](img/b8bf2308d544e5c58829726646209d32_19.png)

In the source domain so basically we may have completely unmatched graphs we may have also you know some graphs you know that grow which means all these nodes will be will exist in the target domain and i'm just you know for example growing my graph okay so something like that so you guys can see that there are different scenarios and you don't have to have matching or parity between these nodes you can take graph A and in a very generic way try to predict a different graph B with different nodes in different edge types and different feature types so here basically this is a generic formalizations so given all of these three elements okay ideally this is a graph with all the annotations right we want to predict the target graph with n prime nodes and also a different dimension the dimension here could be different okay so we may have more or less features in the target graph right。

Then also we may have a very accessory different number of edge features for the target graph G prime here。



![](img/b8bf2308d544e5c58829726646209d32_21.png)

Basically， if we write it mathematically， what are we trying to do is we are trying to learn a mapping or a neural network。

 an FGNN or a neural network here that takes as input A X and E and it outputs a prime Tilde prediction X tilde and let's write it down and E tilde prime Tilde okay so these are our predictions here and let me just put it over here。

 so this is our network and how do we know that our network you know has performed well。

 so of course if we do have the ground truth we can easily compare do pairwise comparison where you compare the A the predicted a with the ground truth one。

 the feature map， the node feature map and the edge E feature map with the ground truth that we have。



![](img/b8bf2308d544e5c58829726646209d32_23.png)

![](img/b8bf2308d544e5c58829726646209d32_24.png)

![](img/b8bf2308d544e5c58829726646209d32_25.png)

![](img/b8bf2308d544e5c58829726646209d32_26.png)

So supposedly we do have these here because we're doing a supervised task in this example， okay。

 now let me ask you a question so for example。

![](img/b8bf2308d544e5c58829726646209d32_28.png)

![](img/b8bf2308d544e5c58829726646209d32_29.png)

![](img/b8bf2308d544e5c58829726646209d32_30.png)

So how to define the loss function so I just gave you some hints here so how to define the loss function the generative loss function so this depends on the target data to generate so we need to first fix or identify which data we want to generate so do we want to generate only the a' we don't care about the features do we want to generate the topology the graph topology the a matrix and the features is assigned to the node so we have a ground truth feature that we want to benchmark against so we need to select which variables which graph variables we want to optimize over and these will define what we want to generate okay so remember so one thing that is so this is a very important rule I want you guys to remember。



![](img/b8bf2308d544e5c58829726646209d32_32.png)

That you know if we want to use a GCN right so message passing requires two things it requires the a the topology and the features because we were learning how to embed each node so that's the power of message passing or the update rule in GNNs is to learn how to embed nodes in whole graphs also so we actually need these two if we want to do GNNs okay so the E is additional but primarily we need a and x which is the initial embedding that we initial so x is the original features okay so now I have a question here how。



![](img/b8bf2308d544e5c58829726646209d32_34.png)

To solve the following generative tasks， so given that we need both， right？Okay。

How to solve this generative task so the generative task here is that we have a source graph okay so and this source graph doesn't have is not annotated so we have only the topology so this is basically if you you draw the matrix it's a four by four matrix okay and then we have here a bigger matrix so here it's six by six。

Oops so we have six by six matrix and what we want we want actually to predict these to map you know the small matrix onto the bigger one right so we want to predict these values so this is let's call it the low resolution graph AL for example okay and this is the high resolution graph and we want to learn this mapping here so we don't have actually any any features we only have the a's okay so now how can we do that this is something I want you guys to take a minute and think about it。



![](img/b8bf2308d544e5c58829726646209d32_36.png)

![](img/b8bf2308d544e5c58829726646209d32_37.png)

![](img/b8bf2308d544e5c58829726646209d32_38.png)

How can we leverage a GCN？And do this predictive task using GCNs knowing that we don't have any features。

Which kind of？Tricks or。Strategies we can use to do this。



![](img/b8bf2308d544e5c58829726646209d32_40.png)

So here we have different solutions， so let's look at that so first。



![](img/b8bf2308d544e5c58829726646209d32_42.png)

![](img/b8bf2308d544e5c58829726646209d32_43.png)

All right， so if we don't have any features， what we can do is。



![](img/b8bf2308d544e5c58829726646209d32_45.png)

We can initialize we can create features so if our target is to generate a graph that has only adjacency matrix we can initialize x either randomly so what we can do we can take all these values and draw from a normal distribution for example okay and01 and we can put different values here so 0。

3 a you know10 etc cea all right so we randomly sample the second option is we can use the topological attributes which would maybe be more interesting of every given each given note so for example here for each so here we can do topological attributes topological or centrality attributes。

Meeasures or measures okay so for example we can take the node degree here the degree is to so we can take the degree of a node we can also put different values here so these value will be different topological measures like for example rank page we can do aen vector centrality right we can select different or clustering coefficient to detect segregation properties in a network so there are many many attributes that we can derive from the graph itself from the topology itself so this is you know topology driven okay topology。

Driven。Now the last one is to use identity we can this is also another option you may have other options depending on the problem on the data so we can basically simply set them all to one Okay so we have a bunch of ones for everyone for。

For the source network and also for the target so for the target network and here this is just I wanted to keep in mind guys that this is just an initialization okay so we just initialize now what we're going to do these because we're optimizing over the target graph so this is our target graph we optimize over the target graph loss so we want the a basically so let's look at our loss here。



![](img/b8bf2308d544e5c58829726646209d32_47.png)

So what we want is actually we want to minimize the distance between the ground truth you know graph and the target domain okay。

 this is the target graph a prime and so this is the ground truth and this is the prediction okay prediction so this is the prediction that we have。



![](img/b8bf2308d544e5c58829726646209d32_49.png)

And what we want to do we want to minimize the loss so this is our GNN laws we minimize over the distance between these two now for the TNN mapping we want to learn a network function F or GNN that takes as input A and X so we need to give it the X okay and message passing for example。

 for using GCNs okay and then we are predicting these two so although we're going to predict the x tillilde prime so we will predict these values so i'll talk about it in a second we don't need we don't need to evaluate this we don't need the loss okay to include this y。



![](img/b8bf2308d544e5c58829726646209d32_51.png)

Because we we don't have ground。Ground truth feature。 so no ground truth X， Okay。

 so x prime we don't have ground truth X prime。 So basically what we need to minimize。

 although our network will learn these， okay。

![](img/b8bf2308d544e5c58829726646209d32_53.png)

![](img/b8bf2308d544e5c58829726646209d32_54.png)

So when we minimize when we optimize this task we try to generate this graph so what our network will do is that it will learn these embedding so remember guys we do the update of the embeddings H in each layer K right and this is in target graphs so we know already that we have six nodes so all we need to do is basically to learn the embeddings of these nodes and as in the target domain and if I learn the embedding at layer K okay so this is node for example that's right of node I and this is the embedding layer K of node J so what we need what we can do to predict if there is an edge here or not between them we can use the sigmoid function of HK of J transpose HK of I and this will give us the probability the probability of of an edge existing or not existing okay so this is a link prediction。



![](img/b8bf2308d544e5c58829726646209d32_56.png)

Kin of problem and the goal is actually to learn very good embeddings if we learn good embeddings then we are able to predict if there is an edge or not and we can also basically quantify that depending on we have weighted if we have weighted graphs or we have binary graphs of course but the key idea is to leverage these two embeddings that we're learning through the GCN and the target domain the target graph and to derive the connections to derive the a matrix so the a prime matrix okay so this will give us the a prime matrix that we want to predict。

All right， cool so now this is why it's important to learn these embeddings。

 however we're not evaluating the features， these embeddings or we're not reconstructing any original features in the target domain because we don't have them actually okay。



![](img/b8bf2308d544e5c58829726646209d32_58.png)

![](img/b8bf2308d544e5c58829726646209d32_59.png)

![](img/b8bf2308d544e5c58829726646209d32_60.png)

So now here in the loss function so we're optimizing the loss so as we optimize the loss what happens is that you predict better the graph so you have the number of ebox here in your training your loss L1 and if we have for example a graph like this so let's say this is the target graph and the graph where look you know let's say so this is for example the ground truth graph app so we want to converge to this one so as we optimize as we minimize our loss okay here the loss of course has the parameters of theta that parameterize this whole network so this stack all parameters all G andN parameters okay and as we optimize basically what happens is that at the beginning we're gonna to have really bad kind of predictions so we may。



![](img/b8bf2308d544e5c58829726646209d32_62.png)

![](img/b8bf2308d544e5c58829726646209d32_63.png)

![](img/b8bf2308d544e5c58829726646209d32_64.png)

![](img/b8bf2308d544e5c58829726646209d32_65.png)

![](img/b8bf2308d544e5c58829726646209d32_66.png)

![](img/b8bf2308d544e5c58829726646209d32_67.png)

![](img/b8bf2308d544e5c58829726646209d32_68.png)

Have some mistakes here made and the prediction is not actually good and then as we progress the prediction becomes better。

 which means during the training the training graph，At EpoC， for example， I don't know。

 okay Epoch here and the final one training， this is a training graph， final epoch。Okay。

 will become better。 So we we are optimizing over， of course。

 the train set and this been optimized over。Optimize over the train sets and we know that already okay the train sets so we need to optimize over the train set the training graphs al right now the second question or the second sorry the scenario second scenario is when we have a graph。



![](img/b8bf2308d544e5c58829726646209d32_70.png)

The graph。Has only node features， so now we do have the graph truth node features and we want to predict the topology Additionallyly。

 we want to predict these node features so this is a more complex problem because now we want to learn how to predict the topology itself based on embeddings but we also want to recover some node features so these are not you know necessarily the embes so imagine that we have the original feature vector here。

 the source graph feature vector so sometimes we need to kind of decrease a dimensionality but at some point you need to increase it if you have maybe way more features in the target domain So if this guy right here has many features we need to somehow up samplele right so as we do in simple and deep learning models so we need to do some upsling but anyway so this is a complex problem we're not going to cover different approaches but I want you guys to engage in thinking about these problems so how can we solve that。

Given the tools that you learned during the course。

 you should be able to at least formalize the first you know kind of steps of a plausible solution to this problem okay so first here what we have we have the GN our GN mapping function so the GN mapping function takes as input a and X and outputs you know the predicted a prime and the predicted x prime tilde and the loss now has two terms so we need to optimize over two things right so we have the input we need to somehow calculate distance so this distance could be any kind of function that we're using right it could be L1 norm if we want to impose sparsity so it could be L2 norm it could be L1 norm if we want to impose sorry sparsity so we want to learn you know。



![](img/b8bf2308d544e5c58829726646209d32_72.png)

![](img/b8bf2308d544e5c58829726646209d32_73.png)

![](img/b8bf2308d544e5c58829726646209d32_74.png)

We want our matrices to be spae if we add also regularization of course we want to specifysify them but this means that we're using different distances。

 we can use different types of distances to compare you know the similarity between a prime and the predicted a prime tilde all right and then we do the same for these so we want to compare how close these are and this will define our loss that we want to optimize now the third scenario is when we have when the target graph has actually both node and edge features so we want to generate an adjacency matrix and also its node and edge matrixrices in the target domain so here for example this is you know our mapping network so the network is huge actually it is able to predict three things you know the whole the whole graph topology the features assigned to each node and the target domain and the edge features in the target domain okay so。



![](img/b8bf2308d544e5c58829726646209d32_76.png)

Function now is even bigger because we have three terms L3 so here we have the first term that evaluates so maybe we can write it down so this evaluates the graph topology。

 theological soundness this is also this evaluates the quality of the features the node features that we predicted and this evaluates the edge features that we predicted Okay sorry edge。



![](img/b8bf2308d544e5c58829726646209d32_78.png)

![](img/b8bf2308d544e5c58829726646209d32_79.png)

![](img/b8bf2308d544e5c58829726646209d32_80.png)

Features okay so now lambda lambda1 and lambda2 these are scalrs so these are they kind of you know balance the these terms so for example if the range of this distance is in the order of 100 and the range of this distance is in the order of one so you guys can see that lambda2 to bring these two together right to the same range for the optimizer we need to multiply by 100 because if you don't do that the optimizer will only focus on the largest value。

 which is of the order of 100 so all these values are very large。

 the loss is so is so large and this term is negligible compared to the first term so to kind of you know counter that we add a term a lambda here lambda2 scalar and we can set lambda2 to 100 so we can balance things out and this means you know terms out and this means。

Basically that we want to optimize these two equally or in the same way， all right。

 so we want to optimize them equally or in the same way。And if we don't want to do that。

 if we want to pay more attention to this guy so maybe we can multiply by 50 so we can set you know this will give less attention to this term okay and the optimization so we want to actually minimize the first loss compared to this one so this is you know the logic behind these these values or like these parameters。

 hyperparameters that we need to tune and depending on the problem and depending on the focus of the optimizer that we want to have okay cool so now there are several there are various supervised or conditional generative gen and tasks so supervise or conditioned on the target graph that we want to generate because we do have a ground truth so sometimes we can use the word conditional here it has different usages a conditioning means on a label on a contact so you have a variety of usage。



![](img/b8bf2308d544e5c58829726646209d32_82.png)

![](img/b8bf2308d544e5c58829726646209d32_83.png)

![](img/b8bf2308d544e5c58829726646209d32_84.png)

or applications the word and formalization of conditioning and generative learning。

 but here we will use it just you know in a simple and simple and reductions way we say like you know supervised is a type of conditioning okay so which means we condition on the target that we want to predict。



![](img/b8bf2308d544e5c58829726646209d32_86.png)

So so there are different tasks if you want to generalize so this is also from a review paper so if we want to predict a single graph and the notes are the same so they have the same meaning here so which means we're only doing rewiring so youre only simply rewire so this is a rewiring problem so which means rewiring and reweighting okay so you weight the edges so you can see this one has become thinner in the target domain for example okay and you can also add a new graph a new or a new edge so here you added a new edge so that's kind of rewiring and also adding more so you can change edges rewire but you can also add edges sos it's more complex and more rich then simply changing the edge connectivity okay so now this is one problem here we can of course add features and we can add。

Edge attributes okay so here it's onlynithology so now in this example in the multigraph prediction we have a source given a source graph our goal is to generate multiple graphs jointly at the same time so the target domain has multiple types of graphs to generate so for example。

 given a brain graph here that is a that。Shows morphological connection morphological connections in the brain between two parts in the brain or two nodes in the brain we can predict。

 for example the functional connection which is a different type of connection okay so in the structural one also another type so these edge values the meaning of the edges here we have will be different okay so we won't have the same meaning of the edge here across these domains right across these target domains so generative G dimensions have basically we have seen you know here we're doing different domains right so this is the first axis we can also do different scales and you can have a。

A generative model that solves all of these together， so which means it does multiple scales。

 multiple domains， etca， so here for the sake of simplicity we kind of you know。

cateategorize them into different subcategories so here， for example。

 we have a low resolution graph it means it has a number of nodes n and then we want to predict a graph in the target domain and n prime and n prime is much larger or larger than n okay so this is what we call the graph super resolution so you' trying to create a bigger graph from a smaller one and this is not just growing the graph these nodes may not have correspondence so if you look at these two nodes right there is no matching this node doesn't exist in the original graph so we're generating completely a bigger graph in a target domain from a source graph and there is not necessarily a matching or correspondence between them also the meaning the meaning of the edges here will be different so the meaning of this edge and the meaning of that edge like one would for example quantify sort of a similarity in a particular property and the other one will capture a completely different property okay。



![](img/b8bf2308d544e5c58829726646209d32_88.png)

So now。The last one is graph super resolution sorry graph evolution prediction so this is across time so here the example i've given is on the brain graph so we can also apply to any kind of graphs so this means that given a source graph we aim to generate its time dependent evolution over time at different time points so our goal is to actually learn a time dependent you know DNANN time dependent mapping。



![](img/b8bf2308d544e5c58829726646209d32_90.png)

GNN that allows us to predict these at different time points okay in the future so this is a graph forecasting or graph temporal prediction or generation so there are different terms or dynamic graph prediction so you can use different terms for this so for example。

 dynamic graph。Prediction， also we can say generation， right？

And you can use other terms like forecasting。And other terms Okay cool so this was the overview of you know the general overview of how we formalize generative geneN tasks in a supervised way and now I would like to cover the selfservised or the unsupervised way of generating a graph so this is。

 you know a different problem here that we're。

![](img/b8bf2308d544e5c58829726646209d32_92.png)

![](img/b8bf2308d544e5c58829726646209d32_93.png)

![](img/b8bf2308d544e5c58829726646209d32_94.png)

![](img/b8bf2308d544e5c58829726646209d32_95.png)

![](img/b8bf2308d544e5c58829726646209d32_96.png)