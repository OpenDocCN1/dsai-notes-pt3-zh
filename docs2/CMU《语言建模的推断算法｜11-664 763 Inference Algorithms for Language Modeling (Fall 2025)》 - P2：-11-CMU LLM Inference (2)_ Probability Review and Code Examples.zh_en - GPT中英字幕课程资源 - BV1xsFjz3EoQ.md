# CMU《语言建模的推断算法｜11-664 763 Inference Algorithms for Language Modeling (Fall 2025)》 - P2：-11-CMU LLM Inference (2)_ Probability Review and Code Examples.zh_en - GPT中英字幕课程资源 - BV1xsFjz3EoQ

Okay hellello everyone I'd like to get started so the first thing I'd like to point out is on the class schedule until two minutes ago there was nothing for this lecture now there is something for this lecture so you can you can go here it has the code link here and this time I'm not going to be going through slides I'm going to be going through like demonstrating some stuff in a Ju putter notebook so there's no slides link for today but you can click through and run it yourself。

The reason why I want to do this is I want to show like a very minimal example of some of the like algorithms that we're going to be using this time to set everything up so that you can use it properly。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_1.png)

嗯。So I oh yeah and actually before that let me do some logistics announcements。

 which is number one starting next week we will have office hours。

 the Ts are and I are arranging everything but that will be host on Piazza all of the class videos will try to post on Piazza as soon as we can。

The homework is not out yet， but it will homework one will be out soon any any other questions have people had about general logistics things。

Or a wheel set。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_3.png)

Okay。Cool， so let me go ahead with this。嗯。And so some of this may be。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_5.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_6.png)

Some of this may be relatively elementary to everyone， but to some people。

 but one thing I've noticed is that actually a lot of these concepts are not know as universally held as I may originally thought so I just want to make sure that we get everybody on the same page。

And so today is a four part is in four parts， the first thing I want to talk about is some probability fundamentals。

And these are going to go into like basically everything we do So we'll talk about that first the second thing I'm going to do is just going to show a very basic implementation of a transformer model again I assume that most people have dealt with this before。

 but this implementation may also be useful if you want to try it out in future work so I'll just go through it quickly and then after that I want to show some generation algorithms and how we can evaluate models using language models as a judge and then finally I want to talk a little bit about metageneration algorithms which are like reranking algorithms that allow you to pick the best output。

And not everything's in the code， I'm going to go off track a little bit some of the time and also please feel free to ask any questions。

嗯。So yeah， let's get started。So the first thing that I want to talk about is probability fundamentals and so I'm going to go through some basic concepts and I would definitely encourage you to go walk along with the code。

 you can run it locally if you click opening CoLab you can run it on CoLab but you'll have to like copy paste in the library files so it might not be super convenient。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_8.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_9.png)

The first thing we do is just set up our environment with torch andump and Maplot lab and import everything。

 so this is not interesting。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_11.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_12.png)

嗯。So the first thing I want to talk about is conditional probabilities and the reason why I want to talk about conditional probabilities is because we are dealing with autoregressive language models。

 mostly in autoregressive language models are based on conditional probabilities where we predict the probability of the next token。

嗯。Have people learned of any variety of language models other than transformers？Yes。😊。

Okay word embeddings word embeddings so that's a good point is word embedding a language model？

According to our definition last week。Anyone remember what the definition of a English model last week was？

It's not a fair question yet。Right essentially make one specific token。

 given like the token that you ready yeah， model that predicts the next token。

 given the previous token。 yes， that's specifically an autoregressive language model。

 So if we go even broader。It's a model that。Yeah， gender。That generates text， yes。

It should have the ability to generate text， that's actually not how I defined it on Tuesday though。

Yeah， generic sequences of tokens sequences of tokens yes。

 but that's also not how I define it less to say yes assigning probability sequences so and then specifically autoregressive models assign probabilities to sequences by predicting the next token and so when we predict the next token that's a conditional probability。

 it's the probability of the next the next token given all of the previous tokens or you know the probability of y given x where x is x is the previous tokens。

😊，So now going back to the question， is word tove a language model？If so， yes， if not， why not？

Any ideas， who knows where to to back， by the way？😀呵。😊，Maybe not everybody is yeah。ItYeah。

 so word to for people who aren't familiar， I can draw it quickly on the board Basically it's it's a way of learning embeddings for Protokens but。

What it does is Word to that's actually a software toolkit it's not a any individual method it's either of two methods where basically。

Based on the surrounding tokens。You're predicting the tokens in the center or based on the token in the center you're predicting the surrounding tokens and then you use that to learn you use that to learn embeddings。

 but this actually violates the principle of going from left to right and so it can't be an autoregressive model and。

If you work really， really hard， you can kind of turn it into a language model that actually predicts the probability of sequences。

 but it's like。Not designed for that purpose。so any other ideas， bird is also similar， by the way。

 bird is a it's called a mass language model， but it's actually really hard to get it to assign out probability sequences。

Any others yeah？Diffusion models， yes， very good， but that's not the one I'm looking for。

Recurrent neural networks。 Yeah， that's a very good one。

 Did anyone take a kind of old school NLP class。What did you learn as language models here？BM 25。

 BM 25 is more of a， await thing。Yeah， Ngra models。 Yeah， there we go。

 So Ngra models are are maybe not not taught so widely anymore。

 but they're a good illustrative model that we can we can work with And Ngra model。

 basically what it is is it predicts the next the next word based on the previous n minus one words and。

😊，嗯 the。In this particular case， I set up a bigram model， which is a two gra。

 so it predicts the next word based on the previous one word。

 the next word based on the previous one word。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_14.png)

I came up with a fake and grim model where I just kind of assigned probabilities to this very small vocab of beginning of sentence the cat dog park mat at ran walked played on in too quickly slowly and end of sentence symbol。

I or more accurately Claude came up with these probabilities for each of the tokens here。

 so given the beginning of the sentence。What is the next possible word like the catat dog park？

Given the what is the next possible word cat dog park， et cetera， et cetera。

 And so this definitely satisfies this this equation here， but it。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_16.png)

Also， additionally， who mentioned the Markov assumption last time， yeah。

 so this has a Markov assumption， which means that we are only paying attention to a certain number of previous words and so we're basically lopping off everything except the immediately previous word and just ignoring it and only conditioning of previous word。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_18.png)

So。What this gives us is this gives us a set of conditional probabilities that look a bit like this。

 And so given S， given the previous word was S， you know， we can predict any of these words。

 Given that the previous word was the， we can predict any of these words， any of these nouns。

 Given that the previous word was cat， we could predict things like sat Ra walked played， et cetera。

 et cetera。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_20.png)

So we're not actually going to use any of these models。

 I'm just using them here because they're very fast to calculate and easy for illustrative purposes。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_22.png)

But there we are。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_24.png)

Any questions sir？Who's actually like implemented or used an Ngram model in a class？Wow， I feel 2025。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_26.png)

Exciting， exciting to see the change this was like the staple five years ago， I think so cool， Okay。

 so now I want to talk about sampling from language levels。

 So this is the most simple inference algorithm that we're going to use。 It's also very。😊。

A very special inference algorithm， which I'm going to talk about in a second。

And so basically the way we sample from a language model is we start from the beginning token and use the conditional probabilities to sample the next word。

 update the current context and repeat， and then we continue until we reach an end token or maximum length。

And so this is like what we do in every autoregressive language model。

 It's the same for transformers。 The only difference is。Here for updating the current context。

 we're just remembering the previous word in a transformer model， we run it through many。

 many layers of the transformer model and like append the the embeddings to the Kv cache and all the other things。

 So， but the overall you know， way of implementing this is the same。

 So what we do is we take our vocabulary we get a list of all of the he's in the vocabulary。

 and we start our sequence with just the beginning of sentence。 So。😊。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_28.png)

Said that as our our current index。 and then we step through until we get to a max length。

 Then actually， this max length is important when you're using， you know， any sort of like。

Neural network or deep learning based language model。

 because it may go on forever if you're not careful so you kind of need to set this so you don't run out of memory。

嗯。So I'll get to temperature or no I'll explain temperature now。

 So we're going to talk about a lot of different sampling algorithms。

 temperatureer sampling is a very common one that we use and basically the idea behind temperature sampling is that we want to。

We might want to make the distribution more peaky or less peaky so that we get more higher probability outputs or lower probability outputs。

And so in a mathematical equation。In a mathematical equation， what we do is。We take the probability。

Of I and so typically。Typically if we have a probability。The all this will add up to one。

Because it's a probability and probabilities need to add up to one。

And so the sum is just one so we don't need to worry about it so the probability of I is the probability of I right so typically we could just cancel this out。

 but what we do what we do when we have the temperature。也属于。Make an adjustment。Where we take。你。

To the log probability。我系。E to the what probability of J。

And then we multiply it by one divided by the number。

And so what does this mean when the temperature is one？Any ideas？对。Yeah， nothing happens。

 It's a no op because you， you get one over one， this is one。

 and then Ian log cancel out and we get we get the same thing we went before it。

What does this mean when we set the temperature to be。Infinity。话通时翻你惊家为都咩。

All of the values will become one and so what that means is what if our vocabulary size is 1000？Yeah。

 each of them will have one by 100， so it gives us a uniform probability distribution。

What if we set this to zero？For the probability。It might be undefined in infinity。

 but what's the limit is it approaches infinity。关。好。There's only one single probable word。

 so basically what happens is the largest。The largest token becomes infinitely larger than all of the other tokens。

Because it's exponential because it's multiplied and then expd。

 So basically like what that means is you get a one hot vector。嗯。Where a single word。

A single actually， I'm may worded token， but let's just say token where a single token it's a probability of one and all of the other ones going probability you zero so you'll always pick the most probable token slight caveat。

 if few tokens have exactly the same probability， then you would get a uniform distribution over all of the most probable tokens。

 but basically it is you pick the most probable token。So that's what we're doing here。

 we're basically taking the log of the probabilities， we're dividing it by the temperature。

 and then we're taking the softm and the softm is basically expeditiating in the normal license。

 so that's what we do here。So once we've done this， we then sample the next token。

 So if we're not taking the temperature， we sample it according to the original probability distribution。

 if we。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_30.png)

If we do take the temperature， we sample it according to the adjusted probability distribution。

 we append this as the next word to the sequence and we continue until we hit the end of end of sequence token。

Good。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_32.png)

Great， so let's try it out。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_34.png)

I'm just sampling some outputs from the model。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_36.png)

And my model gave us the dog played the cat played quickly。 the dog played in the park qua。

 So I don't know if anybody's sort of a garden path sentence。

 but this feels like a garden path sentence here。 It's one of those sentences that kind of seems to make sense until you the last word。

 and it doesn't make any sense at all。 But basically。

 the reason why we use big transformers is because vi models like this are really bad models of language So they give you lots of like very unnatural things。

 So， but anyway， like this is we can generate something that vaguely looks like English in this way。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_38.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_39.png)

So anyway， we going to use this model， we're not going to use this model to do anything。

 it's mainly for demonstration purposes。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_41.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_42.png)

And the next demonstration that I would like to make is how we estimate quantities through sampling。

嗯。And the basic idea is here we have a true conditional probability of the next word。

 given the current word， so we know this according to our bygram model。

But what if I said I wanted the joint probability of two words co occurring here？

And so the joint probability would be。Not。呃。Not the conditional probability were we divided by P of X。

 but just the thing on top of this so just like what's the probability that these two words。

 if you looked at any two arbitrary words that the first word would be X in the next word。

So does anyone have a good way to calculate this？

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_44.png)

Could you write a program that solves for this value by taking in this big matrix？有。

Or is the probability of not operating and is the probability of photo is not available to get。

The the probability of both words not occurring together， Yeah I mean， if you could get that。

 you could get you could maybe use that to find this。But basically， long story short。

 coming up with an analytical solution to this is maybe possible， but it's hard like there's。

 it's not very easy to。Take these conditional probabilities and come up with a system of equations that would allow you to come up with a joint probability。

 and it becomes even more impossible when you start talking about like finding this joint probability for a transformer based model。

 you just wouldn't be able to do it， right。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_46.png)

So what we do instead is we can actually estimate quantities through sampling。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_48.png)

And so what we can do is we can generate a whole bunch of sentences with the model using our sampling algorithm and estimate this like estimate this unknown quantity。

 this probability of the two。So。Why is why is this useful。

 this is useful for a very large number of reasons， it can be useful for， for example。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_50.png)

Let's say you have a transformer based bottle where you can calculate conditional probabilities。

 and you want to know what percentage of the time it generates toxic content。

So there's no analytical solution where you throw in your you know transformer and where you throw in your transformer and like say。

 okay。Now run the system of equations and tell me how much toxic content there is。

 but what you can do is you can sample a million outputs and see what percentage of them are toxic and so that gives you the expected number of like toxic outputs that it would generate given a particular prompt or something like this。

But we're going to do something a little bit more boring。

 which is just you know estimating the joint probability of any two tokens in a sequence and so what we have here is we have our bigram count。

 we have the total bigrams， we sample a certain number of sequences and based on this we find the current index in the next index and we just add to the bygram count and the total number of bigrams。

And then when we're done， we divide the bygram counts by the total number of bygrams。

 and that gives us the joint probability of having these two in a sequence。嗯。And。So let's run that。

 I also have a function to estimate conditional probabilities from sequences。

 But this is a little bit。Like uninteresting at this point because we already know the conditional probabilities。

 So why do we need to you know estimate them from sequences， So we'll do that later。嗯。

So what I want to do now。Oh， actually， sorry， no， I am going to demonstrate that we're going to estimate conditional probabilities from sequences。

 And the reason why is because the more we sample， the better our estimates become。

 And so if we sample more and more outputs， our estimates are going to become more and more accurate。

 and I want to demonstrate this by looking at the if the conditional probabilitybabilities that we estimate by counting up all of the bigrams and then dividing by the number of times we saw a previous word and comparing that with the true conditional probabilitybabilities that we know because we know this is a bigram models。

 So yeah， sorry， actually maybe just to rewind a little bit。

 the way we can estimate a conditional probability from a sequence is we look at the current I。

 we look at the next I， we calculate the bygram count we calculate the count of the first word in that bygram and then we can calculate the conditional probability by dividing the bigram count with with the current word count。

 So basically。Calculate this without the like x in the bottom。

So let's do this and we're going to calculate the bigram counts or the conditional probabilities for cat。

 given the satAT， given cat， the given on and on given satAT。

And I won't go through like all of this code here because it's a little bit a little bit involved。

 but。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_52.png)

Let's run this。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_54.png)

And what we can see is if we sample 100 outputs， the actual condition conditional probability of on given the is 0。

5， and we happened to get it like exactly right when we sampled only 100 outputs。

 but all of the other ones， we actually got zero we got 0% probability for like satAT given on。

 for instance。 So basically if we only sampled 100 examples。

 we got a really bad estimate of many of these of many of these。

 But then if we scaled up to like 500 or 1000 or 500010000 50000。Sorry， wait。100。sorry，1050100，500。

1000，5000，10000。 We can see that gradually， like our estimates are converging to the actual value that we know is correct。

 And so like the more we sample the better estimates we get。

And this is like looking at all of the outputs， how much does our error converge after we sample that any。

This somehow on。Great question。 So the question was， does this somehow depend on the temperature。

 Does anyone have an idea about whether this depends on the temperature。I'm going to show you a plot。

 but yeah。It's。That's more impressed。Yeah， it does。

 And the answer is it depends on the temperature because the temperature modifies the probability。

 So yes， that's absolutely correct and。The actual answer is one is a very special temperature。

 It's the only temperature that gives you the true probability distribution。

 And it's actually the only temperature where you can like。😊，Where。

 where you can accurately sample from the joint distribution， according to that temperature。

 all kinds of other things。 So if you sample with a probability of one。

 you're actually guaranteed to get an unbiased if sample from the conditional probability or sorry from the joint probability distribution that you can get from the conditional probability distribution。

 So I don't have the autoregressive。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_56.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_57.png)

Equation up here， but basically like if you multiply all these together。

 you get the joint distribution of all of the tokens of the sequence， right so。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_59.png)

Yeah， if you don't use one， if you don't use one， you get it incorrect。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_61.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_62.png)

Cool， and then these are the final estimated conditional probabilities。

 we'd have to scroll up to compare them to the real conditional probabilities。

 but like as you sample more you're going to get this closer and closer to the actual distribution。

So。This is important for a number of reasons， any questions here？

This is also important for model training， Anyone know why this is important for model training？

Any ideas。dont regrets like。一都扛过去。Prevent evil contentence it's not the answer I was looking for。

 but maybe that。Yeah， I。是个。嗯，对。Yeah so basically if we want to so the answer was if we want to match the true probability distribution of like text on the internet we just need to sample an infinite amount of text on the internet and we'll get unbiased sample of you know of the text。

 I mean what does unbiased mean here， you know depending on what sites you download and stuff like that you might not be able to get like all of the words that people have ever said but you can get pretty close with the internet but the other implication is if you have a small sample it is it's not going to be able to give you a good estimate of what all the text on the internet looks like so when you train on only a small sample of data you're going to risk overfitting another stuff like that so it all boils down to basically this。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_64.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_65.png)

So。Yeah， so then the next thing I want to talk about is marginalization。

 which is summing over variables and。This is also important and we're going to be talking about it a lot in our metagen section。

 but。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_67.png)

So can somebody。I kind of actually already said the answer。

 so marginalization is basically taking the sum， for example。

 taking the sum over y and predicting the probability of x or taking the sum over x and predicting the probability of y。

 Does anyone know why it's called marginalization， by the way。Anyone heard of this reports？



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_69.png)

Yeah， exactly。 You write the sum in the margin of the table。 So what。

 if this is a table of all of the probabilities， actually， this is a conditional probability。

 So it's not not as interesting。 But if you have the joint， the table of the joint probabilities。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_71.png)

You would write the sum in the margin over here， because it would be the sum of all of the。

Like values in the row or all of the values in the column so that's where the word came from。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_73.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_74.png)

Great， okay， so the way we do this is not that tricky basically in Pytorch， it's a single call。

 we just sum over the dimension like dimension one or dimension zero。

And we estimated the joint probabilities from the sequence。

 so we're going to base this on the joint probabilities and actually I have the joint probabilities here and you can see that the marginal probability of this being the current word is this so the highest the highest probability current word is the start of sentence symbol the sentence symbol can never be the next word so it's probability is zero and then we have like different values and we got all of this without me not you know ever being able to calculate this directly or analytically because we can sample and we can calculate these six。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_76.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_77.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_78.png)

Okay， so。In particular， why I wanted to talk about marginalization is I want to talk about latent yeah。

 sorry。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_80.png)

嗯。my to。Sure。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_82.png)

In this as we increase a number of sequences see that that point of given that I mean we have say just0100000 sequences or something that' error convergence that so this should go to zero like if you sample infinitely because we're sampling in an unbiased manner and we're just calculating counts so this error should should go to zero if I did were like you want to you want to try。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_84.png)

But。Let's make my laptop a little bit hotter。They might need to change。😔，O。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_86.png)

Maybe this will just work。My sampling is also not optimized。

 I am using very inefficient inference algorithms of Python4 loops so。

I would suggest you use an optimized implementation if you try this， they actually try this。😊。

So yeah， while that's working， maybe I will I will go on the next part so。😊。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_88.png)

Lant variables。 So this is hidden structure like hidden variables that are not maybe necessarily the input that you have or the output that you care about。

 but somehow you know have an effect on the final output。 So you'd like to include them。

So there's a really common variety of latent variable that we use in language models nowadays anybody。

Have an idea of what this might be off the top of your head and this needs to be a probabilistic variable。

 so it's not like the hidden embeddings or something like that。It's very， very popular as about。

12 months ago。9 months ago。What's a big trend in language models nowadays？

In the reasoning yes reasoning so recently a big trend in language modelss is reasoning models and basically what reasoning models do is they have a long they have a chain of thought or a long chain of thought that they use before giving you the final answer with the hope that adding this chain of thought will improve the overall quality of the final answer。

And so here x is the first word sorry， x would be like your input prompt。

Z would be the reasoning price of a reasoning model and why would be the final answer that you would be providing so。

That's one example， there are other examples， but this is definitely the most prominent example that it is。

And so the idea is。If you calculate。So let's say we have a model that has no chain of thought or no reasoning whatsoever。

It would be calculating。Just the conditional probability of the answer。A model with chain of thought。

Might generate might generate。The chain of thought and then generate the answer。

 so this is calculating the joint probability of the chain of thought and then the answer。

And let's say we don't care about the shade of thought and we just throw it away but we can actually sample lots and lots of them so this is a method called self consistency that's used pretty widely and we're also going to talk about minimum based risk which is kind of similar to self consistency in a way。

And what that means。This you do。嗯。So you sample you sample the chain of thought and you actually like I could have just used that this one。

 and then you over some over all of the samples that you've got and this gives you an estimate of P ofI given act。

And it's an estimate of P of the x。And this， this is， you know， similar to predicting directly。

 But because the probability of why gets more accurate by adding this reasoning。

 you actually get a better estimate and you get better better results when you do this。

 So we're going to talk a lot more about this。 But this is like the connection to modern language models。

 But here I'm going to focus on kind of the。喂。I' just focusing on like the basic idea of this。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_90.png)

And actually， this just finished。It's not converging as fast as I thought it would be。

 but you can see it definitely went down from where it was before。啊。Yeah。

 I'm almost a little bit worried I have a bug in my code so I need to go back and double check that。

 but this should eventually approach zero。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_92.png)

嗯。So， yeah。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_94.png)

And so like in this particular。Example， you know we could we could generate and we could say the first word is x。

 the last word is y， and then all the words in the middle are the latent variables。

 So that's kind of like what we do with chain of thought。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_96.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_97.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_98.png)

Just in the interest of finishing everything， so just to go back to the point about temperature and bias estimates。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_100.png)

So this is what temperature sampling looks like。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_102.png)

And so like let's run with temperature sampling。The same experiment that I ran before。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_104.png)

And basically what we can see is that if we sample from a model where temperature is one。

 this gives us an unbiased estimate of what the actual conditional probabilities are。

 and so our error goes down and down and down and down。

 but if we're sampling from a biased estimate of what the probability is then this indeed will plateau and this will not give us a correct estimate of what that output of the model will look like。

So。Why is this important， this is important because almost nobody does this。

 this temperature sampling of one， like you some language models enforce it。

 like I think 01 like the open AI reasoning models enforce temperature of one and you're not allowed to do other temperatures。

 but a lot of models for various reasons which I'm going to talk about in a second， use like。

Use this。 And actually， if we go even more extreme and we say we're going to set the temperature to 0。

 we're going to do greedy。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_106.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_107.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_108.png)

We're going to do this greedy， let's see。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_110.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_111.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_112.png)

But my my code was not robust to sample from from 0。 But like if you did greedy。

 it would be even more biased。 So like， what does this。😊。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_114.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_115.png)

What this means is unless we're sampling with the temperature of one。

 we're not getting like the actual language models like model of language， right。

 we're getting something that's like a bias distribution that the model isn't actually generating。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_117.png)

嗯。Cool， so like， let's say。Then the question is like， why do we want to do inference。

 We actually had a question about this last time， but one reason why we might want to do inference is to get good outputs。

 in which case， you know， we want to use any inference algorithm that will give us the best outputs by whatever definition of good we have the other reason could be we actually want to understand the qualities of the language model。

 And if we do， then。Basically， sampling with the temperature of one is the only way to get the true distribution of the model。

 so that's a good thing to remember。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_119.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_120.png)

Okay， that's the first part are there any questions about that yeah？没有你。就是 basic。

Is there any use case where you set the temperature to greater than one？I have。

Almost never seen this， I've seen this like a little bit。

 but almost never and actually I think you might see the reason why in the in the slide or in the notebook after the one that I'm going to talk about。

 but usually one is in the upper limit of what people said。😊，Yes。

 temperature of one gives con just depends by every user within virtual systems。Yeah， that's great。

 why don't I show the next notebook and then get there cool so。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_122.png)

I actually don't know if I'll really go through this。

 I'm kind of assuming you know everybody has either taken NLP or deep learning or something。

 So this is just a transformer model。 The nice thing about this transformer model is that it's very。

 very simple there's like 2002000 lines of code in the huggingface transformers implementation of G2 and this one has like a couple hundred but yeah。

 it's basically the GT2 model the few things that I think would be like particularly interesting to take a look at are how big is this model So G2 small。

 basically it had a vocab of 5000 it had 12 layers。

 12 heads and an embedding size of 768 This had 24 layers，16 heads embedding size of 1024。

And then large had 36 layers，20 heads embedding size of 1280s。

 So this is approximately like 10 x smaller than the the models that we use nowadays for most of these dimensions。

Except maybe layers， the size here is。Cool， so let's go on the generation part。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_124.png)

And so here in the generation what I want to do is I want to do two things。

 I want to get like a qualitative idea of what the output looks like when we sample at different temperatures to answer like some of the questions that we just had now and then separately from there I want to demonstrate how we can do like some very rudimentary evaluation and this is not like you know the gold standard way of doing evaluation of language model outputs。

 but it'll give you an idea in like a starting place where you can start until we get to the gold standard ways so。

Here are temperature values， so zero is greedy sampling， it's deterministic。

 it should always give you the same result。A temperature of 0。

5 is kind of a more conservative variety of sampling and it will focus on things that kind of have high probabilities one is you know the only true sampling number and then 1。

5 is creative sampling more diverse outputs so let's go ahead and initialize that。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_126.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_127.png)

One thing I will notice is I kind of cheated here and I'm using an API key。

 so I'm like actually asking Quaude to evaluate my results for me。

 but all the generations are going to be from my model。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_129.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_130.png)

Oh and by the way， I'm going to try to get everybody number one。

 I'm going to try to get everybody like credits that you can use on API based language models。

 everybody will get $50 so it's not it's not a lot。

 but it should be enough for like these language models as a judge sell things and we want everybody to sign up for AWS if you haven't already with your Andrew ID and tell us your AWS number and we have a quiz that you created already。

okay the quiz will be with the one today， so please try to add your add your number there and I'll try to get you AWS card as soon as possible。

 but back to the normally scheduled programming I'll do temperature sampling and this time we're doing it with GP2 so it'll give us like actual like somewhat reasonable looking results。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_132.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_133.png)

Oh， other one small thing that I probably should mention。Is within this。

Oh actually maybe it's not here， but if you're using a map。

 I would definitely recommend that you use the map Mac accelerator。

 I think like most people have Macs here and if you have the apple silicon that makes it a lot faster so there's an example of that in this notebook。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_135.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_136.png)

嗯，过。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_138.png)

So， here are the。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_140.png)

Here are the texts and I'm going to generate。Based on a prompt。

 the future of artificial intelligence is。And I'm generating three from each of these outputs。

 so basically doing inference three times for each。So if we look at greedy here。

It gives us the same answer always， and it says the future of artificial intelligence is uncertain period。

 we're not sure what the future will look like， said Dr。 Michael S。 Schidfeld。

 who I don't know if that's a real person or not， but given I think it might I think it might be。

 given that this is great E deco codingding and it's probably not going be too creative。

 but but yeah。Then for this one down here。Oh， actually，1， one piece of。

Knowledge about greedy decoding that I should say here before it drives you crazy is when you do greedy decoding。

 will you always get the same result？I got the same result three times。Yes。😊，Yeah， no， sorry。

 you will not always get the same result and there's a reason for it。

Does anyone know the reason for why you might call like GPT40 or a clode or something like that with a temperature of zero and get different results？

是是 kind of。Because you're still sampling for the probabilities and not the actual values。

 what do you mean by the probabilities？W to adventure of the nextN market。decided side it that sound。

We said so actually when you switch it to zero， it's mostly just picking the highest scoring ones。

 so specifically in the case of zero， you'll be picking the arc。Yeah。

Floating point errors can propagate， yes， so this is very， very very， very tricky。

 but it has to do with the hardware that all of these models are running on and basically all these models are running on GPUs and what's the characteristic of GPUs。

They have lots of。Lots of threats， right that are all running at the same time。

 And so there there's two ways you can do a sum on a GPU。 One way you can do a sum。Is。You say。Okay。

 thread one， let's say we have 16 threads。 threadread one， you calculated one。

 so you get to go first， threadread2， you calculated two， so you get to go first， threadread3。

 you calculated three， so you get to go first， and then you just add them all in order But the problem is if you do this。

 you you have a whole lot of locks and like some threads might finish a little bit faster than others just due to how hot the GP was or whether it had a good day yesterday or things like this。

 And so。If you add all these locks， it hurts your efficiency a whole lot。Theoretically。

 you could turn on determinism on GPUs and make things go all in order。 But in reality。

 none of the people serving things on GPs does this。 So what happens instead is。

thread7 finishes a little bit faster， so thread7 gets to go first and then thread two finishes。

And so thread two gets to go next and then thread one finishes and then thread three finishes。

 And so the addition happens in a different order every time， just based on like。Well。

 nothing is random， but mostly mostly random factors。 And so because of this。

 if you combine this with the fact that。The very small floating point numbers。

 depending on the order you add them will round differently。

 This can cause very small differences when you run。 And so these differences are are really。

 really tiny， but you have something like an argm， when you select a vocabulary item。

 So if the maximum vocabulary item changes just once in your like 1000 token generated sequence。

 then it will change everything that happened after that。

 So you only need a very tiny difference caused by these floating point errors to throw things off。

 And so you'll notice if you run like something with clod， you'll get it the same like five times。

 but then you'll get a different once or something like this。

This is compounded further by two things。 The first thing is mixture of experts。

 And so mixture of experts are a very popular thing。 We'll talk about them a little bit。

 But basically， you're choosing which parts of the network to use。 So now。

 instead of having an arcm over just the token， you also have an arc max over the experts。

 So you have like many， many more arcmes。And then let's say you're running an agent or something like that like a coding agent now you don't just have one prediction you have many。

 many predictions so like when we were trying to reproduce our coding agent results with Claude。

 we would never be able to get same results on the same even on the same instance with like greedy simply I'm wondering if there's because there's still this randomness even though it's very small whether or not that corresponds to。

What temperature would like period， whether or not it's。It's set to zero。

 but because of these hardware quas is actually more closer to like a number than single point0 point or something anyone has ever tried to measure that that's a great idea just to repeat it's like what is the empirical temperature。

Despite the fact that your set temperature is zero。

 what's the actual temperature that you're getting and I don't know the answer。Yeah it was。

Exceent you by also using multiple instances which you can use。

Does it get compound by using multiple instances of GPUs yeah it depends where you aggregate。

 but like if you know one GPU is more likely to have the larger difference than the threads within the GPU so it certainly would。

对对。Does quantization make the problem worse， yeah， well because you'll have more rounding errorss。

kindThen you use this behavior to infer what kind of quantization it's using so basically you want to like uncover what quantization open AI is using or something like that good idea please do that give i'll give you an a+ on the project if you can demonstrate that。

Or prove that I'll give a high bar。Cool okay so now let's go to the temperature 0。

5 so the future of artificial intelligence is in question if you're a software developer and you are looking for a new way to create and deploy applications clear in the future of the world is bright the future is bright the future is bright very bright it's a lot like the future of computers I'm not sure what the word intelligence。

And then for one， you have like largely up in the air many eagerly await and think。

 seen Joawwi's creation， expect to see everyone around be clear autoomicon 2017。

 the future of artificial intelligence is clear Facebook just poppedpped up。

Going to be very interesting it will change the way we think and treat people the future of artificial and then going up above temperature of one。

😊，The future of artificial intelligence clashing across league allies and designer gangs the circuit feared the wling bastard Benalier。

So maybe this is kind of your answer why we don't use a temperature larger than one it just kind of goes off the rails so so then the question is we looked at this and we kind of like had an idea what was going on here from our you know own qualitative qualitative analysis but we can't do this all the time right like I couldn't do this very well in Chinese for sure and you know I couldn't look at thousands thousands of examples and so you can run this。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_142.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_143.png)

And so what I want to do next is I want to actually like evaluate the outputs and see how good they are。

And。There's a number of ways to do this like I mentioned before on Tuesday。

 so the first way you can do this is you can use some sort of deterministic metrics that you can calculate you know directly from the generated text and for this I'm going to use a diversity metric。

And。So the diversity metric。That I'm going to use here is the ratio of unique words in the set compared to the total number of words。

Oh so sorry， this is the diversity within a single example and then for the cross generation diversity。

 what I'm going to try to do is find the overlap of words or biograms between the two outputs and if there's less overlap than it will be more diverse。

So these are kind of like this is just an example of a deterministic metric you could do。

 You could also measure the length。 you could measure， you know。

 other other varieties of things like this。 but another popular way of evaluating things is using a language model as a judge。

 And so this is。The reason why this is nice is it's like super easy to do super powerful things with this by just asking a language model a question about the output。

 there's a lot of caveats that go into this， which I can talk about a little bit。

 but here I'm just going to show a very simple example。

 which is rate the fluency and coherence of this text on a scale of  zero to 10。

 10 equals perfect only respond with a number，So I'll do this， I'll give it my API key。

And then generate。Co， and then to run the evaluation。

 I'll take all the things that I generated before and run them to calculate this fluency score in the evaluation score。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_145.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_146.png)

So it's evaluating each of these。I didn't for the purpose of simplicity。

 I didn't speed up my alarm calls。 like in reality， if I did this， I'd I'd use kind of。

Many calls in parallel， but I didn't do that at this time， so。

For me throwing this together in like a few minutes。

 I think the results actually were pretty interesting。

 which was we measured fluency of the greedy decod text and the fluency of the greedy decod text got a score of 5。

3， which I think is not that bad。But the diversity was relatively low because basically it all of them were the same and then the diversity got higher and higher as we had more and more outputs but the fluency went down。

So this is a very common issue， which is like as you sample more diverse things。

 the quality goes down。And temperature sampling is particularly well known for this。

 There's a lot of other methods that we're going to talk about next class， that are。

Kind of Peretto optimal with respect to diversity and quality so you can get like better diversity and better quality。

 better diversity and better quality than temperature sampling。Cool。Any questions here？Okay。

 one caveat I'd like to give about language models as judges is don't trust them blindly languageage models are very bad judges for a lot of things and they're particularly bad at things and judging things where they themselves are not good at them so if a language model is not good at solving math problems it'll also be a generally be a bad judge for math problems。

And another thing that people have reported is language model judges like like their own generations more than they like other language models。

 So cloud like really like cloud G or really like g this is not a。Hard and fast rule。

 it's not true all the time， but it is true some of the time， so be aware of that。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_148.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_149.png)

Cool嗯。So the final thing I'd like to talk about is metagen algorithms。

 so this is going to be a big theme of the class and this is the simplest possible metagen algorithm again。

 which is reranking and so what I want to do。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_151.png)

Is I want to rerink。嗯。I want to rera the output of GPT2 small with GPT2 medium。

 and so we have a bigger and stronger model and then the smaller model that generates。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_153.png)

嗯。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_155.png)

So yeah， this is just the code to generate to calculate the probability actually here。

This is the important code if you want to run on like a GPU or or MP。

 but hopefully like people have done this done this before， I'm sure like everybody's run on GPUs。

 but like if you're running just on your Mac， like definitely do this because this will。

Speed it up by a lot for free and like smaller models you can actually run on your own computer。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_157.png)

I'm getting an error。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_159.png)

Why am I getting an error。Okay， maybe I just didn't run that。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_161.png)

不。And so we can generate some outputs and calculate the log probabilities between them。

So while we're waiting for this to finish， this is actually。

A commonly used method in inference where you use a small model to generate an output and then a larger model to like calculate the probability of the output。

 Does anyone know what。The name for this is it's not exactly what we're doing here yet。

Speculative decoding， Yes， so typically in speculative decoding， what you do is you generate。

 you use a small model to generate like 5 tokens or 10 tokens or whatever。

 And then you use the large model until you get to a point where the small model is wrong。

 And the reason why this is good is because like calculating tokens and batches is much faster on GPU。

 So you can save a lot of time doing this。 But we'll talk about that later else。So anyway。

 this is the output and the likelihood so we have the future of artificial intelligence is bright and promising the future of artificial intelligence is banana purple elephant and artificial intelligence will transform many industries and in this case。

 I guess the small model always gave a worse always gave a worse probability than the large ones so that's not like。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_163.png)

Super exciting。 But the more interesting thing is when we actually like use it for reranking。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_165.png)

And so。You get to see which outputs a particular model prefers。

And in the case of a smaller model and a larger model from the same model family。

 it's actually pretty clear it's pretty fun。So here here's the small model。

 here's the text set the small model prefers versus the text set the large model prefers。

 And because I generated from the small model， it will make a lot of sense that the small model will prefer most of these。

 So it's actually more interesting to look at the ones where the medium model prefers it。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_167.png)

So let's look at here。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_169.png)

Okay。So。Actually， there's only one that's kind of boring。This is randomly sampled。

 so I get a different result every time when I did it like earlier I got three， but here's the one。

 the future of artificial intelligence is shaping up in very interesting ways。 in our next issue。

 we examined whether machine learning might be able to produce complex tasks And here the medium model preferred it。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_171.png)

Does anybody notice anything about the difference between that？And in this。1。另好。嗯。Yeah。

 it's really long。 Actually， unfortunately， I'm cutting these off here。 So that's that's not it。 Oh。

 I forgot to mention one other thing。 So this is not the the log probability。

 This is the per per token log probability。 And the reason why I did the per token log probability is that makes it easier to compare longer and shorter things on the same footing。

😊。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_173.png)

Let me， let me see if I can cut off this like stop this dot to dot， dot， dot， dot stuff。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_175.png)

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_176.png)

Too many dad thus。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_178.png)

Yes， I will one second， okay。Andy， actually me let me generate again so we don't。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_180.png)

So you can get some like additional samples。

![](img/9d0c55d03e0484cd6b7591cbd3a8f955_182.png)

But what I meant by which farm？嗯能。Oh the per token log probability。

 So what we saw before when we generated from Quen on Tuesday was like the longer ones tended to have a high like a lower probability。

 They had a larger absolute value of their log probability。

 And so like let's say we wanted to find the output where the medium model preferred it。

More than the small model by the largest margin。So like what and actually hopefully I can do that if we get more than one。

 let me see if this works。Yeah， okay。 so here what I did is I wanted to find the one where the the medium model preferred it by the like most。

And when I do this， I would like to。Had that be relatively independent of how long the actual output is？

Because if the output is really long， the difference is going to be larger just because the magnitude。

 the overall magnitude is larger and so by dividing by the number of tokens we can like normalize for the length yeah。

 sequence level log probability normalized by yeah。So here's a few more examples。

 So the future of artificial intelligence is now back on the forefront of technology。

 believing AI will deny us an advantage over humans for modeling and understanding the human mind。

's a little bit weird。 the future of artificial intelligence is at stake， he warned。

 might there be a tipping point coming。 But while championship golf can ful American。呃。😊，Interesting。

 I think I don't want to read this article， but so like do people notice any difference between this and the ones that I had up here？



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_184.png)

Like still in its infancy， the full attention of expert scientific communities depends on in intelligent machines。

 driven both by the goals that saw the current scientific literature become obsolete and by priorities that reflect redistributive objectives higher education。

So maybe not as clear as I was hoping， but any ideas？No你是因为是个 sense。Simp simpler sentences overall。

 yeah， maybe。What I would say is they have more surprising vocabulary。

 like more surprising vocabulary choices while still being mostly fluent like the the golf kind of threw me for a loop。

 But and like my general my general。Overall， impression of like stronger models in larger models are typically stronger models is that they。

They give a higher probability or they're more likely to generate sentences that are kind of like interesting and surprising while still not being too like off the wall and like just to give an example of this I was trying to test whether deepS or GP5 wrote better essays and I tried several of them and deepSq would always write a great essay it was just kind of like generic and boring whereas if I used GPT5 it would write like and actually like somewhat interesting essay and that's the level we're talking about with our strongest models now and so you know the weaker models will like GPT2 will not not be at that level but still the same general principle like their better model in low vocabulary items low frequency you phenomena。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_186.png)

Other stuff like that。嗯。Cool， yeah。 that's all I had for today。

 Are there things that people would like to discuss around this。Yeah对。You feel like。

Oh what's subjective of what， sorry， could you speak up？哎，好，并不这个不程。

The downstream use case of metageneration is to quality， improve overall quality。

Let let's give an example， like you have a rebraer that's a really strong model that you cannot generate。

 you know， you cannot generate from efficiently。 let's say it's an agent that goes out to。

It's an agent that goes out and confirms information or something like that。

 So it will also be talking about like tool use in the loop of generation and other stuff。

 if that's the case， you。Might not want to run that at generation time but you might be willing to do that to confirm that there's no hallucinations in your text or something and then do that over like five different texts Another thing is selfconsistency is also a variety of metageneration where you generate multiple outputs and then you do majority voting over them so like there's a lot of different varieties of this。

Well， any other things？Yeah， you think the difference that you saw5 is side or on the the difference between deepse and GT5 I think it they're both reasoning models and I love them both reason so I think it's probably more on the training side they' yeah GT5 we not 100% sure what they're doing for inference。



![](img/9d0c55d03e0484cd6b7591cbd3a8f955_188.png)

Cool， okay， thanks everyone， happy to do。