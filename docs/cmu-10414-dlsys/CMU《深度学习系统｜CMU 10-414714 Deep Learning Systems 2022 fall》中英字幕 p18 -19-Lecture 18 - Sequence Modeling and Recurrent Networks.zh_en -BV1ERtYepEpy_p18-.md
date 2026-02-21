# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p18 -19-Lecture 18 - Sequence Modeling and Recurrent Networks.zh_en -BV1ERtYepEpy_p18-

All right， hi everyone， welcome back to Deep learninging systemss Alegrithms and implementationm。

Today we're going to talk about our first of two lectures。

 this is sort of the more algorithmic lecture， next will be the implementation lecture on sequence modeling and recurrent networks。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_1.png)

So to give a quick outline for the lecture today。We're first going to talk about sequence modeling kind of in the general case。

 how does sequence modeling differ from the types of machine learning problems we've been dealing with so far？

Then I'm going to talk about one particular method for handling sequence models in or sequence modeling in deep networks。

 namely recurrent neural networks， which is sort of a whole class of networks that we'll talk about today。

We'll then talk about one particular instantiation of a recurrent neural network。

 which is an LSTM or long short term memory。And finally。

 we'll end by briefly talking about how we can use the techniques of our current networks and LSTMs to move beyond what I'm calling simple sequential models to more maybe complex prediction tasks that still involve some sort of temporal element。

All right， so let's start off with and jump into the problem of sequence modeling in general。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_3.png)

So sequence modeling differs a bit from the kind of problems we've been dealing with so far。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_5.png)

So so far we've been dealing with prediction problems for the most part。

 at least when except for the generative modeling lectures we had recently。

 for the most part we've been dealing with prediction problems where we're given is pairs of X and Y variables those are the inputs and target outputs of our system right so we're given a collection of these things。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_7.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_8.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_9.png)

And the implicit assumption of most of our lectures thus far is that these input output pairs。

 the collection were given， so our whole data set namely know XX1 to XM， etc。

 is what's called independent and identically distributed or IID。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_11.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_12.png)

And what that means in some sense is there's no inherent ordering to these points it doesn't really matter if you do them in if you see the first one。

 first second， one second， there's no inherent ordering and all that really matters here is the collection of examples we're getting that's been our implicit assumption so far and we see that when we do things like reorder the batches So if we reorder the batch to or randomly sample our examples to create a mini batch that sort of implicitly using this assumption that our inputs are in some sense independent from each other。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_14.png)

But in practice， of course， this is not always the case。

 There are many cases where the input output pairs。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_16.png)

For some sort of dependent sequence right and in particular。

 we're going to consider the case here where they form some sort of sequential set of input output pairs that will sort of use figures like this to denote。

 So these figures like there's an x1 that leads to Y1 but then it also influences somehow x2。

 which produces y2， etc。 And this is not sort of a to be clear。

 this is not kind of a strict causal diagram or anything like this。

 it's just sort of a diagram here that we use to remind ourselves that this problem that we're talking about today。

 where we have X Y pairs still， but where the X Y pairs are now ordered sequentially。

 we're just using this notation to remind us that these things are dependent in this way。

 so that's really what what this nottation here is for。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_18.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_19.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_20.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_21.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_22.png)

Now。One other change we'll make here is that we're not going to use for the rest of this lecture。

 know for the most part we've used kind of superscripts here。

 X superscript I and little parentheses here to differentiate， I guess from expon。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_24.png)

But we've been using a notation to sort of denote the Ith example in our data right。

 and we're going to move away from that today because to be honest。

 this' is just not very common in temporal modeling。

 what's much more common is to use subscripts to denote the index in time that an example appears in。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_26.png)

But it's very important to note that in this notation here。In general， for all these things。

 Xt in this notation would be a vector， so Xt would be some vector， say， in RN。Previously。

 we've been using the subscripts to index into a vector， so x1 would be the first element of x。

But we're not going to be doing that here for simplicity。

 We're going to assume that kind of everything is a vector。 So we're going to。

We're going to make this simplification， which is somewhat。

Of a hassle because now if we want to refer to the I element of this vector。

 we have to do weird things like this and stuff like that， but for the most part。

 we don't do too much work that looks at the individual entries in vectors。

 we typically operate on them as vectors so it's much more convenient to use subscripts for the sequence dimension ie the time dimension and we're going to use that for the rest of the lecture today。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_28.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_29.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_30.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_31.png)

嗯。And so what we'll actually see is sort of figures like this that sort of show the temporal dependencies and the temporal sequence of things。

 but using subscripts here to denote where things are in the sequence。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_33.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_34.png)

All right， now let me give a few examples of tasks that are sequence dependent。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_36.png)

And one good example of this would be something like part of speech tagging in natural language。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_38.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_39.png)

So the task here is that we want to take。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_41.png)

A sequence of words， like the quick brown fox jumped， etc。

 and translate or rather predict from each of these the part of speech that each one of these is。

 so browns， adjective， fox a noun， etc。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_43.png)

And the crucial point that I want to make here about this task。

Is that this is a task that shows the importance of。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_45.png)

Sequence modeling and the fact is a sequence。Because if we had another element here， like it jumped。

Well。The part of speech of well。Cannot be predicted。Just from that word alone。

Right well can be either a adverb describing how the fox jumped or it can be a noun right describing like a well in the ground and things like this right so the important part about sequence modeling to keep in mind is that not only can the temporal dependence kind of help us make better predictions。

In some cases， the temporal sequence is crucial for predicting at all because without the temporal sequence。

 there's just no way to predict what the next or what the true kind of label of this word is so if we don't have verb。

 say beforehand， it would just be very hard to know what the what the correct prediction would be for this part of speech here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_47.png)

Another nice example is a speech to text。 So the the the task carriers were given a bunch of audio or something like this and we want to predict the。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_49.png)

The speech or the words， the text of all these things right so we want to give in some sequence here。

 So this is actually a picture of me recording the phrase deep learning systems。

 algorithms and the implementation， and let's even assume that we're given sort of the correct boundaries。

 let's even assume that we're sort of given all the audio boundaries here somehow it doesn't really matter how we get that of course。

 in reality this is not given to you and you have to figure out what the word boundaries are but if we're given these word boundaries we now another sequence problem another sequence prediction problem because we're given a sequence of these inputs of audio here。

 we have to predict from them the。😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_51.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_52.png)

Word or the text that they correspond to。And again， to use a somewhat。

A bit looser analogy here because I guess this example here wouldn't course with a different word boundaries in this case。

 but another key element of text a speech text is that it's extremely important to take in the word ordering and the temporal sequence here and also just the dependencies between words in general。

 there's a famous sort of example of how hard it is to recognize speech。

 to recognize speech which if you interpret it differently would sound could sound like recognize speech and it just sort of highlights the fact that not only does the temporal sequence matter。

 its sort of unusual to say the words recognize beach but it really the context and the sequence of words both matter in this prediction problem。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_54.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_55.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_56.png)

And the last example I want to highlight here is is a。

Sequence prediction problems has taken on special meaning in the past few years due to its extensive use in things like language models。

mAnd this is a setting of autoregressive prediction。

 especially auto aggressivegressive prediction for things like language。So to be very clear。

 auto aggressivegressive prediction is not。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_58.png)

The only sequence prediction problem there is there's lots of sequence prediction problems like the kind I've already said。

 but autoregressive prediction is one special case of sequence prediction that has again taken on an outsized importance in recent years due to it being at the foundation of large language models。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_60.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_61.png)

And the idea here is that we want to also make a sequential prediction task。

 but so we have some input sequence， which is again， for example， a English sentence。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_63.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_64.png)

But instead of predicting the part of speech or things like this。

 the task at each location is to predict the next term in the sequence Okay。

 so at this point after the quick， we want to predict the word brown After sort of getting the quick brown。

 we want to predict f， etc， right so given all the words up until now。

 we want to predict the next word， or this can all of course， operate on not words。

 but on characters are on tokens， kind of somewhere in the middle， but this is the basic idea here。

 right。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_66.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_67.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_68.png)

And this is a very common problem， not just in language modeling。

 but also in things like time series forecasting more generally and actually many use cases involve autoaggressive prediction。

 however， right now sort of most well known for these applications in language modeling。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_70.png)

And so what I want to emphasize here is again， this is not all sequence prediction， of course。

 is autoaggressive， but this is one very particular example of a sequence prediction problem that we will come back to a few times later in this course。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_72.png)

All right， so with that as some and again， of course， the the examples here is that。

The important point to note here is that this prediction problem so predicting the quick brown and then predicting f from it。

 this depends not just on the word brown， so if you just had the single word of the sequence。

 it would be very hard to predict what the next one would be， but given the whole prior sequence。

 even though you can't predict of course exactly you can do a much better job at capturing the distribution over next tokens than you would be able to normally。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_74.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_75.png)

Al right， so let's talk now about one possible now deep network model。

It's arguably deep network depending on your perspective here。

 but we'll go ahead and call it a deep network。One deep network model for solving this problem。

 which is the model of recurrent neural networks。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_77.png)

So the basic idea of a recurrent neural network。Is that we model。

A network that kind of in some sense mimics the temporal structure of our input sequence。All right。

 so we have our input sequence here。X1， x2， x3。But instead of trying to directly predict Y1。

 y2 and Y3 from this。We， in some sense， modulate our predictions through a hidden state。

Which is maintained over time。😡，And in particular， if we look at the update rule for a given hidden state。

This is a function not just of the input of that time， but also of the previous hidden state。

And then we we want to predict our output。We make this a function， just。Of the hidden state。

So we can write this more formally now， we can write this as our hidden state Yt Ht here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_79.png)

Is equal to some function， F， some nonlinear functions， so this could be like the sigmoid。

 like the value， like anything else。Some linear function of。A。

Matrix W HH times our previous hidden state， H T minus1。Right？So this is a sort of。In some sense。

 like a multilayer perceptron， of course， you can add more structure to this too。

 but so these could be things like convolutions if you wanted。

 but more common to sort of start off with things is just thinking of the hidden state as a vector。

 thinking of the I'm thinking of the mapping from our previous hidden state to our current hidden state as as a matrix。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_81.png)

Then plus some other matrix， WHx。Times Xt。Plus， what I'm calling the bias of H。

So what's a biased term of H。In particular， let's also look at the sizes of these things here。

 So we're not going to dwell too much on the sizes of these things。

 but I should give some some sort of simple examples of what these things could be。

 So here H T could be a vector， say in R D。 so it would be a D dimensional hidden state。

Let's say that X T。It would be。An n dimensional hidden vector。And just for the sake of it。

 let's say that YT。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_83.png)

This clearly could be anything else。 but let's just make Y T real valued for now。

 Maybe actually let you know what， let's actually just make it an RK。

 So it could be something like move We've used output values in RK before。

 So let's actually use Y being an output value in RK。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_85.png)

All right， and what that would imply， of course。Is that W？H， H would be a D by D matrix。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_87.png)

Move this over。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_89.png)

W would be a D by D matrix， WHh would be D by D matrix。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_91.png)

WHX would be， well， it has to map。呃。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_93.png)

X and dimensional inputs to D dimensional hidden states。 So that has to be a。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_95.png)

D by N matrix。And B here， B。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_97.png)

H would of course then be a D dimensionsal vector。So that's our state update for the H state。

And similarly， we can write a function that sort of gives our predicted outputs Yt。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_99.png)

That would be some other nonlinear function of some matrix WYH applied to our hidden state of time T plus some bias。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_101.png)

For our output。We're here again， W。Y H would be， in this case， a K by。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_103.png)

The dimensional matrix。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_105.png)

And B， Y would be a K dimensional vector。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_107.png)

The sizes aren't too important here， would I really want to emphasize are the updates？



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_109.png)

But and then the future I actually won't give all the sizes always for all these things。

 I'll sort of assume that you know the size it would be in order for these things to make the multiplications work。

 but I want to sort of lay it out here explicitly。Now， to be clear。

 what's happening here is that we are taking our previous when we're creating this current state here。

Again， what our update equation says is that this hidden state here is some function of our past hidden state and our input。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_111.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_112.png)

And the really important point to keep in mind here。Is that our hidden state。

 because our hidden state， you can kind of see this from the computational graph itself。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_114.png)

Because our hidden state depends on the previous hidden state。

 which depends on the previous hidden date of that， which et cetera， et cetera， in some sense。

 the hidden state at time T。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_116.png)

Captures or can capture in the ideal case。All the inputs it has seen up until that point。

Because the hidden state H3 say is a function。Imp plus is a function kind of。

via this recursive procedure of x1 of x2 and of x3 right there is a computational chain that leads from x1 to x3 from x2 to x3 and of course from x3 to sorry for x1 to H3 from x2 to H3 and from x3 to x to H3 right so this hidden state here and this is actually a really important point。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_118.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_119.png)

It can capture or in some sense， summarize all the information up until that point in the sequence。

And in fact， if we do a good job。Of learning this recurrent neural network。

 then the hidden state really should capture all the information that we need to solve our prediction task at that point。

All right， so that is in a nutshell， the structure of a simple recurrent neural network。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_121.png)

Now the next obvious question is how do we go about actually training a recurrent neural network。

 how do we in fact learn the parameters of our network。

 which would be in this case these matrices right how do we learn WH， W，HHWx， HX， the biases， etc。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_123.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_124.png)

And when you think about it。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_126.png)

Because these same functions here are used。To form all our predictions， right， when you form H1。

 you use W， you use these terms when you form y1， etc。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_128.png)

嗯。😊，These are the parameterss of our network。And we want to adjust these parameters so as to make our outputs here match some target outputs。

😡。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_130.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_131.png)

So the way we're going to write that is that we have some set of input and output targets。

 and here I'm going to be a little bit。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_133.png)

changenge data slightly from what you saw previously。

 but I'm going to refer because it's common to refer to the Y's as the outputs of the R&N。

 I'm going to refer to the targets of our production problem as y star。

 so you know y star1 would be the thing that we wanted to predict at time1， y star 2， et cetera。

 up to some time frame， y star T。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_135.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_136.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_137.png)

可以。So this is the target sequence we have。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_139.png)

And now if you think about it。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_141.png)

I think personally， it would be pretty challenging to， by hand， derive all the gradients of。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_143.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_144.png)

Some loss of， you know， between my entire sequence that I predicted and this target sequence for。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_146.png)

To derive the gradient of this loss with respect to all the relevant parameters of my network。

 namely all my weights and all my bias terms。Okay， but the good news about。RNN training。

Is that we don't need to worry about this We don't need to we don't need to worry about the precise form of the gradients because we can make use here of our automatic differentiation tools and this is sort of the key aspect of that I would emphasize of RnNs which sort of which really codifies how great automatic differentiation is so I want to show you now kind of what an optimization loop would look like for an RnN we form some optimizer like our SGD or atom E formed a needle。

 we'd have our parameters here which would be our weights。

 all the weights and all the biases right and now we would just sort of make our predictions so we initial our first hidden state to be zero this is actually an important point that I didn't quite mention in the last slide there's no equation for H0 there's no sort of notion of what this is and in fact when we talk about turning long sequences。

 we will talk about this more in the next lecture and truncated back propagation through time is what we're gonna to talk about。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_148.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_149.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_150.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_151.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_152.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_153.png)

Lecture。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_155.png)

But for now， the way to think about H0 is just initialize it's zero， so I mean， of course。

 with a recurrent network like this， you have to pick what your first hidden state is， right？



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_157.png)

You can't， can't form age there's no sequence yet， you can't form anything。

 so just just make it zero， right that's sort of the simple， the simple thing to do。

So set your initial state to be0 such a loss to be0。 and then iterate over your whole sequence。

 So from one to T。 so from one to T， you form your next hidden state， right。

 which is this update equation。😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_159.png)

A function of our previous hidden state and our current input。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_161.png)

Form the output prediction， which is again a function of our current hidden state。

And then compute a loss between our prediction Y T and the true output y star T。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_163.png)

And I'm running this in sort of the pseudocode for a reason here。

 which is that I don't want to write this out algorithmically algorithmically。

 this is just sort of the equation you saw previously plus some loss between y and y star。

 But what I definitely don't want to do is actually derive what the gradient is expected WHH of this loss。

 because it depends on know the I mean， WH affects all these terms， right。

 there's there's influence on every H T on WH and all the terms that came before it。

 And running at this gradient would be would be quite。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_165.png)

Would be quite cumbersome。In fact， people used to do that right used to be when you sort of derived RnNs。

 you have derive these long chain rule gradients and it's not that bad。

 you can certainly do it and you can write them in recursive form and all this kind of stuff。

 but boy， it's so much easier to just write this if you have because we've set this up this whole chain of the dependency in needle or in our automatic differentiation toolkit we can compute all the gradients by just to call the loss do backwards and this really。

 really showcases the power of these automatic differentiation tools so we compute our loss。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_167.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_168.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_169.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_170.png)

And then we just call up that step。Like thats that's the optimization method and this whole procedure here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_172.png)

Is often called back propagation through time。Through。Time。Or just BP T T。That a be。BPTD。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_174.png)

Back propagation through time Okay， so this is the this is the algorithm that we typically referred to as back propagation through time。

 it just basically means that we are explicitly unrolling our recurrent network over some time sequence。

😊，And then we are taking gradient steps over that whole time sequence。And as I said， next lecture。

 we'll talk about a slight variant of this that actually if we don't want to unroll our entire sequence。

 which could be intractable for very large sequences。

 you can approximate this by just truncating this procedure at various points。

 but again we'll talk about that next lecture。All right。

 so that's that's actually all I'm going to say about training RNNs right and the beauty of it is that that's all I have to say because we've developed this。

Great automatic differentiation toolkit that really all we have to do is to find in some sense kind of the forward path of our network to find the loss function。

 and then we have right away our way of training this。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_176.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_177.png)

All right， a few points of note before I talk about。

 I guess I would say the problem or the challenges with RNNs because while this is， you know，す。

The previous slide in some sense conceptually shows how you build and train RNNs。

If you just try to do that， these won't work very well admittedly。

 so we'll talk about why that's the case。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_179.png)

Before you though， I do want to mention one quick point， which is that just like all deep networks。

 RNNs are stackable， right， so you can stack an RNN to make a deeper RNN。

And what this usually means here is that when we say deep RNNs， I mean。

 depth now has sort of two possible meanings because and sometimes we're already doing deep computations because we're sort of doing a chain of computations going forward in time。

 but when we say stacking RNs what we actually mean typically is that we take one RN here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_181.png)

And we stack another RNA on top of it and what that means is that the outputs from the previous RN。

 so the outputs from this RNN。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_183.png)

Become the inputs to the next layer R&N， so that's what we mean by stacking it。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_185.png)

And note that this sequence like this still obeys the same temporal dependencies of our single layer RnN in particular。

 y2 in this computational graph is only a function of x1 and x2 I mean of course the hidden states2 but we don't work that and certainly that should be y3 there。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_187.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_188.png)

This should be。W 3， but y 3 is only a function of。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_190.png)

X3， x2， and x1。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_192.png)

Okay， even when you stack these things deeper， there's no violation of a temporalal dependencies here。

Okay， now let's talk a little bit about the challenges of training RNNs。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_194.png)

And the challenges of training RNNs are frequently called either exploding or vanishing activations and gradients。

 but I want to highlight both of these sort of two possibilities here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_196.png)

And to do this， I'm actually going to recall things we talked about when we talked about training very deep multilayer perceptrons so if you go back to the lectures we had on normalization and these sorts of normalization and regularization an initialization right one thing we saw was that when we trained a very deep a very deep multilayer perceptron or even initialized a very deep multilayer perceptron。

 the initial weights of the network really mattered Okay so if you again you can go back to that lecture is this I think lecture it was lecture five or six or something like this so again maybe maybe six maybe seven around that time so a long time I've been now。

But if you remember， we sort of looked at different initializations of these networks and we saw that the activations of our inside our network would change depending on these things and if you remember like if we initialize our network normally with well really what we should do is initialize our network with weights with as normal values or what we could do is initialize our network with normal Gaussian values with variance2 over n。

 that was sort of a sweet spot for value to maintain variances across throughout the network。😊。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_198.png)

That and if we had two more than two over n， the actually would decrease over the depth of the network and if we had less than two over n。

 it would decrease over the network。That problem in the case of a deep multilayer perceptron was admittedly a bit artificial because we don't typically train。

 at least in that specific case because we don't typically train 50 layer deep multilayer perceptrons。

Okay， but the important point with RNNs here， so the thing I want to emphasize with RNNs is that a very similar pattern occurs。

But unlike MLPs say， RNNs and RNs， we actually are very naturally。

 in many cases going to be that deep， because we might have sequences that are 200 steps long or even longer right and those problems that we encountered in deep MLPs of activations blowing up or going to zero。

 those problems are all still going to occur here， and they're going to cause problems for us。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_200.png)

So what I'm showing here is I'm showing actually a plot of the a sequence in time。

 just an arbitrary sequence I think just use random inputs here。

 but what I'm plotting here is the norm of the hidden unit over this time period and importantly this scale here is exponential So a little bit bigger here as much bigger like 10 to the six is the unit here in in other words。

 just too big to really represent and you what would really happen if you try to do this is you'll get quick to get ans if you use。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_202.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_203.png)

32 bit floating point representations here。So what I've done here is I've initialized my network。

 I'm using RELUs in my network， and we'll get back to REs in a second so we probably don't want to use REUs and our current networks。

 but we'll talk about that in a second。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_205.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_206.png)

I'm using a weight matrix， WHH， that again， that's my hidden to hidden weight matrix。

 that's the one that maps。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_208.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_209.png)

Hidden， going back a few slides， that is the one that maps。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_211.png)

In。Vectures to the hidden state， the next hidden state。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_213.png)

I've initialized that with sort of too big an initialization for values right so I mentioned it with variance3 over n instead of two over n if I do two over and initialization it'll work。

 but it'll quickly diverge from that when you train these things。😊。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_215.png)

So I've initial asset here and what we see is that just like in an MLP。

 the activations kind of increase over time so they're blowing up and the end result is he we would get Ns if you try to actually train this。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_217.png)

嗯。And so this is a problem with with RNs。 This is called an exploding activation or。Again。

 what you would also get here is you would get if you look at the gradients of this。

 you'll find that all your gradients， because your activationations grow very large。

 all your gradients also grow very large， actually with the whole sequence。

 and so this is called the exploding gradient problem also。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_219.png)

And of course， as well the opposite problem exists too。

 so there's also the problem of vanishing gradients and activations so the weights are too small。

 so if WHH is initialized too small say 1。5 over n。

 then your norm of your weights decreases up your sequence length and your gradients will similarly decrease and your gradients will be too small and you will not be able to learn。

😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_221.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_222.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_223.png)

Now one thing I should mention is that this is actually only adding a non zero input over at time1 so that the inputs that I'm showing here for all times except time one are zero。

 that's important because if we keep adding new information right so we keep adding another。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_225.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_226.png)

X term， this will in fact， be able to to stay nonze。

 but this is actually kind of hiding the real problem because the problem here is that。

 you know in an R andN， we want to maintain what we're calling here sort of long range dependencies So we want it to be the case that at some later point in time。

 we can still maintain some dependency or in sometimes look back to point X1。

 in order to make our predictions at that later time， right， otherwise， if we don't do that。

 we sort of lost the whole point of R andNs in some sense。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_228.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_229.png)

And if your weights are too small， you have this problem called vanish gradients or vanish activations。

 which means basically that the influence of previous time points， x1 over x 10。

 say get smaller and smaller and effectively vanishes here and if that doesn't even take if you look at that again this is a log scale here。

 so very quickly the dependency on at 0。1 will vanish and there will be no real influence of your input at time 1 on on the output here。

Okay， so these are the two， I would say， core problems of RNNs。

 the exploding ingredient problem and the vanish ingredient problem。And in some sense。

 dealing with these two problems has been the history of RNNs or finding ways to deal with these two problems to spin the history of RNNs。

And there are a number of things you can do here， of course in previous lectures we talked about normalization and you also can do things like normalization。

 but one thing I want to emphasize and in fact there will be sort of very similar things that are done。

 but these don't really solve the problem。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_231.png)

And in fact， the thing that I want to emphasize right now。

 which to be honest actually has similar effects as normalization。

 is just make one point about how we could possibly fix these things using non nonlinear activations So one sort of oddity of these previous two slides right these penencies of the previous two slides。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_233.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_234.png)

。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_236.png)

Is that I used reU activations So this is an RN with a re activation。 And if you know RNNs very well。

 you actually probably know that they don't really tend to use re activations for this exact reason right so can I actually can get away from this problem if I just use my activation initially or initialization and get away from this problem if I just use two over N as my activation。

 But as I take gradient steps then I'm going to be changing this and very quickly you'll get the same problem when you use reU So very quickly you'll either have activations blow up or they'll shrink and your gradients will therefore blow up or shrink So re use are sort of tricky to use at least very finicky if you're going to use them。

😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_238.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_239.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_240.png)

And so a very common thing to sort of think about is， well， why don't we just sort of。

Normalize our layers or Ie， why don't we cap the maximum value we can have for our layers？By say。

 using an activation that is actually bounded， right。

 this actually has a similar effect in some cases to normalization。

 right and you can kind of think of them similarly， at least for the case of RN here。So for example。

 we could use the syigmoid activation right we activation like this， which would。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_242.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_243.png)

Limit the values of our hidden states to zero or1 or a10h activation， similar shape。

 which would limit the values to be between negative1 and one。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_245.png)

Does this solve our problem？And the answer is no， This does not solve either the vanish ingredient or the does to I guess it does solve sort of trivially。

 I would say， the exploding gradient problem and the exploding activation problem。

 because you've just limited your your activations period， right。

 So they they they're just going to be smaller， there's no point on this with that with that large gradient。

 And so when。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_247.png)

With that larger term that has sort of a product of the gradient and the activation。

 and so you're not going to have sort of the exploding activation problems as you can see here because of course you're just forcing your activations to be limited to negative one or1 or zero or1 so you're not going to exploding activation problem。

 but it turns out these by themselves don't solve the problem，And in particular。

 they don't solve the problem of the vanished ingredient problem because one of two things will happen right you're either going to be sort of in this region here in your activation in which case your activation sort of will stagnate right so thing with a 10h right right in that central point there you actually are zero so if you're in the point with sort of a non-zero gradient you're going to have your activation is good to zero。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_249.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_250.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_251.png)

On the other hand， if you get kind of in this region here where you have saturating where you sort of hit the saturation point。

In this point， the gradient of this function approaches 0。

 right So here the activation approach is 0 here， the gradient approaches is 0。

 And so if you start getting larger activations， you're actually in regions where you're gradient to 0。

 And so your gradients is going to have a still vanish。

 And so essentially these sorts of activations。 And even though the sigmoid might look a little bit different because you you're at 0。

5 there instead of 0， it actually is the same the same as that problem。

 This is sort of a constant shift。 And so basically either you have。😊。

You're reading either a region with a very small value or a very small gradient。

 And this essentially will cause the exact same problems to happen here as you had before。

 And so the short story of this all is that there is just using。These activations。

Will not cause will not fix the problem of vanish ingredients。 All right。

 And even if you use a saturating non linearity， you're still going to have。Essentially。

 a vanishing influence between earlier points in your sequence and later points。

So how might we go about fixing this and there are many ways you can fix it。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_253.png)

But one method that I want to highlight because it has reached such popularity in deep networks is to use a different architecture for our RNN。

And one of the most famous of these is what's called the LSTM or long short term memory recurrence network。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_255.png)

So an LSTM which again stands for long short termm memory， they are what an LSTM is。

 and again LSTMs are often given this kind of outsized importance and they are to declare very historically important in sort of the evolution of recurrent networks。

 they were the first or one of the first recurrent networks that really started to deal head on with this problem of vanish ingredients and at least one of the very popular initial ones。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_257.png)

But in some sense， all they are is they are a particular form of hidden update。

Of should write that they solve some of the。Problems of vanilla RNNs。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_259.png)

So LSTMs are a particular form of RN that solves some of to some degree， not not fully。

 but they solve to a certain degree， some of the problems of vanilla recurrent neural networks and what I mean by that is just the recurrent neural network you saw on their previous slides here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_261.png)

So。😊，Part of the confusion with LSTMs comes， I think from the terminology that's being used。

 what an LSTM does， it takes this sort of diagram that we have on the left here。

 and it takes these hidden states。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_263.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_264.png)

And it splits the hidden state into two different components that has two correspondingly different update rules and these are called。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_266.png)

Very confusingly the hidden state and the cell state， but to be very， very clear here。

 the cell state is just another component of the hidden state。

 it's not something special or different， it's just another aspect of the hidden state that has in total a different update rule。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_268.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_269.png)

So that's the first step is you're going to split the hidden state into these two different components called again。

 very confusing the hidden state， but they're both the hidden state to be clear。

 the hidden state and the cell state are both elements of the hidden state for this LSTM at time at time T。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_271.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_272.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_273.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_274.png)

And then what we're going to do is we're going to use a very specific form of update for the hidden state and for the cell state。

And I'm going to write these out here， I'm going to write exactly what they are。😊。

TheyThey're a bit cumbersome。And they're cumbersome because they use these intermediate states with weird names like the forget gate or the input gate or the output gate。

 and I think actually so that's this is the input gate， this is the output gate， is the forget gate。

 I think this is called like called the gate gate it's going to G but I think it's called the cell gate。

 we've already used the term Cs， we have to used the term G there。😊。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_276.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_277.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_278.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_279.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_280.png)

These are very confusingly named， but let me just state what they are。 Al right。

 so what we're going to do with an LSTM is we are going to give we're going to compute first these terms here。

 which they don't really have too much importance。 they're just intermediate terms we're going to use to then form our updates of the next。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_282.png)

Hidden state and the next cell state as a function of the previous one， okay。

 so these terms here for some time you know HT and CCT。

 these terms will all be functions as sort of the previous states。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_284.png)

And then we're going to form the next states as a function of these things。

 and I guess also the previous states， let me just write it what these are and then we'll go from there。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_286.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_287.png)

All right， so this uses the following update。😡，Some function。

 some nonlinear function of first of all， it may also just just define sizes。

 so all these things I should mention， so IFT， all of these things， these are all。😊，Ging to be in。RD。

 say， so assuming all of these things are RD， so in other words。

 all of these gates here are the same size CT is the same size H is the same size。

 they're all D dimensional vectors。Okay。So。The update is going to be we're going to form all of these things as some。

Function of the previous。Hidden state。Plus。You may I just write it like this。 I won't use H， H。

 I just use W H here。 Actually' not gonna to use W H H， even though that's。

 that's somewhat confusing because， you know， it， it's actually not mapping hidden hidden It mapping hidden to all those things。

 but I'， I'll talk about that in a second Time W。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_289.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_290.png)

H X。Just to use sort of consistent notation with the past one to make clear this is not that different from the previous the previous RN plus a bias term here B。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_292.png)

H， so that actually looks very similar to our previous update， right？



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_294.png)

The only difference， I guess being that we're not using the whole hidden state here。

 we're only using sort of this portion of the hidden state to form this。And then we're going to。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_296.png)

Apply different nonlinearities to this to form each of the different updates。

 so in particular I'm going to write like this to like what these different nonlinears are。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_298.png)

I， to get the I term here， we'll take this whole term here and to get that component will apply sigmoid。

The next one will all seize the sigmoid。GT will be different， it will use it special， at least 10h。

And the next one is a sigmoid。Okay， the important to keep in mind here is sort of just just understand what I'm doing here。

 So again， H T。Here would be a vector， which is in RD。 That means， by the way。

 the total hidden state size here。Would be。2 D dimensional， not 2 D， but two times d dimensional。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_300.png)

And so this vector， this matrix here， WHH would be。In our 4D times D， right， because it's mapping on。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_302.png)

D dimensionsional vector。H。To a。4ourD dimensional vector that we're going to split into four different components and call IT。

 FT， GT， and OT。and these are all that we get these by applying different sigmoids。

 but it's important to note that what this means is that know we're taking W here。

 which is a large 4 d by D matrix。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_304.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_305.png)

Forming all those different components and then applying different on nonlinearities to all of them。

 and similarly， if this one here。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_307.png)

If x was n dimensional， then this here would have to be。4 D by N。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_309.png)

Okay， so that's sort of the sizes of all these things。All right。

 that's kind to step one of this procedure。We're forming these initial things and oftentimes if you've seen it before。

 you may see like this broken down into the different individual elements。

 like a input gate weight and a mapping from x's to the input gates and x to the forget gate。

 but it isn't even implemented that that internally and these libraries。

 there's always one matrix because it better these one matrix and split things。

 So it's much better to think of these in analogy to a normal Rnn as just having one matrix that just sort of in some sense inflates the hidden and a little bit inflates the states to four times the dimension for these intermediate terms here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_311.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_312.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_313.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_314.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_315.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_316.png)

And then。Now we're going to form the updates for。For these terms。And in particular。

 CTt is going to be equal to CTt minus1。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_318.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_319.png)

Eleement wise product with FT。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_321.png)

Okay。😊，Plus。IT element wise product with GT。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_323.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_324.png)

Okay。And then finally， H。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_326.png)

Equals。The1 H。Of CT。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_328.png)

Elmas product with Ot。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_330.png)

Allright and now I want to sort of， you know， look at that for a moment and just add like a suitably appropriate number of question marks。

 maybe exclamation points， something like this， like what what on earth is happening here。

 like why did they what did these updates mean why did we choose these updates。

 like what did equations actually correspond to？

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_332.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_333.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_334.png)

Now。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_336.png)

There are a number of。Papers and blog posts and a number of descriptions here on。

How an understanding。These updates and understanding of how LSTMs work。

And I find most of them rather unhelpful， I don't find much intuition if I'm clearly honest in the names of these things。

Input gates and forget gates and output gates， these seem to me rather arbitrary。

 and I think they are rather arbitrary。A lot of other structures work just fine here too。

 you can actually simplify a lot of these things and have other recurrent units that accomplish many of the same effects as LSTMs。

 but are simpler or just structured differently or somehow different。

To be very clear LSTMs have survived a very， very long time and survived very well because they've sometimes been tuned very well and these particular equations do seem nice。

 but they are somewhat arbitrary。So。I don't want to。

 I'm not going go over kind of the intuition about what each of these things is doing and why it makes total sense to call them the input gate and the output gate and the forget gate and the cell gate。

 because I actually don't think it makes sense。 What I'm gonna to try to do is describe the key aspect that I by which I view LSTMs and and try to explain at a high level why these things at least help to avoid the vanish ingredient problem we saw in。

In previous vanilla Rs。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_338.png)

And the key line that I want to highlight is this line。So what is this line doing？

This line is forming the current cell state， which again， the cell state is just an element。

 a portion of the hidden state， so the portion that's maintained over time。Um。

Part of the hidden state， basically。And the way it forms the hint at time T the cell data time T。

 I'll call it the cell state， but importantly， this is an element of the hidden state。

 it forms the cell state time T as a function of the previous cell state time T times Ft。

But FT here is some sigmoid of something things， in other words， FT importantly。

Is going to be a vector。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_340.png)

All containing zero1s， I guess that should be 01 to the D here。So I went to the D。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_342.png)

So FT is going to be a vector in with 01 elements to the T。

And what that means it's going to do is going to take the previous cell state and it's going to scale it down It's going to scale it down or keep it the same。

 So it sort of can do anything。 It can either。If FT is all zeros。

 it will ignore entirely the past cell state or if FT is all one。

 they'll remember entirely the past cell state。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_344.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_345.png)

This is that's maybe why it's called the forget gate it determines how much you forget the past cell state。

But what we're doing is we're form the next cell state as sort of a A。

Some scaling of the previous state。And importantly。

 we have the ability sort of with the proper weights。 You know， if。

 if F T has chosen such that it's close to one， we're largely gonna just sort of。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_347.png)

Keep around。The past cell state。Then we're going to add to it。This term here。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_349.png)

Right， and this term here again， is some。You know，s it's a term I that is also going to be in zero1。

And then GT， which is sort of going to be between negative 1 and 1。

 So we're adding to this cell state， we're scaling it down and then adding an additional bounded term。

 right， this term here， this whole term well sort of emphasize that this whole term here because you're multiing 01 times negative 1。

1， this whole term here would be a negative1 and positive  one to the D。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_351.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_352.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_353.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_354.png)

Right and so what you're doing in some instance you're sort of decreasing the scale of the previous term and adding a new term to it。

 and the relative weight of these two terms is decided by， in some sense， this FT and IT。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_356.png)

Okay， and。The sort of important point that I would think here is that， you know。

 because the sigmoids is saturating， there's a limit how much of the previous state you can sort of keep around and you could either keep all of it around or zero it out。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_358.png)

Then how the hidden it evolves to be honest is a bit arbitrary， you know this output here。

 this is just sort of we're taking some 10h term so this whole thing will you know be a bounded value too。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_360.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_361.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_362.png)

But that's actually the important update in my view is this cell state update sort of keeps is where you keep around kind of the memory of the past of the past state。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_364.png)

Right。So that's the update。 And again， I I I dont want to dwell too much on it because it's just some updates。

 It has some nice properties like you also， by the way。

 another very nice property here is you have element wise multiplication of of。

Of different hidden states here， which is actually quite hard operation to simulate by other operations。

 We'll see this again， actually when we come to self attention later or attention in general。

 two lectures from now。😊，So there is an aspect to which this particular form of update also captures No nonlineararies like multiplication。

 which element Y multiplication， which also seem good sort of separately。

 but this is the update and the bottom line of this update is because of this form of the cell state update you have less or you have more ability to preserve the influence of previous inputs on future inputs。

 especially namely if I pick just intuitively here if I pick FT to always be one if I set it if I choose it to be all ones by picking my weights properly。

 then basically I never would really forget any previous cell state because I am always of just adding to my previous state。

 of course you don't always want to remember everything about the past so you also want the ability to sort of decrease that dependency。

 but that's the rough intuition I think and I think personally for me going much deeper into into it。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_366.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_367.png)

Has always been kind of a losing battle， and I've never really seen too much value for it。So okay。

 this is the this is the this is as far as we're going go on on why LSTM's work。

 but I do want to mention kind of a little bit of the history of LSTMs here because essentially really a really great history so LSTMs were proposed by Steph Critor and Yugenshmaneuver in 1997 was the paper and I believe actually this paper is one of the most cited papers of the last decade in deep learning so it's been cited 75000 times and published I mean actually the longer you go back the harder is to get more publications because now with these days in modern deep learning you can get know tons of citations by having a really good Comve early on in the history of machine learning。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_369.png)

But for a paper from the 90s， this is actually quite hard。

 and so this is actually one of the most cited papers I believe in all of machine learning from prior to turn of the century。

The is called long script memory and introduced this this LSTM。

 but I actually also want to mention And be clear this this was this was know a seminal paper it proposes architecture and architectures not widely used。

 however one point to another sort of important point in the development。

 I think in the development of RNs， which came from a blog post actually by Andre Carpathy。

 So Andre in 2015 wrote a blog post called。😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_371.png)

All it' called is called the unreasonable effectiveness of recurrent neural networks or something like this。

 I'll play on I think every paper for a while was titled the unreasonable effectiveness of something。

 It's like something all you need now in deep learning。

 It's like a trope and the this this blog post I think was is。😊。

It sort of shows that not every contribution to even academic work has to be in the form of a paper。

 So this blog was was sort of in some sense， kind of a fun exploration of recurrent networks。

 but I think had a huge impact on the field。 So if you haven't seen it before。

 certainly go out and check out this blog posts it actually specifically deals with recurrent sorry it deals with recurrent networks for autoregressive prediction and does some very cool things and it uses LSTM And just to make a little point there。

 I think there's probably a non I know all of deep learning with the floating at that time。

 but I think there was a non-zero correlation between the release of this blog post and the explosion of interest in in in LSTMs as seen by this inflection point in 2015。

😊，When people started using LSTs a whole lot more than they had before。

 which just so happened to be the exact year that Andre wrote has blog posts。 So。

 so I think there is some， there is some nonze correlation here。 And again。

 I mentioned this because both I think it's it's an important example， but also shows that， you know。

 it's things like blog posts can actually have a。😊，Have an impact on the field。嗯。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_373.png)

Also at that point， I want to highlight some of the things that were produced in that blog post at the time。

 So as I said before， Andre produced Andre wrote these recurrent networks that would predict text character by character and one of the things he traineded on was the Linux kernel source code。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_375.png)

And kind of so he trained it on the entire sort of Linux kernel to predict character at a time。

 And then he used it to generate new text。 And this might not be that impressive these days， right。

 These days， we have libraries like like codex and things like this that actually。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_377.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_378.png)

Predict real code。 I actually can write real code。 But at the time。

 this sort of absolutely blew my mind。 So， you know。

 predicting text one character at a time produces code that to be clear， doesn't actually run。

 So to be clear I mean just emphasize what what this code is。 So so this code here is sort of saying。

 okay， now that we have this predictive model， we're we're gonna sample from it。

 So we're going sort of sample one character from this model。

 then we're gonna input that character into the as the input for the from an RN Pre the next character treat that is the input etc。

 and use as a prediction process。😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_380.png)

And this process that produced code that looked absurdly good。 So it's， it doesn't run， of course。

 here。 like it as meaningless this code here， but it。

 it looked like it could be code from the Linuxs kernel。 has like comments that terminate and。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_382.png)

Foratting and comments and stuff like this is it's really hilarious。

 And actually even more so one thing I found even more impressive is that I didn't quite see sort of what was really done here。

 but another example he trained。😊，A similar version on a。

 I think was an algebraic topology textbook and in latex And from this generated latex code that actually。

 with a few， I think I'm not quite sure how much he's mentioned with a few edits actually compiled to latex code。

 And if if you can zoom in on the slide at some point download the slides and zoo in on It's really hilarious。

 It writes this text that is of course， completely meaningless again。

 it's writing text character at a time。 but it's it's writing sentences and it starts proofs。

 And then it says things that the proof is triviala and stuff like this。

 It's really really hilarious。 So I think I think this post it really sort of sparked the imagination of what was possible with these models。

 And I think was not a uninfluential thing in the later development。😊。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_384.png)

Language models and these sorts of things。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_386.png)

Okay， so actually that's the majority of what I want to talk about today for RNNs。

 but I want to end with two last points talking about more complex things you can do with RNNs beyond just simple sequential modeling。

So。RNNs， as I formulated them before several slides ago。

 they had a sequence of inputs that you sequence of inputs X1 through Xt。

 and for each of these you predicted a sequence of outputs。

And you had this constraint that the output at time T only depended on things before。

That time in the sequence。However， both those elements are sometimes things you want to to change。

 right， so that those constraints are not always。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_388.png)

And sometimes the right constraints for a prediction task。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_390.png)

For example， let's look at a more reasonable sequence prediction task or not not shouldn say a more reasonable a slightly different sequence prediction task like translating language Al right。

 so let's know take our input sentence here， say something like translating language is difficult in this case we're to produce something like the Spanish sentence try lateridioama as D so so this。

😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_392.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_393.png)

Translate the language in general， I picked a pretty simple example here。

But translating language in general is very hard because languages don't have a one to one correspondence。

 but you can't just translate each word and get a meaningful sentence。

 there's switches in the ordering of words， there's sort of colloquialisms and sort of phrases that we use in one language that don't really translate to another language and so you need to not only consider language word I mean predictions made of word by word。

 but kind of。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_395.png)

Translating an entire sentence or an entire paragraph sometimes。

 and it's not immediately obvious how RNNs apply to that right so RnNs would sort of predict。

 you know， take our input translating and predict like one thing from that， right？



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_397.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_398.png)

嗯。The point I want to make here and I won't go into this too deeply is that there's ways to leverage RNNs to get much more power than this and one very famous example of this comes from what they're called sequence to sequence model。

And the idea here is that instead of having one RNN that just predicts。

 a mapping from these inputs to outputs。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_400.png)

We actually predict a we use。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_402.png)

1 RN。To parse the whole sequence in some sense。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_404.png)

But we don't actually stop there， so we treat this as sort of the input sequence here。

But we don't actually stop there。 What we actually do is we take the last state of this RN。

 which in some sense is like the。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_406.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_407.png)

Since it is like the summary， remember a hidden state for Ar is like a summary of all past text。

 we actually don't try to have outputs on each of these intermediate states here。

 we just have this last hidden state。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_409.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_410.png)

And we feed this into another RN。A top which tries to generate an entire sequence。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_412.png)

For the translation and the way this typically works is that this later RN on top here would be an autoaggressive one so I'm not actually writing this because it gets a bit complicated。

 but what would actually be happening here is that this RNN here would make the prediction of the first word。

 then it would feed this first word much like the autoaggressive RN as we saw before into the next state predict the next word feed this into the next word etc。

 so you have this chain to predict that and then of course youll know when you're done so at the very end at some point it'll predict the RNN would predict the phrase stop。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_414.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_415.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_416.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_417.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_418.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_419.png)

That's how you know that you're done。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_421.png)

And you actually also input the phrase stop so the R&N knows it should sort of summarize the text and then start the output。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_423.png)

嗯。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_425.png)

I don't want to get too much into sequencequencing modeling because this is actually a fairly complex and a whole nother paper in some sense。

The point that I want to emphasize here is that what these models did is they leveraged R andNs as。

 in some sense， a module， So this class， we talk frequently about modules and about how we。

 we use modules intelligently。 what these and put modules together once we coded a module and R andN module。

 we can put this together to。Create more。To build up more complex structures。

 and this is exactly what sequence sequence models are doing。 They're taking an RNN。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_427.png)

Typically used to predict things one at a time， not doing that。

 treating the whole RNAN is sort of as basically an encoder which maps the entire state it's seen so far or summarizes it in this one hidden vector H5 and then uses this vector as input to the next to a decoder which produces the output。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_429.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_430.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_431.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_432.png)

Okay， and I don't want to make too much of this again because it is a complex thing and we haven't talked too much about encoder decoder architectures here and that's okay。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_434.png)

The high level point is。All of these things， despite their seeming complexity。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_436.png)

Can effectively be trained in the same end to end manner because these are all modules we have built that can be traineded together in automatic differentiation using a tool like needle。

 or of course， in reality like pipetorch or Tensorflow or these sorts of things。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_438.png)

Okay， so that's sequence sequence modeling。 And the other kind of important aspect of RnNs that I want to mention or other important extension to RNs that I want to mention are bidirectional RNs。

 So a bidirectional RN11 feature of RnNs as we had before。 So not this version here。

 but one feature that we had。s copied my figure。 So again should be a y3 there。

 one feature we had of RNs are that the output at time T X3 depended only on x1 through X。😊。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_440.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_441.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_442.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_443.png)

X1 through x3 and similarly， y2 here would depend on a normal RNA and only on x1 through x2。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_445.png)

And that's good when we have。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_447.png)

when our sequence prediction task is such that we don't want to incorporate any future information into our prediction that of course。

 makes total sense in those tasks like autoregressive prediction where the target is is the next word so of course if you use the future to predict the sequence to predict that you could do it trivially and you wouldn't learn anything but importantly there are many kind of sequence tasks where we want to use the whole sequence in order to predict our output and a good example actually is language translation right there's no reason why we have to use only the sentence up until this current point to predict the next point we could use the whole sequence。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_449.png)

Same with， for example， part of speech tacking in， in language， right， we don't need to。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_451.png)

Sort of only use the time up to that point to predict the part of speech。

 we can use the whole sentence。And。I actually think that the methods we're going to talk about two lectures from now of transformers offer a slightly more elegant solution to this problem。

嗯。Or even convolutional networks maybe even offer a more elegant solution to this problem but I do want to mention that there are ways to modify RNNs to allow for temporal dependence to flow both ways。

 so to remove this constraint that the prediction at time T can only depend on the sequence up to that point。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_453.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_454.png)

And the most common thing to do is use what's called a bidirectional RNAN。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_456.png)

Whi essentially stacks two RNNs one after the other or of course you can stack many of these then。

 but immediately it stacks two one after the other where one of the RNNs runs forward in time here so this one runs kind of like a normal RNN and then you stack on top of this an RNN that runs backwards in time。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_458.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_459.png)

And the idea here is that with this particular compute graph。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_461.png)

You have now。Joint dependency between all the outputs and all the inputs right because。

 you know X Y1 here has a path of influence from all the other states through the backward RnNs to make its prediction right。

 and of course， there's many different chain of influence fact。 You know。

 you have this chain of influence。 You have this chain of influence， etc cetera。

 right So you have lots of different sort of flows for information through this network。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_463.png)

This allows for。For essentially dependence in your in your prediction sequence that it's not just causal。

 it's not just going where the output here does not to just depend on x1 and x2。

 but also depend on x3。 Again， this is not always desired and in fact。

 for something like an auto aggressivegressive model this is explicitly forbidden because this would make the problem trivial and it would make the problem you wouldn't learn anything from the problem then。

 but for problems where you want to use the whole sequence like translation。

 there's no reason not to do this。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_465.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_466.png)

And so this is one mechanism for capturing this kind of dependence here。And again。

 I would be very scared about deriving， I think I could do it for a normal RnN。

 I could derive by hand the equations for all all the gradients。

 actually I admit I would not ever want to do that for a biodirectionalal RN because there's so many different dependencies and chains of dependency here that you have for how different parameters influence at the ones you really have to basically do it by deriving kind of automatic differentiation and he to do it in the most simple way and so I'm very glad that we can just use our automatic differentiation toolkit to just write the forward pass of this thing and immediately get a way of computing all the gradients involved。



![](img/7aa4074b9cbeb47e2e1301a0b799f83d_468.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_469.png)

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_470.png)

All right， so that's it for today's lecture next lecture we're going to talk about how to actually implement RNNs and particular that we're going to implement the LSTM on LSTM's layer and as we will see。

 despite the seeming complexity of LSTMs and the frequent I guess very long co use for LSTMs we'll see is actually a very simple process in。

😊。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_472.png)

At least at its core level， and we'll use that to build a very sort of short。

 compact implementation for LSCMs。

![](img/7aa4074b9cbeb47e2e1301a0b799f83d_474.png)

S little nextさ。