# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p24 2024 ｜ Introduction to Deep Compression Autoencoder [BV1c8wNe1ErX_p24]

As you can imagine， the more we can press。The less the workload。

 the smaller the number of resolutions， smaller the number of tokens。

So recently we invented a deep compression of。Rather than compress。We can cope it by eight times。

 so we can compress it by 64 times。我 does that mean？

It means eight times more compression in each side and altogether you have how many fewer proteinskens。

64 times fewer confidence because each times double。拖是土啥。64 times less voltage。

And how does that impact the attentions。很快次的。For thousand time。But problems， right？せです。

The pension computation complexity is quara。poraically related to the number of tokens。

 were reducing each side by eight times altogether in 64 times less tokens。4 thousand9 six times。

So this is original stable deputions。Myational encoder VAAE reducing the resolution by eight times passes the diffusion model pretty slow。

This is our proposed approach using deep compression of COD。スポタ。

On each side those would be different models and make it much faster。However。

 this is not straightforward my approach， for example， a CDAE， under 64 kinds of compression。

 the quality is very poor， but use a deep compression BE。The quality is much better。

On the abouttime side， we have the entire compression ratio， the higher the compression ratio。

More preferable， but at the harder。Based on methods， STVE， the FID dec rates very rapidly。But。

Keep compression， altering coldD phase。Very stable F even given 128 times compression ratio。

And how did we achieve that？So reducing the resolution。You have a very打 approach。

You can directly move the information from spatial dimension to the channel dimension。

Say every two by two pixel， four pixels。You can change it from two times  two times 1 into one times one times 4。

So that's the explicit transformation from spatial to China。And by explicit spatial to channel。

 we can have this explicit spatial to channelal branch。呃。土地当山后。

And added this explosive channel to the spatial branch to the outside polar block。

We call it residual of in coding。So rather than using the weight by the weights to learn such stuff。

Zero wait， French， no wait。Z with branchch。As a residual bypass。

To learn this and we find I would argue you this residual output coding makes it a lot easier。

For example， the RFID without residual auto codinging will deter with third fast。You have 64。

It remains very stable and they're high from ratio。

The second technique is three stage adaptation to high resolution。

 so we want to deal with high resolution like 4K like 4K image generation。

 so how do we have an audio encoder to support so much higher resolution without requiring a lot of training blocks。

So we decoup it into three phases， the first phase。

 we just performed lower resolution between the whole， both the encoder and the decoder。

 and given an image encoder encoding into a latetnt space and the decoder reconstructed to the original image。

 and so this is lower resolution full training。InThe second S， we ordered the safe computation。

We perform high resolution latent adaptation only to the middle layer。

So the middle layer correspond to classifiers last。Only human is made middle layers。And phrase。

Remeion。And finally， we added this catalog locks。To further college。

To do some refinement only to the last layer of the decoder。

 since that's only related to the low level features。

 The low level feature is actually refined in the last stage。We do such layer Y sparse tuning。

 not tunening all the layers， but sparsely tune at the middle layer or the late stage to save the computation and make it very fast to train such a auto encoder。

So using this auto encoder， we can greatly accelerate。The啊 image generation一就是 model。

So this is using the original latent space。I see the AU， which is think times reduction。

So it's pretty slow， it generate only 17 images per second。Andside we are using this。こ啊。

Times compression。I have 64 reducing the number of。Okay this problem。

Using the resolution from512 to 8 by8。So we can confused on almost Wednesday before COs。

HoweverPrevious we have to keep used。4K， so it's a lot faster， 19 times faster。

P the refuse in the original。Autoender， so autoender matters a lot if you can apply such deep compression autoencoder。

 you can have much fewer tokens。Cora reduce。The communicationplication blockss for inference of models。

And another benefit is that now we can。Achieve high resolution and image generation without using a lot of computes。

For example，4K image generation。多开的是。不看的 detail。是4K吧4K。Generation。Comparative with one pay。说到用个张州。

The4K has a lot more details。まだの？patient if you don't use。Techniques like deep compression。

 auto encoder。