# Andrej《语言建模的详解入门：构建 makemore》中英字幕（deepseek-R1 - P5：Building makemore Part 5_ Building a WaveNet.zh_en - GPT中英字幕课程资源 - BV1SDRxYKEfM

Hi。Today we are continuing our implementation of Makemore。

 our favorite character level language model。Now you'll notice that the background behind me is different。

 that's because I am in Kyoto and it is awesome， so I'm in the hotel from here。

Now over the last few lectures we've built up to this architecture that is a multilayer perceptron character level language model。

 so we see that it receives three previous characters in tries to predict the fourth character in a sequence using a very simple multi perceptron using one hidden layer of neurons with tenageal Neities。

So what I'd like to do now in this lecture is I'd like to complexify this architecture。In particular。

 we would like to take more characters in a sequence as an input， not just three。

 and in addition to that， we don't just want to feed them all into a single hidden layer because that squashes too much information too quickly。

 Instead， we would like to make a deeper model that progressively fuses this information to make its guess about the next character in a sequence。

And so we'll see that as we make this architecture more complex。

 we're actually going to arrive at something that looks very much like a waveNe。



![](img/c2c4c553adf638a00076095ae2876499_1.png)

So Wiignnet is this paper published by Deffind in 2016， and it is also a language model basically。

 but it tries to predict audio sequences instead of character level sequences or word level sequences。



![](img/c2c4c553adf638a00076095ae2876499_3.png)

![](img/c2c4c553adf638a00076095ae2876499_4.png)

![](img/c2c4c553adf638a00076095ae2876499_5.png)

But fundamentally， the modeling setup up is identical， it is an auto aggressivegressive model。

 and it tries to predict the next character a sequence。

And the architecture actually takes this interesting hiarchical sort of approach to predicting the next character in a sequence with this street like structure。

 and this is the architecture and we're going to implement it in the course of this video。

 so let's get started。

![](img/c2c4c553adf638a00076095ae2876499_7.png)

![](img/c2c4c553adf638a00076095ae2876499_8.png)

So the start code for part 5 is very similar to where we ended up in in part 3。

 recall that part 4 was the manual that application exercise that is kind of an。

 So we are coming back to part 3 copy pasting chunks out of it。

 and that is our start code for part 5。 I've changed very few things otherwise。

 So a lot of this should look familiar to if you've gone through part 3。

 So in particular very briefly。 We are doing imports。 We are reading our data set of words。



![](img/c2c4c553adf638a00076095ae2876499_10.png)

![](img/c2c4c553adf638a00076095ae2876499_11.png)

![](img/c2c4c553adf638a00076095ae2876499_12.png)

And we are processing their set of words into individual examples。

 and none of this data generation code has changed and basically we have lots and lots of examples。

 in particular we have 182，000 examples of three characters trying to predict the fourth one。



![](img/c2c4c553adf638a00076095ae2876499_14.png)

And we've broken up every one of these words into little problems of given three characters predict the fourth one。

So this is our data set and this is what we're trying to get the neural left to do。



![](img/c2c4c553adf638a00076095ae2876499_16.png)

Now in part three， we started to develop our code around these layer modules that are， for example。

 like class linear， and we're doing this because we want to think of these modules as building blocks and like a Lego building block bricks that we can sort of like stack up into neural networks and we can feed data between these layers and stack them up into sort of graphs。

Now we also developed these layers to have APIs and signatures very similar to those that are found in Pytorch。



![](img/c2c4c553adf638a00076095ae2876499_18.png)

So we have Torrsdot Nn and it's got all these layer building blocks that you would use in practice。

 and we were developing all these to mimic the APIpis of these。 So for example， we have linear。

 So there will also be a Torrsdot Nn dot linear and its signature will be very similar to our signature and the functionality will be also quite identical as far as I'm aware So we had the linear layer with the vom 1 D layer and the 10h layer though we developed previously。



![](img/c2c4c553adf638a00076095ae2876499_20.png)

![](img/c2c4c553adf638a00076095ae2876499_21.png)

![](img/c2c4c553adf638a00076095ae2876499_22.png)

And linear just does a matrix multiply in the forward path of this module。



![](img/c2c4c553adf638a00076095ae2876499_24.png)

Bch number of course is this crazy layer that we developed in the previous lecture and what's crazy about it is well there's many things。

 number one it has these running mean and variances that are trained outside of back application。

 they are trained using exponential moving average inside this layer when we call the forward Pass。



![](img/c2c4c553adf638a00076095ae2876499_26.png)

![](img/c2c4c553adf638a00076095ae2876499_27.png)

In addition to that。There's this training flag because the behavior of bashorm is different during train time and evaluation time。

 and so suddenly we have to be very careful that bashorm is in its correct state。

 that it's in the evaluation state or training state so that something can now keep track of something that sometimes introduces bugs。

Because you forget to put it into the right mode。And finally we saw that batchroom couples the statistics or the activations across the examples in the batch。

 so normally we thought of the batch as just an efficiency thing。

 but now we are coupling the computation across batch elements and it's done for the purposes of controlling the activation statistics as we saw in the previous video。



![](img/c2c4c553adf638a00076095ae2876499_29.png)

So it's a very weird layer， at least to a lot of bugs， partly for example。

 because you have to modulate the training and eval phase and so on。



![](img/c2c4c553adf638a00076095ae2876499_31.png)

![](img/c2c4c553adf638a00076095ae2876499_32.png)

In addition， for example， you have to wait for the mean and variance to settle and to actually reach a steady state。

 and so you have to make sure that basically there's state in this layer and state is harmful usually。



![](img/c2c4c553adf638a00076095ae2876499_34.png)

![](img/c2c4c553adf638a00076095ae2876499_35.png)

Now I brought out the generator object， previously we had a generator equals G and so on inside these layers。

 I've discarded that in favor of just initializing the torch RNG outside here just once globally。

 just for simplicity。

![](img/c2c4c553adf638a00076095ae2876499_37.png)

![](img/c2c4c553adf638a00076095ae2876499_38.png)

![](img/c2c4c553adf638a00076095ae2876499_39.png)

![](img/c2c4c553adf638a00076095ae2876499_40.png)

And then here we are starting to build out some of the neural network elements。

 this should look very familiar， we have our embedding table C。

 and then we have a list of players and it's a linear feedats to batchchelor feeds to 10h。

 and then a linear output layer and its weights are scaled down so we are not confidently wrong at initialization。



![](img/c2c4c553adf638a00076095ae2876499_42.png)

We see that this is about 12，000 parameters。We're telling Py the parameters of car gradients。



![](img/c2c4c553adf638a00076095ae2876499_44.png)

The optimization is， as far as them will aware identical and should look very， very familiar。



![](img/c2c4c553adf638a00076095ae2876499_46.png)

Nothing changed here。Lo function looks very。

![](img/c2c4c553adf638a00076095ae2876499_48.png)

Crazy， we should probably fix this and that's because 32 batch elements are too few and so you can get very lucky or unlucky in any one of these batches and it creates a very thick loss function。

 so we're going to fix that soon。

![](img/c2c4c553adf638a00076095ae2876499_50.png)

![](img/c2c4c553adf638a00076095ae2876499_51.png)

Now， once we want to evaluate the trained neural network。

 we need to remember because of the bathroom layers to set all the layers to be training equals false。

 so this only matters for the bathroom layer so far。



![](img/c2c4c553adf638a00076095ae2876499_53.png)

![](img/c2c4c553adf638a00076095ae2876499_54.png)

And then we evaluate。We see that currently we have validation loss of 2。10， which is fairly good。

 but there's still ways to go， but even at 2。10， we see that when we sample from the model we actually get relatively namelike results that do not exist in a training set。

 so for example， Yvonne Ki pro。

![](img/c2c4c553adf638a00076095ae2876499_56.png)

![](img/c2c4c553adf638a00076095ae2876499_57.png)

Aliaa， et cetera。 So certainly not。

![](img/c2c4c553adf638a00076095ae2876499_59.png)

Reasonable， not unreasonable， I would say， but not amazing。

 and we can still push this validation loss even lower and get much better samples that are even more namelike。



![](img/c2c4c553adf638a00076095ae2876499_61.png)

![](img/c2c4c553adf638a00076095ae2876499_62.png)

So let's improve。This model now。

![](img/c2c4c553adf638a00076095ae2876499_64.png)

Okay， first， let's fix this graph because it is daggers in my eyes and I just can't take it anymore。



![](img/c2c4c553adf638a00076095ae2876499_66.png)

So lossci， if you recall， is a Python list of floats， so for example。

 the first 10 elements look like this。

![](img/c2c4c553adf638a00076095ae2876499_68.png)

Now what we'd like to do basically is we need to average up some of these values to get a more sort of representative value along the way。

 so one way to do this is the following。In parttorch， if I create， for example。

A tensor of the first  ten0 numbers。Then this is currently a one dimensional array。

 but recall that I can view this array as two dimensional。 So for example。

 I can view it as a two by5 array。And this is a 2D tensor now，2 by5。

 And you see what Peroch has done is that the first row of this tensor is the first five elements。

 and the second row is the second five elements。I can also view it as a p by two as an example。

And then recall that I can also use negative one in place of one of these numbers。

And parttor will calculate what that number must be in order to make the number of elements work out。

 So this can be。This or like that， both will work， of course this would not work。Okay。

 so this allows it to spread out some of the consecutive values into rows。

 So that's very helpful because what we can do now is， first of all。

 we're going to create a tor shot tensor out of the。A list of floats。

And then we're going to view it as whatever it is， but we're going to stretch it out into rows of 1000 consecutive elements。

So the shape of this now becomes 200 by 1000。And each row is 1，000 consecutive elements in this list。

So that's very helpful because now we can do a mean along the row。

And the shape of this will just be 200。And so we've taken basically the mean on every row。

 so PLT that' plot of that should be something nicer。



![](img/c2c4c553adf638a00076095ae2876499_70.png)

That'uch better。So we see that we've basically made a lot of progress and then here this is the learning rate decay。

 so here we see that the learning rate decay subtracted a ton of energy out of the system and allowed us to settle and to serve the local minimum in this optimization。



![](img/c2c4c553adf638a00076095ae2876499_72.png)

So this is a much nicer plot。 Let me come up and delete the monster。

 and we're going to be using this going forward。 Now， next up， what I'm bothered by is that。



![](img/c2c4c553adf638a00076095ae2876499_74.png)

![](img/c2c4c553adf638a00076095ae2876499_75.png)

You see our forward pass is a little bit gnarly and takes away too many lines of code。

 so in particular we see that we've organized some of the layers inside the layers list。

 but not all of them for no reason。

![](img/c2c4c553adf638a00076095ae2876499_77.png)

So in particular， we see that we still have the embedding table， special case outside of the layers。

 and in addition to that， the viewing operation here is also outside of our layers。

 Let's create layers for these and then we can add those layers to just our list。So in particular。

 the two things that we need is here， we have this embedding table and we are indexing at the integers inside the batch XB inside the Tensor XB。

So that's an embedding table lookup just done with indexing and then here we see that we have this view operation。

 which if you recall from the previous video， simply rearranges the character embeddings。

And stretches them out into a row。 And effectively， what Bette does is the concatenation operation。

 basically， except it's free because viewing is very cheap in Pytorch and no no memory is being copied。

 We're just rerepresenting how we view that tensor。 So let's create。



![](img/c2c4c553adf638a00076095ae2876499_79.png)

Moddules for both of these operations， the embedding operation and flattening operation。



![](img/c2c4c553adf638a00076095ae2876499_81.png)

So I actually wrote the code in just to save some time。



![](img/c2c4c553adf638a00076095ae2876499_83.png)

So we have a module embedding and a module flatten。

 and both of them simply do the indexing operation in a forward pass and the flattening operation here。



![](img/c2c4c553adf638a00076095ae2876499_85.png)

And this C now will just become a salt at weight inside an embedding module。



![](img/c2c4c553adf638a00076095ae2876499_87.png)

And I'm calling these layers specifically embedding and flatten because it turns out that both of them actually exist in Pytorch。



![](img/c2c4c553adf638a00076095ae2876499_89.png)

So in Pytorch， we have n and doubt embedding， and it also takes the number of embeddings and the dimensionality of the embedding。

 just like we have here， but in addition， Pytorch takes in a lot of other keyword arguments that we are not using for our purposes yet。



![](img/c2c4c553adf638a00076095ae2876499_91.png)

![](img/c2c4c553adf638a00076095ae2876499_92.png)

![](img/c2c4c553adf638a00076095ae2876499_93.png)

And for flatten， that also exists in Pytorch， and it also takes additional keyword arguments that we are not using。

 so we have a very simple flatten。

![](img/c2c4c553adf638a00076095ae2876499_95.png)

But both of them exist in Pythor they just a bit more simpler。And now that we have these。

 we can simply take out some of these special case。



![](img/c2c4c553adf638a00076095ae2876499_97.png)

![](img/c2c4c553adf638a00076095ae2876499_98.png)

Thanks， so instead of C， we're just going to have an embedding。And v up size and N embed。

And then after the embedding， we are going to flatten。

So let's construct those modules and now I can take out this the。



![](img/c2c4c553adf638a00076095ae2876499_100.png)

And here， I don't have to special case any more because now C is the embeddings weight and is inside layers。



![](img/c2c4c553adf638a00076095ae2876499_102.png)

So this should just work。And then here， our forward path simplifies substantially because we don't need to do these now outside of these layers outside and explicitly。

 they're now inside layers。

![](img/c2c4c553adf638a00076095ae2876499_104.png)

So we can delete those。But now to kick things off， we want this little X。

 which in the beginning is just Xb， the tensor of integers specifying the identities of these characters at the input。

And so these characters can now directly feed into the first layer， and they should just work。



![](img/c2c4c553adf638a00076095ae2876499_106.png)

So let me come here and insert a break because I just want to make sure that the first iteration of this runs and that there's no mistake so that ran properly。



![](img/c2c4c553adf638a00076095ae2876499_108.png)

![](img/c2c4c553adf638a00076095ae2876499_109.png)

And basically， we've substantially simplified the forward past year。 Okay。

 I'm sorry I changed my microphone。 so hopefully the audio is a little bit better。



![](img/c2c4c553adf638a00076095ae2876499_111.png)

Now， one more thing that I would like to do in order to pytorrchify our code even further is that right now we are maintaining all of our modules in a naked list of layers。

 and we can also simplify this because we can introduce the concept of Pytorrch containers。

 So in Torchdo N N， which we are basically rebuilding from scratch here。

 there's a concept of containers。

![](img/c2c4c553adf638a00076095ae2876499_113.png)

![](img/c2c4c553adf638a00076095ae2876499_114.png)

![](img/c2c4c553adf638a00076095ae2876499_115.png)

And these containers are basically a way of organizing layers into lists or dicks and so on。

 so in particular theres a sequential which maintains a list of layers and is a module。

 class and pytorrch， and it basically just passes a given input through all the layers sequentially。

 exactly as we are doing here。

![](img/c2c4c553adf638a00076095ae2876499_117.png)

![](img/c2c4c553adf638a00076095ae2876499_118.png)

So let's write our own sequential。

![](img/c2c4c553adf638a00076095ae2876499_120.png)

I've written a code here and basically the code for sequential is quite straightforward。

 we pass in a list of layers which we keep here and then given any input in a forward pass。

 we just call all the layers sequentially and return the result in terms of the parameters。

 it's just all the parameters of the child modules。



![](img/c2c4c553adf638a00076095ae2876499_122.png)

So we can run this， and we can again simplify this substantially because we don't maintain this naked list of layers。

 We now have a notion of a model which is a module。 and in particular。

 is a sequential of all these layers。

![](img/c2c4c553adf638a00076095ae2876499_124.png)

![](img/c2c4c553adf638a00076095ae2876499_125.png)

And now， parameters are simply just a model of parameters。

And so that list comprehension now lift here。

![](img/c2c4c553adf638a00076095ae2876499_127.png)

And then here are press here we are doing all the things we used to do。



![](img/c2c4c553adf638a00076095ae2876499_129.png)

Now here， the code again simplifies substantially because we don't have to do this forwarding here instead we just call the model on the input data and the input data here are the integers inside XB。

So we can simply do logits， which are the outputs of our model。

 are simply the model called on the Xb。And then the cross entropy here takes the logits and the targets。

So this simplifies substantially。And then this looks good。 So let's just make sure this runs。

 That looks good。

![](img/c2c4c553adf638a00076095ae2876499_131.png)

Now here we actually have some work to do still here。

 but I'm going to come back later for now there's no more layers， there's a model that layers。

 but it's not easy to access attributes of these classes directly。

 so we'll come back and fix this later。

![](img/c2c4c553adf638a00076095ae2876499_133.png)

And then here， of course， this simplifies substantially as well。

 because logits are the model called on x。

![](img/c2c4c553adf638a00076095ae2876499_135.png)

And then these log jets come here。So we can evaluate the train e validation loss。

 which currently is terrible because we just initialized it in neural lot。



![](img/c2c4c553adf638a00076095ae2876499_137.png)

And then we can also simplify the model， and this simplifies dramatically as well。

Because we just want to call the model onto the context and outcome Loits。



![](img/c2c4c553adf638a00076095ae2876499_139.png)

![](img/c2c4c553adf638a00076095ae2876499_140.png)

And then these logits go into softftmax and get the probabilities， etc。

 so we can sample from this model。

![](img/c2c4c553adf638a00076095ae2876499_142.png)

What did I screw up？

![](img/c2c4c553adf638a00076095ae2876499_144.png)

Okay， so I fixed the issue and we now get the result that we expect。

 which is gibberish because the model is not trained because we re initialitialize it from scratch。



![](img/c2c4c553adf638a00076095ae2876499_146.png)

The problem was that when I fixed this cell to be modeled out layers instead of just layers。

 I did not actually run the cell。 And so our neural nu was in a training mode。

 And what caused the issue here is the bathroom layer， as ba layer often likes to do。

 because Ba was in the training mode。 And here we are passing in an input。

 which is a batch of just a single example made up of the context。



![](img/c2c4c553adf638a00076095ae2876499_148.png)

![](img/c2c4c553adf638a00076095ae2876499_149.png)

And so if you are trying to pass in a single example into a bash norm that is in the training mode。

 you're going to end up estimating the variance using the input and the variance of a single number is not a number because it is a measure of a spread so for example。

 the variance of just a single number5 you can see is not a number and so that's what happened and bashm basically caused an issue and then that polluted all of the further processing。



![](img/c2c4c553adf638a00076095ae2876499_151.png)

![](img/c2c4c553adf638a00076095ae2876499_152.png)

![](img/c2c4c553adf638a00076095ae2876499_153.png)

![](img/c2c4c553adf638a00076095ae2876499_154.png)

![](img/c2c4c553adf638a00076095ae2876499_155.png)

So all that we had to do was make sure that this runs。 and we basically made the issue of。



![](img/c2c4c553adf638a00076095ae2876499_157.png)

![](img/c2c4c553adf638a00076095ae2876499_158.png)

Again， we didn't actually see the issue with the loss。 We could have valued the loss。

 but we got the wrong result because Bashm was in the training mode。



![](img/c2c4c553adf638a00076095ae2876499_160.png)

And and so we still get a result， It's just the wrong result because it's using the sample statistics of the batch。

Whereas we want to use the running mean and running variant inside the baho。



![](img/c2c4c553adf638a00076095ae2876499_162.png)

And so。Again， an example of introducing a bug in line because we did not properly maintain the state of what is training or not。



![](img/c2c4c553adf638a00076095ae2876499_164.png)

![](img/c2c4c553adf638a00076095ae2876499_165.png)

Okay， so I rewritten everything， and here's where we are as a reminder。

 we have the training loss of 2。05 and validation of 2。10。Now。

 because these losses are very similar to each other。

 we have a sense that we are not overfitting too much on this task and we can make additional progress in our performance by scaling up the size of the neural network and making everything bigger and deeper。



![](img/c2c4c553adf638a00076095ae2876499_167.png)

Now， currently we are using this architecture here。

 where we are taken in some number of characters going into a single hidden layer and then going to the prediction of the next character。

The problem here is we don't have a naive way of making this bigger in a productive way。

 We could of course， use our layers， sort of building blocks and materials to introduce additional layers here and make the network deeper。

 but it is still the case that we are crushing all of the characters into a single layer all the way at the beginning。



![](img/c2c4c553adf638a00076095ae2876499_169.png)

And even if we make this a bigger layer and add neurons。

 it's all kind of like silly to squash all that information so fast in a single step。

So we'd like to do instead is we'd like our network to look a lot more like this in the wavenet case。

 So you see in the waveNe when we are trying to make the prediction for the next characterton sequence。



![](img/c2c4c553adf638a00076095ae2876499_171.png)

It is a function of the previous characters that feed in。

 but not all of these different characters are not just crushed to a single layer。

 and then you have a sandwich。 they are crushed slowly。

 so in particular we take two characters and we fuse them into sort of like a bygram representation。

And we do that for all these characters consecutively。

 and then we take the bigrams and we fuse those into four character level chunks。

And then we fuse that again， and so we do that in this like tree like hiarchical manner。

 so we fuse the information from the previous context slowly into the network as it gets deeper。

And so this is the kind of architecture that we want to implement。Now， in the Wnets case。

 this is a visualization of a stack of dilated causal convolution layers。

 And this makes it sound very scary， but actually the idea is very simple。

 And the fact that it's a dilated causal convolution layer。

 is really just an implementation detail to make everything fast。 We're gonna to see that later。

 But for now， let's just keep the basic idea of it， which is this progressive fusion。

 So we want to make the network deeper。 And at each level。

 we want to fuse only two consecutive elements。 two characters， then two bigrams。

 then to4 gras and so on。 So let's implement this。 Okay， so first up。

 let me scroll to where we build a dataset set。 And let's change the block size from 3 to 8。

 So we're going to be taking eight characters of context to predict the9 character。

 So the dataset set now looks like this。 We have a lot more context feeding in to predict any next character in a sequence。

 And these eight characters are going to be processed in this tree like structure。



![](img/c2c4c553adf638a00076095ae2876499_173.png)

![](img/c2c4c553adf638a00076095ae2876499_174.png)

Now， if we scroll here。Everything here should just be able to work。

 so we should be able to redefine the network。You see that the number of parameters has increased by 10。

000， and that's because the block size has grown， so this first linear layer is much， much bigger。



![](img/c2c4c553adf638a00076095ae2876499_176.png)

Our linear layer now takes 8 characters into this middle layer。

 So there's a lot more parameters there。 but this should just run。



![](img/c2c4c553adf638a00076095ae2876499_178.png)

![](img/c2c4c553adf638a00076095ae2876499_179.png)

Let me just break right after the very first iteration。 So you see that this runs just fine。

 It's just that this network doesn't make too much sense。

 We're crushing way too much information way too fast。



![](img/c2c4c553adf638a00076095ae2876499_181.png)

![](img/c2c4c553adf638a00076095ae2876499_182.png)

So let's now come in and see how we could try to implement the hiarchical scheme。



![](img/c2c4c553adf638a00076095ae2876499_184.png)

Now， before we dive into the detail of the reimpleation here。

 I was just curious to actually run it and see where we are in terms of the baseline performance of just lazily scaling up the context length。

 so I'll let it run， we get a nice loss curve and then evaluating the loss we actually see quite a bit of improvement just from increasing the context length so I started a little bit of a performance log here and previously where we were is we were getting a performance of 2。

10 on the validation loss and now simply scaling up the context length from 3 to 8 gives us a performance of 2。

02。

![](img/c2c4c553adf638a00076095ae2876499_186.png)

![](img/c2c4c553adf638a00076095ae2876499_187.png)

![](img/c2c4c553adf638a00076095ae2876499_188.png)

So quite a bit of an improvement here， and also when you sample from the model。

 you see that the names are definitely improving qualitatively as well。



![](img/c2c4c553adf638a00076095ae2876499_190.png)

![](img/c2c4c553adf638a00076095ae2876499_191.png)

So we could of course spend a lot of time herening tuning things and making it even bigger and scaling up the network further。

 even with a simple sort of setup here， but let's continue and let's implement here a model and treat this as just a rough baseline performance but there's a lot of optimization like left on the table in terms of some of the hyperparameter that you're hopefully getting a sense of now Okay so let's screw up now。



![](img/c2c4c553adf638a00076095ae2876499_193.png)

And come back up。

![](img/c2c4c553adf638a00076095ae2876499_195.png)

And what I've done here is I've created a bit of a scratch space for us to just like look at the forward path of the neural net and inspect the shape of the tensors along the way as the neural net forwards。

So here I'm just temporarily for debugging， creating a batch of just say four examples。

 so four random integers， then I'm pling out those rows from our training set。

And then I'm passing into the model， the input XB。Now the shape of XB here。

 because we have only four examples is4 by 8， and this8 is now the current block size。

So inspecting XB， we just see that we have four examples， each one of them is a row of XB。



![](img/c2c4c553adf638a00076095ae2876499_197.png)

And we have eight characters here， and this integer tensor just contains the identities of those characters。



![](img/c2c4c553adf638a00076095ae2876499_199.png)

うん。So the first layer of our neural nut is the embedding layer， surpassing XB。

 this integer tensor through the embedding layer creates an output that is 4 by 8 by 10。



![](img/c2c4c553adf638a00076095ae2876499_201.png)

![](img/c2c4c553adf638a00076095ae2876499_202.png)

So our embedding table has， for each character， a 10 dimensional vector that we are trying to learn。

And so what the embedding layer does here is it plucks out the embedding vector for each one of these integers。

And organizes it all in a 4 by 8 by 10 tensor now。So all of these integers are translated into 10 dimensional vectors inside this three dimensional tensor now。



![](img/c2c4c553adf638a00076095ae2876499_204.png)

Now passing that through the flatten layer， as you recall。

 what this does is it views this tensor as just a 4 by 80 tensor。



![](img/c2c4c553adf638a00076095ae2876499_206.png)

And what that effectively does is that all these tendial embeddings for all these eight characters just end up being stretched out into a long row。

And that looks kind of like a concatenation operation。 Basically。

 So by viewing the answer differently， we now have a 4 by 80 And inside this 80。

 it's all the tendial。Vectctorors just concatenate next to each other。And then the linear layer。

 of course， takes 80 and creates 200 channels just via matrix multiplication。



![](img/c2c4c553adf638a00076095ae2876499_208.png)

So so far， so good。 Now I'd like to show you something surprising。

Let's look at the insides of the linear layer and remind ourselves how it works。



![](img/c2c4c553adf638a00076095ae2876499_210.png)

The linear layer here in a forward pass takes the input X， multiplies it with weight。

 and then optionally adds bias。And the weight here is two dimensional， as defined here。

 and the bias is one dimensional here。

![](img/c2c4c553adf638a00076095ae2876499_212.png)

So effectively in terms of the shapes involved， what's happening inside this linear layer looks like this right now。



![](img/c2c4c553adf638a00076095ae2876499_214.png)

![](img/c2c4c553adf638a00076095ae2876499_215.png)

And I'm using random numbers here， but I'm just illustrating the shapes and what happens。Basically。

 a 4 by 80 input comes into the linear layer， gets multiplied by this 80 by 200 weight matrix inside。

 and there's a plus 200 bias。 and the shape of the whole thing that comes out of the linear layer is 4 by 200。

 as we see here。Now notice here， by the way， that this here will create a 4 by 200 tensor and then plus 200。

 there's a broadcasting happening here， about 4 by 200 broadcasts with 200， so everything works here。

So now the surprising thing that I'd like to show you that you may not expect is that this input here that is being multiplied doesn't actually have to be two dimensional。

This matrix multiply operator in pythtor is quite powerful， and in fact。

 you can actually pass in higher dimensional arrays or tensors and everything works fine。 So。

 for example， this could be 4 by 5 by 80， and the result in that case will become 4 by 5 by 200。

You can add as many dimensions as you like on the left here。

And so effectively what's happening is that the matrix multiplication only works on the last dimension。

 and the dimensions before it in the inputottensor are left unchanged。🤧嗯。

So that is and basically these， these dimensions on the left are all treated as just a batch dimension。

 so we can have multiple batch dimensions and then in parallel over all those dimensions。

 we are doing the matrix multiplication on the last dimension。

So this is quite convenient because we can use that in our network now。



![](img/c2c4c553adf638a00076095ae2876499_217.png)

Because remember that we had these eight characters coming in。

And we don't want to now flatten all of it out into a large eight dimensional vector。

Because we don't want to matrix multiply AD。Into a weight matrix， multiply immediately。Instead。

 we want to group these。Like this。So， every consecutive two elements。1。

 2 and 3 and 4 and 5 and6 and 7 and 8。 All of these should be now。

Basically flattened out and multiply by weight matrix， but all of these four groups here。

 we like to process in parallel， so it's kind of like a batch dimension that we can introduce。

And then we can in parallel， basically process all of these bigram groups in the four batch dimensions of an individual example。

 and also over the actual batch dimension of the four examples in our example here。



![](img/c2c4c553adf638a00076095ae2876499_219.png)

So let's see how that works。Effectively， what we want is right now we take a4 by 80。

And multiplied by8 by 200。In the linear layer， this is what happens。

But instead of what we want is we don't want 80 characters or 80 numbers to come in。

 We only want two characters to come in on the very first layer。

 and those two characters should be fused。So in other words， we just want 20 to come in， right。

 20 numbers would come in。And here， we don't want a4 by 80 to feed into the linear layer。

 We actually want these groups of two to feed in。 So instead of 4 by 80。

 we want this to be a 4 by 4 by 20。So these are the four groups of two。

 and each one of them is 10 dimensional vector。So what we want is now is we need to change the flatten layer。

 so it doesn't output a 4 by 80， but it outputs a 4 by 4 by 20， where basically these。

Every two consecutive characters are packed in on the very last dimension。

 and then these four is the first batchsh dimension。

 and this four is the second batchsh dimension referring to the four groups inside every one of these examples。

And then this will just multiply like this。 So this is what we want to get to。

So we're going to have to change the linear layer in terms of how many inputs it expects shouldn。

Expect 80， if should just expect 20 numbers。 and we have to change our flatten layer。

 So it doesn't just fully flatten out this entire example。It needs to create a 4 by 4 by 20。

 instead of 4 by 80。

![](img/c2c4c553adf638a00076095ae2876499_221.png)

So let's see how this could be implemented。Basically right now we have an imppath that is a4 by 8 by 10 that feeds into the flatten layer。

 and currently the flatten layer just stretches it out。

 So if you remember the implementation of flatten。

![](img/c2c4c553adf638a00076095ae2876499_223.png)

![](img/c2c4c553adf638a00076095ae2876499_224.png)

![](img/c2c4c553adf638a00076095ae2876499_225.png)

It takes our x， and it just views it as whatever the batch dimension is， and then  negative1。



![](img/c2c4c553adf638a00076095ae2876499_227.png)

So effectively， what it does right now is it does E W of4 negative1， and the shape of this。

 of course， is for by80。

![](img/c2c4c553adf638a00076095ae2876499_229.png)

So that's what currently happens， and we instead want this to be a 4 by4 by 20。

 where these consecutive ten dimensional vectors get concatenated。So you know how in Python。

 you can take a list of range of 10。So we have numbers from0 to nine。

And we can index like this to get all the even parts。

And we can also index like starting at one and going in steps of two to get all the oddg parts。

So one way to implement this， it would be as follows。 We can take E。

 and we can index into it for all the batch elements。



![](img/c2c4c553adf638a00076095ae2876499_231.png)

And then just even elements in this dimension。 So at indexes 0，2，4， and 8。

And then all the parts here from this last dimension。And this gives us the even characters。And then。

 here。This gives us all the odd characters。 And basically what we want to do is we make we want to make sure that these get concatenated in Pytorrch。

 and we want to concatenate these two tensors along the second dimension。

So this and the shape of it would be 4 by 4 by 20。 This is definitely the result we want。

 We are explicitly grabbing the even parts and the odd parts。

 and we're arranging those 4 by 4 by 10 right next to each other includingcateate。So this works。

 but it turns out that what also works is you can simply use view again and just request the right shape and it just so happens that in this case。

 those vectors will again end up being arranged in exactly the way we want。

 So in particular if we take E and we just view it as a 4 by 4 by 20， which is what we want。



![](img/c2c4c553adf638a00076095ae2876499_233.png)

![](img/c2c4c553adf638a00076095ae2876499_234.png)

We can check that。 this is exactly equal to。But let me call this， this is the explicit concatenation。

 I suppose。嗯。So explicit do shape is 4 by4 by 20。If you just view it as for my by 20。

 you can check that when you compare to explicit。You got a big， this is element wise operation。

 So making sure that all of them are true。If that is the truth。So basically long story short。

 we don't need to make an explicit call to concatetnate， etc ceter。

 We can simply take this inputotsor to flatten and we can just view it in whatever way we want。

And in particular， you don't want to stretch things out with negative  one。

 We want to actually create a three dimensional array。

 And depending on how many vectors that are consecutive， we want to。Fuse， like for example，2。

Then we can just simply ask for this dimension to be 20。Use a negative one here。

 and Pytch will figure out how many groups it needs to pack into this additional batch dimension。



![](img/c2c4c553adf638a00076095ae2876499_236.png)

So let's now go to flatten and implement this。 Okay， so I scroll up here to flatten。

And what we'd like to do is we'd like to change it now。

 So let me create a constructor and take the number of elements that are consecutive that we would like to concatenate now in the last dimension of the output。

So here we're just going to remember solve that n equals n。



![](img/c2c4c553adf638a00076095ae2876499_238.png)

And then I want to be careful here because Pythrch actually has a torch to flatten and its keyword arguments are different and they kind of like function differently。

 so our flatten is going to start to depart from Pythtorch flatten。

 so let me call it flatten consecutive or something like that just to make sure that our APIs are about equal。



![](img/c2c4c553adf638a00076095ae2876499_240.png)

So， this。Basically flattens only some N consecutive elements and puts them into the last dimension。



![](img/c2c4c553adf638a00076095ae2876499_242.png)

Now， here， the shape of x is B by T by C。 So let me。

Pop those out into variables and recall that in our example down below， B was 4。 T was 8。

 and C was 10。Now， instead of doing Xt view of B by native1。This is what we had before。

We want this to be B by negative one by。And basically， here we want C times n。

 That's how many consecutive elements we want。And here， instead of negative 1。

 I don't super love to use of negative 1 because I like to be very explicit so that you get error messages when things don't go according to your expectation。

 So what do we expect here， We expect this to become T。Divide and using integer division here。

So that's what I expect to happen。And then one more thing I want to do here is remember previously all the way in the beginning。

 n was3。And basically， we're concatenating all the three characters that existed there。

So we basically are concatenated everything。And so sometimes that can create a spurious dimension of one here。

 So if it is the case that x dot shape at1 is one， then it's kind of like a spurious dimension。

So we don't want to return a three dimensional tensor with a one here。

 we just want to return a two dimensional tensor exactly as we did before。So in this case， basically。

 we will just say x equals x dots quiz。That is a pytorch function。



![](img/c2c4c553adf638a00076095ae2876499_244.png)

嗯。And squeezeque takes a dimension that it either squeezes out all the dimensions of a tensor that are one。

 or you can specify the exact dimension that you want to be squeezed。And again。

 I like to be as explicit as possible always， so I expect to squeeze out the first dimension only。



![](img/c2c4c553adf638a00076095ae2876499_246.png)

Of this tensor。This three dimensional tensor， and if this dimension here is one。

 then I just want to return B by c times 10。And so cell do out will be x。

 and then we return cell that out。

![](img/c2c4c553adf638a00076095ae2876499_248.png)

So that's the candidate implementation， and of course this should be self do in instead of just in。



![](img/c2c4c553adf638a00076095ae2876499_250.png)

So let's run。

![](img/c2c4c553adf638a00076095ae2876499_252.png)

And let's come here now。And take it for a spin。 So flatten， consecutive。



![](img/c2c4c553adf638a00076095ae2876499_254.png)

And in the beginning， let's just use8， so this should recover the previous behavior。

 so flatten and consecutive of8， which is the current block size。



![](img/c2c4c553adf638a00076095ae2876499_256.png)

![](img/c2c4c553adf638a00076095ae2876499_257.png)

![](img/c2c4c553adf638a00076095ae2876499_258.png)

We can do this。I'llLet you recover the previous behavior。So we should be able to run the model。



![](img/c2c4c553adf638a00076095ae2876499_260.png)

And here we can inspect， I have a little code snippet here， where I iterate over all the layers。

 I print the name of this class and the shape。And so we see the shapes as we expect them after every single layer in the top。



![](img/c2c4c553adf638a00076095ae2876499_262.png)

So now let's try to restructure it using our flatten consecutive and do it hiarchically。



![](img/c2c4c553adf638a00076095ae2876499_264.png)

So， in particular。We want to flatten consecutive， not just not block size， but just two。



![](img/c2c4c553adf638a00076095ae2876499_266.png)

And then we want to process this with linear。 Now， the number of inputs to this linear will not be an embed times block size。

 It will now only be n embed times 2。20。This goes through the first layer。



![](img/c2c4c553adf638a00076095ae2876499_268.png)

And now we can， in principle， just copy paste this。Now。

 the next linear layer should expect and hidden times 2。

And the last piece of it should expect and hidden times to again。



![](img/c2c4c553adf638a00076095ae2876499_270.png)

![](img/c2c4c553adf638a00076095ae2876499_271.png)

So this is sort of like an the E version of it。

![](img/c2c4c553adf638a00076095ae2876499_273.png)

So running this， we now have much， much bigger model。

And we should be able to basically just forward the model。



![](img/c2c4c553adf638a00076095ae2876499_275.png)

And now we can inspect the numbers in between。

![](img/c2c4c553adf638a00076095ae2876499_277.png)

So4 byte by 20。Was flat consecutively linked to  4 by 20。This was projected into 4 by4 by 200。

And then Basm just worked out of the box， and we have to verify that Bastm does the correct thing。

 even though it takes a three dimensional input instead of two dimensional input。Then we have 10 h。

 which is element twice， then we crushed it again， so if we flatten consecutively and ended up with the four by 2 by 400 now。

Then linear brought it back down to 200 bashroom 10 H。 And lastly we get a 4 by 400。

 and we see that the flatten consecutive for the last flatten here。

 it's squeezed out that dimension of one， So we only ended up with 4 by 400。

 and then linear in bashm 10 and the last linear layer to get our logts。

 And so the Los end up in the same shape as they were before。

 but now we actually have a nice three layer neural nu。

 and it basically corresponds toops sorry it basically corresponds exactly to this network now。

 except only this piece here because we only have three layers whereas here in this example。

 there's four layers with a total receptive field size of 16 characters instead of just8 characters。

 So the block size here is 16。

![](img/c2c4c553adf638a00076095ae2876499_279.png)

So this piece of it is basically implemented here now we just have to kind of figure out some good channel numbers to use here Now in particular。

 I changed the number of hidden units to be 68 in this architecture because when I use 68 the number of parameters comes out to be 22000 so that's exactly the same that we had before and we have the same amount of capacity at this neural or not in terms of the number of parameters but the question is whether we are utilizing those parameters in more efficient architecture。



![](img/c2c4c553adf638a00076095ae2876499_281.png)

![](img/c2c4c553adf638a00076095ae2876499_282.png)

![](img/c2c4c553adf638a00076095ae2876499_283.png)

So what I did then is I got rid of a lot of the debugging cells here and werun the optimization and scrolling down to the result。

 we see that we get the identical performance roughly so our valuation loss now is 2。

029 and previously it was 2027， so controlling for the number of parameters changing from the flat to hierarchical is not giving us anything yet。



![](img/c2c4c553adf638a00076095ae2876499_285.png)

![](img/c2c4c553adf638a00076095ae2876499_286.png)

That said， there are two things to point out， number one。

 we didn't really torture the architecture here very much。 This is just my first guess。

 and there's a bunch of hyperparameter search that we could do in in terms of how we allocate our budget of parameters to what layers number two。

 we still may have a bug inside the baroom 1 D layer。 So let's take a look at。



![](img/c2c4c553adf638a00076095ae2876499_288.png)

![](img/c2c4c553adf638a00076095ae2876499_289.png)

![](img/c2c4c553adf638a00076095ae2876499_290.png)

![](img/c2c4c553adf638a00076095ae2876499_291.png)

That because it runs but does it do the right thing？



![](img/c2c4c553adf638a00076095ae2876499_293.png)

So I pulled up the layer inspector sort of that we have here and printed out the shape along the way。

 and currently it looks like the batchstr is receiving an input that is 32 by 4 by 68， right？

And here on the right， I have the current implementation of batchchelor that we have right now。Now。

 this bashor assumed in the way we wrote it。 and at the time that x is two dimensional。

 So it was n by D， where n was the batch size。 So that's why we only reduced the mean of variance over the zeroth dimension。

 But now， x will basically become three dimensional。

 So what's happening inside the bashm layer right now and how come it's working at all and not giving any errors。

The reason for that is basically because everything broadcasts properly。

 but the bathroom is not doing what we want it to do。



![](img/c2c4c553adf638a00076095ae2876499_295.png)

So in particular， let's basically think through what's happening inside the bathroom。

 looking at what's happening here。

![](img/c2c4c553adf638a00076095ae2876499_297.png)

I have the code here。So we're receiving an input of 32 by 4 by 68。

And then we are doing here x do mean here， I have E instead of x， but we're doing the mean over 0。

And that's actually given us 1 by 4 by 68。 So we're doing the mean only over the very first dimension and has given us a mean in a variance that still maintain this dimension here。

So these means are only taken over 32 numbers in the first dimension。And then when we perform this。

 everything broadcasts correctly still。But basically， what ends up happening is。

When we also look at the running mean。The shape of it。 so I'm looking at the model that layers at 3。

 which is the first bathroom layer， and then looking at whatever the running mean became and its shape。

The shape of this running me now is 1 by 4 by 68。RightInstead of it being just size of dimension。

Because we have 68 channels。 We expect to have 68 means and variances that we're maintaining。

 But actually， we have an array of 4 by 68。 And so basically。

 what this is telling us is this baor is only。This baachem is currently working in parallel。Over。

Four times 68 instead of just 68 channels。So basically。

 we are maintaining statistics for every one of these four positions individually and independently。

And instead， what we want to do is we want to treat this4 as a bash dimension。

 just like the0th dimension。 So as far as the bash norm is concerned， it doesn't want to average。

 We don't want to average over 32 numbers。 We want to now average over 32 times  four numbers for every single one of these 68 channels。

And so， let me now。Remove this。

![](img/c2c4c553adf638a00076095ae2876499_299.png)

It turns out that when you look at the documentation of Torchdot mean。



![](img/c2c4c553adf638a00076095ae2876499_301.png)

So let's what the tors I mean。In one of its signatures， when we specify the dimension。



![](img/c2c4c553adf638a00076095ae2876499_303.png)

We see that the dimension here is not， it can be int， or it can also be a tuple of ins。

So we can reduce over multiple integers at the same time， over multiple dimensions at the same time。

 So instead of just reducing over 0， we can pass in at tuple 0，1。



![](img/c2c4c553adf638a00076095ae2876499_305.png)

And here is 01 as well。 And then what's going to happen is the output， of course。

 is going to be the same。But now what's going to happen is because we reduce over 0 and1。

 if we look at inine that shape。We see that now we've reduced。

 we took the mean over both the0 and the first dimension。

 so we're just getting 68 numbers and a bunch of spurious dimensions here。



![](img/c2c4c553adf638a00076095ae2876499_307.png)

So now this becomes  one by one by 68， and the running mean and the running variance analogously will become 1 by one by 68。

 So even though there are the spurious dimensions， the current， the current。

 the correct thing will happen in that we are only maintaining means and variances for 64。 sorry。

 for 68 channels。 And we're not cgiving the mean variance across 32 times 4 dimensions。

 So that's exactly what we want。And let's change the implementation of batchroom 1 D that we have so that it can take in two dimensional or three dimensional inputs and perform accordingly。

 So at the end of the day， the fix is relatively straightforward。



![](img/c2c4c553adf638a00076095ae2876499_309.png)

Basically， the dimension we want to reduce over is either 0 or the top 0 in 1。

 depending on the dimensionality of x。 So if x dot n dim is 2。 So it's a two dimensional tensor。

 then the dimension we want to reduce over is just the integer 0。



![](img/c2c4c553adf638a00076095ae2876499_311.png)

L of x dot and M is 3， so as a three dimensional tensor。

 Then the dims we're going to assume are 0 and1 that we want to reduce over。

 And then here we just pass in dim。And if the dimensionalality v is anything else。

 we'll now get an error， which is good。嗯。So that should be the fix。

 Now I want to point out one more thing。 we're actually departing from the API of Pytorrch here a little bit。

 because when you come to batchroom 1 D and Pytorrch。



![](img/c2c4c553adf638a00076095ae2876499_313.png)

You can scroll down and you can see that the input to this layer can either be n by c。

 where N is the back size and C is the number of features or channels。

 or it actually does accept three dimensional inputs， but it expects it to be n by c by L。



![](img/c2c4c553adf638a00076095ae2876499_315.png)

Where lets say like the sequence length or something like that。So。

This is problem because you see how C is nested here in the middle。

And so when it gets three dimensional inputs， this batchshroom layer will reduce over 0 and 2 instead of 0 and 1。

 So it basically Pytorch bam 1 D layer assumes that C will always be the first dimension。 whereas we。

 we assume here that C is the last dimension， and there are some number of batch dimensions beforehand。



![](img/c2c4c553adf638a00076095ae2876499_317.png)

嗯。And so。

![](img/c2c4c553adf638a00076095ae2876499_319.png)

It expects M by C or M by c by L， we expect M by C or n by L by c。And so it's a deviation。



![](img/c2c4c553adf638a00076095ae2876499_321.png)

I think it's O。 I prefer it this way， honestly。 So this is the way that we will keep it for our purposes。



![](img/c2c4c553adf638a00076095ae2876499_323.png)

So I redefined the layers re initialialized in neural lot and did a single forward pass with a break just for one step。

 looking at the shapes along the way。 They're， of course， identical。 all the shapes are the same。

 By the way we see that things are actually working as we want them to now is that when we look at the bathroom layer。

 the running mean shape is now one by1 by 68。 So we're only maintaining 68 means for every one of our channels and we're treating both the0 and the first dimension as a batch dimension。

 which is exactly what we want。 So let me retrained the neural lot now。 Okay。

 so I retrained the neuralette with the bug fix。 and we get a nice curve。

 And when we look at the validation performance， we do actually see a slight improvement。

 So we went from 2。0 to9 to 2。0 to 2。 So basically the bug inside the bathroom was holding us back like a little bit it looks like。

 and we are getting a tiny improvement now， but it's not clear if this is statistically significant。



![](img/c2c4c553adf638a00076095ae2876499_325.png)

![](img/c2c4c553adf638a00076095ae2876499_326.png)

![](img/c2c4c553adf638a00076095ae2876499_327.png)

![](img/c2c4c553adf638a00076095ae2876499_328.png)

嗯。And the reason we slightly expect an improvement is because we're not maintaining so many different means and variances that are only estimated users using 32 numbers effectively。

 Now we are estimating them using 32 times for numbers。

 so you just have a lot more numbers that go into any one estimate of the mean and variance。

And it allows things to be a bit more stable and less wiggly inside those estimates of those statistics。



![](img/c2c4c553adf638a00076095ae2876499_330.png)

So pretty nice with this more general architecture in place。

 we are now set up to push the performance further by increasing the size of the network。

So for example， I bumped up the number of embeddings to 24 instead of 10 and also increased number of hidden units。



![](img/c2c4c553adf638a00076095ae2876499_332.png)

But using the exact same architecture， we now have 76000 parameters。

 and the training takes a lot longer。 but we do get a nice curve。

 And then when you actually evaluate the performance， we are now getting validation performance of 1。

993 So we've crossed over the 2。0 sort of territory。 And we're at about 1。99。

 But we are starting to have to wait quite a bit longer。

 And we're a little bit in the dark with respect to the correct setting of the hyper parameters here and the learning rate and so on because the experiments are starting to take longer to train。

 And so we are missing sort of like an experimental harness on which we could run a number of experiments and really tune these architecture very well。

 So I'd like to conclude now with a few notes。

![](img/c2c4c553adf638a00076095ae2876499_334.png)

![](img/c2c4c553adf638a00076095ae2876499_335.png)

![](img/c2c4c553adf638a00076095ae2876499_336.png)

![](img/c2c4c553adf638a00076095ae2876499_337.png)

![](img/c2c4c553adf638a00076095ae2876499_338.png)

![](img/c2c4c553adf638a00076095ae2876499_339.png)

We basically improved our performance from a starting of 2。1 down to 1。9。

 but I don't want that to be the focus because honestly， we're kind of in the dark。

 We have no experimental harness。 We're just guessing and checking。 And this whole thing is terrible。

 We're just looking at the training loss。 Normally。

 you want to look at both the training and the validation loss together。

 The whole thing looks different If you're actually trying to squeeze out numbers。



![](img/c2c4c553adf638a00076095ae2876499_341.png)

![](img/c2c4c553adf638a00076095ae2876499_342.png)

![](img/c2c4c553adf638a00076095ae2876499_343.png)

That said， we did implement this architecture from the wavenet paper。



![](img/c2c4c553adf638a00076095ae2876499_345.png)

But we did not implement this specific forward pass it where we have a more complicated linear layer sort of that is this gated linear layer kind of。

 and there's residual residual connections and skip connections and so on。

 So we did not implement that。 We just implemented this structure。



![](img/c2c4c553adf638a00076095ae2876499_347.png)

I would like to briefly hint or preview how what we've done here relates to convolutional neural networks as used in the wavenet paper。



![](img/c2c4c553adf638a00076095ae2876499_349.png)

And basically the use of convolutions is strictly for efficiency。

 it doesn't actually change the model we've implemented。



![](img/c2c4c553adf638a00076095ae2876499_351.png)

So here， for example。Let me look at a specific name to work with an example。

 So there's a name in our training set and it's deandre， and it has seven letters。

 so that is eight independent examples in our model。

 So all these rows here are independent examples of deandre。



![](img/c2c4c553adf638a00076095ae2876499_353.png)

Now， you can forward， of course， any one of these rows independently so I can take my model and call。

 call it on。Any individual index， notice， by the way， here， I'm being a little bit tricky。

The reason for this is that extra at 7， that shape is just one dimensional array of8。

 so you can't actually call the model on it。 you're going to get an error because there's no batch dimension。

So。When you do extra at。List of seven， then the shape of this becomes  one by 8。

 so I get an extra batch dimension of one， and then we can forward the model。



![](img/c2c4c553adf638a00076095ae2876499_355.png)

So。That forwards a single example， and you might imagine that you actually may well forward all of these eight at the same time。

So pre alllocating some memory and then doing a four loop H times and forwarding all of those eight here will give us all the logits in all these different cases。



![](img/c2c4c553adf638a00076095ae2876499_357.png)

Now， for us with the model， as we've implemented it right now。

 this is eight independent calls to our model。But what convolutions allow you to do is it allow you to basically slide this model efficiently over the input sequence。

And so this for loop can be done not outside in Python， but inside of kernels in Ka。

And so this forward gets hidden into the convolution。So the convolution， basically。

 you can think of it as it's a for loop。Applying a little linear filter over space of some input sequence。

 And in our case， the space we're interested in is one dimensional。

 and we're interested in sliding these filters over the input data。

So this diagram actually is fairly good as well。Basically。

 what we've done is here they are highlighting in black one individual one single sort of like tree of this calculation。

 so just calculating the single example here。And so this is basically what we've implemented here。

 We've implemented a single， this black structure， we've implemented that and calculated a single output like a single example。

But what convolutions allow you to do is it allows you to take this black structure and kind of like slide it over the input sequence here and calculate all of these orange outputs at the same time。

Or here that corresponds to calculating all of these outputs off at all the positions of De Andre at the same time。

And。The reason that this is much more efficient is because number one， as I mentioned， the for loop。

 is inside the couta kernels in the sliding。 So that makes it efficient。 But number  two。

 note the variable reuse here。 For example， if we look at this circle， this node here。

 This node here is the right child of this node。But is also the left child of the node here。

And so basically， this node and its value is used twice。And so right now in this naivevo。

 we'd have to recalculate it， but here we are allowed to reuse it。

So in the combvolution neural network， you think of these linear layers that we have up above as filters and we take these filters and their linear filters and you slide them over input sequence and we calculate the first layer and then a second layer and then a third layer and then the output layer of the sandwich。

 and it's all done very efficiently using these convolutions。



![](img/c2c4c553adf638a00076095ae2876499_359.png)

So we're going to cover that in a future video The second thing I hope you took away from this video is you've seen me basically implement all of these layer LeGgo building blocks or module building blocks。

 and I'm implementing them over here and we've implemented a number of layers together and we've also implementing these containers。



![](img/c2c4c553adf638a00076095ae2876499_361.png)

![](img/c2c4c553adf638a00076095ae2876499_362.png)

![](img/c2c4c553adf638a00076095ae2876499_363.png)

![](img/c2c4c553adf638a00076095ae2876499_364.png)

And we've overall p torified our code quite a bit more。Now。

 basically what we're doing here is we're reimplementing Torch Nn。

 which is the neural networks library on top of Torch dot tensor， and it looks very much like this。

 except it is much better because because it's in pytorrch instead of jling my Jupyter notebook So I think going forward I will probably have considered as having unlocked torch do nn。

 we understand roughly what's in there， how these modules work。

 how they're nested and what they're doing on top of torch dot tensor So hopefully we' just we'll just switch over and and start using torchdot nn directly。

 the next thing I hope you got a bit of a sense of is what the development process of building deep neural networks looks like which I think was relatively represented it to some extent。

 So number one we are spending a lot of time in the documentation pytorrch and we're reading through all the layers looking at documentations。

 where the shapes of the inputs， what can they be what does the layer do and so on。

 unfortunately I have to say the pytorch documentation is not。



![](img/c2c4c553adf638a00076095ae2876499_366.png)

![](img/c2c4c553adf638a00076095ae2876499_367.png)

![](img/c2c4c553adf638a00076095ae2876499_368.png)

![](img/c2c4c553adf638a00076095ae2876499_369.png)

![](img/c2c4c553adf638a00076095ae2876499_370.png)

![](img/c2c4c553adf638a00076095ae2876499_371.png)

![](img/c2c4c553adf638a00076095ae2876499_372.png)

Very good they spend a ton of time on hardcore engineering of all kinds of distributed primitives。

 etc ce， but as far as I can tell no one is maintaining documentation， it will lie to you。

 it will be wrong， it will be incomplete， it will be unclear so unfortunately it is what it is and you just kind of do your best with what they've given us。



![](img/c2c4c553adf638a00076095ae2876499_374.png)

![](img/c2c4c553adf638a00076095ae2876499_375.png)

![](img/c2c4c553adf638a00076095ae2876499_376.png)

Number two。

![](img/c2c4c553adf638a00076095ae2876499_378.png)

The other thing that I hope you got a sense of is there's a ton of trying to make the shapes work and there's a lot of gymnastics around these multidimensional arrays and are they two dimensionmenional。

 three dimensionmensional， four dimensionmensional what layers take what shapes is it NL or NLC and you're peruting and viewing and it just get pretty messy and so that brings me to number3 I very often prototype these layers and implementations in Jupyter notebooks and make sure that all the shapes work out and I'm spending a lot of time basically babysittting the shapes and making sure everything is correct and then once I'm satisfied with the functionality in a Jupyter notebook I will take that code and copy paste it into my repository of actual code that I'm training with and so then I'm working with VS code on a side so I usually have Jupyter notebook and VS code I develop a Jupyter notebook I paste into VS code and then I kick off experiments from the RePA of course from the code repository。



![](img/c2c4c553adf638a00076095ae2876499_380.png)

![](img/c2c4c553adf638a00076095ae2876499_381.png)

![](img/c2c4c553adf638a00076095ae2876499_382.png)

So that's roughly some notes on the development process of working with neural lens Lastly。

 I think this lecture unlocks a lot of potential further lectures because number one。

 we have to convert our neural network to actually use these dilated causal convolutional layers。

 so implementing the comenet。

![](img/c2c4c553adf638a00076095ae2876499_384.png)

Number two， potentially starting to get into what this means。

 where residual connections and skip connections and why are they useful？



![](img/c2c4c553adf638a00076095ae2876499_386.png)

Number three， as I mentioned， we don't have any experimental harness。

 so right now I'm just guessing checking everything。

 This is not representative of typical deep learning workflows。

 you have to set up your evaluation harness， you can kick off experiments。

 you have lots of arguments that your script can take you're kicking off a lot of experimentation you're looking at a lot of plots of training and validation losses and you're looking at what is working and what is not working and you're working on this like population level and you're doing all these hyperparameter searches and so we've done none of that so far so how to set that up and how to make it good。

 I think as's a whole another topic。

![](img/c2c4c553adf638a00076095ae2876499_388.png)

![](img/c2c4c553adf638a00076095ae2876499_389.png)

![](img/c2c4c553adf638a00076095ae2876499_390.png)

And number three， we should probably cover recurren neural networks。

 ANs LSTMs groupss and of course transformers， so many places to go and we'll cover that in the future for now。



![](img/c2c4c553adf638a00076095ae2876499_392.png)

![](img/c2c4c553adf638a00076095ae2876499_393.png)

![](img/c2c4c553adf638a00076095ae2876499_394.png)

Sorry， I forgot to say that if you are interested， I think it is kind of interesting to try to beat this number 1。

993 because I really haven't tried a lot of experimentation here and there's quite a bit of longing fruit potentially to still purchase further。

 So I haven't tried any other ways of allocating these channels in this neural net。

 Maybe the number of dimensions for the embedding is all wrong。

 maybe it's possible to actually take the original network which is one hidden layer and make it big enough and actually beat my fancy hierarchical network。

 It's not obvious。

![](img/c2c4c553adf638a00076095ae2876499_396.png)

![](img/c2c4c553adf638a00076095ae2876499_397.png)

![](img/c2c4c553adf638a00076095ae2876499_398.png)

![](img/c2c4c553adf638a00076095ae2876499_399.png)

![](img/c2c4c553adf638a00076095ae2876499_400.png)

It would be kind of embarrassing if this did not do better， even once you torture it a little bit。

Maybe you can read the weightnet paper and try to figure out how some of these layers work and implement them yourselves using what we have。

And of course， you can always tune some of the initialization or some of the optimization and see if you can improve it that way。

 So I'd be curious if people can come up with some ways to beat this。 and yeah， that's it for now。



![](img/c2c4c553adf638a00076095ae2876499_402.png)

![](img/c2c4c553adf638a00076095ae2876499_403.png)

![](img/c2c4c553adf638a00076095ae2876499_404.png)