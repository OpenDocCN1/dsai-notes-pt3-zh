# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p28 P28 Cluster Structure of Solutions in GTVmin - Local Models in Federated Learnin -BV1cojRzDEfQ_p28-

The next question is， how do we know that these solutions are any good。



![](img/2601f23486a59372fd75c1500fefbb76_1.png)

So we could。 we could evaluate this W head that we get。

So this W head superscript I is one part of this W head vector。 We get this W head I by。

 by reading out the chunks of this W head vector。

![](img/2601f23486a59372fd75c1500fefbb76_3.png)

![](img/2601f23486a59372fd75c1500fefbb76_4.png)

That I talked about before。How do we know that they are useful， Well。

 we could evaluate the local laws， but the local laws can be misleading。



![](img/2601f23486a59372fd75c1500fefbb76_6.png)

![](img/2601f23486a59372fd75c1500fefbb76_7.png)

So the local loss that we get can be equal to 0， but still。

 the model parameters that we got are not useful at all。



![](img/2601f23486a59372fd75c1500fefbb76_9.png)

This is overfitting so we can， we can suffer from overfitting。



![](img/2601f23486a59372fd75c1500fefbb76_11.png)

And there one way to， to circumvent or avoid this problem is to aggregate the local loss function。

 So to look， to look for other local model parameters that are approximately similar or to cluster the devices。

 according to the local models。 So when two devices have similar local model parameters。

 they belong to the same cluster。And we can also get then this ego cluster or local cluster from the perspective of node I by by pullinging together all nodes that have similar trained model parameters add node I。

 S node I。

![](img/2601f23486a59372fd75c1500fefbb76_13.png)

And then we can evaluate， we can evaluate this W head I using the aggregate。



![](img/2601f23486a59372fd75c1500fefbb76_15.png)

By， by summing all these local loss functions in the cluster。



![](img/2601f23486a59372fd75c1500fefbb76_17.png)

Okay， so what about this cluster structure？It turns out that the solutions of GTV minimization。

They form clusters。 So this is essentially a form of spectral clustering。



![](img/2601f23486a59372fd75c1500fefbb76_19.png)

It's spectral clustering taking into account the local loss functions。



![](img/2601f23486a59372fd75c1500fefbb76_21.png)

And these clusters， so the clusters that form depend on two things。 First。

 they depend on the network structure。If there are many Hs between nodes with high weight。

 then we get a cluster and to depend on this alpha。 So this alpha。



![](img/2601f23486a59372fd75c1500fefbb76_23.png)

![](img/2601f23486a59372fd75c1500fefbb76_24.png)

That appears here in， in GTV minimization， this alpha， this。Prameter or regularization strength。

 alpha。This kind of modulates globally， the， the edge weights。

So it's like a global extra factor that makes the edge weights larger or smaller。

 And when we make them very large。

![](img/2601f23486a59372fd75c1500fefbb76_26.png)

The class has become larger and larger。 At some point， when we use a very， very large alpha。

 the solutions of G TVV minimization will be。Almost identical at each node。 So we。

 we train the same model at all node。If we make alpha large enough and this could be useful for some applications and some applications。

 and actually the the original setting of federated learning was about training one single model that is used by everybody。

 but in a privacy friendly way。 And this you can achieve with GTV minimization。

 just by you making alpha large enough。Making alpha for large enough results in solutions in local model parameters that are almost the same at each node。

 So you train essentially the same model at all nodes。

 But in a privacy friendly way because you solve in a distributed fashion。

 you solve this optimization problem。

![](img/2601f23486a59372fd75c1500fefbb76_28.png)

![](img/2601f23486a59372fd75c1500fefbb76_29.png)

![](img/2601f23486a59372fd75c1500fefbb76_30.png)

Okay and to make this precise， you can derive bounds。

 so when we when we look at a federated learning network which is connected。

 which means that it has a fela eigenvalue or a second smallest eigenvalue larger than0。

And the the loss functions are somewhat aligned。 So the loss functions must admit an approximate minimizer。

 common minimizer。 This is what this assumption says。 So there is one。

 one choice of motor parameters such that it minimizes approximately all the local loss functions。

Then if you solve GTV minimization， it turns out that the solutions are very tightly grouped around the。

 the average of the model parameters。

![](img/2601f23486a59372fd75c1500fefbb76_32.png)

And you can even develop a bound so you can upbound this this variation of the local model parameters around its mean by this quantity。

 So this depends on the on this epsilon， which is the measures。

 how how well these local loss functions are aligned。

 So if all nodes would have the same local loss function。



![](img/2601f23486a59372fd75c1500fefbb76_34.png)

![](img/2601f23486a59372fd75c1500fefbb76_35.png)

![](img/2601f23486a59372fd75c1500fefbb76_36.png)

Then this epsilon would be0。But typically， the local loss functions。

 they are a bit different because they are constructed from local data sets that might have sampling noise in them。

 So they are a bit misaligned and this misalignment is covered or captured by this epsilon。



![](img/2601f23486a59372fd75c1500fefbb76_38.png)

The smaller the epsilon here， the， the smaller the epsilon。And we can we can assure this。

 this condition means that the better aligned are the local loss functions。



![](img/2601f23486a59372fd75c1500fefbb76_40.png)

So for a small epsilon， this deviation is small。 On the other hand， if we make alpha very large。

 if we pump up this GTV mean parameter alpha， we can flatten out or ironing out。

 so to say the lo model parameter， so to become more and more concentrated around their mean。



![](img/2601f23486a59372fd75c1500fefbb76_42.png)

![](img/2601f23486a59372fd75c1500fefbb76_43.png)

Which means there is no， no variation between local models anymore。Okay， any questions at this point。

嗯。

![](img/2601f23486a59372fd75c1500fefbb76_45.png)

Yes， yeah。 also the questions at the chat。