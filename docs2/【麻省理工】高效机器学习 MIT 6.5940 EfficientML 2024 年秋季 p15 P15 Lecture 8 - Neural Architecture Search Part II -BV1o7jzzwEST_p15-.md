# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p15 P15 Lecture 8 - Neural Architecture Search Part II -BV1o7jzzwEST_p15-

Okay，335， let's get started， so today we are going to talk about E MLL lecture8 to discuss neuro architectitect search part two。

 this is the last part of neuro architectect search search。And lab two was released。

 don't forget to check it out， we'll implement those quantization algorithms we learned last week。

So let's continue to talk about neuro architecture search just to review what we want here here we have multiple targets we want to design a network from scratch rather than compressrising the model rather than pruning the model quantizing the model now our goal is to design a model from the beginning。

Ideally， we want a model to be accurate and then have low latency， hydroput。

 low energy and also low storage。In the last lecture。

 we talk about what are the primitive operations， the building blocks and what is NAS， including。

The search space， how to design and narrow down the search space。

 what is the search strategy like reinforcement learning evolutionary strategy， greater search。

 random search through this lecture will talk about efficientff。

 how to efficiently search and efficient architecture。And also hardware awareness。

 including how do we quickly estimate the accuracy having to without having to train the model from scratch each time。

And also how to do hardware awareness， make sure the model is not only high accuracy。

 but also as low it。Zero shortness， can we be able searching a model without even training it？

And also how do we search the hardware architecture and the neural network architecture at the same time。

 the code design， code search， the hardware architecture， and also the neural architecture。

And finally， we are going to apply what we learn about NAS to diverse applications。

 including natural language processing， GN， point cloud， host estimation。

 and also large language models。Okay， so okay， so let's start today's journey。

 starting with accuracy estimation strategies。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_1.png)

So as an overview of the neuro architectureect search pipeline， we started with the search space。

 cell level， network level we discussed in the previous lecture。

 and then we have a couple of search strategies we discussed with great search rather than search replacement learning green descent evolutionary research。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_3.png)

It proposes architecture and then returns the performance and an estimation so now we are going to focus on how do we estimate the performance a quick and efficient performance estimation strategy so that's the focus of today's lecture we'll start by talking about trim from scratch and then kind weight and then a hypernet。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_5.png)

Train from scratch is the easiest we just train a model， find find a model architecture。

 train it to convergence and then see the accuracy and latency right we train a given model from scratch on a training set X evaluate the model on the evaluation validation set that get accuracy R but this is apparently very costly even on Cypher 10 this method need to train tens of thousands of models。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_7.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_8.png)

And that require 22，000 GDP hours that's really expensive， even on such a small data set， at 10。

Not to mention those large scale data sets images that Coco。

 those are actually not considered large scale data data sets these days。 Now we are talking about。

Three trading tokens eight trading tokens those are the large scale we mean by large scale these days。

 so having to train from stretch apparently is not scalable doesn't scale to this large scale training are there other alternatives。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_10.png)

Or we can inherit the weight。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_12.png)

don't retrain the weight， but starting from a pretrain model。

 inherit the weight I to change the architecture on top of。They retrieve the model。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_14.png)

So very famous work is this led to that we can。Inherit the weight from this architecture and then we can change the architecture by having three neurons rather than two neurons here。

 what we do here is actually replicating this node this age in the second human node replicate twice and here we are dividing the weight here by half。

 so we are mathematically equal， but the architecture get adapted。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_16.png)

So this is net to wider net we are having reducing the。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_18.png)

Reducing the weight value， but duplicating the nodes。We can also perform net to deeper net。

 say this is just one layer。 Now we want to。到。Just this is just one layer。

 we want to add another layer on top of it， so what we do we add an identity mapping layer okay so this layer is basically identity mapping。

So even we finite these two layer， the result will be the same。

So in this way we can train on top of this architecture to make a deeper model。

 okay it contains a ability mapping， initialize the layers。

 so effectively without any retreattraining we can change the architecture and maintain the still maintained to mathematical equal mathematical equal as the original model okay so this is net wider net by using divided by two。

 this is one net to deeper net by cascading with identity mapping layer。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_20.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_21.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_22.png)

So in this way， we can inherit the weight from a parent model to reduce the trading cost。

 we get a new architecture and we don't have a retrain model。

Using this net to net approach we can propose new acade factorss。

 so remember previously we talked about using an RNA or LSTM。

 each step we propose an action now the action would be either net to wider net or net to deeper net can either of them so we can effectively carry the weight from the parent model to prevent us from having to return the model。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_24.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_25.png)

Okay， so next approach is to use a hyper network。Iyper network means you have another network that is predicting the weight of your model and the network is you used to predict your weight。

So what does that look like？We are given a network architecture right here， this is the connectivity。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_27.png)

I'm expresseded as a graph。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_29.png)

And then we have initial note embedding means what is embedding embedding means。The features of this。

Now this natural architecture， for example， the NCHW， the channel， the width， the height。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_31.png)

The kernel size， et cetera， so administrator has embedding here we have five layers therefore we have five embeddings。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_33.png)

Not only the feature matters， but also the connectivity also matters。

 so how do we model the connectivity？The connectivity is modeled as graph。

 graph node on the edges define this computation graph， so we can use a graph network。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_35.png)

As it through several layers of graph network。To have a final node embedding since in each step。

 each node interact with the neighbors for this node for this node for this node。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_37.png)

E cetera， each node gets collected information from its neighbors。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_39.png)

So that's the graph when the graph natural from us。The model is the network architecture。

 and then we get a final embedding， we feed it to a shared NP， which is the hyper network to predict。

 to generate the weight。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_41.png)

For the final model okay， so the final model's weight is generated but the hyper network。

We see the hyper network。And input to the hyper network is node embedding is node embedding。

 so the hyper network generates weights based on the model of architecture。

 and we can use gradient descent to update the weights of the hyper network。Not quite widely used。

 we are not going to visit this in the lab， but just give you some idea what people has done to reduce the training costs。

Okay， next checker would be very important very interesting we are having them in the homework。

 so network hardware awareness the model not only want to be we want it to be high accuracy but also should be very hardware efficient。

Okay， so the general purpose model may not be efficient since we have diverse platforms to deploy like a raspberry reply。

 very small memory， GPU， very large memory， large memory footprint， high parallelism。

 CPU maybe lower parallelism， mobile phone， resource constraint， memory constraint。

 battery constraint。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_43.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_44.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_45.png)

So ideal view today， we want to have specialized specialized model for different。

Other platforms like a timing model for rat reply， high paraise model less's turn on call for GPU。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_47.png)

ASpial CPU model and specialized GPU model that takes less energy and less memory footprint。

But you can imagine if we hand design， hand design different models for different other platform that's not automated。

 and that's very costly， right。So how do we cope with that problem？We can。

 since previous neuroarchitect search approach is very expensive， for example。

 NAnet take 48000 GPU hours， even just search on Siharar data set that's like five years if you have a single GPU。

 4000 GPU hours。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_49.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_50.png)

Ds take hundreds of gigabytes of GPU memory if you directly search it on image that。

 so very time consuming， very memory consuming。Therefore， previous work have to utilize a proxy task。

 you can think about it as a simpler simpler task so rather than directly search for a target task and target target platform。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_52.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_53.png)

We find a simple proxy task， a smaller proxy task。For example， the data set can be very simple。

 except for 10， 10 class classification rather than1 thousand class imagenet classification。

Or we can search a small search in a small architecture space。Like very low that。

We can also do just a few ipoCs of training， we don't have to train all the way to converence。

 but we just train a little bit and see if that looks promising， right？



![](img/e3235c6f70ce0e0137b13a43cda8ae34_55.png)

And rather than plug in， the real hardware to measure the latency， we can use the proxy。

 which is flops， flops， and the parameter cons we learn in the first lecture。

 how do we estimate how do we calculate the flops， how do we calculate the parameter number of parameters。

 we use that as a proxy task for the hardware efficiency。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_57.png)

But you can imagine this is not accurate， right， a model that works very well what is a problem with you search separate。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_59.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_60.png)

A model that works on S 10 may not work well on image that since the data side is very different。

And also， if you just search a very small architecture space， you just search one building block。

 use that the same building block on top of each other。

The first couple of layer and the last couple later may not prefer the same building block， right。

 so it's not good to search in a smaller search space。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_62.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_63.png)

And also fewer iOs of training， you may find a model that converges super fast in the beginning。

 but after training after a while， the convergence may not be good。You waste a lot of GPU cycle。

And also we learned that flops and number parameters。

 do they do not directly translate to latency and speed out， so that is also not quite helpful。

So what we do here is to directly search in target task and target hardware without relying on any proxy task。

So how do we save the trading cost？

![](img/e3235c6f70ce0e0137b13a43cda8ae34_65.png)

But also be able to directly search on the target task and also target hardware。So this is one layer。

 input， output。You have managed choices。You can have three by three conve5 by five and density pooling etca。

 right so conventional model just have this weight parameter right。

 but now we introduce these architectural parameters。

 which is the probability of choosing three by three conve probabilitybabil is a using the three by three con probabilities beta etctera。

 we assign assign。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_67.png)

The different choices。One architectural parameter， which is a probability of choosing this particular block。

we have five choices then we have five probabilities， we add up to one。

 and we learn not only the weight of each choice， but also we learn the probability of choosing them。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_69.png)

系。Therefore， we introduce these two updates， one is updating the weight parameter。

 the actual weights in the 3 by three convolution，  three by three by In China or by Al China。

And we also iterativelyly learn those architectural parameters。

 the probability of choosing each path， okay？In a different time。We are bannerizing。

These architectural parameters zero means thrownrun away one means we keep it so that during treating we only have one path in the GPU memory rather than doing a weigh in sum of all these different paths if that is the case we have to compute the activation after three by three activation after five to five activation after putting average them together using the probability then you can consume a lot of GPU memory you have n choices then the GPU memory is on that is not good so we only sample by finalizing the gates finalizing these probabilitybabilities and choose the one that has the highest probability and then only sample one path。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_71.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_72.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_73.png)

Iprove those redundant path based on these architectureural parameters。So in this way。

 we are learning training the model from scratch， which not only these weight parameters。

 but also these architectural parameters。If we have the architect parameter， here is 0。9， 0。1。

 then at inference time， we are going to sample the architecture parameter with the highest probability。

 usually 0。9， then we are going to choose the first choice。

And also mineralizing the architectural parameter allow only one path。

Of the activations will be active。And therefore the memory footprint would be O rather than ON right no matter how many different choice you will have。

 you may have different channel size， you may have different kernel size， if have a lot of choices。

 we want to make sure that tri memory is over1 rather than taking hundreds of gigabytes of deepping memory which is very expensive。

So in this way， getting the architecture is as cheap as training the model in a single pass。

 and you just train the model once you train not only the architecture weight parameter。

 but also train the architecture for parameter。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_75.png)

So we turn this modality from a proxy tasks and eliminated these proxy taskss。

 we can just directly train the model you heard to train the model on a target task and target hardware proposal architecture and update okay。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_77.png)

So that we call this work proxies NA。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_79.png)

Please we don't rely on proxy task or proxy hardware metric like fls okay so proxy task like Sa10 now we can right use image that to train it since the training cost is the same as training the model from scratch。

We no longer have to be constrained with a small architecture search space。

 but we can open up a much larger search space since we are finalizing different choices but keep your memories over。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_81.png)

A capableably。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_83.png)

And also we don't have to contrain on ourselves with only fewer ipos and training。

 or we can do full training。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_85.png)

And also we don't have to just use the flos and parameter number of parameters。

 but also we can profile the latency， we're going to talk about this。

 how do we use profile the latency to directly without having to using the flops。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_87.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_88.png)

Actually using flops is sometimes dangerous so this is this X axis is the max。

 the Y axis is the latest measured on Google Pix1 mobile phone okay。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_90.png)

SoThere are three dots， the blue one is the mobile net V。The orange dot here is the last net。

 the green dot is a mobile net。These two models and those are searched by conventional maths approach they have similar Macs actually they have smaller Macs compared with Bri mobileNe me2 mobileNe2 has roughly 500。

18 mini maxs。But this model on mobile has only about 550。Meium max， it's a smaller max。

But unfortunately， the latency is 190 milliseconds compared with more less than 150 milliseconds。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_92.png)

So max doesn't translate to real hardware efficiency， right we can have lower max。

 but actually higher em， much higher em。Right similar for the GPU platforms。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_94.png)

If you reduce。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_96.png)

The hidden dimension size。From the latency actually doesn't quite change， the Y access is the latest。

Reducing the hidden dimension fairly reduces your density since GPU has very high parallelism。

 if you reduce the workload， it may be hungry， it may not realize any measured of the speed。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_98.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_99.png)

But here if we still the number of layers。The latency will scale proportionally speaking in the number of layers。

 the latency will be scale proportionateally。So similar flops， but very different than is。

 the access is very pretty much the same。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_101.png)

But theiliancy differs a lot。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_103.png)

So Max， the conclusion is that Max doesn't translate to the measured real hardware efficiency。

So we have to be careful using flops as the proxy represents efficiency。Here are some other examples。

 for example， if you change the hidden dimension。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_105.png)

For Ra reply。Reducing the healing dimensions will effectively reduce the v。Well。

 Juputo is not influenced by the hidden dimension。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_107.png)

Since GPU has very large par， even if you have a very large human dimension。

 the GPU is not saturated。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_109.png)

So what does it mean to us we should not use the flops as a reward right since it's not a true reward。

 we want to use the latency， measure the latency as a true reward for your neuroarchural search algorithm。

Thereforeful， we want to measure that it is on the target hardware reply。

But you can imagine measure the laency is very slow， right。

 you can also have a bunch of hardware devices to measure them in parallel。

 but that becomes expensive。We spend quite a bunch to purchase a lot of phones we have a mobile phones。

Build a mobile phone so that you can buy that it is in parallel and it's just getting more expensive。

So what can we do here？We use a machine model， design， design a latency predictor。

Given a neural network architecture to predict how fast it can run。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_111.png)

So here we collect a latency data set。Architecture latency， architecture latency。

 architecture latency， right？

![](img/e3235c6f70ce0e0137b13a43cda8ae34_113.png)

And we build an agency model。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_115.png)

So that given a even neural neural network architecture， we can predict the la。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_117.png)

How fast it can run on this target platform？我 the most simple。

Model for latency providing is basically a lookup table。啊，嗯。Profile， basically。

 everything you have you could encounter。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_119.png)

And then啊 look into index into the lookup table。We build a latency data set which campaigns。

 operator one， latency， operator2， latency， etc cetera。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_121.png)

And then we summarize them in the Excel sheet。And later when we see that layer。

 we just look at that entry in the lookup table。And adding different layer together。

 adding the latency of different layer together。And actually， that works quite well。

 This is the estimated latency， This is the real real latency from this proy is last work。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_123.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_124.png)

Roughly follows y equal to x， roughly follow that line。To be more complicated。

 we can also build a predictor rather than using the lookup table。

So what is the feature for this predictor？A feature for a layer can be like the NCHW。

 the kernel signs， the width， the resolution， different dimensions， etc cetera， given those feature。

 we can use a simple linear model to predict a latency。And actually that also works quite well。

 this is for transformer architecture in this work HAT hardware orware transformformer。

 this is y equal to x， predict latency is very close to the real latency。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_126.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_127.png)

And we are just summing up the latency of different layers together to get a total N to end latency for a particular model。

What could be the problem here？By summing up individual layers laency to get a total it。OnTP use。

You may have kernel fusion， sometimes two kernels might be fused into a single kernel。

 then the latency might be much smaller than adding up these two layers together。

So you have to be careful about the implementation like Teer RRT might do those optimizations behind。

But how do we know if some layer can be fused or not？

The rule thumb is roughly if it is computation intensive kernel。

 followed by another compute intensive kernel， like mightma followed by another mightte Ma。

 usually doest help usually what what helpful is a like matrix multiplication followed by non nonlinear activation function。

 which is memory bond the compute bond versus memory bond。

 memory bond share the same output or input then you can be fused in the previous layer。

 so that' all of the a lot of this class， but thats some insight we we can keep in mind。

 some of the layers can be easily diused。Okay， so let's see how that helps building such specialized hardware aware proxies neural natural architecture。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_129.png)

So this is the Motime too a very well designed， well curated model from Google for mobile devices。

And the red line is basically mobile ads。The x axis is the latency， the lower the better。

 the lower the faster， the y axis is the top on accuracy， the higher the better。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_131.png)

We can see it's about 80% faster。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_133.png)

And compare with。This is not hardware awareness。This is the accuracy。

 this the latency as the smallest latency by the highest accuracy。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_135.png)

Was just showing such small specialized model is really helpful for the latency and accuracy trade off。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_137.png)

Talking about specialization， we want to exam when we are targeting different kinds of platforms。

 a GPU a CPUU or mobile device。And this is the Prox NAS searched target GPU。

We specialize this model for the GPU， and this is a specialized design。

 specialized model for the CPU design， a specialized model for mobile。

And they have different accuracy and let's see what if we apply this GPU model to GPU to CPU and to mobile。

Can you find that。Unsurprisingly， the diagonal latency is the shortest。

showing that the model specialized for mobile works the best for mobile。

 it does not run as fast than the GPU compared with the GPU model。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_139.png)

That makes sense because GPU has very high parallelism and CPU has no parallelism。So of course。

 they prefer different neural architectures。好的。And so here we want to visualize the search process。

During the training process， remember we are learning not only the weight parameter。

 but also the architectural parameter， so different from conventional training where the model architecture stays that the same you are training exactly the same model architecture rule off。

The different dialpos。But now we are training also the new architectures and upon emergeence。

 we can see that the CPU model is much a CPU model is much deeper。

 GPU model much general and GPU model is much wider。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_141.png)

CP model model is narrower， GPP model use a lot of large kernels seven by7di kernel， which is in red。

CPU model actually didn't use MP7 by7 kernel all the kernel are either three by three or five by5 because CPUU has。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_143.png)

Thatice terrorismism。So large kernel may not be more efficient over there。

 but GDP really prefer a low number of kernel calls since each kernel call takes a lot of time。

 therefore it prefers very wide but fewer number of layers， which is indeed the case。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_145.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_146.png)

So let's take a look at the whole process again， starting with the exactly same utilizationization。

And as a graduate learns， the GPU model actually becomes shallower but wider using entrepreneurial GP one go graduate is yellow earth is red and later disappear。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_148.png)

One， only one left。呼关呼。All the until the end， theres are no no large kernel at all。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_150.png)

So it's very interesting to see the search history。

 how the neuralate architecture adapts to different hardware features like terrorismism。Okay。

 so that's for one way to search specialized model for different hardware platforms。

Then the next question is， if we are given a model， given a hardware platform。

 like a GPU or GPU or DSSP or accelerator， we have to repeat the process to search a model for each of them。

 which can get quite positive。How do we further improve the productivity and we just have one single model and then we somehow later we can tweak it to fit GPU to fit TU to fit DSP or a smaller one to the mobile device a module one to fit a GPU。

Comvental methods， like if we have one hardware platform like we are searching model for a phone。

 we spend a couple of duty hours。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_152.png)

By several research ipoOCs training backward， forward， forward and backward， if it is good。

 that we break and then we do some post training optimization after that。When you have more devices。

 we have to repeat。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_154.png)

The process for more devices， we can be， which can be more costly。And if we have many devices。

 they become super expensive to do this process。So in order to eliminate the search cost。

 reduce the search cost for diverse， diverse hardware platforms。

We'll talk about a once for our approach， once for our approach。

 we are going to implement this in lab three， so the lecture here is very important。

So rather than training each network from scratch， like using the using the Pro down approach。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_156.png)

Now we treat multiple models at the saving time。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_158.png)

We have a single model。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_160.png)

That contain many sub networks， which means one small network， they are sparsely activated。

We can have many sub， just like this。We can activate， sparsely activate some sub network。

 a small portion of things。And then we get the latency， we get the accuracy。嗯。

And we want to see if the latency and accuracy meet our conserv。He brings meat， this mat。

 then we finish the search process， you know doesn meet。Then previously， we have to re another。

A train from scratch， train a day or even longer time。Reat this process， which can be possible。

So now we don't retrain it， you just sample another sub network。

 a different sub network from this one small network。

We are going to provide you one of this oncefo network for you during the homework so you can just implement this process and you don't have to train in from scratch。

 give you a one for network， you can sample a sub networkwork and sample it with different sub network。

 get a vancy， measure the accuracy and see whether it meets your demand。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_162.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_163.png)

If not， you can rather than just train it again， you can just settle from the Westfo network。So。

 let's see。What is that good for？So we can train once and get many so that we can reduce the design cost。

 the training cost is amized but not many search user revisions。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_165.png)

This once small network contains managed child networks that are sparsely activated。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_167.png)

So during architecture search， we can search a。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_169.png)

Larger sub network deployed on powerful GP like H100。

 a mid size network deployed on a consumer level GPU like 1490 GPU。

We can also derive a small version。And feed it on a。Mobile GQ， like I media Jason already。8。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_171.png)

And for these three modelss， we don't have to train it from scratch。

And this is particularly helpful for large language model where it's very costly not quite affordable between these models from scratch but now you can build two in one model and get many sub networks to get different get models of different。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_173.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_174.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_175.png)

NowSizes like3 Vs， 7 B，70 B， etc cetera。Similarly， if different chips have different memory streams。

 you can design， deploy a larger sub network。Under larger memory constraints。

 means middle one for a middle sized memory， a tiny one for a tiny memory。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_177.png)

Okay。Or a larger model for a new phone， or old smaller model for an old phone。

So that we can cater for users with different forms， like someone may have iPhone 16。

 some may have iPhone 11， we want to make sure the model can rank on all different platforms。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_179.png)

And similarly， when you leave home in the morning， your phone may be a full battery。

During late night you maybe have very little memory during battery receiving mode。

 so now it can seamlessly shift to this tiny model that is derived from the same once fallen on ice。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_181.png)

So that is the usage。So a principle is just true once and get many， and true once。

And then we get mag， surprisingly we can get1 to the 19th。And for9。

 a surprising a large amount of child networks for free by just training this。Once for on next。

Different child networks are sponsorly activated。But they shared the weights with his wife foreign network and trained them jointly to amortize the design costs。

AndOFA can design specialized models for diverse hardware platforms。

So how do we implement such a onceV network？First of all， let's brainstorm some challenges。

It's hard for a model to operate。independently because they share the weight， right。

How do we prevent different sub networks from interfering with each other。

 how to make sure they can all independently operate。

So let's take a five minute break and then we are going to return to talk about how to implement it。

Okay， welcome back， so let's dive Viper， how do we implement。

 how do we realize this magic once for a network that can help many sub networks independently operate。

😊，So the key part is to progressively prune and shrink the kernel sized depth resolution across different dimensions okay。

 so we want to progressively shrink the kernel size remember we want to support both large model middle model small model therefore we want to do across different dimensions。

 the kernel size， the layer and channel okay from the kernel size perspective。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_183.png)

We started with a seven by seven kernel。And then the inner part of the seven by seven。

 which is five by five。We pass it through a transformation matrix， we learn that matrix。

 and then we can derive。And middle size middle kernel， which is five by five。

And also we can use the inner part of this five by five kernel to get a three by three kernel， okay？

So in this way， we can either operate on a small model， a middle model or a large model。

 they share the weight。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_185.png)

So naively to support these three different sizes， how many parameters you need。

 you need 49 plus 25 plus plus9 right but now we need only one7 by seven 49 weights and these five by five weight ensure let the inner part of this  seven by seven weight of this nine3 by3 weight is the inner subsection subpart of this five by five weight。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_187.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_188.png)

And similarly， we want to apply that weight sharing principle to two other dimensions。

 the number of layers， and also the number of channels implemented in the lab L three。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_190.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_191.png)

So no careful book and， so we start with the full deaths。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_193.png)

Here we have example of depth of four， and then we shrink the depths to support we can have depth of three or depth of four。

 depending on which one we choose。We further shrink the depths by allowing it to the 03 to come directly out of layer2。

 so we can have two layers or three layers only only four layers。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_195.png)

So that's progressively shrinking the number of layers。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_197.png)

From four layers， three layers to two layers。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_199.png)

We can also progressively shrink the number of channels initially we have four channels showing with the full width。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_201.png)

And then we can sort the channel importance by looking at the magnitude of different channel。

We organize them according to the size， the largest one is the blue one we put in the front insert sorted。

 and then if we allow it to have only three channels。

 we pick the first three most important channels。And finally。

 we can also allow it sorted again to pick only two channels then we pick the two largest slides。

The green one，0。85， the yellow one。The yellow one is among the largest one these two。

 so we can either choose the four layers， four channels or three channels or two channels。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_203.png)

So the network becomes very idealgile， where it becomes very elastic， elastic。

 we can have a larger one。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_205.png)

And this larger kernel， larger depths， larger width， we also have a smaller one， smaller kernel。

 smaller smaller depths， smaller width。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_207.png)

But they share the weight， so ultimately you have one the biggest model。

 and then the small model can be derived from that biggest model。Okay。

 so let's see this in animation question here。可以。到。呢系。So the question is。

 how do we make sure the biggest model still works after training the smaller burdens right so during training we sample the larger one。

 larger one and also the smaller one， so both the larger one and smaller one get a chance to be sampled。

So that you can make sure the larger larger one didn't get destroyed。For example， iteration one。

 we may train a bigger， very big one， iteration two， we may treat a smaller one， iteration three。

 we may go back to train a very big one。And there are different sampling and probabilities。

 schedules you can choose。Yes， because we are sharing the weight we are treating a smaller one。

 You're also updating the bigger one。But only the middle parts， yes， you got it。The share the weight。

 so even you heard if you're training the smallest model， the biggest model is still impact。Okay。

 so this is an emission showing that we start with the depth dimension。

 starting with the elastic depths， elastic resolution， so there's another dimension。

 which is the resolution dimension， we can also run randomly sample different input resolution for each batch。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_209.png)

So small resolution made the resolution， large resolution。

 that doesn't impact your weight because different resolution is share the same weights。

 but that impacts your max， your flos。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_211.png)

And also， elastic kernel size。E lastastic steps。And also， elastic wood。

So that's the four dimensions we are going to make it to be elastic， including the resolution。

 the kernel size， the depths and the width， so in the lab we are going to provide you with such a model that already that has already went through this whole triium pipeline。

 so you can directly use it sample different sub networks。

 smaller kernel larger kernel smaller depths， larger depths et cetera to play with it。

 build a latency predictor and given a particular latency just find the best network architecture。

So let's do some roof line analysis to see how this efficiency compare with others so when it is roof line analysis so there are two axis。

 the X axis is the operations per bitete so you fetch one bit of data move one bit of data。

 how many operations operations are able to do on top of that memory。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_213.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_214.png)

So data movement is very expensive， communication is cheap。Ideally。

 we want to fetch one bite of data and we do a lot of operations on top of it。Okay。

 and the Y axis is the G Phps is the GFps to realize the performance。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_216.png)

And initially we are memory bottlene， so as long as we are increasing the operations provide。

We can improve the GOs。And later we are compute on， no matter how many operations provider have。

 we are limited by the number of multipliers and multipliers and others in the platforms。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_218.png)

So this is a rule fly analysis， it looks like a roof， so people call it rule fly analysis。

And let's see how does the once4 network， where is the once4 network located compared with other approach like MNNe mobilenet B2 so this is not human design model。

 this is a N model。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_220.png)

So actually， once for all is。Is having is on the top right corner what does upper right corner mean it means you can achieve higher GOs per second and also right means it has higher operations per bitete。

So this is log access， so the difference is actually quite big。

Okay so bigger operations per bite means that we can make it more memory efficient。

 we fetch one bite of data， we can do more operations on top of it。

 therefore is why it's getting more efficient。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_222.png)

And indeed， we measure the realized efficiency， measure the GOs per second and see one phone as indeed having a higher measured of GOs per second on the Hollywood platform。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_224.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_225.png)

So this is just one hardware platform， let's see how it performs on diverse hardware platforms。

So we measured it on Samsung phone， Google， phone， LG phone，V GPPU， Intel CPUPU and ZningPGA。诶就。

This blue part is the baseline latency versus accuracy， ideally we want a low latency， high accuracy。

 so the top left corner is's good。嗯。Acro all different platforms。

 we can see you once for a network design the sub network actually reside on a better prior to optimal curve with lower latency and also higher accuracy。

All right so。That is the hardware awareness， Any questions so far。

Make sure you unclear about how one smart network works so that we can complete lab three。O。

 no question is in one to talk about zero short nutss。

Only zero shot lastPrevious啊 we have to measure the latency on a hardware platform。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_227.png)

We have to first train it for a while and then estimate the accuracy right which can be quite costly you have to train it which can be quite slow train it for a while and now let's just look at the model without having to train it let's just see eyeball tracking no actually eyeball tracking we just see some some of the featuress itself without having to train it just look at it look at the analyze architecture。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_229.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_230.png)

And see and guess whether we can have a good accuracy or not。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_232.png)

I will introduce two pieces of work， then not and also grab。The motivation is basically。

 don't train it and tell me the accuracy what it is promising。So zero short nuts z nutss here。

 there's one heuristic saying that we just randomly initialize the input for the following normal distribution。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_234.png)

And then we add a small perturbation and produce small perturbation to obtain a new X。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_236.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_237.png)

And then we initialize all the weights of a neuralnaural architecture using normal distribution。

 so random weights basically。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_239.png)

So this paper is saying that the difference between these two inputs。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_241.png)

The two inputs will generate two outputs in FX and FX S。

And the difference between these two output outputs。If the model is good。

 then the difference should be large okay if the input is difference is the same good model should be sensitive to the input of preservation。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_243.png)

Change the input a little bit， the output should dramatically change。

And it propose a second heuristic， which is saying the batch normalization。

 so we want to have fine the average for the variance in the baby layer and we add them up together。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_245.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_246.png)

We want to encourage the variances to be large， otherwise different inputs they have exactly the same output that's not good if the variance is large。

 then consider design architecture to be good。But frankly。The architecture is just a tip of iceberg。

 the way it also matters， so here is using the random weight so it's very core screen eyeball checking not very。

But actually the result works quite well atm releasing this paper just look at given the perturbation of the input。

 if the output changes a lot， then that's good for different batches， if the variance is big。

 then that's good。Another hereic red sign so red sign this paper basically says a good model will have very dense very dense sampleized local mini mark so the two local mini mark should be very close rather than very far away from each other。

Therefore， the distance between the local minima should be closes to each other okay and therefore there's a higher probability that the gradients in different sample you try different samples。

 x1， x2， x1 and x2 should have the same sign。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_248.png)

Calculating the sign is very cheap right so in this area in the red area the sine of the gradient here is negative here is positive they are of the different signs and if they are in the scoring region here both of them have negative gradient here both of them have positive gradient right？

So if you sweep， starting from here and here， the the green region will have the same sign。

The red region we have different sign。A good model， which have very close local minimum。

Should have a very large portion of them in green， which means the gradient should be of the same sign。

 that's why this works name is hot gra sign so we can。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_250.png)

Use this approach to count the number of entries that has given the same gradient。And if the。

 if the sum is large， that means a lot of region is is green and it's good。

So those are very two very simple heuristics， you don't never train the model。

 you just feed it with some input and then calculateulate either the output difference or the variance of the normalization layer or the sign of the gradient。

Okay。So far we talk about given a hardware platform， maybe the hardware platform is fixed。

 how do we optimize the neural network architecture？And now also， let's open the box。

 say you can also。Have the freedom to design the hardware architecture by yourself design an AsI by yourself。

 you open up the box， you can now design both the hardware architecture and also the mineral architecture。

 how do you design them together？So that's the next chapter， which well not do in the lab。

 but it good it might be eye opening。Let's talk about the new chapter about neural architecture。

 neuralacccelerator architecture search， and search not only the neural architecture。

 but also the accelerator architecture。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_252.png)

So we propose a hardware design， we then propose a neural architecture design。

 we collect some feedback running this neural network on this hardware。

 and then we it tweak the hardware and also the neural network patch。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_254.png)

That true。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_256.png)

Where this look。And here are this is showing we can tweak the neural architecture。

 this is showing we can tweak the accelerator architecture。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_258.png)

And both of them both designs are important to enable specialization。

 that now we talk about specialized architecture runs the most efficiently。

So let's see what is the design space， we must have a much bigger design space including both the newer architecture and also the hardware architecture。

 much larger design space。左那的kity measures呢？We have three components， right。

 we have the hardware accelerator。W which include several hardware dimensions。

 like the local buffer size， global buffer size， the number of processing evidence。

 the number of PEs。The size of the compute array， the P connectivity。On the compiler side。

 which compiler maps the neural network on the hardware excalgerator。

 so on the compiler side we have the loop orders， right which loop to process first。

 which loop to process later， loop ti size and data flow right。A neuroex perspective。TheN of layers。

 number of channels， kernel size， whether we have bypass an input and output and weight quantization precision。

So that's a pretty big design space。And the solution is to ideally。

 we want to do have one optimization loop， this is one optimization loop to search both the accelerator architecture and also the neural architecture。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_260.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_261.png)

So let's see first， the accelerator architecture， which include a pretty large design space。

 including categorize them into two categories， one category is the size related。

 which is very simple， like the buffer size， local buffer size， global buffer size。

 the number of pes。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_263.png)

And second one is slightly more challenging to represent in numbers。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_265.png)

The P connectivity， which one connects to which one。

And our key idea is to talk about how do we put those non numerical numbers like the connectivity。

 you cannot easily represent connectivity by a number and how do we design those non numerical values。

So when we are mapping the。A couple of operations like a follow up operations into the hardware roughly there are two categories okay one is temporal mapping one in spatial making so what is difference here spatial making here means you can process them in parallel in space like here I have 10 multipliers then I can process 10 multiplications in parallel one to34 five so physical theyre in the space or I have two by two by5 you have 10 multipliers so that's called spatial parallels you can parallelze them in space theyre executed inly。

And also you have temporal temporal mapping， okay， that means you can process them sequentially。

 okay， but in different order， so what determines the order。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_267.png)

The sequence of the fall loop determines the order okay so in this case we have two lines of code indicates hardware parallelism paralyzing space for the M and n dimension range 16 and 16。

 so probably you have 256 modpliers here， you can concurrently execute them paralyzze them in space。

And then you have this temporal， including both the tiding， what is the tile size。

 what is the order determines in which sequence do you map these loopop powders in the temporal dimension。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_269.png)

So here we categorize them into two parts， one is the hardware including a vector。

 the algorithm is the mapping including vector。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_271.png)

One is related to the hardware， one is related to the compiler， the mapping。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_273.png)

Some of them is not a numerical， right？

![](img/e3235c6f70ce0e0137b13a43cda8ae34_275.png)

The parallel dimension choosing which dimension to para in space okay。

 so that's not easy to be represented by a single value and the look order also may not be very straightforward to represent similar to like the tile size number of P in the kind size。

 which is just a single value， this is not。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_277.png)

by youwei is to do index based ind， for example， zero means。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_279.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_280.png)

Sequence CR XY KYS1 means C XY RSK， C means channel XY means the height than width。

 RRS means the kernel size and width K means the number of kernels。

 but actually it doesn't convey any physical information why this one has a larger index than this one doesn't make sense。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_282.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_283.png)

So when we do try to make it have some meaning， we first fix the dimension position in the encoing vector。

 for example， the first position is k is second position C。Colonnal size， channel number。

 height and Wood， Col external Y。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_285.png)

And itper number of kernels， numbertris， height and width。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_287.png)

Theternal science。And then we assign numerical importance to these dimensions。

So this is numerical value， the importance is a numerical value。And then we can sort them。

 right we can pick the two largest one。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_289.png)

C is the largest one， A is the largest one， so that if we want to paralyze them in space。

 we for sure we want to paralyze the dimensions with the high with the high importance。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_291.png)

So we choose the first two dimensions， the dimension size is two low， and we choose the top two。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_293.png)

And for the most order。We assigned the most important dimension as the utterermost since it will be iterated last number of times。

And we put the least important in the inner side， the inner loop， which will be very hot。

 which will be executed many times more time consuming。

 therefore we put it in the less important in the innermost。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_295.png)

So in that way， we can convert these parallel dimensions in versus the loop order， which。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_297.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_298.png)

Our definition is not numerical value， we turn into numerical representation by sorting them。

So let's see if the search result give you this number like。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_300.png)

The parallel dimension will have two dimensions， and then we choose。

The first two most important dimensions C and K since their importance value is the largest six and4。

 we put them as the parallel four， we have these two rows of parallel four we are paralyzing in space。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_302.png)

Since this is related to the hardware improvement matter。

 which dimension mention do we paralyzze in space rather than serialize in time？



![](img/e3235c6f70ce0e0137b13a43cda8ae34_304.png)

And then the parallel dimension cs of size two will pick these two most important ones。

And then the dimension sizes is given by 16， then we fill in 16 and 16 in the entry here。

 meaning that when we altogether have 16， this dimension 16， that dimension multiply them together。

 you have 256 bodypliers。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_306.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_307.png)

And then on the right hand side blue part tiny tinying signs and loop order。

 the loop order which is CRx K YS， so we follow that CRx K YS。

 it will put the important one in the outer loop since it will be executed less number of times。

 a less important one in the inner loop which is S。

What is their block and ti and size that appear in numerical value during the architecture search？

Here we search 7733 with Q limit the value for y to 7 for x is7 r for3 s is3 okay so everything now can be represented in numerical values we can even use the numerical value to search which dimension to parallellyzing space and what is the group order。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_309.png)

So that the effectively solved the mapping problem。So this is the overall big picture。

 we have three components， this is a neural network architectureural design。

 this is the hardware architectureural design， this is the mapping that maps the neural network on the hardware and theyre all using evolutionary strategies we do mutation cross over and do the evolutionary strategy to select the best fit with low energy delay product。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_311.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_312.png)

This is given neuro architect search space， this is given a making search space。

 this is given an accelerator search space。And finally。

 we want a model with the lowest energy delay product。

But on the right hand side we can see the follow loop， okay。

 we first generate a hardware and then generate the network。

 then do the matching match this network on this hardware and the energy related product。

 update the OFA model and then later update the final optimizer。And this way。

 let's compare the architecture sizing only。The energy delay product， energy。

 we want a low energy delay， we want a low delay low latency， so the energy delay reduction is good。

So compared with the baseline， arche sizing only can reduce the MDD product by like 20% or 2。1 times。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_314.png)

But searching both the seizing and also connectivity of small。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_316.png)

And here we have this tradeoff between energy energy delay product lower the better versus the accuracy。

 the higher the better， we can see that here the hardware aware。

 hardware architecture search plus the West wall new architecture search together。

 hardware neuro architecture search together， people a better tradeoff， so starting from this point。

 which is the baseline human design and then the hardware architecture research。

 theres the hardware architecture search plus the new architecture search。And very interestingly。

 the data flow designed by NES actually paralyzed the input height and output channel dimension。

 which is very different from the human design。So we will not implement that in the homework。

 just give you some insight that we can do new architecture and hardware architecture search altogether。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_318.png)

All right， lastly， having talk about all these techniques， let's look at the applications。

 how does the oneful approach apply to the natural language processing， G applications。

 point out application， post estimation， etc。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_320.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_321.png)

So we've been mostly talking about Cs at the moment。

 but W4 approach works quite well for transformers， similar to previous design approach。

 we can design a once for all transformer that is a very big giant network containing many subnet。

 we can design a smaller transformer Botania and a larger transformer for the GPU。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_323.png)

![](img/e3235c6f70ce0e0137b13a43cda8ae34_324.png)

And here we're comparing the latency and also the model size， but latency could be 2。

7 times smaller compared with evolved the transformer and model size can be reduced by 3。7 times。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_326.png)

And the search cost is also much lower since we are sharing the same West spot ice work。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_328.png)

Iortize the training costs across different search processes。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_330.png)

And there's some speed out。Very good speed up the fl of infection。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_332.png)

Actually， we also implement this in out chip。They out a chip to verify the idea。

 So the chip is called a Sptin Spin transformer let me turn on the mic so I can hear the voice。

So this is the Spartan transformoma chip demo as plate。Hello， everyone。 My name is Henry Wang。

 I'm currently a Ph student at MI T。 I very glad to show our transform chip demo for efficient natural language processing。

 So here on the left hand side， we have the GI for this demo。

 We can input some sentence to let the trip to process。For example。

 we can input the sentence get me flight ticket from Boston to San Francisco on August 28。

We can use the transformer chip to run the transform models and then return the information about the classification of the sentence and also the classification results of each token。

little bit so what is's doing here is basically hellello everyone， my name is Henryong。我复出嚟我。

Hello everyone。 My name is Henry Wang。 I'm currently a Ph student MI T。

 I'm very glad to show our transform chip demo for efficient natural language processing。

 So here on the left hand side， we have the G I for this demo。

 We can input some sentence to let the trip process。For example。

 we can input the sentence get me flight ticket from Boston to San Francisco on August 28。

We can use the transformer chip to run the transfer models and then return the information about the classification of the sentence and also the classification results of each token。

Then we can use the information to call a web browser on right hand side to automatically search for the fat information and return to the GUI。

Besides searching for flying ticket， we can also use it to search for the weather， for example。

 what is the weather in Boston again， we can use the transformer chip to process the sentence and then obtain the location information。

 and then we call the browser again to search for the weather and then return the weather information to the GUI on the left hand side。

Our model can actually support for different size， and all of them will share the same set of weights。

 This technique is called super transformer。 Different size will share the same set of parameters to save the ancient memory footprint。

Here we can reduce the attention， head number and emdding dimension and try to process play music by JO。

Here we can see the correct result， and we can call the browser to play the music。

Thank you for watching。就飞。It's technology， so it's city proof two leaders for us to work on this process。

Together。Actually get a best demo award back design conference。Okay。

 so not only for natural language processing， but also for 3D vision。 Okay。

 so this is a demo from a self driving car with the。啊，来点来点 sensor sir so。This is Muco。

 this is segmenting different objects， the road that drive area， trees， etc ceter。

 can see is pretty slow， only 3。4 frames per second。

 but on the autumn on the bottom our our work done our T hot here。

But as PV NA sparse point also neuro architecture search to search a very advanced architecture that can run nine frames per second。

 this get many wallss in the LiDar segmentation computations， so basic idea is the same。

 using this one small approach so we super network that can support fine brain elastic number of channels and also elastic depth。

So initially we can train with depth of three， depth of two and three， depth of one， two， and three。

 and similarly for the channels， we share the weight。

And later we do the evolutionary architecture search， given the supert， we sample a child batch。

 measure the leency and accuracy， and then we sample if it doesn't fit our demand and finally we do the evolutionary architecture search with mutation。

And also cross over with the two caves cross over。To do an evolutionary architecture search。

Very effective in reducing the laency。Next once for all for can models， which is an plus again。

Ideally， we want to run this photo editing locally on our laptops or mobile devices like iPad。

 so you can see this is very slow。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_334.png)

So here we have the simple image， we have this spark。

 we want to pull it to the right here we are making her look younger。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_336.png)

We can also change other aspects like changing the hair color， etctera。

But it's not quite affordable to run on a mobile device， like three seconds， too slow to run。

So we can now wait reach gear to design course again。And then we make for a smile。So's very fast。

 only 0。 three seconds。prettyty much in real time。We can also slide the young button to make her look younger。

And change the hair color。And finally， we can click the finalized button。

To run the food network only once。And then to get the finalized output， which is of high quality。し。

Thank。并此关于。不起。对。嗯。你说。嗯谢谢。我应该。对。Right， if you only need one model， then just point it。

 but if you need future models like 70 billion parameter， 35 billion， 13 billion，  seven billion。

 three billion， one billion in one of the whole landscape。Similarly they switch。

 then this model helps。So here we are training the onefor approach for the CA model。

 different generators， smaller sub generator， low cost for fast prototyping。

 we can quickly prototype and finally run this large sub network high quality。

 good for good for finalization。So this demo is open source it's deployable on a MacBook it was done actually three years ago in 2021 at that time you can run a MacBook about 0。

3 seconds now it I should be much faster， feel free to download and play with it。

So next we also have for14 answer for post estimation。

So post estimation is basically finding the skeleton， the joints on your body， the arms， the head。

 the legs， the knees， etca。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_338.png)

So previously it runs quite slowly， but we can push the front here to make it about four to five times faster running on the samedagon mobile CPU。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_340.png)

So this is also derived by hardware aware architecture search。We have a couple of more demos。

 all of them are open source on our labs， GitHub。For on device person car detection。

 this is on device case and estimation。 So gaze estimation is very useful for auto driving cars like in my car。

 if I don't look at the road， my car is going to alert me when I'm using the auto pilot mode。

 So basically tracking where I looking at if you're not looking at the road the car will send out an arm。

 So this is good useful for driver monitor system BMS。I and in local mountain by segmentation。

Very interestingly， my4 approach also works for quantum AI。

 this is done by my student PhD and Henry one。So we find actually there is a large gap between the theoretical accuracy of doing this unus for only four class classification on quantum device versus the measured accuracy the gap will reduce a 80% to only 40% a 40% drop of accuracy so what is the reason because quantum circuitulate is highly suffering very heavily from the noise。

 so not necessarily you have better accuracy a better good results if you put more circuits。

But sometimes you want to put a less number of gates， only put them in the right place， more gates。

 more noise， so we want to start with a super circuit and then sample many sub circuitcus and then search the best sub circuitit that meets your accuracy demand。

So we want to search a sub circuit that is very robust to normal who those small magnitude quantum gates。

And as a result， we can improve the accuracy from 40% back to 85% right and this was measured on a real。

 you'll see a real quantum here same principle that apply to a different discipline very interesting and that work is open source by To quantum。

Okay， very recently I media adopted oneF approach and applied it to large language models。

 okay so this is inference adaptive adaptive inference。

 we can generate different models for H100 broken bank for the Orient。

 we can have a larger model to fit H100。谁拉着毛的风穿汉是。Me model for RX 49 small model for originient platform。

 so multiple models in one sub network and for the projectQ can run the full network or the desktop。

 you can run a middle network or mobile phone to run the smallest sub network。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_342.png)

From converting a train model， this is using a very similar approach we can have different dimensions。

For both and layer and also for the attention layer。

 we can have a router to have to determine whether we are running the half or the quarter or1 eighth of the channels。



![](img/e3235c6f70ce0e0137b13a43cda8ae34_344.png)

So many in one flexible large language models。Okay。

 so that's the summary of today's lecture we talk about how do we efficiently do performance estimation。

 how do we aware nows using pro this NAS once for approach in particular once fall approach we we implement that in lab three and finally we talk about NAAS applications in the next lecture we' will talk about a new chapter about knowledge installation。

嘿大嫂好，thank you for listening。😊。

![](img/e3235c6f70ce0e0137b13a43cda8ae34_346.png)