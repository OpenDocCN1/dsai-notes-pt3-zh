# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p13 P13_W08.2_基于掩码的视觉表示学习_MAE__BEiT__iBOT_第2-2部分 -BV1RPZwB6EJZ_p13-

four months。诶。We is as， the design performance much faster compared to training from scratchs。And。

It also works very well for downstream tasks since we mask。

For downstream tasks at somatic segmentation。嗯。So Bit version two is only a smarter way to integrate this idea of assigning。

But is to。visual the code， the visual copyright。And the mask encoder is these of throats。

ItJust that this comparison is only for big base。W the masco ander。

 you can even scale it to base with large bits。While I think this model is only big base。

And bit large。So the mass encodeder is much easier to scale in very， very big models。

Which is a significant advantage。 if you have a tremendousmentous amount of。你系咪。Okay。

 this is so regarding this idea of adapting。Bairt。Like training intervention vision。

 are there any questions？Okay it's not too difficult to understand。

 so you just have to find a way to assign to discretize to assign like a label or a vocabulary entry or all the passes。

 so this is a core problem you need to solve。So the last part is mask image modeling。

 which is very similar to what weve discussed before。So。The next step。诶。

So by decoupling this bird like training into creating a pretrained tokenizer or。

The network that is responsible to assign。The visual vocabulary， we now try to integrate this。

In one step and doing someupvised learning。But without relying on a pre traineded tokenizer that will give us the label。

 the vocabulary entry for this war。So， this is the most。Eant way to do it。嗯。

So CLS is the classification head。Two to identical networks。

Here online refers to an exponential moving Albert， as always。

 this self distillation approach so this like a teacher model。

It's an exponential moving average of the student， that's why here there are no gradients。

And both models have two heads。One is response。 So if you remove this head and this head。We。

 the method is reduced to the D approach。 What we said。 So now we try to。So this head。

And the loss that corresponds to these heads attaching two views。

Of the same image as that you can see with different colors。So。

We take the classification throughout again。And we。We minimize the cross entropy。

For two different colors， of course， one to different。

 two different views of the same as of why you see the cross。So if you remove this and this。

It's exactly the approach of Dino just with different schematic。But additionally。

We want to take the same view of the Emmaas。One time mask on the past level or the sequence level of the transformer for the student and one time un masked for the teacher。

 so let's just focus on the oranges。Enities。And instead of only。

Optimizing for minimizing the cross center for two different use， we also want to。Predict。

All the talkingken or path based representations that are masked from the student to the teacher。

So this is just， again， cross entropy。So again， you need to have some number of classes。

 so in Dino we saw that they have these 65，000 classes。And here they have， again。

A similar type of overlapclassing。😊，So。As you would expect， again， we have corantropy。

Just between two different entities。Well you can see the next slide。

The first objective is what we saw Dino， so pay attention here we have U and V。

 so two different views of the same image， we pass them to different networks and then optimize the constantcentroppy。

So this is just percentage of week， this is a teacher model and this is a student。But here。

We have n parties， so this sum is over the different parties。

And M corresponds to which bates are masked。So it's like a buy mask。But here we have UI and UI H。

So here we tried to match。the representations。The masks and unmasked representations of the same view。

Wning the first objective？We try to match different views of the same image。Is it clear。Okay。

So this is the whole idea of mass image modeling。The main advantage is that here。

The teacher is beat dynamically with this exponential moving average and this allows the teacher to evolve through training as we saw。

 and so now we are no longer bounded by the performance of the pretrained teacher or tokenizer as we were in the case of this bait approach。

This is clear what is the advantage here that the teacher is trained and this。Vocabulary。

 this visual vocabulary is learned。Some training for the assignment。好。Buts。To classes he's learned。

Throughout training is not predetermined as in the first case。Is that clear？Okay。

Here are some obblation studies。嗯。I would say the most important ones are how to balance these two losses in the end。

 they use a weight of one。Equal weight。 you don't need to come up with。스 안 수도。But in those ways。

 and the second is the number of prototypes， so we saw that during sophomores。

 we have some number of classes。And here they use a smaller number of classes compared to dining in the previous one was 8。

000， but still。Significantly larger than the number of ground truth classes for universities which is 1000。

And here they。They sack for the。For the moing ratio。So how much of the information you have to model？

And you can see again that it's。Significant， not significantly。

 but still between 30 and 40%20 and 30% so still。Larger than the。Baired in natural language。呃。

So this is smaller dec。So， very。Lfe approaches in NSP。You have a 5% masking。

Then the master the encoder。That reconstructs everything on the image space。75% mark。Then，北。

ButRelies on。呃。This predefined tokenizer that assigns this codebook， it has 40% mark。

And the last approach， which is iPo is。Debriation。But it basically master much modeling。Invis。

But the teacher is now trained with self distillation and the vocabulary。Is the number of。

Enternce in the vocaby is predefined to 8，000。But the assignment to those。

Classes or entries is learned during training is I think。30%。

So it's still significantly larger than in any case all the time， you have a larger percentage。诶。

So here I want to make a there is a small。Disrepancy between linear probing。And fine tuning。

 So I want to ask you if。In case it's not like if you have a gene task like masscor and discriminative tasks like Dno。

 so let's say we have just these two methods， which one。

Is more likely to work better during linear probing。Yes， this woman has just gone。Yeah。

 the discriminative one， okay， there's no real answer。

 but do you have like any intuition as to why that may happen？Because对。ごさ。嗯，也其。Yes， yes。

 So they try to。Asign。The views of the images is into the same probability distribution of classes。

Why the master doesn and cold there， so cross entropy？Again。

 there is no theoretical justification behind uses just。Some， let's say speculations。

When you use this cross entropy and you have to decide。

Not for exactly for one class because it's not one hot distribution。

 but a distribution among classes。The amount of information that you need to。

Sustain from the image is significantly smaller compared to reconstructing the whole image。

 so at least 75% of the image， so when the network is trained to reconstruct the image with an L2 loss。

It's really， really likely even though we have no theoretical work for that。

 that the intermediate features contain much more information。And features that are maybe useless。

Inside this representation。 And that's why you need to find you。

They call there or their presentations。To have。A very good downstream performance。While with Dno。

 it is hypothesized the intermediate representations that you learn。2。诶。Less redundant。

 they're less related。Some information needs to be thrown away to learn this representation。

For the pretext task。And that's why I see significant difference between plots and papers。So， here。

Hes linear probing。And you see that there is no mascoder or vague in this analysis。

And you can even see here the numbers。3。So that the upper table is fine unique。

And you see that these two methods are similar or even。So everything is in the same range of values。

But here， when you stay in the linear propbing case。放 you。So here when you are in the lead program。

是哪里有。You have。Large differences between the different models and this。Mustet based approaches。

Are not even in the same。That's why you go see these。Bit or past encoder in this graph。

It isn't clear why the differences are。Why we have a much stronger difference when we do linear probing。

And。Yeah， the last part of the top。I will try to keep it sort。How they recently used these eyeballs。

Approached as a baseline and did a lot of engineering tricks on top to reach the new state of the art accuracy with the new state of the art method。

So。I will try to emphasize on the most important parts。So the first。

Very important optimization or improvement is to replace the centering approach。哦， from the。D know。

We had this century。好啥。Which was on the features of the picture。So， over the。

You take the average features over the bus dimension。To create a centering parameter。

 and then you subtract these from all the output features。

And this was a way to avoid this mode collapse as we saw in the previous lecture。

And these sink or knob bats。Normalization， but normalization。

 it just means that we apply this operation along the bat axis again。So we try to balance。

How the samples of the mini pads are distributed。And they refer to this as a。

Specific case of the optimal transport problem in the， in the standard literature of。

Computer science。So they have this iteric method which tries to estimate these。Q呃 star。

And if you want to take a look how this works。诶 is诶。In essence。

 try to we apply some raw and column based normalizations the side。

 on the bats dimension to kind of balance。How the features are distributed within a mini box。

So if you want to look that up in the literature and here is some code on title for that。

And interestingly， when。The offers of D or tried this， it isn't show significant improvements。

And even though you don't have improvements in terms of performance。

 you have a more stable behavior that allowed the offers of the next version of Dyino to train the network with less hyperpar tuning and larger butt sizes。

And the second， most important。诶。3。Is this a regularizer？

So let's start from the very beginning because maybe it sounds too complicated。

 what do we mean when we say regularization in deep neural networks in general？What made。Yeah。

 wayade decay is one technique， Yes， did you remember how way decay works？How it works。

 Do you remember athlete？Yes也。With。Yes， so not meaningful it doesn't allow the weight to have large values。

嗯。You want to say something。Okay， so regularization is a general。Let's say pro。

To machine and deep learning。Does anybody want to give some explanation or regularization？Yes。😊。

It's useful for reducing the model capacity。Yes， so we use the space of all possible。Soutions。

So solutions in our case would be all the possible sets of different not hyper parameters。

So say you have c得。Like 10 million parameters， we have an infinitely large space of combinations of these values。

That they can taken regularization helps you to not help。

 aims at reducing this number of all the possible solutions so it leads to。

It allows you to search a smaller。Space of solutions very， very rapidly。诶。So， these。This objective。

 disregization。As to。Okay， let's first discuss a bit about。The properties of the hydrosphere。

For the feature space。So we discussed a lot。诶。你先有 lot objective。哎。

We had two very important properties。So let's imagine even this is two。

 let's imagine the hydrosphere again， so everything all the vectors have like a unique magnitude and they are l normalized。

We said that of the Sr objective is theoretically backed and it has two。Quite nice properties。

On the feature space。Do you remember。The the two properties of。

How the features will be distributed if you train。With seems CLR for images to different orientations。

This was like yeah， an explanation。Yes， that you like。Yeah。The whole distribution will be equal。

Roughly， roughly asymptotically distributed uniformly in this hypersphere because it's the only way to push everything apart from each other because we only push it together use of the same image。

Oh， this is。谁啦哇。2，3。4 plus5 was on。And in the same time。use。one。谁 you啊。And you too。

So the views that correspond to toto hoistic transformation of the same image will be marked。

Qu are sufficiently closed on this feature space。At least closer。Then in the supervised case。

 that's what they showed with some both experimental and theoretical results that they presented a couple of weeks ago。

However， during this cross entropy and this pretext task that we saw， so basically cross entropy。

Between different。Features and self distillation。 there is no such analysis that one can perform。

 We cannot guarantee in advance。But we will have this behavior which we really desire。诶。

And the way to。Come up with a trick to go closer to this to mimic this behavior one of the ways was this centering operation。

I think I removed it so the centering was a way to kind of distribute and push everything a bit apart so that we don't collapse by。

MLike by mapping all the vectors to。Independent of the image in one。Class。

And this sink or knob is another way to distribute at least on the mini baths because we only have one mini bath during its iteration。

Of training where we perform backward propagation。 So there's another tip trait to kind of distribute everything。

说 that诶。ItIt would lead to maximum entropy。This is an iterative method and the number of iterations is usually three to between three and 10。

 so the more iterations you do on this method you kind of，For lease。

Unior spreading on the bat dimension。And this co utilizeizer is a very recent。Method that。

Aims to mimic this kind of properties。So let's see the lost function。Okay， this。

Okay this is a strategy。Whatever。Okay， so everything is again added to normalize， so we have the。

In this case， we don't。Since we have this regularization。And we want to。 there's a loss function。

Can you guess if these X， I and Xj come from the student around the teacher and why？

So this is a loss function， so it means that here we want to propagate creating it。We had you。

 So this will be。We need to consider the student outputs here。As opposed to the previous scenario。

 centering and synron normalization where we。Do this on the teacher side where we don't have any grades。

嗯。So what do we do here？So let's say we have two different dog breeds， class one and class two。And。

And during training， these two。Cllasts that let's say， they correspond to。

Very semantically similar data。For example， two dog breeds that on the downstream that we would like to separate them。

We would like that they start to get close with each other。

 so even though we want to maximize between these two views。And these two views will say this is U1。

图。So these two representations tend to。It say called lab， they tend to get too close to each other。

Which may lead to training instabilities， most collapse， and other other undesirable behaviors。

So here， let's say。诶。I number two。1。Make it。So this is number one， this is number one。

 this is number two， this is U and this is B。So let's say V1 and U1 are the representations from the student。

 and V2 and U2 are the representation from the teacher。I give this on purpose so that least。

Look closer。So， we're trying to push。Even though。诶。Lets发。F， whatever letter want。是这。么是。考别嘅建议啊。

So during all the different student views inside the minibars。So one just correspond to the student。

 we try to find。This mean operation just tries to find。

What is the closest vector to the reference one， so let's say we take as reference Xi。

And we see that you。A V1 is the closest to U1， and we only push away not at all the different pairs。

But we push away on the feature space。Only the one that are the closest。

So we would only push away V1 from U1。How do we do that？诶。So in cross Centralro B。You have why。say。

Target。En love。Prediction。So what is outside the lo？

The prediction tries to mimic what is outside below。So in this case， this one divided by N。

Is a vector of a uniform distribution。So this distance between the closest pair on the feature space tries to follow the uniform distribution。

 so this is what I did by pushing away。Only the closest pairs on the feature space。Is that clear？

Okay， so this is a spark trick。And if you don't。Have these mean？呃。

Probably you push everything away from each other so we will have this type of collapse where we have a sort of uniform distribution with maximum enthtropy and the model cannot decide which class to assign。

For its。Example。So it's very crucial to only push。Push away the ones that are tend to go closer to each other is it clear that without this mean this operation will not work？

Okay， this is one of the most important and as you will see。There are other tricks。

 but there are more engineering tricks。So I will just skip them for now。So this di will do。

Starting from the previous baseline of this。And incrementally on the large。

With a large model and a large lake， so they incrementally add in different ways either to make everything more stable or to increase the performance。

And if you see thisregization on the picture space was one of the most critical。

 at least in terms of。KN accuracy， so KNN it means。But on the downstream task， I see the。

I take into account the K， let's say， 20 nearest neighbors， and I do majority voting and take。

They as the label of the test data based on the 20 closest training data。

And you can see a platform from audience and hearing tricks。This is the core。Objective。

 the core trick or regularization or loss function that had the largest impact on the nearest neighbors。

诶。This simple no normalization。Which is a combined。诶。

A combined technique along with scaling out the bad size。So these two， you can。

P see them like as a pair。So by increasing the pad size and using the sink or noob。Let's say。

 normalization in the paths there。Aes。You make everything much much more stable that would be that you would otherwise need different tricks。

都媒体说。The other are just engineering tweaks and paper barmeter services。Bness。Have here。Yeah。

 we will cover this in the next lecture。 I don't want to push you off mat。

 I will just let you see a couple of。今ま sahus。That we would use as datasets to not only rely on the validation accuracy of humansNe。

 but see how the model and the layer representations perform into more challenging scenarios。

So we'll only take a very quick look on the evens。So this im A stands data for adversarial。诶。

Refers to a set of images that neural networks have a very hard time recognizing the real objects and they tend to confuse。

The the object， the。The class。With with something else。 So the red one， as far as I remember is the。

The prediction， which is always wrong。So for some reason we don't quite understand。

 I think it's the result from CNNs， but patient transformers are equally susceptible or more or less。

In the same case， accepted the two recognizing。To not distinguish to not classify these images correctly。

 and on the black， like Co squeal is the real class。So these are some typical examples。

And this image O refers to， as we call them out of distribution samples， so samples that。

Are really different。Semanally and statistically， or。Iither one of them。

 and this is an example of a photosphere。呃， which is。

Something that the has not seen during pre traininging on innocent。hy诶。

And it tends to be fooled to the body is getting fooled and it directly classifies with a very high confidence this as a jellyfish。

These images are what we call。Natural adversarial examples， so very difficult examples too。

Classify within your network。Im of R are different renderings。

So we use some side transfer techniques。This texture here indicates the type of rendering that you apply to the initial limits so that you distort。

The style you still keep the initialL image， for example， this would be a SA。

When you try to apply a different type of rendering。And you want to see how the network。

If the network can still be invariant to different rendering types。The last one。Yeah。

 these are algorithmically generated corrupt images and the text。Indates a different。

Transforms that you can apply these animals with a very high brightness。

 animals with a very low contrast， blair， different types of blair， the ocean noise。

So this is another subset or Enet。屎。C refers to these kind of cor optionss or perturbations。

And the last one is。Sket is drawn from humans as far as I remember。诶。

With classes of correspond to Amazonaz， but。Sketchy so really abstract。See。

And in the next one or two lectures， we try to see not just how we perform on EsNe validation set for vision。

 but also this， as we call them robust studies， so how robust are the different representations if we。

Perter either naturally or adversarary these inputs of the network。嗯。So as I remember， yeah。

 that's it for today。我不要带。Thank you。