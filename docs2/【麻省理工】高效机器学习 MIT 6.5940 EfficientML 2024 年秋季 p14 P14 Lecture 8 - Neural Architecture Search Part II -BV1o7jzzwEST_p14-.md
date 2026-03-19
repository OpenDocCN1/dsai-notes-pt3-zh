# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p14 P14 Lecture 8 - Neural Architecture Search Part II -BV1o7jzzwEST_p14-

Okay， it's 335， let's get started。So today we are going to talk about efficient ML lecture 8 to discuss neuro architectureectural search。

 part two， this is the last part of neuro architectureural search。And lab2 was released。

 don't forget， we'll check it out， we'll implement。With quantization algorithms we learned last week。

So let's continue to talk about neuro architecture research， just review what we want。

 here we have multiple targets。To design a network from Swch rather than compressrising the model。

Rather than appccruning the model， quantizing the model an hour ago is to design a model from the beginning。

Ideally， we want a model to be accurate and then have low latency， height input。

 low energy and also low storage。In the last lecture。

 we talk about what are the primitive operations， the building blocks？And what is that， including。

The search space， how to design and narrow down the search space。What is the search strategy？

It really possible learning， evolutionary strategy。Were in to search， random search。

 so this lecture will' talk about efficient， how to efficiently search an efficient architecture。

And also hardware awareness， including how do we quickly estimate the accuracy having to without having to train the model from scratch each time。

And also how to how we aware that， make sure the model is not only high accuracy。

 but also has low limits。Zero shot gas can we enable searching the model without even traininging it？

And also， how do we search the hardware architecture？

The neural network architecture at the same time， the code design， code search。

 the hardware architecture， and also the neural architecture。And finally。

 we are going to apply what we learn about math to diverse applications。

 including natural language processing， GN， point cloud， post estimation。

 and also larger language models。Okay okay， so let's start today's journey。

 starting with accuracy estimation strategies。So as an overview of。

Un architectureecture search pipeline， we start with the search space。So available。

 natural level we discussed in the previous lecture。

 and then we have a couple of search strategies we discussed with the brain search。

 random search reinforce learning， brain Descent and pollution research。

It propose is architecture that returns the performance。

And estimation So now we are going to focus on how we estimate the performance。

Quick and efficient performance estimation strategy。That' the focus of today's lecture。

We will start by talking about trim from scratch。开 the会 and then have network。

Ting from scratch is the easiest， we just train a model， find a model architecture。

 train it into convergence， and then see the accuracy of limits。We we a human mo from fresh。

Tining set actually value the model on the evaluation validation addition set， like at accuracy R。

But this is apparently very costly， even on Cypher 10。

 this method to train tens of thousands of models。And that require 22000 GPU hours。

 That's really expensive， even on such a small data set， etc ceter 10。

Not to mention those large scale data sets image that Co those are actually not considered large scale data data sets these days。

 Now we are talking about。Three tri tokens， tris eight treated tokens。

 those are have large scale we need by large scale these days。

 So having to train from scratch apparently is not scalable it doesn't scale to this large scale training。

Are there other alternatives？So we can inherit the weight don't retrain the weight。

 but starting from a pretrained model， inherit the weight。

 try to change the architecture on top of a pretrained model。So a very famous work is。Its map to map。

 and you can inherit the weight from this architecture。And then we can change the architecture by。

Having three neurons rather than two neurons here， what we do here is actually replicated this node。

 the second hidden node replicate twice。And here we are providing the weights here by half。

So they are mathematical or equal， but the architecture gets adapted。So this is net to wider net。

啊 we are having。Reducing the。Reducing the weight value by duplicating the nose。

We can also perform much to deeper that。Say this is just one layer。那我们呢啊。

This is just one layer we want to add another layer on top of it， so what we do。

 we add an identity mapping layer， okay so this layer is basically identity mapping。

So even if you have this two layer。The result will be the same。

So in this way we can train on top of this architecture to make a deeper mode。

 it contains a epimatic initialized the layers， so effectively without any rettriium we can change the architecture and maintain the mathematical still maintain to mathematical equal mathematical equal as the original model so this is not to wider net。

By using divided by tools。To deep that by cascading with the identity American layer。So in this way。

 we can inherit the weights from a parent model to reduce the training cost。

 we get a new architecture or we don't have to re training costs。

Using this net to net approach we can propose new architectures。

 so remember previously we talked about using other RNA or IOCM， each step we propose some action。

 now the action would be either net to wider net or net to deeper net。

Do either of them so we can effectivelyher the weight from a parent model to prevent us from having to retrain the model。

So that's approach is to use a hyper network。Hypernet means you have another network that is predicting the weight of your model and the network is used to predict the weight。

そ到三分。We are given at network architecture right here， this is the connectivity。WeExpri as a graph。

And then we have the initial look embedding is。 So what is embedding， embedding means。

The features of。Now this network architecture， for example， the NCHW， the channel， the width。

 the height。Cnal size。This veryた。呢路你下。5 layers。花唔。Not only the future matters。

 but also the connectivity also matters。We model the connectivity。

So connectivity is modeled as a graph。Gra node。And the edges define this computation graph。

We can use as a graph。Ha it through several layers of graph。就系我翻到 know明。In each side。

 or each node interact with neighbor。To node， this node， node， et cetera。

 each node can collect information from its neighbors。So， that's。The graph。With a graphite from that。

The models and that's what I。And we get assign value， we feed it to a shared NP。

 which is a hyper network to pre to generate the weight。课嘅快系冇。And the final models weight。

 it's generated by the hyper。咋回れ。Inputs happenper来说。It is no in。这是弄明白。

So the hypernet generates weights based on the model architecture。

 and we can use gradient descent to update the weights of the hyperne。Not quite widely used。

 we are not going to visit this in the lab， but just give you some idea what people has done to reduce the training costs。

Okay， next chapter will be very important and very interesting。So that's true hardwarem wear max。

Even model not only to be， we want it to be high accuracy。

 but also it should be very hardware efficient。系 so。A gender purpose model may not be deficient。

We have diverse platforms to deploy like a high， very small memory， GPU， very large memory。

 footprint， high parallel， CPU， maybe lower parallelism， mobile phone， resource can drink。

 memory can drink， battery can drink。So idealally， we want to have specialized model for different。啊。

还是盼。tiny model or high high parallel model， as Colonel Hall， would if you。specialized CPU model。

 specialized GP model that takes nice energy and nice memory footprint。

But you can imagine if you hand design， hand design different models for different hardware platform that's not automated。

 and that's very costly。So how do we cope with that problem？We can。

 since previous neural architecture search approach is very expensive， for example。

 does that take 400，000 GP hours， even just search on Cyar data set， that's like five years。

 if you have a single GPU， 400，000 GPU hours。Ds take hundreds of gigabytes of GPU memory。

 you can directly search it on the imageNe， so very time consuming， memory consuming。Therefore。

 previous work have utilized a proxy task。You can think about it as a simpler， simpler task。

Rather than directly search for a target task and target has platform。We翻的啊。A proxy task。

 a smaller proxy task。For example， the data set can be a very simple， exc。

 pen class classification will than a thousand class imagenet classification。

Or we can search a searching in the small architecture space。Like very low debt。

We can also do just a few ipocs of training。 We don't have to train all the way to convergence。

 but we just train a little bit and see if that looks promising。

And rather than plug in the real hardware to measure latency， we can use the protein， which is flops。

Faws。The parameter counts we learned in the first lecture。

 how do we estimate how do calculate the flos， how do we calculate the parameter number of predators。

We use that as a proxy task for the hardware efficiency。But you can imagine this is not accurate。

A although that works very well， what is the problem me if you search them？

A model that works well on Sron 10 may not work well by E X。And then outside is very different。

And also， if you to search a very small attached space， if you search one duty block。

 you stack the same building block right。Tal of each other。

The first couple later and the last couple later may not prefer the same building block。

So it's not good。Soarchly in a smaller search space。And also fewer is of training。

 you may find a model that converges super fast in the beginning， but after training after a while。

 the convergence may not be good。He wasted all of GPU is。

And also we learned that fs and number parameters， they do not direct a translate to stency and speed up。

 so that is also not quite helpful。So what we do here is should directly search a。

Target has and target how without relying on any pro task。So how do we save the training cost？

But also be able to directly search target tasks。So this is one layer， our input output。

You' have better choices。You can have three by three count， by5 identity density reporting， etca。

So conventional model just have this。我。But now we introduce these architectural parameters。

 which is the probability of choosing threeta3 comm， probabilitybabil is alpha。

 choosing the three3 column probabilitybabilities beta， ettera， assign assign。Of different choices。

One architectural parameter， which is a probability of choosing this for particular。Block。

And we have five choices， then we have five probabilities， they add up to one。

 and we learn not only the weight of each choice， but also we learn the probability of choosing them。

Therefore， we introduce。two are updates， one is updating the weight printer。

 the actual weights in the 3 by3 conclusion， 3 by3 by input channel by output channel。

And we also iterative the learn。Those architectural factors， the probability of choosing each path。

In at time。问一下法外。These architectural parameters， zero means provenrun away。

 one means when we keep it so that during treating。

 we only have one path in the GPU memory rather than。Do I wake up all these different paths。

If that is the case， we have to compute。The calculation after3 by3 calculation after 5 by5 calculation after putting average together。

 using the probability， then you can consume a lot of GPO memory， you have n choices。

 then the GPO memory is all n that is not good， so we only sample by finalizing the gates。

 finalizing these probabilities。And choose the one that has a highest age probability。

And then诶 only sample安。And crew those redbut path based on this architectural prime。所以 this way。

We are learning traininging the model from scratch which not only。Now only is weight to predators。

But also these architectural predator。If we have the architectural parameter。here is 0。 is 0。1。

 then at inference time， we are going to sample the architectural parameter with the highest probability。

Because for nine other truth。The the first， the first choice。

And also finalizing the architectural parameter。Alow only one pass。Of activation to be active。

And therefore， the memory footprint would be O1 rather than O。

 no matter how many different choice you have， you may have different channel size。

 you may have different kernel size。We have a lot of choices。

 we want to make sure that treating memory is over rather than taking hundreds of gigytes of deepping memory。

 which。Expensive。So in this way。Getting the architecture is as cheap as training the model in a single pass。

 and you can train the model once you trade not only the architecture for away parameter。

 but also train the architecture。So we turn this mod from a proxypath。

And eliminateinated this process it has， you can just directly train the model。

You're run doing the model on a target task and target hardware。Proposal architecture。

So that we call this work approximate maps。Proxy is that we don't rely on proxy task for a proxy hardware metric like flops。

So prop it has like Cy 10 now we can directly use image network。

Since the training cost is the same as training the model from scratch。

We no longer have to be constrained with a small architect search space。

But we can open up a much larger such space since we are finalizing different choices。

 a particular memory is all。助ける。And also， we don't have to contrain on ourselves with only a fewer eye。

我 we can do付除为名。And also， we don't have to just use the flaws and number of parameters。

 but also we can profile the。And talk about this， how do we use profile of agencyt？To啊。

Directly without having to using the box。Actually， using flops is sometimes dangerous。So， this is。

The X axis， is the max， the Y axis。They the latest measured on Google Pix 1， mobile phone。

So there are three dos。如 are this over to。The orange out here is mass mat。不到で个 mobile。

These two models。Those are searched by conventional math approach。They have similar life。

I could have smaller bags。This说默默 that me to。Over I2 has roughly 500。18 mini max。But。

This model of mobile has only about 500。Mini max。Smaller land。But unfortunately。

 the litency is like 90 meiseconds。おな。Lasts than 150 meetings I guess。So， max doesn't。

Translate to real hardware efficiency， right， We can have lower maxs， but actually higher la。

 much higher la。Similar for the GPU platforms。If we reduce。The低 dimension size。From。

The laency actually doesn't quite change why accesses that it is。Reding the human dimension。

 it barely reduces our theyancy。Since GPU has very high parallelism， if you reduce the workload。

 it may be hungry， you may not realize any measure the speed up。

But here you mean scale the number of layers。But it is it will scale proportionateally。

It's giving a number of layers， but anything be scaled proportionateally。So similar flops。

 but better different areas。That excess。四万毫升。Of the。difference a lot。So Max。

 the conclusion is that Max doesn't translate to the measured real hardware efficiency。

So we have to be careful using flps as the proxy to represent efficiency。

Here are some other examples， for example， if you change the hidden dimension。For us third pie。

Reducing the he dimension will effectively reduce。Well。

 GPPU is not influenced by the hidden dimension。So Ju has very large par of， even if you have a。

In dimension mentioned， the detail is not saturated。So what does it mean to us。

 we should not use the fs as a reward right since it's not a true reward， we want to use the la。

Measure the latency as a true log for your neuro architect search algorithm。Therefore。

 we want to measure the laency on this target target。

But you can imagine measure the latency is very slow。

You can also have a bunch of hardware devices to marry them in parallel， but that becomes expensive。

看到拍了 bit快了 bunch。Two questions about the phones we have a mobile phone。

Build a mobile phone so that you can matter anything in parallel。

 but thats just get it more expensive。So what can we do here？我用怎么设那 modeldeser。

 design a latency predictor。Given a neuralna architecture to predict how fast it can run。So， here。

We collect a laency data。Architecture agencytency， architecture agencytency。

 architecture agencytency。And we build any anything involved。So that they a new neuro， neuro network。

We can predict the la。How fast it can run on this target platform。我 the most simple。

Model for lit providing is basically a look at people。啊，有。

Profile basically everything you could have you could encounter。And then。

Looking to index into them table。Weview the latency data， which contains operator  one。

 laency operator 2， latency， etca。And then we summarize them in the exc sheets。

And later when we see that layer， we just。Look at that entry in the lookout table。

And adding different layer together， adding the latency of different layer together。

And actually that works quite well。楽め。呃，6呃6。Our problem is Pro is Na。ItRough follows y equal to x。

 roughly follows that y。To be more complicated， we can also build a predictor rather than using the lookup table。

So what is the feature for this predictor？A feature for a layer can be like the NCHW。

 the current of science， the width， the resolution。Different dimensions。

Can you give with the feature， you can use America simple linear model to predict the latency。

And actually that also worked quite well。This is for transformformer architecture in。

have get awareness transform former。This is why couple lives predict agencyancy in very close。

And we are just summing up the latency of different layers together to get the total n to and the latency。

model。What could be the problem here？By summing up individual layers licenseency get a total litency。

On GPUs， you may have kernel fusion， sometimes two kernels might be fus into a single kernel。

 then the dataency might be much smaller than adding up these two layers together。

So you have to be careful about the implementation like Tensor RRT by doing thoseion optimizations behind。

But how do we know if some later can be fued or not？

The rule thumb is roughly uous computation intensive kernel。

 followed by another compute intensive kernel。 like Mac Ma。

 followed by another Mac Ma usually doesn't help。 Usually what help was's helpful is a matrix modification followed by a。

Mline activation function， which is memory bonded。Compute bomb versus a memory bomb， the memory bond。

 share the same output or input， then it can be used even previously。So that's all of the business。

All of his class， but that some insight。To keep in mind， some of those can be easily filled。Okay。

 so let's see how that helps building such specialized hardware aware propertiess neural network architecture。

So this is the momenttime too， a very well designed。

 well curated model from Google for mobile devices。And the red line is basically mobile ads。

The exact is the littency， the lower the better， the lower the faster。

The wide axis is the top by accuracy， the higher the better。You can see it's about 80% faster。

And compare with。There's no power aware。Because its a is inency。

The longest de littency but highest accuracy。This just showing you that small。

 a specializedized model is really helpful for the vacancy and accuracy trade off。

Talking about specialization， we want to exam when we are targeting different power platforms。電きはほま。

哦。This is the Proxlate NAS search。GPU。We specializedize this model for GPPU。

 and this is a specialized design， specialized model for the CPU design。

 specialized model for mobile。And different accuracy and let's see。

 what if we apply this GPU model to GPU to CPU and the mobile。快。Unsurprisingly。

 the diagonal vtancy is the shortest。收银在。The model specialized for mobile works the best for mobile。

 It does not run by fast in the GPU compared with the GPU model。

That makes sense because GPU has a high hero， CPUU has no heroism。

 so of course they prefer different neuro architectures。

And so here we want to visualize the search process。During the training process， remember。

 we are learning not only the wave parameter， but also the architectural parameter。

So different from conventional training。The model architecture states that should the same。

 you are training exactly the same model architecture throughout。The different ipos。

But now we are training also the neural architectures。And public emergence。

 we can see that the CPU model is much。ACP model is much deeper， TP model much shallower。

 and GPP model is much wider。And symptom handle is an error， GP model use a lot of large kernels。

7even by seven kernel， which is in red。CPU model说 didn天 use any seven by7。the criminal。

By three or5 by5， because CPU has。That's currency。But the may not be more efficient over there。

A GPPU really prefer a low number of kernel calls， since each kernel call takes a lot of time。

 therefore it prefers very wide but fewer number of layers。Which is indeed indeed the case。So， let's。

Take a look at the whole process again， starting with the mechanism same neutralization。And I said。

 graduatedu learns the GPU model actually。How shallower wider is not a kernel。CPM model graduate。

 is get a little bit red later disappear year。And it was that。不 one图。あで。あ表年。嗯。no large kernel at all。

It's very interesting to see this search history and how the neural network architecture adapts to different hardware features like parallel。

Okay， so that's one way to search a specialized model for different。Then the next question is。

 if we are given a model， given a hardware platform by the GPU or GPU or DSP or accelerator。

 we have to repeat the process。To search model for each of them， which can get quite costly。

How do we further improve the productivity， Can we just have one single model。

 and then we somehow later we can tweak it to fit GPU to fit TU to fitPSP or a smaller one mobile device module one to fit a GPU。

Comventional methods。You can have one hardware platform， like we are searching a model for a phone。

 we spend a couple of GP hours。By summer research， I popped twin backward forward the backward。

 if it' is good， then we break。And we have do some post training。Pos after that。We have more devices。

The process for more devices， which can be more costly。And if we have。

Many devices they become super expensive to do this process。So in order to。

 eliminate the search cost， reduce the search cost for， diverse hardware platforms。

We'll talk about a once for our approach， once for our approach。

 we are going to implement this in lap three， so the lecture here is very important。

So rather than training each network from scratch， like using the as well using the pro is method。

Can we treat multiple models at the same time？We have a single model that contain many sub networks。

Between and once small and， they are spaly activated。We can have many supplement。Just like this。

We can activate， sparsely activate some sub network， a small portion of it。

And then we got the vacancy， we got the accuracy。嗯。

We want to see if the adverse personally meet our constraint。ベスみ？

Ma that we finish the search process， if it doesn't mean。

Then previously we have to retrievetrain model。He train from scratch， train Bay or even longer time。

And repeat this process， which can be quite slow。And now we don't retrain it。

 we just sample another sub network， a different sub network from this ones voice。

We are going to provide you one of this once for network for you during the homework so you can just implement this process and you don't have to train from scratch。

 we are giving you a once for network， you can sample a sub network。

Can supply for different sub networkss， get availabilityancy， measure the accuracy， and see。

Whether it meets。要一万。If not， you can rather than just train it again。

 you can just sample from the white flow。So， let's see。What is that good for？So we can处 once。

You get many so that we can reduce the design cost。

 The training cost is amortized by many search iterations。This one more。 that's right。

I wasSrsly activated。So during architecture search， we can。所。

Lger sub network employed a powerful GPU like H100。The mutant size natural required a。

AConer rival GPU， like 490 GPU。And we can also derive a small version。非你话系。Bile G。

 like I mean that Jason already。And for these three modelss， we don't have to trim it from scratch。

And this is particularly helpful for large language model where it's very costly not quite affordable。

Twing these models from scratch。now we can to train one model and get many sub。To get different。

 get models of different。sizes。Like3 B is 7 b is 7 B。Similarly。

 if have different chips have different memory constraints。Deploy a larger sub。

Eith larger memory constraints means middle one for a middle sized memory。

 a tinyly one for a tiny memory。Or a larger model for a new phone or older smallerer model for an auto phone。

So that we can cater for users with different forms like someone may have。

T someone may have iPhone1 then we want to make sure the model can run。All different platformss。

系 similarly。You home in the morning， your phone may be a full battery during late night and maybe。

very little memory to better receive the mode。 so now you can seamlessly。

shifthift to this tiny model。That is derived from the city of West Florida。So that is the usage。

So a principle is just train once and get money。AndS， we can that 10 to the 19th。

1029 is a surprising and large amount of child that for free by just training this。Once four。啊，就是。

Child networks are spaly activated。But theyre share the rates。This one whole on network。

T them jointly to amortize the design cost。And it's all I think that design specializedize models what at risk。

ho。So how do we implement such a once spa network？First of all， let's brainstorm some challenges。

It's hard for a model to operate。independently， because they share weight。

How do we prevent different sub networks from interfering with each other。

 how to make sure they can all independently operate？So let's take a five minute break。

 and then we're not going to to return。方がある。Okay， welcome back。So let's start deeper。

 how do we implement， how do we realize this magic once smaller a network that can have many sub networks independently operate？

So the key part is to progressively prune and shrink the kernel size that resolution across different dimensions。

 so we want to progressively shrink the kernel size。So remember， we want to support both large model。

 middle model， small model。Therefore， do a across different dimensions。The criminal size。

 the layer channel from the criminal size perspective。We started with a seventh% internal。

And then the either part of the set Minnesotata， which is5 by five。

We pass it through a transformation matrix， we learn that matrix， and then we can be。

And middle size middle kernel， which is5 by5。And also。

 we may use the inner part of this five by five kernel to get a three by three kernel。So in this way。

 we can either operate on a small model， a middle model or a large model。They share the weight。

So valuable to support this through different sizes。

 how many parameters you need using 49 plus 25 plus plus9。But now we need only one seven by seven。

 49 weights。There's quite of ways to sure that you not part of the seminar。

It's nine3 by three weight is the inner subsection subpart of this five by5 weight。In a similarly。

 we want to apply that weight sharing principle to two other dimensions， the number of layers。

 and also the number of channels， and we have putting implemented in the lab at three。

So' take a a careful look at this。So we start with the four of that。Here we have example Pe of four。

 and then we shrink the map to suppose we can have Pe of three or depth of four。

 depending on which one we choose。We further shrink the adapt by allowing it to。

The all three come directly out of layer2， so we can have two layers or three layers。

 only four layers。So that's progressively shrinking the number of layers。Four layers， three years。

 two years。We can also progressively shrink the number of channels。哎，你音出来。4our channels。出现位置-5S。

And then we can sort the child importance by looking at the magnitude of different channel。

WeReorgan them， according to the。A lot of the sites， the largest one is green one。有时候呢。

And then we allow it to have only three channels， we pick the first three most important channels。

And finally， we can while sorting with him。To take only two channels then we pick the two libraries one。

The1，2，45。你老话。The yellow one is one the largest among these two。

So we can either choose the four layers， four channels or three channels or two channels。

So the network becomes very agile。ItBa becomes very elastic。Elastic， we can have a larger one。

Like this， larger kernel， under adapts， larger width， because theyll have a smaller one。

 smaller kernel， smaller。What a smaller that， smaller width。But they share the weight。

So ultimately you have one the biggest model， and then the small model can be derived from that biggest model。

Okay， so let's see this animation question here。Yeah how you。机的的这个房公。It you right。So the question is。

 how do we make sure the biggest model still works after2 of the smaller birds？

So就是 trading定 re sample the large one， large one and also the small one。

So both a larger one and smaller one get a chance to be sampled。

So that you can make sure the larger one didn't get destroyed。For example， iteration one。

 we may train a bigger， very big one， Ineration two， we may treat a smaller one。 Ineration 3。

 we may go back to train a very big one。And there are different sampling probabilities。

 schedules if you choose， but when you train a smaller。

Updating the middle weights of the big one Yes because we are sharing the weight。

 we are shooting the smaller one， youre also out in the bigger one。

 the middle but only the middle part， yes， you got it。They share the weight。

 so even if you're trading the smallest model， the business model is still impact。Okay。

 so this is animation showing that we start with。The maps dimension。

 starting with the elastic depths。A you like the resolution， so there's another dimension。

 which is a resolution dimension， we can also randomly sample different input resolution for each batch。

So small resolution， mean resolution， large resolution。

 that doesn't impact your weight because different resolution is share the same weight。

 but that impacts your max， your flows。And also， elastic kernel size。Easastic tap。

And also in last civil West。So that's the four dimensions， we are going to make it to be elastic。

 including。The resolutions and criminal size of deaths and the West。So in the lab。

 we are going to provide you with such a model that already did that has already went through this whole shootinging pipeline so you can directly use it。

 sample different sub networks， smaller kernel， larger kernel， smaller depths， larger das， etctera。

 to play with it， build a latency predictor。Given a particular latency。

 just find the best network architecture。So let's do a blueline analysis to see。

How does efficiency compare with others？So what is roof line analysis？If they are two axis。

 the X axis is the operations per byte， so you fetch one bite of data， move one bite of data。

 how many operations operations are you able to do on top of that memory。

So data movement is very expensive， Comp is cheap。Ideally。

 we want to fetch one bite of data and we do a lot of operations on top of it。

And the why axis is the G flows。The G the realized performance。Initially they are memory bottleneck。

 so as long as the increasing operations provides。We can improve the Gs。Later， we are compute on。

No matter how many person provider you have， you are limited by the number of multipliers and multipliers and others。

やぱりと。So this is a roof line analysis， it looks like a roof， so people call it roof line analysis。

And let's see， how does the WestW network， where is the WestW network located？你看我。Other approach。

 like I does that move on that V tool。No human。So actually a lot more。

Is having his on the top right corner， okay what has top right corner。

It achieve higher Gs per second， and also right means it has higher operations per bite。

So this is all。I access the difference。犯罪。So bigger operations for bite means that we can make it more memory efficient。

 we fetch more and vital data， and we can do more operations on top of it。

 therefore is why it's getting more efficient。And indeed， we measure the realized efficiency。

 we measure the geos per second。And see what call that。having a higher measure of geo per second。

放 the好快。So this is just one hardware platform， let's see how it performs on diverse hardware platforms。

So we matter it on Samsung phone， Google phone， R G phone，Q Intel CPU PG。です。The rule part is。

Latency versus accuracy， ideally， we want a low latency。

 high accuracy so the top left corner is good。嗯。Across all different platforms。

In one small network the subnet actually reside on a better practicalal optimal curve。

Lower latency and also higher accuracy。So that is how do we everyone to ask any questions so far？

Make sure you are clear about how as well as it works so that we can complete that three。Okay。

 no question。 Let's move one to talk about zero short next。从的自由上班。Previously。

 we have to measure the vactancy on the hardware platform， we have to first train it for a while。

 and then estimate the accuracy。whichch can be quite cost。 you have the training。

 which can be quite slow training for a while。 And now let's just look at the model without having the training。

 let's just see eyeball tracking not actually eyeball tracking。

 We just see some of the features itself without having the training。

Look at analyze the architecture。And see it and guess whether we can have a。黄道。

I introduce two pieces of work， then now as an also website。The motivation is basically。

 don't train it and tell me the accuracy whether it's promising。So zero说呢 Z呢是 here。

There's one heuristic saying that we just randomly neutralize input。保了 follow你当的标。

And then we had a small perturbation and a small perturbation to obtain a new X。

And then we neutralize all the weights of a neuralnaural architecture。Using normal distribution。

 So random weights， basically。So this paper is saying that。A difference between these two inputs。

The two inputs will generate to alls。ス。And the difference between these two output households。

If the model is good， then the difference。呃 should be large。If's an input difference in the same。

 that good model should be sensitive to the input preserv。Change the input a little bit。

 the output will dramatically change。And it proposed a second theistic。

 which is saying the batch normalization。Find the average， put the variance in the back there year。

 and we add them map together。We want to encourage the variance to be large。

 otherwise different inputs， they have exactly the same output。

 that's not good if the variance is large， then consider this architecture to be good。But frankly。

 the architecture is just。Tip of the iceberg， the way it also matters。

 So here is using the random weights。 So it's very coarse green eyeball checking， not very。

But actually the result works quite well， at least in this paper。

 just look at given the perturbation of input。If the output changes a lot。

 then that's good for different batches， if the variance is big， then that's good。Another还。

We're at side。So we're sign， this kid her missing this。A good model will have very dense。

 very dense sample wise local mini。So the two ofmar should be very close rather than very far away from each other。

Therefore， the distance between the local minima should be close to each other，And therefore。

 there's a higher probability that the br。In different sample， you try different samples， X1 and X2。

 X1 and X2 should have the same size。Calculating the sign is very cheap。So in this area。

 in the red area， the sine of the wave here is negative， here is positive。

 they are of the different signs。And if you are in the schooling region， here。

 both of them have magnitude gradients。There was also some positive great gradients。

So if you sweep starting from here to here， the blue rate of the green region。

 will have the same sign。The rest region will have different sign。

A good model which have very close local medium models。是他的。Orinal in green。

Which means the gradient should be of the same sign， that's why his work's name is hot Greg site。重新看。

I this approach to count。The number of entries。skip the same gradient。And if the sum is large。

 then it means。A lot of region is green and it's good。So those are two very simple heuristics。

 you don't never train the model， you just feed it with some input and then calculate either the output difference or the variance of the normalization layer or the sign of the gradient。

O。So far we talk about given a hardware platform， okay the hardware platform is fixed。

How do we optimize the neural network？And now also let's open the box。 say you can also。

Have the freedom to design the next hardware architecture by ourselves， design I。By yourself。

 you open up the box， you can now design both the hardware architecture and also the neural architecture。

 How do you design them together？So that's the next chapter， which well not do in the lab。

 but it might be eye opening。Let's talk about the new chapter about neural architecture。

 neural accelerator architecture search， Okay search not only the neural architecture。

 but also the accelerator。We propose a hardware design？We then propose a new architecture design。

We collect some feedback running in this neural network on this hardware。In。

Click the hardware and also the neural natural architecture。What is look。And第二。

This is showing we can tweak the newer architecture。can退 the accelerator。And both of them。

 both designs are important to enable specialization。

 just now we talk about specialized architecture runs the most efficiently。

So let's see with the design space， we must have a much bigger design space。

 including both neural architecture and also the hardware architecture。Watch rather design space。

So are的 key dimensions now。We have three components。We have to hover ourselves that。

We should include several hardware dimensions。LikeThe local buffer size， global buffer size。

 the number of processing elements， the number of PEs。The size of the compute array。

 the PE connectivity。On the compiler side， which compiler maps the neural network on the hardware Acccelerator。

So on the compiler side， we have the group of orders。Which loop do you process first。

 Which loop do you process later， loop tiny size。And dataful。A neuronaal perspective。

The number of layers， number of channels， kernel size， whether we have bypass。

And input and output and weight quantization precision。So that's a pretty big design space。

And solution is to ideally， we want to have one optimization loop。

 this is one optimization loop to search both the accelerator architecture and also the new architecture。

So let's see first， the accelerator architecture。Inlude a pretty large design space。

 including we categor them into two categories。One category is size related， which is very simple。

The buffer size， global buffer size， global buffer size， the number of PEs。

And second one is slightly more challenging to represent in numbers。The P connectivity。

 which one connect to which one。And our key idea is to talk about how do we put those non numerical numbers like the connectivity。

 you cannot easily represent connectivity by a number and how do we design those non numerical values。

So when we are wrap be。A couple of operations， like a follow up operations。嗯。Into the hardware。

 roughly there are two categories， Okay， one is temporal mapping， one is spatial making。

 So what is difference here， spatial mapping here means you can process them in parallel in space like here I have。

10 modifiers。 Then I can process10 multis in parallel 1，2，3，4 parts。 Ph， they are in the space。

 where I have2 by2 by 5 we have 10 modplifiers。 So that's called spatial paradigm。

 You can parallelze them in space。 They are executed concurrently。And also you have temporal。

That means。You can process them sequentially， but in different order。 So what determines the order。

The sequence of the for loop determines the order， so in this case。We have。

Two lines of hope indicates how parallelm paralyzing space for them and n dimension range 16 and 16。

 so you have 256 quaifiers here。Can currentlyrently execute and， paralyze them in space。And then。

How this temporal landing， including both the pi， what is the tile size。

 what is the order determines which sequence。To map these stool powders in the temporal dimension。

So here we categorize them into two parts， one is the how we encode， the vector the other。holdinging。

Mine is related to the algorithm， but one is related to the compiler for Mac。

Some of them is not numerical。The parallel dimension， choosing which dimension to paralyze in space。

 okay， so that's not easy。Use see to be represented by a single。

And the loop order can also in obviousular straightforward to represent similar to like the tile size。

 number of PE the cache size， which is just a single value， this is not。

By new way is to do index based recordinging。三ポゼロ。Sequence CR， X，Y， KYS y means。我。

See means channel X I means the highway width。Rs means the kernel size of width。

 pay means the number of criminals。But actually， there doesn't convey any physical information， why。

This话。Mo impact on this one。So we we do try to make it， have some meaning。

The first fixed dimension position in the colon length， for example， the first position is A。

 second position is C。Cal science China number。High and with， criminal X， criminal Y。おかす。Chs。还还很问。

Coral science。And then we assign numerical importance。To these dimensions。So this is numerical value。

 the importance is a numerical value。And then we can sort them。You can pick the two of largest one。

C is the largest one， K is the largest one， so that if we want to paralyze the new space。

 for sure we want to paralyze the dimensions with the high importance。

So we chose the first food dimension。苏人。talk to。Andform order。

We assigned the most important image as outermost， since it will be elevatedted last number of times。

We put the least important in the inner side， the inner loop， which will be very hot。

 which will be executed many times， more time consuming。

 before we put it in the less important in the innermost。So in that way， we can convert。嗯。

imagine selection versus the rule order which。By definition is not numerical value。

 we turn into numerical representation by sorting them。

So let's see if the search results gives you list number。哦。看or dimension。We have two dimensions。

 and then we choose。The first two most important dimension。诶先啊。

It seems very important in January of August。Therefore， they put them。I see a color for。

These two rows of tele， we are paralyzing in space。Since this is related to the。

Which dimension do we paralyzze in space rather than serializing time？car of about dimension。啊，就这种赛。

Size2 which is two most important ones。And then imagine sizes。It's given by 16 in。And six him。

In the entry here， meaning that we all together have 16， this dimension， 16， that dimension。

 multiply them together we have 256 multipliers。And then on the right hand side。中号。开呃开 size做好的。

The group other is CR。Okay Y S， so we follow that CR X， K Y S。

 you put the important one in the other room since it will be executed less number of times。

 a less important one in the inner room。ItS。And what is their block timing size as a purely numerical value？

search。You we research at 7733。啊同埋要防威。27， slide7 are。3 it three。

So everything now can be represented in numerical values。

 we can even use the numerical value to search which dimension to paralyze this。

And what is the loop order？So that effectively solve the mapping problem。

So this is an overall big picture， we have three components。

 and this is a neural network architecture design。ハル開けない。

This is the mapping that maps the neural network on the hardware。

 and they are all using evolutionary strategies with mutation cross over。

The motion is strategy to select the capacity to fit with low energy delay product。

This is given a neuro rocket space。I in search space， this is given an accelerator search space。

And finally， we want to model with the lowest energy related product that。But on the right hand side。

 you can see the mo， we first generate the hardware。等等将个。Then do the。

 like this network on the hardware。Ha the energy。Outtake the OA model and then later update the final。

In this way， let's compare the architecture sizing only。The energy delay product， energy。

 we want a low energy delay， we want a low latency， so the energy delay reaction is good。

So compared with the baseline， architect for science will make kind of reduce the energy that they caught by。

20% or2。1 times。But searching both the size and。AndThat can be helps more。

And here we have this tradeoff between energy delayed product。

 lower on the better versus the accuracy， the higher the value。We can see that here we where。

How do architecture search plus what's more neural architecture search together， Okay。

 how do neural architecture search together give a better。Trade off so starting from this point。

 which is the baseline feeling。And then个。颜色是。hardware that research cost the。And very interestingly。

 the data flow designed by NAS。Actually paralyzze the input heights and output channel image。

 which is very different from the human design。So we will not implement that in the homework。

 just give you some insight that we can do new architecture and hardware architecture search altogether。

All right， honestly， how you thought about all these techniques？Applications。

 how does the one whole approach apply to metro language processing， G applications。

 point how the application post estimation， eta？So we've be mostly talking about studentss at the moment。

 but the Westfall approach works quite well for transformers。Similar to a previous design approach。

 we can design once small transformer， but is's a very big giant network。

And paying the money sub that trucks。We can design design a smaller transformer， but Ken now larger。

give。And here we are comparing。The latency and also the model of science， the latency could be 2。

7 times smaller compared with above the transformer。And model size can be reduced by 3。7 times。

And the search cost is also much lower since we are sharing the same one store as。

I'm multi between costs across different search processes。There is a speed out。Out the fl of action。

Actually， we also implement this in chip。They on a trip to verify the idea。

So the chip is called a Spin， Sppartin transformer。Let me turn on。But can hear the voice。

So this is a sp t over chip da。スとレつ。Hello， everyone。 My name is Henry Wang。

 I'm currently at PhD student at MIP。 I'm very glad to show our transfership demo for English national language。

So here on the left side， we have to do I for this table。

We can increase some sentence to that check process。For example。

 we can input the sentence that flight ticket from Boston to San Francisco on August Friday8。

We can use theship to grant the models and then return information about the classification of the sentence and also the classification results of each token。

So let me pause a little bit， so what it's doing here is basically。啊，包是那I看到。Interrupt the video。

 So we have to watch it again。I would like to show our sensor panel for efficient natural bandwidth processing。

 So here on the left hand， we have the GI for this demo。

 we can increase some sentence to language check process。For example。

 we can implement this den from Boston to San Francisco on August 28。

We can use it to software to run the models and then return the information about the。

The symptoms and also the artificial results of each coD。

Then we can use the information to call a web browser on website to automatically search for information and return to the G。

Besides searching for flying ticket， we can also use it to search for the weather。 For example。

 weight is the weather in Boston。 Again， we can use the transform to process the sentence and then obtain the location information。

 And then we call the browser again to search for the weather and then return the weather information to the G I on the level side。

 Our model can actually support for different size。

 and all of them will share the same set of weights。 This technique is called super transer。

 Different size of share the same set of parameters to save the oxygen matter footprint。😊。

Here we can reduce the efficient high number and guide emission and try to process。佢于食界其实。

Here you can see the correct result。 I can call the author to play music。一起防。So actually。

 it's technology。Sic proof。ちょっとしす。Pa6。together。I try get a best panel of water back。

These I mentioned conference。Okay， so not only for natural longer processing， but also for 3D region。

 Okay so this is a demo。From a south car。あれた。来点来点 sensor。This has been constanting that。

This is seing different objects， the road the drove by area， the trees， etc cetera。

 you can see it's pretty slow only 3。4 frames per second。

 but on the on the autumn is our work that our T hop here。Caed as fewBna。

 sparse point box of neuroactural research to search a very fast architecture that can run at nine frames per second。

Many awards in the。L our segmentation competitions。

 so the basic idea is the same using this one floor approach， so we truly supernatural。

But his support fine way。Easastic number of channels and also elastic baths。

So initially entering that three， thatpt two and three， vector one， two， and three。只本上两个。Chhannels。

 they share the weight。And later we do the evolutionary architecture search， given the super network。

 in example， a child network， measure the latency and accuracy。

We sample if it doesn't fit our demand。诶翻过嚟回度。architectureitecture search with neo fiction。

And also cross over， and there' be two hundreds to cross over。Avolutionary architecture search。

Very effective in reducing the rate。The next once more all for models。W is any cost gap。Ideally。

 we want to run this photo editing locally on our laptops or mobile devices。

But I can see this is very slow。So here we have。こ image。this spark。

 we want to pull it to the right here。原个。You can also change other aspects。

 like changing the head counter。拆出了。But it's not quite affordable to run and you have a mobile device。

 take three seconds too slow to run。So we can now switch gear to this as cost again。

And then we make her smile， its very fast， only0 points three seconds。Pretty much real time。

We can also like a young button to make her look younger。And change the hair color。And finally。

 we can click the finalized button。To run the food network， only once。

And then to get the finalized output。都是一个 high quality。So就是一个。These sports for our models。

 the biggest。He and反。Ones that theyre trained。With shared ways。

So you get a little bit more efficiency。You sample from different dimensions。

 you are sort of running。And that is。そじゃのおかつ。Right， if you only need one model， then just print it。

 but if you need different models like 70 billion parameter， 35 billion，13 billion，7 billion。

 3 billion，1 billion， you wanted the whole landscape。Sly rich， then this matter helps。

So here we are twin the onefall approach for the G model， different generators。

 smaller sub generator， low cost for faster prototypety。

 we can quickly prototype and finally run this large subnet。

啊 high quality good for final good for finalization。So this demo is open source。

 It's deployable on a MacBook。 It was done actually three years ago in 2021。 at that time。

 you can run a MacBook。 theres 0。3 seconds now should be much faster。 Feel free to download and play。

So next we also have for one small natural proposed estimation。

So post estimation is basically finding the skeleton joints on your body。The arms have。

The like意 center。So previously in went slowly， we can push it from here to make it about four to five times faster。

Bunning on the sided mobile mobile CPUU。So this is also derived by how they we aware in our architecture research。

We have a couple of fat more demos。All of them are open source on our lab， SHub。For on device person。

 car detection。On device estimation。 So case estimation is very useful for auto driving cars。

 like in my car， if I don't look at the road， my car is going to alert me when I'm using the possible mode。

 So basically tracking where you're looking at。 ifre not look at the road。

 the car will send out on arm。So this is good。Useful for driver monitor system Ps。

Foride sign is being local healthy segmentation。Very interesting W small approach also works for quantum AI。

 This is done my student PhD student Henry one。So we we find actually there's a market。

Between the theoretical accuracy of doing this unist for and for class classification on quantum。

Where measured啊还。Yeah， which is。80% only 40%。So 40% drop of accuracy。

So what is the reason because quantum circuit is highly？Sing very heavily from the voice。

Not necessary， you have better accuracy， better good results， you put more circuits。把三块。

Several gates only put them in the right place， more gates。

 more noise So start with a super circuitcase。Some some circuits。

And then search the fastest sub circuit that meets your accuracy demand。

So we want a certain a sound circuit that is very robust and noise and cool with small lightt included on quantum case。

看来是是造图。Iprove。You see from 40% back to。85%。And this is measured on a real QC， a real。

The same principle apply to a different discipline， very interesting。

And that is open source and Torch Hong。Okay， very recently。

 I meeting now about this oneflow approach and applied it to large language models。

So this's this adaptive inference。different bottles for each100。90 but that already。

We have a larger model to fit H100。对那着毛子回说他是。Meddle model for OX 49， small model for orange platform。

Multiple models。We want找 my通。For the cloud GPU， we can run the full network。

So that's how we看到 middle network the mobile phone。 You are the smallest。佢不俾我吹 model都。

This is using a very similarim approach。We can have human interventions。我 both a当时 for的 pension。嗯。

to have to determine what。方 what is。channels。So。Might one， flexible large number models。Okay。

 so that's the summary of today's lecture， we talk about how do we efficiently do performance estimation。

 how to learn awareness now using confidence with NA， my small approach。

 in particular my small approach， we will implement that in that week and finally we talk about NADS applications。

In the next lecture。A new chapter about knowledge this。かそ。

