# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p19 Lecture 19 - Distributed Training Part 1 (Zoom Recording) (MIT 6.5940, Fall 2024 [BV1c8wNe1ErX_p19]

All right， good afternoon everyone， let's get started。

 so today we are going to start a new chapter about distributed training。

So in the first two part of the lecture， as first give a quick over review。

 we learned about how to accelerate inference right inference techniques， general purpose techniques。

 domain specific techniques including improvingruning quantization， neuro architecture search。

 distillation， for large language models for diffusion models for video models， etca。

So from today we are going to start a new chapter about training。

 how to make training faster if you in the country a model is too slow to train。

 hopefully we'll teach you some techniques to make your training faster。

So this is an agenda for today， we'll start with background and motivation。

 why we need distributed training and we'll cover several techniques about parallellyzization。

Including data parism， model parism， pipeline paradigmism， sequence parism。

A modeldel parism is also called a tensor par。In particular， for data parallelism， we'll talk about。

Several sharding methods，0， one，2，3 and fully sharded distributed FSDP parallelism FSDP techniques okay fully sharded distributed parallel okay data parallel so let's start with background and motivation。



![](img/3c11e41698f0868314a0cef338e9d65e_1.png)

So these models are usually coming at a very high cost of training， so the higher the accuracy。

 the more max we need。

![](img/3c11e41698f0868314a0cef338e9d65e_3.png)

Hey， the normalms we need。To train this GPT model， GT3 model require 3 million GPU hours。

 which is too slow to train if you have a single GPU， so we need multiple GPUs to make it faster。

So this is showing how long it takes to train a model， from Rein 50 to birth based to an LLG， GT3。

 particularly for GPT3，1 75 billion parameter is a huge amount of GP hours if you have a single GPU that will take 355 years to train the model。

 which is too slow。

![](img/3c11e41698f0868314a0cef338e9d65e_5.png)

![](img/3c11e41698f0868314a0cef338e9d65e_6.png)

And these numbers are measured NV a 100 GPU。So the boss asks you。

 what did you do over the last month？And the answer is twin the model for one ipoC。Pa asked， fine。

 what's their plan for the next month and answer train train the model for one more i talk Okay so that greatly limits the productivity of our designers which machine learning。

Practitioners， right so we want to make the model train faster。

So we want to use multiple GPUs just to buy multiple GPUs to do that， for example。

 if a training task take 10 GPU， a single GPU 10 days， 10 GPU days， if you have 1024 GPUs。

 thatll take only 14 minutes， 14 minutes over just a cup of coffee。



![](img/3c11e41698f0868314a0cef338e9d65e_8.png)

![](img/3c11e41698f0868314a0cef338e9d65e_9.png)

![](img/3c11e41698f0868314a0cef338e9d65e_10.png)

So this kind of technique can greatly speed up our research and development cycle。

So let's see a real use case that our lab did for distributed training a couple of years ago。

 so we exploitd this summit supercomputer， it has many V100 core it's pretty big at that time we trained over 1。

000 GPUs at that time H GPU is V 100 that's already2 or three generations ago V 100 and the A100 and the H100 and now B 100 is coming。

At that time， it has 200 gigabit per second in V band now you can easily get 400 gigabit per second after this this was in 2019 this was in 2019 so only four years there's tremendous。

Development is tremendous improvement from N media for the GPU family。 So this is at that time。

 we train this video model， video understanding module and per shift module over 66 hours of video。

 which is。

![](img/3c11e41698f0868314a0cef338e9d65e_12.png)

![](img/3c11e41698f0868314a0cef338e9d65e_13.png)

Considered a small amount these days， but at that time it was considered a pretty big amount。

So with only one node， six GPUs that take 49 hours， roughly two days。



![](img/3c11e41698f0868314a0cef338e9d65e_15.png)

And with 128 knows that 700 GPUs，28 minutes with 1536 GPUs will shorten that to 14 minutes。

That's 211 times faster， so theoretically it should be 256 times faster。

 so the accuracy is well maintained。

![](img/3c11e41698f0868314a0cef338e9d65e_17.png)

So we've talked about temporal shift module just to shift the channels across different frames to enable temporal modeling。

 which is a good replacement of 3D convolution that is much more computationally efficient。



![](img/3c11e41698f0868314a0cef338e9d65e_19.png)

So this is just showing by utilizing more GPUs by buying more GPU so we can shorten the design cycle day from two days to 14 minutes。



![](img/3c11e41698f0868314a0cef338e9d65e_21.png)

Okay， so let's dive deeper into how do we achieve that。

 given distributed training can be so helpful to shorten the design cycle。

 let's see how do we paralyze and how do we exploit so many GPUs。

 say you have budget to buy like 100 GPUs， how to program them， how to exploit them。

So let's talk about parallellyization techniques in the following four aspects。

 one is data parallelism。

![](img/3c11e41698f0868314a0cef338e9d65e_23.png)

呃， pipeline parallelism。Pencer parasal and the sequence parasal。

So this sequence parallelism is a new content we added this year in last year and the year before last year we don't have this content。

 this is new given the fast development of long sequence， long contacts， large language model。



![](img/3c11e41698f0868314a0cef338e9d65e_25.png)

Like well a video can be one hour an hour long video in 1080 peak can easily exceed 100 million tokens right a whole series of Harry Potter book is a million tokens so how to parallelze them across the sequence dimension is also very crucial so we added this new chapter。

So let's first look at the data parallel。

![](img/3c11e41698f0868314a0cef338e9d65e_27.png)

Imagine we have a deep learning model， we have a lot of trading data。

 one idea is to distribute across different part of the data， like we have three part， blue part。

 the green part， the orange part， and then we paralyze the yellow the blue part to GPU1。

 the green part to GPU2 and orange part to GPUN。

![](img/3c11e41698f0868314a0cef338e9d65e_29.png)

So we are splitt， splitting the trading data to multiple GPUs， splitting the data。

A and each GPU are sharing a the same model。The city model across different GPUus。

 So thats data parallel， we are partitioning the data。 We are sharing the model。

And the second technique， we can partition the model。



![](img/3c11e41698f0868314a0cef338e9d65e_31.png)

And sharing the data。Aration the model in M parts。In the pipeline manner。

 but they are sharing the same training data set， sharing the same training data set。



![](img/3c11e41698f0868314a0cef338e9d65e_33.png)

![](img/3c11e41698f0868314a0cef338e9d65e_34.png)

So we have a single copy of data。But we are partitioning， splitting the model on GPU1， GPU 2。

 GPUN are processing different layers of the model。And next is the Tensor parallelm。

We can partition in another dimension， okay we are also parting the model。

 but not from the layer dimension， but within the layer。

 we are partitioning a different part of the matrix multiplication across different GPU。



![](img/3c11e41698f0868314a0cef338e9d65e_36.png)

There are partition in the activations， the first， a third， next third。

 the last a third of the activation is fed to different GPUs。



![](img/3c11e41698f0868314a0cef338e9d65e_38.png)

And in this case， GPU1 is responsible for the first third of the activation。

And then we can continue the same way for different layers。Okay。

 so this is also sharing the same training data， but we are partitioning across different activation for the model。

For example， if you have a big matrix modification like 4K by 4K。

 you can partitioning that by 4 to 4K by 2K and use two GPUs process that 4 GPU 4K matrix modification。

Okay， lastly， we have this sequence heroism。Okay， so say we have a long context。

 long text for training， like three books。

![](img/3c11e41698f0868314a0cef338e9d65e_40.png)

First， we have thispat size dimension。啊，Token dimension， hidden dimension。哎， so the batch dimension。

 we can use the data terrorism。Slint by the batch， like three books with split it and use only one book on one GP。

And then from the token dimension， the token is too long。

 like the book can have like tens of thousands of tokens。



![](img/3c11e41698f0868314a0cef338e9d65e_42.png)

![](img/3c11e41698f0868314a0cef338e9d65e_43.png)

So we can exploit sequence carrier， a long sequence， we can split it into several shorter sequence。

You can split the tokens just like this book， we have three chapters。

 you can see chapter one to GPU1， chapter two to GPU2， chapter 3 to GPU 3。Justs like this。



![](img/3c11e41698f0868314a0cef338e9d65e_45.png)

so each GPU is responsible for all the entire model， the model is not each GPU has the whole model。

 but it's only responsible for processing a part of the sequence part of the sequence since the total sequence too long each GPU just process part of it so that sequence parism。

 so this is a quick overview of the four different parallelization approaches。

 and now we are going to dive deeper into each parallelization approach and see how to we implement the film。



![](img/3c11e41698f0868314a0cef338e9d65e_47.png)

![](img/3c11e41698f0868314a0cef338e9d65e_48.png)

So we are going to start with data parallelism， communication primitives， zero and FSDP。

 so these are all related to data parallelism。

![](img/3c11e41698f0868314a0cef338e9d65e_50.png)

Next， we're going to talk about pipeline parallelism。

And then tensor parallel followed by sequence parallels to cover all the four priorization techniques。



![](img/3c11e41698f0868314a0cef338e9d65e_52.png)

He， ready， let's go with the data horizon。

![](img/3c11e41698f0868314a0cef338e9d65e_54.png)

So let's first introduce a method called using a parameter server。

 so we can scale the distributed training with parameter server。



![](img/3c11e41698f0868314a0cef338e9d65e_56.png)

So this is a centralized approach， not quite widely used anymore。

 but let me start by introducing the basics。

![](img/3c11e41698f0868314a0cef338e9d65e_58.png)

So there is a central controller of the whole training process and then we have many worker node in this case we have four workers。

 the parameter server or receive the gradient from the workers and send back the aggregated results。



![](img/3c11e41698f0868314a0cef338e9d65e_60.png)

And each worker will receive a part of the training data， a split training data。

And then update and calculate the gradient and send the gradient to the parameter server。



![](img/3c11e41698f0868314a0cef338e9d65e_62.png)

So put it in another way， we have a neuralNe model， we have a gradient in the parameter server。

 and we have pool of worker node。Including the gradient。

 the local replica of the neuralnaal model and the training data and the training data is splitted from the entire training data set and we split it into four parts。

 each GPU is responsible for one part。

![](img/3c11e41698f0868314a0cef338e9d65e_64.png)

To begin with。The parameter server will replicate。

![](img/3c11e41698f0868314a0cef338e9d65e_66.png)

Replate the model。And each worker will pool。The model from the prime server， right， so four workers。

 each will pull the model from the worker。

![](img/3c11e41698f0868314a0cef338e9d65e_68.png)

![](img/3c11e41698f0868314a0cef338e9d65e_69.png)

And then it will also split the data set randomly but evenly。



![](img/3c11e41698f0868314a0cef338e9d65e_71.png)

Across four workers。And we have the weight， we have we have the data。

 then each worker will calculate the local grid on that piece of training data。



![](img/3c11e41698f0868314a0cef338e9d65e_73.png)

Over that local replica of the model。So the question is， are the four local gradients the same？No。

 they are not the same because they're using the same model。

 but they're using different pieces of training data， which is randomly splited。



![](img/3c11e41698f0868314a0cef338e9d65e_75.png)

Okay， so they each have a copy of local greetings。What they do is they push。



![](img/3c11e41698f0868314a0cef338e9d65e_77.png)

The local gradient will sum them up to the prime care server。



![](img/3c11e41698f0868314a0cef338e9d65e_79.png)

Okay so we'm going to have the prime server right here。



![](img/3c11e41698f0868314a0cef338e9d65e_81.png)

And the primary server is responsible for updating the neuralnaural model with。



![](img/3c11e41698f0868314a0cef338e9d65e_83.png)

A gradient。

![](img/3c11e41698f0868314a0cef338e9d65e_85.png)

So now。So。Primeterter server will replicate。And each worker will replicate and pull the updated model。

To update his local copy， otherwise， this local replica will will be still。 He。

 now it's going to be replicate a new model。

![](img/3c11e41698f0868314a0cef338e9d65e_87.png)

And then repeat this process to pull the model， split the data， calculate the local gradient。

 send it to the primary server， primary server， update the model。

 and then each worker pulled it again。

![](img/3c11e41698f0868314a0cef338e9d65e_89.png)

So if we see the difference between single node training versus distributed training。

 previously each iteration with sample the data， calculate the gradient。

 form a step to update the weight。Now we add this part to pull the gradient from the printer server and then it's the same sample the data。

 calculate the gradient， and we added another part here to push the gradient to the printer server。

And some sum it up and then Prime Minister will perform this good news stamp。



![](img/3c11e41698f0868314a0cef338e9d65e_91.png)

![](img/3c11e41698f0868314a0cef338e9d65e_92.png)

So there are actually two synchronization steps here in the red。



![](img/3c11e41698f0868314a0cef338e9d65e_94.png)

Okay， so make sure each server， each worker is synchronized。So synchronization has overhead。

 is not free， so let's talk about these communication primitives and see how can we save this communication overhead。

So there are a couple of communication primitives when you come to send and receive data。

In the forward the network across different node， so a simple one simple one is send and receive okay。

 so we have several nodes we can send from node zero to node3 this is receiving from node3 to node zero okay so this is one to one communication transferring data from one to another。



![](img/3c11e41698f0868314a0cef338e9d65e_96.png)

![](img/3c11e41698f0868314a0cef338e9d65e_97.png)

![](img/3c11e41698f0868314a0cef338e9d65e_98.png)

And then we have one too many， scatter and gather。Okay so scatter her basically send a attention to all the other workers。

And so Tensor's four components， it will send it to zero， one，2，3， so this is one， to many。

 one too many。And gather is basically the reverse money to one。

 then we gather the beta from worker zero， worker one， worker2， worker3。

 and gather everything into worker zero。

![](img/3c11e41698f0868314a0cef338e9d65e_100.png)

To receive the answer from all other workers is taught is many to one versus scatterer is sending the data to many servers。

 one too many。

![](img/3c11e41698f0868314a0cef338e9d65e_102.png)

![](img/3c11e41698f0868314a0cef338e9d65e_103.png)

Another one for many is capturing reduce also reduce。



![](img/3c11e41698f0868314a0cef338e9d65e_105.png)

It's very similar to， but it's different， so gather basically only gather all the data。

 but reduce will'll do another operation which is sum made up。Or。Finding the sum。

 finding the max is going to do a reduce operation after the gather operation。

 so you can think of reduce operation as。The gather operation followed by a reduction operation。

 so if you sum them up， then that's reduce， if you don't sum it up， leave it at this。

 then it's gather。

![](img/3c11e41698f0868314a0cef338e9d65e_107.png)

![](img/3c11e41698f0868314a0cef338e9d65e_108.png)

There's also another one too many operation called broadcast。

 so broadcast one tensor to all the workers。

![](img/3c11e41698f0868314a0cef338e9d65e_110.png)

![](img/3c11e41698f0868314a0cef338e9d65e_111.png)

Broadcast is actually different from scatter。So Ser is going to send tensor different parts of the tensor to different workers and different workers will receive different piece of data。



![](img/3c11e41698f0868314a0cef338e9d65e_113.png)

But broadcast。

![](img/3c11e41698f0868314a0cef338e9d65e_115.png)

Will send identical copies of data。

![](img/3c11e41698f0868314a0cef338e9d65e_117.png)

To all the other workers， that's the difference between broadcast versus scatter。



![](img/3c11e41698f0868314a0cef338e9d65e_119.png)

Finally， we have this many too many operation。

![](img/3c11e41698f0868314a0cef338e9d65e_121.png)

So this is our reduce， this is all， so our reduce will perform a reduce operation on all the workers。

 So if you look at our reduce versus reduce reduce is basically working on one receiver。



![](img/3c11e41698f0868314a0cef338e9d65e_123.png)

But for all reduce， theyre performing reduce on all the workers， reduce on zero， reduce on one。

 two three， okay。And similarly， for the all gather operation is to perform together on all the workers gather on worker zero。

 gather from worker one， gather on worker two， gather on worker three。



![](img/3c11e41698f0868314a0cef338e9d65e_125.png)

So that's the relationship between reduce， gather， or reduce and all together。



![](img/3c11e41698f0868314a0cef338e9d65e_127.png)

So this is reduced。This is together。

![](img/3c11e41698f0868314a0cef338e9d65e_129.png)

Operating on one receiver， operating on one receiver。

But running too many it's operating on many receivers， okay。They share some similar properties。

So let's see， how do we use those communication primitives？In the parameter server setting。



![](img/3c11e41698f0868314a0cef338e9d65e_131.png)

So we just talk about primary server， and then we have manual workers。

 they have a different replica of the training data。



![](img/3c11e41698f0868314a0cef338e9d65e_133.png)

So which type of communication scheme is used when we are replicating？



![](img/3c11e41698f0868314a0cef338e9d65e_135.png)

In the blue part。Versus the orange part when we are pushing and suming the ingredients。



![](img/3c11e41698f0868314a0cef338e9d65e_137.png)

So we have all reduce， all gather， reduce， broadcast， scatter， scatter， gather， send and receive。

During the orange and blue operation， which operation which。Communication primitive are we using？



![](img/3c11e41698f0868314a0cef338e9d65e_139.png)

Yeah， so the broadcast is used for replicating and pool right so we have our central prime server and we want to broadcast the weight to all the workers。

And for pushion sum is reduced and so we averaging from all the workers。

 other worker get its own gradient and we want to sum the gradient in the private server so it's actually reduced。

 it's not only gather， it need to also perform a reduction， so it's reduced。



![](img/3c11e41698f0868314a0cef338e9d65e_141.png)

So what is the bottleneck here， what is the bandwidth requirement to do this？

So replicate and pull each worker is O one。 right You just need to pull one copy of data。



![](img/3c11e41698f0868314a0cef338e9d65e_143.png)

But for the parameter server， the bandwidth is ON。Because you have N workers。

So the replicate and the pool will take ON。Communication complexity。For the push。

 each worker just need to push its own copy of grade。 So that's O one。Butful primary server。

And to receive end copies so。

![](img/3c11e41698f0868314a0cef338e9d65e_145.png)

The complex is all。

![](img/3c11e41698f0868314a0cef338e9d65e_147.png)

So it's actually pretty heavy， right， for the primary server， the networking traffic。



![](img/3c11e41698f0868314a0cef338e9d65e_149.png)

It's O， it's not quite scalable， the more worker you have。

 the larger the bandwidth requirement is needed。

![](img/3c11e41698f0868314a0cef338e9d65e_151.png)

So the bandwidth of the central parameter server will grow linearly。



![](img/3c11e41698f0868314a0cef338e9d65e_153.png)

With the amount of workers， which can be a bottleneck。When you have a lot of machines。

So a natural thinking is， can we make it more scalable by getting rid of this centralized parameter server and make everything decentralized without a parameter server？

Of course， we can do that by using this or reduce operation。

To get rid of is centralized the Pre server。And how do we do that？



![](img/3c11e41698f0868314a0cef338e9d65e_155.png)

So以 we start with a naive on reducing implementation and using the sequential way。



![](img/3c11e41698f0868314a0cef338e9d65e_157.png)

So each GPU will calculate its local gradient on its of own piece of data， right？



![](img/3c11e41698f0868314a0cef338e9d65e_159.png)

And now we perform or reduce on our node。 Okay， so reduce on node 0。 Okay， reduce on note  one。

 reduce on node 2， reduce on node 3。 So each node， each worker will do a。



![](img/3c11e41698f0868314a0cef338e9d65e_161.png)

![](img/3c11e41698f0868314a0cef338e9d65e_162.png)

Gather and then reduction to combine。

![](img/3c11e41698f0868314a0cef338e9d65e_164.png)

All the gradientings together。Although the calculation has some redundancy。

 they are all calculating the sum of this。

![](img/3c11e41698f0868314a0cef338e9d65e_166.png)

![](img/3c11e41698f0868314a0cef338e9d65e_167.png)

Green， yellow， blue， and red， right？

![](img/3c11e41698f0868314a0cef338e9d65e_169.png)

So what is the time complexity， actually that's O sequentially doing the reduce reduction， Okay。

 so time is O， what about the bandwidth。

![](img/3c11e41698f0868314a0cef338e9d65e_171.png)

![](img/3c11e41698f0868314a0cef338e9d65e_172.png)

It's also because each worker requires receiving the data from all the other workers。

 so both the time and bandwidth is all， which is not good。



![](img/3c11e41698f0868314a0cef338e9d65e_174.png)

So can we do better？So we can do this a better ring。

 reduce operation by using this ring or reduce what does that look like？



![](img/3c11e41698f0868314a0cef338e9d65e_176.png)

![](img/3c11e41698f0868314a0cef338e9d65e_177.png)

So it's that one。Work her zero。Send the gradient to worker one， worker one， send it to worker2。

 worker2， send it to all worker3， worker3， send it to worker zero， Okay， so at this moment。

 worker zero has data both from itself and also from worker3。Okay， so Worlder one。

Can have the data can have the gradient both from worker one and worker zero since worker zero is sending to worker one and worker one previously already have this yellow data。

 so now it has both the yellow data and on the green data。So that's the first step。

And the second step， we do the same worker zero。Some data to work a lot such that。

Worker one has both the green， the yellow， and also the red。It is's red， ands green， it has yellow。

AndWorker one send its greeting to worker2。Such that Mor code4 will have。The orange the the yellow。

 the blue， and also the green， the green comes from lower white。And we do the same for two two three。

 three to zero。

![](img/3c11e41698f0868314a0cef338e9d65e_179.png)

In a real manner， so everyone just sent to his neighbor。



![](img/3c11e41698f0868314a0cef338e9d65e_181.png)

And after step 3，0， and one，1 and2， so that worker one has data from the red， the the green。

 the yellow， and also the blue， so now it has all the data。有命。

And similar things happens for all the other notes， they each have the green， the orange， the yellow。

 the blue and the red。

![](img/3c11e41698f0868314a0cef338e9d65e_183.png)

So only in four steps。And we have all the data。So the time is still on。



![](img/3c11e41698f0868314a0cef338e9d65e_185.png)

Since we have four node， we require three steps， so time is still O， but bandwidth， it's only01。



![](img/3c11e41698f0868314a0cef338e9d65e_187.png)

We only need to communicate with our neighbor， so there's no very little bandwidth needed right here。

Remember previously the primary server， the centralized primary server requires ON bandwidth now everything is all what so that's good we made some progress by using the ring or reduce。



![](img/3c11e41698f0868314a0cef338e9d65e_189.png)

![](img/3c11e41698f0868314a0cef338e9d65e_190.png)

Can we do even better？ There is still some redundant computation， right， Can we do even better。Okay。

 so before looking at the more advance version， let's look at na or reduced implementation。

 parallel reduce。So previously， we talk about sequential or reduce of four steps for four workers。



![](img/3c11e41698f0868314a0cef338e9d65e_192.png)

We can do all everything in parallel。 At the same time， worker  zero is doing a reduce worker one。

 worker  two， worker3， they are all doing the reduce， Okay， so we only only need0 one time。

Since it's not sequential， it it's parallel。 However， the bandwidth of its O N square， so all the。

Each arrow， everything is happening at the same time， so we have N， we have N。

 so we have O N square communication happening in the middle。 So the time is pretty short。

 but the bandwidth is too large。

![](img/3c11e41698f0868314a0cef338e9d65e_194.png)

![](img/3c11e41698f0868314a0cef338e9d65e_195.png)

Compared with this ring or reduce， we need the ON time， time is large， but bandwidth is small。



![](img/3c11e41698f0868314a0cef338e9d65e_197.png)

So can we have even better solution。Sumaries so far， we talk about parameter server， for one time。



![](img/3c11e41698f0868314a0cef338e9d65e_199.png)

But peak node bandwidth is O， total bandwidth O。Sequential or reduce。

I is O N peak note bandwidth O N， total bandwidth is also O N。For all reduce， using a ring manner。

 the peak note bandwidth is reduced to O1 since I only need to communicate with my neighbor。

Ptto bandwidth is still on， things have to do that for n times。And parallel or reduce time is01。

 which is pretty good。 But peak node bandwidth is O N for each node。

 The total bandwidth is O N square。

![](img/3c11e41698f0868314a0cef338e9d65e_201.png)

And now we want to combine the advantage of the ring and parallel or reduce or ring or reduce combined with parallel or reduce。

 and let's see how do we further reduce the bandwidth in time。Okay。

 so now the example gets a little more complicated， so let's use8 eight node in this example okay so。



![](img/3c11e41698f0868314a0cef338e9d65e_203.png)

![](img/3c11e41698f0868314a0cef338e9d65e_204.png)

In the first cycle， we will combine the data from adjacent node。



![](img/3c11e41698f0868314a0cef338e9d65e_206.png)

With neighbors with outside of one that's adjacent know。So one combined with two， two with three。

 or sorry， three with four， five with six， seven with eight。



![](img/3c11e41698f0868314a0cef338e9d65e_208.png)

![](img/3c11e41698f0868314a0cef338e9d65e_209.png)

And as a result， node one has both the green and red。No two also have green and red。

 no three has this blue and orange。

![](img/3c11e41698f0868314a0cef338e9d65e_211.png)

cetera， okay， so just after one cycle， everybody communicated with its neighbor with offset one。

Step two， each node will exchange with neighbors with offset two。



![](img/3c11e41698f0868314a0cef338e9d65e_213.png)

Okay， so node one will communicate with node。3。And no three will communicate with node the one。

 no two will communicate with no the four。Okay， so this is one group and the other group。

 node five will communicate with node7 and six with eight。And as a result。

You can see we are already making some progress， everything on the left。

 we already have all four colors， everything on the right， already has all the four colors。

 so we can do one more iteration to complete this we can complete this job。



![](img/3c11e41698f0868314a0cef338e9d65e_215.png)

So let's your brainstorm。How should we do next， what should we communicate？

In the next step so that everybody has。Bate colors。With a larger offset， first one。

 last one or first one with a fifth one。Right， so if we。Exge。



![](img/3c11e41698f0868314a0cef338e9d65e_217.png)

The node with neighbors of outside four。Then their first node and the fifth node。

That we'll communicate with each other right and second one with a sixth one。



![](img/3c11e41698f0868314a0cef338e9d65e_219.png)

Another result。This one will have also this color， so all the eight colors for each node will have all the eight colors。

 right？And then we complete this process and how many cycles did we take？



![](img/3c11e41698f0868314a0cef338e9d65e_221.png)

Actually， we have eight node， but only three cycles。



![](img/3c11e41698f0868314a0cef338e9d65e_223.png)

Okay， after three cycles， every node has a data from everybody else。

So only log N steps rather than O step， which is much faster。



![](img/3c11e41698f0868314a0cef338e9d65e_225.png)

So this is called re recursive havinglving or reduce。



![](img/3c11e41698f0868314a0cef338e9d65e_227.png)

People also call it butterfly or reduce because this structure looks like a butterfly。

 but not exactly。

![](img/3c11e41698f0868314a0cef338e9d65e_229.png)

![](img/3c11e41698f0868314a0cef338e9d65e_230.png)

It just。For end workers， all reduce can finish within low bin steps。

So this is much widely used technique compared with a parameter server， like in our lab。

 we do a lot of distributed training but we don't use a centralized parameter server。

 instead we use this or reduce method。Okay。Okay， so now let's switch gear to continue talk about data parallelism to reduce the memory using the zero。

 one，2， three and fully sharded distributed fully shed data parallelm Before that。

 let's take a quick break。

![](img/3c11e41698f0868314a0cef338e9d65e_232.png)

![](img/3c11e41698f0868314a0cef338e9d65e_233.png)

All five minutes。All right， welcome back。Let's continue a discussion about zero and I IDP。

 So zero is actually a very popular technique for large training large language model these days。

 It stands for。Zero redundancy optimizer。 so let's see how that works。



![](img/3c11e41698f0868314a0cef338e9d65e_235.png)

So recently the large language model is pretty big。

 like Gb3 is 175 175 billion parameters if we train it even in FP16。



![](img/3c11e41698f0868314a0cef338e9d65e_237.png)

![](img/3c11e41698f0868314a0cef338e9d65e_238.png)

So just to hold those weight， how much memory do we need？We need 350 gigabyte of memory。

 just to hold the weight， not to mention the activations， the gradient， the optimizer state。



![](img/3c11e41698f0868314a0cef338e9d65e_240.png)

![](img/3c11e41698f0868314a0cef338e9d65e_241.png)

Well， a 100 GPU or H100 GPU has 80 gigabyte of memory， B100 is getting larger。

 but still less than 200。

![](img/3c11e41698f0868314a0cef338e9d65e_243.png)

Right so even a best GPPU可能 feed the models waiting to wait into memory。



![](img/3c11e41698f0868314a0cef338e9d65e_245.png)

So how do we solve that problem using limited GPU memory to train big model？

So let's first break down。What is the memory consumption to train a single parameter？



![](img/3c11e41698f0868314a0cef338e9d65e_247.png)

Okay so we can break down into three component， the weight， two bytes per weight。

 assuming is FP 16 training， which is already pretty popular these days， ingredient2 bytes， FP 16。

We also have to store those optimizer states。Including three part。

One is a FP 32 copy of the parameter。 So the weight requires a master copy。

 a full precision master copy for the accumulation。 So that's4 bytes。



![](img/3c11e41698f0868314a0cef338e9d65e_249.png)

We need another two numbers for the optimizer state if you need to use the item optimizer。

 you need to store both the first order and second order momentum。

The two momentum require two number and the master copy of the weight is another number。

 so altogether we need three numbers。

![](img/3c11e41698f0868314a0cef338e9d65e_251.png)

Every number is four bytes， so you need altogether 12 bytes for the optimizer states okay so this optimizer state and this is the gradient this is the weight and so optimized state actually occupies a pretty large portion of the total total memory。

So。This is the total sum， summing up the weight， the gradient ultimately estate。Altogether。

 you need 16 bytes。To store or to train for each parameter。

And so we can calculate if we do the tri naively， how many parameters can a train on a 80 gigabyte of memory。

Even not to mention the activation。So 16 bytes。For each parameter。

We can train only  five billion parameter model， even not even a Lama 270 so only 5 billion parameters。

 which is far away from the current state of the art。



![](img/3c11e41698f0868314a0cef338e9d65e_253.png)

So how can we do better？So previously， we are having copies of the weight gradients of the optimizer state across each GPU since we are doing data terrorism。

They are processing different data， splitting the data， but they are sharing the model。

 So each GPU has the same， same copy。Zero one basically proposed we can partition or we can call it sh。

 the optimizer state。

![](img/3c11e41698f0868314a0cef338e9d65e_255.png)

So since we have NGPUs， we don't need to store a we can still only store the local copy。For each。



![](img/3c11e41698f0868314a0cef338e9d65e_257.png)

For each of them， rather than storing and copies of them。



![](img/3c11e41698f0868314a0cef338e9d65e_259.png)

So if we have entryPs， we no longer need to store 12。



![](img/3c11e41698f0868314a0cef338e9d65e_261.png)

But it's each， but we can store a 12 divided value button， so we are sharding the optimizer state。



![](img/3c11e41698f0868314a0cef338e9d65e_263.png)

If we have N equal 64。

![](img/3c11e41698f0868314a0cef338e9d65e_265.png)

We put an equal to 64 right here。Each parameter can require only 4。2。



![](img/3c11e41698f0868314a0cef338e9d65e_267.png)

And we can feed 19 Bs。19 billion parameter in a single 80 gigabyte of GPU。So that's  zero one。

Zero2 is more aggressive。

![](img/3c11e41698f0868314a0cef338e9d65e_269.png)

Okay， zero stands for zero redundancy optimizer， so 0 two also shard。Not only the optimizer states。

 but also the gradient。So the gradient。 so the gradient is also2 divided by M。上的规定还 well。

So each parameter requires 2。2 bytes。To train an 8 gigabyte of memory can train a 36 billion parameter model。

 so that's much bigger。

![](img/3c11e41698f0868314a0cef338e9d65e_271.png)

So this's already pretty big。

![](img/3c11e41698f0868314a0cef338e9d65e_273.png)

Zero three。Is an even more aggressive approach by sharding not only the optimizer state。

 the gradient， but also the weight。

![](img/3c11e41698f0868314a0cef338e9d65e_275.png)

so each server no longer have the whole copy。The entire copy of the weight。

 it only have one over n of the weight。 So the weight is also sharded。

 split partisitioned across N GPUus， so。The total number parameter啊 totalt number byte。no。Becomes 0。

25 bys。For 80 gigabyte of memory and I'll hit 320 billion parameters， so that's a lot larger。

So this is the widely used approach。To train these large language models， Okay。

 so we shard the weight， shard the activity shard the optimizer state。

 shard the gradient and also shard the weight。

![](img/3c11e41698f0868314a0cef338e9d65e_277.png)

Across the GPUs， so you can increase。The twinable prime are from。

Just maybe five billion parameters all the way to 300 pure billion parameters。

Okay so in Pytorch is 03， this algorithm proposed by Microsoft is implemented by fully sharded data Para okay it's known as FSTP very widely used library these days feel free to try it out。



![](img/3c11e41698f0868314a0cef338e9d65e_279.png)

So for large language models。Below like 7 billion parameter。

 it's pretty safe to use this approach to train it。Okay。

 so that's the zero and FSDP now let's switch gear to talk about pipeline parallelism okay remember we have four parallelism to talk about one is data parallelism including communication primitives and sharding and pipeline parallelism cancer parallelism and and sequence parallel。

 now let's switch gear to talk about second part which is pipeline parallelism。



![](img/3c11e41698f0868314a0cef338e9d65e_281.png)

![](img/3c11e41698f0868314a0cef338e9d65e_282.png)

So data parallelism， what are we splitting， where are splitting the data？Sharing the weight。

 Now we are splitter data。

![](img/3c11e41698f0868314a0cef338e9d65e_284.png)

Instead of sticking the data， we want to split the model， okay so the model may have many layers。



![](img/3c11e41698f0868314a0cef338e9d65e_286.png)

We can put each layer on one worker。What is the good thing about what language model is that？

Different blocks， different layers are identical。Identical number of hidden size。

 identical number of heads。So each parallel pipeline stage are exactly taking exactly the same time。

 so which is very suitable。For pipeline parism。If we split it's 350 gigabyte across。



![](img/3c11e41698f0868314a0cef338e9d65e_288.png)

E card， so each card requires only 43。0。75 gigabytes， which is smaller than 80 gigabytes。



![](img/3c11e41698f0868314a0cef338e9d65e_290.png)

So this is the money required for the 175 billion prime on weights。

So that's another dimension to fit a larger model within the limited GPU memory。

So now you implementation。

![](img/3c11e41698f0868314a0cef338e9d65e_292.png)

Basically partition the training data flow say we have four different layers forward at 0，1。

23 and backward 32，10 Okay we need to store the intermediate intermediate。

Acs to calculate the backward and so its the forward GPU 0，1，2，3 and backward 3，2，1，0。

 finally we can update。

![](img/3c11e41698f0868314a0cef338e9d65e_294.png)

So the model is split into four partition in this way and assigning each partition to one GPU。

And the problem is that if we just process a single batch in this way， GPUs are underutilized。

A lot of idol， a lot of bubbles in this case。So what is the theoretical utilization here？

So only one quarter， 25% utilization。Because most of the time， the GPU is idle。

So what is the best way to do that？So previously we have a big batch now we want to scale it with micro batch。

 pipeline parallelism。

![](img/3c11e41698f0868314a0cef338e9d65e_296.png)

What you're saying is that previously we have like 16 batches now we want to split it into four batch four such four batchs。



![](img/3c11e41698f0868314a0cef338e9d65e_298.png)

![](img/3c11e41698f0868314a0cef338e9d65e_299.png)

So rather than naive parallellyization， now we can make a look at this。So small batch， one， two。

 three， or four batches。And then after GPU0 completes F 00。

 it can handle the data to GPU1 to compute GP F10 and the GPU0 continues to talk。



![](img/3c11e41698f0868314a0cef338e9d65e_301.png)

To compute I 401。 Okay， so in this way， the bubble is a lot less compared with the naive implementation。

So we want to make a computation split it more fine grid in a fine grade manner。



![](img/3c11e41698f0868314a0cef338e9d65e_303.png)

Previously 25% utilization now using micro badge， it can improve it to 57%， which is 2。

5 x improvement。

![](img/3c11e41698f0868314a0cef338e9d65e_305.png)

So lesson we learned here is that we want to split the training in a fine grain manner。

 so beyond pipeline parallelm to split the model， we also have another degree to split the model。

 which is sensor parallelism to split the model。Okay。

 so further improve the granularity to make a more fine grain。嗯。

By partitioning further partition in the model， not just the layer， even for a single layer。

 we want to continue partitioning that。

![](img/3c11e41698f0868314a0cef338e9d65e_307.png)

Say a layer has a two by two by three matrix okay， so we want to this is a single F layer right。

 a single F layer， we want to partition that into three parts。啊，GP one，GP2，GP3。

And each GPU is calculating only one third。Of the matrix。

And finally we can get the result in parallel， so partition the model in a more or fine green manner within a layer。



![](img/3c11e41698f0868314a0cef338e9d65e_309.png)

And that fits perfectly for large language model， so this is the illustration of tensor parallelism in megatra。

So。Including both MLP layer and also the self attention layer。

Here we want to minimize what do we want to minimize， minimize the communication。

 right since compute chip communication is expensive。

So we only need to communicate in F and G in the start in the end。Which dennots this our reduce。

And synchronization operations。Okay， so this is one is。Scatter one is the or reduce operation。用心。

Communication only happens in the beginning and also in the end。

And let's see how that works first for the FFN layer。

So we have two FFM layers in large language model， okay， one FF layer， a second FFM layer。



![](img/3c11e41698f0868314a0cef338e9d65e_311.png)

We just give an example could be simple one by two metrics， this is the activation， one by two。

And two by6， which is the weight。Of the first FA layer。We have two GPUs in this case。

 we split it in this way， each GPU hold two by three and two by three to two GPUs that's two by6。

 right？So we first do a broadcast， okay， broadcast， broadcast the activation to two GPUs， GPU1， GPU2。

 we perform half of the matrix modification on each GPU。

 the other half of the second GPU and we get y1 and y2 okay corresponding to here are y1 and y2。

No communication is needed。Need in here， and then we can directly move to the next section。

In the next section， we are performing the second matrix modification。

 which is of dimension6 by two okay so this is the activation from the previous layer and we have the matrix6 by two so six by4。

 right？Now we split it horizontally GPU1， GPU2， GPU1 is responsible the first half。

 GPU2 is responsible for the second half。And what we do here is we perform y1 times B1。

Independently with y 2 times V2， A， y1 times V1， y 2 times V2。

Okay so no communication is needed because11 is associated with B1， there's nothing to do with B2。

 right？And then we can obtain two intermediate outputs， Z1， which is one by two， Z2 is one by two。

What is the final dimension of？Of the matrix modification， one by two， two by6，6 by two。

 so the result should be one by two， right？But now we are two， we get two one by two tensors。

So they are partial， partial sum。So we have to sum up the partial sum and now we have to do a communication。

 we want to do all reduce operation to sum the up。U together Z and so corresponding to here。

 we do all reduce appreciation to some demand。Into Z。So， we only need。

A broadcast in the beginning and are reduce in the end。

 and in the middle these two matrix modifications are done in parallel across two GPUs Bill1 and GPU2 in this case。



![](img/3c11e41698f0868314a0cef338e9d65e_313.png)

So two matrix modifications corresponding to the two FFN layer in large language model is perfectly paralyzing。



![](img/3c11e41698f0868314a0cef338e9d65e_315.png)

And let's look at here in the middle of the MLP， we discussed that it doesn't require any communication because it takes。



![](img/3c11e41698f0868314a0cef338e9d65e_317.png)

The first matrix is partitioned vertically， the second is partitioned horizontally and there's no communication is needed in the middle。

And let's see， how do we do that for the attention view？



![](img/3c11e41698f0868314a0cef338e9d65e_319.png)

So this is the self attention with QKV transformation， softm。

 and then DoA and then matrix modification。

![](img/3c11e41698f0868314a0cef338e9d65e_321.png)

Two major modifications， finally， followed by a。Output projection layer， okay？



![](img/3c11e41698f0868314a0cef338e9d65e_323.png)

So this is the QKV。transformation matrix， A， we have Q K V O。 We have four transformation matrix。

3 for the input， one for the output。 So this the three transformation for the input。

The hidden dimension is2 okay， so we have two by6， two by6 for Q two by6 for k for the key and two by two by6 for the value okay。

 input is two one by two。

![](img/3c11e41698f0868314a0cef338e9d65e_325.png)

One by two and two by six， so that's perfectly match。So what we do here。

 we also split in the split vertically across two GPUs。

 so each GPU is responsible for only half of the hidden dimension。

Actually that's the head dimension and each GPU is responsible for one head， one head。

 this is another head and we do a broadcast okay， so X is broadcasted to GPU1 and the GPU2。



![](img/3c11e41698f0868314a0cef338e9d65e_327.png)

And GPPU1 is holding the first half the transformation matrix for Q。

 GPU2 which responsible for the second half of the transformation matrix transformation matrix for the Q similar for the K and similar for the V okay we are broadcasting x in this way。

 so we do the matrix modification one by two， two by3， so we get one by three one by three。



![](img/3c11e41698f0868314a0cef338e9d65e_329.png)

A responding to the QOKB transformation。And next we want to do the attention okay so asq time2 k transpose times v。

 either is a soft max。

![](img/3c11e41698f0868314a0cef338e9d65e_331.png)

![](img/3c11e41698f0868314a0cef338e9d65e_332.png)

So we do。For the first GPU。

![](img/3c11e41698f0868314a0cef338e9d65e_334.png)

Remember right here， the first GPU already has。啊，Q1 K oneV one second degree还是Q two V two and pay two。

 so we are doing them separately for。Q1， K1 and V1， we can do the QK transpose soft max times V。

QK transpose soft soft max times V independently as the Q2 Okay。

 so QK transpose soft max times V they are independent。

And then we get y1 and y2 corresponding responding to here， we'll get at y1 and y2。



![](img/3c11e41698f0868314a0cef338e9d65e_336.png)

So far， no communication is needed。And finally， we want to do the output projection。

 remember we have  Q K VO4 projection motions now we are talking about the last output projection。



![](img/3c11e41698f0868314a0cef338e9d65e_338.png)

We have y1 and y2 right here and this is the projection matrix which is6 by2 input is one by6。

 so we split the output projection horizontally such that we can do the B1 with the first half and B2 with the second half。

So yy is multiplied with B1， y2 is multiplied with B2 and similar to before we get these two intermediate outputs in Z1 and z2。

And finally， we do all reduce now we need this operation， this all reduce operation。

 we need this communication right here， we do a communication in the last end together of Z final Z。



![](img/3c11e41698f0868314a0cef338e9d65e_340.png)

so that's the whole process of splitting in the head dimension for calculating the attention。

And the beauty here is that we only need communication at broadcast in the beginning on the communication which is all reduced in the end right here in gene in green and everything in the middle。

 there's no communication needed across the two GPUs。

 which is why this attention mechanism fits perfectly for multiple GPUs。

 I mean it's so easy to scale it up。

![](img/3c11e41698f0868314a0cef338e9d65e_342.png)

![](img/3c11e41698f0868314a0cef338e9d65e_343.png)

And Michael Tng attributed a huge contribution to scaling up these large language model traininging across multiple GPUs。

I don't know if the designer of Transformer actually。Thought about this parallelization process。

 but it's very beautiful that no communication is needed in the middle for both the attention and also for the two IFM layers。

But this is a perfect example for algorithm and system co design。For neural network acceleration。

All right， we are three quarters in our journey we talk about data parallelism about parallellyzing the data sharing the model。

 we also talk about pipeline parallelism and tensor parallelism which is sharing the data and partitioning the model now let's talk about the last one last parallellyzization technique which is sequence parallelism this part of the lecture is new this year don't have that yet in the last year because it is very trending topic for handling long context long context is very crucial for example for natural language processing you want to understand long documents right long documents。

 many books。

![](img/3c11e41698f0868314a0cef338e9d65e_345.png)

![](img/3c11e41698f0868314a0cef338e9d65e_346.png)

Complicated financial report， legal documents， etca。

 long context is also important for video understanding you want to understand the history to know when and what is happening at what time it also important for robotics you want to have a long trajectory of what has happened in the past in order to predict what's going to happen in the future so all that require a lot of tokens and tokens are very valuable these context lung is also valuable but it's very complicated to train take a lot of GPU memory。

That's why we need sequence parallelism to partition this long sequence。

 this long contexts into multiple GPUs， so one GPU can handle only a limited amount of tokens。Again。

 the rule of thumb is we want to minimize the communication， maximize the utilization。

 and let's see how can we partition that so this is the basic concept say we have a book of three chapters。

 three chapters。

![](img/3c11e41698f0868314a0cef338e9d65e_348.png)

Maybe each chapter is say 10 k tokens， now we have 30 30 k tokens， we put one 10 k for each GPU。

They are sharing the same weight， same model， but different part of the sequence。

 different part of the data。

![](img/3c11e41698f0868314a0cef338e9d65e_350.png)

The question here is that each GPU only has its own piece of data right for the query GPU1 has the first part。

 GPU2 has second part， GPU3 has the third part， similarly for the key and the values right。

 so different GPU only has its own QKV。

![](img/3c11e41698f0868314a0cef338e9d65e_352.png)

![](img/3c11e41698f0868314a0cef338e9d65e_353.png)

However， for the attention mechanism， we need to attend the first part of the document with the second part。

 first part with the third part， second part with the second part， second part with the third part。

 and third part with the third part right so that's n by N matrix。

 which require a lot of communication。

![](img/3c11e41698f0868314a0cef338e9d65e_355.png)

![](img/3c11e41698f0868314a0cef338e9d65e_356.png)

![](img/3c11e41698f0868314a0cef338e9d65e_357.png)

You can just do the attention locally。If you' just without any communication between GPU1 and 23。

 what's going to happen？Everything can only attend locally this chapter one will not see chapter 2。

 chapter3。Will not be able to see chapterpt2， Okay， so you cannot mingle the data anymore。

 say you want to cor something happened in Cha2 with chapter 3 you cannot do that only chapter3 with chapter3。

 chapter 2 with chapter 2， chapter one with chapter one that's too bad。



![](img/3c11e41698f0868314a0cef338e9d65e_359.png)

Let's see how do we solve this problem？Okay， I'm going to introduce two methods。

 feel free to come up with third one your final project。

 but solution one is a popular technique called deep speed releases。

Which is very widely used technique these days to repartition the data in the attention layer。

 so how do we do that let's see。

![](img/3c11e41698f0868314a0cef338e9d65e_361.png)

So this is a QKV transformation matrix， so we have the three tokens just。Use that as example， one。

 two， three。And we feed the token1 to GPU1。Okay so token 1 is one by two transformation matrix two by three so the result will be one by three and one by three the for the Q。

 one by three for the K， one by three for the V。Okay so GP2 is responsible for the second part of the token。

 okay， second part of token， the background is in green， okay， background is in green。

And the third GPU is responsible for the third part of the token， the background is in yellow。

AndGPU1，2，3 all share the same QKB transformation matrix。

So by multiplying this two by three matrix with the one by two by two by three。

 we get one by three for the Q for key and4B thanks so far so good we are each GPU is responsible for only one third of the tokens only one third of the tokens in different color。



![](img/3c11e41698f0868314a0cef338e9d65e_363.png)

And now we want to do the attention attention requires。嗯。



![](img/3c11e41698f0868314a0cef338e9d65e_365.png)

The firstequ first token and first part of the token also attend to the second part， second part。

 attend to the third part。And how do we do that we want to do all to all communication right here Okay so for all the queries。

 so all the queries are previously in GPU1 are GPU2。And GP3 for the different heads， right。

 we have three heads in this case， we have the light green， we have dark green and we have green。

 right， So now we want to collect everything related to the。Dark green into the third GPPU。

 Everything related to the light green in the second GPPU， everything in the。

We called it normal green in the first GPU， right， so each GPU is responsible for。

One part of the head now we are partitioning in the head dimension previously we are partitioning in the sequence dimension and a long sequence different part in blue in green。

 in yellow， right now we are partitioning the head dimension。This is head one。

 head two head three in green， height green and dark gray right now were part the in the head dimension so GPUY is responsible for head one。

 everything related into doing so we just collect everything in the first column。

Which is the first the had。Like everything to GPU1。So that we can compute the QKV， the tension。

 the complete attention for all the sequence right so it contains from token1 contains when token 2 contains information from token 3 right so everything related to the first head the entire sequence now is in GPU1。

 everything related to the second head for the entire sequence now is in GPU2 everything in the third head for the entire sequence now is in GPU3 then so we do the attention computation separately。

So in this way， you can see where does the communication happen？Communication happens here。Right。

 we need to auto all communication Okay， so previously each GPU has green， light green。

 dark green now GP1 has everything related to green GP2， everything related to light green， GPU3。

 everything related to dark green， So the number of GPUs equal to the number of partition in the sequences。



![](img/3c11e41698f0868314a0cef338e9d65e_367.png)

And we chop the sequence into three parts， we have three GPUs。

And also you go to the number of hass in this example， we have three hass。

So what's the limitation of this approach？看。Okay。对对下。对。我不意。我。

Because you have to first calculate the QKV transformation。

 you have to calculate this matrix modification before calculating the QKV transformation。

And therefore， in the middle， you have to do a communication to exchange the data。

 so everything related to head1 is gathered in GP1。问清楚啊。对。关。And if that's the exactly case。

 this is GPPU1 only has head one。 GPU 2 only has everything in head2。



![](img/3c11e41698f0868314a0cef338e9d65e_369.png)

But you cannot have that here。Because here we are partitioning the sequence on different GPUs。

But not here， GPP1 has all the hats， but only related to the first third of the sequence last。

 only first third。

![](img/3c11e41698f0868314a0cef338e9d65e_371.png)

So that's why we needed such shuffle， yeah。没。Right， exactly。Right。Yes。

 that's the answer to why was the limitation here right the auto communication is pretty heavy right here within a node that's pretty good and media has M link across the node we have m switch but communication every in January is very expensive and the other limitation is actually。

What is the max amount of terrorism we can have？For sequence， you can have a limited amount of。

like segments， but for the hass you have a limited amount of hass 32 hass 16 hass it has like that's the limitation you can have the max amount of heroism you have is limited by the number of attention hass in the model。

 which is a fixed number after the model is trained。So that's the Osses approach。

And let me introduce the second solution， which is also quite popular called the R attention in Google's paper I mentioned this。

 Berkeley paper also mentioned this it's a pretty powerful approach。



![](img/3c11e41698f0868314a0cef338e9d65e_373.png)

So we want to communicate such that the GPU1s sequence can also attend to GPU 2。

 GPU1 also want to see GPU 3。

![](img/3c11e41698f0868314a0cef338e9d65e_375.png)

Right， so。What does it remind you of？The ring are reduce right， the ring are reduce。

 so you have a ring， GPU1，2，3， GP1，2，3， form circle right here。



![](img/3c11e41698f0868314a0cef338e9d65e_377.png)

![](img/3c11e41698f0868314a0cef338e9d65e_378.png)

In the first cycle。Okay， we just rotated by one third。Such that we can communicate between。



![](img/3c11e41698f0868314a0cef338e9d65e_380.png)

GPU 1 and2， such that we we are no longer computing only the diagonal， but also attending。

Between the first first third and the second third of the document okay so this is the first third of the document previously on GPU1 now GPU1 GPU2 switched and see here previously is one23 now is switched and becomes312 so the second third of the of the sequence。

 second third of the sequence now reside on GPU1 okay so still within GPU1， we are do the attention。

 but now we are attending the blue document with the green one okay the first third with the second third。



![](img/3c11e41698f0868314a0cef338e9d65e_382.png)

![](img/3c11e41698f0868314a0cef338e9d65e_383.png)

In another cycle， we rotated one more time such that GPU1 the query will be multiplied with the orange document。

 the last third of the document Okay so we computed the attention in this corner。



![](img/3c11e41698f0868314a0cef338e9d65e_385.png)

Okay so we put it together previously， we only have the diagonal part。

 which the blue document attend to blue document， the first third attend to the first third。



![](img/3c11e41698f0868314a0cef338e9d65e_387.png)

![](img/3c11e41698f0868314a0cef338e9d65e_388.png)

Now the first third attend to the second third。And then the first， and third。

 attend to the last third of the documents。So now we complete。The whole attention process。

So previously a lot of places are white， meaning the attention has not been computed now we filled in the white with color。

 meaning that we have computed。And in another cycle， we field in everything computing。

So that's the real attention using real attention to perform sequence parallel in this way it's not limited by the number of hass as the max amount of parallelism we can have。

 but this can effectively attend increase the content now during training and inference。

走光 interesting花。IsRecently we've been combining these two methods， one is the woods method。

 the repetitioning intention layers versus this ring attention into a 2D parallel by combining them。

Sinceing within a node。8th GPUs has higher bandwidth of communication bandwidth compared with between the node。

So between the node， we can use ring attention。Within a node， we can use this all method。Okay。

 so in that way we can effectively perform 2D parallel by combining this two parallel method to utilize the heterogeneity between the node versus within a node and that paper is called Long Villa feel free to check it out it's also open source。

All right， and let's move on。To summarize of today's lecture。

 we talked about data parallelism and sequence parallelism。

 they are both splitting the data sequence parallelism is new due to this long context requirement for large language model。

 we also talk about pipeline parallelyms， with the model by layer and also tensor parallelm。

 split the model by tensor。

![](img/3c11e41698f0868314a0cef338e9d65e_390.png)

![](img/3c11e41698f0868314a0cef338e9d65e_391.png)

![](img/3c11e41698f0868314a0cef338e9d65e_392.png)

![](img/3c11e41698f0868314a0cef338e9d65e_393.png)

We also talk about these communication primitives， the reduce the or reduce operation and also this magic ring or reduce and this recursive having or reduce using log n complexity。

We also talk about 0123 and FSDP， which is probably the most popular technique for distributed training in Pytorrch。

And also how to implement pipeline parallelism and also tensor parallelism in the context of large language model。

All right， that's all for today's lecture and we will also release the greetding for lab four。

And for the final project， some of you ask about what is the template for the final project's final report and also the proposal。

 so we use the new Ris template so very standard flagship machine learning conference basic case should include a proposal should include the。

Motivation why do what kind of problem are you trying to solve why do you need to solve that problem and also starting with the abstract just a few few lines probably 10 to 20 lines abstract like the abstract of the paper and then starting with the motivation and also what is your method what is the prior methods what is your method and what is the final result and how does your result compare with the prior art that's roughly the template of the final report and for the proposal you can just remove the results section and then that is the proposal if you have any questions feel free to come to our office hour and we'd love to help you okay。

All right， that's all for todays lecture。 Thank you。



![](img/3c11e41698f0868314a0cef338e9d65e_395.png)