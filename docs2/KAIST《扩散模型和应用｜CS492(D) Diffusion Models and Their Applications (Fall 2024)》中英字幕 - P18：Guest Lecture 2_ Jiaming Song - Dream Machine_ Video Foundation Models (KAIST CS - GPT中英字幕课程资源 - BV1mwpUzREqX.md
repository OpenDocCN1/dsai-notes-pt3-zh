# KAIST《扩散模型和应用｜CS492(D) Diffusion Models and Their Applications (Fall 2024)》中英字幕 - P18：Guest Lecture 2_ Jiaming Song - Dream Machine_ Video Foundation Models (KAIST CS - GPT中英字幕课程资源 - BV1mwpUzREqX

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_0.png)

And yep， I mean， please take it away。 Thank you。Yeah， thanks so much。 So yeah。

 today I'm going to talk about dream machine and。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_2.png)

So I guess I'm not sure if many of you have seen this particular video。

 so it basically shows you you know some kind of a transition of a girl like gradually smoothly transitioning into like you know older and older and you know this video actually got pretty viral after you know sharing it on Instagrams probably got the few hundred million views。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_4.png)

And in the you also you know， there has been like you know like video applications such as these with you know different types of you know things that are like entirely AI generated。

 So its like gives you the like camera control and the consistency that were not there in like video models in the past year。

 and yeah， it was entirely made by dream machine and we developed model and like released to public at around like June。

 So at that time， it was pretty popular and you know broke the internet like Elizabeth。

 and as a result， our GPU were kind of burning， which is shown in this particular video。 and yeah。

 some of the videos actually got a lot of the views such as like you know like tens of millions of views。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_6.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_7.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_8.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_9.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_10.png)

Actually， like just yesterday we also like launched like a New stream machine which basically allows you to you know like ideate visualize and create videos and share things and ideas over the world。

 so if you're interested just use like Lo Appster AI and check it out。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_12.png)

So before we talk about the， you know， like videos and you know。

 like video foundation models that me first talk about like how Luma started， you know。

 like as a company。 So Luma initially started like working on things such as like Su capture。

 So this is more related to like nurse and ga span。 So in this case， basically you know。

 one could try to capture like multi view。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_14.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_15.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_16.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_17.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_18.png)

Images of a scene， so for example， this is have been captured by like a probeme footage and basically then because these things are relatively static one can use some 3D reconstruction methods such as nerve or gasous spting to you know convert this into like interactive 3DC。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_20.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_21.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_22.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_23.png)

And then we also launched genie， which is like 3D generation kind of like like utility。

 So basically allows you to you know， create 3D assets using text and it extends on top of what have been done on。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_25.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_26.png)

Certainly in reconstruction， we are the cost study。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_28.png)

However， the more we work on like like Recon as SuD generation。

 we quickly realize that there is like an issue with like SuD and that issue is basically this 3D data that's not very scalable。

😊，To put it into context， so for images and videos。

 there's like very like abundant resources online so of for example。

 line this large scale like AI Open network data set was the one that was used to train the original like stable diffsion and its they claim to have collected about 5 billion images and after even after some filtering you can get to like basically like images about the order of billions and similarly for videos there's a lot of videos that you know like like people have collected for data sets for research purposes。

Another thing about images and videos is that it's relatively easy to create so for example。

 if you really want to you know capture a like image or a video you can just do it on the cell phone so like everyone has a cell phone nowadays so there's a very abundance of such data。

😊，However， for 3D data the thing is entirely opposite so actually if you like you know check what are kind of the size of the 3D data maybe one of the biggest set of3D data is this data that called objectverse Excel so basically it claims that it has universe of 10 million 3D objects and this is kind of as big as it cans and you know versus 1 billion。

 this is already like 100 x difference but what this doesn't actually tell you is that even within this 10 million objects there are many objects that actually are rather low quality so here most of the high quality objects are shown but if you actually do the filtering to filter out like things that are like duplicated are or have the same shape but different texture or are just like not exactly correct then you're not actually left with not nearly 10 million objects it' more about like 1 million so for example if you。

😊，Look at the objectverse data set are fish there is actually a category of fish that have the same shape however。

 if you actually want to use that fish in the training。

 you need to clean it because someone actually put a rubiks cube like a very tiny rubik's cube that is like beside the fish and if you just directly use the data from the fish you actually also include the rubik's cube so I'm saying is that this kind of data is actually pretty like low quality and even the like considering lowest quality is not that much another alternative is to do like certainly or multi view captures so for example this data actually called a multiview imagenet what they're trying to do is basically they hire a bunch of people that these people take their cell phone to like scan these like items in a multi view fashion and in some sense this is also how some of the capture like Luma capture data process like is there and as a result they hire。

😊，B of people and ended up with about 200 k these like multi view images so similarly you know。

 another thing is that you need to actually kind of hire people and educate them about like how in you know how to actually capture these without you know like these objects being。

😊，Becoming like。You know like usable in this like scenario and so all I'm saying is that the3D data is actually very hard to create。

 even the ones that there exist using like you know the artist or using like multi view images is very scarce and this is even just a shape and like appearance and there is even less data with materials articulations and business and so on。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_30.png)

The algorithm that currently you know power 3D is also kind of like non scalable so for example。

 if we do like a nerve for gasian spaning， we basically need to optimize a particular like you know procedure that reverses the rendering process so in nerve and gasian spanting there are assumed to be some kind of rendering process and you know basically one tries to like solve for this problem and you know if we want to recreate the world basically you also need to have the forward model of not only kind of rendering equations but also materials you know on fixed physics and alters and causalities and you know in order to solve this problem you need to basically have something that's almost like learnable gaming and try to optimize on top of the gaming engine to get other the features so this also is like quite unscalalable so both the data and the algorithms are kind of like very nonsable。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_32.png)

So with that in mind， I really want to you know go into you know a quick overview of like why like we as a company decide to kind of you know work on videos and you know this is kind of driven by like multimodal diffusion models and how basically most of the text to 3D generation works are being done and next I will show some like emergingnt vision capabilities of dream machine which despite not being able to train on like 3D data actually has some interesting properties related to like 3D vision。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_34.png)

So I guess everyone you know who have like like heard about or know working on AI would have known that you know the most kind of popular and most scalable approach in like AI now is like autoaggress large language models so the idea is quite simple you have an input sequence and the model try to for each sequence try to predict do next token prediction so basically in this earlier sequence you try to give a probability of each of the possible work or token and give a probability of that so in this case you can see that the next word is supposedly doed and the model gives a higher confidence over the word doc and this is interesting because in language these are tokenized to a discrete space so then naturally people would ask like what about continuous signals such as images while autoaggress like models has also been tried for things like images as well as the videos it's actually。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_36.png)

Less popular approach today， so today people mostly try you know things like diffusion models which are proven to be a scalable kind of alternative to auto requestive large language models。

😊，So the key idea of a diffusion model is a quite straightforward。

 so instead of trying to know do this expert prediction。

 we actually try to you know solve a different task which is based on denoisy so in diffusion we assume that from the left which is a clean image we actually gradually add more and more ga noise to the image so that at the end this you know original image gets entirely corrupted and you basically cannot see what's the original image like from the like from at the right and what a diffusion model does essentially is trying to reverse this process so basically it is a learned model and the learned model is mostly just trying to dennoise the image so basically given the noisy image how to recover the clean image。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_38.png)

And basically， the the task of a diffusion model itself next token prediction。 Basically。

 it tries to dennoise the image at you know， different noise level with you know， like regression。

 So basically， I have different noise levels。 Some noise levels are like， you know。

 add a little bit of noise and some noise levels at a bit more noise。

 and my model tries to do this denoing task at different noise levels。

 the model also knows the noise level。 So basically。

 it knows like the standard deviation of the Gher noise that that is provided。

 And that allows the model to you know。😊，Be dependent on the noise level and also do like mean prediction on the images。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_40.png)

So how does that like simple idea work for like multiple like multiple other cases so in like。

Like actually most of these like models are powerful by powered by kind of one of the most amazing invention in the past 10 years in deep learning called attention so basically if we have a text let's say a Corgi playing a thing throwing trumpet and image which is Corgi playing a thing throwing trumpet in this data set basically what you know like attention does is I try to create association with them so basically we know that the for example。

 we have this query， which is the the text token and like。😊。

The keys are basically just you know the image patches so it tries to kind of build this association across the text modality and the image modality so on the right we can see that on the top row there are like multiple words Corgi playing a faint throwing trumpet and left hand side we actually see different image patches so here basically if you see the word Corgi it is being like highlighted by some of the four patches that contains the actual like corgi and similarly if you have the word flame throwing it actually shows you the top patch which like has a little bit of like faint throwing like element in it and similarly basically the idea of attention is try to build this connection implicitly through the different modalities of course the actual reputation of the the inner workings of this query and keys are slightly different but as the network becomes deeper the model begins to learn to like uncover。

😊，were these associations between like different modalities like quite easily。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_42.png)

And this is the building block behind stable diffusion and more of the key component。

 the actual model is a little bit more complicated than the above。

 but mostly the key components are just self- attention and cross attention。

 so cross attention tries to read association between text and the images and in self-at it tries to build this association between images in itself in something like newer architectures there are more based directly on self attention for example stable diffusion3 is based on just entire self-at with different experts attending to different modities but like attention is very key component in this and on this right here I'm showing basically one of the earliest papers that tries to do purely like transformer or attentionbased approach to like image generation and this work is called like pixelix art alpha。

よ。Yeah， as you can see here we have like the text and the image tries to build this like connections。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_44.png)

So one may ask， okay， this you know simply diffion work really well images and there's know countless texture image models right now you know based on like contention mechanism it seems pretty ubiquitous can we actually just do multimodal diffusion models for 3D from 3D data so there actually has to be some works like based on this and for example in this paper called make shape is's trying to explicitly say that this is a 10min scale of 3D shape model so as the name suggests it is trying to learn a model based like 3D data and there's the 3D data is basically on the order of 10 minutes so it's actually pretty powerful in the sense that you can actually see that some of the application logs on the right so there is image to shape so some texture image to shape and it allows you to show some like multim images to the shape so theres multiple images of different views。

It also can reconstruct into the shape and there is also different cases which such as like point cloud to shape so basically I give you the point cloud of the model like you can reconstruct the shape so actually it's a pretty powerful like shape model but you can see that most of these like input types are something that we can easily generate from you know the 3D data for example。

 these multi images and the point clouds but these are not necessarily the case for text so if I you know maybe input。

😊，like a random text prompt ask you to generate some asset。

 maybe it doesn't necessarily work so well。And as we have established earlier。

 the same like method was pretty scalable， so the problem is really not the method itself。

 but the scale of the data with I believe it was like a billion scale 3D data you could actually do like text to 3D generation。

 but unfortunately the data is just not that much。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_46.png)

So how do you actually make like Texas SuD work and I'm sure you know people are excited about like looking at the videos。

 but you know， I'll get to it in a moment。😊，So again。

 like what we have like on the diffusion community learned from the like language modeling community。

 we can just leverage like ideas like similar adaptation from Lms。

 we again leverage another idea from like large language models such as this notion called surprise fine tuning。

😊，And in superse 5， what is done is this， so suppose that we have a lot of low quality but high quality text so suppose these are just a script on the internet。

And you have a base like a model that initialized from random waste has been trained to do this simple next token prediction task。

However， because this， you know， the data is high quality but low quality。

 it is actually doesn't necessarily like do some task very well such as like answering your questions。

😊，However， if you manage to you know， collect some demonstrations。 So， for example。

 like how humans will interact with each other， then you actually actually have this like a data that is higher quality。

 However， it is like pretty tricky to collect this data at scale。

 So the the amount of data is still like pretty low。 So is a high quality but low quality data。😊。

So surprise fine is pretty easy in how it works， so you just simply initialize with the base model that you have trained on this a lot of like a local like rawtex and then you just apply the same next token prediction like algorithm to like optimize the weight and that's basically it。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_48.png)

And you can see that how this might lead to something that's quite interesting。

 like related to Su so。We just established that there's a lot of image data and there is not a lot of like 3D data however。

 for the like 3D generation problem， maybe 3D data is the category in which 3D is is very high quality but low quality and images are the type of data that are like low quality but high quality so you instead in this case you for example。

 this work called image dream essentially it leverage that idea So basically will take an image model that is a train from like billions of image data and then you can do surprise fine tuning on millions of 3D data and the way they are trying to do this is by instead of generating a single image it actually tries to generate a multi view image So on the top on the left figure it shows how it works on the top it shows basically how you this regular image training has been done and basically based on self attention this image。

😊，Patch attends to different image patch within the same image。However。

 at the bottom you can actually have like multiple view images so there's multiple images within the you know kind of the same network pass and so instead of having this single you know selfitation that acts within the image。

 it simply just applies selfation across like four images or the multi view images and also there's like additional camera conditioning that you know counts the model like which like images which correspond to which view。

 otherwise if we don't provide this information， the model self attention doesn't distinguish between these different views。

😊，And that's just about it， so this you know simple kind of a super vi procedure actually works on images and and has places pretty well for like multi view images。

 so on the right you can actually see that you know this texture image model has been converted into a text to multi image model so you can see things like astronaut riding a horse or like an e car with a wood or like bulldog wearing a hat and these kind of you know multi view images and of course you know it is possible that some of these like appear in the。

😊，Some of these appear in the like you know the training set of the 3D data。

 but it's very unlikely to have like this kind of diversity， for example。

 astronauts riding a horse type of things。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_50.png)

So we just established how we are going to get from like。You know。

 image model to a multi view image model。 So how do we go to 3D。

 So going to 3D is actually pretty straightforward。

 So because you already have like multiple views of the same image。

 you can actually use it to like do some like a 3D reconstruction again。

 So but instead like trying to solve this you know like3D reconstruction problem such as the nerve and the setting。

 one could just also apply a transformerbased reconstruction。

 So basically you train on this particular task where the input is multiple images and the output is some like 3D reputation such as a nerve model。

 of course， you can also just optimize the nerve based on like multiple views and you can also get 3D model。

 But you know， once you have multiple view images like getting a 3D model becomes like like a problem that happens like after it。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_52.png)

So then you know what's how do related videos so well again if you want to generate something that's even richer than 3D then it is 4D right so in 4D we have like 3 dimensions height you know like with you know depth and time and of course in this case you know I can say in order to generate 4D I can first generate 3D and then I use whatever that comes from the graphics community to you know convert that 3D into 4D so for example。

 for a human I do some like rigging I you know code up some like animation and you know I try to basically use human prior knowledge to drive it。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_54.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_55.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_56.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_57.png)

However， as we can see earlier from the approach of you know image to 3D it would be quite natural to think maybe if we have this like you know time dimension that's being added it should the real scalable solutions should be videos to 40 so with that in mind we actually you know begin to explore a video a bit more because you know it's seemingly the like only scalable solution that we come can come about in terms of like generating 40 so we went on this quest to you know train a video model and as you can see some of the results are actually pretty cool so。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_59.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_60.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_61.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_62.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_63.png)

In particular， some of these cases actually can be done in this way。

 so you can actually like render like an image and you put them image into this image to video pipeline。

 and then you can convert that into 3D back to the interactive scenes like in spendinging。

 So basically the video， of course， is also a multi view image if you decompose the frames and this clearly shows that the model is actually learning some 3D things because if it weren't really consistent。

 then you wouldn't be able to like dump it into a pipeline that you know basically does 3D to construction。

 So this video model actually does it and it's pretty cool。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_65.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_66.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_67.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_68.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_69.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_70.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_71.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_72.png)

And naturally， we also try you know， image and video tasks on some some kind of like data sets that are from the kind of like Sw construction community such as Z。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_74.png)

And you know， there's just multiple examples from like like Nf and you can see that some of the cases the model actually tries to imagine new details that were like otherwise like out of frame。

 so this is also quite interesting。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_76.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_77.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_78.png)

So next， we want to show that basically， you know how。From， you know， from a3D perspective。

 like what does the video model like actually learn and， you know， what is。

 is the video model able to kind of just， you know。

Have some like emergent kind of understanding of the world around us， you know。

 just by watching videos。 Again， this is not， you know。

 based on any kind of Su data or like multi data that I mentioned earlier。So for example。

 you know the model actually learns steps from like watching videos so in this case you can see that as the camera turns the person in the front actually like is you know moving slower than the mountains like right behind her so the model clearly knows that the mountain is at a distance whereas the big person is closer。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_80.png)

AndSimilarly， this particular case is also the case that you have this particular subject in front and there's the generations in the back。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_82.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_83.png)

And similarly， like even for like very abstract things this actually works。

 So it's not like in the case of saying well， it has to be a physical like like possible object for you know this kind of notion of depth to work not really in this case is basically based on like entirely just you know like abstract art and so you wouldn't actually assign a physical kind of a depth in a physical depth just basically just doesn't make sense。

 but you can also see that you know as the you know circus terms it's actually giving you a sense of depth that you know it's still consistent with what human beliefs so the notion of that's why I kind of quoted the notion of depth because in this abstract case is not really depth but something like related to that。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_85.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_86.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_87.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_88.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_89.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_90.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_91.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_92.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_93.png)

And similarly， you can actually have this， you know。

 like generate some clue kind of a camera transition as well as， you know。

 like generate some things that were。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_95.png)

Normally speaking， not the， you know， like not something that you would expect from a video model like。

 you know， back in the day。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_97.png)

Another interesting property is you know light transport。

 So I think in the graphics community people who spend years trying to investigate how light transports。

 you know like onto the surface across surfaces and you know on different materials so in this particular case。

 what I want everyone to kind of look at is how as the neo sign luma turns on from like right to left you can see how much like this right light gets shined on the person's hair。

 So basically you know as the sign you know is at the center of course the more of this like brightness gets like redness gets like reflected onto the person and as the kind of a sign goes to the right it you know actually sorry goes to the left it actually has more of this like like you know。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_99.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_100.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_101.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_102.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_103.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_104.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_105.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_106.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_107.png)

Brightness onto the like left side of the person。 Another thing to notice that the person is wearing like very heavy。

 like yellow glasseses。 And as you can， as she turns， you can see some of the， like， you know。

 refraction like coming out of this， of the the glasseses。 And as you can see。

 is's a yellow pair of yellow glasseses。 And yeah， it's。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_109.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_110.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_111.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_112.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_113.png)

That。So clearly， the model is able to kind of recreate some of the kind of nontribut scene that again。

 one would， if you want to recreate this entire scene in like3 or graphics。

 it would be actually quite difficult。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_115.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_116.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_117.png)

Similarly， you can see that on this like light bulb as the camera turns。

 some of the background objects get。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_119.png)

Or because the glass is transparent， you can actually see some of the shelf on the background。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_121.png)

And similarly， you can see as the you know teddy bear wallobbles in this ocean。

 some of the like like water reflections get like resurfaced like showing how this you know a bear works and similarly。

 you can actually show some of them like know this case of a microof of a like you know of some kind of a leaf or cocoon leaf and as the camera turns。

 you can see more of the lights getting shown like you know across it。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_123.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_124.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_125.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_126.png)

So the model also clearly not only learns steps， which is like relatively easy or task to identify。

 but also slightly harder task of you know， doing like like transport in a reasonably realistic manner。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_128.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_129.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_130.png)

And because you know we worked on Nf before， so naturally we wanted to compare like how it does like when compared with like Su reconstruction based like techniques such as like Nf。

 so here is you know a particular you know example where we capture 100 images around this particular coffee machine and you know like we do studio reconstruction on this coffee machine so you can actually see some of these like a light being like you know。

 on this metal surface of the coffee machine being like reflected on the surface。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_132.png)

And dream machine， we actually just took take one image and do image to video and the scene actually was looking reasonable and you can see on the coffee machine the kind of the metallic refreshs like still gets like reflected as you turn the camera。

 so it means that you know on this like surface that are relatively reflective。

 you know things look the way things look kind of big sense。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_134.png)

And it it also the metallic surface behaved very differently from the piece of wood that's the on the table because the wood actually is not nearly as like reflecteded。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_136.png)

Similarly， you can see that basically there is the case of like learning like， you know。

 very cool dynamics and transitions with， you know， water splashes and you know。

 this kind of things and you know with the teddy bear like bears fur and all the sorts。

 it is actually creating pretty coy。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_138.png)

And some of the cases you can actually take like real life images of objects and if it's not prompted。

 then this AI generated video actually can get pretty tricky to notice that this is like an AI generated cat itself like a real cat。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_140.png)

And similarly， you know， you can actually use it to generate a very like nontrivial camera traditions。

 though it is unlike you know previous video models where are based on only a few frames。

 it actually allows you to generate like many frames and it like with like camera controls。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_142.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_143.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_144.png)

And similarly， you can see some of the you know the shadows being like transported into different like behind this giraffe。

 the shadow is also moving as this camera turns and the giraffe is moving so in this sense。

 it's obviously not perfect but it is like somewhat realistic as to like how this relationship between the giraffe。

 the sun and the shadow。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_146.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_147.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_148.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_149.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_150.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_151.png)

And similarly， you can you know generate some kind of a like dynamic situations such as like a smoke fire and you know like like paper falling around and you can use it to generate some interesting things like a clothing like simulations。

 so basically again， these would be like pretty difficult to reproduce in like traditional graphic settings。

 whereas in video models it can be done。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_153.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_154.png)

Another interesting thing that is entirely out of the scope of maybe perhaps。嗯。Graphs is basically。

 you know， like causality。 And this coloromy is more like less about like physical causality。

 but more on like a deeper level。 So， for example， in this particular video， it shows like initial。诶。

Like shot of this monster。 And then it cut to a next scene containing the same monster and， you know。

 an interesting forest。 And you can see that the monster is kind of。Shoock or in awe。

 possibly due to this forest which evokeked this emotion of the monster。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_156.png)

And similarly， you can see that this girl is like very terrified by what she has been seeing in this first frame。

 which is a very you know scary eye， and you can look at that the girl has very short hairs and a blue dress and this know short hair and blue dress actually was also consistent with the first sceneme。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_158.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_159.png)

Another thing again， is like， you know， this， you know， kind of。

video model also is able to dream out like reasonably looking fans even in this， you know。

 like fantasy world that is not physically like possible。 So， for example， in this， you know。

 like painting， you actually can also generate some like camera traditions。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_161.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_162.png)

And similarly， you can like put in very like abstract things and you're still generating something that is like consistent with like tells you the story。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_164.png)

So I hope I chose I have used this to demonstrate that， you know。

 like video models such as stream machine is。Very powerful， and it is able to you know， be used to。

Generate， you know a lot of the like learn a lot of the emerging capabilities and these emergingnt capabilities include depths。

 it includes you know some like transport includes some like materials the dynamics。

 it includes you know some causal and again I would say all of this is just based on like simple well a diffusion model and it is mostly like the power of a transformers and diffusion models。

😊，So I guess then the next question is like what are you know like how can we you know do even better and what are some kind of useful techniques to think about in the context of like research community and you know in in the academia so the there has been always this debate between like auto regression models and like diffusion models and I started this you know。

I started the talk by introducing autogressive and saying that diffusion model is this like alternative and there's countless people have trying to you know make autoaggressive model work in image video generation cases but unfortunately most of these results don't actually be to like better quality results simply possibly because of like you know tokenization the discrete space is just generally harder for continuous signals So very natural idea is like you know why not use both like we know that diffusion model works very well with images and we know autoaggressive model works very well with text So essentially you can just train one model that actually does both and it's just a different two different task and for the text task you can just do next token prediction and for the like image task you do diffusion。

😊，So that's basically it of the idea of this paper called transfusion and you know。

 like it has like one multi model model and you know， it tries to you know， produce like。

Like a sequence or try to learn from a sequence that is interveed， you know。Like text and you know。

 images。 and this is a paper for meta。 but you know， at the same time， a lot of the different。

You know， like universities and research apps have like have their own versions of like such models。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_166.png)

Of course， you know similarly you know not autoaggressive models not all last all lot。

 so there are also still be worse like for example。

 called visual auto aggressivegressive modeling which tries to leverage the uniqueness of like visual domain so basically because we know that images like act in this multi scale so it is usually easy to predict a lower resolution scale with less tokens and then predict the net scale which has like more tokens so in this case it's actually also some idea used in diffusion models where you know like in original diffusion models。

 people try to use cascades where you first predict a lower resolution version and then use that lower resolution version to guide higher resolution generation。

😊，And again， another type of like， you know idea that comes between like that mixes autogressor models and diffusion models are。

 you know， for example， this work called diffusion forcing。So instead of trying to treat。You know。

 instead I trying to treat all this like frames in the sequence to be the same and I actually treat you know。

 different frames of the of different frames like differently。 So for example。

 you can think of this no in process as also a masking。

 So as long as you you know add enough noise then you lose all the information about the frame。

 And then this basically is like kind of a just masking procedure。😊。

And what diffusion forcing does is basically， you know， instead of trying to you know。

 mask everything or like noise every piece， the same speed。 It actually。

 you can try to noise different pieces at different speeds。 So， for example， you know。

 you try to generate this you know sequence in a nearly autoreive fashion and， you know。😊。

For the unknown part， it has more noise and for the more known point part it has like less noise。

 so basically you apply different noise levels onto different parts of the sequence and this is obviously different from you know the traditional like autogressive generation where you just you know keep like having this like the same like noise level and do generation autoly or the full sequence diffusion where basically every sequence has the same noise level。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_168.png)

Of course this you know like video models are not without their thoughts and you know for example。

 like many people criticize that these models actually don't follow the like you know like think exactly physics so for example this is a image to video scene that tries to kind of do LK 99 and basically it shows that you know after a flash this rock suddenly becomes higher and this like weird lightning going around and it is possible that this error is caused by the model thinking that there is like a short change。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_170.png)

And similarly， you know， in this like， you know， image to videos hass a clever dataset set。

 the model actually does a very interesting kind of an like optical illusion。

 which in which like it merges things like moves the cube around and then， you know， like have like。

😊，Have like things just like floating in and， you know， going back。 So what is。

 what is actually interesting is after the cube cylinder goes up， the shadow also goes up。

 So the model is like definitely not perfect in terms of like learning these physics。

 but it' certainly also learned something。😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_172.png)

And you know like for example， there's also the case of like trying to control the cameras better。

 but I think this is can be mostly solved by data and another problem that we often see like know working on the3D and you know and videos is this problem called the Janus or the multiface problem So Janice is you know a God supposedly have like multiple face and if you have worked on like you know text Su using techniques such as like。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_174.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_175.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_176.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_177.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_178.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_179.png)

SDS or score disillation something。 This is a common like problem。

 The problem is basically that you're trying to optimize a problem where this 3D object has multiple views。

 and each view tries to match this know image match the image model。

 but know like the image obviously look at like front faces more than like like back。

 So the model the 3D object will actually have multiple faces。 And similarly。

 we found that some of these cases also appear in videos， for example。

 in this particular car or in this particular bear。

 know theres multiple faces that know appear in the object。 So interestingly。

 like video models also have this like problem that are common in 3。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_181.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_182.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_183.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_184.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_185.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_186.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_187.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_188.png)

And similarly， as you know， the speed goes very fast。

 there's some like morphing effects that are like sometimes like just a， you know。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_190.png)

Natural at some part and you know it just suddenly becomes unnatural in like other parts。

 but again I suspect this is something that is you know closer to how hands the converse in like image diffusion models like two years ago and it probably can be fixed by like more data。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_192.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_193.png)

And， of course， you know， we talked about how video models can be， you know。

 a good avenue to getting to like 40 generation。 So like then what's like。

 how do we actually do that。 So I think a lot of people actually are already collecting data sets relates to that thing。

 So， for example， this is a like ego Xo 40 and where basically。

 it shows from multiple views how this， you know particular person does the same thing or inside the scene。

 So essentially， this is like a multim video and it it's like a multi view like image。

 but in like multiple dimensions。 And of course， you know， similar to。😊。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_195.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_196.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_197.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_198.png)

Like。Text and Swie where the multi view image part is just like four views。

 in principle you can also just use similar approaches to like find tune a video model and generate like forward es and that actually has also been done in the research community and over the past few months。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_200.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_201.png)

So before I conclude I want to say like special thanks for the folks who developed the dream machine model and if you have any questions just send me an email at Jamie and Lus AI and you know we are also hiring so if you're like interested in joining like please please just send me an email thank you。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_203.png)

I think that's it， thank you。Yeah thank you very much thank you for the very great talk we also discussed some of the topics that you mentioned in the talk about like some 3D generation and some combination of the auto model and the division models in this quest。

 but it was really kind of be great summary and also giving lots of the insights for those topics but thank you for the great talk so I guess the audience might also have some lots of big questions for the journey talk so maybe we can have some Q&A sessions。



![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_205.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_206.png)

Oh yeah， certainly， yeah。And while we are waiting for some person from the audience。

 maybe I can start with some questions So yeah most of the results were like really impressive in terms of making some very realistic videos and I also agree that the video degene models can replace many kind of some graphics applications in terms of we don't need to render some 34D things but we can make some kind of the videos as the ops but I was wondering like how you know the Luma AID team is like handling some kind of some issues in the controllability4 the video degeneration So actually you mentioned like we the user might want to have some kind of the controls like if we really want to like replace some kind of the game engine with the video degened models and they user might want to basically change many things not just like giving some kind of the text but rotating the camera but like moving some of the objects where like making some kind of the changes in the shape。

 whatever kind of things for those kind of。Controls the question that I had is that while we have some like tons of the videos in the Internet。

I guess there are not many kind of the large scale data that are basically pairing those kind of the condition with the videos so in terms of that I guess that would be quite challenging problem like you know having this kind of the controlability like how we can frame a kind of the e model that can takes these types of the the control as kind of the condition So yeah yes yes yeah that's that's a very great question So you know I think one of the like you know very common themes in like。

You know， that ambition is that， you know， for， you know。For image generation domain。

 we learn from like Lms and I would say similarly for like video generation domain。

 we will try to learn from like image domain。 So on image domain。

 know I think one of the greatest discovery last year is like control net。

 So basically it shows that basically you don't actually need a lot of like data and you essentially can leverage the models like innate capabilities to provide these kind of control。

 even though the model hasn't really been trained like you know like at large scale on these things。

 So I would assume that you know like in order to get this type of control signal to the videos one way to do this is also do like things like control net that allows you to take the know some signal in and provide the video signal out however。

 another yeah like like basically I think that's kind of the easiest way that one could get to of course。

 you know what kind of data that can be used in this。😊，scenario。

 So like one example is like know capture data。 So in the capture data。

 you basically have like reconstructed3D objects in this scene。 So in theory。

 you can just use it to render the entire like render anything like any camera trajectory and not only the camera trajectoryies like it string。

 but also interesting this。 So basically you can actually use the models like the 3D assets to generate scenes such as like Do zoo and basically and it will be it would be a pretty reasonable case do。

 But of course， you know if we want to go into the route of like making it again。

 like ultimately super scalable and very dynamic then yes。

 I think there's more like know some of the techniques based on know like slam or like3 like post estimation could prove to be very useful here yeah。

😊，Yeah， I think that would be quite interesting direction。So we have some questions the June chat。

 I guess it might be also good for you to check with so the first question is about。Yeah。

 so like extending the pretrain video， the just models for some kind of the some downstream the test。

 some like more applications like editing， segmentation on。Yes， so yes。

 so I definitely agree that in this case， like video models can be extended to like other industrialstream task。

 And in fact， that's kind of the point when I initially tried to stay about like depth the model certainly no steps and you know I think there has been some works already that tries to do depth estimation like from pretrained you know。

 like image infffusion models。 so for example， in this year CPR。

 there's a paper called Mariigold that tries to do that and the。😊，Yeah， and so， so I think basically。

 you know， the model， I guess might。The examples I show in this。

In this you know in the illustrations is to basically show that。

 you know the model does actually have knowledge about this kind of you know like implicit community。

 So like like other than depth the model certainly also know segmentation because it those the foreground and the background and it also knows how to kind of generate you know things that were like you know not on original view and will kind of impat some like new views。

 So I think it can certainly be extended to this downstream task and similarly just just similar to how you know people have used diffus models to know address some of the kind of image understanding task I think video models can also be used for such downstream task。

 of course， theres the matter of like cost efficiency。

 So the models currently cost a little bit more than what would naturally desire So for like real like I think it's certainly doable in an academic sense for。

They forward。Kind of a production level sense maybe I think currently most of the existing techniques will probably work like better in terms of the cost and you know。

 like like quality frontier。😊，Yeah the next question is about the modeling the physics the knowledge。

 so the question is about like whether we need to model each knowledge like more explicitly or we just need to train the model more with some more videos。

Oh， yes。 So I think there's。I mean， it， it doesn't have to be a a， you know， like。Like or question。

 So， so so， for example， the model can definitely be improved by watching more videos。

 Like I think that is certainly the case， given the fact that we can you know。

 have better image like models by having， you know， like like over the year。😊。

Like over the past two years by like I mean the image model like could be bigger and look at more images。

 So this is part of where at least scale of law still currently works and you know like I think over the two years ago people were complaining that you know image model doesn't really generate hands well and you would say that sorry。

😊，And， you know， people have come up with like many kind of metricss to try to improve this particular cases。

 But eventually， you know， like， like most of the methods are like quite simple and it doesn't actually involve designing a hand specific like objective function so。

The the reason why this is the case also is similar to maybe how language model is able to have emergings capabilities so basically you know they are like different tasks and some tasks are easier to solve and some tasks are like harder to solve and a bigger model certainly like you know has the capacity key to kind of solve harder tasks and you know like as you train more the model like also begins to solve more of these tasks so I think like scaling law to some extent I think will work however you know。

😊，Being able to have some physical knowledge is also like quite useful from a video generation。

 So for example， if you want precise control to， you know the the generated videos such as like for like you know。

 game engines， then of of course you would need to some kind of physical knowledge this physical knowledge might just be like you know graphics。

 So for example， you need to know the camera locations of。😊，The camera location， so for example。

 the camera its and interestings so like having some knowledge here is certainly like very helpful for photo model as well。

 but you know， the way I mentioned was like less dependent on the like changing the like core architecture was transformer of course in the text 3D generation rounds people also tried methods that you know leverage explicitly like 3D representations。

 So for example， in the energy dream case I mentioned that， you know， in。😊，People。

Generate multi view like images。 And these multi view images are connected by， you know。

 just just full sation， which was quite straightforward。 However。

 I think there's also works that try to leverage the fact that， you know where these， you know。Like。

Like the camera， like it changess and intrinsics of these like， you know， pixels are coming about。

 So basically， it allows you to and basically， it means that， you know。

 like the model kind of knows the different like how like this on this view。

 how it matches the other other view。 So that kind of knowledge can certainly be leverage。

 But I think。😊，The benefit of like， building this， you know。

Engine or building this like prior knowledge into the model is not。

As big as one might think and you know it can help a little bit， but you know。

 like together with the fact that this also becomes like harder to work with on like GPUus。

 it's like certainly very different。So I would say， you know。

 I don't think this is a either work question， both are kind of important and you know。

 like we can definitely make them all better by doing both。Yeah。

 I think thiss really kind of the open question。 The next question is about also the 3 d40 representation。

 So you also you work about like3 d40 generation， the question is like。

 what are the kind of the most effectively and preferable the representation。I see。 yeah。

 that's a very great question so。I would think like many of these methods all have their like you know relative advantages and like disadvantages。

 so I guess a mesh based reputation is you know very good for things where you want to combine it like with like auto aggressive generation or like a language model so you basically just generate the vertices and generate the like edges like it can model this realL elementsMs and basically it allows you to generate reasonable stuff but you know of course with mesh this you know topology becomes an issue like it has to be you know it has to satisfy some topology。

😊，Voxel representation is also， you know， basically just a 3D version of a image， so it is also very。

😊，Good in the sense that you can use it to， you know， like。

You can like use it for like generation just like how you would generate that images。

 but of course the problem is like fossil representationation is that it's very high dimensional so there is you know if you do 26 by 26 by 56 kind of okay but maybe if you have like 1K by 1k by 1K it becomes like harder to deal with so there also has been some work that tries to just learn latent space of fossil representations and tries to drive down the computational cost similar to how like image and video models are doing compress so I think that part can still reasonably be solved。

😊，In terms of33D Gs， it's very powerful in the sense like how you like render these and it's definitely preferable than nerve in terms of like how you would render these and like of course。

 you know the rendering equations in 3D Gs it like a little bit different than nerves so both have their like relatively random advantages in terms of like you know3D construction again。

 like for like3D generation I think you know both like like3d Gs and the nerve also like all appeared in like countless papers by now and perhaps maybe nowadays like people are using more in 3D Gs because of the efficiency reasons so I would say for like3D representation there's just you know all these representations exist for a reason and unfortunately like。

I wouldn't say there's a like preferable case that I personally find I just find that you know whatever suit best for your use case is the one that you should pursue So if you care about like combining that with like game engines or like downstream pipeline then having mesh is certainly important but you can also convert mesh from nerve for CDGS or Voxel these different representations can also be converted from one or the other of course there's a quality degradations or quality differences but yeah it's certainly possible。

😊，YeahThe next question is again about some bis below law。

 I think you already partially like answered the question。

 but the question is about that you know there was like paper that says that the behavior models are like kind of overfitting some kind of bi law that they have seen in the training data and ultimately can resolve those kind of issues。

Yeah， I mean， to be honest， I don't really know， I think this is a like natural problem in like machine learning and like in machine learning there is this like generalization issue that is you know。

That's always there。 Of course， you know， there is a possibility that， you know。

 some of these can be addressed with more data and， you know。TheOf course。

 some of these can be the case of like getting， giving the model more physical constraints and of the things。

 But on the other hand， maybe we are asking a lot about the the the models like at the moment。 So。

 so， for example， like prefer humans， you wouldn't expect them to。

Just kind of like hand draw a video for you。 Most of these are still captured by by cameras and and things。

 things like that。 And maybe if you try to kind of。

Imagine or like recreate or draw the see or a video。

 It's probably very physically like inaccurate either like even drawing pictures。

 I think it takes years of like learning and practice to kind of do it well。

 So I would say that humans are great at。😊，Like telling differences or like discrimating things but maybe people are humans are actually also not that great at generative things because if if they were。

 you know， people don't spend years learning how to be artists so。😊，But， you know。

 on the discriminant side， I believe that the model actually is also able to already do pretty well if we are providing it the right kind of downstream training。

 But yeah， the it is an open problem。 So I think it you know， I I would hope that， you know。

 both methods can get us like， models that are higher quality。Yeah。

The next question is about like the synthetic data。

 How much the synthetic data will be helpful for improving the quality of the video generation。 Yes。

 that's a good question。 So I think in some sense， it certainly will help。 So， for example。

 in the case of like。In the case of like trying to do camera control or like render scenes that are have like movements and stuff in it certainly will help。

 but of course there is this matter of like sync to real gap and like synthetic data well help like in certain cases but not necessarily work for cases that are hard to create I think for language models like things that are easier to create synthetic data for the things that you can verify correctly such as like code or map but for other things it's actually trickier to generate synthetic data because well if we knew how to generate the synthetic data we wouldn't have like a machine learning model in the first place we wouldn't have to use machine learningry model in the first place so I think physical 3D simulation could certainly help something such as camera but it also has like limitations in terms of like this is actually different from the real reality but as you can see like most of the tech to 3D works actually leverage synthetic data from。

Its really to kind of improve the model's capability。 So I think it will certainly help。

 It just need to be controlled how much you want to deviate like into into this like synthetic data side。

😊，The next question is about the supervisor。Let we know the genetic model can make some like high quality mis reading from various differents。

I see。So in the field of a superion。I think。A single model generate high quality images across variable resolutions that actually has been shown so like you can actually train the model to like just add a different resolution then they can actually generate high quality images across like like various resolutions for resolutions that haven't been seen during training So there's some extent of like generalization but of course it's not perfect and you know but like usually speaking like like interpreting between the resolutions or the aspirationration you have seen during training certainly like works to a bit of extent。

😊，And the。The next scale prediction is super resolution， I think。

I guess most folks don't use the same model for like super resolution at a different scale。

 mostly because of like efficient reasons。 So， for example， if I use the same transformer for。

 you know， like predicting 2。6 by 256 versus like 1 K by1 K。

 I already have like 16 x more like sequence less。 So the you know。

 like competition is just gonna be less efficient。 the other thing is about like utility。

 So for super resolution， there is an extent to which like humans cannot tell like the difference。

 So like humans eyes has like a limit or like what the resolution accept。

 So it doesn't have to be like infinite resolution。 And I would say that， you know， for some tasks。

 it becomes like unnecessary to do。Like， you know， to use diffusion models to do superion。

 but there are some tasks where you know diffion model is very useful for super。 And for for example。

 if you try to upscale from like say64 the 64 26 by 26。

 this is a task where the model has to kind of imagine a lot of the details and this is kind of the case where you having a general model is like very useful in this case it can be slow because diffusion model searches naturally slow。

 but you know the task is also harder， on the other hand。

 if you're talking about cases like like you know invi the deep learning super sampling。

 So basically you want this thing to be very fast and working on game engines。😊，So， but。

 but also instead of trying to generate from 64 to 6 56。

 you are mostly in this like case of like a one like a180p to like， you know，4K。

 So you just like you're already having a very high resolution。

 And then you want to just two by two ups sampleble the resolution。 And in that case， typically。

 you don't need that many。😊，You don't need like， you know。

 that powerful model because well your model also has to like run on real time。 So as a result。

 they also try to， you know， like have game that models。

 So the solution can depend quite differently like for even for super resolution。

Like depending on the the problem。 So I think although that being said。

 I do think there is it is certainly possible for one single model to do multi type of like resolution super resolution tasks。

 but you know， at certain level， the utility of like， you know。

 doing super resolution for like super high resolution in diffusion models becomes like lower， yeah。

😊，Yeah， okay we also discussed like how to solve the import problem using the pre transd model in this class。

 including your paper， the P GDM in this class， so yeah oh yes。

So in in my basically the idea was that basically， you know， in classroom of free guidance。

 you basically try to treat the diffusion generated process as you know， like learning this like。

Gradient of the log probability。 So you have the gradient of log probability of your base model。

 but then you P of x， I think。 But you also have the conditioning， which is like a P of y given x。

 And basically in super resolution， we can just come up with a constraint。

 So we want to generate our constraint is basically that I want to generate some x that is close to the digital distribution。

 while with being downsled， it is this you know like a lower resolution image。

 So if you don't have the constraint， they would just generate that random image that doesn't do your super resolution task。

 So basically in my paper， and I think in like some other papers。

 the goal is to basically try to know approximate the term that is the log probability of y given x。

 So there's like different version of trying to approximate these things that like my work one particular way of doing this without going to too much details。

 So I guess the benefit of that is like you can actually。You know， use appreciate model and you know。

 do these different tasks at infrastructure。 But of course， with things like control Ne。

 you can actually also just train these tasks like a or they using not as much compute as you would expect。

 And this would this could also solve the problems in a reasonable manner。😊，嗯。Yeah。

 you I guess we can also combine the next two questions like both are about like。

 but the ability of the video division model， the video digitalgen models in terms like understanding the causality and many some physical roles and many things and also having some kind of capabilities about some precise the control I think you also partially answer those questions but。

Yes， so I guess in in this case， basically， yeah， these are kind of just the ongoing questions that is on the。

 you know， video generation model community。 So I think one of the。

Some of the techniques I think is similar to how you address hallucination in large language models so certainly you wouldn't say like large language models are you know like perfect in terms of like what they what they like like produce but the the responses certainly get better and better as you improve like posting techniques so for example you have like supered by and also like ROH kind of techniques that can be used to improve the quality of the models of course the。

😊，呃。The you know， like similarly for like medium models。

 I think you know like because this surreal or dreamlike representation is basically I think the hallucination of the of the model。

 so from the from a perspective I think using more of the post training techniques that language models inspire us to certainly will help improve like reflecting some of these like principles as well as they like causal relationships although I do have to mention that you know like。

😊，There are just the different approaches to solve the different problems and they're getting you know。

Like even getting some of the principles or causal relationships into the model doesn't have to involve。

 you know， like building this into the model。 It can be more like， you know， oh。

 I generate data from the human nature that actually be used as synthetic today synthesized data helps like guide the model。

 whether will like， you know， entirely soft the model。 I don't know。 So it's hard to say。

 The other question is like， you know。Can the model precisely control like physical properties， so。

The I guess then the manner of question is like how precise you want to be。

 So I think like there are certainly cases where， you know。

 it is good to like some people and maybe not good for some other people。 So for example。

 like I cleared like this year there's a submission called I light that actually tries to use like know like change lighting in the images。

 So certainly some of these techniques can also be used in there。

 So I would say like the models can certainly be used to control physical like properties， but。😊。

How precise is you know， be caresing because like in real physical worlds。

 the measurements are also like quite noisy and imprecise。 So for example。

 in like cases where you go to like microoscopic matter or you know， like you just you know。

 like uncertainty principles where like yeah， like just measurement is like not always precise in in in like physical world as well。

 So， so in that sense， I think like data can certainly help。 So and。😊，But you know。

 to how precise is something that we would really can only like experiment upon like we need to do the experiments to know what like colors they can do。

嗯。呃。Yeah， we have like one new question about some details about E PM and。Yes， yes。啊。

So in the DDI paper introduce it， yes。What might happen if the virus is increased further？😡，So， the。

Yes， okay， okay。 So I think in that case， it's really， you know。

It doesn't satisfy mathematics in a sense that， you know。

 it will give you a reverse process that like exactly reproduces the kind of a big reverse diffusion process in the DDPM case。

 so I would say this is you know like。Tricky to。Reason in like the mass case。 But of course。

 you know， just like you know， people are using some things that are not necessarily precise in mass。

 So for example， in classifier free guidance is actually also not precisely like measuring like correctly the exact kind of conditional like score like functions that you use to like sample from diffusion models。

 but know nevertheless people find this be super useful in practice。

 And I think similarly for these kind of applications。

 the reason why you would add a lot more noise is simply because that the the kind of the model prediction is further from the truth。

 So if youre modeling is precise， then using DDRM should be like better。

 And this has been shown in liketer carlysis like 2022 like Europe best paper called the like elucidated the diffusion called EDM。

 So in that case super data experiment where they have a very， very welltrained diffusion model and。

T different types of exemprs， such as the DDIM the determin one like DDIM and like non determincing was that un noisey。

And the finding was that adding noise adding noise certainly hurts if your model is like extremely precise。

 but of course， if your model is not precise， then adding noise helps in terms of like you know helping to like be more robust。

 So the model becomes more robust as the ad becomes like more precise。

 So that I think is the main differences and the image in painting tasks basically the noise predictions are just very heuristic and very imprecise。

 So adding more noise probably just help in the sense that it will like mask out the imperfections of the prediction and it's just generally more robust。

😊，Yeah。Thank you， yeah， it's really good to know to learn those things from the A of BDDI， thank you。

😊。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_208.png)

I'd like to wrap up this session with the one last question so I'm just wondering how you envisionvis the future of genetic the AI the technique and for the next like three years or the five years like what would be happened and also I guess there might be many students here who might be dreaming of some kind of career in this like building the vision AI so I just want to ask you to give some kind of a bit of some kind of advice in terms of how they should also prepare the future。

Yes， yes。 So I think at least for video models， I mentioned that the future is， you know。

 going into like similar trend in like large language models。 So you know。

 like freeing post training and， you know， going into these directions and you know。

 solving the efficiency problems of video models certainly is also very important and you know。

 being able to have， you know， as I have listed in some of the future works， you know。

 being able to maybe combine the future models and auto regressiongressor models and having you know。

 which like taking the advantages of both sides is also going to be quite interesting。

 So as for like career rise， I think it you know， it's。😊，It's you know。

 they' like if you're pursuing like like a PhC programs in perhaps like the the more reasonable choices to do like。

 you know， research scientists or do go into industry or you know go to academia and in this case。

 you know， going into academia requires like more you know like like papers or groundbreaking papers and。

 you know， going into industry not as much but you know a lot of the kind of industry like or。

Like knowledge。 And I think depends on what you want to do。

 It's certainly like a slightly different set of skills。 But I think as you know。

 we go into this like more foundation model kind of skills， like。

 you know things that are like more practical such as data side of things as well as like like in set of things become like actually at least a lot more like relevant than what I was doing my PhD like during like my PhD。

 we only have like like 2080 as the GP and I did all the like know DDM experiments on like or like to like2080 GP。

 I had no almost nothing thing about like distributed training。

 And I was actually mostly just using like like。😊，Like like data parallel itself of a distributed data parallel in like effort。

 So like certainly， I didn't know much。 But I think， you know， at this day and age， like。

 it is very important to be able to kind of a embrace the like change that has been brought by foundation models and like them being kind of a like learning fast and。

 you know， like being able to kind of a take。😊，Like like learn new things quickly is certainly going to be like very important in this like very rapidly like advancing age and yeah I don't have very good system signal advice because I think like the the situations that。

Different every year。 And， you know， this also。Like the field is also becoming like a more and more competitive and unfortunately less kind of a。

 you know， acceptable for like like ideas that are like a smaller scale， but like really low。

 but I think， you know， at least working along the lines where the general trend is going is going to be helpful for like coming up with like research ideas or you know。

😊，Like pursuing a career like in the field and another like final piece of like advice is like the。😊。

I think like eventually people like。As since the case for me like people remember you for the you know most impactful thing that you do and similar for me like I have like probably like a 30 or 50 papers during my PhD but you know people mostly remember TDN so I think this is the same case regardless whether you go to like academia or going to industry it's very important to kind of a target for like high impact things rather than like you know spend a lot of time on like many many incremental things so yeah that's it。

Yeah， really great advice。 I think that would be very helpful for the many instance here。 Yeah。

 by the way， are we attending rapes this time。😊，Possibly， but I won't be saying long if I if I work。

 but I haven't finalized my like if you are attending I be happy to also Okay。 thank you very。

 thank for and also all the insightful comments and also thank you for the audience for joining today。

 So yeah， me。 Thank you。 thank you Thank you thank you， happy to be here Thank you。 you。

