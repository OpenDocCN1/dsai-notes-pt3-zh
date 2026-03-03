# Vizuara【中英⚡多模态LLM中的Transformer｜Transformers for Vision and Multimodal LLMs】 p07 P12 Introduction to Swin transformer [BV1X9zuByEuF_p7]

Welcome to a new lecture。Today we'll be learning about Sw transformer architecture。

 Sw transformer is a natural extension to the two transformer architectures that we learned in the last few lectures。

 especially vision transformer and data vision image transformer。

So I originally thought we will first try to understand an intuition and then coding from scratch today。

 but Sw transform architecture is actually a little bit more complex so I'm splitting this into two parts in today's lecture will be understanding an intuition which I will also remind you to kind of brush up once before the next lecture and next lecture we will code a Sw transform from scratch and code will be a little bit more complex than anything that we have done so far in this course。

So I really want you to be on your full attention today and next week。

 because there are a few things about the implementation of Sw transformer that are not so straightforward。

I will also be putting out a video on a review of the Sw transformer paper。

 so I've been going through the Sw Transer paper in detail。The paper is really dense。

 it's from Microsoft， the paper has around 38，000 citations。

 it's I think it came out in year 2021 and it's from Microsoft Asia research team。



![](img/87dfdb6cae0b813d77630435ac27c0f2_1.png)

![](img/87dfdb6cae0b813d77630435ac27c0f2_2.png)

And they showed。Probably in the most convincing way for the first time that transformer architecture can become a good backbone for pretty much any kind of universal image task like classification detection segmentation etc。

 so that's the relevance of this paper。But one thing I personally found from the paper is the paper is not written in the best possible way。

 it's it's very dense and I wish they had。They were not so frugal in terms of number of words while writing。

 but in any case that's the reason why we will spend a lot of time on the architecture itself。So。

With that， the swing transformer architecture is basically an a short form of shifted window transformer so shifted we'll see what what is window and what is being shifted。

It has a lot of things similar to vision transformer。

 so your past knowledge from how vision Transer works will be useful here。

 but there are also quite a lot of differences and architecture when I show you the architecture diagram you will understand。

So in vision transformomer， it was doing this in a brief nutshell。

 you had an image of height width and number of channels。And then this image was split into patches。

 patches are basically non overlapping and each patch is considered as a token。

And then we flatten these patches into like an array。

 so in this case you have nine patches representing the image and then one patch is added as a classification token and all these one token is added as classification and all these tokens also are added with position embedding。

And then that whole sequence of tokens is was what goes into the transformer architecture。

And transformer architecture is something with self attention without masking because here the task is not expert word prediction because of which masked multiha attention is not not needed。

 it's unmasked。And then after going through attention it the CLS tokens context vector alone goes into MLP classification head and then here you decide what class this particular image belongs to。

In data efficient image transformer， we had some differences， one was an extra distillation token。

 distillation token was appended at the very end。And distillation token was trained on the predictions made by the teacher model。

Classification token was trained on the ground truth in the last lecture we saw how data efficient transformer can be much more lightweight it was trained on just Iate 1k dataset set。

Now a vision transformer， although it was great， it had bunch of issues。

 specifically with respect to computation。😊，So just look at this。

 if you have an image of let me not show you this first， I'll just ask you。

 let's say you have an image of Tce I or image of height H and width W。And let's say batch size is B。

Totally how many patches do you have in this whole image mathematically based on these three parameters？

You can mention in the chat。The total number of patches。

It should be you have h by P patches along the height。

And w by P patches along the width total number of patch will be h by P multiplied by w by w by P right these many patches are there。

And which means number of tokens is same as this。Number of tokens is same as number of patches because each patch is converted into one token。

Now， if we were to construct self attention。In self attention， you have to do the。

Dot product between query and key， so Q dot key transpose。And bunch of other things， also。

But when you perform this calculation。The order of magnitude of complexity is proportional to what so if I were to say order of complexity of attention。

Is proportional to what？Is it proportional to the number of tokens or is it proportional to something else？

It must be proportional to the square of number of tokens Why is that because you will have n。Quries。

And you will have N keys。And every single query is taken as a dot product with every single key。

 so the order of magnitude of this attentions complexity attention computation complexity will scale with the square of number of tokens now what is square of number of tokens what is hW actually。

😊，What is the product of H andW， HW equal to what？In terms of image， what is this？

It is a total number of pixels you have h pixels along the height W pixels along the width。

 so HW is basically image size if we were to denote image size by the total number of pixels。😊。

So from that point of view， in transformer， okay？Vision transformomer is great because you can construct global attention or long term long range dependency between tokens that are geometrically far away you can have a strong attention score between top left token and bottom right token it's possible。

But。😊，The complexity of attention calculation。Will scale。With n square。

N square is proportional to hw square。Which is basically image size。or number of pixels in the image。

 so basically if you double your image size or if you double your resolution。😊。

Your order of magnitude of the attention score calculation will will go up by4。

 the complexity will go up by a factor of four this is why it's called quadratic complex。😊。

So this was one issue with self attention it becomes immediately challenging for high resolution images and you you know。

 if you want to perform tasks which are。like semantic segmentation or instant segmentation where every single pixel is classified instead of classifying the whole image or instead of drawing a bounding rectangle around the object for such tasks you need higher resolution images and higher resolution images are always problematic for vision transformers so here in this image Im showing you an example so you have let's say number of tokens n equal to5 then you have five queries and 5 keys which means your attention score or attention weight matrix will be5 by 5 so basically it is scaling as n square。

So if you have an image of height 80 and width 80 and patch size 16 by 16。

 you totally have five patches along the height and five patches along the width。

 which are 25 patches。If you increase the image size from 80 to 160。

 I mean total number of pixels are becoming 4x。Your attention complexity actually becomes 16x。

Because you have 10 tokens along the height row and 10 tokens along the height so totally now you have 100 tokens。

100 tokens as queries and 100 tokens as keys so 100 queries are attending to 100 keys so 100 by 10010000 so 625 order of complexity will become 10000 so 4 x increase in number of pixels result in 16 x increase in complexity so 16 is the square of 4。

This is a problem with vision transformer。So what vision swing transformer does is。

It basically limits its attention to some local windows so what I mean by local window is attention is not constructed。

By considering all these patches at once， it will construct a local window which may look like this。

Something like let's say this is a window of2 by two tokens or two by two patches so inside this window only attention is calculated then inside this window attention is calculated inside this window is calculated like this。

So we will see why this leads to a better computational efficiency。😊。

Because in the paper they claim that they have linear computational efficiency。

 we'll see why it is linear and not qua it and we'll also see some issues by converting attention into from global thing into a local thing。

😊，So this。

![](img/87dfdb6cae0b813d77630435ac27c0f2_4.png)