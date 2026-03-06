# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p44 P44 Federated Learning - Coupling Personalized Models Explained -BV1cojRzDEfQ_p44-

Okay， so how do we do it， How do we build a penalty and the ideas as follows。

So let's consider we have two nodes which represent two devices。

 So we have a node I and a node I prime。 These are two devices。

 let's say my smartphone and my friends， smartphone or my neighbors smartphone and the neighbor and me。

 we collect our own data like activity logs from our exercises。 So we each of us collects data。

 And then each of us wants to train a model， a fitness advisor app。 Let's say。

 but we somehow want to agree on on a few certain things。 So I know， for example。

 that my neighbor is similar to me and that we don't like to do running when it rains。



![](img/1bf0a47fcc49af3355594379ff70d76a_1.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_2.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_3.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_4.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_5.png)

And this kind of agreement we can implement by forcing the trained models。

 So I have a trained model here for me for I and node I and the trained model。

 this red curve for nodede I prime to agree on a test set。



![](img/1bf0a47fcc49af3355594379ff70d76a_7.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_8.png)

And this test set could be carefully selected reference days。 So like specific days in the past。

 where there were specific weather conditions and where we， we both agree what to do。

 Let's say there was one day where it was 35 degrees。 So we both decided to go swimming。



![](img/1bf0a47fcc49af3355594379ff70d76a_10.png)

And this， we can enforce by making this discrepancy of these two hypotheses on the test set small。



![](img/1bf0a47fcc49af3355594379ff70d76a_12.png)

That's the main idea behind all the methods that we will learn in this course。

And but we can use different ways to measure the discrepancy like like the loss function for machine learning methods。

 also the measure the discrepancy measure here， how you measure this discrepancy in detail is a design choice and one of these design choices is the squared error loss so we can compare the predictions of these two models on the test set。

 this gives us predicted values or let's call them pseudo labels and we compute the squared error loss。



![](img/1bf0a47fcc49af3355594379ff70d76a_14.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_15.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_16.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_17.png)

Between those two。 And this gives us a measure for the disagreement of the trained model at node I and node I prime。



![](img/1bf0a47fcc49af3355594379ff70d76a_19.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_20.png)

What else could we use to measure the discrepancy， Well， if this。

 if these models are not regression models so they don't deliver numeric quantities。

 but they deliver labels or categories， then we， then the square error loss is typically another good choice。

 And we could use something like the cross entropy。



![](img/1bf0a47fcc49af3355594379ff70d76a_22.png)

So whatever you， you know from basic machine learning methods as possible loss function。

 you could also use for this discrepancy measure。

![](img/1bf0a47fcc49af3355594379ff70d76a_24.png)

Yeah， I would like to point out that this test set。

 this test set on which we compare those two models， this can be different for， for different edges。

 So this test set。

![](img/1bf0a47fcc49af3355594379ff70d76a_26.png)

Is tailored to a pair of nodes。 So this test set is only used for node I and I prime and for another pair of nodes for another edge in our federated learning graph federated learning network。

 we might use another test set。

![](img/1bf0a47fcc49af3355594379ff70d76a_28.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_29.png)

![](img/1bf0a47fcc49af3355594379ff70d76a_30.png)