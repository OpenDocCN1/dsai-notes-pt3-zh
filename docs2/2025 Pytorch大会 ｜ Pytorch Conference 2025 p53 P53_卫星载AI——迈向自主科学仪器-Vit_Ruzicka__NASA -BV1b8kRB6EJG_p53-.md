# 2025 Pytorch大会 ｜ Pytorch Conference 2025 p53 P53_卫星载AI——迈向自主科学仪器-Vit_Ruzicka__NASA -BV1b8kRB6EJG_p53-

So hello， everyone。 thank you for coming for this talk。 My name is Vita Rujika。 Yes。

 that many hooks and surclous in my name。😊。

![](img/139184b5b95f64940c9ca8afee6c81b0_1.png)

And I'm working at NASA JL and today I will be talking about deploying AI models on board of satellites。

 so primarily satellites orbiting Earth and towards this idea of autonomous scientific instruments。

My talk will be split into two segments first I will talk about kind of my prior work。

 which was in deploying this image embedding model and on board of satellites and figuring out what we can do with this and in the second part I will focus more on the kind of more current work which has been in trying to use some machine learning models that can deal with so-called hyperpecttor data and I will explain when we get there what that means and what are the kind of benefits we get there。

 but also the difficulties。So maybe let me start with the big picture。

 why do we even want AI on board？And perhaps some kind of complications that this brings。

 So this initial image shows how， how how the current state is of of using satellite satellites to collect images around the earth。

So typically they observe some data and the satellite itself doesn't really know that it has observed something interesting。

 so there are some examples of floods or methane leaks。

 but the satellite itself doesn't know that something like this has happened this image has to be then kind of sent down to the ground through some usually limited communicational channel communication channel and this happens every now and then when the satellite is orbiting some nearby ground station。

😊，So naturally there is already some delay there and then typically there would be some kind of AI model working near the ground station or near some centers there that would maybe create some products detecting these events but as you can see this could take days just to be even for the data to be downlinked to the ground station and in some cases where this data needs to be manually checked and observed it could take weeks and simply for some type of events its too late。

With。Oh yeah sorry yeah with AI on word， what we could actually do is push this boundary from this regime that we are processing the data on the ground on the edge and have some kind of capabilities there so there are number of top tip tasks that we can do with that capability。

 the first and simplest one is to sort of send some sort of alert signal saying hey there in this location these geological coordinates there is a fire starting perhaps you should go check and you should stop it before it gets out of control。

😊，There could be some sort of intelligent selection。

 so perhaps select sending only the relevant data through risk limited communication or bottleneck。

 or there could be some sort of automated tasking of some follow up instruments that are flying perhaps in a constellation of satellites so perhaps there is an interesting event happening there。

 can you take another look， especially at this location， perhaps with a different instrument。

 higher resolution and stuff like that。Or perhaps we could do some sort of onboard reaction and kind of initiate some sort of manoeuver right after detecting this onboard。

So this becomes quite hard despite space being quite cool。

 it's also really difficult space to work in， the hardware that's deployed on satellites is usually quite it is a low compute environment because we have some limitations in terms of power but also in terms of the chips that are typically used。

 up until now not many satellites use anything that would run machine learning models。

 even having like a GPU in high orbit satellites is tricky because these devices tend to be not very radiation hardened and tole。

 so random particles for space could actually flip some bits and linear computation。😊，Okay。

So I will start with the first application or first example that we have been working on and this is leveraging something that is called just unsupervised learning methods。

 so having some sort of model that is able to take the input images in this case we worked with Sentinel2 multipectral data so this is a tile of 32 by 32 pixels and that gets encoded into some latent representation。

😊，Means of doing this are many in this research we have been using VAEs。

 but since then research has moved obviously so we would use something like VQ VEs or some other contrastive learning methods。

 etc ce， but this is more or less just a demonstration of what we could actually do if we had this data compression mechanism on board。

The understanding is that in this latent vector so the most important features are retained。

 so perhaps this is enough to be downloadlinked instead of the original data so this could be used for loss data compression or perhaps there is another use we have been checking which is change detection so instead of having to remember the whole previous state of the entire earth on the satellite we could just remember these latent vectors and they would still allow us to have these kind of change detection predictions and there is an example of like image before image after which the image after contains a flooding event and by this model it is being detected quite correctly when compared with the ground to label so naturally world has moved since VAs and I think now what people would use would be much more complicated models or much more complicated trainings hema but this is not unlike stuff that is being used in foundational models where。

We have some domain of data， some kind of general task， this modelist pretrain on。

 and then we lever E lengthnt encodings for some downstream tasks。Oh。

One example of leveraging these latent comes from this image on the bottom left and that is just a Uap visualization or something like a Disney visualization of tileylus encoded in this latent space and we see that the tiles that correspond to the。

😊，Floodded events， they kind of nicely partition somewhere else than the rest of the data。

 and then if you look at it the rest of the data they are also kind of they are assembled together according to some kind of similarity。

And from this intuition comes， the idea that we could actually do some kind of training on board of a satellite。

呃。To explain that fully， if we have some kind of outside arbiter of ground truth。

 which perhaps means that the satellite is flying over some calibration zone where we know these type of events are there。

 or perhaps there is other instrument in some constellation of satellites telling us。

This what you are seeing right now is this kind of label， this kind of class。

 we could take these labels and train a bottle on board of this satellite why we we would even want to do that。

 perhaps the sensors of this current satellite we are on are perhaps degrading over time and so the images are changing。

 but perhaps we still would like to some kind of capability of this slowly breaking down satellite to detect these events。

This is a little bit theory scifi idea because people have not been doing this。

 and this actually was an example of the first few short learning on board of satellites using neural networks。

😊，How we leverage that how we actually have done it was that we used the pretrained model here with its frozen weights and as you can imagine。

 most of the compute actually happens here in the like the largest number of weights where in that encoder and decoder segment and so when we are able to speed this up for example in something like O Nx then because we need to change the weights of the train model that is something that actually cannot run in these efficient inference engines like O Nx but we are able to do training purely in Pythtorch and because this is just a really tiny model。

 it doesn't kind of matter that we are running it on CPU。😊。

So you may ask what the task was actually this is an example。

 it was just kind of a demo we trained the model using just six of these labeled images which had a bunch of tiles marked as here this is cloud no this is not cloud and then the model actually even just from these six images so it's a really small training that I set is able to kind of learn this and spread the patternss through these images and kind of detect even quite weak events。

 perhaps yes it misses some other but this is more of an example of like the demo of the concept。

And so when deploying this model we were targeting a special device which had a specialized compute unit。

 a VPU， so this was done on the VPU and this was done actually on the CPU where the model itself was really tiny。

If you want to know about the hardware， this has been I've worked with the UK aerospace Company the Orbit on their mission called the Ding Through the Star。

 where they were launching this IN CVV004 satellite and on their hardware we were able to run this model this experiment and you can compare these specs of the CPU with something that we typically use here on the ground。

 which is just massive more powerful。Okay。There are some results。

 I think the most interesting ones are not the numbers on the top， but the numbers on the bottom。

 this training on a CV satellite where we were able to kind of perform this change detection for a whole area of almost 5 by5 kilometers in less than 0。

11 seconds and then if we encode a whole training data set and then conduct a 10 epos worth of training of this tiny model on board。

 we were able to have a brand new model in less than2 seconds in 1。

55 seconds basically on this really limited hardware。Okay。Well。

 this was a little bit of my past work and now I'm kind of getting into the area of what I'm currently working on I'm very much interested in processing so-called hyperpectral data or some people also call it imaging spectroscopy data and these are images that come from satellites that have special sensors so I think in the computer vision land world we typically observe world like us humans in red bluegr so all the models are sort of designed to handle RGB well when we process images from satellites things that become a bit more complicated because atypical satellite will have more bands than this a example of widely used satellite is sententinel2 or Lsat 8 and they typically have something like tens of bands when we come to this hyperpecttorral realm instead of having tens we have hundreds so there is a recent mission by NASA called Emmet and this one on its own has 285 bands so imaging how。

😊，How do the models that have been designed for computer vision data。

 how do they far with suddenly this kind of different types of data？

Why would we even care about this the reason is that this hyperpectral data allows us to kind of really neatly look at the phenomena that's occurring on the ground each bend has a very narrow wave blank range and so we are able to detect some very hard to detect signals there so these black line in that figure for example is the signature of methane and with typical satellites it would be really hard to detect it but with hyperspectral satellites which are represented by these lines where every line is a bend we are actually able to look at individual features and corresponding spectra。

Okay。Why do we care about detecting methane on board of a satellite？ Well， in theory。

 a satellite itself， this is some kind of product that that visualizes the methane plume。

 typically it's not really easily visible。 but if we use some models than it is。

 So the satellites work that they are scanning line by line and collecting this data。 And if we are。

 if we were to detect this this event。 So there is like a trigger instance here where yes。

 we have detected methane plume。 we would be able。😊。

To tell the satellite to rotate and kind of take view of another path of the event。

To get another second acquisition of this image， and then after this we would kind of trigger another in for the satellite。

 which would mean return to normal processing。😊，And so by this flight again we would get a third recording of the same event Why does this matter isn't just one detection of this image enough well it turns out from a very recent research by Michael Eastro from NASA actually having multiple images of these methane plumes allows us to do this kind of quantification of the windpees and that allows us to say okay this is exactly this amount of methane that has been leaked up until now the estimates currently are something like some number plus minus 50% but with these additional information these uncertainties reduced to 15% something like that。

And the way how they have collected this kind of data is not unlike the so-called vomitAT committ plane which basically they had to fly in a plane and had to make a special man ever to kind of to point down I think first and then back up。

 I don't really know， but basically to do this same process that outlining here with the satellites loose。

 but in a plane where they were in it as well。😊，This is not scalable。

 but something like doing this on a satellite actually would be quite scalable。Okay。

So there are a couple of problems with processing this kind of data on board of the satellite。

 they all primarily come from the fact that these satellites have very limited computes。

And so I'm marking some kind of slow and fast here。

 this is all kind of related to some flight hardware proxy。诶。Also。

 data coming from the sensor is so-called raw。 So these are just digital numbers。

 and they tend to have to have lots of kind of corrections and and operations that that are there to fix this data find some elements that are kind of broken and stuff and eliminated calibration basically。

 So this step on its own is really slow。 Then also computing some kind of product to highlight these to highlight these mee leaks。

 there is algorithm called match filter that tends to be also slow。

 Thankly in all of this actually using the machine learning model at the end of this and detecting。

 yeah， this is a methane link。 This is a mee link。 that's actually the fast bit。😊，So in this。

Pippeline， we have several bottlenecks。 and this is what we are proposing or what I am working on。

 So instead of computing these like proper radiances using all the calibration methods。

 we could perhaps use some kind of just approximated methods to get this So we lose some details and some information that's relevant for some kind of tasks。

 but perhaps not in the bands where the methane is visible so we can avoid that kind of work。😊。

And instead of using some kind of product which is here the match filter。

 we could use end to end machine learning models， which means feeding the model already。

 let's say8s because that's where the meta is visible and feeding that to the machine learning model itself so these two are citations of my work that I have been trying to tackle this task。

 these hyperpecttorral bits is a new kind of type of architecture that I'm designing to work better with this type of data。

😊，So as I was alluding to at the beginning model st to break when you try to feed them with 86 bands or hundreds of bends。

 things just explode somewhere， and one of these examples why is that if you look at almost any architecture that is used for semantic segmentation。

 the immediate first operation will be some kind of 2D convolution and that one will reduce your data volume from these nice 86 bands into just that fixed number of output channels and if we don't have it fixed and it's a multiplier it would actually explode anyway on in the small hardware。

So this is where I have been trying to propose some models that are basically just adding some specialized layers。

 so this would be one by one convolutions， which are just sort of like perhaps extracting some more amount of information from the data before they are fed into the architecture。

There are some problems with the models downcaling the data。

 which is okay for some computer vision tasks， tasks， but actually in remote and this is not so good。

 so there are some additional edits that we have added to these models。Okay。

 let's look at the numbers。Or maybe let's look at the images actually on the right。

 this is the kind of image of the mee leak visualized on this matched filter。

 This is an output of the model if we use this full on pipeline。

 which is slow and this is the output on the same data if we were to to use these like onboard processing pipeline。

 which means avoiding some of the special calibrations steps。 So this is great。

 The event is still detected。😊，The numbers of processing。

 I think the largest reduction is here in instead of taking more than two minutes to process this raw data from the sensor from these digital numbers into some user radiances product。

 instead of taking this taking like two minutes if we deploy it and then cut off some calibration steps。

 we are in less than0 point3， if you are deploying this on a GPU of for this task I have selected to use jettson or in nanosuper as a sort of proxy。

 which has decent CPU， some GPU and NFR to play around with， this is not too far of the real world。

 I think people at planet are currently deploying jetsons into space as well。Okay。

 we also avoid this matched filter computation because we are just directly using end to end models so that's again8 seconds that we are avoiding and then only the model inference remains I think all in all we can just look at this total time which has been reduced by more than 99% and the important aspect here is that the speed of how fast this particular satellite or this instrument called emit flies it gets new block of data that we process in this time in about 1。

12 seconds。😊，So with these numbers and they are all initial， we are well below this threshold。😊。

What is currently missing is a sort of more proper evaluation。

 I think I need to evaluate this on more samples， the models themselves could be trained on more images。

 there is always endless work to be done obviously。

 but these numbers already kind of show us that it's quite good to we are meeting this deadline。

Okay why do I think this kind of research is interesting。

 I think there is high kind of generalizability of these models and these methods to other tasks。

 high perspective data is amazing in the fact that it can be used for just all sorts of things so there are applications in atmosphere like this fine gas detection or maybe actually cloud detection as well in geology so tasks such as like mineral detection there has been lots of applications in the rare earth elements as well in hydrology in vegetation where you can distinguish between like a health eatery and an notheery just by looking at its spectral signature which is really cool but all of this actually you have to ask okay where do we actually need some sort of onboard capability where do we care about this detection being quite fast。

😊，And so typically this would be in some areas of disaster events or fire of these gas leaks。Or。

In in cases where this data would be actually collected somewhere deep in space where we actually don't have the capability to send all of these like terabytes of data to the ground。

 So being able to produce， produce some initial products there and send these only would allow the scientists to select。

 okay， this actually looks interesting。 but I don't believe your analysis send me the raw data。

 And so they would be able to select the the information or the the source data from there。😊，Okay。

 so yeah thank you all for your attention。 This is it。 I'm trying to kind of finish it。

 if anyone is interested in any of the details， please speak with me or there is like a list of different references that like I skip through some things but it's all in there and there is a little bit of time for some questions。

 So yeah。😊，I was wondering if you can comment a little bit about low resolution data that you might be collecting from satellites。

 for example and how。You could think about coming up with models that kind of preserve fidelity。

 but also work on the。you know， also work with quantized relatively resource constrained。

 for example， you know， if it's on the satellite you want to do some onboard inferencing and then as you said。

 you know， transmit it back as needed。Yeah。So so the resolution of the data really depends on the satellite。

 There are generations of these imaging spectrometer being sent out。

 The current resolution is that one pixel is 60 me， so 60 by 60 me will be one pixel。

 So it's actually everything that you have there is really kind of just a mixture of all sorts of elements that are there but the future there are plans for future missions it will have 30 meters and some like this is probably going to be better and better。

 There are some multispecral satellites which obviously have much kind of better ground sampling。

I think it's also interesting that you you would be able to deploy these these sensors on board of the UAVs and stuff and in that you could actually sort of fly over and then have much better resolution trying to detect like your target signature of like。

This is my chemical I care about which is polluting this land， okay。

 let me just fly this drone with this setting and then maybe I can detect that。嗯 thank you。

You mentioned onboard training with GPU， are you running Pythtorch like on board with auto Python and stuff。

 Yes， yeah， so it was， I think to make things easier for for me or us the developers people at the orbit set up the system that there was just a docker of like Ubutu running some stuff。

 and I could just code my or pipeline in。On my own computer using the same docker and then deploy just that kind of update。

 which meant the code and the model weight。 And then it was running there。

 I think realistic scenario would be that people kind of bakeg these models more into some。

More compiled stuff or actually some FPGAs and stuff like that。😊，But yeah。

 that's way more difficult to do。Thanks。He great talk， thank you， by the way。

So you mentioned disaster events as one big application of this right。

 but another application is like you said any sort of event detection that can't be transmitted quickly to ground and that's where the AI would take over Do you think this could apply on like Mars rovers or something because that is a big anything to do with Mars satellites and communication takes a while obviously so there's a lot of situations where we don't know what's happening in real time So what do you think about that do you think this could be applied to them absolutely so like this would be this would allow more science data to be doneling because the scientists could look at just some kind of product and select like hey I care about these things there is an example already of some autonomy on board of these Mars rovers。

 something called rocks through which selects interesting rocks and then it scans them which is really cool It's actually quite old work even and they still have this autonomy on board and I think it would be also useful for some transient events so something that's happening really fast。

And you kind of want to like immediately react and turn on some instrument to like monitor this。

 I think there is some example of like a June or some like a， what's called。

Like a twisting wind that they just randomly captured on some image because it happened and they they were turned on and like they have it now but but actually like these kind of events。

 you cannot detect otherwise， like you would have to have some kind of you have to wait for them and then react when you are there。

 And if you wait for the communication to go to the earth and then all the way back， it's gone。So。

 thank you。So we still have， I think two minutes I was told so is there questions。那这样。

OhThank you for the speaker。 I'm just wondering for the autonomous。

 Does it include like for the camera on satellite can be autonomous for， for the autonomous。 Yeah。

 do you have any plans for those。😊，Con controllinging the cameras。 I see。 Yeah， Yeah。

 like I want to scan。 I， I mean， I want to detect something unusual around D C or something else like this kind of autonomous。

 Yeah， so。Yeah， the autonomy of the scientific instrument。If I understood it correctly it means。

 for example， in this case， we have the detection that's kind of the primary information that we get in some time。

 but we need to trigger the kind of later event and that would mean okay satellite rotate this way and then rotate that way and and that that's kind of the trigger that people would have to give or actually in some scenarios。

 this would be too difficult and we would instead sort of like move some mirrors in the instrument itself And so this really depends on the mission design and sometimes people becomes wide。

😊，Afraid when like okay， if you have a moving element and if it breaks。

 you stop the mission so like maybe actually moving the whole thing is safer somehow。

 so these are like interesting things that come from these kind of designs。😊，One more question。

 So I was wondering with these kind of events。 And obviously with space， everything is far away。

 right， So would there be an application of this potentially on like Hubble or James Webbbs where they're detecting。

 I mean， it would。He would。Probably have to do with the strength of the camera probably right。

 but those are really strong cameras and telescopes right。

 So do you think it could detect far away events that are happening that we usually just get a still shot image of。

 but we could。Understand those events more I actually don't super know how these work。

 I think they are quite close to Earth and there is some established connection that's quite fast。

 so you are able to react， but I don think that people sort of just schedule it manually saying。😊。

This is space， this big look at this blob， and then it just scans through。So the telescope itself。

 I think is close to Earth， but like when it has to do with images that are much farther away。

 does that make a difference or all？So， so， so like the image is captured through the sensor。

 which is nearby。 And then then the that downling is quite fast。 I。

 I don't know if you mean like having some sort of similar instrument on some other planet。

 and then you're like having a hubble on Mars or something。 I don't know。 actually， I don't know。

 X3 or like I can talk to you afterwards as well。 But more like when like， for example。

 you're detecting like a methane gas leak。 Yeah and that's closer to the camera。

 probably or the sensor that you can see。 But what about when it's。😊。

And like a supernova is something that's happening much farther away。

I think it's so like you don't care about this thing happening far away because you care about when you are seeing it。

 I think anyway， and and we are seeing the past because light moves slowly。

 So I think then the reaction time。 but maybe you detect like currently expodding supernova。

 and you care about that。 I don't know。 like these are I don't know really these sound， sorry。😊。



![](img/139184b5b95f64940c9ca8afee6c81b0_3.png)