# 斯坦福大学《计算机视觉的深度学习｜CS231n： Deep Learning for Computer Vision 2025》中英字幕 p11 -12-Lecture 11_ Large Scale Distributed Training.zh_en -BV1FqazzVE6w_p11-

![](img/016171e1511ffec1c0fe95f4b73186be_0.png)

Welcome back to CS2311， lecture 11 today we're going to talk about largescale distributed training and this is a pretty exciting topic because this is basically how all neural networks get trained in practice today when you look at large models from startups from industries even academia really large scale is kind of the new norm in deep learning nowadays and that's actually something that's changed quite a lot in the last 10 years since we started this class10 years ago。

 it was really actually pretty common to train all models basically on one GPU one device and it was fairly uncommon to train on multiple devices but as we'll see nowadays the new norm is to train models on tens。

 hundreds， thousands， even tens of thousands of devices concurrently so we need to develop new algorithms and new ways of thinking in order to do that。

😊。

![](img/016171e1511ffec1c0fe95f4b73186be_2.png)

So as a bit of running example through today's lecture。

 we're going to be talking a lot about Lama 3405B， not because this is the best model or the most interesting model。

 but because this is a model that this is a fairly close to state of the art model that actually shares a lot of the implementation details of how it was trained。

 the model architecture， everything like that there's a lot of really amazing powerful models that have been trained in the last couple of years from Google from OpenAI from Anthropic from others。

 but basically they don't share any details whatsoever about their models anymore。

 there's a very famous quote that just sort of marked a sea change in industry to me that was in the GT4 paper back in 2023 so when they released the GT4 model。

 they said given both the competitive landscape and the safety implications of large scale models like G4。

 this report meaning the paper they wrote about GT4 contains no further details about the architecture。

 including model size， hardware， training compute data construction。

 training method or similar and that's basically the news that's basically been the state of the art for large scale models the last three years since since。

P4， they don't tell you anything about anything。 They'll tell you nothing about the model。

 You'll be lucky if they'll tell you it's a transformer。 They might tell you that much。

 Soll Lama 3 is sort of notable， not because it's the best model out there。

 but because it's one of the most open models out there。

 So this is a large language model that was trained by Me and released open source about a year ago in April 2024。

And unlike Open AI， the paper actually does share a lot of the details about the model training。

 not too much about the data， a lot about the system infrastructure that was used to train it。

 so this is something that we and this gives us a sort of a peek into how large scale LLMs are actually trained these days and by the way。

 there is a new La of 4 model that just came out from that last month。

 April 2025 so there are slightly better models out there in open source already。

 but there's no paper on Lama 4 yet， so I'm excited to read that one hopefully when it comes out in a couple months and see what can we learn from the new generation of Lama training。

 but just as a running example through today's lecture we'll be pointing a lot of examples from the Lama 3405B model for this reason。

Okay so there's basically two things that I want to talk about today。

 One is a bit about GPU hardware and the other is how to train on lots of GPUus。

 so I want to give you a sense both of what actually is the hardware that these things execute on as well as the algorithms that we need to use in order to train on a lot of them。

 So first we're gonna to talk a little bit about GPU hardware So GPU for those of you that don't know is graphics processing unit these were specialized co-processors that were originally developed for computer graphics and they turned out to become to be very useful generalizable parallel processorors it's actually very fitting to be giving this lecture in this room because this is the Huang Aorium Jensen Huang is the CEO and founder of NviDdia which is sort of the biggest company right now and has been for the last couple decades in producing GPUs both for gaming and for and for M。

 So these things started off basically for graphics because if you think about it when you're doing computer graphics you need to generate a lot of pixels on the screen you need to process a little lots of little pieces of primitive geometry to produce those pixels So it's kind of very natural。

to do a lot of computation all in parallel when you're doing computer graphics so people quickly figured out that this hardware that had been built intended to use in computer graphics could actually be used for much more general pieces of parallel computation as well so researchers so in the early days sort of early 200s researchers figured out how they could contort these graphics cards into doing generalizable parallel programming and then moving on towards the end of the 2000s and into the 2010s andviDdia really picked up this and sort of developed these things marketed them。

 built them with the intention of being generalized parallel processors they didn't quite know at the time what exactly they were going to be used for I think they had this general idea that parallel processing was going to be important and they really capitalized on deep learning when it started to take off in the early 2010s much to NviDdia's credit I think they really realized the potential of this research area very early even in the early 2010s and sort of putting a ton of resources into making sure that their hardware was really useful for deep learning training and it's based。

beenen the main way that people train large scale deep learning models for more than a decade now。

 that's starting to change as we'll see a little bit。

 but their chips are kind of the main one that people use。

So I think I always like looking inside these things and seeing like what's in them So this is a picture of the NviIDdia H100 which is sort of the mainstay of deep learning training right now today。

 there's a next generation that just came out but it's not really accessible yet。

 I haven't trained anything on it yet so this is kind of the state of the art right now inside this NviIDdia inside this H100 GPU in the middle here are these compute cores and surrounding that our 80 gigabytes of HBM memory high bandwidth memory so you can see the memory is separated from the compute course。

 they they need to talk to each other over this bus to move data back and forth from the GPU memory into the course and it can do that at a speed of about3 terabytes per second which is a lot of bits moving around。

Now if we dive deeper inside the GPU cores， we see that in the middle in that compute core part。

 we've got a smaller piece of memory， about 50 meytes of L2 cache that is much much smaller than that 80 gigabytes of HBM memory but it's very very close to the actual computing elements so they can be accessed much more quickly from the compute cores and then the real heart of the thing are these 132 streaming multiprocessors or Ss these are kind of like independent parallel cores they're a little bit more powerful in some ways than a typical CPU core because they can do a lot more parallelism but they're a lot weaker than a typical CPU core also in a lot of ways because they tend to have lower clock speeds they can't do as much instruction prediction as much branch prediction so it's really hard to make exact apples to apples comparisons between these GP cores and the CPU cores but I usually think of these streaming multiprocessors as roughly akin to a CPU core also I know someone's going to go back home and actually count all the little boxes on this screen and you'll see that they are actually 144。

when I' said there's only 132， Why is that？ It's because all GPU hardware uses a process called binning。

 where making these things， they have so many transistors， so many little computing elements。

 no matter how much money they pour into the process， they just don't come out perfectly。

 Some of them always end up a little bit messed up。

 So they kind of plan for that in the development of their products。

 And they say we're gonna to try to make a chip。 The full chip in theory has 144。

 but none of the chips are perfect。 but we know we'll get a reasonable number of those that have at least 132 that are functioning。

 So they tend to use this process of binning。 So then they actually only can sell a much more larger proportion of the chips they try to produce by only promising that 132 of them will be will be turned on。

Then we can dive even deeper inside one of those streaming multiprocessors and then we can see even more what's going on inside of these GPUs so this is just one of the 132 active streaming multiprocessors inside an H100 and there's a couple interesting elements in here to look at first we see we have 256 kilobytes of L1 cache and register files so this continues the trend of the memory hierarchy in the GPU we saw that in general you thought you were learning deep learning you're actually learning computer architecture sorry it's a surprise and it turns out that that memory hierarchy is really important for deep learning and for all kind of high performance computing and the general trend is that you have larger bits of memory that are farther away from the compute course and the closer you get to the compute course you have smaller bits of memory but are much much faster and it's really important to write if you're writing the lowlel algorithms that run on these things it's very important to be aware of this memory hierarchy and to be very diligent in passing data between different phases of this memory hierarchy and if you're writing performance GPU kernels you spend a lot。

Time trying to optimize that。 So just to give you a flavor of that。

 you see the three levels of memory memory hierarchy in the H100。 You've got 256 k of L1 cache。

50te of L2 cache， and then 80 gigtes of HBM memory。

 So those are the three primary levels of memory hierarchy in the H100。😊。

Then we've also got 128 of these FP32 cores， these are little arithmetic units that can do sort of generalized floating point operations and in particular each one of these 128 FP32 cores can compute AX plus B where AX and B are all scalrs。

 it can perform that bit of computation in one clock cycle。

 so then if you add this all up that AX plus B is basically one multiply one addition and you've got 128 of these cores so you can do this whole SM can do 256 floating point operations per SM per clock cycle of the device。

Then we'll also see that in red we've got this is where the real magic happens in addition to these FP32 cores。

 there are also these four tensor cores I think the name is a little bit of a misnomer these are actually matrix cores what each of these little tensor cores does is their special circuits that are designed they only do one thing they do matrix multiply so each one of these little tensor cores can do a single chunk of matrix multiply in particular I believe the H100 ones can do a16 input matrix a is 16 by4 input matrix B is 4 by 8 and then plus a bias matrix a size 16 by 8 so it basically does ax plus B where ax and B or little matrix chunks of this fixed size and it can do that that one little chunk of matrix multiply once per tensor core per clock cycle so then if you kind of multiply all these numbers out you see that that little matrix multiply of aX plus B of that particular size is 1024 floating。

operations where that's counting each multiply each ad as a single floating point operation。

 we multiply that by the four tensor cores in the SM and we see that the entire SM。

 if it's going through the tensor cores can do just over you do 4096 floating point operations per SM per clock cycle and this we need to compare with the 256 that we can get from the FP32 cores and here we see that just like the tensor cores are where all the magic happens。

 this is where the main throughput of the device comes from and if you're writing code that wants to run on these GPUs and maximum usage of them。

 you need to make maximum usage of these tensor cores。

Another interesting thing about these tensor cores is that they actually operate in mixed precision rather than traditional floating point numbers which are normally 32 bit the tensor cores tend to use a mixed precision procedure where the inputs are usually 16 bit and there's a couple different interesting 16 bit formats that they can use that we can't get into today and they'll do the multiplications in this lower precision 16 bit and then do the additions。

 the accumulations in a higher precision 32 bit so these tensor cores take a low precision 16 bit input and then and then do some of the intermediate computation and produce the outputs in a higher precision 32 bit and this is important because if the pytorrch layer。

 if you forget to cast your model into 16 bit， it will run on the floating point cores and cores instead it will be 20 times slower than you expect。

 so this seems like a little bit of minutia， but it becomes very tangible when you mess up those data types in your pytorrch code。

And then so GPUs are really fast and it's really crazy just how much faster they've gotten over the past decade or 15 years or so。

 so when I first started my PhD and was working on deep learning。

 the state of the art GPU that we were all using was this K40 GPU which was released back in 2013 and this thing could do just5terralops of FP32 compute for the whole device all right so I should explain the graph so the X axis is time ranging from about 2013 up to present day and then the y axis is the peak throughput of each of these devices measured in terms ofteraflopsteraflops per second per device and you can see like the graph goes up a lot but there's something salient to notice here is that from the K40 to the P100 something really amazing happened in the V100 which came out towards the end of my PhD around 202016- 2017 and the V100 was the first device that introduced these tensor cores and since then。

Since then， more recent devices have gotten more tensor cores， bigger tensor cores。

 more the device area allocated to Tensor cores， and this has resulted in a gigantic increase in the throughput of these devices over the past 10 or 15 years and the most recent device is this B200 that was formally announced it's slowly rolling out now this one in theory has about has about 83。

3 teraflops per second of FP32 compute and 5000 terralops per second in theory of NI precision compute and a Tensor cores So if you step back like this is like literally we've been living through a 1000 fold increase in computation over the past 12 years and that's just at the per device level so one explanation of why AI has gotten so good in the last 10 years what has happened like this is the answer there's now a source of computation that we're taking advantage of and it's gone up by 1000 x in the last decade anytime anything in the world changes by 1。

XYou should step up and pay attention because that's going to cause major changes in our technological capabilities。

 And this 1000 X improvement， I think， is the major driver of improvement in deep learning over the past decade。

So it does not have 000 does not have 500 tensor cores。

 That's 5000teraflops of compute on the Tensor course。Yeah。

 so we always try to distinguish between the compute on the tensor cores versus the compute on E P 32 cores。

Right， so like this is already crazy， right It's already crazy that there's been a 1000 increase in like a device that you can hold in your hands。

 Like I've held a K 40 in my hands。 and I've not held I've not had the opportunity to hold a B100。

 but they feel like the same physical object。 It's like about the same size about the same weight kind of looks the same。

 but the one from today is 1000 times faster than the one from 12 years ago。 That's insane。

 But it gets even crazier because we don't train on one GPU。

 right I said that when when the K40 first came out in 2013。

 it actually was common to train a lot of models on just one GPU。

 but today we're training not just on one GPU， we're training on thousands， tens of thousands。

 sometimes hundreds of thousands of GPUs all working together to train one model。

 so stack that on top of this 100 fold increase in per device throughput and something truly insane has happened in the past decade。

😊，So then then we can we've looked inside the GPU Now from here。

 I want to zoom out and put that GPU in context， not looking at individual devices。

 but thinking about the modern GP clusters that we build that stitch a lot of these things together。

 So we've already seen a single H100 GPU。 We saw here here we can think of it as another level of memory hierarchy。

 we already saw inside the H100， there were sort of three layers of memory hierarchy as we got closer to the compute elements。

 and as you got farther away from the compute elements， the bandwidth， the memory bandwidth。

 the ability of the device to move bits around between different parts of the system gets slower。

 and this trend actually continues， if you once you escape the bounds of a single device and imagine these in the context of a full data center。

 So here we saw a single H100 GPU gets about three terabte of memory bandwidth that's sort of the GPU memory talking to from its own HM memory to its own compute elements。

3 terabytes per second。 it can move bits around。 But these things typically live inside a GPU server。

 almost all GPU servers have8 devices。One big box and those GPUs can talk to each other and they typically talk to each other at a rate of about 900 gigabytes per second from any one GPU in the server to any other GPU in the server。

 so you can see that's like a 3x less communication bandwidth compared to the GPU talking inside one device。

And here here we again turn to Lama 3， a lot of major players don't publish a lot of details on their training clusters。

 but the Lama3 technical report did actually give a lot of details around their training clusters。

 so from here some of the specifics probably vary a little bit from cluster to cluster but these are now numbers from the Lama3 cluster that was used to train their models。

 so they given one GPU box， they stack two of those box into one server rack and a server rack if you haven't seen it about six feet tall like about the size of a person to just kind of get a mental picture of one of those things so one server rack has two servers inside of it。

 total of 16 GPUs。Then we connect a lot of server racks together into a GPU pod。

 the Lama3 cluster has GPU pods that are composed of 192 racks which is a total of 3072 GPUs and these things have really high bandwidth connectors between all the different racks and as a result。

 any pair of GPUs inside that pod can talk to each other at a rate of about 50 gigytes per second and now you see this is another sort of 20x decrease in memory traffic between what an individual server can talk and then what any GPU across an entire rack can talk to each other。

So 3072 GPUs seems like a lot of compute， but now it's nowhere near enough。

 So we're going stack those GPU pods together into a full GPU cluster。

 So this is actually the full GPU cluster that Me built to train the Obama3 models。

 This thing combines 8 GPU pods together for a total of 24576 GPUs。

 I could not find exact numbers on the memory traffic between these things。

 but it's definitely less than 50 gigys per second。And by the way。

 this is not the largest GPU cluster in the world by a long shot。

 it's the biggest one that I could quickly find precise numbers on。

 but there are definitely GPU clusters out there in the world that are 50，000 GPUs， 100，000 GPUs。

 they exist and people train models on them。And like the way that this works is it sort of scales out naturally。

 So you would just sort of cluster together more pods together to create a bigger a bigger cluster。

 or you might have another level of hierarchy where you might have sort of a superpod that connects to other superpods to get you another level up。

How long do they train that GP cluster I don't remember offhand for the Lama three models。

 but there's been kind of a rule of thumb for the past decade is that the longest models that people train are usually on the order of months and that I think has less to do with technology and more to do with people when it comes to making having progress like making plans like having people work on things it's very difficult to have training runs that are very。

 very long so the longest training runs， the biggest state of the art models I think are typically measured in months I would not be surprised if the very。

 very largest models， the G 4。5s， the G5s if those are like pushing closer to a year at this point but it's pretty common to see training runs that are on the order of a couple of months on these really long really big training clusters。

The question is why do you organize servers into a rack rather than in a pod。

 You got to put them somewhere There's physical constraints on these things。

 So server racks are have been a standard unit in just like data centers for decades at this point。

 So when these new devices came onto the scene of GPUs that gives you a different kind of server。

 they're a lot physically bigger they have a lot more power but you can't redesign the whole data center from scratch overnight。

 So as a result， the server rack has been kind of a standard unit with standard hardware sizes and everything that data centers are typically built around。

How much physical suite does like a cluster？Oh， that's a great question。

So a single you should think of a single server rack as being like around6，8 feet tall。

 something like that， like about this big， So maybe like server rack would be like around the size of this podium and about as tall as me then you've got 192 racks in a pod so imagine like 200 of these podiums how big would that be and then multiply that by8 but that's actually a little bit of an underestimate because you typically organize these things in rows so people can actually walk between them and there's more hardware that you need to pack into the cluster not not just the compute racks So in addition to the compute racks that have the physical GPU servers。

 there'll be other racks that contain networking hardware。

 we've got a lot of bits that need to fly around between all these devices so there'll be dedicated racks that only hold networking hardware there will also be dedicated racks that only hold storage hardware because you need to store the training data somewhere and get that into your devices So these things can take up quite a lot of space。

Oh yeah， question is when you go to these big clusters。

 do the smaller units of compute maintain the higher throughput and yes they do。

 and that's part of the secret and the challenge of designing for these systems because you ideally want to take advantage of the fast communication when you can get it。

 but also fall back gracefully to the slower communication on the larger units as you scale up。

How hot does it get Pretty hot。 Like if any of you is a gamer and has 4090 GPU or 5090 GPU in in your desktop at home。

 like a single 4090 GPU， if you're playing game will heat up your room like make you want to open the window。

 it will make the room physically warmer。 So imagine if that's what a single gaming GPU can do to an average sized room。

 Yeah， there's some serious cooling requirements for these things once you stack tens of thousands of them in a big data center。

😊，Although another interesting thing is about I mean， the cooling gets crazy right。

 So a gaming desktop will typically be air cooled， sometimes water cooled。

 And then like you can design different different cooling systems。

 and you can go nuts on the hardware here to try to optimize all this stuff。😊，All right。

 so I think this stuff is super cool， just like imagining like these GPUs are not just mythical creatures that are floating around in the cloud。

 these are like actual physical atoms that someone built and stacked up in a room somewhere。

 and it's really interesting to imagine what they look like。😊。

And so basically one kind of mindset shift when we move to these big GPU clusters is actually thinking not so much about the individual devices。

 about the individual servers， I basically try to think of the entire data center as one big computer and this big computer in this case has 24000 GPUs。

 1。8 petabytes of HM memory on the GPUs， 415 million FP32 cores。

 13 million tensor cores and this whole thing can do 24 exoflops of compute per second that's 24 times 10 to 18 that's a lot of flops It's a lot of flops。

 but I guarantee you five years from today， it will not feel like a lot of flops。

 which is the even crazier part。And our goal here is actually to think of this entire block of 24。

000 GPUs as one giant supercomputer。 and then the question is how can we train one neural network for months at a time on this one giant supercomputer and train a really gigantic neural network that's really powerful that can soak up tons and tons of data。

 and that's basically the question and the paradigm that we've moved to in deep learning。

And by the way， I keep saying GPU， I keep saying NVIDdia because they are sort of the most dominant training architecture and hardware today。

 but there are some others that have sprung up the biggest competitor I think right now to Nvidia training hardware is Google Google has their own hardware called Tensor processinging units TPUus and these are really good they've gone through six generations of these already these are the stats of the V5 TpU which you can rent in Google Cloud today and it's sort of roughly same order of magnitude kind of similar specs as the H100 that we just talked about there are some interesting design decisions in the TU that are quite different from the GPUs which I find fascinating but we just don't have time to get into today and someone was asking how big are these things this is an actual picture just like GPUs these TUs are arranged into pods and the V5 TPUus can be arranged in pods of up to 8960 chips and this is a picture actually of a V2 TPU pod。

 which has only 256 chips。So then that kind of gives you a sense of how big these things are each one of those then you see there's four racks here。

 those racks are kind of like I said， maybe about as a little bit taller than me。

 and there's four of them side by side for 256 TP chips and now imagine this thing is going to get a lot bigger in the more recent pods that have up to almost 9。

000 chips。Yes， so Google's Gemini models are almost certainly trained on Tpus。 I would be of course。

 they don't tell you， but I would be astounded， absolutelyol astounded if they were not。

And like I said the TpUus are actually very good。 I assume that most large-scale Google models are trained on these things and those are very competitive models。

 So this is really good training hardware。 The difference within NviIA is you can't buy it the only way you can access TpUus are either by working at Google or by renting them on Google Cloud but it is very good hardware and a lot of people are making use of it but I think it's still a little bit less popular today than H100 than NviDdia GPUus。

 and of course other companies obviously know that this is a very important thing。

 So there's a lot of other companies that are trying to build competitive training hardware。

 but I think like my honest assessment right now is that probably NviDdia and TpUus are the two big ones they're way ahead of everyone else right now today in terms of usability performance just like market share。

 but there are a lot of others that are trying to catch up here two notable ones are AMD AMD has been sort the second major GPU manufacturer for many decades they also have a training accelerator called the Mi325x on paper it actually has really good stats that are pretty comparable to。

H100， but it just has not had the same impact as the H100 right now AWS also has their own training chip that they've developed called cha Traium I don't know too much about this one I've never tried to use it myself。

 but I know that Anthropic uses it for some of their training。

 I don't know to what extent their training is entirely trainingium versus GPUs。

So we should expect to see more， but like today， I think NVIDdia GPUs are probably the most dominant and Google TUs are like right there。

 they're really good as well， but probably not quite as widely used as GPUs from NVIDdia。Okay。

 so that's basically part one。 is what are GPUs， How do we arrange them into clusters。

 Just give you a sense of the physicality of these machines that we're building and training on。

And the second question is how do we actually write algorithms that can make use of this giant GPU cluster with tens of thousands of GPUs It's going to require us to develop new algorithms。

 new ways of thinking about our compute and new ways of parallellyzing and splitting up our neural networks So the basic strategy here is going to be split up your computation these things are giant parallel devices they have a lot we saw they have a lot of GPUs。

 a lot of CPU cores， a lot of GPU cores that can all operate independently and they can't talk to each other too much。

 If you think about what a computer really does like at a high level a computer basically does two things It does computation。

 which is taking input bits and computing new output bits from those and it does communication which is taking bits and moving them from one bit of memory in one place to some bit of memory in some other place and the whole trick is how do we make use of all of these multiple scales of memory hierarchy across the entire cluster to overlap the communication with the computation and also to split up the computation and parallellyze it。

In the process of training a giant neural network， we have useful work for all of those tens of thousands of individual GPUs。

 all of those millions of individual compute elements。

 we have useful work for all of them to be doing in parallel and then get them to communicate their work to each other in a way that achieves training a giant neural network all on this giant cluster。

😡，So to that end， one way I like to think about it is there's basically five degrees of parallelism that people exploit when training neural networks largescale neural networks today。

 a lot of this is specific to transformers because those are the dominant architecture that people are using for a large scale training so if you think about a transformer a transformer is basically a stack of L layers and each one of those L layers is operating on a three- dimensional tensor of size one dimension is the mini batch dimension。

 we've got a bunch of sequences all operating in a mini batch a sequence dimension。

 know we're operating on sequences or sets of tokens and a dim dimension so each of those tokens itself is a vector with some dimension so our tensor are transformers are operating on these three- dimensionsal tensors and they operate through a stack of layers so that gives us four axes to parallelze on we can parallellyze on the layers axis which is pipeline parallelism we can on the batch dimension which is data parallelism we can split on the sequence dimension。

which is called context parallelism and we can split on that dim dimension。

 which is called tensor parallelism， so all of these have kind of funny names。

 but if you think about it in this way， they're basically all different ways of splitting up your computation across these four axes of compute inside your transformer and then we're going to step through each one of these in more detail because there's a lot of interesting nuances with all of these different mechanisms of distributed training。

So the first one is data parallelism or DP。 And the basic idea here is kind of simple。

 So remember when we're training neural networks， we're always operating on mini batches of samples。

 right like we're always you know taking a mini batch of elements。

 we're computing a loss for every entry in our mini batch。

 depending on whatever our training task is， then we compute a gradient where the gradient is actually typically an average of the gradients of the losses for the individual elements in the mini batch。

 So in most neural network architectures， the computation of computing a loss and then computing the gradient is independent for each of the elements in the mini batch。

 So this is something that seems trivially parallelzable。😊。

So the basic idea is that if you can fit a mini batch of n examples on a single GPU and you have access to M GPUus。

 then we're going to train our model with a giant mini batch of M times n examples where we split up that giant mini batch into a little tiny smaller mini batch of n samples that goes on each GPU and if you think about mathematically why this makes sense it's because gradients are linear so in practice if you're kind of computing a single scalar loss L。

 which is going to be the average of some individual losses computed on each our so these Xj are all the entries across your entire macro batch I guess we'll call it and then the w or the weight weight matrices of the entire network。

 then typically the loss that you're computing at the end of the forward pass is an average of the losses on each of the individual mini batch elements and then if you take the gradients of the loss with respect to the weight of the network' that's the thing we need to compute in order to make a weight update then that is actually going split and because gradients are linear。

You get to sort of choose in what order do we want to do the sum do we want to do the gradient。

 do we want to do the averaging， so in particular it becomes convenient to arrange the gradient in this particular formulation where there's this inner term that we've highlighted in blue。

 which is basically a normal for backward pass on end elements。

 and these can be computed in parallel on different GPUs。

 and then there's an outer sum where we need to take an average of the gradients across our M different devices that we're operating on。

So that's kind of why what's happening from a mathematical perspective and we see that this is perfectly mathematically sound。

 This is basically exactly the same mathematically as training on a single device。

 we've just been clever with our algebra and changed the order of doing our averages in our summations。

 but this is not an approximation。 This is exactly the same computation as we would have done on a single larger GPU。

So kind of what this looks like at the GPU perspective is that we have N GPU M GPUus here I'm showing m equals3 because that's all that can sensibly fit on the slide but you know think that this is much larger than three in practice then each one of those GPUs actually maintains its own separate copy of the neural network weights of the optimizer state and of the gradients so then what we're going to do each GPU will load in parallel a different mini batch of data here we're showing each GPU loading three of mini batch of three elements and crucially the different GPUs need to load different mini batches of data I've had bugs in my code and students code where they accidentally load the same mini batch and all the GPus that's not going to help you that's not going to be good don't make that mistake so it's crucially important that your different GPUs actually load different mini batches of data then each GPU will independently do its own forward pass on its own mini batch of data to compute its own local loss on its own local mini batch of data and these can all operate totally independently does not require。

Any communication between GPUs？Then each network will do its own backward pass to compute the gradient of its own local loss with respect to all the weights of the model。

 And again， this can happen totally independently because each model， remember。

 has its HU has its own independent copy of the model weights。

 It can do its own four backward passs completely independently。

But now after the backward path is done， this is where things get tricky。

 remember we said we needed to compute an average of those gradients across all the devices that are participating in our training。

 so then we need communication so this is where we do an all reduced operation and every GPU needs to needs to send its gradients to all the other GPUs and so there's sort of two things happening simultaneously one each GPU needs to broadcast its gradients to all the GPUs and then two each GPU needs to collect the gradients from all the GPUus that are participating in the training so this is an all- reducedded operation and this kind of happens in sort of logarithmic time typically depending on in the number of GPUs but at the end of this all-red operation then each GPU now has an average of all the gradients across all the devices so at this point the communication has happened each GPU now has an identical copy of the gradients that have been all reduced across all the devices so now at the beginning of the training iteration we assume。

that each GPU had its own independent copy of the model weights Now at this point。

 each GPU has its own independent but identical copy of the gradients across the entire macro batch of data。

 so now at this point each GPU can make a weight update on its own local copy of the weights and because they started with the same weights and they applied the same gradient。

 they're going to have the same weights after the local weight update assuming the arithmetic was deterministic。

And also by the way， and this is really important。 steps 4 and5 can actually happen in parallel。

 We said that there's two things that there's actually two things here that can happen in parallel。

 one is the backward pass where each GPU computes its own backward pass to compute gradients and the other is the communication of the gradients across the GPUs and these things in practice will typically happen simultaneously so that means that each model will start off doing doing backward pass over the last layer in the network and then compute its own local gradient Now the model will move its compute on computing backward pass for the second to last layer of the model and while the compute elements are busy computing the backward pass on the second to last layer。

 then the GPUus will simultaneously but doing all reduce of the gradients of the last layer so this means that these things kind of chunk along communication for layer L plus1 and backward pass for layer L and they can just chunk along in parallel so that hopefully by the time we've gotten to the end of the network and by the time the backward pass is done the gradients have already been all reduced across all the devices。

And we can make our weight update all at once without waiting。

 this is really important because like we said， with their communication is relatively slow。

 so the whole trick in these things is figuring out ways to hide the communication costs and do them at the same time as the compute。

The question is is four or five going be the bottleneck and the answer is yes。

 It depends entirely on how fast your device， how big is your model， how big is your mini batch。

 how fast does the interconnect between the devices。

 When you get to this lower scale distributed trading， the answer is always。

 it depends on your situation， and you need to benchmark for your situation。

Why not take M different gradient steps on each of them。 That's actually a really cool idea。

 There actually was a popular set of algorithms that people used a while back called asynchronous SGD where they would basically do that then basically have a bunch of different model replicas I'll take a bunch of independent model steps and then try to average them every once in a while and those were popular there were some actually Google used to do this before they develop the TpP pods and some of their earlier networks in the early 2010s were trained in this way but one it tends to just be a lot more unstable and two it's very hard to debug and reproduce it just tends to work a little bit worse so it does feel like a more scalable approach but in practice if you can do everything synchronously then your algorithms are easier to debug easier to understand easier to reason about and basically if you can get away with synchronous gradient updates。

 it's probably going to work better but actually I would personally not be too surprised if we see a resurgence of asnc SGD methods in the next couple of years at some point because I think they are a lot more friendly to distribute。

There's no one computer that can orchestrate all this stuff。

 All these things are independent devices with their own independent stuff。

 there's no driver that can take a God's eye view and take those steps。

All that computation has to happen somewhere。 great question。 I said。

 like as you're overlapping communication and compute。

 you need to write code for this or does the hardware do this automatically。

 you definitely got to write code for this。 The hardware is not smart enough to understand what you want to do。

 like the hardware， like we said it's of understands these little matrix multipied chunks that understands pretty lowle stuff。

 anything that you want to do to schedule that communication you need to take care of in software。

 but thankfully for a lot of these common use cases， Pytorch ships with it for you。

 So for example in this case there's a pytorch class called distributed data parallel that will do this for you and make this sort of happen relatively transparently on top of otherwise straightforward pytorch code that you've written。

😊，Although actually that is really interesting to contrast with the individual devices。

 because if you're programming an individual GPU in KUuda。

 which is NviDIious's language for programming GPUs。

 then actually the hardware does take care of a lot of this async transfer for you automatically。

 but at the cluster level， it typically doesn't， then you typically need to do it in software。

 so it actually is a little bit of interesting asymmetry here between parallelism on the individual device level where a lot of that does happen automatically in hardware versus at the cluster level where it needs to be orchestrated in software。

Yeah， so so typically these are heterogeneous systems where different parts of the system are written in different programming languages。

 So there's gonna to be low-leve device kernels that actually are the code that executes inside the GPU and those are typically written in Kuta。

 which is know it's a Clike language that is Nvidia's language for programming their own GPUs。

 but then those individual GP kernels will get wrapped up and you can call those GPU kernels from Python。

 And this is basically how Pytororch works。 Pytorch is sort of like a collection of a lot of GPU kernels that can do lots of interesting stuff on the GPU and then a lot of C plus plus and Python code that wraps around those GPU kernels and makes it more user friendly to program。

So in this picture， each GPU is computing its own gradients in black by itself。

 and then the gradients in red get computed via and all reduce across all the GPUs in parallel。

Oh the backward pass at the lower layer is dependent on the gradients from the previous layer。

 but crucially network is each GPU is only doing backward passs locally on its own mini batch。

 So then there's basically two different variants of the gradient at each layer that you need to think about now。

 there is the local gradients about the gradient of the local loss of my mini batch with respect to my network weights。

 and there's the global gradient， which is the derivative of the total loss of the macro batch with respect to the network weights。

 So each GPU can only in order to compute a backward pass。

 each GPU only needs the local version of its upstream gradient。

 But then computing the global version of the upstream gradient requires communication。😊。

So this is data parallelism and there's actually a bit of problem here which is this is a great way to paralyze GPU computation and this was the first way that people started paralyzing GPU computation in neural network training but we quickly hit a bottleneck on the model size So here remember that each GPU is keeping its own independent copy of the model parameters and this becomes a bottleneck when you want to have really big models So in particular now each weight in your neural network。

 you basically need to keep track of four numbers， the weight itself the gradient of the gradient of that weight and the optimizer state。

 So if we're using atom that's typically a beta that's a beta 1 and a beta 2 per parameter in the network and sometimes you'll also have an exponential moving average of the model parameters as well So typically you'll have four to five scals that you need to keep track of for every weight in your network and if you're training with 16 bit precision which is pretty common these days some of these you'll sometimes keep in higher precision but let's talk about 16 bit as a lower bound then you need two bytes for each number so that means that we need。

😊，Numbers2 by we we need 8 by per scalar in the network to keep track of。

 which means that 1 billion parameters 1 billion model parameters is going to take about 8 gig of GP memory to store all that stuff。

 And we said the whole GPU only has 80 gigs of memory for an H100。

 So that means that the biggest model you could ever hope to train in this scenario is something like 10 billion parameters And that's not big enough。

 We want really big models。 We don't want to be constrained by the tyranny of our GPU memory size in telling us how big a models were allowed to train。

 So we need to fix this somehow。And the fix for this is actually relatively easy。

 split we need to split the model weights across the different GPUs。

 so in addition to splitting the batch of data across GPUs。

 we're also going to split our model weights across the GPUs。

 and this leads to a variant of data parallelism called fully sharded data parallelism or FSDP and this is relatively conceptually what we're going to do is each model weight in the network。

 each weight WI， we're going to assign it to a owner GPU。

 so each weight will be owned by a unique GPU among the M GPUs that we're training on and that the GPU that owns each weight will also be responsible for managing the global gradients for that weight and the optimizer state for that weight。

And typically you would split this up by layer， like you're not managing individual scalrs。

 this W you should think of as the weight matrix for an entire layer of the neural network。

So now now now the picture on the right changes a little bit here we're only showing two GPUus because spoiler there's gonna to be a lot more arrow is flying around here in just a moment。

 So here we're showing a four layer network that we're distributing across two different GPUus we've assigned the first two network the weights for the first two network layer is W1 and W2 those are owned by GPU1 the weights W3 and W4 are owned by GPU3 a GPU2 So that means that at the start of each batch the network weights are split up across the GPUs in this way but it's still data parallelism it's still the same basic idea that each GPU is going to load its own independent batch of elements。

 do a full forward backward pass on that batch to compute its own local gradients then we'll reduce the gradients and take a gradient step same basic algorithm but it gets tricky now because the model weights are split up So here we need to introduce extra communication So when you're doing fully sharded data parallelism now at the beginning of forward before you start doing the forward pass of the first layer whoever owns that weight for the first layer。

Nes to broadcast that weight matrix to all the other GPUs that you're training on。 So in this case。

 GPU1 owns W1。 So it broadcasts that to GPU 2。 So GPU 2 now has a copy of W1。

 Now that all the GPUs have a copy of W1， they can run a forward pass for the first layer of the network and compute the activations at the first layer of the network。

And now after you run the forward pass， each GPU that does not own that W1 is going to delete its local copy of the W1 weight matrix to save memory。

 So then after we run the first after we run the forward pass for the first layer。

 we're back in the state where the model weights are split up across the GPUs。

 but now all the GPUus have also have an activations in GP memory that is the result of running the first layer of the network and now now it's time to do the second layer and we do the exact same thing。

 So then the GPU that owns the weight matrix for layer2 is going to broadcast that to all the GPUs that we're training on now they all have their own local copy of W2 they can and they can go forward and by the way。

 we also have an opportunity to interleave computation and communication here as well。

 so that while we are computing the forward pass for layer I。

 we can be pre-feting the weights for the next layer。

 So in practice this will happen in parallel during the forward pass of an FSDP run So then we'll be computing well be computing layer2 at the same time we're fetching the weights for layer 3 and once we get to layer3。

Note that now GPU1 owns layer 3， so then GPU1 will be broadcasting the weights to all the GPUs that we're training on and this will repeat until we've gotten to the end of the network and now at the end of the network。

 then all models now each model has on a full forward pass compute its local loss on its own local mini batch and has all the activations for all the layers in memory already for backward and now we need to do the same thing in reverse in order to compute the backward pass So at the beginning of the backward pass for for the last layer whoever owns that last layer weight will broadcast it to all the devices once the devices have that weight then they can perform the backward pass and this whole will do a similar kind of procedure in the backward pass now there is a little bit of optimization we can do on the very last layer in the network。

 which is don't delete how all the GPus keep the weights for the last layer in memory So this is something that you'll usually do in practice because at the end all the GPUs already have a copy of the last layer weights from the forward pass they'll just keep it in memory and they know they're about to reuse it for the backward pass anyway。

So we just won't delete the weights from the very last layer。

So now there's now there's basically three things that need to happen during the backward pass。

 one is that you once the GPUs have computed the backward pass for their last layer of the network。

 now that they have a copy of the weights now at that point。

 each GPU has computed its own local backward its own local gradients for its local loss with respect to that last layer weights then we need to we need to communicate those gradients back and we said that the GPU that owns the weight matrix is also going to be responsible for managing the gradients for that weight matrix。

 So now rather than all reducing the gradients as we did in the data parallelism case instead we're going just the one weight matrix that owns just the one GPU that owns that one last layer weights is going to gather and take a sum across all the local gradients across all our devices。

 So in this case， GPU1 is going to send its last layer local gradient to GP to GPU2 which will then have the full gradient DL Dw4 of the entire macro batchch with respect。

To the last their weights。What happens during the downtime。

 you got to get all this stuff happening in parallel So in this so then you know there's basically three things that need to happen during backward during backward。

 we need to communicate the weights， so whoever whatever GPU owns owns the weights for that layer has to broadcast them two we need all the GPUs once they get that weight need to compute a backward pass for that layer and then three after each GPU computes its backward pass。

 then it needs to send the result of that the gradients with respect to the weights of that backward pass back to the GPU that owns it and and then after that then the then once the owner of the weights has that full gradient then only the owner of the weight matrix can now make a gradient update that one weight matrix but I think at this point we actually do not need to communicate the updated weight matrix because it will get recommunicated to all the GPUs on the next forward pass so that's a little bit different from the D case maybe and then basically all of these things can actually happen in parallel。

As well so they will repeat this for every layer of the network and then basically in the steady state of a very deep network。

 all three of these things will be happening simultaneously so while we are computing the backward pass for layer L we will be aggregating the gradients and performing a weight update on layer L plus1 and we will be prefeting the weights for layer L of minus-1 so I said there's three things that need to happen we need to get the weight run the backward pass and then update the weight and then aggregate the gradient and update the weight and these things can all happen in parallel so we'll basically in general be operating on three consecutive layers and doing all three of these things in parallel over the course of the backward pass。

Right so then and then as we chunk backwards over the network。

 by the time then hopefully if you were properly able to overlap all that communication and computation。

 then by the time you finish your backward pass， then all the gradients have already been communicated all the GPs have already finished doing their update on all the weights and we and also hopefully your data loader that's loading data is also happening asynchronously usually on the CPU cores of our servers so then the CPU is like ready with a fresh batch of data to go forward again。

 So these things are basically parallelization machines， we have a lot of stuff that needs to happen。

 both within a GPU and across GPUs and we need to overlap all of that as much as possible so we can always feed the GPUs and have them running on those tensor cores as densely as possible。

😊，Right， so then we're basically ready to do our next batch after， after that。So this is great。

 this is fully sharded data parallelism and this can get you a long way。

 but there' is actually a slightly slightly fancier variant of data parallelism that people sometimes use called hybrid sharded data parallelism or HSDp and in this case we're actually going imagine conceptually dividing our GPUs into a twodimenional grid so in the previous examples we said we had sort of n GPUus and the way that we parallellyzed our computation was kind of the same。

 we had sort of one axis of parallelization in the previous variant of data parallelism once we get to hybrid sharded data parallelism we now we're going to have two separate axes of parallelism that we will do at the same time So the first axis is we will do typical fSDp fully sharded data parallelism along one axis that we just talked about So we'll have sort of groups of kgUus and each group of k GPUus we be doing fully sharded data parallelism that we just talked about so within each group of K GPpUs the model weights will be split across those KGpus and they will be interleaving。

😊，Sending weights and gradients back and forth to each other during the forward and backward passes。

 but we will have now M copies of those K groups operating in parallel。

 So in this case we have two groups of four GPUs， so each group of four GPUs you see has the weights split across the four GPUs。

 but we have entire the entire the entire setup duplicated a second time on a second group of two GPUs。

And the reason and then when you do this， now you know then they do typical data parallelism across the groups。

 so within a group we're going to do forward backward and at the end of the backward each group will have computed its own local gradients and then after the backward then each group needs to all reduce the gradients across the groups so that we now have like the full like macro macro batch gradients across the two groups and then each group can make an gradient update independently once they've received the full gradients for the macro macro batch。

So this is called multidimensional parallelism because now there's basically two different axes。

 two different strategies that we're using to paralyze our computation simultaneously and why this might be useful is because there's different amounts of communication required for these two different kinds of parallelism So if we think about fully sharded parallelism we actually need to what do we need to communicate during fully sharded data parallelism during FSDP during the forward pass。

 remember we are copying the weights all over So we sort of copy like during the forward pass。

 we end up doing a communication of one full copy of the network weights then during the backward pass we need to recommunicate the network weights and we also need to communicate the gradients So basically when it comes to when you use fully sharded data parallelism during a single forward backward pass you need to communicate three times the network weights across everything participating in an FSDP group but when you do normal data parallelism where each group keeps its own independent copy of the weights you only need to all reduce the gradients So that means that across multiple data parallelism groups。

 you only need to communicate the。Work weights once over a four backward pass and this plays into this idea of multiple levels of hierarchy inside of our GPU clusters。

 So what you might do， for example， is have a GPU server where it has8 GPUs with higher interconnect inside a single machine those might be an FSDP group because it requires more communication inside an FSDP group but then you could have multiple servers that on this other access。

 So you have sort of one server with a full copy of the model weights than another server with another full copy of the model weights and remember communication across servers is going to be slower than communication inside a server。

 So then this is our first example of designing algorithms to take advantage of the network topology that we know our devices are connected into。

Qu is， would you rather have Jeep， like， these things are impossible to tune。 It's very。

 very hard to say。嗯。Right， so you know， and then basically but once you have data parallelism。

 once you have this DP， FSDP and HSDP， this is actually a recipe that can take you a long ways so for example。

 you know a model with 100 billion parameters would take 800 GB of memory to store and if you split that over 80 GPUs。

 it only takes 10 gigabytes of memory per GPU so you can have you know a pretty big model once you have FSDP。

But there's another problem that the model activations themselves now start to fill up memory。

 so if we go back to Lama 3，4 or 5 B， it's a transformer with 126 layers， model dimension of 16。

000 sequence length 496 so if you kind of imagine how much GPU memory it takes to just store the hidden states during a forward pass that's going to be a lot so that's going to quickly cause your GPU to run out of memory once your models and sequences get really big。

So that leads to another trick is called activation checkpointing。

 which means that we're actually not going to store all the activations in memory。

 we're going to recompute them during the backward pass。

So to see how this works like it's useful to think of your neural network in a different way where there's actually two different layers each layer in the neural network does two things。

 it does a forward pass that computes activations for the next layer。

 then it has a backward pass that computes gradients that take both the upstream gradients and the activations so normally you know how much compute and memory does this all take if we assume that all these are constant then typically a forward backward pass will take sort of one2。

3，4， four steps during forward you'll remember those activations during the forward pass then one，2。

3， four steps during backward so in a normal forward backward pass。

 it sort of takes ON compute and ON memory for an N layer network。But as we just said。

 this is gonna to run out of memory。 So instead what we can do is imagine recomputing the activations during the backward pass。

 So what that looks like is something like this。 so we'll start with the activations。

 we'll run the first layer and then immediately throw away the activations for the run the four pass for the first layer and then immediately throw away those activations and sort of do this four times So now we've sort of gone through the network once got the activations of the last layer this point we can compute our backward for the last layer。

 but now we're kind of out of luck we don't have the activations from a3 to compute the next backward pass but we can recompute them so we recompute them now we can do the backward pass now recompute some more now do the backward pass。

 now recompute， now do another backward pass So if you kind of add this all up this ends up being n squared compute and constant memory for a network with n layers because it's sort of sum n and minus-1 and minus-2 n minus-3 b down to1。

 that's quadratic time。And you can split this up， you know N squared compute is pretty bad for deep networks。

 So instead let's not recompute everything。 Let's instead imagine taking a checkpoint of activations every C layers。

 so we'll only sort of compute like recompute within blocks of within tinier blocks the network。

Then in that case， if you take C checkpoints where you remember your activations。

 C times over the course of your network， then it's going to take n squared over C compute and O of C memory。

 and a pretty common thing to do is to set C equal to root n in which case this becomes n root n compute and O of root n memory。

 so this is a pretty common way that you can trade off computation and memory to train even bigger models。

Okay， so now at this point， once we have FSDP activation checkpointing， HSDP。

 we actually we can do a lot of damage here。 we can start to train some really big models and the recipe for that is basically is following So your're scaling recipe that will take you quite a long way from here is first use data parallelism just raw data parallelism roughly up to 128 GPUs and roughly up to models of around a billion parameters。

 you can just do normal data parallelism for models of this size it tends to work pretty well。

 And another thing that you almost always want to set the local batch size per GPU to max up the GP memory that's almost always the right thing to do。

And then once your model starts to get big， then the model itself will take up a lot of memory inside your GPU。

 so that will start to give you problems， so you know it kind of depends on how much memory your GPU has。

 how fast your interconects are， but in general once your model starts to be more than a billion parameters。

 that's when you want to start thinking about switching from data parallelism to fully sharded data parallelism。

And then at this point you can scale up quite a bit。

 but then you'll run into the memory bottleneck for your activations。

 and that's when you turn on activation checkpointing。

 activation checkpointing kind of sucks because it makes everything a lot slower。

 but it does let you train much bigger models。And this will scale like up to several hundred GPUs。

 and then there's some point usually depending on your cluster topology， maybe around 256 GPUs。

 maybe around 5，12 GPUs， once you get to like on the order of multiple hundreds of devices。

 then FSDP becomes too expensive and you need to start switching to HSDP and then this is basically going to let you get up to models that are roughly tens of billions of parameters。

 training on maybe 1000 GPUs， that's on like pretty long sequence lengths。

 so that's pretty good but if you have maybe more than1000 GPUs。

 more than 50 billion parameter models， sequence lengths more more than 10，000 or so。

 this is when you need to turn to these more advanced strategies， context parallelism。

 pipeline parallelism or tensor parallelism。And then there's a big question iss like， oh my God。

 there's a lot of knobs to tune here like how am I supposed to optimize this。

 I need to set the global batch size， the local batch size， the HSTP dimension， the FSDB dimension。

 like how much to recompute like I'm lost here， what do I do。

 There's so many knobs I don't know what do I do The answer is to optimize a very important metric called model flops utilization MFU whenever you get lost in the C of GPU parallelism like model flops utilization is your guiding light。

 followow this It will tell you what to do to optimize your training stack。

But before we get to model flops utilization， we need to talk about hardware flops utilization。

 So remember we said in theory， an H100 can do 988989。4 tfps per second of compute on a tensor core。

 but that's theoretical， How much can you actually get The question is how much can you actually achieve in practice and that's the metric of hardware fls utilization you're running some compute on a device How much compute do you actually realize of that theoretical maximum and this is not hard to do like you can write a couple lines of pitorrch code and just benchmark this So this is a benchmark that I wrote that I ran on an H100 yesterday。

 and you can see what it does is basically x axis。 It just does dense matrix multiply in a loop and then times how long did the matrix multiply happen。

 How long did the matrix multiply take we can compute how many flops of matrix multiply takes then on the x axis we're plotting the size of our matrix going from 512 up to 32000 and the y axis is this hardware flops utilization which is basically the fraction of the theoretical maximum throughput of the device that we actually realize from these matrix。

Multiplies and you can see that on this know pretty straightforward pytorrch loop。

 we're getting about 80% HFU on an H100 once we get to large matrix multiplies of around 8，000 by 8。

000。So that's pretty good。 But the problem is that HFU does not account for all the other stuff that your model needs to do。

 right we're maybe doing activation recomputation， we're maybe running some other models on the side。

 we're maybe doing data loading， data augmentation。

 There's a lot of other stuff your GPU is doing other than just four backward on your raw model。

 And that's where we move from hardware flops utilization to model flops utilization。

 So model flops utilization is basically saying what fraction of the GP's theoretical peak flops are being used for forward backward in my model。

 And this is the thing you always want to optimize for。 So then to make this more concrete。

 you basically compute you know based on your model architecture。

 the size of the number of the layers， the size of the layers you compute how many flops does it take to do a full four backward pass of your architecture on your mini batch of data。

😊，Then you look up somewhere the peak theoretical throughput of the device you're running on and then you divide those two and that tells you how long should a full four backward pass take if you were achieving the theoretical maximum throughput of the device that's like the theoretical fastest you could ever do a four backward pass on your model then you actually time a four backward pass of your model know your training loop is doing all this other stuff is's doing data loading is it's doing augmentation is's doing communication it's doing maybe activation checkpointing so it's doing recomput during backward your training loop is doing a lot of stuff just time see how long it actually takes and then divide those two numbers that gives you a number between zero and1 which is like what fraction of that theoretical maximum are you actually achieving in your training loop。

And that's your MFU here model Phps utilization and again we can kind of benchmark this with some relatively simple Pytorch code。

 here's an example running forward backward on just like a cup like a short multilayer perception with a relu nonlinearity and with really big with really wide MLP layers and a gigantic batch size on a single H100。

 this is getting around 50% MFU。then in general， whenever you're trying to tune knobs for distributed training。

 you always want to try to tune whatever knobs you can to maximize MFU。

 because that's the one metric that we typically care about when trying to optimize training throughput。

And in general， you know an MFU these days generally above 30% is pretty good if you're way under 30% you've probably got some gigantic bottleneck somewhere and something is going wrong and above 40% is pretty pretty excellent and that's basically state of the art and here's some numbers that we can pull from a couple papers in particular this is that Lama 3405B paper that we talked about in their final training step they have a couple different variants of their up training phases where they train on between 8000 and 16000 GPUs simultaneously and across that they're getting MFUs roughly in the like high 30s low 40s and that's that's pretty good you're never going to get really much higher than that on H100。

And actually paradoxically， more recent devices sometimes get worse MFUs。

 so on the previous generation devices， the A100s， you could sometimes get MFUs above 50% and the reason for that is because GPUs are getting faster。

 faster than they are getting faster at communicating so when we move from the A100 to the H100。

 we got roughly a 3x improvement in the theoretical throughput of the compute。

 but we only got a 2x improvement in the theoretical memory bandwidth so there's this growing gap between making GPUs are getting faster。

 really fast， but it's harder to scale the communication between the GPUs and as a result we tend to sometimes get worse MFUs actually on more recent generations of devices。

So that's and I intentionally wanted to spend most of the time on those points because those are the ones that you guys are probably going to use in practice I don't think anyone this room likely has access to a 10。

000 GPU cluster if you do like come talk to me after class I would love to be your friend but so like those are the ones that you're likely to encounter in practice like up to many hundreds of GPUs。

 but there are these other ones that I just like there are slides here that are pretty I think are pretty nice。

 but it's okay if we don't go through the full details of these you can check it offline。

So we said context parallelism is basically splitting on the sequence dimension。

 so we said transformers are operating on sequences and basically the idea is you've got a long sequence you know make different GPPUs handle different parts of the sequence and if you recall your transformer block。

 this is actually easy for large parts of the transformer because the layer norm。

 the multilayair like the FFN MLLP and the residual connections。

 those all operate independently across the sequence anyway。

 so it's relatively straightforward to ask to chunk up that computation across the sequence dimension things get I mean it does get a little bit hairy inside the MLP because there are weights in there so that you have to have some all reduced of the gradients like we did in the data parallelism cases。

The attention is where things get hairy for sequence parallelism because if we remember attention。

 we need to compute the sort of all pair's interaction between every pair of elements inside the sequence the QKB projection is easy because that's sort of trivial parallelzable over the sequence but that core attention matrix that actually gets pretty tricky to parallel the like the first version of this that people developed what's called ring attention where you basically take that full attention matrix chunk it up into blocks and then have your GPU sort of work on those blocks independently in parallel in the right order to make sure everything works out there's a lot of details in there you can check out the paper for more details The second which is a little bit conceptually easier is called ulysses attention where you do parallelism over the heads so remember in a transformer you're almost always doing multi-head attention where you're sort of computing attention over like multiple attention matrices all in parallel so in ulysses attention we're going to parallelze that computation of that core attention operator parallelze that over heads and then everything else。

Other parts of the transformer are paralyzed over the sequence dimension。

And as an example this context parallelism becomes important once you scale up your sequence length to be quite large。

 so if we go back to this example of Lama 3 pretraining， they actually train the model in two stages。

 the first stage they go sequence length of 8000 with no context parallelism whatsoever and then they have a second stage of training where they crank the sequence length up to 130。

000 and then at that point they do 16 way context parallelism so that means that each of those 131000 long sequences has 16 GPUs operating on one sequence in parallel and that's kind of like saying the batch size is like one over 16 because now each batch each GPU is working on like less than one element。

So that's context parallelism， pipeline parallelism。

 we're going to split across the layers dimension， intuitively what you want to do。

 you a network with a bunch of layers， and we're going to just divide the layers across the GPUs。

 that's actually a very intuitive thing to do。The problem is that there's sequential dependencies because each GPU like needs the activations from the previous GPU to continue running the forward pass and during the backward pass。

 I need the gradients from the upstream layers in order to compute the backward pass so we can draw a diagram like this where the vertical axis or GPU is 1 to4 the horizontal access is what happens over the course of time so you can see that GPU run GPU1 runs forward。

 then passes the activations to GPU2 which passes activations to GPU3。

 which passes activations to GPU4 GPU4 is lucky， it can do forward backward all at once。

 then passes gradients back to GPU3 back to GPU2 back to GPU1 so from this graph that's obviously really really bad because the GPUs are mostly sitting idle and in fact if you have N GPUs like you're only getting useful work out of them one over n of the time so that means that if we had like8 way pipeline parallelism。

 your maximum possible MFU at that point is like 12% which is terrible So that's really bad and by the way there's a cute name。

These are sometimes called the bubble is like that chunk of where GPUs are waiting for work and they're like waiting around for the communication。

 So the trick and pipeline parallelism is to shrink the bubble。 You want to have less bubble。

 And the way that we do that is running multiple micro batches simultaneously。 So now。

 like rather than running one batch of data through all the GPUs for it and backward。

 We're going to have multiple batches of data in play simultaneously and shuttle these things across the GPUs in parallel。

😊，So there's a lot of different interesting patterns you can try to design for this。

 but here's a relatively simple one where we have four-way pipeline parallelism So there's four GPUs that are all working in parallel and then we have four batches of data that are all active at the same time and these batches are color coded so we see that GPU1 runs forward on the blue batch。

 then forward on the yellow batch， then forward on the green batch then forward on the red batch and while GP1 is going forward on the yellow batch we've pass the activations of the blue batch to GPU1 or to GPU2 and GPU2 can now do forward on the blue batch so these things can all sort of cascade down and happen in parallel and then the same kind of pattern repeats during the backward pass we can kind of interleave these different mini batch these different micro batchches as we pipeline them through the different GPUs and in this case with fourway pipeline parallelism with four micro batchches are like the max theoretical MFU is just like the fraction of this graph which is not white and that increases now to 57% which is pretty good。

So with pipeline parallelism in theory， if you go to like lots and lots of micro batchches。

 then your MF is going to be good because you can do a lot of work in parallel。

 but the more micro batchches you have， they need to store all the activations in memory So now you need do activation checkpointing And then you think like oh crap。

 Like how do I tune these things Should I have more pipeline parallelism。

 Should I have fewer micro batches， Should I have more aggressive activation checkpointing。

 And then should I also layer data parallelism on top of that， I don't know。

 What are you going to do， Maximize MF， You're going to try to turn tune all of those knobs to maximize the MF of your training pipeline。

Then the last one is tensor parallelism So this one you're going to split on that dimension on that model dimension so basically what we're gonna to do is we have a lot of weight matrices in our model。

 all those weight matrices are like computing xw equals y that's basically what we're doing over and over again inside of our transformer Now the idea is we'll split each weight matrix across GPUs and now this is different from FSDP because we're actually splitting a single weight matrix across GPUs and now there's no communication now we do a block matrix multiply each GPU is now computing a slice of that matrix multiply on the full input so in this case we split our weight matrix into W1w2w3w4 and then each GPU just computes a slice of that matrix multiply to compute a slice of output。

And then a problem is that now after you do that forward pass。

 then you need to gather the activations across all the GPUus to to the next forward pass。

 There's a slight trick， which is if you have two of these layers in sequence。

 you can actually get away with not computing with not gathering in between two layers So if you have two layers you can sit down in a quiet place and work through this you split the first way matrix into column shapeped chunks and you split the second way matrix into rowshaped chunks and if you do all this then it all kind of works out magically because of the magic and mystery of block matrix multiplication and you see that the final output。

 you can kind of compute as an inner productlike structure of this block of these block matrix multiplies of y and U so then you basically can have two layers of matrix multiply and that are split across multiple GPus and then they only need to communicate at the end of every two layers and this actually works out nicely because remember transformers have a two layer NLP in the fFN So this is a really nice trick that plays really nicely。

The two layer MLPs that transformers always have。 So it's pretty common in big transformers to use tensor parallelism。

 this this like two layer tensor parallelism trick on the MLP in a transformer。

So that's basically all of our mechanisms for splitting up computation across GPUs。

 which one is the best The actual answer is all of them So in practice we're going to use ND parallelism we saw already an example of two- dimensionional parallelism with HSDP in practice the current state of the art is like four-dimensional parallelism if we go back to llma we see that they are training with on their biggest training run with 16000 GPUs they're using eightway tensor parallelism。

 16 way context parallelism， 16 way pipeline parallelism and eightway data parallelism all at the same time and if you're careful in like these different mechanisms of parallelism have different communication requirements So if you're careful in how you arrange how you arrange these different axes of parallelism along your cluster you can try to take advantage of that varying speeds of communication across your whole cluster。

And that's basically a whirlwind tour of large-scale distributed training。

 so the takeaway for today is that an individual GPU is basically a generalizable parallel computing machine。

 a GPU cluster is a giant massively parallel machine with tens of thousands。

 maybe hundreds of thousands of individual GPUs that we want to program as one big unit and then we talked about multiple different mechanisms of parallellyzing our computation across big clusters as well as one trick activation checkpointing for saving memory and then the one guiding light metric that you're always trying to optimize when you design these pipelines which is model flps utilization。

 so the next time you're going out and training on tens of thousands of GPUs hope you keep this in mind and let me know so I can borrow your tens of thousands of GPUs。



![](img/016171e1511ffec1c0fe95f4b73186be_4.png)