# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p17 P117 Nyströmformer：基于Nyström方法的自注意力近似算法（AI论文解读） [BV1j8x5zJEvx_p17]

Hi there。 Today， we're talking about a nicetformer。

 a nicetom based algorithm for approximating self attention by Yung Yang Xong Champ Peng Cheeng。

 Ruraz Chakra Borti， Ming Xin Tan， Glen Fung， Yin Li and Vika Singh。So this paper。

 yet another paper that proposes a approximation to the self attention mechanism to the self attention matrix in transformer models。

 This time it's based on the nicetroom matrix approximation。

 That's why the model is called nicetroformer。 and why it is not called the nicetroomer。

 I don't know like you had you had the chance。 So I'm officially renaming this to the Ntroomer。 Okay。



![](img/35ad7f0539be3a3f94f43308cd53724c_1.png)

That's the that's the title now that's the model now， the nice dreammer by the way。

 if you're not in any language that has this sign or this sign， it's called an e， soer。

 you go oh but u。

![](img/35ad7f0539be3a3f94f43308cd53724c_3.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_4.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_5.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_6.png)

Well， it's， it's hard to explain。 In any case， as I said。

 this is an approximation to the self attention matrix。

The Itro method basically takes a subset of rows and columns sorry of keys and queries in this case and approximates the full matrix by just using this subset and we're going to look at how this works。

 but the promise is that you can scale transformers to much longer sequences without having the classic attention bottleneck that you'd have in transformers and the results so far show are pretty good for this model。



![](img/35ad7f0539be3a3f94f43308cd53724c_8.png)

No results in single papers， you know how I feel about those， but we'll check it out。

 we'll go through it。 if you have comments， let me know in the comments and don't hesitate to share the video out if you like content like this。



![](img/35ad7f0539be3a3f94f43308cd53724c_10.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_11.png)

Alright， let's dive in。 So there is a long discussion here about transformers and this。

 this kind of bottleneck， this quadratic memory bottleneck。

 And if you don't know what I'm talking about， you can go watch the video on attention is all you need or any of the transformer videos。

 The paper really starts down here。 with the introduction of self attention。

 So here we're dealing with self attention。 There is also something like cross attention。

 Like when you have an encoder and the decoder and you need to pass information from the encoder to the decoder。



![](img/35ad7f0539be3a3f94f43308cd53724c_13.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_14.png)

That is not self attention。 That is called something like cross attention。 or I。

 I don't actually even know what is called This model。 this paper deals with self attention， though。

 I know that lucid rainins and clash look on Twitter had a nice conversation about how you could do this also for cross attention。

 I'll， I'll link to it。 Check both of these people out。 Yeah。



![](img/35ad7f0539be3a3f94f43308cd53724c_16.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_17.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_18.png)

All right， so self attention， you have your input， your input signal， this is one attention layer。

 right it's usually multi head attention， but here will' just have one head。



![](img/35ad7f0539be3a3f94f43308cd53724c_20.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_21.png)

So you have your retention layer， which takes an input X。

 so your x is usually some kind of a sequence。

![](img/35ad7f0539be3a3f94f43308cd53724c_23.png)

And you want to transform it into another sequence。 So we've been here a bunch of times already。

 and you want to know， it's probably an equally long sequence。

 You want to know which information do you need to pass where。 So maybe。

This thing needs to inform those two， and this thing needs to inform those three。

 and this thing just needs to inform that one and so on。 So you。

 you sort of want to transform transform a sequence into another sequence in the next higher layer and。



![](img/35ad7f0539be3a3f94f43308cd53724c_25.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_26.png)

Yeah you want to kind of send information around so that every sequence element knows about every other relevant sequence element。

 the way you do this is by attention， so what you do is you construct these query key and value matrices of the attention mechanism simply by linear projection so you can see that the x here is an input to all of them。



![](img/35ad7f0539be3a3f94f43308cd53724c_28.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_29.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_30.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_31.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_32.png)

What do you do next is？You this is the crucial operation， you multiplies the queries by the keys。

 so essentially what you do is you express。

![](img/35ad7f0539be3a3f94f43308cd53724c_34.png)

The keys are as are vectors and basically every sequence element is advertising what it has to offer。

 so the keys are vectors， something like this， so every sequence element expresses a key and the key is an encoding of what the sequence what kind of information the sequence element contains and then every sequence element also expresses a query and the query I usually draw up here。

And that is what kind of information would this sequence element like to gather from its surroundings right so and then you do the inner product。

 you multiply each query by each key and you can see already like this element here is probably going to receive information from this and from this because the inner product is very high between the query that this expresses and the keys that these express and so on。

 so you can see that you need to multiply each query by each key that's exactly this operation over here。



![](img/35ad7f0539be3a3f94f43308cd53724c_36.png)

Query times keys， and that gives you a quadratic complexity in time and memory。

 basically so you have usually your query matrix and your query matrix is number of sequence elements。

 So your query matrix is number of sequence elements。



![](img/35ad7f0539be3a3f94f43308cd53724c_38.png)

Times the number of dimensions， so you have some kind of D dimensionality for your queries and here n is the sequence length right so you have one query per sequence element。

TheOne row here is one query。And then you have the keys and the keys and usually write the keys as a transpose matrix are exactly the same。

 So they are number of sequence elements times some kind of dimensionality。

 inner dimensionality Now I'm on purpose， I'm already drawing the dimensionality smaller than the number of sequence elements。

 because that's usually the case。 So the especially if you have multi head attention。

 the dimensionality can be lower or is often lower than the number of sequence elements N right here。



![](img/35ad7f0539be3a3f94f43308cd53724c_40.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_41.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_42.png)

And then you perform this product and what you end up with is as we set this end by N matrix。

So this is an n by n matrix and one element in this matrix is going to be the product， of course。

 of the corresponding query and key。Now。

![](img/35ad7f0539be3a3f94f43308cd53724c_44.png)

The we'll get to the rank in just a second。 The second notable operation here is this softmax operation。

 So after you put queries and keys together， you want to perform a softmax。

 and that is a row wise softmax。 It says it down here， a rowwise softmax， which means that in order。



![](img/35ad7f0539be3a3f94f43308cd53724c_46.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_47.png)

To really。 So this is， this is this here is simply queries， times keys。

 This is not the self attention matrix yet。 What you need to do is you need to put it through a softm。

 And in the softm， it's the same matrix， except it's normalized by row， right？

 So the softm is something like the softm of X is something like。Um。

At position I and like E to the X I divided by sum over j E to the x J。Right。

 so you exponentiate every element， and then you normalize by the whole row。

 So this is the normalization over the whole row。 It's sort of like。

The softmax at the end of a classifier where you just have a bunch of logitts at the end of a classifier So if this is your zero line。

 you have a bunch of logits， one says this is class is kinda likely， this one's not。

 this one's super likely， but it's just a bunch of numbers or your works give you a bunch of numbers and then through the softmax you transform that into a proper histogram where you know this one is the highest probability。

 this one a bit more and these two are just really low probabilitybabilities。

So the same softmax operation goes for here because ultimately you want to know from which point do you send information where and that is going to be a histogram。

 that is going to be a distribution over so the。

![](img/35ad7f0539be3a3f94f43308cd53724c_49.png)

There is this。Any sequence element？Seize the input then as a distribution。

Over where it should gather input from and how it should weigh it when it aggregates it。

 people have tried this without the softm， and it just turns out that it doesn't work as well。

 I guess in the future。 someone might come up with something that doesn't require normalization， but。

 you know， it is what it is right now。 Okay， so you need to normalize this。



![](img/35ad7f0539be3a3f94f43308cd53724c_51.png)

![](img/35ad7f0539be3a3f94f43308cd53724c_52.png)

And you can see that in order to normalize， you actually need the whole row。



![](img/35ad7f0539be3a3f94f43308cd53724c_54.png)

So you need the whole row。