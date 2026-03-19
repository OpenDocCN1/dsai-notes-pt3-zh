# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p31 P31 Lecture 19 - Distributed Training Part 1 -BV1o7jzzwEST_p31-

All right， good afternoon everyone， let's get started。

 so today we are going to start a new chapter about distributed training。

So in the first two part of the lecture， as first gave a quick review。

 we learn about how to accelerate inference， right inference techniques， general purpose techniques。

 domain specific techniques， including improving quantization， neural architecture search。

 distillation， for large language models for diffusion models for video models， etc。

So from today we are going to start a new chapter about training。

 how to make training faster if you in the country a model is too slow to train。

 hopefully we'll teach you some techniques to make your training faster。

So this is an agenda for today， we'll start with background and motivation why we need distributed training and we'll cover several techniques about parallellyzization。

Including data parism， model parism， pipeline paradigm， sequence parism。

A modeldel parism is also called a tensor par。AndIn particular， for data parallelism。

 we'll talk about。Several sharding methods0， one，2。

3 and fully sharded distributed FSDP parallelism FSDP techniques。

 okay fully sharded distributed parallel， okay data parallel so let's start with background and motivation。



![](img/209ed443c4853f48f00587bb925ce6ae_1.png)

So these models are usually coming at a very high cost of training， so the higher the accuracy。

 the more max we need。

![](img/209ed443c4853f48f00587bb925ce6ae_3.png)

Hey， the normalms we need。To train this GP model， GT3 model require 3 million GPU hours。

 which is too slow to train if you have a single GPU， so we need multiple GPUs to make it faster。

So this is showing how long it takes to train a model like from Re than 50 to bird based to an NLG。

 GT3， particularly for GPT3， Y 75 billion parameter is a huge amount of GP hours if you have a single GPU that will take 355 years to train the model。

 which is too slow。

![](img/209ed443c4853f48f00587bb925ce6ae_5.png)

![](img/209ed443c4853f48f00587bb925ce6ae_6.png)

And these numbers are measured NV a 100 GPU。So the boss ask you， what did you do over the last month？

And the answer is train the model for one ipoC。Pa asked fine。

 what's their plan for the next month and answer train train the model for one more ipoC so that greatly limits the productivity of our designers which machine learning。

Practitioners， right so we want to make the model train faster。

So we want to use multiple GPUs just to buy multiple GPUs to do that， for example。

 if training task take 10 GPU， a single GPU 10 days， 10 GPU days， if you have 1024 GPUs。

 thatll take only 14 minutes， 14 minutes over just a cup of coffee。



![](img/209ed443c4853f48f00587bb925ce6ae_8.png)

![](img/209ed443c4853f48f00587bb925ce6ae_9.png)

So this kind of technique can greatly speed up our research and development cycle。

So let's see a real use case that our lab did for distributed training a couple of years ago。

 so we exploit this summit supercomputer， it has many V100 core pretty big at that time we trained over 1000 GPUs at that time H GPU is v 100 that's already2 or three generations ago V 100 and the A100 and the H100 and now B100 is coming at that time it has 200 gigabit per second in Vi band now you can easily get 400 gigabit per second after this was in 2019 this was in 2019 so only four years there's tremendous development this tremendous improvement from NV for the GPU family so this is at that time we trained this video model video understanding module and per shift module over 606 hours of video which is。



![](img/209ed443c4853f48f00587bb925ce6ae_11.png)

![](img/209ed443c4853f48f00587bb925ce6ae_12.png)

Considered a small amount these days， but at that time it was considered a pretty big amount。

So with only one node， six GPUs that take 49 hours， roughly two days。



![](img/209ed443c4853f48f00587bb925ce6ae_14.png)

And with 128 knows that 700 GPUs， 228 minutes with 1，536 GPUs will shorten that to 14 minutes。

That's 211 times faster， so theoretically it should be 256 times faster。

 so the accuracy is well maintained。

![](img/209ed443c4853f48f00587bb925ce6ae_16.png)

So we've talked about temporal shift module just to shift the channels across different frames to enable temporal modeling。

 which is a good replacement of 3D convolution that is much more computationally efficient。



![](img/209ed443c4853f48f00587bb925ce6ae_18.png)

So this is just showing by utilizing more GPUs by buying more GPU so we can shorten the design cycle1 day from two days to 14 minutes。



![](img/209ed443c4853f48f00587bb925ce6ae_20.png)

Okay， so let's dive deeper into how do we achieve that。

 given distributed training can be so helpful to shorten the design cycle。

 let's see how do we paralyze and how do we exploit so many GPUs。

 say you have budget to buy like 100 GPUs， how to program them， how to exploit them。

So let's talk about parallellyization techniques in the following four aspects。

 one is data parallelism。

![](img/209ed443c4853f48f00587bb925ce6ae_22.png)

呃 pipeline parism。Pcer parasal and sequence parallelsal。

So this sequence parallelism is a new content we added this year in last year and the year before last year we don't have this content this is new given the fast development of long sequence。

 long contacts， large language model。

![](img/209ed443c4853f48f00587bb925ce6ae_24.png)

Like well a video can be one hour an hour long video in 1080 peak can easily exceed 100 million tokens right a whole series of Harry Potter book is a medium tokens so how to parallelze them across the sequence dimension is also very crucial so we added this new chapter。

So let's first look at the data parallel。

![](img/209ed443c4853f48f00587bb925ce6ae_26.png)

Imagine we have a different learning model， we have a lot of training data。

 one idea is to distribute across different parts of the data， like we have three part， blue part。

 the green part， the orange part， and then we paralyze the yellow the blue part to GPU1。

 the green part to GPU2 and orange part to GPUN。

![](img/209ed443c4853f48f00587bb925ce6ae_28.png)

So we are splitting， splitting the trading data to multiple GPUs， splitting the data。

A and each GPU are sharing a the same model。The city model across different GPUus。

 So that data parallel。 we are partitioning the data。 We are sharing the model。

And the second technique， we can partition the model。



![](img/209ed443c4853f48f00587bb925ce6ae_30.png)

哎，相应的 datata。Aration the model in M parts。In the pipeline manner。

 but they are sharing the same training data set， sharing the same training data set。



![](img/209ed443c4853f48f00587bb925ce6ae_32.png)

So we have a single copy of data。But we are partitioning， splitting the model on GPU1， GPU 2。

 GPUN are processing different layers of the model。And next is the Tensor parallelm。

We can partition in another dimension， okay we are also partitioning the model。

 but not from the layer dimension， but within the layer we are partitioning a different part of the matrix multiplication across different GPUus。



![](img/209ed443c4853f48f00587bb925ce6ae_34.png)

There are partition in the activations， the first， a third， next third， the last。

 a third of the activation is fed to different GPUs。



![](img/209ed443c4853f48f00587bb925ce6ae_36.png)

And in this case， GPU1 is responsible for the first third of the activation。

And then we can continue the same way for different layers。

And so this is also sharing the same training data。

 but we are partitioning across different activation for the model。For example。

 if you have a big matrix modificationplication like 4K by 4K。

 you can partitioning that by 4K to 4K by 2K and use 2 GPUs process that 4 GPU 4K matrix modification。

Okay， lastly， we have this sequence heroism。Okay， so say we have a long contact。

 long text for training， like three books。

![](img/209ed443c4853f48f00587bb925ce6ae_38.png)

First， we have this batch size dimension。啊，Token dimension， hidden dimension。

哎 so the batch dimension， we can use the data terrorism。Spprinted by the batch。

Like three books with splited and use only train one book on one GQ。

And then from the token dimension， the token is too long。

 like the book can have like tens of thousands of tokens。



![](img/209ed443c4853f48f00587bb925ce6ae_40.png)

![](img/209ed443c4853f48f00587bb925ce6ae_41.png)

So we can exploit sequence carrier， a long sequence， we can split it into several shorter sequence。

You can split the tokens， just like this book， we have three chapters。

 you can see chapter one to GPU1， chapter two to GPU2， chapter 3 to GPU3。Just like this。



![](img/209ed443c4853f48f00587bb925ce6ae_43.png)

so each GPU is responsible for all all the entire model。

 the model is not each GPU has the whole model， but it's only responsible for processing a part of the sequence part of the sequence since the total sequence too long each GPU just process part of it so that sequence par。

Okay， so this is a quick overview of the four different parallelization approaches。

 and now we are going to dive deeper into each parallelization approach and see how to implement film。



![](img/209ed443c4853f48f00587bb925ce6ae_45.png)

![](img/209ed443c4853f48f00587bb925ce6ae_46.png)

So we are going to start with data parallelism， communication primitives， zero and FSDP。

 so these are all related to data parallelism。

![](img/209ed443c4853f48f00587bb925ce6ae_48.png)

Next， we're going to talk about pipeline parallelism。

And then tensor parallel followed by sequence parallels to cover all the four priorization techniques。



![](img/209ed443c4853f48f00587bb925ce6ae_50.png)

He， really， let's go with the data horizon。

![](img/209ed443c4853f48f00587bb925ce6ae_52.png)

So let's first introduce a method called using a parameter server。

 okay so we can scale the distributed training with parameter server。



![](img/209ed443c4853f48f00587bb925ce6ae_54.png)

So this is a centralized approach， not quite widely used anymore。

 but let me start by introducing the basics。

![](img/209ed443c4853f48f00587bb925ce6ae_56.png)

So there is a central controller of the whole training process and then we have many worker node in this case we have four workers。

 the parameter server or receive the gradient from the workers and send back the aggregated results。



![](img/209ed443c4853f48f00587bb925ce6ae_58.png)

And each worker will receive a part of the training data， split training data。

And then update and calculate the gradient and send the gradient to the parameter server。



![](img/209ed443c4853f48f00587bb925ce6ae_60.png)

So put it another way， we have a neuralNe model， we have a gradient in the parameter server。

 and we have pool of worker node。Including the gradient。

 the local replica of the neuralnaal model and the training data and the training data is splitted from the entire training data set and we split it into four parts。

 each GPU is responsible for one part。

![](img/209ed443c4853f48f00587bb925ce6ae_62.png)

To begin with。The parameter server will replicate。

![](img/209ed443c4853f48f00587bb925ce6ae_64.png)

Replate the model。And each worker will pool。The model from the parameter server， Okay。

 so four workers， each will pull the model from the worker。



![](img/209ed443c4853f48f00587bb925ce6ae_66.png)

![](img/209ed443c4853f48f00587bb925ce6ae_67.png)

And then it will also split the data set randomly but evenly。



![](img/209ed443c4853f48f00587bb925ce6ae_69.png)

Across four workers。And we have the weight， we have we have the data。

 then each worker will calculate the local grid on that piece of training data。



![](img/209ed443c4853f48f00587bb925ce6ae_71.png)

Over that local replica of the model。So the question is， are the four local gradients the same？No。

 they are not the same because they're using the same model。

 but they're using different pieces of training data， which is randomly splited。



![](img/209ed443c4853f48f00587bb925ce6ae_73.png)

Okay， so they each have a copy of local greetings。What they do is they push。



![](img/209ed443c4853f48f00587bb925ce6ae_75.png)

The local gradient will sum them up。

![](img/209ed443c4853f48f00587bb925ce6ae_77.png)

To the prime test server。Okay so we'm going to have the problem server right here。



![](img/209ed443c4853f48f00587bb925ce6ae_79.png)

And the primary server is responsible for updating the neuralnaural model with。



![](img/209ed443c4853f48f00587bb925ce6ae_81.png)

A gradient。

![](img/209ed443c4853f48f00587bb925ce6ae_83.png)

So now。So。Prirameter server will replicate。And pull each worker will replicate and pull the updated model。

To update this local copy， otherwise， this local replica will will be still。

 now it's going to be replicate a new model。

![](img/209ed443c4853f48f00587bb925ce6ae_85.png)

And then repeat this process to pull the model， split the data， calculate the local gradient。

 send it to the primary server， primary server， update the model， and then each worker pull it again。



![](img/209ed443c4853f48f00587bb925ce6ae_87.png)

So if we see the difference between single node training versus distributed training。

 previously each iteration with sample the data， calculate the gradient。

 form a step to update the weight。Now we add this part to pull the gradient from the printer server and then it's the same sample the data。

 calculate the gradient and we added another part here to push the gradient to the printer server。

And some sum it up and then Prime Minister will perform this good news stamp。



![](img/209ed443c4853f48f00587bb925ce6ae_89.png)

![](img/209ed443c4853f48f00587bb925ce6ae_90.png)

So there are actually two synchronization steps here in the red。



![](img/209ed443c4853f48f00587bb925ce6ae_92.png)

Okay so make sure each server， each worker is synchronized。So synchronization has overhead。

 is not free， so let's talk about these communication primitives and see how can we save this communication overhead。

So there are a couple of communication primitives when you come to send and receive data。

In the forward network across different node， so a simple one simple one is send and receive okay so we have several nodes we can send from node zero to node3 this is receiving from node3 to node zero okay so this is one to one communication transferring data from one to another。



![](img/209ed443c4853f48f00587bb925ce6ae_94.png)

![](img/209ed443c4853f48f00587bb925ce6ae_95.png)

![](img/209ed443c4853f48f00587bb925ce6ae_96.png)

And then we have one too many scatter and gather。Okay。

 so scatter basically send a attention to all the other workers。And so tensor's four components。

 it was send it to0，1，2，3。 So this is one， too many， one， too many。

And gather is basically the reverse money to one， then we gather the beta from worker0， worker one。

 worker2， worker3， and gather everything into worker zero。



![](img/209ed443c4853f48f00587bb925ce6ae_98.png)

To receive the ten from all other workers is taught is many to one versus scatterer is sending the data to many servers。

 one too many。

![](img/209ed443c4853f48f00587bb925ce6ae_100.png)

![](img/209ed443c4853f48f00587bb925ce6ae_101.png)

Another one for many is actually reduce and also reduce。



![](img/209ed443c4853f48f00587bb925ce6ae_103.png)

It's very similar to together， but it's different， so gather basically only gather all the data。

 but reduce will do another operation， which sum made up。Or。Finding the sum。

 finding the max is going to do a reduced operation after the gather operation。

 So you can think of reduce operation as。The gather operation followed by a reduction operation。

 so if you sum them up， then that's reduce， if you don't sum it up， leave it at this。

 then it's gather。

![](img/209ed443c4853f48f00587bb925ce6ae_105.png)

![](img/209ed443c4853f48f00587bb925ce6ae_106.png)

There's also another one too many operation called broadcast。

 so broadcast one tensor to all the workers。

![](img/209ed443c4853f48f00587bb925ce6ae_108.png)

![](img/209ed443c4853f48f00587bb925ce6ae_109.png)

Broadcast is actually different from scatter。So Ser is going to send tensor。

 different parts of the tensor to different workers and different workers will receive different piece of data。



![](img/209ed443c4853f48f00587bb925ce6ae_111.png)

But broadcast。

![](img/209ed443c4853f48f00587bb925ce6ae_113.png)

Will send identical copies of data。

![](img/209ed443c4853f48f00587bb925ce6ae_115.png)

To other the other workers， that' the difference between broadcast versus scatter。



![](img/209ed443c4853f48f00587bb925ce6ae_117.png)

Finally， we have this many many too many operation。



![](img/209ed443c4853f48f00587bb925ce6ae_119.png)

So this is our reduce， this is all， so our reduce will perform a reduce operation on all the workers。

 so if you look at our reduce versus reduce reduce is basically working on one receiver。



![](img/209ed443c4853f48f00587bb925ce6ae_121.png)

But for all reduce， you performing reduce on all the workers， reduce on zero， reduce on one。

 two three， okay。And similarly， for the all gather operation is to perform together on all the workers gather on worker zero。

 gather from worker one， gather on worker two， gather on work three。



![](img/209ed443c4853f48f00587bb925ce6ae_123.png)

So that's the relationship between reduce， gather or reduce and all together。



![](img/209ed443c4853f48f00587bb925ce6ae_125.png)

So this is reduced。This is together。

![](img/209ed443c4853f48f00587bb925ce6ae_127.png)

Operating on one receiver， operating on one receiver。

But running too many it's operating on many receivers，They share some seasonal properties。

So let's see， how do we use those communication primitives？In the parameter server setting。



![](img/209ed443c4853f48f00587bb925ce6ae_129.png)

So we just talk about primary Minister server， and then we have many workers。

 they have a different replica of the training data。



![](img/209ed443c4853f48f00587bb925ce6ae_131.png)

So which type of communication scheme is used when we are replicating？



![](img/209ed443c4853f48f00587bb925ce6ae_133.png)

In the blue part。Versus the orange part when we are pushing and suming the ingredients。



![](img/209ed443c4853f48f00587bb925ce6ae_135.png)

So we have all reduce， all gather， reduce， broadcast， scatter， scatter， gather， send and receive。

During the orange and blue operation， which operation which。Communication primitive are we using？



![](img/209ed443c4853f48f00587bb925ce6ae_137.png)

Yeah， so the broadcast is used for replicating and pool right so we have our central private server and we want to broadcast the weight to all the workers。

And for pushion sum is reduced and so we averaging from all the workers。

 other worker get its own gradient and we want to sum the gradient in the present server so it's actually reduced。

 it's not only gather it need to also perform a reduction so it's reduced。



![](img/209ed443c4853f48f00587bb925ce6ae_139.png)

So what is the bottleneck here， what is the bandwidth requirement to do this？

SoRe and pull each worker is O one。 You just need to pull one copy of data。



![](img/209ed443c4853f48f00587bb925ce6ae_141.png)

But for for the parameter server， the bandwidth is ON。Because you have N workers。

So the replicate and the pool will will take ON。Communication complexity。For the push。

 each worker just need to push its own copy of grade。 So that's O one。Buts all prime Minister Ser。

And to receive n copies so。

![](img/209ed443c4853f48f00587bb925ce6ae_143.png)

The complex is all。

![](img/209ed443c4853f48f00587bb925ce6ae_145.png)

So it's actually pretty heavy， right， for the primary server， the networking traffic。



![](img/209ed443c4853f48f00587bb925ce6ae_147.png)

It's O， it's not quite scalable， the more worker you have。

 the larger the bandwidth requirement is needed。

![](img/209ed443c4853f48f00587bb925ce6ae_149.png)

So the bandwidth of the central parameter server will grow linearly。



![](img/209ed443c4853f48f00587bb925ce6ae_151.png)

With the amount of workers， which can be a bottleneck。When you have a lot of machines。

So a natural thinking is， can we make it more scalable by getting rid of this centralized parameter server and make everything decentralized without a parameter server？

Of course， we can do that by using this or reduce operation。

To get rid of is centralized the parameter server。How do we do that？



![](img/209ed443c4853f48f00587bb925ce6ae_153.png)

So we start with naive on reducing implementation。

![](img/209ed443c4853f48f00587bb925ce6ae_155.png)

A using in a sequential way。So each GPU will calculate its local gradient on its of own piece of data。

 right？

![](img/209ed443c4853f48f00587bb925ce6ae_157.png)

And now we perform or reduce on our node。 Okay， so reduce on node0。 Okay reduce on note 1。

 reduceuce on note 2， reduce on note 3。 So each node， each worker will do a。



![](img/209ed443c4853f48f00587bb925ce6ae_159.png)

![](img/209ed443c4853f48f00587bb925ce6ae_160.png)

Gather and then reduction to combine。

![](img/209ed443c4853f48f00587bb925ce6ae_162.png)

All the greetings together。Although the calculation has some redundancy。

 they are all calculating the sum of this。

![](img/209ed443c4853f48f00587bb925ce6ae_164.png)

![](img/209ed443c4853f48f00587bb925ce6ae_165.png)

Green， yellow， blue， and red， right？

![](img/209ed443c4853f48f00587bb925ce6ae_167.png)

So what is the time complexity， actually that's on sequentially doing the reduce。



![](img/209ed443c4853f48f00587bb925ce6ae_169.png)

Reduction， okay， so time is on。 What about the bandwidth。



![](img/209ed443c4853f48f00587bb925ce6ae_171.png)

It's also because each worker requires receiving the data from all the other workers。

 so both the time and bandwidth is all， which is not good。



![](img/209ed443c4853f48f00587bb925ce6ae_173.png)

So can we do better？So we can do this a better ring reduce operation by using this ring or reduce and what does that look like？



![](img/209ed443c4853f48f00587bb925ce6ae_175.png)

So it's that one。Work her zero。Send the gradient to worker one， worker one， send it to worker2。

 worker2， send it to worker 3， worker 3， send it to worker 0。 Okay， so at this moment。

 worker 0 has data are both from itself and also from worker 3。Okay， so Worlder one。

Can have the data can have the gradient both from worker one and worker zero since worker zero is sending to worker one。

 worker one previously already have this yellow data。

 so now it has both the yellow data and on the green data。So that's the first step。

And the second step， we do the same worker zero。Send data to worker one。

 such that worker one has both the green， the yellow， and also the red。It is red ands green。

 it has yellow。And worker one send its greeting to worker2。Such that more code4 will have。

The orange the the yellow， the blue， and also the green， the green comes from lower one。

And we do the same for two two three， three to zero。



![](img/209ed443c4853f48f00587bb925ce6ae_177.png)

In a real manner， so everyone just sending to his neighbor。



![](img/209ed443c4853f48f00587bb925ce6ae_179.png)

And after step  three，0， center one，1 and2， so that worker one has data from the red， the the green。

 the yellow， and also the blue。 so now it has all the data。有没。

And similar things happens for all the other notes， they each have the green， the orange， the yellow。

 the blue and the red。

![](img/209ed443c4853f48f00587bb925ce6ae_181.png)

So only in four steps。And we have all the data。So the time is still on。



![](img/209ed443c4853f48f00587bb925ce6ae_183.png)

Since we have four node， we require three steps， so time is still O， but bandwidth， it's only01。



![](img/209ed443c4853f48f00587bb925ce6ae_185.png)

We only need to communicate with our neighbor， so there's no very little bandwidth needed right here。

Remember previously the primary server， the centralized primary server requires ON bandwidth now everything is all what so that's good we made some progress by using this ring or reduce。



![](img/209ed443c4853f48f00587bb925ce6ae_187.png)

![](img/209ed443c4853f48f00587bb925ce6ae_188.png)

Can we do even better？ There is still some redundant computation， right， Can we do even better。Okay。

 so before looking at it more advance， let's look at now or reduced implementation， parallel reduce。

So previously， we talk about sequential or reduce of four steps for four workers。



![](img/209ed443c4853f48f00587bb925ce6ae_190.png)

We can do all everything in parallel at the same time， worker zero is doing a reduce worker one。

 worker two， worker3， they are all doing the reduce， okay， so we only only need0 one time。

Since it's not special， it its parallel。 However， the bandwidth of its O N square。 So all the。

Each arrow everything is happening at the same time， so we have n， we have n。

 so we have ON square communication happening in the middle。

 so the time is pretty short but the bandwidth is too large。



![](img/209ed443c4853f48f00587bb925ce6ae_192.png)

![](img/209ed443c4853f48f00587bb925ce6ae_193.png)

Compared with this ring or reduce， we need ON time， time is large， but bandwidth is small。



![](img/209ed443c4853f48f00587bb925ce6ae_195.png)

So can we have even better solution。Sumaries so far， we talk about parameter server， for one time。



![](img/209ed443c4853f48f00587bb925ce6ae_197.png)

But peak node bandwidth is O N， total bandwidth O。Sequential or reduce。

I is O N signal note bandwidth O N， total bandwidth is also O N。For all reduce using a ring manner。

 the peak note bandwidth is reduced to O1 since I only need to communicate with my neighbor。

Total bandwidth is still on， since have to do that for n times。Andter or reduce time is01。

 which is pretty good。 but peak node bandwidth is O N for each node。

 The total bandwidth is O N square。

![](img/209ed443c4853f48f00587bb925ce6ae_199.png)

But now we want to combine the advantage of the ring and parallel or reduce or ring or reduce combined with parallel or reduce and let's see how do we further reduce the bandwidth in time。

Okay， so now the example gets a little more complicated， so let's use eight。



![](img/209ed443c4853f48f00587bb925ce6ae_201.png)

Eight notes in this example okay so。

![](img/209ed443c4853f48f00587bb925ce6ae_203.png)

In the first cycle， we will combine the data from adjacent node。



![](img/209ed443c4853f48f00587bb925ce6ae_205.png)

With neighbors with outside of one， that' adjacent know。So one combined with two， two with three。

 or sorry， three with four， five with six， seven with eight。



![](img/209ed443c4853f48f00587bb925ce6ae_207.png)

![](img/209ed443c4853f48f00587bb925ce6ae_208.png)

And as a result， node one has both the green and red。No two also have green and red。

 no three has this blue and orange。

![](img/209ed443c4853f48f00587bb925ce6ae_210.png)

一直在传。So just after one cycle， everybody communicated with its neighbor with offset one。Step two。

 each node will exchange with neighbors with offset two。



![](img/209ed443c4853f48f00587bb925ce6ae_212.png)

Okay， so node one will communicate with node。Through。And no three will communicate with node the one。

 no two will communicate with node the four。Okay， so this is one group and the other group。

 node five will communicate with node7 and six with eight。And as a result。

You can see we are already making some progress， everything on the left。

 we already have all four colors， everything on the right， already has all the four colors。

 so we can do one more iteration to complete this we can complete this job。



![](img/209ed443c4853f48f00587bb925ce6ae_214.png)

So let's your printstorm。How should we do next， what should we communicate？

In the next step so that everybody has。Bate colors。With a larger offset。

 first one left one or first one with a fifth one。Right。So， if we。Exge。



![](img/209ed443c4853f48f00587bb925ce6ae_216.png)

The node with neighbors of outside four。Then the first node and the fifth node。

That we'll communicate with each other right and second one with a sixth one。



![](img/209ed443c4853f48f00587bb925ce6ae_218.png)

One other result。This one will have also this color。

 so all the eight colors for each node will have all the eight colors， right？

And then we complete this process and how many cycles did we take？Actually， we have eight node。

 but only three cycles。Okay， after three cycles， every node has the data from everybody else。

So only log N steps rather than or N step， which is much faster。

So this is called re recursive havinglving or reduce。

People also call it butterfly or reduce because this structure looks like a butterfly。

 but not exactly。Which is for end workers， all reduce can finish within log gain steps。

So this is much widely used technique compared with a parameter server， like in our lab。

 we do a lot of distributed training but we don't use a centralized parameter server。

 instead we use this or reduce method。Okay。Okay， so now let's switch gear to continue talk about data parallelism to reduce the memory using the zero。

 one，2 three and distributed fully sharded data parallelm before that let's take a quick break。



![](img/209ed443c4853f48f00587bb925ce6ae_220.png)

![](img/209ed443c4853f48f00587bb925ce6ae_221.png)

Or five minutes。All right， welcome back。Let's continue a discussion about zero and FSDP。

 so zero is actually a very popular technique for large training large language model these days。

 it stands for。Zero redundancy optimizer， so let's see how that works。



![](img/209ed443c4853f48f00587bb925ce6ae_223.png)

So recently the large language model is pretty big， like GP3 is 175 as 175 billion parameters。



![](img/209ed443c4853f48f00587bb925ce6ae_225.png)

If we train it even in after year 16。

![](img/209ed443c4853f48f00587bb925ce6ae_227.png)

So just to hold those weight， how much memory do we need？

We need 350 gigabyte of memory just to hold the weight， not to mention the activations， the gradient。

 the optimizer state。

![](img/209ed443c4853f48f00587bb925ce6ae_229.png)

![](img/209ed443c4853f48f00587bb925ce6ae_230.png)

Well， a 100 GPU or H100 GPU has 80 gigabyte of memory， B100 is getting larger。

 but still less than 200。

![](img/209ed443c4853f48f00587bb925ce6ae_232.png)

Right so even best GPU可能 feed the models to wait into memory。



![](img/209ed443c4853f48f00587bb925ce6ae_234.png)

So how do we solve that problem using limited GPU memory to train big model？

So let's first break down。What is the memory consumption to train a single parameter？



![](img/209ed443c4853f48f00587bb925ce6ae_236.png)

OkaySo we can break down into three components， the weight， two bytes per weight。

 assuming's FP 16 training， which is already pretty popular these days， ingredient2 bytes FP 16。

We also have to store those optimizer states。Including three part。

One is a FP 32 copy of the parameter。 So the weight requires a master copy。

 a full precision master copy for the accumulation。 So that's4 bytes。



![](img/209ed443c4853f48f00587bb925ce6ae_238.png)

We need another two numbers for the optimizer state， if you need to use the item optimizer。

 you need to store both the first order and second order momentum。

The two momentum require two number and the master copy of the weight is another number。

 so altogether we need three numbers。

![](img/209ed443c4853f48f00587bb925ce6ae_240.png)

EveryEvery number is four bytes， so you need altogether 12 bytes for the optimizer states okay so this optimizer state this is the gradient。

 this is the weight and so optimizer state actually occupies a pretty large portion of the total total memory。



![](img/209ed443c4853f48f00587bb925ce6ae_242.png)

So。

![](img/209ed443c4853f48f00587bb925ce6ae_244.png)

This is the total sum， summing up the weight， the gradient ultimately state。Altogether。

 you need 16 bytes。To store or to train for each parameter。

And so we can calculate if we do the training naively。

 how many parameter can you train on a 80 gigabyte of memory。Even not to mention the activation。

So 16 bytes。For each parametermeter。We can train only  five billion parameter model。

 even not even a Lama 27b， so only  five billion parameters。

 which is far away from the current state of the art。



![](img/209ed443c4853f48f00587bb925ce6ae_246.png)

So how can we do better？So previously we are havingco of the weight gradient of the optimizer state across each GPU since we are doing data H。

They are processing different data， splitting the data， but they are sharing the model。

 So each GPU has the same， same copy。Zero1 basically proposed we can partition or we call it sh the optimizer state。



![](img/209ed443c4853f48f00587bb925ce6ae_248.png)

So since we have N GPPUs， we don't need to store a we can still only store the local copy。For each。



![](img/209ed443c4853f48f00587bb925ce6ae_250.png)

For each of them， rather than storing and copies of them。



![](img/209ed443c4853f48f00587bb925ce6ae_252.png)

So if we have nPs， we no longer need to store 12。By it's each， but we can store a 122 body button。

 so we are sharding the optimizer state。If we have N equal 64。



![](img/209ed443c4853f48f00587bb925ce6ae_254.png)

We put an equal to 64 right here。Each parameter require only 4。2。



![](img/209ed443c4853f48f00587bb925ce6ae_256.png)

And we can feed 19 Bs。A 19 billion parameter in a single 80 gigabyte of GPU。So that's  zero one。

Zero2 is more aggressive。

![](img/209ed443c4853f48f00587bb925ce6ae_258.png)

Okay， zero stands for zero redundancy optimizer， so zero two also shard。

Not only the optimizer states， but also the gradient。So the gradient。

 so the gradient is also2 divided by M。上的 gradient as well。So each parameterer requires 2。2 bytes。

To train an 8 gigabyte of memory can train a 36 billion parameter model， so that's much bigger。

So this's already pretty big。Zero， three。Is an even more aggressive approach by sh not only the optimizer state。

 the gradient， but also the weight。

![](img/209ed443c4853f48f00587bb925ce6ae_260.png)

so each server no longer have the whole copy。The entire copy of the weight。

 it only have one over n of the weight。 So the weight is also sharded。

 splited partisitioned across N GPUus， so。The total number parameter啊 totalt number byte。no。

Becomes 0。25， right？For 80 gigabyte of memory and I'll hit 320 billion parameters。

 so that's a lot larger。So this is the widely used approach。

To train these large language models okay， so we shard the weight。

 shard the activity shard the optimizer state， shard the gradient and also shard the weight。

Across the GPUs， so you can increase。The twinable prime from。

Just maybe five billion parameters all the way to 300 per billion parameters。

Okay so in Pytorch this 03 is the algorithm proposed by Microsoft is implemented by fully sharded data Para okay it's known as FSTP very widely used library these days。

 feel free to try it out。So for large language models。Be like 70 billion parameterter。

 it's pretty safe to use this approach to train it。Okay。

 so that's the zero and FSDP now let's switch gear to talk about pipeline parallelism okay remember we have four parallelism to talk about one is data parallelism including communication primitives and sharding and pipeline parallelism transfer parallelism and and sequence parallel。

 now let's switch gear to talk about second part which is pipeline parallelism。



![](img/209ed443c4853f48f00587bb925ce6ae_262.png)

![](img/209ed443c4853f48f00587bb925ce6ae_263.png)

So for data parallelism， what are we splitting， where are splitting the data？Sharing the weight。

 Now we are splitter data。

![](img/209ed443c4853f48f00587bb925ce6ae_265.png)

Instead of spliting the data， we want to split the model， okay， so the model may have many layers。



![](img/209ed443c4853f48f00587bb925ce6ae_267.png)

We can put each layer on one worker。What is the good thing about what language model is that？

Different blocks， different layers are identical。Identical number of hidden size。

 identical number of heads。So each parallel pipeline stage are exactly taking exactly the same time。

 so which is very suitable。For pipeline heroism。If we split， it's 300。



![](img/209ed443c4853f48f00587bb925ce6ae_269.png)

50 gigabte across。E card， so each card required only 43。75 gigabytes。

 which is smaller than 80 gigabytes。

![](img/209ed443c4853f48f00587bb925ce6ae_271.png)

So this is the money required for the 175 billion prime on weights。

So that's another dimension to fit a larger model within the limited GPU memory。

So now you implementation。

![](img/209ed443c4853f48f00587bb925ce6ae_273.png)

Basically partition the training data flow say we have four different layers forward at 0，1。

23 and backward32，1，0 Okay we need to store the intermediate intermediate。

Activs to calculate the backward and so it's the forward GPU 01，2。

3 and backward 3210 finally we can update。

![](img/209ed443c4853f48f00587bb925ce6ae_275.png)

So the model is splitd into four partition in this way and assigning each partition to one GPU。

And the problem is that if we just process a single batch in this way， GPUs are underutilized。

A lot of idol， a lot of bubbles in this case。So what is the theoretical utilization here？

So only one quarter， 25% utilization。Because most of the time， the GPU is idle。

So what is the best way to do that？So previously we have a big batch now we want to scale it with micro batch pipeline parallelism。



![](img/209ed443c4853f48f00587bb925ce6ae_277.png)

What you're saying is that previously we have like 16 batches now we want to split it into four batch four such four batchges。

So rather than naive parallellyization， now we can make a look like this。So small batch， one， two。

 three， four batchs。And then after GPU0 completes F 00。

 it can handle the data to GPU1 to compute GP F10 and the GPU0 continues to talk。



![](img/209ed443c4853f48f00587bb925ce6ae_279.png)

To compute I 401。 Okay， so in this way， the bubble is a lot less compared with the naive implementation。

So we want to make a computation splitd more fine grid in a fine grade manner。



![](img/209ed443c4853f48f00587bb925ce6ae_281.png)

Previously， 25% utilization now using micro badge， it can improve it to 57%， which is 2。

5 x improvement。

![](img/209ed443c4853f48f00587bb925ce6ae_283.png)

So lesson we learned here is that we want to split the training in a fine green manner。

 so beyond pipeline parallelm to split the model， we also have another degree to split the model。

 which is cancer parallelism to split the model。Okay。

 so further improve the granularity to make a more fine grain。啊。

By partitioning further partition in the model， not just the layer， even for a single layer。

 we want to continue partitioning that。

![](img/209ed443c4853f48f00587bb925ce6ae_285.png)

Say a layer has a two by two by three matrix okay， so we want to， this is a single F layer right。

 a single F layer， we want to partition that into three parts。啊，GP oneGP2GP3。

And each GPU is calculating only one third。Of the matrix。And finally。

 we can get the result in parallel， so partition the model in a more or fine grain manner within a layer。



![](img/209ed443c4853f48f00587bb925ce6ae_287.png)

And that fits perfectly for large language model， so this is the illustration of tensor parallelism in megatra。

So。Including both MLP layer and also the self attention layer。

Here we want to minimize what do we want to minimize， minimize the communication。

 right since compute chip communication is expensive。

So we only need to communicate in F and G in the star in the end。Which dennots this our reduce。

And synchronization operations。Okay， so this is one is。Scattertter one is the or reduce operation。

我先啦，你。Communication only happens in the beginning and also in the end。

And let's see how that works first for the FFN layer。

So we have two FF layers in large language model， okay， one FF layer， a second FFM layer。



![](img/209ed443c4853f48f00587bb925ce6ae_289.png)

We just give an example could be simple one by two metrics this is div， one by two。And two by6。

 which is the weight。Of the first FA layer。We have two GPUs in this case， we split it in this way。

 each GPU hold two by three and two by three two GPUs that's two by six， right？



![](img/209ed443c4853f48f00587bb925ce6ae_291.png)

So we first do a broadcast， okay， broadcast， broadcast the activation to two GPUs， GPU1， GPU2。

 we perform half of the matrix multiplication on each GPU， the other half of the second GPU。

 and we get y1 and y2， okay corresponding to here are y1 and y2。



![](img/209ed443c4853f48f00587bb925ce6ae_293.png)

No communication is needed。Need in here， and then we can directly move to the next section。

In the next section， we are performing the second matrix modification。

 which is of dimension6 by two okay so this is the activation from the previous layer and we have the matrix6 by two six by4。

 right？Now we split it horizontally GPU1， GPU2， GPU1 is responsible the first half。

 GPU2 is responsible for the second half and what we do here is we perform y1 times B1。

Independently with y  two times V2 A， y1 times V1， Y 2 times V 2。

Okay so no communication is needed because one1 is associated with B1， there's nothing to do with B2。

 right？And then we can obtain two intermediate outputs， Z1， which is one by two， Z2 is one by two。

What is the final dimension of？Of the matrix modification， one by two， two by6，6 by two。

 so the result should be one by two， right？But now we are two， we get two， one by two tensors。

So they are partial， partial sum。So we have to sum up the partial sum。

 and now we have to do a communication。 We want to do all reduce operation to sum the up。

U togetherge Z and so corresponding to here， we do all reduce appreciation to some demand。



![](img/209ed443c4853f48f00587bb925ce6ae_295.png)

Into z。So we only need的。A broadcast in the beginning and are reduce in the end and in the middle these two matrix modifications are done in parallel across two GPUs。

 the1 and GPU2 in this case。So two matrix modifications corresponding to the two FFN layer in large language model is perfectly paralyzing。



![](img/209ed443c4853f48f00587bb925ce6ae_297.png)

And let's look at here in the middle of the MLP， we discussed that it doesn't require any communication。

 because it takes。

![](img/209ed443c4853f48f00587bb925ce6ae_299.png)

The first matrix is partitioned vertically， the second is partitioned horizontally and there's no communication is needed in the middle。

And let's see， how do we do that for the attention there？



![](img/209ed443c4853f48f00587bb925ce6ae_301.png)

So this is the self attention with QKV transformation， softmax and then matrix modification。



![](img/209ed443c4853f48f00587bb925ce6ae_303.png)

Two major modifications， finally， followed by a。Output projection A， okay？



![](img/209ed443c4853f48f00587bb925ce6ae_305.png)

So this is the QKV。transformation matrix， a， we have Q K， V O， we have four transformation matrix。

 three for the input， one for the output。 So this is the three transformation for the input。

The hidden dimension is full， so we have two by6， two by6 for Q2 by6 for k for the key and two by two by6 for the value okay。

 the input is two one by two。

![](img/209ed443c4853f48f00587bb925ce6ae_307.png)

One by two， two by six， so that's perfect and match。So what we do here。

 we also split in the split vertically across two GPUs。

 so each GPU is responsible for only half of the hidden dimension。

Actuallyly that's the head dimension and each GPU is responsible for one head， one head。

 this is another head， and we do a broadcast okay so X is broadcasted to GPU1 and GPU2。



![](img/209ed443c4853f48f00587bb925ce6ae_309.png)

And GPPU1 is holding the first half the transformation matrix for Q。

 GPU2 is responsible for the second half of the transformation matrix transformation matrix for the Q similar for the K and similar for the V okay we are broadcasting x in this way。

 so we do the matrix modification one by two two by3， so we get one by3 one by three。



![](img/209ed443c4853f48f00587bb925ce6ae_311.png)

Are responding to the QKB transformation。And next we want to do the attention okay so asq time2 k transpose times v。

 either is a soft max。

![](img/209ed443c4853f48f00587bb925ce6ae_313.png)

![](img/209ed443c4853f48f00587bb925ce6ae_314.png)

So we do。For the first GPU。

![](img/209ed443c4853f48f00587bb925ce6ae_316.png)

Remember right here， the first GPU already has。呃，Q1K1V one second degree还是Q two V two and pay two。

 so we are doing them separately for。Q1， K1 and V1， we can do the QK transpose soft max times V。

Thanks QK transpose soft soft max times V independently as the Q2 so Q K transpose soft max times V。

 they are independent。And then we get y1 and y2 corresponding responding to here。

 well get at y1 and y2。

![](img/209ed443c4853f48f00587bb925ce6ae_318.png)

So far， no communication is needed。And finally， we want to do the output projection remember we have Q K VO4 projection motions now we are talking about the last output projection。



![](img/209ed443c4853f48f00587bb925ce6ae_320.png)

We have y1 and y2 right here and this is the projection matrix， which is6 by2 input is one by6。

 so we split the output projection horizontally such that we can do the B1 with the first half and B2 with the second half。

So yy is multiplied with B1， y2 is multiplied with B2。

 and similar to before we get these two intermediate outputs in Z1 and z2。And finally。

 we do all reduce now we need this operation， this all reduce operation。

 we need this communication right here， we do a communication in the last end together get of Z final Z。



![](img/209ed443c4853f48f00587bb925ce6ae_322.png)

Okay so that's the whole process of splitting in the head dimension for calculating the attention。

And the beauty here is that we only need communication at broadcast in the beginning on the communication which is all reduced in the end right here in June in green。

 and everything in the middle， there's no communication needed across the two GPUs。

 which is why this attention mechanism fits perfectly for multiple GPUs。

 I mean it's so easy to scale it up。

![](img/209ed443c4853f48f00587bb925ce6ae_324.png)

![](img/209ed443c4853f48f00587bb925ce6ae_325.png)

And Michael Chng attributed a huge contribution to scaling up this large language amount of traininging across multiple GPUs。

I don't know if the designer of Transformer actually。Thought about this priorization process。

 but it's very beautiful that no communication is needed in the middle for both the attention and also for the two I layers。

But this is a perfect example for algorithm and system co design。For neural networkural acceleration。

All right， we are。Three quarters in our journey we talk about data parallelism about parallellyzing the data sharing the model。

 we also talk about pipeline parallel and tensor parallelism。

 which is sharing the data and partitioning the model now let's talk about the last one last parallellyzization technique which is sequence parallelism this part of the lecture is new this year don't have that yet in the last year because it is very trending topic for handling long context long context is very crucial for example。

 for natural language processing you want to understand long documents right long documents。

 many books。

![](img/209ed443c4853f48f00587bb925ce6ae_327.png)

![](img/209ed443c4853f48f00587bb925ce6ae_328.png)

Complicated financial report， legal documents， etca。

 long context is also important for video understanding you want to understand the history to know when and what is happening at what time it's also important for robotics to want to have a long trajectory what has happened in the past in order to predict what's going to happen in the future so all that require a lot of tokens tokens are very valuable this context length is also valuable but it's very complicated to train take a lot of GPU memory。

That's why we need sequence parallelism to partition this long sequence。

 this long contexts into multiple GPUs， so one GPU can handle only a limited amount of tokens。Again。

 the rule of thumb is we want to minimize the communication， maximize the utilization。

 and let's see how can we partition that so this is the basic concept say we have a book of three chapters。

 three chapters。

![](img/209ed443c4853f48f00587bb925ce6ae_330.png)

Maybe each chapter is say 10 k tokens， now we have 30 30 k tokens， we put one 10 k for each GPU。

They are sharing the same weight， same model， but different part of the sequence。

 different part of the data。

![](img/209ed443c4853f48f00587bb925ce6ae_332.png)

The question here is that each GPU only has its own piece of data right for the query。

 GPU1 has the first part， GPU2 has second part， GPU3 has the third part。

 similarly for the key and values right， so different GPU only has its own QKV。



![](img/209ed443c4853f48f00587bb925ce6ae_334.png)

![](img/209ed443c4853f48f00587bb925ce6ae_335.png)

However， for the attention mechanism， we need to attend the first part of the document with the second part。

 first part with the third part， second part with the second part， second part with the third part。

 and third part with the third part right so that's n by N matrix which require a lot of communication。



![](img/209ed443c4853f48f00587bb925ce6ae_337.png)

![](img/209ed443c4853f48f00587bb925ce6ae_338.png)

![](img/209ed443c4853f48f00587bb925ce6ae_339.png)

You can just do the attention locally。If you' just without any communication between GPU1 and 23。

 what's going to happen？Everything can only attend locally。 This chapter one will not see chapter 2。

 chapter 3。We not be able to see chapter2 okay， so we cannot mingle the data anymore。

 say you want to cor something happened in chapter2 with chapter3 you cannot do that only chapter three with chapter three。

 chapter2 with chapter 2， chapter one with chapter one， that's too。



![](img/209ed443c4853f48f00587bb925ce6ae_341.png)

Let's see， how do we solve this problem？Okay， I'm going to introduce two methods。

 feel free to come off with third one your final project。

 but solution one is a popular technique called deep speed releases。

Which is very widely used technique these to repartition the data in the attention layer。

 So how do we do that let see。

![](img/209ed443c4853f48f00587bb925ce6ae_343.png)

So this is a QKV transformation matrix， so we have the three tokens just。use that as example， one。

 two， three。And we feed the token1 to GPU1。And so token1 is one by two transformation matrix two by three so the result will be one by three okay one by three for the for the Q。

 one by three for the K， one by3 for the V。Okay， so P2 is responsible for the second part of the token。

 okay， second part of token， the background is in green， okay， background is in green。

And the third GPU is responsible for the third part of the token， the background is in yellow。

And GPPU1，2，3 all share the same QKB transformation matrix。

So by multiplying this two by three matrix with the one by two by two by three。

 we get one by three for the Q and for key and for V think so far so good。

 we are each GPU is responsible for only one third of the tokens only one third of the tokens in different color。

And now we want to do the attention， attention requires。嗯。The firstequ first token。

 first part of the token also attend to the second part， second part， attend to the third part。

And how do we do that， we want to do all to all communication right here Okay。

 so for all the queries， so all the queries are previously in GPU1 are GPU2。

And in GPU3 for the different heads， right we have three heads in this case， we have the light green。

 we have dark green and we have green right so now we want to collect everything related to the。

Dark green into the third GPU， Everything related to the light green in the second GPPU。

 everything in the。We called it normal green in the first GPU right， so each GPU is responsible for。

One part of the head now we are partitioning in the head dimension previously we are partitioning in the sequence dimension and along sequence different parts in blue。

 in green， in yellow right now we are partitioning in the head dimension。

This is head one head two head three in green， height green and dark gray right now were partitioning the in the head dimension so GPUY is responsible for head one。

 everything related into doing so we just collect everything in the first column。

Which is the first the had。Like everything to GPU1。So that we can compute the QKV， the attention。

 the complete attention for all the sequence right so it contains from token1 contains when token2 contains information from token 3 right so everything related to the first head the entire sequence now is in GPU1 everything related to the second head for the entire sequence now is in GPU2 everything in the third head for the entire sequence now is in GPU3 then so we do the attention computation separately。



![](img/209ed443c4853f48f00587bb925ce6ae_345.png)

So in this way， you can see where does the communication happen？Communication happens here。

Right we need to auto all communication okay so previously each GPU has green， light green。

 dark green now GP1 has everything related to green GP2。

 everything related to light green GPU3 everything related to dark green。

 so the number of GPUs equal to the number of partition in the sequences。

And we chop the sequence into three parts， and we have three GPUs。

And also you go to the number of hass in this example， we have three hass。

So what's the limitation of this approach？看。Oh。对对太。对。我不意。我。

Because because you have to first calculate the QKV transformation。

You have to calculate this a matrix modification before calculating the QKV transformation。

And therefore， in the middle， you have to do a communication to exchange the data。

 so everything related to head1 is gathered in GP1。问清楚啊。对。关。that's the exactly case。

 This is GPPU1 only has head one。 GPPU 2 only has everything in head2。



![](img/209ed443c4853f48f00587bb925ce6ae_347.png)

But you cannot have that here。Because here we are partitioning the sequence on different GPUs。

And not here， GPP1 has all the hats， but only related to the first third of the sequence left。

 only first first third。

![](img/209ed443c4853f48f00587bb925ce6ae_349.png)

So that's why we needed such shuffle， yeah。No。Right， exactly。Right。Yes。

 that's the answer to why was the limitation here right the auto communication is pretty heavy right here within a node that's pretty good and media has N link across the node we have N switch but communication every in January is very expensive and the other limitation is actually。

What is the max amount of terrorism we can have？For sequence， you can have a limited amount of。

like segments， but for the hass you have a limited amount of hass 3 two hass 16 hass it has like that's the limitation you can have the max amount of heroism you have is limited by the number of attention hass in the model。

 which is's a fixed number after the model is trained。😊，So that's the Oicesses approach。

And let me introduce the second solution， which is also quite popular for the R attention in Google's paper I mentioned this。

 Berkeley paper also mentioned this it's a pretty powerful approach。



![](img/209ed443c4853f48f00587bb925ce6ae_351.png)

So we want to communicate such that the GPU1 sequence can also attend to GPU 2。

 GPU1 also want to see GPU 3。

![](img/209ed443c4853f48f00587bb925ce6ae_353.png)

喂，苏。WhatWhat does it remind you of？The ring or reduce， right， the ring all reduce。

 so you have a ring， GP1，2，3， GP1，2，3， a form circle right here。



![](img/209ed443c4853f48f00587bb925ce6ae_355.png)

![](img/209ed443c4853f48f00587bb925ce6ae_356.png)

In the first cycle。Okay， we just rotated by one third。Such that。We can communicate between。



![](img/209ed443c4853f48f00587bb925ce6ae_358.png)

GPU 1 and2， such that we we are no longer computing only the diagonal， but also attending。

Between the first first third and the second third of the document okay。

 so this is the first third of the document previous GPU1 now GPU1 GPU2 switched and see here previously is one23 now its switched it becomes312 so the second third of the of the sequence。

 second third of the sequence now reside on GPU1 okay so still within GPU1 we are do the attention。

 but now we are attending the blue document with the green one okay the first third with the second third。



![](img/209ed443c4853f48f00587bb925ce6ae_360.png)

![](img/209ed443c4853f48f00587bb925ce6ae_361.png)

In another cycle， we rotated one more time， such that GPU1 the query will be multiplied with the orange document。

 the last third of the document。

![](img/209ed443c4853f48f00587bb925ce6ae_363.png)

And so we computed the attention in this corner。Okay， so we put it together previously。

 we only have the diagonal part， which the blue document attend to blue blue document。

 the first third attend to the first third。

![](img/209ed443c4853f48f00587bb925ce6ae_365.png)

![](img/209ed443c4853f48f00587bb925ce6ae_366.png)

Now， the first third attend to the second third。And then the first， and third。

 attend to the last third of the documents。So now are we complete。The whole attention process。

So previously a lot of places are white， meaning the attention has not been computed。

 now we filled in the white with color， meaning that we have computed。And in another cycle。

 we field in everything computing。So that's the real attention using real attention to perform sequence parism in this way it's not limited by the number of hass as the max amount of parallelism we can have。

 but this can effectively attend increase the content now during training any inference。

So one interesting part is recently we've been combining these two methods。

 one is the woodesis method， the repetitioning in intention layers versus this ring attention into a 2D parallel by combining them。

Since within a note。8th GPUs has higher bandwidth of communication bandwidth compared with between the node。

So between the node， we can use ring attention。Within a node， we can use this all method。Okay。

 so in that way， we can effectively perform 2D parallelm by combining this two parallelm method to utilize the heterogeneity between the node versus within a node and that paper is called Long Villa。

 feel free to check it out it's also open source。All right， and let's move on。

To summarize of today's lecture we talked about data parallelism and sequence parallelism。

 theyre both splitting the data sequence parallelism is new due to this long context requirement or large language model。

 we also talk about pipeline parallels， split the model by layer and also tensor parallelm split the model by tensor。



![](img/209ed443c4853f48f00587bb925ce6ae_368.png)

![](img/209ed443c4853f48f00587bb925ce6ae_369.png)

We also talk about these communication primitives， the reduce， the or reduce operation。

 and also this magic ring or reduce and this recursive having or reduce using log n complexity。

We also talk about 0123 and FSDP， which is probably the most popular technique for distributed training in Pytorrch。

And also how to implement pipeline parallelism and also tensor parallelism in the context of large language model。

All right， that's all for today's lecture and we will also release the greetding for lab four。

And for the final project， some of you ask about what is the template for the final project's final report and also the proposal so we use the new Ris template so very standard flagship machine learning conference basic case include a proposal should include the。

Motivation do what kind of problem are you trying to solve why do you need to solve that problem and also starting with the abstract just a few few line probably 10 to 20 lines abstract like the abstract of the paper and then starting with the motivation and also what is your method what is the prior methods what is your method and what is the final result and how does your result compare with the prior art that's roughly the template of the final report and for the proposal you can just remove the results section and then that is the proposal if you have any questions feel free to come to our office hour and we'd love to help you okay。

All right， that's all for today lecture。 Thank you。



![](img/209ed443c4853f48f00587bb925ce6ae_371.png)