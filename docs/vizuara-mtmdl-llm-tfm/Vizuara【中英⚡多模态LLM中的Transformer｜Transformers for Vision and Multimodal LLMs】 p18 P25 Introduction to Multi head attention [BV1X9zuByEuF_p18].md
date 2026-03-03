# Vizuara【中英⚡多模态LLM中的Transformer｜Transformers for Vision and Multimodal LLMs】 p18 P25 Introduction to Multi head attention [BV1X9zuByEuF_p18]

Hi， welcome back to a new lecture from Transformers for Vision series。

Today we will be discussing about multi head attention。

I will give you a brief recap of our journey so far at the beginning and then we will see how much we know and you will truly realize that multiai attention is in fact very simple because we have already discussed causal attention in the last lecture。

So there are two approaches。For implementing multi headard attention that we are discussing in this series in the current lecture。

 we will be discussing the approach using concatenating the context vector mattressrices that we get out of each attention head。

And then after that， in the next lecture， we can discuss a bit more unified approach which is adopted by modern large language models。

If you don't know what is。Attention， self attention， causal attention， etc。

 I highly recommend you to watch the immediately lectures that are immediately before this one so that you will have better context。

And especially if you have fairly good idea about the causal attention that we discussed in the last lecture。

 you will find today's lecture very easy with that let us get into the lecture。😊。



![](img/9ee25835d3a75e4248dba079b676d078_1.png)

🎼Yeah。

![](img/9ee25835d3a75e4248dba079b676d078_3.png)

So first， let's have a brief recap of what all did we learn so far in this understanding of transformer architecture？

We first looked at the transformer architecture itself as a whole。

 so here in the last part of this I have a figure so we looked at the transformer architecture as a whole。

And then we discussed it in three parts， input， transformer block and output。

But there we did not go into details of the multi headd attention。



![](img/9ee25835d3a75e4248dba079b676d078_5.png)

So we kept multiha attention alone separate， but we looked at the rest of the architecture。



![](img/9ee25835d3a75e4248dba079b676d078_7.png)

And then we started to discuss about attention， So first we started with Ba and our attention。



![](img/9ee25835d3a75e4248dba079b676d078_9.png)

In the context of neural machine translation。Yeah。After this。

 we discussed about self attention and when we implemented。

 we first implemented a simplified self attention。So here we did not use any trainable weights。

 we simply said the attention score between two input embeddings or two vectors is simply the dot product between them。

And once we have the attention scores corresponding to one query。

 we can normalize those attention scores to get attention weights。

 so this is what we did in simplify itself attention。But in the lecture following， we。

Discussed self attention with trainable weights。And here for the first time。

 we introduced the weight matrix for WQ for query。WK for key and W V for value。

And here we discuss that instead of directly taking the dot product between the two input embeddings。

What we do is we transform those input embeddings into query key value spaces。

 then we take the dot product of the transformed input embedding。

In query space and transformed input embedding in key space， so we got query dot key transpose。

Q dot k transpose。And then we said we will scale this by the square root of dimensionality of the key space。

 square root of dk。And then we said we will take softm of this resulting attention weight。

 so what we get out of this is the attention weights， so we will take softm of this。

And after taking softmax， actually before this it will be attention scores and softmax will give us attention weights。

And once we have attention weight matrix， we can multiply it with a value matrix。😊。

So this is basically the input embeddings converted into value matrix。

So this was the final context vector matrix that we can get out of the。嗯。

Attention with trainable weights。So this was what we discussed two lectures ago。

 and then after that we discussed causal self attention。😊，Or mask self attention。Yeah。

So this is what we discussed in the lecture before。So in causal self attention or causal attention。

 what we discussed was the following。

![](img/9ee25835d3a75e4248dba079b676d078_11.png)

![](img/9ee25835d3a75e4248dba079b676d078_12.png)

First we have input embedding， so here we have 1，2，3，45。

 we have five input vectors in three dimensions。So total。

 this matrix will be a 5 by3 dimensional matrix。And then we want to transform each of these vectors into the query space。

 key space and value space。So query space dimensionality is2 according to our assumptions。

 so we said we will use query key value spaces of dimensionality 2 instead of three。

So to convert5 vectors each of dimensions 3 into5 vectors each of dimension 2。

We used a transformation matrix of dimension 3 by 2。

 so 5 by 3 multiplied by 3 by 2 will be a 5 by 2 matrix。

So this transformation matrix was the query weight matrix， which is a trainable matrix。😊。

Like this well have another trainable matrix to convert the same input embeddings into keys and same input embeddings into values。

😊，So these three are the trainable matrices which perform the transformation of input into query key and values。



![](img/9ee25835d3a75e4248dba079b676d078_14.png)

Now once we have these three， first what we do is we calculate the attention weights so first wetry to get the attention scores you multiply you take the dot product between query and key。

 so to get the dot product you multiply Q with the transpose of key。



![](img/9ee25835d3a75e4248dba079b676d078_16.png)

So this is phi comma 2 because you have5 input embeddings and in the query space each of them is two dimensional。

 so iss phi comma 2 the transpose of key is 2 by 5。

And then the result of this matrix operation will be matrix multiplication will be a  phi by5 matrix and this is the attention scores。



![](img/9ee25835d3a75e4248dba079b676d078_18.png)

And then， we said。To create masked attention。

![](img/9ee25835d3a75e4248dba079b676d078_20.png)

Where we want to mask the future keys。

![](img/9ee25835d3a75e4248dba079b676d078_22.png)

Basically， queryry should not pay attention to keys that are supposed to come in the future。

 we want to mask the upper triangle。So all these values， we wanted to have it to be0。



![](img/9ee25835d3a75e4248dba079b676d078_24.png)

For that， what should we do？We should have those numbers as negative infinity when we are applying softftmax operation because softftmax operation is eases to x。



![](img/9ee25835d3a75e4248dba079b676d078_26.png)

![](img/9ee25835d3a75e4248dba079b676d078_27.png)

Divided by sigma era rise to x so e is to minus infinity is 0。

 so if we had minus infinity before we applied softmax。

 then those numbers will become0 after application of softmax。



![](img/9ee25835d3a75e4248dba079b676d078_29.png)

![](img/9ee25835d3a75e4248dba079b676d078_30.png)

![](img/9ee25835d3a75e4248dba079b676d078_31.png)

So， what we did was the attention scores that we got。

 we converted the upper triangle into negative infinity numbers。



![](img/9ee25835d3a75e4248dba079b676d078_33.png)

Then， we scaled。

![](img/9ee25835d3a75e4248dba079b676d078_35.png)

The dot product。 So this is the dot product， Q dot。Key transpose， Q dot or。



![](img/9ee25835d3a75e4248dba079b676d078_37.png)

Qury is multiplied by key。

![](img/9ee25835d3a75e4248dba079b676d078_39.png)

And then we scale it。Basically this scaling is done to reduce the variance or keep the variance of the resulting dot product numbers equal to 1。

 so we saw that the variance scales with square root of d so if you divide by square root of d where d is the dimensionality in this case the dimensionality is 2 the dimensionality of the query key value space。

So since the variance of the resulting attention scores， which are these numbers。

 numbers inside this is proportional to square root of d。

 if you divide the resulting matrix by square root of d， you can keep the variance close to 1。



![](img/9ee25835d3a75e4248dba079b676d078_41.png)

![](img/9ee25835d3a75e4248dba079b676d078_42.png)

So this resulting thing is called scaled dot product because we are scaling by square 1 by square root of d。



![](img/9ee25835d3a75e4248dba079b676d078_44.png)

![](img/9ee25835d3a75e4248dba079b676d078_45.png)

And the scale dot product we were normalizing using softmax so softftmax is applied row by so that each row will sum up to1。

So this was the mask self attention because you are basically applying a mass negative infinity。😊。



![](img/9ee25835d3a75e4248dba079b676d078_47.png)

Is the upper triangle， so this mask will produce a final output of zeros in the upper triangle。



![](img/9ee25835d3a75e4248dba079b676d078_49.png)

And then。😊，Each of those rows through some of the one because these are normalized attention weights。

 so the first item will simply be one because dream as a query。Has only one key to focus。

 which is dream itself dream cannot see big because in this sentence。

 big comes after dream and you are preventing the tokens or preventing queries from accessing the future keys。

Big has access to only3 and big。So the sum of these two should be one。

 some of these three should be one， so every row should sum up to one。



![](img/9ee25835d3a75e4248dba079b676d078_51.png)

Then at the end of the last lecture， we discussed about a dropout mask。



![](img/9ee25835d3a75e4248dba079b676d078_53.png)

Which。Drops out these attention weights randomly at a certain probability。



![](img/9ee25835d3a75e4248dba079b676d078_55.png)

So if the probability is such that if we are dropping out at 0。5， let's say half of the。



![](img/9ee25835d3a75e4248dba079b676d078_57.png)

Half of these items are masks masked。Then we said the remaining numbers。



![](img/9ee25835d3a75e4248dba079b676d078_59.png)

The remaining numbers in this。

![](img/9ee25835d3a75e4248dba079b676d078_61.png)