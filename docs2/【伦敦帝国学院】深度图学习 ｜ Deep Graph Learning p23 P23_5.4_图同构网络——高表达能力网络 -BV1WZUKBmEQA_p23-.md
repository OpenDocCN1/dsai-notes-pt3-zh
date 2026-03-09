# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p23 P23_5.4_图同构网络——高表达能力网络 -BV1WZUKBmEQA_p23-

And this paper is called how powerful are graph neural networkss。

 it introduced the graph isomorphism network， the G network that basically maximizes the expressivist of any。

Graph neuralural network so something really cool about this paper that they discovered or introduced a formula where you can define a message update rule of the embedding that is highly or maximally expressive okay so this is a different way there are also like a family of other works that you know like look at the expressive of the network from a different perspective。

 but let's have a look at what this paper has offered。

To the community so here first were start so the first thing is that they showed that Ts are u most as powerful as a WL tests and distinguishing graph structures。

And they could be as powerful as this test and also they they define particular conditions on the neighbor aggregate okay the graph readdo function so the graph readout here。

 the word readout is what we called previously the。

Okay so it's the final function that will output the label or the target score and so here they basically find particular conditions on the neighbor aggregation and the graph readout function so this aggregation function and the readout function they need to have satisfied particular conditions and under these conditions the GNN is becomes as powerful as the DL test which is really cool property to have now the third things they also identified graph structure that cannot be distinguished by popular GN variance so for example the typical GCN and graph saved here that use max function and also that use mean so using the max and the mean during the pullinging you know or the aggregation turns out not to be in and have seen examples actually guys previously so we have seen here that these you know using the max and the mean。



![](img/488b63677411758ad529a4b81a68b80a_1.png)

On different exampless in distinguishing between different apologies and this is also from the Gin paper okay？



![](img/488b63677411758ad529a4b81a68b80a_3.png)

![](img/488b63677411758ad529a4b81a68b80a_4.png)

So now the third， the last point they showed is that。



![](img/488b63677411758ad529a4b81a68b80a_6.png)

They showed that they developed you know a neural network architecture or graph isomorphism network so so it's actually a simple update rule that they introduced it's a layer that it's a。



![](img/488b63677411758ad529a4b81a68b80a_8.png)

There are are different layers that you can introduce in your network so I'll explain this in a bit。

 but the idea is that we want to aggregate in an injective way。

 how can we do that so let's define let's update our aggregation functions in this layer and this is what they focus on they updated these two components and by making guaranteeing that they would be injective okay。

So they show then that this actually has a discriminative and representational power that is equal to the power of WL tests and these are nice experiments in the paper。

 so I really encourage you guys to you know kind of have an in depth read of this paper and its methodology。



![](img/488b63677411758ad529a4b81a68b80a_10.png)

So one important theorem in the paper and I wanted to kind of spotlight this theorem because I found it very important and interesting。

 I think this is the crux of the paper。

![](img/488b63677411758ad529a4b81a68b80a_12.png)

![](img/488b63677411758ad529a4b81a68b80a_13.png)

First。Let's start with the with you know let let's go through this theorem3 okay so let's a be a GNN so a basically define our internet network so we have a graph and we it takes in a graph and it maps it onto and outputs d dimensional space so a is our architecture is our neural network okay so that's the architecture or our neural network。

It takes in the input graph， this is the input graph and outputs a the dimensional vector so here with sufficient number of GN layers a maps any graphs G1 and G2 that the WL tests of isomorphicide as non isomorphic to different embeddings if the following conditions hold okay so we need to satisfy these two conditions all right for our a network to you know like be able to map different graphs or naomorphic graphs G1 and G2 which means that there are different so theyre different graphs。

Onto different embedding， so this is a very important property that we want to satisfy。

So what are these two conditions okay so the first condition is that our network A aggregates so there is an aggregation here that happens aggregates and updates node features iteratively with so this is the update the node and rule so we have some different rules before on message passing rules okay so this is the update rule and the update rule basically takes in two things it takes the cell the node itself which is V here and the neighbors right so the way we aggregate the neighbors so F applies actually to the node and then it transforms the node so this is like in different models so we take the node we transform them and we aggregate them so it aggregates the node and then phi takes in the current node itself and the aggregated ones and applies a linear transformation so have another transformation phi here so F aggregates it operates on the neighbors and。



![](img/488b63677411758ad529a4b81a68b80a_15.png)

I operates on the kincatenation of these two， you know the integration of these two so Phi can take different forms and F can take。

 of course， different forms， for example， for F we have seen what did we say So F could be for example。

 max pooling it could be summation sum it could be also mean right aggregation etca all right now phi is our linear transformation function that we want to learn so basically what happens here is that first we want。

Do you know F， both F？And fine to be injective so that's the same thing that you need to retain。

 So these two need to be injective right so if they are injective it means in our in our function in our update rule right mapping the previous embeddings of layer K minus onto K to get the new embedding right here the update of the embedding both functions are injective so we're going we're going to aggregate in injective way which maximizes the expressiveness right of the network so the second and then is that。



![](img/488b63677411758ad529a4b81a68b80a_17.png)

A A so the A graph level readout， the final readout function that takes in， for example。

 all the Hv for every single V in the the graph right and transform it transforms it into for example。

 the H graph or if we're doing a graph based classification right So this function also。

 if you're using， I don't know， like whatever previously we have seen max also some we have seen mean and other kinds of。

 you know like functions with attention mechanism and stuff like that。 So these need to be injected。

 So the readout also needs to be an injective function。 So everything is injective。

 So basically the middle layers。

![](img/488b63677411758ad529a4b81a68b80a_19.png)

Or the aggregation beginning end is injective。And the final one to do the transformation and get the output。

 the readout， the prediction score or the class label it should be vector2 all right。



![](img/488b63677411758ad529a4b81a68b80a_21.png)

Now let's look at these different examples。

![](img/488b63677411758ad529a4b81a68b80a_23.png)

So here we rank different， for example， we rank the sum mean max aggregators over a multi set a multi set is actually a set where you have multiplicity。

 which means you have a bag of。

![](img/488b63677411758ad529a4b81a68b80a_25.png)

![](img/488b63677411758ad529a4b81a68b80a_26.png)

Notdes and in the bag of nodes you have you know you can have redundant nodes okay so here for example。

 we can see that we have a multi a multiplicity of four for the blue one and a multiplicity of the pink one which means you know the number of times these nodes appear in the in the band the multiset okay so now we want to see which ones are more more expressive so the left panel it shows the input multiet okay so the network neighborhood to be aggregated So this is the network neighborhood that we want to aggregate so we basically what happens in the paper with all these and we put them we define a set okay so now we have you know like a bag of nodes every computational graphs very simple but in this nice example what we want to look at is how different aggregations behave on this you know computational graph。



![](img/488b63677411758ad529a4b81a68b80a_28.png)

![](img/488b63677411758ad529a4b81a68b80a_29.png)

![](img/488b63677411758ad529a4b81a68b80a_30.png)

![](img/488b63677411758ad529a4b81a68b80a_31.png)

Now turned on into a multiet okay so the next three panels illustrate the aspects of the multiset given the aggregator is able to capture so the sum here is a summation means you put everybody there so add them all up so everybody will contribute Okay if you sum them up so you can see that you know here the summation acts as a multiet it preserves the power of everybody because you're summing all these embeddings right here so I'm going to put them vertically so let's do some。



![](img/488b63677411758ad529a4b81a68b80a_33.png)

Ebeddings vertically so these are my embeddings if I sum them up somehow i'm preserving everybody everybody will have a condition with a multiplicity so this guy will be repeated twice these four embeddings will be repeated four times right so if we take color we can change the color actually here to match this example so we'll take blue so here we'll have you know four con right now if you do the mean if I take the original。

Input and I take the average so what happens here you're going to collapse you know two onto one and four onto two so basically what you're going to have is like you're going to capture the distribution so mean actually gives you the distribution of points and you can see in the distribution for every two points we have one pink and here for every two actually points we have two blues because。

And we do have a number of four there so two times two right so basically here this is this givess us the mean distribution。

And then the max distribution will remove the multiplicity so we will find a set so it acts as a set because we're going take the maximum value and taking the maximum value it will reduce this set onto this so aggregation using max X as a set aggregation using mean it kind of captures the distribution and the aggregation using sum is a very nice thing to have because it actually preserves the whole computational graph。

 the whole multiet okay so here let's summarize this so some captures so just a re so some captures the full multi set mean captures the proportion distribution of elements in a given type and max aggregators ignores multiplicity a multiplicity so the multi simple set all right so that's what it actually looks at because if you're going to look at the maximum of these how many points。

1，2，3，4，56，6 points it boils down。To actually looking at the max these two because we have redundancy so we don't care about redundancy and the max function right the multiplicity all right。

 now now let's look at the summation here， will the summation fix this problem the sum we see it before we didn't actually test this before so here going back。



![](img/488b63677411758ad529a4b81a68b80a_35.png)

![](img/488b63677411758ad529a4b81a68b80a_36.png)

To this example， so let's say。Actually， maybe it's better to redo it here independently。



![](img/488b63677411758ad529a4b81a68b80a_38.png)

We have space， so let's say we have two nodes， we have I and node J。

And node I is connected to two other nodes and J has。Three neighbors， okay？

So each of these have identical so we start with the same scenario。

 we have identical features and now we're going to do the sum just so we do the sum。

Now we're going to get these guys three times， let's call it embedding E， okay， three times E， right？

And now what we're going to have here is two times e so these will be different。

 so now some here is actually very nice because in aggregation it allows us to distinguish。

Between these two topologies。😡，As opposed to for example， average。

 so if you take average or you take the max or you're going to add have it like exactly the same thing so these two guys so let me put it differently。

Actually， here we're going to have the so these two guys will map up to the same。

The same actually embedding right with these two functions and our functions are as I mentioned are here we can use the max or also the mean aggregation so these are not good right however the summation is actually good for aggregation so here we have some nice insights into which kind of aggregation we should use right。



![](img/488b63677411758ad529a4b81a68b80a_40.png)

![](img/488b63677411758ad529a4b81a68b80a_41.png)

So now this is something really nice and a nice example in the paper。

 but not can we guarantee that the aggregation function here is actually。



![](img/488b63677411758ad529a4b81a68b80a_43.png)

Ender。Alright， so maybe we don't want to use only summation all the time we want to use kind of we want to have more variability and a complex mapping of our embedding so if we use summation and may it may work out nicely。

 but we may want to use more complex things and have you know capture more complexity in these embedding so we may want to kind of you know map them differently not using a simple summation right so in learn how to map them in more complex linear way compared to this simple summation right here so the paper proposes that basically so in the paper the g paper they showed that。



![](img/488b63677411758ad529a4b81a68b80a_45.png)

![](img/488b63677411758ad529a4b81a68b80a_46.png)

![](img/488b63677411758ad529a4b81a68b80a_47.png)

![](img/488b63677411758ad529a4b81a68b80a_48.png)

![](img/488b63677411758ad529a4b81a68b80a_49.png)

We can actually max that so this is the final takeaway from the paper so how to maximize the expressiveness of a GNN model so we can use multilayer preceptrons so multilayer preceptrons they are universal function appromators which is you know a simple you know convolutional fully connected convolution neural networks so simple' sorry yeah so it's like fully connected network with not the the spatial convolutions just you know we're learning how to do multiplications and summation so it's a fully connected network and these fully connected networks they turn out to be universal function appmators so we can use them easily to model F and phi all right so these two functions that we want to have here table and also the readout function so。



![](img/488b63677411758ad529a4b81a68b80a_51.png)

![](img/488b63677411758ad529a4b81a68b80a_52.png)

![](img/488b63677411758ad529a4b81a68b80a_53.png)

Gin basically is a maximally expressive GenN among others that may exist and the Gin here what it does。

 it uses MLP layers to do you know it adds it up to the transformation layer that graphph neural network layers use GCN you're going top it up with an MLP and somehow this MLP that you add it right here right it will allow you to map injectively different inputs onto different outputs so this will allow you to distinguish you know like the neighbors because now it's a very simple idea every time instead of aggregating somehow adding here in MLP layer right that will allow me this MLP will depend on okay and this you know MLP layer。

 this new mapping function that I introduced here MLP map。



![](img/488b63677411758ad529a4b81a68b80a_55.png)

![](img/488b63677411758ad529a4b81a68b80a_56.png)

![](img/488b63677411758ad529a4b81a68b80a_57.png)

![](img/488b63677411758ad529a4b81a68b80a_58.png)

![](img/488b63677411758ad529a4b81a68b80a_59.png)

![](img/488b63677411758ad529a4b81a68b80a_60.png)

Will allow me to distinguish these。

![](img/488b63677411758ad529a4b81a68b80a_62.png)

You know， different topologies all right and map them differently so this is something really nice and。

Basically this is what they have proven in the paper if you read the paper so they discovered that by expressing Nphi as MLPs we can guarantee the expressiveness and the injectivity of the aggregation function that we have right here so when we aggregate we actually take you know so this is the neighbors right we take the neighbors here and we have seen before this is the self you can actually set up zero so they look at different cases where you actually remove this term and sometimes in other times it doesn't but just in a nutshell what we have here we have aggregation neighbor aggregation all that we do is that we replace instead of using a simple map。



![](img/488b63677411758ad529a4b81a68b80a_64.png)

Or mean or what else did you see guys the sum right which was better than the others we replaced these with an MLP and by doing so we can guarantee that we have basically this nice expressiveness okay so an expressive Gen block and take the following form so you can add an MLP before your conventional DNA layers so for example node classification or post layers you can do both combine both and this is something to kind of you know experience with and try and see you know what kind of behaviors you will get in terms of mapping different isomorphic isomorphic graphs with different with identical embedding and see what we can distinguish that with these functions and the paper goes through like kind of overviews set of you know a large set of experiment。

And you can have a read of that I think you will master deeply， you know， like the the。

The details of that of this whole again are lecture， but the idea is actually very simple。

 so instead of simply using well what we have used before I so just the message you take away is that instead of using a fixed a predefined so that's what they do using a predefined a fixed aggregation function or pooling function。



![](img/488b63677411758ad529a4b81a68b80a_66.png)

Function or fooling function， they make it learnable。All right。

 so it becomes learnable now the bad news with that is they increasing so even when it becomes learnable so it kind of you know these layers they may be you know they increase they require more。



![](img/488b63677411758ad529a4b81a68b80a_68.png)

![](img/488b63677411758ad529a4b81a68b80a_69.png)

Computal budget， so this increases you know， these layer may increase。

The compute budget for the network。For the network。

 because instead of using simply defined aggregation functions， we are learning them。Okay。

 oh so that was the again and I think towards the end of this it would be wonderful guys if you can take a few minutes remember how to define node invariance mathematically and intuitively run a total few examples note equivaris in GNNs and also expressiveness what does mean to have a highly expressive GNN and how can we guarantee that what is the key idea here okay thank you。



![](img/488b63677411758ad529a4b81a68b80a_71.png)