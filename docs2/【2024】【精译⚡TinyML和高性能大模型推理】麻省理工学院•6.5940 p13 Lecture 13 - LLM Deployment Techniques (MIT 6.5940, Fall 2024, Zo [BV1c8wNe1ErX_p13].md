# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p13 Lecture 13 - LLM Deployment Techniques (MIT 6.5940, Fall 2024, Zo [BV1c8wNe1ErX_p13]

Okay let's get started so lab three is due lap four will be out today so today we are going to talk about large language model efficient deployment techniques one of the algorithm we learn in all AWQ will be part of the homework so we' also be helping you do deploy a large language model on our laptop for La five so today's lecture will be super interesting so let's get started with ourOM deployment techniques。

So here are the three major chapters we're going to talk about today。

 starting with quantization with eight bit weight activation quantization。

 and then weight only quantization， and then we combine the best of both world to talk about Q serve。

 quantizing both weight and activation total precision。

Then we are going to talk about applying sparsity to large language models， weight sparsity。

 contextual sparsity， attention， sparsity。And finally system support for large language model inference so inference these days is getting super important if you see G 401 the inference time skating is getting super crucial so increasing the inference efficiency is a very important topic for efficientLM so here we'll talk about metrics for Im'm serving I'm using page attention flash attention speculative decocoding。

And also you fashion techniques。He that's agenda let's start with the first part which is quant today's lecture is pretty dense so let's move on quickly。

So a brief overview of quantization， we briefly chatted about quantization in lecture five and are also lecture six。

 so we can cast a floating point number into a integer from using 6 bit to using only four bit。嗯。

So lots of the quantization techniques， including what we learned in lecture four and lecture five。



![](img/badc5f90e9fe4250bd201b5025a023b0_1.png)

Does not quite apply to large language models， so if we see when the model science gets pretty large from 1。

3 billion to 6。7 billion 13 billion 175 billion。The accuracy for the eight bit quantization is going to drop okay。

 so it only works for those small small models， but with a large when the model gets much bigger。



![](img/badc5f90e9fe4250bd201b5025a023b0_3.png)

Those algorithms that traditionally work for scenes does not work for large language models。

What is the reason why we cannot apply previous quantization techniques to large language models？



![](img/badc5f90e9fe4250bd201b5025a023b0_5.png)

Actually， the reason is due to these outfires， it activations in certain channels pretty big。

 super big values that are going to destroy the accuracy after quant。



![](img/badc5f90e9fe4250bd201b5025a023b0_7.png)

So we visualized the activation value across different channels。

 so here we have 5000 channels and this is across different tokens here we have 300 tokens。



![](img/badc5f90e9fe4250bd201b5025a023b0_9.png)

We can see three outfireer channels， okay， so across different tokens。

 their activation value is consistently pretty large。



![](img/badc5f90e9fe4250bd201b5025a023b0_11.png)

Across different tokens。

![](img/badc5f90e9fe4250bd201b5025a023b0_13.png)

And you can see the value on the y axis， they are pretty big。

 much bigger than the remaining activations。

![](img/badc5f90e9fe4250bd201b5025a023b0_15.png)

So what happens if we quantize this cancer， if we quantize this cancer？



![](img/badc5f90e9fe4250bd201b5025a023b0_17.png)

So all the values in the blue area will be climbed to zero。



![](img/badc5f90e9fe4250bd201b5025a023b0_19.png)

Since these outlier channels are wasting the dynamic range。

So all these new values will be clamped to zero。So that's the new problem。

 that's the quantization difficulty for large language model。



![](img/badc5f90e9fe4250bd201b5025a023b0_21.png)

系。But the weight， okay the weight is actually pretty flat。

 you can see it's all blue so the weight is very easy to quantize and the activation is super hard。

 super hard to quant。

![](img/badc5f90e9fe4250bd201b5025a023b0_23.png)

So how do we deal with that， How do we mingle the weights and activations and balance the quant difficulty。

Can we migrate deep people？Actually， yes， because the matrix multiplication is linear。

 you can multiply this channel by 0。1， multiply the corresponding which channel by 10。



![](img/badc5f90e9fe4250bd201b5025a023b0_25.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_26.png)

What happens So So 0。1 times 10 equal to one by one。

 It's linear so we can scale and push the quantization difficulty between weight and activation。

 the result will be still mathematically equal。So here we migrate the quantization typically by shrinking the activation。

 increasing the weight。So now the activation becomes easier to quantize on the way it becomes harder。

 but still relatively easy to quantize， you see some of the channels are getting larger due to we are multiplying the weight with a larger number。

 multiplying the activation with a smaller number。That's like 1 times 100 equal to 10 by 10 and use that to equalize between to smooth between the weight and activations。

And we are effectively migrating this quant typically from the activation to the weight。

 and the result is mathematical equal。So a let's see an example to digest this algorithm。



![](img/badc5f90e9fe4250bd201b5025a023b0_28.png)

So this is before。This is after so before smooth pond。This is the original activation。

 this is the original weight， weight W activation X。X will be multipl with W， the input has two。

On two sequences， okay， two sequences， each one has four。

it has each one has four hidden dimensions and here the W also has four input dimension and three output dimension and so this color will be multiplied with this column initially。



![](img/badc5f90e9fe4250bd201b5025a023b0_30.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_31.png)

Unfortunately， previously， initially we have these two outlier channels， 160 and8。

6 and nine in the activations， we color them the。Red color corresponds to the bigger value。

 so the white color corresponding to smaller value。



![](img/badc5f90e9fe4250bd201b5025a023b0_33.png)

But they can see the weight the color is pretty wide， there's no outlier here。



![](img/badc5f90e9fe4250bd201b5025a023b0_35.png)

So how do we aggregate the quant deeply from a to weight。

 so let's proceed the result okay so this is after a small part。These two outlier channels。

16 and eight。Now become four and two， six and nine become two and three。

 so previously 16 will be multiplied with one。Now four will be multiplied with four。

 so 16 times one equal to four times four， so the result is the same。Similarly。

 previously say eight times1 now is two times four it's still the same okay。

 so after you can see after this transformation。

![](img/badc5f90e9fe4250bd201b5025a023b0_37.png)

The result of the weight multiplied activation doesn't change。So how do we achieve that？



![](img/badc5f90e9fe4250bd201b5025a023b0_39.png)

Let's see the error。So let's first find the absolute value。

 the max of the absolute value of each column in the first column。

The absolute value max is two second column， the max of the absolute value is 16 third column。

 the max of that absolute value is two。Both volume is nine。

 so we get a max of the absolute value of the activations。

For the weights we do it in another direction for the first row， we get the max absolute value two。

 second row， third row and the fourth row， so we get two vector， one is the max of x absolute value。

 the other is the max of the absolute value of W。

![](img/badc5f90e9fe4250bd201b5025a023b0_41.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_42.png)

And we flip them here， so this is a max X， this is a max stop。

What we do is we divide x by W and find the square root of that。16 divided by one square root有点错。

N divided by one square root look at three， so we'll get a scaling factor 1，4，1，3 in this case。



![](img/badc5f90e9fe4250bd201b5025a023b0_44.png)

So this is during the collaborationlib stage we one a few batch of sentences。

And we collect these statistics， collect this activation information。



![](img/badc5f90e9fe4250bd201b5025a023b0_46.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_47.png)

By the scaling factors really division between the weight and activation is square root of that we find this scaling factor。



![](img/badc5f90e9fe4250bd201b5025a023b0_49.png)

So the next step will apply the scalingating factor so by dividing x with the scalingkating factor。

And the multiifier W with the scanning factor，Same scalingating factor。

 one is divided by that one is multiplying with that。

 so mathematicalologically it's the same okay so it's x。Divided by S， W model divided by S。

These as will cancel each other。So let's soon， what do we get？So x divided by s at to y。

We get this output。They scaled the output channel。By S。



![](img/badc5f90e9fe4250bd201b5025a023b0_51.png)

So now it's smoother than before right previously we have 16， which is a big outlier now can four。

 which is much smoother。

![](img/badc5f90e9fe4250bd201b5025a023b0_53.png)

In W， your row Y is multiply with this skin effect， so it becomes this matrix。



![](img/badc5f90e9fe4250bd201b5025a023b0_55.png)

And in the end， we have the transformed。X a and transformed W。After such transformation。

The weight matrix activation matrix are becoming both easier to quant so let's see this is the final result and in first time there's no skating and skating can been folded into the previous layer and compile time okay so at inference time we are just calculating the modificationplication of these two matrices the scaled x and the scaled value。



![](img/badc5f90e9fe4250bd201b5025a023b0_57.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_58.png)

And they're all in integer without any runtime overhead。And the outlier problem is also solved。

In this space。Since we are pushing the quantization difficulty from activation to the weight。

 there is a strength， how much do we push do we push all the difficulty to weight。



![](img/badc5f90e9fe4250bd201b5025a023b0_60.png)

That becomes。

![](img/badc5f90e9fe4250bd201b5025a023b0_62.png)

This extreme when push nothing to the weight basis， the other extreme， pushing everything。

 all the quant to the activationav here， we are pushing all the quantization difficulty to the weight。

Actually， you you compare the accuracy， none of them is good。

 but in the middle that's the sweet spots， roughly 0。5 and that's why we did this very root。



![](img/badc5f90e9fe4250bd201b5025a023b0_64.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_65.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_66.png)

Right here。And we find those spare roots。Squa root right here。

 that's corresponding to the general case where we're having the x to the power of alpha。



![](img/badc5f90e9fe4250bd201b5025a023b0_68.png)

And w to the power of more1 minus alpha尔法。

![](img/badc5f90e9fe4250bd201b5025a023b0_70.png)

Our is the migration strength determining how much quant typically do we push from activation to the weight。



![](img/badc5f90e9fe4250bd201b5025a023b0_72.png)

The larger the alpha， the more we are pushing the quantization difficulty to the weight and the weight becomes much harder to quantize as activation becomes easy。



![](img/badc5f90e9fe4250bd201b5025a023b0_74.png)

The middle is a sweet spot where the accuracyene maintain pretty high。



![](img/badc5f90e9fe4250bd201b5025a023b0_76.png)

So we're practically  0。5。Or finding a square root is a very good recipe。

Okay so we integrated smooth font into faster transformer。

 so this is the precision flow the precision of each compute node。

 the yellow one is at P16 the green one is into8， we want to have all the compute intensive operations like linear operations batch the modificationplication to be done in the quantized manner。

 so these green parts are all in quantized the manner like QKV BMM and other BMM for the attention output projection FN1 FFN2 they are all performed in all in into8。



![](img/badc5f90e9fe4250bd201b5025a023b0_78.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_79.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_80.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_81.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_82.png)

Versus this is not nonlinear layer like layer norm， soft Mac， layer norm element was add。

 they are done in F16 to preserve the accuracy。

![](img/badc5f90e9fe4250bd201b5025a023b0_84.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_85.png)

And here the bypass branch， the second bypass branch and the input to the Le norm。

 they are done in being they are done in the P16 manner to preserve the accuracy and they are not compute intensive。

 so it's fine， it's fine to keep them in P16。

![](img/badc5f90e9fe4250bd201b5025a023b0_87.png)

Okay talking very little letacy。So this is a system implementation part。

Combining the system implementation with the smooth font algorithm。

 we can well preserve the accuracy across different models and big models， this is the P16。

 this is the smooth font version maintaining the accuracy while reducing the serving costs previously it require eight GPUs to serve this 175 billion parameter model now it requires only four GPUs to serve this 175 billion parameter model and if you see that agencyency。



![](img/badc5f90e9fe4250bd201b5025a023b0_89.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_90.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_91.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_92.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_93.png)

We reduce the GPU by half， the wait is even shorter。

 it's even shorter even faster because of the reduced communication overhead。

And the memory is also reduced by half， adding fewer GPUs。



![](img/badc5f90e9fe4250bd201b5025a023b0_95.png)

Each GPU is pretty expensive， so it makes a lot of sense to reduce from8 GPU for four GPPUs and have the same qualities。



![](img/badc5f90e9fe4250bd201b5025a023b0_97.png)

We even scale it up to a 530 billion parameter model。 Hey we want to serve that in a single GPU node。

 Why it's good to serve the model in a single node。



![](img/badc5f90e9fe4250bd201b5025a023b0_99.png)

Ratherther than in a distributed manner。Communication over。

 right you want to fit the model in the node so you don't have to communicate easier to paralyze。



![](img/badc5f90e9fe4250bd201b5025a023b0_101.png)

Previously in this is by 12， I require 16 GPUs to serve with Microsoft current LG 530 billion times model and then require two node。

 each node has 8 GPUs， 16 GPUs has two boxes。And after applying a smooth quantities。

 we apply into8 composition， only8 GP can fit， and the latency didn't change much。



![](img/badc5f90e9fe4250bd201b5025a023b0_103.png)

Pretty much the same having the GPQU memory and having the number of GPUs right here。Okay。

 so smoothoo Qua also works for newer models like Dma。

 and this is comparing 1816 versus smoothmth quo across different benchmarks。



![](img/badc5f90e9fe4250bd201b5025a023b0_105.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_106.png)

就那个拉着拉拉一处smder拉。All right， so that's the first algorithm of La oil and quantization， smooth quas。

So we want to continue push forward to use fewer bits right so I'm going to introduce the activation of where weight only quantization that push the weight precision to only4 bit from8 bit to four bit。

And also the tiny chat， which is the system that support the implement AWQ algorithm。



![](img/badc5f90e9fe4250bd201b5025a023b0_108.png)

So here we want to target on device， single batch， single user inference。

 so on device Im inference is pretty helpful where you want to interact with your device locally without communicating your data to the external to the internet。



![](img/badc5f90e9fe4250bd201b5025a023b0_110.png)

So the weight is actually the bottleneck。

![](img/badc5f90e9fe4250bd201b5025a023b0_112.png)

So from larger batch to a smaller batch， the compute intensity is much lower since matrix matrix modificationplication becomes matrix vector modification。

 it still fetch the same amount of weight， but a lot less reuse in matrix vector modification。



![](img/badc5f90e9fe4250bd201b5025a023b0_114.png)

So we want to alleviate this bottleneck caused by the weight memory axis。

 so here the X axis is the compute intensity fetch one bite of data。

 how much process how much flops you can do the Y axis is the is the key lops error gloves per second。

So we need low bit， low bit weight only quant for this setting because the activation is not the bottom line here。

Wight is the bottleneck in a single batch serving， that's why we quantize the weight to extreme and need the content leave the activation in Simbi and also leave arithmetic in Simbi since for low batch arithmetic is not the bottleneck。

 but weight is the bottleneck。And here we are focusing on the generation stage。

 a which is the red part， so compare with the black part， which is the contact stage。

 the contacts here has 200 tokens， the generation we want to generate 20 tokens。

 the generation stage is the bottom line occupying the majority of the total inference time。

The second figure is showing that we are focusing on the generation stage。

 but the generation stage is bounded by the memory bandwidth so the red curve here is the IP 16 version。

 the yellow curve is the into8 version。

![](img/badc5f90e9fe4250bd201b5025a023b0_116.png)

On the。The green one is the new one we are composing here in the fall for the weight P 16 for the activations in the switch region。

 when the batch size is small， when the computation intensity is small。

 the W4 version has much higher achieved performance。And on the right hand side。

 they're preparing the weight versus the activation， the weight is in red， activation is in black。

 so weight this is the logariththmetic y axisces and you can see。

The memory footprint for the weight is like 70 times more than the activation here for the FFN it's over 1。

000 times larger than the activation， so weight is the focus you want to weight the only quantization in this work。



![](img/badc5f90e9fe4250bd201b5025a023b0_118.png)

So given that setting。Let's see。 what if we do them naively using what we have learned in the lecture so far。



![](img/badc5f90e9fe4250bd201b5025a023b0_120.png)

So this is the weight matrix。It is8 by four， initially it is p6， we want to quant it。

 given the space limitation， we quant it to into three eight choices。Unfortunately。

even doing such round to nearest quant， there is a big。

 very strong degradation for the perplexity measured on w text2 data set。

 a very strong degradation and the perplex， a big change， a big increase。



![](img/badc5f90e9fe4250bd201b5025a023b0_122.png)

Big degradation for the perplexity， which is too bad。

Showing that our conventional algorithms will not work。So what do we do。Interestingly。

 we'll find just preserving one role in this case，1 percent at 1%。

Of the city which channels unized can greatly improve the complexity。

Just have 1% of the channels keep them unfized， we can save the perplexity and see immediately saving the perplexity reducing the perplexity when having 1% of the models unized。

But the interesting thing is， how do we select those 1% of city channels？

When we are quantizing the weight， it's very natural。To look at the weight distribution。

 the weight values， for example， when we are pulling the weight。

 we prune away those small weights when we are quantizing the weight。

We na if the solution is to look at the weight， for example， if the weight magnitude is large。

 we can don't quantize it， right。But contrary intuitively。

 AWQ find that we should not look at the weight when quantizing the weight。

 we should look at the activation when we are quantizing the weight。



![](img/badc5f90e9fe4250bd201b5025a023b0_124.png)

This makes sense because the weight will be multiplied with the activation。



![](img/badc5f90e9fe4250bd201b5025a023b0_126.png)

And we have this outlier problem in the activation。

 some channels like this red channel may be super big。Two orders of magnitude larger。

 so if you are changing the activation and if you are changing the weight by a small disturbance。

By a small amount， it will disturb the final value a lot if the activation is large because this activation。

 the second column here will be multiplied with the second row。

So thisel will be multiplied with a pretty big number， then we should protect this。

So that's where the AWQ comes from activation awareness question。

Oh perplexity is the measurement of the quality of your own language and model。

 so it's basically showing comparing your output versus the ground truth output。

 the lower the better。Okay， so this is showing activation has a lot of outliers。

 we should look at the activation but not the weight。So this is comparing。Look at the weight。

 look at a random random selection selected by weight versus selected by the acquisition。

And there is a big improvement for the perplexity by selecting based on theation， not the weight。

But the problem， there is a real problem here right here we are keeping 1% of the channels unized there are succeed。

That's very difficult to implement if you have both in the4 and left B6 in the same ten。

Which will introduce mixed precision， which we don't like that makes the inference library very complicated。

So is it really necessary to introduce mixed precision？

Is there a more efficient way to get a rate of is 1% of floating point number？Actually。

 there is a way to do that okay so we can protect the same weight by simply scaling them without mixed precision okay by simply scaling them this is inheriting the intuition of smooth parts if we multiply scale the weight。



![](img/badc5f90e9fe4250bd201b5025a023b0_128.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_129.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_130.png)

Skilled activation in a reverse manner， they can cancel each other okay and so the result will be the same。



![](img/badc5f90e9fe4250bd201b5025a023b0_132.png)

Here's some notation where the quant is the weight equal to with first calculate this delta。

 which is the quantization scalar， which is the IBS max within the group so the delta is the range。

 the max value and then we round the result dividing in w by this max value to the power divided by2 power of n minus1 n is the number of bits。



![](img/badc5f90e9fe4250bd201b5025a023b0_134.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_135.png)

So we can actually scale。The activation to protect it that's actually super effective。



![](img/badc5f90e9fe4250bd201b5025a023b0_137.png)

If we modify the se channel by 1。5， the complexity reduced from 43 to 14。

Multiply the sitting channel by two， reduced to 14 multiplly by 4， 14。4。



![](img/badc5f90e9fe4250bd201b5025a023b0_139.png)

So this is a very interesting observation。You don't need to keep it basic。 You only need to scale up。

If a channel is in it。Then how do we decide。How much do we scale。

 we can see here if you scale at the right amount like 2x， it's very big saving。

 but if you scale it by too much like 4x。

![](img/badc5f90e9fe4250bd201b5025a023b0_141.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_142.png)

The perplex will get worse。So intuitively， if you are s only one channel by two。

 other channel remains the same。You are effectively adding one more bit。If you scale it by four。

 we are effectively adding two more bits。Right。Say give an example， 0。5 and one。Without any skating。

0。5 will be rounded to why。You cannot distinguish them。But if you scale them。0。5 becomes what。

One becomes two。Right， and so you can distinguish them now。Assuming other ideas stay the same。

so that's the simple intuition behind why scaling up。A channel will protect it。

Previously something cannot be distinguished， now you can distinguish。Okay。

 so let's dive deeper mathematically， why s up， skating it up will work。



![](img/badc5f90e9fe4250bd201b5025a023b0_144.png)

So on the left hand side it's showing this is the quantized， the weight multiplied by the activation。

So this is the quantization equation we introduced in lecture five。

And this is a scaled version on the bottom， skilledd version of W， skilledd version of x。

 which is point me as to both weight and activation。



![](img/badc5f90e9fe4250bd201b5025a023b0_146.png)

And now we want to calculate the error the error of the quantized weight times the activation。



![](img/badc5f90e9fe4250bd201b5025a023b0_148.png)

We just to plug in the。It probably question here on the left。Delta。

 the quant scalar is ABS max within the group， so it has no error。But this wronging function。

 the other error comes from this wronging function。



![](img/badc5f90e9fe4250bd201b5025a023b0_150.png)

So the rounding function ranges from 0。50 to 0。5， so the expectation is 0。

25 if you have a lot of numbers。

![](img/badc5f90e9fe4250bd201b5025a023b0_152.png)

So this round functions error。The error of aroing function has the expectation of 0。25。

And if you have this scalingating factor， s here， s is multiplied with x x is divided by s and since we are scaling them up。

S is greater than what。So plug in this equation。this ABX max within the group stay roughly the same since you're only scaling up 1% of the channel。

 it's very unlikely you are scaling up the biggest channel。



![](img/badc5f90e9fe4250bd201b5025a023b0_154.png)

So this。

![](img/badc5f90e9fe4250bd201b5025a023b0_156.png)

This delta roughly stays the same and only this s is different so that a larger s will reduce the error。



![](img/badc5f90e9fe4250bd201b5025a023b0_158.png)

So can S get infinitely large？It cannot， otherwise it will impact。



![](img/badc5f90e9fe4250bd201b5025a023b0_160.png)

Is ABS max this datata？

![](img/badc5f90e9fe4250bd201b5025a023b0_162.png)

So I kind get super big。As we can see when。

![](img/badc5f90e9fe4250bd201b5025a023b0_164.png)

As gets bigger from two to four。The complexity will get larger。

 will get worse because they are destroying those land sient channels。



![](img/badc5f90e9fe4250bd201b5025a023b0_166.png)

So next question is we need to search for the best scale how do we now how do we scale the activation？



![](img/badc5f90e9fe4250bd201b5025a023b0_168.png)

So here is a recipe，The skating factor is。The average activation magnitude as x x is the activation。

Sx was the average activation magnitude to the power of。

 and alpha is the hyper parameter we can search from zero to1。



![](img/badc5f90e9fe4250bd201b5025a023b0_170.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_171.png)

And we want to minimize this scaled WS versus the original WX。

And here the s to the power of minus1 can be fused to the previous operation。

 remember we have the pre norm， so the normalization comes before the matrix multi。

And the later norm as a skating factor。

![](img/badc5f90e9fe4250bd201b5025a023b0_173.png)

this is to power of minus1， this scaling factor can be effectively folded into that operation。



![](img/badc5f90e9fe4250bd201b5025a023b0_175.png)

When we are scaling the weight， it's also static because we know the weight ahead of time。

 so wait time scaling factor can be calculated often so there's no runtime overhead in this case。



![](img/badc5f90e9fe4250bd201b5025a023b0_177.png)

Okay， so that's the algorithm of AWQ and let's see how that works。So this is the。



![](img/badc5f90e9fe4250bd201b5025a023b0_179.png)

Perplexity， the lower the better between GBTQ and the AWQ， so this is the collaboration sequence。

 actually we require very little very short sequence like 64 sequence。

 then the propplexity is pretty already pretty low。When we have very short cl is set。



![](img/badc5f90e9fe4250bd201b5025a023b0_181.png)

The perities are also much lower than the business。

So this method doesn't require any fact propagation。

 so it only require a collaborationration data set。

It doesn't require this regression based method which tend to overfe and doesn't generalize also have very good data efficiency only very short clean sequence can help a lot and generalized but better。

To different across different data sets， for example，M， which is a medical data set。

 inter is a corporate email data set。

![](img/badc5f90e9fe4250bd201b5025a023b0_183.png)

Two completely different domains。Using the baseline method， the GPBTQ method。

The complexity increase a lot two or four points when you are switching between a different。

P Ro and V that。Be different labor version data sets。When you are using the actual data set on text。

 under text versus AWQ can have very minimum complexity increase when you are switching the collaboration data sets。



![](img/badc5f90e9fe4250bd201b5025a023b0_185.png)

That is different from your accuracy testing data sets。

And this is showing AWQ for large language model quantization for Lama Lama two。



![](img/badc5f90e9fe4250bd201b5025a023b0_187.png)

Of comparing different approaches across different model sizes from 7 B to 70 B。



![](img/badc5f90e9fe4250bd201b5025a023b0_189.png)

The accuracy of complexity is pretty low。AW also works for visual language model， okay。

 so basically given EV image or video， you want to tell what is happening and do question answering。

We are going to talk about that in the later lecture， like given my video。

 here is a football soccer game。Please tell me what happens in the video。And this is Ron。

run live at Vla。MITEDU， youre free to check it out。 This is deployed using the AWQ algorithm。

啊 deployeded on a single啊 single to。And the question is please tell me what happens in the video。

 Amida says a video shows a soccer game where a player scores a goal。

 the crowd cheers and the player celebrates with his teammates。

And this is using the AWQ4bic wordland。So here we compare that P16 version。

Versus the full bit version， the accuracy across different benchmarks is pretty well maintained for both the 7 B and the 13 B model。

And to implement them there's a question。不错。好，听。It's actually one time。开活。Whi one。

Just don't talk about。他の相应。I'm not aware。 I don't know。There are many users of Villa。

 maybe that's one of them either。I'm not aware we did this。

 I think this work was in June in 2024 and all the demo is available。Earlier this year， actually。

Okay， so how do we implement the four bit AWQ model Okay。

 so we have an engine developer engine called pan chat， our inference engine on the edge device。

So tiny chat is a lightweight large language model inference engine。Based on Python。

 we have a lot of low level implementations， but we expose to the user， the Python interface。

 very lightweight weighted， efficient， support multiple platforms， CPUs， GPUs， etc。

So we want to target two， bigger merit， make it efficient， and also make sure it's easy to use。

And support multiple platforms， including the cloud， desktop， laptops。

 which you will implement that in your homework， lab5， and also edgeG GPPUs， mobile CPUs， etcter。

The problem here is that since 1960s， computers has been bite or light the minimum units。

Computer is a bitete and a Bte is 8 B， right， Well AWQ1ang tie is the weight to only 4 bit。

So how do we align this mismatch？

![](img/badc5f90e9fe4250bd201b5025a023b0_191.png)

Every register， right， this is the width register， each register have to store eight bits。



![](img/badc5f90e9fe4250bd201b5025a023b0_193.png)

But each weight is only four bit。Which means for each bite， we are going to store two links。

And we want to decode the weight such that we can exploit the register level heroism。



![](img/badc5f90e9fe4250bd201b5025a023b0_195.png)

So this is original weight。He， this is the weight we want to process。So for every two boxes。

 that indicates a byte for bit。

![](img/badc5f90e9fe4250bd201b5025a023b0_197.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_198.png)

In each rectangle， I represent four bit。

![](img/badc5f90e9fe4250bd201b5025a023b0_200.png)

分首打分。The motivation here is to be able to easily we want to easily decode the packed weight so here we want to store the weight in this manner rather than storing consecutive manner that  31 30 and then 1510 okay we want to store them in this manner。



![](img/badc5f90e9fe4250bd201b5025a023b0_202.png)

啊31 first and then15 then double two71，160，可 in an inter livedve manner。



![](img/badc5f90e9fe4250bd201b5025a023b0_204.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_205.png)

So if you just look at the gray part， they are consecutive 0，1，2， all a 15。

If you look at the yellow red part， you are conceptual like 1617 all the way to 31 okay。



![](img/badc5f90e9fe4250bd201b5025a023b0_207.png)

Well， we can perform two low level operations to be it。



![](img/badc5f90e9fe4250bd201b5025a023b0_209.png)

First， with a mask。This did this vector with。The lowest bit to be one and the highest bit to be zero。

 then we can decode the lower bit。The math would be00 F，0 F，0 F。And then we can shift by four， shift。

This pack the weights by four bits。And then mask it after shifted。

The red part go to the bottom okay and after maxing it with the0 f，0 f。

 we get the top from W 31 to W 16。

![](img/badc5f90e9fe4250bd201b5025a023b0_211.png)

Yes。😊。

![](img/badc5f90e9fe4250bd201b5025a023b0_213.png)

And using this packed approach， we can reduce rela about 20% speed up arm near。



![](img/badc5f90e9fe4250bd201b5025a023b0_215.png)

Another important technique is kernel fusion， so in the parallel processing lecture we talk about the overhead of kernel calls in the GPU so it's not free lunch。

Launching each kernel is taking a lot more time than expected， so we want to。



![](img/badc5f90e9fe4250bd201b5025a023b0_217.png)

Fs all these operations in a single kernel， so BMM， QK transpose， softm。

And then multiply the attention map with the V， the value vector， and all of these。

 we want tofuse them into a single kernel for the attention。

And also we want to use the kernel for the ja okay in the contact stage。

 we also want to have a single kernel for the ja。

![](img/badc5f90e9fe4250bd201b5025a023b0_219.png)

O these techniques。Ting chats can significantly apply be applied to accelerate action language model。



![](img/badc5f90e9fe4250bd201b5025a023b0_221.png)

You point on a desktop GPU， a laptop GPU， a mobile GPU that is Jason already widely using self learning parts。

These baseline， those are the three parties at PCC speed the red part the interval AWQ results。



![](img/badc5f90e9fe4250bd201b5025a023b0_223.png)

On these three benchmarks and different hydro platforms， AWQ had achieved roughly a3 x speed up。



![](img/badc5f90e9fe4250bd201b5025a023b0_225.png)

And previously， some of the models cannot fit。

![](img/badc5f90e9fe4250bd201b5025a023b0_227.png)

And not of it。The laptop GQ the GPQ has only8 gigabytes of GPQ diamond the laptop。



![](img/badc5f90e9fe4250bd201b5025a023b0_229.png)

So FP16 runs completely runs out of memory， but the AWQ version onfi。

So this is comparing AWQ with other frameworks like autoGPTQ， Lama， do CPP， EX Lama。

 etc cetera on a JN Orrange mobile GPU。But we build a tiny track computer， which is right here。

Which is powered by Jason Oro。 can run Lama 2，7 B on this。Tinny chat computer， it's 3 printed。

And inside in the back， it has a Jason ao。Wch is right here。我现再见。

The board has about 7 gigabytes of available memory。And tiny chats and Qua time。

The number to 70 to 4 bit。 So that requires3 and a half gigabyte of weight memory。

It can fit well in a  seven gigabytes。Devicice also strong to see the previous。Outs。

So such mobile development can enable data privacy and security。

Even without internet enable customization and personalization， and after lab5。

 you will going to see bring your home， something like this。

 deploy a large language model on a laptop， either a CPU laptop or GPU laptop or a MacBook。

So on the left hand sideです。showing only 25 meconds per token right on the right hand side。

 we are trying to write some code to compare to a race on a MacBook。

And this will be exactly the same thing we are going to do in La five。So in La four4。

 we are going to first to do AWQ quantization in La five。

 we are going to implement the quantize model on your laptop。

So make sure your laptop has more than 8 giggay or manually。Okay。

 so this is showing the speedup on cloud GPPUs。哦 desktop， GPU， gaming GPU， and also the mobile GPPU。

So a 1490 and or tokens per second means how many tokens they can output the second it can generate。

So comparing the baseline version into4 AWQ model consistently deliver about 3x speed up over P16 on the Orient platform。

So this is the originient platform， which is a mobile GPU。

We are running Vla visual language model on it， whatever is unusual in this image。

And it's going to say there's a herd of deer crossing the streets， a car is waiting for them to pass。

What should should the driver keep going， No， the driver should not keep going。

To wait should wait for the deers to cross the road。In Central。

 30 about running and about 4043 milliseconds per token。Also。

 this is a visual language model demo runable on a laptop。So what is the name of this painting？

This is with M1 chip running on a CPU， not even a GPU。And那 goes going to say portrait of Monna Lisaa。

And who drew this will拿到打边题。And describe the painting in details。

And it's when to talk about that running it life。Without transmitting your pictures。

 languages or top。So in our homework five， lab five。

 we are just going to implement the language model without the image。

 but feel free to also support image。In that which could be part of your final project。

 which is open ending。呃，So AWQ also has pretty a lot of downloads， a lot of users。

At the time we will make this slide， it's1 million downloads。

 but now it's already over  six million downloads on Huging phase being used by media， Ten TROM。

 which is a flagship library for large language model， deployment for Nuance，M Berkeley， Cha。

 transformer， Huging phase， transformer， etc。All right。

 let's take a break before we jump into the next part。All right， welcome back。

 we spent a lot of time talking about smooth Qua and AWQ since they are going to be in lab four。

 so we talk them in very detail to strengthen your understanding now let's move on to combine the best of both world between smooth quas and AWQ。

So let's first look at the difference between AWQ and smoothta。

Here the red curve is showing the smooth font where we are having8 bit for the activations。



![](img/badc5f90e9fe4250bd201b5025a023b0_231.png)

So the red curve here is showing App16。

![](img/badc5f90e9fe4250bd201b5025a023b0_233.png)

OM well this orange curve is showing the in8 OM right so the smooth point is basically into8 for both the weight activation and also the KV cache we not take by W8 a8 KV8 KV for KV cache A for activation W for weight。



![](img/badc5f90e9fe4250bd201b5025a023b0_235.png)

Okay， so this is pretty good for the cloud serving W4 A16 KV16， which is the AWQ setting408。

 16 billion activation， 16 billion KV cash， that's good for the edge inference。



![](img/badc5f90e9fe4250bd201b5025a023b0_237.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_238.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_239.png)

Because for the cloud serving， usually there have been a pretty big batch size and the popular setting is WA8。

 where the weight is an8 bit activation8 bit and KV cash is using 8 bit per tensor composition。



![](img/badc5f90e9fe4250bd201b5025a023b0_241.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_242.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_243.png)

It can improve we can lift the roof line so previously it's one treated numbers per second since each element is two byte in a316 into8。

 each element each number is only one byte so we can pass two treated numbers calculated two treated numbers per second also have a bigger peak of peak performance。



![](img/badc5f90e9fe4250bd201b5025a023b0_245.png)

Well， for the edge device， the most partner is that4 a16。



![](img/badc5f90e9fe4250bd201b5025a023b0_247.png)

So in the low batch area， it wins over this yellow curve because the weight dominates memory bandwidth dominates into the bottleneck。

For once it peaks， the peak performance the same asP16 is2 smaller than the W8 a8 so the red is the baseline we have these two solutions a smooth point is this yellow part AWQ is is this green part。



![](img/badc5f90e9fe4250bd201b5025a023b0_249.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_250.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_251.png)

Our question is， can we combine the best of both world to have something into this W4A8 part into this green part？

So that's the motivation and that's the goal for the Q serve is to combine the best of both world in both the small batch and also the large batch settinging to using the four bit weight。

8 bit activation and8 bitrithmetic。

![](img/badc5f90e9fe4250bd201b5025a023b0_253.png)

There is some prior exploration， but unfortunately and failed， which feel very good through folks。

So you see the baseline on Ten IT from EMmedia and this is Adam， this is Pro but4 a4。

 they're all got before4 a4， but unfortunately the throughput measured by tokens per second。



![](img/badc5f90e9fe4250bd201b5025a023b0_255.png)

It's even smaller even half compared with tensor RTs W8 A8， so they reduced the precision。

 but unfortunately without a good engine knows to be done， but two I slow down。



![](img/badc5f90e9fe4250bd201b5025a023b0_257.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_258.png)

And also that brings significant accuracy loss using the W4A8 W4A4 manner compared with the higher precision version。

So we try to dive deeper to understand the overhead in quantized jam on the GPUs。

So couda core in the main loop is pretty expensive。

 we try to do as much processing in the tensor core。

 not the coa core and should try to do as little as possible such things such as the skating in the tensor core in the couda core inside the main loop this is the main loop this is the epilo and also this is the tenOM the free from the media in the8 weights and in8 activation so the main loop it' all processed the orange means the in the8 the red meansP16 only in the epilo we do the skating。



![](img/badc5f90e9fe4250bd201b5025a023b0_260.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_261.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_262.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_263.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_264.png)

On the quo core， so this is actually pretty efficient。And let's see。

 let's take a look at other alternatives， why framework is not efficient， for example。

 Adam they to cancel for the in the four operations， this is in green in the fall。

But they had to do a lot of quo operations in FP 16 in the main note， this is in the main note。

And particularly it's doing the scalingating of the partial sum with the partial sum。

 we have to modify them with the floating 0。1616 scalingating factors right here。So Paros and Ja。

We consume much more registers compared with the inputs。

哎 and partial some decoization from in in 32 to IP 16， decoization requires much more computation。

That's why it's even slower。And compared with this is the ten alarmMs implementation of AWQ。

 fourbi weight，6immb activation， which this is the fourbi weight in green。

In the Qa core it converted into a 16 bit floating point。

 very quickly converted to 16 bit floating point， and then all the major computation that are using the 16 bit floating point。

So this conversion is the input conversion is much more efficient compared with the partial sum decoetization。

 which require much more register than inputs。Which have much smaller pressure using the registers。

So what we propose here is using the four bit for the weight。

8 bit for the activation and8 bit for the arithmetic。

 so first convert this four bit weight into8 bit integer and do the other matrix modification in8 bit integer right here do the sum so this is the main loop。

And outside in the Buddha core， we multiplied with the scalingium factor as the IPloc。

Since this is outside the main loop， this is outside the main loop。

 the processing is much more efficient。So the take home here is that you try to do this deco quantetization。

 not in the main， but in the IP log， and also try to minimize the conversion the decoquization of the partial sums。

 which consume much more registers。So monizing the the KB cash to4 bit is actually quite challenging。

 So we are observing。

![](img/badc5f90e9fe4250bd201b5025a023b0_266.png)

There is actually a lot of outliers in the keys， so this is the value value is pretty smooth。

 but the key is this the proposed road。We we talk about real real keys。

 some channels has pretty big outfires。

![](img/badc5f90e9fe4250bd201b5025a023b0_268.png)

So we can actually apply smooth attention to using a similar approach as smooth font to smooth away those art tires in the piece。

So since the keys will be multiplied with queries， we want to push the quantization difficulty between the query Q and the key and we are going to use this giving factor will be just related to the K since we are pushing all the quantization difficulty from K to the Q since query is pretty small we can keep them in6 and keep the quant push all the quantization difficulty from P to query。

 that's why here we have only a single term which is K there's no Q。Another technique。啊 to嗯。

Determined to de quantize from the for bitd einstein inte of einstein into4 to sine into8 is a sequence between the subtraction and the multiply okay remember we have a bias。

 we have a zero point， we have to subtract it and then multiply it by the sating factor。

Unfortunately， using this way， it will lead to overflow。

 so this is original context the weight binary representation。



![](img/badc5f90e9fe4250bd201b5025a023b0_270.png)

A hackx representation of the Pocra Lake if you first subtract the zero point。

 look at this this value a minus1 minus8， this is the hackx representation same as before before here is the decimoid representation here is the hackx representation。

And then we multiply with the scaling factor to two， scaling factor two。Unfortunately。

 the carrier bit will lead to over originally this is 14 this is 14 minus 10 and will be e2。

 so the carrier will overflow the next value。

![](img/badc5f90e9fe4250bd201b5025a023b0_272.png)

So this actually can be solved by multiply first， first multiply with two and then subtract。



![](img/badc5f90e9fe4250bd201b5025a023b0_274.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_275.png)

By9 16， and this will lead to no overflow。So the sequence matters previously if you want to calculate something like you want to scale it and then subtract versus subtract and then scale that make a difference。

I have no precision。So to serve actually outperform the state of the art in French libraries， that's。



![](img/badc5f90e9fe4250bd201b5025a023b0_277.png)

The RCN， AWQ。And the Rrov item and who serve actually have a。



![](img/badc5f90e9fe4250bd201b5025a023b0_279.png)

Pretty good， pretty low perplexity and W 4A8 KB4 quant。And this is the speed up， the throughput。

Masured on a 100 on the first row and L for the s on the second row。Okay。

 so let's now switch gear from quantization to pruning and sparsity。

 so I'm going to talk about weight sparsity， contextual sparsity and also attention sparsity。

So this work basically pro the weights， and not previously we were when we are pouring the weight。

 we look at the weight， if the weight is small， like these weights are small in blue。

 then we are going to zero them out。

![](img/badc5f90e9fe4250bd201b5025a023b0_281.png)

And this paper basically is showing that we should not look at the weights。

 we should look at the activation， so this is activation that's going be multiply little weight。

The multily results from here， for example，1 is multiplied with eight and becomes eight。



![](img/badc5f90e9fe4250bd201b5025a023b0_283.png)

And then we look at the values that's pretty small okay， so this zero is small， four is small。

 pretty small， we look at the result of w minus w times the input activation and we profile and we eliminate those small pull activations and using such activation to guide the weight the intuition is very similar to a WQ where we should be activation aware。

 look at the weight look at activation when we are either provingruning the weight or quantizing the weight。

So this is showing comparing the performance of the magnitude based the pruning， sp GT and onenda。

 and this method is showing that the weight times the activation as the criteria for pruning actually outperforms the magnitude based the pruning。

Okay， contextual sparsity， so people find when we are pulling the activations。

 the static that sparsity hurtss it should be input dependent right so contextual sparsity is basically saying that the small input dependent sets of attend heads and features exist in the large language models。

So we can use a predictor， twin a predictor to predict which a ca head is useless and which dimension of the an P layer is useless。

 when we train such a predictor using the previous layer to predict for the next layer which dimension is useless。

 we can safely remove。啊Those啊。Tokens okay， so this is showing using static sparsity。

 the accuracy quickly drop when the parameter reduces。This is showing losing context transcity。

 and accuracy can be well maintained。At a very high primary reduction ratio。

And on the right hand side it is showing the showing the speed up compared with the baselines， D Ju。

 which is showing this contextual process can bring very reasonable speed up compared with the baseline。

There's also the mixture of expert as a coarse braindiparity。

 which is showing that given different input。Different tokens generation will use different part of the weights okay。

 for example， when we are generating this token， the route are routed to the second epron versus another token will be routed to the first eturn。

Which is showing we can use different parts of a model to generate the next token。

So this is showing the router so we have several experts here we have three experts altogether we have six tokens。

Here is showing the first expert is responsible for these two tokens。

 the second expert responsible for these two tokens we can design this capacity factor to be tokens per batch divided by the number of experts。

 and this capacity factor。If the capacity factor equal to one is showing that altogether we have six six tokens。

 so tokens per batch six number of expert， we have one two three， we have three expert MC1。

 so every expert can process at most two tokens。And if the capacityac factor is 1。5。

 average expert can process at most of three tokens at most of three tokens。

 so there's an empty select。Token for expert two and three。

So the router the routing mechanism can have different approaches。

 one is by token the other is by expert so here is showing a token one can choose between expert one expert two all the way to expert5。



![](img/badc5f90e9fe4250bd201b5025a023b0_285.png)

And token2 can also select its preferred expert。The other way is per expert。

 so expert one and choose the top K to handle token one， token 2 or token 3。

 expert two can also choose to handle different tokens。

We can also do this global assignment expert assignment， which token gets assigned to which expert。



![](img/badc5f90e9fe4250bd201b5025a023b0_287.png)

So there is also the attention spity， okay， so spapart is showing that we can do token pruning and head pruning。

For example， given a sentence as a visual treat， the film is almost perfect。

 it has 11 tokens and 12 tasks。We can it to only five tokens and1 hats as treat film perfect。

And then prorun it to only two tokens。 Hum perfect。

They can still classify the sentiment to be positive。

 which is showing the natural language has a lot of redundancy and it's safe to remove most of the redundancy and still achieve the similar goal。

On the right hand side， it's showing the attention mask to show how do we perform at this token pruning。

When we look at the attention map， I bet the video game is a lot more fun than the film。

 and this is the attention map for each token with sum the attention score across the entire column。

For example， u will be sum up to0。4， learning little attention across different tokens for this u token。

Versus fun。The attentions cumulative attention scores went nice pretty high。

 Like some of the tokens are very heavily to this token， so it cannot be removed。Token is like I。好，不。

哦都。Period， they receive very little attention so we can safely remove those token so in summary tokens when small cumulative important score will be proved。

So following this work is H2O this paper fine it is possible to prove tokens in the KB cache which is very similar to the spattan work okay so also look at the attention attention map now the difference is now it's causal also just look at the cumulative attention score if a certain token has very small cumulative attention score it's going to prorun it away。

Okay， so next chapter let's talk about our' serving systems。

 let's first introduce the metrics for ourM serving so the first concept is about time to first openken you measures after your type of question your query how quickly does the large language model begin to respond to you so this is very crucial for real time interaction you want to input your question and you want to immediately get an answer。

And there is also a concept called time per output token， tokens per second。

 which is a time that is taken to generate each output token。For example。

you can 0 it takes 100 mill secondsconds to generate each token then that corresponds to 10 tokens per second。

And that is roughly the threshold。Above that， and well feel is very interactive but below that we willll feel the large language of model is pretty dumb。

 it can generate very very slowly。And the total laency will equal to the time to the first token plus time per output token times the number of tokens to be generated。

That's the total latency to complete the task。And the thirdput is the number of tokens generated per second across all the requests by the inference server。

So the goal of the inference system optimization is to minimize the time to the first hook and we want to maximize the throughput。

And also reduce the time per output token。And there's usually a tradeoff between the throughput versus the time per output token。

 we are going to see that。And there are several heuristics of a model evaluation， for example。

 the output love。Since the op generation will dominate the latest。

 the input life that will impact the time to first token。And also the model size。

 usually the larger the model size， the slower the inference。

But it's not proportional because for example， the 70 billion parameter model。Is about 2 x。

 that agencyency of a 13 billion time model is not proportional。

So the first optimization technique is called VROM。page attention。

 So previously we talk about the KB cash。 when you have a lot of tokens。

 the K B cash can grow pretty large。 this is the equation how to calculate the KB cash we learned previously。

And there are several wasting， there are several scenarios of potential waste in the KVc system。

 so the first potential waste is the internal fragmentation。

 we have to over allocatelocate several spaces for the p cache due to the unknown sequence loss。



![](img/badc5f90e9fe4250bd201b5025a023b0_289.png)

So for example， here we have more than 2000 slots but it's never used。

We may also have reservation fragmentation and so it's not used in current steps。

 but it will be used in the future。For example， artificial intelligence is the future。Of technology。

 the request this current year， we generated two tokens。

But we have three tokens that has not been generated。

 we still have to allocate space for them that is currently not being used。

 we still have to allocate the space for them that is called the reservation。

Also there is external fragmentation so this is just one single request when we have multiple requests。

 they may have different sequence maths。

![](img/badc5f90e9fe4250bd201b5025a023b0_291.png)

To deal with such a fragment issue， if you have taken 6。191。

 the operating I will remember the operating system has this paging mechanism where different processes we can share a page table and we can share the memory space using page tables。

 similarly we can also use the similar memory management system for the large language model just to use the memory virtual memory and paging。



![](img/badc5f90e9fe4250bd201b5025a023b0_293.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_294.png)

So we can have the KB page to manage that。For example， in this case。

The prompt is Alan Turing is a computer scientist， so initially。I mean by this relatively slowly。

Initially we are going to fill the heavy cache by having I locate two blocks。

 each block has four entries and then as we generate we run out。

 we allocate a new block and update the block table to show which is the physical page number。

 so physical page number seven for an turn is a。

![](img/badc5f90e9fe4250bd201b5025a023b0_296.png)

I it has full entries first block is computer scientists and not so we' are keeping the physical block number and also the number of field slots。



![](img/badc5f90e9fe4250bd201b5025a023b0_298.png)

In this way， when we are having two requests， requests A and request B。

 they can work with the same physical KD block the yellow part belongs to request A。

 the green part belongs to request B， they can interleave interleave without worrying about the fragmentation issue。



![](img/badc5f90e9fe4250bd201b5025a023b0_300.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_301.png)

And the good thing about this VLM is that we can share and we can share the prompt so during the parallel sample say this is the prompt future of cloud computing is。



![](img/badc5f90e9fe4250bd201b5025a023b0_303.png)

Bright and poise or further growth intertwined with advancement of other digital intelligence likely to be characterized by several key trends。

 so for different outputs they share the same input and then you can allocate the same just a single KD block for this shared shared prompt so they both' have them both sequence A and sequence B has this prompt rather than allocating duplicatedd K blocks we can just。



![](img/badc5f90e9fe4250bd201b5025a023b0_305.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_306.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_307.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_308.png)

Moify the pointer。Both of them point to the same physical cave block。



![](img/badc5f90e9fe4250bd201b5025a023b0_310.png)

And then they can have their own paving blocks for the parallel coding。Fish attention。

 very important concept。 So when we are generating the attention matrix is' n by N。

 that's pretty big since O square。 Okay， so the key idea is use tiiding to prevent prevent you have to store all the N by N attention matrix in memory。

 So we have learned about the tiding idea in our parallel processing class that's exactly the same motivation。

We want to calculate the attention results of Q and k and immediately multiply that with a B without having to materialize that。

This is comparing the pitor implementation， this is comparing the flash of pension implementation that feels the kernel fusing this QK transpose and then times you lead these two kernels into one by you can dramatically save the agency。

And this is comparing the baseline type 14 in blue versus white flash attention in yellow versus flash attention2 in purple very significant speed up for。

For with and without the causal mask， the left is without causal mask， the right is with causal mask。

The next technique is speculative decoding okay。So the generation of the token is memory bonded。

 no matter how many you generate， if the batch size is pretty small。

 you are bottlenecked by the memory by the memory bandwidth。So the idea is to use two models。

 two models for spec decoding。 One is a small model for generation also called a draft model。

 The other is a large model for verification， we can。



![](img/badc5f90e9fe4250bd201b5025a023b0_312.png)

You know， running this large model is pretty expensive so we only run this small model auto aggressively auto aggressively and then generate many tokens in serial and then verify them in parallel so the small model generate K opens auto aggressivelyively and then the K generated tokens will be verified in parallel with feed K generated tokens to the large model the 175 billion model to run them in a similar batch manner so running K model K token will be roughly similar to running one token if K is not too large on the GPU due to the terrorism。



![](img/badc5f90e9fe4250bd201b5025a023b0_314.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_315.png)

So let's see example， so this is using two models， a small model and a large model over use a small model to generate draft tokens or draft tokens generated one by one autoregressly and then feed these four tokens together into this large model in the batch the matter its non autoregress paradigm and then verify if the generation is correct or not if it's not correct。

 you can redo it do it again by the small model。

![](img/badc5f90e9fe4250bd201b5025a023b0_317.png)

So here is， in example， we are generating these green tokens by the small model and then use the large model to verify them altogether in the batch manner and refine oh this large last the last token is incorrect then we have to use called the small model to generate again and then verify if find something is incorrect。

 generate again， the yellow the green part is the accepted but accepted token。

 the red part is the rejected token and the blue part is the corrected token。



![](img/badc5f90e9fe4250bd201b5025a023b0_319.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_320.png)

Finally， it can achieve about2 to3 x speed up with identical output。Okay。

 so the last technique is batching okay， so why do we need batching running multiple inputs simultaneously in parallel can maximize the throughput by fully Italy utilizing the GPU resources and avoid idle time。

There are several batching methods， of course， the simplest way is no batching when a request arrives。

 then we just immediately the process that we may underutilize the GPU resource。Static batch。

 which is wait for full batch of requests。Before we can process them。

 this is pretty good for offline tasks like scheduled tasks， you have like 10，000 images to label。

 take overnight and then you can use static batching。

But it will increase the latency for real time tasks。

 we may have to wait for the batch to be full for you to process。There's also the dynamic batch。

 Okay， so the batches are。Processed either when the batch is full or set a predefined time has arrived。

The last part is the continuous continuous batching also called in flight batchching okay have a final granularity token by token and let's see example of dynamic batching。



![](img/badc5f90e9fe4250bd201b5025a023b0_322.png)

So static batch basically you have to wait for fourken full requests to arrive。

 which may take a long time here， take a long time here。

 dynamic batch is saying either when the batch is full or when the pre set time has arrived here。

 this amount of time is arrived， then you should process that even if the batch is not full。

 this is like a bus will leave when it's full or when a time expires to ensure minimum wait time。



![](img/badc5f90e9fe4250bd201b5025a023b0_324.png)

This is good for the generation has uniform inference latency， like image generation。

 you have a predefin， you have the known fixed amount of inference latency。

What if the generation is not fixed you can generate a different number of tokens for different users。

 so this is the。In flight batching or continuous batching okay so compared with this kind of dynamic batching we don't have to wait for this extra slack。

 but we can immediately push the second。Second request when the first one has finished in a token granularity。

 this is like when a bus where passengers can get get off the bus at different stops we can immediately make space for new riders so here we have people get off the bus and then we can make immediately make this space for new riders this is continuous batching versus dynamic catching。



![](img/badc5f90e9fe4250bd201b5025a023b0_326.png)

All right， we pretty much covered all the techniques。now supported by Canor RTLM。

 a large language model influenced library by NV， to talk about multi high attention。

 multi query attention， group query attention in the last lecture， inar batch， pageKV cash。

 in four weight quantization， smooth Qua GDPBQ AWQ， F8 and Ro。



![](img/badc5f90e9fe4250bd201b5025a023b0_328.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_329.png)

![](img/badc5f90e9fe4250bd201b5025a023b0_330.png)

So we are going to cover tighter parallel， pipeline parallelism in the future lecture。

Lo of content today hope you master them all and enjoy La five and La four， thank you。



![](img/badc5f90e9fe4250bd201b5025a023b0_332.png)