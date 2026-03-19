# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p03 P03 Lecture 2 - Basics of Neural Networks -BV1o7jzzwEST_p3-

Good afternoon， everyone。 Let's get started with lecture 2 of efficient and model AI。

 So today we are going to learn about basics of neural networks。😊，As we have seen the last lecture。

 there is a big gap between the supply and and demand of AI computing。

 where the demand of computation is growing really fast。

 as indicated by the model size of recent large language models。

And more law is roughly doubling every two years， but the deep learning models is getting more than four times larger every two years。

 so there's going to be a gap which motivated us to bridge this gap with model compression and acceleration techniques So in the last lecture just do a quick recap。

 we went through several examples from vision to language to visual language model and and also the multimodality models to give the overview about the latest advancement of airI computing and how much demand of computing they need to motivate us to build this efficient algorithms and systems to accelerate efficient air computing。

So today we are going to start with those details， technical details to first review the term terminology of neural networks such as neurons。

 synapses， activation， feature， weight， parameter， etca。And also。

 we are going to review the popular building blocks with the fully connected layer convolution layer group convolution。

 depth convolution， especially， especially to understand the computation demand behind that。

 including both the memory demand out of and also the computation demand。

We are also going to introduce those efficiency metrics， including the number of parameters。

 how to calculate the number of parameters， the model size， the peak activation size， the Mac， flop。

 flops， OP ops， what is the difference between them。

 what is the relationship between them latency throughput。And if you have time。

 we're going to go through lab0， which is a tutorial on Pytorrch。So La zero is optional。

 but make sure we also want you to make a submission on Cans， it's not going to be graded。

 but it will get yourself familiarized with the proper procedure all way submit homework on Cans。

And for all the announcements related please keep an eye on our course website。

 we are going to make all the announcements， the lecture slides， lecture videos。

 homeworks assignments， everything will be released at our course website。

 which is efficient Ml do AI So if you have not bookmarked it make sure to bookmark our course website。

 efficient M dot AI and check it every week to get the latest slides videos and homeworks all the home we have five labs。

 the schedule of the lab released will be also announced in the efficient M do AI website so make sure you bookmark our website。

Okay， so let's jump into neural synapse。 So as shown on the right hand side。

 we have a synapse on the left and and。We have input X on the left， outputll X on the right。

 and we have the synapse that compute the weighted average of the input axon。

 So the synapse is basically the weight of the neural network。

And so the right part is the synapses right so we use the terminology interchangeably between synapses。

 weights and parameters， so if you heard these terms， they mean the same thing。And the neurons。

 features and activations， we use these terminologies interchangeably。 They also mean the same thing。

So in this example， we have two layer neural network and get an output。

 So the dimensionality of these hidden layers determines the width of the model。

 right So the width of the model matters a lot to the efficiency of neural networks。

So you can design a wide but shallow network。With the the same number parameter as narrow but deep neural network。

So and I guess which one is more accurate and which one is more hardware efficient in these two scenarios。

One is a very deep。But our narrow neural network， The other is a shallow but wide neural network。

 Which one is more hardware friendly。我。TheWd and shallow and why is that the case？不能费。

Exactly fewer number of kernel calls and I have more parodism to fully exhaust the number of threads in the GPUs so from the efficiency perspective。

 a wide and shallow network might be more efficient in the meantime from the accuracy perspective from the accuracy perspective really deep network matter helps a lot So there is a tradeoff you don't get a free lunch on both side So that's the beauty of neural network architecture design where we're going to visit in the later part of this lecture how to trade off between this hardware hardware efficiency and also the accuracy So let's visit a few popular neural network layers starting from the fully connect layer also called a linear layer。

So in the linear year， you have a weight matrix， which is of dimension C input channel times CO。

 which is the output channel Okay， so the number parameters here is C times CO okay and this is the input activation C and this is the output activation CO。

So that's the input feature dimension， usually when we are talking about efficiency computing it's super important to understand the dimension of each tensor okay later when we are going to build the model to calculate the flops number of operations and also the model the parameter size。

 the model size， it all concerns about the dimension of of each tensor。

 so it's very crucial to figure out the dimension of the input feature。

 output feature map weight feature and also the bias。Especially the bias。

 when we are going to learn about the efficient ond training。

 we are having a technique called bias only update or recently the Laura which concerns about the bias。

 so we are going to revisit that in later part of the lecture。

So very simple output equal to the weighty sum of the input。 So that's the fully connected layer。

 also called the linear layer。What do we if we have multiple inputs so here we have a batch size of who we have two inputs right so the weight dimension stays the same it's C times CO。

 but the input becomes n time C and output feature map becomes n times CO。Comvolution layer。

 so the output neuron is no longer connected to all the inputs。

 but is connected only to the inputs within the receptive field。Okay。

 so we have a input feature and this is the spatial dimension now we just assume it's 1D convolution a little let jump into 2D in this 1D convolution this is the channel dimension。

 this is the spatial 1D spatial dimension and we apply this green filter here we also have the input channel dimension C and here we have the KW which is the filter dimension。

And then we have multiple such filters。 Okay， each filter is going to convolve with the input and produce one output。

And we can shift it， shift this sliding window by one to get another output and can shift it again to get another output。

 So as a result， the output feature dimension output channel dimension is three since we have three kernels for the weight。

And the weight dimension is basically C times k times co since each kernel dimension。

 we have a C times k， and we have CO this amount of kernels。And finally。

 we have a bias with a dimension of CO。But now let's generalize that to two dimensional convolution。

 toD。Okay，As we can see， we added another dimension is 2D convolution。

 but looks like the feature map is looks like the feature map is three dimensional plus because for each X Y location。

 we have a channel dimension okay， the channel dimension so the for 2D convolution。

 the feature map is actually 3D。So the activation map， the H times W。

 assuming iming you have a picture with is W height is H。And then we'll apply a filter。

 which is KH by KW， which is the filter dimension for the H and W dimension with the same input channel dimension C。

And then we have multiple attributes， three suchs， which is equal to CO in this case。

Im looking shifted by one to get another output。Shifted by2 to get the another output that we can shift in another dimension。

On and so on。 So at the output feature map， three by three， output feature。

And how do we calculate the size of the Oppo feature map is equal to the size of the input minus the size of the kernel plus one and y plus one。

 because you can shift Kh minus1， this amount of shifts。

And applying an each shift you get a one more output。

 So platecho equal to H minus KH plus one in this case， the H equal to4， the input is 4 by4。

And then the K， the kerneld size is 3。 Therefore， the output dimension is 4-3 plus 1。

 It will be 2 in this case。Let's also talk about padding， okay。

 so padding can be used to keep the output feature map the same as the input feature map。

 otherwise using convolution， the feature map will get smaller and smaller as you have a deeper number of layers。

So one common way is to do to apply zero padding had the input boundaries with the zero。

 which is the default pytorrch。There's for example， in this case。

 the original item width equal to5 in this animation and kernel size is three。

 so the output height and weight equal to5 plus2 times 12 p okay padding equal to one we pad one on each side and minus3 plus1 equal to 5 so the output feature map is the same as the input compared with the initial version like in here the output becomes。

Becomes smaller。 The input is 3，4 by 4， but the output becomes2， as we can see on the。



![](img/74c33c5587ac05d2ad1d20699864ba38_1.png)

On the example here right initially the input is four by four。

 output becomes two and after we apply padding after we apply padding。

 the input and output are both5 by5 in this case。

![](img/74c33c5587ac05d2ad1d20699864ba38_3.png)

So we can have zero padding， there are also other methods to apply padding， for example。

 using reflection padding， so for example right here。

 the added number is the reflected that value of the original feature map。

 we can also apply the replication padding to use the closest number the replicate that to apply the padding。



![](img/74c33c5587ac05d2ad1d20699864ba38_5.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_6.png)

But zero pattern is still the widely used approach。So after padding。

 let's now talk about the receptive field， for example， the output pixel here， how many pixels。



![](img/74c33c5587ac05d2ad1d20699864ba38_8.png)

才能才能适应 the previous layer。It can see。Three by three pixels， if the kernel size is three by three。

 right， and each pixel here is another three by three。

So how many pixels from here here actually5 by5 and one more layer get a 7 by7 receptive field and why do we need a large receptive field。

 we want to understand the relationship between different pixels。



![](img/74c33c5587ac05d2ad1d20699864ba38_10.png)

For example， a car on the road versus some pedestrian also on the road。

 the relationship between the car and pedestrian I means whether you can drive or you can you should avoid the pedestrian right so the relationship matters for those high level vision tasks and why people imagine transformers later because transformer give you a global receptive field you can see every pixel can attend to every pixel in transformers we're going to cover later so the principle is that a larger receptive field helps a lot is very crucial to highle image understanding。

So with two layers， three kernels， we can see a receptive field L5 by 5。

 and in general the equation is here with L layers。

 the receptive field size equal to l times kernel size minus1 plus one。



![](img/74c33c5587ac05d2ad1d20699864ba38_12.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_13.png)

So for two layers， kernel size equal to three，s the receptive field is five。And if have three layers。

 cono size is three， the re field is7。So the problem is that for large images in order to have a large receptive field we have to have very deep layers。

 we need many， many layers and we just talk about that in the early part of the lecture if you have too many layers you have lots of kernel calls you also have to store a lot of activations activations has to be stored during back propagation increasing our training memory so how do we have a large receptive field at the same time we don't want to have so many layers。

So we can done sample inside the neural network。 One example is to use the strideed convolution layer。

So compared with str equal to one， which is on the bottom。

So on the top shows the stride equal to2 Okay， so rather than every pixel sees the adjacent3 by3 pixels now is see5 by5 Okay。

 the adjacent green adjacent green 3 by three right rectangle is shifted by not one pixel。

 but two pixels。 Okay， you can see。

![](img/74c33c5587ac05d2ad1d20699864ba38_15.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_16.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_17.png)

This three by three versus this three by three is actually shifted by by two。

 so that's a stride of two every time you don't move one step， but you move two steps。



![](img/74c33c5587ac05d2ad1d20699864ba38_19.png)

So that's the stranded convolution。In this case， for two layers and kernel size equal to 3。

 the receptive field becomes 7Previous it was5， now it was7 you have a larger receptive field with the same number of layers。

So this is very helpful for reducing the number of layers， reducing the number of weights。

 reducing the number of activations。But have the same receptive field。

 but of course you may lose a bit accuracy because the model capacity might be smaller。

But everything is trade off。 There's no no free lunch in deep neural network design。

 Everything is about constrained optimization。Which makes the optimization highly interesting。Okay。

 so。Our goal is to continue reducing the number of parameters。 Okay， so for convolution layer。

 each oppo channel is connected to all the input channel to all the input channel， okay。

How to reduce the amount of computation。 people demand this group convolution later。 Okay。

 so previously we have just one group。 Every channel is Op channel is connected with all the input channel。



![](img/74c33c5587ac05d2ad1d20699864ba38_21.png)

Now we can divide them into two groups。 So for the first group。

 only half of the input channel is connected。

![](img/74c33c5587ac05d2ad1d20699864ba38_23.png)

And for the second half。That's the second group okay so effectively if we have G groups okay。

 we can see the feature map size doesn an input feature map size and output feature map size doesn't change stays the same as before but the number of weights will be G times smaller okay。



![](img/74c33c5587ac05d2ad1d20699864ba38_25.png)

Will be G times smaller so CO will be divided by G and C will also be divided by G and we have G amount of such such filters Okay。

 therefore the total amount of weights is reduced by G okay， so that's the group convolutionator。



![](img/74c33c5587ac05d2ad1d20699864ba38_27.png)

And what is the extreme of group evolutionvol？The number of group。

The number of group will be equal to the number of input or output channel。

 so which is exactly this case。

![](img/74c33c5587ac05d2ad1d20699864ba38_29.png)

Previously we have two groups now we have CO groups in this case it's eight right we have eight groups。

 so each oppo channel is only connected to one input channel。



![](img/74c33c5587ac05d2ad1d20699864ba38_31.png)

So the number number number of input feature features stays the same and the number of weights will be C。

 which is the same for CIMC so we just use C times KH and KW。

 which is the extreme case of group convolution， called depthPS was convolution layer。

 which is quite widely used seems 2015， 2016 where when mobileNe was invented。



![](img/74c33c5587ac05d2ad1d20699864ba38_33.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_34.png)

The next， Pu layer， we want to have a smaller feature map。

 originally the input image might be like 1k by 1 k is pretty large。

And we want to have a smaller feature map and condensed information， right？

This is actually quite useful for large resolution input we want to quickly pull the feature map to make it smaller。



![](img/74c33c5587ac05d2ad1d20699864ba38_36.png)

So here we have an example with the four by four input feature map and how do we put it to two by two。

 we can you either use max Pu so for every four by four input。

 we find the max element within that group。Or we can do this kind of average footing。

 finding the average in the blue area， finding the average for the yellow area to do the average footing。



![](img/74c33c5587ac05d2ad1d20699864ba38_38.png)

The good thing about pool is that there's no learnable parameters， or you can assume， yeah。

 so contains zero weight， which is very parameter efficient。Next。

 let's talk about normalization layer， so normal batch normalization came roughly in 2015 or New Europes15 or7 or 16。

 roughly  seven or eight years ago， which later becomes quite useful to stabilize the training。

For example， the layer norm also become super helpful in the age of attention transformers。

 So what exactly is normalization。So we will normalize。

The feature map to make the optimization faster。 Okay， so how do we apply that。

 So we minus the feature map minus the mean of that tensor Okay， and divided by the sigma。 Okay。

 so we want to make sure we want to minus the mean and divided by the standard deviation over a set of pixels or tensors。

 if it is no vision， okay。

![](img/74c33c5587ac05d2ad1d20699864ba38_40.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_41.png)

So use as a reminder how to calculate the meaning and standard deviation。



![](img/74c33c5587ac05d2ad1d20699864ba38_43.png)

And note here we have a small sigma right here， Okay。

 so that is due to we want to avoid dividing by zero， so we put a very small number over there。



![](img/74c33c5587ac05d2ad1d20699864ba38_45.png)

And then we learn a a channel linear transformation。

 which is indicated by the scanning factor and also the bias right here to compensate for the possible loss of representational ability okay？



![](img/74c33c5587ac05d2ad1d20699864ba38_47.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_48.png)

So how do we define this set of pixels or set of tensors on the bottom。

 it shows four different ways to find that group of pixels。

 the first one very widely used in CNNs called batch normalization。



![](img/74c33c5587ac05d2ad1d20699864ba38_50.png)

Okay， so it's normalizing across the N dimension。 N is the image dimension。Okay， and also。

 we just use a single C dimension across all the H and W heightened width dimension。 Okay。

 normalized across different batches。

![](img/74c33c5587ac05d2ad1d20699864ba38_52.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_53.png)

Second one is quite widely used in the attention mechanism。

 so for different input for each input across different H and W and C C is a channel dimension。

 make sure it's normalized so for each token in the attention mechanism when you are doing the attention after each token is normalized then the attention map makes sense otherwise if it's not normalized the attention map will be。



![](img/74c33c5587ac05d2ad1d20699864ba38_55.png)

Much harder to optimize。There's also the instance normalization， Okay。

 just normal across the H and W dimension， not the C dimension。And when the C is too large。

 there is also the group normalization on the right。

 which divide the C by several groups and only normalize within that group。

There's a lot of tricks we can play for the normalization layer， for example。

 when we are doing fine cuY。Actually normalization layer， the number of parameters is very small。

 so we can only fine tune the weight the biasers and also the scalingkating factor in the normalization layer。

 making the fine tuning much more parameter efficient。

The normalization layer can also absorb the transformation of such as smooth quantization。

 so without having incurring another kernel call， we can absorb lots of the computation in the IP log or afuse it with the normalization layer so we we are going to visit them in later part of this lecture。

Okay， next one is activation function。So we have seen many different activation functions。

 but let me talk about the efficiency and accuracy trade off here。

Sigmoid very ancient activational function。TheIt ranges between 0 and one is's very easy to quantize。

 very efficient to quantize because the dynamic range is very limited and its fixed between 0 and1。

But what is the drawback？

![](img/74c33c5587ac05d2ad1d20699864ba38_57.png)

Greding vanish， right so if the battery will be super small or super large， there's no gradient。



![](img/74c33c5587ac05d2ad1d20699864ba38_59.png)

And then people come up with relu okay when it's positive， the gradient never vanishes。

 but when it's negative， the neuro is basically that。

 there's no way to put it back because there's no gradient anywhere when the value is smaller than zero。

But the what is good about it is that it's very easy to specify since we are going to talk about pdence and sparsity in the later part of this lecture。

 the relu activation function naturally brings sparsity because lot of the activation once they are negative they become zero and zero multiply by anything is zero so you don't have to compute on it you don't even to store it you can just do a mask showing that this is zero just using one bit。



![](img/74c33c5587ac05d2ad1d20699864ba38_61.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_62.png)

And the gradient is why everywhere else， okay， so you don't even need to save this feature map。

 you can just save a bit mask。For this for that tensor if it is the bit mass is zero。

 then the output is zero if the back bit mass is one it will just copy the feature map from the previous output so very activation friendly。

 sparsity friendly simple。But what is the downside， The dynamic range is super large。

 it's not easy to quant， so people invented Ra 6 okay Ra 6 to cap the long largest value to be6。

 that's why people call it Ra 6， okay， it's purely empirical。

And that makes the quantization range much more constraint reducing the dynamic range make it easier to quant。

Another drawback is that there's no gradient in the negative region， so people invented leaky red。

 okay， there's a smaller scope slope on the negative side okay so you can also let the gradient have the gradient flow in the negative region。



![](img/74c33c5587ac05d2ad1d20699864ba38_64.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_65.png)

But the downside is that you no longer have this sparsity benefit。



![](img/74c33c5587ac05d2ad1d20699864ba38_67.png)

If the value is small， it is negative， it's no longer zero。



![](img/74c33c5587ac05d2ad1d20699864ba38_69.png)

And then people are using neural architecture search。

 find a very interesting activation function or a switch。

 a Sw basically very similar to Railu that is using x divided by1 plus e to the minus of x。



![](img/74c33c5587ac05d2ad1d20699864ba38_71.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_72.png)

But people later find it hard to implement hardware right so people come up with approximated switch called higher switch okay so when x is smaller than minus3 is zero above three is just x in between that。

The value is x plus three divided by 6 okay so all this activation function somehow have something to do with efficiency。

 like sparsity quantization， dynamic range easy to implement so that's the story behind the progression of different activation functions。



![](img/74c33c5587ac05d2ad1d20699864ba38_74.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_75.png)

And finally， transformers， transformer are getting super important since the invention in 2017， 2018。

 we learn more about Transformer architecture in lecture 12 we have a dedicated lecture just to talk about transformers。

 the entire pipeline entire structure of transformers。

 so let's just give a very simple overview today。So there are two stages。

 the encoding stage and the decoding stage for each stage。

 we have a more add attention followed by FFN。

![](img/74c33c5587ac05d2ad1d20699864ba38_77.png)

Fit over the network and this is the architecture for the attention mechanism。

 you have three tensors， QKV very key and value we do a attention dot skilled dot product attention and then pass it through a linear layer get the O QKVO those are the four activation tensors and there's no weight in the attention mechanism that's the in the middle part only weight in the QKVO transformation okay。



![](img/74c33c5587ac05d2ad1d20699864ba38_79.png)

And the detailed way to do that for the query key value。

 the design is actually very analogous to the retrieval system。 Just take a YouTube search。

 as example， the query is like the text prompt in the search bar。

 and the key would be like the title or description。

 some short information about the video and value would be the corresponding video。

So you do a dot product with a query and a key to get the similarity and use the similarity to fetch to do a weighted average of the value。

And remember， we want to divide the Q and K by a normalization factor。

 which is square root of D to accommodate for the dimension change to make the optimization more stable and followed by the softm to get a attention map n by N attention map and use that attention map to do a weighted average weighted sum of the of the value and later part of the lecture were going to visit in the attention map。

 the n by N attention map would be the bottleneck for both computation and the on the memory since this is growing quadraically with the number of token N and for images。

 the number of token also grow quadraically with the resolution So n square would be super expensive。

So there's sparseity opportunity， not all attention， not all token need to attend to each other。

 sparse attention， we're going to introduce that。And also flash attention we can use in place attention to minimize the data movement so that we can have a constant almost constant memory。

But the flps is not reduced。 So in order to deal with that problem。

 we are going to introduce long context techniques。All related to this attention mechanism。

 So although attention itself doesn't have any weights， there's a lot of interesting。

 interesting stuff we can explore， even the KB cash。

They become the activation when we are calculating the KB cache。

 but when we are using that to generate the next token。

 they become the weight when new tokens is generated， so how do we quantize。

 how do we roomrune the KB cache， we're also going to cover that in later part of the lecture。

Let's continue the lecture to talk about the efficiency metrics。

 How should we measure the efficiency of neural networks？

So there are several pillars we want to achieve at the same time。

 but it's pretty hard having a smaller model。 So when we are when you're uploading the model to the Apple store。

 it's pretty small right You don't want to download a model that is hundreds of a gigaby that iss too hard to download。

And also we want to have a faster model it give you the real time prediction。

 never miss a pedestrian on the road for a selfdiving car and also generate images instantly on your phone。

 for example。And also greener model， taking less battery， for example， iPhone on the mobile devices。

 you don't want to join your battery with its AI applications。And that concerns the。And computation。

 the memory is is determining the storage latency and energy。

 so we are going to introduce several efficiency metrics on the right hand side。

 some of them are memory are related， some of them are computation related on the memory side will introduce how to count the number of parameters the model size。

 the total activation size and peak activation size。



![](img/74c33c5587ac05d2ad1d20699864ba38_81.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_82.png)

For the computation related， we are going to talk about what is Mac， what is flop， what is flops。

 what is opb， what is ops。

![](img/74c33c5587ac05d2ad1d20699864ba38_84.png)

So let's first talk about latency， so what is latency？

Leadency measures the delay for a specific task。And let me directly show you examples on the left hand side is a high latency right each to predict the segmentation mask of output takes a long time。



![](img/74c33c5587ac05d2ad1d20699864ba38_86.png)

And right hand side is lower dency， only  46 milliseconds to process each frame。

What is the throughput it measures the rate at which data is processed on the left hand side is low throughput you can process six videos per second on the right hand side is high throughput 77 videos per second this is from a temporary shift module paper for video understanding we are going to introduce data。

So what is the relationship between latency and the throughput？

Does higher throughput translate to lower latency， Does lower latency translate to higher throughput？

So that's the example。The first design， the latency is 50 meiseconds。So every 50 minute second。

 we can process my image。So how many images can we process every second is 20， right？

On the design tool， we have higher parism。 We can process four images at the same time。

 each taking 100 millisecond so they didn't need to process each image from start to end。

 it's 100 millisecond。And the throughput would be 40 images per second since we are processing four such image at the same time。

So on the left hand side is having a lower latency by lower throughput。

 right hand side is having a higher latency by higher throughput。As a result。

 higher throughput doesn't translate to lower latency。

And lower latency also doesn't translate to higher throughput。On the mobile。

 we sometimes care about the we mostly care about the latency on the data center on batch processing tasks。

 we care about the throughput， so those are very important metrics。

 latency and throughput sometimes we want to make sure we report both。

So what is the factors that impact the latency？So there are two factors that is determining the latency。

 one is the computation， one is the memory okay。The T of computation equal to the number of operations in a neural network model divided by the number of operations。

 but the process can process per second。And the bottom is the hardware specific characteristic on the top is neural network specific。

And then team memory also determine is determined by two factors。

 the activations and also the weight to move the activation and move the weight。

 So this is about inference， if it is training it also concerns about communication about the gradient。

So T datata movement of weight equal to the weight， the model size divided by the memory bandwidth。

Otherwise specific， neuro network specific。And T they movement of activations is determined by the input activation size plus the output activation size。

 This is first order， all these are first order approximations to give you a ballpark estimation。

Divided by the memory bandwidth of the processor。So which one is more expensive？

So this is a figure showing the energy consumption。

Of different operations from a 32 bit inte add to accessing a register file to multiplication。



![](img/74c33c5587ac05d2ad1d20699864ba38_88.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_89.png)

So accessing the IRM cache， to access to the DRM cache。



![](img/74c33c5587ac05d2ad1d20699864ba38_91.png)

we can to access the D memory， we can see that accessing the D memory could be super expensive 640 people juice versus just doing a 32 bit ad。

 It's just 0。1 people。 So accessing the memory is a lot more expensive than doing the arithmetic。



![](img/74c33c5587ac05d2ad1d20699864ba38_93.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_94.png)

Like two orders of magnitude， more energy is consumed by access in the memory。 So keep in mind。

 computation is cheap， memorym， data movement is very expensive。



![](img/74c33c5587ac05d2ad1d20699864ba38_96.png)

So。It is the data movement that is joining the battery。系。

So let's talk about how to calculate the number of parameters since data movement is expensive。

So parameter is the number of weight neural network。 for example， in the linear layer。

 the weight tensor is C in times C out。 So the number parameter is just C。C in time C out。

In a convolution layer， be a weight tensor。

![](img/74c33c5587ac05d2ad1d20699864ba38_98.png)

Its four dimensional。 each kernel has K H K W times C in。 and we have C among CO number of kernels。

 So altogether， we have a。

![](img/74c33c5587ac05d2ad1d20699864ba38_100.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_101.png)

Multiplying these four terms together to get the total number of parameters for a convolution layer。

For a group convolution we divided the C and CO by G so CI is divided by G CO is divided by G。

 but we have G amount of such kernels， so altogether we have only one g and the denominator G times smaller compared with the convolution with the same dimension。



![](img/74c33c5587ac05d2ad1d20699864ba38_103.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_104.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_105.png)

For depthwise convolution， where G equal to C I equal to C O。

 therefore the total number prime equal to C times K H times KW。

And let's see the number parameters for popular neural networks for Nflnet right so let me do the calculation for the first layer where the channel number is input channels3。

 output channel is 96 and the kernel size is 11 by 11 so the first layer。

 the number parameter is 96 output three input 11 by 11 okay。



![](img/74c33c5587ac05d2ad1d20699864ba38_107.png)

And similarly， we can calculate the second layer， it's a group convolution。

 so we divide a number of parameters by two since group size is2。



![](img/74c33c5587ac05d2ad1d20699864ba38_109.png)

So I'll give you one minute to calculate to think about the layer number parameters for the next layer here 13 by 13 image size。

And three by3 convolution。The channel number is 2 384。

So here' is a quick answer since the input channel is 2256。

 output'll is 384 and the channel number kernel size is three by three。

 this is the way to calculate that。

![](img/74c33c5587ac05d2ad1d20699864ba38_111.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_112.png)

And finally， for that fully connected layer， you just multiply the input channel with the op channel to calculate the total number of weights。

 which is 61 million in total。So how does that translate to the model size between the number parameters to model size was the relationship？

You want to multiply the number of bytes for each parameter with a number of parameters， okay。

 so the number of parameters with multiplied with bit width， look at the model size。So。For example。

 Alex N has 61 million parameters。 If each weight is in is represented by the。

A single precision 332 bit number and how many bytes are there in a 32 bit？You have four bytes。

 right， 32 bits equal to four bytes， so 61 million times4， you have 224 megabytes。

So make sure you have the prerequisite so that you can understand these concepts relatively easily many bits per bite。

And if you want to quantize the weight to integer right to8 bit integer。

 what is the total storage for the weight？So8 bit that equal to one by8， 61 million parameters。

 that's 61 megabitte。61 MBbyte， four times smaller， right， compared with to 32 bit。

And later part of this lecture， we are going to learn about an activation of where weight only quantization AWQ to quantize it to four bit。

 and4 bit will be another two times smaller。So that you can fit large language model locally on your laptop。

Okay， so now let's switch gear to talk about the total and the peak number of activations。

So activation is the bottleneck for seeing inference， not the parameters， for example。

 here from ResNe to mobileNe。

![](img/74c33c5587ac05d2ad1d20699864ba38_114.png)

Number of parameters it reduce a lot by four times more than four times。



![](img/74c33c5587ac05d2ad1d20699864ba38_116.png)

But the activation， the peak activation didn't decrease， got increased。

 So for how to reduce the activation activation is very crucial。 The deeper the later。

 the more number of activations， usually that' the case。😊。

And also the peak activation determines the memory bottleneck， for example。

 the third layer here determines what is the max memory you are going to consume when you are doing the inference。

So the imbalanced memory distribution happens very popular for Cs， why is that a case。

 because the first couple layers you have very high resolution and then square。

 and later you have a lower resolution due to down sample。For example。

 if a microcontroller has only 256 kilobyte of IRAM in the。Of SRM to hold these activations。

 you want to make sure the largest layer， for example， here。

 doesn't exceed the SRM so that you can put all the activations in the fast SRAM。

Actation is also becoming the memory bottleneck in training。In Cs for large language models。

 the number of parameters also the bottleneck， that's why people later proposed this model parism to do the sharding of the weight so here is an example for the scenes where this is showing the number of parameters versus the number of activations the number of activation is like seven times larger than the number of parameters when you are doing training due to the batch the activation is pretty large occupying a lot of the GPU memories。

And here from Re than 50 to Mo9V2 1。6， they pretty much have the same accuracy。

 so it's apples apples comparison， the parameter is reduced by four times。

 but the main memory bottleneck， which is the activation didn't improve much only 1。1 times only 10%。

 so optimizing the activation is hard。

![](img/74c33c5587ac05d2ad1d20699864ba38_118.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_119.png)

And usually for Cs， the distribution for the weight and activation is different the middle part is the activation。

 the blue part is the weight。😊，It's U shaped and initially the activation memory is large later the weight memory is large。

 this is due to it has high resolution and this is due to it has larger amount of channels。

So this is calculating the number of activations of LXnet so C times h times w that's the way to calculate the activation size and if you add them together can see this is total amount of activations for LNe。

And the peak activation is roughly first order of approximation， number of input。

 activation plus the number of output activation。Okay。

 now let's switch gear to talk about compute funded metrics。 for example， Mac。

 So what is a Mac is not McDonald is multiply and accumulate multiply and accumulate。

 So a equal to a plus B times C that's one Mac1 accumulation and one multiplication。

It usually comes as a single instruction in GPUs。So for matrix vector multiplication。

 how to calculate the number of maxs。For example， on the top right corner。

 this is a matrix matrix vector multiplication， Okay， so we are going to produce。



![](img/74c33c5587ac05d2ad1d20699864ba38_121.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_122.png)

M outputs in order to produce each output we need to compute。

N notplication as in order to produce each output， we need to calculate n max。

 So altogether we have m times n max。

![](img/74c33c5587ac05d2ad1d20699864ba38_124.png)

![](img/74c33c5587ac05d2ad1d20699864ba38_125.png)

What about a matrix matrix modificationplication for GEMN。

 general matrix matrix modificationplication？On the right hand side， we have an M by K matrix。

 Im a K by N matrix。And produce a M by N output。So we have M by n output in order to calculate each output。

 we need K max， so altogether we need M times n times K max。

So here we are showing the number of Macs for different layers for the linear layer。

 we just talk about that， the Mac equal go to the C in times C out assume batch size of one。

And for convolution is actually multiplying six terms together。 Okay。

 so we are calculating this is the amount of output feature output features we have to calculate。

 which is W times W output H output times CO and in order to compute。

In order to compute each output pixel， how many Macs do we need？

We need the entire kernel to be to be conved， so that's kW times k times C。

 so multiplying them together we have to multiply these six terms together six。

 three from here and three from here that's the way to calculate the convolution max。

With group convolution， okay， we just divided by G G is the number of groups and for depthwise convolution C equal to G。

 So we canceled one term multiply these five terms together C gets canceled due to G equal to C。

And this is calculating the max for AlexXnet， for example。

 each layer multiplying these six terms together。If it is group convolution divided by the number of groups in this case。

 two in this case。And finally， for the last three fully connected layers is just input channel times the output channel。

 two terms multiplied together， where ultimately you have a 724 million max in total。Okay。

 so now let's switch gear to talk about flop and flops。So one multiply。Is a floating point operation。

 One ad is also a floating point operation。So Fop is for number of floating point operations。

 floating point operations。So how many how many flops are there in a Mac。A Mac has a multiply。

 a multiplier of fl。 A Mac also has a。An ad， an ad is also a flaw。 So one multiply。

And accumulate operation is equal to two floating point operations if the operas are floating point numbers。

For example， AlexNet has 724 medium max， the total number of floating point operations will be 724 times2 that's 1。

4 giga flops。And what is flops， so that's for 1 floating point operations per second。

 the number of flops divided by how many second， so there's a performance metric。Showing how many。

 how fast are you processing these floating point numbers。So what is it op？

We don't always represent the numbers in floating point。

 sometimes we represent them in integer right so both floating point operation and integer operation。

 all kinds of inte operation， even beat mask or even external operation， we can call it the op。

To generalize the number of operations is used to measure the amount of computation。For example。

 if AlexN has 724 million max， if each number is represented by say binary or ternary or floating point or integer。

 you have， whatever you have， any operation can be counted as an op。

So 724 million max will be equal to 1。4 gigawops。And similarly， operations per second。

 OPS equal to total out number of operations demanded by the number of seconds to complete this operation。

 which is a performance speed matrix。Hey， before jumping into the lab zero tutorial。

 let's give a short summary of today's lecture， reviewed the basics of neural networkss。

 output activation， synapses， weight， popular layers into including F layer， convolution layer。

 depthwise convolution， protein normalization。We also introduced efficiency metrics， parameters。

 model size， activations， Macs， floop， flops， up and offs。



![](img/74c33c5587ac05d2ad1d20699864ba38_127.png)