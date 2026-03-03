# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p17 Lecture 17 - GAN, Video, Point Cloud (MIT 6.5940, Fall 2024) [BV1c8wNe1ErX_p17]

Okay， good afternoon everyone let's get started， so today we're going to talk about efficient Gs。

 videos and point cloud understanding。We have talked a lot about general purpose application optimizations。

 so today we're going to talk about the specific application optimization focusing on GN for image generation。

 video understanding and point power。So why we choose this application？On one hand。

 they are very computationally heavy required a lot。On the other hand， they have a lot of redundancy。

For example。To the spatial redundancy for videos， there's temporary redundancy between the frames。

 also frame are similar， so it's very wasteful to use 3D convolution to do that。

And also for point cloud， there is also spatial srxity， not every point is actually occupied。

 so there is a lot of rules。improvement。This is a journal。We will first introduce efficient cans。

 including three techniques， gun compression， how to compress gun models， any cost again。

 how will apply this one ball technique to use a smaller gun model for quick additive and prototyping and finally using a larger one for finalization。

And finally， the data efficiency， how do we use fewer number of images to train scan models。

The inferable augmentation will be education。Second chapter， we're going to talk。Video understanding。

 particularly the TSM， the temporary shift module。Finally。

 we are going to talk about efficient point cloud understanding。Including a point box。

And also be future。So let's start with the first part， efficient camp。

So again stand for generative adversarial networks。

 it is super popular technique for image generation， it consists of two parts， one is a generator。

 the other is a discriminator， so we train the generator so that the sample cannot be distinguished between the generator image versus the real image。

To fool the discriator that we are the same。But if thisri term。

 the tri purpose is to make sure it can distinguish。Between the trina the real image versus the15。

So therefore， there are two large terms。To accelerate the inference。

 which should we improve efficiency？Should we compressr a generator or should we compress a discriminator？

So as generation type， only the generator will be used， right。

 the discriminator will not be used at the inference type， so the purpose。

The focus of compression will be the gals apart， and this is what we need to scale up。

So this is a little bit of background。Of cans， so this is learning to genuine digs for a。这。翻我。

Weistic images for hundred0 indigenous。AG has two components of two categories。

 one is unconditional gam， the other is traditional gap， so for unconditional gain。

 we use random noise。Feed the gap models generate the random noise。To generate the output。

Versus so conditional gap， the post discriminator and also the generator are conditioned on provided labels。

 either the class label or a segmentation lab。し況？So this is a different。

Condition versus unconditioned。And this is a famous work。

 Gaul Khan from N media a years ago for drawing。啊做 a stroke down the American side。

It can render an image， can draw of mountains。And then it'll feel about that。

And change the color to the grass and get a river。So such a kind of task。Prefers real time possible。

 but G is pretty heavy。So this is another example。D就是 model呃地就是 model从你。就。Here。

 we're going to talk more about addition models。So although can is pretty powerful。

Such shadow model is much more computationally expensive。And these recognition models。

For example example here， we see the number predators。Mobile app， Ra 15。

These are discriminative models。4。2，25。Meing parameters， but and 93 million parameters。

Versus of fs below。Be like below four。G x versus 400 gigms， so it's pretty computationally expensive。

 which motivate us to compress these ga models。And let's see。

 how can we apply what we learned so far to get compression。So here we have a pretty large。在着聊天。

We want to compress it to be smaller by reducing the number of panel。

So here we try to apply three losses and one is the reconstruction loss， for example。

 if we want to turn a horse into a zebra， we want to do pixel Y。

 calculate the loss pixel Y for each pixel to make sure it looks like a zebra。然后 also为的资钱嘛。

Since the final reconstruction loss at the end， it's not enough。

 remember during de we talked about also match the intermediate feature of mass。So the future map。

 the channel number is different， so we have to learn one by one conution this projector to project between a large resolution。

 a large number of channel versus a smaller。So that's a decision loss。没有。Finally。

 there is a conditional ga loss， the original ga loss。So finally。

 we put out together these three lost terms altogether。And here we can use the West wall approach。

You train a super network， which is similar to what you did in like three。

By changing the number of channels from smart channel to large channel and randomly select the number of channels。

And the反。To recover the accuracy。So finally， we can perform neural rocket Engine search to select the number of channels that fit our littency requirement。

So this is the result， because it's the pixel to the pixel model。Given the import shops。

These are the ground truth images。This is the original model， pixel to pixel model。

 that in the shoes。Make it 11 times smaller。The quality is quite comparable with the baseline。

On the right hand side， of course。ほ死掉。はスパれ。あ台い。AndThe kill dropped by the same， which is pretty cool。

は議ら。example compressing。高干肯那个三 input。ground truth。This is the original Gka model。

 this is a constructive one。And this is a video demo， showing the speed。Of course。

 the zebra the floororral compression and afterpirin。So this is running on。ジセ随の況もま。Originally。

 it's very slow。I mean about 12 for this percent second。包。Once to the game on the bottom。

 now I kind fully this。あ質ろ。所你们 horse谁 to a基本。AndRning real time on a mobile GPPU。

Okay so that's scan compression， now let's switch here to talk about any cost scan for image editing。

The motivation is that gun can be used for image editing， but the generation is pretty slow。

 make it difficult for us to run this image editing interactively on our laptops and tablets。

So the algorithm here is given an equal image。Projected into a he space， into an engine space。

And then we feed the point in the action in the space as input to the generator。

And then go generate the image。By tuning different dos。In the late space we can control。Smiing hair。

Gsses。嗯。Apply imageality by changing validation space。However， this is pretty slow。

 which motivates us。Find the way for a quick image editor。So how can我 do that。

The re example motivated。So people can get very fast preview by reducing the number of sample risks。

For example， this is the race。Part 12， 128， 64。although the neutral quality looks worse。

 but it's pretty quick。But here we want to make the computes less number of computes。

 but also the quality hopefully as good as a full model。

 so can we do the same or even better for gass？I say motivated us to think about the once smaller network so doing everything we can run a low cost smaller sub network。

We have a super network， then we have a sub network。Do anything。

a smaller subject network running at low cost， just as you did in lap three。

For very quick review preview。And actually we are satisfied with our editing。We can run full cost。

 the full model。W a slow but with higher quality output。也说的这个办到。

Finalized image and hopefully the finalized image versus the preview are very similar。

 they're consistent with each other， okay so that's our goal。And let's see， how can we achieve that？

So in order to specify let's specify what dimensions do you want it to be the wise small approach？

So we want to。乘450。Support different resolution。And support different channel numbers。So now again。

 to let first see how resolution， how do we support different resolutions during preview probably used slower resolution during the finalization stage。

 let's use a higher resolution， let's see how can we make it better。

The conventional work is still again in school， so this is a generator。32，64。

56 were actually to increase the resolution and then field the highest resolution to the discriminator to see if it's real or faith。

And as she can see all the resolutions from 32 to '64， what from 8 to 56。everage to the。

Discriminator。That makes it more challenging because the distributor has more information about the。

It has to be。Either it has all the information across different resolutions。

Make it harder to pretend it to be a real image because for each resolution。

 it has looked like a real image rather than generated。老头付我的这。So now we need to support different。

Resolutionution。So it's even more challenging， we want to make sure for every message that we generate in 64。

 128 or 256， all the resolutions。We can fool the disriminator。Not only the highest resolution。

So what should we do？第二问题啥呃书面法。你原的。B的。一份还子路。It outputput to the discriminator。Any。Here is the264。政府。

Before18 randomly simple， different resolution。To feed to the discriminator。

Such that when we are running a different resolution。From 32，64， all the way to 1 k by 1 k。

 the approach， our approach。this may have better FID， lower FID。Comp single resolution。にせす。

MG G versus， which is all the resolution can see significant in。嗯议。I idea both no resolution。

So the central base multi resolution support very similar to the disriminative model we built。

However， this type an interesting。第两名。So for so听下。It's the only as higher as a it works。

When the resolution gets low。You can barely tell。Yous our approaching smoothly transit。

Between time resolution and。老板怎么？Versus it comes completely false。So this sampling approach。

Its very helpful。Okay， so next。Second goal， let's support different number of channels and we can run a full model with larger channel。

 better quality， higher fidelality versus we also want to support a smaller number of channels。

 make a faster， immediate inference。So here the approach is to sample adaptive panel numbers。

And sometimes what the full channel。The number of yellow here indicates how much channel are we actually。

And so here we are not only suffering different resolution。

But also a sample difference had number of tens， as indicated in the yellow pie。Okay。

 so we don't deserve some inconsistence。For example， this is 100% of the channel。

 this is 50% of the channel。You see actually， they don't look like his other。

The baby previously has a pair of glasses。Now her v is gone，How solve as usual。

 we actually added this distinguish loss。都少不打艺术。So make sure at a different stage。

 we had this disation loss so that the image。Fu channel versus half of the channel still look similar to each other。

So we observe a second problem when we are working at FE where some of the subs works。For example。

 it's 25%。信。25% for 28th resolution， this is from 256。オ。

You are using the same disriminator for a different number panel when。嗯。

Where it's at a couple5 six house。With the channel number of is 25%。I these normally spine。出工气。

And lower resolution。When the channel number is big， 50% and the 5 percent。Its also把茶叶全部个你啦。

MoWithout physical much law approach。Which is showing that not using the same is through curve。

It's not good。A single disriator cannot provide。Inact feedback for different sub generators。

That makes sense if the generator is pretty weak。Pretty slim， very few number of channels。

The deriminatoratorator should also accommodate that。

Using a single disriminator for big and small generator doesn't quite。So what should we do？

The proposes。Generator conditioned disriminator So the disriminator should be aware of the configuration of the generator。

So here this the right hand side is the gl， right hand side is the ventator。We collect statistics。

Architecture of the generator， like how many channels do we have is the resolution？

And we feel it to a and use that to modulate the discriminator。

We call it a geneative conditioned pet ruminator， such that。And scin isn't aware of the size of the。

AndPreviously the problem of saying be swimming the problem now that solve。Even better。

7 reduced to three。So generator condition discminator。Make it actually pretty helpful。

So that's what's unique about this one's small approach。For家。Since SC model has two components。

 a generator and a discriminator。They have to be tightly coupled。

IMake it a little bit difficult to optimize。And next lecture we'll talk about the deus model。

 which has only one model for。So finally， we can see some good results。

So this is the forward consistency and resolutions， so 1124， by 12， 128。Different channels 100%。

So the5% half。但发院不在。So they are very consistent。Transit between。photos是。有块。あす。

Which one has the lowest computation and run fast？So no resolution。alwaysway a resolution motion。

Lowest number of channels。A feel looks absolutely composed。不包。On the right hand side。

 which is the lowest。As we have lowest number of panels。是。F resolution至负差。

So we can also compare a different computation reaction， what does the quality look like。

All these four images are derivative， not real。We can reduce the back by up to five times。

When the power is shrinking， we can hardly tell the degradation of the quality of the image。

Some 8% 59，39。19%。Now we can apply it to photo editingitive。 So this is a demo running on a。你来逃跑。

My book？Actually， that was a couple of years ago， I believe these days。faster。委托代理chan。

The original model is very slow， runs about three seconds， 3。24 a second。So， here we are。Smile。

And also， making look younger by changing the。毕竟一录这两份。まよ。

So here we can control different panels and different resolution。Now we can write it again。

 it's really fast to somewhat instant。shrinking the channel I shrink。然上我。Interactiveing。

 so this is showing the latest。さのスタし。フデースの。把了。full model which take longer。3 seconds。然后并不是。原告。

But look better。反他个里没。How we都。有高的。T you say hair。You make the green。是楚。

Her the polar is really associated。These high glasses。そ我の。大过。There the sliding bar of eye。

And glasses are removed。Finally way we can click finalize together a final high definition image。

But this is open source。And its rather deployable on a MacBook， so feel free to use this。

As part of the final project or discuss ask if you have other ideas。Alright， so as。

Talk about the third part having talk about the computation efficiency now let's talk about data efficiency。

 so trading G requires a lot of data， it takes months or even years to collect a lot of data。

 especially label data。So annotation is pretty expensive too recently there are some automated tools to automate the labeling process。

Still collecting the data is practically pretty。heart suffer from copypyY数。第二层他这。

Data are used for2 with energy models， one of them is iPad HQ。Which contains 78，000。

Post process of human things is。Another popular one is image thats contain more than a million image。

There were categories。We tried training the G model with limited model of training data。For example。

 using only 100 images to create the format。改りさ。Or using 160 image to train。家阵快放啊。我所以还是并为去处以到。下给我过。

So although the original cell can cool from NA works quite well。

If we have a limited number of samples feed it， the quality is very poor given a limited amount of data。

So this is the quantitative result。Starting from 100% training data， lots of images。10%，10%。This isV。

 the I keeps growing， showing the degradation of the quality。Do a less model处 data。

So the current techniques of G training lead to inferior results when the training data is very limited。

And let's see why about apples。So this is in terms of between accuracy versus the e Act。With 100%。

Triing data， both of them， the tri accuracy is pretty good。你边没钱。It's okay。

But if we reduce the training data to only 20%， 20%， the training accuracy is improve a log。

But the imagination accuracy， not even the past， the imagination accuracy dropped very significantly。

说应白。It very hard to generalize。Not to mention if we go through like only 10%。哦，确定被查。

Here the validation accuracy is even lower and another low validation accuracy。

Showing that the discriminator will overfiet。A small amount of training data leading into worse generator performance because the disri is very poor。

 the generator can all work well。睇先卡步。So that makes us naturally think about the data augmentation。

If we have two images。等不看的往里面。Six images by rotating it tinted with different color by prop。

So traditionally data augmentation is a very effective technique to prevent overfeing then the question is how do we augment gap models？

So one technique is to complement the real images。There's a discriminator which train the generator。

Triminator it。One very popular technique is to apply。These artifacts color deing notm。

How applied to our degree？Qu some translation that shifted it by to the top right corner。

Or换 some卡 out。他配。A piece image。If we augment the real images only。

 so thisrimin can take either the real image or the fake image， the fake image is generated。

If we only augment the。only argument for the real image will will happen。Actually。

 we find the generated image will suffer from the same artifact as the。As the。

as we apply the right here， for example， in the generator， you may also look after a prior。

The dynamic you may also suffer from this translation and they also suffer from。

the directly image have a big patch。That is because the this rumator sees the real image。

It's already gone through this transformation or color detering， et cetera。

 so believe the real image should also suffer from such transformation。

 therefore encourage the generator to generate images like that。This is not effective。

Same artifact appear on the generated image。合理属于。fire solution。 Natural solution is。

To apply the translation T not only on the real image， but also on the generated fake image。

so therefore， the three minutes are been。的等20来。It doesn't have to come from a generator。

 but it can be clean。AndThe later applied the translation。诶。

So we find it has very high accuracy on the Tx， on fixed image。The translate。

 the generator image after the translation， but it has very low accuracy on the。On the GZ。

 so this is the GZ good without the transmission。So these accuracy is highly embaled。

Finance optimization makes training very hard because when we are training the G。

 in the training generator， there's no transformation， when' training the D， it has a generator。

A害死了啊。So what we need to do is actually apply the same transformation。

 Also during the training process of the generator， make sure it is different。

 So the laws can propagates all the way to the generator when we are training。

So make sure both the被 imageH。Re image。Apply the same transformation and for the。

F generous can also by propagate。这个这个这的问题。So the solution is by augmentation on both the real and the fake。

This is the real， this the thing for both the deriminator and also for both the deriminator and the generator。

And immediately， it's solve a problembable。The worst quality。So it no longer increased quickly。

 but phase。For the stable， it did increase a little bit because you have low data。

The FI becomes much stable， much more stable。好听个那个。136。And let's see。

 given this low short generation， if we apply differentiable orientation， how does they look like？す。

The Southhan baseline， this is Southan2 plus the Algament。这个是啥还。Images of Obama fans。Now， it becomes。

It's 16 half。对别这个。那是。300。And results much better。We can also interpolate。Across different images。

 so below images are all trained。判里面是。ケ。看照。Different sceneries。

We inter between different seasons between the night and daytime， which super well。

 given only 100 images。All right， so let's take a short break。Before we jump into from met chapter。

あ明ですね。Okay， welcome back。So it's gear to talk about video understanding。

So video is the biggest big I growing in superpaths。1 five hours of videos are uploaded to YouTube。

P se is from elevatedated data。It's very essential for both the power that our edge。啊，本开始。

There's lots of applications related to video， for example， action， gesture recognition。

 scene understanding， video search for ads。And also for autonomous driving。

The interesting new thing about video understanding comparative image is that we need to performly。

Timeproing is very crucial， for example， given a single image。

 we cannot tell whether we are putting something about math to right or from right to not。Only。

 only if we watch。R video sequence。And we tell after we are moving the big from。いそ。

That's the interesting part of our company model。There's also a lot of redundance in Ter followingway。

 so like the background。The paper stay exactly the same， the white Pa stay they're exactly the same。

Only the wholeground。啊，Change。So we should exploit such a redundancy for efficient video processing。

So let's first visit two DCNs for visual understanding and then three DCNs。

And then introduce the temperature shifter module that gives3 disease， performance。

 accuracy performance。By the cost， computation cost that two these years。

So2D see based method in history。A naval approach actually learned a straightforward approach。

Its a sample frames and process。我租地几。And they'll aggregate the scores for prediction。

 either use an average。The max school。Another approach in the history is using this two three method。

会 published 2014。The first stream is the spatial stream。For image， the second is the temporal string。

Which is the optical flow and so off flow is the vector indicating for each pixel where is the moving。

 where is the moving。The optical flow is actually pretty computationally heavy。So it a full stream。

 one is three so stream， one is temporal stream， and thenfuse them。Together。

There's also approach to combine2DC。Plus late fuion， which is LSTM。Tofuse that。

Different eventss from12 from three throughout our CM。しし？啊，有了丢0。G be a final prediction。However。

 I imagine such late diff fusion， what is a problem here。The low level information is lost。

 right since the low level information is。Extractive independently by different。

 only the high level feature is extractive。てや。So let's summarize the pros and cons of 2DN based methods。

So2Dine is very computationally efficient， we can also reuse2Dines trained from image classification。

 image pass。等包括在第二。Aduating the same comenesians。Can now model the temporary information since each frame is processed independently。

St to be low acres。And if you use optical flow itself， it's very slow to compute。

And late futureion can also can oil the low level of temporal relationship。So naturally。

 people think about using3D。For video understanding。So what iss through this union？

The first work by early work again in 2014， a decade ago。

 this work called C3D involved not only the spatial dimension， but also the temporal dimension。

To be convolution， evolve to to space。Multipable ways。Now so。This is the breathing combination。

 not only in the spatial dimension， but also the temporal dimension。

So can join my model the spatial and temporal information by using a 3D convolution to come up over。

あす。But you can imagine the3 days in United。mentioned has more parameters。Pretty， pretty。

So can we inherit？土地声。To。I make it become 3s here。在。This paper is how I3D。initialize3土。

The waves are proed by how image X。And how do we neutralize a 3D C using 2D C that actually is called the inflation？

Inflation actually the idea is to repeat the weight across the new dimension。

 repeating multiple times。To repeat the weights across the temporal dimension for initialization。

 the same weight repeated several times， for example。

 if have a you could have a kernel size of three in the temporal dimension and you just repeat the original2ing seen by three times。

クリミシまた。And the puty kernel now becomes a 3D kernel。

So the pro come here is that we can join my model the special hyper information。

 which is group thing。And can also model both the low level and middle level and also the high level information。

But the problem is that it has very high transportation costs and also the storage costs。

Sore a 3D actually 4D answer for the waste。A lot more computation since we're adding one more。

Actuaual dimension。So the natural question is。Can we achieve 3D savings performance accuracy？

But at two these serious cost。To get the best of both world。And actually， that's kind shift logic。

 a new operation， which is neither 2D convolution nor 3D combvolution but shift。然后他的时候。考试。

And I's see how that works。So this shift operation contains zero fluxs， no computation， zero。

 no parameter， but it can very effectively perform temporal。So let's see this then。

 let's figure out the dimension first。So this is a temporal dimension， we have a T1， P2， T3 P4。

 three colors。Here is the channel dimension。So this is the original cancer without any shift。

And here the depth is the ancient W dimension。So temporal shift。

 you can shift it both from the past future to the present and also from present to the future。

And so here， the first channel， the second channel gets shifted。

Third channel fourth channel decide what didn't change。

What happens here is that now T2 has certain channels， not only from T2， which is in。Blue。

 but also channel from P1 in yellow and from P3， which。It's great。😊。

So this T2 not only have T2's information， but also T1's information as T3s information。Therefore。

 you could combine the information by mingle across the channel。

We the one conclusion across the channel to mingle the information from the past frame and also from the future frame。

And how how much percentage do we shift， That's a hyperprimeter。

 You can imagine if you shift too little， you have too little information from the past and from the future。

But if you shift too much， you have no information for the present。

So that's a hypohymic parallel visual should kill。So for off flight video understanding， for example。

 you have a 10，000 hours of video process， this is a very good approach。

Another scenario is that we need online video understand。For example， for celebrating。In that case。

 we cannot shift from the future to the present。Since it's real time。We can only shift from the past。

So here we are shifting from here T0 to T1， T1 to T2， T2 to T3， etctera。Thereforeful。

 when we are doing a2D convol on each of them on PY， for example。

It has the information of4 P1 and T is0。So back here， it has information from P3 also T2。

Previous layer， T2 also has the information from TY。So as a result， it has this diminishing。

Wait all the way to the very first。Tele frame， timet。So in this way， we use steel crops。

Since shift the shift operation can just shift move the pointer without moving the data。

And there's no parameter associated with a chip operation。

So very effective technique to do control modeling。

And it can be inserted off the shelf to these if you have a protuous to these or stop the shelves in to enable temperature and the cost of。

Zero2s and zero parameters。So let's see， how do we insert this temporal shift module into two these things。

Starting with the offline PS models， for example， action recommend。Ping action， video recommendation。

Where the frames aren' processing the bench。This can be processed。こイと。

TheJust the novel to the evolution。嗯。こpon ship operation。So that。Each time set you also have。就是。

Information and previous information。And youll pass it to the next layer and you have an identity。

Imvent the to compensate for the information。The den is actually quite crucial。

Because the first fourth China in this case is lost， currently information is lost。

 that's compensated by this。Bypass later。So that's all my。Have access to both the future。怕す。pass还是。

And also the future time。This is online PSF module and I autoous drivingium。Z aial。

 it's frame by frame processing in a streaming patch。T p plus one way toFN。So what we do here is。Abs。

Computes part of the channels， we actually shoot it off， catching the memory。

And for the next layer we。Replaceed that channel with the previous。friends。

And shoot off the cover of the title。And feed it to the next time， time。Howtan goes on。

His final layer。The information across all the layers， because at each layer。

 you have its previous layers of information。Previous。next time。the next。嗯，判三。

The previous and the previous data is information as a result。

Have access to the entire history update。And implementationm is actually quite simple。

 can be done in the just five lines of code。You can shoot the mask。Shes write some of the。So forward。

It was a have private。I think how many divisions you want to have。

 some of them may want to ship that。remaining the don ship。Very simple to。

So let's see what is the performance。This is the fluxps。For we do， smaller is the better。

These are TSM。Is accuracy pretty high accuracy compared with peace？Based on method。

 like I believe method much smaller。Prime person， that's indicated by the size of this circle。

It consumes pre location。That the EC family and six times the less per patient。local30 family。

So this is demo for other something， something in data。 here we are。后。

Tating something with something。那后边商品的我也份。C me something。就是 rolling something on the surface。

Something putting something。电点上。And this is comparative latency about using 3D convolution on the top of about 164 milliseconds per video now it much faster about 17 milliseconds。

About nineX do that。呃，地板就是。This is published in 2009。And this is about the throughput。

 the baseline method of about six videos per second。Now we can achieve7 seven videos per a second。

And the accuracy of actually even better， 43 of us is  41%。So this is for all my。

To be your recognition， we'll process them free by frame in a streaming manner。

So this is a across favorite business sets。This is the baseline。improveded approach。A。知道吗。

We find a double digit right here。And this is showing you creature just observeable。

100% of the video have you watched。Like40% of the。Orre only 1% of the video。top pro is a PS。

Given if you' feeding it with。1% of the video the accuracy maintains much better。

These Facebook mindset。That was equivalent jobs。And this is a driving scenario for detection。

So100 percent。个号2当。I see a method which is potentially frame by frame。

It will misclassify it as a twin， probably see in the high。

This is quite dangerous for a common dining。Since we want to make it stable。

So frame by frame processing。Thanks much。A lot less robust compared。

temporary shape the module which has a history， it knows previously the car can not suddenly become a trick。

Procalating down， entrepreneur shift module is also having very low agency for low power deployment。

Just now here has two mobile phones。对我。More than 2 frames per second on a CPU and more than assembly frames per second on a mobile GP。

Which is just hour。Sating up， we also tried large scale training on the summit super computer。这个卫。

佢个呢va还是打 time。So we are comparing several aspects， one is the through code。

 one is hardware utilization， much better2x better than baseline on IPD method。's lowerer folkss。

Here is showing you the batch。Computer time versus。So this time after has a lot of IO time。

Pign is pured， dominateinated by compute time because canign is very white。

I all be creating the proposal。By time。patternttern scalability due to a smaller amount of size life weight to communicate or distributed training。

Even by large number of reviews。is pretty high， so were going to talk about distributed training technique starting from next week。

You scale up the training and utilize multiple reviews to speed up the training。

So we can speed up swinging my。Sometimes。Use minority views from today is only4。第二就完头问。

Here is 256 notes。 One node is taking over two days。For1% accuracy。Us。

In sixth though this takes only 14 minutes as a cup of coffee。呃，高平看。

Get pretty much the same accuracy。So the theoretical speed up is 256 times。

YeahIning the node from one node to。えの？A speed off。to eleven1。

So this is accuracy versus the batch size when we are increasing the batch size。说。

And on the way optimal 12 k。By size。So that's a perpetual issue when increase batch size usually is associated with improved efficiency。

 but how to find the proper learning rate schedule to make sure a large batch size can still trim while that's a very interesting。

You should be explore。So this is shown as scalability as were increasing the number of GPUs。

What is the through code？So PSM has the highest。Compared with different the baselineside methods。那个。

We can also dissect TSM to localize and understand。For example， China53 moving something away。

Here we要。Spatial and temporal pixels。To understand why the model with TsA model is thinking now we are moving something away。

第的 highlight来。Sppatial temporary inflammation。不怕。And something while we move the way。

There's a about and then we move it away。And title 446。

Understand youre pushing something to the left。有没有。不看不是。他。本地。呃不是。It's Fox。

So we can also apply it to gesture recognition。G recognition required cannot be done in a single frame。

So this is a Google Ma navigation using gestures。Use this approach this texture to switch between the switch wheel。

中标。You attention to a streetfield。Zoo命 zoo帽说了，go back to the map view。And this is by real time I。

I mean， that does a not。Hey， finally， let's talk about a point cloud understanding。我们拖地 to three米。

So there are a lot of 3D sensors like we use in our lives， like the phone， iPhone we have now have。

A lightar lightar sensor can understand the distance so we can。Use that as a measure。

 measure the distance， measure the E 3D images。And also for short self driving cars。

 some of them has a。L sensor on the top Jones。So what they collect is actually the 3D point card。

So point column is a collection of points， X Y， z together with the。Inly。With seen dimensions。看。

So it's actually very sparse if there's no object right here。

Theres actually no point so in the3 space， this is super sparse。

 compared with images to the images which has dense pixels， these has very sparse pixels。

There response points。It has many applications such as in autonomous driving。

Meajosure the distance and service another。Moernality for the import。好做火。

This is the hallway at Stanford。Before the renovation in， it was。When I was there， this was exactly。

The my now is foot。Rightated so。Onlying our VA applications。

So the challenge is that point cloud is highly sparse and irregular。So black images is pretty dense。

不。1K by 1K image， so Android pixel so it's occupied very dense and regular that can be processed by conventional convol neural networks。

But point cloud is extremely price。so sometimes it's more than。Like less than 0。1%。Dity。

 the lower density， the smaller the smaller pixels。And it's very irregularly stored in the memory。为止。

GPU and parallel processing doesn't work。What we like is actually。Continuous memory reference。

 regular memory access pattern， and large continuous memory。Fooprint， but this is not the case。

And we are suffered from the limited computation resource。For example， in ARVR headsets。

 we don't want to have a whole backpack of computers。

And a big battery we have to put it in the pocket。have headsets。And also， for self driving cars。

 yout want to have a whole of workss。So these point cloud depart models must be deployed on resource contrain action devices。

So we are going to introduce the PVCN as PVCN technique。To efficiency。啊个分包我。

So let's first understand the bottlenecks for。It's point walk open the black which is。

2 approach to deal with。啲困头。说。For the present this is resolution versus。

The English points versus E GPial Ma。So as we are increasing the vox resolution。

And the resolution gets。他有他有。It it's getting better for the simple。Un points。

The resolution is through。We cannot all distinguish the points because they merge into the same box。

If we want to去。1%。The points is to be beginning。听果说。我的是哪份还。So we an increase the resolution。

The memory is growing。Ts ruling toobly with the resolution since it's three。是那就是苏北和一个。这表是公司。

And here with eight think。Q memory， more than 40% of information is actually lost。

On the right hand side it's showing the computation and overhead。So。Is it showing the effect？

The patient versus a dynamic kernel versus irregular access。Well given point based methods。

So the baseline methods actually have a lot of overhead due to the regular memory。そずたら。

What oural method ac is is actually fating the more。冇错嘅你同时我哋解桥。Inmation， not over。

So this is comparing the memory access of abandons versus the energy。So this is modifyly and ad。

A rate is a D right rate。So he remembered this all the sale。It's a about higher energy。

That's what I'm ready。さ。So Iran off Iran access gets much more expensive。The risk。

Our pretty low here and pretty high here。And bandwidth is actually much lower compared。还法规。

So we want to avoid the run。Rom member access is also quite inefficient due to the potential pathway so well re。

Its actually continuous address。Addres0 address  one， address3。Without any conflict。

So what we are working on here is prop proping Act。called point box。so we have two branches。

One is the also branch， the other is the point branch。But for the box of branch。

 we divide the 3D space into a grid of boxs。Here is to版。It's representing 2D。

 but actually it's in 3D space。You can imagine that a two by two by2 are in the3 space。

And then we can it because it's very regular。All all these blue points。blue points。

Will be associated with the same also。And this green point。

 these two green points will be associated with this green boxel， that's why we're saying。

The higher the resolution is the more distinguishable points。Otherwise， these can be points。

Are not distinguishable because they all fall into this blue box。就 not我给你看吗？regular pencil。

 two by foot cancer， we can do3 contion。放上去有冇说啊。I assign the same feature called these three period points。

So that's basically modeling。The neighborhood information。

Ja the neighborhood information out across Jason Marxos。And there's another branch。Scusing on。

Pointwise operations similar to the point that。Transform the feature of individual points。

throw talk first。Which is fully focusing on future transformation rather than neighborhood modeling。

So what is the mon here， its a smallel based of branch。Much better regular letter。

Its a very dense sensor and there's no in。I have a h cop。

It's very good for an neighborhood and information agriculture。Keep high resolution。

6 individual points。How we distinguished。Aevviate the inflammation loss。Which appeal here。

 like theses all three points。Fall into the same lo zone can no longer be distinguished。

 so batch information can be mediaviated by hygienism point of branch。

To alleviate the information loss during the optimization process。

So let's see how does this two branch work well together？I tried these books are all quite branch。

It's focusing on this large areas like the table of call。这啊。

Where'as the point place of branchs focusing on those colors。Theive。あのこら。不确。

A variation is in like small versus large， local versus global。

So point v CNN is pretty fast and accurate。这是。来年ス？スピー up。Some I stooded out superior。

We move accuracy versus the GPO memory。Flow memory。hire I know you。

So pretty good memory and viancy you trade off。So this is a demo for indoor during the segmentation。

So here is the point mat， which is pretty slow， like two seconds， now it's only one second。

So what is the limitation for point box or combination？Actually， the multiization。

Pse and you how and you can introduce this information loss， so the box slide the same。

There's a legal scene。This is also like the scene， so the person here。

 the person here becomes four dots and only five dots。Because the localization is coursely。

So我 can we do。The improvement the resolution for this Oxford branch without be improving too much。

啊还 resolution。Actually， we can introduce this Sprse point mark of carbon motion。

So rather than using dense convolution， we can use s convolution。French on the P。So me first。

 walk all lines up and then red stars con only on the v that has 9 zero and then we see。

The patient no zero points。And that kind of have a better。Distinguishable points。第。

Point base branch is actually focusing on the small that a person with the trunk exactly is trapped side the trunk。

 tree trunk， etctera。And then given the latency constraints。

 we can actually perform3 your architectural research。To further improve the efficiency。哦。

Quin call understanding。You're familiar with that already we heard truly on super network by having fine green elastic channel number。

So you're got to say that number。就是。Of different。We have ways sharing between the Eco channelnel and Al channelnel。

Here we perform an evolutionary architecture search， very similar to what we did in lab3。

 going to supernatural。Nework。て。Then as a predictor we keep that in architecture otherwise we sample can。

Then we do location and cross over。To search the best model。In this way， it introduce。

The searchhouse by。定す。Reviews the max。All right， so we talk about both the camera and also either the image and also the point cloud。

 now let'sfuse them together。So this is a common scenario for auto autoogenic cars。

 it has multiple multi vehicle。This is actually the Seaorn area in Boston。

The frontron camera front right。Back开 around。大。It also has a lidA。

So how do we fuse multiple sensors and relation together in the same space and perform perception in that shared space？

So what if that shared for？It needs to be easily converted for multiple modalities without much loss of information。

And it also should be suitable for different 3D perception paths。

Object detection and also map segmentation。Our solution is using the bird idea。

The the bird idea or to feel them。So the live feature。Because we can project in the bird eye。

And also for the camera feature， it can also project。The bird idea basically look at the。

The world from the top。from top so that we。Bash them together， cu them together。

Just like we give an example here。in CilBuild， this is a camera for a sector。This is the bird。この套大です。

So we want to do this new transformation。Transform from sarrh to this bird ideal。

And for all the sensors to feel their information， it is share a space。

So here is a popular of what has the car。Some radar。

We canfuse the information across multiple sensors。

That has these of fence images and also the spas point2。They will mean two。

In that flow one is the dense branch for the camera， and the bottom is the sp。哪一个。

We've weren information in the bird idealO space in the P space。Wherehi streams would conver。

We first pass it through a cat encodeder。Because camera feature。

And we perform this camera to PB this visual transformation。I sounded that a lost。

For this critical operator。To concept into a B space。For the V sensor。

 we pass through a light encoder to get a。flaten that。

Space assuming that no car will be laid on top of another。You can flatten that in these speed。

イ space。The access。We've got a lot of featuring B space。Then we can contaminatnate。The information。

Has it through the V encoder。featuresature。And we can use multiple hats with decoac。

What ahead for the map and to。用。AndThe other four。Intction at the bond box。你 can。To visit the demo。

refion。Using multiple sensors as the input to do joint to the object segmentation for the cars and also the BB map segmentation。

When it was released， he was actually running a talk。俾欢我啊俾我呢。Okay， so let's off look to this lecture。

 we talk about domain specific acceleration techniques， including Gs for image generation。

 gun compression， any cost scan， are also deable augmentation for data efficient Gs。

Followed by the due understanding using temporal shift mods in the shift operation。

Very cheap for temporary model。Finally point cloud recognitionation。

 which is using PVCN X PVCN to accelerate。啊第。Poン号。In the next lecture。

 we'll be introduce infuion models。