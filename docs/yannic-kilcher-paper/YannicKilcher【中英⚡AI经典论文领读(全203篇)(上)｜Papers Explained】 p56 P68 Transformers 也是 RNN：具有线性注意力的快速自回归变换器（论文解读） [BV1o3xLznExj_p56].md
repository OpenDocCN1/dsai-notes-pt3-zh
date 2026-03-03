# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p56 P68 Transformers 也是 RNN：具有线性注意力的快速自回归变换器（论文解读） [BV1o3xLznExj_p56]

Hi there Today we're looking at transformers or RNNs。

 fast autoregressive transformers with linear attention by Angalocaopulos。

 Aor Viage Nikolaauos Papaas and Fransoa flure so this paper on a high level proposes to interpret the attention mechanism in transformers with in terms of a kernel function and therefore the resulting higher dimensional linear operation can be used to formulate the linear transformer。

 which is orders of magnitude faster than a classic transformer。

 they also show that in the case of autoregressive transformers makes the transformer essentially equivalent to a special kind of RNN so yeah that's what this paper is about and I think some comments to make that I haven't really seen made by others though I have to admit so haven't really looked at many comments。

I might just be telling old boring things as always， if you like content like this。

 consider sharing it out， leave a like if you liked it leave a comment to let me know what you think I do read the comments and they're generally comment section is very very helpful to me and also people you know respond to each other it's fairly cool to see that the community is usually very helpful to people asking questions。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_1.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_2.png)

And yeah， just let me know what do you think。

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_4.png)

Alright， so what's the problem with transformers。 And I've done many videos on transformers。 And I。

 you know， keep referring back to them for people who don't know what it is。

 But there's this original paper called attention is all you need that where I made a video about that。

 So if you don't know what transformers are， you can go look at that。

 that should basically cover everything you need to know。

 But there's many more transformers in the meantime。 There's Bt G to G。

 whatever the number is after that，Many sequence processing models are now transformers。

 Many set processing models are now transformers。 So this has reached a very， very。

 made a very big splash in the community。 So essentially。

 transformers come with this attention mechanism where you have an input set， actually。

 but let's consider it a sequence。 So a sequence of text， maybe like I have。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_6.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_7.png)

An ice cream cone， something like this。 And you want to classify the text。

 or you want to perform language modelling。 So in language modelling， the problem is as follows。

 I give you this piece of text。 And I ask you to predict the next piece of text。 This is。

 this was kind of the first task that these transformers were used on。

And this is what is called an autoaggressive transformer because you always have a piece。

 you predict the next piece， and then I give you that next give you that entire piece。

 and then you predict the next piece yet again and so on。

 And this autoaggressive property is going come in play in this paper later。 But ultimately。

 what you have in a transformer is called an attention mechanism。

 So an attention mechanism is the following。 Each layer in the transformer。

 you can imagine as having the same number of nodes kind of same number of neurons as your sequence is long。

 Now， from this input sequence， you're going to generate。For each of these tokens。

 you're going to generate three different things。 You're going to generate a key query in the value。

 So in in this you do from so usually this doesn't come in form of a letter right。

 This comes in form of some kind of embedding vector。

 And from that you're going to generate three different things。

 I should probably use different colors for for So this is a function。

 You're going to produce three different things from that。 you're going to produce a key。

 you're going to produce a query and you're going to produce a value。Now， the key。

Is you can imagine it being attached to this lower layer right here。

 So that's the key for this this token right here。 That's the key。

 the key here for that token right here， it's a word piece right So the keys again are also just you know vectors。

 vector vector。 The query you figuratively attached to the top layer right here。

 So the queries they go here for each token and they are also vectors。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_9.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_10.png)

And the values will keep out of it for now。 So the queries and the keys define basically how you route the information and you route the information。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_12.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_13.png)

By going over each so each each。

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_15.png)

You have to imagine each token right here， this have or have。

It needs to aggregate information from all the other tokens。

 right So we're going through multiple layers of this。 And in each layer。

 each of these tokens is aggregating information from the other tokens。

 If we do this in multiple rounds is eventually， you know， each token is aggregating information。

 eventually each token knows about all the other tokens。

 But how this information aggregation is done is very important， for example。

 if the token is a pronoun。 It would be very interested in information coming from any sort of named entity in the sentence。

 because it very much wants to know what it is referring to， if you are。

 if you are the the pronoun in the sentence， it is very vital that you understand which of these things you refer to。

 So you'll start aggregating information for that。 And then once you know。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_17.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_18.png)

Who or what you refer to， then the other parts of the sentence can make use of that information so they will start requesting information from you and。

So layer after layer， each token aggregates information from each other token， so this works by。

 let's say we're at this token right here， what we're going to do is we're going to form the inner product between that vector and each of these vectors and then we're going to transfer that into a softm which makes this into a first of all。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_20.png)

There's so we do the query together with all the keys， key。

 and then we run it through the exponential function。

 and after that we're going to normalize it by the sum of all the exponential functions that will give us a properly normalized distribution。

 so a histogram basically of where we are going to get our information from。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_22.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_23.png)

This is going to be the highest where the inner product right here is the highest。

 So from this token right here。 and， you know， this is fairly， fairly。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_25.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_26.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_27.png)

Standard， what I drew by accident is fairly standard that a token probably wants to know a lot about itself。

 so you want to carry forward the information that you already have in this particular token that's why your inner product is going to maybe align a lot with your own key So the keys andqueries are learned。

 So each token decides what kind of information it wants to advertise to the others and then also each token decides what kind of information it wants to gather from the others。

And the the routing then is put through a softmax function and that gives you this right here。

 you do this for every single token。 So the problem with this is that every single token needs to do the inner product of its query with all the different keys。

 then each of that has to go through the softmax and then the value that's actually aggregated are these values right here Now the values are simply a transformation of the incoming values。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_29.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_30.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_31.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_32.png)

Values are what's really propagated。You can think of it as just like a one layer neural network ultimately you could also leave away the values。

 people don't do this some people do the same queries and keys。

 but the values are just a transformation of your input so the important thing is this right here this decides how you're going to aggregate the values。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_34.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_35.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_36.png)

All right， so this has a quadratic complexity， so if if you have n input tokens。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_38.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_39.png)

Then this entire process will require n squared operations because you need to form the inner products between each pair of queries and keys and it also is going to require that much memory and we're going to see this is in large part due to this softmax operation because because we have a softmax it makes the whole thing non nonlinear and it being- nonlinearar basically means we'll have to you store everything。

 keep everything around and we have to recompute for each query we're going to see in this paper formulation where if we make the whole process linear。

 then we will not have to do that。

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_41.png)

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_42.png)

So let's dive into it。

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_44.png)

So here they go linear transformers。

![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_46.png)

They start off with saying each transformal layer is essentially this right here。

 so this is kind of a higher level of view what we've viewed so far is just this part right here。

 this is the attention routing mechanism each layer is actually wrapped in a residual connection。



![](img/245f91c13fdb65fdf9c4fb96c3e3e7b8_48.png)