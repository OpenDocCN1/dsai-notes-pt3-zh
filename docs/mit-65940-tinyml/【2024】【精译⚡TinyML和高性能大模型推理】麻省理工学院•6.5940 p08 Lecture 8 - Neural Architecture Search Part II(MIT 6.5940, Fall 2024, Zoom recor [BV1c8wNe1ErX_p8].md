# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p08 Lecture 8 - Neural Architecture Search Part II(MIT 6.5940, Fall 2024, Zoom recor [BV1c8wNe1ErX_p8]

Okay 335 let's get started， so today we are going to talk about E MLL lecture8 to discuss neuro architectitect search part two。

 this is the last part of neuro architectect research search。And lab two was released。

 don't forget to check it out， we'll implement those quantization algorithms we learned last week。

So let's continue to talk about neural architecture search just to review what we want here here we have multiple targets we wantna to design a network from scratch rather than compressrising the model rather than pruning the model quantizing the model now our goal is to design a model from the beginning。

Ideally， we want a model to be accurate and then have low latency， hydroput。

 low energy and also low storage。In the last lecture。

 we talk about what are the primitive operations， the building blocks， and what is NAS。

 including the search space， how to design and narrow down the search space。

 what is the search strategy like reinforcement learning， evolutionary strategy， greater search。

 random search through this lecture， we'll talk about efficientffient。

 how to efficiently search and efficient architecture。And also hardwareware awareness。

 including how do we quickly estimate the accuracy having to without having to train the model from scratch each time。

And also how to do hardware awareness， make sure the model is not only high accuracy。

 but also as low it。Zero shortness， can we be able searching a model without even training it？

And also how do we search the hardware architecture and the neural network architecture at the same time。

 the co design， code search， the hardware architecture， and also the neural architecture。And finally。

 we are going to apply what we learn about NAS to diverse applications。

 including natural language processing， GN， point cloud， post estimation。

 and also large language models。Okay， so okay， so let's start today's journey。

 starting with accuracy estimation strategies。

![](img/71796c0b5afbbca61fdeb798c7bdd401_1.png)

So as an overview of the neuro architectureect search pipeline， we started with the search space。

 cell level， network level we discussed in the previous lecture。

 and then we have a couple of search strategies we discussed the great search rather than search reinforcement learning green descent evolutionary research。



![](img/71796c0b5afbbca61fdeb798c7bdd401_3.png)

It proposes architecture and then returns the performance and an estimation so now we are going to focus on how do we estimate the performance a quick and efficient performance estimation strategy so that's the focus of today's lecture we will start by talking about trim from scratch and then ahead weight and then a hypernet。



![](img/71796c0b5afbbca61fdeb798c7bdd401_5.png)

Train from scratch is the easiest we just train a model， find find a model architecture。

 train it to convergence and then see the accuracy and latency right we train a given model from scratch on a training set X evaluate the model on the evaluation validation set that get accuracy R but this is apparently very costly even on Cy far 10 this method need to train tens of thousands of models。



![](img/71796c0b5afbbca61fdeb798c7bdd401_7.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_8.png)

And that require 22，000 GP hours that's really expensive， even on such a small data set， except 10。

Not to mention those large scale data sets images that Coco。

 those are actually not considered large scale data sets these days。 Now we are talking about。

Three trading tokens training us eight trading tokens。

 those are large scale we mean by large scale these days。

 so having to train from stretch apparently is not scalable it doesn't scale to this large scale training。

Are there other alternatives？Or we can inherit the weight。don't retrain the weight。

 but starting from a pretrain model， inherit the weight but to change the architecture on top of。

They treat the model。

![](img/71796c0b5afbbca61fdeb798c7bdd401_10.png)

So very famous work is this net to， hey we can。

![](img/71796c0b5afbbca61fdeb798c7bdd401_12.png)

Inherit the weight from this architecture and then we can change the architecture by having three neurons rather than two neurons here。

 what we do here is actually replicating this node this age which in the second human node replicate twice and here we are dividing the weight here by half。

 so we are mathematically equal， but the architecture can adapted。



![](img/71796c0b5afbbca61fdeb798c7bdd401_14.png)

So this is net to wider net we are having。Reducing the。



![](img/71796c0b5afbbca61fdeb798c7bdd401_16.png)

Reducing the weight value but duplicating the nodes。



![](img/71796c0b5afbbca61fdeb798c7bdd401_18.png)

We can also perform net to deeper net， say this is just one layer now we want to。



![](img/71796c0b5afbbca61fdeb798c7bdd401_20.png)

到。this is just one layer， we want to add another layer on top of it。

 so when we do we add an identity mapping layer okay so this layer is basically identity mapping。

So even we've finite added these two layer， the result will be the same。

So in this way we can train on top of this architecture to make a deeper model okay it contains a mapping initialized layers。

 so effectively without any retraining we can change the architecture and maintain the mathematical still maintained to mathematical equal mathematical equal as the original model okay so this is net wider net by using divided by two。

 this is one net to deeper net by cascading with identity mapping layer。



![](img/71796c0b5afbbca61fdeb798c7bdd401_22.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_23.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_24.png)

So in this way， we can inherit the weight from a parent model to reduce the trading cost。

 we get a new architecture or we don't have a retrain model。

Using this net to net approach we can propose new a fractures。

 so remember previously we talked about using an RNA or LSCM。

 each step we propose an action now the action would be either net to wider net or net to deeper net and we can do either of them so we can effectively carry the weight from the parent model to prevent us from having to return the model。



![](img/71796c0b5afbbca61fdeb798c7bdd401_26.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_27.png)

Okay， so next approach is use a hyper network。Iyper network means you have another network that is predicting the weight of your model and the network is used to predict your weight。



![](img/71796c0b5afbbca61fdeb798c7bdd401_29.png)

So what does that look like？We are given a network architecture right here， this is the connectivity。



![](img/71796c0b5afbbca61fdeb798c7bdd401_31.png)

I'm surprised as a graph。And then we have initial note embedding means what is embedding embedding means the features of this。

Now this network architecture， for example， the NCHW， the channel， the width， the height。



![](img/71796c0b5afbbca61fdeb798c7bdd401_33.png)

The kernel size， et cetera， so in layer has embedding here we have five layers。

 therefore we have five embeddings。

![](img/71796c0b5afbbca61fdeb798c7bdd401_35.png)

Not only the future matters， but also the connectivity also matters。

 so how do we model the connectivity？The connectivity is modeled as graph。

 graph node and the edges define this computation graph， so we can use a graph network。



![](img/71796c0b5afbbca61fdeb798c7bdd401_37.png)

As it through several layers of graph network。To have a final node embedding since in each step。

 each node interact with the neighbors for this node for this node for this node。E cetera。

 each node gets collected information from its neighbors。

So that's the graph when the graph natural from the glass。The model the natural architecture。

 and though we get a final embedding， we feed it to a shared NP。

 which is the hyper network to predict， to generate the weight。For the final model okay。

 so the final model's weight is generated by the hypernet。This is the hyper network。

And input to the hyper network is node embedding is node embe okay。

 so the hyper network generates weights based on the model of architecture。

 we can use gradient descent to update the weights of the hyper network。



![](img/71796c0b5afbbca61fdeb798c7bdd401_39.png)

Not quite widely used， we are not going to visit this in。

 but just give you some idea what people has done to reduce the training costs。Okay。

 next checker would be very important and interesting we are having them in the home。

 so network hardware awareness that model not only want to be we want it to be high accuracy。

 but also should be very hardware efficient。

![](img/71796c0b5afbbca61fdeb798c7bdd401_41.png)

Okay， so the general purpose model may not be efficient since we have diverse platforms to deploy like a raberry high。

 very small memory， GP， very large memory， large memory footprint， high parallelism。

 CPU maybe be lower parallelism， mobile phone， resource constraint， memory constraint。

 battery constraint。

![](img/71796c0b5afbbca61fdeb798c7bdd401_43.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_44.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_45.png)

So ideal view way， we want to have specialized specialized model for different。Other platforms。

 like a tiny model for rat reply， high parameter model， lets turn on call for GPU。



![](img/71796c0b5afbbca61fdeb798c7bdd401_47.png)

ASp CPU model and specialized GPU model that takes less energy and less memory footprint。

But you can imagine if we hand design， hand design different models for different other platform。

 that's not automated， and that's very costly， right。So how do we cope with that problem？We can。

 since previous neuroarchitect search approach is very expensive， for example。

 NAnet take 48000 GPU hours， even just search on Sifar data set that's like five years if you have a single GPU。

 4，000 GPU hours。

![](img/71796c0b5afbbca61fdeb798c7bdd401_49.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_50.png)

When darts take hundreds of gigabytes of GPU memory if you directly search it on an imageNe。

 so very kind consuming， very memory consuming。Therefore， previous work have to utilize a proxy test。

 you can think about it as a simpler simpler task so rather than directly search for a target task from target target platform。



![](img/71796c0b5afbbca61fdeb798c7bdd401_52.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_53.png)

We find a simpler proxy task， a smaller proxy task。For example， the data set can be very simple。

 except for。10 class classification， rather than1 thousand class imagenet classification。

Or we can search a search in the small architecture space。Like very low that。

We can also do just a few ipoCs of training， we don't have to train all the way with converence。

 but we just train a little bit and see if that looks promising， right？



![](img/71796c0b5afbbca61fdeb798c7bdd401_55.png)

rather than plug， the real hardware to measure the latency， you can use the proxy， which is flops。

 flops， and the parameter cons we learned in the first lecture。

 how do we estimate how do we calculate the flops， how do we calculate the parameter number of parameters。

 we use that as a proxy task for the hardware efficiency。



![](img/71796c0b5afbbca61fdeb798c7bdd401_57.png)

But you can imagine this is not accurate， right， a model that works very well。

 what is the problem if you search。

![](img/71796c0b5afbbca61fdeb798c7bdd401_59.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_60.png)

A model that works for Sf 10 may not work well on image ads seems the data side is very different。

And also if you just search a very small architecture space， you just search one building block。

 use that the same building block on top of each other。

The first couple of later and the last couple later may not prefer the same building block right。

 so it's not good to search in a smaller search space。



![](img/71796c0b5afbbca61fdeb798c7bdd401_62.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_63.png)

And also fewer ipoOs of training， you may find a model that converges super fast in the beginning。

But after training after a while， the convergence may not be good。You waste a lot of GPPU cycles。

And also we learned that flops and number parameters。

 they do not they do not directly translate to latency and speed out。

 so that is also not quite helpful。So what we do here is to directly search in target task and target hardware without relying on any proxy task。



![](img/71796c0b5afbbca61fdeb798c7bdd401_65.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_66.png)

So how do we save the trading cost？

![](img/71796c0b5afbbca61fdeb798c7bdd401_68.png)

But I'll also be able to directly search on the target task and also target how。So this is one layer。

 input， output。

![](img/71796c0b5afbbca61fdeb798c7bdd401_70.png)

You have managed choices。You can have three by three conve5 by5 and density the pullinging etca right so conventional model just have this weight parameter right。

 but now we introduce these architectural parameters。

 which is the probability of choosing three by three conve probabilitybabil is a using the three by three con probabilitybabil is betaa。

 we assign。Asign。A different choices。One architectural parameter。

 which is a probability of choosing this particular block。



![](img/71796c0b5afbbca61fdeb798c7bdd401_72.png)

we have five choices then we have five probabilities， they add up to one。

 and we learn not only the weight of each choice， but also we learn the probability of choosing them。



![](img/71796c0b5afbbca61fdeb798c7bdd401_74.png)

系。Therefore， we introduce these two updates， one is updating the weight parameter。

 the actual weights in the  three by three convolution。

  three by three by In China or by alpha China。And we also iteratively learn those architectural parameters。

 the probability of choosing each path。

![](img/71796c0b5afbbca61fdeb798c7bdd401_76.png)

诶。In at the inference time。We are bannerizing。These architectural parameters zero means thrown away one means we keep it so that during treating we only have one path in the GPU memory rather than within sum of all these different paths if that is the case we have to compute the activation after three by three activation after five to five activation after putting average them together using the probability。

 then you can consume a lot of GPU memory you have n choices then the GPU memory is on N that is not good so we only sample by binaryizing the gates binaryizing these probabilities and choose the one that has the highest probability and then only sample one path。



![](img/71796c0b5afbbca61fdeb798c7bdd401_78.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_79.png)

Iprove those redundant paths based on these architectureural parameters。So in this way。

 we are learning training the model from scratch， which train not not only these weight parameters。

 but also these architectural parameters。If we have the architect parameter， here is 0。9 0。1。

 then at inference time， we are going to sample the architectural parameter with the highest probability。

 usually 0。9， then we are going to choose the first choice。

And also binizing the architectural parameter allow only one path。Of the activation will be active。

And therefore the memory footprint would be O1 rather than ON right no matter how many different choice you will have。

 you may have different channel size， you may have different kernel size， if a lot of choices。

 we want to make sure that tri memory is over1 rather than taking hundreds of gigabytes of deepping memory which is very expensive。

So in this way， getting the architecture is as cheap as training the model in a single class。

 and you just train the model once you train not only the architecture weight parameter。

 but also train the architectureural parameter。

![](img/71796c0b5afbbca61fdeb798c7bdd401_81.png)

So we turn this mod from a proxy task and eliminated these proxy taskss。

 we can just directly train the model you heard to train the model on the target task and target hardware proposal architecture and update okay。



![](img/71796c0b5afbbca61fdeb798c7bdd401_83.png)

So that we call this work proxies nice。

![](img/71796c0b5afbbca61fdeb798c7bdd401_85.png)

Because we don't rely on proxy task or proxy hardware metric like Fls okay so proxy task like Sara10 now we can right use image have to train it since the training cost is the same as training the model from scratch。

We no longer have to be constrained with a small architecture search space。

 but we can open up a much larger search space since we are finalizing different choices but keep your memories over。



![](img/71796c0b5afbbca61fdeb798c7bdd401_87.png)

A capableable。

![](img/71796c0b5afbbca61fdeb798c7bdd401_89.png)

And also， we don't have to contrain on ourselves with only fewer ipos and training。

 or we can do full training。

![](img/71796c0b5afbbca61fdeb798c7bdd401_91.png)

And also we don't have to just use the flops and parameter number of parameters。

 but also we can profile the latency， we're going to talk about this。

 how do we use profile the latency to directly without having to measure using the flops。

Actually using flops is sometimes dangerous so this is this X axis is the max。

 the Y axis is the latest measured on Google Pix Y mobile phone okay。



![](img/71796c0b5afbbca61fdeb798c7bdd401_93.png)

So there are three dots， the blue one is the mobile net Li。The orange dot here is the last net。

 the green dot is a mobile net。These two models and those are searched by conventional maths approach they have similar Macs actually they have smaller Macs compared with thiswa mobileNe me tool mobileNe2 has roughly 500 and。

18 medium maxs。But this model on mobilenet has only about 550。Meium max， it's a small。

But unfortunately， the latency is 190 mill seconds compared with more less than 150 millise seconds。



![](img/71796c0b5afbbca61fdeb798c7bdd401_95.png)

So max doesn't translate to real hardware efficiency。

 right we can have lower max but actually higher agency， much higher em。Right。

 similar for the GP platforms。

![](img/71796c0b5afbbca61fdeb798c7bdd401_97.png)

If you reduce。

![](img/71796c0b5afbbca61fdeb798c7bdd401_99.png)

The hidden dimension size。From the laency actually doesn't quite change， the Y access is the latest。



![](img/71796c0b5afbbca61fdeb798c7bdd401_101.png)

Reduccing the hidden dimension barely reduce your density right since GPU has very high parallelism。

 if you reduce the workload may be hungry， you may not realize any measured the speed。



![](img/71796c0b5afbbca61fdeb798c7bdd401_103.png)

But here if we still a number of layers。

![](img/71796c0b5afbbca61fdeb798c7bdd401_105.png)

The latency will scale proportionally speaking in the number of layers。

 the latency will be scale proportionateally。

![](img/71796c0b5afbbca61fdeb798c7bdd401_107.png)

So similar flops， but very different than is， the access is very clearly much the same。



![](img/71796c0b5afbbca61fdeb798c7bdd401_109.png)

But theiliancy differs a lot。

![](img/71796c0b5afbbca61fdeb798c7bdd401_111.png)

So Max， the conclusion is that Max doesn't translate to the measured real hardware efficiently。

So we have to be careful using flops as the proxy represents efficiency。Here are some other examples。

 for example， if you change the hidden dimension。For Ra reply。



![](img/71796c0b5afbbca61fdeb798c7bdd401_113.png)

Reducing the healing dimensions will effectively reduce the v。Well。

 Triputo is not influenced by the hidden dimension。



![](img/71796c0b5afbbca61fdeb798c7bdd401_115.png)

Since GPU has very large par， even if you have a very large even dimension， the GPU is not saturated。



![](img/71796c0b5afbbca61fdeb798c7bdd401_117.png)

So what does it mean to us， we should not use the flops as a reward right since it's not a true reward。

 we want to use the latency， measure the latency as a true reward for your neuroural search algorithm。



![](img/71796c0b5afbbca61fdeb798c7bdd401_119.png)

Thereforeful， we want to measure that it is on the target hardware platform。



![](img/71796c0b5afbbca61fdeb798c7bdd401_121.png)

But you can imagine measure the litency is very slow right you can also have a bunch of hardware devices to measure them in parallel。

 but that becomes expensive。We spend quite a bunch to purchase a lot of phones we have a mobile phone。

build a mobile phone so that you can buy that it is in parallel and it's just getting more expensive。

So what can we do here？We use a machine model， design， design a latency predictor。

Given a neural network architecture to predict how fast it can run。

So here we collect a littency data set。

![](img/71796c0b5afbbca61fdeb798c7bdd401_123.png)

Architecture latency， architecture latency， architecture latency， right？



![](img/71796c0b5afbbca61fdeb798c7bdd401_125.png)

And we do with a agencyency model。

![](img/71796c0b5afbbca61fdeb798c7bdd401_127.png)

So that given a new neural neural network actually， we can predict the la。



![](img/71796c0b5afbbca61fdeb798c7bdd401_129.png)

How far it can run on this target platform。我 the most simple。

Model for latency providing is basically a lookup table。啊，你。

Pro while basically everything you have you could encounter。

And then啊 look into index into the lookup table。

![](img/71796c0b5afbbca61fdeb798c7bdd401_131.png)

We build a latency data set which containss operator one， latency， operator2， latency， etc cetera。



![](img/71796c0b5afbbca61fdeb798c7bdd401_133.png)

And then we summarize them in the Excel sheet。And later when we see that layer。

 we just look at that entry in the lookout table。And adding different layer together。

 adding the latency of different layer together。And actually， that works quite well。

 This is the estimated latency。 This is the real real latency from this pro of last work。



![](img/71796c0b5afbbca61fdeb798c7bdd401_135.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_136.png)

Roughly follows y equal to x， roughly follow that line。Would be more complicated。

 we can also build a predictor rather than using the lookup table。

So what is the feature for this predictor？A feature for a layer can be like the NCHW。

 the kernel size， the width， the resolution， different dimensions， etctera， given those feature。

 we can use a simple linear model to predict the latency。And actually that also work quite well。

 this is form transformer architecture in this work HAT hardware hardwareware transformformer。

 this is y equal to x， predict latency is very close to the real latency。



![](img/71796c0b5afbbca61fdeb798c7bdd401_138.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_139.png)

And we are just summing up the latency of different layers together to get a total N to end latency for a particular model。

What could be the problem here？By summing up individual layers licenseency to get a total it。On twos。

You may have kernel fusion， sometimes two kernels might be fused into a single kernel。

 then the latency might be much smaller than adding up these two layers together。

So you have to be careful about the implementation like Teer RRT might do those optimizations behind。

But how do we know if some layer can be fused or not？

The rule thumb is roughly if it this computation intensive kernel followed by another compute intensive kernel。

 like mighttema followed by another mite Ma usually doesn't help usually what what helpful is like matrix multiplication followed by a9 nonlinear activation function。

 which is memory bond the compute bond versus the memory bond memory bond share the same output or input then you can be fused in the previous layer。

 so that's all of the a lot of this class， but thats some insight we can we can keep in mind some of the layers can be easily fused。

Okay， so let's see how that helps building such specialized hardware aware propertiesxies neural natural architecture。



![](img/71796c0b5afbbca61fdeb798c7bdd401_141.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_142.png)

So this is the Motime to very well designed well curated model from Google for mobile devices。

And the red line is basically a mobile net。The x axis is the latency， the lower the better。

 the lower the faster， the y axis is the top line accuracy， the higher the better。



![](img/71796c0b5afbbca61fdeb798c7bdd401_144.png)

We can see it's about 80% faster。

![](img/71796c0b5afbbca61fdeb798c7bdd401_146.png)

And compare it with。This is not hardware awareness us。This is the accuracy。

 this is the latency as the smallest latency by the highest accuracy。



![](img/71796c0b5afbbca61fdeb798c7bdd401_148.png)

Was just showing such small specialized model is really helpful for the latency and accuracy trade off。



![](img/71796c0b5afbbca61fdeb798c7bdd401_150.png)

Talking about specialization， we want to exam when we are targeting different kinds of platforms。

 a GPU a CPU or mobile device。

![](img/71796c0b5afbbca61fdeb798c7bdd401_152.png)

And this is the Proxy NAS search target GPU。We specialize this model for the GPU。

 and this is a specialized design， specialized model for the CPU design。

 a specialized model for mobile。And they have different accuracy and let's see。

 what if we apply this GPU model to GP to CPU and to Googlewell？Can you find。Unsurprisingly。

 the diagonal latency is the shortest。Showing that the model specialized for mobile works the best for mobile。

 it does not run as fast than the GPU compared with the GPU model。



![](img/71796c0b5afbbca61fdeb798c7bdd401_154.png)

That makes sense because GPU has very high parallelism and CPU has no parallelism。So of course。

 they prefer different neural architectures。好的。And so here we want to visualize the search process。

During the training process， remember we are learning not only the weight parameter but also the architectural parameter。

 so different from conventional training where the model architecture stay the the same you are training exactly the same model architecture rule off。

The different typepos。But now we are training also the new architectures and upon congence。

 we can see that the CPU model is much a CPU model is much deeper， GPU model much general。

 and GPU model is much wider。

![](img/71796c0b5afbbca61fdeb798c7bdd401_156.png)

CP metal model is narrower， GPP model use a lot of large kernels seven by sevendi kernel。

 which is in red。CPU model actually didn't use MP7 by7 kernel all the kernel are either three by three or five by five because CPUU has。



![](img/71796c0b5afbbca61fdeb798c7bdd401_158.png)

Thatice terrorismism。So large kernel may not be more efficient and over there。

 but GDP really prefer a low number of kernel costs since each kernel call takes a lot of time。

 therefore it prefers very wide but fewer number of layers， which is indeed the case。



![](img/71796c0b5afbbca61fdeb798c7bdd401_160.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_161.png)

So let's take a look at the whole process again， starting with the exactly same utilizationization。

And as a graduate learns， the GPU model actually becomes shallower but wider is entrepreneurial GP one go graduate is yellow earth is red and later disappear。



![](img/71796c0b5afbbca61fdeb798c7bdd401_163.png)

One， only one left。呼关呼。until the end， there's no no large kernel at all。



![](img/71796c0b5afbbca61fdeb798c7bdd401_165.png)

So it's very interesting to see the search history how the neural network architecture adapts to different hardware features like terrorismism。

Okay， so that's for one way to search specialized model for different hardware platforms forms。

Then the next question is， if we are given a model， given a hardware platform。

 like a GPU or GPU or DSNP or accelerator， we have to repeat the process to search model for each of them。

 which can get quite positive。How do we further improve the productivity and we just have one single model and then we somehow later we can tweak it to fit GPU to fit GPU to fit theP or a smaller one to the mobile device a module one to fit a GPU。

Comvental methods， like if we have one hardware platform， like we are searching model for a phone。

 we spend a couple of duty hours。

![](img/71796c0b5afbbca61fdeb798c7bdd401_167.png)

By several research ipoOCs training right， forward， forward and backward， if it is good。

 that we break and then we do some post training optimization after that。When you have more devices。

 we have to repeat。

![](img/71796c0b5afbbca61fdeb798c7bdd401_169.png)

The process for more devices， we can be， which can be more costly。And if we have many devices。

 they become super expensive to do this process。So in order to eliminate the search cost。

 reduce the search cost for diverse， diverse hardware platforms。

We'll talk about a once for all approach， once for all approach。

 we are going to implement this in lab three， so the lecture here is very important。

So rather than training each network from scratch， like using the using the Pro dance approach。



![](img/71796c0b5afbbca61fdeb798c7bdd401_171.png)

Now we treat multiple models at the same time。We have a single model okay that contain mainly sub networks。

 okay， which once small network， they are sparsly activated。We can have many sub just like this。

We can activate， sparsely activate some sub network， a small portion of data。

And then we get the latency， we get the accuracy。嗯。

And we want to see if the latency and accuracy meet our conserv。He brings meat， he math。

 then we finish the search process， you doesn meat。Then previously， we have to retrieve model。

A train from scratch， train a day or even longer time。AndRe this process， which can be flexible。

And now we don't retrain it， you just sample another sub network。

 a different sub network around Mos long network。We are going to provide you one of this once for network for you during the homework so you can just implement this process and you don't have to train in from scratch。

 give you the once for network， you can sample a sub network， and sample with different sub networks。

 can a vtency measure the accuracy and see whether it meets your demand。



![](img/71796c0b5afbbca61fdeb798c7bdd401_173.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_174.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_175.png)

If not， you can rather than just train it again， you can just sample from the Westvo network。So。

 let's see。What is that good for？So we can train once and get many so that we can reduce the design cost。

 the training cost is amortized， but not many searchs。



![](img/71796c0b5afbbca61fdeb798c7bdd401_177.png)

This once small network contains managed child networks that are sparsely activated。



![](img/71796c0b5afbbca61fdeb798c7bdd401_179.png)

So during architecture search， we can search a。

![](img/71796c0b5afbbca61fdeb798c7bdd401_181.png)

Larger sub network deployed on powerful GP like H100。

 a mid sized network deployed on a consumer level GPU like 1490 GPU。

We can also derive a small version。And feed it on a。Mobile toQ， like I mean Jason already。

And for these three models， we don't have to train it from scratch。



![](img/71796c0b5afbbca61fdeb798c7bdd401_183.png)

And this is particularly helpful for large language model where it's very costly not quite affordable between these models from scratch。

 but now you can do three in one model and get many sub networks to get different get models of different sizes like3 Vs。

 7B， 70B， etc。

![](img/71796c0b5afbbca61fdeb798c7bdd401_185.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_186.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_187.png)

Similarly， if different chips have different memory con streams， you can design。

 deploy a larger sub network。Under larger memory const， means middle one for a middle sized memory。

 a tiny one for a tiny memory。

![](img/71796c0b5afbbca61fdeb798c7bdd401_189.png)

Okay。Or a larger model for a new phone， or old smaller model for an old phone。

So that we can cater for users with different forms， like someone may have iPhone 16。

 someone may have iPhone 11， we want to make sure the model can write on all different platforms。



![](img/71796c0b5afbbca61fdeb798c7bdd401_191.png)

But similarly， when you leave home in the morning， your phone may be a full battery。

During late night， you maybe have very little memory during battery receiving mode。

 so now it can seamlessly shift to this tiny model that is derived from the same once fallen ice。



![](img/71796c0b5afbbca61fdeb798c7bdd401_193.png)

So that is the usage。

![](img/71796c0b5afbbca61fdeb798c7bdd401_195.png)

So a principle is just true once and get many， and we true one。And then we get mag。

 surprisingly we can get1 to the 19th。And for I think it's a surprisingly large amount of child networks for free by just training this。

Onces four on experts。Different child metrics are spaly activated。

But they shared the weights with his wife's foreign network。

 and trained them jointly to amortize the design cost。

AndOFA can design specialized models for diverse hardware platforms。

So how do we implement such a once one network？First of all， let's brainstorm some challenges。

It's hard for a model to operate。So independently because they share the weight， right。

 how do we prevent different sub networks from interfering with each other。

 how to make sure they can all independently operate。

So let's take a five minute break and then we are going to return to talk about how to implement it。

Okay。Okay， welcome back， so let's dive Viper， how do we implement。

 how do we realize this magic once for a network that can have many sub networks independently operate。

😊。

![](img/71796c0b5afbbca61fdeb798c7bdd401_197.png)

So the key part is to progressively prune and shrink the kernel size depth resolution across different dimensions okay so we want to progressively shrink the kernel size remember we want to support both large model。

 middle model， small model therefore we want to do across different dimensions， the kernel size。

 the layer and channel from the kernel size perspective。



![](img/71796c0b5afbbca61fdeb798c7bdd401_199.png)

We started with a seven by seven kernel。And then the inner part of the seven by seven。

 which is five by five。We pass it through a transformation matrix， we learn that matrix。

 and then we can derive。And middle size， middle kernel， which is5 by five。And also。

 we can use the inner part of this five by five kernel to get a three by three kernel， okay？

So in this way， we can either operate on a small model， a middle model or a large model。

 they share the weight。

![](img/71796c0b5afbbca61fdeb798c7bdd401_201.png)

So naively to support these three different sizes， how many parameters you need。

 you need 49 plus 25 plus plus9 right but now we need only one7 by7 49 weights and it five by five weight ensure that the inner part of the  seven by seven weight and this nine3 by30 weight is the inner subsection subpart of this five by5 weight。



![](img/71796c0b5afbbca61fdeb798c7bdd401_203.png)

And similarly， we want to apply， but weight sharing principle to two other dimensions。

 the number of layers and also the number of channels we are implemented in the lab L three。



![](img/71796c0b5afbbca61fdeb798c7bdd401_205.png)

What's single a careful book at this？

![](img/71796c0b5afbbca61fdeb798c7bdd401_207.png)

So we start with the full thats。Here we have example of depth of four。

 and then we shrink the depth to support we can have depth of three or depth of four。

 depending on which one we choose。We further shrink the depths by allowing it to the 03 to come directly out of layer2。

 so we can have two layers or three layers only only four layers。



![](img/71796c0b5afbbca61fdeb798c7bdd401_209.png)

So that's progressively shrinking the number of layers。



![](img/71796c0b5afbbca61fdeb798c7bdd401_211.png)

From four layers， three layers to two layers。

![](img/71796c0b5afbbca61fdeb798c7bdd401_213.png)

We can also progressively shrink the number of channels initially。

 we have four channels shrink with the full width。

![](img/71796c0b5afbbca61fdeb798c7bdd401_215.png)

And then we can sort the channel importance by looking at the magnitude of different channel。

We organize them according to the size， the largest one is the blue one we put in the front insert sorted。

 and then if we allow it to have only three channels。

 we pick the first three most important channels。And finally， we can also allow it sorted again。

 so we pick only two channels that we pick the two largest slides。The green one，0。85， the yellow one。

The yellow one is among the largest one least， so we can either choose the four layers。

 four channels or three channels or two channels。

![](img/71796c0b5afbbca61fdeb798c7bdd401_217.png)

So the network becomes very idile， where it becomes very elastic， elastic， we can have a larger one。



![](img/71796c0b5afbbca61fdeb798c7bdd401_219.png)

And this larger kernel， other depths， larger width， we also have a smaller one， smaller kernel。

 smaller smaller depths， smaller width。

![](img/71796c0b5afbbca61fdeb798c7bdd401_221.png)

But they share the weight， so ultimately you have one the biggest model。

 then a small model can be derived from that biggest model。Okay。

 so let's see this in animation question here。可以。到。呢系。

So the question is how do we make sure the biggest model still works after training the smaller burdens right so during training we sample the larger one。

 larger one and also the smaller one， so both the larger one and smaller one get a chance to be sampled。

So that you can make sure the larger larger one didn't get destroyed。For example， iteration one。

 we may train a bigger， very big one， iteration two， we may treat a smaller one， iteration three。

 we may go back to train a very big one。And there are different sampling and probabilities。

 schedules you can choose。Yes， because we are sharing the weight we are treating a smaller one。

 you're also updating the bigger one。By only the middle parts， yes， you got it。They share the weight。

 so even you heard if you're training smallest model， the biggest model is still impact。Okay。

 so this is an emission showing that we start with the depth dimension。

 starting with the elastic depths， elastic resolution， so there's another dimension。

 which is the resolution dimension， and we can also randomly sample different input resolution for each batch。



![](img/71796c0b5afbbca61fdeb798c7bdd401_223.png)

So small resolution made the resolution， large resolution。

 that doesn't impact your weight because different resolution is share the same weight。

 but that impacts your max， your flops。

![](img/71796c0b5afbbca61fdeb798c7bdd401_225.png)

And also elastic kernel size。Eel lastastic steps。And also elastic width。

So that's the four dimensions we are going to make it to be elastic， including the resolution。

 the kernel size， the depths and the width， so in that lab we are going to provide you with such a model that already that has already went through this whole toolium pipeline so you can directly use it in sample different sub networkss。

 smaller kernel larger kernel smaller depths， larger depths， etc cetera to play with it。

 build a latency predictor and given a particular latency， just find the best network architecture。

So let's do some roof line analysis to see how this efficiency compare with others so when it is roof line analysis so there are two axis the X axis is the operations per bite so you fetch one bit of data move one bit of data。

 how many operations operations are able to do on top of that memory。



![](img/71796c0b5afbbca61fdeb798c7bdd401_227.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_228.png)

So data movement is very expensive， computation is cheap。Ideally。

 we want to fetch one bite of data and we do a lot of operations on top of it。Okay。

 and the Y axis is the G flops is the GFps to realize the performance。



![](img/71796c0b5afbbca61fdeb798c7bdd401_230.png)

And initially we are memory bottlene， so as long as we are increasing the operations per。

We can improve the GOs。And later we are compute bound， no matter how many operations provider have。

 you are limited by the number of multipliers and multipliers and others in the platforms。



![](img/71796c0b5afbbca61fdeb798c7bdd401_232.png)

So this is a rule fly analysis， it looks like a roof， so people call it rule fly analysis。

And let's see how does the One4 network， where is the once4 network located compared with other approach like MNNe。

 mobilenet B2 so this is not human design model， this is a N model。



![](img/71796c0b5afbbca61fdeb798c7bdd401_234.png)

So actually once for all is having is on the top right corner， what does upper right corner mean。

 it means you can achieve higher G per second and also right means it has higher operations per bite。

So this is log access， so the difference is actually quite big。

so bigger operations per bite means that we can have making more memory efficient。

 we fetch one bite of data， we can do more operations on top of it。

 therefore is why it's getting more efficient。

![](img/71796c0b5afbbca61fdeb798c7bdd401_236.png)

And indeed， we measure the realized efficiency， measure the GOs per second and see one foreign network indeed having a higher measured of GOs per second on the housing platform。



![](img/71796c0b5afbbca61fdeb798c7bdd401_238.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_239.png)

So this is just one hardware platform， let's see how it performs on diverse hardware platforms。

So we measured it on Samsung phone， Google， phone， LG， phone，V GPPU， Intel CPUPU and ZningPGA。诶就。

This blue part is the baseline latency versus accuracy， ideally we want a low latency， high accuracy。

 so the top left corner is good。嗯。acrosscro all different platforms。

 you can see you once for a network design the sub network actually reside on a better priorto optimal curve with lower latency and also higher accuracy。

All right。That is the hardware awareness， Any questions so far。

Make sure you unclear about how once smart network works so that we can complete La three。Okay。

 no question is in one to talk about zero shortness。



![](img/71796c0b5afbbca61fdeb798c7bdd401_241.png)

Onlyly zero short lastPrevious啊 we can to measure the latency on a hardware platform。



![](img/71796c0b5afbbca61fdeb798c7bdd401_243.png)

We have to first train it for a while and then estimate the accuracy right which can be quite costly。

 you have to train it which can be quite slow train it for a while but now let's just look at the model without having to train it。

 let's just see eyeball tracking not actually eyeball tracking。

 we just see some of the featuress itself without having to train it just look at it look at the analyze architecture。



![](img/71796c0b5afbbca61fdeb798c7bdd401_245.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_246.png)

And see and guess whether you can have a good accuracy or not。



![](img/71796c0b5afbbca61fdeb798c7bdd401_248.png)

I' will introduced two pieces of work， then not and also grab。The motivation is basically。

 don't train it and tell me the accuracy whether it's promising。So zero short nuts z nus here。

 there's one heuristic saying that we just randomly initialize the input for the poly normal distribution。



![](img/71796c0b5afbbca61fdeb798c7bdd401_250.png)

And then we add a small perturbation and small perturbation to obtain a new X。



![](img/71796c0b5afbbca61fdeb798c7bdd401_252.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_253.png)

And then we initialize all the weights of a neuronaural architecture using normal distribution。

 so random weights basically。

![](img/71796c0b5afbbca61fdeb798c7bdd401_255.png)

So this paper is saying that the difference between these two inputs。



![](img/71796c0b5afbbca61fdeb798c7bdd401_257.png)

the two inputs will generate two outputs in FX and FX S。

And the difference between these two output outputs。If the model is good。

 then the difference should be large okay if the input is difference is the same。

 good model should be sensitive to the input preservation。



![](img/71796c0b5afbbca61fdeb798c7bdd401_259.png)

Change the input that a little bit， the output looks dramatically change。

And it propose a second heuristic， which is saying the batch normalization。

 so we want to have fine the average for the variance in the8 layer， and we add them up together。



![](img/71796c0b5afbbca61fdeb798c7bdd401_261.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_262.png)

We want to encourage the variances to be large， otherwise different inputs they have exactly the same output that's not good if the variance is large。

 then consider design potential to be good。But frankly。The architecture is just a tip of iceberg。

 the way it also matters， so here is using the random weights so it's very core screen eyeball checking not very。

But actually the result works quite well at least in this paper。

 just look at given the perturbation of the input， if the output changes a lot。

 then that's good for different batches， if the variance is big， then that's good。

Another hereic great sign so great sign this paper basically says a good model will have very dense。

 very dense simpleized local mini okay so the two local minis should be very close rather than very far away from each other。



![](img/71796c0b5afbbca61fdeb798c7bdd401_264.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_265.png)

Therefore， the distance between the local minima should be close to each other okay and therefore there's a higher probability that the gradients in different sample。

 you try different samples， x1， x2， x1， x2 should have the same sign。



![](img/71796c0b5afbbca61fdeb798c7bdd401_267.png)

Calculating the sign is very cheap right so in this area in the red area the signine of the gradient here is negative here is positive they are of the different signs and if they are in the scoring region here both of them have negative gradient here both of them positive gradient okay。

So if you sweep， starting from here and here， the the green region will have the same sign。

The red region we have different sign。A good model， which have very close local minimum。

Should have a very large portion of them in green， which means the gradient should be of the same sign。

 that's why this works name is hot gra sign so we can。



![](img/71796c0b5afbbca61fdeb798c7bdd401_269.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_270.png)

Use this approach to count the number of entries that has given the same gradient。And if the sign。

 if the sum is large， that means a lot of region is good and green and it's good。

So those are very two very simple heuristics， you don't never train the model。

 you just feed it with some input and then calculateulate either the output difference or the variance of the normalization layer or the sign of the gradient。

ok。So far we talk about given a hardware platform， maybe the hardware platform is fixed。

 how do we optimize the neural network architecture？And now also， let's open the box。

 say you can also。Have the freedom to design the hardware architecture by yourself is an AsI by yourself。

 you open up the box， you can now design both the hardware architecture and also the inner architecture。

 how do you design them together？So that's the next chapter， which we'll not do in the lab。

 but it good it might be eye opening。Let's talk about the new chapter about neural architecture。

 neural accelerator architecture search， search not only the neural architecture。

 but also the accelerator architecture。

![](img/71796c0b5afbbca61fdeb798c7bdd401_272.png)

So we propose a hardware design， we then propose a neural architectureural design。

 we collect some feedback running this neural network on this hardware。

 and then we it routinely tweak the hardware and also the neural network。



![](img/71796c0b5afbbca61fdeb798c7bdd401_274.png)

Extra。

![](img/71796c0b5afbbca61fdeb798c7bdd401_276.png)

With this look。And here are this is showing we can tweak the neural architecture。

 this is showing we can tweak the accelerator architecture。



![](img/71796c0b5afbbca61fdeb798c7bdd401_278.png)

And both of them， both designs are important to enable specialization。

 just now we talk about specialized architecture runs the most efficiently。

So let's see what is the design space， we must have a much bigger design space including both the newer architecture and also the hardware architecture。

 much larger design space。So what are the key dimensions now。We have three components， right。

 we have the hardware accelerator。W whichch include several hardware dimensions。

 like the local buffer science， global buffer size， the number of processing evidence。

 the number of PEs。The size of the compute array， the PE connectivity。On the compiler side。

 which compiler maps the neural network on the hardware excalgerator。

 so on the compiler side we have the loop orders， right which loop to process first which loop to process later。

 loop ti size and data flow right。A neuroex for perspective。TheNumb of layers， number of channels。

 kernel size， whether we have bypass an input and output and weight quantization precision。

So that's a pretty big design space。And the solution is to ideally we want to do have one optimization loop。

 okay， this is one optimization loop to search both the accelerator architecture and also the neural architecture。



![](img/71796c0b5afbbca61fdeb798c7bdd401_280.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_281.png)

So let's see first， the accelerator architecture， which you include a pretty large design space。

 including can categorize them into two categories， one category is the size related。

 which is very simple， like the buffer size， local buffer size， global buffer size。

 the number of pes。

![](img/71796c0b5afbbca61fdeb798c7bdd401_283.png)

And second one is slightly more challenging to represent in numbers next。



![](img/71796c0b5afbbca61fdeb798c7bdd401_285.png)

The PD connectivity， which one connect to which one。

And our key idea is to talk about how do we put those non numerical numbers like the connectivity。

 you cannot easily represent connectivity by a number and how do we design those non numerical values。

So when we are mapping the。A couple of operations like a follow up operations into the hardware roughly there are two categories okay one is temporal mapping one is spatial making so what is difference here spatial mapping here means you can process them in parallel in space like here I have 10 multipliers then I can process 10 multiplications in parallel one to34 five so physical theyre in the space or I have two by two by5 we have 10 multipliers so that's taught spatial parallels you can parallelze them in space theyre executed incorrectly。

And also you have temporal temporal mapping， okay， that means you can process them sequentially。

 okay， but in different order， so what determines the order。



![](img/71796c0b5afbbca61fdeb798c7bdd401_287.png)

The sequence of the fall loop determines the order okay so in this case we have two lines of code indicates hardware parallelism paralyzing space for the M and n dimension range 16 and 16 so probably have 256 modpliers here。

 you can concurrently execute them paralyzze them in space。And then you have this temporal mapping。

 including both the tiding， what is the tile size， what is the order determines in which sequence do you map these loop powders in the temporal dimension。



![](img/71796c0b5afbbca61fdeb798c7bdd401_289.png)

So here we categorize them into two parts， one is the hardware includingd a vector。

 the algorithm is the mapping including a vector。

![](img/71796c0b5afbbca61fdeb798c7bdd401_291.png)

One is related to the hardware， but one is related to the compiler， the mapping。



![](img/71796c0b5afbbca61fdeb798c7bdd401_293.png)

Some of them is not numerical， right。

![](img/71796c0b5afbbca61fdeb798c7bdd401_295.png)

The parallel dimension choosing which dimension to para in space okay。

 so that's not easy to be represented by a single value and the look order also may not be very straightforward to represent similar to like the tile size number of P in the kind size。

 which is just a single value， this is not。

![](img/71796c0b5afbbca61fdeb798c7bdd401_297.png)

W Wei is to do index based encoding， for example， zero means sequence CR XY KY S1 means C X Y RSK C means channel XY means the height than width RRS means the kernel size and width K means the number of kernels。

 but actually it doesn't convey any physical information Y this one has a larger index than this one doesn't make sense。



![](img/71796c0b5afbbca61fdeb798c7bdd401_299.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_300.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_301.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_302.png)

So what we do try to make it have some meaning， we first fix the dimension position in the encoding vector。

 for example， the first position is k is second position C。Colonnal size， channel number。

 height and width， Col external Y。

![](img/71796c0b5afbbca61fdeb798c7bdd401_304.png)

Andper number of criminals， number of tris， height and waste。



![](img/71796c0b5afbbca61fdeb798c7bdd401_306.png)

The eternal science。And then we assign a numerical importance to these dimensions。

So this is numerical value。 The importance is a numerical value。And then we can sort them。

 right we can pick the two largest one。

![](img/71796c0b5afbbca61fdeb798c7bdd401_308.png)

C is the largest one， a is the largest one so that if we want to paralyze them in space。

 we for sure we want to paralyze the dimensions with the high with the high importance。



![](img/71796c0b5afbbca61fdeb798c7bdd401_310.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_311.png)

So we choose the first two dimensions， if the dimension size is two low， and we choose the top two。



![](img/71796c0b5afbbca61fdeb798c7bdd401_313.png)

And for the mood other。We assigned the most important dimension as the outermost since it will be iterated last number of times。

And we put the least important in the inner side， the inner loop， which will be very hot。

 which will be executed many times more time consuming。

 therefore we put it in the less important in the innermost。



![](img/71796c0b5afbbca61fdeb798c7bdd401_315.png)

So in that way， we can convert these parallel dimensions in versus the loop order， which。



![](img/71796c0b5afbbca61fdeb798c7bdd401_317.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_318.png)

Our definition is not numerical value， we turn into a numerical representation by sorting them。

So let's see if the search results give you this number like。



![](img/71796c0b5afbbca61fdeb798c7bdd401_320.png)

The parallel dimension will have two dimensions， and then we choose。

The first two most important dimensions C and K since their importance value is the largest six and4。

 we put them as the parallel4 we have these two rows of parallel four we are paralyzing in space。



![](img/71796c0b5afbbca61fdeb798c7bdd401_322.png)

Since this is related to the hardware improvement matter。

 which didn mention do we paralyzze in space rather than serialize in time？



![](img/71796c0b5afbbca61fdeb798c7bdd401_324.png)

And then the parallel dimension cs of size two we repeat these two most important ones。

And then the dimension sizes is given by 16， then we fill in 16 and 16 in the entry here。

 meaning that we altogether have 16， this dimension 16， that dimension multiply them together。

 you have 256 bodypliers。

![](img/71796c0b5afbbca61fdeb798c7bdd401_326.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_327.png)

And then on the right hand side blue part tiny tinying signs and loop order。

 the loop order which is CRx K YS， so we follow that CRx K YS。

 it will put the important one in the outer loop since it will be executed less number of times a less important one in the inner loop which is S。

What is their block and tiling size that numerical value during the architecture search？

Here we search 7733 will be the value for y to7 for x is7 r is3 s is3 okay so everything now can be represented in numerical values we can even use the numerical value to search which dimension to parallellyzing space and what is the group order。



![](img/71796c0b5afbbca61fdeb798c7bdd401_329.png)

So that the effect is effectively solved the mapping problem。So this is the overall big picture。

 we have three components， this is a neural network architectureural design。

 this is the hardware architectureural design， this is the mapping that maps the neural network on the hardware and they're all using evolutionary strategies we do not crossover and do the evolutionary strategy to select the best fit with low energy delay product。

This is given an neurooc search space， this is given a mi search space。

 this is given an accelerator search space。And finally。

 we want a model with the lowest energy delay product。

But on the right hand side we can see the follow loop， okay。

 we first generate a hardware and then generate a network。

 then do the matching match this network on this hardware and energy related product。

 update the OFA model and then make we update the final optimizer。And this way。

 let's compare the architecture sizing only。The energy delay product， energy。

 we want a low energy delay， we want a low delay low latency， so the energy delay reduction is good。

So compared with the baseline， archetypeer sizing only can reduce the MDD product by like 20% or2。

1 times。

![](img/71796c0b5afbbca61fdeb798c7bdd401_331.png)

But searching both the sizing and also connectivity of S。



![](img/71796c0b5afbbca61fdeb798c7bdd401_333.png)

And here we have this trade off between energy delayed product。

 the lower the better versus the accuracy， the higher the better。

 we can see that here the hardware aware， hardware architecture search plus the West wall new architecture search together hardware new architecture search together。

 give a better tradeoff， so starting from this point。

 which is the baseline human design and then the hardware architecture research。

 there is the hardware architecture search plus the new architect search。And very interestingly。

 the be flow designed by NAES actually paralyzed the input height and output channel dimension。

 which is very different from the human design。So we will not implement that in the homework。

 just give you some insight that we can do new architecture and hardware architecture search altogether。



![](img/71796c0b5afbbca61fdeb798c7bdd401_335.png)

All right， lastly， having talk about all these techniques， let's look at applications。

 how does the oneful approach apply to the natural language processing， G applications。

 point out application， post estimation， etc。

![](img/71796c0b5afbbca61fdeb798c7bdd401_337.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_338.png)

So we've been mostly talking about CNs at the moment。

 but W4 approach works quite well for transformers， similar to previous design approach。

 we can design a once for all transformer that is a very big giant network containing many subnet。

 we can design a smaller transformer Botannia and a larger transformer for the GPU。



![](img/71796c0b5afbbca61fdeb798c7bdd401_340.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_341.png)

And here we're comparing the latency and also the model size， the latency could be 2。

7 times smaller compared with evolved the transformer and model size can be reduced by 3。

7 times and the search costs is also much lower since we are sharing the same white spot network work。



![](img/71796c0b5afbbca61fdeb798c7bdd401_343.png)

![](img/71796c0b5afbbca61fdeb798c7bdd401_344.png)

Iortize the training costs across different search processes。



![](img/71796c0b5afbbca61fdeb798c7bdd401_346.png)

And there's some speed out。Very would speed up and a flow action。



![](img/71796c0b5afbbca61fdeb798c7bdd401_348.png)

Actually， we also implement this in in out chip。They called a chip to verify the idea。

 so the chip is called a Sptin Sppartin transformer let me turn on the mic so I can hear the voice。

So this is the Spartan transform chip demo， let's play it。Hello everyone。 My name is Henry Wang。

 I'm currently a Ph student at MIT。 I' very glad to show our transfer chip demo for efficient natural language processing。

 So here on the left hand side， we have the GI for this demo。

 We can input some sentence to let the chip process。For example。

 we can input the sentence get me flight ticket from Boston to San Francisco on August 28。

We can use the transformer chip to run the transform models and then return the information about the classification of the sentence and also the classification results of each token。

a little bit so what is' doing here is basically hellello everyone， my name is everyoneong。我放出嚟嗌个我。

Hello everyone。 My name is Henry Wang。 I'm currently a Ph student MI T。

 I'm very glad to show our transform chip demo for efficient natural language processing。

 So here on the left hand side， we have the G I for this demo。

 We can input some sentence to let the chip process。For example。

 we can input sentence get me flight ticket from Boston to San Francisco on August 28。

We can use the transformer chip to run the transfer models and then return the information about the classification of the sentence and also the classification results of each token。

Then we can use the information to call a web browser on right hand side to automatically search for the fat information and return to the G UI。

Besides searching for flying ticket， we can also use it to search for the weather， for example。

 what is the weather in Boston again， we can use the transformer chip to process the sentence and then obtain the location information。

 and then we call the browser again to search for the weather and then return the weather information to the GUI on the left hand side。

Our model can actually support for different size， and all of them will share the same set of weights。

 This technique is called super transformer。 Different size will share the same set of parameters to save the ancient memory footprint。

Here we can reduce the attention， head number and embedding dimension and try to process play music by JO。

If we can see the correct result， and we can call the browser to play the music。

Thank you for watching。play。It's taken trip， so it's city improve to two years for us to work on this process。

together。Actually get a best demo award back design information conference。Okay。

 so not only for natural language processing， but also for 3D vision。 Okay。

 so this is a demo from a self driving car with the。啊，来段来段3 sir so。This is Mu Coskyive。

 this is segmenting different objects， the road that d area， trees， et cea， can see is pretty slow。

 only 3。4 frames per second， but on the autumn on the bottom our her work done our T hot。

But SPV NA sparse point also neuro eye search to search a learn fast architecture that can run sets nine frames per second this get many awards in the LiDar segmentation computations。

 so the basic idea is the same using this one small approach so we a super network that can support fine brain elastic number of channels and also elastic depth。

So initially we can train with depth of three， depth of two and three， depth of one， two and three。

 and similarly for the channels， we share the weight。

And later we do the evolutionary architecture search， given the supertural， we sample a child batch。

 measure the leency and accuracy， and then we sample if it doesn't fit our demand and finally we do the evolutionary architecture search with mutation。

And also crossover with the two parents cross over。To do our evolutionary architecture search。

Very effective in reducing the label。The next once for all for can models， which is only plus again。

Ideally， we want to run this photo editing locally on our laptops or mobile devices like iPad。

 so you can see this is very slow。

![](img/71796c0b5afbbca61fdeb798c7bdd401_350.png)

So here we have this input image， we have this bar。

 we want to put it to the right here we are making her look younger。



![](img/71796c0b5afbbca61fdeb798c7bdd401_352.png)

We can also change other aspects like changing the hair color， etctera。

But it's not quite affordable to run on a mobile device， like three seconds， too slow to run。

So we can now reach gear to design course again。And then we make for a smile。So very fast， only0。

3 seconds。prettyty much in real time。We can also slide the young button to make her look younger。

And change the hair color。And finally way， we can click the finalized button。

To run on the full network only once。And then to get the finalized output， which is of high quality。

し。并此关。好意思。对。Okay。Okay。你说。Yes谢谢。都应该。对。Right， if you only need one model， then just put it。

 but if you need different models like 70 billion parameter， 35 billion， 13 billion，  seven billion。

 3 billion， one billion in one of the whole landscape。Similarly they switch， then this matter helps。

So here we are training the onefall approach for the CA model， different generators。

 smaller sub generator， low cost for fast prototyping we can quickly prototype and finally run this large sub network high quality。

 good for good for finalization。So this demo is open source it's deployable on a MacBook it was done actually three years ago in 2021 at that time you can run a MacBook I at 0。

3 seconds now it I should be much faster feel free to download and play with it。

So next we also have for once4 for post estimation。

So post estimation is basically finding the skeleton， the joints on your body， the arms， the head。

 the legs， the knees， etca。

![](img/71796c0b5afbbca61fdeb798c7bdd401_354.png)

So previously it runs quite slowly， but we can push the frontier to make it about four to five times faster running on the Sdagon mobile CPU。



![](img/71796c0b5afbbca61fdeb798c7bdd401_356.png)

So this is also derived by hardware aware neural architecture search。We have a couple of more demos。

 all of them are open source on our labs， GitHub。For on device person car detection。

 this is on device case and estimation， So gaze estimation is very useful for auto driving cars like in my car if I don't look at the road。

 my car is going to alert me when I'm using the auto pilot mode。

 so basically tracking where looking at if you're not looking at the road the car will send out an arm So this is good useful for driver monitor system DMS。

I in local active by segmentation。Very interestingly， my fall approach also works for quantum AI。

 this is done by my student PhD with Henry one。So we find actually there is a large gap between the theoretical accuracy of doing this an for only four class classification on quantum device versus the measured accuracy gap will reduce a 80% to only 40% so 40% drop of accuracy so what is the reason because quantum circuit is highly suffering very heavily from the noise so not necessarily you have better accuracy a better good results if you put more circuits？

But sometimes you want to put a less number of gates， only put them in the right place， more gates。

 more noise， so we want to start with a super circuit and then sample many sub circuitcus and then search the best sub circuitcuit that meets your accuracy demand。

So we want to search a sub circuit that is very robust to normal who those small magnitude quantum gates。

And as a result we can improve the accuracy from 40% back to 85% right and this was measured on a real。

 you'll see a real quantum here same principle and apply to a different discipline very interesting and that work is open source by Tor quantum。

Okay， very recently， I media adopted oneF approach and applied it to large language models， okay。

 so this is inference adaptive adaptive inference we can generate different models for H100 from bank projects Orient。

 we can have a larger model to fit H100。谁拉着毛都风穿汉。Me model for RX 490 small model for originient platform。

 so multiple models in one sub network for the cloud GQ can run the full network or the desktop。

 you can run a middle network or mobile phone， you run the smallest sub network。



![](img/71796c0b5afbbca61fdeb798c7bdd401_358.png)

From converting a twin model， this is using a very similar approach we can have different dimensions。

For both and layer and also for the attention layer。

 we can have a router to have to determine whether we are running the half the quarter or1/ eighth of the channels。



![](img/71796c0b5afbbca61fdeb798c7bdd401_360.png)

So many in one are flexible large language models。Okay。

 so that's the summary of today's lecture we talk about how do we efficiently do performance estimation。

 how do we' aware NA using prox to this NAS once fall approach in particular once fall approach we we implement that in lab three and finally we talk about NAAS applications in the next lecture we' will talk about a new chapter about knowledge installation。

嘿大嫂，than you for listening。😊。

![](img/71796c0b5afbbca61fdeb798c7bdd401_362.png)