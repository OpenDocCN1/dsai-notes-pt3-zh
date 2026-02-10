# Andrej《让我们构建GPT｜Lets build GPT_ from scratch, in code, spelled out》中英字幕（deepseek - P1 - GPT中英字幕课程资源 - BV1K4LPzLEoA

看种。So by now you have probably heard of Cha GBT， it has taken the world and the AI community by stormm。

And it is a system that allows you to interact with an AI and give it text based tasks。 So。

 for example， we can ask Chat EPT to write us a small Haiku about how important it is that people understand AI。

 and that they can use it to improve the world and make it more prosperous。So when we run this。

Aha knowledge brings prosperity for all to see。 embrace its power。 Okay， not bad。

 And so you could see that Chay P went from left to right and generated all these words sort of sequentially。

Now， I asked it already the exact same prompt a little bit earlier。

 and it generated a slightly different outcome。AI is power to grow， ignoring holds's back。

 learn prosperity waits。So pretty good in both cases and slightly different。

 So you can see that Cha EPT is a probabilistic system。

 and for any one prompt it can give us multiple answers， sort of replying to it。Now。

 this is just one example of a prompt。 People have come up with many， many examples。

 and there are entire websites that index interactions with chahi Bt。

 And so many of them are quite humorous， explainedplain H Tl to me like I'm a dog write Res notes for ch 2。



![](img/bf8e317787d215eeac53dc1b82b1c757_1.png)

Write a note about Elon Musk buying a Twitter。And so on。So as an example。

 please write a break and news article about a leaf falling from a tree。In a shocking turn of events。

 A leaf has fallen from a tree in the local park。 Winess report that the leaf。

 which was previously attachedched to a branch of a tree， detached itself and fell to the ground。

 Very dramatic。So you can see that this is a pretty remarkable system。

 and it is what we call a language model because it models the sequence of words or characters or tokens more generally。

 and it knows how sort of words follow each other in English language。



![](img/bf8e317787d215eeac53dc1b82b1c757_3.png)

And so from its perspective， what it is doing is it is completing the sequence。

 So I give it the start of a sequence， and it completes the sequence with the outcome。

 And so it's a language model in that sense。Now， I would like to focus on the under the of under the hood components of what makes chat G work。

So what is the neural network under the hood that models the sequence of these words。



![](img/bf8e317787d215eeac53dc1b82b1c757_5.png)

And that comes from this paper called Attention is All You need。 In 2017， a landmark paper。

 a landmark paper and AI that produced an proposed the transformer architecture。

So G is short for generally generatively pretrained transformer。

 So Transer is the neural nu that actually does all the heavy lifting under the hood。

 It comes from this paper in 2017。 Now， if you read this paper。

 this reads like a pretty random machine translation paper。

 And that's because I think the authors didn't fully anticipate the impact that the transformer would have on the field。

 and this architecture that they produced in the context of machine translation In their case。

 actually ended up taking over the rest of AI in the next five years after。

 And so this architecture with minor changes， was copy paste it into a huge amount of applications in AI in more recent years。

 And that includes at the core of chat G。Now we are not going to。

 what I'd like to do now is I'd like to build out something like Chat ET。



![](img/bf8e317787d215eeac53dc1b82b1c757_7.png)

But we're not going to be able to， of course， reproduce Chagi Bt。

 This is a very serious production grade system。 It is trained on a good chunk of internet。

 And then there's a lot of pretrain and fine tuning stages to it。 And so it's very complicated。

 What I'd like to focus on is just to train a transformer based language model。 And in our case。

 it's going to be a character level。A languageage model。

 I still think that is very educational with respect to how these systems work。

So I don't want to train on the chunk of internet。 We need a smaller data set。In this case。

 I propose that we work with my favorite toy dataset set。 It's called tiny Shakespeare。

 And what it is is basically， it's a concatenation of all of the works of Shakespeare。

 In my understanding。 And so this is all of Shakespeare in a single file。 This file is about 1 MBby。

And it's just all of Shakespeare。And what we are going to do now is we're going to basically model how these characters follow each other。

 So， for example， given a chunk of these characters like this。

Given some context of characters in the past， the transformer neural network will look at the characters that I've highlighted and is going to predict that G is likely to come next in the sequence。

 And it's going to do that because we're going to train that transformer on Shakespeare。

 And it's just going to try to produce character sequences that look like this。

And in that process is going to model all the patterns inside this data。



![](img/bf8e317787d215eeac53dc1b82b1c757_9.png)

So once we've trained the system， I'd just like to give you a preview。

 We can generate infinite Shakespeare。 And， of course。

 it's a fake thing that looks kind of like Shakespeare。嗯。

Apologies for theres some ja that I'm not able to resolve in， in here， but。

You can see how this is going character by character。

 And it's kind of like predicting Shakespeare like language。 So verily my Lord。

 the sights have left the， again， the king coming with my curses with precious pale。

 And then Troos says something else， et cetera。 And this is just coming out of the transformer in a very similar manner。

 as it would come out in Chay pt。 In our case， character by character。 In Chay pt。

 It's coming out on the token by token level。 And tokens are these a sort of like a little subward pieces。

 So they're not word level， They're kind of like word chunk level。



![](img/bf8e317787d215eeac53dc1b82b1c757_11.png)

And。Now I've already written this entire code to train these transformers。

And it is in a Github repository that you can find， and it's called a nanoGPT。



![](img/bf8e317787d215eeac53dc1b82b1c757_13.png)

So nanoGPT is a repository that you can find on my GitHub。

 and it's a repository for training transformers on any given text。

And what I think is interesting about it because there's many ways to train transformers。

 but this is a very simple implementation。 So it's just two files of 300 lines of code each one file defineies the GT model。

 the transformer， and one file trains it on some given text dataset set。

And here I'm showing that if you train it on an open webt dataset。

 which is a fairly large dataset set of webp pages， then I reproduce the performance of G2。

 So G2 is an early version of Open AIs G from 2017 if I curl correctly。

 and I've only so far reproduced the smallest 124 million parameter model。

 but basically this is just proving that the code base is correctly arranged。

 and I'm able to load the neural network weights that Open AI has released later。

So you can take a look at the finished code here in nanoGPT。

 but what I would like to do in this lecture is I would like to basically write this repository from scratch。



![](img/bf8e317787d215eeac53dc1b82b1c757_15.png)

So we're going to begin with an empty file， and we are going to define a transformer piece by piece。



![](img/bf8e317787d215eeac53dc1b82b1c757_17.png)

We're going to train it on the tiny Shakespeare dataset set。



![](img/bf8e317787d215eeac53dc1b82b1c757_19.png)

And we'll see how we can then generate infinite Shakespeare。



![](img/bf8e317787d215eeac53dc1b82b1c757_21.png)

And of course， this can copy paste to any arbitrary text data set that you like。

 but my goal really here is to just make you understand and appreciate how under the hood chat ET works。



![](img/bf8e317787d215eeac53dc1b82b1c757_23.png)

And really， all that's required is a proficiency in Python and some basic understanding of calculus and statistics。

 And it would help if you also see my previous videos on the same YouTube channel in particular。

 my make more series where I。Define smaller and simpler neural network language models。

 So multi perceptrons and so on。 it really introduces the language modeling framework。

 And then here in this video， we're going to focus on the transformer neural network itself。



![](img/bf8e317787d215eeac53dc1b82b1c757_25.png)

Okay， so I created a new Google Coab Jupyter notebook here。

And this will allow me to later easily share this code that we're going to develop together with you so you can follow along。

 so this will be in the video description later。Now， here I've just done some preliminaries。

 I downloaded the dataset set， the tiny Shakespeare dataset set at this URL。

 and you can see that it's about a 1 meby file。Then here I open the Ipatat TXD file and just read an all the text of the string。

And we see that we are working with1 million characters， roughly。And the first 1000 characters。

 if we just print them out， are basically what you would expect。

 This is the first 1000 characters of the tiny Shakespeare dataset set， roughly up to here。

So so far so good。 Next， we're going to take this text。

 and the text is a sequence of characters in Python。 So when I call the set constructor on it。

 I'm just going to get the set of all the characters that occur in this text。

And then I call list on that to create a list of those characters instead of just a set so that I have an ordering。

 an arbitrary ordering。And then I sort that。So basically。

 we get just all the characters that occur in the entire data set and they're sorted。Now。

 the number of them is going to be our vocabulary size。

 These are the possible elements of our sequences。And we see that when I print here， the characters。

There's 65 of them in total。 There's a space character， and then all kinds of special characters。

And then capitals and lowercase letters。 So that's our vocabulary。

 And that's the sort of like possible characters that the model can see or emitit。Okay。

 so next we would like to develop some strategy to tokenize the input text。Now。

 when people say tokenized， they mean convert the raw text as a string to some sequence of integers according to some vocabulary of possible elements。

So as an example， here we are going to be building a character level language model。

 so we're simply going to be translating individual characters into integers。

So let me show you a chunk of code that sort does that for us。

So we're building both the encoder and the decoder。

And let me just talk through what's happening here。When we encode an arbitrary text like hi there。

 we're going to receive a list of integers that represents that strain。 So， for example，46，47。

 et cetera。And then we also have the reverse mapping so we can take this list and decode it to get back the exact same string。

So it's really just like a translation to integers and back for arbitrary string。And for us。

 it is done on a character level。Now， the way this was achieved is we just iterate over all the characters here and create a look up table from the character to the integer and vice versa。

 And then to encode some string， we simply translate all the characters individually and to decode it back。

 We use the reverse mapping and concatenate all of it。Now。

 this is only one of many possible encodings or many possible sort of tokenizers。

 and it's a very simple one。 But there's many other schemas that people have come up with in practice。

 So， for example， Google uses a sentence piece。So sentence piece will also encode text into integers。

 but in a different schema and using a different vocabulary。

 and sentence piece is a subword sort of tokenizer。

 And what that means is that you're not encoding entire words。

 but you're not also encoding individual characters。 Its it's a subword unit level。

 And that's usually what's adopted in practice。 For example。

 also open Ai has this library called Tk token that uses a by pair encoding tokenizer。

And that's what G uses。And you can also just encode words into La hell world into a list of integers。



![](img/bf8e317787d215eeac53dc1b82b1c757_27.png)

So as an example， I'm using the Tiktoken library here。I'm getting the encoding for G T 2。

 or that was used for G 2。Instead of just having 65 possible characters or tokens， they have 50。

000 tokens。And so when they encode the exact same string high there。

 we only get a list of three integers， but those integers are not between 0 and 64。

 They are between 0 and 500050256。So basically， you can trade off the codebook size and the sequence length。

So you can have very long sequences of integers with very small vocabularies。

 or you can have a short。Sequences of integers with very large vocabularies。 And so typically。

 people use in practice these subward encodings， but I'd like to keep our tokenizer very simple。

 So we're using character level tokenizer。

![](img/bf8e317787d215eeac53dc1b82b1c757_29.png)

And that means that we have very small code books。 We have very simple encode， and decode functions。

But we do get very long sequences as a result。 But that's the level at which we're going to stick with this lecture because it's the simplest thing。

 Okay， so now that we have an encoder and a decoder effectively a tokenizer。

 we can tokenize the entire training set of Shakespeare。So here's a chunk of code that does that。

And I'm going to start to use the Pytorrch library and specifically the Torjat tensor from the Pytorch library。

So we're going to take all of the text in tiny Shakespeare， encode it。

 and then wrap it into a Torrschdot tensor to get the data tensor。

 So here's what the data tensor looks like When I look at just the first 1000 characters or the 1000 elements of it。

So we see that we have a massive sequence of integers。

 and this sequence of integers here is basically an identical translation of the first 100 characters。

So I believe， for example， that 0 is a nuon character and maybe one is a space， not 100 per sure。

 but from now on， the entire data set of text is rerepresented as just。

 it just stretched out as a single， very large sequence of integers。

Let me do one more thing before we move on here。 I'd like to separate out our data set into a train and a validation split。

So in particular， we're going to take the first 90% of the data set and consider that to be the training data for the transformer。

 and we're going to withhold the last 10% at the end of it to be the validation data。

And this will help us understand to what extent our model is overfitting。

 So we're going to basically hide and keep the validation data on the side。

Because we don't want just a perfect memorization of this exact Shakespeare。

 We want a neural network that sort of creates Shakespeare like text。

 And so it should be fairly likely for it to produce。The actual like， stowed away。

 true Shakespeare text。And so we're going to use this to get a sense of the overfitting。 Okay。

 so now we would like to start plugging these text sequences or integer sequences into the transformer so that it can train and learn those patterns。

Now， the important thing to realize is we're never going to actually feed entire text into transformer all at once that would be computationally very expensive and prohibitive。

So when we actually train a transformer on a lot of these dataset sets。

 we only work with chunks of the dataset， and when we train the transformer。

 we basically sample random little chunks out of the training set and train on just chunks at a time。

And these chunks have basically some kind of a length。And that's a maximum length。Now。

 the maximum length， typically， at least in the code I usually write， is called block size。You can。

 you can find it on the different names like context length or something like that。

 Let's start with the block size of just8。 and let me look at the first trained data characters。

The first block size plus onean characters。 I'll explain why plus one in a second。

So this is the first nine characters in the sequence in the training set。

Now what I'd like to point out is that when you sample a chunk of data like this。

 so say if these nine characters out of the training set。

This actually has multiple examples packed into it。

And that's because all of these characters follow each other。And so what this。

Thing is going to say when we plug it into a transformer。

Is we're going to actually simultaneously train it to make prediction at every one of these positions。

Now， in the， in a chunk of9 characters， there's actually 8 individual examples packed in there。

So there's the example that when  when in the context of 18， 47 likely comes next。

In a context of 18 and 47，56 comes next。In the context of 1847，56，57 can come next and so on。

 So that's the8 individual examples。 Let me actually spell it out with code。

So here's a chunk of code to illustrate。X are the inputs to the transformer。

 It will just be the first block size characterss。Why will be the next block size characters。

 So it's offset by one。And that's because why are the targets for each position in the input。

And then here I'm iterating over all the block size of it。

And the context is always all the characters and X up to T， and including T。

And the target is always the teeth character， but in the targets array Y。So let me just run this。

And basically， it spells out what I said in words。 These are the eight examples hidden in a chunk of9 characters that we sampled from the training set。

I want to mention one more thing。 We train on all the eight examples here with context between one all the way up to context of block size。

And we train on that not just for computational reasons。

 because we happen to have the sequence already or something like that。

 it's not just them for efficiency。It's also done to make the transformer network be used to seeing contexts all the way from as little as one。

 all the way to block size。And we'd like the transformer to be used to seeing everything in。

 And that's going to be useful later during inference， because while we're sampling。

 we can start a sampling generation with as little as one character of context。

 And then transformer knows how to predict the next character with all the way up to just context of one。

 And so then it can predict everything up to block size。 And after block size。

 we have to start truncating。 because the transformer will never receive more than block size inputs。

 when it's predicting the next character。Okay， so we've looked at the time dimension of the tensors that are going to be feeding into the transformer。

 There's one more dimension to care about。 And that is the batchsh dimension。

And so as we're sampling these chunks of text， we're going to be actually every time we're going to feed them into a transformer。

 we're going to have many batches of multiple chunks of text that are all like stacked up in a single tensor。

And that's just done for efficiency just so that we can keep the GPUus busy because they are very good at parallel processing of data。

 And so we just want to process multiple chunks all at the same time。

 but those chunks are processed completely independently。 They don't talk to each other and so on。

 So let me basically just generalize this and introduce a batch dimension。 Here's a chunk of code。

Let' me just run it， and then I'm going to explain what it does。So here。

 because we are going to start sampling random locations in the dataset set to pull chunks from。

 I am setting the seed so that in the random number generator so that the numbers I see here are going to be the same numbers you see later if you try to reproduce this。

Now the batch size here is how many independent sequences we are processing every forward backward pass of the transformer。

The block size， as I explained， is the maximum context length to make those predictions。

So let's say by size 4， block size 8， and then here's how we get batch。For any arbitrary split。

If the split is a training split， then we're going to look at train data， otherwise at Valde。

That gives us the data array。And then when I generate random positions to grab a chunk out of。

I actually grab。 I actually generate batch size number of。Random upsets。So because this is four。

 IX is going to be a four numbers that are randomly generated between zero and length of data minus block size。

So it's just random offsets into the training set。And then X， as I explained。

 are the first block size characters starting at I。The Ys are the offset by one of that。

 So just add plus one。And then we're going to get those chunks for every one of integer's I in I X and use a torch dot stack to take all those one dimensional tensors。

 as we saw here。And we're going to stack them up。At Rose。

And so they all become a row in a 4 by 8 tenssor。So here's what I'm printing then。

Would I sample batch X， B and Y， B。The inputs of the transformer now are。

The input X is the 4 by 8 tensor。4 rows of8 columns。

And each one of these is a chunk of the training set。

And then the targets here are in the associated array Y。

 and they will come in to the transformer all the way at the end to create the loss function。

 so they will give us the correct answer for every single position inside x。

And then these are the four independent rows。So spelled out， as we did before。

This 4 by 8 array contains a total of 32 examples， and theyre completely independent as far as the transformer is concerned。

So， when the。Input is 24。 The target is 43， or rather 43 here in the Y array。 When the input is 24。

43， the target is 58。When the input is 24，43，58， the target is5， et cetera。Or like when it is a  52。

58，1， the target is 58。Right so you can sort of see this spelled out。

 These are the 32 independent examples packed in to a single batch of the input X。

 and then the desired targets are in y。And so now， this integer tensor。

Of X is going to feed into the transformer。And that transformer is going to simultaneously process all these examples and then look up the correct integers to predict in every one of these positions in the tensor Y。

 Okay， so now that we have our batch of input that we'd like to feed into a transformer。

 let's start basically feeding this into neural networks。

Now we're going to start off with the simplest possible neural network。

 which in the case of language modeling， in my opinion， is the bigram language model。

 and we've covered the bigram language model in my makemore series in a lot of depth。

And so here I'm going to sort of go faster and let's just implement the Pyroch module directly that implements the bigram language model。

So I'm importing the Pytorrch and then module。For reproducibility。

And then here I'm constructing a bigram language model， which is the subclass of NN module。

And then I'm calling it， and I'm passing in the inputs and the targets。And I'm just printing。

Now when the inputs on targets come here。You see that I'm just taking the index， the inputs X here。

 which I rename to I X。 And I'm just passing them into this token embedding table。

So what's going on here is that here in the constructor。We are creating a token embedding table。

And it is of size， vocab size by vocab size。And we're using an enddot embedding。

 which is a very thin wrapper around basically a tensor of shape， vocab size by vab size。

And what's happening here is that when we pass I D X here。

 every single integer in our input is going to refer to this embedding table and is going to pluck out a row of that embedding table corresponding to its index。

So 24 here， we'll go to the embedding table and we'll pluck out the 24th row。

And then 43 will go here and block out the 43rd row， et cetera。

 And then Pytorrch is going to arrange all of this into a batch by time by channel tensor。

In this case， batch is 4 time is 8 and C， which is the channels is vab size or 65。

And so we're just going to pluck out all those rows， arrange them in a B by T by C。

And now we'm going to interpret this as the logits。

 which are basically the scores for the next character a sequence。

And so what's happening here is we are predicting what comes next based on just the individual identity of a single token。

And you can do that because， I mean， currently the tokens are not talking to each other and they're not seeing any context except for they're just seeing themselves。

 So I'm a token number 5。 And then I can actually make pretty decent predictions about what comes next just by knowing that I'm token 5。

 because some characters know follow other characters in typical scenarios。

So we saw a lot of this in a lot more depth in the make more series。 And here， if I just run this。

Then we currently get the predictions， the scores， the logits。For every one of the 4 by 8 positions。

 now that we've make predictions about what comes next， we'd like to evaluate the loss function。

 And so in makemore series， we saw that a good way to measure a loss or like a quality of the predictions。

 is to use the negative log likelihood loss， which is also implemented in Pytorch under the name cross entropy。

So what we'd like to do here is。Loss is the cross entropy on the predictions and the targets。

 And so this measures the quality of the logits with respect to the targets。In other words。

 we have the identity of the next character。 So how well are we predicting the next character based on the legs。

And intuitively， the correct。The correct dimension of logicitts。Depending on what the target is。

 should have a very high number， and all the other dimensions should be very low number， right。Now。

 the issue is that this won't actually， this is what we want。

 We want to basically output the logicits and the loss。This is what we want， but unfortunately。

 this won't actually run。We get an error message， but intuitively， we want to measure this。 Now。

 when we go to the Pytorrch cross entropy。A documentation here。嗯。

We're trying to call the cross entropy in its functional form。

 So that means we don't have to create like a module for it。But here we go to the documentation。

You have to look into the details of how Pytorch expects these inputs。 And basically。

 the issue here is Pytorch expects if you have multidimensional input， which we do。

 because we have a B by T by C tensor， then it actually really wants the channels to be the second dimension here。

So， if you。So basically， it wants a B by C by T instead of a B by T by C。

And so it's just the details of how Pytorch treats。These kinds of inputs。

 And so we don't actually want to deal with that。 So what we're going to do instead is we need to basically reshape our logits。

So here's what I like to do。 I like to take basically give names to the dimensions。

 So Loes that shape is B by T by C and unpack those numbers。

And then let's say that logts equals logs。 view。And we want it to be a be times C， be times C by sea。

 So just a two dimensional array。Right， so we're going to take all the。

We're going to take all of these。Positions here， and we're going to stretch them out in one dimensional sequence。

And preserve the channel dimension as the second dimension。

So we're just kind of like stretching out the array so it's two dimensional， and in that case。

 it's going to better conform to what Pytorch sort of expects in its dimensions。Now。

 we have to do the same to targets。Because currently， targets。Are of shape B by T。

 And we want it to be just be times T。 So one dimensional。Now， alternative。

 you could only still just do -1 because Pytorch will guess what this should be if you want to lay it out。

 but let me just be explicit and save you T。Once we reshaped this。

 it will match the cross entropy case。And then we should be able to evaluate our loss。Okay。

 so that right now。 and we can。Do loss。 And currently we see that the loss is 4。87。Now， because our。

 we have 65 possible vocabulary elements， we can actually guess at what the loss should be。

And in particular。We covered negative log likelihood in a lot of detail。

 We are expecting log or long of one over 65 and negative of that。

So we're expecting the loss to be about 4。1 ti 17。 by we're getting 4。87。

 And so that's telling us that the initial predictions are not super diffuse。

 They've got a little bit of entropy。 And so we're guessing wrong。So， yes， but actually， were I able。

 we are able to evaluate the loss。Okay， so now that we can evaluate the quality of the model on some data。

 we'd like to also be able to generate from the model。 So let's do the generation。

 Now I'm going to go again a little bit faster here because I covered all this already in previous videos。

So。Here's a generate function for the model。So we we take the same kind of input ID X here。And。

 basically。This is the current context of some characters in a batch in some batch。

So it's also B by T and the job of generate is to basically take this B by T and extend it to be B by t plus 1 plus 2 plus 3。

 and so it's just basically it continues the generation in all the batch dimensions in the time dimension。

So that's his job， and it will do that for Max Mu tokens。So you can see here on the bottom。

 theres going to be some stuff here， but on the bottom。

 whatever is predicted is concateated on top of the previous I X。Along the first dimension。

 which is the time dimension to create a B by T plus one。So that becomes a new I X。

 So the job of generate is to take a B by T and make it a B by T plus 1 plus2 plus 3。

As many as we want， maxim new tokens。 So this is the generation from the model。Now。

 inside the generation， what are we doing， we're taking the current indices。

 we're getting the predictions， so we get those are in the logits。

And then the loss here is going to be ignored because we're not using that and we have no targets that are sort of ground truth targets that we're going to be comparing with。

Then once we get the logits， we are only focusing on the last step。 So instead of a B by T by C。

 we're going to pluck out the negative one， the last element in the time dimension。

Because those are the predictions for what comes next。So that gives us the logicits。

 which we then convert to probabilities via softmax。

And then we need source our multinomials to sample from those probabilities。

 and we ask Py to give us one sample。And so I D X next will become a B by one。Because niche。

 one of the batch dimensions， we're going to have a single prediction for what comes next。

 So this nu samples equals one will make this be a one。

And then we're going to take those integers that come from the sampling process。

 according to the probability distribution given here。

And those integers got just concatenated on top of the current。

 sort of like running stream of integers。And this gives us a P by T plus one。And then。

 we can return that。Now， one thing here is you see how I'm calling self of I D X。

 which will end up going to the forward function。 I'm not providing any targets。 So currently。

 this would give an error because targets is is sort of like not given。So targets has to be optional。

 So targets is none by default。 And then if targets is none， then there's no loss to create。

 So it's just loss is none。But else， all of this happens。 and we can create a loss。

So this will make it so。If we have the targets， we provide them and get a loss。

 If we have no targets， it will just get thelogits。So this here will generate from the model。嗯。

And let's take that for a ride now。Oops。So I have another code chunk here。

 which will generate for the model from the model。 And okay， this is kind of crazy。 So maybe let me。

Let me break this down。So these are the I X， right。I'm creating a batch will be just one。

 Time will be just one。So I'm creating a little one by one tensor， and it's holding a zero。

And the D type， the data type is integer。So zero is going to be how we kick off the generation and remember that zero is the element standing for a new line character。

 so it's kind of like a reasonable thing to feed in as the very first character in a sequence to be the new line。

So there's going to be I D X， which we're going to feed in here。

 Then we're going to ask for 100 tokens。And then end that generate will continue that。Now。

 because generate works on the level of batches， we we then have to index into the zero throw to basically unpllock the。

The single。Bash dimension that exists。And then， that gives us a。

Time steps is just a one dimensional array of all indices。

 which we will convert to simple Python list。From Pytorch tensor so that that can feed into our decocode function and。

Convert those integers into text。So let me bring this back and we're generating 100 tokens。

 Let's run。And here's the generation that we achieved。So obviously， it's garbage。

 and the reason it's garbage is because this is a totally random model。 So next up。

 we're going to want to train this model。Now， one more thing I wanted to point out here is。

This function is written to be general， but it's kind of like ridiculous right now because。

We're feeding in all this。 We're building out this context， and we're concatenating at all。

 And we're always feeding it all into the model。But that's kind of ridiculous because this is just a simple bigra model。

 So to make， for example， this prediction about K， we only needed this W。

 But actually what we fed into the model is we fed the entire sequence。

 and then we only looked at the very last piece and a predicted K。

So the only reason I'm writing it in this way is because right now， this is a bigram model。

 but I'd like to keep this function fixed， and I'd like it to work later when our characters actually basically look further in the history。

 And so right now， the history is not used。 So this looks silly。 But eventually。

 the history will be used。 And so that's why we want to do it this way。

 So just a quick comment on that。So now we see that this is random。 So let's train the model。

 So it becomes a bit less random。 Okay， let's now train the model。

 So first what I'm going to do is I'm going to create a pytorrch optimization object。

So here we are using the optimizer。Ad M W。Now， in a make more series。

 we've only ever used a castastic gradienting descent， the simplest possible optimizer。

 which you can get using the S GD instead。 But I want to use Adam。

 which is a much more advanced and popular optimizer。

 and it works extremely well for a typical good setting for the learning rate is roughly 3 e negative 4。

 but for very， very small networks。 like is the case here。

 you can get away with much much higher learning rates。 One negative 3 or even higher， probably。

But let me create the optimizer object。Which will basically take the gradients and update the parameters。

 using the gradient。And then， here。Our batch size up above was only four。

 so let me actually use something bigger。 let's say 32。 And then for some number of steps。

 we are sampling a new batch of data。 We're evaluating the loss。

 We're zeroing out all the gradients from the previous step。

Getting the gradients for all the parameters and then using those gradients to update our parameters。

 So typical training loop， as we saw in the make more series。So， let me now run this。For say。

00 iterations。 and let's see what kind of boss we're going to get。So， we started around 4。7。

And now we're going to down to like 4。6， 4。5， et cetera。 So the optimization is definitely happening。

 but。Let's sort of try to increase the number of iterations and only print at the end。

Because we probably will not train for hoer。Okay， so we're down to 3。6 roughly。Roughly down to 3。

This is the most janky optimization。Okay， it's working。 Let's just do 10000。And then from here。

 we want to copy this。And hopefully， we're going to get something reasonable。 and of course。

 it's not going to be Shakespeare from a binarygra model。

 but at least we see that the loss is improving and hopefully we're expecting something a bit more reasonable。

Okayk， so were done in about 2。5 is。 Let's see what we get。Okay。

Dramatic improvements certainly on what we had here。So let me just increase the number of tokens。

Okay， so we see that we're starting to get something at least like。Reasonable is。

It'ly not Shakespeare， but the model is making progress。 So that is the simplest possible model。

So now what I'd like to do is。Obviously， this is a very simple model because the tokens are not talking to each other。

 So given the previous context of whatever was generated。

 we're only looking at the very last character to make the predictions about what comes next。

 So now these now these tokens have to start talking to each other and figuring out what is in the context so that they can make better predictions for what comes next。

 And this is how we're gonna kick off the transformer。 Okay， so next。

 I take the code that we developed in this Jupyter notebook and I converted it to be a script。



![](img/bf8e317787d215eeac53dc1b82b1c757_31.png)

And I'm doing this because I just want to simplify our intermediate work into just the final product that we have at this point。

So in the top here， I put all the hypo parameters that we've defined。 I introduced a few。

 and I'm going to speak to that in a little bit。Otherwise， a lot of this should be recognizable。

 reproducibility。Read data， get the encoder in the decoder， create the train and test splits。

Use the kind of like data loader that gets a batch of the inputs and targets。This is new。

 and I'll talk about it in a second。Now， this is the Bagram language model that we developed。

And it can forward and give us alogits and loss， and it can generate。

And then here we are creating the optimizer， and this is the training loop。

So everything here should look pretty familiar。 Now。

 some of the small things that I added number one。I added the ability to run on a GPU if you have it。

 So if you have a GPU， then you can this will use kuda instead of just CPU and everything will be a lot more faster。

Now， when device becomes kuda， then we need to make sure that when we load the data。

 we move it to device。When we create the model， we want to move the model parameters to device。

So as an example， here we have the NN embedding table， and it's got a dot weight inside it。

 which stores the sort of lookup table。 So that would be moved to the GPU so that all the calculations here happen on the GPU。

 and they can be a lot faster。And then finally here。

 when I'm creating the context that feed it to generate。

 I have to make sure that I create on the device。Number two， what I introduced is。

The fact that here in the training loop。

![](img/bf8e317787d215eeac53dc1b82b1c757_33.png)

Here I was just printing the lost dot item。Inside the training loop。

 But this is a very noisy measurement of the current loss。

 because every batch will be more or less lucky。

![](img/bf8e317787d215eeac53dc1b82b1c757_35.png)

And so what I want to do usually is。I have an estimate loss function。

 and the estimate loss basically then goes up here。And it averages up the loss over multiple batches。

So in particular， we're going to iterate eval iter times， and we're going to basically get our loss。

 and then we're going to get the average loss for both splits。 And so this will be a lot less noisy。

So here when we call the estimate loss， we're going to report the pretty accurate train and validation loss。

Now， when we come back up， you'll notice a few things here。

 I'm setting the model to a evaluation phase， and down here， I'm resetting it back to training phase。

Now right now for our model as is， this doesn't actually do anything。

Because the only thing inside this model is this N N dot embedding。

 and this network would behave both would behave the same in both evaluation mode and training mode。

 We have no dropout layers。 We have no bathroom layers， etc cea。

 But it is a good practice to think through what mode your neural network is in。

 because some layers will have different behavior at inference time or training time。And。

There's also this context manager torch Nograd， and this is just telling Pytorrch that everything that happens inside this function。

 we will not call dot backward on。And so Pyttorch can be a lot more efficient with its memory use because it doesn't have to store all the intermediate variables because we're never going to call backward。

 And so it can can be a lot more memory efficient in that way。

 So also a good practice to tell Pytorch when we don't intend to do back propag。

So right now this script is about 120 lines of code of and that's kind of our starter code。

I'm calling it bygram that pie and I'm going to release it later。Now， running this script。

Gives us output in the terminal。 Can it looks something like this。ItBaically， as I ran this code。

 it was giving me the train loss and valve loss， and we see that we convert to somewhere around 2。5。

With the bigra model。 And then here's the sample that we produced at the end。

And so we have everything packaged up in a script， And we're in a good position now to iterate on this。

 Okay， so we are almost ready to start writing our very first self attention block for processing these tokens。

😊。

![](img/bf8e317787d215eeac53dc1b82b1c757_37.png)

Now， before we actually get there， I want to get you used to a mathematical trick that is used in the self attention inside a transformer。

 and it iss really just like at the heart of an efficient implementation of self attention。

And so I want to work with this toy example to just get used to this operation。

 and then it's going to make it much more clear once we actually get to it in the script again。

So let's create a B by T by C where Bt and C are just 4，8 and 2 in this story example。

And these are basically channels， and we have batches， and we have the time component。

 and we have some information at each point in the sequence， so see。Now。

 what we would like to do is we would like these tokens。 So we have up to 8 tokens here in a batch。

 And these8 tokens are currently not talking to each other。

 and we would like them to talk to each other。 Wed like to couple them。And in particular， we。

 we want to couple them in a very specific way。 So the token， for example， at the fifth location。

 it should not communicate with tokens in the 6，7 and 8 location。

Because those are future tokens in the sequence。The token on the fifth location should only talk to the one in the fourth。

 third， second， and first。So information only flows from previous context to the current time step。

And we cannot get any information from the future because we are about to try to predict the future。

So。What is the easiest way for tokens to communicate， Okay， the easiest way I would say， is， okay。

 if we are up to， were a fifth token， and I'd like to communicate with my past。

 The simplest way we can do that is to just do a weight is to just do an average of all the of all the preceding elements。

 So， for example， if I'm the fifth token。 I would like to take the channels that make up that are information at my step。

 But then also the channels from the first step， third step， Second step in the first step。

 I'd like to average those up。 And then that would become sort of like a feature vector that summarizes me in the context of my history。

Now， of course， just doing a sum or like an average is an extremely weak form of interaction。

 like this communication is extremely lossy。 We've lost a ton of information about the spatial arrangements of all those tokens。

But that's okay for now， well see how we can bring that information back later。For now。

 what we would like to do is。For every single batch element， independently。

For every teeth token in that sequence， we'd like to now calculate the average of all the vectors in all the previous tokens and also at this token。

So let's write that out。I have a small snippet here， and instead of just fumbling around。

Let me just copy paste it， and talk to it。So in other words， we're going to create X。And B。

 O W is short for bag of words， because back of words is。It's kind of like。

A term that people use when you are just averaging up things。 So this is just a bag of words。

 Basically， there's a word stored on every one of these eight locations。

 And we're doing a bag of words are just averaging。So in the beginning。

 we're going to say that it's just initialized at 0。 And then I'm doing a for loop here。

 So we're not being efficient yet。 that's coming。 But for now。

 we're just iterating over all the batchsh dimensions independently， iterating over time。

And then the previous tokens are at this batch， dimension。

 and then everything up to and including the teeth token。So when we slice out X in this way。

 X Pv becomes of shape。 how many T elements there were in the past。 and then， of course， C。

 So all the two dimensional information from these little tokens。

So that's the previous sort of chunk of tokens。From my current sequence。

And then I'm just doing the average or the mean over the zero dimension。

 So I'm averaging out the time here。And I'm just going to get a little C one dimensional vector。

 which I'm going to store in X bag of words。So I can run this。

And this is not going to be very informative， because。Let's see。 So this is x of 0。

 So this is the zeroth batch element， and then expo at 0 now。You see how the。

At the first location here， you see that the two are equal。

 and that's because it' we're just doing an average of this one token。But here。

 this one is now an average of these two。And now this one is an average of these  three。And so on。So。

 and this last one is the average of all of these elements。 So vertical average。

 just averaging up all the tokens now gives this outcome here。So this is all well and good。

 but this is very inefficient。 Now， the trick is that we can be very。

 very efficient about doing this using matrix multiplication。So that's the mathematical trick。

 And let me show you what I mean。 Let's work with the toy example here。Let me run it。

 and I'll explain。I have a simple matrix here that is 3 by three of all ones。

A matrix B of just random numbers ands a 3 by 2。 and a matrix C， which will be 3 by 3。

 multiply 3 by 2， which will give out a 3 by 2。So here we're just using。Ma your smooth application。

So a multiply B gives us C。Okay， so how are these numbers in C achieved， right？

 So this number in the top left is the first row of a dot product with the first column of B。

And since all the row of a right now is all just once。Then the dot product here with。

 with this column of B is just going to do a sum of these of this column。 So 2 plus 6 plus 6 is 14。

The element here in the output of C is also the first column here。

 The first row of a multiplied now with the second column of B。 So 7 plus 4 plus plus 5 is 16。Now。

 you see that there's repeating elements here。 So this 14 again。

 is because this row is again all once and it's multiplying the first column of B。 So we get 14。

And this one is and so on。 So this last number here is the last row dark product last column。Now。

 the trick here is the following。This is just a boring number of， is just a boring array of all once。

 But Torch has this function called the trailll。Which is short for a triangular。Something like that。

 And you can wrap it entoched at once and it will just return the lower triangular portion of this。

Okay。So now it will basically zero out these guys here， so we just get the lower triangular apart。

Well， what happens if。We do that。So， now will have。A like this And B like this。

 And now what are we getting here and see。Well， what is this number， Well。

 this is the first row times the first column。 And because this is zeros。

These elements here are now ignored， so we just get a two。

And then this number here is the first row times the second column。And because these are zeros。

 they get ignored and is just 7。 The7 multiplies this one。But look what happened here。

 because this is one and then zeros。 we what ended up happening is we're just plucking out the row of this row of B。

 And that's what we got。Now， here we have 1，1，0。 So here，1，1。

0 dot product with these two columns will now give us 2 plus 6， which is 8 and 7 plus 4， which is 11。

And because this is 1，11， we ended up with the addition of all of them。And so basically。

 depending on how many once and zeros we have here。

 we are basically doing a sum currently of a variable number of beat rows。

 and that gets deposited into C。So currently we're doing sums because these are ones。

 but we can also do average， right， and you can start to see how it could do average of the rows of B。

 sort of in incremental fashion。Because we don't have to。

 we can basically normalize these rows so that they sum to one。

 and then we're going to get an average。So if we took a and then we did a equals a divide。

Torched at sun。In the。Of a。In the1。Dimenssion。And then let's keep them as true。So therefore。

 the broadcasting will work out。So if I re on this。You see now that these rows now sum to one。

 So this row is one。 This row is 。5。50。 And here we get one third。And now when we do a multiply B。

 what are we getting。Here we are just getting the first row， first row。

Here now we are getting the average of the first two rows。Okay， so2 and 6 average is 4。

 and 4 and 7 average is 5。5。And on the bottom here。

 we are now getting the average of these three rows。

So the average of all of elements of B are now deposited here。

And so you can see that by manipulating these elements of this multiplying matrix and then multiplying it with any given matrix。

 we can do these averages in this incremental fashion， because we just get。

And we can manipulate that based on the elements of a。 Okay， so that's very convenient。

 So let's swing back up here and see how we can vectorize this and make it much more efficient using what we've learned。

So in particular。We are going to produce an array A。

 but here I'm going to call it way short for weights。But this is R。

And this is how much of every row we want to average up。

 And it's going to be an average because you can see that these rows sum to one。So this is R A。

 and then R B in this example， of course， is。X。So what's going to happen here now is that we are going to have an expo2。

And this expo，2 is going to be way multiplying。R x。So let's think this through。 Way is T by T。

 and this is matrix multiplying in pytorch， A B by T by C。And it's giving us。The what shape。

 So Pytorarch will come here and it will see that these shapes are not the same。

 so it will create a batch dimension here。And this is a batched matrix multiply。

And so it will apply this matrix multiplication in all the batch elements in parallel。

And individually。And then for each batch element， there will be a T by T multiplying T by C。

 exactly as we had below。So， this will now create。B by T by C。

And expo2 will now become identical to expo。So。We can see that。 Torched out all close。

Of expo and expo 2， should be true。Now。So this kind of like convincees us that these are， in fact。

 the same。So expo and expo， too， if I just print them。Okay， we're not going to be able to， Okay。

 we're not going to be able to just stare it down， but。Well。

 let me try expo basically just at the0th element and expo 2 at the0th element。

 So just the first batch。 and we should see that this and that should be identical， which they are。

Right so what happened here， the trick is， we were able to use batched matrix multiply。

To do this aggregation， really。And it's a weighted aggregation。

 and the weights are specified in this T by T array。And we're basically doing weighted sums。

And these weighted sums are according to the weights inside here that take on sort of this triangular form。

And so that means that a token at the teeth dimension will only get sort of information from the tokens perceiving it。

 So that's exactly what we want。And finally， I would like to rewrite it in one more way。

And we're going to see why that's useful。So this is the third version。

 and it's also identical to the first and second。 But let me talk through it。 It uses softmax。So。

Trill here。Is this matrix。Lower triangular ones。Way begins， as all 0。Okay。

 so if I just print way in the beginning， it's all zero。Then， I used。Masked Phil。

So what this is doing is。Wait that masked Phil。 It's all zeros。 And I'm saying。

For all the elements where tri is equal to  equal0， make them be negative infinity。

So all the elements where a tri is 0 will become negative infinity now。So this is what we get。

And then the final one here is softmax。So if I take a softmax along every single。

 so dim is negative one， so along every single row。If I do a softm， what is that going to do？Well。

 softm is。It's also like a normalization operation， right。And so spoiler alert。

 you get the exact same matrix。Let me bring back the softm。And recall that in softm。

 we're going to exponentiate every single one of these。And then we're going to divide by the sum。

And so if we exponentiate every single element here， we're going to get a1。

 and here we're going to get basically 0，0，0，0，0 everywhere else。And then when we normalize。

 we just get one。Here we're going to get 1，1， and then zeros。 And then softm will again divide。

 and this will give less 05。5 and so on。And so this is also the same way to produce this mask。Now。

 the reason that this is a bit more interesting and the reason we're going to end up using it in self attention。

Is that。These weights here begin with0。 and you can think of this as like an interaction strength or like an affinity。

So basically， it's telling us how much of each token from the past do we want to aggregate an average up？

And then this line is saying tokens from the past cannot communicate by setting them to negative infinity or saying that we will not aggregate anything from those tokens。

And so basically， this then goes through softftmax and through the weighted。

 and this is the aggregation through matrix multiplication。

And so what this is now is you can think of these as these zeros are currently just set by us to be 0。

 But a quick preview is that these affinities between the tokens are not going to be just constant at 0。

 Theyre going to be data dependent。 These tokens are going to start looking at each other。

 And some tokens will find other tokens more or less interesting。

And depending on what their values are， they're going to find each other interesting to different amounts。

 And I'm going to call those affinities， I think。And then here we are saying the future cannot communicate with the past。

We we're going to clamp them。And then when we normalize and sum。

 we're going to aggregate sort of their values， depending on how interesting they find each other。

And so that's the preview for self attention。 And basically。

 long story short from this entire section is that you can do weighted aggregations of your past elements。

By having， by using nature multiplication of a lower triangular fashion。

And then the elements here in the lower triangular part are telling you how much of each element fuses into this position。

So we're going to use this trick now to develop the self attention block。



![](img/bf8e317787d215eeac53dc1b82b1c757_39.png)

So first， let's get some quick preliminaries out of the way。First。

 the thing I'm kind of bothered by is that you see how we're passing in vocab size into the constructor。

 there's no need to do that because vab size is already defined up top as a global variable。

 so there's no need to pass this stuff around。Next 1 I want to do is I don't want to actually create。

 I want to create like a level of indirect here where we don't directly go to the embedding for the。

Loits。 But instead， we go through this intermediate phase because we're going to start making that bigger。

So let me introduce a new variable， and embed。 It short for number of embedding dimensions。So。

 an embed。Here。Will be， say 32。That was the suggestion from Gitthub compiled， by the way。

 it also shows 32， which is a good number。So this is an embedding table and only 32 dimensional embeddings。

So then here， this is not going to give us logits directly。 Instead。

 this is going to give us token embeddings。That's what I'm going to call it。

 And then to go from the token emtings to the logits， we're going to need a linear layer。

 So sub that Lm head。 Let's call it short for language modeling head。

Is N and linear from N embed up to v up size。And then when we swing over here。

 we're actually going to get the logs by exactly what the coppi says。Now。

 we have to be careful here because this C and this C are not equal。This is an embed C。

 and this is willap size。So let's just say that an embed is equal to C。

And then this just creates one spurious layer of interaction through a linear layer。

But this should basically run。So we see that this front。 and this currently looks kindas spurious。

 but we're going to build on top of this。Now， next up， so far。

 we've taken these indices and we've encoded them based on the identity of the tokens inside ID X。

The next thing that people very often do is that we're not just encoding the identity of these tokens。

 but also their position。So we're going to have a second position embedding table here。

 so salt that position embedding table。Is an in embedding of block size by an embed。

And so each position from 0 to block size minus 1 will also get its own embedding vector。

And then here， first， let me decode B by T from ID D X that shape。And then here。

 we're also going to have a puzzlebedding， which is the positional embedding。 And these are。

 this is torch range。So this will be basically just integers from 0 to t -1。

And all of those integers from 0 to t minus-1 get embeddedbed through the table to create a T by C。

And then here， this gets renamed to just say X。And X will be。The addition of the token embedding。

 with the positional embeddings。And here， the broadcasting note will work out。

 So B by T by C plus T by C， This gets right aligned a new dimension of one gets added。

 and it gets broadcasted across batch。So at this point， X holds not just the token identities。

 but the positions in which these tokens occur。And this is currently not that useful because。

 of course we just have a simple bigra model。 So it doesn't matter if you're in the fifth position。

 the second position or wherever， it's all translation invariant at this stage。

 So this information currently wouldn't help。 But as we work on the self attention block。

 we'll see that this starts to matter。

![](img/bf8e317787d215eeac53dc1b82b1c757_41.png)

Okay， so now we get the crux of self attention。 So this is probably the most important part of this video to understand。

We're going to implement a small self attention for a single individual head， as they're called。

So we start off with where we were， so all of this code is familiar。

So right now I'm working with an example where I change the number of channels from 2 to 32。

 so we have a 4 by8 arrangement of tokens each and the information of each token is currently 32 dimensional。

 but we just are working with random numbers。Now， we saw here that。The code， as we had at before。

 does a simple weight， simple average of all the past tokens and the current token。

 So it is just the previous information and current information is just being mixed together in an average。

And that's what this code currently achieves。 and it does so by creating this lower triangular structure。

 which allows us to mask out this weight matrix that we create。So we mask it out。

 and then we normalize it。 And currently， when we initialize the affinities between all the different sort of tokens or nodes。

 I'm going to use those terms interchangeably。So when we initialize the affinities between all the different tokens to be zero。

Then we see that w gives us this structure where every single row has these。Uniform numbers。

 And so that's what that's what then in this matrix multiply makes it so that we're doing a simple average。

Now。We don't actually want this to be。All uniform， because different tokens will find different other tokens more or less interesting。

 and we want that to be data dependent。 So， for example， if I'm a vowel。

 then maybe I'm looking for consonants in my past， and maybe I want to know what those consonants are。

 And I want that information to flow to me。And so I want to now gather information from the past。

 but I want to do it in a data dependent way。 And this is the problem that self attention solves。Now。

 the way self attention solves this is the following。

 Every single node or every single token at each position will emit two vectors。It will emit a query。

And it will emit a key。Now， the query vector， roughly speaking， is， what am I looking for？

And the key vector， roughly speaking， is， what do I contain。

And then the way we get affinities between these tokens now and a sequence。

Is we basically just do a dot product between the keys and the queries。

So my query dot products with all the keys of all the other tokens and that dot product now becomes way。

And so if the key and the query are sort of aligned， they will interact to a very high amount。

 and then I will get to learn more about that specific token。

 as opposed to any other token in the sequence。So let's implement this stuff。

We're going to implement a single。What's called head of self attention。So this is just one head。

 There is a hyperparameter involved with these heads， which is the head size。

And then here I'm initializing linear modules， and I'm using Bisqs false。

 so these are just going to apply a matrix multiply with some fixed weights。

And now let me produce eight。K and Q， K And Q by forwarding these modules on X。

So the size of this will not become。B by T by 16， because that is the head size and the same here。

 B by T by 16。So this being that size。So you see here that when I forward this linear on top of my X。

All the tokens in all the positions in the B by T arrangement。

 all of them in parallel and independently produce a key in a query。

 So no communication has happened yet。But the communication comes now。

 All the queries will dot product with all the keys。So basically。

 what we want is we want way now or the affinities between these to be query， multiplying key。

But we have to be careful with， we can't venture multiply this。 We actually need to transpose K。

 but we have to be also careful because。These are when you have the batchsh dimension。

 So in particular， we want to transpose the last two dimensions。

 dimension negative 1 and dimension negative 2。So negative2。Negative one。

And so this matrix multiply now will basically do the following B by T by 16。

Majos multiplies B by 16 by T。To give us。Be by T by T。Right。So for every row of B。

 we're now going to have a T square matrix， giving us the affinities。 And these are now the way。

So they are not zeros。 They are now coming from this dot product between the keys and aquarries。

So this can now run。 I can。 I can run this。And the weighted aggregation now is a function in a data and manner between the keys and queries of these notes。

So just inspecting what happened here。The way takes on this form。

And you see that before way was just a constant。 So it was applied in the same way to all the batch elements。

 But now every single batch elements will have different sort of way because every single batch element contains different tokens at different positions。

 And so this is not data dependent。So when we look at just the zero row， for example， in the input。

These are the weights that came out。 And so you can see now that they're not just exactly uniform。

And in particular， as an example here for the last row， this was the 8 token。

 and the 8 token knows what content it has， and it knows at what position it's in。

And now the a token， based on that。Creates a query。 Hey， I'm looking for this kind of stuff。

 I'm a vowel。 I'm on the eighth position。 I'm looking for any consonants at positions up to 4。

And then all the nodes get to emit keys。And maybe one of the channels could be。

 I am I am a consonant， and I am in the position up to 4。

And that key would have a high number in that specific channel。

 And that's how the query and the key when they dark product。

 they can find each other and create a high affinity。And when they have a high affinity， like， say。

 this token was pretty interesting to， to this eighth token。When they have a high affinity。

 then through the softm， I will end up aggregating a lot of its information into my position。

And so I'll get to learn a lot about it。Now， just this we're looking at way after this has already happened。

嗯。Let me erase this operation as well。 So let me erase the masking and the softm just to show you the under hood internals and how that works。

So without the masking and the softm， weight comes out like this， right？

 This is the outputs of the dot products。And these are the raw outputs。

 and they take on values from negative to positive two， etc cetera。

So that's the raw interactions and raw affinities between all the nodes。But now， if I'm a。

 if I'm a fifth node， I will not want to aggregate anything from the sixth node。

 seventh node and the eighth node。 So actually， we use the upper triangular masking。

So those are not allowed to communicate。And now we actually want to have a nice distribution。

 So we don't want to aggregate negative 0。11 of this node。 That's crazy。 So instead。

 we exponentiate and normalize。And now I get a nice distribution that sums to one。

And this is telling us now in the data dependent manner how much of information to aggregate from any of these tokens in the past。

So that's way。 and it's not zeros any more。 but but it's calculated in this way。 Now。

 there is one more part to a single self attention head。 And that is that when we do the aggregation。

 we don't actually aggregate deep tokens exactly。 We aggregate。 We produce one more value here。

 And we call that the value。So in the same way that we produced P inquiry。

 we' are also going to create a value。And then。Here。We don't aggregate。X， we calculate a V。

 which is just achieved by propagating this linear on top of X again。And then， we。

Output way multiplied by V。 So V is the elements that we aggregate or the the vector that we aggregate instead of the raw x。

And now， of course， this will make it so that the output here of this single head will be 16 dimensional because that is the head size。

So you can think of x as kind of like private information to this token。 if you。

 if you think about it that way。 So x is kind of private to this token。

 So I'm a fifth token at some and I have some identity， and my information is kept in vector X。

And now， for the purposes of the single head， here's what I'm interested in。 Here's what I have。

And if you find me interesting， here's what I will communicate to you。 And that's stored in V。

And so V is the thing that gets aggregated for the purposes of this single head between the different notes。

And that's。Basically， the self attention mechanism。 This is， this is what it does。

There are a few notes that I would make like to make about attention。Number one， attention is。

A communication mechanism。 You can merely think about it as a communication mechanism where you have a number of nodes in a directed graph where basically。

 you have edges pointed between nodes like this。And what happens is every node has some vector of information。

 and it gets to aggregate information via a weighted sum from all the nodes that point to it。

And this is done in a data dependent manner， so depending on whatever data is actually stored。

 you should know at any point in time。Now。Our graph doesn't look like this。

 Our graph has a different structure， we have eight nodes because the block size is8。

 and there's always eight tokens。And the first node is only pointed to by itself。

 The second node is pointed to by the first node and itself all the way up to the eighth node。

 which is pointed to by all the previous nodes and itself。

And so that's the structure that our directed graph has or happens happens to have an utter aggressive sort of scenario like language modeling。

But in principle， attention can be applied to any arbitrary directed graph。

 and it's just a communication mechanism between the nodes。

The second note is that notice that there is no notion of space。

 So attention simply acts over like a set of vectors in this graph。 And so by default。

 these nodes have no idea where they are positioned in the space。

 And that's why we need to encode them positionally and sort of give them some information that is anchors to a specific position so that they sort of know where they are。

 And this is different than， for example， from convolution。 because if you run， for example。

 a convolution operation over some input， there is a very specific sort of layout of the information in space and the convolutional filters sort of act in space。

 And so it's not like in attention。 and attention is just a set of vectors out there in space。

 they communicate， And if you want them to have a notion of space， you need to specifically add。

 which is what we've done when we calculate the relative the positional encode encodings and added that information to the vectors。

 The next thing that I hope is very clear， is that the elements across the batch dimension。

 which are independent examples never talk to each other。They're always processed independently。

 And this is a baed matrix multiply that applies basically a matrix multiplication kind of imp parallel across the batchsh dimension。

 So maybe it would be more accurate to say that in this analogy of a directed graph。

 we really have because the batch size is4。 We really have four separate pools of eight nodes。

 and those eight nodes only talk to each other。 But in total。

 there's like 32 nodes that are being processed。 but there's sort of four separate pools of8。

 You can look at it that way。The next note is that here in the case of language modeling。

We have this specific structure of directed graph where the future tokens will not communicate to the past tokens。

But this doesn't necessarily have to be the constraint in the general case。 And in fact。

 in many cases， you may want to have all of the notes talk to each other fully。 So as an example。

 if you're doing sentiment analysis or something like that with a transformer。

 you might have a number of tokens and you may want to have them all talk to each other fully。

 because later you are predicting， for example， the sentiment of the sentence。

And so it's okay for these notes to talk to each other。And so in those cases。

 you will use an encoder block of self attention。And all it means that it's an encoder block is that you will delete this line of code。

 allowing all the nodes to completely talk to each other。

 What we' are implementing here is sometimes called a decoder block。

 and it's called a decoder because it is sort of like decoding language and it's got this autoag format where you have to mask with the triangle and matrix so that notes from the future never talk to the past。

Because they would give away the answer。And so basically， in encoder blocks， you would delete this。

 allow all the nodes to talk in decoder blocks。 This will always be present so that you have this triangular structure。

 but both are allowed and attention doesn't care。 Attention supports arbitrary connectivity between nodes。

The next thing I wanted to comment on is you keep me you keep hearing me， say attention。

 self attention， et cetera。 There's actually also something called cross attention。

 What is the difference。🤧So。Basically， the reason this attention is self attention。

Is because the keys， queries and the values are all coming from the same source from X。

 So the same source X produces keys queries and values。 So these nodes are self attending。

But in principle， attention is much more general than that。 So， for example。

 an encoder decoder transformers。You can have a case where the queries are produced from X。

 but the keys and the values come from a whole separate external source。

 and sometimes from encoder blocks that encode some context that we'd like to condition on。

 And so the keys and the values will actually come from a whole separate source。

 Those are nodes on the side。 And here we're just producing queries。

 And we're reading off information from the side。So cross attention is used when there's a separate source of nodes。

 we'd like to pull information from into our nodes。And it self attention。

 if we just had nodes that we like to look at each other and talk to each other。

So this attention here happens to be self attention。But， in principle。Attention is lot more general。

 Okay， and the last note at this stage is if we come to the attention is all you need paper here。

 we've already implemented attention。 So given query key and value。

 we've multiplied the query on the key。We've softmaed it， and then we are aggregating the values。

There's one more thing that we're missing here， which is the dividing by one over square root of the head size。

 the decay here is the head size。Why are they doing this one is important。

So they call it the skilled attention。And it's kind of like an important normalization to basically have。

The problem is， if you have unit Gaussian inputs。 So 0 mean unit variance， K and Q are unit Gaussian。

 then if you just do weigh naively， then you see that your way actually will be the variance will be on the order of head size。

 which in our case is 16。But if you multiply by one over head size square root。

 So this is square root， and this is one over。Then the variance of y will be one。

 so it will be preserved。Now， why is this important？You'll notice that way here。

Will feed into softmax。And so it's really important。

 especially at initialization that way be fairly diffuse。So in our case here。

We sort of locked out here， and we。Had a fairly diffuse numbers here， so。Now。

 the problem is that because of softmax， if weight takes on very positive and very negative numbers inside it。

 softftm will actually converge towards one hot vectors。And so I can illustrate that here。嗯。

Say we are applying softm to a tensor of values that are very close to 0。

 They more a diffuse thing out of softm。But the moment I take the exact same thing。

 and I start sharpening it， and making it bigger by multiplying these numbers by 8。 For example。

 you'll see that the softm will start to sharpen， and， in fact， it will sharpen towards the max。

 So it will sharpen towards whatever number here is the highest。And so basically。

 we don't want these values to be too extreme， especially at the initialization。 Otherwise。

 softmax will be way too peaky。 And you're basically aggregating information from like a single node。

 Every node just aggregates information from a single other node。 That's not what we want。

 especially initialization。 And so the scaling is used just to control the variance at initialization。

 Okay， so having said all that， let's now take our self attention knowledge。

 and let's take it first a spin。

![](img/bf8e317787d215eeac53dc1b82b1c757_43.png)

So here in the code， I've created this head module and implements a single head of self attention。

So you give it a head size。 And then here it creates the key query and the value linear layers。

 Typically， people learn misbies in these。So those are the linear projections that we're going to apply to all of our nodes。

Now， here I'm creating this tri variable。 Trill is not a parameter of the module。

 So in sort of Pyrch naming conventions， this is called a buffer。 It's not a parameter。

 And you have to call it。 you have to assign it to the module using a register buffer。

 So that creates the tri。The lower triangular matrix。And over given the input X。

 this should look very familiar。 Now， we calculated the keys， the queries。

 We col calculatecate the attentions course insideway。We normalize it。

 so we're using scaled attention here。Then we make sure that feature doesn't communicate with the past。

 so this makes it a decoder block。And then softmax and then aggregate the value and output。

Then near in the language model， I'm creating a head in the constructor。

 and I'm calling it self attention head and the head size I'm going to keep as the same and embed just for now。

And then here， once we've encoded the information with the token embeddings and the position embeddings。

 we're simply going to feed it into the self attention head。

 And then the output of that is going to go into the decoder language modelling head and create the logits。

 So this is this sort of the simplest way to plug in a self attentional component into our network right now。

I had to make one more change， which is that here。In the generate。

 we have to make sure that our I X that we feed into the model。

Because now we're using position embeddings， we can never have more than block size coming in。

 because if I X is more than block size， then our position embedding table is going to run out of scope because it only has embeddings for up to block size。

And so therefore， I added some code here to crop the context。That we're going to feed into self。

So that we never pass in more than block size elements。

So those are the changes and let's now train the network。 Okay， so I also came up to the script here。

 and I decreased the learning rate because the self attention can't tolerate very。

 very high learning rates。And then I also increase number of iterations because the learning rate is lower。

And then I trained it。 And previously， we were only able to get to up to 2。5。

 And now we are down to 2。4。 So we definitely see a little bit of improvement from 2。5 to 2。

4 roughly， but the text is still not amazing。So clearly。

 the self attention head is doing some useful communication， but we still have a long way to go。

 Okay， so now we've implemented the scale dot product attention。 Now next up。

 and the attention is all you need paper。 Theres something called multi head attention。

 And what is multi head attention。 It's just applying multiple attentions in parallel in concatenating their results。



![](img/bf8e317787d215eeac53dc1b82b1c757_45.png)

So they have a little bit of diagram here。 I don't know if this is super clear。

 It's really just multiple attentions in parallel。

![](img/bf8e317787d215eeac53dc1b82b1c757_47.png)

So let's implement that fairly straightforward。If we want a multi head attention。

 then we want multiple heads of self attention running in parallel。So in Pytorrch。

 we can do this by simply creating multiple heads。So however， heads， many。

 however many heads you want， and then what is the head size of each。

And then we run all them in parallel into a list and simply concatenate all of the olets。

And were concatenating over the channel dimension。So the way this looks now is we don't have just a single attention。

That has a hit size of 32， because remember N embed is 32。

Instead of having one communication channel， we now have four communication channels in parallel。

 and each one of these communication channels typically will be smaller correspondingly。

 so because we have four communication channels， we want eight dimensional self attention。

And so from each communication channel， we're going together8 dimensional vectors。

 And then we have four of them， and thatcatenates to give us 32， which is the original and embed。

And so this is kind of similar to if you're familiar with convolutions。

 this is kind of like a group convolution because basically， instead of having one large convolution。

 we do convolution in groups， and that's multi headed self attention。

And so then here we just use essay heads， self attention heads instead。

Now I actually ran it and scrolling down。I ran the same thing， and that we now get this down to 2。28。

 roughly。And the output is still， the generation is still not amazing。

 but clearly the validation loss is improving because we were at 2。4 just now。

And so it helps to have multiple communication channels because obviously。

 these tokens have a lot to talk about。 They want to find the consonants， The vowels。

 They want to find the vowels just from certain positions。

 They want to find any kinds of different things。 And so it helps to create multiple independent channels of communication。

 gather lots of different types of data， and then decode the output。 Now。

 going back to the paper for a second。 Of course， I didn't explain this figure in full detail。

 But We are starting to see some components of what we've already implemented。

 We have the positional encoings。 The token encoings that add。

 we have the masked multi headed attention implemented。



![](img/bf8e317787d215eeac53dc1b82b1c757_49.png)

Now， here's another multiheaded attention， which is a cross attention to an encodecor。

 which we haven't。 We're not going to implement。 in this case。 I'm going to come back to that later。

But I want you to notice that there's a feet forward part here。

 and then this is grouped into a block that gets repeated again and again。

Now the feed forward part here is just a simple multi layerer preron。So the multi headed。

 So here position why speak networks is just a simple little MP。

So I want to start basically in a similar fashion， also adding computation into the network。



![](img/bf8e317787d215eeac53dc1b82b1c757_51.png)

And this computation is on a per node level， so。I've already implemented it。

 and you can see the diff highlighted on the left here when I've added or changed things。Now， before。

 we had the multi headed self attention that did the communication。

 but we went way too fast to calculate the logicits。 So the tokens looked at each other。

 but didn't really have a lot of time to think on what they found from the other tokens。

And so what I've implemented here is a little feet forward single layer。

 and this little layer is just a linear followed by a re nonlinearity。 and that's it。

So it's just a little later。 and then I call it feet forward。An embed。

And then this feet forward is just consequently right after the self attention。 So we self attend。

 Then we feed forward。 And you'll notice that the feet forward here when in supplying linear。

 this is on a per token level， all the tokens do this independently。

 So the self attention is the communication。 And then once they gathered all the data。

 Now they need to think of that data individually。And so that's what Fe forward is doing。

 and that's why I've added it here。Now， when I train this。

 the validation loss actually continues to go down now to 2。24， which is down from 2。28。

 The output still looked kind of terrible， but at least we've improved the situation。And so。

 as a preview。We're going to now start to intersperse the communication with the computation。

 And that's also what the transformer does。

![](img/bf8e317787d215eeac53dc1b82b1c757_53.png)

When it has blocks that communicate and then compute， and it groups them and replicates them。



![](img/bf8e317787d215eeac53dc1b82b1c757_55.png)

Okay， so let me show you what we'd like to do。 We'd like to do something like this。 We have a block。

 and this block is basically this part here， except for the cross attention。



![](img/bf8e317787d215eeac53dc1b82b1c757_57.png)

![](img/bf8e317787d215eeac53dc1b82b1c757_58.png)

Now， the block basically enters process communication and the computation。 The computation。

 the communication is done using multi head self attention。

And then the computation is done using a feet forward network。On all the tokens， independently。Now。

 what I've added here also is you'll notice。This takes the number of embeddings in the embedding dimension and the number of heads that we would like。

 which is kind of like group sizing group convolution。

 And I'm saying that the number of heads we like is 4。 And so because this is 32。

 we calculate that because this is 32， the number of heads should be 4。

The head size should be  eight so that everything sort of works out channel wise。

So this is how the transformer structures sort of the sizes， typically。

So the head size will become 8。 And then this is how we want to intersperse them。

 And then here I'm trying to create blocks， which is just a sequential application of block block block。

 so that we're interspersing communication fee forward many， many times。 And then finally， we decode。

Now， actually we tried to run this and the problem is this doesn't actually give a very good answer。

And very good result。 And the reason for that is we're start starting to actually get like a pretty deep neural net。

 and deep neural nets suffer from optimization issues。

 And I think that's what we're kind of like slightly starting to run into。

 So we need one more idea that we can borrow from the transformer paper to resolve those difficulties。

 Now， there are two optimizations that dramatically help with the depth of these networks and make sure that the networks remain optimizable。

 Let's talk about the first one。

![](img/bf8e317787d215eeac53dc1b82b1c757_60.png)

The first one in this diagram is you see this arrow here。And then this arrow and this arrow。

 those are skip connections， or sometimes called residual connections。



![](img/bf8e317787d215eeac53dc1b82b1c757_62.png)

They come from this paper， the Preional Learning forage recognition from about 2015。



![](img/bf8e317787d215eeac53dc1b82b1c757_64.png)

That introduced the concept。Now， these are basically what it means is you transform data。

 but then you have a skip connection with addition。From the previous features。Now。

 the way I like to visualize it that I prefer is the following here the computation happens from the top to bottom。

And basically， you have this residual pathway。And you are free to fork off from the residual pathway。

 perform some computation， and then project back to the residual pathway via addition。

And so you go from the the inputs to the targets， only the plus and plus and plus。

And the reason this is useful is because during that propagation。 Remember。

 from our micrograd video earlier， edition distributes gradients equally to both of its branches。

That fed as the input。 And so the supervision or the gradients from the loss basically hop through every addition node all the way to the input。

 and then also fork off into the residual blocks。But basically。

 you have this gradient superhighway that goes directly from the supervision all the way to the input。

 unimpeded。And then these residual blocks are usually initialized in the beginning。

 So they contribute very， very little， if anything， to the residual pathway。 They。

 they are initialized that way。 So in the beginning， they are almost kind of like not there。

 But then during the optimization， they come online line over time。 and they start to contribute。

 but at least at the initialization， you can go from directly supervision to the input gradient is unimpeded and just close。

 And then the blocks over time kick in。

![](img/bf8e317787d215eeac53dc1b82b1c757_66.png)

And so that dramatically helps with the optimization。 So let's implement this。

 So coming back to our block here， basically what we want to do is。We want to do x equals x plus。

Sollf attention and x equals x plus solve that T forward。So this is X。

 and then we fork off and do some communication and come back。

 and we fork off and we do some computation and come back。

So those are residual connections and then swinging them back up here。

We also have to introduce this projection。So N then dot linear。And this is going to be from。

After we cancatenate this， this is the size and embed。

So this is the output of the soft tension itself。But then we actually want the to apply the projection。

And that's the result。So the projection is just a linear transformation of the outcome of this layer。

So that's the projection back into the virtual pathway。And then here in a feet forward。

 it's going to be the same thing。 I could have a self thought projection here as well。

 But let me just simplify it。And， let me。Couple it inside the same sequential container。

And so this is the projection layer going back into the residual pathway。And so。



![](img/bf8e317787d215eeac53dc1b82b1c757_68.png)

That's， well， that's it。 So now we can train this。 So I implementing one more small change。

When you look into the paper again， you see that the dimensionality of input and output is 5。

12 for them。 And they're saying that the inner layer here in the feet forward has dimensionality of 2048。

 So there's a multiplier of 4。And so the inner layer of the feet forward network。



![](img/bf8e317787d215eeac53dc1b82b1c757_70.png)

Should be multiplied by  four in terms of channel sizes。 So I came here。

 and I multiplied four times embed here for the feet forward。

 And then from four times N embed coming back down to an embed。

 When we go back to the project to the projection。 So adding a bit of computation here and growing that layer that is in the residual block on a side of the residual pathway。

And then I train this。 and we actually get down all the way to 2。08 validation loss。

 And we also see that the network is starting to get big enough that our train loss is getting ahead of validation loss。

 So we start to see like a little bit of overfitting。And our our。

Generations here are still not amazing， but at least you see that we can see like is here this now。

 grief sank。Like this starts to almost look like English。 So， yeah。

 we're starting to really get there。 Okay， and the second innovation that is very helpful for optimizing very deep neural works is right here。

 So we have this addition。 Now。 that's the residual part。

 But this norm is referring to something called layer norm。



![](img/bf8e317787d215eeac53dc1b82b1c757_72.png)

So layer norm is implemented in Pytorch， it's a paper that came out a while back here。嗯。

And layer norm is very， very similar to bashm。 So remember back to our make more series Part 3。

 we implemented batch normalization。And batch normal basically just make sure that across the batch dimension。

 any individual neuron had unit Gaussian distribution。 So it was0 mean and unit standard deviation。

 one standard deviation output。So what I did here is I'm copy pasting the bathroom 1 D that we developed in our make more series。

And see here， we can initialize， for example， this module， and we can have a batch of 32。

 100 dimensional vectors feeding through the ba layer。So what this does is， it guarantees。

That when we look at just the zeroth column。It's a zero mean one standard deviation。

So it's normalizing every single column of this input。Now。

 the rows are not going to be normalized by default because we're just normalizing columns。

So let's not implement layer norm。It's very complicated。We come here， we changed this from 0 to one。

So we don't normalize the columns。 We normalize the rows。And now we've implemented Laor。

So now the columns are not going to be normalized。But the rows are going to be normalized for every individual example。

 its 100 dimensional elect is normalized in this way。

And because our computation now does not span across examples。

 we can delete all of this buffer stuff because we can always apply this operation and don't need to maintain any running buffers。

So we don't need the buffers。We don't。There's no distinction between training and test time。

And we don't need these running buffers。 We do keep gamma and beta。 We don't need the momentum。

 We don't care if it's training or not。And this is now a layer norm。

And it normalizes the row instead of the columns。 And this here。Is identical to basically， this here。

So let's now implement layer norm in our transformer。 Before I incorporate the layer norm。

 I just wanted to note that， as I said， very few details about the transformer have changed in the last five years。

 but this is actually something that slightly departs from the original paper。

You see that the add and norm is applied after the transformation。

But now it is a bit more basically common to apply the layer norm before the transformation。

 so there's a reshuffling of the layer norms。So this is called the pre normor formulation。

 and that's the one that we're going to implement as well。

 So slight deviationation from the original paper。

![](img/bf8e317787d215eeac53dc1b82b1c757_74.png)

Basically， we need to layer norms。 La norm 1 is an N dot layer norm。And we tell it how many。

 what is the embedding dimension？And we need the second layer norm。And then here。

 the larums are applied immediately on X。So solve that layerer 1 in apply to next。And salt out larum。

 too applied on X before it goes into self attention and feed forward。

And the size of the layerome here is n embeds of 32。

So when the layer norm is normalizing our features。



![](img/bf8e317787d215eeac53dc1b82b1c757_76.png)

It is the normalization here。Happens the mean and the variance are taken over 32 numbers。

 So the batch and the time act as batch dimensions， both of them。



![](img/bf8e317787d215eeac53dc1b82b1c757_78.png)

So this is kind of like a perk token transformation that just normalizes the features and makes them unit mean unit Gaussian at initialization。



![](img/bf8e317787d215eeac53dc1b82b1c757_80.png)

But， of course， because these layer norms inside it have these gamma and beta trainable parameters。

The layer normal will eventually create outputs that might not be unit Gasian。

 but the optimization will determine that。

![](img/bf8e317787d215eeac53dc1b82b1c757_82.png)

So for now， this is incorporating the layer norms and let's train them up。Okay， so Ill let it run。

 and we see that we get down to 2。06， which is better than the previous 2。08。

 So a slight improvement by adding the layer norms。

 And I'd expect that they help even more if we had bigger and deeper network。

One more thing I forgot to add is that there should be a layer norm here also typically as at the end of the transformer and right before the final linear layer that decocodes into vocabulary。

 so I added that as well。So at this stage， we actually have a pretty complete transformer according to the original paper。

 and it's a decoder only transformer。 I'll talk about that in a second。 But at this stage。

 the major pieces are in place so we can try to scale this up and see how well we can push this number。



![](img/bf8e317787d215eeac53dc1b82b1c757_84.png)

![](img/bf8e317787d215eeac53dc1b82b1c757_85.png)

Now， in order to scale up the model， I had to perform some cosmetic changes here to make it nicer。

 So I introduced this variable called N layerer， which just specifies how many layers of the blocks we're going to have。

 I create a bunch of blocks， and we have a new variable number of heads， as well。

I pulled out the layer norm here。 And so this is identical。 Now。

 one thing that I did briefly change is I added dropout。

So dropout is something that you can add right before the residual connection back。

Or right before the connection back into the residual pathway。

So we can drop out that as the last layer here。We can drop out here at the end of the multihead sh as well。

And we can also drop out here when we calculate the。Basically， affinities and after the softm。

 we can drop out some of those so we can randomly prevent some of the notes from communicating。



![](img/bf8e317787d215eeac53dc1b82b1c757_87.png)

And so dropout comes from this paper。From 2014 or so。And。Basically， it takes your neural mat。

And at randomly， every forward backward pass shuts off some subset of neurons。

So randomly drop them to zero。And trains without them。

 And what this does effectively is because the mask of what's being dropped out is changed every single four backward pass。

 It ends up kind of training an ensemble of sub networks。And then at test time。

 everything is fully enabled。 and kind of all of those sub works are merged into a single ensemble。

 if you can， if you want to think about it that way。

So I would read the paper to get the full detail for now。

 we're just going to stay on the level of this is a regularization technique。

 and I added it because I'm about to scale up the model quite a bit。

 and I was concerned about overfitting。

![](img/bf8e317787d215eeac53dc1b82b1c757_89.png)

So now when we scroll up to the top， we'll see that I changed a number of hyperparameters here about our neural nu。

 So I made the batch size be much larger。 now was 64。I changed a block size to be 2，56。

 So previously it was just 8，8 characters of context。 Now。

 it is 256 characters of context to predict the 257th。

I brought down the learning rate a little bit because the neuralNe is now much bigger。

 so I brought down the learning rate。The embedding dimension is not 384， and there are six heads。

So 384 divide 6 means that every head is 64 dimensional as it， as a standard。

And then there're also going to need six layers of that。And the dropout will be a pointtu。

 So every forward backward pass 20% of all these。Intermediate calculations are disabled and dropped to zero。

And then I already trained this and I ran it， so drum roll， hell old does it perform？

So let me just scroll up here。We get a validation loss of 1。48。

 which is actually quite a bit of an improvement on what we had before， which I think was 2。07。

 So we went from 2。07 all the way down to 1。48， just by scaling up this neural nut with the code that we have。

And this， of course， ran for a lot longer。 This may be trained for。

 I want to say about 15 minutes on my a 100 GPU。 So that's a pretty good GPU。

 And if you don't have a GPU， you're not going to be able to reproduce this on a CPU， this would be。

 I would not run this on the CPU or a MacBook or something like that。

 You'll have to bring down the number of layers and the embedding dimension and so on。

But in about 15 minutes， we can get this kind of a result， and I'm printing。

Some of the Shakespeare here。 But what I did also is I printed 10000 characters。 So a lot more。

 And I wrote them to a file。And so here we see some of the outputs。

So it's a lot more recognizable as the input text file。 So the input text file， just for reference。

 looked like this。So there's always like someone speaking in this matter and。

Our predictions now take on that form。Except， of course。

 they're nonsical when you actually read them。So。It is every crty bee house。 O。

 those preparationbation。We get heat。You know。O， ho， sent me you， mighty Lordd。ふふ。😊，Anyway。

 so you can read through this。 It's nonsensical， of course。

 but this is just a transformer trained on the character level for 1 million characters that come from Shakespeare。

 So theyre sort of like blabbber on in Shakespeare like manner， but it doesn't of course。

 make sense at this scale。But I think， I think still a pretty good demonstration of what's possible。

So， now。I think that kind of like concludes the programming section of this video。

 We basically kind of did a pretty good job of implementing this transformer。

 but the picture doesn't exactly match up to what we've done。

 So what's going on with all these additional parts here。

 So let me finish explaining this architecture and why it looks so funky。



![](img/bf8e317787d215eeac53dc1b82b1c757_91.png)

Basically， what's happening here is what we implemented here is a decoder only transformer。

 So there's no component here。 This part is called the encoder。

 and there's no cross attention block here。 Our block only has a self attention and the feet forward。

 So it is missing this third in between piece here。 This piece does cross attention。

 So we don't have it and we don't have the encodeder， we just have the decoder。

 And the reason we have a decoder only。Is because we are just generating text and it's unconditioned on anything or just we're just blabbing on according to a given data set。

What makes it a decoder is that we are using the triangular mask in our transformer。

 So it has this auto aggressivegressive property where we can just go and sample from it。

So the fact that it's using the triangular mask to mask out the attention makes it a decoder。

And it can be used for language modeling。Now， the reason that the original paper had an encoder decoder architecture is because it is a machine translation paper。

 so it is concerned with a different setting in particular。It expects some tokens that encode， say。

 for example， French。And then it is expected to decode the translation in English。

So you typically these here are special tokens， so you are expected to read in this and condition on it。

And then you start off the generation with a special token called Start。

 so this is a special new token that you introduce and always place in a beginning。

And then the network is expected to output neural networks are awesome。

 and then a special end token to finish a generation。

So this part here will be decoded exactly as we we've done it。 Neural networks are awesome。

 will be identical to what we did。😊，But unlike what we did。

 they want to condition the generation on some additional information。 And in that case。

 this additional information is the French sentence that they should be translating。

So what they do now？Is the bringing the encoder？Now， the encoder reads this part here。

 So we're only going to take the part of French， and we're going to create tokens from it exactly as we've seen in our video。

 And we're going to put a transformer on it。 But there's going to be no triangular mask。

 And so all the tokens are allowed to talk to each other as much as they want。

 And they're just encoding whatevers the content of this French sentence。Once they've encoded it。

They， they basically come out in the top here。And then what happens here is in our decoder。

 which does the language modeling， there's an additional connection here to the outputs of the encoder。

And that is brought in through cross attention。So the queries are still generated from X。

 But now the keys and the values are coming from the side。

 The keys and the values are coming from the top generated by the nodes that came outside of the encoder。

And those tops， the keys and the valleys there， the top of it。

Feed in on a side into every single block of the decoder。

 And so that's why there is an additional cross attention。And really。

 what is doing is its's conditioning the decoding， not just on the past of this current decoding。

 but also on having seen the full， fully encoded French prompt， sort of。

And so it's an encoder decoder model， which is why we have those two transformers an additional block and so on。

 So we did not do this because we have no， we have nothing to encode。 There's no conditioning。

 We just have a text file， and we just want to imitate it。

 And that's why we are using a decoder only transformer exactly as done in G。

Okay so now I wanted to do a very brief walkthrough of nanoGPT。

 which you can find in my Gitthub and nanoGPT is basically two files of interest。

 there's trained uppi and model uppi。Trink that pie is all boiler plate code for training the network。

 It is basically all the stuff that we had here is the training loop。



![](img/bf8e317787d215eeac53dc1b82b1c757_93.png)

It's just that it's a lot more complicated because we are saving and loading checkpoints and pretrained weights。

 and we are decaying the learning rate and compiling the model and using distributed training across multiple nodes or GPUus。

 So the train that pie gets a little bit more hairy， complicated。 There's more options， etc cetera。



![](img/bf8e317787d215eeac53dc1b82b1c757_95.png)

But the model that by should look very， very similar to what we've done here。 In fact。

 the model is almost identical。So first， here we have the causal self attention block。

 and all of this should look very， very recognizable to you。 We're producingqueries's keys values。

 We're doing dot products， We're masking， applying soft maxs， optionally dropping out。

 And here we are pooling the values。What is different here is that in our code。



![](img/bf8e317787d215eeac53dc1b82b1c757_97.png)

I have。Separate it out the multi headeded attention into just a single individual head。

And then here I have multiple heads， and I explicitly concatenate them。



![](img/bf8e317787d215eeac53dc1b82b1c757_99.png)

Whereas here， all of it is implemented in a batched manner inside a single causal self attention。

 And so we don't just have a B and a T and a C dimension。 We also end up with a fourth dimension。

 which is the heads。And so it just gets a lot more sort of hairrry because we have four dimensional array tensors now。

 but it is equivalent mathematically， so the exact same thing is happening as what we have。

 it's just it's a bit more efficient because all the heads are now treated as a batch dimension as well。



![](img/bf8e317787d215eeac53dc1b82b1c757_101.png)

![](img/bf8e317787d215eeac53dc1b82b1c757_102.png)

Then we have the multi perceptron， it's using the Gaoon non nonlinearity。

 which is defined here except instead of Relu， and this is done just because Open I used it and I want to be able to load their checkpoints。

The blocks of the transformer are identical。 The communicate in the compute face， as we saw。

 And then the G will be identical。 We have the position encodings， token encodings， the blocks。

 the layer norm at the end， the final linear layer。And this should look all very recognizable。

And there's a bit more here because I'm loading checkpoints and stuff like that。

 I'm separating out the parameters into those that should be weight decayed and those that shouldn't。



![](img/bf8e317787d215eeac53dc1b82b1c757_104.png)

But the generate function should also be very， very similar。 So a few details are different。

 but you should definitely be able to look at this file and be able to understand a lot of the pieces now。

So let's now bring things back to Cha GT。What would it look like if we wanted to train Chatpiity ourselves and how does it relate to what we learned today？

While to train the chat EP， there are roughly two stages。

 First as the pre training stage and then the fine tuning stage。In the pre training stage。

 we are training on a large chunk of internet and just trying to get a first decoder only transformer to babel text。

 So it's very， very similar to what we've done ourselves。



![](img/bf8e317787d215eeac53dc1b82b1c757_106.png)

Except we've done like a tiny little baby pre training step。 And so in our case。

 this is how you print a number of parameters。 I printed it， and it's about 10 million。

 So this transformer that I created here to create little Shakespeare transformer。

Was about 10 million parameters。Our data set is roughly 1 million characters。

 so roughly 1 million tokens。 But you have to remember that opening eyes is different vocabulary。

 They're not on a character level。 They use these subward chunks of words。

 And so they have a vocabulary of 50000 roughly elements。

 And so their sequences are a bit more condensed。So our data， the Shakespeare dataset。

 would be probably around 300，000 tokens in the Open AI vocabulary， roughly。

So we trained about 10 million primary model and roughly 300，000 tokens。



![](img/bf8e317787d215eeac53dc1b82b1c757_108.png)

Now， when you go to the Juputy3 paper。

![](img/bf8e317787d215eeac53dc1b82b1c757_110.png)

And you look at the transformers that they trained。

They trained a number of transformers of different sizes。

 but the biggest transformer here has 175 billion parameters， so ours is again，10 million。

They used this number of layers in the transformer。 This is the N in bed。This is the number of heads。

 and this is the head size。And then this is the batch size， so ours will 65。

And the learning rate is similar。 Now， when they train this transformer。

 they trained on 300 billion tokens。 So， again， remember， ours is about 300000。

 So this is about a million fold increase。 And this number would not be even that large by today standards。

 You'd be going up 1 trillion above。So they are training a significantly larger model。

On a good chunk of the internet。And that is the pre training stage。 But otherwise。

 these hyperparameter should be fairly recognizable to you。

 and the architecture is actually like nearly identical to what we implemented ourselves。

But of course， it's a massive infrastructure challenge to train this。

 You're talking about typically thousands of GPUs having to you know talk to each other to train models of this size。

 So that's just a pretraining stage。Now， after you complete the pre training stage。

 you don't get something that responds to your questions with answers and is not helpful and etc cea。

 you get a document complete。

![](img/bf8e317787d215eeac53dc1b82b1c757_112.png)

Right so it babbles， but it doesn't babble Shakespeare。 It babbles Internet。

 It will create arbitrary news articles and documents。

 and it will try to complete documents because that's what it's trained for。

 It's trying to complete the sequence。

![](img/bf8e317787d215eeac53dc1b82b1c757_114.png)

So when you give it a question， it would just potentially just give you more questions。

 It would follow with more questions。 It will do whatever it looks like。

 the some close document would do in the training data on the Internet。

 And so who knows you're getting kind of like undefined behavior。

 It might basically answer with two questions with other questions。 It might ignore your question。

 It might just try to complete some news article。 It's totally undermined as we say。

So the second fine tuning stage is to actually align it to be an assistant。

 and this is the second stage。

![](img/bf8e317787d215eeac53dc1b82b1c757_116.png)

And so this ChayPT block post from Open eye talks a little bit about how this stage is achieved。



![](img/bf8e317787d215eeac53dc1b82b1c757_118.png)

We basically。There's roughly three steps to this stage。

 So what they do here is they start to collect training data that looks specifically like what an assistant would do。

 so they have documents that have the format where the question is on top and then an answer is below。

 and they have a large number of these， but probably not on the order of the internet。

 this is probably on the order of maybe thousands of examples。

And so they then fine tune the model to basically only focus on documents that look like that。

 And so you're starting to slowly align it。 So it's going to expect a question at the top and it's going to expect to complete the answer。

And these very， very large models are very sample efficient during their fine tuning。

 So this actually somehow works。But that's just step 1。 That's just fine tuning。

 So then they actually have more steps where， okay。

 the second step is you let the model respond and then different raters look at the different responses and rank them for their preference as to which one is better than the other。

 They use that to train a reward model。 So they can predict basically using a different network。

 How much of any candidate response would be desirable。And then once they have a reward model。

 they run PPO， which is a form of policyi gradient reinforcement learning optimizeizer。

To fine tune this sampling policy so that the answers that the G Cha GPT now generates are expected to score a high reward。

 according to the reward model。And so basically， there's a whole alignning stage here or fine tuning stage。

 It's got multiple steps in between there as well， and it takes the model from being a document Compr to a question answerer。

 And that's like a whole separate stage。 A lot of this data is not available publicly。

 It is internal to open an eye， and it's much harder to replicate this stage。

And so that's roughly what would give you a chat G。 And nanoGPT focuses on the pre training stage。

 Okay， and that's everything that I wanted to cover today。

 So we trained to summarize a decoder only transformer following this famous paper attention is all you need from 2017。



![](img/bf8e317787d215eeac53dc1b82b1c757_120.png)

And so that's basically a GT。 We trained it on a tiny Shakespeare， and got sensible results。



![](img/bf8e317787d215eeac53dc1b82b1c757_122.png)

All of the train code is roughly。200 lines of code。I will be releasing this code base。

 So also it comes with all the Gitlog commits along the way as we built it up。



![](img/bf8e317787d215eeac53dc1b82b1c757_124.png)

In addition to this code， I'm going to release the notebook。 of course， the Google Coab。



![](img/bf8e317787d215eeac53dc1b82b1c757_126.png)

And I hope that give you a sense for how you can train。These models， like say， G3。

 that will be architecturally basically identical to what we have。

 but they are somewhere between 10000 and 1 million times bigger， depending on how you count。

And so that's all I have for now we did not talk about any of the fine tuning stages that would typically go on top of this。

 so if you're interested in something that's not just language modeling。

 but you actually want to you know say perform tasks or you want them to be aligned in a specific way or you want to detect sentiment or anything like that。

 basically anytime you don't want something that's just a document Compr。

 you have to complete further stages of fine tuning which we did not cover。And that could be simple。

 supervised fine tuning， or it can be something more fancy like we see in ChaBT。

 we actually train a reward model and then do runs of PPO to align it with respect to the reward model。



![](img/bf8e317787d215eeac53dc1b82b1c757_128.png)

![](img/bf8e317787d215eeac53dc1b82b1c757_129.png)

So there's a lot more that can be done on top of it。 I think for now。

 we're starting to get to about two hours mark。 So I'm going to。Kind of finish here。

I hope you enjoyed the lecture and yeah， go forth and transform see there。



![](img/bf8e317787d215eeac53dc1b82b1c757_131.png)