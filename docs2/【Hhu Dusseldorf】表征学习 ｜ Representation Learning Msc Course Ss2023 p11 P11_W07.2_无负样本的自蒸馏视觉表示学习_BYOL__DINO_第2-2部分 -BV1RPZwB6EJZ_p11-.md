# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p11 P11_W07.2_无负样本的自蒸馏视觉表示学习_BYOL__DINO_第2-2部分 -BV1RPZwB6EJZ_p11-

ISa this is the golf product。So if these are l to normalize， this is one。Right。

Because after a de normalmalization， you have a。This is un type for spiritear。租。书。

And this is basically cost science stimuli。I assume that these vector are already normalized。I agree。

所以第三个。Optimizing this or optimizing this is exactly the same thing。I think its too correct。Okay。

 this is the idea， I don't know if there's many some small marketing stick。系啊。And we still keep。

The momentum is again， the financial moving average over the parameter。Okay， so now we will see。

How we avoid collapse， which is these boxes of centering and sharpening。

 this even it those sharpening， I will explain what they mean with centering and sharpening。

But it's important here to highlight that。This was the first work。

That also was not dependent to bat normalization。So， here we are not。

Depenent to bus normalization for the first time and for the first time。

We are able to train vision transformers with these architecture。

 so even though vision transformers already existed for two years or something。

 this was the first work that was able to train with subupervised learning on the vision domain。

 a transformer network。Yes。其中。This doesn't rely on the。

Does that mean that you can also use way smaller adventurees？Yes， here you can use small， much。

 smaller， batch sizes。呃，我认这。級先がしま。Bization has a lot of disadvantages。诶。嗯。So。

Specifically to representation， selfupvisal learning。We have some free training distribution。

 some unlabeled data， so these are like the images that we train on， right？And during pre training。

Basically， such supervised learning me。We learn。Some means some standard deviation that we will use for infrared。

 let's say when we see new data。However。This distribution is。Very different from the。Let's say。

Downstream tasks， so that the distribution of the downstream task。So during supervised learning。

 this is also a problem because the training data and the test data。

Are not always this II independent and identity distributed， but here the gap is much more much。

 much stronger。呃，稍微。And this leads to， like。Different means which don't。

 so these mean when you learn， okay， I didn't cover this one。

 so during training you compute this based on the statistics of the bath。Here。And on inference。

 because you are not guaranteed to have any available bots you can even do inference with one。

 you keep an exponential moving out again of these parameters。So these basically the statistics。

Of the features。The pre training versus downstream tasks or in supervisor advertising training data versus test data。

Is very likely to be different。 And here the。This assumption of IID doesn't even hold because we just take a more general data set and more in the wild cellular dataset set。

And。It's also quite。告你。I don't know if you were in the last lecture I discussed about。

So when you have small batch sizes， this estimation is very noisy。And when you distribute。

Like a training job between multiple GPUs， in general workers， GPUs， GPUs。

 it depends on your resources。Then you have to decide。If you want to use the statistics。

So if you have a button， okay， I will do more work。So if here you have a mini box of B images。

It's warje。 So this is a DU。So each worker has to see one quarter。我是 data下。So this mean。

Will be computed。To a quarter of the data and the smaller it is， the more noise it gets。

 and then you have to decide either to keep。The individual means。Or if you want to aggregate。

 and if you aggregate， it's much， much slower because this GPP used me to communicate。

So this is the synchronized bus normalization。Where we aggregate the statistics？

Which makes everything much more slow。All right。嗯。I also talked about how the vision transformer is using layer normalization。

And how different is layer normalization in vision， but I to go deep into that。

 Let's take a look at centering first。So centering by itself is again an exponential moving after。

 this is the solution to most of the problems， but here it's not over parameters of a network。

But over the output features of the teacher， so T course is a sub。Porsponding to the teacher model。

So I use this notation from the initial paper。So before we have this alpha， now they would call it M。

And this C is that a center。So this is the average over multiple iterations。

Of the features of the teacher so before。So， much。We have。An estimate。A dynamic estimate。

 so it changes it iteration of the average of the output features。And what we do is just sub these。

So we take this z。And subtract these。Let's say this back door。This is an average feature vector。😊。

Very， very loud。But you can see from the equation。And then because you ask again。

if you want to implement this。Very similar to bus normalization， you also have to collect。

All the features from if we will not do this in the exercise， but if you had mood to be used。

You have to collect。Basically to aggregate all the different features。And take their options。

So everything that is computed over the bad size dimension。

 you have to rethink how you implement it in。In a let's say challenging real life scenario where you have multiple GPPUs or TPU。

Even though it's not directly related to the method and the math。In practice。

 it would take you even years to train these models on large scale dataset set with the same interview。

So you can imagine。第啲一啲。And GPPUs do things and time faster， which is not the case。Ideally。

 this would be the case。So something that could be trained in 10 days， if you had 10 GPs。

 you could train it in one day。And yeah， the next question was， okay， here， we have this head。Again。

 is MLP。Where in the end， we。Assign。Some distribution over classes。Which is a soft much operation。

But how can we choose？How can we assign features to classes or prototypes？And。I don't know so here。

 very here。So they do this。Ablation study， and they using 65，000 output classes， which is。

And muchs larger， like Inet has 1000 class。嗯。Yeah in general， you have to pick。

At least one order of magnitude larger than your actual。Ground rules， let's say later。

 So if you have like separate for them。You have to pick at least 100 if you at 1000， at least 10，000。

 let's say this is like a very hard estimate and rough estimate。

And then they were the first to show this dynamic of mo collapse。And identify。

These two cases of mold collapse， which is exactly what we saw in the downstream task of IAT's cly。

So I don't know for those of you。don't remember， I would repeat anyway。嗯。一本。来。我啦。说下 some。

Classes or clusters， what we saw in a classroom was that。We want to learn exactly。The amount of。

Classes that the data should have， even though we don't know it。活当系理佢地噶。And。

When we assign everything to classes， we can have two different scenarios。We can have ten0 glasses。

The first is。The uniform distribution。So let's say for its input。Email， features， whatever。

We have like a uniform distribution of our glasses。And of course， the uniform distribution。

Has the maximum entropy。So uniform distribution， maximum entropy is when we apply just the center。

I will talk about sharp， but you have to。诶。Draw the connection between centering， which is basically。

They take the output features from the teacher network。And then subtract DC。

 where we see this exponential moving average。So this is when we just take the output of the teacher。

 use the teacher here。Make sure。嗯。So centered by itself。Kind of balancing the statistics on the vers。

呃 lead to。The uniform distribution， but10 classes， one out the 10 maximum。诶。

And you can see a similar behavior of K atpars。In both of these sharpening in centering cases go to zero。

The second case is independent of the input to assign all the probability in one class。

So if we have 10 glasses， we always assign。Class4 is a probability of 100%。

 and this would correspond to zero entropy， which is basically when we do sharping without centering。

 so when we remove the centering，And apply softs。We get this zero entropy。For all the。

It depends on the input basically it doesn't matter if it's。From the same image or different image。

And the third case is basically what's happening in this approach。嗯。We first center the features。

But then we apply a temperature scale soft box。Both。To the teacher and the student。

 but with different temperatures。I don't know if you have the equation。So， we have。

If I have a mistake it not， so here if we use the subscript of the teacher。

 we have the teacher features that are already centered and if we use the subset the subscript。

Of the student， who have the student features that are not centered。

 so this already created asymmetry。呃。So， the second。Frerick。

Is the impact of the temperatures scaling before the soft mask。get somebody remind remind us。

Even in general， if we have these classes， what is thetuition behind？The temperature。Yes。

 if you have the small of a temperature。Let's say what pointy these flex output。Yeah。

 more sharp Yeah so you use a very low temperature this the result of the soft mix is going to lean towards one class。

 it's more like one。Yes， perfect。Okay， so in both cases， the temperature is smaller than one。

But the teacher has a smaller temperature， the have， yeah， the temperature of the student。

In practice is 0。1。And the temperature of the of the teacher network。诶。0。0， what is it7？So。Perfect。

Training would be to have the same temperature。At least it brings the teacherer temperature as smaller。

 as closer to the student to minimize this diverse。Derence。呃。

But even this in practice may lead to unstable results。

 that's why what they do is like they do this warm up， so they start from a much smaller。

Deempparatory practice is 0。02 or 0。04。And during the first Epo。

So the first Epo is like an a traditional of the holiday innocent， they linear scale up。From 0。

04 to 0。07。So even in the beginning。We need a smaller two。

Baically up the confidence of the teacher to create this dynamic that one network needs to be better than the other one。

Okay。CollAny questions regarding this study？Again， it's。

It's really connected to the two cases of collapse we discussed on Is classrooming。

 so these are like they can be regarded as。Overlasting based。Suchupvised learning methods。

So that's why I wanted to show you this application of clustering。

 even though it relates so much to the collapse study that's happening here。

And this is the dynamic that you asked me about。😊，So this is during training， okay， there laser are。

After example， and this is the。The validation I。So you see they don't evolve in exactly the same way。

 but when the student gets better。And it's updated with back propagation。

 the teacher is following up。The improvement。And you see also in the beginning that the advantage is almost nothing because they both start with random initialization。

 it's just that the teachers sees like a bigger crop of the。Otherwise， the transformation are simple。

 and this is really surprising to me that okay， just using the previous iteration。😊。

The feature is does the network in the previous collapses。

But even taking the average of the teacher model from the previous Et even though it doesn't collapse。

 it doesn't work as well as the exponential moving average。

 so momentum is exponential moving out of the parameter。仲要跌得嚟啊。So here they try different features。嗯。

So， this is without。Without gradients， but it does that we stay like an identical network。

The the the。The model before it gets。Updated with backification show the same network want iteration。

On the bus。So it always says random。So if we are on iteration 100。

We use the teacher model that was on iteration 99， just a copy of the print， son randomon。

And then in the second one， you still have the random one from the first。第三个。

the first step it doesn't apply， but on the step N。

 you use the model as it was in the iteration n minus1 the weight before they got update it。

 but the interesting part is here， even if you take an average with the previous Epo。

Probably this is an average， I'm assuming that this is an average not like an exponential moving average。

诶。It doesn't work as well as having this moment。别。应该是。They just keep yeah， this is not unsupervised。

 they take the checkpoints from each apple and they do linearer probing at each step。

 after each apple they store the checkpoints and then they do。

They evaluate directly of the downstream task。Which here is like email classification on emailsnet。

So it's not directly。Like supervise evaluation， if you like。

But what's important is to understand this dynamic。Between。

Instead of knowledgeillation and a frozen teacher。To a teacher that is beat。

In parallel and both models improve。Any question here？How important is it that the。

Teacher sees like a bigger picture of coffee and hyperbarmeter。

AlThe teacher always is a bigger and that's like essential， otherwise， yes， yes in this method。😊。

IIt's essential。So I think the hyp parameters for vision transformer is。From 5%。

Something like 25 or 30%。So this is like the range of the local crops for the student。

 and then 25 to 100% for the teacher。The idea behind that that the teacher more or less learns like a global view and the all like global。

Yeah， it has more information。So it has the advantage and then the cross entry be basically here。你是。

He teacher is student。So this is more like your target。So this is like the target model。

It doesn't have like this one called distribution， but it's already sabeded and already has more information。

The the the idea is to。Ultimately， you just want to create a smaller push here on this orange line in the beginning。

And then with this way of iterly alternating between updating the student with back and the teacher with EMA。

You achieve this dynamic that both networks evolve through training。

Could you please please appreciate。Which part。At the beginning， both networks are randomized。

 so you want to somehow give a smaller advantage to the teacher model。With the temperature。

And of the bigger crops。Any。And here you can even train with a small but size of 128。And。You don't。

你 don't see a mode collapse。Ask given that you have found the balance between the temperatures。

So if you switch to medical limits， as you would do in the exercise。

 you need to establish the balance with the temperature， but we probably just provide you with the。

I prefer啊 just不来。首先为而。Even even less sensitive。To the bad size。 So I told you would be all。

You can train even with CLRric starts with 2，000 badt size。

 at least with PO and you can train even with 512 without significant performance deterioration。

 and here even with small batch size， you can work it out。Okay。

 how does the prediction look like Yeah， this is because during the cluster you ask me。

How is this clustering head look like and it's always like an MLP with two， three layers。

YeahIf you want to look it out， they use a very specific architecture here。

 they provide some operation studies。嗯。I don't think it's extremely effectiveing if you use。

So three layers， it means that this amount has three layers， two layers。

 and then this linear layer has。It'sOne more leader video。

So this means that the MLLP has two layers and four means that the MLP has three layers。

And here is the hypoparmeter， the hidden dimension is 2000。At the bottom technician insurance 256。

But the most important is that it showed that bus normalization is not really。嗯。

An important component to avoid mo collapse anymore。Okayケーございますあ。

This is a completely independent improvement on the literature of supervised learning。

So they found that instead of having， we always talk about two views。So we take an imagema。

 we take a crop， and then we resize and we have two views with different transformation。So。

 to speak up。You can apply this technique， it's called multiple local and global crops。

 so just of having two views of that are reside of 224。They also include in general end times。呃。

96 by 96 groups。And in this way。You are not restricting yourself to having like two views of the same image。

 but effectively eight views。And to。Compet safe for the additional complexity。

 they resideize the use to smaller ones。But you still are able to learn better features。

Measured with a can or snake groups or everything。 So this technique improves。

Most subupvised model by at least2%。 I think the only exception is this beyond。Soれ么。Yeah，6 59。

 all the other models so kind of。More stable versions。Okay。

 this is thick called Dr Le are significantly improved with this technique。

And you would also implement that in the exercise。嗯。So for this approach， cornino。

 these are like the two global crops。And this would be the six local crops。

So even though they are sized to smaller。Sppatial measure， they also have these different arrays。

So from 5% to 25%， I the views corresponding to the ones that are at six times 96。

And these are crops。Like the scale of the crop is from 25% inside 100。

I already mentioned that this was the first approach that was able to combine the advancements of。

Artectural advancements was basically a vision transformer with selfupvised learning。ok。

That's it for today， I hope to some kind get question。So。If we take a look back。

 we start from this pre textex task like。Predicting the rotation of an image。 And yeah。

 then we wanted to avoid that and。Protroduced by using negative samples， negative examples。

For example， CLL yes from rotation basically we go to contrast flow。原等你。

And then we want to avoid this negative samples using this teacher student architecture。Yes。

 there any work。开三分。Yes to by data implementation。Dtamentation。Has not been able to。

 We have We are not able to avoid this。呃。Because。This is the way we inject。Information。

Yes but with yeah， it's a strong human prior， so you can imagine that it's sort of the human supervision。

 the prior is what we define。As what is important as an augmentation。

 I don't know if you remember we discussed it。Whatever gets transport in the augment。

Whatever survives， let's say the augmentation。Is the the the。The thing we want to learn。

 so how we distinguish between these two views， even though it's flipped。

 if though the dog is horizontally flipped or citer statistics。

We still want to map them do the same thing。So this is the biggest gap between natural language and vision。

And。Ideally， we would like to have some more general application because these pipeline are。

Very well configured and very stable for natural limits。But we cannot extend them to。

I showed you this application of depth。Having like depth images as input or medical images。诶诶。

And it's one of the talents on the next exercises you will work directly with medical images so you can always。

Just adopt these pipelines。And we also have different problems and applications with。

Xray images and stuff like that。There is not even the notion of three channels。

 or I have worked with femas that have five tunnel from some lab microsco pi。

These augmentation don really are not really generalized good。For example。

 the saturation parameters that we play on Torch vision are only referring to naturally limits to RGB based。

But color glitteriting， which is basically playing with the brightness and the controlrums。

 it can be applied in any channel in any type of images。Which is the most general to。

Brightness and contrast。Zittering more or less plus。Cropping。

Or random re crop or random crop is usually the strategy do to go about。

Even in one of my applications。We had these。Okay， we had。5 tiny images。Of sense。And we find out that。

Her randomized crop didn't work。诶。Didn't achieve superior results compared the fixed crops。

Because in this domain。The size of the cell may indicate their toxicity or heterogeneity or features that would be interesting to learn。

So these augmentations are excellent as long as you stay on the natural imaging domain。

 but you always have to rethink and redesign very sensitive。Yes， to the domain and the application。

 also in this application and we included。All the images from the microscope where the fixed magnification came with。

We say the same zoom in and zoom out in terms of a camera。

So this could be identical to having all the objects on Enet one meter from the lens。

 is is what it means and in this case we saw no improvement。

Between random precise crops and just fixed random crops。Any other questions？Okay。

I think I also want got。A small connection between。If you have some time， okay， three minutes。

 if you have some time， a small connection between these be models。And the vision transform map。

And everything we talked about about distillation tolkens and mass tokens。

Maybe it's not the correct time， but。I just want to emphasize that the same thing did you did in the bird exercise。

 just replace some tokens with a mouth token and then predict。The same， the correct class。

 which basically this is called。Must。Language modeling。呃。因此。More or less。

 the same thing we use vision transformers， so we have multiple to tokens。Instead of masking。

In the sense of classification。We have a new token， which we call CS token。

I think we also have this in the garden of exercise。😊，So this would be all the parties。诶。系。SV。

be squared， this is the pot size patch。And then we have as many outputs， plus one， which could be。

The representation corresponds to the classification tool。So， this will be the。

And this token communicates with all the other tokens inside the network， and then we use this onewa。

To do everything related to cross entropy， as we would do。1 bed。So， here。have is in much。

So this is the， the vision transform model。The output is。

As much as the input saw the number of the sequences。

 and we just take the first the first the representation of the first token or the sequence。

 which refers to this。Which is the output of the classification function。

So the other classification classification token is the only one that will be used and all the other representation are。

Not taken into the lost function。也算。Yeah， at at each step of the transformer layer。

 you have self attention， which is a global operation， show all these tokenins。

All the information from this token is routeutd together。

 they need to be combined information to produce， even with one transformer layer。Their presentation。

我你你。Without are white。Ha to take into account。All the parts， projection。

 all the other tokens of the sequence。So even though we don't directly use the output of its paths on the vision transformer。

We use justice。This one token， which is like more global。So this what。It's not shown here。

 it's like a more general approach， but during the vision transformer where you just have one output。

 so its P1 and P2。Are derived from the classification to。That's it for today。Thank you。好。Yeah。

