# 斯坦福大学《计算机视觉的深度学习｜CS231n： Deep Learning for Computer Vision 2025》中英字幕 p08 -08-Lecture 8_ Attention and Transformers.zh_en -BV1FqazzVE6w_p8-

![](img/1fdc141c64e1dc4a50bf654efb636e7b_0.png)

Alright， welcomel back， everyone to Le 8。 today， we're going to talk about attention and transformers。

 And I think this， this is a really fun one。😊。

![](img/1fdc141c64e1dc4a50bf654efb636e7b_2.png)

So as a quick recap last time we were talking about recurrent neural networks and recurrent neural networks where this new kind of neural network architecture meant for processing sequences and in particular we saw how neural networks by processing sequences。

 let us attack a whole new different kinds of problems than we could with convolutional networks before。

 So in particular usually we have been thinking about these one to one problems where you input one thing like an image and then output one thing like a classification for what's in that image。

 but once you have the ability to move beyond images and move towards sequences of data。

 it let us tackle a lot of new kinds of problems like one to many problems， image captioning。

 maybe we want to input an image output a textual description of that image which is going to be a sequence of words maybe many to one where we do input a sequence of frames and output a classification for those frames and a bunch of other problems along this vein So now we're seeing that moving into these sophisticated neural network architectures both is sort of more interesting architectureurally but also lets us tackle new problems than we could with more traditional。

Forward neural networks。So today we're going to build on that and talk about two new things in today's lecture The first thing is going to be attention。

 which is going to be a brand new neural network primitive that fundamentally operates on sets of vectors。

 and then the second thing we're going to talk about is the transformer and the transformer is a different neural network architecture that has self-atten at its core and this and the spoil alert is that transformers are basically the architecture that we use for almost all problems in deep learning today。

 so any of the largest applications that you're seeing out there in the wild today。

 whether it's classifying images generating images generating text classifying text working with audio。

 basically any kind of large neural network today that is large state of the art trained in a lot of data deployed by a big company。

 almost all of them are going to be transformers today so that's really exciting that we get to get you up to speed on the latest and greatest architectures that people are using now。

But even though transformers are this sort of state of the art architecture that everyone is using for everything today。

 they they have a relatively long history and they initially like it's kind of interesting watching these fields develop because looking back on it when the moment that transformers came out it feels like it ought to have been this big moment。

 this big thing when there was a big sea change， this new architecture。

 this new thing but it actually didn't feel that way because even though there was one moment where the transformer architecture was born these ideas around self-attention around using attention in various ways。

 those had actually been around in the field for several years at that time and in particular these ideas around attention。

 self-attention， they actually developed out of recurrent neural networks。

 so we're going to start there to talk about and motivate these problems so this is going to be a little bit mirroring the historical development of these ideas。

So for that reason， we're actually going in order to introduce transformers。

 we're actually going roll back and recap a little bit about this idea of recurrent neural networks that we saw in the last lecture。

 so as a motivating problem， let's think about this sequence to sequence problem of translation so we want to input one sequence which is going to be a sequence of words in English then we want to output another sequence which is going to be a sequence of words in a different language Italian and because and we can't make assumptions that there's any correspondence between those words the number of words in English sentence might be different from the number of words in the Italian sentence and the order of those words might be totally different so this is a perfect application of a kind of sequence processing algorithms that we sequence processing architectures that we saw in recurrent neural networks and indeed this idea of processing these sequence to sequence problems with recurrent neural networks。

 this goes all the way back to 2014 even a bit earlier than that。

 but people have been processing sequences with recurrent neural networks for more than a decade more than a decade at this point。

So the basic architecture for processing sequence to sequence problems with recurrent neural networks is that typically you'll start with one encoder。

 your encoder is a recurrent neural network， the recurrent neural network recall is this function that gets applied recursively。

 two inputs， one is your XT， your input at the current time step， and the other is your HT minus1。

 which is your hidden state at the previous time step。

 and your recurrent neural network unit will then spit out a next hidden unit。

 a next hidden state at the next time step。And then we can apply that same recurrent neural network unit over in time to process a sequence a potentially variable length。

So in this case， we're using a recurrent neural network encoder that inputs the input sequence in English。

 input sequence， you've got to use relatively short sentences to fit on slides and still have all the boxes show up。

 so we're using a kind of short silly sentence we see the sky and each word and that sentence gets processed but via one tick of the recurrent neural network。

And then the idea of this encoder recurrent neural network is it wants to process all of the words in the input sequence and somehow summarize the content of that input sentence so that we can translate it into a differently into our output target language。

 so the more concrete way that this happens is that after processing all the words in the input in the input sequence。

 we' are going to summarize the entire content of that input sequence into a single vector called the context vector。

And there's a couple different ways that people would typically do these in recurrent neural networks。

 I don't think the details are too interesting， so as you can just think that that context vector is basically the last hidden state of the encoder recurrent neural network。

And now the idea is that because of the recurrent structure of our recurrent neural networks。

 the last hidden state sort of incorporates information of the entire input sequence so we can think of that last hidden state as summarizing or encoding all of the information in the entire input sequence。

 so then that is one vector that is going to kind of summarize that entire input sequence to do whatever we want with it。

And in this case， what we want to do with it is translate that input sequence into an output sequence in a different language。

 So to do that we're going to use a second recurrent neural network called the decoder。

 which usually has the same architecture， but potentially a different weight matrix。

 different set of learned parameters in this decoder G is going to be a different recurrent neural network with different learnable weights U but has the same basic idea now a recurrent neural network unit is going to take three inputs at every time step it's going to take y t minus1。

 which is the token and the output sequence at the previous time step it's going to take s t minus-1 which is the previous hidden state in the output sequence and C which is that context vector summarizing the entire input sequence and then we kind of unroll that output sequence just as we saw in the last lecture and produce words one at a time in the output sequence and I don't speak Italian so I'm I'm not going to try to pronounce these but there's some Italian words on the screen that you can see and I'm assuming that。

That indeed translates to we see the sky。 Hopefully that's correct。

 But the idea is we're going to tick this recurrent neural network one tick at a time。

 It's going to output words one at a time。 And this is basically a summary of what we saw last lecture。

 So this should basically not be too surprising in light of the previous lecture。

But there's a potential problem here right and there's a communication bottleneck here between the input sequence and the output sequence。

 right the only way in which the input sequence is communicating with the output sequence is via that context vector C and that C is going to be a fixed length vector because the size of that vector is fixed when we set the size of our current neural network and maybe that's fine So C might be a fixed length vector of like 128 floats。

 1024 floats， but the size of that input vector is not going to change as our input and output sequence sizes grow or shrink and that's a potential problem So if we're doing short sequences like we see the sky。

 maybe it seems pretty plausible that we can summarize everything we need to know about that sequence in that fixed vector of 1 1024 floats but what if we're not trying to translate four words what if we're trying to translate a whole paragraph or a whole book or like an entire corpus of data then in that case we're going to run into a bottleneck where at some point as we scale that input sequence。

It's just not going to be sensible to ask the network to summarize the entire input sequence into a single fixed length vector。

 so that's going to be a problem。😡，So the solution here is actually let's not bottleneck the network a fixed through one fixed length vector instead let's change the architecture of our recurrent neural network intuitively what we want to do is not force a bottleneck between in a fixed length vector between the input and the output instead as we process the output sequence。

 we're going to give the model the ability to look back at the input sequence and now every time it produces an output vector。

 we want to give the network the opportunity to look back at the entire input sequence and if we do this there's going to be no bottleneck it will scale to much longer sequences and hopefully the model architecture will work much better so that's the motivating idea that lead to attention and transformers and all this great stuff that we see it today it all came like one way of telling the stories that it all came from trying to solve this bottleneck problem in recurrent neural networks。

So let's see how we can actually implement this intuition and endow our recurrent neural network with the ability to look back at the input sequence on every time step。

 So here we're going to start with the same thing。 our encoder neural network is going to remain the same no changes there we still need to set some initial hidden state for the output sequence and so we need to set some initial decoder state S0 in some way but now once we have that decoder hidden state what we're going to do is look back at the input sequence so the way that we're going to do that is by computing some alignment scores by comparing that basically compute a scalar value a scalar value for each step in the input sequence that says how much does that initial decoder state S0 how much does that decoder state match each token of the input sequence so in this case there were four tokens in the input sequence so we want to compute four alignment scores each of which is just a single number that says how what is the similarity between the input。

The input sequence， the token of the input sequence， and this initial decoder state as zero。

Now there's a lot of ways that we could implement alignment scores。

 but a simple way is just use a simple linear layer that we're calling F subatT。

 and so that linear layer is going to input is going to concatenate the decoder hidden state S with one of the encoder hidden states H。

 concatenate those two into a vector and then apply a linear transform that squashes that down into a scalar。

 and that's just a linear operator that can be put into a computational graph and learned jointly of the gradient descent just in the way that we learned all other parameters of a network。

So now at this point we've got sort of this scalar alignment score for each step in the input sequence and now we want to apply a softmax function these scalar alignment scores are totally unbounded。

 they' arbitrary arbitrary real values from minus infinity to infinity we want to put some structure on this to prevent things from blowing up so one way that we do this is apply a softmax function so we've got four scalar values telling us the alignment of that decoder hidden state which each with each of the encoder hidden states now we apply a softmax over those four values to give us a distribution over over those four values so remember the softmax function that we saw a few lectures ago is going to take a vector of arbitrary scores and convert it into a probability distribution which means it'll have the property that each entry in the output softmax probabilities will be between zero and1 and they will sum to one。

So we can think of we have whenever we run a vector through a softmax。

 we can think of the thing we get out as a probability distribution。

 or rather a discrete probability distribution over those input scores。 So in this case。

 so at this point， after we take those alignment scores and run them through a softmax。

 what we've essentially done is predicted a distribution over the input tokens。

 given that decoder hidden state。😊，So now what we want to do is take that distribution over the input tokens and use them to compute a vector summarizing the information in the encoder。

 so the way that we do that is we take our attention scores which recall these numbers A11 a12。

 a13 a14， they're all between 011， they sum to1， we're going to take a linear combination now of the encoder hidden states。

 H1 H2H3H4 and take a linear combination of those encoder hidden states weighted by our attention scores and this will give us a new a context vector that we're calling C1 here in purple。

 which is going to summarize the information in the encoder sequence in some way that's modulated by by those by those attention weights。

And now at this point right so then this C1 is basically some linear combination of the input encoder states H1 to H4 things look basically the same as they did in the non-attention case。

 so we have our context vector we concatenate it with our first token of the output sequence y0 past that to our recurrent unit to get both to get to get our next hidden state of the decoder recurrent neural network as well as the first output token from the decoder recurrent neural network so basically the structure of that decoder RNN did not really change all we did is rather than we computed the context vector in a different way using this attention linear combination mechanism。

But now crucially right so the intuition here is that this context vector basically attends or looks at different parts of the input sequence that is modulated by whatever the output R wants to look at at this moment in time so for example。

 you know part of the input you know as part of the input sequence has this token these two words we see so then in trying to produce that one word in Italian that corresponds to we see the network probably wants to go back and look at those two words in the input sequence in order to know what output word to produce。

 so expect we might want to have some we might expect that intuitively when trying to produce the word ven demo then the network will wants to look back at the words we see and put higher attention weights on those and it doesn't really care about the sky because those words are not necessary for producing that venmo output。

And that's the kind of intuition we're giving the network the ability to look back at the relevant parts of the input sequence for the word that is trying to predict at this moment in time。

And the other thing to keep in mind is that this is all differentiable。

 We don't need to supervise the network。 We don't need to tell it which words in the input sequence were required for each word in the output。

 instead this is just a big computational graph composed of differentable operations。

 this all of this can be learned and to end via gradient descent。

 So at the end of the day we're still going to have this cross-enttropy softmax loss where the network is trying to predict the tokens of the output sequence and in the process of trying to predict the right tokens in the output sequence。

 it's going to learn for itself how to attend to different parts of the input sequence。😡。

So that's really critical right if we had to go in and supervise and tell the network the alignment between the two。

 it would be very difficult to get training data for this kind of thing。

The question is how do we initialize the decoder We're actually using the word you got to be careful。

 we're using the word initialize a little bit overloaded here。

 So one question is the decoder is itself a neural network that has weights when we start training that network。

 we need to initialize those weights in some way so then we will typically initialize the weights of the decoder randomly and then optimize them via gradient descent just as we do with any other neural network weights。

 but there's a second notion of initialize which is that when the network is processing a sequence whether whatever its current value of the weights are。

 we need some way to set that initial hidden state at the time we start processing an output sequence and in that case we need some rule or some way to set that initial hidden state of the decoder output sequence there's a couple different mechanisms for this sometimes you might initialize it as the last hidden state of the encodeder is one thing you'll sometimes do you might have a linear transform that projects has some learned projection from decoder state to first from the last encodeder。

State to the first decoder state， or sometimes will people even initialize the first hidden state of the decoder to be all zeros。

 Any of those will work as long as you train the network to expect that kind of input。

So the question is negations and XOs would this cause a problem， maybe this is a hard problem。

 but then you need a lot of data， a lot of flops to try to hope the network can disentangle this。

 but basically recurrent unit takes three things as input。

 it takes in the decoder it takes the previous hidden state， the previous decoder hidden state。

 it takes the current context vector and it takes the current token in the output sequence and then from that we produce the next hidden state。

 and then from the next hidden state， then we go and predict the output token。

So that's actually the same setup as in the non attentiontention case。 I guess there's。

 there's an implicit connection from theres， there's a connection from S 0 to S 1 that we're not drawing。

 Well， so there there should have been another arrow from S 0 to S 1。

 I think I just dropped the S 0 arrow。 So sorry about that。Well。

 we're basically letting the network decide for itself to look back at any part of the input sequence that it thinks might be relevant for the task at hand。

 but the reason why we think that this mechanism is plausible and might be helpful for the network is because we know that in a language task there often is some kind of correspondence between words and the output and words and input and we want to let the network kind of look back and pick out which are the relevant bits of the input for producing this bit of the output。

 but again， we're not directly supervising it， We're not telling it how to use these attention scores。

 but the intuition is that we think that's a plausible thing that it might choose to do given this mechanism。

Okay so that's sort of like one tick of the output and now basically we do it again。

 we do this whole process again for every time we tick the decoder RnN right remember the problem we're trying to solve is that previously the decoder was bottlenecking through a single vector now we're going compute instead of bottlenecking through a single vector we're going to repeat this whole process again and compute a new context vector for the second time step of the decoder and let it go back and look at the whole input sequence yet again So now basically given our S1。

 which is our computed first hidden state in the decoder we're going go back take S1 go back and compute comparison and use our attention mechanism to compute similarity scores between S1 and all of the hidden states in the encodeder that will compute our similarity scores using that exact same FATT that same linear projection that we used at the first time step compute these alignment scores again cram them through softm to get a new distribution over the input sequence for the second。

decoder time step and now compute a new linear combination of the encoder hidden states now weighted by this new distribution that we computed at the second time step and this will basically give us a new context vector。

 C2 that now is a different summarization of the input sequence that's now computed as a new linear combination of the input encoder hidden states。

And then the whole thing kind of iterates we have a new context vector。

 we use that to run another tick of our decoder RNN unit that will now does include that mysterious missing arrow that wasn't there on the previous time step。

 so then given our new context vector， given the next token of the output sequence and given the S1 hidden state of the decoder。

 we compute a new decoder state S2 and then from that compute another token of the output sequence。

And again， remember， you know in this case it's producing ill。

 which maybe is the according to the slide， I hope that's true and then you in this case there's maybe a one to one correspondence between the word the network is trying to produce for this sequence and one of the words in the output and one of the words in the input so we might expect that the network should put relatively high attention weight on just one of the words in the input sequence and relatively low attention weight on all the other words in the input sequence。

 but again we don't supervise this， the network is deciding for itself how to make use of this mechanism all driven by gradient descent on our training task and this whole thing is we're just going to repeat that whole process for every tick of the decoder RNM。

So now this basically solved our problem right we are no longer bottlenecking the input sequence through a single fixed length vector instead we have this new mechanism where at every time step of the decoder。

 the network looks back at the entire input sequence resummarizes the input sequence to generate a new context vector on the fly for this one time step of the decoder and then uses that to produce the outputs。

 so this is a pretty cool mechanism and this is called attention because the network is attending or looking at different parts of the input sequence at every moment in its output。

😡，So we talked about these attention weights and we said that they were driven the network was learning for itself how to set these attention weights based on its training data based on its training task and another really cool thing about attention is it also gives us a way to introspect and see what the network is looking at as it's trying to solve this problem so we never told it what the alignment was between the input sequence and the output sequence。

 but by looking at the attention weights that the network predicts when trying to solve this task。

 we get a sense of what the network was looking at while trying to solve the problem so that gives us a way to interpret the processing of the neural network in some way。

 and so heres so one thing that we can do is then go and look at in the process of producing a processing a particular sequence what were the attention weights that the network predicted when trying to do this task and we can visualize these in a two-dimensional grid so here we're looking at an example of English to French translation and across and across。

The top， we have our input sequence。 The agreement on the European economic area was signed in August 1992 and then running down the rows is the output sequence。

 which is in French， which I will not attempt to pronounce。

 But you can see that basically through this attention mechanism for every remember the way this attention mechanism work is that each time the network produced one of these words in the output sequence。

 it predicted a probability distribution over the entire input sequence。

 So we visualize that in that first row。 So if you look at the first row of this matrix。

 we're visualizing that predicted probability distribution over the entire input English sentence。

 And we see that when trying to predict that first word of the French sentence。

 then it puts a lot of probability mass on the English word the and basically no probability mass on any of the other words。

 then when predicting the second word of the output sequence。

 remember it goes back and predict a new distribution over the entire input sequence。

 and that's going to be the second row in this matrix。 So you can see that。

Cord it puts a lot of probability mass on agreement and then no probability mass anywhere else。

 so then that gives us some sense that the network actually kind of did figure out the alignment between the input words and the output words when doing this translation task。

And there's some interesting patterns here that here that kind of pop up look when we see diagonal structures in this attention matrix。

 that means that there was a one to one correspondence between words in order between the input sequence and the output sequence。

 so in particular we see that the agreement on the first four words of the input sequence correspond to this diagonal structure in the attention matrix so that means that the network has decided for itself that these first four words of the input sequence sort of align or matchup or correspond to the first four words of the input sequence and the same thing for the last several words。

 so again we see this diagonal structure at the end of the sequence。

 which means that August 1992 or in August 1992 corresponds to these last couple words in the French sequence and again there's this one to one correspondence between words in the output and words in the input。

But we see some other interesting stuff in the middle here。 So in the middle。

 we see European economic area， but in the French， we see words that look kind of like those in a slightly different order。

Good question。 How does it figure out the grammar， That's the mystery of deep learning。

 but like basically we told that we didn't tell the network anything about grammar。

 We told the network we supervised it with a lot of input output pairs。

 We told it here's an input sequence in English， here's an output sequence in French。

 here's a mechanism for processing this and learn via gradient descent to like set the weights of this architecture in order in order to produce this output from this input。

 we'd never told it anything about grammar， but it kind of because we as human designers have this intuition that maybe it makes sense that there ought to be some correspondence。

 with some of the words， so we bake in a mechanism that we think as the human designers might be helpful for solving this problem。

 and the network figures out for itself in the process of doing the end- to-end task how to make use of that mechanism to solve the problem we set for it。

😊，And it's pretty， pretty amazing that it works。Right， but in this case。

 you know it kind of figured out some of the grammar for itself。

 so it sees that you know we see this non- diagonal sort of backward diagonal in the attention matrix here。

 and that means that the network figured out for itself this other this different word order between words in English and words in French。

Or in the middle， you see there's a little there's a little like two by two grid kind of here and that kind of corresponds to a situation where there might not have been a one to one correspondence between the English words and the French words。

 There might have been two French words that corresponded to two English words and they didn't perfectly disentangle perfectly。

 I mean the network just all figures out this for itself over the process of training on a lot of data and putting a lot of compute through this and that's pretty cool。

Okay， so there's actually so that's and this actually was the initial usage of attention in machine learning it actually came from these machine translation problems so this was from a paper back in 2015 neural Machine translationlation by jointly a learning to align and translate and this paper actually just won the runnerup Test of Time Award at ICR 2025 so that's pretty cool a nice nice know this has been a really impactful paper over time。

But it turns out that there's actually a more general idea here and a more general operator hiding here。

 you know we approach this problem from the perspective of trying to fix our recurrent neural networks。

 but it turns out the mechanism that we used to fix the recurrent neural networks actually is something general and interesting and really powerful in its own right so now we want to try to pull that out。

 pull out this idea of attention and divorce the idea of attention from the recurrent neural networks and it turns out that attention will be a very useful and powerful computational primitive for neural networks in its own right even if then we can cut away the recurrent neural network part and just be left with attention as the core primitive in our architecture and that's kind of where we're going towards。

😡，So now what we want to do is take this idea of attention as we saw it in recurrent neural networks and try to generalize it and try to carve out this independent operator that can be used on its own。

 So let's think about what this attention mechanism was doing basically what this attention mechanism did is there were a bunch of query vectors are maybe maybe it makes sense to talk about these in the other order。

 So there's data vectors which are like data that we want to summarize。

 These are the encoder states of the encoder RnN。 So we have this input sequence and we've summarized that into a sequence of vectors and the sequence of vectors is sort of data that we think is relevant for the problem that we're trying to solve and now in the process of trying to make use of that data we want to produce a bunch of outputs and for each output we have a query vector a query vector is a vector that we're trying to use to solve to produce some piece of output and in this case the query vectors are the hidden states of the decoder RNN and we have this property that for each。

Qury vector， we want to go back， look at the data vectors and summarize the information in the data vectors into into a context vector for each。

 Well， okay from purpose from the purpose of attention， this gets a little bit weird。

 So the output of the attention operator are the context vectors that we just talked about for the RN。

 So if we're thinking about just what does that attention operator do。

 the output of the attention operator where the context vectors that we feed into the RN。

 So then what is the attention operator doing， the attention operator is taking a query vector going back to the input data vectors。

 summarizing the data vectors in some new way to produce an output vector。

 and that's what the attention operator is doing。 does that kind of make sense as a generalization of this attention mechanism that we just saw。

这有。Yeah， yeah， I'll repeat it again because it's tricky There's a lot of stuff flying around here。

 a lot of boxes and we're changing the words that we're using to define the boxes。 So I get it。

 there's a lot of happening。 So what the attention operator is doing is there's a bunch of data vectors。

 which are the encoder hidden states then we have a bunch of query vectors which are the things we're trying to produce output for。

 now in the process of processing a query vector， we're going to go back to the data vectors。

 summarize the data vectors in a new custom way for each query vector and that will produce and output vector which is the context to be fed into the next tick of the RnN so our query vectors are these guys in green for each query vector。

 we go back to the data vectors， summarize the data vectors and then produce a new output vector。

 which is one of the contexts that we then feed into the rest of the network So you know this is kind of tricky because we're trying to go into this architecture and like cut carefully cut out the attention part and cut it out from the RNN。

So then we're going to try to like walk through this again from the perspective of just the attention operator。

 so from the perspective of just the attention operator。

 we're going to start with just one query vector at first， which is know one of the states in our RN。

 we also have a bunch of data vectors， which are the encoder hidden states in the RN。

Now the computation that we want to perform is first compute similarities between that query vector and all of the data vectors。

 this is the exact same thing that we just saw just sort of written in a different way。

 so we use this FATT function to compute these similarity scores from to compute similarities between each data vector and our one query vector。

Then once we have those similarities， we're going to squash them through a softmax to get attention weights。

 And this will be a distribution over the data vectors that has been computed on the fly for this one query vector。

Then we want to do is produce an output vector。 and this output vector is a linear combination of our data vectors where those linear combination weights are the attention scores that we just computed。

 So this is the output of the attention layer。 And then in the context of the larger RN that we saw the output of the attention layer or the attention operator will'll become an input to the next tick of the decoder RN。

 but we're trying to deprecate the RnN。 So we don't want to talk about that。

 We just want to talk about the attention and focus on the computation happening inside the attention layer。

So so this is basically the operator that we saw in the RN right we had this one we did this process over and over again of taking a query vector。

 using it to compute similarity scores， getting attention weights， getting an output vector。

 then we got a new query vector where did that query vector come from， At operator doesn't care。

 get a new query vector， go back， summarize the data vectors。

 get a new output vector and that's the core of the attention operator。

 so now let's try to generalize this and make it even more powerful computational primitive。😡，Yeah。

 so in principle， this FATT doesn't have to be it could be any function。

 it could be any function of two vectors that outputs a scalar in principle。

 but in practice we're actually going to make it simpler in a couple slides。But in principle， yeah。

 you could just slot in any any function that you wanted there。

Okay so the first generalization that we're going to do is actually the opposite of what you just suggested and make that similarity function simpler。

 so we said in principle it can be any function that takes two vectors and gives a similarity score What's the simplest possible function that inputs two vectors and gives us a scalar similarity score as a dot product so we want to try to make things simpler and also generalized at the same time。

 and it turns out that a dot product is good enough of a similarity score to be used for this purpose so the first thing we're going to do is actually just only use dot products to compute similarity。

But it turns out there's a slight problem with dot products and this one's kind of subtle because there's a weird interaction between the dot product and the softmax。

 and that has to do with what happens when the dimension of those vectors scales up or down so if you have the motivating example is that if you scale the dimension of that vector say we had a constant vector of all ones of like dimension 10 versus a constant vector of all ones of dimension 100 then as we go to the higher dimensional vector。

 then when we compute the sum inside that softmax， then we're going to be dividing by a larger number。

 So we'll end up with more squashed probability scores as we go to higher dimensional vectors that can lead to vanish ingredientss as we just saw in the previous lecture and prevent learning of this whole thing So as kind of a slight hack to prevent that and make this architecture more generally more generalizably scalable up and down to different dimension vectors what we're going to do is actually not use the pure dot product but。

😊，S the dot product down by the square root of the dimension of those vectors that we're looking at。

 And this is just a way to prevent vanish ingredients and give nicer gradient flow through the softmax for a wider range of dimensions of vectors。

 And this turns out to be very important because as we make these networks bigger and bigger and bigger over time。

 we want to get higher dimensional vectors because that gives us more compute， more capacity。

 So we always want to think about how our architectures will scale as we make the parts of those architectures get bigger and bigger and bigger。

😊，So this scaled dot product is actually really important for preventing vanish ingredients here。

Yeah， a question was we're limited to data inquiry query vectors of the same size。

 but we'll actually fix that。So our first generalization was to use actually scaled dot product similarity as our as our similarity measure。

So now， know if we go back and look at the shapes of these things。

 we have one query vector of dimension DQ， we have data vectors of dimension Nx by DQ as well because it's a dot product they need to match。

But there's actually a next generalization generalization that we're going to do is have multiple query vectors right like maybe we don't want to process just one query vector at a time。

 we want to have the ability to process a whole set of query vectors all at once and this kind of happens in the RnN you know we did end up with a bunch of query vectors and it's useful for the attention operator to be able to process not one query vector at a time but basically process a set of query vectors all in parallel and perform the exact same computation in parallel for a whole set of query vectors so in this case we've now generalized it to have n so q is now a matrix of shape nq by Dq so we have nq query vectors。

 each of those query vectors has dimension Dq we have our data vectors is a matrix of size n x by Dq and now now the computation changes a little bit because now when we compute these alignment scores when we compute these similarities basically we want to compute all pairs of similarities between all of the input data vectors。

And all of the input query vectors and each one of those similarities is a dot product。

 So a scale dot product。 So what's a very efficient and easy and natural way for us to compute dot products between two sets of input vectors that turns out exactly to be a matrix multiply because remember when you do a matrix multiply each entry in the output matrix is the inner product of one of the columns of one of your matrices and the rows of your other matrix And that's so then each entry in the output of a matrix multiply is exactly the dot product between the rows and the columns in the output。

 So by computing a matrix multiply between our query vectors Q and our data vectors X and you need to get a transpose in there to make the grows and columns match up in the right way。

 This basically gives us lets us compute all the similarities between all the data vectors and all the query vectors all in one simple matrix multiply。

Now we still need to compute these attention weights。

 remember the attention weights we want to compute for each query vector。

 we want to compute a distribution over the data vectors。

 Well we already have these now our similarity scores are not just a single vector of scores。

 they're not a matrix of scores giving all the similarities。

 but we still want to compute a distribution over the data vectors for each query vector independently。

 So now we need to compute the softmax over just one of the axes of that matrix of similarity scores。

 So this is basically the exact same computation that we just saw。

 we're just doing it in parallel for a set of query vectors all at once。

Now we need to compute the output vectors and remember the output vectors were going to be a weighted combination of the data vectors where those weights are the values in the softmax and it turns out that this is also something the matrix multiply does another way to think about matrix multiply is that when you take a matrix multiply of two matrices a different way to view a matrix multiply is that it takes a linear combination of oh man am I going to get the rows in the columns in the right way。

 but I think you get the linear combination of the columns of one of your input matrices weighted by the values in the other input matrix so this is another interpretation of matrix multiplication so then if you kind of work through the indices and draw some little pictures for yourself to prove to yourself what's going on it also turns out that in order to compute now we want to do is compute many linear combinations of the data vectors where each linear combination will be given by the probabilities in one of the rows of the attention matrix。

So we can compute all of these all at once with another matrix multiply between the attention matrix A and the data vectors X。

 And again， you need to get the transpos in the right order to make this work out。

 But basically this is the exact same operation that we just saw。

 but we're now doing it for a set of query vectors all at once。

 And it turns out that we can do it all at once。 with just a couple matrix multiplies。

There's a next way that we'll generalize this is notice that in this equation。

 the data vectors X are actually entering in two different places in this computation。

 The first place that we're using the data vectors x is to compute similarities with the query vectors in this similarities computation So in that notion what we're trying to do is say oh hey data vector。

 how much do you line up with each query vector as measured by an inner product。

 but then we're also using the data vectors again to compute the output vectors。

 So the output vectors are now a linear combination of the data vectors weighted by our attention weights and it maybe seems a little bit weird to reuse the data vectors in those two different contexts。

 So now what we want to do is separate those two usage of the data vectors and let the network sort of figure out for itself two different ways to use the data vectors in those two contexts。

So to do that we'll introduce this idea of keys and queries so now what we're going to do is you know we had a set of data vectors。

 but what we're going to do is for each data vector。

 we're going to project each data vector into two vectors， one is a key vector。

 one is a value vector and the idea of the key vectors are the key vectors are going to be compared with the query vectors to compute the alignment scores and the value vectors are what we're going to compute linear combinations of in order to compute the output from the layer。

And this also so then the way that we implement this is we add two learnable weight matrices。

 the key matrix and the value matrix which are going to be linear projections that project the input that project the data vectors into key vectors and value vectors so now the data vectors remember we have n data vectors。

 each of dimension dx so now the key matrix projects is a linear transformation that project from dx into Dq because we know that we're going to compare the key vectors with the query vectors so they need to have the same dimension as the query vectors so that will project so then applying matrix multiply of k equals xwk will project each data vector into a key vector of dimension Dq then we' have another weight matrix that projects from dx to Dv which is the dimension of the value vectors which in principle could be different than the query vector dimension and then will'll separately project each data vector into a value vector again with a matrix multiply operation。

OrHere。And the intuition here is that is kind of like in a search engine like you want to separate what you're looking for from the answer you want in response to that query right so like you go to Google or these days chat EptT and you type in like what is the best school in the world that's your query and then the value you get that's the query that needs to be combined with the keys in the backend but then the value。

 the data you want to get back from that query is actually different from the query you typed in right so we want to separate this idea of like you put your query in what is the best school in the world。

 that query needs to go match on all the different strings in on the internet and then the value you want to get back from that query is Stanford which is a different value which is a different value which is different from the query that you put in so that's kind of the intuition another intuition between separating the keys and the queries and the values in this way the query is what I'm looking for the key is in the back end we have some record of all the data back there in the data vectors but when we query we want to match up against part of potentially just part。

of the data vector， and then the thing we want to get back from the data vector is the value。

 So we're separating the usage of the data vectors into those two different notions of keys and values。

Then we can visualize this in a different way。So now we're finally throwing away the RNN and we're looking at attention just as an operator on its own。

 so we can step through this operation again， we've got our query vectors coming in。

 we've got our data vectors coming in。😊，Now what we're going to do is from the data vectors。

 we're going to project each data vector into a key and a value then we're going to compare each key with each query to get our similarity scores right so this isity this is a matrix of scalars giving the similarities between each key and each query then once we have this matrix of similarity scores。

 we want to compute a distribution over each a distribution over the data vectors for each query so that means we need to run softmax over this matrix of alignment scores or we compute the softmax over each row。

Then what we do is we want to take reweight the value vectors by the attention scores in the softmax。

Oh， actually， no， sorry， we column we want each column to be a distribution， right。

 because we for each query a distribution over the keys。

 which means we want softmax over the columns because we want it to be aligned to the columns。

So then what we do is you know we've got this query1 we've predicted this distribution over all of the keys from this computation。

 then we're going to take a linear combination of the values weighted by these attention weights and compute a linear combination of the value vectors to produce our first output vector y1 and then the same thing happens over here our second query got compared with all the keys。

 we computed a distribution over those alignment scores to get a distribution over the keys for the second query which then get linear then we use those to linearly combine the values to produce our output vector so now this is now the attention operator sort of standing on its own。

 divorce from the recurrent neural network。The question is how do you divide the data vector into keys and values。

 the beautiful part is we don't have to say how just we just give the neural network the capacity to split it by itself by giving it this mechanism to project separately into keys and values but we're not going to tell it how to do it these are just going to be the key matrix and the value matrix are just going to be learnable parameters of the model that will be learned via gradient descent along with everything else。

 so just as we did not tell it how to align the English and the French sentences。

 all of that was sort of learned via gradient descent。

 the model we learn for itself how to separately project into keys and values in a way that's sensible that's helpful for the problem it's trying to solve。

So the keys and values， you might think of it as some kind of filter。

 So the data vector might have a lot of stuff in there， but for the task at hand。

 we might want to filter the data vector in various ways and only try to match our queries against part of it。

 and we only care about retrieving information of a different part of it。

 So you could think of those as yeah， filtering the information in the data vector in two different ways。

Okay， so this is this is basically our attention operator。 And now like there's no R andN here。

 This is just a neural network layer that you could have standing on its own， right。

 It receives two inputs， the query vectors in the data vectors。

 It has two weights of learnable parameters， which are the key matrix and the value matrix。

 It inputs sets two sequences of vectors。 outputs a sequence of vectors。

 So this is a neural network layer in its own right。

 that you could start to plug into your neural network architectures in various places。

This is sometimes called a cross attention layer because it has two sets of inputs coming in。

 right The idea is we have both data vectors and query vectors。

 they're potentially coming from two different sources and this is sometimes useful so that I have a set of queries for each query I want to go and summarize information from my data which is potentially different or a different number or totally different of my query vectors so this is sometimes called a crossat layer because we're cross-attending between two different sets of things。

But there's another version of this that happens maybe even more commonly is a self-attention layer。

 So here what we're going to do is we only have one set of things。

 we only have one sequence of inputs。 we have one set of vectors。

 one sequence of vectors that we're processing and then so now we no longer had this separation between data vectors and query vectors。

 We just have one set of input vectors。That we would like to process。

 So in a self-atten layer we're going to have we're going have a set of input vectors and we're going to produce a set of output vectors。

 so we want to input a set of vectors x output a set of vectors Y that are the same number as the input vectors。

 But now the mechanism of this is basically the same attention mechanism that we just saw But now rather than projecting then we're still going to use this notion of filtering but rather than projecting our data vectors into keys and queries as we previously did now what we're going to do is take each one of our input vectors and project it to three different things from each of our input vectors we're going to project it to a query to a key and to a value and so the equations change just a little bit but the picture over here doesn't actually change very much for each of our input vectors we separately project it to a query to a key and to a value and now we have the exact same computation now we've got queries。

 we've got keys， we've got values from the perspective of everything happening up here it's all。

me it just so happened that we computed the keys and the queries and the values all from different linear projections of those same input vectors。

 but all the computation otherwise shared。Yeah， question is， how do you where what are D N and D out。

 How are they sized， So these are going be architectural hyperparameters of the layer， right。

 Like just when we have a learnable linear layer in a model。

 a linear layer basically projects from a D N to a D out。

 those are going be architectural hyperparameters of the layer。 same thing with the self-atten layer。

 The D N and the D out are going be architectural hyperparameters of the layer。 And in principle。

 they could be different， right， there's enough there's enough flexibility in this architecture so that in principle。

 D N and D out could be different， although I don't think I've almost ever seen that in practice。

 they're like almost always the same。 So I've been like a little bit extra general in the notation here。

Okay so I don't know that we necessarily need to walk through this Oh actually there is one important thing right so I said that we are separately projecting the inputs into queries keys and values so that happens via three matrix multiplies with our three learnable weight matrices now we have three learnable weight matrices。

 one for keys， one for value is one for queries and we separately project the input vectors x into keys queries and values but in practice we can actually typically compute just one matrix multiply all at once for those because it's typically more efficient on hardware to do fewer large matrix multiplies than it is to do more smaller matrix multiplies so a pretty common trick in practice is to fuse is to sort of concatenate these three matrices along the dimensions and compute all of these keys queries and values for all the input vectors all at once with one big matrix multiply。

If you've read transformers before， they sometimes separate between encodeder and decoder transformers or encodeder decoder attention。

 so in that case like this would be the decoder only attention if you've read transformer papers before。

 and which corresponds to the way that it's used in the decoder of the RNN in the initial example of beginning of class。

 but this mechanism is actually just like the most commonly used flavor of attention nowadays is this sort of so-called decoder only attention。

So we are quite divorcing ourselves away from the RNN now so this flavor of it doesn't really make sense to be used in the RNN that we saw at the beginning of class right so we've basically been like doing a little bit of a sle of hand here where we introduced this architecture for the purpose of RNN in this very concrete case of machine translation sequences sequence。

 but we've now generalized it to become a totally different operator that can be used all on its own and in this particular generalization into self-attention。

 it actually no longer can be used in that decoder in the RNN。

 but it's a very useful primitive that gets used in a lot of other places it turns out。

The question is what's the benefit or difference between the self-attention worth cross attention they would get used in different contexts。

 So in some situations you naturally have two different kinds of data that you want to compare which we saw。

 for example， in the machine translation setting we have an input sentence we have an output sentence。

 we believe that there's some natural structure in the problem that there's two different sets of things that we want to compare that also might happen in say image captioning say we have an input image。

 we want to produce an output sentence， there's two different kinds of things we want to compare pieces of the image and tokens in the words that we're generating So for some problems there's just this natural structure where you have two different kinds of things floating around but for other problems。

 there aren't two kinds of things there's just one thing So say you're doing image classification then there's only an image we just want to process the image So in that case we just want to compare parts of the image with itself and that's where you would use a self-atten layer So they just get used in different for different kinds of problems。

But， crucially， we want to reuse basically the same machinery and the same computational primitives you to be used in those different kinds of problems。

 And that's really beneficial。There's a couple interesting things about attention that I want to get through。

 So one is like let's consider what happens if you permute the inputs right we had a set of input vectors。

 what happens if you shuffle them and process them in a different order。

 now actually a lot of interesting stuff happens So the keys。

 the queries and the values will all end up the same because they are computed as linear projections of the input So we'll end up getting the same keys queries and values。

 they'll just be in a different order shuffled in the same way that the inputs were and now because our similarity scores where just do products willll also end up with the same similarity scores just again shuffled in accordance with the way we shuffled input same thing with the softmax Somax doesn't actually care about the order of its inputs So the softmax is now operating on the same vector but shuffled So each column of our attention weights will end up the same as they did before just shuffled and then same thing with linear combinations So our our outputs y will actually still be the same outputs as we said before。

 they'll just all be shuffled So that means there's a really interesting structure here called。

variRemember we saw this a couple lectures ago with convolution。

 Now we see a different equivariance property of these self-attention layers。

 which is that if we shuffle the inputs， then the outputs that we get the same outputs just shuffled in the same way that the inputs were shuffled。

And this kind of means in this case that self-attention doesn't actually care about the order of the inputs。

 If we change the order of the inputs， we'll get the same outputs just shuffled in the same way that the computation of the layer does not depend on the order in which we present the inputs So that means that we can think of self-attention actually not as operating on sequences of vectors。

 they happen to be packed into an ordered sequence of a matrix。

 but we really think of it instead as operating on an unordered set of vectors。

 because the outputs that we get don't actually depend on what order we patch those vectors into our input matrix。

 So we really think about this as a kind of different neural network primitive。

 thatre fundamentally operates on sets of vectors rather than sequences of vectors。😡。

But this is sometimes a problem， sometimes it is useful to tell the neural network what the order of the entries is。

 so as a quick fix to that will sometimes concatenate an additional piece of data onto each of the input vectors called a position embedding that is basically some piece of data that tells the neural network。

 this one's at index1， this one's in index 2 this one's in index 3， blah， bh， bh bh bla。

 and there's a bunch of different mechanisms for that。The question is。

 is it going to train to the same result， the training I'm not really talking about the training here。

 I'm talking about if you fix the weight matrices and just consider the computation of the layer。

 then if I were to shuffle the inputs， then I receive the same outputs。

 but they'll be shuffled in the same way that the inputs were shuffled so like the question of what vectors do I compute at the output does not depend on the vectors on the order of the vectors and input。

 but the order of the vectors I get from the output does depend on the order that they were presented in the input。

😡，So there's another couple tricks we can do with self-attention well I'll go through these a little bit faster。

 So sometimes in a full self-atten layer， we allowed every piece of the input to look at every other piece of the input。

 but for some problems we might want to impose some structure on this computation and say that certain piece of the input are only allowed to look at certain other pieces of the input rather than at rather than everything being allowed to look at everything and we can implement a notion called mask self-atten So what we're going to do is after we compute these alignment scores E。

 we're going to go in and override the alignment scores with negative infinities in places where we want to block the attention and now if you have a negative infinity in your alignment scores then after you do a softmax。

 it's going to end up as a zero if you walk through the softmax computation so that means that if there's a zero whatever there's a negative infinity in the alignment scores。

We end up with a zero in the softmax in the scores after the softmax。

 which means that that output Y will not depend on the value vector computed at that index。

 So this is a mechanism to let us control which inputs are allowed to interact with each other in the process of the computation。

And we might want to do this now for language modeling right because now we've generalized this operator to the point where we don't need an RNN at all。

 we can just use this for the same problem that we used to use an R&N for。

 so now we can use it to process sequence those words like attention is very and then output is very cool so then in this case we're doing this same language modeling task that we saw last lecture with RNNs。

 but we can now do us just do it natively with this self-attenion block。

 but in this case we want to make the first output is only depend on the first word。

 the second output very only allowed to depend on the first two words we don't want let the network look ahead in the sequence and cheat so here is where we would use masking。

😡，Another thing that we'll sometimes do with self-attention is called multi-headed selfattention。

 where you run end copies like H separate independent copies of self-attention in parallel。

 Why do you want to do this because it's more computation， it's more flops， it's more parameters。

 deep learning we always want more and bigger and this is another way that you can make this network that make this layer more and bigger and more powerful so what we're going do is take our inputs X route them to H independent copies of separate self-atten layers。

 this will each produce their own outputs y， which will then stack up along the output and then fuse and then have another linear projection at the output to kind of fuse the output data from each of the independent self- attentionten layers。

And now in this case， this is called multiheaded self attention。

 and this is basically the format that we always see in practice。

 so this is like whenever you see self attention used these days。

 it's almost always this multiheaded selfat version。

And in practice it turns out that you can compute this all with matrix multiplies as well so you don't have to like run a for loop you can compute each of these h copies of self-attention all in parallel if you're clever and use batched matrix multiplies all in the right places so in fact this whole self-atten operator it seems like a lot of stuff going on but it's really basically just four matrix multiplies we have one matrix multiply where we take our inputs and project them to queries keys and values we have another matrix multiply where we computeq case similarity for each  Q。

 we compute the similarity against all all the ks and that's one big batched matrix multiply now in the multi-headed case we have another one called v weighting where we want to take linear combinations of all the values weighted by the softmax entries and that can be done in another big batched matrix multiply and then finally we have an output projection to mix information across our different heads of our self-attention So even though there's a lot of equations there's a lot of vectors flying around this whole self- attention。

operatorator is basically just four big batch matrix multiplies。

 and that's great because matrix multiplies are a really scalable， powerful。

 primitive that we can distribute， we can optimize。

 and we can make this thing highly highly parallel， highly scalable， highly efficient。Yeah。

 the question is that the X1， X to X 3， they're exactly the same。 but just， but。

Yeah but we're just going to have separate like basically separate copies of the self- attentionential layer they all and they will all be random they all have different weights critically and those weights will be initialized randomly different and initialization。

 so they will end up learning to process them in slightly different ways。

 so this is just a way to give extra capacity to the layer。No， yeah。

 the only thing different between the different heads is the weights。

 So the architecture is exactly the same。 The computation is exactly the same。

 but they'll have different weights， and those weights will be initialized to different things at initialization。

 But other than that， it's all exactly the same。Okay， there's some stuff there that we can skip。

 but now basically we've gotten to one really interesting place where we have basically three different ways to process sequences that we've seen in this class。

 The first is recurrent neural networks。 We saw that recurrent neural networks basically operate on1Dored sequences and they're really cool。

 They're really powerful。 people like them for a long time。

 but they're fundamentally not very parazable because of this concurrent structure where each hidden state depends on the previous hidden state。

 Then they're just a fundamentally sequential algorithm。

 There's no way to parallellyze this across the sequence and that makes them very difficult to scale。

 very difficult to make very big。😊，Another primitive that we've seen is convolution and convolution basically operates on multi-dimensional grids。

 we've seen it in twodimensional grids in the case of images， you can also run them on 1D grids。

 3D grids， 4D grids and convolution basically is something that mixes information locally in ndimensal grids This is great。

 it's very parallelizable because by this notion of sliding a kernel around a grid each position that we might want to place the kernel can in principle be computed in parallel。

 so this is a very parallelizable primitive but it has a hard time building up large receptive fields if we want to summarize an entire very long input sequence or an entire very large image with convolution we even need to have very large convolutional kernels or stack up many。

 many， many convolutional layers so that still introduces some fundamentalal sequentiality in the way that we need to process large pieces of data。

😊，And now self-at basically is a separate kind of primitive that operates on sets of vectors。

 It sort of naturally generalizes to long sequences。

 There are no bottlenecks in the way that there are in recurrent neural networks there's also no necessity of stacking up many。

 many layers of them to let all the vectors look at each other in one layer of self-atten。

 every vector looks at every other vector So with just one layer you can summarize you can do a lot of computation and it's also highly parallelzable as we saw the whole operation is just four big matrix multiplies and matrix multiplies are a great primitive that we can distribute。

 we can run on GPs we can run in very scalable distributed ways the only downside of attention is that it's expensive。

 it ends up having n squared compute for a sequence of length N and n squared or later n or n memory for a sequence of length n。

 and if your N ends up being like 100000 million10 million n squared becomes very expensive but you can solve that by buying more GPUs So that's basically the solution that people have come up。

here so basically， attention has become this super awesome primitive that is super powerful for processing very arbitrary pieces of data。

 and you might be wondering which of these you should use attention is all you need。

 It turns out that of the three， you can get a long way using only attention。

 Yeah the question is is parazable， what's the advantage of that。

 the advantage of that is that in the history of computing it gets hard to make processors faster we've sort of run up against this limit as a fundamental limit in hardware。

 that it's become very difficult to make individual processor faster。

 But what we can do very easily is get a lot of processors right So so the way that we've able to marshal more computation over the last two decades is finding algorithms that do not require running on one really fast processor。

 But instead if we can have an algorithm that can make use of 10 processors or 10 processors or 100 processors there are a million processors。

 I want to blanket the entire Stanford campus with processors and have all of them work。😊。

together in concert to process this big thing， if we can find algorithms that do that。

 that's how we can scale up and get really big， powerful computations。

 So the benefit of parallelzability is that if you have algorithms that can trivially make use of more and more and more processors in parallel。

 then we can scale up those algorithms without having to wait for our individual processors to become faster。

 which they may never will。Yeah is there a tradeoff at the n squared。

 I think the n squared is actually a good thing， so it seems bad。

 you're taught in computer science that higher parameters inside that n that those is bad。

 but in the case of neural networks for compute it could actually be a good thing because more compute means the network is doing more computation it has more ability to think。

 more ability to process so actually the more compute the network does on the input sequence actually maybe the better answer it it could arrive to so it means that it's more expensive but that's not necessarily a bad thing。

So basically the transformer is now a neural network architecture that puts self-attention at the core of everything。

 So our input is going to be a set of vectors X。 then we're going to run all those vectors through self-attention。

 which is， as we just said this amazing primitive that lets all the vectors talk to each other after that we'll wrap that self-atten in residual connection for all the same reasons that we wanted to use residual connections in resnets just a couple lectures ago we will take the output of that residual connection pass it through a layer normalization because as we saw in resnets and in CNNNs adding normalization inside your architectures makes them train more stably but then now there's something interesting because the self-attention。

 basically what it does is compares all the vectors with each other and that's a very useful primitive that's a very powerful thing to do but we also want to give this network the ability to perform processing vectors independently one by one So then there's a second primitive inside the transformer which is the multilayer perception on MLP or also called FFN but basically this is a little。

2 layer neural network that operates that is run independently on each one of our vectors inside。

 so then this kind of works in concert with a self-attention。

 whereas selfattention lets all the vectors talk to each other and compare with each other and the FFN or MLP lets us perform computation on each vector independently。

We'll also wrap the MLP in a residual connection， put a layer normalization and put a boxer on the whole thing and call it a neural network block。

 So this is our transformer block and a transformer is just a sequence of transformer blocks and these things have gotten much。

 much bigger over time the architectures haven't changed too much since 2017 when this is introduced the original transformer was something like 12 blocks。

 200 million parameters and now where people are training transformers with hundreds of blocks and trillions of parameters so this same architecture has scaled across many orders of magnitude in compute and size and parameters over the past eight years。

They can be used both for language modeling as we've sort of already seen。

 they also can be used for images， and here the application is fairly straightforward。

 given an image， we basically divide the image up into patches。

 project each of those patches separately into a vector。

 those vectors then get passed as inputs to our transformer。

 and then the output gives us one output from the transformer for every patch in the input now if you want to do something like a classification score。

 do a classification problem then you do a pooling operation on all the vectors coming out of the transformer and have a linear layer that predict your class scores。

So that's then the same architecture of a transformer can be applied both to a language and to images and to a lot of other things as well。

 I mentioned there have been a couple minor tweaks to transformers since they were first introduced but we're running out of time so I'll just leave those as extra reading So kind of the summary of where we get to at the end of this lecture is basically two things that I promise at the beginning one is that we introduced attention which is this new primitive that lets us operate on sets of vectors it's highly parallelizzable。

 it's basically just a couple matrix multiplies so it's highly scalable， highly parallelizzable。

 highly flexible， can be applied in a lot of different situations and the transformer which is now a neural network architecture that uses self-attention as it main computational primitive and the transformer is basically the neural network architecture that every application in deep learning is using these days so that's super powerful super interesting super exciting transformers have been with us for like eight years now and I don't see them really dying any time。

 so that's， pretty exciting。So that's basically it for today's lecture。

 and then next time we'll come back and talk about some new tasks， detection， segmentation。

 visualization and see how we can use these architectures to do new cool things。😊。



![](img/1fdc141c64e1dc4a50bf654efb636e7b_4.png)