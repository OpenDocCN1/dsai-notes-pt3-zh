# 斯坦福大学《深度学习自然语言处理｜Stanford CS224N NLP with Deep Learning 2024》中英字幕（deepseek-R1 - P8：-08-2023 _ Lecture 8 - Self-Attention and Transformers.zh_en - GPT中英字幕课程资源 - BV1U5RNYgEfp

![](img/ff239821ddd1fbac07988d7751909a2b_0.png)

![](img/ff239821ddd1fbac07988d7751909a2b_1.png)

Hi everyone。 welcomelcome to CS 224 N。 We're about two minutes and so let's get started。

 So today we've got one I think is quite an exciting lecture topic。

 We're going to talk about self-atten and transformers。

 So these are some ideas that are sort of the foundation of most of the modern advances in natural language processing and actually sort of AI systems in a broad range of fields。

 So it's a very， very fun topic。 Before we get into that。😊，Okay， before we get into that。

 we're gonna have a couple of reminders。 So there are brand new lecture notes。 nice， thank you。 Yeah。

 I'm very excited about them。 they go into they， they。

 but they pretty much follow along with what I'll be talking about today。

 But go into considerably more detail。 assignment 4 is due a week from today。 Yeah。

 so the issues with Azure continue。 thankfully。 thankfully，😊。

Our Ts especially has tested that this works on coabab and the amount of training is such that。

 you know you know a coab session will allow you to train your machine translation system。

 So if you don't have a GPU use coabab。 We're continuing to work on getting access to more GPus for assignment 5 in the final project。

 will continue to update you as we're able to but know the usual systems this year are no longer holding because companies are changing their minds about things。

 Okay So our final project proposal you have a proposal of what you want to work on for your final project。

 will give you feedback on whether we think it's a feasible idea or how to change it。

 So this is very important because we want you to work on something that we think has a good chance of success for the rest of the quarter。

 that's gonna be out tonight， we'll have an Ed announcement when it is out。

 and we want to get you feedback on that pretty quickly。😊。

Because you'll be working on this after assignment5 is done。

 really the major core component of the course after that is the final project。Okay， any questions？

Co， okay。嗯。Okay， so， so let's， let's kind of take a look back into what we've done so far in this course and sort of see what you know what we were doing in natural language processing。

 What was our strategy， If you had a natural language processing problem。

 and you wanted to say take like your best effort attempt at it without doing anything too fancy。

 you would have said， okay， I'm going have a bidirectional LSTM。

 instead of a simple R I'm gonna to use an LSTM to encode my sentences， I get bidirectional context。

 And if I have an output that I'm trying to generate。

 I'll have like a undirectional LSTM know I was gonna generate one by one。

 So you have a translation or a parse or whatever。 And so maybe I've encoded in a bidirectional LTM。

 the source sentence and I'm sort of you， one by one decoding out the target with my undirectional LTM And then also I was gonna use something like attention to give flexible access to memory if I you know felt like I needed to do。

😊，To sort of look back and see where I want to translate from okay and this was just working exceptionally well and we motivated so attention through wanting to do machine translation and you have this bottleneck where you don't want to have to encode the whole source sentence in a single vector。

Okay， and in this lecture， we have the same goal。 So we're gonna be looking at a lot of the same problems that we did previously。

 but we're gonna use different building blocks。 We're going to say， you know。

 if if 2014 to 2017 I was using recurrence through lots of trial and error years later it was we had these like brand new building blocks that we could plug in sort of。

 you know， direct replacement for LTMs and they're gonna allow for just a huge range of much more successful applications。

 And。😊，And so what what are the issues with the recurrent neural networks we used to use and what are the new systems that we're going to use sort of from this point moving forward。

Okay， so， so one of the issues with， with the recurrent neural network is what we're going to call linear interaction distance。

 So as we know， you know。Adens are unrolled left to right or right to left。

 depending on the language and the direction。 Okay。

 but it encodes the sort of notion of linear locality。

 which is useful because if two words occur right next to each other。

 sometimes they're actually quite related。 So tasty pizza。 They're nearby。

 And in the recurrent neural network right， you sort of encode you know， tasty。

 And then you sort of walk one step and you encode pizza。

So nearby words do often affect each other's meanings。 But， you know， you have this。

 this problem where very long distance dependencies can take a very long time to interact。

 So if I have this sentence， the chef。So those are nearby， those interact with each other。

And then who and then a bunch of stuff like the chef who went to the stores and picked up the ingredients and。

 you know， loves garlic and then was right， Like， I actually have an R and N step， right。

 the sort of application of the recurrent weight matrix and some element wise No nonlinearities once。

 twice， three times right， sort of as many times as there is potentially the the length of the sequence between chef and was。

 right， And it's the chef who was。 So this is a long distance dependency should feel kind of。

 you know， related to the stuff that we did in dependency syntax。 But， you know。

 it's quite difficult。😊，To learn potentially that these words should be related。

 So if you have sort of a lot of steps between。Between words。嗯。😊，It， you know。

 it can be difficult to learn the dependencies between them。 You know。

 we talked about all these gradient problems。 L TMs do a lot better at modeling the gradients across long distances than simple recurrent neural networks。

 but it's not perfect。And we already know sort of that this linear linear order isn't sort of the right way to think about。

 about sentences。 So if I wanted to learn that it's the chef who。Was then， you know。

 I might have a hard time doing it because the gradients have to propagate from was to chef。 And。

 you know， really， I'd like more direct connection between words that might be related in the sentence or in a document。

 even， right， if these are going to get much longer。

So so this is this linear interaction distance problem。

 we would like words that might be related to be able to interact with each other in the neural networks computation sort of graph more easily than sort of being linearly far away。

 yeah， so that we can learn these long- distance dependencies better。And there's a related problem。

 too that again， comes back to the recurrent neural network's dependence on the index。

 on the index into the sequence， often call it a dependence on time。

 So in a recurrent neural network， the forward and backward passes have O of sequence length many。

 So that means just roughly sequence in this case， just sequence length。

 many unparalleizable operations。 So you know， we know GPUus are great they can do a lot of operations at once as long as there's no dependency between the operations in terms of time that you have to compute one and then compute the other。

 right， But in in a recurrent neural network， you can't actually compute the RN hidden state for time step 5 before you compute the RN hidden state for time step 4 or time step 3 right And so you get this graph that looks very similar where if I want to compute this hidden state。

 So I've got some word I have zero operations I need to do before I can compute this state。

 I have one operation I can do before I can compute this state。And as my sequence length grows。

 right， I've got， okay here。 I've got three operations I need to do before I can compute this state with the number3 because I need to compute this and this and that。

 So there's sort of three unparallelyzable operations。 and I'm sort of glamming， you know。

 all the matrix multiplies and stuff into a single one。 So， so 1，2，3， And， of course。

 this grows with the sequence length as well。 So， down over here。 So as the sequence length grows。

 I can't parallellyze， you know， I can't just have a big GPU just know Kachana with with the matrix multiply to compute this state because I need to compute all the previous states beforehand。

😊，Okay， any questions about that。 So those are these are these two sort of related problems。

 both with the depends on time。 Yeah， Yeah， so have a question on the linear interaction issues。

 I thought that was whole point of the extension network and then how。我没票。

You want during the training of the actual selve and that depend on each other。

 can't we do something like the attention？呃，我再问一下。So the question is。

 with the linear interaction distance， wasn't this sort of the point of attention that sort of gets around that。

 Can't we use something with attention to sort of help or if that just help。

 So it won't solve the parallelzability problem。 And in fact。

 everything we do in the rest of this lecture will be attention based。

 But we'll get rid of the recurrence and just do attention more or less。 So will， yeah。

 it's a great intuition。Any other questions？Yeah。Okay cool。So。So if not recurrence。

 what about attention。 you just a slide slide back。 And so， you know。

 just we're gonna get deep into attention today。 But just for the second attention treats each word's representation as a query to access and incorporate information from a set of values。

 So previously， we were in a decoder， We were decoding out a translation of a sentence。

 and we attended to the encoder so that we didn't have to store the entire representation of the source sentence into a single vector。

 And here today we'll think about attention within a single sentence。

 So I've got this sort of sentence written out here with know word one through word T in this case and on these sort of integers in the boxes Im writing out the number of unparalleizable operations that you need to do before you can can compute these。

 So for each word， you can independently compute its embedding without doing anything else previously。

 right because the embedding just depends on the word identity。😊，And then with attention。

 if I wanted to build an attention representation of this word by looking at all the other words in the sequence。

 that's sort of one big operation。 and I can do them in parallel for all the words。

 So the attention for this word， I can do the attention for this word。

 I don't need to sort of walk left to right like I did for an R N。 again。

 will get much deeper into this。 But this you should have the intuition that it solves the linear interaction problem and the nonparallyzability problem。

 because now， no matter how far away words are from each other， I am potentially interacting。

 I might just attend to you， even if you're very， very far away。

 sort of independent of how far away you are， and I also don't need to sort of walk along the sequence linearly long。

 So I'm treating the whole sequence at once。Alright， so， so， you know。

 the intuition is that attention allows you to look very far away at once。

 and it doesn't have this dependence on the sequence index that keeps us from paralleling operations。

 And so now the rest of the lecture will talk in great depth about attention。

 So maybe let's just move on， okay。So let's think more deeply about attention。 You know。

 one thing that you might think of with attention is that it's sort of performing kind of a fuzzy lookup in a key value store。

 So you have a bunch of keys， a bunch of values and is gonna help you sort of access that。

 So in in an actual lookup table， just like a dictionary in Python， for example， right， Very simple。

 you have a table of keys that each key maps to a value。

 And then you like give it a query and the query matches you know， one of the keys。

 and then you return the value， right， So I've got a bunch of keys here。😊。

And my query matches the key。 So I return the value， simple。Fair， easy， okay， good。And in attention。

 right， So just like we saw before， the query matcheses all keys softly。 There's no exact match。

 You sort of compute some sort of similarity between the key and all of the sorry the query and all of the keys。

 and then you sort of weight the results。 So you've got a query again。 You've got a bunch of keys。

The query to different extents is similar to each of the keys。

And you will sort of measure that similarity between0 and 1 through a softmax。

And then you get the values out， you average them via the weights of the similarity between the key and the query and the keys。

You do a weighted sum with those weights and you get an output， right。

 So it really is quite a bit like a lookup table。 but in this sort of soft vector space， you know。

 mushy sort of sense。 So I'm really doing some kind of accessing into this information that's stored in the key value store。

 but I'm sort of softly looking at all of the results。😊，Okay， any questions there。Gong。So。

 so what might this look like， right？ So if I was trying to represent this sentence。

 I went to Stanford's C 224 N and learned。 So I'm trying to build a representation of learned。

You know， I have a key for each words。 This is this selfattention thing that well we'll get into。

 I have a key for each word， a value for each word。 I've got the query for learned。

 And I've got these sort of these sort of teaellish bars up top。

 which sort of might say how much you're going to try to access each of the word like， so。

 maybe 224 n is not that important C S， maybe that determines what I learned， you know， Stanford。

 right， and then learned， maybe that's important to representing itself。

 So you sort of look across the whole sentence and build up the sort of soft accessing of information across the sentence in order to represent learned in context。

😊，Okay， so this is just a toy， a toy diagram。So let's get into the math。

 So we're going to look at a sequence of words。 So that's W1 to N。 sequence of words in a vocabulary。

 So this is like， you know， Zuko made his uncle T。 That's， that's a good sequence。 And for each word。

 we're going to embed it with this embedding matrix， just like we've been doing in this class， right。

 So I have this embedding matrix that goes from the vocabulary size to the dimensionality D。😊。

So that's each word has a noncontextual right， only dependent on itself word embedding。

 And now I'm going to transform each word with one of three different weight matrices。

 So this is often called key query value selfatten。 right， So I have a matrix Q。

 which is an R D to D。 So this maps X to which is a vector of dimensionality D to another vector of dimensionality D。

 And so that's going to be a query vector。 right， So it takes an X and it sort of you know rotates it shuffles it around。

 stretches it， squishes it。😊，Makes it different。 now it's a query。

 And now for a different learnable parameter， K， So that's another matrix。

 I'm going come up with my keys。And with a different learnable parameter V。

 I'm going to come up with my values。 right， So I'm taking each of the noncontextual word embeddings。

 each of these Xs， and I'm transforming each of them to come up with my query for that word。

 my key for that word， and my value for that word。Okay， so every word is doing each of these roles。

Next， I'm going to compute all pairs of similarities between the keys and queries， right。

 So in the toy example we saw， I was computing sort of the similarity between a single query for the word learned and all of the keys for the entire sentence。

In this context， I'm computing all pairs of similarities between all keys and all values。

 because I want to represent sort of all of these sums。 So I've got。This sort of dot product。

 I'm just gonna take the dot product between these two vectors。 right， So I've got Q I。

 So this is saying the query for word I dotted with the key for word J， And I get this score。

 which is， you know， a real value mightight be very large negative， might be 0。

 mightight be very large and positive。 And so that's like。

 how much should I look at J in this lookup table。And then I do the softmax， right， So I softmax。

 So I say that， you know， the actual weight that I'm going to look at J from I is softmax of this over all of the possible indices。

 right， So it's like the the affinity between I and J normalized by the affinity between I and all of the possible J prime in the sequence。

😊，And then my output is just the weighted sum of values， so I've got this output for word I。

 so maybe I is like one for zuco， and I'm representing it as the sum of these weights for all J。

 so zuko and ma and his and uncle and T， and the value vector for that word J。

 I'm looking from I to J as much as alpha Ij。What's the dimension of WI？Oh， W Y。

 you can either think of it as a symbol in vocab V。 So that's like。

 you can think of it as a one hot vector in。Yeah， in this case， we are， I guess thinking of this。

 So one hot vector in dimensionality size of vocab。 So in the matrix E。

 you see that it's R D by bars around V。 That's size of the vocabulary。

 So when I do E multiplied by W I， that's taking E， which is D by V， multiplying it by W。

 which is V and returning a vector that's dimensionality D。 So W that first line like W1 n。

 that's a matrix where it has like maybe like a column for every word in that sentence in each column is a length V。

😊，Yeah， usually， I guess we think of it as having a， I mean， if I'm putting the。

 the sequence length index first， you might think of it having a row for each word。 but。

 but similarly， yeah， it's， it's n， which is the sequence length。

 And then the second dimension would be V， which is the vocabulary size。

 And then that gets mapped to this thing， which is sequence length by D。

Why do we learn two different matrices， Q and K when Q transse QI transpose Kj is really just one matrix in the middle。

That's a great question。 It ends up being because this will end up being a low rank approximation to that matrix。

 So it is for computational efficiency reasons， although it also， think feels kind of nice in the。

 in the presentation。 But yeah， what will end up doing is having a very low rank approximation to Q K transpose。

 And so it it， you actually do do it like this。 It's a good question。😊，I I， so the cur would。

AnyAny specific。So I could repeat that for me so the query of the wordted with the key itself。

 does it look like an identity or it？particular it's a good question。 Okay。

 let me remember to repeat questions。 So does E I I， right， for， for J equal to I。

 So looking at itself look like anything in particular， Does it look like the identity。

 Is that the question， okay， so。So right， it it's unclear， actually。

 this question of should you look at yourself for representing yourself， Well。

 it's gonna to be encoded by the matrices Q and K， right， If I didn't have Q and K in there。

 if those were the identity matrices。 if Q' is identity K's identity。

 then this would be sort of do credit with yourself， which is gonna be high on average。

 like you're pointing in the same direction as yourself。 But it could be that， you know。

 Q X and K X I might be sort of arbitrarily different from each other because Q could be the identity and K could map you to the negative of yourself。

 for example， so that you don't look at yourself。 So this is all learned in practice。

 So you end up it can sort of decide by learning whether you should be looking at yourself or not。

 and that's some of the flexibility that parameterizing it as Q and K gives you that wouldn't be there if I just used X's everywhere in in this equation。

I'm going try to move on。 I'm afraid because there's a lot to get on。

 but we'll keep talking about self- attention。 And so as more questions come up。

 I can also potentially return back。Okay， so， so this is our basic building block。

 But there are a bunch of barriers to using it as a replacement for for LSTMs。

 And so what we're going to do for this portion of the lecture is talk about the minimal components that we need in order to use self attentionten as sort of this like very fundamental building block。

 So we can't use it as it stands as I've presented it。

 but because there are a couple of things that we need to sort of solve or fix。

 One of them is that there's no notion of sequence order in self attentionten。 So， so， you know。

What is what does this mean if I have a sentence like when I move over here to the whiteboard briefly and hopefully I'll write quite large。

But I have a sentence like Zuko。Made。His。Uncle。And。Let's say。His uncle。Made。Zuco。

If I were to embed each of these words， right， using its embedding matrix。

 The embedding matrix isn't dependent on。The index of the words。 So this is the word index 1，2，3。

4 versus now his is over here。 an uncle， right。 And so when I compute the self attentionten。

 And there's a lot more on this in the lecture notes that goes through a full example。

 The actual self-attention operation will give you exactly the same representations for this sequence。

 Zuko made his uncle as for this sequence， His uncle made zo。

 And that's bad because there are sentences that mean different things。

 And so right it's sort of this， this idea that self-atten is an operation on sets。

 like you have a set of vectors that you're going to perform self- attentionten on and nowhere does like the exact position of the words come into play directly。

So we're going to encode the position of words through the keys。

 queries and values that we have so you know consider now representing each sequence index right our sequences are going from one to n as a vector so don't worry so far about you know how it's being made。

 but you can imagine representing sort of the number one like the position one， the position two。

 the position3。As a vector in the dimensionality D， just like we're representing our keys。

 queries and values。And so these are position vectors。 You know， you can， if， if you were to。

Want to incorporate the information represented by these positions into our selfattention。

 you could just add these vectors， these P vectors to the inputs right so if I have you know this X embedding of a word which is the word at position I but really just represents。

 oh， the word zuco is here now I can say that oh， it's the word zuco and it's at position 5 because you know this vector represents position5。

Okay， so， so how do we do this， And we might only have to do this once。

 so we can do it once at the very input to the to the network。 And then that sort of is sufficient。

 We don't have to do it at every layer because it sort of noses from the input。

 So so one way in which people have done this is look at these sinusoidal position representations。

 So this looks a little bit like this where you have。 So these are this is a vector P。

 which is in dimensionality D right And each one of the dimensions， you take the value I。

 you modify it by some constant and you。You pass it to the sine or cosine function and you get these sort of values that vary according to the period。

 differing periods， depending on the dimensionality D。

 So I've got this sort of a representation of a matrix where D is the vertical dimension。

 And then N is the horizontal。 and you can see that there's sort of like， oh， you know。

 as I walk along， you see the period of the sine function going up and down and each of thes D has a different period。

 And so together you can represent a bunch of different sort of position indices。 And you know。

 it gives this intuition that oh， maybe period maybe sort of the absolute position of a word isn't as important。

 you've got this sort of period， theity of the sines and cosines。

 and maybe that allows you to extrapolate to longer sequences。 But in practice， that doesn't work。

 but this is sort of like an early notion that this still sometimes used for how to represent position in transformers。

And self attention networks in general。 So， so that's one idea。

 You might think it's a little bit complicated。A little bit unintuitive。

 here's something that feels a little bit more deep learning。So we're just going to say， oh。

 you know， I'm going to maximum sequence length of n。 And I'm just gonna learn a matrix。

 That's dimensionality D by N。 And that's gonna represent my positions。

 I'm gonna learn it as a parameter。 just like I learn every other parameter。 And what do they mean。

 Oh， I have no idea， But it know， represents position So。😊，Right。

 and so you just sort of add this matrix to the Xs， your input embeddings。And it learns to。

 you know fit to data。 So whatever representation of position that's linear， sort of， you know。

 index base that you want， you can learn。 And the cons are that， well。

 you definitely now can't represent anything that's longer than N words long。

 No sequence longer than N。 you can handle because， well。

 you only learn a matrix of this many positions。 And so in practice， you'll get， you know。

 a model error。 if you， if you pass a self attentiontention model， something longer than length N。

 it will just sort of crash and say， I can't， I can't do this。

And so this is sort of what most systems nowadays use there are more flexible representations of position。

 including a couple in the lecture notes you might want to look at sort of like the relative linear position or words before or after each other but not their absolute position is also some sort of representations that harkken back to our dependency syntax because like oh maybe words that are close in the dependency parse tree should be the things that are sort of close in the self-attention operation okay questions。

😊，In practice， do we typically just make N large enough that we don't run into the issue of Bush？

Having something that could be input longer than it。So the question is， in practice。

 do we just make n long enough that we don't run into the problem where we're going to you know look at a text longer than N。

 No， in practice， it's actually quite a problem。 even today。

 even in the largest biggest language models and you know know。

 can I fit this prompt into chat G or whatever。 iss a thing that you might see on Twitter。 I mean。

 these continue to be issues。 And part of it is because the selfattention operation。

 and we'll get into this later in the lecture， it' it's quadratic complexity in the sequence length。

 So you're going to you're gonna to spend n squared sort of memory budget in order to make sequence length longer。

 So in practice， you know， this might be on a large model， say 4000 or so and is 4000。

 you can fit 4000 words， which feels like a lot， but it's not gonna fit a novel It's not gonna fit a Wikipedia page。

 you know， and so and there are models that do longer sequences for sure。 and again。

 we'll talk a bit about it。 But no this actually is an issue。

How P how do you know that the P that you've learned。

 this matrix that you've learned is representing position as opposed to anything else。

 and the reason is the only thing that correlates this position。Right。

 so like when I see these vectors， I'm adding this P matrix to my X matrix， the word embeddings。

I'm adding them together。 And the words that show at each index will vary depending on what word actually showed up there in the example。

 But the P matrix never differs。 It's always exactly the same at every index。

 And so it's the only thing in the data that it correlates with。

 So you're sort of learning it implicitly。 like this vector at index 1 is always at index 1 for every example for every gradient update and nothing else。

Coocs like that。Yeah， so what you end up learning， I'm， I don't know。 It's unclear。

 but it definitely allows you to know， oh， this word is with this index of this， yeah。O。

Just quickly Wednesdayick， but that in space。Is the sequence right now defined as assistance。

 so sequences of roomss or。Figure out what the unit is using it。Okay。

 so the question is when this is quadratic in this sequence。 Is that a sequence of words。 Yeah。

 think of it as a sequence of words。 Sometimes there'll be pieces that are smaller than words。

 which will go into in next in the next lecture。 But yeah， think of this as a sequence of words。

 but not necessarily just for a sentence， maybe for an entire paragraph or an entire document or something like that。

Okay， got the attention please worth。Yeah， the tension is based words to words。Okay， cool。

 I'm gonna move on。Okay， so， right， so we have another problem。 Another is that， you know。

 based on the presentation of self attention that we've done， you know。

 there's really no nonlinearities for sort of deep learning magic。

 We're just sort of computing weighted averages of stuff。😊，So， so， you know。

 if I apply selfattention and then apply self-attention again and again and again and again。

 you get you should look at the lecture notes if you're interested in this it's actually quite cool。

 But what you end up doing is you're just reveraging value vectors together。

 So you're like computing averages of value vectors。 And it ends up looking like one big selfatten。

 But there's an easy fix to this if you want sort of the traditional deep learning magic。

 and you can just add a feed forward network to postpro each output vector。

 So I've got a word here that's sort of the output of selfatten。

 And I'm going to pass it through in this case， I'm calling it a multilayer perceptron MP。

 So this is a vector and R that's going to be and it's taking in as input a vector and RD。

 And you do the usual sort of multilayer perceptron thing where you have the output and you multiply by matrix。

 pass it through a nonlinearity multiply it by another matrix。

 and so what this looks like in selfatten。 is that I've got this sort of sentence， the chef who food。

 And I've got my。😊，ddings for it。 I pass through this whole big self-atten block which looks at the whole sequence and sort of incorporates context and all that。

 And then I pass each one individually through a feed forward layer。

 right So so this embedding that's sort of the output of the self-at for the word is passed independently through a multilayer perceptron here And that's sort of you can think of it as sort of combining you know together or processing the result of attention。

 So so a number of reasons why we do this。 one of them also is that you can actually stack a ton of computation into these feed forward networks very。

 very efficiently， very parallelizable， very good for GPUus。 But this is what's done in practice。

 So you do self-at。 and then you can you pass it through this sort of positionwise feed forward layer every word is processed independently by this feed forward network to process the result。

😊，Okay， so that's adding our sort of classical， deep learning nonlinearities for self attention。

 And that's an easy fix for this sort of no nonlinearities problem in self attentionten。

 And then we have a last issue before we have our final minimal self attention building block with which we can replace R andNs。

And that's that， well， you know， when I've been writing out all of these examples of self- attentionten。

 you can sort of look at the entire sequence right， and， and in practice， for some tasks。

 such as machine translation or language modeling。 whenever you want to define a probability distribution over a sequence。

 you can't cheat and look at the future。Right， so， you know， at every time step。

 I could define the set of keys and queries and values to only include past words。

 but this is inefficient。 bear with me。 It's inefficient because you can't parallelze it so well。

 So instead， we compute the entire N by N matrix， just like I showed in the slide discussing selfatten。

 And then I mask out words in the future。 So this score， EI J。

 and I computed EI J for all N by N pairs of words。 it's equal to whatever it was before。

If the word that you're looking at at index J is an index that is less than or equal to where you are index I。

 and it's equal to negative infinity ish otherwise， if it's in the future。

 and when you soft match the EIJ， negative infinity gets mapped to0。

So now my attention is weighted 0。 My my weighted average is 0 on the future。 So I can't look at it。

What does this look like， So in order to encode these words， the chef。

 who and maybe the start start symbol there。I can look at these words。 right。

 That's all pairs of words。 And then I just gray out。

 I I sort of negative infinity out the words I can't look at。 So whencoding the start symbol。

 I can just look at the start symbol。 when encoding the。

 I can look at the start symbol and the whencoding chef， I can look at start the chef， but I。

 you know， can't look at who。😊，Right， and so it， with this representation of chef that encode code。

 that is， you know， only looking at start the chef。

I can define a probability distribution using this vector that allows me to predict who without having cheated by already looking ahead and seeing that。

 well， who is the next word。Questions。So it says we're using it in decoders。

Do we do this for both the encoding layer and the Eding layer or for the encoding layer how are we allowing ourselves to look for？

The question is， it says here that we're using this in a decoder。

 Do we also use it in the encodeder So that this is the distinction between sort of like a bidirectional LSTM and a unitdirectional LSTM。

 right， So wherever you don't need this constraint。You probably don't use it。

 So if you're using an encoder right on the source sentence of your machine translation problem。

 you probably don't do this masking because it's probably good to let everything look at each other。

 And then whenever you do need to use it， because you have this auto aggressivegress sort of probability of word one。

 probability of two given one， you know， three given two and one， then you would use this。

 So traditionally， yes， in decoders， you will use it in encoders， you will not。Yes。

My question is a lot bit philosophical how humans actually generate sentences by having some notion of the probability of future words before they say。

啊。The words that or before they choose the words that they are。Friendly。Spea or question。

 So the question is， isn't， you know， looking ahead a little bit and sort of predicting or getting an idea of the words that you might say in the future。

 sort of how humans generate language instead of the sort of strict constraint of not seeing into the future。

 Is that， iss that what you're okay， So， so right， you know。

 trying to plan ahead to see what I should do is definitely an interesting idea。

 But when I am training the network right， I can't。If I'm。

 I'm teaching it to try to predict the next word。 and if I give it the answer。

 it's not going to learn anything useful。So in practice， when I'm generating text。

 maybe it would be a good idea to make some guesses far into the future or have a high-leve plan or something。

 but in training the network， I can't encode that intuition about how humans build like generate sequences of language by just giving it the answer of the future directly at least because then it's just too easy like there's nothing to learn。

 but there might be interesting ideas about maybe giving the network like a hint as to what kind of thing could come next。

 for example， but that's out of scope for this。Yeah， question up here。

 So I understand the like why we want to mask the feature for stuff like language models。

 but how does it apply to machine translation like would Yeah， so in machine translation。

 we're going to come over to this board and hopefully get a better marker。Nice。

 in machine translation， you know， I have a sentence like I。Like。Pizza。And I want to be able to。

 you know， translate it。Jim。啊，我彼吃。Nice， right， And so when I'm， when I'm looking at the I like pizza。

 right， I get this as the input。 And so I want self attention。😊，嗯。Without masking。

Because I want I to look at like and I to look at pizza and like to look at pizza。 And I want it all。

 And then when I'm generating this， right， if my tokens are like J M la pizza。

 I want to in encoding this word。 I want to be able to look only at myself。

 and will'll talk about encoder decoder architectures in this later in the lecture。

 But I want to be able to look at myself， none of the future and all of this。

 And so what I'm talking about right now in this mask in case is masking out， you know。😊。

With like negative infinity， all of these words。 So that sort of attention score from Z to everything else should be net to be。

 you know， negative infinity。 Yeah， does that answer your question， great。Okay， let's move ahead。

 okay。So， so that was our last big sort of building block issue， a selfatten。

 So this is what I would call。 And this is my personal opinion， a minimal， you know。

 self-atten building block。 You have selfatten， the basis of the method。

 So that's sort of here and the red。 And maybe we had， you know， the inputs to the sequence here。

 And then you embed it with that embedding matrix E。 And then you add position embeddings right。

 then these three arrows represent using， you know， the the key。

 the value and the query that's sort of stylized there。 This is often how you see these diagrams。

 right， And so you you pass it to self attentionten。With the position representation， right。

 So that specifies the sequence order because otherwise you'd have no idea what order the words showed up in。

You have the nonlinearities in sort of the Tl feed forward network there to sort of provide that sort of squashing and sort of deep learning expressivity。

 and then you have masking in order to have parallelizable operations that don't look at the future。

Okay， so this is sort of our minimal architecture。 And then up at the top above here， right。

 So you have this thing。 Maybe you repeat this sort of selfat and feed forward many times。

 So self attention， feed forward， self attention， feed forward， self attention， feed forward， right。

 Let's calling this block。And then maybe at the end of it， you， you know， predict something。

 I don't know。 We haven't really talked about that， but， you know， you have these representations。

 and then you predict the next word or you predict the sentiment or you predict whatever。

 So this is like a self attention architecture。Okay， we're gonna move on to the transformer next。

 So if there are any questions。 Yeah， all the way around。

 We will use masking for decoders where I want to decocode out the sequence。

Where I have an informational constraint where to represent this word properly。

 I cannot have the information of the future。Okay。Great。😊，So now let's talk about the transformers。

 So what I've pitched to you is what I call a minimal self attention architecture。And you know。

 I quite， I quite like pitching it that way。 but really no one uses the architecture that was just up on the slide。

 the previous slide it doesn't work quite as well as it could。

 And there's a bunch of sort of important details that we'll talk about now that goes into the transformer what I would hope though。

 to sort of how you take away from that， is that the transformer architecture。

 as I'll present it now， is not necessarily the endpoint of our search for better and better ways of representing language。

 even though it's now ubiquitous and has been for a couple of years。 So。

 so think about these sort of ideas of the problems of using self-atten。

 and maybe ways of fixing some of the issues with transformers。😊，Okay。

 so a transformer decoder is how we'll build systems like language models， right。

 And so we've discussed this。 It's like our decoder with our self attentionten only sort of minimal architecture。

 It's got a couple of extra components， some of which I've gradeed out here that will go over one by one。

 The first that's actually different。Is that we'll replace our self attention with masking。

 with masked multi head self attention。 This ends up being crucial。

 It's probably the most important distinction between the transformer and this sort of minimal architecture that I presented。

So let's come back to our toy example of attention where we've been trying to represent the word learned in the context of the sequence I went to Stanford C S 224 N and learned。

 And I was sort of giving these teal bars to say， oh， maybe intuitively。

 you look at various things to build up your representation of learned。 But， you know， really。

 there are varying ways in which I want to look back at the sequence to see varying sort of aspects of information that I want to incorporate into my representation。

 So maybe in this way， I sort of want to look at Stanford C S 2，24 N。Because like， oh。

 it's like entities like it， you， you learn different stuff at Stanford， T S 2。

24 N than you do at other courses or other universities or whatever， right。

 And so maybe I want to look here for this reason。And maybe， you know， there's in another sense。

 I actually want to look at the word learned。 and I want to look at I， you know， I went and learned。

 right as these sort of like maybe syntactically relevant words， right。

 Like it's very different reasons for which I might want to look at different things in the sequence。

😊，And so trying to sort of average it all out with a single operation of self attention ends up being maybe somewhat too difficult in a way that will make precise in assignment 5。

 we'll do a little bit more math。 Okay， so any questions about this in this intuition。Yeah。

 so it should be an application of attention just as I've presented it。 right。

 So one independent define the keys， define the queries， to the values。

 I'll define it more precisely here。 But think of it as I do attention once。And then I do it again。

 with different， like being different parameters， being able to look at different things， etc ceter。

 So like two separate something。How do we ensure the thing？We do not okay。

 so the question is if we have two separate sets of weights trying to learn。

 say to do this and to do that， how do we ensure that they learn different things。

 we do not ensure that they learn different things and in practice they do。

 although not perfectly so it ends up being the case that you have some redundancy and you can sort of like cut out some of these but sort of out of scope for this。

 but we sort of hope just like we hope that different sort of dimensions in our feed forward layers will learn different things because of lack of symmetry and whatever that we hope that the heads will start to specialize and that will mean they'll specialize even more and yeah。

Okay。Alright， so in order to discuss multihead selfatten well。

 we really need to talk about the matrices， how we're going implement this in GPs efficiently。

 We're going to talk about the sequence stacked form of attention。

 So we've been talking about each word sort of individually as a vector in dimensionality D。

 But you know， really， we're going to be working on these as big matrices that are stacked。

 So I take， you know all of my word embeddings x1 to X n。

 And I stack them together and now have a big matrix that is in dimensionality R and by D。😊，Okay。

 and now with my matrices， K， Q and V， I can just multiply them sort of on this side of x。

 So x is R n by D。 K is R D by D。 So n by D times D by D gives you N by D again。

 so I can just compute a big， you know matrix multiply on my whole sequence to multiply each one of the words with my key query and value matrices very efficiently。

 right So this is sort of this vectorization idea。 I don't want to for loop over the sequence。

 I represent the sequence as a big matrix。And I just do one big matrix， multiply。

Then the output is defined as this sort of inscrutable bit of math。

 which I'm going to go over visually。So first， we're going to take the key query dot products in one matrix so we've got。

😊，We've got xq， which is R N by D。And I've got Xk transpose， which is our D by N。 So N by D D by N。

 this is computing all of the EIJs， these scores for selfattention， right。

 so this is all pairs of attention scores computed in one big matrix multiply。Okay。

 so this is this big matrix here。 Next， I use the softm， right。

 So I softm this over the second dimension， the second n dimension。

 And I get my sort of normalized scores。 And then I multiply with X V。

 So this is an N by N matrix multiplied by an N by D matrix。😊，And what do I get， Well。

 this is just doing the weighted average， right， So this is one big weighted average contribution on the whole matrix。

 giving me my whole self attentionten output in R and by D， right。

 So I've just restated identically the self-atten operations but computed in terms of matrices so that you could do this efficiently on a GPU。

😊，Okay， so multihyed attention。This is going to give us。

 And it's going to be important to compute this in terms of the matrices， which we'll see。

 This is going to give us the ability to look in multiple places at once for different reasons。

 So sort of， you know， for self attentionten looks where this dot product here is high。Right。

 this X I， the Q matrix， the key matrix。 but maybe we want to look in different places for different reasons。

 So we actually define multiple key query key and value matrices。

 So I'm going to have a bunch of heads。 I'm going have H selfatten heads。 And for H head。

 I'm going to define an independent query key and value matrix。

 And I'm going to say that it's its shape is going to map from the model dimensionality to the model dimensionality over H。

 So each one of these is doing projection down to a lower dimensional space。

 This is going be for computational efficiency。 And。😊。

I'll just apply self attention sort of independently for each output。

 So this equation here is identical to the one we saw for single headed self attention。

 except we've got these sort of L indices everywhere。So I've got this lower dimensional thing。

 I'm mapping to a lower dimensional space。 and then I do have my lower dimensional value vector there。

 So my output is an R D by H。 but really， you're doing exactly the same kind of operation。

 I'm just doing it H different times。 And then you combine the outputs。

 So I've done sort of look in different places with the different key query and value matrices。

 And then I get each of their outputs。😊，And then I concatenate them together。

 So each one is dimensionality D by H。And I can catnate them together and then sort of mix them together with the final linear transformation。

And so each head gets to look at different things and construct their value vectors differently。

 And then I sort of combine the result altogether at once。Okay。

 let's go through this visually because it's at least helpful for me。 So， right。

 it's actually not more costly to do this really than it is to compute a single head of self attention。

 And we'll see you through the pictures。So， you know， we were in single headed self attention。

 We computed X Q and in multi headed self attention， we also compute X Q the same way。

So xq is R and by D。And then we can reshape it into our N。

 that's sequence length times the number of heads times the model dimensionality over the number of heads。

 So I've just reshaped it to say now I've got you know a big three axis tensor。

 the first axis is the sequence length， the second ones the number of heads。

 the third is this reduced model dimensionality and that costs nothing and do the same thing for X and V and then I transpose so that I've got the head axis as the first axis and now I can compute all my other operations with the head axis kind of like a batch。

So what does this look like in practice， like instead of having one big X Q matrix that's model dimensionality D。

 I've got like in this case， three X Q matrices of model dimensionality D by3， D by3， D by 3。

 same thing with the key matrix here。So everything looks almost identical。

 It's just the reshaping of the tensors。 And now， right， at the output of this。

 I've got three sets of attention scores right， just by doing this reshape。😊，And the cost is that。

 well， you know， each of my attention heads has only a D by H vector to work with instead of a D dimensional vector to work with。

 right， So I get the output。 I get these three sets of pairs of scores。

I compute the softmax independently for each of the three。

 and then I have three value matrices there as well。 each of them lower dimensional。

 And then finally， right， I get my three different output vectors。

 and I have a final linear transformation to sort of。😊，Mush them together。 And I get an output。

And in summary， what this allows you to do is exactly what I gave in the toy example。

 which was I can have each of these heads look at different parts of a sequence for different reasons。

Just a questionSo this is at a given block right like all of these attention heads are for a given transformer block。

 a next block would also could also have three attention heads。The question is。

 are all of these for a given block and we'll talk about a block again。

 but this block was this sort of pair of self-attention and feed forward network。

 So you do like self-attention feed forward。 That's one block。

 another block is another self- attention， another feed forward。

 And the question is are the parameters shared between the blocks or not generally they are not shared。

 you'll have independent parameters at every block， although there are some exceptions。Ving on that。

 is it typically the case that you have the same number of like heads at each block。

 or do you carry the number of heads across blocks？You have this， you definitely could vary。

 People haven't found reason to vary。 So the question is。

 do you have different numbers of heads across the different blocks。

 or do you have the same number of heads across all blocks， You know。

 the simplest thing is to just have it be the same everywhere， which is what people have done。

 I haven't yet found a good reason to vary it， but。Could be interesting。

 It's definitely the case that， you know after training these networks。

 you can actually just totally zero out， remove some of the attention heads。

 and I'd be curious to know if you could remove more or less depending on the like layer index。

 which might then say， oh， we should just have fewer， but again。

 it's not actually more expensive to have a bunch So people tend to instead set the number of heads to be roughly so that you have like a reasonable number of dimensions per head given the total model dimensionality D that you want。

 so for example， I might want at least 64 dimensions per head which if D is you know 128 that tells me how many heads I'm going to have roughly So people tend to scale the number of heads up with the model dimensionality。

Yeah。X Q by stizing it in different columns。 You're reducing the rank of the final matrix， right。

 Yeah this， but that doesn't really have any effect from the results。 So the question is。

 by having you sort of reduced X Q and X， K matrices， right， This is a very low rank approximation。

 this little sliver in this little sliver defining this whole big matrix， It's very low rank。

 Is that not bad。In practice， no， I mean， again， it's sort of the reason why we limit the number of heads。

Depending on the model dimensionality， because you， you know， you want intuitively。

 at least some number of dimensions。 So you， 64 is sometimes done，128， something like that。 But。

 you know， if you're not giving each head too much to do and it's got sort of a simple job。

 You've got a lot of heads。 It ends up sort of being okay。 all we really know is that empirically。

 it's way better to have more heads than like one。Yes。

I'm wondering have there been studies to see if information in one of the sets of the attention scores like information that one of them learns is consistent like？

Related to each other or。the question is， have there been studies to see if there's sort of consistent information encoded by the attention heads。

 And， you know， yes， actually， there's been quite a lot of sort of study and interpretability and analysis of these models to try to figure out what roles。

 what sort of mechanistic roles each of these heads takes on。

 And there's quite a bit of exciting results there around some attention heads， you know。

 learning to pick out sort of the you know， it's like syntactic dependencies or maybe doing like sort of a global averaging of context。

 the question is quite nuanced， though， because in a deep network。 It's unclear。

 we should talk about this more offline， but it's unclear if you look at a word 10 layers deep in a network。

 what you're really looking at because it's already incorporated context from everyone else and it's a little bit unclear active area of research。

 But I think I should move on now to keep discussing transformers。 But yeah。

 if you to talk more about it， I'm happy to。😊，Okay， so。

 so another sort of hack that I'm going to toss in here。 I mean， maybe they wouldn't call it hack。

 But you know， it's， it's a nice little method to improve things。

 It's called scaled dot product attention。 So one of the issues with this sort of key query value。

 self attention is that when the model dimensionality becomes large。

 the dot products between vectors， even random vectors tend to become large。And when that happens。

 the inputs to the softmax function can be very large， making the gradients small。 So intuitively。

 if you have two random vectors in model dimensionality D and you just dot product them together as D grows。

 their dot product grows in expectation to be very large。 And so you know。

 you sort of want to start out with everyone's attention being very uniform， very flat。

 sort of look everywhere。 But as some dot products are very large， then you know。

 learning will be inhibited。 And so what you end up doing is you just sort of for each of your heads。

 you know， you just sort of divide all the scores by this constant that's determined by the model dimensionality。

 So as the vectors grow very large， their dot products don't。 at least at an initialization time。

 So this is sort of like a nice little。😊，You know， important， but， but maybe not。T like， yeah。

 it is it， it's important to know。And so that's called scale dot product attention from here on out。

 We'll just assume that we do this。 You know， it's quite easy to implement。

 You just do a little division in all of your computations。Okay， so。

 so now in the transformer decoder， we've got a couple of other things that I have un faded out here。

 We have two big optimization tricks or optimization methods， I should say， really。

 because these are quite important。 that end up being very important。

 we've got residual connections and layer normalization。

 And in transformer diagrams that you see sort of around the web they're often written together as this add and norm box。

 And in practice in a transformer decoder， I'm going to you know， apply mask multihead attention。

 and then do this sort of optimization add and norm。 and I'll do a feed forward application。

 and then add and norm。 So， you know， this is quite important。

 So let's go over these two individual components。😊，The first is residual connections。 I mean， we've。

 I think we've talked about residual connections before， right， it's worth doing it again。 But。

 you know， it's really a good trick to help models train better。 So just to recap， right。

 we're going to take instead of having this sort of you have a layer layer I -1。

 and you pass it through a thing。 maybe it's self attention。 Maybe it's a feed forward network。

 Now you've got layer I。😊，I am going to add the result of layer I to this sort of to its input here。

 So now I'm saying， I'm just going to computee the layer and I'm going to add in the input to the layer so that I only have to learn the residual from the previous layer right so I've got this sort of connection here it's often written as this this sort of like connection。

Okay， right， goes around。 And you should think that the gradient is just really great through the residual connection。

 right， like， you know， if I've got vanishing or exploding gradient vanishing gradients through this layer。

 well， I can at least learn everything behind it because I've got this residual connection where the。

 where the gradient is one because it's the identity。😊，This is really nice。 And， you know。

 it also maybe is like a buy， at least at initialization。

 everything looks a little bit like the identity function now， right。

 because if the in contribution of the layer is somewhat small because all of your weights are small。

 And I have the addition from the input， maybe the whole thing looks a little bit like the identity。

 which might be a good sort of place to start。😊，And， you know， there are really nice visualizations。

 I just love this visualization， right， So this is your like lost landscape， right。

 So you're gradient descent and you're trying to traverse the mountains of the lost landscape。

 This is like the parameter space and down is better in your lost function。 And it's really hard。

 So you get stuck in some local optima。 And you can't sort of find your way to， to get out。

 And then this with residual connections。 I mean， come on， you just sort of walk down。😊，I mean。

 it's not actually， I guess， really how it works all the time。 But I really love this。 It's great。😊。

Okay。So yeah， we've seen residual connections。 We should move on to layer normalization。

 So layer norm is another thing to help your model train faster。 And， you know， there's。😊。

The intuitions around layer normalization and sort of the empiricism of it working very well maybe aren't perfectly like。

 let's say， connected but。You know， you should imagine， I suppose， that we want to say， you know。

 this variation within each layer， things can get very big， things can get very small。

 That's not actually informative because of， you know。

 variations between maybe the gradients or I've got sort of weird things going on in my layers that I can't totally control。

 I haven't been able to sort of make everything behave sort of nicely where everything stays roughly the same norm。

 maybe something explode， maybe something things shrink。

And I want to cut down on sort of uninformative variation in between layers。

 So I'm going to let X and R D be an individual word vector in the model。

 So this is I add a single single index one vector。

 And what I'm going to try to do is just normalize it。

Normalize it in the sense of it's got a bunch of variation。 and I'm going to cut out on everything。

 I'm going to normalize it to unit mean and and standard deviation。

 So I'm going to estimate the mean。嗯。Here across so for all of the dimensions in the vector。

 So J equals one to the model dimensionality， I'm going to sum up the value。

 So I've got this one big word vector。 and I sum up all the values Division by D here。 right。

 That's the mean。 I'm gonna have my estimate of the standard deviation。 Again。

 these should say estimates。 This is my simple estimate of the standard deviation or the values within this one vector。

😊，And I'm just going to and then possibly， I guess I can have learned parameters to try to like scale back out in terms of multiplicatively and additively here。

 that's optional。 We're gonna compute this， this standardization。 right。

 I'm gonna to take my vector X subtract out the mean divideide by the standard deviation plus this epsilon sort of constant。

 if there's not a lot of variation。 I don't want things to explode。

 So I'm gonna have this epsilon there， that's close to0。 So this part here。

 x minus mu over square sigma plus epsilon is saying take all the variation and sort of normalize it to unit mean and standard deviation。

And then maybe I want to sort of scale it， stretch it back out and then maybe add an offset beta that I've learned。

 although in practice actually this part and discuss this in lecture notes and practice this part maybe isn't actually that important。

 but so layer normalization， yeah， you're sort of you know。

 you can think of this as when I get the output of layer normalization。

 it's going to be sort of look nice and look similar to the next layer independent of what's gone on because it's going to be unit mean and standard deviation So maybe that makes for a better thing to learn off of for the next layer。

Okay， any questions for residual or layer norm， yes？We need to subscribe this st vectors。Yeah。

 it's a good question。 When I subtract the scalar mu from the vector X。

 I broadcast mu to dimensionality D and remove mu from all D。 Yeah， good point。Thank you。

 that was unclear。In the fourth bowl maybe。Is it divided， should it be divided by D from me？

Sorry can you repeat that in the fourth bullet point when you're calculating the mean。

 is it divided by D or is it or maybe I'm just it is divided by D？These are。

 so this is the average deviation from the mean of all of the， yeah。Yes。

Have five words in the sentence by there norm。 Do you。我来被上。5111 one。So the question is。

 if I have five words in the sequence， do I normalize by sort of aggregating the statistics to estimate mu and sigma across all the five words。

 share their statistics or do it independently for each word。

 This is a great question which I think in all the papers that discuss transformers is under specified。

 you do not share across the five words， which is somewhat confusing to me but。

So each of the five words is done completely independently。

You could have shared across the five words and said that my estimate of the statistics are just based on all five。

 but you do not。I can't pretend I understand totally why。For example， group basketball。嗯。

I close from the same position。So similar question。 The question is。

 if you have a batch of sequences right so like just like we're doing batchbased training。

 do you for a single word now we don't share across the sequence index for sharing the statistics。

 but do you share across the batch And the answer is no， you also do not share across the batch。

 In fact， layer normalization was sort of invented as your replacement for batch normalization。

 which did just that。 And the issue with batch normalization is that now your forward pass sort of depends in a way that you don't like on examples that should be not related to your example。

 And so yeah， you don't share statistics across the batch。Okay， cool。Okay。

 so so now we have our full transformer decoder and we have our blocks。

 So in this sort of slightly grayed out thing here that says repeat for a number of encoder or sorry decoder blocks each block consists of I pass it through self-atten。

 and then my add and norm right So I've got this residual connection here that goes around add。

 we've got the layer normalization there。 and then a feed forward layer。

 and then another add and norm。 And so that sort of set of four operations， I apply you know。

 for some number of times， number of blocks。 So that whole thing is called a single block。

 And that's it。 that's the transformer decoder。😊，As it is。Cool。

 so that's a whole architecture right there。 We've solved things like needing to represent position。

 We've solved things like。Not being able to look into the future。

 We've solved a lot of different optimization problems。 You had a question， yes。Here is。あのリカルます。Yes。

 mass multi head attention， yeah。With the dot product scaling with the square root do over age as well。

So the question is， how do these models handle variable length inputs， Yeah， so。嗯。

If you have so the input to the like GPU forward pass is going to be a constant length。

 so you're going to maybe pad to a constant length and in order to not look at the future。

 the stuff that's sort of happening in the future you can mask out the pad tokens。

 just like the masking that we showed for not looking at the future in general。

 you can just say set all of the attention weights to zero or the scores negative infinity for all of the pad tokens。

Yeah， exactly。 So you can， you can set everything to this maximum length。 Now， in practice。

 So the question was， do you set this length that you have everything be， be that maximum length。

 I mean， you know， yes， often， although you can save computation by setting it to something smaller and everything。

 the math all still works out， you just have to code it properly so it can handle you set everything instead of the n。

 you set it all to 5。 if everything is shorter than like 5 and you save a lot of computation。

 All of the self attention operations just work。😊，Pig， so， yeah。How many you later。forward。

There's one hidden layer in the feed forward yeah。Okay， I should move on。

 got a couple more things in very much time。 Okay， but I'll be here after the class as well。

 So in the encoder。 So the transformer encoder is almost identical。 But again。

 we want bidirectional context。 And so we just don't do the masking， right。

 So I've got in my multi head attention here。 I've got no masking。 And so it's。

 it's that easy to make the model bi directional。 Okay。😊，So that's easy。

 So that's called the transformer encodeder。 It's almost identical but no masking。 And then finally。

 we've got the transformer encodeder decoder， which is actually how the transformer was originally presented in this paper attention is all you need。

 And this is when we want to have sort of a bidirectional network。 Here's the encodeder。

 It takes say my source sentence for machine translation It's multi-headed attention is not masked。

 and I have a decoder to de out my sentence。 Now but you'll see that this is slightly more complicated。

 I have my masked multihead selfat just like I had before in my decoder。

 but now I have an extra operation， which is called crossat where I am going to use my decoder vectors as my queries。

 But then I'll take the output of the encodeder as my keys and values。

 So now for every word in the decoder。 I'm looking at all the possible words in the output of all of the。

😊，Of the encoder， yes。The keys and the values， how do we get like a key in values separated from the output。

 could collapse those into the single output？So we well sorry。

 how will we get the keys and values out like how do we because when we have the output。

 didn't we collapse like the keys and values into like a single output so we we。Yeah。

 the question is， how do you get the keys and values and queries out of this sort of single collapsed output。

 Now， remember， the output for each word is just this weighted average of the value vectors for the。

 for the previous words， right， And then from that output for the next layer。

 we apply a new key query and value transformation to each of them for the next layer of self attention So it's not actually that you're to the output。

' not when you're Yeah， you apply the key matrix， the query matrix to the output of whatever came before it。

 Yeah， and so just in a little bit of math right， we have。😊，These vectors H1 throughHN。

 I'm going to call them that are the output of the encoder right。

 and then I've got vectors that are the output of the decoder。So I've got these Zs。

 I'm calling you output to the decoder， and then I simply define my keys and my values from the encoder vectors。

 these H's。right so I take the H's I apply a key matrix and a value matrix。

 and then I define the queries from my decoder。 So my queries here。

 So this is why two of the arrows come from the encodeder and one of the arrows comes from the decoder。

 I've got my z's here。 get my queries my keys and values from the encoder。Okay。So that is it。

 I've got a couple of minutes。 I want to discuss some of the sort of results of transformers。

 and I'm happy to answer more questions about transformers after class。 So， so， you know， really。

 the original results of transformers。 They had this big pitch for like， oh， look。

 you can do way more computation because of parallelization。

 they got great results in machine translation。 So you had。😊，Do do do。

You had transformers sort of doing quite well， although not like astoundingly better than existing machine translation systems。

And but they were significantly more efficient to train because you don't have this parallelization problem。

 you could compute on much more data much faster， and you could make use of faster GPUus much more。

 know after that， there were things like document generation where you had this sort of old standard of sequence to sequence models the LSTMs。

 and eventually everything became sort of transformers all the way down。

 transformformers also enabled this revolution into pre-training。

 which will go over in next year next class and sort of the efficiency。

 the parallelz ability allows you to compute on tons and tons of data and so after a certain point sort of on standard large benchmarks。

 everything became transformer based， this ability to make use of lots and lots of data。

 lots and lots of compute， just put transformers head and shoulders above LTMs let's say almost every sort of modern advancement in natural language processing。

There are many sort of drawbacks and variants to transformers。

 you know the clearest one that people have tried to work on quite a bit is this quadratic compute problem So this all pairs of interactions means that our sort of total computation for each block grows quadraically with a sequence length and in a student's question。

 we heard that you know well as the sequence length becomes long if I want to process you know a whole Wikipedia article a whole novel that becomes quite unfeasible and actually you know that's a step backwards in some sense because for recurrent neural networks。

 it only grew linearly with a sequence length know other things people have tried to work on are sort of better position representations because the absolute index of a word is not really you know the best way maybe to represent its position in a sequence。

And just to give you an intuition of quadratic sequence length。

 right remember that we had this big matrix multiply here that resulted in this matrix of n by N and computing this is like you know a big a big cost。

 it costs a lot of memory。 And so there's been work oh yeah。

 And so if you think of the model dimensionality is like 1000， although today it gets much larger。

 then for a short sequence of n is roughly 30。 maybe you know if you're computing n squared times d30 isn't so bad。

 But if you had something like you know50000， then n squared becomes huge and sort of totally in。

 So people have tried to sort of map things down to a lower dimensional space to get rid of the sort of quadratic computation。

 But in practice， I mean， as people have gone to things like G3 chat G。

 most of the computation doesn't show up in the self- attentionten。

 So people are wondering sort of is it even necessary to get rid of。😊。

Self attentiontention operations， quadratic constraint。 It's an open form of research。

 whether this is sort of necessary。 And then finally。

 there have been a ton of modifications for the transformer over the last， you know，5，4 is years。

 And it turns out that the original transformer plus maybe a couple of of modifications is pretty much the best thing there is still there have been a couple of things that end up being important。

 changing out the nonlinearities。And the feed For network ends up being important。 But it's sort of。

 it's had lasting power so far。 And so it's， it's， but I think it's。

 it's ripe for people to come through and think about how to sort of improve it in various ways。

 So pretraining is on Tuesday。 Good luck on assignment for。 And then yeah。

 we'll have the project proposal documents out tonight。 for you to talk about。😊。



![](img/ff239821ddd1fbac07988d7751909a2b_3.png)