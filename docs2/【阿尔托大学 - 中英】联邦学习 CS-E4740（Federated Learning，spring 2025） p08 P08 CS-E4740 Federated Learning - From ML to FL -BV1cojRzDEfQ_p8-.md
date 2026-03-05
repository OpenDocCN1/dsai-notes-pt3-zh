# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p08 P08 CS-E4740 Federated Learning - From ML to FL -BV1cojRzDEfQ_p8-

![](img/8fcf324176a316c183515131d3cfac91_0.png)

Okay so federated learning is of course a subfield of machine learning and what it sets apart is that instead of this basic machine learning setting where we train a single model by minimizing an average loss on a single data。

 we now have a whole network of different models， personal models and each of these models is trained by its own local data。

 so we in Python for example， maybe some of you have implement machine learning Python so this picture here might be familiar you this is a standard codenippet where you read in data you read in data somehow you store it in anumpiary X for the features and y for the labels you choose a model which is some Python object。



![](img/8fcf324176a316c183515131d3cfac91_2.png)

![](img/8fcf324176a316c183515131d3cfac91_3.png)

![](img/8fcf324176a316c183515131d3cfac91_4.png)

![](img/8fcf324176a316c183515131d3cfac91_5.png)

![](img/8fcf324176a316c183515131d3cfac91_6.png)

![](img/8fcf324176a316c183515131d3cfac91_7.png)

And you fit the model。 So you， this dot fit does in the end。

 nothing but trying to minimize the training error by tuning the parameters of this model。



![](img/8fcf324176a316c183515131d3cfac91_9.png)

And now from federated learning， we go sorry from machine learning。

 we go to federated learning with Python by just having several instances of this workflow。

 So you have one of these Python called snippets running on different machines。

 Each machine here is indicated by a different IP address and so how do they collaborate。 Well。

 they can collaborate while this read data function。

 So in this readT data function and this you will see then later in the course。

 how to implement this this readT data function could be， for example。

 reading data from this IP address and the information that is shared here is not raw data is not the raw data from this。

 but for example， a model pameter update like a delta W a model pameter update that is used somehow in in this read data function to generate new feature matrix and label vector you can turn model。



![](img/8fcf324176a316c183515131d3cfac91_11.png)

![](img/8fcf324176a316c183515131d3cfac91_12.png)

![](img/8fcf324176a316c183515131d3cfac91_13.png)

![](img/8fcf324176a316c183515131d3cfac91_14.png)

![](img/8fcf324176a316c183515131d3cfac91_15.png)

![](img/8fcf324176a316c183515131d3cfac91_16.png)

![](img/8fcf324176a316c183515131d3cfac91_17.png)

Pmeter into data you will see this later so like machine learning machine learning training turns data into a trained model。

 but you can also do it the other way， and we will use this to implement and construct federated learning systems which which just exchange this model parameter updates and similar you could use here and this rate data function on this device you could read in the data from here and from here。

And of course， you typically cannot communicate with all devices。

 but you have some network structure and we will encode this network structure or represent this network structure or communication structure of a federated learning system using this concept of federated learning networks。

 which we will see later。

![](img/8fcf324176a316c183515131d3cfac91_19.png)

So you see it's really a natural evolution of machine learning。

 Machine learning with Python is you have one data set。You have one data set and one model。

 you train the model on this data set In federated learning， you have several。



![](img/8fcf324176a316c183515131d3cfac91_21.png)

Models， so each one and yeah， by the way， here， we have here different models。

 So we will also see federated learning systems that can use different models for different devices。

 So this device here has SD stochastic gradient decent regressionor model type of model。

 This here has a linear regression model。 And this is a decision tree。

 So this quite different models。 But you will see how we can still couple them。

 how they still can collaborate with each other to get to train down each of these models better。



![](img/8fcf324176a316c183515131d3cfac91_23.png)

![](img/8fcf324176a316c183515131d3cfac91_24.png)

Yeah， and more， more abstract depiction of this generalization is you have here a single point cloud。

 This is this is machine learning here on the left。



![](img/8fcf324176a316c183515131d3cfac91_26.png)

We have your machine learning。And。On the right， we have federated learning。

 so we have several point clouds。And for each point cloud we want to train a different model。

 but somehow we want to also share information between those model training instances。Okay。

 so now the final part of this first lecture is just a quick recap。



![](img/8fcf324176a316c183515131d3cfac91_28.png)