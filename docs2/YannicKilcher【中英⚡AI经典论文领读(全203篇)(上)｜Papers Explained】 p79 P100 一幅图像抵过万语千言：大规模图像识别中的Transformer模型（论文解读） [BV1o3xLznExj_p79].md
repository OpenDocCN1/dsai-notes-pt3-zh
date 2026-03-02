# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p79 P100 一幅图像抵过万语千言：大规模图像识别中的Transformer模型（论文解读） [BV1o3xLznExj_p79]

Hi there， today we'll look at an image is worth 16 by 16 words。

 transformers for image recognition at scale。So this paper is a bit special。

 Andre Kpathy tweeted this out， and I'm going guess many of you have seen it already。

 It's a paper that's under review at ICl。 IClar， of course。

 uses open review So all these submitted papers can be seen and can technically be commented on and as you can see。

 it's anonymous and good thing it's anonymous because the double blindind review process relies on anonymity。

 So we can really evaluate this paper which is a very interesting paper at its merits without。

 you know， having a clue who would be writing something like this。 Now， out of pure。😊。



![](img/79f3979a791785f69df5da42389b9e11_1.png)

Out of pure randomness， I just happened to have this in my like control C control V memory。

 I just pasted this here。 I don't know why， but this is this other paper called Big Trans general visual representation learning by Alexander Kniov Luka Bayers Xhua Chai and others of Google research。

 I've actually made a video about this。 So if you're interested totally ran not related at all。

 I mean， yeah， so。

![](img/79f3979a791785f69df5da42389b9e11_3.png)

![](img/79f3979a791785f69df5da42389b9e11_4.png)

![](img/79f3979a791785f69df5da42389b9e11_5.png)

![](img/79f3979a791785f69df5da42389b9e11_6.png)

![](img/79f3979a791785f69df5da42389b9e11_7.png)

![](img/79f3979a791785f69df5da42389b9e11_8.png)

Disregard the fact that the paper that we're discussing here uses a GFT 300 M data set that is not available to the public only to Google that is。



![](img/79f3979a791785f69df5da42389b9e11_10.png)

And actually， this other paper also trains on that。

Disregard that also largely disregard the fact that their model is called。VIT。Well。

 the other paper model is called B， I T。 disregard the fact that they train on the exact same data sets。

 as you can see right here。 I mean， this here is imagenet。 Then see for 1000 pets， F and the V tabab。

 V tabab， these visual task adaptation benchmark。 I've done a video on that， too。 by Google。

But they do have actually the Inet reel here， which is just a set of new labels for INe。

 which comes out of a paper by Google with largely the same authors as this paper， I mean。

 dissregard the fact that the color scheme for the VTab evaluation is exactly the same as is the histogram plotting and of course we don't even want a bi about the plotting style with these bubblebble sizes and so I mean anyone could do this anyone。

 anyone in the world could just randomly have this much overlap with these models and of course anyone just has the money laying around two train on 2。

5000 TPU V3 days and you know compared with 9。9000 TPU V3 days for the BIT。



![](img/79f3979a791785f69df5da42389b9e11_12.png)

![](img/79f3979a791785f69df5da42389b9e11_13.png)

I guess you could just pick those numbers out of the paper， but what do I know？So。No， don't worry。

 peer review is totally fine like like， I mean， yeah， so I hope I've made my point。



![](img/79f3979a791785f69df5da42389b9e11_15.png)

This is by these people。

![](img/79f3979a791785f69df5da42389b9e11_17.png)

And。You know， people say you know， we need anonymous on archive because the danger is that people upload their paper and archive and then we can see who they are。

 I think this should prove to anyone that an anonymous archive is like it's the crapies why， why。

Like， why would you ever work against the core incentives of people Like clearly these authors have an incentive to make known who they are and clearly we as readers have an incentive to figure it out and to completely work against these incentives just seems so it seems dumb。

 It seems counterproductive， and it doesn't work as you can see， what do you want to do。

 standardize the plotting styles， standardize everything standardize the citations。 I mean。

 come on here， you go like。

![](img/79f3979a791785f69df5da42389b9e11_19.png)

![](img/79f3979a791785f69df5da42389b9e11_20.png)

![](img/79f3979a791785f69df5da42389b9e11_21.png)

![](img/79f3979a791785f69df5da42389b9e11_22.png)

When we compare， oh， no。嗯。Where is it。WhenWhen they compare against things， they say， oh。

 our first point of comparison， our first point of comparison is the big randomly。

 just big transfer by these authors that we have no relation to maybe or maybe not。😊。



![](img/79f3979a791785f69df5da42389b9e11_24.png)

It's ridiculous， you can't shield this fake anonymity。

 this is actually counterproductive and it only helps the big labs， this anonymity criterion。



![](img/79f3979a791785f69df5da42389b9e11_26.png)

![](img/79f3979a791785f69df5da42389b9e11_27.png)

Alright， let's actually dive into the paper after this ran。 Well， yeah， yeah， don't worry。

 peer review， very pristine， very good， very anonymous。 Dole blind for sure。



![](img/79f3979a791785f69df5da42389b9e11_29.png)

U。So， the。

![](img/79f3979a791785f69df5da42389b9e11_31.png)

Paper says， while the transformer architecture has become the de facto standard for natural language processing tasks and we know this。

 you know， this is from the first attention is all you need paper to things like Bert， GPT， GPT2。

 GPT3， transformers have revolutionized NLP。sayy its applications to computer vision remain limited Invision attention is either applied in conjunction with convolutional networks or used to replace certain components of convolutional networks while keeping their overall structure in place。

 which is correct in computer vision convolutional networks have been so incredibly successful since Alexnett and then of course Resnets being the major contributor there。

 I mean even this big transfer paper right here， all it does is scale up Resnets and then feed in more data。

 so CNNs are extremely extremely powerful in computer vision。



![](img/79f3979a791785f69df5da42389b9e11_33.png)

![](img/79f3979a791785f69df5da42389b9e11_34.png)

![](img/79f3979a791785f69df5da42389b9e11_35.png)

We show that this reliance on CNNs is not necessary。

 and a pure transformer can perform very well on image classification tasks when applied directly to sequences of image patches。

And they go on saying that they outperform CNNNs while requiring substantially fewer computational resources to train。

 Well， you know， substantially fewer in these regimes of thousands of TPU days is， you know。

 something that。

![](img/79f3979a791785f69df5da42389b9e11_37.png)

![](img/79f3979a791785f69df5da42389b9e11_38.png)

![](img/79f3979a791785f69df5da42389b9e11_39.png)

Is a bit ironic， honestly， but， you know， it's it's， it's， it's pretty cool。

 So what's the deal with transformers and images。 classicalically， transformers are， of course。

 things， models that operate on sequences， specifically actually， they operate on sets。

 So you'd have a set of words， which you can characterize as tokens。

 which I'm just gonna characterizes as bubbles。 And then the transformer would somehow take all of these in and do something with them and something in this particular case is attention and attention is a quadratic operation。

 which basically means that you have to calculate the pairwise inner product between each of these between each pair of the。

😊，Of these bubbles， which becomes a very， very large task very quickly。 you see。

 I even have trouble drawing， I think I drew this twice。However， this already with five， it is many。

 many， many interconnections and you can imagine that if you are in NLP and have a paragraph that's maybe 500 tokens long。

 you need 500 squared connections， so this one thing is the limitation of transformers。

 they work really， really well for NLP。😊，However， they are limited by the memory and compute requirements of that quadratic attention。

Images are therefore much harder for transformers because an image of course。

 is a raster of pixels and there are many， many， many。

 many pixels to an image so usually even in sort of IageNe might be IageNe counts as a large images in computer vision applications。

 but even the INe they are like what 250 by 250 pixels which are small by human standards。

 we are used to looking at。I don't know， 1000 or 2000 pixel。

Side length on a regular basis for it to be clear， I mean even the raization of this PDFf you can see is you will recognize it as blurry and that's that's way way more resolution than imagenet images so the just thesterization of images is a problem in itself。

 even for convolutional neural networks， but if you want to feed this into a transformer。

 you have to think that every single location here。

 every single pixel has to attend to every single other pixel which。



![](img/79f3979a791785f69df5da42389b9e11_41.png)

![](img/79f3979a791785f69df5da42389b9e11_42.png)

![](img/79f3979a791785f69df5da42389b9e11_43.png)

The image itself is 250 squared。Big， so the attention will cost you 250 squared squared。

 which is impossible in current hardware even for Google right， maybe they can do it but。

So people have resorted to other things， doing things like only local attention。

 so only attending to the kind of area around them， which of course is the。



![](img/79f3979a791785f69df5da42389b9e11_45.png)