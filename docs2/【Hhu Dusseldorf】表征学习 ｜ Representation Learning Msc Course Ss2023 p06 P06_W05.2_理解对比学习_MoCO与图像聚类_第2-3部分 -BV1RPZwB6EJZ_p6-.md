# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p06 P06_W05.2_理解对比学习_MoCO与图像聚类_第2-3部分 -BV1RPZwB6EJZ_p6-

Smalization works like be。So these are。So these are for each channel the output of a convolutional network。

 we have standard wise mean and standard deviation。

Where we divide these are just trainedable parameter parameters。We ignore them for this analysis。

So these means。I usually calculate it from the minibas， so in a distributed data parallel。

 you have the option to either aggregate the statistics locally。

So let's say we have two GPUs and each one is 128。Samples。

You have the option to either aggregate and compute these。

Means solidgregation locally from 128 elements elements or synchronize statistics from two GPUs。

Agggregate the statistics have a much better estimation of the mean and the standard deviation。

Long story short， they use the synchronized version of baization while here they do another trick。

Where they take the output of the momentum encoder， the teacher， and they suffer。It's。

And another way would be to reduce with labor money。I know it's like not exactly related to。

The actual paper or the method， but it's only if you get。

The small details right that you can see the effectiveness of those approaches。

 so it's not completely independent。Another's more note。

For those of you who have a notion of layer normalization from sequences and transformers。

I have a small slide indicating that layer normal is different from natural language。

Where you have a sequence of Tolkin's versus vision。So in evolutionvol your networks。

We average over the when we do layer normalization。

 we average over the different channels and spatial dimensions and not。With the bad size。

Wing transformers。We only average between。The D model dimension so the last dimension。

We don't average the statistics between different tokens or elements of the whole sequence。Okay。

 we found a way in case the bad size， we don't have the compute。Or the date are really large。

 for example， in the research center in Julieli， close to thisaddor， they have these huge bras scans。

Where。The experts identified that in order to learn meaningful features between those two brain scan take some crops。

 they cannot use 128 crops and maximize their similarity。 they need to go in the level of。都少人。

By 2000。So there may be many use cases where you either don't have the resources or your data。

Where you want to do representation learning are way to be。So the question is。

Is it necessary if we just optimize for performance？And the answer is no。So俾。

Like one and a half year later， they made three tricks。Two tricks。They abandon this queue。

If you want to have like the maximum possible performance on E or。Standard vision based benchmarks。

They abandon this cube。Since they don't have like computational issues。

 they train with maybe 128 degrees and the bad size of 4096 and another thing which I want you to。

To pay attention is the sumatization of the loss。诶。So basically。So far。

 we have CCLR where we have an encoder。But， here。And for the next weeks， we will see。Very commonly。

 we have two different architectures， so this is the student and the teacher。

 so there's an exponential moving out。And。所以。They are not the same network。

 sosymmetricization doesn't make sense on SCLR objective， but if these two models are different。Then。

 instead of feeding。View1 to the student， V2 to the teacher， compute the loss， we also。

 since we produce the augmentation we load the data to the GPU， we switch those values。

We would you to hear。You one here and compute the same log。So this is what we mean。

 And then we can average between these two losses。Oh。

 this corresponds to this line on the pole where you say cinema drive。CTR stands for Cross Centralry。

Any questions so far？Okay。诶。现爱文。Very， very briefly， go， I will just illustrate some more things。

 I just want to show you that contrastive learning is not limited either to RGP matches。

So here there is another paper from these guys from MID。Where， instead of。靓。

The use of the same imagemat， they take a scene， a multiple sensor， like a depth sensor or。

Different views from different sensors and maximizing similar the mutual information between them while considering as negatives。

Views from other seats。And this would result since they create their pretext task like this。

 since this would result in representations that are view invariant。

Then if you have not just two views， but a set of M views， I don't know if I add here。

How many pairs do we have for end use？So if you have a four by four。And this is a dial。诶You have。

All these elements， basically the lower triangular or the upper triangular part， which ends。

AM minus1 by by two。 So there's a number of views。When you have M views， you have。

M multiplied by m minus1 divided by two pairs， So basically all these would be。

The parents that would be considered positive。And they take two different approaches。

So they use the RGB as a reference point。And take all the contrast resources between all the other views。

So this is a presentation of a graph， so they represent us a graph and say， okay。

 we want to learn these type of connections。With its love between all those pairs。And in this case。

 they take all positive connections so。All possible。Theirs for contrastive learning。

And they use usually when you have this type of problems in vision， you have a dancingstream task as。

Sigmentation。So these four rows where they created their experimental study， they vary。

By only the encoder weights， so they use a decoder， they train on the dancing tu。

 but the first they train the decoder with a random fri。Encodeder。

 then they use this cored view where they take RGB as a reference。

 and then they use all the possible views， and this is basically fine tuning from random initialization where both encoder and decoder change。

And this is something we will cover three weeks from now。

 basically an extension from contrasted learning。To诶。Multimodal， So in this case， we maximize。

The similarity or between images。And thanks。十三。So we saw the importance of al normalization。

 why we needed what is the difference， we saw the impact of contrastive loss and what's actually happening that features uniformly distribute themselves in the hypersphere。

We saw the memory bank that you can solve problems even where you don't have the resources。

 the compute power， or the problem demands you to use a small bad size。

Even though it's not the optimal when you just optimize for performance， but usually in real life。

 there are much more requirements。We saw that。Engineering can cause。

Problems similar to baization causing information leaks。

That we should always be aware of what's happening as much as possible and lastly。

Contrasted learning is not limited to RTB or single model。In general images。

 we will cover the last approach called clip and Lagu you must be training in the next lectures。

Any question？This is your last because after we will make a small break for 10 minutes。

And then we will switch to talking to talk about， I will talk about a bit about Emmama's class。

So any questions regarding all the contrasting momentum code there？Then let's take a small break。

That means okay。