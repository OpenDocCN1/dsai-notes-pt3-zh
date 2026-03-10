# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p03 P03_1.3_图学习任务（基于节点、边和图） -BV1WZUKBmEQA_p3-

Our graphs well defined we have our features， annotations of it could be of nodes or edges we can have annotated edges too with different features we can do。



![](img/8f2235fb32dab62539de80e9a88d7afb_1.png)

Learning okay so we can learn on these graphs and there are different things we can learn al right so here this diagram summarizes the different types of learning we have on a graph so we can do what we call a node level learning task or prediction we can do an edge level prediction and we can also do graph level prediction so for example。



![](img/8f2235fb32dab62539de80e9a88d7afb_3.png)

For the node level prediction we have a node and what we want to do is we want to predict so let me right here so we want to predict the the label of a node so if it's a classification problem。

 so we predict the label so which means we're doing classification。Okay， if we're predicting a score。

 then this is a regression problem， so we're trying to predict the value of this particular node given the other nodes and these all the other nodes would be for example。

 these are the training nodes。And this is a test node that we want to predict。

It's a value okay so test node so this is what we call node level prediction we can also do what we we can also do an edge level prediction。

 which means for example， I have all these edges connecting my data but I want to know or discover if there is an edge here how can I know that if these two nodes are connected or not so this is what we call a link or a link or edge prediction problem。

And it's one of of the very challenging I would say problems to solve in a graph deep graph learning okay so prediction so now the last one is kind of simple so you have a whole graph and you want to do a graph based prediction so you want to classify the graph so this graph you want to assign it a label so this is you know a classification problem you want to classify it or you want to give it a score so you want to regress it or you want to for example you know generate another graph from it so generate another graph so this is generative learning。

Another graph from it， okay？So you map this graph onto another graph or another output so the output could be anything okay so it depends on how we define our problem。

 but this is the idea of you know like learning on graph so we can divide it into three categories node base edge base and graph base Now let's look at three simple examples here and if you guys are familiar with machine learning this should be very easy to understand so the first example is a graph classification example so here we have an input graph a so our graph has six nodes and these are an annotated notes with input features that are stored at each node so we apply what we call a graph neural network and we'll learn this in the coming lectures so just be patient and after applying this neural network we will get what we call we'll learn new features so we'll update these values right。



![](img/8f2235fb32dab62539de80e9a88d7afb_5.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_6.png)

So you guys can see that in this example the graph structure remains unchanged。

 so we have the same graph structure， the same structure so the same structure it means the a is actually fixed okay so we have a fixed a's not moving the topology here is the same so we have the same connectivity so what is changing is these guys the embedding so we are taking the input features okay and we are learning learned new representation representation also called embedding okay so we will study this in detail but for now just keep in mind that somehow through this graph neural network I'm transforming this you know this embedding I'm mapping it into a new representation and that's through the network or the mapping function that we're learning let's called W for example。

オッケ？So now once you get so remember we're trying to classify a whole graph so you know as you if you want to classify a graph so let's see so we're classifying。

Classify a graph， so for example， the graph could be a molecule and you want a molecule and then you want to know if the molecule is poisonous or not okay to humans okay for example。

 so you're classifying the whole graph it could be a brain network so you want to know if this brain network is healthy。

Or help。The or disordered， okay？So these are different things you can do different classifications that you can do at the graph level at the whole graph level and to assign a value to that so what you do after we get these embeddings that we learned and we hope that these will tell us more about these nodes right in my graph then we can combine them stack them all together so we just stack them here horizontally and then what we do we combine them we integrate them and then we can classify them so we can use this vector to predict you know the classes of the class of this you know graph okay so if you have three classes it will give us some probabilities like for example0。

8 for this one and 0。10。 one for the two other classes which means this graph belongs to class one now let's look at this mathematically so what do we have here so basically this is。



![](img/8f2235fb32dab62539de80e9a88d7afb_8.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_9.png)

Expressed as like a linear， I would say， classification problem， so what we have。

With some of course we can have some you know hidden nonlinear ages somewhere。

 so linear is just for the sake of simplicity， but we can make it nonlinear so we'll also discover that in the future。

 but for now for the sake of simplicity let's say this is you know the predicted class。Probability。

And it is calculated through the sigmoid function， so we have a sigmoid that takes in a learned bias。

 so this is a learned bias。Also I learned mapping vector or parameter。For at the last layer okay。

 so this is here at the last layer the learned embedding so the final learned embedding。



![](img/8f2235fb32dab62539de80e9a88d7afb_11.png)

And this is a one vector。

![](img/8f2235fb32dab62539de80e9a88d7afb_13.png)

So basically if we look at this let's look at this value what is this value here so before we look at the purple value and we debunk this part which is basically this whole equation before we map it using linear algebra let's define the sigmoid okay so the sigmoid function is an activation function that is used to predict probabilities and we use that we use it in classification we use it also in deep learning in general and the sigmoid looks like this so if x is smaller than zero is' lower than zero so it's negative so we set it to zero here it gives you a value close to zero but if it's like higher or larger than zero then it's set to one okay so it's like it kind of approximates the step function and I talked about this before why we're using the sigmoid has some nice properties and it's a smooth approximation it's a smooth approximation。



![](img/8f2235fb32dab62539de80e9a88d7afb_15.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_16.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_17.png)

Of a step function okay and it is used to kind of you know condense or map all values into a0 or a1。

 which means you know a yes or no like which gives us a probability to a class very high or very low All right so that's why we use the sigmoid and is highly used in classification tasks and also in logistic regression and other things all right and this is a derivative of the sigmoid so you can see the derivative of sigma of x with respect to x and this is how the function looks like okay so it has some properties but I'm not going to go into the details of this activation or logistic activation function。

 but I just want you to keep in mind that the sigmoid actually allows us to map any input value onto either some you know somewhere like to onto zero or one。



![](img/8f2235fb32dab62539de80e9a88d7afb_19.png)

Close values。 Allright cool， so now let's get back to our node to our graph classification task。

 So here we have our you know like mapping function of the neural network。

 So the neural network basically takes in what we call the learned weights。

 So this is the learned these are the learned weights here of the whole network at the last layer so this is our W so in Wk let's say it has d value So it is one times d D is actually the size of the embeddings okay so it needs to be of the dimension of H because we're going to multiply it by H So H is actually this matrix and Hk is the matrix that stores all you know embeddings for each node so this is the embedding learned for node one okay this is the embedding for the last。



![](img/8f2235fb32dab62539de80e9a88d7afb_21.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_22.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_23.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_24.png)

Not node6 so it stores these values at the k we called k because k here is the you know last the final layer all right and what happens is that so we can remove the k completely if you guys want we can completely get rid of it but let's keep it there so it's not I don't find it annoying so it's fine now what we have we multiply so this matrix what is the size of this matrix so first we have one times d vector we have D times you know n where n is the number of samples。

And here this vector， actually the one vector， we will have like n times one， okay。

 so this is all a bunch of ones。And n times one vector so if if you look at this if we do the multiplication between these three elements。

 you can see that the d cancels out the n and we're going to get one by one value which is this value okay so we are going get a scalar out of this so first we do what we call so let's let me explain what happens here so basically we are mapping we're linearly combining first all these embedding so this is this happens through this vector this vector is very important because this vector of ones takes in all the you know each embedding okay and it combines it across nodes so after this multiplication we're going to get basically a a vector that is d by one okay so we're going to get a d by one vector that integrates our sums it's a linear combination and it's like an average pooling。



![](img/8f2235fb32dab62539de80e9a88d7afb_26.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_27.png)

Okay， so in if you guys are familiar with deep learning also this called average。Polling， oh， sorry。

Flling。Or meaning。So mean pulling means that I take all these values and I sum them up and I create their average。

 so I sum an average and the average is created because we are dividing by n so this operation right here。

 this whole block right here is a mean pool block which means I am integrating the embeddings across all notes I'm taking all these guys and for each value I'm creating the average of the first embedding the first element across all node I put the value here and then I'm going to take the second embedding okay value across all node and I'm going to put it here okay so once I get this value so now comes the real magic is that the mapping through the learned weight so this is what the network learns so this is what you know the network learns you know this mapping function W for classification and here by taking basically this vector。

And multiplying it so if I take this vector now that is normalized of course。

 because this output of the whole block so duplicate and I multiply I'm going to put it right here guys。

 so this is my integration vector where I integrated all the embeddings across all nodes al right I take。



![](img/8f2235fb32dab62539de80e9a88d7afb_29.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_30.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_31.png)

This and what is happening here， copy and then I do paste。

no past image all right so what is what happens here is when I do this multiplication somehow I am projecting all this this vector onto the w so this is basically I take each element here each embedding dimension and I multiply it by my mapping function so the w is a mapping function that allows me to map this vector onto a target value which is the the predicted purple score okay so it's the probability that we are after and this gives us you know the first element okay so this is very actually simple it not difficult and then we add a simple bias here so beta is a bias you can also get rid of it if you want or integrated with W here but we have a bias that we add to that and then once we get the final quantity。



![](img/8f2235fb32dab62539de80e9a88d7afb_33.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_34.png)

We pass it through， we have a value we pass it through a sigmoid so if we have a value of two if this whole quantity is equal to two。

 then we're going to get the sigmoid of two and it gives us one so that gives us the probability of 0。

8 which means。

![](img/8f2235fb32dab62539de80e9a88d7afb_36.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_37.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_38.png)

We have a high value there Okay， so for why so yeah。

 so that's how it works step by step and now I think we can easily。



![](img/8f2235fb32dab62539de80e9a88d7afb_40.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_41.png)

General like like not generalized so we generalized actually the started with the graph classification of based learning and we can easily look at the note based prediction or note level classification so here for example what we want to do so let me move these a little bit further。

😊。

![](img/8f2235fb32dab62539de80e9a88d7afb_43.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_44.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_45.png)

Or thanks， okay， so。Averridge bullying let's blur it over there。All right， so in this case。



![](img/8f2235fb32dab62539de80e9a88d7afb_47.png)

We have no we want to classify a node all right， so the goal is that we have， for example。

A set of nodes and we want to color the nodes so we want to assign a color to a node So for example brown or blue or orange here or blue okay so the blue color for example can denote so it tells you that this is a picture of dog or this is a dog right and this is maybe a picture of a cat so it's the classification problem okay we have two labels here so to classifying node we do the same thing we take the original graph。

 the structure a remains fixed so a does not change is fixed you can see it here okay so and also towards the end so it's the same is's the same thing we didn't change the a all right so a is fixed throughout the whole process and。

And then yeah so we pass it through our neural network， we get the embeddings。

 which is the most important thing， so we learn these embeddings and then we classify node from node the node from the node embedding so we use this embedding to discover or to assign a label to this node a color to this node to say well this is class zero or class one so it's the same thing so here we have simply we do this for every single node so we have the H。



![](img/8f2235fb32dab62539de80e9a88d7afb_49.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_50.png)

HK of node n so n is the node okay， so this is for each node we map the node through the weights the weight the learned weights wK so we do a projection here and through this projection onto W we get our we add a beta。

Okay， all right， so we get this first。Element over there so let's call it output one so output for node n all right plus and k so we have k and plus the beta K and as we add the beta K here right so we're gonna to get the final scalar that we will pass through our you know sigmoid function and this will give us the label of node predicted label of node n okay so this is the predicted label of node n so here you can see so simple actually it's much simpler because every you don't need to aggregate you don't need to combine or do anything you just through this one so here we did a mean pullinging or aggregation through this vector right there but here we don't need that we actually need to kind of you know take each embedding pass each embedding through a the mapping function that we learned the W and then getting adding the bias。



![](img/8f2235fb32dab62539de80e9a88d7afb_52.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_53.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_54.png)

And applying a sigmoid and we get the predicted label immediately okay。

 so that's the probability of the talk for the classes that we may have。



![](img/8f2235fb32dab62539de80e9a88d7afb_56.png)

So now we move to the last example and that's even simpler。

 so the last example is about edge or link prediction so in link prediction the question that we're asking is do we have a link between two particular nodes so if we look at node one and two we want to predict the edge presence using their adjacent embeddings okay so we look at these you know we look at these embeddings。

 the embeddings of the neighboring nodes so the neighbors of one and two or three four and five these are the immediate neighbors if we look at only one help right here okay and by looking at these embeddings somehow we can derive the embeddings of these nodes so we can learn these embeddings of our target nodes one and two and then we can we can use these two embeddings to calculate a cosines。

ity or a sort of we apply particular function just to measure the similarity between these two embeddings And if they are very similar we can say。

 oh look there now there is we discovered that there is an edge and the weight of the edge is 0。

9 so it's very close to oh one if it's normalized between 0 and1 for example okay so there are so many things that we can use for link prediction so many at different operations so here for example。

 we use the dot product Okay so we。

![](img/8f2235fb32dab62539de80e9a88d7afb_58.png)

We calculate simply the existing of links。 So this is， you know， the existing or the yeah。

 so it's like the probability of。The probability。Of link existence。Existence。Between。Nots。

M and N okay so it's the same thing we're using the sigmoid function because it maps onto zero and one so it's beautiful so it tells you if there is no link or there is a link okay so what we need to do is like once we learn so the key thing is to learn the embeddings right here so once we learn very good embeddings here very good representations of these two nodes we can simply take their you know dot products so we take H transpose and H and times HN。



![](img/8f2235fb32dab62539de80e9a88d7afb_60.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_61.png)

And we get the final value， which we pass through a sigmoid so you guys can see this is actually H。

And transposed and here we have the embedding of M this is also the embedding of a node n HN and this is the operation that we do so a simple multiplication which is here a dot broadad of H M and Hn and we're going to get the scalar here that will pass through a sigmoid function sigma X which will get us the value y M n you know in around zero1 okay so that's pretty much it so you guys can see that all these problems okay。



![](img/8f2235fb32dab62539de80e9a88d7afb_63.png)

Or all these learning tasks， they share one。

![](img/8f2235fb32dab62539de80e9a88d7afb_65.png)

Key component and that key component is these embeddings how are we going to learn these embeddings right how to represent each node because you know if you're going to classify a graph you're going to use the h of all embeddings of all nodes the embeddings of all nodes if you're going to classify only a node you will check the embedding of a particular node only a node n if you're going to do a link prediction you need to check the embedding of two adjacent nodes okay so it's all about learning this embedding or this feature representation using these graph neural networks and once we learn how to do that any task you can see is easily solvable you can use these simple。

 simple mathematical projections and linear algebra equations and some nonlinearities for probability prediction to just get what you want al right。



![](img/8f2235fb32dab62539de80e9a88d7afb_67.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_68.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_69.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_70.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_71.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_72.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_73.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_74.png)

So we'll learn in the next lecture we'll learn about how to basically calculate these node embeddings and yeah。

 so that's it for today， so an overview of adjacency matrix properties and you know we covered a few graph types and not everything but the most important categories and a few fundamental learning tasks here。



![](img/8f2235fb32dab62539de80e9a88d7afb_76.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_77.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_78.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_79.png)

![](img/8f2235fb32dab62539de80e9a88d7afb_80.png)

Thanks very much。Do you guys？

![](img/8f2235fb32dab62539de80e9a88d7afb_82.png)