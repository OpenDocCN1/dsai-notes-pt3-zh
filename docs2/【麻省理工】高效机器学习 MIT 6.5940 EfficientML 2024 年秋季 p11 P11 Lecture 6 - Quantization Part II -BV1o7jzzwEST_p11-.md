# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p11 P11 Lecture 6 - Quantization Part II -BV1o7jzzwEST_p11-

All right， good afternoon everyone， let's get started。 So today we are going to learn about lecture6。

 the second part of the quantization lecture。 so in the previous lecture。

 we introduced the basic techniques of quantization。

 which is a super important technique both in the vision age and also in the large language model age quantization is very widely used。

 no matter if you want to deploy a neural network on the phone on the edge device or in the cloud。

 this is a very useful techniques very widely adopted in industry and actually a big shortage of engineers currently who can specialize in such techniques。

 so into this lecture we first review the linear quantization and also we'll cover two important concepts。

 one is posttrain quantization PTQ the other is the Q A。

 the quantization where training how do we fine tune the model so that you can recover the accuracy remember like improving we talk about pruning and how to fine tune improve the model。

To recover the accuracy and similar here inpoli well quantize it and then fine tune it。

 So that's Q A。And then we'll talk about binary and quantization to further push the quantization bit to lower bit to only one bit。

And finally we'll introduce automatic mixed precision quant。

 not every layer required the same number of bits， just like improvingrun。

 some of the layers are more sensitive， some of the layers are less sensitive。

 so we want to treat different layer differently to minimize the storage and maximize the efficiency in similar case for quant。

Okay so this is where we were left over since last Thursday。

 we talked about Kme first we started with the floating point weights， P32 for the weights。

 P 32 for the activations。And then the second part。

 we quantized the weight using the K means quantization。 Okay， so for example， here。

 this is our familiar matrix， we have a codebook and each entry with a store two bit or four bit a low precision index looking into the weight。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_1.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_2.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_3.png)

So that's the code book。So the computation is still arithmetic since we have de quantitized the weight into floating point。

 it saved storage say but doesn't save the computation。

 which is still useful for large language model inference batch size of one where is memory bonded not compute bonded and weight is the memory the weight is the memory bottleneck so very useful technique we're going to implement that in the lab two。

 hopefully you are all。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_5.png)

You will all downloaded， we will have them available in our website for lab too。Last lecture。

 we also introduce linear quantization， so both the weight and activations can be quantized to interior values。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_7.png)

And the computation is also done in integer arithmetic。 Okay， so we have a bias。

 we have a scalingkating factor。 We derive the equation for that。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_9.png)

So this is the K means quant， we have a cluster index， we have a centroid。

 and then we can fine tune the centroid。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_11.png)

We can see the accuracy is very well maintained， we can combine。

 we can even combine p and quantization to further push the model size to be a smaller。

When we are talking about linear quantization we introduced this zero point and the scalingkating factor okay。

 so for two bits， we can represent four numbers in four colors。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_13.png)

And this is the quant value minus the  zero point multiplied with a scalingating factor。

 and we can get a recovered P32 weight。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_15.png)

So remember how to calculate the scalingating factor。

 so scalingating factor basically maps the interior range to the floating point range okay so this is the interior range。

 this is a floating point range。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_17.png)

And this zero point maps z0 point in integer representation into zero in the floating point representation。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_19.png)

And we went through all the math to calculate in a quantized matrix matrix multiplication。

 so the single layer andLP， what is the breakdown about the computation so this is the majority of the computation then in no precision integer plus the bias。

 then this can be done by linear operation and also the shift operation and finally plus the integer add。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_21.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_22.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_23.png)

For convolution is very similar， we just replace matrix multiplication with convolution。

 majority of the job is done in the integer convolution。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_25.png)

Okay， so how should we get the optimal linear quantization parameters S and z。

 so we'll talk about quantization granularity， similar to pruning granularity where we can prune a single weight。

 we can prune a row of weight， we can prune the whole channel or a whole filter or the entire channel to the different granularities for pruning and similarly there are different granularities for quantization。

And then we are going to talk about dynamic range clipping。

 so you may have a pretty big dynamic range， how do we clip them。And finally， about rounding， like 1。

5， should we run it to one， should we run it to two， Should we s classicalically round it。

 We talk about rounding。So let's start withs start with quantization granularity。

So well first talk about per tensor quantization， you use one scaling factor to scale the whole tensor so this is percent tensor quantization followed by per channel quantization so for one channel。

 all the values in one channel share the same scalingk factor。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_27.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_28.png)

And which has more scalingating factors？

![](img/a0a5750243207e7cc2c5a05bc95edfa6_30.png)

For channel quantization we have if you have like seven channels。

 you will have seven scaling factors right here per tensor quantization。

 you have one scalingkating factor for the whole tensor okay。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_32.png)

And finally， group quant， this is very important for after blackwell architecture and India blackwell architecture。

 group quant is very useful for four bit or below， we introduce per vector quant and also the MX data type。

 the shared macro exponent data type。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_34.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_35.png)

Which is a very interesting data type in lower precision。Okay。

 so let's start with potential quantization， which is very widely used。These days。

So we have one scaling factor for the whole tensor。

 using a single scaling factor for the whole weight tensor that works quite well for large models。

 but for small models， people observe this degradation of accuracy。Why is the reason。

 what is the reason this potential quantization suffer from accuracy degradation？



![](img/a0a5750243207e7cc2c5a05bc95edfa6_37.png)

So if we plot。The channel index here is the range okay we can see the range actually differ a lot。

 some of the layers have a pretty big range， some of them have very little range if you use the same scalingkating factor for these diverse channels。

 of course you can now have a very good feeling for them all。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_39.png)

So the failure comes from the large difference in the ranges of the weight across different op channels some of them have pretty big outliers outliers and the weight values that has either a very big value or super small value compared with other values so that cause the you are wasting the dynamic range you observe very different behavior compared with other channels。

 so if you use the same scaling factor across all different channels。

 you cannot very well represent them。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_41.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_42.png)

So the solution is per channel on， we want to treat these different channels individually okay so that we can have a specialized scaling factor for each channel。

And how does that look like？So this is our familiar four by four matrix， input channel。

 output channel4 by four， will compare per channel quant versus the previous pertensor quantization。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_44.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_45.png)

Using persor quantization， we want to calculate first the scalingating factor okay in order to calculate the scalingating factor。

 we want to first have the R max， the power max， which is the max value。

 the value which have the max absolute value in the tensor， which is 2。12 in this case， R max is 2。

12。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_47.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_48.png)

And here we are using how many bits，2 bits， okay， two bits。

 so Q max equal to equal to1 okay so R max divided by cube  Q max using the equation we derived in the last lecture。

 we can find the scaling factor that map this integer range into that floating point range。

 so the scaling factor is 2。12。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_50.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_51.png)

So we have the scaling factor now we can quantize the matrix since we are using symmetry quantization。

 so 0 point is0。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_53.png)

So for example， 2。09 right here divided by 0。 2。12 that's approximately 0。

9 something is very close to1， so we quantize that to1 this is the minus 0。98 divided by 2。

12 the absolute value is smaller than 0。5 therefore we quantize to 0 okay but on and so on we can repeat that and quantize each value。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_55.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_56.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_57.png)

So this is the quantized answer。And if you can compare with the reconstructed tensor。

 we multiply each value with。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_59.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_60.png)

The scalingkating factoror， of course， the biasers is zero。

 so we can directly multiply to basically the reconstructed matrix。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_62.png)

And we can calculate a difference 2。28。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_64.png)

But now let's see， how does it look if we do the per channel on rather than treating the whole tensor。

 now we treat each each row， each channel individually。So let's first look at the first rule。

 what is Rx。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_66.png)

R minus is 2。09。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_68.png)

嗯。Therefore， the scaling factor is 2。09。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_70.png)

Second row R max is 2。12， scalingkating factor is 2。

12 and so on okay so different channels now we have different scalingk factor。

 which is the max value of the absolute value of that row。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_72.png)

And now let's see how do we quantize that？Now we are using different scaling factors for different roles okay and so that we can quantize it in this way for example。

 previously 2。09 if we are using persor quantization will divided by 2。

12 now we are dividediding that by 2。09 it's very close is actually y and then the second value divided by 2。

09 the absolute value is smaller than 0。5 therefore is rounded to 0。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_74.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_75.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_76.png)

And this is the reconstructed cancer。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_78.png)

Compared with the previous reconstructive tensor using per tensor quantization now the value is more diverse you have 2。

19 you have 2。12 1。92 etc。 And the reason is that we are using different scaling factor for different channel So actually the reconstruction error。

 the quant error is smaller than the per tensor quant。

 So we just want to use this very simple example to show you the the intuition where the per channel quantization can have a usually have a lower quant error compared with per tensor。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_80.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_81.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_82.png)

And in particular。What do you see which one is different？This is the quantized。

Tsor using per channel， this is quantized tensor using per tensor quantization。

 we observe this value is actually different。The rest of the value are all the same， 10，10， 1010。

 only of these values is minus1 minus is zero。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_84.png)

What was the reason for that？The sian factor， right， for example， if you look at this value， 1。03。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_86.png)

Using the peror quant， it will be divided by this getting factor divided by 2。12。

 the absolute value is smaller than the half。And therefore。

 it's quantile to 0 because the value is smaller than 0。5， surroundeded to 0 in this case。

But in this case。This values minus 1。03 will be divided by the scalingkating factor 1。92。

The absolute value is larger than 0。5 since 1。03 is larger than half of 1。

92 therefore is quantized to minus1 okay so that's the subtle difference you have a fine grained more fine grained scalingating factor compared with a single scalingating factor therefore the representation will be more accurate smaller quantization error using the perernal quantization and pertensor quantization。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_88.png)

So of course， there's a tradeoff。What's bad about perernal consation？

Right you need to store more values， more scalingating factors previously you need only one scalingkating factor now each channel you need one so there's no free lunch。

 always a tradeoff you need to store more scaling factors。Okay。

So let's continue if we want to go even lower precision。

We need more accurate representation and more flexibility， right？

So so we can actually shrink the group size rather than per tenor per channel can further reduce the group size。

 we call it group quant。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_90.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_91.png)

Okay， using group quantization will introduce the per vector quantization and also the MX data data type。

 Metro exponent data type， which is very new。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_93.png)

对。So that's first multi wave。Group font， so I mean released this blackwell generation GPU。

 which is super powerful if you compare the performance， so comparing the H100 here this is G 200。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_95.png)

Grace blackwell 200。This is running。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_97.png)

Another model has a very big。Imrovement compared with the H100。

 the Black wh architecture compared with the Hopper architecture。

There 7 x improvement and on the right time side， we see a new data time。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_99.png)

A new tens core called FP4 tens core Okay so these are what we are already familiar with like FP 16。

 B F 16， four and half。Pta flops， in8 tensor core， nine peta ops， FP8， FP6， nine pet flops， FP4。

 18 pet flops，2 x2 x the pixel input compared with FP8 innate tensor core。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_101.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_102.png)

Right。So blackwell GPU。Introduce this macrotensor scaling。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_104.png)

So that we can maintain the accuracy of FP4。Models。And in order to do that。

 that's basically what we are going to learn the group quant。

 having an even smaller group size to have a fine grained scalingkating factor so that you can have more accurate representation using lower precision。

So let's jump into that。We will first introduce the VS quant per vector a back per vector scaled quantization。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_106.png)

SoPreviously， we have a scaling factor for each tensor， the per tensor quantization。

And now we want to have a scaling factor for each sub vector。

 like this sub vector and this sub vectoror。Okay， so rather than r equal to scalingkating factor R cube minus z。

 now we have two levels of scalingkating factor， one global and one local。

 this global scalingkating factor is a 14 point core grain skating factor for the whole tensor。

We also have a integer per vectoror， a fine grain per vectoror for each vector， smaller granularity。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_108.png)

Sating fat。And we are going to multiply these two scalingating factors together。To scale a Q minus。

So that's achieving a balance between accuracy and the hardware efficiency by the fact that we can have a more expensive looking point scalingating factor。

But they are at a very close regularity。So let's try to understand this again。

Which is a more expensive scalingkating factor。The potentialsor one or the per vectoror is skin factor。

 which one is more expensive？This is F。16， those can be in the four or in eight。

So this is more expensive， right it FP1660， very expensive its getting effective。

 but we can have it as a very force granularity， the whole cancer have only one such expensive FP 16。

High precision gettingkating factor。Only having that is not enough。

 we compound that with the less expensive integer getting factor at finalr granular。Okay。

 so we have a less expensive scaling factor for only low low precision。

 but at a final gran just a couple of weights， we have one scaling factor。

 so that's a very smart way to have on both sides。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_110.png)

So in order to calculate the memory overhead， let's see how that work so we have a four bit quant with a weight we have four bit per vector scale。

 so this is four bit per vector scaling vector for every 16 element。

 so this is 16 element right here。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_112.png)

And we also， what is the effective bandwidth width？So each value is represented in four bits。

And then we also have a four bit scanning factor for every 16 elementss okay so the four bit scanning factor is amorized across 16 different elementss。

Plus， the original four bit。So it's altogether 4。2 to5。Four。 to5 bits。

 so that's the way to calculate of it。The overhead of two levels getting。So in that context。

 we can have multiple levels of scaling factor， okay。We can have the first level 0。

 level  one and continue different levels。 So let's see what we have learned so far。

 How does that fall into this specific picture。We introduce this per channel on， okay。

 we have a scaling factor about zero level zero scaling factor for the whole channel。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_114.png)

So the data type or the weight for the weight in red is into four。

 and then the group size I0 level0 group sizes per channel。

 the whole channel share the FP16 scaling factor so the effective bit width is four。

Since we have four here， I'm assuming we have many channels， thousands。

 tens of thousands of channels in large language models。This FP16 divided by 10。

000 that can be negligible， so you fact to bit with Israel4。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_116.png)

And in VS quant and in VS quant， the data type is also in four， so intramedia is four bit。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_118.png)

And then the L0 group size is 6 last me？Every 16 adamant we have a skating factor and the skating factor is on sign in4。

Okay and the next level ver size is per channel， the whole channel also share FP 16 scalingkating factor。

So what is the effect bandwidth with？The four bits and then another four bits being factor about shared by 16 values。

And this F 16 bit can be divided by tens of thousands that can be ignored。

 so we have two and four and a quarter that's the effective bandwidth width。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_120.png)

So now all comes to famous。MX4， MX6， and MX9 data type。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_122.png)

So I start with MX Mx4。So data type is啊 S one M two。Remember in the last lecture。

 we have one signing bit and we have two mentesa bit， what is missing here。TheExonent bit， right。

 where is the exponent bit？Im sure they are here。So we have one exponent bit that is shared by two values。

And we have one bit share by two letters。We also have an a bit scaling factor and this E8 only exponent。

 shared by 16 values。These are the two levels of scaling factor。

And now we can quickly calculate what is the effective precision bid with for an export form。

One bit for sine， two bit for the Manteza， three bits， right？

And then we have two bits shared by two values。Oh sorry， we have one bit right here， E1。

 one bit shared by two values， so that's half a bit。And finally。

 we have eight bits shared by 16 values， that's another half bit。

So three plus half plus half plus altogether together four bit， that's why we call the anx4。

We also have Mx6， which has one sign bit form and tisA bit plus's four other five bits altogether。

 one exponent shared by two values。And eight exponents share by 16 values or eight five by a half by a half plus six。

similar for the Mx9， Mx9， we have one sign bit， seven antiza bit。eight bit here。

 and then we have one bit of exponent shared by two values， group size of two。

 and then eight bit of exponent shared by one group size， which is 16。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_124.png)

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



![](img/a0a5750243207e7cc2c5a05bc95edfa6_126.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_127.png)

And what is that we maintain this R max and Rmin which is R max and Rmin across different iterations。

 so at t minus1， which is t this is t， so Rt basically equal to alpha Rt plus1 minus alpha rt minus1 okay we are using this discounting factor to discount the previous dynamic range。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_129.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_130.png)

With the current dynamic range。So the larger the alpha， the more we are using the riit dynamic range。

 okay， so we smooth the dynamic range by using alpha。What is the extreme case？

A尔pha equals one right if alpha equals one， we are not using any of the old dynamic range because this term becomes zero okay。

 so that's intuition。But that is only possible if you have access to the training process。

 if you're train the model by yourself。If the model is trained by somebody else。

 we don't have access to this whole training process， therefore it's very hard。

 it's not possible to estimate the dynamic rich in that way。But that is the most common case。

 sometimes we just download a model from hugging phase， we quantize them， we deploy them。

Then in that case， how do we get the dynamic rich？We want to maintain a collaboration batch collaboration data set and just use that collaborationlib set like a bunch of images or a bunch of text to calculate to estimate the dynamic range。

We can use the dynamic range for you in this collaborationlib set。

To represent to assume that is representative for the。Iput images or text from other sources。Okay。

 so by running the collaboration batch， we have two ways try to find the R max okay where we probably don't want to use the full RmX。

 so actually there is a trade off here。Say this is the distribution of the activation， okay？



![](img/a0a5750243207e7cc2c5a05bc95edfa6_132.png)

We can observe there is a very long tail。Of distribution， some of the values are super big。

 but you have a very small a small amount of big values。

 very small amount of these very negative values。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_134.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_135.png)

So if you set the me and max to be like here versus here。You have a big waste。

 You are wasting lots of the representation。Because。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_137.png)

You have only a few， very few values in the extreme corners。

So assuming we want to push the mean and max to be somewhere here where there are at least some weights because if you squeeze it closer the distance between each quantization boundary will be will be smaller and the representation for these values in the middle these values in the middle will be more accurate if the quantization distance between adjacent bucket will be closer right so there is a tradeoff。

 the mean and max you don't want it to be like the exact max mean value。

 you don't want it to be a very small but there might be a sweet spot。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_139.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_140.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_141.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_142.png)

So if it is a laplashian distribution， we have closed form solution to find a sweet spot and for two bit。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_144.png)

That it's 2。83 B for three business that's 8。89B。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_146.png)

Okay， so that B is the Laha parameter can be estimated from the collaborationlib input distribution。

But this is a very rare case， very rarely the input follow this uppling distribution。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_148.png)

So what should we do if we。Doesn't it doesn't follow the La passion distribution。

So a very widely used technique is to use the KL divergence method to collarate their range。

So we want to minimize the loss of information okay。

 since the interest models encode the same information as the original proteinin point model。

So we want to find the dynamic range by minimizing。Mimizing the k divergence。

 so this is the equation for these two distributions， P and Q。One is before quantization。

 One is after quantization。And we find the mean and max value such that it can minimize this kL divergence。

Let's give some intuition。Say this is the distribution， this is distribution of activation value。

 this absolute value ranges from zero all the way to 400， some of them might be even 480。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_150.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_151.png)

But most of the value okay so this is the normalized number of counts so loss value is actually below at 40 and then has this long tail。

If we decide to set the max value to be here， what happens？So all the values above。

 all the values in this long tail will be clipped。To this value roughly 50。

 roughly 40 or 50 right all the value above 50 will be clipped to 50。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_153.png)

And the count will be the sum of all these values count will be a this is the count okay。

 so this is before and after the finding the max value using the minimizing the k divergence。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_155.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_156.png)

What happens if you have a larger max value？So we you will have a a shorter tail on the right hand side。

And the value near the quantization near the max value will be more accurate， however。

The range will be larger， therefore these values。These values。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_158.png)

We actually have a lot of them will be less accurate because the dynamic range is now larger and quantization error is now larger。

It can be too small， it can be not to be too large。

 The best way to calculate that is by minimizing this chaos divergence。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_160.png)

And let's see some other examples。So Alex now at present 152， GoogleNet， GoogleNe。

 so this is the clipping， the optimal clipping range。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_162.png)

Discovered for these different models， Okay， none of them is。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_164.png)

The the largest value， they are not using the largest value。This is the largest value。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_166.png)

But they are using somewhere smaller than the largest value which。嗯。Clelip。

The largest value to be the quantization max。So this figure further illustrates the intuition。

Between why we needed such kind of clipping rather than using the max value Okay。

 so if we have such a distribution， such a distribution very long tail。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_168.png)

The long tail， if you choose the me and max， according to the real。Mean， this is negative 0。8。

 this is top positive 0。8 if we choose the max and mean this way。

 this will be your quantization range。And you can see the quantization noise is pretty large because the adjacent quantization cent。

 the distance is pretty far from each other。And in particular， you have very low density data。

 just a few of them is in this big range。Whereasus we can clip it okay this is the new mirror and this is the new la and this is the new dynamic rid。

And distance between adjacent adjacent central becomes much。Smaller， right。

 much smaller compared with Israel， so the quantization noise becomes much smallerer。

And all these videos will be click to hear。still okay， why， because we just have very little。

 very few of them in this range， very few of them in this range。

 so it's fine to click them to the desired max we want。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_170.png)

And this is actually a quite helpful technique very widely used。

So on the right hand side is's showing the animation。This work is calledoccta from NVdia。

 it can automatically find the optimal ving range。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_172.png)

On the left hand side is showing that the means error is conx and you be the cliping scr cannot be too small or too large。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_174.png)

You feel too small， you waste a lot of the， you feel too large。

 you waste a lot of the dynamic bridge。It are too small。

 Then many values will be clicked to the boundary。 So there is a sweet， It's complex。

 There is a sweet spot in the middle。And you can use this technique to find the optimal vaping rid。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_176.png)

And after applying occta， see the accuracy can be very well maintained compared pair with by P32 accuracy。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_178.png)

哎。😊，So finding the granularity very important and then cliping is very important。Okay。

 any questions so far。Yeah。I their emergency。With the student large and。我。

the value is the determined if you have four bits， you have 16 values。说。不是。嗯。One type， yes， right。

All right， no question， let's take a quick break and come back in five minutes to continue discussion about wronging。

All right， welcome back。Let me turn on the mic so you can hear me， all right。

So let's jump into the third part of quantation about Ry， okay？



![](img/a0a5750243207e7cc2c5a05bc95edfa6_180.png)

So this is our conventional wisdom if you have a vector， 0。3， 0。5 0。7， 0。2。

 you want to run it to like 0，1，1，  zero okay， so this round to the nearest。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_182.png)

But contradictory to our conventional wisdom running to near is actually not optimal。

So weights are correlated with each other， the best running for each weight to the nearest is not the running the best round for the whole answer okay so sometimes we want to want some want to have some randomness。

 for example， the same answer sometimes like 0。5。If you run into zero， if you run into one。

 not necessarily running into one might be the option， sometimes we can even run into zero。诶。😊。

So such stochastic running usually helps during the quantization process。

So instead of running into the near， we want to choose near running down or rather running up and sto to get best reconstruction。

 we can also learn a delta between zero and one。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_184.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_185.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_186.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_187.png)

We added to the original weight and then we run it to the nearest。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_189.png)

For example， rather than just finding the newest。Runundning into the nearest。

 we can add a value this value would be learned when we pass it through a function H is a function to map V to the range between0 and1 between0 and1 this is a possible solution using such rectified sigmoid so the Hv is between0 and1。

 we added it to W and then we run it to the nearest so that we can learn a tensor with the same dimension so this V is a random variable of the same same shape。

 same dimension。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_191.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_192.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_193.png)

Flllowed by a regularization term encouraging the HV to be binary between either zero or one so this is called an run very popular paper helping recover the accuracy。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_195.png)

So just intuition is that don't just run to nearest， usually you can apply some stochastic。

To add some randomly during the writinging process usually helps。

So let's do a quick summary about linear quantization what we have learned so far。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_197.png)

We learn about zero points。Scaling granularity per tensor。

 qua grain per channel or group quant after below four bits。

 group quant is getting super popular and super important， Mx4， Mx6， IPP4， etc ce。Range weing。

 you can use different techniques to find the optimal range to clip it and then run the rounding techniques。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_199.png)

So by applying these techniques。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_201.png)

For the weight for the activation， we can actually very well maintain the accuracy for a bunch of models like Googlenet。

 ResNe。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_203.png)

However， some of the smaller models like mobilenet， they still suffer。

Very heavy accuracy degradation， even after applying all the techniques we have learned so far。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_205.png)

Like 10%， 2% degradation of accuracy， which is quite bad。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_207.png)

So what should we do， so let's talk about。Find engineering techniques to recover the accuracy for these models。

 So let's talk about Q A， the quant of wire training。

A very simple technique was already introduced in the last lecture about using pay means quant where we have a code book after we get the gradient which is of the same size of as the weight。

 so this is the weight because the gradient， the dimension are exactly the same。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_209.png)

With sum the gradients corresponding to the same color， the same centroid。

 sum the mop multiplied by the verin rate subtracted from the original centroid to get a fine tune in the centuryroid。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_211.png)

So that's very simple for the K means context。Ne network where we are just updating the centralroid。

 updating the code book。Actually。呃It's more。Get more complicated if they're doing linear quantization。

Okay， so in the linear quant， the weight and activations are all low precision。

 okay in or in the4 or I4。In that case， during the treating process。

 we actually maintain a full precision weight in the back。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_213.png)

Okay， maintainin a full precision， not4 bit， not 8 bit， but 32 bit or IP 16 or 16 bit。

 a full precision copy of the weight。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_215.png)

In the back through all the tweeting。So that we can。Accumulate very small gradients。

 very small changes。Aumulate that in the weight without， without loss of precision。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_217.png)

And once the model is fully trained， this F 32， this full precision weight can be thrown away。

 we only keep the quantized weight deployment time。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_219.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_220.png)

So this is the layer minus one layer n layer n plus one， these are the activations。

 these are the weights， the weight will be quantized， this is the full precision weight in the back。

 quantized， bid it to calculate layer n and count of being redlu and then get the output and for the next layer。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_222.png)

For the backward process， we update this full precision weight so that we don't lose any precision。

And remember during the activation here， we calculate the activation and we should quantize that activation so that the boundary of the output。

 the value is quantized。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_224.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_225.png)

So this whole process is called simulated quantization or fake quantization during the training process。

Because the weight is quant to QW， but is still using a 32 bit floating point register to represent that value。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_227.png)

Although the value itself is context， but we are still using a broken point number to for it。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_229.png)

So we trained the model taking quantization into consideration by adding these two quantization nodes。

 compute nodes， one is quantization quantizing the weight。

 the other is quantizing the activation to simulate this quantization process。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_231.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_232.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_233.png)

So we have QW here， we have QY here。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_235.png)

对。So forward process is very simple if  QW have QY， what about the backward process。

 how does the grid flow to the weight？Because the quantization this is the basically quantization activation if you think about it as an activation function okay so below0 and0。

5 is all0 between 0 and5 to 1。5  one between 1。5 and 2。

5 there two right so it's actually a step function。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_237.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_238.png)

So the quantization makes the input value to be discrete， okay， the output is dereitized。

What's the problem here for the gradient？

![](img/a0a5750243207e7cc2c5a05bc95edfa6_240.png)

The gradient is all zeros。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_242.png)

Right gradient become zero， then you can learn nothing if you have a zero gradient。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_244.png)

So actually we are using a technique called straight through estimator， STE。

 straight through estimator。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_246.png)

We simply pass the gradient through the quantization as if it has never been quantized if it is just an identity function。

 so the gradient to the weight is the same as the gradient to the quantized weight the gradient of the quantized weight versus the gradient of the weight to be exactly the same。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_248.png)

So this is the quantization compute node。This is quantas W。

 this is w okay to treat the gradient between this purple line and this purple line to be exactly the same as if it is just identity function in this blue quantization node。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_250.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_251.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_252.png)

And what happens？becomeses a a function。 are making the green calculation much easier。

So this is the full full picture， okay， so the purple line is back with us。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_254.png)

During the back of the pass。Before and after the quantnotization node。

 the GY is exactly the gradient of the quantized y and here the GW is exactly the gradient of the quantized W。

 as see this blue quantization node is an identity function so we can use this straight through estimation technique。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_256.png)

To estimate the gradient for the floating point weight。And floating point activationav。

By using quantization of where training， so here are the quantization of where training results here are without the quantization of where training。

 we can compare the accuracy drastically improved a lot， so peror quantization improved from 0。

1% almost 19 to 70%。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_258.png)

The channel con originally is better， it's like 59% now becomes 70% so this con where're training really plays quite a helpful role in the accuracy recovery Some of the models like NA mobile here。

 the original accuracy already is already pretty good。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_260.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_261.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_262.png)

So the quant of where training gives a marginal improvement。But for large language models。

 which is very hard to pre， it will be the desired scenario will be like this and you're just using post training quantization without any fine tuning the accuracy should be very good we'll cover that in the large language models section。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_264.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_265.png)

In details。Okay， so that concludes the linear quantation part。Can we go even smaller。

Will introduce binary internal quant。 Just use 01， maybe minus-1。

To represent the weight and activations。 And let's see what kind of magic we're having here about binaryary and turnernary quantization to further push the quantization precision to only one bit。

So let's see an example， so wait。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_267.png)

AMo product with activation eight times 5 minus-3。 So this is the weight， this is activation。

We assume the boundary is 1x， computation is 1x， each operation is a plus add and also and multiply and accumulate。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_269.png)

We can quantize the weight to be binary okay rather than eight minus three，5 minus one。

 we have one minus one，1 minus one， so we binaryized the weight if it is positive then it's one。

 if it's negative， then it's minus one。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_271.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_272.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_273.png)

So we no longer have any modifications， but everything is plus or minus。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_275.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_276.png)

So the memory32 times smaller for the weight， previously you need 32 bit。

 now you need only one bit plus one minute。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_278.png)

And the computation is roughly2 x nice flops because previously you have。Mulipplication。

 now you have no multiplication， only add。找好的维度的。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_280.png)

One way is to deterministically finalize that if the way is positive， it's positive one。

 if it's negative， then it's negative one。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_282.png)

That's basically a sine function， very straightforward。

 but you can imagine this results in a big degradation of accuracy。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_284.png)

Just now we mentioned adding some randomness usually helps with quantization so we can do stochastic mineralization。

 like in this equation here， if it's smaller than minus1 is deterministically to be zero。

 if it is above one is of first one， but between minus one positive one。

 sometimes it can be minus one， sometimes it can be quantized to plus one， if it is zero。

 you have half probability to be quantized to to0 it have half of the probability to be quantized to positive。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_286.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_287.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_288.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_289.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_290.png)

And can have a linear interpolation between minus one and plus one。

But it's harder to implement since we need a hardware hardware random number generator and hardware that's not straightforward。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_292.png)

So let let's see what happens to our familiar matrix。

 this four by four matrix we use 90 times if we binaryize them to one bit just using the sign before and after the accuracygraded by a big margin。

 degraded by 21%。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_294.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_295.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_296.png)

And the quantnotation arrow is 9。28， really big quantnotation  error。

And what happens if we do some trick， okay， so we can have a scalingkating factor。

 and we have a floating point scalingkating factor， which is r in this case。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_298.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_299.png)

So to make sure the sum of all the values， the absolute value。

 sum of the absolute values of all the elements stays the same。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_301.png)

So here， the sating cancer will be calculated by the O1 norm， which is the sum of the absolutebaial。

Deivided by n since every entry， the absolute value is one， so we have n elements。

 16 elements in this case。Then we can just calculate the alpha， actually it to be 1。05。

which is equal to the what norm divided by 16 values？And if we multiply this sk factor。

 we can see the quantization error slightly decreased。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_303.png)

And the accuracy deelta actually improved a lot， actually becomes 0。2%。positive is 0。2%。

 which is very interesting。So just now we quantized only a binaryize only the weight。

 now we want to bindize not only the weight， but also the activation。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_305.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_306.png)

はい。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_308.png)

So let's see what happens if both the weight and activation is finalized。

 so we have one times 1 plus1，1 times minus1 minus1， minus1 minus1 plus one， okay。

 so it's the choose table。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_310.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_311.png)

Let's see another operation， which which is the export operation Okay， X operation if this a。

Both values are the same， 11，00， then the output is one。If the two inputs are different， 10，01。

 then the output is 0， so that's the x operation you might have learned in 6。191。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_313.png)

What's the relationship between finalized weight and activation versus the actual operation？

Actually they are heavily correlated， so if calculate if you sum them up for the external results。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_315.png)

Okay so this is one， I ignore with  one， minus this is0， I ignore with one， one， I ignore with zero。

 zero， x norm with one。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_317.png)

You can get one plus 0 plus 0 plus 0 one。So now even doing this actually doesn't help。

It's minus minus2 versus1， they're not the same。So what's the relationship。

 how do we use external operation to implement the binaryized weight and activation？

Since I ignore it's just solely simple to implement in hardware。So let's see， how do we match them？

So' assuming everything is minus1， okay， so since the smallest value is minus one。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_319.png)

Okay if we have everything is minus1， if everything with some the mo， that's actually minus four。And。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_321.png)

But here， if we modify the sum of the X results with two， okay so this is the sum of the X result。

 which is one times2 times2 can be very efficiently implemented by shift to the left for one bit。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_323.png)

I think minus four plus the count times 2 plus minus2， that's exactly the value on the left。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_325.png)

Okay， so take another look and assume everything is zero， okay， we just count't the number of ones。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_327.png)

In this case。Because only if both values are the same then it's one otherwise is zero8 it is zero iss corresponding to everything on the left is minus one so that's why we assume if everything is minus one and add the difference the difference how do we calculate the difference is the number of ones in this case times two since the difference between minus one and plus one is two so we have one more you add two you have two you have two more you add four you have three more you add six okay so you just count how many values are one and then times two。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_329.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_330.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_331.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_332.png)

And they can match the left on the right hand side。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_334.png)

So put it in math if equal2 minus n n is the number of elements， in this case， we have four elements。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_336.png)

1，2， three， four， minus n times plus two times。The sum of Disnora are Christian。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_338.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_339.png)

So minus minus four， since we have four entries here， we calculate the x sum the mo。

 sum the mo to be 1 times2 and add minus4， so that's minus2。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_341.png)

So we can use this very simple XO operation to calculate the scenario where both weight and activations are minorized。

And this count operation has a name is called P count in return the number once。In this array。

 maybe the array is binaryry either one or zero， pop count operation is basically applying on this binaryry array count the number of ys just return the number of one it's called pop count。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_343.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_344.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_345.png)

So using the pop count function， the final result would be minus n plus pop counts shifted by one since shipped by one is basically multiplying by two。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_347.png)

Okay using that we can easily calculate the dot product very easily。

 so for example here this is the original floating point on quantized weight and activation。

 this is quantized weight and activation， we just do the explore operation and then shifts it by one。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_349.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_350.png)

And then plus four， so that's the result。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_352.png)

So the operation rather than multiplication and add now it becomes In and pop cut。

 both are very cheap to be implementing in hardware the memory is 32 times smaller since both the weight and activation becomes one bit。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_354.png)

The computation is roughly 58 times less， why is that that's roughly the risk roughly the complexity between explore popcorn operation versus Mac operation。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_356.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_357.png)

So in that way we can use very cheap other， you no longer need to have multipliers or others。

 you just need to have the INR and pop count operations。

What is accuracy so if you only quantize the weight， leaving the activation to be 32 bit。

 you have very little drop of accuracy， if you have both the weight and activation to be by theized。

 actually a big drop of accuracy， but if you use the x that。

 thats no operation the accuracy is improved， but still very noticeable degradation of accuracy。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_359.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_360.png)

And if you want to see actually a detailed implementation。

 I actually did one Rpo open source reportport on the FPG only use these two operations。

 one is external operation， the other is the popcor operation。

 which synthesized that we wrote very long we since that open source that can be deployed I stick FPG very small FPG it's open source on our GiHub。

 feel free to check it out。Okay， so since the accuracy is too low here。

 can we do better by using give it one more centralroid， give it a zero right。

 rather than minus one plus one， let's have a zero and make it turnern。So turn weight networks。

 the weights are quantized to plus 1， minus1 and also zero。

 so we have a threshold above the threshold is positive between that and zero。

 although the threshold is minus okay。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_362.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_363.png)

And how do we calculate delta。 So there's empirical value。

 You find the absolute this distribution about the absolute value， and then multiply by 0。

7 the purely empirical。I use that to determine this threshold okay so given this is our familiar weight to matrix and then component threshold 16 entries with sum the model。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_365.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_366.png)

And then times this empirical 0。7， so delta is 0。73 to use that as the boundary 2。

09 is above the boundary so it's 0 to plus 1 minus 0。98 is below the boundary， so it's 0。 to minus1。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_368.png)

All right so on， like this 0。09 is between the minus and positive boundary， so it's 052 to0。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_370.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_371.png)

Okay we can also find the scalingating factor， find the scalingating factor such that the sum of the absolute value remains the same between the left and the right。

 so here the scalingating factor is calculated as 1。

5 because this is the counting the number of9 zero elements and divided by the number of9 zero elements here。

 which is the 11。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_373.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_374.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_375.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_376.png)

In that way， we find the accuracy can be improved from 60 to 65。

 but still there's a gap with the fruit precision 69。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_378.png)

So how do we further improve that？So rather than using the heuristic， we can also trim。

 rather than using this fixed scaling factor， we can use two treatable parameters the positive weight and also the negative weight to represent the positive and negative scales in the quantization。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_380.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_381.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_382.png)

So this is the original food precision weight。You normalize them to be between minus one and positive one。

And then we find the threshold to be T， and we quantize them。

And then we scale them by two learnable scaling factors， W positive and W negative。

 so the final weight becomes minus w negative。Zero and positive， W positive。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_384.png)

We can train this WN and WP to improve accuracy。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_386.png)

And finally， the accuracy in TDQ further improved on top of the2 bit TWN。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_388.png)

To further match the original full precision model。

So there's some tricks we can play for tunneling neural networks。So this is the big picture。

 we started with floating point weights， floating point arithmetic and then we talk about this K means quantization。

 now we have integer weights plus of floating point codebook and still using floating point arithmetic。

And then we have this is probably the most popular linear quantization。

 we have integer weights and also integer arithmetic。

 we talk about a lot of techniques to find a granularity， to find a clipping eye etc。And finally。

 we have this binary andernary quant to have binary andernary weights using bitwise operations。

But here I want to point out that not necessarily the lower the better there should be a sweet spot and roughly fourbit is commonly a great sweet spot these days it might get lower in the future。

 but there's a tradeoff right so the aic intensity matters a lot for hardware efficiency so it have more compute。

You might be memory bounded， so if you when you're reducing the precision。

 the memory footprint decreases linearly。By the compute， the actual bottle expressiveness。

 the flop the。Bitwise operations actually reduces projectically。

 so the compute reduces faster than the memory， okay the memory reduces slower and the memory is more expensive than the compute。

Therefore， the expensive stuff is reducing slower， the cheap stuff is reducing faster。

 so there is a imbalance you can diminish return after that so that's something to pay attention when you are reducing the precision。

And usually you don't want honor one design one design knob to the extreme。

 you want to utilize all the design knobs， for example， pruning quantization， distillation。

 neuro architectural search， all different techniques together。All right， lastly。

 just like we talk about the sensitivity analysis for pruning where different layers may have different sensitivity。

 some of them may have higher pruning ratio， some of them may have lower pruning ratio that's actually the similar case or quantization so here we have three layers they are all quantized for the weight and activation all quantized the same number of bits all eight bits。

We can also do mixed precision quantization okay so for some of the layer which is more sensitive like this layer we use more precision。

 some of them is less sensitive like here and here we use fewer precision。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_390.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_391.png)

There are a lot of choices right from one bit to eight bit， you have eight choices。

 a weight and activation， you have 64 choices and you have n layers that 64 to the n number of design the design space has so many choices in4 to the N choices。

You can use different techniques to search in this large search space here in this paper called HIQ。

 how we' are aware automatic quantization with mixed precision。

 we use this a critique model or our agent to search that。

We map it to the hardware and then we get the direct feedback。

 including the latency and the energy so that we can feedback the reward to the actual critique model and to give the next generation of action。

I think that's overcomplic， but that's rule of thumb is that。You want to have different。

 sometimes you want to have different precision for each layer。

 some of them you can keep them in FP 32 or IPP 16 if it doesn't quite hurt to accuracy。

 like some of the very cheap layers。Or some of the memory bonding layers right for some compute bonding layers。

 you definitely want to have a lower precision and make sure they they are less sensitive to the accuracy。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_393.png)

So this is a trade off between the latency versus the accuracy。In the design space， right。

 so this is linear uniform quant versus using the hardware aware quant。

 you can see the hardware aware quant given the same latency。

 it can have a higher accuracy and given the same accuracy has a lower latency。



![](img/a0a5750243207e7cc2c5a05bc95edfa6_395.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_396.png)

![](img/a0a5750243207e7cc2c5a05bc95edfa6_397.png)

And using that technique we can also optimize for different design and design targets which we are going to cover in the neural architecture search section okay we want a model to have smaller model size to be faster to be energy efficient so using such an automated approach hardware awareness。

 we can optimize not only for the model size but also for the latency and also for the energy。

All right， in summary， in this lecture we reviewed linear quantization and then we introduced post training quantization techniques。

 we introduced different granularity of quantization。

 the per tensor per channel group quantization in particular FP4， and also MX4， data types。

And also we talk about how to determine the dynamic range， clipping the rounding techniques。

Next we talk about this quantization of where traininging techniques to use fine tuning to recover the accuracy。

 in particular this straight through estimator to use STE technique to fine tumor quantize model。

And then we introduce binary internal neural nets， just use one bit or two bit to represent the width and activation。

 in particular， use pop count and X operation to deal with the binary quantize network。And finally。

 we talk about automatic mixed precision quantization。

All right so that's the end of this lecture in the next lecture we'll talk about neuroarch research and lab two is released so we'll come to try it out。

 thank you。

![](img/a0a5750243207e7cc2c5a05bc95edfa6_399.png)