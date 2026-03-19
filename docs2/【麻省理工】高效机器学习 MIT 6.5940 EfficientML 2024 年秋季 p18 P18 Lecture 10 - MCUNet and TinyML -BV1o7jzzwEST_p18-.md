# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p18 P18 Lecture 10 - MCUNet and TinyML -BV1o7jzzwEST_p18-

Okay， welcome everybody， let's get started。So today we're going to talk about efficient amount of AI lecture 10 about MUNe and tiny ML。

So today's lecture we are going to cover the following sections， so what is tiny ML。

 what are the challenges of tiny ML and how to design those tiny neural networks and what are the applications。

 including tiny vision， tiny audio， tiny time series， and also anomaly detection。

So just give an overview of where we are so far， we talked about a lot of techniques to shrink to compress neural networks。

 including brooding quantization， distillation， neural architecture search。

 and now we want to combine these different efforts together and build some cool applications and really deploy them on small devices。

So what is tiny ML， today's AI is pretty big， as we shown across the years。

 the model size measured in billions of parameters that growing super fast。

But we need algorithms and hardware， new algorithm and hardware that is more efficient。

 efficient for inference， efficient for training， rather than taking a giant。

 a lot of resources for memory for compute， but we can fit them in our pocket。

 fit them in our phones right and reduce the carbon reduce the carbon footprint towards greener AI。

So recently the ChaGBT， the GBT3 actually contains 175 billion parameters right it takes 355 years GPU years to train cost more than $4 million pretty expensive。

 and the Algo beating Lio Do took 1，920 CPUs and 280 GPUs。

 which costs $3000 per game just to play one game。On the contrast。

 we hope deep learninging can go tiny so not only on the cloud but also on the edge where we no longer have to transmit our personal data either the image or the text or the voice to the cloud。

 which may suffer from adversarial attacks and privacy leaks et。

 but we want to keep everything local on the phones and even on smaller devices like IoT devices。

For example， microcontrolls and these microcontrolls are everywhere in the lives and in our lives。

There are billions of IoT devices around the world based on microcontrollers。

And you can see across the years， the number of IoT devices are increasing。

And they have very low cost， just a few dollars。So everybody can afford it， right？

We can democratize AI to these low cost edge devices。And also they are of low power。

 so we don't have to worry or battery get strained right。

 running out of battery or youll go to a spaceship， there's no wfi connection。

 there's also limited battery， you can run them in very low cost in low power even using renewable energy thatll be super cool。

And these tiny ML application for a lot of usage across different aspects like smart home and control different appliances in smart manufacturing to do automatic defect detection。

 personalized the healthcare， adjust dose， according to different patient' symptom and also precision agriculture。

But it's not easy， Tan on is quite challenging。What makes it so challenging？The resource。

 primarily the memory resource。So for Cloud AI， you can easily get in this slide its showing 32 gigabyte of memory。

 but now you can easily get 80 gigabytes of memory， A100 H100 GPU， which has petabytes。

 terabytes or even petabytes of data of storage to store the weights on data。

On mobile devices like on our phones， you can easily get a couple of gigabytes of memory ands hundreds of gigabytes of storage。

 that's a planet。But on those microcontrollers， the resource is tiny。

You have a couple hundred kilobytes of memory for the SR to hold those activations。

And you have just maybe just one megabyte， one megabyte of storage。啊。In the flash， okay？

And the flash is only sometimes read only and I' write to it， only the as is readable。

 so the resource is very tiny。It's four to five orders of magnitude are smaller compared with the cloud AI and also the mobile AI。

So we need to reduce both the weights and also the activations so that we can fit these deep neural nets into tiny ML devices。



![](img/59bb15ccd45ead4e52fbc007870bf273_1.png)

So compared with mobile AI where we are constrained by the latency and also we are constrained that energy。

 now we have a new constraint， the memory right since these tiny devices has very little memory。



![](img/59bb15ccd45ead4e52fbc007870bf273_3.png)

A lot of the principles can actually be applied to a large language model these days since they are so big。

 even one GPU cannot hold and accommodate all the weights。

 like 175 billion parameters if we don't quantize them in p16 and that's 340 gigabytes of memory well a GPU has less than 200 gigabytes of memory so same principle can also apply to large models。

Okay， so let's dive deeper to understand the challenge， especially the memory challenge of tiny ML。

 what is the bottleneck for the weight memory， what is the bottleneck for the activation memory。

So this is an overview of convolution neural nets， you have a couple of con layers。

 pullinging layers followed by F layers in this case。



![](img/59bb15ccd45ead4e52fbc007870bf273_5.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_6.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_7.png)

For each layer， we have input activation。

![](img/59bb15ccd45ead4e52fbc007870bf273_9.png)

Evolved with a kernel， three by three kernel， and produce this output activation。



![](img/59bb15ccd45ead4e52fbc007870bf273_11.png)

And where do we need to store， since we are concernedtrain about the memory， let's dive deeper。

 where are they stored。

![](img/59bb15ccd45ead4e52fbc007870bf273_13.png)

So input activation and output activation， we need to both read and write and we read the previous input we write to the output of the next layer。

So it has to be both readable and readable， so it consumes the asRAM。

 which is both readable and readable as for static static random access memory， asRAM。



![](img/59bb15ccd45ead4e52fbc007870bf273_15.png)

And for microcontrollers， they probably usually don't have any D only a couple of very little resource for flash so it's read only so only the weights。

 the weights is actually read only if you don't do back propagation if you don't do training the weight can be stored in the flash。



![](img/59bb15ccd45ead4e52fbc007870bf273_17.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_18.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_19.png)

And the flash different from ARM， if you power off the device， the data in IM will be gone。诶。😊。



![](img/59bb15ccd45ead4e52fbc007870bf273_21.png)

The flash can hold the data。 It's not volatile。Okay but IRM is a volatile if you power off the device。

 the data in the iceRM will be gone。You don't want the weight to be gone。

 so you have to store the weight in the flash。

![](img/59bb15ccd45ead4e52fbc007870bf273_23.png)

So these are some popular mobile microcontroller devices like Adreno， nanono。

 this device has 256 kilobytes of SM， one megabyte of flash。This item 32，7， four7，4，6， which we use。

As3 20 kiloby of I run and1 megaby of flash， so very small resource。



![](img/59bb15ccd45ead4e52fbc007870bf273_25.png)

Okay， so the flash usage。Roughly equal to the model size because theyre static。

 they have to be nanomoile， you need to hold the entire model so the number of weights is constrained by the size of the flash we are going to revisit revisit this later part in the lecture。

 so the weight as to fit the flash since it's nonmotile。



![](img/59bb15ccd45ead4e52fbc007870bf273_27.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_28.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_29.png)

And asM usage roughly equal to the input activation plus the output activation。



![](img/59bb15ccd45ead4e52fbc007870bf273_31.png)

Since they are read and read dynamically during the inference and we care about the peak iceRA usage。

 which means the largest layer， the size of the largest layer。Determines our peak memory usage。

Wes are not counted here since they can be partially fetched。

 fetch them compute on they throw it away。So what is the gap here okay。

 so this is comparing Reszen 15 mobile 92 mobile 92 intake version。



![](img/59bb15ccd45ead4e52fbc007870bf273_33.png)

Here is a 320 kilobys。Of memory constraints that a micro controller has。Well。

 rather than 50 peak extra usage， 23 times larger。Mobin number two，2 two times larger。

quantizing quantization we learned in the previous lecture。

Slightly reduce it by four times is very good， but still five times larger okay so we are going to learn in this lecture how do we overcome this gap and be able to fit。



![](img/59bb15ccd45ead4e52fbc007870bf273_35.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_36.png)

The model in the microcontroller while having similar accuracy as Open I2 okay。



![](img/59bb15ccd45ead4e52fbc007870bf273_38.png)

So what are the efforts， the prior what are the prior efforts Okay， so we learned about MoM2。

 which is a very small model targeting mobile devices like mobile phones。But still， that's too big。

And if you see the bottleneck， especially the activationation bottleneck， it's very unfortunate that。



![](img/59bb15ccd45ead4e52fbc007870bf273_40.png)

The activation didn't decrease， but actually increased by 80%。So it's very primarily efficient。

 so you can compare， here is the Re than 18。Here this is the mobile IB tool， 0。75。喂。



![](img/59bb15ccd45ead4e52fbc007870bf273_42.png)

The weight is reduced by more than four times so that's pretty efficient。

 the weight is much smaller so it takes less to communicate from the Apple store to download the app right and so that's pretty good。



![](img/59bb15ccd45ead4e52fbc007870bf273_44.png)

However。The peak activation even decreased， but increased。



![](img/59bb15ccd45ead4e52fbc007870bf273_46.png)

so that's a big problem we need to solve。

![](img/59bb15ccd45ead4e52fbc007870bf273_48.png)

So we are going to learn about MC net， okay， not only reduce the weights by six times compared with res 18 with a similar accuracy。

 but also the peak activation is also reduced by 3。4 x compared with Mo magnitudeitude okay。



![](img/59bb15ccd45ead4e52fbc007870bf273_50.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_51.png)

So that's our goal。 We have to balance both。

![](img/59bb15ccd45ead4e52fbc007870bf273_53.png)

The number of parameters and also the peak activation we have to fit both of them in the microcontroller if you cannot fit any of them。

 you cannot fit the models。So let's go through formally， how do we design these tiny neural networks。

 given the understanding of the challenges， given the concept we learned so far。

 we'll introduce at Mnet the system and algorithm Po design we was covered by9 News for a couple of years ago。

 which is very new。

![](img/59bb15ccd45ead4e52fbc007870bf273_55.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_56.png)

So what is system and algorithm code design， we have a very large design space， okay。

 we can either design the algorithm side by changing the neural network architecture given a fixed library。



![](img/59bb15ccd45ead4e52fbc007870bf273_58.png)

For example， we learned O is NAS designing a customized， specialized model given the hardware。

 given the library。

![](img/59bb15ccd45ead4e52fbc007870bf273_60.png)

There's other work focusing on assuming the model stays the same， but we want to design。

 develop new libraries like TBbM。

![](img/59bb15ccd45ead4e52fbc007870bf273_62.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_63.png)

What we find。The extreme efficiency comes from who designing the neural architecture and also the inference engine you need to。

Co design both directions so that you can explore and explore a larger design space。

 including the neural architecture， then proposed efficient neural architecture。

 and also efficient compilers and run time so that you can map the architecture on the inference engine。



![](img/59bb15ccd45ead4e52fbc007870bf273_65.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_66.png)

So。The basic idea of MCnet is system and algorithm full design。In this lecture。

 we are going to cover the first part， which is tiny knots， tiny nuer architecture search。



![](img/59bb15ccd45ead4e52fbc007870bf273_68.png)

How to design automatically and optimize the model given the hardware resource constraint。



![](img/59bb15ccd45ead4e52fbc007870bf273_70.png)

And in the next lecture， we are going to cover the second part， the tiny engine。

Efficion compiler and run time how to optimize the inference engine。So let's start with tiny Nas。

 which has two stages， okay two stages for neural architecture and knots for neural architecture search we covered before okay。



![](img/59bb15ccd45ead4e52fbc007870bf273_72.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_73.png)

This is a short recap， what is design automation for neural nets， what is the motivation for that。

 so remember recover in the previous lecture rather than using a lot of engineers to hand design the model given different hardware constraints。

 solid manual， architecture design， use a lot of human expertise， pretty expensive。



![](img/59bb15ccd45ead4e52fbc007870bf273_75.png)

We want to use machine learning to actually automatically search a good architecture that fits our demand。



![](img/59bb15ccd45ead4e52fbc007870bf273_77.png)

Youre acting as。When we are doing the search， we talk about， we need a good search space， right， so。



![](img/59bb15ccd45ead4e52fbc007870bf273_79.png)

Like finding a friend in a forest， the forest is pretty large， we want to first narrow down。

 narrow down the possible areas， for example， here or here。

 right narrow down with search space before we do the exploration。



![](img/59bb15ccd45ead4e52fbc007870bf273_81.png)

So the quality of the search space largely determines the performance of the search the model。



![](img/59bb15ccd45ead4e52fbc007870bf273_83.png)

So the first stage of two stage of tiny Nas is actually to search the search space。



![](img/59bb15ccd45ead4e52fbc007870bf273_85.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_86.png)

And find a good subspace so that if feel promising， rather than explore in the entire search space。

 we want to explore in a much smaller consjotrained search space。



![](img/59bb15ccd45ead4e52fbc007870bf273_88.png)

So how do we find that search space？One approach actually can reuse the prior search space for mobile night。

 for example。

![](img/59bb15ccd45ead4e52fbc007870bf273_90.png)

However， the constraint for mobile device is quite a lot different from I these tiny microcontrolls to differ by a couple of orders of magnitude。



![](img/59bb15ccd45ead4e52fbc007870bf273_92.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_93.png)

So even the smallest sub network in the mobile search space too can all fit with of that。

Due to the huge gap， so mobile device has four gigabytes of memory versus the microcontroller has 320 kiloabyte of memory。

 so even the smallest network clean search space still cannot fit the microcontroller。



![](img/59bb15ccd45ead4e52fbc007870bf273_95.png)

走我可虑度。We can only design a new search space targeting IoT devices。And how do we做 that。

So we can scale down， we can scale the previous search space for mobileNe。

mobile ads using a different resolution and different width multiply it。For example。

 the original search space typical for mobile devices。

 the resolution is 224 by 224 and the width is 1。0。



![](img/59bb15ccd45ead4e52fbc007870bf273_97.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_98.png)

That's pretty suitable for mobile phones。And we can scale them up for GPUs， similarly。

 we can scale them down for microcons。Then the question is。

 how much do we exactly to scale them down they have。

Different metal controllers also has different memory budgets from 256 kilobytes all the way through 512 kilotobytes。



![](img/59bb15ccd45ead4e52fbc007870bf273_100.png)

So the overall structure will be given a full search space。

 we want to add our memory and the storage constraint。

And then produce and optimize the search space and then perform neuro research on top of it。



![](img/59bb15ccd45ead4e52fbc007870bf273_102.png)

So the optimizer search space， including two design ops。

 including the resolution and also the width modplier。



![](img/59bb15ccd45ead4e52fbc007870bf273_104.png)

And after that， we narrow it down， and then we search the kernel sizes， the expansion ratios。

 and also the number of blocks for each stage。

![](img/59bb15ccd45ead4e52fbc007870bf273_106.png)

So here is the algorithm for automated the search space optimization and we want to analyze the flock distribution okay we have seen this figure before but let's dive deeper today。



![](img/59bb15ccd45ead4e52fbc007870bf273_108.png)

And analyze the flop distribution for satisfying models in each search space。

 so here the X axis is the number of flps within the search space from 25 million flops to 65 meeting flops。

The Y axis is the cumulative probabilityities。And different curves corresponds to different search spaces。

For example， the black search space， the width is 0。3， 30% weight， 30% width the resolution in 160。

I just rather the search space。width width is larger， is 0。5， resolution is smaller， 144。



![](img/59bb15ccd45ead4e52fbc007870bf273_110.png)

So in different search space， the flop is very different， for example in the red search space。

 all the models。Has the flops more than 41 million flockps， instance here iss 41。

Here is all the models has。Prime is larger than 41 million countries and 20% of the models in here correspond to 80% so one subtracted 20 to 80%。

So 20% of the models are larger than 50 million als。

Versus the black curve as much smaller than the fluxps。

Here all the models are larger than 28 meeting compared to 41 meeting。And here this 80%。

 one minus 80% is 20%， so 20% of the models has larger than 32 million fonts。

 other than here it's 50 million fonts。So we can see these two different design spaces can fit different amount of flops given the same memory budget。

Since we learned that computation is cheap， memory is expensive。

We want to maximize the amount of flops we can work on the same amount of memory footprint。

 the same amount of data movement in fetch one bite of data。

 we want to do as much of compute by fetch after fetch one data， right。So of course。

 a good design space it showing that a if a design space can achieve high fls a high fls of accommodate a lot of arithmetic operations under the same memory constraint then it's likely to be a good design space。

And that' indeed the case， for example， the rent space， the best accuracy you can get is 78。7%。Well。

 for this black design space。The best accuracy we get is only 74%。Okay。So this is very helpful。

 heuristic without having to train the model，我 didn't even train the model。

But we can just analyze the flops， and analyze the flops we can accommodate。

Given different design space， the project the final accuracy。Okay， and let's see。

 given different constraintsst， let's analyzed， given different as constraintst。

And this is given different flash size of the flash。

 ranging from512 kilobyte all the way to megabytes。The X axis is the flash， the y axis。

Is the SRAM going from 190 kilobytes to 5， 12 kilobyte， 192 kilobytes to 5 12 kilobytes。

So we want to understand。When the flash increases， but the SM size stay the same。

What would happen for the wave modplier and the first loop figure is for the weight modplier from 0。

40 to 0。9？And the second image is showing the resolution and some of them is 120 which 112。

 some of them is2 or8。So when the flash increase stay mass rampm。

 what happens for the width modplifier？the other question is when IRAM increase you have more IRAM in are like controller。

 same amount of flash， what happens to the width modifier， what happens to the resolution。

I've give you。One minute to think about this question。

And a hint is you can consider with three points， first point， second point， third point。

 first point， second point。Their point。Okay， I see the answer so when the flash increase but IRAMs stay the same。

 remember what gets stored in the flash， what gets stored in the IRAM。

Right exactly so flash storess the weight the kernels and asstrM storess the activations right so when the flash increase meaning you can hold the plumed more weights。

Right so you can have a larger amount of channelss。

So that's why the wave modplifier is increasing from 0 0。4 to 0。8 what about the resolution？

Since we have the same SRA。And the channels are getting larger。

 which means the resolution has to be smaller。So that the channel times the resolution square will be the same。

 otherwise， you cannot hold it in the same model as算。So larger channel smaller resolution。

 larger channel， smaller resolution。What about when a increase but the flash say the same？So iceram。

Stors， your activations right but this flash stays the same once on here。

The resolution actually increased。Because you can hold more activations， right。

 you can hold more activations。嗯。But the the flash stays the same。

 which means the weight actually stays the same， the flash stores the weight。

 the number of flash stays the same so the width roughly stays the same across different channels。

 different columns of the blue feeder。And since the am gets larger can larger feature map larger resolution。

 so across the column dimension here， you can see the resolution actually increased。

So this figure gave you some intuition about。The intertwining relationship between SRM and flash。

 activation， weight， channel and resolution。Any questions about this either in general？OK不用我把什我。

So having figure out。The design space， we can now perform the access search。In this design space。

 just like trying to find your friend in the big forest， now you finally find determine okay。

 my friend is in Ra in this area then I can focus on this area to search a friend in the forest。

So here we use the W fall approach we learned in the previous lecture。

 we now we apply them to do some real stuff， so we have this between the super network this Vi fall network。



![](img/59bb15ccd45ead4e52fbc007870bf273_112.png)

We randomly sample different sub networks and we jointly fine tune the sub networks and then repeat this process where the small child networks are en nested in the larger ones so we truly only onces。

 we can perform， we can produce many different sub networks。



![](img/59bb15ccd45ead4e52fbc007870bf273_114.png)

And by the way， the lab three is released today， the neural architecturection search part。

So make sure to visit our website at Eic Ial about AI to download the neural architectureecture search lab。

And the model searched by tiny Nas actually and better utilize the memory。



![](img/59bb15ccd45ead4e52fbc007870bf273_116.png)

So this is before this is after we can see the peak memory for different layer is very imbalance for hand and design Mo level tool。

The difference between the max and average is 2。2 times。To the largest layer。

Determined the bottleneck is actually the largest layer so you have to have at least this amount of memory so that you can hold this network well depending us search the model has a smaller gap between the max and average its more balanced versus there is a very big peak。



![](img/59bb15ccd45ead4e52fbc007870bf273_118.png)

So tiny us can design networks with more uniform peak memory distribution for each block。

 allowing us to fit a larger model at the same amount of memory。

So this is comparing the MZunenet with different prior work， MZunenet which is Monet pro NAs。

 we learned before。

![](img/59bb15ccd45ead4e52fbc007870bf273_120.png)

This is our winning in 2029， actually we make it 2。 or 2。4 times faster to lose the latency。

The lower the better and here is the visual weightward accuracy， the higher the better。

 so M that is faster and also here is the memory a aRAm measured in fetobytes about 3。

7 times smaller compared with this Mo everyV2。

![](img/59bb15ccd45ead4e52fbc007870bf273_122.png)

呃 green part is multi likely too。So let's revisit the problem of this imbalanced memory access where the peak memory is the peak is actually the bottleneck。

 not the average。

![](img/59bb15ccd45ead4e52fbc007870bf273_124.png)

And the recap， the asRM usage is dynamic， repair care about the peak asRM。



![](img/59bb15ccd45ead4e52fbc007870bf273_126.png)

So roughly we can find there are two regions the first region is layer0，1234。

 this this is memory consumption for each layer in this case。

 ranging from 500 to 1400 this this is memory usage put across different layers。

 the first couple of layer is using a lot of memory。

 very high bars and the later blocks as you down sample and down sample with down sample the resolution gets smaller and smaller so the activation is actually getting smaller and smaller。



![](img/59bb15ccd45ead4e52fbc007870bf273_128.png)

And here is the 256 constraint of a map controller and so this is our memory constraint。



![](img/59bb15ccd45ead4e52fbc007870bf273_130.png)

And what happens here？You can see from stage zero to stage four， they are all above this 256。

Constraints of the controller， but after layer5， they are all below this memory constraint。

 which means after layer five it can fit， but the four layer layer5， especially layer two。

 is actually eight times eight times larger。

![](img/59bb15ccd45ead4e52fbc007870bf273_132.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_133.png)

Compeded with our constraints。

![](img/59bb15ccd45ead4e52fbc007870bf273_135.png)

So only the later part， later blocks can fit。But the first couple of blocks has very high memory consumption consumption。

 it can fit。

![](img/59bb15ccd45ead4e52fbc007870bf273_137.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_138.png)

So if we can reduce the memory usage of the initial five stages。

 then we can reduce the overall memory。

![](img/59bb15ccd45ead4e52fbc007870bf273_140.png)

And so how do we save the memory？So we can break the monitor bottleneck by patch bas inference。

So let's look at the original conventional approach， so here we have two layers， this is layer one。

 this is layer two at each layer we gather the whole input。



![](img/59bb15ccd45ead4e52fbc007870bf273_142.png)

Produce the whole output and then produce the whole output for the next layer every time you have to finish calculating the whole output over a particular layer like layer one before you calculate layer two。



![](img/59bb15ccd45ead4e52fbc007870bf273_144.png)

What is alternative？So rather than calculating everything， now we just calculate。



![](img/59bb15ccd45ead4e52fbc007870bf273_146.png)

One quarter。One quarter of the activation。And then we can we can directly go to the second layer。



![](img/59bb15ccd45ead4e52fbc007870bf273_148.png)

We just calculated just like eating a pizza， if the pizza is too large， you cannot eat it。

 then you chop it divide it into four pieces and need a smaller smaller pizza。



![](img/59bb15ccd45ead4e52fbc007870bf273_150.png)

And here we have four smaller pizza。AndFinally we have to hold the entire output。

 assuming after a couple of down sample layers this becomes a smaller pizza okay。

 so this one has to be everything you have to hold everything in the menu before that for these larger activations you can divide it into several patches so we call that patch per patch inference the patch inference rather than this kind of per layer inference。



![](img/59bb15ccd45ead4e52fbc007870bf273_152.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_153.png)

And what is the upper bound of the memory saving in this case， how much times of memory may you save？

Depends on the number of patches right so here we divide it into four patches。

 so the upper bound will be four times。If you divide it by three by three。

 the upper bound would be nine times。

![](img/59bb15ccd45ead4e52fbc007870bf273_155.png)

But it's the upper bound， it's not achievable because you have to fit。

 you have to store all the activations in the next layer， the final layer in the magnet。



![](img/59bb15ccd45ead4e52fbc007870bf273_157.png)

So let's see what happens after applying this patch based inference。

So by using the pervaor inferencefer， it keeps the memory， the peak memory is 1，372 kilobytes。

But after applying per patchch inference， they reduced to one7 and2 kilobytes。



![](img/59bb15ccd45ead4e52fbc007870bf273_159.png)

It's a lot less。So it's pretty amazing that all these high bars。

 large memories now suddenly gets much smaller。

![](img/59bb15ccd45ead4e52fbc007870bf273_161.png)

Even smaller than 256 threshold， kilobyte of threshold of the microcon。It's pretty amazing， Finally。

 we can feel it。And now let's see the theoretical forex saving on two by two patch。

And the nine times saving for three by three patch， what is the actual achieved saving？



![](img/59bb15ccd45ead4e52fbc007870bf273_163.png)

So the highest bar corresponds to the per layer inference， right， 300 300。Pillowbins with their head。

The middle part is per patch by two by two catch， okay， so 315 now becomes 113 roughly 3 x saving。

 not4 x since that's the theoretical limit。

![](img/59bb15ccd45ead4e52fbc007870bf273_165.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_166.png)

But you could use three about three a。

![](img/59bb15ccd45ead4e52fbc007870bf273_168.png)

That becomes about five times 4。9 times smaller， reduce it to only 64 kilowatts。

Same observation for different network architectures。Which is pretty good。 But is there any。

Drawback any problem and overhead using such kind of perpech based inference。V is but all happens。

Where does the latency overhead come from？Sequificial rather than patches。

 right if if the parism of the device is pretty big， now we limit in the par。

But in micro controllers， they usually have very low challenges。We can you two instructions for site。

When you learn it on micro controllers， that may not give an indication of GPUs are idea to be Christian。

But overall direction is spread， there' latency overhead， where where does the overhead come from？

So if you think about just one layer， so this is just one layer output， this is the input。



![](img/59bb15ccd45ead4e52fbc007870bf273_170.png)

The convolution has a receptive field， if this three by three convolution， the output is two by2。

 what is the effective receptive field？So here we have about three by three column。

Detroy it in tool removing by two pixels。So the receptive field is five， high by five。

So everything in this yellow region will impact in yellow region here。

Everything in the blue region here will impact Blue region here。They have no overlap at this point。

 but they have a one pixel overlap here。Repeated con， redundant computation in the halo region。

Even before that layer， the receptive field gets propagated。

It gets larger and there's a three by three overland halo region。

So it's not complete independent divided independently， but they have the overlap。



![](img/59bb15ccd45ead4e52fbc007870bf273_172.png)

The yellow region and the blue region overlapped by three by three。

 nine pixels so such overlap caused thecomp overhead。



![](img/59bb15ccd45ead4e52fbc007870bf273_174.png)

And such spatial overlapking comes from the receptive field roads embedded into a larger computation overhead。



![](img/59bb15ccd45ead4e52fbc007870bf273_176.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_177.png)

And how much is the overhead we measure that on over  only2 or5 is about 10% overhead。



![](img/59bb15ccd45ead4e52fbc007870bf273_179.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_180.png)

So everything， an order of magnitude to a little smaller can be ignored for first order approximation。

 but actually we can do optimization to actually remove。That 10% overhead by redistribution。

How do we do that？Since the reason for this overlap。Is due to the larger receptive field。

 the recept field from two by2 to five by five， seven by seven， you have a larger receptive field。



![](img/59bb15ccd45ead4e52fbc007870bf273_182.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_183.png)

What if we limit or reduce the receptive field that will reduce。The area of the halo。

 the overlap region。So actually we can redistribute some layers。



![](img/59bb15ccd45ead4e52fbc007870bf273_185.png)

So here the first couple of layer， we are using per patch based inference。

 later peak later the add layers， we are using the normal per layer inference。



![](img/59bb15ccd45ead4e52fbc007870bf273_187.png)

Since remember in the figure here， only the first couple layers suffer from pretty big activation。

 but later these late layers they can fit the memory already so we don't need to apply the perpe based inference。



![](img/59bb15ccd45ead4e52fbc007870bf273_189.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_190.png)

In the later stage， but only in this early stage before here。

 we have to apply this per patch based interface。

![](img/59bb15ccd45ead4e52fbc007870bf273_192.png)

And since the receptive field is causing memory overhead， let's remove。

 reduce some of the receptive field。We can change this three by three convolution into one by one convolution。

Okay， smallerler kernel size means smaller receptive field， we can also remove one layer。

 remove one three by three layer to reduce the receptive fieldback pool。



![](img/59bb15ccd45ead4e52fbc007870bf273_194.png)

But the total receptive field need to remain the same so we can compensate that by redistributing the receptive field from the first stage to this later stage。

 but here we added one three by three convolution layer to compensate so that the final receptive field stays the same。



![](img/59bb15ccd45ead4e52fbc007870bf273_196.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_197.png)

So we use this network redistribution to reduce its overhead。



![](img/59bb15ccd45ead4e52fbc007870bf273_199.png)

And finally， latest the number of Macs here， the number of Macs using percache based inference becomes the same as before。



![](img/59bb15ccd45ead4e52fbc007870bf273_201.png)

Although we changed the architecture， the reive field didn't change and we the accuracy after prun。

 when you mentioned that classification object detection the accuracy is very well maintained。



![](img/59bb15ccd45ead4e52fbc007870bf273_203.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_204.png)

All right， so finally， we can apply this per patch based inference into the search space and joint play。



![](img/59bb15ccd45ead4e52fbc007870bf273_206.png)

Search the neuroarchect and inference scheduling methods。

The neural architecture includes the number of layers， number of channels， thermalnal size。

 resolution， inference scheduling means whether we use perpe based scheduling or and how many patches do we use like two by two or three by three。

You can see there's diminish return。

![](img/59bb15ccd45ead4e52fbc007870bf273_208.png)

How many layers do we use this per based inference and also other knos in tiny engine we are going to cover in the next lecture？

Okay， so putting everything together， we can further improve this visual weakcourse under only 32 kilobytes of memory。



![](img/59bb15ccd45ead4e52fbc007870bf273_210.png)

So what is visual withward， basically deciding whether there's person or no person in the field。

So this is the improvement across the years， so X axis is the。Measure the peak IRAM usage。

 the smaller， the better Y axis is the visual weightworth BWW visual weight accuracy。

So this is our 2019 results， this is 2020 results， this is 2021 result。

 every year we are pushing around by2 to4 times smaller from MZ net， which is version 1。

 here is a version2， MZnet V2 which introduced is per patch based inference using 2 by2 patch。

 we can save about 4 x， the memory consumption， or using the same memory 1 18 kilobyte but 4% better accuracy。

And look at this model， only 0 30 kilobys， 30 kilobyt of by round。



![](img/59bb15ccd45ead4e52fbc007870bf273_212.png)

But taking achieving 1% of accuracy。

![](img/59bb15ccd45ead4e52fbc007870bf273_214.png)

And using per cash based inference to peak and strand at the same accuracy。

 metas accuracy is reduced by 4X。

![](img/59bb15ccd45ead4e52fbc007870bf273_216.png)

And not only on that binary person versus no person classification。

 but I'm that need to also advance classification detection to large scale。

 like an image1 level classification result。

![](img/59bb15ccd45ead4e52fbc007870bf273_218.png)

So this is accuracy improvement of IUMV2 versus Amazon net under 256 kilobytes of IRAM versus 320 kilobytes of iceRAM。

 by big improvement。Given the same memory， now we can fit a larger model。

 larger activation so that the accuracyes are higher。

this is MMoV2 plus CMC which is your first library from ArRM this is MS IV2。

 this is the object detection I also a quite big bubble digit improvement from MU NV1 to MU IV2。



![](img/59bb15ccd45ead4e52fbc007870bf273_220.png)

So let's take a five minute break before we dive into details to dissect time 92。Okay。

All right welcome back so let's continue to discuss let's dissect the mobile and architecture to understand some of the design principles and see this kind of automated design actually have lots of insights。

 for example， the kernel science。In the perpech stage， which。

Is this early stage where the resolution is pretty big the activation is pretty large so that we have to use per patch based the inference to fit it in the memory okay the kernel science is actually chosen to be pretty small that's a decision made by our neuro architectectural search algorithm to reduce the spatial overlapping。

 okay the smaller the overlap， the smaller the halo。



![](img/59bb15ccd45ead4e52fbc007870bf273_222.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_223.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_224.png)

The less overhead for compute， which makes a lot of sense。



![](img/59bb15ccd45ead4e52fbc007870bf273_226.png)

In the middle stage， the expansion ratio is actually small to reduce the peak memory。

Because here the down sample layer is not too many， so the resolution is relatively big。

 it's not as big as here， but it's much bigger than those a later stage。

 so the expansion ratio in the middle stage is small to reduce peak memory。



![](img/59bb15ccd45ead4e52fbc007870bf273_228.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_229.png)

And the e expansion ratio in the later layer is getting much larger。

 much wider here because the resolution after a lot of down sample is already pretty small。

 so you can fit a much larger width。

![](img/59bb15ccd45ead4e52fbc007870bf273_231.png)

And also we find we can fit a larger input resolution okay for those resolution。

 sensitive data sets like region weakwards， make sure you have a larger resolution。

 so even a smaller person far away， you can still detect him on her。



![](img/59bb15ccd45ead4e52fbc007870bf273_233.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_234.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_235.png)

Versus our last generation M F1 can only support after 128 now we can support 160。



![](img/59bb15ccd45ead4e52fbc007870bf273_237.png)

Okay， so having learned about how to search， how to design tiny tiny models。

 let's try to visit some to see what kind of applications can we build， including tiny vision。

 tiny audio and also tiny time series and also anomaly detection。



![](img/59bb15ccd45ead4e52fbc007870bf273_239.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_240.png)

So starting with the simplest tiny image classification。 So this is a demo from Google。

showing the microcontroller can do very simple classification between oranges。

 bananas and apples and here is the probability actually this is super easy you can you don't even need a neuralnaural you can just look at the colors the RGB colors so can you see distinguish different fruits。

ButWhat gets more challenging is to expand it to large scale， on image design level。

 real life applications。

![](img/59bb15ccd45ead4e52fbc007870bf273_242.png)

I'm assuming that can actually achieve that more than 70% to accuracy。

 this is the level of mobileNe we're used to acquire a mobile phone to do such tasks。

 but now we can feed into a couple of dollar micro controller first to achieve more than 70% imaging accuracy of commercial microcontrolls compared with prior work likeL2 can only achieve 53%。



![](img/59bb15ccd45ead4e52fbc007870bf273_244.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_245.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_246.png)

Another application is the oh， by the way， there are different chain ranges of map controllers。

 some of them as 256 kiloyte。

![](img/59bb15ccd45ead4e52fbc007870bf273_248.png)

Some of them has two bygabyte flash， some of them have one megabyte flash it's very hard to design different models for different weights for different constraints right。

 but thanks to the once for all effort， we can just train a single model and then we can specialize according to the constraints for the activation。

 constraints for the weight。

![](img/59bb15ccd45ead4e52fbc007870bf273_250.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_251.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_252.png)

Just training on device， we are going to explore such automated search using even our homework in app three。

 which is released today and feel free to try it out。

Another application is for image classification is visual vehicles。



![](img/59bb15ccd45ead4e52fbc007870bf273_254.png)

So this visual wwards to detect if there' is person or no person， if it's just background。

 we don't have to trigger the second pipeline stage by recognizing who it is。

 little can just keep it idle this might be a much larger model seems this more complicated that to face and to see who it is but the first stage can be done in a very small model only if there is person then the second stage which is face recognition will be triggered。

 otherwise we don't trigger that to preserve the battery to save the privacy。



![](img/59bb15ccd45ead4e52fbc007870bf273_256.png)

Here is a vanmo。We shop in building 38 in the elevator， this is my postdoc。

So we have this microcontroller right here as a light， if it is red， showing there is person。

You these screens showing there' is no person recognizing them on the microcontroll。

And we also have a demo from our T pad that you can。

We distributebute the d across everybody body to take a look。

 we just place it in front of person to see the lights， if it is a person in front of it。

 it'll be in red， otherwise it should be in green。嗯。

The microcontroller without a screen is the visual vehicle then。

We can also do a tiny object detection okay per using this perpech based inference。

 the challenge is that to do object detection you really need a pretty high resolution and high resolution means we need a larger activation larger activation means。

A high astomic consumption， which is challenging。And resolution matters a lot for the accuracy。



![](img/59bb15ccd45ead4e52fbc007870bf273_258.png)

So here from March records resolution， if you shrink the resolution。

 the accuracy is going to degrade not very much for imagenet in the in the red yellow curve。



![](img/59bb15ccd45ead4e52fbc007870bf273_260.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_261.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_262.png)

Or actually you should print point the camera。Do someone see the vertically。

 just can you please tell them the direction。 It's not horizontal to the vertical， I remember。



![](img/59bb15ccd45ead4e52fbc007870bf273_264.png)

But if you can see for the detection to work， it's actually very sensitive。

 very sensitive to the resolution the actual resolution gets smaller。

 the accuracy drop are very sharply here。

![](img/59bb15ccd45ead4e52fbc007870bf273_266.png)

So perpe based inference is getting very helpful to maintain the accuracy。

 so here's a demo for object detection， this is phase and mass detection， this is person detection。

And you can see。Here in person comes and here the maskst is br。Then this has no mask， so it's red。

This project was done during COVID so we can tell from the demo is when the project was done。

 we have a lot of masks at that time in the lab。And what is the advantage of using such catch catch based inference okay so this is without using patch based inference。

 this is with using catch based inference you can see this boy was missing。

 the detection was missing but using patch based inference can be defected。

And here there's a mixed mispred on the hand， but there's no mispredation。

So is here the amount I lost the bunging box。Because the phase was side face and now we could detect it using M92。

 here is a misrediction， here is no misrediction， so high resolution helps a lot per patch based patch based method allows for larger input resolution which helps a lot with the accuracy。

We can even do on device training。Okay to learn new tasks on the micro controller。

 so here' is a demo， we have two buttons on this micro controller。



![](img/59bb15ccd45ead4e52fbc007870bf273_268.png)

A red button and a green button will push the green button for the orange。 We push the。



![](img/59bb15ccd45ead4e52fbc007870bf273_270.png)

read button for the banana呢。I then do it啊。A couple of times。To give it a few labels。

Here is doing the back propagation locally on the device。Including ingredients。The activations。

 the weight， we have to fit everything in the microcontroller。And after a while。

 we can distinguish the banana versus the apple okay we are going to very such technique in the later part of this lecture when we talk about cleaning。

So that tiny vision task， we can also apply it to tiny audio tasks。

So audio is a very common application in daily lives， like we can do audio keyword spotting like hey。

 Alex O， Google， pay Siri， etc。For speech recognition for noise cancel cancellation。And actually。

 we can turn this audio problem into a visual problem because we can convert this speech signal。



![](img/59bb15ccd45ead4e52fbc007870bf273_272.png)

Okay good， yes。Into the2D fishisher map， the axis is the time dimension。

 The vertical dimension is the frequency dimension， and the strength indicates。



![](img/59bb15ccd45ead4e52fbc007870bf273_274.png)

Thet spectrum on different frequency。On different frequencies so that we can do convolution on the 2D feature map is no longer one dimensional It actually becomes two dimensional。

So we can run those classification problem similar to an image recognition to understand the speech。

 what you see is no of exception。So you can usually outperform the fully connected layer using an intervolutional layer since there's the local locality relationship between in time versus in frequency adjacent time versus adjacent frequency usually the signal as relationships。

 so we want to capture those local relationships by convolution。



![](img/59bb15ccd45ead4e52fbc007870bf273_276.png)

And here we can see the force force reject。On CM， the models is really better than the F layers。



![](img/59bb15ccd45ead4e52fbc007870bf273_278.png)

And MCUnet can also improve the efficiency on speech command data we have a lot of speech command and we want a low latency and high accuracy。

 so this is comparing Mo92 products is NA versus MCnet， which is on the good front here。And finally。

 we have tiny time serious anomaly detection widely used in manufactureries。

And also applied it to video surveillance in healthcare to prevent fraud to detect abnormal products。

So here we can see this is a normal normal capsule， this is an abnormal one， this is a normal knot。

 this is an abnormal knot。And we want to use this machine vision to detect those different anomalies。

And also analyze very long videos to see something normally happen。

But recently with the announcements of large language model， especially the visual language model。

There are alternatives to that， so we try， we're going to cover this later in the lecture。

 but we want to give you a peek。So just put these two nuts。

And feed it to our visual language model called the Vla， it has 7 billion parameters。

 it can do a lot of stuff。Here we ask it， the first image is normal is a normal nu。

What is abnormal for the second image， they can tell the second image is abnormal because it shows a knot with the whole image。

So it can generalize quite a well and understand images and languages。

So the technology is evolving pretty fast just within two years。

 I made this slide roughly two years ago and now a lot of changes in the technique with the advance of large language model。

 which will be our focus for the second half of this lecture。So before large language model。

 how is this done？To detect anomaly with auto encoders， okay。

 so auto encodeder is a very key technique。

![](img/59bb15ccd45ead4e52fbc007870bf273_280.png)

So given an input signal， that it first passes through a encoder and project it into a low dimensional code vector。

 so input may be of high dimension like high resolution image。

 but here it has a very low low dimension。Wwhich is the abstraction of input and finally we pass through a train decoer。

 the deco decoer takes this low dimensional vectoring as input and try to reconstruct the output to be the same to be the same as the input。



![](img/59bb15ccd45ead4e52fbc007870bf273_282.png)

So that's the structure for an auto encoder to predict the input ideally。

 the x flash should be the same as X。

![](img/59bb15ccd45ead4e52fbc007870bf273_284.png)

And during the training， we try to minimize the reconstruction error。

 so this is the input this is the reconstructed output。

 which was reconstructed into using this low dimensional code vector。



![](img/59bb15ccd45ead4e52fbc007870bf273_286.png)

And if the input is following the desired distribution， then。

The difference between the input and output would be pretty small otherwise。

 if the input doesn't follow the trading datas distribution like an abnormal data appeared in the input。

 the reconstruction， the reconstruction error will be high because in the trading data it does not look like this。

 so it cannot reconstruct a abnormal input data， therefore the reconstruction will be high。



![](img/59bb15ccd45ead4e52fbc007870bf273_288.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_289.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_290.png)

But if the input image follow the normal distribution。

Which has a lot of such images in the training data。



![](img/59bb15ccd45ead4e52fbc007870bf273_292.png)

The auto importer will be able to reconstruct the output。

 so the reconstruction error will be low for normal data and will be high for normal data。

So we can use such auto encoder to deal with many different signals， including images and also sound。

And the audios， so here's a demo。To detect the anomaly detection for the fans。

 so we purchase the fan and here we have a microcontroller attached to the fan。

 which has 256 kiloby SM， only one megabyte of flash， only 64 megahertz。



![](img/59bb15ccd45ead4e52fbc007870bf273_294.png)

![](img/59bb15ccd45ead4e52fbc007870bf273_295.png)

And we apply anomaly detection here。And when we are picking the fund using a screwdriver。

And we can see later the light is going to change the color。



![](img/59bb15ccd45ead4e52fbc007870bf273_297.png)

Yellow light is moving light up。Right here as we poke。A the fun greatest is some noise。

And after a while。The you know light will be severe here。



![](img/59bb15ccd45ead4e52fbc007870bf273_299.png)

Until we shake it。The yellow light will appear again。Since we have a generous scope。

 I have several metter。应的范好。

![](img/59bb15ccd45ead4e52fbc007870bf273_301.png)

You shaking it。If we will light up， the yellow light we will light up， it's pretty small。



![](img/59bb15ccd45ead4e52fbc007870bf273_303.png)

Okay， so this is the summary of today's lecture， we introduced the tiny andL concepts and the challenges of tiny and now。

And also how do we design the models that can fit tiny devices and apply them to our daily lives。

 including vision task， audio task， and also time series tasks。And finally。

 let's see some of the demos。嗯。Our AIT。Which might introduce in the last lecture and I see some of the demos the website is actually MIT。

study。It's cater for our course。So we can ask some questions， Mike。

If you're not clear of some concepts， like。好诉。form。冇到。Instill， which we learn。In the last lecture。

We are using the rag technique。Um to do the embedding of our lecture slides， lecture notes。

 and also lecture videos。And we put it in cabinet。The question with our prompt and speak to。啊。

 fade对 to the啊 large language拉。And then it can give us a very detailed answer。

And what I like about it is you can actually click the link。to watch the corresponding lecture video。

You can also click the corresponding respond link。To find the textbook which describe this particular concept。

What is interesting is actually you can test yourself by creating quizzes。For example， for example。

Create aquiz。About。有难说。因本来是。What is quoteates？嗯。What is the primary goal of the network reporting。

 increase the model size， reduce the model's computational compact enhance the model's accuracy。

 increase the number of neurons。Seems pretty simple we can also ask you some complicated concepts。啊。

来。How to maybe you guys can ask a question。Some， some questions you want to ask in Paza。

 that's find here。Thank。Somebody want to give it a shot。

If the activation if the activation is larger than the patch size。嗯， how to。Perform。

Hch those new friends。嗯个。O。It's like a somewhat。嗯。The input is rather than the patch size。

 doesn't claim excess。You the object is larger than the batch size。Oh。

 then maybe one object will be across two different patchs， that's what question right okay about it。

广84。Howut to perform patch based inference if the object is larger than the type size。

Divide the input image into smaller manageable patches。

 each patch is processed separately through the model。

 this reduces memory consumption and allows inference on devices with limited resources such as microcontrollers。

We talk about a receptive field distribution that's exactly what we discussed overlap handling the general letters and finally do new right type search I think this is very general。

 but it didn't give you saw view a very specific question。In this case。

I would be able to vote because it's not specific。对。All right。

 so that's maybe one candidate for you to think about for final projects building something like this will be very doable for the final project and feel free to ask the IT but we are always here to help you so consider us as the final source of help okay。

All right， that's all for today's lecture， thank you。



![](img/59bb15ccd45ead4e52fbc007870bf273_305.png)