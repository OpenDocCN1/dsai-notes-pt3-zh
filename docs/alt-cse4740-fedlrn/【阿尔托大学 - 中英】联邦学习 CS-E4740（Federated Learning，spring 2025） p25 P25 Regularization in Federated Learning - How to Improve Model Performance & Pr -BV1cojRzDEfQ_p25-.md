# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p25 P25 Regularization in Federated Learning - How to Improve Model Performance & Pr -BV1cojRzDEfQ_p25-

![](img/2cdc13a1c0c332325285a6eec353460b_0.png)

We now use this network structure to implement regularization。

 Why do we why do we need to mess around with regularization or should we at all use this network structure。

 Why not just training at each each node has data has a local loss function has a local model。

 Why not having a simple machine learning algorithm running separately in each of these devices。



![](img/2cdc13a1c0c332325285a6eec353460b_2.png)

![](img/2cdc13a1c0c332325285a6eec353460b_3.png)

![](img/2cdc13a1c0c332325285a6eec353460b_4.png)

![](img/2cdc13a1c0c332325285a6eec353460b_5.png)

Well， the problem is typically these devices don't have access to enough data， or in other words。

 the local loss functions are not informative enough。



![](img/2cdc13a1c0c332325285a6eec353460b_7.png)

You can use these local data sets to build a training error。

 but this training error doesn't have enough statistical power or information to reliably train a model and typically the nightmare will happen of machine learning。

 which is overfitting。

![](img/2cdc13a1c0c332325285a6eec353460b_9.png)

![](img/2cdc13a1c0c332325285a6eec353460b_10.png)

Think of， think of a note here being a smartphone， like， let's say my smartphone， Alex smartphone。

 And I want to train a highly complicated model that tells me。



![](img/2cdc13a1c0c332325285a6eec353460b_12.png)

What activity should I do tomorrow， Should I run， Should I cycle， Should I swim and how long。

 How many minutes in order to optimally improve my fitness。😊。

I think I'm pretty sure this is a highly complicated physical process。

 this how how your fitness level evolves based on your activities and also your diet。

 So we need a typically a very high dimensional model like a large language model， for example。

 or transform a network。 And these models， they have billions of parameters。

 So you need typically on the order of billions data points in your training set。

And so I should have started a billion years ago and collect collect example data like workouts or the result of workouts。

 monitoring my my my weight and my body masss index， my my fat level。

 I didn't do and even if I started not to do it， I would never collect enough data。

 I would never collect enough samples， but there might be many other people who also use this fitness set。

 millions or billions of people。 and if each one of those donate one or two data points。

 then we might have enough。And this is the idea of federated learning as I teach it in this course。

 So we use the neighbors and the neighbors of the neighbors。

 so the spreads around the spreads through the network this information。

 we use the information of the neighbors to regularize the training of a local model。

 so I use the here for this blue node， I somehow use the neighbors model。



![](img/2cdc13a1c0c332325285a6eec353460b_14.png)

![](img/2cdc13a1c0c332325285a6eec353460b_15.png)

![](img/2cdc13a1c0c332325285a6eec353460b_16.png)

To regularize my model and this node in turn， uses its neighbors model training to regularize its training and so on and so forth。

 so we hop through the network via is a neighborhood regularization idea。



![](img/2cdc13a1c0c332325285a6eec353460b_18.png)

![](img/2cdc13a1c0c332325285a6eec353460b_19.png)

![](img/2cdc13a1c0c332325285a6eec353460b_20.png)

Okay， so that's I would say that's the main idea of the whole course or of the the main idea behind the federated learning methods that I teach in this course use the neighbors or the neighbors lost functions than the model training at the neighbors to regularize。



![](img/2cdc13a1c0c332325285a6eec353460b_22.png)

And now how， how can we do it？ So if you remember in basic machine learning or in the basic machine learning refresher that I。

 that I gave in the first lecture。

![](img/2cdc13a1c0c332325285a6eec353460b_24.png)

![](img/2cdc13a1c0c332325285a6eec353460b_25.png)

There are in principle  three perspectives or three ways you can do regularization。 And these three。

 these three opportunities correspond exactly to the three main components of machine learning。

 So what are the three main components of machine learning。The main component of machine learning is。

Data， we need data。 The second component of machine learning is models。

 So we we train local models in Feerated learning， and the third component is a loss function。

 And all these three components allowed to implement regularization。

 we can do regularization by augmenting data by collecting more data points in a very efficient way or automated way。

 So one one way to collect more data or to augment data is， for example。

 add a bit of noise to the features of a data point。

 Another way to augment data is use use symmetries， symmetries in a very general sense。

 like when you know that an image shows a cat than the rotated image still shows a cat。 So you know。

 the label of the rotated image。 But the features of the rotated image are different。

 So it's a different data point。

![](img/2cdc13a1c0c332325285a6eec353460b_27.png)

![](img/2cdc13a1c0c332325285a6eec353460b_28.png)

![](img/2cdc13a1c0c332325285a6eec353460b_29.png)

Or a shifted image of a cat， distiller kit。 So all the symmetries allow to augment the data。



![](img/2cdc13a1c0c332325285a6eec353460b_31.png)

![](img/2cdc13a1c0c332325285a6eec353460b_32.png)

And here we could， I mean， a very raw way to， to augment the data would be just ship the data sets of the neighbors to to the node where we want to train a model。

 Is this a good idea。

![](img/2cdc13a1c0c332325285a6eec353460b_34.png)

![](img/2cdc13a1c0c332325285a6eec353460b_35.png)

Is this a good approach to federated learning。 So this blue node， for example。

 gathers the local data from this blue node， from this blue node and from this red node from all its neighbors。



![](img/2cdc13a1c0c332325285a6eec353460b_37.png)

This would be one way that we use enable neighbors to regularize， just take。

 grab their local data sets。Would this be a good approach。Why， why is this typically not done。

 Mo could be done， but infeerated learning applications。

Why do you typically not send raw data between neighbors？For privacy reasons， yes。

 so the one of the of the。

![](img/2cdc13a1c0c332325285a6eec353460b_39.png)

Main motivations for federated learning as a field， as I observed it。

 was the privacy friendly way to do distributed machine learning and just sharing raw data between neighbors would not be privacy friendly。

 And I， for example， I mean， of course， Imm I'm a bit naive。 I like to share my， my exercise data。

 but for example， my personal healthcare records I would not share with my neighbors。



![](img/2cdc13a1c0c332325285a6eec353460b_41.png)

So we don't want to share raw data。

![](img/2cdc13a1c0c332325285a6eec353460b_43.png)

But we could do something else so we could somehow prune the local models。

 So one way to do regularization is to make the local model smaller， lower dimensional。

 So how could we prune them， Well， we could prune them by requiring to somehow agree over the edges。



![](img/2cdc13a1c0c332325285a6eec353460b_45.png)

![](img/2cdc13a1c0c332325285a6eec353460b_46.png)

![](img/2cdc13a1c0c332325285a6eec353460b_47.png)

So I could say this， this model here must behave similar to the model at the red node and by by requiring this consistency across edges。

 we essentially make the model smaller。 we make the hypothesis space smaller。 we prune it。



![](img/2cdc13a1c0c332325285a6eec353460b_49.png)

So this is odd option。 And here， this is already privacy friendly。

 So we don't really need here to exchange raw data。 So this is okay for federated learning。

 but the main focus of this course will be the third option。

 We will we will implement regularization by adding a penalty term in order to couple the training of neighbors。



![](img/2cdc13a1c0c332325285a6eec353460b_51.png)

![](img/2cdc13a1c0c332325285a6eec353460b_52.png)

So。Is there any questions at this point？

![](img/2cdc13a1c0c332325285a6eec353460b_54.png)

So these are the three options or the three ways we can do regularization in particular we want to do infedererated learning。

 we do regularization in order to exploit the information at neighbors at the neighbors learning tasks。



![](img/2cdc13a1c0c332325285a6eec353460b_56.png)

![](img/2cdc13a1c0c332325285a6eec353460b_57.png)

There are three ways to do it， and the focus of this course will be on the third way。

We use a penalty term， we add a penalty term to the loss functions， to the local loss functions。



![](img/2cdc13a1c0c332325285a6eec353460b_59.png)