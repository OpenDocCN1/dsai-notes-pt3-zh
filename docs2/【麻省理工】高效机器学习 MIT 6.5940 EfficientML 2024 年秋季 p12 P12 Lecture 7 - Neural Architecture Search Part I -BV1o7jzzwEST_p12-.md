# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p12 P12 Lecture 7 - Neural Architecture Search Part I -BV1o7jzzwEST_p12-

Okay， good afternoon everyone， let's get started， so today we're going to jump into lecture seven about your architecture search。

 it's a new section， so as a review we talk about pruning， we talk about content。

And the pruning lab is built today， so let me show you want。

I submit the homework lab1 by today and also lab two results about quantization will implement a lot of cool techniques like K means quantization。

 linear quantization， derived the equations by itself to see the in quantization。4 big compensation。

 et ceter。 So both web one， that two， make sure you check out efficient and all about AI to see。

So we are going to start a new section about your architecture search。

So there is many tradeoffs between the efficiency metrics and also the accuracy。

So it's very hard to get the best of both world。In general， we want a low latency， high accuracy。

 low energy， and also low storage。But it's very hard to get both。From the latency perspective。

 you're able want a model write fast。For example， you can want to make a。Tact to image generation。

 You want to generate image within seconds or millisecond， tens of hundreds of milliseconds。

 You don't want to wait for like 10 minutes。To generate a single image。And also if a self at the car。

 you want to make timely action rather than climbing。Civing someone and finding some other objects。

So the real time matters a lot also for robots， right。

 robots interacting with other people and some other stuff， you want a real time interaction。

And also energy is crucial， sometimes you want to run these applications on mobile devices like running on the phone。

These edge devices are battery cons。哎，羽绒华服。The application to cool a battery and run out a battery within half a day。

 so energy matters a lot。Energy also matters for many in large scale data centers。

The cooling is a big issue。C2 emission is a big issue， environmental issue。

And the accessibility to those large power plant is not easy。

 we are talking about this megawatts power plant。Very high power consumption。Storage also matters。

 You don't want the model to be。7 gigyte。Which make it very hard to download on the phone。

 of the some of you want me want to make a startup in the future。

F some AI applications uploaded to Appleor or Google Play。

You don't want the user to download it and join the whole month quota of their 5G quota and the phone。

 So storage also matters。But none of this is as important as accuracy。

 even if you have very low limits， low energy， low storage， but if the accuracy is poor。

 it's very hard to attract users use this A application， so accuracy certainly is the foundation。

 That's why we put it at the bottom， it's the foundation。So when we are optimizing that latency。

 the energy and the storage， we want to make sure the accuracy doesn't hurt or sometimes even improve。

So that's a very complicated process。 So today we are going to talk about rather than compress。

 compressing an existing model by pruning quantization。Can we design a small。

 compact and efficient model to begin with。So that's the motivation for neural architecture search。

In order to achieve that， we'll go through the following sections。

 we first talk about these prim operations。And review those classic building blocks。

 if you're architect if you're constructing a new building。

 what are the building blocks now we are constructing a new network architecture。

 what is the building block？And then we will talk about neuro architectureural search。

 what is the search space？And how do we design the search space and also how to search what the search strategy is within that search space？

So let's start with primitive operations， which is old。First。

 let's recap the primitive operations like fullyconulator。The input feature C in dimension。

 n is the batch size， C dimension， which is the output feature， the way it is C in times C out。

 and there's also a bias。The number of maxs is just the in time C out。

We also learn about convolution layer， 1D convolution and also 2D convolution。

 the input feature size， the times W。If you have both heights and width， that's heights and width。

 that's the 2D scenario C in to C out and the weight is four dimensional， we have the kernels。

 height kernel width， channel in， channel out。And the way to calculate the match is multi in the six terms C in。

 C， out， H And W， K， H and K W。We also learned about group convolution error。

 so basically turn a fully connected layer divided into several groups。

 such that the number of weights can be divided by G and similarly。

 the group convolutions max is also reduced by G times compared with。The original convolution。

We also introduced a depthwise convolution layer， which is a special case for group convolution where the number of groups equal to the number of channels。

So each channel basically interact with only itself， only interact with itself。

 So the number of weight， there is no C out C in equal to C out。 So here it just K H KW times C。

And also the Mac， we have only these five terms， rather than see in hand， it's only scalp。

And finally， we have the by1 convol where KH and KW kernel size is just one。

 which basically projects the input dimension from C in to C out。

So those are the primitive operations。Using these primitive operations。

 we can construct on the building blocks， so there is a famous Re 50 bottleneck bottleneck block。

 which consists of three layers in by one by one layer。Followed by a three by three convol。

 followed by another one。and there is also a biopass layer connecting the input to the output。

 such that these three layers is basically learning the delta， learning the theji。

It has a very special design called bottleneck。Which is very good trade off between the expressiveness versus。

notation complexityplexing。So as we know，3 by3 comb lotion is pretty expensive， it's nine ops。

Compared with one by one， only one， so we want to first reduce the number of channels here by 4 x。

 we have this1 by one convolution projecting from 2K channels to only52。From 2K to 512。

 and then we do three by three co from 512 to 512。And finally。

 I will project it back to 2k using another one by one col。Plus the sample will design okay。

 so we'll feed the reduce the feature map， not the original feature map， which has 2K channels。

 but we want to feed the reduce the feature map， which has only 512 channels to the  three by3 convol。

Finally， we expanded the channel so that we can have good expressiveness。

By having 2K channel in the end。So how to calculate the total number of max？

So the first layer we have。2K2K input Oppo channel H by W1 by one。The middle。

 we have three by three conution， input output both part 12 by part 12， which by times time。百岁靠护事。

Last year， from 512 to 2 k，1 by one con reached that 50。あこのま。

How does that compare with if we have only a three by3 conclusion？And looking like this。

 if we only have historybacter convol， is9。And then we're projecting from 2K to 2K from 2K2K to2K。

That's actually  eight times 8。5。Times more compared with。Oural case。

To do this photoneck architecture。So the bodyneck architecture really shrinked the number of channels for the three by three convolution。

Such we can reduce the max。What about the number of parameters？Weve three column one by one column。

to pay by。2 and then three by three columns by 12 by about 12 and then one by one。

So this is a total number of maxs。And again， compared with just using a single3 by3 column from 2k to 2k。

 that will cause a 2k by 2k by  nine。Whi is 8。5 times higher compared with this bottleneck architecture。

 so the bottleneck architecture in Re5 is quite efficient with respect to both the number of Macs and also the number of parameters。

Pa an actual resac， there's res next， the next version of re。

Which introduced the group called motion， so originally we have。就是。2，56， dimension input，256。

 dimension and output。Well， one by one。Projecting from 256。

 reduce it to Y28 and using a three battery to project Y28 to  y28。

 here actually they are using a group。Group combinationmotion with group size of 32。

 and what does that mean？So we can have 32。 It's like we have 32 independent， smaller compositions。

 Each one is no longer。One to8， about one behave， but as I from 256， I project from 256 to4。

But then from 256 to 128， we have from 256 to 4， and we have 32 of them， so four times 32 that's 128。

And further change that since the last layer from 128 to 56 can be also viewed as from 4 to 256 and we have3 two of them。

是 four times3 two， you do2。Such that we can think about it as altogether we have 32 paths。

And these paths can work together。It's equivalent to a multi path block。

And potentially can convert it into a mixture of as。So that's group convol in Resn。

There is also very widely used architecture and mobilenet， which we introduced。

The depths wise separable block。So we use that to use the depth source con to capture the spatial information。

 and also use the WiY one convol to capture the information across the channels。

While we call it that separable， we are separating the modeling of the spatial information versus the channel information。

TheSp information is followed by that accomplish。only spatial information。

And then the pointwise foundation motion models the channel wise interactions so we separated them so that we can reduce the computation。

那我打啥？Look like actually mobile I V2 introduce this inverted bottleneck block， okay。

 inverted bottleneck block。Different from a bottom of block。

 actually the network channels either decrease by increase by six times， expanded by six times。

What is the reason behind that？So here we have depthwise convolusution。

 and remember depthwise convolusution， the flops is very low， it has one less dimension。

Fly five terms multiplied together。So the expressiveness is very weak。

So compensate it for that we want to introduce。More channels。

 so here we are expanding the number of channels by one by one using one by1 Kong。

 expanding the number of channels by six。In the bottleneck layer。

 we are reducing it by four because three by three normal col is very expensive。

But here we are expanding it because the depth wise convol is very cheap。

And we want to have good expressiveness and model capacity。

 So here we are expanding the number of channels rather than shrinking the number of channels。

So how it will we calculated the Mac in this case？1 by one column stays the same。

 one by one column high and width。啊，你 put China破 China，你不 China，不 China。And for the middle part。

 that's where it gets interesting， so we expansion number channels from 160 to 960 maybe from 160 to 960。

はいスかしま。Since this is a depth wise comb there， there is no other 9，60。

 It's just 960 rather than 960 times 960 In channel times output channel。 is depth wise。

 So it's just a single 960。So this is a total model。What about the total number of parameters？Again。

 using equal 16 as an example， I usually want to use real numbers rather than。

Just the letters so that you can get some informationmission。

So this is the one by one column input channel output channel，1 by one co input channel。

 output channel， and this is the depth wise layer nine times we have 960 channels。

 So the number parameter is very short， very small actually。Just nine times 96。

So that's why mobilenet gets applied to mobile devices a lot， it has very low maxs and low private。

And the key reason for that is thanks to this inverted modern night layer and thanks convolution。

Where it has one less dimension。Nmal corporation。But it's not perfect， what is under the rug here。

So the excavation memory is actually not efficient。For this kind of inverted automaticic structure。

The activation matter。Why is that the case？不开心。You are expanding the number of channels。

By six times to compensate for the batch source convol， low computation complexity。

There are expanded number channels by six times。 So the future map originally is big now is。

Six times bigger， so it's actually not activation memorym for。If we look at the inference。

This is from R at 18 to low IV2， shrink by 75%， they are of the similar accuracy of using that。

The number parameters reduced by four or five times from resNe to mobileNe。However。

The peak activation didn't decrease， but even increase the 80%。So that condition is a bit larger。

But you can see the peak activation is not the bottlene for you。It for inference edge size of1。

 activation is smaller than the weight。However， during the training side where you have a pretty large match size。

 the activation matters a lot。So here are the parameter reduced。But by four times。

 but activation only improved by 10% so red Mo app is very good for inference inference time model size reduction。

 the flow reduction， but is not good at reducing the activation memory。

 which is a bottleneck for training。So as training time， you wouldn't observe much。Memory reduction。

 if you change from Re 50 to Mo me2， with very large batch size。All right， next design。

 next building block， shuffle mat。So here we are familiar with these already。

1 by one comes through by three1 by one。This is group wise convolution， now we have three groups。

What is the problem here？😔，Different group only interact with itself。And it's a rest room。

Breen and blue group。 they are independent。And now we want to encourage different groups to talk to each other。

 therefore we want to shuffle the channels across different groups。The channel cha， the red group。

The component from both the red and also the blue and aspect green。

So this is the shuffle information to encourage the information to flow between different channels。

All right， there's also the transformer building block， which is getting super popular these days。

 like invasion transformers。Basically， all the operations are vision or transformer books。

So for transformer block， there is the multi had self attention MH I say。And what is that？

So we have a tensor we first projected into query key and value with three different。

We the projection matrices。After converting that， we pass it through the attention mechanism we're going to talk about in the transformer lecture in detail。

 which is basically as the scaled dot product between the QKB。

 we first calculate QK transposedse and normalize that by the square root of the hidden dimension。

 we pass it through the softns。We do a mask。Like a causal mass， finally。

 we multily that within the beam。So that every token can attend to every token in this case。

 if it is causal the future token or the current token can attend to all the previous tokens。

So rather than convolution， which has a very limited receptive field in one layer。

 you would need a lot of layers， many layers to have a global excess global receptive field or a pretty large receptive field。

Different from that。This body height attention， this attention mechanism。

 just using one layer you can attend to all the previous tokens。

 in the middle they give you a pretty large receptive field。

 which is good for both fu and also language tasks。So after the MHSA。

 we can coordinatenate the output from given head， so each head。

 they are independently operating in the attention mechanism the QK transpose solve the X times to。

They are doing the attention mechanism independently。

 and finally we can candidate them together and then project it again using the output projection matrix。

So here， although we have three input projection matrices like WQ KE。

They can be concateinated into a single three times larger matrix。

Do one single kernel call for the matrix modification。

 Since we want to avoid the number of kernel calls to reduce the time spend on the GPU kernel calls。

So if you see the right hand side basically depicts what is the process of the attention mechanism。

 we have three pans QK transpose， and also Q K transpose and also the B。Q， this is n dimension。

 we have n number of tokens。This token is of dimension D K transpose that becomes D times n。

We do the matrix multiplication。We learn what is the number of maxs in the matrix modification？

And地他系。And the back is n squared D。N squared D， since output is n by n in order to compute each element。

 we need D max。 So altogether is n squared d。We do the softmax， and then we do another。

Mattrix modification with a B。So dimension would be n times n。 So that's the result of N D I T N。

 The result is n by n。And then we modify n by n by N times T。The computation is n square n squared B。

 So altogether we have two n squared d。 So it' O n square。

 A grow projectally with the number of tokens。So as the resolution gets bigger。

 the number of token gets longer， as the context gets larger。

 the document gets larger and tokens gets larger， this is actually quite computationally。Expensive。

So that's the attention part。And what does the pension map look like？So here is a sentence。

就是 re example。We're having the pizza neighborhood called a staff。

The sentence is at that the video game is a lot more fun than I feel。

And you can see the game word game attend habit to video， and I attend to fun and a lot。

And more apparently highway is here。To bad more than。Talk together。Film here can have a。To给。哎。

So that's the tension map capturing the relationship between different tokens。

And naturally you can see some of the tokens they don't attend to anything。

Pretty much everything is white， so meaning is' not attending to any stuff。

 so in the future lecture we are going to talk about token pruning。

 tokens like that can be safely approved。Question。Why is it a symmetric。

 Why is it not symmetric in a diagonal， it doesn't have to be symmetric。

 the future tend to the past versus the past tend to the future not necessarily symmetric。

And here when we are talking about multi head attention。

 basically we are concateivating the attention result across different head and pass it through the output transformation matrix WO。

Okay， so that concludes our beauty box section we talk about。I see there。Doorl convolution。

 world convol， depth convolution。We use those convols to build building blocks such as invertedneck bottleneck。

And also， the Mo Moide attention blocks。So we have a lot of building blocks now。

 now we talk about how do we select among the other building blocks。

So we introduce neuro architectureitecture Search。So commercially， when we are designing the model。

 we usually design a model。So many layers。Many some kernel we choose across different kernel size。

 three by three， one by one，5 by5，7 by seven。I'm going to pick a resolution， maybe 224， maybe 256。

 384。And we learned those connectivity， bypass layer， no bypass layer。

And we want to choose the number of channels， started by three。And then we added more channels。

Graduate had more tunnels。Reduccing the resolution， and in the channel。

 there is a model of black magic doing the manual architecture search。

 and usually it's very hard to get a model exactly feeding the demand of the hardware。For example。

Google's CPUU has 28， first generation of CPUU has 28 mebytes。Of ice cream on cheap ice cream。

 so that fits perfect would go that do one because。法庭。Microbi exactly click and fit the model。

 everything can be fit on the cache。How do we design the model of that exactly 28 megabyte or 100 megabyte or certain of certain size？

If it fits then can fit in the cash it'll be very fast， if it doesn't， it'll be very slow。

Which motivates us to build automated design， space， exploration and method。

So that we can use machine learning to design this neural architects。

Rather than a manual design though。So this is comparing the manual design versus。Automated design。

The search the design space in this number of Mac this X axiss。

 we want to low low max so that we can make it faster， but we want a higher accuracy。

 so ideally we want us a model that is right here on the top left color both。

Low computation and high accuracy。We hope the circle size to be small。

 the circle size indicates the number prime。Like this week means and there's two million predators。

4 meeting is a 8 meeting， here's 64 million。Primeterters。So all these models are handcrafted designs。

 like less than 50 is roughly four million bags。76 called on accuracy。exception model re01。

 re x 11 roughly 80% of an accuracy， 80 billion max， so there's no free lunch。

 every increment for the accuracy income at the cost of the floats。What about our automated design。

 Okay， Mike this once small approach designed by our。You have only half of billion Mac。

 half of billion in Mac for match accuracy， even higher accuracy compared with res next and also exception。

Whi is showing you that its a very powerful tool to use neural architect research to design a。

Very small model， low computation， but can match the accuracy with。The啊。Very big human design models。

And this is a bit。A whole family of models designed by AlML。 So here you see the。

Circle in the middle， I create distinguisht the run with how profit versus this asterisk。

 this is out not these are。These are department design models。

When you can easily tell the difference between these tools， we have a bunch of。

Bs on the top left corner， which showing that。Given its huge design space。

 manual design is sometimes。Theeria comparative with such automated design approach。

With that is motivation， let's see whatever components of a neuroarchural search。

And what is the goal of the neuro research， Okay， so given the design space。

 these are the building blocks。でスでてる。Search space， building blocks with a lot building blocks。

And then we have a search strategy and also a performance exhibition strategy。

We want to propose the architecture。And then collect the performance feedback and then iterate this process。

 If you find a good model， you can stop this iteration。 Otherwise。

 you want to continue this iteration， propose a new architecture， estimated performance。

 estimate efficiency。Such as vancy， energy， storage， different perspectives。

 and also accuracy for sure， give the feedback and repeat the search process again until you find a model and feature name。

And to begin with， let's talk about the search space。Okay， so that's。

A set of candidate neural architectures where going to choose from。I think we'll introduce。

Two search spaces here， one is the cell level， the other is the network level。

 okay so let's first look at the cell level， what does that mean。So， this is from the。

Emage all the way to the output when they have magnet layers。Initially， we have a large resolution。

 like 22224。And finally， we have a very low resolution given a single prediction。

 so we have to go through many down sample polar layers to reduce the resolution and increase the number of channels。

So those are the reduced reduction cell， reducing in the number of。表着路审。

Can be done by Str the con or。系铺力。And between those reduction cells。We have those normal cells。

And those normal cells are usually repeated。So the philosophy from this cell level search space is that you just want to search one building block。

 okay and then you're not going to repeat that building block many， many times。

I here repeat it1 times。Another N times， another of the N times。And here for the reduction cell。

 we are reusing the same reduction cell across different stages。So basically。

 all the building blocks boiled down to two building blocks。 One is the normal cell。

An normal cell between the reduction cells。So that makes a very complicated problem much simpler。

 so previously we have like 50 meters。Now we only need to search two layers and we are repeating these two layers for the whole network。

With two layers。For into two categories， one is the reduction cell， one is normal cell。

 normal cell just repeat between this reduction cells and the reduction cells the responsibility is to reduce the resolution。

 for example， initially is 224。In the end， it becomes seven by7， so you reduced from 224 by 224。

To 12，128。我221 two。2，24 by 224， to 1，12 by 1，12 to 56 by 56 to 28 by 28，14 by 14。 and finally，7 by 7。

 Okay，5 reduction cells。In the middle， that's the normal。Let see the result first。

 and then well we look down deeper how I work。From this paper， neuroonpat source paper。

The cell architecture is quite unreadable。 Okay， so that's the models searched architectureect searched by machine learning。

 and we can see roughly， there are。a layer H， this is H minus I minus1。

 so we can take the input either from the previous layer or from the layer before the previous。

can do some operation。Separable three by three， density。And then do some operation I add to。

Add these two or price。And then cancate all the twice together and feed it with the output。

And similarly for the reduction cell， basically choose the input either from H or H minus1。

 pass it through two operations item together， and then concate them in the end。

So how is the architecture to select his choices？So here this paper used a recurrent neural network as a controller to generate the candidate cell。

We don't quite R and these states， but let's give a review but first， select the one hidden states。

And then select back another in States。And they aggressivelyly select the operation for the first hidden。

And then they the operation for the second heat。But now we want to combine these hidden states。

You want to select the method to combine these students today。And well repeat this be times。

So here we first。C life。The gray part， select one hidden state layer A。

 and then select another hidden state， select layer B。

 and then select the operation top of the first hidden state here is select3 by three column and then select the second hidden state operation。

 which is2 by2 next pool。And then we select the method to combine them。

 and here it's using add operation to combine them。Okay， so we are repeating this process。啊病开。

The question here， what is the design space， what is the size of the design space。

 say we have two calendar inputs exactly like this case。

And then we have M can operations to transform the inputs。To transform the endpoint。

The yellowlow part， we have M candidates。And then we need to combine them。TheGen牌。

And there are N potential operations to combine them。 Add is one of them。

 but there are N potential methods。What is the size of the search space that we have V layers？

Give you one minute to think about it。H to consider step by step。Which is a。

They're commonly used prompt。Think step by step。So what is the step one？Okay step one。How。Is to。

Se Iki market state。So we can either select from theri here。

We can either select from the previous state or the state before the previous。No choices。

For selecting one he states。And then we have another two choices for selecting security。

And then we select the operation on the first unit States。

 there are operations and candidate operations to perform the input。

The second one also on possibilities。And after that。

 we have earned approaches to combine those two key states。So that's just one layer year。

And we want to repeat this for fear errors。OkaySo。To the power of B。

 So that's the complexity of selecting the total design space。Assuming I'm equal to five。

 that's actually very typical we can have one by one column， three by three column。

5 by five column identity or pull in easily if can get five choices。I mean for the five。

N equal to two， we can do Iized addition。Or we can do itemized modificationplication。

So we can easily have two or more than two operations for。They're Bs。Given this example。

 we can have 10 to the power of United。C is in the design space has a pretty huge design space。

Which motivates us。And the later part of this lecture we are going to learn。How to select。

 how to search within such a big search space。Okay， so that is the cell level search space。

 the philosophy is we took a lot of effort， very big design space， super big design space。

We just want to pick a single cell。Very elegant。 We want to repeat itself so many。So many times。

But another thinking is that that may not be optimal because from deeper layer versus shallow layer。

 you may want a different cells， okay from a deeper layer versus shallow layer。

 behavior is very different。It may not be the best solution to just repeat the same building block。

 same cell across the whole effects。Often it' answer。Okay， so。

It might be better to think about the whole design space， the whole network as a whole。

 it a larger design space， different blocks may have different architects。

So what is the design space in this case？So starting from the input with an output。

 we can have a reliable number of layersPrevious when we are repeating， we assume certain depths。

 but now we can also change the depth。For example， the first。First stage， so here we have。

StEach stage there of the same resolution， we reduced from 224 on the way to 7。The first stage。

 we can have depth of one types of two network three and similarly for later stage aistic。

 we can have three5， silent nine different。That we can say choose from。Also。

 we can have the resolution dimension。 Okay， the input resolution doesn't have to be 224 by 224。

Rather， it can be 128 by 128。Or 1256 by 1256。Or at training time。

 you can dynamically randomly select different resolutions， which usually helps。

 like in the previous quantization lecture， we learned about。

 usually adding randomness helps with generalization and helps with training。

 So here we can also train with sometimes with one92 by1 92 sometimes train it with 256 or 256。

So that's the resolution we measure。We also have this width dimension， okay。

 so you can choose from 48 channels in the first。The first place and 64 or 96。We are going deeper。

 we want to have a resolution， a larger dimension right here， so we can have 120120。1280 or。20848。

 etc cetera。Okay， so we can choose different width。Also we can choose from different curve sizes。

 so different color here mean different。Different size， for example here， three by three column。

7 by seven column， five by five column， we can have different kernel size。It's all very flexible。

We can also have the topology， the connection。For example， when we are doing the pound sample。From。

One time to two times， four times， eight times all the way to 32， 32 times。

 you can go through different paths。We can stay at the eight times down sample and then stay for a while。

 and then we jump to 16 times down sample until the end。For some super resolution tasks。

 or sorry for some classification tasks， this is the way to go and reducing the resolution。

And sometimes for segmentation tasks， we want to have pixel wise prediction。

 So the output resolution and input resolution are pretty much the same。 So we want to first。

Down sample up sample。 So this also applies to auto encoders。

 which nowadays is very very widely used。In diffusion models。

LDM lengthnt diffusion models we are going to learn later in this lecture series。

Can your first thumb sample and then your have sample。就要睇下属单身放鸭身好单身放鸭心。So。

The trajectory across the grid India is representing actually the architecture of the model， Okay。

 When do you down samplele， for example， here， when we are we are doing the down sample the layer or we are not。

 and then we are doing down sample and next layer we don't versus we just down sample down sample。

Of some some samples， so the different。Pas， different trajectories within this grid， I。

Correspond to a network architecture in the search space。

So that's natural level topology connection on the search space。Okay， so now let's take a break。

Before we jump into how to design the search space。All right。

 welcome back and let's continue discussion， let's now talk about design and design search space。

 so just now we talk about there's a huge design space。

Either using the cell level or the network plan。But how do we narrow down these aspects？For example。

 when we are searching something， we don't want to search。But in a forest， the forest is pretty big。

 your friend can lost。AndThe first you want to do is to narrow down which part of the forest it got lost just like here we are given a pretty big search space for our target design。

If you want to first may with that， okay， I'll try get lost enough。That the part of the forest。

 and we want to further， optimize the search space。

And then we do the model and search the specialization within the smaller。

 the optimized search space。So we'll introduce Ta Na。

How do we do automated the search space optimization to search the search space。

 and then we do the resource contrained model architecture search and specialized the model for a particular hovering contrain。

So talking about how work constraints dreams。On the mobile devices， the latency matters。

 you want it to react very fast， the energy matters。

 you don't want it to train in the battery of your phone very quickly， but on these IOT devices。

 memory consume is also pretty。And also recently for large language models。

 memory and GPU is also very scarce resource， sometimes you have only 80 gigabyte of memory。

 you want to really well utilize the memory。So in maancy， energy and memory。

 those are the big constraints。You press it from cloud AI to mobile AI to tiny AI。

When we are looking at a memory size， were help you。T is a figure by。

Few petetalytes versus a couple of hundred kilotoytes for tiny AI。

Which has a pretty big gap between the available resource of the memory and if you feel0 kilobytes versus several megabytes。

For even not to mention large language矛盾 which just so big。And if you compare the memory。

The GPU or mobile phone to macroconts are almost invisible for the macro controller since the memory is so small。

Here we have three orders of magnitude， smaller memory。

And the four there is opening to smaller storage。So as a computer scientist。

 you want to design across the whole space， both big and also small， but it's pretty challenging。

So we want to first narrow down a design space。So how do we find a good design space first of all。

 here we listed a bunch of design spaces we have different width。的位置的。

Channel and also different resolutions， 160，112，69， 96。So given these different design spaces。

 which is good and which is bad？Ideally， we want to evaluate the accuracy by training the model to the end to observe the accuracy。

 but that is very computationally costly。So how do we evaluate a model without training that？

So here we use a very simple but effective heuristic。

It you see a good design space is more likely to achieve higher fluxs under the same memory consstrictt。

You only have this amount of memory and it gave me the most amount of flops。

Assuming the model capacity is proportional， is proportional to the fs。

So if given the model same memory constraints， you can fit more flops that is considered a good design space。

And also for hardware from hardware perspective， computation is cheap， being a movement。

Access is expensive。So if they given the same model of memory drinks， you can fit more flops。

 and that model of architecture is considered more efficient。Therefore。

 we ploted the relationship between the flocks。And also this is a cumulative probability of different design space。

はいです。R horizontal width of 0。5 resolutions。The full is black he face。A correspond one to width of 0。

3 resolution of 160。 So its higher resolution， but。Lower。Smaller width。

You don't know which is better， right， lower resolution， higher width or higher resolution。

 lower weight it's hard to tell。But now this chart can easily tell the difference。

 so in this red design space。80% of the models has more than 15。3 million max。

But in this blind design space， 80% of the model has only 32 mini maxs。

 so the red design spaces can fit more flops given the same memory project。

 so we consider that as a good design space。And we verify that。

 train a bunch of models within that design space and observe that the best accuracy in this design space is about 78。

7%。Versus in inspect design space， only 74%。Which better however。Idea that。

A design space that can give you more flos， given the same American joint will be a better design space。

Okay， so。We just want to analyze the flow distribution。Modular fls means module model capacity。

It's more likely to give a higher accuracy。So we use this principle to design this design space。Okay。

 so I mean's actually quite effective。Compared with the rest 18 and224 resolution。啊。

Which is actually running out of memory。On the。Micro controllerts design space。

Our space is superior and Paris。Even rather huge design space for random。

And also the search space was higher beam fls on the X axis phase。In accuracy。

 yeah very positive and cultivateated。So you're going to have higher fls。

Then most likely you'll have high anchor。The correlation is similar and it's pretty linear。

So we use this approach to narrow down a design space using the heuristic that you want to have more fls given the same memory budget。

And now let's talk about now we finalize the design space。

 how do we do search on how of that design space？And how do we automate this process without human intervention？

Which is quite helpful if you want to build a product， build a tool。

You don't want to specialize it by using a human extract。That's notsable。

You want to have push the button solution no matter。其ar都 came。you are given a new memory constraint。

 given a new latency constraint you want to exactly fit this amount of design target。

 accuracy target， getting target， how do you have a push button solution to find the neural network architecture？

So we're going talk about several search strategies on top of the search space。

 including grade search， random search， reinforcement learning。

Growing in disscent and also evolutionary research。So let's start with grid research。

 which is the simplest and sometimes work very well。

So research very traditional way of private optimization can have many。

Deegrees of optimization in this scenario， we use tool for illustration purpose。

One is the resolution， y x or1。2 x or 1。 yx。The width either 1。1，1。1，1。2。

 So we are trading out between resolution and width。

We call it grid research because on each dimension we can have a step size。

And then we can have a grid by dividing the whole space into several smaller ones。嗯。

Each do on the grid is one design in the search space。

So the entire search space is represented as the Carassian product of a single dimension design space。

This is basically an awkward product between the resolution and the width。

And to obtain accuracy on each candidate network， we want to train them from scratch。

We don't have to train them all the into emergence。

 but we can train in for a while to observe the accuracy。So that's the bad part of it。

 You have to train for each design。 You have a lot of， if you have a lot of GPUs。

That's probably a very easy way， just two for rules， four resolution。

 for wave training and pick the best one for me。Of course。

 you want to satisfy that it is in con some of them。By large with pretty big resolution。

 you may not fit， you may not satisfy the it in， so we are going to eliminate them even before we train。

So I the points， the design。freakak that it is in con before and2 of them。

So its very easy to implement。But it may take quite a long time to evaluate them one by one。

Make sure you're pruning away those obvious deadline lines like the red lines in this scenario。

And now we want to introduce compound skating。 You have so many dimensions to search from。

Do you push one to the extreme or do you。Tune is now the moderate way for each other。

So given the baseline。This is based architecture from input to output。We can of scale the width。

 make the width much wider， probably the first one。We can also steal the depth， make it much deeper。

We can also steal the resolution。Higher resolution， low resolution。

And the best way is actually do not corner each design knob to the extreme。

 like only scale the width， only in skilled depths。 But we want to do compound。He。

 that's the lesson think here。You want to make it a little deeper。Not absolutely to the extreme。

 a little higher resolution， a little wider。 so here the target is to。

Make the model to access the original network so you don't want to。Make only one dimension to x。

For each dimension， width depth resolution， multiply them together。

 you want to have flags from each of them。可以。So that's the principle。And similarly。

 if you want to compress a network， you don to you don't want to just do quantization on this direction。

 you want to put them together， just do a little bit of each。

 and combine them together that really works pretty well。So that's great search。

Random search seems very trivial right you can compare it with a grid search1 by one just for x for y and then evaluate each of them。

 now you can randomly evaluate them in the design space。

But this is actually quite untri and quite helpful for sanity check。从30回来。Even in the homework。

 make sure you want you run random search for a little while。

 you want to see that the reward gets constant， no improvement at all。

 but must be something wrong in your design space or the search or the evaluation or the reward function。

You already want to do some first order approximation and do a quick s check by running random search。

After a few iterations。You probably want to observe some improvement of vancy accuracy in your tradeoff。

It's a random search you later first had to do。Reinforcement learning， that's a very advanced way。

 some tricky tricky way and not quite easy to。To use in practice， but I want to put it here。

So we design a sequential decision making problem， so you want to decide what is the number of filters。

 what is the future height filter what。Stripe， height and width， number filters and high。

It was then design them step by step one by one using a RN nowadays， R is no longer popular。

 probably using an autoregressive model， some kind of autoregressive model。

 not necessarily RN controller。And using that controller to propose the architecture consisting of the。

TheH the width， future size， et cetera。Propose this architecture with probability P and then train a child network with this architecture to get accuracy latency to get a reward。

 and then you compute the gradient of P， which is a probability here and simulate it by R to update the controller。

You can have an updated controller and next situation is going encourage high reward and discourage bad reward and repeat that process as through reward at higher and higher。

We can also use brilliant des。To make this search process differentiable。

So for a path from this node to this node， we can have many different choices。

 many different configurations。You3 by three column， five by5 column， or that'sized column。Okay。

 so how do we choose from them？We can treat the output as a weighted sum of different edges。Red。

 yellow， urban colors， we are learning the probability of choosing different choices。For example。

 here we are choosing this blue part， maybe it could give like one by one column。

But actually during training time we run inferences for all of them。

 you can imagine the memory requirement would be much larger because we have to run the activation for both those 335 by file。

And we are learning the probability for these three。 Okay， and with an inference time。

 we sample one with the highest probability。 So at train in time。

 you can imagine this fix a lot of GPU memory。And in time。

 we just pick the one with their probability， sample according to the probability and choose the path。

And this is about。Making it differentiable， how about latency。

 can we also make latency differentiable if the case that'll be interesting？So here we have。

Four different choices for this layer。啊，所以把 three count by by five count and根进的处理。

From an accuracy perspective， probably two by three and  five by5。

 maybe five by five has higher expressiveness。Ha higher capacity， but from the latency perspective。

 they are slow， the identity would be the fastest。So how do we take that into account when we are doing the stochastic readinging descent？

Previously， we just care about the cross entropy loss， which doesn't。F into the vi。

I think to be maybe a lot better than five by five with respect to the agency。

So how do we make latency differential？走 here我边。The probability of choosing each path。好对噶。Please再说。

And then we pre measure the latency for each beauty block。

 like we pre measure the latency for the three by three convol。

 measure latency sequence the same across different inputs。Measuring the letency equal5 by5。

 the leency of identity， the letency for reporting。And then the expected latency will be summing up。

 The probability times each latency， probability times latency probability times each latency。

 So that's the expected latency。 Okay， given the probability distribution here。

And we can update this。Prob distribution by adding this expected agency to the loss function。

Maybe so this is the cross fee laws。This is the regularization for the weights。

 this is the latency portion of the loss function， in this way we are learning the probability so that we can make latency differential and we plug in with latency as part of the most term so that when we are doing the gradient descent。

 we can also take care of the latency。Such that we can learn a model that both give a high accuracy and also give a low distance。

Any questions for this part。About how to make Clintonvan。えく。The next way to go。

the search strategy is for evolutionary research。In a quick review we couple all starting with random search。

Right， and then we talk about using RL， read the search， now， let's talk about evolutionary。

But mimic make the revolution process in biology， we have a population which is our red designed space。

And then we have a previous function， which basically is the accuracy， the agencyency， et cetera。

And then we move not and cross over。佢他不好。And then select the survivor。

 assuming they are the best species。And then we repeat this process to do mutation crossover。

Surviv selection causes on and so on。And never terminate。So let's see how that works。

Fitness selection， we are given a once smaller network we're going to talk about the next lecture and also in the home。

Given on a submetro， we want to measure low latency and accuracy。

 we want to have low accuracy or low latency and high accuracy。Otherwise， it doesn't fit。

It's too slow or at is too low， then we need to re。

And after that we'll give the feedback we sample again and repeat this process。

 so the fitness function is basically selecting between the latency， the accuracy。

 the efficiency such as latency， throughput， library consumption， energy， etca。

So that's the fitness function。And what is mutation so we started with。

This natural architecture were two stages， perhaps of three in the first stage。

That's of three in the second stage。And then we mutate gaps such that the first stage can become two。

 thats of two， second stage can become thats of four or three or five， and change it。

We can change maps， we can also change the operator， for example。

 you will take from a3 by three convol to a 5 by5 convolution。

From a 3 by3 convol to a 7 by7 convolution。So as mutation。We can also do crossover。

 so crossover take two inputs， mutation take one input。Okay， so also make cool good。

This is input one， this is input two， two architectures we want on cross over。

So these two are the same， so compared one there's no problem。From the second layer。

 we can choose from even pair while， parent2， actually， the pro is chosen from pair2。

It seems for the last layer is also chosen from parent2。

So randomly choose one operator among the two choices。We have two parents for each。

 so that's the crossover。 we are going to implement that in the third lab。

 so make sure you are clear about this。Mutation takes one input， crossover， takes two inputs。

 two parents。After that， we conclude this lecture about。The。

 we first introduced the primitive operations and used that primitive operation to construct the building blocks。

And then we talk about the search space， very large search space cell level versus the network level。

 and how do we design the search space such that we can have。

High flos given the same memory contraint。And finally。

 how do we search on top of the search space using random search， where to search。

 reinforce learning and eye evolutionary research？All right， so map two is out。

 feel free to check it out and let us know if you have any questions。in the office hours。Yeah。

 some reference。 Thank you。 That's all for the lecture。

