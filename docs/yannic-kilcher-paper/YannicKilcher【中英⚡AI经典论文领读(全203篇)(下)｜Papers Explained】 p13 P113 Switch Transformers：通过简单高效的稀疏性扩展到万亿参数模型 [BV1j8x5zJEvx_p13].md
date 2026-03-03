# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p13 P113 Switch Transformers：通过简单高效的稀疏性扩展到万亿参数模型 [BV1j8x5zJEvx_p13]

Hi there。 Today we'll talk about switch transformers scaling to trillion parameter models with simple and efficient sparsity by William Fitus。

 Barrettzoov and Noam Schsir of Google Brain So as you can see right off the title Were going towards trillions of parameters GT3 had175 billion parameters this paper claims to have a model with a trillion parameters Now is it really five times bigger or 10 times bigger than G3 that's a debatable question because the trillion parameters are not used in the same way as in a classic transformers they are used actually in a sparse way that's why the word sparsity is in here and the way they are used in sparse manner is this new architecture called the switch transformer It's not entirely new it's built on mixture of experts in this paper。

That's also called M OE。 that has been around for a while。 And we're going to see what that is。 Now。

 on a high level， switch transformers takes mixture of experts to an extreme in that it is a transformer and。

The feet forward layer is divided up into these experts， and the switch transformer。

Only routes each token to one expert only。 That's the sparse part so。

The mixture of experts previously， they always claimed you need at least two experts in order to get a stable training signal。

 the switch transformer manages to get it down to a single expert。

 so it's like a hard routing of information。To just a single endpoint per layer of each token。

So that means you can now scale the experts and you can scale the number of parameters in the model without making the model compute more。

 that's a very special notion so you can up the parameters of the model but if a forward pass of a data point will still have the same amount of flops that it needs to forward propagate through the network very special architecture right here so yeah that's why I'm saying trillion parameters not necessarily comparable to the 175 billion parameters of something like GPT3。



![](img/fe65e4b5766816e306836b82be633f5a_1.png)

![](img/fe65e4b5766816e306836b82be633f5a_2.png)

So how do they do it， because previously was claimed it was unstable。

 they have new ways of making the training stable， such as selective dropout。

 selective casting of parameters to different precisions， and a better initialization。



![](img/fe65e4b5766816e306836b82be633f5a_4.png)

So that's the high levelve overview of the paper and we'll dive into it。

 we'll explore kind of what mixture of experts is and how the model works and what turns out it's a very long paper as you can see when papers have a table of content that's a lot of fun but it's a lot of engineering as well and we're mostly interested in the model here。

 what it can do and what how does it sort of fit in the big world of transformers and language models and so on Last thing I want to say trillion parameters is you it's a catchy title most of the paper they don't work with trillion parameter models they work with models in the order of billions of parameters and at the end they build a model with the trillion parameters。

 it doesn't do as well as their models as their smaller models also it feels like they don't put that much。



![](img/fe65e4b5766816e306836b82be633f5a_6.png)

![](img/fe65e4b5766816e306836b82be633f5a_7.png)

![](img/fe65e4b5766816e306836b82be633f5a_8.png)

![](img/fe65e4b5766816e306836b82be633f5a_9.png)

![](img/fe65e4b5766816e306836b82be633f5a_10.png)

![](img/fe65e4b5766816e306836b82be633f5a_11.png)

![](img/fe65e4b5766816e306836b82be633f5a_12.png)

work into it because it's probably also quite fuzzy and expensive。

 but just know we're not going to have trillion parameter models around anytime soon just yet。



![](img/fe65e4b5766816e306836b82be633f5a_14.png)

Interesting fact， the original resnet paper also built a 1000 layer convolutional neural network。

 even though the resnets we have today， you know they are maybe 50 or 150 layers deep。

 they did build a000 layer model， so it maybe compare it a bit to that one。

 it's just like we can do it not necessarily we need to。



![](img/fe65e4b5766816e306836b82be633f5a_16.png)

![](img/fe65e4b5766816e306836b82be633f5a_17.png)

![](img/fe65e4b5766816e306836b82be633f5a_18.png)

So here you can see something they discover。 The curve on the left is very。

 very known to people that are in the language model game。

 let's say or in the in the let's scale up AI game。

 and that is as you increase the size of the model。 the loss will go down。 and that's loss。

 as I understand it。 So that's test loss。

![](img/fe65e4b5766816e306836b82be633f5a_20.png)

I believe that is perplexity。So scaling properties exactly that that might be perplexity or test loss on some downstream task in any way。

 as you scale up the model parameters， the model gets better and better and better。



![](img/fe65e4b5766816e306836b82be633f5a_22.png)

The interesting thing right here is twofold。 First of all。

 I believe they do hold the data set constant。 So the data is always the same。

 The amount of compute you put into it。 The amount of either number of steps or time is also always the same。

 And in this specific case， the amount of flops per forward passes also the same。

 The only thing that changes is the number of parameters。 Again。

 it's very special to have a model where you can scale up the number of parameters。

 Yet the flops require to forward propagates stay the same。 So you can see here that。😊。

There is a almost unhalalted decrease here， it flattens out a little bit towards the bottom。

 though that is not necessarily does not necessarily mean it will ever flatten out before it's at zero。

I will approach zero I guess so and you can see that you know they scale up the model quite a bit and also their main comparison here is the T5 base so that's the text to text transform transformer by the way if you don't know what a transformer is or what a language model is。

 is best you go back to my earlier videos and look up like the the GPT3 paper or the attention is all you need paper I've made videos about lots of these things I assume that you know them。



![](img/fe65e4b5766816e306836b82be633f5a_24.png)

![](img/fe65e4b5766816e306836b82be633f5a_25.png)

![](img/fe65e4b5766816e306836b82be633f5a_26.png)

You can see right here that if you compare to number of training steps， for example。

These switch models， all of them， no matter how big they are。

 they provide massive gains over like something like a T5。



![](img/fe65e4b5766816e306836b82be633f5a_28.png)

And they also do this in time。So。

![](img/fe65e4b5766816e306836b82be633f5a_30.png)

This paper is very much about trade offs。 You do require more storage for your weights。

 so you have to have more memory， more RA。 however， that memory can be distributed。

 it can be sharded because they use this mesh Tensorflow library to implement the switch transformers and because their model has this sparsity。



![](img/fe65e4b5766816e306836b82be633f5a_32.png)

![](img/fe65e4b5766816e306836b82be633f5a_33.png)

They can efficiently shard the model。So you trade off more memory which can be sharded。

 but what you gain is training speed and both in terms of time and number of training steps required。

 so you are much more efficient note that this only all of this holds in this super large regime right they say they've also discovered these speedups in smaller models。

 but you know as far as the paper is concerned we are talking about millions。

 hundreds of millions of parameters， billions of parameters。

 even to trillion of parameters together with these giant corpora of text。

 so that's sort of the regime we are in and the results do not necessarily transfer down to the lower scale problems that you know you might face with your lonely one coab in the corner。



![](img/fe65e4b5766816e306836b82be633f5a_35.png)

![](img/fe65e4b5766816e306836b82be633f5a_36.png)

Alright， so in a transformer， you have a transformer is nothing else。

 but a bunch of these layers right here。 This is this is in in itself a transformer layer in its basic form。

 and it consists of sort of two parts。 It consists of this selfat right here。

 Now that's the standard transformer selfat。 That's what was introduced in attention is all you need and what's been used ever since in all the transformers。



![](img/fe65e4b5766816e306836b82be633f5a_38.png)

![](img/fe65e4b5766816e306836b82be633f5a_39.png)

This one right here is a， is an， as I understand it， a language model。 So， you know， this。

 this is very standard。 However， after the self attention。

 you have this feet forward layer now usually。

![](img/fe65e4b5766816e306836b82be633f5a_41.png)

![](img/fe65e4b5766816e306836b82be633f5a_42.png)

What you do is you have an input sequence and you transform that through multi head attention。



![](img/fe65e4b5766816e306836b82be633f5a_44.png)

Into another sequence right here and then what you do is you take each of these things and feed them through a feet forward layer。

 and as I understand it。

![](img/fe65e4b5766816e306836b82be633f5a_46.png)

This feet forward layer is simply。You know， a regular feet forward layer that you would find in an neural network and you pass them。

 you pass these things individually so this here it's a vector， you pass it。



![](img/fe65e4b5766816e306836b82be633f5a_48.png)