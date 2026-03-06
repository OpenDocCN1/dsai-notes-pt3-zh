# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p39 P39 CS-E4740 Single Model FL -BV1cojRzDEfQ_p39-

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_0.png)

Okay， to start with the single model federated learning， which was also maybe the starting point。

 the starting point of federated learning was or the first works on federated learning who defined the field so to say they consider a single model。

 So you want to train a single model let's say a large language model which is trained at some big computer that could be a server。

 a web server， but to train a model， you need data。 machinech learning is based on data。

 We need data to train a model， and this data could be often distributed over many different clients。

 So in this single model federated learning， we want to train a single global model having parameters W superscript K case the iteration index to an iterative process K indexes time steps。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_2.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_3.png)

And we want to improve the， the， this global model parameters using local data sets。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_5.png)

And one basic approach， maybe the first approach was infeerated learning was。

Take the current guess for global model parameters at time K。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_7.png)

Broadcast it to all clients。 and each client who has some small chunks of local data computes a local update。

 So it， it gets a current guess for the motor parameters。

 and it uses its local data set to improve it。

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_9.png)

And then after each one or each of these grants has done this local updates。

 these update updated local model parameters are sent back to the server。

 which aggregates them somehow。

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_11.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_12.png)

Yeah， there's a question here how？Can you think of specific implementations of this update。

 So what could we do to update a current choice for motor parameters based on data。

What are widely used update techniques。To improve model parameters using a bit of data。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_14.png)

So I give you a model current choice for model parameters。

 You have your own local data set that you have collected labeled data points。

 How can you use your own local data set to improve the model parameters。Any guesses， ideas。Well。

 one one trivial update would be to do nothing， so to use as new updated model parameter the same one as before。

But， I mean， the advantage of this is it doesn't use much computation。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_16.png)

But the disadvantage is， it doesn't pick up any of the information that is in your own local data set。

 So how can we transform the information in in a local data set into an improved bottle parametermeter。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_18.png)

How can we extract the fuel in the data， So to say or turn the the fuel， the data fuel into work。

In to do something useful， to finding a better choice for model parameters。

What's the elementary transforming step in machine learning or one of the this elementary transformational steps。

Well， gradient descent or stochastic gradient descent。 That's exactly it is。

 So gradient descent is a way that is is a procedure or a technique to turn a data set into a model update。

 model parameter update。And these updated model parameters are then sent back to the server。

 which are aggregated。

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_20.png)

For example， computing the average。Or some more fancy average， like a trimmed mean。

 which could be useful for， for cyber securitycur to compute the new estimate for the global model parameters。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_22.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_23.png)

And here， here' is this Ser client implementation of the single model federated learning algorithm。

W whichhich is， yeah。Based on a single server， the disadvantage is， of course。

 the server is a single point of failure。 So if somebody gets the server down。

 the whole federated learning system doesn't work anymore。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_25.png)

That's why it might be better to use something more distributed or decentralized。

 which is exactly what what what we do when we use G TVV minimization。 And actually， we can。

 we can translate this server client setting into an equivalent G TVV mean instance。

 using a federated learning network， which is connected。

 All we need to do is we need to make sure that the network is connected。

 This is already the case by a star graph。 and choose alpha large enough。

 if we choose alpha large enough。 The solutions of G TVV minimization will be constant。

 will be the same。 So they， we can then interpret interpret these solutions as copies。

 copies of the global model parameter。

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_27.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_28.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_29.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_30.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_31.png)

Okay， so this was。

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_33.png)

The first main flavor， which is single model federated learning。

 And it turns out it's just a special case of GTV minimization。😊。

Using a connected graph and a very large choice for alpha。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_35.png)

![](img/a81512c2f7f9cf6b912adb1fe7b4d140_36.png)

Or large， large value for this regularization parameter alpha。



![](img/a81512c2f7f9cf6b912adb1fe7b4d140_38.png)

Okay， then let's move on to the next one。