# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p24 P24 Lecture 16 - Vision Transformer -BV1o7jzzwEST_p24-

Okay， good afternoon everyone， let's get started，'m happy had a win and we prepared this demo we to play with can generate any images。

 for example， here is generating。Halloween and pumpkin。

 this is using a hybrid autoaggressive modeling developed。

 where we will talk about that in the later part of this lecture it's super fast。

 it's running on a 6，000 GPU in the basement。Just take a few seconds to generate new images。

The website is。HartMTEDU。 so feel free to play with it。Okay。

 so today we are going to talk about lecture 16 the slide。Okay。

 welcome to lecture 16 on vision transformformers， So we learn about using transformers for language modeling for such as large language models。

 lots LLP path。But the transformers is so powerful that we can also use the same architecture to model the images。

 to extract the features for images。So this is the agenda for today's lecture。

 we' are going to first talk about the basics of vision transformer and then talk about how to accelerate that because vision transformers are basically super big。

 how do we make it faster， using Windows attention。

 using linear attention such as efficient VIT and also using sparsely using sparse attention to accelerate these vision transformers。

Next， we are going to talk about selfupvised learning for building transformers。

 how to continue to scale it up without having to have access to many labeled data using contrastive learning。

 using mask image modeling。And finally， we'll talk about VIT with autoregressive image generation。

 in particular， we'll talk about the techniques behind the model behind the demo and just shown the hybrid autoregressive transformer done by our T Hao Tian。

So let's start with the basics of vision transformers。So remember your transformers。

 what is the basic studio。So the input， the granular of input is tokens， so tax is very easy。

To be converted into tokens， each word is roughly a token。 some words are two tokens。

 But how do we represent images with tokens， we， How can we tokenize images。

A natural way is actually to。patchch。To convert the image into， into patches， like in this case。

We have a image and we divide it into three by three patches。Here are the volume patches。

So we convert the 2D image into a sequence of patches。Okay， and we。Consider each patch as a co。

 so for example， the original image that you dimension is 96 by 96。The patch size is 32 by 32。

 So right here we have line focus。so there are nine tokens。

 the dimension of each token is3 by 32 by 32 a roughly 3 k。And then we are do a linear projection。

To flattenen the patches。 The patch is2 D， we flaten it into a single into 1 D， okay。

 and we projected from roughly。He to 7766 to 68 in this case。

So we convert2 the dimension into a sequence of patches using this way。

What is the practical implementation of that so rather than using an LC layer？To project between。

There is only2 to7 CC8， you can just use a convolution。Use a convolution， the kernel size 32 by 32。

 That's the dimension of each patch，32 by 32。Striide of 32 as well paddding to be0 in channel is three since input we have three input channels。

 RGB， the output channel is 768 for the output channel。

And then we can apply the standard standard transformer architecture after applying the position encoings。

Otherwise， we don't know where the people will come from。

 so we need to apply the positioning codings。And then we can feed the feed the patch em to a standard transformer inputder。

 just like language。And there are several variants。The these transformers。For example。

 there is the VIT page， VIT large， VIT huge， they have different layers。

 VIT large has 24 layers hidden the image size。He， my allP is4 pay，6 highest。300 roughly。

300 million pan。And usually there's another location。Slash 16 that means。

The patch size is 16 by 16 so you can have different patch size， the larger the patch size。

More coursearse the granularity is。So how does VIT compare with CNNs？So this is showing。要除那三公。

The wide access is help on accuracy。We are comparing to the UBIT and CNN when the2 data is not allowed。

Not a lot， actual reality is inferior compared with the seeing。However。

 when we have a lot of to there。So we had theat surpass is when the per triium with a very large data set。

So we had key scale better than seeing this。But when the datata is small， DNA is more efficient。Okay。

 so having introduced the basics about VIT， let's talk about how to make it more efficient。

 how to make it tiny。We are going to introduce efficient BIT techniques before that。

 let's first introduce why it's crucial to let BIT handle this high resolution。あイメです。For example。

 medical image segmentation， we need to have those fine grain details， for example。

 this is diagnosed and kidney sized， we need to verify grain resolution。

And lots of tasks require this high resolution， dense prediction， such as super resolution。

ThisThis is no resolution。We can accelerate it to make it much faster。

 41 ris per second compared with 16 pms per second， such super resolution task is widely used。

 for example， in NVD ELSS， basically to the super resolution given a resolution video making a high resolution and that require real time front system。

And also， high resolution is important for Thomas driving tasks， yeah。

If you are using a very low resolution like in this image。

 you can hardly distinguish there is somebody riding a bike right here。

 but right here given a high resolution image you can tell actually there is a people riding a bike or a motorcycle。

The accuracy actually grows with the resolution。So here we are comparing the I IOU， which is a。

A bunch it vary in the quality of the sedimentation past， the high resolution， the red bars。

The low resolution creep bar actually is a big cap。こ。From low resolution to high resolution。However。

 increasing the resolution， there's no free lunch。You see the max， the Q max con。For BIT。

 it's actually grows much faster。I我 CNN。咁。1K to 2K， the coefficient VIP grow much faster。

 why is that the case？Think about the attention mechanism。It's all in square， right。

 then is the number focus。The number of Mac is ON square you need to calculate token by the tension between each token。

 so the computation complexity is ON square。And the number of token is。好。

Equal to the resolution to the power of two， right。

 So therefore it's total computation is resolution to the power of four。 So it's pretty completely。

So how do we this problem。Actually， efficient IT can make it much faster。

 this is compared to the baseline， which is running。1。

6 frames for second second former is very pi hearinging work using transformer for segmentation tasks at that time。

The frame is pretty low。 but after the acceleration， I find efficiency energy。

 can make it much faster from one frames to 21 frames per second。

 but still while maintaining the accuracy。 So this is measured on a。Avidia Jackson Or。

 a driving GPU driving mobile GPU。We haveP 16 and hyper slice a lot。

And high resolution dance prediction is also helpful for this AR。And VR applications。

 like there's a fault。Ddicating where you are looking at。And it's going to tell。

So the segment the stuff you are looking at。And that is using in this paper called Sediment anything。

 basically the image is passed through an image encoder， which is a VIP。

 this is taking the majority of the time。到年摆啲。And then the prompt could be a coin could be a bar。

 could be a last。你扣的 problem。哋边个诶认啊。Image en codingd with a mask and finally predict the final mask。

So such work require pretty heavy image encoder based on the。全。Input as input prompt。

 point as input prompt or box as input prompt， or even text， which is not released in this paper。

So it's profitable image segmentation。And do it in a way of design。

You can send within entire scissors or only a handle or only one of the handles。

It has automatic data。To use this model to annotate more data and use more data to train the model。

 Okay， so those are some of the use cases about dense prediction。

And the use case or VIP as the image encoder cans a lot of applications。So given those motivation。

 let's see， what are my ideas to accelerate and make it more efficient to deal with the VITs。

 starting with the window attention。So previously we are converting the patches across the whole image。

 so every patch in the image can attend to each other， so if the image resolution gets pretty large。

 the computation grows photographly。So instead of doing a patient implementationplication over all the tokens。

没看到怕window attached。So the attention mechanism only happens within the window。 Okay。

 so say this window sign is7 by。 So the attention only happens within this local window。

It seems the number of proteinss in each window is fixed。

Computation complexity is linear rather than quadratic in this case。For example， here。

Each patch is seven by seven， and we do the attention within the pack。90 patches。第二。哦。

So this is the original tension where each patch has to attend to。Now we can divide it into several。

Several windows and only the tokens within the window will attend to each other。

So what is the problem of this case？😔，Tokens only attend to each other within that token within that window。

来。So， adjacent windows。Thetopkens cannot到的太腿长了。So the information can flow。So that's the problem。

 so how do we not solve that locality problem to enable this kind of global a lot much larger receptive fuel。

So actually， a shift operation is added to this window attached。So for the layer one。

 this is the window divided by two by two Windows。or layeror who。

 we actually shift the window and then shift this window by two boxes。So that adjacent windows。

The tokens in the second window can also attend to the first window in the second layer。

 So if we repeat this process， all the tokens will be be able to attend to other tokens。

 no matter if they are in the same window or not， thanks to this shift operation。Okay， as a result。

This method actually achieves better imaging and accuracy than the VIP is with the VIP top and accuracy。

 this is the screen transformers。Shifting the window attention。

 human transformer accuracy better than。The original VIT， not only on imageNes。

 but also on other paths， like object detection， and also image segmentation tasks。

So are all the windows useful， actually。It's not the case， sometimes sparsity can also help。

Not all the windows are useful， we can safely discard lot of windows， especially in one Kong。

Actually 99。9% of the walkaws are actually sparse， there is no object， like right here。

 there's no object。So the spatial sparsity is pretty high。So how do we exploit those basket。

 we can use window attention。The white area shows there's no point， so it's zero。

But how do we divide the window， right， How do we set the window？

So one way to apply this equal window group。An equal window like this is a window C itself A is a window。

 H T G this is a window。It's very regular it's to by who。However， if you do it in this way。

 the window size is highly un。Purple window has only one element。

And that's why I have four elementmen by the grapewater I have three。

So this into too difficulty for parallelism， right， so the slow one need to wait for the fact。

Another way is actually。To apply equal size booking， rather than the physical window。

So a group based on the number of elements such that。But each group we have exactly the same。

 very balanced。Distbut about the number of9，0 item。We won the first。First window， the next ring。

 in the second window， the next ring， in the third page， actually， that's perfectly balanced。

And as a result， you can imagine this is much more hardware friendly。

One much faster compared with different transformer based models and even faster than col based models。

很用是微信包。Tranform this model measure on a media Jackson Or driving chip。Okay。

 so this is using window attention and刷 window attention。

Since the attention mechanism has opened square complexity， her natural optimization is， can we？

Simplify that to linear complexity。And so that they gives this linear attention。

so let's switch gear to a linear action。Before that， firsttz seen the also amounts of attention。E。

 so we have Q A B， we first。QQK transpose， we get a n by N。Po patient mask。This is all and square。

 scale it， but square root have been find the soft maps and use that to put the weight sum with a V you at the final output。

So the cost is O and square I want to do。This is a slightly changed version and so using rather linear attention so refer to the。

这个这他。The rental exhibition。Function right here we pass it through the mathma， scale it。

 and then what finally。Mulippl was v， so the cause is still over squared。

So can we change the order such that we can have O rather than O square complexity？

So that idea is the third solution。Since AB times C equal a times B。

So this is a soative property of the maximum operation。And you rather that QK first。

 we do a KE first。Maybe first so it's E N andD， so it's O D square。

 A D square is proportional to n rather than O N square， so it's O D square。

And then we monize a Q in the last order， so by changing the order， and becomes。

It switches from O D n square to。And these square。And so it's proportional B proportional to N。まだと。

So we change the order of the mapma using such sosociative property and we can reduce the computation complexity。

Does this work？I should not。You can imagine reducing the computation， there's no free lunch。

Originally， using the soft max attention， the attention is very strong at the points of interest。

 like the eyes of the dog and nose。爽爽。But using linear attention， everything becomes really weak。

嘅时况啦。The test。The nose is no longer heavily attempted it becomes very flat。You plotted。

 it's indeed a case， such as using the softmatic， versus it not using softax attention。

The blue curve becomes much。So flight start compared with the ra。

Which shows that the right linear their attention cannot produce the sharp distributions。 Okay。

 so it's good at capturing global contact information。

 but not good at capturing those local information。

Local information is not captured in the linear attention。

It also lacks this multi scale learning ability。 So how do we。啊Do with that。As a result。

 you can see there is a big macrocur gap because we replace the soft tension with the readily。

The problem accuracy dropped a lot。So how do we alleviate such。Dation。Without losing efficiency。

 but can effectively handle the local information extraction。

So let's firststorm what is good at extracting local information to compensate？

For the laws of opening commission extraction for a bit。That's convolution， right。

 convolution is our it was our friend to extract local information。

 so we can simply add a convolution branch。To to do the local feature extraction without。

 but in order to not to lose efficiency， we use a diide con followed by a one by one group con to save the coefficient right here rather than using the full con。

他このスシレドとか。Spatial modeling versus China modeling。So we can enhance linear attention by such multi scale。

In addition with the coal。AndSo here the F layer。The steps why is Camussha。

To compensate for the loss of actors。It added very little computation。

 but accuracy wise fully brought back accuracy accuracy and also actually improved the accuracy a bit。

So added the thatwise pollution can further enhance the linear attentions。

 local information and extraction capability。And as a result， we can see the speedup right here。

 this is a mobile chip。学校实家长毛国村。It achieved about 5。

8 times speed up with even higher accuracy on segmentation tasks。In the middle is an orange。

 I address orange for driving applications。Achie about 2。8 times speed up。

right hand side is a cloud GPU， which is A100， which is about 1。7 x speed up。

Not only on segmentation， but also on super resolution tasks。So。Here is some two data sets。

 one is the WHQ data， which is human face data sets。

 we are trying to do the simple resolution from 512 to 1k。把主开。This is the original KNR。

We can achieve even higher ourNR， originally， and it takes 92 million secondss now it's only 70 minutes。

If we see the details， this is bi cubic。It is not quite new。This is dollar about 3。

6 centimeters per second。Swing IR。At 7 images per second， this is our sufficient VIP7。

Let's keep running for another data for every data set。R。If the higher originally is 30 milliseconds。

 now it's 2。8 milliseconds。And let's see， how does that apply to the segment anything task？

So here we are using the box box prompt。This is said an a result。

But the notebook book is increased from 11 to 182 images per second。最後のてと。あ在。先好。sorryrry thing but。

Well， definitely this。Another example is showing the dot dot prompt prompt。

You have a single asterisk。好在合的。So the Chaer second from the person。In the car right here。

We can also segment everything， so given a lot of do everywhere the image and transport segment。

 as I think。This is before acceleration， this is after acceleration。

 and see the quality is very well maintained。And this is the image classification result。

This is the latency， the lower the better。Acurly， the higher the better。

 so ideally we wanted something right healing。Comparing with level baselines。

This is appreciate as good off。Throughput at you high throughput and higher。

So why do we measure latency on already and throughput on 100， Because this is edge device usually。

Serving a single user， a single driver， while this is a cloud device。

 it simultaneously serves multiple multiple users， therefore we care about throughput on the cloud and we care about latency。

Okay， so having talk about linear attention， let's further use spaarrssity to accelerate and simplify these vision transformers。

So this is the writing scenario。In Bostonos， the seaport area of Boston。

There's a question about the resolution， right， since the computation complexity grows quaraically with the resolution。

 A natural question is， can we use a lower resolution。

So you can resize the image by using a lower resolution and power of the resolution。

But using ten speaks of 100% density。You can see it's very low resolution。The details are wrong。

 so you can hardly tell this the person。So how about you response but high resolution in？

High resolution is why the resolution， but as far as pixels 25%。

Because the total activation size would be the same。で是なよ。

A dramatic growth with the resolution into the film。25%。It's proud to be。Which one is better？

So the first step about star AIP， which is Spar Vi transformformer。

 is to apply this window activation pruning。なユでフォームパス。P moment those red red。These useful areas。

 like the person here， the cars right here， which is the point of。TheImportant windows。

And how do we determine the importance of the window。

 we can just look at the L2 activation magnitude， the activation is magnitude of our window。

 the larger the more important we think we think it is。

And then we can sort and gather by the importance。The most important。Second，430。哦你说。

This is just one layer， and the second layer， the third layer。

 we can make it again sponsor and sponsor。But how smarte should we allocate the computation to each layer。

 we need to search for that。So as the model is originally trained with only dense activation。

 so we want to gradually improve the sparsity awareness。

 so we need to find tune in the model given in such sparsity。啊。

Here we are doing the randoms randomly sampling even sparsity。 The first layer is always stands。

 Second can sponsor， Third year get even sponsor。 you can also。Sample a different sparsity schedule。

 So for each training information， we are asmbling a different sparsityity pattern。

 what is common here is that。The later layer is always more sparse than the first layer。

 seems if a token is pruned， it cannot recover in this case。And finally。

 how do we select the correct par for each layer， we use this e version or research。

We have implemented that in the newer architecture search chapter。So， given a。

We first have whether it satisfy the vac budgets。Yes， we keep it otherwisewisely sample it。

So this is showing the。Acro different search iPods。Accuracy。Evol research。Get better。

The red search pretty much stays the same without improvement。

So now let's see how much we can improve。 So here is the agency the lower the better。 Here is an。

 the higher the better。So here we are comparing with。Several baselines， for example。

 this is under 226 resolution， this is under 224 resolution， so Sprss and EIT can be 1。

5 times faster。baseline。Without using SpVT in this case。So this is for3D of。for to be inセ。

Somentation。But let's visualize what is the sparsity mask。

 what kind of math did we learn in this case？So given啊。

These are three frames in a driving scenario and Sp he tried to prune those relevant background。

 for example。This is a 24 medium second layer L model that focus on those foreground rather than the background。

But either pack are even smaller model。Fcus on the person， the car here。

 lock here rather than the background。And the car is bright。

 so it's pruning away those irrelevant irrelevant。Background windows and retaining those informative foreground windows。

This idea might also be helpful for visual language models， which we can。

I discard those areas that is not interesting， both in the spatial dimension and also in the temporal dimension。

Okay， so let's take a break and then we are going to jump into self supervising。

So supervised ver for vision transformers。So the main motivation is that。

Labeling that data asset is pretty expensive， right？

But these VIPs is helpful when we have a lot of data。

 but such a large amount of data is difficult to acquire。

 so how do we train the model without needing to label the data？

So we want to train with unlabeled data to mitigate this issue。

So how do we give it a target task and so how do we use unlebelable data？

So we are going to talk about two techniques， one is using contrastive learning。

 the other is using a mask image modeling。So contrastrusive learning basically consists of positive samples and also negative samples。

 given a task， we're going to give two views of the same path。So this is one bill。

 this is another bill， theyre both cats， so we we tell those are。Positive samples。

And then we have a negative sample which is a above。

So both cats pass it through a rem encoder and then get it in embedded。

The emium from the cats should be similar with each other。

 so we' are going to acquire the one to pull together。P together be。Features from the cats。

And pull apart the features between the cat and the dog。So as a result， so with the random elite。

 we can see on the side part end。As the model gets larger， it doesn't help。嘅 know。

But with self surprise learning in this way。When we are increasing the model capacity from VIT base to VIT。

 huge。It deliver a stronger performance。And it's actually the self supervised VIP actually delivers stronger performance than the supervised counterpart。

And the accuracy increases when using a larger。Yeah。We can also apply multi model contrast learning。

 Okay， Multimod means here。 We can learn between the text and also the image。 So famous work is。

Contractive language image。啊可 train。So in a2 time， we have a piece of language。We have an image。

Now we pass the language into a text encoder。明摆啲。And also we passes it through the imaging code and get an imaging item。

那个。Actually处的。Different images and different packs。They can have a attention map。

 so the image corresponding to the text description。Image corresponding to the text description。

 which is in the diagonal position， will receive higher attention score。

So by using such paired image text samples， were can try to。Super it by。izing the diagonal part。

Which can effectively align the image and text into the same space， into the same space。

So at inference height。We pass the image into an image encoder。And then。You time。

ThereThere could be different。And then it that the one that be the highest。

We're are show you that this patch will align best with this image。we align fast with this image。

So this is showing the accuracy。But。This is zero shot twist， this is linear probing or click。

 linear probing means just adding an acillator to do the classification。

It actually enables zero shot， so this is number of labeled between examples for price given。

这个只有罗条卡个。Can be a better decent accuracy。OfPre versus international method require at least some amount of training data。

 but it's pretty amazing。 click can enable zero shot。Cability。

And the next technique is mask auto the encoder， which borrows the idea from script from language modeling。

 so we can mask away some of those pixels in the image。

We pass in remaining hatches including encoder。And then we pass it into a decoder and that will cover the original image。

 so this is target， this is input， which。Its mask。 we try to predict the missing patches based on the same patches。

Which reminded us about the math language models， MLOM。

 which we talked about in the previous lectures。So here we are asking some of the content here。

 The movie is very boring。 We must live boring。 We passed the remaining words into。到就在锁门。

And you try to supervise it by predicting the mask。啊，偷ken。

So we can pass a certain percentage of the input tokens and random and predict those masks。Tokens。

And can we use a similar pre creating strategy in the region domain。

 so in that way we don't have to label the images we try to just predict the missing patches。

 which is coming for free。I say that works。So we hear those two encoders。

 when it's a highly encoder process， only those un mass it open。But by。第发到分。

Here we just have one through three， four， five， six， seven， eight， we just have eight un' master。

Pa is unmed open through a pging encoder。嗯。And we。Feedback。Gther with a mask。

the green part means those cool things are mask。When we pass that to when life be there。

So we do called all the output tokens。35 from8。絶対。re example呢。' to recover。The original image。

So why do we need a highly versus light because a highly encoder deals with fewer tokens。

 this light encoder can deal with more token。Actually， this method works quite well， for example。

 even if we must a lot of component。Here the clock becomes almost this undisinguishable but amazing ladies approach and still recover the bug。

 the bus。The dog the lab， only with a few pixels。よけそ。

You can imagine there should be a limit we can mask away， we cannot mask away like 99% of the pixels。

 right？And it turned out， the max visual had a sweet spot。三点5%。10%， this is 90%。

So Sws fault is roughly achieved at  75%。Mask ratio。就是他们。I。啊。So it， this has a pretty high ma ratio。

Ma ratio is only about 15%。But maybe can actually achieve 75%。What does that imp？Actually。

 that implies that image data has lower information density。But low information and more dependence。

Compareed with language data， such that we。Must weigh more information and still we can recover the original information。

So this is comparative。一佢先。My thought being called their works quite well。It this higher。

Icur it on the baseline。Okay， so now let's reach gear to the third section and talk about generation。

 which is very very new work done by our T Hao Tian。To talk about progressive image generation。

So far， we all talk about something about discriminative models， like segmentation， detection。

 classification， right。tooitive models which that will predict like what is the past， for example。

 feeding in the image patches， tokenized。Cotonized privilege。

And then pass it through a transformer that predict the final cost。

So those are discriminative models。Now we want to design generative models， can generate images。

So autoreive models can generate。Naturally， generally tokens。So the natural way， natural thinking is。

 can we use the auto aggressiveive transformer to generate visual tokens in open in open up？

The input token would be the language， something we wanted to generate。

 and the output token would be the image token。Actually。

 it's such awful progressive evening generation。Benets from the model， language models， for example。

 down。古会。K that that I was the author of aggressive model of individual generation。方です。

With an important distinction that the models are multimoded from the beginning and can natively output images using discrete image tokens。

So we designed this offer progressive generation， offer aggressive short core AR that can achieve even faster。

Sreed that distributionusion models。 So we are going to introduce distributionion。Thanks lecture。

 but here we're going give it a very quick hint。😊，It has many handt。

 try to predict the noise and try to denoise。喂。We predictt noise and then subtract the noise。

And you report about steps。And hard to require。Notatuch lower fewer number steps。

And achieve much higher circle。Two images per second can tell about 0。2 images per second。

 much faster。Excel， think so art。Did not play one as。所以再。So how do we generate image tokens。

 what kind of order do we generate the image tokens？Actually in this paper， summarize three ways。

 the first way is just using the ratster altogether。ree four， five， six seven。我我。

Each time we just generate。One more coconut for one。You last rising。We can also use the random order。

Next time you can generate this pixel well， nexts time you can also generate another patch。

Friend and father。But the problem here is that it generally at a time， which is memory bonded。

 as we learned during the quantization part。Single co generation。

 you need to go through all the weight。Which is a lot。So we also generally part topics。

And we also generate multiple focus。你系度声下。先个到嘅同系奖。先体。So those are three basic approaches。

So what is different from language generation to image generation？For language。

 we have a fixed vocabulary。Right， like in English， we have like。So were tens of thousands。

English words their district。So that we can use the CE loss very easily to add a loss。

To supervise this distinguished。It's critical。But images。Is different。

Those pixels are actually continuous， there's not such a vocabulary。Like。10，000 peish works。

There's not like 10，000 image patches。So， but for which make it difficult to supervis。

So a natural way to harmonize these two modalities is to use discrete image topicss。

 event discrete image topicss。So that we can fit it into the same auto progressivegress infrastructure。

我拿去两个。Then we can supervise it by the same loss as language law。

So previously we have an encoder decoder now we added a new vector quant encoded and vector quantize。

Together with a code book。So we turn those continuous image patches。

 these visual tokens into discrete。Image topicsken。We can decode it。Although there are。

 there's a limited amount of pack。Tokens in the code book。

 we can have different mingling for these tokens， such as。Decode them。

 decocode them into various diverse images。This is highly related to the code book that we talk about during the quantization lecture。

The difference is that previously we are contact individual way to activation。This is a scalener。

We are doing a scaler。These two these three values are all falling into this century。

 that we just do。Central index。So now we are not contact individual weights but。In vectoror。

Of pixels。So that's why we call it vector to quantization here that's a scr。先。

So we can do a vector quantization into the area generation， where each index may correspond。

One of the indexes。For example， this vector that closes the color of the right here。

 so we are storedoring in that。And this color。It's different from any of them， but。

The closest is wise is。3， so we saw。The blue is close。In this code entering the code book。

 therefore they are going。Hre0。indexd of0。And you can see previously those。Continuous。

 continuousuous。So now， they are discized。Represented by infe addict。So。

You can tell this is like thehor of the deep impression from the closest central lookup to the closest vector。

And use the integer index to represent a vector instead of a single wave。

So that we can generate those indexes， which is discrete。

And this work called VAR basically introduced a new order to generate。The pockets。Remember。

 the rule of thumb is try to generate more tokens， not just one token。

 generate more tokens at a time。what it does is actually first generate one token。

 Okay pull the entire image into a single token。反正 two by兔 two by兔 who to。Okay，And then 4 by4。

16 pocket but a five essential will actually increase the number of to to generate。就当时你来证就。

The big picture， very raw。Big picture versus the master stage will be a very high resolution details。

from the。Big picture with the fine grade of details from course grade。Pel to the fine grade pixelel。

 So that's the order where it's going to generate those tokens。

And the interesting part is the pension mat。It's no longer the triangle shape。 So what it new shape。

So imagine initially we generate just one token for the entire image and then two by two。

 four tokens， and then three by three nine tokens， then us will be like this。平湾。Before and night。

So in this way， when we are at this stage。Three three token。

 we can generate nine tokens at the same time， it's no longer a memory bond in it。G token by token。

 you have to fetch the entire weight for each token is purely memory bonded， but now is no longer。

Which is pretty hardware friendly。However， this is not a perfect in the generated picture compared with the original reference。

The爱。Be friends。挂注攞系。So on top of that， we designed a new technique。hybridbrid approach。

M perfectly with the original reference。明一先。More details here。

So the discrete tokenizer inherently has its limitation。 The world， the images。Conuous。

 you force it to be discrete。Right， so you can see the recover quality for。担么。

It's not quite well recovered。See name right here， there's a model。Distortion。这是 heart。

recover that quite well。So how should we build such a tokenizer。

 what's the limitation of the existing district？都很买责。So， we introduced。

The capability to decode both the continuous and also the discrete codes。This is a continuous token。

 this is after the N compizer， we' get the discrete token。Okay。

 and if you skip the entire vector contact， just use the continuous token basically that the decoder becomes。

The has the capability to decode con topicsken。But in the training time， we example。

Sometimes in example， from directly from the continuous tokenizer， sometimes in example。

 the discrete tokenizer。So to make sure that they're in the same space so that the same decoder can decocode both the continuous token and also the discrete token。

大概说一下。We try to learn the residual token if the residual is the difference between the continuous and also the discrete token。

 you can imagine。It's very difficult for us to learn those fine grain details purely from these kind of discrete topicss。

So we can offload the difficulty of learning those fine green details by a very small diffusion model。

Ca it de。That model can be as small as like 30 to 40 million parameters compared with hundreds of millions of parameters。

Primmatters， but just 30 or 40 million parameters。Very small rigid diffusion model to learn the difference between continuousflow and this threetop。

 just to learn the difference so that we can make this diffusion model super super small and super fast。

And let's try to see what are we trying to learn from the discrete token。

 which is basically the big picture versus the residual token， this is learned by a small。

 very small diffusion model。哦。It can hardly tell that is roughly the fine grain of details。

 versus if we combine them together， the three brokenken versus the residual content together。

 it can give you a very fine green。Like previously， you can see the eyes， the theater。

 versus is the eyes。😊，of the heart。Iscript only this is the discrete plus residual。

More a lot more fine。So that these three tokens are basically learning those big picture versus the Magjiio tokens are learning those fine details like the eyes。

 the hair， etc。But the natural question is how to efficiently model this discrete and tokens at high resolution。

I'm guided by tax prompt， not just the class prompt。So for class prompt。

 it is very easy like you just input a class index occupying a single token。贵州。战思中。

So we can animate the first。Text， so the first the class index with the generated。Image tokens。

 so from2 by2。と。It three by three， sort of business nine by mind which three by three。

 generally line opens。Everything has what happened to each other。

OkaySo this is purely using the discrete token。 So from set one， we get a。By one， step two。

 we get two by two， three by three， all the way to。Much larger resolution。

Adding the catch problem is pretty simple。他 through的 tax窗。全。sideideor with golden height。

 golden hair， it passes through our arm， get a few text tokens。Ex examplele're showing three here。

I have more with just Academy。The very school of Dar。But this is actually not enough。

Because the generator just using this。D token， that generate image quality is not quite good。

The image product。We need to also add this residual diffusion model。To predict the difference。

The difference。Between the original image versus the sum of the predicted top different resolution。

1 by one，2 by two，3 by  three，4 by four， we add them together。

The past of the small diffusion model is to model the， model the di between。

The sum of it is strict cos versus。呃。The final output and this becomes quite easy and only 30 or 40 million parameter is enough to complete this task。

For the residual dispute to learn these residual topicss。

 and finally we had the residual tos with the original discrete topicss。The final output。

And that's how we achieve嘛。hi大家y。Mgial generation。第二。And also， achieve by high throughput。

And this is comparing the heart versus the fu models。How long is hard。

A cop is a boy and a girl falling love， which is hard。好的事。We Brown。9二。

As TL these are all diffusion modelss。Second。I'm called full on shot， a French woman。

Photography in French streets。Compared with this。so third one is strong wheel of waves crashing face。

P to be sir。In terriblerible。H Chris。And the most exciting thing is hard can run at interactive speed on a laptop。

 If you have a laptop with a 4090 mobile GPU。We can do image generation on it。Let's play the video。

就这是。Stream park makeup。In the style of we ray tracing。It's almost instant。

Just click the button and make can run more。This is astronaut riding a horse。The classic bamal。

We can also do a dog that has been medicating all the time。A neo holography crystal cat。

Or crystal dog。 Just take one second。And this is everything is local，'s no internet connected。

To go laptop top here。An astronaut in a huge GPU classroom。

If you're interested to play play with more demos， you come to try just go to heart。mT。edu。

 there are more examples we can also try。You England going to fall with the river。House。

And can immediately generate。イ。Or we can try some default。没有好了玩。still cat。AndRun it。

It will generate instant。OkayGo back to the slide， So let's summarize today this lecture。

we talk about starting with the basics of fuion transformer， everything can be tokenized。

 not only language， but also images can be tokenized so we can have token in token out。

basics architecture of VIT it grows， the computation grows quadraically with the resolution。

 So how do we make it more efficient， We can first try the window attention， So only。

Everything is constrained locally within that window， we can also use linear attention using ph VIT。

 users sparse attention， not all the windows need to be attending to each other。

And then we talk about how do we deal with the data efficiency of VIT。

 basically not requiring a lot of well labeled data， but using selfsupervised learning。

 including contrastive learning learning and also mass image modeling。And finally。

 we talk about only the understanding or distriive model， but also the generative model。

 how do we use this token in token out approach combined with a very lightweight distribution model to do autoregressive to apply this hybrid autoregressive transformer hard to do image generation。

So in the next lecture， we will introduce diion models for image generation。

So the code for E and T and heart is open source， so youre interested in continue developing heart or use heart as a tool for other applications welcome come to talk to us and the TA is Hakiian is the author of this paper。

Feel free to try it out。But we will release the grading for lab  two and three by this weekend by this Sunday。

 So if there are any questions， feel free to talk to us。

And it's time to get started to think about the final projects we already released many project ideas。

 some of them is like hard for， some of them is related to application We don't want to constrain your。

Imagination， so feel free to select the one you are most interested in。

 and we are always here to help during the office hour。All right， that all for today's lecture。

 happyapp Halloween。