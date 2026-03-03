# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p21 P121 DeBERTa：采用解耦注意力机制的增强型BERT解码（机器学习论文解读） [BV1j8x5zJEvx_p21]

Hi there。 Today， we'll look at deerta decoding enhanced Bt with this entangled attention by Pgqing He Xiaong Liu。

 Zhang Feng Gao and Wai Zhu Zhen of Microsoft。 This paper is an improvement on Bert。

 the language model and the Roberta variant of it， specifically。

 it it suggests two improvement namely。First is this disentangle attention where they disentangle positional information and content information of the individual tokens in the attention mechanism。

 And the second improvement kind of results from the first improvement as this decoding enhanced decoder。

 I guess enhanced decoder， where， because they only use relative positional information in the transformer part of the model。

 they have to refe the absolute positional information at the end。

 which gives them another bit of improvement altogether with this。

 they reach state of the art in various NLP tasks。 And this model。

 deberta is now available in hugging face for you to download for all of your NLP needs。So。

We're going to go through the paper and look at the two improvements and what they give。

 Let's and see if that's relevant。As always， if you like content like this。

 don't hesitate to share it out to all of your friends and leave a like and a comment。

 I still read all the comments。 So give me your opinion。

And please also give me your opinions on the new recording setup。

 there should be a title somewhere here and a picture somewhere here。

 I absolutely want to hear feedback because I have no idea what I'm doing。 So yeah。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_1.png)

Alright， let's dive in Dierta or deerta or deerta。 I don't know。

 I think it's deerta because it's from decoding enhanced。 Dierta is a new model architecture。

 they say here。 we propose a new model architecture Dierta decoding enhanced Bt with disentangled attention that improves theert and roa models using two novel techniques。

 The first is the disentangled attention mechanism where each word is represented using two vectors that encode its content and position respectively。

 and the attention weights among the words are computed using disentangled matrices on their content and relative positions respectively。

 Okay， we'll look at that first。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_3.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_4.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_5.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_6.png)

So what they mean is when you have a multi head attention layer。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_8.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_9.png)

What we want to do is we want to transform one sequence of tokens of token representations into the next sequence of token representations。

 Now， usually every token， let's say these are our tokens。

 And this could be a sentence in a language like I am hungry。And here is like this， C。

 this classification token。That we always add when we train Bt。

 every one of these tokens is represented by a vector。Like， this is a vector。 This is a vector。

 It has many entries。 This is a vector。 Some of the vectors are thicker than others。 I mean。

 that's just a。This one just hasn't eaten enough。 So every one of these token is represented by a vector。

 And what a multi head attention layer does is it， it simply transforms this。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_11.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_12.png)

Via means of the attention mechanism into a series of vectors again。

 So we we put in a series of vectors， and we end up with another series of vectors。

 If you want to know what a multi head attention does in detail。

 please go look at my video attention is all you need where thats explained， specifically。

 it is a attention。 It is sort of an information routing algorithm that sees that sees how information needs to be routed from tokens to tokens。

 using queries， keys， values and so on。 If you haven't seen the video， Its a beautiful mechanism。

 But I'm not going to explain it again right here。 I'm sorry。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_14.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_15.png)

All right。So。In this。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_17.png)

What usually do is you transform vectors into vectors。

 And because of how the multihead attention mechanism works。

 the mechanism has no way to discern where in a sentence， for example， a given token is。

 so it cannot differentiate between this sentence here and the sentence。

 am I hungry if it's just multihead attention is just not possible for it。

 because it treats the incoming sentence as like a bag of words， which is not the case in。

 for example， a recurrent neural network， a recurrent neural network would go one by one。

 over these word representations and。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_19.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_20.png)

It has kind of a mechanism to see what a sequence is。 however multied attention doesn't。

 So what people usually do is they augment these representations with position andcodings。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_22.png)

So， that's。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_24.png)

At the beginning， you know， where you might ask， where do these vectors come from The very。

 of course， they come from the last layer， But the very first vectors you put in come from a table。

 And these are your classic word vectors。 So at some， at some point， you have a big table。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_26.png)

And the big table has your entire vocabulary in it。 So every word in the language that you consider。

 So there is I and there is am， and there is U， and there is Apple， and there is hungry。

 And there is even this C L S token。 All of them have a table entry。

 and all of them have a vector associated with them。 Now， these vectors are trainable。

 So the neural network can decide itself what goes into these vectors。

 But every word has a fixed vector in there。 And in the very first layer because you don't have a last layer to draw from。

 you simply look at what token it is。 you go to the table。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_28.png)

Right here。You retrieve this vector， and you put it here。 And that's your start。

 And then you transform up the layers， of course， every time from the last layer。

 But at the beginning， you have embeddings。 Now， the same thing you do for positions。 Okay。

 So you also have a second table， usually， and the original transformer paper。 by the way。

 these were fixed vectors。 but nowadays， I think most of them are also trained。

 So you label the position。 So that's position。 that's position 1， that's position 2，3 and 4。

 So for every position 2，3，4。 and maybe you have also 5 and 6， there is a maximum length。

 But right now we consider sentences of length。3 with a C L S token appended。 So these are length 4。

So every position also has a vector， and I'm going to actually draw these vectors。In this color。

 so every position has a vector。Irrespective of what word there is。 Okay， right now。

 we just have vectors for words， Irespective of where they are， and we have vectors of positions。

 Irespective of what words there are。 And what you do is same。 You look at what position is here。

 You go to the table。 you retrieve that embedding。 and you somehow also put it here。 Now。

 I've made a bit of a mess。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_30.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_31.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_32.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_33.png)

Here with this thing， sorry。So。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_35.png)

How do you now you have two vectors all of a sudden per word。 So you have one that is a position。

 and you have one that is the kind of the the word itself that represents the word itself。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_37.png)

And the neural network， it needs both in order to understand the sentence， right。

 if every word has these two vectors at the beginning， now it can understand。 aha。

 this is the word I that is at the beginning of the sentence。

 So it's probably the subject of a sentence。 However， if the word M was at the beginning。

 it could be， oh， it probably a question because it starts with a verb like M I hungry。

 And it can also evaluate the relative distances of things to each other and so on。

 So given this information， the neural network has all the tools it sort of needs to understand that sentence as a sequence。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_39.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_40.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_41.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_42.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_43.png)

Now。Well， you， you have， you have basically two ways of combining the two things。 First of all。

 you can concatenate them， which means that I'm gonna do it in this。 You just put， no。

 that's terrible。

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_45.png)

You just put the I'm not too skilled yet with this new thing。You put this on top here。

 Imagine this is the same length。 and you just concatenate the vector。

 So now the the vector is longer。 Of course， that also increases your dimensionality。

 computationalal issues and so on。 So what a lot of people do is they simply you know。

 line them up if there is the same size and they add them together element wise。 And， you know。

 in the worst case， the neural network now can decide because both of these are trained， right。

 So the neural network can absolutely decide that， you know， in the top part here。

 it simply learns a bunch of zeros。 And then the bottom part here。

 it simply learns a bunch of zeros here。 So essentially， it's a concatenation。 That's the worst case。

 in the best case， the neural network can actually do some kind of information combining already in this addition step down here。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_47.png)

![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_48.png)

Okay， so the。You， you give both encodings to the neural network as a single vector。 right。

 So what goes into the multied attention mechanism is a single vector。 This paper says that is。



![](img/63a5d853b650fb8badc4c5dd6ed1b6d6_50.png)