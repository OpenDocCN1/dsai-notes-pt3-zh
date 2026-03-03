# Vizuara【中英⚡多模态LLM中的Transformer｜Transformers for Vision and Multimodal LLMs】 p17 P24 Implementing multi head attention with tensors ｜ Avoiding loops to enable LL [BV1X9zuByEuF_p17]

Hi， welcome back to a new lecture from Transformers forion series in today's lecture we will be once again diving into multi head attention in the last lecture we learned about how we can implement MHA or multi head attention in a naive way by simply looping through different attention heads and concatenating context vector matrices to produce the final context vector matrix so this part we looked at in the last lecture。

In today's lecture， we will see how to implement multi headd attention in a much more efficient way so that large language models can experience scalability using the technique called weight splits。

So today's lecture is going to be a lot of。Focus on dimensionality， there is batches。

 there are number of tokens each token has a dimension then there are attention heads in multi head attention and each attention head has a dimensionality so bunch of numbers you will be going to see in today's lecture so please pay good attention at the end of the lecture you will have a fairly good mathematical picture and a fairly good understanding about how multi head attention is actually implemented in practice in large language models。



![](img/65024829f6ffe188f357bcea39463f97_1.png)

🎼Yeah。

![](img/65024829f6ffe188f357bcea39463f97_3.png)

So one point that I want to mention before we proceed ahead is that this is the last lecture on attention mechanism。

In this series， so by the end of today's lecture you should feel very comfortable to think about the transformer block to think about the attention mechanism。

 to think about context vectors， and also to implement them in a simple Python code。

So let's first do a brief recap of what we looked at in the last lecture。

 what was multi head attention？So in multi head attention， we will have more than one query matrix。

 key matrix and value matrix， so this figure was summing up our full idea which we discussed in the previous lecture very nicely。

So let's say your inputs is bunch of vectors of say dimension 3。

 so your input vectors are three dimensional。So these input vectors we need to convert into query key value space。

But how do we convert this into query key value space using query weight matrix。

 key wave matrix and value weight matrix， so this is the weight matrix for query。

This is the weight matrix for key and this is the weight matrix for value。

In the absence of multi head attention or if the multi head attention just had one head。

 you will only have one weight matrix， but here you can see that there are two weight matrices WQ1 and WQ2。



![](img/65024829f6ffe188f357bcea39463f97_5.png)

Which will operate separately on the input to convert them into Q1， which is first set of queries。

 Q2， which is the second set of queries。So now in the query space。

 because this attention head has two two heads， this multi head attention has two heads。

 you have two query vectors。

![](img/65024829f6ffe188f357bcea39463f97_7.png)

Corresponding to every single input vector。Same thing applies for keys and values。

 so this is the most simplified form of multigri attention with two attention date。



![](img/65024829f6ffe188f357bcea39463f97_9.png)

![](img/65024829f6ffe188f357bcea39463f97_10.png)

Now， because you have two attention heads， you will have two matrices corresponding to your attention scores。



![](img/65024829f6ffe188f357bcea39463f97_12.png)

So how did you get the first attention how did you get the first query matrix Q1 Q1 was the product of your input x and w Q1 so x multiplied by WQ1 will give you  Q1。



![](img/65024829f6ffe188f357bcea39463f97_14.png)

X multiplied by W Q2 will give you Q2， so this is matrix multiplication。



![](img/65024829f6ffe188f357bcea39463f97_16.png)

Now， what if x is6 by3 matrix， what does this mean there are six tokens and each token has three dimensions and let's say the。



![](img/65024829f6ffe188f357bcea39463f97_18.png)

![](img/65024829f6ffe188f357bcea39463f97_19.png)

![](img/65024829f6ffe188f357bcea39463f97_20.png)

Qury key value space has a dimensionality of2。

![](img/65024829f6ffe188f357bcea39463f97_22.png)

Which means here the dimensionality of a single token is2。So I should have six tokens。

And each token should have two dimensions here also I should have six tokens。

 each token should have two dimensions， correct？

![](img/65024829f6ffe188f357bcea39463f97_24.png)

Same thing applies for value and keys also。

![](img/65024829f6ffe188f357bcea39463f97_26.png)

So how do you convert a 6 by3 matrix into a 6 by 2 matrix， you simply multiply with a 3 by2 matrix。

So your Wq1 will be a 3 by2 matrix， your Wq2 will be also a 3 by 2 matrix。

 so this 3 by2 matrix will convert your 6 by 3 matrix which are six tokens with each of them being three dimensional it will be converted into six tokens with each of them being two dimensional and like that you will have two attention heads and because of that you will have two queries corresponding to every single input token。



![](img/65024829f6ffe188f357bcea39463f97_28.png)

![](img/65024829f6ffe188f357bcea39463f97_29.png)

Now to calculate attention scores， usually what you do is you take the dot product between query and key so Q dot key transpose or Q multiplied by Q transpose。

So here you have now two attention score matrices， not just one。



![](img/65024829f6ffe188f357bcea39463f97_31.png)

Each of dimension what it will be I mean， although I have drawn it as3 by3 here。

 if we have six tokens， we should have an attention matrix。

 attention score matrix of dimension 6 by6。And like that we should have two attention score matrices the first matrix will be the result of dot product between Q1 and K1。

 so this is Q1 do K1 transpose I'm not sure how much you can see the transpose T its a little bit blurred the second one is Q2 do k2 transpose。



![](img/65024829f6ffe188f357bcea39463f97_33.png)

So this first matrix will be the attention scores between queries and keys in the head number one。

 the second matrix which is behind will be the attention scores between queries and keys in head number2。



![](img/65024829f6ffe188f357bcea39463f97_35.png)

![](img/65024829f6ffe188f357bcea39463f97_36.png)

Now， attention scores are converted to attention waves by first you doing scaling。



![](img/65024829f6ffe188f357bcea39463f97_38.png)

Then you perform masking so scaling is division by  one by square root of dimensionality of the key space。

Let me reduce the thickness of the pen。So scaling is done by。

Dividing by square root of decay per decay is the dimensionality of the key space。

 in our case the dimensionality of the key space is2。Masking is done by putting minus infinity。

 so this will be minus infinite。This will be minus infinite， this will be minus infinite。

 so that when you take softmax， all the upper triangular elements will become zeros。

 so softmax of minus infinity in a series will be 0 because softmax is eraase to x。



![](img/65024829f6ffe188f357bcea39463f97_40.png)

E raiseds to Z I divided by sigma E raised to Z I， so if Z i is minus infinite。

 e raised to minus infinite will be 0。

![](img/65024829f6ffe188f357bcea39463f97_42.png)

So all these items will become zero after taking softftmax。



![](img/65024829f6ffe188f357bcea39463f97_44.png)

And then you apply dropout so here now you convert attention scores into attention ways because every row will sum up to one so this will be one this might be like 0。

8。2 it's not 3 by3 by the way we are considering six tokens but if our input had only three tokens this would have been perfect so if this instead of this being six if it was just three tokens each being dimension three then this three by three representation is perfect because you have three keys and three queries。



![](img/65024829f6ffe188f357bcea39463f97_46.png)

![](img/65024829f6ffe188f357bcea39463f97_47.png)

![](img/65024829f6ffe188f357bcea39463f97_48.png)

And similarly， the last row will also sum up to be more， so these are attention weights。



![](img/65024829f6ffe188f357bcea39463f97_50.png)

Now you apply dropout mask with a certain probability， so if probability p is equal to 0。5。

 randomly you will be masking half of the elements from your attention weights matrix。



![](img/65024829f6ffe188f357bcea39463f97_52.png)

And the remaining elements which are not masked will be scaled up by a factor of 1 by 1 minus p。

This also we discussed in the last lecture of the reason why why this scaling is done is because if we don't do the scaling now you are expecting similar magnitude output with on an average half the number of values or half the number of parameters。

 which is not possible because you are on an average reducing the number of available parameters by half。

 which means the remaining half of the parameters should do the similar job so that the values of those weights should be。

Scaled up proportionate to the probability with which you are performing masky。



![](img/65024829f6ffe188f357bcea39463f97_54.png)

Now after you perform dropout you have now your final mass attention weights with dropout and then you are ready to calculate the context vectors。

 how do you get context vectors this attention weights after dropping out you multiply with values so value is again you have two attention you have two heads head one and head two so you have two value matrices in after dropout also you have two matrices so those are attention weights after dropout you have two attention weight matrices then you drop out in each of them separately so you have two dropout matrices the mat number one is this。



![](img/65024829f6ffe188f357bcea39463f97_56.png)

![](img/65024829f6ffe188f357bcea39463f97_57.png)

![](img/65024829f6ffe188f357bcea39463f97_58.png)

Matrix number two is the one behind and then corresponding correspondingly here in values you have v1 which is the first value matrix。

 this is v2 which is the second value matrix so if you have three input tokens with each of them being three dimensional here you will have three tokens each of them being two dimensional here also you will have three tokens。

 each of them being two dimensional。

![](img/65024829f6ffe188f357bcea39463f97_60.png)

![](img/65024829f6ffe188f357bcea39463f97_61.png)

![](img/65024829f6ffe188f357bcea39463f97_62.png)

Now。When you multiply the。Attention waits after dropout with values。



![](img/65024829f6ffe188f357bcea39463f97_64.png)

You will get context vectors z so what is the dimensionality here by the way this should be 3 by 3 because we just initially we also started with6 by 3 we later changed it to3 by3 just for the purpose of illustration。

 so three tokens each of them being three dimensional which means your attention weight should also be 3 by 3。



![](img/65024829f6ffe188f357bcea39463f97_66.png)

![](img/65024829f6ffe188f357bcea39463f97_67.png)

![](img/65024829f6ffe188f357bcea39463f97_68.png)

![](img/65024829f6ffe188f357bcea39463f97_69.png)

Now you have this one being three by three， this is also three by three。



![](img/65024829f6ffe188f357bcea39463f97_71.png)

And three by3 by two， you will multiply with3 by3 to get。



![](img/65024829f6ffe188f357bcea39463f97_73.png)