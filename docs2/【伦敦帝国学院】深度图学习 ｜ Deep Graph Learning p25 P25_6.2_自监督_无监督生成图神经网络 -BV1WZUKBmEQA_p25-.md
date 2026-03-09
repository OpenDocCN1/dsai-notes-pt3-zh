# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p25 P25_6.2_自监督_无监督生成图神经网络 -BV1WZUKBmEQA_p25-

Selfupvised or the unsupervised way of generating a graph。 So this is， you know。

 a different problem here that we're trying to solve， which means when we have self supervised okay。

 or unsupervised it means that we don't have。

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_1.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_2.png)

A targets so。So in self supervised and unsupervised generative GNNs。

 we are solving a different problem because here we don't have no target corresponding， okay？

Ground truth graph， which means given， for example。Given GS。Generate。

GT so we may not have GT here so we don't have the correspondence here we don't have that。

 so we need to learn how to generate in a fully self-supervised way。

 which means we only have the graph this is similar to clustering okay so given the the data itself you want to kind of you know use the data that you have to extract some meaning to do some pattern identification or here we want to do some generation you know data generation or graph generation okay so this is very different from the early tasks that we have seen previously so let's look at how we actually formalize this so as I said previously we learned that encoding graph structure how to encode graph structure by generating node embedding so we have seen this in graph classification and this is based on the aggregation。

 the local aggregation the computational graph that we have。

Folded the subree computational graph the transformation that we apply after the aggregation or before so this was the first part that we learned about GCNs and different pulling and update rules and message propagation rules etc okay so now graph neural networks can also be used to capture feature information and also graph structure okay so what we can do we can for example using graph encoders that we'll talk about in a bit we can learn how to you know map the graph to embeddings and this is actually what we have done somehow so we encoded the graph or embedded the graph so this part has been you know implemented or like explored previously encoded or embedded okay。

A given graph。G belonging to a set of graphs big G Okay， so now what we want to do So this is。

 you know， the encoding process， if we learn how to generate how to define the the opposite operation。

 which means now given you know the graph embedding we can use a decoder to transform the embeddings into graphs Okay。

 so and this is what we will do， this is actually the generative power so this is actually。

The generative。Power that we want to implement。 So basically， given the embedding。

 so given the embedding。 So let's say given。And embedding sometimes they call it here Z but if we call it HG right we can easily regenerate a graphG so that's the idea here and this is what we call decoding so we decode the embedding into a full graph all right so this is this is what we want to do eventually we want to generate new graphs from you know like a you know a certain compact representations this is one way of thinking or formalizing generative graph neural networks so why geneative graph neural networks are important there are so many applications so graph neural networks they allow us like you know graph generation is a process that can allow us to understand how graphs form how they expand how they shrink right how node get removed added etc right in a dynamic way we can also identify abnormal parts in the graph。

If you're working on network cybersecurity networks， you can identify threats。

 you can identify you know like certain vulnerabilities in the network or even in the code if you're mapping the code onto a graph so there are so many things so many applications that you can do predicting new structures if you're learning about if you're for example using drug data you can try to learn or predict a new structure of a drug that is able to treat a particular disease and it's so difficult you can spend you know like months and years trying to do drug discovery effective drug discovery but using GNNs now you can easily discover drugs you know across a variety of applications well of course not always easy but it takes less time right so now simulations of also as I mentioned novel graph structures graph completion which is basically。

Trying to complete a graph where partially a partial part of the graph is available。

 which means partially here， it means you know maybe notes， a few notes。

And edges slash edges are available。Okay so I mean there are so many things we can do and one example here is to generate a new kind of molecule that cures a certain disease so given a class of molecules like toxic and non-tin we want to you know generate we want new molecules that satisfy this class for example a particular class okay so we want to generate non-toxic molecules for example。

 now the second thing is generate the dynamic evolution of brain connectivity graphs so see how the brain evolves over time to spot atypical alterations and that may be related or linked to neurological disorders such as schizophrenia or autism or dementia right so you can see here it's so interesting to learn how to generate new graphs in general from a particular class a particular category etc okay so now let's look at the basics for this self-sup。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_4.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_5.png)

An unsupervised graph generation All right， so first。

We start with the P data P data is the data distributions。

 the graph distribution that we have so here we can see we have molecular data okay so given P data which is the data distribution unfortunately we can actually measure it or you know define it in a very accurate way so this is you know having access we need to have access to every single instance of molecular data for example a brain graph to cover the whole distribution to all possibilities of you know the manifestations or the sampling of a brain graph so we can do that unless we have access to every single instance and because we have limited data we collect only few samples a few representations this task is you know hard to solve okay so actually we don't know the distribution of the data and it's a high dimensional data remember guys like we have graphs or we have images。

These are a highdiional entities so trying to kind of model that high dimensionional complex distribution is really not an easy task and so basically here P data is represented but by the example so in the reductionist way by the example that we have so the existing samples of graph so if we have these samples the P data that we will just simply represented by the distribution of the data that we have which is the training data okay so here we can approximated here by the training data so this is the training data here okay so if you're right here so this is the train。

Data， okay， so the training graphs now the goal here giving graphs sampled from P data of G So G is like the graph that we want to as sample so we sample different graphs。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_7.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_8.png)

These are the sampled graphs from the distribution， so let's say for example。

 this is the distribution of P data okay so this is the distribution and what we want to do okay so i'm going to just copy paste it here。

All right。So in this example， next what we want to do is actually we we want to learn a good model okay。

 so we want to learn a good model that represents the graph and this means that if this model can recreate this data can kind of you know。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_10.png)

If this model is able to approximate this distribution which means recreate similar graphs to this train set right so we it means that these guys here that we created using the distribution of the learn distribution by our model right which is parameterized by theta it means that we are able to approximate the data distribution that we have that looks like this okay so let's say again so basically it's actually very simple given the graph sampled from P data we want to learn a model that represents these graphs so we want to learn the distribution P model of the given theta right that approximate the training data that we have and then after we learn this model is so easy the second step is to basically identify how to sample from this model so once we have the distribution we want to generate。

New graphs and to generate new graphs we need to learn how to sample from this complex distribution。

 So P model here is the model parameterized actually the model parameterized by theta that we used to approximate the distribution of the training data that we have Okay so so that's you know a simple thing so we want to create something we want to generate a data that has a distribution so maybe I can use a different color here so let's say。

Let's use a different color maybe green Okay so we want to generate a data here in the target domain by our model and we hope that the distribution of this data will be close to the pink one okay so if it is close it means our model is quite good and we are able to kind of you know to to approximate very well the original data distribution okay that we have here now one thing how to simple think about it so you randomly draw so you can draw from this distribution multiple values and as you draw this sampling process will allow you to create a new。

You know sample new graphs so basically what happened what happened here is that we learned the distribution。

 we learn this distribution， the P model， we learn the P model G given theta right and then once we learn it we can sample and as we sample we can create this set。

Okay so we can create all these graphs we can generate all these graphs through the sampling so sample or generate new graphs so our goal is to basically you know learn this model that allows us to kind of match this original distribution and once we do we can use the distribution that we learned to sample and generate new samples Okay so I hope it's clear guys I know i've repeated it multiple times。

 but yeah so that's the key idea now let's detail this a little bit more further so first。

So yeah so as you guys can see here， we don't actually have a ground truth which means each you know generated graph here doesn't have a ground truth to benchmark against here right so there is no matching but our ground truth is actually or not ground truth because we don't actually we don't have the ground truth so our approximation is the P data that we have here so the P data of G and our goal is to match this right so this is what we want to match and here is' like you know we want to be able to capture this distribution to the best of our capacity by optimizing the data。

 the parameters of our model and if we do that we are able to generate new samples and these new samples how can we evaluate their goodness it's a huge problem so we're going to talk about evaluation later on but the idea here is you can think about you know the distance between these two distributions and if it is if you can quantify the distance for example using KL div。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_12.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_13.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_14.png)

The closer these distributions are the better you would trust the quality of your generated graphs。

 but you you may need to add some other criteria like for example。

 that you generated something real and not something you know that is not valid so you need to check the validity you need to check the validity of these molecules and this is another thing so anyway so here basically it's fitting a distribution onto another one and these two steps are actually very easy so the first one is a density estimation so what we want is to use a maximum likelihood to make P model okay approximate P data so here we take the we want to discover the theta star which is our optimal the optimal parameters of our model where we take the average so on average okay or if we sum all these probabilities we want to。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_16.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_17.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_18.png)

The P model to approximate all samples in the data on average on average because we are taking the expectation here。

 so it's sort of an average okay and here the idea is that for every single you know like G in our data we want to regenerated you know using the theta here and if we have the theta that is able to regenerate the G drawn from this data distribution P data right then we have solved the problem quite nicely okay so the goal is to find。

 as I said， the parameters data star such that for the observed graph points。

 GI for all observed graph points if we have1 thousand graph points right as initial training set。

 what we want is the sum over all these points of the log the probability that is returned by the models of the density that。

Probability density that we have here has the highest value。

 so we want to maximize this among all possible choices of theta of course so here we can flip this and we can say theta star is minimizes okay theta if we take the negative of the expectation or the negative of the log and then we can turn this into a minimization problem so these are two different ways of formalizing this problem and the goal is as I said is to find the model theta that is' most likely to have generated the original observed graphs G okay so now the good thing this is called self-supervised y because you have here the distribution you have G right and what you want to do is you're taking the data itself to regenerate itself so you know self。

Regeneration。So I'm using the data here well'm oversimplified， of course。

 is the you know the P data here， the distribution， right？

Of the data and i'm trying to learn the theta star that allows me to create， you know。

 so i'm going to use different color I want to learn the theta star that allows me to create this distribution Okay again。

 so it's self supervision and this is what we call why we call itself。

Supervised because we use here self-supervision， some papers called also unsupervised。

 but I prefer the word self-supervised here okay so now the last step after we learned the theta star So we have our theta star so all is good we have our model we have approximated very well here now we can do the sampling so to do the sampling there are different strategies but this is one potential strategy and is first we want to sample from this complex distribution that we learned okay so the most common approach is to sample from a simple noise distribution。

 which means we take Z I， which is a normal distribution here and then what we do is that we transform the noise that I via our deep neural network function or genN function which was trained of course or optimize on the input graphs right and then we pass it through this function and then we're able to。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_20.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_21.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_22.png)

Generate a new graph。 So here by taking a noise。Some noise kind of you know representation are embedding we pass it through our network and this vector actually when we pass it through the network we will get the new generated graph so we will see how this works it may be very difficult to digest at first because here what you see is that you're having noise right and noise is like a random vector that looks like this and this vector has values 0。

8 maybe 0。1 0。52 etc cea and what you're giving to your network you're giving noise and you're getting something that looks real。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_24.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_25.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_26.png)

So how is this network training， So this is this is the key idea So how to train you know F how to learn F in such a way that if we give it some noise right and giving the optimal parameters that we have here of our you know model。

 the model that we have learned how can we get new graphs。 So imagine these graphs right here。

 So these have been generated each one of them from a random noise or random set。

 So we'll look at this in a bit and yeah， so these were the two sections。

 the first one is on a few examples on supervised generative GNNs and the second one on unsupervised where we had the selfsupervision here the self regeneration of selfsupervision where we try to match the input data itself so we don't have a target data we have only the input data that we're gonna use without any extra information to do the generation for here at this stage okay。



![](img/6403b0f538f5f7e36de0b2e4d736fdd4_28.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_29.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_30.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_31.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_32.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_33.png)

![](img/6403b0f538f5f7e36de0b2e4d736fdd4_34.png)

Cool。