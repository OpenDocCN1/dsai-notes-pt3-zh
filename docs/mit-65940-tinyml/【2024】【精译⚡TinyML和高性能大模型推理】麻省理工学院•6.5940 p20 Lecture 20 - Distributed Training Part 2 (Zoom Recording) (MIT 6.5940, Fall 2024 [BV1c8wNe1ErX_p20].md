# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p20 Lecture 20 - Distributed Training Part 2 (Zoom Recording) (MIT 6.5940, Fall 2024 [BV1c8wNe1ErX_p20]

All right， good afternoon everyone， and let's get started with lecture 20 about the second lecture of distributed training。

So in the last lecture， we talk about several parallellyzization techniques。

 so today we' are going to continue to discuss how to use combine these techniques using mixed parallel。

 hybrid parallelism， 2D and 3D parallelism。

![](img/9b9df0b85cedf4488d543957e4d9de11_1.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_2.png)

And also how to auto paralyze the training and also understand the bandwidth and communication latency bottleneck of distributed training。



![](img/9b9df0b85cedf4488d543957e4d9de11_4.png)

And to overcome the bandwidth bottleneck， we're going to talk about gradient compression。

 how do you compress the gradients to overcome the bandwidth bottleneck？



![](img/9b9df0b85cedf4488d543957e4d9de11_6.png)

Including the gradient pruning using scarrsity and like deep gradient compression where we can compress the gradient by100 times without losing accuracy。



![](img/9b9df0b85cedf4488d543957e4d9de11_8.png)

And also how to perform gradient quantization， one bit， SGD and turnernary gradient。And finally。

 to overcome the latency bottleneck， we are going to talk about delayed gradienting update to overcome the latency bottleneck。

So let's first start with hybrid and mixed parallelyism and also how to auto paralyze。

As a review for the last lecture， we talk about four strategies for parallellyization for distributed training。

The first one is data parallelism okay， so separate pieces of data。

 the data is splitted across multiple node， we have n copies of model。

 each GPU is maintaining its own copy。That has pretty good utilization memory cost。

But it's high memory costs and low communication。There's some optimizations on top of the data parallelm instead of each GPU has the entire weight。

 entire gradient， entire optimizer state， we talk about 0123 FSDP techniques to shard the optimizer state to shard the gradient and also shard the weight。

So you don't have to store the entire copy of the weight within one GPU。

Second technique is the pipeline parallelism， so this is one kind of model parallelism because you' are splitting the layers of the model okay with a single copy of the model that has low utilization because if different pipeline stage。

 the latency is different， the slower one， the fast one has to wait for the slower。Low memory calls。

 medium communication， you only need to communicate are between the pipeline stages。

So the next one is tensor paradigmism， so it's another model paradigmm approach。

 but you are splitting the model within the tensor。

I have a single copy of a model and has high utilization， low memory cost， but high communication。

 like in transformers， how many communication， which states do we need communication？

So for the attention， you need one communication in the beginning and end， for the FFN。

 the two FFN layer， you need one communication in the beginning and end， so high communication cost。

Lastly， we talk about sequence parallel when we are handling long contacts， long documents。

 long videos， when theres a lot of tokens， we want to split the token across multiple GPUs so we can split the data by the tokens。

 the first GPU deal with the first chapter， the second GPU deal with the second chapter。

But there is actual communication during the attention layer since different parts of the document still need to attend to each other。

Therefore we talk about two techniques， one is the Oysses technique you want to do or reduce。

For each GPU to get the attention from each document to a different part of the document to each other。

 we also talk about the ring attention where we can perform this ring or reduce to communicate between different GPUs okay。

So that's the four parallellyization methods。The next question we want to answer is， can we combine？

The merits of different parallelization methods and perform 2D or 3D。

 a combination of different techniques。

![](img/9b9df0b85cedf4488d543957e4d9de11_10.png)

So let's talk about 2D parallel。This is one possible example can see at the outer loop。

We are using data parallelm。 So this is one group。 this is one group， so rank one and rank 0。

 the outer loop， we are using data parallelism， feeding different parts of the data to rank one and rank 0。



![](img/9b9df0b85cedf4488d543957e4d9de11_12.png)

I mean in the inner loop， we are using pipeline parallelism， so。



![](img/9b9df0b85cedf4488d543957e4d9de11_14.png)

This is forward one forward zero backward zero， forward one， backward one。

 so we're alternating between two GPUs to do pipeline parallelism okay so this is four GPUs two by two with two hierarchies okay one is doing doing the data parallelism in the outer side。

 the other two is doing pipeline parallelism in the inner side。



![](img/9b9df0b85cedf4488d543957e4d9de11_16.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_17.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_18.png)

Of course we can do other arrangements， for example here we are performing pipeline parallel in the outer loop。



![](img/9b9df0b85cedf4488d543957e4d9de11_20.png)

So this is layer one， this is layer two and we are doing the partition such that these two layers are performing pipeline parallelism in the inner loop。

 we are doing tensor parallelismm， So this is the first half of the tensor。

 This is the second half of the tensor and the top and on the bottom respectively。

 So one matrix is divided into two sub matrixrices Okay so this is tensor parallelm in the inner loop。



![](img/9b9df0b85cedf4488d543957e4d9de11_22.png)

And pipeline paralleling in the aler loop。Let's see another hybrid parallelism。

By combining different sequence parallelizations okay。

 so this is the conventional approach just to use the out ring attention approach Okay。

 so everywhere is using ring attention See here assuming every GPU within this dashed rectangle is within a node。

 so this is one node， this is the second node we have two nodes。

Between the node the communication bandwidth is about 50 gigabytes per second， but within the node。

 the bandwidth could be much higher， could be as high as 900 gigabytes per second。

U this  oneD sequence parallelism using ring attention will underutil because we have to stick to the slowest。

 which is the inter inter node。Communication bandwidth。

 and we are not well exploiting this high bandwidth for en link within the node。

So how to better exploit the high bandwidth provided by Me D。



![](img/9b9df0b85cedf4488d543957e4d9de11_24.png)

We can perform such 2D attention， so within the node we can perform all to all communication using the Uis approach。

And between the node， we can use this ring approach， ring attention， which has lower bandwidth。

And so we are using real attention between those。

![](img/9b9df0b85cedf4488d543957e4d9de11_26.png)

And out repetition within a node， and so this is the out repetition we talked about in the last lecture。

So in this way， we can fully exploit the high bandwidth within the node and lower bandwidth between the nodes。

So this is 2D sequence parallel。We can also we can also have 3D parallelym so combining this pipeline parallelism with tensor parallelm with data parallelm。

 so this is 3D parallel okay so the same color of the GPUs。



![](img/9b9df0b85cedf4488d543957e4d9de11_28.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_29.png)

Are on the same server。We can see within the server。

 we are doing model parallelism since model parallelism is。



![](img/9b9df0b85cedf4488d543957e4d9de11_31.png)

CompIts also called Ter parism， it most communication having， so we put them in the same server。

And then we are doing zero data terrorism in this dimension。

 and we are doing pipeline terrorism by splitting the layer in the vertical dimension。

 so that's the 3D terrorism。

![](img/9b9df0b85cedf4488d543957e4d9de11_33.png)

So that's a pretty large design space， so next question is how do we auto paralyze？

So when the model is too large to fit the GPU， we can either split the model using pipeline polarism to split different layers。



![](img/9b9df0b85cedf4488d543957e4d9de11_35.png)

But if even if a layer is too large， we can split the layer by using tensor parallelism okay so this is parallelism。

 GPU1， GPU2， layer1， layer2， this is tensor parallelism。

 even within the GP within a single GPU within a single layer。

 we can divide the tensor by full in this case。

![](img/9b9df0b85cedf4488d543957e4d9de11_37.png)

But how do we find the best paralleld strategies for each layer there's already a lot of choices。

 you you have so many layers with the best choice。So here I introduce AlPA which is unified compiler for distributed training。

 so given a computational graph four layers in this case。

 this is a pretty large search space between between the layers and also within the layers。

 we can either partition them by two plus two or one plus three， three plus one。

 even within each group who can either partition the ten vertically or horizontally。



![](img/9b9df0b85cedf4488d543957e4d9de11_39.png)

So AlPA proposes hierarchical search space first is the interoper parallelism okay。

 so layer one is a group layer VcT is another group。Or layer AB is a group。 C And D is another group。

Second hierarchy is the intra operator parallel， okay。

 so we can partition B either vertical horizontally， vertically。

 horizontally or vertically horizontally horizontally。

 and so breaking them into these two hierarchies。

![](img/9b9df0b85cedf4488d543957e4d9de11_41.png)

And then we will search for the inter operator parallel so given a computational graph。

 stage one can either include these two layers or this one layer， stage two。

 either a single pulling layer or this con of every tool might Ma。



![](img/9b9df0b85cedf4488d543957e4d9de11_43.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_44.png)

Okay， so different approaches。I can use dynamic programming to divide the stages。

 either at least two plus one plus two plus one or one plus of three plus one plus two。



![](img/9b9df0b85cedf4488d543957e4d9de11_46.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_47.png)

And next， AlPA can search for the intra operator parallelism。So given this A times B。

 we'll get the matrix modification to get a C。

![](img/9b9df0b85cedf4488d543957e4d9de11_49.png)

Maybe we can either replicate them。Replate the B and divide split the A across the two GPUs or we can replicate A and split B across the GPUs or we can split both A and B to get a partial partial sum and finally do R reduce to some of the map so this is different design choices for the intratroOP app parallelism。



![](img/9b9df0b85cedf4488d543957e4d9de11_51.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_52.png)

And then we can calculate the cost function， which is compute cost plus communication cost。



![](img/9b9df0b85cedf4488d543957e4d9de11_54.png)

嗯。Plus the reing cost between the operators。

![](img/9b9df0b85cedf4488d543957e4d9de11_56.png)

So given a computational graph， given a device cluster。

 it will first do the inter operator pass and then intra operator pass to do the cost I estimation。



![](img/9b9df0b85cedf4488d543957e4d9de11_58.png)

And thenll give you the best orchestration after this automatic search。



![](img/9b9df0b85cedf4488d543957e4d9de11_60.png)

And actually， that can actually match almost perfectly with the best manual design system across 148 to 64 GPs。

没问。This is comparing the best manual system。Vus alpha Al can achieve much。



![](img/9b9df0b85cedf4488d543957e4d9de11_62.png)

Higher throughput compared with the best manual system。All right， so that is a hybrid。

 mixed hero and out of paralyise。And now let's try to understand the bandwidth and latency bottleneck of distributed training。

So as the fundamental computation is cheap， data movement is expensive。

 so communication is very essential， okay， communication is the foundation for distributed training。



![](img/9b9df0b85cedf4488d543957e4d9de11_64.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_65.png)

There are several issues when the model gets lighter。Okay， so first we require synchronization。

 so synchronized SGD is still much more widely used the industry these days compared with asynchronous SGD。

But synchronization will lead to high communication frequency。

 we always need to synchronize after each iteration。



![](img/9b9df0b85cedf4488d543957e4d9de11_67.png)

And the models are getting larger these days， which means need we need to transfer a larger gradient because the dimension of the gradient is equal to。



![](img/9b9df0b85cedf4488d543957e4d9de11_69.png)

The dimension of the weight。 if the model the weight is larger。



![](img/9b9df0b85cedf4488d543957e4d9de11_71.png)

The gradient that needs to be transferred is also larger。And also when you have more training those。

 if you want to make your training faster。Like from an hour to a few minutes。

You need to introduce more training nodes， which means more communication between the nodes using like over reduce due to longer lessonss。

 okay so。

![](img/9b9df0b85cedf4488d543957e4d9de11_73.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_74.png)

If you have a more node， the communication time actually will be larger compared with the computation。



![](img/9b9df0b85cedf4488d543957e4d9de11_76.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_77.png)

So on the right hand side is showing this is the ideal speed up。If you have 200 GPUs。

 ideal you want to have 200 times speed up。But different models have different scalability like AlexNe has very poor scalability or inception model has much better scalability and that is because AlexNe you have a lot of weight 240 mebyte。

 160 million parameters so but relatively low compute flows。



![](img/9b9df0b85cedf4488d543957e4d9de11_79.png)

So you do a little computation and you have to do a lot of communication。

 that's why such model is adding much worse scalability。

 200 nodes 200 nodes you 200 GPUs you have only 100 speed up compared with 200。



![](img/9b9df0b85cedf4488d543957e4d9de11_81.png)

And finally， the networking bandwidth， if it becomes the bottleneck。

 it will slow down the distributed training。

![](img/9b9df0b85cedf4488d543957e4d9de11_83.png)

No matter how fast your computation is， how strong your computation in is。

 if the bandwidth of your network is low， you still cannot fully unleash the power of the power for newer generation of GPUs。

So let's see what is the scale， how do we estimate the networkadtency？



![](img/9b9df0b85cedf4488d543957e4d9de11_85.png)

So let's go through different scenarios， so within Iraq。



![](img/9b9df0b85cedf4488d543957e4d9de11_87.png)

Within the rack of server is roughly millisecond or microsecond level。 Okay。

 so as you go through within the data center is millisecond level latency。



![](img/9b9df0b85cedf4488d543957e4d9de11_89.png)

As you go to wireless communication， that's roughly 100 millisecond network conncy。



![](img/9b9df0b85cedf4488d543957e4d9de11_91.png)

But if you want to send a message across the world， it's 100 millisecond or second level latency。

So the smaller the latency， the faster the training speed， well if the latency is too long。

 the training speed will be much lower。So let's talk about techniques to overcome this network can bandwidth bottleneck by introducing two chapters。

 one is the gradient pruning， the a gradient quantization。



![](img/9b9df0b85cedf4488d543957e4d9de11_93.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_94.png)

Okay， so let's first start with how do we reduce the transfer data science？

Let's recall this workflow of parameter server based distributed training。

 so we have a parameter server that hold this neural network work model。

 the first step each worker will pull the parameters， pull the parameters get a local rep time。



![](img/9b9df0b85cedf4488d543957e4d9de11_96.png)

Of you in that our model。It's going to get a split of the training data， a data parallel。

 so it's going to calculate the local gradient given the training data and the model。

After it completes， it will push the gradients to the parameter server。

And the parameter server will synchronize across multiple workers and finally update the server。



![](img/9b9df0b85cedf4488d543957e4d9de11_98.png)

So this step， pushing and pull， pulling the parameters and pushing the gradient。



![](img/9b9df0b85cedf4488d543957e4d9de11_100.png)

Okay， actually this will be。The bottleneck of the network combined with。

Imagine you have 100 node that each has to push to gradient to the parameter server。

Or even if you do ring or reduce， you still have to communicate a lot of gradient。

 which the is of the same size as the weight。

![](img/9b9df0b85cedf4488d543957e4d9de11_102.png)

So natural idea is， can we improve the gradient， So this is the original gradient tensor。



![](img/9b9df0b85cedf4488d543957e4d9de11_104.png)

And we pruned them by setting a lot of them to be zero。Such that we don't need to send。

Those pruned zero credits hey， we only need to send this。Dark green gradients。

And make this light green area pop blocks。

![](img/9b9df0b85cedf4488d543957e4d9de11_106.png)

啊，委东这中三个。Another approach is rather than sending this 32 bit gradient。



![](img/9b9df0b85cedf4488d543957e4d9de11_108.png)

And we quantize the gradient for8 bit。And signed a much lower precision， Bri it。

So this is eight times saving compared with selling everything else， everything in 32 bit。

 so that's roughly put directions we can。

![](img/9b9df0b85cedf4488d543957e4d9de11_110.png)

We can do all to reduce the transfer data size。Let's visit them one by one and let's first visit the pruning and sparse communication approach。



![](img/9b9df0b85cedf4488d543957e4d9de11_112.png)

So let's discuss gradient pruning with local gradient accumulation。



![](img/9b9df0b85cedf4488d543957e4d9de11_114.png)

哎。😊，So the idea is to only send the top K gradients ranked by the magnitude。



![](img/9b9df0b85cedf4488d543957e4d9de11_116.png)

So this is a grid insor and we find the top K by sorting them。



![](img/9b9df0b85cedf4488d543957e4d9de11_118.png)

And these green blocks are the top K gradient。Of course， there will be aarrow， right？

And we can accumulate the error， for example， for the pruned area。

 like everything here pruned at zero， they must have a residual， okay， they are small。

 but they do have a residual。

![](img/9b9df0b85cedf4488d543957e4d9de11_120.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_121.png)

Corresponding to the zero gradient。Rather than sending away those grid schedule to the prime server。

 we want to accumulate。Those gradient locally， okay。

 hopefully next time the gradient will get bigger as the threshold and we'll send them out。

And before they accumulate。To pass the threshold， we just keep the residual locally without sending the mark。



![](img/9b9df0b85cedf4488d543957e4d9de11_123.png)

So that can indeed improve the training speed， so this is a very early paper like seven years ago showing our our mini data set。



![](img/9b9df0b85cedf4488d543957e4d9de11_125.png)

We increase training images per second。But it fails on slightly larger network like Resnet。

 There' is 1% loss of accuracy， which。Its not tolerable。

So how do we solve the issue of loss of accuracy when we are pruning the gradient？And figure out。

Where is the performance degradation coming from， why the performance accuracy dropped？Actually。

 that is due to the momentum。

![](img/9b9df0b85cedf4488d543957e4d9de11_127.png)

So let's review what is the momentum。 So momentum is a very important technique used in the gradient descent。



![](img/9b9df0b85cedf4488d543957e4d9de11_129.png)

Nearly almost all optimizes has momentum these days， it's very useful to overcome the local minima。

And oxcillation。

![](img/9b9df0b85cedf4488d543957e4d9de11_131.png)

It's very widely used and it's not ViGG resident transformer bird。

 even these days for large language models， momentum is very widely used。



![](img/9b9df0b85cedf4488d543957e4d9de11_133.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_134.png)

Here we consider only the first other momentum， okay， so。

This is the gradient in blue and we update the velocity the U and M is the momentum。

 It's a discounting factor。 We take a percentage of the previous velocity and we add the current gradient。

 we get the current velocity and we use velocity rather than the gradient。To update the weight。 Okay。

 so this is a discounted velocity。 This is the current。Brilliant， this is the new velocity。

 which is a combination of the previous velocity and the current gradient。

 and we use that to update the weight。

![](img/9b9df0b85cedf4488d543957e4d9de11_136.png)

So during the SGD， we first obtained the gradient the gradient is in。Blue。

 and then we calculate the velocity using the momentum Okay so this is the previous low velocity U T minus-1。

 this is the UT by combining these two together。

![](img/9b9df0b85cedf4488d543957e4d9de11_138.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_139.png)

To calculate the velocity UT and we update the model weights by UT， not by GT， okay。

 not using gradient， but using momentum but using velocity by using this UT to update the model weights。



![](img/9b9df0b85cedf4488d543957e4d9de11_141.png)

And finally， we repeat and calculate the velocity for the next iteration Okay so this is the new gradient。

嗯。And this is the discounted factor of the previous。Of the previous。U is the velocity okay。

 so this is UT this long， this is a shorter version of that because it is a scaled version of that okay so this is UT plus one。



![](img/9b9df0b85cedf4488d543957e4d9de11_143.png)

And we use U key plus one to update the weight， we are not using G key plus one to update the weight。

 so that's the key point here。And let's see during sparse communication what is accumulated。

 we are accumulating the gradient okay so the residual gradient is accumulated in the local buffers before they get large。

 they don't get sent out， they only get sent out after they get larger。

So in the previous algorithm we directly use an accumulated gradient for momentum calculation。

 so where aulating gradient is that correct like here if the gradient is not sent out。

 we accumulate them locally。

![](img/9b9df0b85cedf4488d543957e4d9de11_145.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_146.png)

Hopefully during the next iteration， it will get larger and get sent out。

So let's see how our looks on this graph。

![](img/9b9df0b85cedf4488d543957e4d9de11_148.png)

So this is the vanilla momentum SGD， we get UT， we get UT plus one。

 we get two updates and the way they started from here， get here， finally it landed here。



![](img/9b9df0b85cedf4488d543957e4d9de11_150.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_151.png)

And momentum IGT with local accumulation， we are accumulating the gradient in the local buffer。



![](img/9b9df0b85cedf4488d543957e4d9de11_153.png)

If the gradient is small， we accumulate them after they get large， we send them out。

 so this is the accumulated gradientig。What if we use that to update the model？



![](img/9b9df0b85cedf4488d543957e4d9de11_155.png)

It will become here。Rather than。Here， right， so you see the difference。

Here we are aumulating ingredients and I get a wrong update。



![](img/9b9df0b85cedf4488d543957e4d9de11_157.png)

Using momentum ID with its naive local accumulation。So it's wrong to add the accumulated gradient。

resulted in the optimization shifted doesn't match， okay？So what should we do？

We should accumulate the velocity， not the gradient。



![](img/9b9df0b85cedf4488d543957e4d9de11_159.png)

So whether it's velocity， So this is a UT， this is UT plus one。

 we should accumulate velocity by combining UT and U T plus one。

 We get the red accumulated the velocity。

![](img/9b9df0b85cedf4488d543957e4d9de11_161.png)

And we use that to update the model weight。Okay， so we should accumulate velocity over many iterations rather than accumulating the gradient。

And in this way， it can land into the same position。In these two scenarios。



![](img/9b9df0b85cedf4488d543957e4d9de11_163.png)

So here's a comparison。Among the vanilla momentum and SGD without momentum corrections with momentum correction。



![](img/9b9df0b85cedf4488d543957e4d9de11_165.png)

Okay， so the next technique is warm up， warm up the training。

So in the early of early stage of the training。The network weight is changing very rapidly。

And local gradient accumulation still gradient will make the problem worse。

 so we don't want to have a very high protein ratio in the first couple of iterations。



![](img/9b9df0b85cedf4488d543957e4d9de11_167.png)

So when the optimization just gets started， the gradient may be pretty large。



![](img/9b9df0b85cedf4488d543957e4d9de11_169.png)

So we can warm up the learning rate initially start with a very small learning rate and gradually here is linearly increasing to the stable learning rate since you can see on the initial training stage。



![](img/9b9df0b85cedf4488d543957e4d9de11_171.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_172.png)

The gradient is very sharp， so we want to be conservative to prevent overshooting by using a smaller learning rate。

Yeah。We can also warm up the sparsity。

![](img/9b9df0b85cedf4488d543957e4d9de11_174.png)

To avoid a sudden change in the sparsity， so here we are gradually increasing thersity gradually increasing the sparsity。



![](img/9b9df0b85cedf4488d543957e4d9de11_176.png)

Here it is exponentially increasing sparsity in the first couple of ipocs。



![](img/9b9df0b85cedf4488d543957e4d9de11_178.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_179.png)

Here three， four ipoOCs to help the optimizer adapt to a larger sparsity in ipoOC5 and become stable。

 sparsity becomes stable。So let's see how this technique improve the accuracy by using by starting with the local gradientding accumulation。

 the baseline model has accuracy of 92%， 92。9%， if you just do naive gridding pruning without doing any grading accumulation。



![](img/9b9df0b85cedf4488d543957e4d9de11_181.png)

It doesn't emerge so you cannot do that。If we add local gradientding accumulation。

 model if the gradienting small， we accumulate them until they get large and send them out。

It can recover a lot， but it still is 1。56% lower than the baseline。

What if I add this local gradient accumulation plus this momentum correction。Okay。

 so accumulate the velocity rather than accumulate the gradient。It becomes 92。5256。

 a lot better than the baseline。What if we only added the warm up？It's also get better from 91。

3 to 91。8。What if we add them together， including local gradienting accumulation。

 momentum correction and warm up training， combininging them all。

 it further increased to more than 93%。And now it's getting even better。Compared with the baseline。

 So this is lesion， and this is。Language modeling。 Okay， so the。



![](img/9b9df0b85cedf4488d543957e4d9de11_183.png)

The word error rate is also well recovered by combining all these techniques。

The lower the better on the right hand side， if you just do this local gradient accumulation actually means three point degradation for the whatever rate。



![](img/9b9df0b85cedf4488d543957e4d9de11_185.png)

If we add the momentum correction to accumulate the velocity rather than accumulate the gradient。

And also do local gradienting clipping， which is quite important for IICM。

 which we want to prevent the gradient of antigen and gradienting explosion problem。

 so we want to also do this local gradienting clipping。It can recover a little bit around 1%。

And then we can add momentum correction and local gradienting click。嗯。



![](img/9b9df0b85cedf4488d543957e4d9de11_187.png)

I can further improve a little bit， finally if we combine。

All the techniques it can further improve to 10。37。So let's see the training curve。

What does the training curve look like？

![](img/9b9df0b85cedf4488d543957e4d9de11_189.png)

So this is the accuracy on the left， the higher the better， this is the loss on the right。

 below the better。And if we can see here， the baseline is in blue and there are several approaches。

 one is to ingredient in dropping。Within dropping in red， actually it's much worse。

It's on the bottom so the accuracy is not good and the loss is the highest。

 so the loss is not good if we just perform query in dropping。

The yellow one is gradient specificificationation with momentum compression。

 only specificificationation with correction without warm up。It is in yellow right here， it's better。

 but it's still worse compared with the baseline is yellow here。

And deep gring compression is in purple， purple is closely matched with a baseline。



![](img/9b9df0b85cedf4488d543957e4d9de11_191.png)

Here is in purple， it's even lower than the baseline。So this is on Sa10。

 surprisingly we can make it a 99。9% sparse for the gradient。

My imageageNe is about 200 to 500 times for income ratio is also quite as significant。



![](img/9b9df0b85cedf4488d543957e4d9de11_193.png)

DGC stands for deep griding compression， this is the top one top five accuracy。

 gradient size is reduced by almost 600 times。Why iss not a thousand times because it's 99。

 almost 99。9% sprsity。

![](img/9b9df0b85cedf4488d543957e4d9de11_195.png)

Why the gradient size is reduced by by 500 times because there's indexing overhead， of course。

 to represent a sparrse array in the indexing overhead。



![](img/9b9df0b85cedf4488d543957e4d9de11_197.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_198.png)

And also the biases are not probed。Remember， in the light to residual training。

 we want to keep the bias bias and it's very important。



![](img/9b9df0b85cedf4488d543957e4d9de11_200.png)

So this is the VGG twin imagenet， top1 and top five accuracy。

 the baseline versus the deep gradient compression。



![](img/9b9df0b85cedf4488d543957e4d9de11_202.png)

Compresssure ratio is more than 200 types。So not only mission， let's also look。

 take a look at language modeling。

![](img/9b9df0b85cedf4488d543957e4d9de11_204.png)

So this is comparing the baseline between compression for the loss， and this is for the perplexity。

The perplexity is very well maintained， but the size of the gradient reduced from 190 megabytes to only less than half a megabyte。



![](img/9b9df0b85cedf4488d543957e4d9de11_206.png)

And this is for speech recognition。

![](img/9b9df0b85cedf4488d543957e4d9de11_208.png)

The word error rate is also well maintained versus the loss。Previously。

 the gradienting is more 480 MBby。 Now is's less than 1 MBby。



![](img/9b9df0b85cedf4488d543957e4d9de11_210.png)

Okay， so what is the problem for people with compression？If we have。Using the R reduce approach。

Actuallyual， after a few iterations。It will get denser， right， so you suppose we have four node，0。

 one，2， three。

![](img/9b9df0b85cedf4488d543957e4d9de11_212.png)

And the scarrsity of each node of the gradients all different。

For node zero is bottom three gradients are one for node three。The other two values are on1 zero。

If we want to perform this all reduce our pressure or reducing these in this。So adding three to zero。

 they will get denser。

![](img/9b9df0b85cedf4488d543957e4d9de11_214.png)

And if you do another iteration it will continue get denser。

 so we'll get denser and denser if you repeat this all reduce process， send three to1，0，0 to1，1 to2。

 two to three。 then you can imagine the final accumulated result will get denser。



![](img/9b9df0b85cedf4488d543957e4d9de11_216.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_217.png)

So what's the solution here？So we can enforce the same sprsity pattern， so when we we do all reduce。

 it will not get denser。

![](img/9b9df0b85cedf4488d543957e4d9de11_219.png)

And you can apply the cause brain the sparsity， okay， co brain sparsity。

 such that you can enforce certain pattern of sparsity。

And also you can continue to prorune in the middle of this ring or reduce， for example。

 prune in the middle of the ring or reduce， prun away some of the9 zeros to be zero again。



![](img/9b9df0b85cedf4488d543957e4d9de11_221.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_222.png)

Okay。There's another approach rather than using sparsity。

 remember during the inference efficiency technique we talk about a lot of techniques。

 one is low rank right so we can not only use sparsity by pruning a lot of small gradients we can also factor the gradients using low rank so this is using rank of one。



![](img/9b9df0b85cedf4488d543957e4d9de11_224.png)

Facting is four by four matrix into a one by four and4 by one matrix Okay。

 so the advantage is that the rank matrix dimension4 by one one by four。

 that's the same across all the servers。 So when you' are doing a ring or reduce。

You are not going to get any difference， not like the sparsity。

 you can get denser here and will not get denser or spar。

 the dimension is the same as you perform or reduce。



![](img/9b9df0b85cedf4488d543957e4d9de11_226.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_227.png)

And let's see how that performs the speed is actually doing quite well。

 this is ranked2 the speed up over the standard ICG is much better。



![](img/9b9df0b85cedf4488d543957e4d9de11_229.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_230.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_231.png)

Almost a linear speed up when the number of workers increase when using this power ICD approach。



![](img/9b9df0b85cedf4488d543957e4d9de11_233.png)

so this is the comparison of different gradient pruning methods， okay we can perform a specification。

 start with local gradient accumulation， okay if the gradient is small。

 then we can accumulate them until it's large after it exceed a certain threshold we send them out。



![](img/9b9df0b85cedf4488d543957e4d9de11_235.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_236.png)

Unfortunately， he can have very low sparsity ratio， otherwise the accuracy will drop。



![](img/9b9df0b85cedf4488d543957e4d9de11_238.png)

And then we introduced the teeth Gring compression technique， which we published in 2017。



![](img/9b9df0b85cedf4488d543957e4d9de11_240.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_241.png)

By using momentum correction， we should be discovered， we should not accumulate the gradient。

 but we should accumulate。The velocity， not the grid， so we call it the momentum correction。

Which can solve the issue of low pricing ratio issue。



![](img/9b9df0b85cedf4488d543957e4d9de11_243.png)

And gradienting clipping okay， so we want to flip the gradient to prevent overflow and also perform warm up 20。

 start with a smaller learning rate， start with a smaller sprsity ratio to warm up that can achieve very high sprsity ratio we can prune away 99。

9%。

![](img/9b9df0b85cedf4488d543957e4d9de11_245.png)

So for weight pruning， even 90% pruning is a very highest pruning ratio。

 but gradient is much easier to compare with the weight。

So that's the lesson we learned while maintaining the accuracy。



![](img/9b9df0b85cedf4488d543957e4d9de11_247.png)

However， this specificification technique have a limitation where it will get denser if you do this rain or reduce for a few iterations。



![](img/9b9df0b85cedf4488d543957e4d9de11_249.png)

Therefore， we'll talk about this power SGD using the low rank approach instead of flying grain p。

To make sure during the communication will not get denser。



![](img/9b9df0b85cedf4488d543957e4d9de11_251.png)

Hey， so that's the first half of this lecture， let's take a five minute break before we jump into quantization approach。

All right， welcome back let's continue the discussion about gradient quantization。

 just now we talk about the first technique of gradient compression which is pruning to remove a lot of gradient and now let's see can we use one bit or turnernary two bits or only three numbers to represent the gradient。

😊。

![](img/9b9df0b85cedf4488d543957e4d9de11_253.png)

So this is one bit SGD okay so starting with a 32 bit full precision gradient tensor。

 we want to quantize them to only one bit plus a delta。

 which is the residual which we can accumulate locally。



![](img/9b9df0b85cedf4488d543957e4d9de11_255.png)

To accumulate the quantization error， so in the next round we can add this residual to the next iteration and hopefully we can alleviate the error coming from this aggressive one bit quantization。

And of course we can apply a column wise scalingkating factor。

 so we can have a skating factor for each column rather than just0 and1。

 we can apply a scalingk factor， FP 32 skating factor for each column。



![](img/9b9df0b85cedf4488d543957e4d9de11_257.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_258.png)

So the whole solution will be like this， we have the original gradient and we set a threshold to be zero。

 if it is greater than zero， we set it to one， otherwise it's zero okay and across each column we calculate we find a scaling factor by maintaining the sum to be the same the absolute value sum to be the same。



![](img/9b9df0b85cedf4488d543957e4d9de11_260.png)

Such that we get the quant as the value okay and we can calculate the gradient residual okay what is the grid quantization error？

Different from inference where this error is indeed error it will propagate。For training。

 we can accumulate the error， okay add it back。Since they're both at P 32。

 we can add it back to the original gradient to get the updated gradient Okay， so the next iteration。

 we can continue this flow。

![](img/9b9df0b85cedf4488d543957e4d9de11_262.png)

Another approach is to set a threshold rather than set the zero threshold and we can set a threshold tau is also a reconstruction value which is chosen in the bus。

 so if it is greater than tau， the value will be co。



![](img/9b9df0b85cedf4488d543957e4d9de11_264.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_265.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_266.png)

In the middle between tau and minus all， it'll be0 if it is smaller than。



![](img/9b9df0b85cedf4488d543957e4d9de11_268.png)

Smaller than minus ta， it will be quantized to minus ta。

So the drawback here is empirically choose the the value top。 similarly。

 it also has the mechanism of。

![](img/9b9df0b85cedf4488d543957e4d9de11_270.png)

Breing quantization error accumulation。 So this is a threshold quantization。The next work is called。



![](img/9b9df0b85cedf4488d543957e4d9de11_272.png)

Turernary red， Turnernary gradient， okay， which is saying can we quantize。



![](img/9b9df0b85cedf4488d543957e4d9de11_274.png)

The gradient divided by the max， the max of the gradient to be  zero，1 and minus1。

But it's probabilistic quantization， so with probability。

 the magnitude divided by the max value okay？

![](img/9b9df0b85cedf4488d543957e4d9de11_276.png)

So usually adding such stochastic。Quantization will improve accuracy and that's indeed the case and so the expectation of the quantized gradient will be the same as the original one。



![](img/9b9df0b85cedf4488d543957e4d9de11_278.png)

So there is no quantization error accumulation since the expectation is matching in this way that's guaranteed so we don't need to accumulate the error so we can do iteration by iteration。

 it's independent instead on the fly okay。

![](img/9b9df0b85cedf4488d543957e4d9de11_280.png)

So this is the turnaround grid。All right， so that is the two solution for gradient compression to overcome the communication bandwidth bottleneck。



![](img/9b9df0b85cedf4488d543957e4d9de11_282.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_283.png)

And the other bottleneck beyond the communication bandwidth is actually the communication latency。

 okay， communication la。

![](img/9b9df0b85cedf4488d543957e4d9de11_285.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_286.png)

And we're going to talk about techniques to solve the latency bottleneck by using delayed gradient update。

 delayed update。

![](img/9b9df0b85cedf4488d543957e4d9de11_288.png)

And first， let's review the concepts between quantization between bandwidth and latency okay so bandwidth is much easier to improve compared with latency。

 for example， we can improve the bandwidth by comprising the gradient。

 make it a smaller and quantize that， make it a fewer number precision。



![](img/9b9df0b85cedf4488d543957e4d9de11_290.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_291.png)

for example， using the techniques we just learned using improvingruning， deep breathing compression。

 term grad， gradientding quantization approach。

![](img/9b9df0b85cedf4488d543957e4d9de11_293.png)

We can also upgrade the hardware anyway so Enet has 100 MBgaits to 1 gigabit per second fiber has about 1 gigabit to 25 gigabit per second。

 we can also upgrade it to the infinity band which can easily get 400 gigabit per second these days。



![](img/9b9df0b85cedf4488d543957e4d9de11_295.png)

So the bandwidth can be improved by upgrading your hardware。However， leency improvement is very hard。

 is restricted by physics， you have physical limit。



![](img/9b9df0b85cedf4488d543957e4d9de11_297.png)

By the speed of light， for example， traveling from Boston to Shanghai at the speed of light。

So it takes 162 meisecond okay， so that's the physical limit。

 it is also possible of the signal congestion the urban offices and the homes creates a lot of signal contenttion。

 so latency optimization is very hard。

![](img/9b9df0b85cedf4488d543957e4d9de11_299.png)

What's the bottleneck， what is the why do we want to load agency during distributed training？



![](img/9b9df0b85cedf4488d543957e4d9de11_301.png)

So for example， these are we have two workers。The green part is the computation。

The yellow part is the communication， and we have to synchronize after each iteration。😊。

So we have to wait for the communication to finish before we can start the second iteration of computation。



![](img/9b9df0b85cedf4488d543957e4d9de11_303.png)

はい。😊。

![](img/9b9df0b85cedf4488d543957e4d9de11_305.png)

If the latency increased。The yellow part， which is communication time， will increase。And worker one。

 worker two， they cannot start the next round of computation before the communication finishes since they need to synchronize so that will increase the total latency。



![](img/9b9df0b85cedf4488d543957e4d9de11_307.png)

So the workers has to wait for the transmission to finish before the next step since the local update and communication are happening sequentially。

So this is too bad。 If we have a longer network latency， the total training will get much slower。



![](img/9b9df0b85cedf4488d543957e4d9de11_309.png)

And the question here is can we find an alternative solution so to allow the stale gradients。

 okay allow the gradient to be stale， we don't have to be blocked but we want to continue to make progress so we can overlap communication with computation。



![](img/9b9df0b85cedf4488d543957e4d9de11_311.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_312.png)

And so this is similar to using the late days to submit your homework okay to transmit your gradient to use the late days right when we are submitting the homework like homework two。

 we can make progress by continue studying about。

![](img/9b9df0b85cedf4488d543957e4d9de11_314.png)

Lecture three before we finish homework two right and we can submit the homework two while still making progress by learning lecture three and we can submit。



![](img/9b9df0b85cedf4488d543957e4d9de11_316.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_317.png)

We no longer has to be blocked by using the late days。

So let's see what does that look like by using such delayed gradientant averaging thing？



![](img/9b9df0b85cedf4488d543957e4d9de11_319.png)

So， let's see。These are four its using distributed ID。

 there's a long delay to send and receive those parameters of the gradient okay so we can now start step two computation before we finish thiscom。



![](img/9b9df0b85cedf4488d543957e4d9de11_321.png)

They are blocked。By this long synchronization。

![](img/9b9df0b85cedf4488d543957e4d9de11_323.png)

But if you allow such delay， we can immediately start。The second iteration。

After the first iteration completes， even though we haven't finished the sign and receive about the gradient。

We can continue make progress， a computing step two， step three， step four， and suddenly we received。

De gradientd coming from step one， which is a stale gradient respect to step four okay it was four or three steps before。

 so that's a stale gradient。But fortunately， our study in this paper find it's still possible to converge perfectly by using stale the gradient to a certain extent。

 at least three step is very safe。So this is called delayed gradient averaging， we are summing up。

The gradient coming from a previous step is delayed。

 but it can still converge so step step four receive the gradient from step one is going to make progress and step five is going to make receive the gradient from step two so we are not losing anything we are just using the state of the gradient we are not skipping any gradient。



![](img/9b9df0b85cedf4488d543957e4d9de11_325.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_326.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_327.png)

So all the grading are transmitted， all the homework is submitted even though we are using the late days right so there must be a certain threshold like our like our lecture we have a fixed number of late days beyond that we don't allow and beyond that the model will not converge so that's the same principle。



![](img/9b9df0b85cedf4488d543957e4d9de11_329.png)

Let's see what happens if we increase the communication latency in this way。

So previously we have to synchronize after each iteration， have this barrier， okay。

 the red one is the synchronization barrier。If we allow one iteration of delay。

 we can remove this barrier in the first iteration as long as on a second iteration。

 they can synchronize okay， so this is one day of late day of a homework。

So this is the communication， so the communication。

 if this gets longer as long as it doesn't exceed this barrier。

It will not increase total latency for the training okay as long as the communication finishes before this barrier。

 so the training total training time is not affected， even if the latency increased。



![](img/9b9df0b85cedf4488d543957e4d9de11_331.png)

は。😊，So the key idea is to delay the receiving timing of the if gradient to a later iteration i plus D。



![](img/9b9df0b85cedf4488d543957e4d9de11_333.png)

I plus D。And we are receiving no sta greet few steps away。So let's see how that works。

 So we initialize。A container for each iteration gradient for G。 and for each training iteration。

 we calculate。The gradient using the network weights and the data we calculate。The local gradient G。

 And we send our local gradient out， send it out to other nodes with the iteration as the I D。

And then we record this G in this array saying that。嗯。For this it， the gradient is G。

An average G is received D steps ago， okay we receive from ID equal to iteration minus D so that's delayed by D steps which we suddenly we finally received since the received function take time when we received it is already d steps away。

And then when we are doing the update， the weight equals through weight minus the learning rate times and the G is our freshly calculated local gradient。

 and we want to subtract subtract the gradient from the current node that was these steps away since we have already received the average gradient from all the servers。

T steps away， we want to encompass compensate it that by subtracting the covered nose E minus D steps away is gradients。

 that's why we need this G vector to record the gradient of each step of each iteration。And finally。

 we average received the average gradient from other node is average G is actually delayed by these stepss。

So that's the only change we need to make any subject the gradientd from the current node as these steps away since we are compensated by receiving the average gradient from all the nodes。



![](img/9b9df0b85cedf4488d543957e4d9de11_335.png)

No。Let's continue to deal with the staleness， so we have seen this speaker already。

 let's compare without the correction， if we directly apply this this weight equal to weight minus learning rate times the stale gradient that is averaged across all the node。

 what will happen。

![](img/9b9df0b85cedf4488d543957e4d9de11_337.png)

Actually， the longer the delay， actually the accuracy will drop very quickly from 88% to 84 to84%。嗯。

This is a delay as you get longer delay without any correction that I prefer a job。



![](img/9b9df0b85cedf4488d543957e4d9de11_339.png)

So let's see how do we apply the correction term so we should not we should subtract。



![](img/9b9df0b85cedf4488d543957e4d9de11_341.png)

The gradient coming from the local gradient that is d steps away and add the current fresh gradient from the current node and add the delayed gradient that is averaged across all the node。

 but d steps away okay。Since this already contained part of。The local gradient has these steps away。

 so with that's why we should subtract it。That's why we should subtract it since this term already contained this term。

And after applying such correction term， we can well maintain the accuracy much better than without correction。

 up to like 4%，5% better compared with without using this correction term。



![](img/9b9df0b85cedf4488d543957e4d9de11_343.png)

So the take home is that we can allow such staleness by using the gradient average gradient D iterations away。

 but don't forget to subtract your local gradient otherwise it will duplicate both from the your own gradient since its already added here and also from sum of the stale gradients。



![](img/9b9df0b85cedf4488d543957e4d9de11_345.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_346.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_347.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_348.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_349.png)

Okay。So within these steps， we assume the learning rate stays roughly the same D is not too large。

 it's only like 1020 userer ratios。

![](img/9b9df0b85cedf4488d543957e4d9de11_351.png)

The say and descendsent as inviting these sign res in these investments in。可以交选择。

Big overshoots or undershoots So the learning rate will scale with the batch size and usually when you have more node you have a larger you have a larger batch size。

 so the learning rate definitely need to scale accordingly。



![](img/9b9df0b85cedf4488d543957e4d9de11_353.png)

Okay， so this is comparing the speed up this is measured the speed up and we compare on different data sets。

 the S part data imagenet Shakespeare partition the data either IID or non IID the baseline is using the fat average k equal to five indicates that we just do the local calculation of the gradient for five iterations sum the map and then send it out okay so that can have a longer time of communication but less communication because we are doing five iterations of gradient calculation without any update we just calculate the gradient the effectiveness is we are increasing the batch size by five times so that's fat average increasing the batch size by five times so that's the baseline we can。



![](img/9b9df0b85cedf4488d543957e4d9de11_355.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_356.png)

Do the accumulation of the of the gradient by 10 iterations without sending the map。

 just doing the gradient calculation locally， sum the map and sending out every 10 iterations。

 so that gave you about 1。5 I speed up。

![](img/9b9df0b85cedf4488d543957e4d9de11_358.png)

And accuracy is well maintained。You can also increase that to 20， you get 2x speed up。

The accuracy is also well maintained， but you can also combine that with delay gradient delayed gradient update that can give you three to4 x speedup well the accuracy of both ID and9ID is well maintained across different scenarios so that give you another design knob not only to do fight average but also can do the delay okay。



![](img/9b9df0b85cedf4488d543957e4d9de11_360.png)

To verify such idea on a local server， we put up with。



![](img/9b9df0b85cedf4488d543957e4d9de11_362.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_363.png)

Small rack of raspberry pi okay so here we have eight raspberry pis as a real world benchmark from one node to node four node all the way to eight node across vision benchmarks and language benchmarks。

 so we are comparing the fat average averaging every five step or 10 step。

 just to local aaging without having to transmit which is a baseline， very strong baseline。

 you can get about three to four x speed up with eight node but combining that with deep grade delayed gradient in averaging。



![](img/9b9df0b85cedf4488d543957e4d9de11_365.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_366.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_367.png)

![](img/9b9df0b85cedf4488d543957e4d9de11_368.png)

You can get 7 or 7。5 x speed up with eight node， although this is connected by very slow。

 actually just standard Ethernet， but it can still scale quite well。All right。

 so here is a summary of today's lecture， we first talked about mixed hybrid parallelism and how to auto parallellyzze 2D parallelism。

 3D parallelism， and then we challenged we are faced with two challenge， one is bandwidth challenge。

 the other is the latency challenge to solve the bandwidth challenge。

 we have a gradientding compression technique using pruning such as deep breathing compression or using quantization such as one bit orernary gradient。



![](img/9b9df0b85cedf4488d543957e4d9de11_370.png)

To solve with the second problem of latency bottleneck。

 we talk about this delayed the gradient update to allow late days when submitting your homework when transmitting the gradient and can still converge quite well。



![](img/9b9df0b85cedf4488d543957e4d9de11_372.png)

All right， so lot five is already due， so we will grade it and return you just I will return the grade by next weekend。

Okay and we also have the whole projects proposal due very soon so hope you can work on that if you need any support。

 feel free to talk to us， we highly encourage new to open source， the final projects。

 for the format of the open source， feel free to check out our labs， GiHub， MIT Han Lab。

 search that on GitHub。Pretty much all the projects we did since 2018 since I joined MIT is open source。

 which both help you to maintain good quality and also make them help the community to get better so if you have any questions feel free to talk to us。

All right， that's all for today's lecture， thank you。



![](img/9b9df0b85cedf4488d543957e4d9de11_374.png)