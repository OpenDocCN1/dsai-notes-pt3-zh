# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p59 P159 《稀疏性在扩展Transformer中已足够（又名Terraformer）》｜机器学习研究论文解读 [BV1j8x5zJEvx_p59]

Hello there。 Today， we'll look at sparse is enough in scaling transformers by researchers of the University of Warsaw。

 Google research and Open AI。 This paper on a high level proposes a set of building blocks to introduce sparsity into transformers and this results in an architecture called the scaling transformer In the second half of the paper。

 they then introduce additional features to the scaling transformer to make it into theterraformer。

 Both the scaling transformer and the terraformer， they are really fast at what they call unbached decoding decoding is essentially inference in such a transformer model and unmatched means that they can do this for single sample。

 Of course they're also faster in batched decoding， but I guess the effects are not as pronounced。

 and we're going to see why because the sparsity really shines through if you have single examples and can only activate very small parts of the network。



![](img/7f10b752bfb2355609a7e74425148d39_1.png)

![](img/7f10b752bfb2355609a7e74425148d39_2.png)

![](img/7f10b752bfb2355609a7e74425148d39_3.png)

![](img/7f10b752bfb2355609a7e74425148d39_4.png)

![](img/7f10b752bfb2355609a7e74425148d39_5.png)

At the same time。So the effect of all of this， at least for the scaling transformer is right here。

 if you have a model with 800 million parameters， I guess today that we call a small model the baseline transformer has a decoding time of about 0。

16 seconds whereas if you add all the tricks to the scaling transformer you speed that up by a factor of about 2。

6 x that's not that pronounced yet yet the effect really shines if you go to bigger models。

 So if you go to a 17 billion parameter models， the baseline transformer takes about 3。

6 seconds on this particular hardware to decode theterra no sorry the scaling transformer with all the tricks activated takes about 0。

18 seconds giving a speed up of 20 x and so in different settings on different configurations the speedups can in fact get even higher I've seen up to like 37。



![](img/7f10b752bfb2355609a7e74425148d39_7.png)

![](img/7f10b752bfb2355609a7e74425148d39_8.png)

![](img/7f10b752bfb2355609a7e74425148d39_9.png)

AnX or something like this， which is quite， quite fast。 And this all。

 while the performance doesn't degrade。 and that is surprising。



![](img/7f10b752bfb2355609a7e74425148d39_11.png)

![](img/7f10b752bfb2355609a7e74425148d39_12.png)

![](img/7f10b752bfb2355609a7e74425148d39_13.png)

So they say surprisingly the sparse layers are enough to obtain the same perplexity as the standard transformer with the same number of parameters。

 So they have the same number of parameters。 It's just that they activate them sparsely when forward propagating。

 which is much faster and needs much less memory。And this results in the same perplexity when language modeling。

 so essentially means that the performance is on par and also they say。If they。

If they integrate with prior sparsity approaches， that's where they achieve the terraformer。

They can do fast inference on long sequence even with limited memory。

 This results in performance competitive to the state of the art on long text summarization。

 which is another thing where their model is state of the art or equivalent to state of the art while being much more sparse。

 much more memory efficient and much faster。 So yeah， we'll dive into this， the architecture。

 it's quite it's quite a mess。 like there are engineering tricks， engineering tricks。

 engineering tricks and you know you have to wander a little bit， you know what came first。

 like which trick came first and which trick necessitated， which other trick。

 but we'll go through the architecture through all the different pieces and you'll see what this is all about and where the savings are done。



![](img/7f10b752bfb2355609a7e74425148d39_15.png)

![](img/7f10b752bfb2355609a7e74425148d39_16.png)

![](img/7f10b752bfb2355609a7e74425148d39_17.png)

![](img/7f10b752bfb2355609a7e74425148d39_18.png)

![](img/7f10b752bfb2355609a7e74425148d39_19.png)

![](img/7f10b752bfb2355609a7e74425148d39_20.png)

Right， if you enjoy content like this， you know， don't hesitate to subscribe。

 I don't want to do the other YouTube will show the graph。 I'll， I'll do like， I'll do this。

 Here's the graph。 Here's the graph。

![](img/7f10b752bfb2355609a7e74425148d39_22.png)

So many of you are not subscribed。 I mean， look at that。 Excelt， alright so。



![](img/7f10b752bfb2355609a7e74425148d39_24.png)

The point with these sparsity gains is that if you implement them somewhere， then that part is fine。

 But then another part is still a dense and is still the bottleneck。

 So you kind have to introduce them everywhere。 So if we look at a classic transformer model and they specifically I think。

 refer to like the stack of attention is all you need and so on。

 So what they have basically is they have two attention modules。 So there's attention one。



![](img/7f10b752bfb2355609a7e74425148d39_26.png)

![](img/7f10b752bfb2355609a7e74425148d39_27.png)

I think there's attention2， and then there is this feed forward layer。 Okay。

 so we're going to take care of all of those right here。 Attention1 is called self attention。

 So if I have a sequence， coming in here， the self attention would be essentially attention in between the elements of the sequence。



![](img/7f10b752bfb2355609a7e74425148d39_29.png)

![](img/7f10b752bfb2355609a7e74425148d39_30.png)

![](img/7f10b752bfb2355609a7e74425148d39_31.png)

The second attention block is I think encoder decoder attention or something like this。

 the variant vary a little bit right here， but I would have sort of a second stack of this right here。

 I would have a input sequence right here so this would be the input this would be the target sequence that I'm about to decode maybe this has some causal attention who knows。

The second layer of attention here is specifically attention that goes to the encoder sequence right here。

So it's attention in between the encoder and the decoder and the feed forward So this essentially these two mix all the information of the different tokens together and the feed forward layer simply takes a single embedding of a single token and feeds it through a feet forward function。

 So all the tokens are handled by the same feet forward function。

 The first thing this paper does is essentially eliminates the distinguishing between the selfatten and the attention between encoder and decoder and I think that makes sense that's also what a lot of other models do。

 So famously Bt is an encoder only model。 G is the decoder only model。

 And if I understand them correctly there as well， they're simply taking the encodings from the source and then just preending them to the target or something like this you know safe to say there are lots of things that。



![](img/7f10b752bfb2355609a7e74425148d39_33.png)

![](img/7f10b752bfb2355609a7e74425148d39_34.png)

Could do right here， but。

![](img/7f10b752bfb2355609a7e74425148d39_36.png)

What I wanted to say is that we now need to replace each of those things with a sparse version。

 so we need a sparse feet forward， and we also need a sparse attention block。



![](img/7f10b752bfb2355609a7e74425148d39_38.png)

So how we're going to achieve this。 First， we're go to the sparse feet forward layer。 Remember。

 a feet forward layer is I have a sequence of embedding。 So that's these are all vectors。

 and these are all embedding vectors。 This is a sequence of embedding vectors that came out of the attention module。

 right？ and the feet forward layer essentially is a matrix。



![](img/7f10b752bfb2355609a7e74425148d39_40.png)

And。I simply pass each of these through a matrix。 in fact， it's not one matrix。

 I think it is usually two matrices， one matrix that sort of， well， that's not how you draw a matrix。

Like this and then like this。so you kind of blow up the dimension in the middle and then here there is a really non linearity in between。

And the point is what I already said， you'd feed every single token by itself through this function。

 so this becomes like a large token， then there's a relu， and then this would become sort of。

A token of the input dimension again， and you feed this token through as well individually。

 which give you this one and so on。So in essence， we have a vector right a token。

 all the tokens are independent， we have a token， and somehow we need to make this sparse right now it's a dense multiplication twice。

 so there's two matrices right here and if have dense multiplication right So what do we do。



![](img/7f10b752bfb2355609a7e74425148d39_42.png)

![](img/7f10b752bfb2355609a7e74425148d39_43.png)

The first thing they say is that， well， given that there is a relu non nonlinearity right here。

 right， there's a relu， a lot of the things here essentially are going to end up being zero right So it makes sense。

 it makes sense to do sparsity here Now I don't I don't follow that entirely you know。

 I guess half of the stuff will end up being zero yet the sparsity goes much further。 So。



![](img/7f10b752bfb2355609a7e74425148d39_45.png)

![](img/7f10b752bfb2355609a7e74425148d39_46.png)

![](img/7f10b752bfb2355609a7e74425148d39_47.png)

![](img/7f10b752bfb2355609a7e74425148d39_48.png)

But maybe maybe they maybe they justify why they can set some things to zero， not entirely sure。

 but I found that reasoning a bit shaky， but here is essentially， you know。

 you don't need a reason to introduce sparsity if it works， it's good。So here is how it works。



![](img/7f10b752bfb2355609a7e74425148d39_50.png)

First， and this is what I found a bit confusing。 so it essentially starts on the right and it goes to the left。

 but I guess it's easier to start on the left。 So what we want to do。



![](img/7f10b752bfb2355609a7e74425148d39_52.png)

You see here is that input vector right and here is that first matrix。

 so the first matrix is of dimension D model which is the same as this dimension and DFF。

 which is the feed forward dimension。And usually I just multiply that together。

 which would give me a vector in the dimension of the feet forward layer。

 which I then send through my re。

![](img/7f10b752bfb2355609a7e74425148d39_54.png)