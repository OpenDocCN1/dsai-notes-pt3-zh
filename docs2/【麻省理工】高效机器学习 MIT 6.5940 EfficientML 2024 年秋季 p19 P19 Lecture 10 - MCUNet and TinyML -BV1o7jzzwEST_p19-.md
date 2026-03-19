# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p19 P19 Lecture 10 - MCUNet and TinyML -BV1o7jzzwEST_p19-

Okay， welcome everybody， let's get started， so today we're going to talk about E model AI lecture 10 about NCnet and tiny MLL。

So for this lecture we are going to cover the following sections， so what is tiny now。

 and what are the challenges of heading now and how to design those tiny neural networks。

 and what are the applications including tiny vision， tiny audio， tiny tiny series。

 and also anomaly detection。So just give an overview of where we are so far。

 we talked about a lot of techniques to shrink， to compress neural networks。

 including pruning quantization， installation， neural architecture search。

 and now we want to combine these different efforts together and build some cool applications and really deploy them on small devices。

So when it HM mouth， today's at AI is pretty big。As we shown across the years。

 the model size measured in billions of parameters that were super fast。

But we need always of on hardware。New algorithm and hardware that is more efficient。

 efficient for inference， efficient for training， rather than taking a giant。

 a lot of resources for memory for compute， but we can fit them in our pocket。

 fit them in our phones and reduce the， reduce the carbon footprint footprint towards the we。

So recently the TGBT， the G3， I contains 175 billion parameters。

It think 355 years GPU years to train cost more than $4 million， pretty expensive。

 and the Algo between years ago took 1，920 CPUs， and 280 GPUs， which costs $3。

000 per game just to play one game。On the contrast， we hope deep learning can go go tiny。

So not only on the cloud， but also on the edge， where we no longer have to transmit our personal data。

 either the image or the text or the voice to the cloud， which may suffer from。

There was several attacks。And privacy leaks， et cetera。

 but we want to keep everything local on the phones。And even on smaller devices。IOP devices。

For example， microors。These microcontours are everywhere in the lives and their lives。

They are feedings IOT devices around the world based on microcontrollers。

And you can see across the years。IT devices are increasing。And they have very low cost。

 just at a few dollars。So everybody can afford it。We can democratize AI to these low cost edge devices。

And also they are of low power， so we don't have to worry or battery get streamed right running out of battery or you go to spaceship。

 there's no Wifi connection and there's also limited the battery。You can run them in very low cost。

 in low power， even using renewable energy that will be super cool。

And this a tiny amount application for a lot of usage across different aspects like smart home you control different appliances in smart manufacturing to do automatic。

Defect， detection， personalized healthcare， adjust dose according to different patient' symptom。

 and precision， agriculture。But it's not easy。 Tanmount is quite talented。

What makes it so challenging？The resource， primarily the memory resource。

So for cloud AI you can easily get- in this slide thiss showing 32 gigabyte of memory。

 but now you can easily get 80 gigabytes of memory on8100， H100 GPU， which hasabte。

 terabytes or even  petabyte of storage to slower weights on data。On mobile devices， like our phones。

 we can easily get a couple of gigabytes of memory and hundreds of gigabytes of storage。

 that's plenty。But on those microcontrollers， the resource is tiny。

You have a couple hundred kilobys of memory for the asRA to hold those activations。

And you have maybe just oneby， one megabyte of storage。啊。In the flash。

AndThe flash is only sometimes read only can write to it。Only the ashronom is ratable。

 so the resource is very tiny。It's four quarter to five orders of magnitude smaller compared with the cloud AI and also the mobile AI。

So we need to reduce both the weights and also the activations so that we can fit these deep neurals into ti。

So compared with mobile AI， where we are constrained by the latency。And also there constrain。

 but the energy now we have a new constraint， the memory。真是。tiny devices has very little memory。

And lots of the principles can actually be applied for large level model these days since they are so big。

 even one GPU can hold can accommodate all the weights， like 175 billion parameters。

quantize them at P6 team， that's 340 gigabytes。GPU has nice than 400。

So same principle also apply to larger model。Okay， so let's start deeper to understand the challenge。

 especially the memory challenge of TML。 What is the bottleneck for the weight memory。

 What is the bottleneck for the activation memory。So this is the overview of pollution neuralaxs。

 We have a couple of。Coliators， coolators。Followed by F layers in this case。

For each layer we have an input activation， the off with a kernel the a kernel and produce this output activation。

Where do we need to store？Since we are considering about the memory， let's that deeper。

 where are they sport？So input activation or op activation， we need to both read and write。We win。

ThePrevious input would be right to the output of the next layer。So啊。

It has to be both readable and readable， so it consumes the asRA。

 which is both readable and readable as for static， static， random access。但是万。

And for microcontrollers， they usually don't have any Iran。

 only a couple of very little resources for flash， so it's rid only it， so only the weights。

 the weights is actually rid on it if you don't do effect propagation if you don't do training。

 the weight can be stored。In the flash。And the flash different from Ash。If you power off the device。

 the data in the IM will be gone。The flash can hold。The data is not volatile。诶。

But the iceron is volatile tile。If you power off the device， the data I stream will be done。

You don't want to wait to demand， So you have to store the weight in the flash。

So these are some powder。Mobile microconctor devices。We know this device has 256 kilobytes of aRAm。

1 MBgabyte。This item 32，7746， which we use。Has 320 kilobybyte run of one microgaby flash。

So that's a small resource。Okay， so the flash usage。

Rund for equal to the model science because they are static， they have to be naal tile。

 you need to hold the entire model so the number of weights its constrained by the size of the flash。

 we're going tovis revisit this later part in the lecture。So the weight has to fit the flash。难忘了他。

And the enter on usage， roughly you go through the equal activation plus the output activation。

Since they are read and read dynamic by during the inference。And we care about the peak HR usage。

 which means the largest layer in the size of the largest layer determines our peak memory usage。

And weights are not content here as since they can be partially， attached them compute on the away。

So what is the gap here？So this is comparing Re 15 mobile every tool。More than in think were。

Here is a 320 kilobyte。Of memory constraints。Remember， micro controller has。Well。

 rather P has shown usage23 times larger。包括那一兔把这兔子产拿。quantization we learned in the previous lecture。

Slightly reduce it by four times its very good， but still five times now。

 so we are going to bring this lecture how do we overcome this gap and be able to fit？

We model in the microcontroller as well， having female accuracy。So what are the efforts， prior。

 what are the prior efforts？So we learn about Mo I tool。

 which is a very small model targeting mobile devices like mobile phones。But still， that's too big。

And if you see the bottleneck， especially the activation bottleneck。

 it's very unfortunate that the activation didn't decrease， but actually increased。By 80%。

So it's better primary efficient。So you can compare。Here is residentnt 18。

And here this is the Mo I tool， 0。75。The weight。Is to reduce them at more than four height。

That's pretty efficient， the weight is much smaller。

 so it takes less to communicate from the Apple store to download the app。So that's pretty good。

However。The peak activation， even decrease or increase。So that's a the problem we need to solve。

So we are going to learn about NU net， okay， not only reduce the weights by six times compared with。

Rent Re 18。But it seen no accuracy。But also the peak activation is also reduced。By 3。4 x。

 compared with Mone。So that's our goal。 We have to balance both。A number of parameters。

And also the peak activation， we have to fit both of them in the microcon。

 If you cannot fit any of them， you cannot fit the model。

So let's go through formulate how do we design these tiny neural networks。

 given the understanding of the challenges given the concept we learned so far。

 we'll introduce I soon that the system and algorithm co design。誰か送り。It's covered by I news。

A couple of years ago， which is very new。So的 system offer code上。We have a very large design space。

 we can either design the algorithm side by changing the neural natural architecture。

Gn the fixed library。For example， we learn artist math。Designing a customized。

 specialized model given the hardware， given the library。

There's other work focusing on assuming the model stays the same， but we want to design。

 develop new libraries like TBM。What we find。The extreme efficiency comes from codesigning the neural architecture and also inference engine。

 you need to codesign both directions so that you can exploit and explore a larger design space。

 including the neural architecture and proposed efficient neural architecture and also efficient compile and run time so that you can map the architecture on the inference engine。

So。The basic idea a Znet is system and algorithm coar。In this lecture。

 we are going to cover the first part， which is tiny NAS， timing newer architecture search。

Aut to design automatically and optimize the model。Given the hardware research constraints。

And in the next lecture， we are going to cover the second part， the tiny engine。Efficient compiler。

 run time， how to optimize the universe engine。So let's start with pan nutss。Which has two stages。

 okay， two stage for neural architecture plants， for neural architecture search。Or。

This is a short recap， what is design automation， for neural nets， what is the motivation for that。

 so you'll remember to cover in the previous lecture rather than using a lot of engineers to hand design the model given a given however。

She called it manual Architure design。Its a lot of human。Pt is pretty expensive。

We want to use machine learning to automatically search a good architecture that fits our demand。

You're actually search。When we are doing a search， we talk about we need a good search space。So。

Like finding a friend in a forest， a forest is pretty large。

 we want to first narrow down the possible areas。Here or here。

 narrow down the search space before we do the exploration。

So the quality of the search space loade determines。At the performance of the search。

So the first stage of。The two stage of pen knot is actually to search the search space。

And find a good subspace， so I feel promising rather than explore the entire search space exploring a much smaller and constrained search space。

So how do we find that search space？One approach actually you can used the prior search space for mobile apps。

For example。好一边。The series from mobile device is quite different from these tiny micro controllertrollers which differ by a couple of orders of magnitude。

So even the smallest sub network in the mobile search space。Still cannot fit， however。

 due to the huge gap。So a mobile device has foldga of memory versus a microcontroller。3 had20。

Ktos memory。 So even the smallest。N work in the search space still cannot fit。不错了。So what can we do。

We have only designed a new search space， targeting IotT devices。他度为主的。So we can scale down。

 we can scale the previous search space for mobileNe， for mobilenets。

 using a different resolution and different with modifier。For example。

 the original search space typical for mobile devices， the resolution is 224 by 224。

 and the width is 1。0。That's pretty suitable for mobile phones。We can scale them up for GPUs。

 similarly we can scale them down for microcontrollers。

Then the question is how much do we exactly to scale them thus and if they have different microcontrollers also has different memory budget。

From 256 kilobytes all the way to 512 kilobytes。So the overall structure will be given a full search space we want to add our memory and storage constraint。

And then produce optimize the search space。And then perform newactive search on to。

So to optimize the search space， including two design k hubbs。

 including the resolution and also the width modifier。AndAfter that， we narrow it down。

 and then we search the criminal sciences， the expansion ratios。

 and also the number of blocks for each stage。So here is the algorithm for automated the search space optimization。

 and we want to analyze the fl distribution。We have seen this speaker before about that deeper。

And then analyze a fl distribution。It will satisfying models in each search space。

So here that axis is another of fls。And search of space。From 25 million plots to 65 billion plots。

Y axis is a cumulative probability。And different curves corresponds to different search spaces。

For example， the black search space。The width is 0。3， 30% weight， 30% width in the resolution in16。

And this ra is her space。With its larger，  is0。5， resolution is smaller， 144。

So in different search space。The fl is very different， for example in the righter space。

All the models。Has the fs more than 41 million fs。It is here it 41。Im here all the models。

Prime first module by 41。20% of the models here are coverage about 80%。W subtract。2 is 80%。

So 20% models are larger than 50 mes。Vasus the black curve has much smaller number of fliess。Here。

 all the models are about 28 million in fact 41 million。Here。It' 80% or minus 80% that's 20%。

So 20% of the models has larger than 32 media forms， whereas here it's 50 media formss。

So we can see these two different design spaces can fit different amount of fls even the same memory budget。

Since we learned that computation is cheap， memory is expensive。

We want to maximize the amount of flux we can work on the same amount of memory footprint。

A same amount of data movement， you fetch one bite of data you want to do as much of computing。

By fashion after fashion with data。So of course， a good design space is showing that。

If a good design is people design space can achieve high fls。

 a high fls of accommodate a lot of arithmetic operations under the same memory cont。

 then it's likely to be a good design space。And does it need the case， for example。

 the run man space， the best accuracy to get？Its778。7%。Well， for this collapse， that space。

The best equity that we get is only 74%。So this is very helpful heuristic。

Without having to train the model， we didn't even train the model。But we can just analyze the flops。

 analyze the flops。Accommodinate give a different design space。To protect final accuracy。Let's see。

 given different。In strings， let's analyze， feeling different and strengths。

And this is good and different。Flash size of the flash。

 ranging from5 to 12 kilobyte all the way to two mybytes。TheX is a flash。The wire access。

Its the asRA from 190 kilobyte to about 12 kilobyte， 192 kilobyte to about 12 kilobytes。

So we want to understand。When the flash increases。But this Aron side stayed the same。

What would happen for the waste bofire？And the first。

Blue curve or blue figure for the weight to modify it from 0 to4 in a 0。9。

The second image is showing in the resolution， some of them is 1 112， some of them is 2 or8。

So when the flash increase same as strength， what happens for the width modplifier？

The other question is， when asRA increase， you have more IRA in your electric controller。

 same on model of flash， what happens to the width modifier and what happens to the resolution。

I give you。One minute we'll think about this question。And I hint it' either。Three points。

 those points at come point。First point， second point。Let's do the answer。So with the flash ins。

 but SRAms stay the same， remember what gets stored in the flash， what gets stored in the asRAM。

A patients guest。Right， exactly， so flash sos， the weight back the kernels。

And thatron towards the activations。So with a flash increase。

 meaning you can hold accommodate in more weights。喂。So we can have larger amount of panel。

So that's why the way bodyifier is increasing。From00。4。What about the resolution。

Seems we have the same as。And the channels are getting larger， which means the resolution has to be。

So that a channel times the resolution square will be the same。

 otherwise you can hold it in the same amount of as。So modern panel some minor resolution。

Larger canal， smaller resolution。What about when astrout in Ukraine got a flash display？So Ira。

Stors your activations。But the flash stays the same。So here。We the resolution actually increased。

Because you can hold more activations。给后多。啊。But the flash says that the flash stays the same。

 which means the weight actually stays the same。 the flash scores the weight。

 the number of flash stays the same to the width roughly。Stays the same across human channelss。

Here are columns of the blue figure。Since the extra gets larger。

 we can larger feature at larger resolution。 So across the column dimension here。

 you can see the resolution actually increase。So this field will give you some inition about。

The intertwining relationship between ARA and flash， activation and weight， panel and resolution。

I mean， questions about this bigger in general？可人。So having figure out。The design space。

 we can now perform the architecture research in this design。

Because like trying to find your friend in the big forest， now you finally determine， okay。

 my friend is roughly in this area then I can focus on this area with circle。

So here we use the one fall approach we learned in the previous lecture。

 and now we apply them to do some real stuff， so we have this training super network。

This ones smaller on that road。We randomly set different sub networks。

We jointly fine tune the sub networks and then repeat this process where the small child networks are nested in the larger ones。

 so we train only once， we can perform， we can produce many different sub networks。And by the way。

 the lab three is released today at the Newer architectureecture Research Park。

So make sure to visit our website at Inionno。aiI。To download the neural search。

And the model searched by Pa gas actually can better utilize the memory。So before this is after。

 you can see the peak。Me if what is from there， it very em。For hand design more than。

The difference between the max and average is 2。2 times。So the largest layer。Determines it。

The bottle bank is actually the largest layer， so we have to have at least。

This amount of memory so that I can hold this network。Well。

 the Penn mass search the model has a smaller gap between the max and average。

It's more balanced versus its a very big peak。So tiny does can design networks with more uniform peak memory distribution for each block。

 allowing us to fit a larger model at the same model of memory。So this is comparing the M of that。

was different prior work。I'm assuming that this is more of that positive past than we heard before。

This is our Williamness。2029， actually we make it three to 2。5， 2。

4 times faster so this is the latency。The lower the better， and here is the visual weight。

H personally， the higher， the better。Im that is faster and also here it the memory。

 pick a ramp measure the feal bites。About 3。7 times smaller compared with。It's mobile every tool。

Green power smoke。So let's revisit the problem of this imbalanced memory access where the peak memory is actually the peak is actually the bottleneck。

 not the average。And then wecap， the as usage is dynamic， we care about the peak。Thats right。

So roughly we can find there are two regions， the first region is layer0，1234。

 and so this is memory consumption for each layer in this case。Ranging from 500 to 1400 this is。

Mem usage， for you across different layers， the first couple of layers is using a lot of memory。

Very high bars。And later blocks， as you town sample town sample you town sample。

 the resolution gets smaller and smaller， So the activation is actually getting smaller and smaller。

And here is the  total 26。Constraints of a Mac controller。And so this is our network Street。

What happens here？You can see from stage zero to stage four， they are all above this 256。

Constraints of the controller。 But after layer 5， they are all below this memory constraint。

 which means after layer 5， it can fit， but before layer layer 5， especially layer 2。

 is actually eight times eight times larger。没 hour。走 only the围块。Laterder blockss。

But the first couple of blocks has very high memory consumption and outfit。

So if we can reduce the primary usage of the initial five stages。

 then we can reduce the overall memory。And so how do we save the memory？

So we can break the modern bottleneck at hatch based in the。

So let's look at the original conventional approach。So here we have two layers。Maor one。

 this is made of2 at each range。Toge the whole。Produce the whole output。

And then produce the whole output for the next layer every time you have to。

Finish calculating the whole output of a particular layer like layer1 before you calculateulate layer 2。

What is alternative？So rather than calculating everything， now we just c。One quarter。

One close health。And then we can we can directly go to the second day。

We just calculated it just like eating a pizza， if the pizza is too large， you cannot not eat it。

 then you drop it directly into four pieces and eat a smaller smaller pizza。

And here we have four smaller pizza。Finally， we have to hold the entire output。

Assuming after a couple of thousandan layers， this becomes a smaller pizza。Okay。

 so this one has to be everything you have to hold everything in the memory before that for these larger activations。

 you can divide it。Several patches， so we call that patch or patch。Propeion friends。

Rather than this kind of pernaator average。And what is the upper bound of the memory saving in this case。

 how much times of memory are you save？Depends on the number of patches right so here we've divided it into four patches。

 so the upper bound would be four times。If you divide it by3 by three。

 the upper bottom will be nine times。But it's not problem bond。

 it's not achievable because you have to。Fit you have to store all the activations in the next layer。

 the final layer in the map。So let's see what happens after applying this patch space。

So by using the perlay difference。えきす。The memory of the peak memory is 1，372 kilobytes。

But also applying her patch inference for us。Reduced to 17 and2 kilowatt。It's a long mess。

It's pretty amazing that all these high bars， smart memories now suddenly gets much smaller。

You smaller the6 kiloby threshold of the macro controller。This is pretty amazing。

 finally look can feel you。And now let's see the theoretical forex saving or tool by tool patch。

And the nine times saving4 three by three patch， what is the actual achieved saving？

The highest bar corresponds to the per layer inference。300300。広場。Meddle part is a per patchch。

About 2 by2 catch， so the 113 now becomes Y 13 roughly 3 x， saving， not4 x。

Since that's a theoretical limit。But if we use three by three a。That becomes about five times，4。

9 times。Smaller， reduce it to 264 kilobys。Same observation for different natural architectures。

Which is pretty good， but is there any drawback， any problems。

 any overhead using such kind of per patch based inference？That is， but it's an overtime。

Where does the latency overhead come from？障和せて。Sequential rather than patches。

 right if the paradigmm of the device is pretty big， now you'll limit the paradigmm。

But the network controllers they usually have very low terrorism。issue to instruction for cycle。

So usually on micro controllers， that may not be a limitation if here use some idea。

But overall direction。There's littency over time。Where does the overhead come from？

So if you think about just one layer， so this is just one layer output'll， this is an input。

The convolution has a receptive field， if this3 convolution， the output is 2 by2。

 what is the effective receptive field？So here we going here by threecom。

De drawinging a tool by tool zones。So the receptive field is five， high by five。

So everything in this yellow region will impact the yellow area here。

And everything that blue here will impact forward。They have no overlap at this point。

 but they have a wide pixelx of overlap here。Repeated computation that computation。还有位。

Even before that layer， the receptive field gets propagated。It gets larger。

 and there's a three by three overlap payload region。So it's not complete。😔，Independent。

 the panel divided independently， but they have to overlap。

got the yellow region and the blue region overlapped by three by three， nine pixels。

So such overlap caused the computation overhead。And such spatial overlap comes from the receptive field groupss leading into a larger computation over。

And how much is the overhead， we measure that。V2 and5 is about 10% overhead。So everything。

 an order of magnitude a the smaller can be ignored for first order of approximation。

 but actually we can do optimization to actually remove。That 10% overlap by redistribution。

How do we do that？Since the reason for this overlap。Is due to the larger re field。

To re fuel from22 to five by five， seven to seven， and have a larger receptive fuel。

What if we limit or reduce the receptive fuel？That will reduce。The area of the halo。

 the overlap region。So actually we can redistributes。Some layers。So here the first couple of layer。

 we are using per patch based in difference。Later later the nters were using the novel per layer difference。

So remember in the figure here， only the first couple layers suffer from pretty big activation。

But later he late later。They can fit the memory already。

 so we don't need to apply the perpe based inference。NowIn a later stage。

 but only in this early stage before here， we have to apply this per patchch basically。

And since the receptive field is causing the memory overhead， let's remove。

 reduce some of the receptive field。We can change this。three three combination what I one。

Smaller kernelcience means smaller receptive food， we can also remove one layer。

 remove one3 by3 layer to reduce the receptive food by two。

But the total receptive field need to remain the same。

 so we can compensate that by redistributing the receptive field from the first stage to this later stage。

And here we added one， three by three con a year to compensate so that the final receptive field stays the same。

So we use this metric redistribution to reduce。おか他。Finally， they see the number of mats。

 the number of mats using。The patch based neprints becomes the same。As before。

Although we changed the architecture， the receptorive view didn't change。

 and we tested that the accuracy after prunning each classification of that detection。

 the accuracy is very well maintained。All right， so finally。

 we can apply this per patch phase inference into the search space and the joint way。

Search the neural architecture and inference scheduling letters。

The neural architecture includes the number of layers， number of channels， kernel size， resolution。

 Uni scheduling means whether we use per patch based scheduling or and how many patches do we use like two by two of river three。

 you can see there's diminish return。How many million do we use this per based inference and also otheromas in tiny engine we are going to cover in the next night？

Okay， so putting everything together， we can further improve this visual where we works。

Under only 32 kiloeto vitals。So why is visual way work？

Basicallyically having whether there's person or no person in the field。

So this is the improvement across the years， so X axis is the。Measure the peak extra usage。

 the smaller the matter Y axis is the visual wave force BWW visual wave accuracy。

So this is our 2019 results， this is 2020 results， this is 2021 results。

 every year we are pushing the front here by two to four times smaller from。I'm super mad。than one。

 and here is a bobon tool， and assuming that tool which introduced this per patch based inferences in2 by2 patch。

 we can say about 4 x the memory consumption or using the same memory1 18 kiloby achieve 4% better。

And look at this model33キロバ，3キロバ。I' takinging anach about%。AndU prop patch based nes。

 the peak and shrimp at the same accuracy net and accuracy is reduced by fo。

And not only on the binary person versus no person classificationification。

 but I assume that B too also advanced classificationification with action to large scale。

イメージたい level。Pification top。So this is accuracy improvement。

Iun at V2 versus amat and the456 kilobytes of aRA versus 320 kilobyte of ara。Had big improvement。

Given the same memory， now we can fit a larger model。

 larger activation so that the accuracy is higher。And this is Monga cool Po Sancin。

 which is our inference by for arm。でジさすだでと。This is the object detection accuracy。

 also probably big double digit improvement from I N1 to I N2。

So let's take a five minute minute break before we dive into。Details to disect。这这。All right。

 welcome back， so let's continue to discuss， let's dissect the Mo and visual architecture to understand some of the design principles and see this kind of automated design actually have lots of insights。

 for example， the kernel science。In the per space， which。

Now is's this early stage where the resolution is pretty big， the activation is pretty large。

 so that we have to use per patch based inference to fit it in the membrane。

The kernel science is actually chosen to be pretty small。

 that's a decision made by our neuroarchural search algorithm to reduce spatial overlapping。

 the smaller the overlap， the smaller the halo。The last overhead for compute。

 which makes a lot of sense。In the middle stage， the expansion ratio is actually small to reduce the peakment。

Because here the down somehow layer is not too， so the resolution is relatively big。

It's not as big its here， but it's much bigger than the later page。😊，So the expenditure ratio。

 the middle stage small to reduce peak memory。And special ratio in the later layer is getting much larger。

 much wider here because the resolution after a lot of done sample is already pretty small so you can fit a much larger width。

And also we find we can fix a larger input resolution for those resolutions sensitive data sets backwards and truly have a larger resolution。

 so even a smaller person far away you can still detect him or her。Versus our last definition。

 and91 Cal support App to 128， now we can support Y60。Okay。

 so having you learned about how to search， how to design tiny tiny models。

 let's try to visit them to see what kind of applications can we build， including tiny vision。

 tiny audio and also tiny time series and also anomaly detection。

So it' starting with the simplest kind name image classification， So this is a demo from Google。

Showing the microcontroller can a simple classification between alls， bananas and apples。

Here's the probability， actually this is super easy， you don't even need a neural naturalral。

 you can just look at the colors colors。This thing might have been interferences？

But what gets more challenging is to expand this remarkable scale。You mentioned that by。

 real life applications。I'm soon that can actually achieve that more than 70% of accuracy。

 this is the level of mobile adss where used to require a mobile phone to do such。

But now we can fit into。A couple of dollar active controllerer first to achieve more than 70% imagine the accuracy of commercial microcontrollers compared with prior work。

2 had only achieved 53%。Another application is the oh， by the way。

 there are different constraints of much controllers， some of them might 256 kilo by。

Some of them has two megabyte flash， some of them have one mega flash。

 it's very hard to design different models for different weights。

 for different constraints right but thanks to the whitewa network。

 we can just create a single model and then we can specialize according to the constraints for the activation。

Contrain for the weight。Just trading when once， we are going to explore such automated search using emailmo homework in map3。

 which is released today， feel free to try it out。Another application is when you mean classification is wait or wait for。

So what is being wait for it， so they've had to finish person or not person。If it's just background。

 we don't have to trigger the second pipeline stage recognizing who it is。

 can just keep it idle and this might be a much larger problem seems system more complicated。

face to方 is。But the first stage can be value a very small model？if there' is a person。

 then the second stage， which is space recognition will be triggered。

 otherwise we don't trigger that。To preserve the battery to save the product。And here is a demo。

 we shop in building 38 in an elevator。ポト。So we have this microcontroller right here， a light。

 if it is red， truly there is person。If this screen is showing that there's no person recognizing them on the microcontroller。

We also have a belor from our TH high。あ。Dtribute the demo across everybody to take a look。

You just place it in front' a person to see the mice， if it's a person in front of it， it'll be red。

 otherwise it should be green。The microconor without a screen is the visual way for that。

We can also do timing object detection， right？Losing this perpech face inference。

The challenge is that to software detection， you really need a pretty high resolution and high resolution means we need a larger activation。

 larger activation means。A high as consumption。Which is challenging。

And resolution matters a lot for the accuracyctor。So here from March writers resolution。

 if you shrink the resolution， the accuracy is going to degrade。

 not very much for if that group or in the red yellow curve。Actually。

 you should print point the camera。To someone and see the vertical， please tell me in the direction。

好。But if you can see it for the attention to work。It's actually very sensitive。

 very sensitive to the if that resolution gets smaller， and actually it drops very sharply here。

So prop based inference is getting very helpful to maintain the accuracy。

So here's a animal fall detection， this is phase and mass detection， this is person detection。

And you can see。Here in person comes。the mask。Its rain。And this guy no mask， it's rather。

This project was not during COVID， so compel from the Ba。Whatever the project was that。

A lot of ask at that time。And what is the advantage of using such？Tuch， touch face to you。

So this is without using patch trace inference， this is with using patch based inference。

Youll see this boy was missing， the detectioner was missing。

 but using patch trace inference can detect。And here there's a mispredion on the hand。

 but there is no misprediction。Here the man had lost。On new box。Because the phase was pi of the face。

now we can detect it using aMV pool， here is a mis prediction， here is no mis prediction。

 so high resolution helps a lot per patch based patch based method allows for a larger input resolution which helps a lot with the accuracy。

We can even do on device training。To learn new tasks of the micrococtoror。So here's a panel。

 we have two buttons on this macro controller。So there the button and a green button。

 we push the green button for the orange。Of push the。那的发生或的不大呢。とえる。A couple of times。

Give me a few labels。And here is doing the back propagation localfully on the device。

Iluded with gradient。The activations， the weights， we have to fix everything in the microcontroller。

And after a while， it kind of against English。The不ら呢不 the爱。We are going to learn such techniques。

The Department of this lecture we me talk about training。So that' tiny vision task。

We can also find timing audiocast。So ToD is a very common adaptation young daily virus。

 like we can do audio keyboardword spoting。哦。系 Google a series etc ce。For speech recognition。

 for noise cancellation。And actually we can turn this audio problem into a visual problem because we can convert。

That interesting。Like here yes。Into the 2D feature map， it axis is the time dimension。

 the vertical dimension is the frequency dimension， and the strength indicates。

The power section on different frequency。On different frequencies so that we can do con on the 2D digitaltro。

 It's no longer one dimensional。 It actually becomes two dimensional。

So we can run those classificationification problems similar to a image recognition to understand the switch。

 whether yes， no on off， et cea。So can URLL perform。

The fully penulator are using conal layer since there's the local locality relationship between in time versus in frequency。

Adjaient time versus adjacent frequency during the signal has relationships。

 so we want to capture those local relationships by convol。here you can see the false。你在。呃，或是是。

I'm seeing him， the models is really better than。TheOators。

And Ioonet can also improve the efficiency on speech command data， we have a lot of speech command。

We want a load agency and high accuracy， so this is comparing mode and cool properties is mass versus MC mass。

 which is on the good front here。And finally， we have tiny， tiny series and anomaly detection。

 widely used in。Infacters。And also added to video surveillance。

 healthcare to prevent fraud to detect of novel products。So here we can see this is a normal capsule。

 this is a normal one， this is a normal knot， this is a normal knot。

And we want to use this machine vision to detect those different anomas。

And also analyze another long videos to see something that nobody happened。Recently。

 with the advance of large language model， the especially visual language model。

There are alternatives。So we try， we're going to cover this later in the lecture。

 but we want to give you a peek。So just put these two nutss。

From feedated to our visual language model called VA， it has 7 billion parameters。

 it can do a lot of stuff。Here we ask you， the first image is， is a normal nu。

What is it ok normalal for the second image？They can tell the second image is abnormal normal because it ensures so not with the whole unit。

So it can generalize quite a well as' that images。ラジ。

So the technique technology is evolving pretty fast just within two years。

 I made this slide for roughly two years ago and now a lot of changes in technique with the advancement of large language model。

 which will be our focus for the second half of this lecture。So before that level tomorrow。

 how was this done？To detect anomaly without the encoders。So also encoder is a very key technique。

So given an encode signal， it first passes through an encoder。

I project it into a low dimensional code vector。So you put it maybe a high dimension。

 like pi resolution image here it has a very low dimension。Which is the abstraction of。

And finally passes through a train a decoder， the legal decoder takes this low dimensional vector as input and try to reconstruct the output to be the same as the input。

So that's the。Structure also encoded to predict the input I the x slash should be the same as x。

And during the training， we tried to minimize the reconstruction error。This is the input。

 this is a reconstructed output， which was reconstructed using this low dimensional code vector。

And if the input is following the desired distribution， then。

The difference between the input and output would be pretty small。 Otherwise。

 if the input doesn't follow the training data distribution， like a abnormal data。

Appear in the input， the reconstruction， the reconstruction error will be high because in the trainingium data。

 it does not look like this， so it cannot reconstruct a abnormal input data。 Therefore。

 the reconstruction will be high。But if the equal image follow the normal distribution。Which？

Ha a lot of such images in the treatment data， the auto encoder will be able to reconstruct the output。

 so the reconstruct error will be low for normal data and will be high for normal data。

So we can use such auto encoder to deal with many different signals， including images and also sound。

And the audience。So here is a animal。To detect the anomaly detection for the fans。

The purchase the fat。And呃。Here we have a microcontroller attached。Which has2 to6 kilobytesgram。

 only one microbytes of flash。Over to 64， I got hurts。And we apply an o detection here。

And when we are picking the F using a screwdriver。You can see if the light it' going to change the powder。

呃。Youバ schoolまょ。对，第二。As we book。5 gradients of noise。I for a while。先ど？And to be shake。

The yellow lights will appear again。Since we have a general slope a severalmeter。一个反。政権。た業らた作れてしまう。

Okay， so this is the summary of today's lecture， we produced tiny andL concepts and the challenges of timing and amount。

And also how do we design the models that can defeat tiny devices and apply them to our daily lives。

 including vision tasks， audio tasks， and also time series tasks。And finally。

 let's see some of the demos in。Our AITA， which might introduced in the last chat that last lecture。

 and we'll see some of the demos。The website is actually an ITI study。And it's cater for our course。

We can have some questions， Mike。You you I'm clear of some concepts。好初。哦。我と。Isulation。

 which we learn。In the last lecture。We are using the rag technique。

To do the embedding of our lecture slides， lecture notes， and also lecture videos。AndRe it connate。

The question with over Trump。ピつ。啊，对 to the。那出那不08楼。And then it can give us a very detailed answer。

And what I like about it is you can actually click the link。Just watch the corresponding extra video。

You can also click the power want the link。To find a textbook which describe this particular concept。

What is interesting is actually it can。T yourself by creating quizz。 for example。Create。会子。About。

New network。ふ。出してる。我哋可。What is the primary goal of the networkpoing， increase the model size。

 reduce the model's computational complexity in high model accuracy， increase nano neurons？

Seems pretty simple。I see some complicated concept。啊。How to maybe you guys can ask the question。

Some questions you want to ask the PazA as right here。Somebody wna give it a shot。space。えきを？

If the activation is not going to patch size。How to。form。Hch this difference。呃。好的。

Is larger than somewhat。系分。The input is loud than the patch size， doesn't quite make sense。

You mean the object is larger than the exercise size。Oh。

 then maybe one objectback will be across two different patchs， that's a question man？ますよ。

How to perform patch based inference if the object is larger than the patch size？

If the input image into smaller manageable patches。

 each patch is processed separately through the model。

 this reduces memory consumption and allows inference on devices with limited resources such as microcontrorolls。

We talk about our receptive fuel distribution that's exactly what we discussed overnight handling。

 that' the general methods。Finally do neuror pressure search， I think this is very general。

 but it didn't give you salvia very specific question。Here this case。

I would have given better of becauses not specific。All right。

 so that's maybe one candidate for you to think about for final projects building something like this will be very global for the final project and feel free to ask AITA but we are always here to help you so consider。

Fal source of health。All right， that's all it is lecture。

