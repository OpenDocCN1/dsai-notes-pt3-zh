# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p06 Lecture 6 - Quantization Part II  (MIT 6.5940, Fall 2024, Zoom recording) [BV1c8wNe1ErX_p6]

All right， good afternoon everyone let's get started so today we are going to learn about lecture six the second part of the quantization lecture so in the previous lecture we introduced the basic techniques of quantization。

 which is a super important technique both in the region age and also in the large language model age。

😊，Quantization is very widely used no matter if you want to deploy a neural network on the phone or the edge device or in the cloud。

 this is a very useful technique very widely adopted in industry and actually a big shortage of engineers currently who can specialize in such techniques so into this lecture well first review the linear quantization and also well cover two important concepts one is posttrain quantization PTQ the other is the QAT the quantization aware training。

 how do we fine tune model so that we can recover the accuracy remember like improvingruning we talk about pruning and how to fine tune p model to recover the accuracy and similarly here in quant we quantize it and then fine tune it so that's QAT。

And then we'll talk about binary and quantization to further push the quantization bit to lower bit to only one bit。

And finally we'll introduce automatic mixed precision quant。

 not every layer required the same number of bits， just like improving。

 some of the layers are more sensitive， some of the layers are less sensitive。

 so we want to treat different layer differently to minimize the storage and maximize the efficiency in similar case for quant。

Okay， so this is where we were left over since last Thursday。

 we talked about K means first we started with the floating point weights， P32 for the weights。

 B 32 for the activations。And then the second part。

 we quantized the weight using the K means quantization Okay， so for example， here。

 this is our familiar matrix， we have a code book and each entry with a sort two bit or four bit a low precision index looking into the weight。



![](img/c7d05054dd51f060aace57ca88c70825_1.png)

![](img/c7d05054dd51f060aace57ca88c70825_2.png)

![](img/c7d05054dd51f060aace57ca88c70825_3.png)

So that's the code book。So the computation is still arithmetic since we have de quantitized the weight into floating point it saved storage say but doesn't save the computation。

 which is still useful for large language model inference batch size of one where is memory bonded not compute bonded and weight is the memory the weight is the memory bottleneck so very useful technique we're going to implement that in the lab2。

 hopefully you are all。

![](img/c7d05054dd51f060aace57ca88c70825_5.png)

You will all downloaded， we will have them available in our website for lab too。



![](img/c7d05054dd51f060aace57ca88c70825_7.png)

Last lecture we also introduce linear quantation so both the weight and activations can be quantized to integer values and the computation is also done in integer arithmetic okay so we have a bias。

 we have a skating factor， we derive the equation for that。



![](img/c7d05054dd51f060aace57ca88c70825_9.png)

![](img/c7d05054dd51f060aace57ca88c70825_10.png)

So this is the K means quantization， we have a cluster index， we have a centroid。

 and then we can fine tune the centroid。

![](img/c7d05054dd51f060aace57ca88c70825_12.png)

We can see the accuracy is very well maintained， we can even combine。

 we can even combine p and quantization to further push the model size to be a smaller。



![](img/c7d05054dd51f060aace57ca88c70825_14.png)

When we are talking about linear quantization we introduced the zero point and the scalingkating factor okay。

 so for two bits， we can represent four numbers in four colors。



![](img/c7d05054dd51f060aace57ca88c70825_16.png)

And this is the quant value minus  zero point multiplied with a scalingating factor。

 and we can get a recovered P32 weight。

![](img/c7d05054dd51f060aace57ca88c70825_18.png)

So remember how to calculate the scalingating factor。

 so scalingating factor basically maps the interior range to the floating point range okay so this is the interior range。

 this is a floating point range。

![](img/c7d05054dd51f060aace57ca88c70825_20.png)

And it zero point maps z0 point in integer representation into zero the floating point representation。



![](img/c7d05054dd51f060aace57ca88c70825_22.png)

And we went through all the math to calculate in a quantized matrix matrix multiplication。

 so the single layer andLP， what is the breakdown about the computation so this is the majority of the computation then in low precision integer plus the bias。

 when this can be done by linear operation and also the shift operation and finally plus the integer add。



![](img/c7d05054dd51f060aace57ca88c70825_24.png)

![](img/c7d05054dd51f060aace57ca88c70825_25.png)

![](img/c7d05054dd51f060aace57ca88c70825_26.png)

But convolution is very similar， we just replace matrix multiplication with convolution。

 majority of the job is done in the integer convolution。



![](img/c7d05054dd51f060aace57ca88c70825_28.png)

Okay， so how should we get the optimal linear quantization parameters S and Z。

 so we'll talk about quantization granularity， similar to pruning granularity where we can prune a single weight。

 we can prune a row of weight， we can prune the whole channel or a whole filter or the entire channel to the different granularities for pruning and similarly there are different granularities for quantization。

And then we are going to talk about dynamic range clipping。

 so you may have a pretty big dynamic range， how do we clip them。And finally， about roundy， like 1。5。

 should we run it to one， should we run it to two， Should we so classicalically round it。

 We talk about roundy。So let's start with I start with quantization granularity。

So well first talk about per tensor quantization， you use one scalingk factor to scale the whole tensor so this is percent tensor quantization followed by per channel quantization so for one channel。

 all the values in one channel share the same scalingk factor。



![](img/c7d05054dd51f060aace57ca88c70825_30.png)

![](img/c7d05054dd51f060aace57ca88c70825_31.png)

And which has more scalingating factors？

![](img/c7d05054dd51f060aace57ca88c70825_33.png)

P channel quantization we have if you have like seven channels。

 you will have seven scaling factors right here per tensor quantization。

 you have one scalingkating factor for the whole tensor okay。



![](img/c7d05054dd51f060aace57ca88c70825_35.png)

And finally， group quant， this is very important for after blackwell architecture and blackwell architecture。

 group quant is very useful for four bit or below， we introduce per vector quant and also the MX data type the shared macro exponent data type。



![](img/c7d05054dd51f060aace57ca88c70825_37.png)

![](img/c7d05054dd51f060aace57ca88c70825_38.png)

Whi is a very interesting data type in lower precision。Okay。

 so let's start with potentialor quantization， which is very widely used。These days。

So we have one scaling factor for the whole tensor using a single scaling factor for the whole weight tensor that works quite well for large models。

 but for small models， people observe this degradation of accuracy。Why is the reason。

 what is the reason this potential quantization suffer from accuracy degradation？



![](img/c7d05054dd51f060aace57ca88c70825_40.png)

So if we plot。The channel index here is the range okay we can see the range actually differ a lot。

 some of the layers have a pretty big range， some of them have very little range if you use the same scalingkating factor for these diverse channels。

 of course you can now have a very good feeling for them all。



![](img/c7d05054dd51f060aace57ca88c70825_42.png)

So the failure comes from the large difference in the ranges of the weight across different op channels some of them have pretty big outliers outliers and weight values that has either a very big value or super small value compared with other values so that cause the you are wasting the dynamic range you observe very different behavior compared with other channels。

 so if you use the same scaling factor across all different channels you cannot very well represent them。

So the solution is per channel on， we want to treat these different channels individually okay so that we can have a specialized scaling factor for each channel。

And how does that look like？So this is our familiar4 by four matrix， input channel。

 output channel4 by four will compare per channel quantization versus the previous pertensor quantization。



![](img/c7d05054dd51f060aace57ca88c70825_44.png)

![](img/c7d05054dd51f060aace57ca88c70825_45.png)

Using persor quantization， we want to calculate first the scalingating factor okay in order to calculate the scalingating factor。

 we want to first have the R max， the power max， which is the max value。

 the value which have the max absolute value in the tensor， which is 2。12 in this case， R max is 2。

12。

![](img/c7d05054dd51f060aace57ca88c70825_47.png)

![](img/c7d05054dd51f060aace57ca88c70825_48.png)

And here we are using how many bits， two bits， okay， two bits。

 so Q max equal to equal to1 okay so R max divided by cube  Q max using the equation we derived in the last lecture。

 we can find the scaling factor that map this integer range into that floating point range so the scalingating factor is 2。

12。

![](img/c7d05054dd51f060aace57ca88c70825_50.png)

![](img/c7d05054dd51f060aace57ca88c70825_51.png)

So we have the scaling factor now we can quantize the matrix and since we are using symmetry quantization。

 so 0 point is0。

![](img/c7d05054dd51f060aace57ca88c70825_53.png)

So for example， 2。09 right here divided by0 2。12 that's approximately 0。

9 something is very close to1， so we quantize that to one this is the minus 0。98 divided by 2。

12 the absolute value is smaller than 0。5 therefore we quantize to 0 okay but on and so on we can repeat that and quantize each value。



![](img/c7d05054dd51f060aace57ca88c70825_55.png)

![](img/c7d05054dd51f060aace57ca88c70825_56.png)

![](img/c7d05054dd51f060aace57ca88c70825_57.png)

So this is the quantized answer。And if you can compare with the reconstructive tensor。

 we multiply each value with。

![](img/c7d05054dd51f060aace57ca88c70825_59.png)

![](img/c7d05054dd51f060aace57ca88c70825_60.png)

The scalingating factoror， of course， the biasers is zero。

 so we can directly multiply this is the reconstructed matrix。



![](img/c7d05054dd51f060aace57ca88c70825_62.png)

And we can calculate the difference 2。28。

![](img/c7d05054dd51f060aace57ca88c70825_64.png)

But now let's see， how does it look if we do the per channel on。

 rather than treating the whole tensor， now we treat each each row， each channel individually。

So let's first look at the first rule， what is Rx。

![](img/c7d05054dd51f060aace57ca88c70825_66.png)

Ourmic is 2。09。

![](img/c7d05054dd51f060aace57ca88c70825_68.png)

嗯。Therefore， the scaling factor is 2。09。

![](img/c7d05054dd51f060aace57ca88c70825_70.png)

Second row， our max is 2。12， skating factor is 2。12 and so on okay so different channels now we have different skating factor。

 which is the max value of the absolute value of that row。



![](img/c7d05054dd51f060aace57ca88c70825_72.png)

And now let's see your how we quantize though。Now we are using different scaling factors for different roles okay and so that we can quantize it in this way for example。

 previously 2。09 if we are using persor quantization will divided by 2。

12 now we are dividing that by 2。09 it's very close is actually y and then the second value divided by 2。

09， the absolute value is smaller than 0。5 therefore is rounded to 0。



![](img/c7d05054dd51f060aace57ca88c70825_74.png)

![](img/c7d05054dd51f060aace57ca88c70825_75.png)

![](img/c7d05054dd51f060aace57ca88c70825_76.png)

And this is the reconstructed cancer。

![](img/c7d05054dd51f060aace57ca88c70825_78.png)

Compared with the previous reconstructive tensor using per tensor quant now the value is more diverse you have 2。

09 you have 2。12， 1。92， etctera。 And the reason is that we are using different scaling factor for different channel so actually the reconstruction error。

 the quant error is smaller and the pertensor quant So we just want to use this very simple example to show you the the intuition where the per channel quantization can have a usually have a lower quant error compared with pertensor。



![](img/c7d05054dd51f060aace57ca88c70825_80.png)

![](img/c7d05054dd51f060aace57ca88c70825_81.png)

![](img/c7d05054dd51f060aace57ca88c70825_82.png)

And in particular。

![](img/c7d05054dd51f060aace57ca88c70825_84.png)

What do you see which one is different？This is the quantized。Tsor using per channel。

 this is quantized tensor using per tensor quantization， we observe this value is actually different。

The rest of the value are all the same， 10，10，1010， over this value is the minus1， this is zero。



![](img/c7d05054dd51f060aace57ca88c70825_86.png)

What was the reason for that？The sian factor， right， for example， if you look at this value， 1。03。



![](img/c7d05054dd51f060aace57ca88c70825_88.png)

Using the peror quant， it will be divided by this getting factor divided by 2。12。

 the absolute value is smaller than the half。And therefore。

 it's quant to 0 because the value is smaller than 0。5， surroundeded to 0 in this case。

But in this case。This values minus 1。03 will be divideded by the scalingkating factor 1。92。

The absolute value is larger than 0。5， since 1。03 is larger than half of 1。92。

 therefore is quantized to minus1 okay。

![](img/c7d05054dd51f060aace57ca88c70825_90.png)

So that's the subtle difference， you have a fine grained。

 more fine grained scalingkating factor compared with a single scalingkating factor。

 therefore the representation will be more accurate。

 smaller quant error using the perernal quantization and pertensor quantization。



![](img/c7d05054dd51f060aace57ca88c70825_92.png)

So of course， there's a tradeoff。What's bad about perernal cons？Right you need to store more values。

 more scalingating factors previously you need only one scalingk factor now each channel you need one so there's no free lunch。

 always a tradeoff you need to store more scaling factors。



![](img/c7d05054dd51f060aace57ca88c70825_94.png)

![](img/c7d05054dd51f060aace57ca88c70825_95.png)

Okay。So let's continue if we want to go even lower precision。

We need more accurate representation and more flexibility， right？

So so we can actually shrink the group size rather than per tensor per channel can further reduce the group size。

 we call it group quant。

![](img/c7d05054dd51f060aace57ca88c70825_97.png)

![](img/c7d05054dd51f060aace57ca88c70825_98.png)

Okay， using group quantization will introduce the per vector quantization and also the MX data data type。

 Metro exponent data type， which is very new。

![](img/c7d05054dd51f060aace57ca88c70825_100.png)

![](img/c7d05054dd51f060aace57ca88c70825_101.png)

![](img/c7d05054dd51f060aace57ca88c70825_102.png)

对。So let's first motivate。Gro quant， so I released this blackwell generation GPU。

 which is super powerful if you compare the performance， so comparing the H100 here this is G 200。



![](img/c7d05054dd51f060aace57ca88c70825_104.png)

Brace blackwell 200。This is running。

![](img/c7d05054dd51f060aace57ca88c70825_106.png)

Another model has a very big。Imrovement compared with the H100， the black wh architecture。

 compared with the Hopper architecture。There 7 x improvement and on the right time side。

 we see a new data time。

![](img/c7d05054dd51f060aace57ca88c70825_108.png)

A new tens core called FP4 tens core Okay so these are what we are already familiar with like FP 16。

 BF16 four and half。Pta flops， in8 tensile core， nine peta ops， FP8， FP 6， nine pet flops， FP 4。

 18 pet flops， 2 x，2 x the pixel input compared with FP8 innate tensil core。



![](img/c7d05054dd51f060aace57ca88c70825_110.png)

![](img/c7d05054dd51f060aace57ca88c70825_111.png)

Thank。So black while GPU。Introduce this macrotensor scaling。



![](img/c7d05054dd51f060aace57ca88c70825_113.png)

So that we can maintain the accuracy of FP4。Models and in order to do that。

 that's basically what we are going to learn the group quant having even smaller group size to have a fine grained scalingk factor so that you can have more accurate representation using lower precision。



![](img/c7d05054dd51f060aace57ca88c70825_115.png)

So let's jump into that， we will first introduce the VS quant per vector per vector scaled quantization。

SoPreviously， we have a scaling factor for each tensor， the per tensor quantization。

And now we want to have a scaling factor for each sub vector。

 like this sub vector and this sub vector。 so rather than r equal to skating factor R Q minus z。

 now we have two levels of skating factor， one global and one local。

 this global scalingkating factor is a 14 point core grain skating factor for the whole tensor。

We also have a integer per vectoror， a fine grain per vectoror for each vector， smaller granularity。

Skating fat。We are going to multiply these two scalingkating factors together。啊To scale a Q minus。

So that's achieving a balance between accuracy and the hardware efficiency by the fact that we can have a more expensive looking point scalingating factor。

But they are at a very close regularity。So let's try to understand this again。

Which is a more expensive scalingkating factor。The potentialsor one or the per vector is skin factor。

 which one is more expensive？This is F。16， those can be in the four or in eight。

So this is more expensive， right its FP 1660 lit， very expensive it getting effective。

 but we can have it as a very force granularity， the whole cancer have only one such expensive FP 16。

High precision skating factor。Only having that is not enough。

 we compound that with the less expensive integer getting factor at finer granularity。

Okay so we have a less expensive scaling factor for only low low precision。

 but at a finalr granular just a couple of weights， we have one scaling factor。

 so that's a very smart way to have on both sides。So in order to calculate the memory overhead。

 let's see how that work so we have a four bit quant with a weight we have four bit per vector scale。

 so this is four bit per vector scaling vector for every 16 element。

 so this is 16 element right here。And we also， what is the effective bandwidth width？

So each value is represented in four bits。And then we also have a four bit scanning factor for every 16 elements okay so the four bit scanning factor is emorized across 16 different elementss。

Plus， the original four bit。So it's altogether 4。2 to5。4our。25 bits， so that's the way to park it。

The overhead of two levels dating。So in that context， we can have multiple levels of scaling factor。

 okay。We can have the first level 0， level  one and continue different levels。

 So let's see what we have learned so far。 How does that fall into this realistic speak picture。



![](img/c7d05054dd51f060aace57ca88c70825_117.png)

We introduce this per channel on， okay， we have a scaling factor out there level zero scaling factor for the whole channel。



![](img/c7d05054dd51f060aace57ca88c70825_119.png)

![](img/c7d05054dd51f060aace57ca88c70825_120.png)

So the data type or the weight for the weight in red is into four。

 and then the group size I0 level0 group sizes per channel。

 the whole channel share the FP16 scaling factor so the effective bit width is four。

Since we have four here， I'm assuming we have many channels， thousands。

 tens of thousands of channels in large language models。This FP16 divided by 10。

000 that can be negligible， so you fact to bit with is roughly4。



![](img/c7d05054dd51f060aace57ca88c70825_122.png)

And in VS quant in VS quant， the data type is also into four， so intramedia is four bit。



![](img/c7d05054dd51f060aace57ca88c70825_124.png)

And then the L0 group size is 6 last me？Every 16 adamants we have a skating factor and the skating factor is on sign in4。

Okay and the next level ver size is per channel， the whole channel also share FP 16 scalingkating factor。

So what is the effective bandwidth with？The four bit and then another four bits being factor about shared by 16 values。

And this F16 bit can be divided by tens of thousands that can be ignored。

 so we have two four and a quarter that's the effective bandwidth width。



![](img/c7d05054dd51f060aace57ca88c70825_126.png)

So now all comes to famous。MX4， M6， and MX9 data type。



![](img/c7d05054dd51f060aace57ca88c70825_128.png)

So I start with Mx Mx4。SoData type is啊 S one M two。Remember in the last lecture。

 we have one signing bit and we have two men teasa bit， what is missing here。The exponent bit， right。

 where is the exponent bit？Im sure they are here。So we have one exponent bit that is shared by two values。

And we have one bit share our two letters。We also have a a bit scaling factor and this E8 only exponent。

 shared by 16 values。These are the two levels of scaling factor。



![](img/c7d05054dd51f060aace57ca88c70825_130.png)

And now we can quickly calculate what is the effective precision bid with for an next form。



![](img/c7d05054dd51f060aace57ca88c70825_132.png)

![](img/c7d05054dd51f060aace57ca88c70825_133.png)

One bit for sine， two bit for the Manteza， three bits， right？

And then we have two bits shared by two values。Oh sorry， we have one bit right here E1。

 one bit shared by two values， so that's half a bit。And finally。

 we have eight bits shared by 16 values， that's another half bit。



![](img/c7d05054dd51f060aace57ca88c70825_135.png)

So three plus half plus half does altogether together four bit， that's why we call the anx4。



![](img/c7d05054dd51f060aace57ca88c70825_137.png)

We also have Mx6， which has one sign bit and form and tisA bit pluss four other five bits altogether。

 one exponent shared by two values。And eighth exponent share by 16 values or85 by a half by a half six。

similar for the Mx9， Mx9， we have one sign bit， seven antiza bit。8ight bit here。

 and then we have one bit of exponent shared by two values， group size of two。

 and then eight bit of exponent shared by L1 group size， which is 16。



![](img/c7d05054dd51f060aace57ca88c70825_139.png)

So that's eight plus a half plus a half that's nine bits。

So these are the more fancy representations going lower precision。And group quantization。

 which is super helpful to maintain the accuracy for such fine grain quantization granularity。

All right， so let's switch gear to talk about next topic about dynamic range leapy。

So dynamic range matters a lot since our it can change across different inputs。

 some of them may be large， some of them may be small。

 but how do we determine the dynamic which because that's very crucial since the skating factor is calculated by dividing the dynamic range between the quant value versus。

The啊 floating point value。So given a bunch of images。

 they may have very different dynamic range for each。So to determine the floating point reach。

 the activations， we need to gather the statistics before deploying the model。

And there are generally two methods， two ways。To calculate the dynamic bridge。

So if the model is trained by yourself， so if you train the model by yourself。

 if you have access to the training recipe during training。

 we can actually calculate the dynamic range by maintaining a EMA， the exponential moving average。



![](img/c7d05054dd51f060aace57ca88c70825_141.png)

![](img/c7d05054dd51f060aace57ca88c70825_142.png)

And what is that we maintain this R max and Rmin which is R max and Rmin across different iterations。

 so at t minus1， which is t this is t， so Rt basically equal to alpha Rt plus1 minus alpha rt minus1 we are using this discounting factor to discount the previous dynamic range。



![](img/c7d05054dd51f060aace57ca88c70825_144.png)

![](img/c7d05054dd51f060aace57ca88c70825_145.png)

With the current dynamic range。So the larger the alpha。

 the more we are using the recent dynamic range， okay so we smooth the dynamic range by using alpha。

What is the extreme case？A尔pha equals one right if alpha equals one。

 we are not using any of the old dynamic range because this term becomes zero okay。

 so that's intuition。But that is only possible if you have access to the training process。

 if you're train the model by yourself。If the model is trained by somebody else。

 we don't have access to this whole training process， therefore it's very hard。

 it's not possible to estimate the dynamic rich in that way。But that is the most common case。

 sometimes we just download a model from hugging phase， we quantize them， we deploy them。

Then in that case， how do we get the dynamic rich？We want to maintain a collaboration batch collaboration data set and just use that collaborationlib set like a bunch of images or a bunch of text to calculate to estimate the dynamic range。

We can use the dynamic range for you in this calib set。

To represent to assume that is representative for the。Iput images or text from other sources。Okay。

 so by running the collaboration batch， we have two ways try to find the R max okay where we probably don't want to use the full RmX。

 so actually there is a trade off here。Say this is the distribution of the activation， okay？

We can observe theres a very long tail。Of distribution， some of the values are super big。

 but you have a very small small amount of big values。

 very small amount of these very negative values。

![](img/c7d05054dd51f060aace57ca88c70825_147.png)

So if you set the me and max to be like here versus here。You have a big waste。

 You are wasting lots of the representation。Because。



![](img/c7d05054dd51f060aace57ca88c70825_149.png)

You have only a few， very few values in the extreme corners。



![](img/c7d05054dd51f060aace57ca88c70825_151.png)

So assuming we want to push the mean and max to be somewhere here where there are at least some weights because if you squeeze it closer the distance between each quantization boundary will will be smaller and a representation for these values in the middle these values in the middle will be more accurate if the quantization distance between adjacent bucket will be closer right so there is a tradeoff the mean and max you don't want it to be like the exact max mean value。

 you don't want it to be a very small but there might be a sweet spot。



![](img/c7d05054dd51f060aace57ca88c70825_153.png)

![](img/c7d05054dd51f060aace57ca88c70825_154.png)

![](img/c7d05054dd51f060aace57ca88c70825_155.png)

So if it is a laplashian distribution， we have closed form solution to find the sweet spot and for two bit。

That is 2。83B for three business， that's 8。89B。Okay。

 so that B is the Laha parameter can be estimated from the collaborationlib input distribution。

But this is a very rare case， very rarely the input follow this uppling distribution。



![](img/c7d05054dd51f060aace57ca88c70825_157.png)

So what should we do if we。Doesn't it doesn't follow the La passion distribution。

So a very widely used technique is to use the KL divergence method to collalibrate their range。

So we want to minimize the loss of information okay。

 since the interest models encode the same information as the original proteinin point model。

So we want to find the dynamic range by minimizing。Minimizing the k divergence。

 so this is the equation for these two distributions， P and Q。One is before quantization。

 one is after quantization。And we find the mean and max value such that it can minimize this kL divergence。

Let's give some intuition。Say this is distribution， this is distribution of activation value。

 this an absolute value ranges from zero all the way to 400， some of them might be even 480。



![](img/c7d05054dd51f060aace57ca88c70825_159.png)

![](img/c7d05054dd51f060aace57ca88c70825_160.png)

But most of the value okay so this is the normalized number of counts so loss of value is actually below at 40 and then has this long tail。

If we decide to set the max value to be here， what happens？So all the values above。

 all the values in this long tail will be clipped。To this value roughly 50。

 roughly 40 or 50 right all the value above 50 will be clipped to 50。



![](img/c7d05054dd51f060aace57ca88c70825_162.png)

And the count will be the sum of all these values count， will be a this is the count okay。

 so this is before and after the finding the max value using the minimizing the k divergence。



![](img/c7d05054dd51f060aace57ca88c70825_164.png)

![](img/c7d05054dd51f060aace57ca88c70825_165.png)

![](img/c7d05054dd51f060aace57ca88c70825_166.png)

What happens if you have a larger max value？So we you will have a a shorter tail on the right hand side。

And the value near the quantization near the max value will be more accurate， however。

The range will be larger， therefore these values。These values。



![](img/c7d05054dd51f060aace57ca88c70825_168.png)

We actually have a lot of them will be less accurate because the dynamic range is now larger and the quantization error is now larger。

It can be too small， it can be not to be too large。

 the best way to calculate that is by minimizing this chaos divergence。



![](img/c7d05054dd51f060aace57ca88c70825_170.png)

And let's see some other examples。So Alex now at present I'22， GoogleNet， GoogleNe。

 so this is the clipping， the optimal clipping range。



![](img/c7d05054dd51f060aace57ca88c70825_172.png)

![](img/c7d05054dd51f060aace57ca88c70825_173.png)

![](img/c7d05054dd51f060aace57ca88c70825_174.png)

Discovered for these different models， Okay， none of them is。



![](img/c7d05054dd51f060aace57ca88c70825_176.png)

The the largest value， they are not using the largest value。This is the largest value。



![](img/c7d05054dd51f060aace57ca88c70825_178.png)

But they are using somewhere smaller than the largest value which。嗯。Cleep。

The largest value to be the quantization max。So this figure further illustrates the intuition。

Between why we needed such kind of clipping rather than using the max value Okay。

 so if we have such a distribution， such a distribution， very long tail。



![](img/c7d05054dd51f060aace57ca88c70825_180.png)

For a long tail， if you choose the me and max， according to the real。Meme， this is negative 0。8。

 this is top positive 0。8 if we choose the max and mean this way。

 this will be your quantization range。And you can see the quantization noise is pretty large because the adjacent quantization cent。

 the distance is pretty far from each other。And in particular you have very low density data。

 just a few of them is in this big range。Whereas says we can clip it and this is the new mirror and this is the new max and this is the new dynamic range。

And the distance between adjacent adjacent central becomes much。Smaller， right。

 much smaller compared with Israel， so the quantization noise becomes much smaller。

And all these videos will be click to hear。still okay， why， because we just have very little。

 very few of them in this range， very few of them in this range。

 so it's fine to click them to the desired max we want。



![](img/c7d05054dd51f060aace57ca88c70825_182.png)

And this is actually a quite helpful technique very widely used。

So on the right hand side is's true the animation。This work is called Octa from NVdia。

 we can automatically find the optimal ving range。

![](img/c7d05054dd51f060aace57ca88c70825_184.png)

On the left hand side is showing that the mean error is conx and you be the cliping scr cannot be too small or too large。



![](img/c7d05054dd51f060aace57ca88c70825_186.png)

You feel too small， you waste a lot of the， you feel too large。

 you waste a lot of the dynamic bridge。It are too small。

 Then many values will be clicked to the boundary。 So there is a sweet， It's complex。

 There is a sweet spot in the middle。

![](img/c7d05054dd51f060aace57ca88c70825_188.png)

![](img/c7d05054dd51f060aace57ca88c70825_189.png)

And you can use this technique to find the optimal ving rid。



![](img/c7d05054dd51f060aace57ca88c70825_191.png)

And after applying occta， you see the accuracy coming mean well very well maintained compared with by P32 accuracy。



![](img/c7d05054dd51f060aace57ca88c70825_193.png)

哎。😊，So finding the granularity very important and then clipping is very important。Okay。

 any questions so far。Yeah。And emerge could also separate programs。With us too large。

 but those really and told。对。the value is the determined if you have four bits， you have 16 values。说。

不是。嗯。One type， yes， right。All right， no question， let's take a quick break and come back in five minutes to continue discussion about wronging。

All right， welcome back。Let me turn on the mic so you can hear me， al right。

So let's jump into the third part of quantization about Rbi， okay？



![](img/c7d05054dd51f060aace57ca88c70825_195.png)

So this is our conventional wisdom if you have a vector， 0。3， 0。5 0。7， 0。

2 you want to run it to like 0，1，1，0 okay so this round to the nearest。



![](img/c7d05054dd51f060aace57ca88c70825_197.png)

But contradictory to our conventional wisdom running to near is actually not optimal。

So weights are correlated with each other， the best running for each weight to the nearest is not the running the best round for the whole answer okay so sometimes we want to want some want to have some randomness。

 for example， the same answer sometimes like 0。5。If you run into zero， if you run into one。

 not necessarily running into one might be the option， sometimes we can even run into zero。诶。😊。

So such stochastic rounding usually helps during the quantization process。

So instead of running into the near， we want to choose running down or running running up and still to get best reconstruction。

 we can also learn a delta between zero and one。

![](img/c7d05054dd51f060aace57ca88c70825_199.png)

![](img/c7d05054dd51f060aace57ca88c70825_200.png)

![](img/c7d05054dd51f060aace57ca88c70825_201.png)

![](img/c7d05054dd51f060aace57ca88c70825_202.png)

We added to the original weight and then we run it to the nearest。



![](img/c7d05054dd51f060aace57ca88c70825_204.png)

For example， rather than just finding the newest。Runundning to the nearest we can add a value this value would be learned and we pass it through a function H is a function to map V to the range between0 and1 between0 and1 this is a possible solution using such rectified sigmoid so the Hv is between0 and1 we added it to w and then we run it to the nearest so that we can learn a tensor with the same dimension so this V is a random variable of the same same shape。

 same dimension。

![](img/c7d05054dd51f060aace57ca88c70825_206.png)

![](img/c7d05054dd51f060aace57ca88c70825_207.png)

![](img/c7d05054dd51f060aace57ca88c70825_208.png)

Flllowed by a regularization term encouraging the H to be binary between either zero or one so this is called an run very popular paper helping recover the accuracy。



![](img/c7d05054dd51f060aace57ca88c70825_210.png)

So just intuition is that don't just run to nearest， usually you can apply some stochastic。

To add some randomness during the wronging process， usually helps。

So let's do a quick summary about linear quantization what we have learned so far。



![](img/c7d05054dd51f060aace57ca88c70825_212.png)

We learn about zero points。Scaling granularity per tensor。

 qua grain per channel or group quant after below four bits。

 group quant is getting super popular and super important， Mx4， Mx6， IP4， etc ceter。Range weing。

 you can use different techniques to find the optimal range to clip it and then run the rounding techniques。



![](img/c7d05054dd51f060aace57ca88c70825_214.png)

![](img/c7d05054dd51f060aace57ca88c70825_215.png)

So by applying these techniques。

![](img/c7d05054dd51f060aace57ca88c70825_217.png)

For the weight for the activation， we can actually very well maintain the accuracy for a bunch of models like GoogleNe。

 ResNe。

![](img/c7d05054dd51f060aace57ca88c70825_219.png)

However， some of the smaller models like mobilenet， they still suffer。

Very heavy accuracy degradation， even after applying all the techniques we have learned so far。



![](img/c7d05054dd51f060aace57ca88c70825_221.png)

Like 10%， 2% degradation of accuracy， which is quite bad。



![](img/c7d05054dd51f060aace57ca88c70825_223.png)

So what should we do， So let's talk about。Find engineering techniques to recover the accuracy for these models。

 So let's talk about Q A， the quant of wire training。

A very simple technique was already introduced in the last lecture about using pay means quantization where we have a codebook after we get the gradient which is of the same size of the as the weight。

 so this is the weight because of the gradient， the dimension are exactly the same。



![](img/c7d05054dd51f060aace57ca88c70825_225.png)

We sum the gradients corresponding to the same color， the same centroid。

 sum the mop multiplied by the verin rate subtracted from the original centroid to get a fine tune in the sroid。



![](img/c7d05054dd51f060aace57ca88c70825_227.png)

So that's very simple for the K means quant。Ne network， where we are just updating the centralroid。

 updating the code book。Actually。呃It's more。Getting more complicated if they're doing linear quantization。

哎。😊，So in the linear quant， the weight and activations are all no precision。

 okay in or in the4 or YP4。In that case， during the treating process。

 we actually maintain a full precision weight in the back。



![](img/c7d05054dd51f060aace57ca88c70825_229.png)

Okay maintainin a full precision， not4 bit， not 8 bit， but 32 billion or IP 16 or 160 bit。

 a full precision copy of the weight。

![](img/c7d05054dd51f060aace57ca88c70825_231.png)

In the back throughout the training。So that we can。Accumulate very small gradients。

 very small changes。Aumulate that in the weight， without loss of precision。



![](img/c7d05054dd51f060aace57ca88c70825_233.png)

and once the model is fully trained， this FP 32， this full precision weight can be thrown away。

 we only keep the quantized weight deployment time。



![](img/c7d05054dd51f060aace57ca88c70825_235.png)

![](img/c7d05054dd51f060aace57ca88c70825_236.png)

So this is the layer minus one layer n layer n plus one， these are the activations。

 these are the weights， the weight will be quantized， this is the full precision weight in the back。

 quantized bid it to calculate layer N and the count being redlu and then get the output and for the next layer。



![](img/c7d05054dd51f060aace57ca88c70825_238.png)

For the backward process， we update this full precision weight so that we don't lose any precision。

And remember during the activation here， we calculate the activation and we should quantize that activation so that the boundary of the output。

 the value is quantized。

![](img/c7d05054dd51f060aace57ca88c70825_240.png)

![](img/c7d05054dd51f060aace57ca88c70825_241.png)

So this whole process is called simulated quantization or fake quantization during the training process。

Because the weight is quant to QW， but is still using a 32 bit floating point register to represent that value。



![](img/c7d05054dd51f060aace57ca88c70825_243.png)

Although the value itself is quantized， but we are still using a broken point number to for it。



![](img/c7d05054dd51f060aace57ca88c70825_245.png)

So we trained the model taking quantization into consideration by adding these two quantization nodes。

 compute nodes， one is quantization quantizing the weight。

 the other is quantizing the activation to simulate this quantization process。



![](img/c7d05054dd51f060aace57ca88c70825_247.png)

![](img/c7d05054dd51f060aace57ca88c70825_248.png)

![](img/c7d05054dd51f060aace57ca88c70825_249.png)

![](img/c7d05054dd51f060aace57ca88c70825_250.png)

So we have QW here， we have QY here。

![](img/c7d05054dd51f060aace57ca88c70825_252.png)

嗯。So forward process is very simple if  QW have QY， what about the backward process。

 how does the gradient flow to the weight？Because the quantization。

 this is the basic quantization activation if you think about it as an activation function okay so below0 and open。

5 is all0 between 0 and5 to 1。5 one between 1。5 and 2。

5 there two right so it's actually a step function。



![](img/c7d05054dd51f060aace57ca88c70825_254.png)

![](img/c7d05054dd51f060aace57ca88c70825_255.png)

So the quantization makes the input value to be discrete， okay the output is dereitized。

What's the problem here for the gradient？

![](img/c7d05054dd51f060aace57ca88c70825_257.png)

The gradient is all zeros。

![](img/c7d05054dd51f060aace57ca88c70825_259.png)

Right gradientd become zero， then you can learn nothing if you have a zero gradient。



![](img/c7d05054dd51f060aace57ca88c70825_261.png)

So actually we are using a technique called straight through estimator， STE。

 straight through estimator。

![](img/c7d05054dd51f060aace57ca88c70825_263.png)

We simply pass the gradient through the quantization as if it has never been quantized if it is just an identity function。

 so the gradient to the weight is the same as the gradient to the quantized weight the gradient of the quantized weight versus the gradient of the weight to be exactly the same。



![](img/c7d05054dd51f060aace57ca88c70825_265.png)

So this is the quantization compute node。This is quants W。

 this is W okay to treat the gradient between this purple line and this purple line to be exactly the same as if it is just identity function in this blue quantization node。



![](img/c7d05054dd51f060aace57ca88c70825_267.png)

![](img/c7d05054dd51f060aace57ca88c70825_268.png)

![](img/c7d05054dd51f060aace57ca88c70825_269.png)

And what happens？It becomes a identity function。哎 are making the written calculation much easier。

So this is the full full picture， Okay， so the purple line is back with us。



![](img/c7d05054dd51f060aace57ca88c70825_271.png)

During the back of the pass。Before and after the quantization node。

 the GY is exactly the gradient of the quantized y。

And here the GW is exactly the gradient of the quantized W。

 I see this blue quantization node is an identity function so we can use this straight through estimation technique。



![](img/c7d05054dd51f060aace57ca88c70825_273.png)

To estimate the gradient for the floating point weight。And floating point activation。

By using quantization of where training， so here are the quantization of where training results here are without the quantization of where training。

 we can compare the accuracy drastically improved a lot， so persor quantization improved from 0。

1% almost 19 to 70%。

![](img/c7d05054dd51f060aace57ca88c70825_275.png)

For channel con originally is better， it's like 59% now becomes 70% so this con where're training really plays quite a helpful role in the accuracy recovery Some of the models when NA mobile here。

 the original accuracy already is already pretty good。



![](img/c7d05054dd51f060aace57ca88c70825_277.png)

![](img/c7d05054dd51f060aace57ca88c70825_278.png)

![](img/c7d05054dd51f060aace57ca88c70825_279.png)

So the conversation where training gives a marginal improvement。But for large language models。

 which is very hard to trim it will be the desired scenario will be like this and you're just using post training quantization without any fine tuning the accuracy should be very good。

 we'll cover that in the large language models section。



![](img/c7d05054dd51f060aace57ca88c70825_281.png)

![](img/c7d05054dd51f060aace57ca88c70825_282.png)

In details。Okay， so that concludes the linear quantation part。Can we go even smaller。

Will introduce binary internal quant。 Just use 01， maybe minus-1。

To represent the weight and activations and let's see what kind of magic we're having here about binaryary and turnernary quantization to further push the quantization precision to only one bit。

So let's see an example， so wait。

![](img/c7d05054dd51f060aace57ca88c70825_284.png)

AMo product with activation eight times5 minus-3。 So this is the weight， this is activation。

We assume the boundary is 1x， computation is 1x， each operation。

 which is add a plus add and also and multiply and accumulate。



![](img/c7d05054dd51f060aace57ca88c70825_286.png)

We can quantize the weight to be binary okay rather than eight minus three，5 minus one。

 we have one minus one，1 minus one， so we finalized the weight if it is positive then it's one。

 if it's negative， then it's minus one。

![](img/c7d05054dd51f060aace57ca88c70825_288.png)

![](img/c7d05054dd51f060aace57ca88c70825_289.png)

![](img/c7d05054dd51f060aace57ca88c70825_290.png)

So we no longer have any modifications， but everything is plus or minus。



![](img/c7d05054dd51f060aace57ca88c70825_292.png)

![](img/c7d05054dd51f060aace57ca88c70825_293.png)

So the memory 32 times smaller for the weight， previously you need 32 bit。

 now you need only one bit plus one manage。

![](img/c7d05054dd51f060aace57ca88c70825_295.png)

And the computation is roughly2 x nice flops because previously you have。Mipplication。

 now they have no multi， only add。找号的维度的。

![](img/c7d05054dd51f060aace57ca88c70825_297.png)

One way is to deterministically finalize that if the wave is positive， then it's positive one。

 if it's negative， then it's negative one。

![](img/c7d05054dd51f060aace57ca88c70825_299.png)

That's basically a sine function， very straightforward。

 but you can imagine this results in a big degradation of accuracy。



![](img/c7d05054dd51f060aace57ca88c70825_301.png)

Just now we mentioned adding some randomness usually helps with quantization so we can do stochastic finalization。

 like in this equation here， if it's smaller than minus1 is deterministically to be zero。

 if it is above one is of first one， but between minus one positive one。

 sometimes it can be minus one， sometimes it can be quantized to plus one， if it is zero。

 you have half probability to be quantized to0 have half of the probability to be quantized to to positive。



![](img/c7d05054dd51f060aace57ca88c70825_303.png)

![](img/c7d05054dd51f060aace57ca88c70825_304.png)

![](img/c7d05054dd51f060aace57ca88c70825_305.png)

![](img/c7d05054dd51f060aace57ca88c70825_306.png)

![](img/c7d05054dd51f060aace57ca88c70825_307.png)

And can have a linear interpolation between minus one and plus one。

But it's harder to implement since we need a hardware hardware random number generator in hardware that's not straightforward。



![](img/c7d05054dd51f060aace57ca88c70825_309.png)

So let's see what happens to our familiar matrix， this four by four matrix we use 90 times。

If we finalize them to one bit just using the sign before and after the accuracy degraded by a big margin。

 degraded by 21%。

![](img/c7d05054dd51f060aace57ca88c70825_311.png)

![](img/c7d05054dd51f060aace57ca88c70825_312.png)

![](img/c7d05054dd51f060aace57ca88c70825_313.png)

And the quantnotation error is 9。28， pretty big quantnotation  error。

And what happens if we do some trick， okay， so we can have a scalingkating factor and we have a floating point scalingkating factor。

 which is r in this case。

![](img/c7d05054dd51f060aace57ca88c70825_315.png)

![](img/c7d05054dd51f060aace57ca88c70825_316.png)

to make sure the sum of all the values， the absolute value。

 sum of the absolute values of all the elements stays the same。



![](img/c7d05054dd51f060aace57ca88c70825_318.png)

So here， the sating cancer will be calculated by the L1 norm， which is the sum of the absoluteba。



![](img/c7d05054dd51f060aace57ca88c70825_320.png)

Deivided by n since every entry， the absolute value is one， so we have n elements。

 16 elements in this case。

![](img/c7d05054dd51f060aace57ca88c70825_322.png)

![](img/c7d05054dd51f060aace57ca88c70825_323.png)

Then we can just calculate the alpha， actually to be 1。05。



![](img/c7d05054dd51f060aace57ca88c70825_325.png)

W which is equal to the what norm divided by 16 valuess？And if we multiply this skating factor。

 we can see the quantization error slightly decreased。



![](img/c7d05054dd51f060aace57ca88c70825_327.png)

And the accuracy deelta actually improved a lot， actually becomes 0。2%。A positive 0。2%。

 which is very interesting。So just now we quantized only a binaryize only the weight。

 now we want to bindize not only the weight， but also the activation。



![](img/c7d05054dd51f060aace57ca88c70825_329.png)

![](img/c7d05054dd51f060aace57ca88c70825_330.png)

はい。

![](img/c7d05054dd51f060aace57ca88c70825_332.png)

So let's see what happens if both the weight and activation is finalized。

 so we have one times 1 plus1，1 times minus1 minus1， minus1 minus1 plus one， okay。

 so it's the choose table。

![](img/c7d05054dd51f060aace57ca88c70825_334.png)

![](img/c7d05054dd51f060aace57ca88c70825_335.png)

Let's see another operation， which which is the X operation Okay， I operation if this a。

Both values are the same， 1，1，0，0， then the output is one。If the two inputs are different， 10，01。

 then the output is 0， so that's the x operation you might have learned in 6。191。



![](img/c7d05054dd51f060aace57ca88c70825_337.png)

SoWhat's the relationship between mineralized weight and activation versus the actual operation？

Actually， they are heavily correlated， so if calculate if you sum them up for the external results。



![](img/c7d05054dd51f060aace57ca88c70825_339.png)

![](img/c7d05054dd51f060aace57ca88c70825_340.png)

Okay so this is one， I ignore with one， minus this is0， I ignore with one， one， I ignore with zero。

 zero， I with one。

![](img/c7d05054dd51f060aace57ca88c70825_342.png)

![](img/c7d05054dd51f060aace57ca88c70825_343.png)

You can get one plus 0 plus 0 plus 0 equal one。So now evenively doing this actually doesn't help。

It's minus minus2 versus1， they're not the same。So what's the relationship。

 how do we use external operation to implement the binaryized weight and activation？

Since Ive ignore it's is solely simple to implement in hardware。So let's see， how do we match them？

So I'm assuming everything is minus1， so since the smallest value is minus1。



![](img/c7d05054dd51f060aace57ca88c70825_345.png)

Okay if we have everything is minus one， if everything with some the mo， that's actually minus four。

And。

![](img/c7d05054dd51f060aace57ca88c70825_347.png)

But here， if we modifyly the sum of the X results with two， okay so this is the sum of the X result。

 which is one times2 and times2 can be very efficiently implemented by shift to the left for one bit。



![](img/c7d05054dd51f060aace57ca88c70825_349.png)

I think minus four plus the count times 2 plus minus4， that's exactly the value on the left。



![](img/c7d05054dd51f060aace57ca88c70825_351.png)

Okay， so take another look and assume everything is zero， okay， we just count't the number of ones。



![](img/c7d05054dd51f060aace57ca88c70825_353.png)

In this case。Because only if both values are the same then it's one otherwise is zero8 if it is zero is's corresponding to everything on the left is minus one so that's why we assume if everything is minus one and add the difference the difference how do we calculate the difference is the number of ones in this case times two since the difference between minus one and plus one is two so we have one more you add two you have two you have two more you add four you have three more you add six okay so you just count how many values are one and then times two。



![](img/c7d05054dd51f060aace57ca88c70825_355.png)

![](img/c7d05054dd51f060aace57ca88c70825_356.png)

![](img/c7d05054dd51f060aace57ca88c70825_357.png)

![](img/c7d05054dd51f060aace57ca88c70825_358.png)

And they can match the left on the right hand side。



![](img/c7d05054dd51f060aace57ca88c70825_360.png)

So put it in math。

![](img/c7d05054dd51f060aace57ca88c70825_362.png)

In equal equal2 minus n n is the number of elementss， in this case， four elementss。One，2， three。

 four， minus n times plus two times the sum of theagonno operation。



![](img/c7d05054dd51f060aace57ca88c70825_364.png)

![](img/c7d05054dd51f060aace57ca88c70825_365.png)

So minus minus four， since we have four entries here， we calculate the x sum the map。

 sum the mo to be 1 times2 and add minus4， so that's minus2。



![](img/c7d05054dd51f060aace57ca88c70825_367.png)

So we can use this very simple xO operation to calculate the scenario where both weight and activations are minorized。

And this count operation has a name is called pop count in return the number once。In this array。

 array is binaryry either one or zero， pop count operation is basically applying on this binaryry array count the number of ones it return the number of one it's called pop count。



![](img/c7d05054dd51f060aace57ca88c70825_369.png)

![](img/c7d05054dd51f060aace57ca88c70825_370.png)

![](img/c7d05054dd51f060aace57ca88c70825_371.png)

So using the pop count function， the final result would be minus n plus pop counts shifted by one since shipped by one is basically multiplying by two。



![](img/c7d05054dd51f060aace57ca88c70825_373.png)

Okay， using that we can easily calculate the dot product very easily。

 so for example here this is the original floating point on quantized weight and activation。

 this is quantized weight and activation。

![](img/c7d05054dd51f060aace57ca88c70825_375.png)

We just do the IO operation and then shift it by one。



![](img/c7d05054dd51f060aace57ca88c70825_377.png)

And then plus four， so that's the result。

![](img/c7d05054dd51f060aace57ca88c70825_379.png)

So the operation rather than multiplication and add now it becomes In and pop cut。

 both are very cheap to be implementing hardware the memory is 32 times smaller since all the weight and activation becomes one bit。



![](img/c7d05054dd51f060aace57ca88c70825_381.png)

![](img/c7d05054dd51f060aace57ca88c70825_382.png)

![](img/c7d05054dd51f060aace57ca88c70825_383.png)

The computation is roughly 58 times less， why is that。

 that's roughly the risk that's roughly the complexity between I explore popcorn operation versus Mac operation。



![](img/c7d05054dd51f060aace57ca88c70825_385.png)

![](img/c7d05054dd51f060aace57ca88c70825_386.png)

So in that way we can use very cheap hardware， you no longer need to have multipliers or others。

 you just need to have the I and pop count operations。

What is accuracy so if you only quantize the weight， leaving the activation to be 32 bit。

 you have very little drop of accuracy， if you have both the weight and activation to be by theized。

 actually a big drop of accuracy， but if you use the x that。

 thats no operation the accuracy is improved， but still very noticeable degradation of accuracy。



![](img/c7d05054dd51f060aace57ca88c70825_388.png)

![](img/c7d05054dd51f060aace57ca88c70825_389.png)

And if you want to see actually a detailed implementation。

 I actually did one Rpo open source report on the FPG only use these two operations。

 one is external operation， the other is the popcor operation。

 we synthesized that we wrote very long since that open source data can be deployed I stick FPG very small FPG it's open source on our GiHub。

 feel free to check it out。Okay， so since the accuracy is too low here。

 can we do better by using give it one more central。

 give it a zero right rather than minus one plus one， let's have a zero and make it turnern。

So turn weight networks， the weights are quantized to plus  one， minus1 and also zero。

 so we have a threshold above the threshold is positive between that and zero。

 although the threshold is minus okay。

![](img/c7d05054dd51f060aace57ca88c70825_391.png)

![](img/c7d05054dd51f060aace57ca88c70825_392.png)

And how do we calculate Dlta。 So there's empirical value。

 You find the absolute this distribution about the absolute value and then multiply by 0。7。

 So that's purely empirical。

![](img/c7d05054dd51f060aace57ca88c70825_394.png)

I use that to determine this threshold okay so given this is our familiar weight to matrix another component the threshold 16 entries we sum them up。



![](img/c7d05054dd51f060aace57ca88c70825_396.png)

![](img/c7d05054dd51f060aace57ca88c70825_397.png)

And then times this empirical 0。7， so delta is 0。73 to use that as the boundary， 2。

09 is above the boundary， so it's 0 to plus 1 minus 0。98 is below the boundary， so it's 0。 to minus1。



![](img/c7d05054dd51f060aace57ca88c70825_399.png)

Oh and so on， like this 0。09 is between the minus and positive boundary， so it's 052 to0。



![](img/c7d05054dd51f060aace57ca88c70825_401.png)

![](img/c7d05054dd51f060aace57ca88c70825_402.png)

Okay we can also find the scalingating factor， find the scalingating factor such that the sum of the absolute value remains the same between the left and the right。

 so here the scalingating factor is calculated as 1。

5 because this is the counting the number of9 zero elements and divided by the number of9 zero elements here。

 which is the 11。

![](img/c7d05054dd51f060aace57ca88c70825_404.png)

![](img/c7d05054dd51f060aace57ca88c70825_405.png)

![](img/c7d05054dd51f060aace57ca88c70825_406.png)

![](img/c7d05054dd51f060aace57ca88c70825_407.png)

In that way， we find the accuracy can be improved from 60 to 65。

 but still there's a gap with the fruit precision 69。



![](img/c7d05054dd51f060aace57ca88c70825_409.png)

So how do we further improve that？So rather than using the heuristic， you can also trim。

 rather than using this fixed scaling factor， we can use two treatable parameters the positive weight and also the negative weight to represent the positive and negative scales in the quantization。



![](img/c7d05054dd51f060aace57ca88c70825_411.png)

![](img/c7d05054dd51f060aace57ca88c70825_412.png)

![](img/c7d05054dd51f060aace57ca88c70825_413.png)

So this is the original food precision weight。You normalize them to be between minus one and positive one。

And then we find the threshold to be T， and we quantize them。

And then we scale them by two learnable scaling factors， W positive and W negative。

 so the final weight becomes minus w negative。

![](img/c7d05054dd51f060aace57ca88c70825_415.png)

0ero and positive， W positive。

![](img/c7d05054dd51f060aace57ca88c70825_417.png)

We can train this WN and WP to improve accuracy。

![](img/c7d05054dd51f060aace57ca88c70825_419.png)

And finally， the accuracy in TTQ further improved on top of the2 bit TWN。



![](img/c7d05054dd51f060aace57ca88c70825_421.png)

嗯。To further match the original full precision model。

So there's some tricks we can play for tunneling neural networks。So this is the big picture。

 we started with floating point weights， floating point arithmetic and then we talk about this K means quantization now we have integer weights plus of floating point codebook and still using floating point arithmetic。

And then we have this is probably the most popular linear quantization。

 we have integer weights and also integer arithmetic。

 we talk about a lot of techniques to find a granularity， to find a clipping eye etc。And finally。

 we have this binary andernary quant to have binary andernary weights using bitwise operations。

But here I want to point out that not necessarily the lower the better there should be a sweet spot and roughly fourbit is commonly a great sweet spot these days it might get lower in the future。

 but there's a tradeoff right so the aic intensity matters a lot for hardware efficiency so we have more compute。

You might be memory bounded， so if you when you're reducing the precision。

 the memory footprint decreases linearly。But the compute， the actual bottle expressiveness。

 the flop the。Bitwise operations actually reduces geographicalographicly。

 so the compute reduces faster than the memory okay the memory reduces slower and the memory is more expensive than the compute。

Therefore， the expensive stuff is reducing slower， the cheap stuff is reducing faster。

 so there is a imbalance you can diminish return after that so that's something to pay attention when you are reducing the precision。

And usually you don't want honor one design one design knob to the extreme。

 you want to utilize all the design knobs， for example， pruning quantization， distillation。

 neuro architecture search， all different techniques together。All right， lastly。

 just like we talk about the sensitivity analysis for pruning where different layers may have different sensitivity。

 some of them may have higher pruning ratio， some of them may have lower pruning ratio that's actually the similar case or quantation so here we have three layers they are all quantized for the weight and activation all quantized the same number of bits all eight bits。

We can also do mixed precision quantization okay， so for some of the layer which is more sensitive like this layer we use more precision。

 some of them is less sensitive like here and here we use fewer precision。



![](img/c7d05054dd51f060aace57ca88c70825_423.png)

![](img/c7d05054dd51f060aace57ca88c70825_424.png)

There are a lot of choices right from one bit to eight bit， you have eight choices。

 a weight and activation， you have 64 choices and you have n layers that 64 to the n number of design the design space has so many choices in4 to the N choices。

You can use different techniques to search in this large search space here in this paper called HIQ。

 how we' are aware automatic quantization with mixed precision。

 we use this actual critique model or our agent to search that。

We map it to the hardware and then we get the direct feedback。

 including the latency and the energy so that we can feedback the reward to the actual critique model and to give the next generation of action。

I think that's overcomp， but that's rule of thumb is that。You want to have different。

 sometimes you want to have different precision for each layer。

 some of them you can keep them in FP 32 or IPP 16 if it doesn't quite hurt to accuracy。

 like some of the very cheap layers。Or some of the memory bonding layers right for some compute bonding layers。

 you definitely want to have a lower precision and make sure they they are less sensitive to the accuracy。



![](img/c7d05054dd51f060aace57ca88c70825_426.png)

So this is a trade off between the lat versus the accuracy。This in the design space， right。

 So this is linear uniform quant versus using the hardware aware quant。

 You can see the hardware aware quant， given the same latency， it can have a higher accuracy。

 and given the same accuracy has a lower latency。

![](img/c7d05054dd51f060aace57ca88c70825_428.png)

![](img/c7d05054dd51f060aace57ca88c70825_429.png)

![](img/c7d05054dd51f060aace57ca88c70825_430.png)

And using that technique we can also optimize for different design design targets which we are going to cover in the neural architecture search section okay we want a model to have smaller model size to be faster to be energy efficient so using such automated approach hardware awareness。

 we can optimize not only for the model size but also for the latency and also for the energy。



![](img/c7d05054dd51f060aace57ca88c70825_432.png)

![](img/c7d05054dd51f060aace57ca88c70825_433.png)

All right， in summary， in this lecture we reviewed linear quantization and then we introduced post training quantization techniques。

 we introduced different granularity of quantization。

 the per tensor per channel group quantization in particular F4， and also MX4， data types。

And also we talk about how to determine the dynamic range， cliping the rounding techniques。

Next we talk about this quantization of where traininging techniques to use fine tuning to recover the accuracy。

 in particular this straight through estimator to use STE technique to fine tumor quantize model。

And then we introduce binary internal neural nets just use one bit or two bit to represent the width and activation。

 in particular use P count and ignore operation to deal with the binary quantize network。And finally。

 we talk about automatic mixed precision quantization。

All right so that's the end of this lecture in the next lecture we'll talk about neuro architecture research and lab two is released so we'll come to try it out。

 thank you。

![](img/c7d05054dd51f060aace57ca88c70825_435.png)