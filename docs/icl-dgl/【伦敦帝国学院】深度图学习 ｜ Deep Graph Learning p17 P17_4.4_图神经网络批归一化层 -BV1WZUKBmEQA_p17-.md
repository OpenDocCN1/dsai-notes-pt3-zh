# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p17 P17_4.4_图神经网络批归一化层 -BV1WZUKBmEQA_p17-

So we have seen different graph sampling methods at the note level。

 the layer level and the subgraph levels， and this is basically to form the mini batches for our stochastic graining descent。

 loss optimization and weight updates。

![](img/bebeea53376b8a8762426882d28a35a2_1.png)

Now one issue that comes with batch based training is what we call the covariate shift。

 so the covariate shift here， if you look at these you know learned representations or embeddings okay。

 so the first dimension and the second dimension so F1 represents the first dimension of our of our learned factor okay。

The learned representation and we have also the second dimension here F2 and this is for layer one for the first layer if we take a single layer so layer one right and if we look at the relationship between these two covariates or these two features in our learned embedding and a particular you know neural network so this is taken by the way from the textbook machine learning refined by Jeremy what chapter 13 section6 so this figure is really beautiful because it shows us。

How the change or the variation in the covariate shift as we train the model so at the beginning of the training you can see the loss function here all right so this is our loss function and these are the parameters that we want to optimize and as we iterate as we as K basically increases at the beginning we have this kind of distribution of you know the relationship between these two features F11 and F21 but then as we start optimizing as we start you know kind of our gradient descent。

We see that the shape changes okay of this relationship and then towards the end of the training it dramatically changes it shifts so there is what we call a big shift between even two consecutive iterations you can see that moving from this point of you know the optimization iteration to the next one there is a big change in the relationship between the features which means our model is not stable because remember guys these features are the output of the activation function and the activation function takes in our W or our transformation right and if we're doing aggregation we're gonna to add the aggregation and a GNN model so all of this goes into the activation and after you get your activations you get the features or the learned embeddings right here the new representation so this new representation is not stable okay is unstable。

So unstable this instability presents a big problem。

So that motivated the proposal or the introduction of the batch normalization okay so the batch normalization or the BN layer in a neural network it aims it aims you know to stabilize the TNN training or deep learning training in general so batch normalization or batch norm it shifts and rescales each activation H right so that the mean and variance across the batch become values which we are learned during the training so let me explain so basically if we have the distribution。



![](img/bebeea53376b8a8762426882d28a35a2_3.png)

![](img/bebeea53376b8a8762426882d28a35a2_4.png)

Of the HK of our node embedding particular node embedding we're gonna to have maybe a distribution like this and then for HK plus one we will have a very different distribution right so this kind of shift dramatic shift or jump or big variation in distribution does not allow the network to stabilize and training because basically the distribution of each batch changes you know impacts these these learned embeddings so because as I mentioned earlier if we have know batch1 B1 with a particular distribution and B2 then you go over B2 with a second kind of distribution so all these you shifts in distribution they will not help you like a network to kind of convert and you know stabilize and its learning so the idea is to kind of constrain or to bring all of these batch distributions into a single uniform or predefined。

butionsWith I mean a shift in a scale to learn Okay。

 so with a particular shifting and scaling parameters to learn let's called them here we have gamma。

And we have sigma okay delta sorry delta so let's look at this so first we calculate the empirical mean of all elements in the batch so we take the embeddings of all nodes in our batch in in a particular GNN layer so this is done for at each layer independently and so this is this depends on particular layer of course so we can add the layer here if we want so we can put layer K right and this is layer K right so we can add the case here everywhere if we want but this is a a generic I would say formula all right so now we calculate the if we add it there so we can put here also etc so we can add it everywhere if we want but let's keep things simple for now and articulate that so basically we take the mean of all nodes in a batch so if we have you know a graph。

like this right and these are the sample nodes so we're going to take the mean embedding of all these nodes in this in this batch B okay now and also we do that we take the standard deviation so we compute the mean and variance over the batch B elements you know over B embeddings in batch B。

And next we do the normalization so the batch normalization basically we normalize each node embedding so the node embedding of node I layer K right so we're going to use the computed mean and variance so we will take the mean out and divide here so this operation right here is just you know the normalization process that we have and then this normalization process it brings everybody to a zero mean and we add an epsilon here to avoid dividing by zero division。

By。0ero， okay， so now for each。Note in the batch for each node I in the batch。

 we will basically update its embedding by doing this operation and this operation it takes in two parameters a shifting a scaling parameter gamma。

 so this is learnable per layer scaling。Perarameter。And then we have a shifting parameter。



![](img/bebeea53376b8a8762426882d28a35a2_6.png)

So both of these are actually learnable so we can optimize them so we can add them if we have。

 you know all our we have our W， we have our beta， the biases and all of that so we're going to add these you know two scalrs。

 the gamma and the deelta and our parameters to co- optimizetimize for our network for this particular layer GNN layer that includes a batch normalization。

 okay。

![](img/bebeea53376b8a8762426882d28a35a2_8.png)

So now the benefits of the batch normalization it has a lot of benefits so the first one is the higher higher learning rate which the batch normalization it kind of smoothest the surface of the loss so the gradient changes in a more kind of you know flowy away so this reduces the problem of zigzagging where you have the zigzagging remember guys happens when we have before we have seen that when you do training stochastic gradient descent for each point individually you will have different kind of shattered gradients and that you know makes the zigzagging like this to the optimum rate of your if you have your loss function now the batch is the same if you have you know this batch the first batch without any normalization and you have the second batch so these will have also different kind of you know average directions and that will cause some you know shattered gradient。

Whi means you know your your gradients will will get shattered in terms of directionality。

 so to kind of you know bring them all to the same direction。

 you do the batch normalization so one can。In this case if you smooth the function， if your function。

 if your loss function doesn't look like you know kind of very so this is not something maybe I don't know is like something like this so your loss function if it looks smoother if it's smooth then you can increase the learning rate you can jump you know make big jumps right but if it is not if it's kind of you know。

Very。It has a lot of narrow areas right that you cannot use a high learning rate so you need to kind of decrease your learning rate and in this case basically to avoid you know like for example if I do a big learning rate here I may miss some local optimum but maybe I wouldn't have something better later on so we can see that because it changes dramatically and quickly right so yeah so using higher learning rates with batch normalization。

Also here we can see that it regularizes， so as I mentioned there is randomness here。

And when we take the batches。So when we do the here the B and the batch when we add the batch normalization layer。

 this injects a sort of noise to the training process because the normalization depends on the statistics of the entire batch so remember the distribution of the batch impacts the learning so here the distribution of the batch impacts our learning so somehow as we do the gamma。

 the shifting and the scaling and this becomes learnable somehow this could be considered as a perturbation that we are introducing to our data distribution and this perturbation allows us to kind of you know regularize the learning so there's a lot of research on this topic very high levelvel research and really exciting research but yeah so just in a nutshell telling you guys about these kind of you know important kind of properties of batch normalization I may add some references as X resources for you if you want to read more on this。



![](img/bebeea53376b8a8762426882d28a35a2_10.png)

![](img/bebeea53376b8a8762426882d28a35a2_11.png)

![](img/bebeea53376b8a8762426882d28a35a2_12.png)

![](img/bebeea53376b8a8762426882d28a35a2_13.png)

![](img/bebeea53376b8a8762426882d28a35a2_14.png)

So injecting a noise model makes models generalize better and this is you know something that has been observed over and over again in the literature of deep learning and。

So for example， here， the activation of a given training sample， a given node， right？

It will be so oops so let me just a given note so the activation here remember when we do the activation we get the H the final embedding it's based on the activation of all this formula that the message propagation formula that we have right so this will be normalized by an amount that depends on the members of the batch because remember here the formula we have you know the H has been normalized with respect to first the mean MH and the standard deviation and this mean and standard deviation depends on the batch on the the batch itself the elements in the batch because it's calculated over the whole batch and then we learned the scaling and the shifting so in this example。



![](img/bebeea53376b8a8762426882d28a35a2_16.png)

![](img/bebeea53376b8a8762426882d28a35a2_17.png)

Basically the normalization somehow it depends on who is with you right so you will have a completely different mean if you have different members so this mean you know of these nodes as called it mean one will be different from mean two if we have for example these kind of notes okay these four node for example in a batch so these will change in because of that they will be process slightly differently depending on the elements of the batch and this is basically considered as as kind of you know it introduce variation into the learning and some sort of randomness also that is controlled by the scaling and the shifting and also by the normalization so we always want to have a controlled sort of kind of a randomness to not let things go out of the way so the last thing here is stable forward propagation。



![](img/bebeea53376b8a8762426882d28a35a2_19.png)

![](img/bebeea53376b8a8762426882d28a35a2_20.png)

![](img/bebeea53376b8a8762426882d28a35a2_21.png)

So in this case here we have let me remove this so the end it allows to control the variance of the learned embeddings and this is you know through the scaling and the shifting so we are controlling the H so here receives you know。



![](img/bebeea53376b8a8762426882d28a35a2_23.png)

Gmma H plus delta right so at each layer going from layer K to k plus1 we are controlling you know the distribution of the embeddings so this allows for a stable forward propagation through the scaling and shifting that is learned at each layer so of course the mean and the standard deviation they depend on the batch but these scaling we will learn each layer so we can bring everybody almost to the same kind of distribution but not identical because we want some diversity in our and the learned embeddings from layer to layer we don't want hk you know we don't want hk to be equal to hK plus one it means like we want them to be different but we don't want them we don't want them to be divergent so divergent is really something like you know extreme okay so here between the two consecutive layers so we want to control the variance of the learned em。

Between consecutive layers K and K plus1。And this stabilizes the network transformation functions。

 which are our mapping functions， W right， so the W function and any other parameters in our the transformation that we're learning are the features between neighboring layers。

So the network can easily control its O learning path and in a more effective way。

 so there is some control over there and here we can see this clearly in this figure so when we add batch normalization you guys can see that even if the distribution of the covariance is changing it's still oops let me use this one better。



![](img/bebeea53376b8a8762426882d28a35a2_25.png)

![](img/bebeea53376b8a8762426882d28a35a2_26.png)

It still follows the same path so here。Let me all right so it still kind of follows the same direction so it is kind of you know being scaled a little bit right like there is a scaling there。

 you can see them with here right but still you know it has the same direction so we're not we're learning the same relationship between these covariates that will control you know like the the final output right so you can see as we learner as we keep on optimizing our loss function we are it's still stable and you guys can also know this clearly that the loss function is much more stable is smoother compared to the first one on the same data set so adding this kind of you know batch normalization it's smooth just shape of the loss function and this is what we have seen before so that's why we can use higher learning rate it is regular compared to this one that is a bit kind of you know。



![](img/bebeea53376b8a8762426882d28a35a2_28.png)

![](img/bebeea53376b8a8762426882d28a35a2_29.png)

And it's not very smooth， all right？

![](img/bebeea53376b8a8762426882d28a35a2_31.png)

酷ol。So that was。

![](img/bebeea53376b8a8762426882d28a35a2_33.png)