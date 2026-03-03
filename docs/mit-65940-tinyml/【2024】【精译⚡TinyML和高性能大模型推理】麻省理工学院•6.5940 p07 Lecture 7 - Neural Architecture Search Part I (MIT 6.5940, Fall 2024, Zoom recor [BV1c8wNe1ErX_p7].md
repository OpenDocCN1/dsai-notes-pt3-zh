# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p07 Lecture 7 - Neural Architecture Search Part I (MIT 6.5940, Fall 2024, Zoom recor [BV1c8wNe1ErX_p7]

Okay， good afternoon everyone， let's get started， so today we' are going to jump into lecture 7 about new architecture search。

 it's a new section， so as a review we talk about pruning， we talk about quantization。

And the pruning lab is due today so make sure you want submit the homework lab1 by today and also lab two is out about quantization will implement a lot of cool techniques that came in quantization。

 linear quantization derived all the equations by yourself to see the intake quantization and for quantization etca。

 so both lab1， lab two make sure you check out efficient and out of AI to see the labs。

So we are going to start a new section about new architecture search。

So there is many tradeoffs between the efficiency metrics and also the accuracy metrics。

 so it's very hard to get the best of both world。In general， we want a low latency， high accuracy。

 low energy， and also low storage， but it's very hard to get both。From the latency perspective。

 you would want a model to run fast。For example， if you want to make a。Tack to image generation。

 you want to generate image within seconds or meisecon tens of hundreds of milliseconds。

 You don't want to wait for like 10 minutes to generate a single image。

And also in a self driving car， you want to make time action rather than fighting someone and finding some objects。

So the real time matters a lot also for robots， right robots interacting with other people and some other stuff。

 you want a real time interaction。And also energy is crucial right sometimes we want to run these applications on mobile devices like running on the phone。

These edge devices are battery constrain。Right， do you don't want to。

The application to drilling your battery and drain out a battery within half a day so energy matters a lot energy also matters for training in large scale data centers the cooling is a big issue。

 CO2 emission is a big issue environmental issue。And the accessibility to those large power plants is not easy we are talking about this megawatts power plant。

 which is very high power consumption。Storage also matters right you don't want the model to be like 70 gigabyte which make it very hard to download on the phone。

 some of them some of you may want to make a startup in the future build some A applications upload it to Apple store or Google Play。

You don't want the user to download it and join the whole month' photo of their 5G photo on the phone。

 so storage also matters。But none of these is always important as accuracy。

 even if you have very low latency， low energy， low storage。

 but if the accuracy is poor it's very hard to attract users use this application。

 so accuracy certainly is the foundation that's why we put it on the bottom is the foundation。

RightSo when we are optimizing the latency， the energy， the storage。

 we want to make sure the accuracy doesn't hurt or sometimes even improve。

So that's a very complicated process， so today we are going to talk about rather than compress compressing an existing model by pruning quantization。

Can we design a small， compact and efficient model to begin with。

So that's the motivation for neural architecture search。In order to achieve that。

 we'll go through the following sections， we first talk about these primitive operations。

And review those classic building blocks if you're architect right if you' are constructing a new building。

 what are the building blocks now we are constructing a neural network architecture。

 what is the building block？And then we'll talk about neuro architectureect search。

 what is the search space？And how do we design the search space and also how to search what the search strategy is within that search space？

So let's start with primitive operations， which is old abuse。First。

 let's recap the primitive operations like fully connected layer， the input feature C in dimension。

 n is the batch size， C out dimension， which is the output feature， the way it is C in time C out。

 and there's also a bias。

![](img/8229e2bc18aa5938afa68d69b84b507c_1.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_2.png)

The number of maxs is just C in time C out。We also learn about convolution layer。

1D convolution and also 2D convolution。

![](img/8229e2bc18aa5938afa68d69b84b507c_4.png)

I the input feature size C in times W。And if you have both height and weight that a height and width。

 that the 2D scenario see in to see out and the weight is four dimensional。

 we have the kernels height kernel width channel in， channel out。



![](img/8229e2bc18aa5938afa68d69b84b507c_6.png)

And the way to calculate the Mac is multiplying these six terms C and， C out， H andW， KH and KW。

We also learned about group convolution layer， so basically turn a fully connected layer divided into several groups。

 such that the number of weights can be divided by G and similarly the group convolution Mac is also reduced by G times compared with the original convolution。



![](img/8229e2bc18aa5938afa68d69b84b507c_8.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_9.png)

We also introduced the Dewise convolution layer， which is a special case or group convolution where the number of groups equal to the number of channels。

 so each channel basically interact with only itself only I interact with itself so that the number of weight。

 theres no C out C equal to C so here just kH KW I C。



![](img/8229e2bc18aa5938afa68d69b84b507c_11.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_12.png)

And also the Mac， we have only its five terms， rather than C in time C， it's only scale。



![](img/8229e2bc18aa5938afa68d69b84b507c_14.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_15.png)

And finally， we have the one by one convolution where KH and Kw the kernel size is just one。

 which basically projects the input dimension from C in to C out。

So those are the primitive operations。Using these primitive operations we can construct on the building blocks Okay so there is a famous resideside 50 bottleneck bottleneck block。

 which consists of three layers in one by one one by one layer。

folllowed by a three by three convolution， followed by another one by one layer okay and there is also a bypass layer connecting the input to the output such that these three layers is basically learning the delta。

 learning the re。

![](img/8229e2bc18aa5938afa68d69b84b507c_17.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_18.png)

It has a very special design called bottleneck。Which is very good trade off between the expressiveness versus the computation and complexity complexity。



![](img/8229e2bc18aa5938afa68d69b84b507c_20.png)

So as we know the3 by3 convolution is pretty expensive， is nine ops compared with1 by1 only one。

 so we want to first reduce the number of channels here by 4x。

 we are this1 by1 convolution projecting from 2K channels to May 512。From 2K to 512。

 and then we do three by 3 convolution from 512 to 512。And finally。

 we project it back to 2K using another one by one convolution。

 so that's the subtle of the design so we'll feed the reduce the feature map。

 not the original feature map which has 2K channels but we want to feed the reduce the feature map。

 which has only five to 12 channels to the  three by three combvolution。



![](img/8229e2bc18aa5938afa68d69b84b507c_22.png)

By the way， we expanded the channel so that we can have a good expressiveness by having 2K channel in the end。

So how to calculate the total number of max， the first layer。

 we have 2K input by12 Oppo channel H by W one by one。



![](img/8229e2bc18aa5938afa68d69b84b507c_24.png)

The middle， we have3 by3 convolution， input output 512 by 512。

 H by w time time since this is3 by3 convolution。Once year from 512 to2 k1 by one to in that y w。

 So that's the total amount of max。

![](img/8229e2bc18aa5938afa68d69b84b507c_26.png)

How does that compare with if we have only the three by three con？



![](img/8229e2bc18aa5938afa68d69b84b507c_28.png)

It'll be like this right if we only have history three by3 convolution each09。

 then we're projecting from 2k to 2k from 2k 2k to 2k。



![](img/8229e2bc18aa5938afa68d69b84b507c_30.png)

That's actually8 times 8。5。Times more compared with our case。We doing is bottleneck architecture。

So the bottleneck architecture already shrinked the number of channels with a three by three convolution。

Such that we can reduce the max。What about the number of parameters？



![](img/8229e2bc18aa5938afa68d69b84b507c_32.png)

Three by three count one by one count， which is2 by512， and then three by three counts。

5 12 by 512 and then one by one。So this is a total number of max。



![](img/8229e2bc18aa5938afa68d69b84b507c_34.png)

And again， compared with just using a single three by three column from 2 k to 2 k。

 that will cause a 2 k by 2 k by nine。

![](img/8229e2bc18aa5938afa68d69b84b507c_36.png)

Wwhich is times 8。5 times higher compared with this bottleneck architecture。

 so the bottleneck architecture in Re 50 is quite efficient with respect to both the number of maxs and also the number of parameters。



![](img/8229e2bc18aa5938afa68d69b84b507c_38.png)

after res， right， it is re next， the next version of re。Which introduced the group convolution。

 So originally we have。

![](img/8229e2bc18aa5938afa68d69b84b507c_40.png)

This is 256 dimension input， 256 dimension output one by one。Projecting from 256。

 reduce it to 128 and using a three by3 to project 128 to 128 but here actually they are using a group。



![](img/8229e2bc18aa5938afa68d69b84b507c_42.png)

Group conmotion with group size of 32， and what does that mean？We can have 32。

 it's like when we have 32 independent smaller populations， each one is no longer 128 by 128。

 but ends actually from 256， actually project from 256 to4。



![](img/8229e2bc18aa5938afa68d69b84b507c_44.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_45.png)

Okay， but then from 256 to 128， we have or 256 to four， and we have 32 of them。

 so four times 32 that's 128。

![](img/8229e2bc18aa5938afa68d69b84b507c_47.png)

We can further change that since the last layer from 12 and8 to 56 can be also viewed as from 4 to 256 and we have three two of them。



![](img/8229e2bc18aa5938afa68d69b84b507c_49.png)

I four times 32 equal to what 28。Such that we can think about it as altogether we have 32 paths。

Right， and these paths can work together。That's equivalent to a multipl block。Po。

 you can convert it into a mixture of experts。So that's group con in Res next。

There is also very widely used architecture and mobile app。

 which we introduced the Dewise separable block。诶。So we use that to capture the use the depthized convolution to capture the spatial information and also use the one by one convolution to capture the information across the channels while we call it depth separable。

 we are separating remodeling of the spatial information versus the channel information。

 the spatial information is modeled by depthized convolution only spatial information。



![](img/8229e2bc18aa5938afa68d69b84b507c_51.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_52.png)

And then the pointwise convol models the channel wise interactions。

 so we separated them so that we can reduce the computation。And what does that？

Look like actually Mo I V2 introduce this inverted bottleneck block， okay inverted bottleneck block。

Different from a bottleneck block， actually the number of channels either a decrease by increase by six times expanded by six times。

What is the reason behind that？So here we have depthized convolution and remember depthized convolution。

 the flops is very low， it has one less dimension okay， only five terms multiplied together。

So the expressiveness is very weak。To compensate it for that， we want to introduce more channels。

 so here we are expanding the number of channels by1 by one using one by1 column。



![](img/8229e2bc18aa5938afa68d69b84b507c_54.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_55.png)

Expand the level of1 by six。In the bottleneck layer。

 we are reducing it by four because three by three normal co is very expensive。

But here we are expanding it because the depthwise convolution is very cheap and we want to have good expressiveness and model capacity。

 so here we are expanding the number of channels rather than shrinking the number of channels。



![](img/8229e2bc18aa5938afa68d69b84b507c_57.png)

So how do we calculate the Mac in this case？One by one column say the same one by one column还 and with。



![](img/8229e2bc18aa5938afa68d69b84b507c_59.png)

Inport channel， Ill channel， input channel， output channel okay。



![](img/8229e2bc18aa5938afa68d69b84b507c_61.png)

And for the middle part， that's where it gets interesting。

 so we expanded the number of channels from 160 to 960 and from 160 to 960 by and width times not。



![](img/8229e2bc18aa5938afa68d69b84b507c_63.png)

Since this is a depthwise combination there are there is no other 960。

 it's just 960 rather than 960 times 960 input channel times output channel but it's steps wise。

 so it's just a single 960 in this case。

![](img/8229e2bc18aa5938afa68d69b84b507c_65.png)

So this is the total amount of max。What about the total number of parameters？Again。

 using n equal to 16 as an example， I usually want to use real numbers rather than just the letter so that you can get some intuition。



![](img/8229e2bc18aa5938afa68d69b84b507c_67.png)

So this is the one by one column input channel， output channel， one by one column input channel。

 output channel。 And this is the depth wise layer9 times we have 960 channels。

 So the number parameter is very very small， I should just9 times 960。



![](img/8229e2bc18aa5938afa68d69b84b507c_69.png)

So that's why mobileNe gets applied to mobile devices a lot and has very low max and low parameters。

And the key reason for that is thanks to this inverted bottleneck layer and depthwise con。

Where it has one less dimension compared with novel convolution。But it's not perfect。

 what is under the rug here？So the activation memory is actually not efficient。

For this kind of inverted bottlene structure。The activation memory。Why is that the case？Okay here。

We are expanding the number of channels by six times to compensate for the F convolutions。

 low computation complexity。You're expanding nano channels by six times。

 so the feature mat originate is big noise。Six times meter right。

 so it's actually not activation memory friendly。If we look at the inference。

 this is from red than 18 to Mo IV to shrink by 75%， they are of the similar accuracy on image Act。

The number parameters reduced by four to five times from resNe to mobileNe。However。

The peak activation didn't increase， but even increased the 18%。 so the activation is a bit larger。

But you can see the peak activation is not the bottleneck for inference okay。

 this is for inference batch size of1。Acation is smaller than the weight。However。

 during training side where you have a pretty large batch size， the activation matters a lot。

So here are trends reduced。But by four times， but activation only improved by 10% okay so mobileNe is very good for inference inference time model size reduction。

 flow reduction， but is not good at reducing the activation memory。

 which is a bottleneck for training。So at training time。

 you wouldn't observe much memory reduction if you change from resident 50 to Mo V2 with very large batch size。

All right next design next building block shtle okay so here we are familiar with this already one by one column three by three one by one and this is group wise convolution now we have three three groups what is the problem here。



![](img/8229e2bc18aa5938afa68d69b84b507c_71.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_72.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_73.png)

Different groups only interact within the。I think the red group。

 green and blue group are independent。

![](img/8229e2bc18aa5938afa68d69b84b507c_75.png)

And now we want to encourage different groups to talk to each other therefore we want to shuffle the channels across different groups。

 this is after the channel shuffling， the red group have the component from both the red and also the blue and also the green okay so this is the shuffle information to encourage the information to flow between different channels。



![](img/8229e2bc18aa5938afa68d69b84b507c_77.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_78.png)

All right， there's also the transformer building block， which is getting super popular these days。

 like in vision transformers， basically all the operations are vision are transformer blocks。

So for transformer block， there's the mod head self attention， and H IA， and what is that？

So we have a tensor we first projected into query key and value with three different。

Weight number of the projection matrices。After converting that。

 we pass it through the attention mechanism we're going to talk about in the transformer lecture in detail。

 which is basically scaled dot product。Between the QKV。

 we first calculated QK transpose and normalizedize that by the square root of the hidden dimension。

 we pass it through the softm， we do a mask like a causal mask， finally we emboply that within the V。



![](img/8229e2bc18aa5938afa68d69b84b507c_80.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_81.png)

So that every token can attend to every token in this case。

 if it is causal the future token or the not a current token can attend to all the previous tokens。

So rather than convolution， which has a very limited receptive field in one layer。

 you would need a lot of layers， many layers to have a global access。

 global receptive field or a pretty large receptive field。Different from that。

This body heart attention， this attention mechanism。

 just using one layer you can attend to all the previous tokens they immediately give you a pretty large receptive field。

 which is good for both region and also language tasks。So after the MHSA。

 we can cnate the output from different head， so each head。

 they are independently operating in the attention mechanism， the QK transpose self max times v。

 they are doing the attention mechanism independently and finally we can coordinatenate them together and then projected again using the output projection matrix。

So here， although we have three input projection matrices like WQ KB。

 they can be contaminatated into a single three times larger matrix to one single kernel call for the matrix multiplication。

 since we want to avoid the number of kernel calls to reduce time spend on the GPU kernel calls。



![](img/8229e2bc18aa5938afa68d69b84b507c_83.png)

So if you see the red hand sign that basically depicts what is the process of the attention mechanism。

 we have three tensors， QK transpose， and also Q K transpose， and absolute B， okay。

Q this is n dimension， we have n number of tokens， Each token is of dimension D K transpose that becomes D times n。

 we do the matrix multiplication。We'll learn what is the number of maxs in the matrix modification。

ND timesCN。Okay。And the Mac is n squared D， n squared D。

 since the output is n by N in order to compute each element， we need D max。

 So altogether there' n squared D。We do the softm， and then we do another matrix multiplication with a V。

 so dimension would be n times n， so that's the result of N D by DN， the result is n by n。

And then we multi n by n by N times D。The computation is n square n squared D。

 so all with it we have two n square d so it's O n square A grow strategically with the number of tokens。



![](img/8229e2bc18aa5938afa68d69b84b507c_85.png)

So as the resolution gets bigger， the number token gets longer， as the context gets larger。

 the document gets larger， the tokens gets larger， this is actually quite computationally expensive。



![](img/8229e2bc18aa5938afa68d69b84b507c_87.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_88.png)

So that's the attention part。What does the attention map look like？

So here is a sentence this is a real example。We have in the page P paper， but a stat。

The sentence is at that the video game is a lot more fun than the film。

And we can see if the game word game attend heavily to video okay and I attend to fun a lot。

And more happened very heavily here to ban since more than I really talk together。

 the film here depend heavily to gain。Okay， so invest the attention map capturing the relationship between different tokens。

And naturally， you can see some of the tokens they don't attend for everything like the。

Pretty much everything is white so a meaning is not attending to planning stuff。

 so in the future lecture we are going to talk about token pruning tokens like that and we safely p。

Question。谢谢。Why is it symmetric， Why is it not symmetric in the diagonal。

It doesn't have to be symmetric， the future attend to the past versus the past attend to the future。

 not necessarily symmetric。And here when we are talking about multi head attention。

 basically we are concatednating the attention result across different head and pass through the output transformation matrix WO。

Okay， so that concludes our beauty box section and we talk about。FC layer， Donald convolution。

 group convolution， depth so as convolution， we use those convolutions to build building blocks such as inverted bottleneck bottleneck。

And also the modifiedide attention blocks。So we have a lot of building block now。

 Now we talk about how do we select among different building blocks。

 So we' introduce neural architecture search。So commercially， when we are designing the model。

 we usually design a manually， right so many layers。Many some kernel。

 we choose across different kernel size， three by three， one by one， by by five， seven by seven。

I' a paper the resolution， maybe 224， maybe 256， 384。And we learn those connectivity， bypass later。

 no bypass later。And we want to choose the number of channels， start with three。

 and then we added more channels。Where I added morehans。Reduccing the resolution， adding the channel。

 there is a lot of black magic doing the manual architecture search and usually it's very hard to get a model in actually feeding the demand of the hardware。

For example。Google's CPUU has 28， first generation of CPUU has 28 microbytes。

Of ice cream on cheap ice cream， so that fixed fit perfectly with Google I V1 because 28 microbyte exactly can fit the model。

 everything can be fit on the dash but。How do we design a model that's exactly 28 megabytes or 100 megabytes or certain of certain size？

If it fits， then it can fit in the cash， it'll be very fast， you could buzz itll be very slow。

Which motivates us to build automated design， space exploration method。

So that we can use machine learning to design these neural architectures rather than manually design them。

So this is comparing the menu design versus automated design。



![](img/8229e2bc18aa5938afa68d69b84b507c_90.png)

The search the design space okay in this number of maxs， this is X axis。

 we want a low low max so that we can make it faster， but we want a higher accuracy。

 so ideally we want us a model that is right here on the top left corner in both。

Low computation and high accuracy， and we hope the circle size to be small okay the circle size indicates the number of parameters。



![](img/8229e2bc18aa5938afa68d69b84b507c_92.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_93.png)

This big means there has two million parameters， here's4 million， here's in8 million。

 here's 64 million parameters。

![](img/8229e2bc18aa5938afa68d69b84b507c_95.png)

So all these models are handcrafted designs like Res than 15 is roughly 4 million max 76 top on accuracy exception model rather than 101。

 re next 101， roughly 80% top on accuracy， 8 billion max， so theres no free lunch。

 every increment for the accuracy comes at the cost of the flaws。



![](img/8229e2bc18aa5938afa68d69b84b507c_97.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_98.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_99.png)

What about automated design okay， like this wise fall approach designed by our lab？

You have only alpha beating math， alpha beating math for match。

 the accuracy even higher accuracy compare with whereass next and also exception。



![](img/8229e2bc18aa5938afa68d69b84b507c_101.png)

whichhich is showing that this very powerful tool to use neuro architect research to design a very small model。

 low computation but to match the accuracy width。

![](img/8229e2bc18aa5938afa68d69b84b507c_103.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_104.png)

。

![](img/8229e2bc18aa5938afa68d69b84b507c_106.png)

Very big human design models。And this is a whole family of models designed by AutoML。

 so here if you see the circle in the middle you can actually distinguish the round with hot graft versus disaster race。

 and this is AutoML design models。

![](img/8229e2bc18aa5938afa68d69b84b507c_108.png)

These are auto my design models。And you can easily tell the difference between these two。

 we have a bunch of dots on the top。leftft corner， which showing that given this huge design space。

 manual design， is sometimes interiorferior interact with such automated design approach。

With that as motivation， let's see what are the components of a neuroarchural search。

What is the goal of the direct search Okay so given the design space these are the building blocks okay this is the building search space building blocks with a lot of building blocks and then we have a search strategy and also a performance estimation strategy okay we want to propose the architecture and then collect the performance feedback and then iterate this process if you find a good model you can stop this iteration otherwise you want to continue this iteration propose a new architecture estimate performance estimate the efficiency。



![](img/8229e2bc18aa5938afa68d69b84b507c_110.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_111.png)

Such as vtency， energy， storage， different perspectives， and also accuracy for sure。

 give the feedback and repeat the search process again until you find a model and fit your need。

And to begin with， let's talk about a search space， okay。

 so that's a set of candidate neural architectures we're going to choose from。

We'll introduce two search spaces here， one is the cell level。

 the other is the network level okay so let's first look at the cell level， what does that mean。

So this is from the image all the way to the output we have magnetga layers。

 initially we have a large resolution like 2224， and finally we have a very low resolution。

 even a single prediction， so we have to go through benefit down sample layers to reduce the resolution and and increase the number of channels。



![](img/8229e2bc18aa5938afa68d69b84b507c_113.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_114.png)

So those are the reduced reduction cell， a reducing the amount of。



![](img/8229e2bc18aa5938afa68d69b84b507c_116.png)

Resolution。Can be done by strrata the cove or by poium。



![](img/8229e2bc18aa5938afa68d69b84b507c_118.png)

And between those reduction cells， we have those normal cells。



![](img/8229e2bc18aa5938afa68d69b84b507c_120.png)

And those normal cells are usually repeated。So the philosophy from this cell level search space is that you just want to search one unit。

And then you are going to repeat by building law many， many times， they here repeat it1 times。



![](img/8229e2bc18aa5938afa68d69b84b507c_122.png)

Another n times another in the n times and here for the reduction cell we are reusing the same reduction cell across different stages so basically all the building block boil down to two building blocks。

 one is the normal cell and the normal cell between the reduction cells。



![](img/8229e2bc18aa5938afa68d69b84b507c_124.png)

Okay。So that make a very complicated problem much simpler， so previously we have like 5 layers。

Now we only need to search two layers and we are repeating these two layers for the whole network。

These two layers fall into two categories， one is the reduction cell， one is normal cell。

 normal cell just repeat between this reduction cells and the reduction cells responsibility is to reduce the resolution。

 for example， initially is 224 and in the end it becomes 7 by7 okay so you reduced from 224 by 224 to 128 or 128。

120 to 2281 sorry 224 by 224 112 by 112 to 56 by 56 to 28 by 28， 14 by 14。

 and finally seven by7 five reduction action cells in the middle by three normal cell。

I see the result first， and then well down deeper how that worked。



![](img/8229e2bc18aa5938afa68d69b84b507c_126.png)

From this paper， the neuroact research paper。

![](img/8229e2bc18aa5938afa68d69b84b507c_128.png)

The cell architecture is quite unreadable okay， so that's the models searched architecture is searched by machine learning and we can see roughly they are this a layer H。

 this is H minus I minus one so we can take the input either from the previous layer or from layer before the previous layer。



![](img/8229e2bc18aa5938afa68d69b84b507c_130.png)

can do some operation like separable three by three bent and then do some operation like add to add these two ups and then cancate other the choices together and feed it to the output。

And similarly for the reduction cell， basically choose the input either from H or H minus1。

 pass say through two operations， add them together and then concatenate them in the end。



![](img/8229e2bc18aa5938afa68d69b84b507c_132.png)

So how is the architecture to select these choices？

So here this paper used a recurrent neural network as a controller to generate the game the candidate cells。

 okay so we don't quite use RN these days， but let's do the review and first select the one hidden state and then select another hidden state and then'll aggressively simply select the operation for the first hidden state。



![](img/8229e2bc18aa5938afa68d69b84b507c_134.png)

And then select the operation for the second hidden。And now we want to combine these hidden states。

 we want to select the method to combine these hidden states， okay and well repeat these b times。



![](img/8229e2bc18aa5938afa68d69b84b507c_136.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_137.png)

So here we first select。The gray part， select one hidden state， layer A。

 and then select another hidden state， layer B， and then select operation on top of the first hidden state here is selected3 by three column。

 and then select the second hidden state operation， which is two by two next pool。

And then we select the method to combine them and here is use an add operation to combine them okay。

 so we are repeating this process B times。

![](img/8229e2bc18aa5938afa68d69b84b507c_139.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_140.png)

The question here， what is the design space， what is the size of the design space。

 say we have two candidate inputs exactly like this case。



![](img/8229e2bc18aa5938afa68d69b84b507c_142.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_143.png)

And then we have M candidate operations to transform the inputs okay to transform the inputs the yellow part。

 we have M candidates。

![](img/8229e2bc18aa5938afa68d69b84b507c_145.png)

And then we need to combine them in the green part and there are n potential operations to combine them。

 a is one of them， but there are n potential methods。



![](img/8229e2bc18aa5938afa68d69b84b507c_147.png)

What is the size of the search space when we have B and ASs？No。Maybe one minute we think about it。

It's consider step by step。It is loud。Very commonly to use the cost。Think step by step。

So what is the step one？Thanks that one。I to。Se I La hidden state。So we can either select from。

 like we mentioned here。

![](img/8229e2bc18aa5938afa68d69b84b507c_149.png)

We can either select from the previous state or the state before the previous date。

 also we have two choices for selecting one hidden state。



![](img/8229e2bc18aa5938afa68d69b84b507c_151.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_152.png)

And then we have another two choices first the elect on the second state。

And then we select the operation on the first hidden state。

 here I'm operations I'm candidate operations to perform the input。And the second one。

 also M possibilities。

![](img/8229e2bc18aa5938afa68d69b84b507c_154.png)

And after that， we have earned approaches to combine those two hidden states。

So that's just one layer。And we want to repeat this for B layers。



![](img/8229e2bc18aa5938afa68d69b84b507c_156.png)

So。

![](img/8229e2bc18aa5938afa68d69b84b507c_158.png)

To the power of B， so that's the complexity of selecting the total design space。

Assuming I'm equal to five， that's actually very typical， we can have one by one column。

 three by three column， five by five column identity orholding easily you can get five choices。

Im equal equal the five。ThenN equal to2。 we can do item wise addition。

Or we can do vitamin Y modificationplication。

![](img/8229e2bc18aa5938afa68d69b84b507c_160.png)

So we can easily have two or more than two operations for M， B layers。



![](img/8229e2bc18aa5938afa68d69b84b507c_162.png)

Given this example， we can have 10 to the power of 11 candidates in the design space that's a pretty huge design space。

 which motivate us。In the later part of this lecture， we are going to learn how to select。

 how to search within such a big search space。Okay， so that is the cell level search space。

 the philosophy is we took a lot of effort， very big design space， super big design space。

 we just want to pick a single cell that's very elegant we want to repeat this cell so many。



![](img/8229e2bc18aa5938afa68d69b84b507c_164.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_165.png)

So many times。But another thinking is that that may not be optimal because from deeper layer versus shallow layer you may want a different cells from deeper layer versus shallow layer behavior is very different。

 it may not be the best solution to just repeat the same building block。

 same cell across the whole depths of the neural network so it might be better to think about the whole design space。

 the whole network as a whole as a a larger design space different blocks may have different architectures。

So what is the design space in this case？

![](img/8229e2bc18aa5938afa68d69b84b507c_167.png)

So starting from the input all the way the output， we can have a reliable number of layers previously when we are repeating。

 we assume certain depths， but now we can also change the depth。



![](img/8229e2bc18aa5938afa68d69b84b507c_169.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_170.png)

For example， the first first stage， so here we have five stages each stage they are of the same resolution reduced from 224 all the way to 7。



![](img/8229e2bc18aa5938afa68d69b84b507c_172.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_173.png)

The first stage we can have depths of one， depth of two， depth of three。

 and similarly for later stage like this stage， we can have three， five， seven。

 nine different depths we can see to choose from。

![](img/8229e2bc18aa5938afa68d69b84b507c_175.png)

Also， we can have the resolution dimension， okay， the input resolution doesn't have to be 224 by 224。

But rather， it can be 120 about 128。Or 256 by 256。Or at training time。

 you can dynamically randomly select different resolutions， which usually helps。

 like in the previous quantization lecture we learn about usually adding randomness helps with generalization and helps with training so here we can also train with sometimes with 192 by 192 sometimes trained with 256 by 256。

So that's the resolution dimension measure。We also have this with dimension， okay。

 so we can choose from 48 channels in the first place and 64 or 96。



![](img/8229e2bc18aa5938afa68d69b84b507c_177.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_178.png)

When we are going deeper， we want to have a larger resolution， a larger dimension right here。

 so we can have 1，20，1，20。啊128 or。啊。208048， et cetera， okay so we can choose different width。Also。

 we can choose from different kernel sizes， so different color here mean different。



![](img/8229e2bc18aa5938afa68d69b84b507c_180.png)

Different size， for example， here， three by three co， seven by seven co， five by five co。

 we can have different kernel sizes。

![](img/8229e2bc18aa5938afa68d69b84b507c_182.png)

Its all very flexible。We can also have the topology， the connection， for example。

 when we are doing the down sample。From。One time to two times four times eight times all the way to 32 32 times。

 we can go through different paths。We can stay at the eight times down sample and they stay for a while and then we jump to16 times down sample until the end。

For some super resolution tasks or sorry for some classification tasks。

 this is the way to go reducing the resolution。And sometimes for for segmentation tasks。

 we want to have pixel or wise prediction， so the output resolution and input resolution are pretty much the same。

 so we want to first。当 sample， then up sample。So this also applies to auto encoders。

 which nowadays is very widely used。In diffusion models， okay， LDM latent diffusion models。

 we are going to learn later in in this lecture series。

And you first down sample and then you up sample。So you can要说 down山头 up山头 down山头 up山头。

So the trajectory across the grid。In is representing actually the architecture of the model and when do you downs samplele。

 for example here when we are we are doing the samplele and the naturally layer we are not and then we are doing nano samplele and naturally layer we don't versus we just down samplele and some down samplele up sample of sample up sample with the different path different trajectories within this grid actually。

correspondrespond to a network architecture in the search space。

 so that's network level topology connection and the search space。Okay。

 so now let's take a break before we jump into how to design the search space。Yeah。All right。

 welcome back and let's continue discussion， let's talk now talk about design and design search space。

 so just now we talk about there's a huge design space right either using the cell level or the network level and how do we narrow down the design space。

For example， when we are searching something we don't want to search like in our forest。

 the forest is pretty big， your friend get lost。The first you want to do is to narrow down which part of the forest it got lost right just like here we are given a pretty big search space for our target design。

 we want to first narrow down okay or front get loss in the left part of the forest and we want to further first optimize the search space。



![](img/8229e2bc18aa5938afa68d69b84b507c_184.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_185.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_186.png)

And then we do the model architecture search the specialization within the smaller。

 the optimized search space。So we'll introduce T Nas。

How do we do automated the search space optimization to search the search space。

 and then we do the resource constrained model architecture search。

 specialized model for a particular hardware constraint。

So talking about hardware work constraints streams。On the mobile devices， the latency matters。

 you want it to react very fast， the energy matters。

 you don't want it to train in the battery of your phone very quickly。But on these IoT devices。

 African drink is also a pretty big drink。And also recently for large language models memory and the GPU is also a very scarce resource。

 sometimes you have only 80 gigabyte of memory you want to really well utilize the memory。

 so latency， energy memory， those are the big constraints。

Especially from cloud AI to mobile AI to tiny AI， when we are looking at the memory size。

 we are talking about tens of gigabytes。

![](img/8229e2bc18aa5938afa68d69b84b507c_188.png)

A few gigabytes versus a couple of hundred kilotoytes or tiny AI。



![](img/8229e2bc18aa5938afa68d69b84b507c_190.png)

Whi has a pretty big gap between the available resource of the memory that can Q q00 kilotobyte versus several megabytes。



![](img/8229e2bc18aa5938afa68d69b84b507c_192.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_193.png)

For even not to mention large language models it just so big。



![](img/8229e2bc18aa5938afa68d69b84b507c_195.png)

And if we compare the memory for GPU for mobile phone to medical controllerts。

 they are almost invisible for the macro controller since the memory is so small。



![](img/8229e2bc18aa5938afa68d69b84b507c_197.png)

Here we have three orders of magnitude， smaller memory， and four orders of magnitude。

 smaller storage。

![](img/8229e2bc18aa5938afa68d69b84b507c_199.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_200.png)

So as a computer scientist， you want to design across the whole space， both big and also small。

 but is pretty challenging。So if we want first narrow down a design space。

So how do we find a good design space first of all。

 here we listed a bunch of design spaces we have different width。



![](img/8229e2bc18aa5938afa68d69b84b507c_202.png)

The width of the channel and also different resolutions， 160， 112， 69， 96， etca。



![](img/8229e2bc18aa5938afa68d69b84b507c_204.png)

So given these different design spaces， which is good， which is bad。Ideally。

 we want to evaluate the accuracy by training the model to the end to observe the accuracy。

 but that is very computationally cost。So how do we evaluate a model without training it？

So here we use a very simple but in fact heuristic is to see a good design space is more likely to achieve high flops under the same memory cat。

You only have this amount of memory， it give me the most amount of flops。

Assuming the model capacity is is proportional to the flos。So if given the model same memory cons。

 you can fit more flops， that is considered a good design space。

And also hardware from hardware perspective， computation is cheap， data movement。

 memory access is expensive。So if you given the same model of memory constraints。

 you can feed more flops， and that model of architecture is considered more efficient。Therefore。

 we ploted the relationship between the flops。And also this is the cumulative probability of different design space。

 like this yet red correspond to width of 0。5 resolution of 1。4。

 this black design space correspond to width of 0。3 resolution of 160， so a higher resolution。

 but lower smaller width。You don't know which is better， right， Low resolution。

 higher width or higher resolution， lower weight， it's hard to tell。But now this chart。

 we can easily tell the difference， so in this red design space。



![](img/8229e2bc18aa5938afa68d69b84b507c_206.png)

80% of the models have more than 15。3 million maxs。But in this supply design space。

 80% of the models has only 32 mini maxs。

![](img/8229e2bc18aa5938afa68d69b84b507c_208.png)

laThe red design space has can fit more gloves given the same memory budget。

 so you consider that as a good design space。

![](img/8229e2bc18aa5938afa68d69b84b507c_210.png)

And you verified that， between a bunch of models within that design space and observed that the best accuracy in this design space is about 78。

7%。

![](img/8229e2bc18aa5938afa68d69b84b507c_212.png)

Versus in the design space on as seed floor。Which verified our。

Idea that a design space that can give you more flops。

 given the same memory constraint will be a better design space。And so。

We just want to analyze the fl distribution。Larral flops means more larger model capacity。

 which is more likely to give a higher accuracy。So we use this principle to design this design space。



![](img/8229e2bc18aa5938afa68d69b84b507c_214.png)

Okay， so and it's actually quite effective compared with the RA at 18 and 24 resolution。

Which is actually running out of memory on the microcons design space。Our space is superiorters。

 even larger and huge design space or random design space。

And also the search space with higher immune flops on the x accents， medicine and accuracy。

 they are very positively correlated。

![](img/8229e2bc18aa5938afa68d69b84b507c_216.png)

so if you have higher flos， then very likely you have higher accuracy you see the correlation is it's pretty linear。

All right， so we use this approach to narrow down in design space using the heuristic that you want to have more flops given the same memory project。

And now let's talk about now we've finalized the design space and how do we do search on top of that design space and how do we automate this process without human interaction。

 which is quite helpful if you want to build a product， build a tool。

You don't want to specialize by using a human expert that's not scalable。

You want to have a push button solution， no matter what kind of scenario came。

 you were given the new memory constraint， given a new latency constraint。

 you wantt exactly fit this amount of design target accuracy target that is in target。

 how do we have a push button solution to find the neuralnaural architecture？



![](img/8229e2bc18aa5938afa68d69b84b507c_218.png)

So we'll talk about several search strategies on top of the search space， including grade search。

 random search， reinforcement learning， including disscent， and also evolution research。



![](img/8229e2bc18aa5938afa68d69b84b507c_220.png)

So let's start with re research， which is the simplest and sometimes work very well。

So research very traditional way of parameter optimization。

 you can have many degrees of optimization in this scenario we use tool for illustration purpose。



![](img/8229e2bc18aa5938afa68d69b84b507c_222.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_223.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_224.png)

One is the resolution， y x or1。2 x or1 from yx。

![](img/8229e2bc18aa5938afa68d69b84b507c_226.png)

With you there 1。1，1。1，1。2。 So we are trading off business resolution and with。

We call it grid search because each dimension we can have a step size。

And then we can have a grid by dividing the whole space into several smaller ones。啊明。

Each dot on the grid is one design in the search space。

So the entire search space is represented as the Cartation product of a single dimension design spaces like this is basically the auto product between resolution and width。



![](img/8229e2bc18aa5938afa68d69b84b507c_228.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_229.png)

But to obtain the accuracy on each candidate network， we want to train them from scratch。

 we don't have to train them all the with convergence。

 but we can train in for a while to observe the accuracy。So that's the bad part of it。

 you have to train for each design， you have a lot of if you have a lot of GPUs。



![](img/8229e2bc18aa5938afa68d69b84b507c_231.png)

That's probably a very easy way， just two for loop。

 for resolution for with training and pick the best one for me。



![](img/8229e2bc18aa5938afa68d69b84b507c_233.png)

Of course you want to satisfy the it a constraint， some of them we have very large with pretty big resolution。

 you may not fit， you may not satisfy the it a cons。

 so we are going to eliminate them even before wewin okay so eliminate the points。

 the design that break the it is a cons before twining them。



![](img/8229e2bc18aa5938afa68d69b84b507c_235.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_236.png)

So this very easy to implement。But it may take a quite a long time to evaluate them one by one。

Make sure you prune away those obvious bad lines like the red lines in this scenario。

And now we want to introduce compound skating， you have so many dimensions to search from。

Do you push one to the extreme or do you。Tune eachnob the moderate way for each other okay。



![](img/8229e2bc18aa5938afa68d69b84b507c_238.png)

Look given the baseline。This is baseline architecture from input to output。We can scale the width。

 make the width much wider compared the first one， we can also still scale the depth。

 make it much deeper。We can also scale the resolution， higher resolution， lower resolution。

And the best way is actually do not corner each design knob to the extreme。

 like only scale the width， only scale the depths， but we want to do Kong Kong scaling okay。

 that's the lesson here。

![](img/8229e2bc18aa5938afa68d69b84b507c_240.png)

You want to make it a little deeper but not absolutely to the extreme。

 a little higher resolution a little wider okay so here the target is to make the model 2 x as the original network so you don't want to make only one dimension2 x but for each dimension the width depth to resolution multiply them together you want to have2 x but not each of them okay。



![](img/8229e2bc18aa5938afa68d69b84b507c_242.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_243.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_244.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_245.png)

So that's the principle。And similarly， if you want to compress the network。

 you don't want to just dorun， you don't want to just do quantization or distillation。

 you want to put them together just and do a little bit of each and combine them together that usually works pretty well。

So that's great search， okay？Random search seems very trivial right you can compare with a grid search one by y youre just for x for y and then evaluate each of them now you can randomly evaluate domain design space。



![](img/8229e2bc18aa5938afa68d69b84b507c_247.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_248.png)

， this is actually quite an tri and quite helpful for s check to start with。Even in the homework。

 make sure you want you run random search for a little while。

You don't want to see that the reward gets constant， no improvement at all。

 that must be something wrong in your design space or the search or the evaluation or the reward function。

Uualally you want to do some first order approximation。

 do a quick sanity check by running random search after a few iterations。

You probably want to observe some improvement of the latency accuracy trade offs。

It's a random search， you need the first have to do。Reinforcement learning。

 that's a very advanced way， some tricky way。And not quite easy to use in practice。

 but I want to put it here。So you design a sequential decision making problem so you want to decide what is the number of filters within the future height using width strike。

 height and width number of filters and future height， etc cea。

 you want to design a step by step one by one using a RNA nowadays RNA is no longer popular probably using an autoregressive model some kind of autoregressive model。

 no necessary RNA controller。

![](img/8229e2bc18aa5938afa68d69b84b507c_250.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_251.png)

And using that controller to propose the architecture consisting of the height， width， user size。

 etc。

![](img/8229e2bc18aa5938afa68d69b84b507c_253.png)

Propose this architecture with probability P and then train a child network with this architecture to get accuracy latency to get a reward。

 and then you compute the gradient of P， which is a probability here and scale it by R to update the controller so you can have an updated controller and max iteration is going to encourage high reward and discourage bad reward and repeat that process as your reward by the higher and higher。



![](img/8229e2bc18aa5938afa68d69b84b507c_255.png)

对。We can also use gradient descent to make this search process differentiable okay so for a path from this node to this node we can have many different choices。

 many different configurations。

![](img/8229e2bc18aa5938afa68d69b84b507c_257.png)

We can have your three by three column， five by5 count or bachelor's count。



![](img/8229e2bc18aa5938afa68d69b84b507c_259.png)

Okay， so how do we choose from them？We can treat the output as a weighted sum。

Of different edges from different red， yellow， different colors。

 right we are learning the probability of choosing different choices。For example。

 here we are choosing this blue part， maybe it be like one by one column but actually during training time when we run inference for all of them。

 you can imagine the memory requirement would be much larger because we have to run in activation for both those three three5 by file and nine by one。



![](img/8229e2bc18aa5938afa68d69b84b507c_261.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_262.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_263.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_264.png)

We are learning the probability for these three okay and and in first time we sampled one with the highest probability。

But tri time you can imagine， this takes a lot of GPU memory。



![](img/8229e2bc18aa5938afa68d69b84b507c_266.png)

And here for his time。We just pick the one with the probability sample across according to the probability and choose a path。



![](img/8229e2bc18aa5938afa68d69b84b507c_268.png)

And this is about。Making it differentiable， how about latency can we also make latency differentiable if the case that'll be interesting。

 right？So here we have four different choices for this layer， three by three cons。

5 by five con densityity and okay。

![](img/8229e2bc18aa5938afa68d69b84b507c_270.png)

From the accuracy perspective， probably three by three and five by five maybe five by five has higher expressiveness has higher capacityac。

 but from the latency perspective therere slow， the identity would be the fastest right so how do we take that into account when we are doing the stochastic reading descent。



![](img/8229e2bc18aa5938afa68d69b84b507c_272.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_273.png)

Previously， we just care about the growth entropy loss， which doesn't。



![](img/8229e2bc18aa5938afa68d69b84b507c_275.png)

F into the lat like identity maybe a lot better than five by five with respect to the latency。

 so how do we make latency differentiable？

![](img/8229e2bc18aa5938afa68d69b84b507c_277.png)

So here we learn。

![](img/8229e2bc18aa5938afa68d69b84b507c_279.png)

The probability of choosing each path there ourdota， ettera。

 and then we pre measure the latency for each building block measure the latency for the three by three convolution measure latency since is the same about inputs。

Mjosure the latency for5 by5， the latency for avent， the the latency for pullinging。

And then the expected latency would be summing up the probability times each latency probability and latency probability times so that the expected latency。

 okay given the probability key distribution here。We can update this。

Probability distribution by adding this expectancy to the loss function Okay so this is the price the loss。

This is the regularization for the weights， this is the latency portion of the loss function in this way we are learning the probability so that we can make latency inf and we plug in with latency as part of the lost term so that when we are doing the gradient descent。

 we can also take care of the latency。

![](img/8229e2bc18aa5938afa68d69b84b507c_281.png)

Such that we can learn about both give a high accuracy and also give a low latency。

Any questions about this part？About autocl in the per？O good。

The next way to do about the search strategy is about evolutionary research okay a quick review we talk about starting with the random search right and then we talk about using RL read the search now let's talk about evolutionary research and let me make the revolution process in biology we have a population which is already red design space。



![](img/8229e2bc18aa5938afa68d69b84b507c_283.png)

And then we have a fitness function， which basically is the accuracy， the latency， ettera。



![](img/8229e2bc18aa5938afa68d69b84b507c_285.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_286.png)

And then we do the notation and cross over and talk about that。And then select the survivor。

 assuming they are the best species， and then we repeat this process to do mutation cross over。

 and then survivors should actually repeat this process on and so on。



![](img/8229e2bc18aa5938afa68d69b84b507c_288.png)

And let me target it。So let's see how that works。Fitness selection。

 we are given a onefall network we're going to talk about in the next lecture and also in the home。



![](img/8229e2bc18aa5938afa68d69b84b507c_290.png)

Given a sub network， you want to measure the latency and accuracy。

 you want to have accuracy low latency and high accuracy， and otherwise it doesn't fit。



![](img/8229e2bc18aa5938afa68d69b84b507c_292.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_293.png)

It's too slow or the accuracy is too low， then we need to rele。



![](img/8229e2bc18aa5938afa68d69b84b507c_295.png)

And after that， we'll give the feedback to sample again and repeat this process。

 so the fitness function is basically selecting between the latency， the efficient a。

 the efficiency such as latency， throughput， memory consumption， energy， etc。



![](img/8229e2bc18aa5938afa68d69b84b507c_297.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_298.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_299.png)

So that's the fitness function。what is mutation。 And， so we started with。



![](img/8229e2bc18aa5938afa68d69b84b507c_301.png)

This natural architecture two stages， perhaps of three， the first stage， perhaps of three。

 the second stage。And then we mutate and depths such that the first stage can become two types of two。

 second stage can become types of four or three or five and can change it。



![](img/8229e2bc18aa5938afa68d69b84b507c_303.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_304.png)

We can change the depths， we can also change the operator， for example。

 we rotateate from a three by three convol to a5 by5 convol。



![](img/8229e2bc18aa5938afa68d69b84b507c_306.png)

![](img/8229e2bc18aa5938afa68d69b84b507c_307.png)

From a three by three convolution to a7 by7 convolution。So that's mutation。

We can also do crossover to crossover， take two inputs， mutation， take one input。



![](img/8229e2bc18aa5938afa68d69b84b507c_309.png)

Okay， so also we take two inputs。Thiss an Nple one， this' is Liple two。

 two architectures we want to cross over。These two are the same， so from parent blind is no problem。

From the second layer， we can choose from either parent one or parent2。

 actually the crossover is chosen from parent2。Similarly for the last layer is also chosen from pairing two Okay so randomly choose one operator among the two choices。



![](img/8229e2bc18aa5938afa68d69b84b507c_311.png)

We have two parents for each layer， so that's the crossover we are going to implement that in the third lab。

 so make sure you are clear about this about mutation takes one input crossover takes two inputs two parents。

And after that， we conclude this lecture about the NAS。

 we first introduced the primitive operations and used that primitive operation to construct the building blocks。

And then we talk about the search space， very large search space cell level versus the network level。

 and then how do we design the search space such that we can have high fluxs given the same memory constraint。

And finally， how do we search on top of the search space using random search， with search。

 reinforce learning and evolutionary search okay？All right， so lab two is。

 feel free to check it out and let us know if you have any questions in the office hours。

Here are some reference。 Thank you。 That's all for the lecture today。



![](img/8229e2bc18aa5938afa68d69b84b507c_313.png)

Yeah。