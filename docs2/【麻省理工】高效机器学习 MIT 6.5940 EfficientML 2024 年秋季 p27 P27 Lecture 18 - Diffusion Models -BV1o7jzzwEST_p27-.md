# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p27 P27 Lecture 18 - Diffusion Models -BV1o7jzzwEST_p27-

Welcome to lecture 16 of efficient ML of AI。 So today we are going to learn about efficient diffusion models。

 how to accelerate diffusion models。In the previous lecture。

 we've briefly talked about deep generative learning so we first truly a model and then we can predict the data distribution。

 so different from disriminative model， which is to predict the decision boundary。

 the generative model tries to predict that the distribution of the data。



![](img/216341b3c3dcc759907e30f02f7a4659_1.png)

So there are lots of applications for generative model， for example photo editing， image generation。

 you may use a mid journey to generate images and open airO can generate videos as well。

 but all these generations are pretty computationally intensive so in this lecture we are going to learn about how to make these algorithms more efficient much cheaper to run on the hardware。

So this is the landscape of deep generative learning we've covered previously already covered generative adversarial networks。

 we will also talk about the heart auto regressive model using aken token in token out approach to model that。

Today we are going to talk about diffusion models。 We also introduce efficient auto encoders。

 So this is the landscape of deep geneuative learning。



![](img/216341b3c3dcc759907e30f02f7a4659_3.png)

So here's the agenda for today， we are going to first talk about the basics of diffusion model in order to accelerate it。

 we need to first understand how diffusion model works including denoising。

 conditional diffusion models， latent diffusion models， image editing and personalization。

Next we are going to introduce fast sampling steps the VDM method， dissillation method。

 and also acceleration techniques using sparsity quantization and also multi GPPU parallelism。

And the figure right on the right hand side is the model Sanana developed ourselves。

And showing a cyber punk cat with a new sign that says MI might T。Okay。

 so let's first introduce how diffusion model works and diffusion model basics。

So there is two concepts， one is the forward diffusion process the other is the reverse diffusion process。

 so during the forward diffusion process we try to add noise to the data。



![](img/216341b3c3dcc759907e30f02f7a4659_5.png)

So the data becomes noise in the reverse process we gradually deno。



![](img/216341b3c3dcc759907e30f02f7a4659_7.png)

And release and review the data。So this can be illustrated in this image the first is the forward pass the second one is the reverse pass and see the forward pass we are trying to destroy the data by gradually adding a small amount of caution noise so originally the image is a。

To different different distributions now they become the noise。And during the reverse process。

 we are trying to create data by gradually benoy in the noise from a stationary distribution finally we converge to review the original image。

So this is a multi step。Process okay so the forward process is basically adding the noise and starting from a data across many steps。

 then it becomes a noise。And。And the FA is actually dependent on the previous staff。

So it's a Gaussian distribution with the mean of this is the mean is related to xt minus1 previous that。

On the barriers is a Gausian noise。So this beta T is prede to control the equation speed。

 so this is the relationship between t and beta t。So as the forward process to add noise。

 we get a relationship between Xt and Xt minus one。



![](img/216341b3c3dcc759907e30f02f7a4659_9.png)

And then what about sampling xt directly from x0 from the original clean image， how do we get？



![](img/216341b3c3dcc759907e30f02f7a4659_11.png)

The noisy image， I have a time sta T。So this is a long derivation。

 but actually it's quite simple since this xt is linearly related to xt minus1。

 we can define alpha t to be y minus beta t so we can rewrite things equation like this。



![](img/216341b3c3dcc759907e30f02f7a4659_13.png)

This is a relationship between xt and xt minus1， we can expand this equation by inserting the same relationship between xt minus1 versus xt minus2 so that we can represent xt with xt minus2 epsilon t minus2 and epsilon t minus1。

I think in two different Gaussians we have this property so that we can combine these two terms the noise term together so we get a relationship between xt and xt minus2 on and so on we can all the way get the relationship between xt xt minus1 minus2 minus3 all the way to x0 and with the combine the noise and we can shorten that by defining the alpha t bar to be the product of all the alpha I and as a result we can represent xt as a relation with respect to x0 plus the noise okay so this is the mean and this is the variance。



![](img/216341b3c3dcc759907e30f02f7a4659_15.png)

So now we have the relationship between the original clean image， which is x0。

 and then at each time step t， what is the xt？

![](img/216341b3c3dcc759907e30f02f7a4659_17.png)

![](img/216341b3c3dcc759907e30f02f7a4659_18.png)

![](img/216341b3c3dcc759907e30f02f7a4659_19.png)

So we define this relationship between Xt and I0 as the diffusion kernel so for sampling XT equal to the relationship between I0 and the noise so beta is designed as such that when alpha t close to zero。

 the distribution is close to the normal distribution。So given a at any time step T。

 now we can represent that as a function of x is zero。

So that's the forward process gradually adding noise。

 you can define any time step respect to the first time step zero。

Now we are going to talk about the reverse process， the reverse binnoizing process starting from Xt。

 we want to obtain x0 okay。So when beta t is small， the relationship between Xt minus1 and t。

 so the adjacent two steps is also a Gaussian。That this is the mean， which is learnable。

 basically that's what we are trying to predict。Are consuming the majority of the computation flops。

Given an XT to get the mean and the variance is also a caution。



![](img/216341b3c3dcc759907e30f02f7a4659_21.png)

So let's see in practice how do we finish the cleaning so given a clean image。

 it this a clean image which is x0 seems we have the relationship between x0 and xt so xt basically equal to x0 plus noise so x0。

 this is getting vector plus noise because is getting factor。

 so square root of alpha t square root of a y minus minus alpha t， which is exactly the same here。



![](img/216341b3c3dcc759907e30f02f7a4659_23.png)

And theippsilon theta is the neurallateral model predicting the noise， okay so we add them together。

 we pass it we get the Xt and then we pass it through the model epsilon theta to predict the noise to predict the added noise and this is our predicted noise this is the noise that we originally added to x0 and then we try to match the predicted noise with the original added noise so that we can have a MIC loss right here I try to try to match them together。



![](img/216341b3c3dcc759907e30f02f7a4659_25.png)

So that's basically the training process， so although the equation is pretty complicated if we draw it in the figure is actually quite simple right。

 so we sample a T， sample a T。

![](img/216341b3c3dcc759907e30f02f7a4659_27.png)

Although we can。嗯。Sample x0， sample image， maybe a cat， maybe a dog。

 And then when sample annoys from from the Gaoin distribution。

And then we add them together by adding the sum up together to get Xt and we predict the noise greater than the Xt okay so ypsilon theta given them the Xt and try to predict the noise。

And try to match the noise that we originally sampled so that's how we add noise to the training process okay so basically the training part is trying to predict the noise。

 make sure the noise match the noise we inserted to to the image。



![](img/216341b3c3dcc759907e30f02f7a4659_29.png)

So that's the training algorithm。What about inference， what are we doing during the inference time？

So。

![](img/216341b3c3dcc759907e30f02f7a4659_31.png)

啊。Given a noisy input at XT okay so we pass it through the model Ipsson data。

 so what are we trying to predict？We are trying to predict xt minus1 okay。

 so we already have the relationship between xt minus1 and xt， so this is the mean。

 this is the variance， the mean we are trying to predict。

Predict that by using this equation and so new data is a combination of XT and epsilon Xt okay so it's a combination of Xt and epsilon XT the epsilon XT is basically predicting the noise given this input and so given this input the model epsilome data is predicting the noise。

 what is the noise inside this image。And we subtract the noise， this is subtract。

 we subtract the noise from the image， these are the sating factors。

 we subtract noise from the image， we get a cleaner image。

And a cleaner image is added with a noise and then get the denoed image xt minus1。so in that way。

 we complete one iteration from a noisy input image。

 a noisy image X T to get a cleaner image Xt minus one。The rule of thumb is D noise。

 we first predict the noise okay predict the noise using the epsilon datata， this is the model。

 this is the majority of the where the computationmplication goes。Predict noise， subtract noise。

 okay， and here you actually added another noise。Another co noise since xt loses the mean。

 this is the variance， and we have to add back this noise to get the noise image。



![](img/216341b3c3dcc759907e30f02f7a4659_33.png)

So that is just one time step， one step of denoising from a noisy image to a cleaner image。

 and then we can repeat this process so that xt minus2。

 xt minus3 all the way to x to zero so that's the entire denoising process。

Different from the previous models where it's just one time now we have to run it the same model it so this is where the majority of the computation goes so it's dense prediction you have to make pixelized prediction。

 not just a class not a bonding boss but you have to make pixelized prediction。



![](img/216341b3c3dcc759907e30f02f7a4659_35.png)

That's why this model is usually pretty heavy and taking the majority of the time， making it slow。

Another reason it is slow is because we cannot do it using just a single step or very hard to do it in a single step。

 but actually we need a lot of steps， that's why it makes it slower。

So these are generated images actually outperforming GNs on the image9 data set。

 so it's a pretty good result， pretty good start。Okay。

 so now let's talk about conditional diffusion models， we don't want to just give a random image。

 but we we want to condition the generation on either a class， for example。

 we just want to only want to generate a cat or a dog。Or tax condition， for example。

 a sequence of text opens a photo of a moon gate。

![](img/216341b3c3dcc759907e30f02f7a4659_37.png)

Sometimes we also want to add the pixel wise conditions， what is pixelized conditions。

 so given this spatial map， like a segmentation map， a cat or a tiny edge， the edge of a cat okay。



![](img/216341b3c3dcc759907e30f02f7a4659_39.png)

![](img/216341b3c3dcc759907e30f02f7a4659_40.png)

So we not only need to provide a timet， but also a condition add a condition to the model。

So let's see， how do we perform conditional image generation using diffusion models？



![](img/216341b3c3dcc759907e30f02f7a4659_42.png)

So one idea is to use this scalar condition， a very simple spatial addition。

 so this is the original feature map， this is the conditioned feature map， how do we condition map。

 given a class ID micro a cat， maybe ID number 776。

And then we encode that by passing it through several multi perceptions。

And then we get an embedding batch size times C is the channel versus the original feature map is PC HW。

 so we broadcast a single element to H times W and then we。

Perform this broadcast addd to add them together together get conditioned feature map。



![](img/216341b3c3dcc759907e30f02f7a4659_44.png)

So that's how we add this class condition。We can make it a little more complicated right。

 for example， we can pass it through a larger NT to get two parts B times 2 C a one is the scalar。

 one is the bias。

![](img/216341b3c3dcc759907e30f02f7a4659_46.png)

So we we scale the feature map we can also add to the feature map to get the condition the feature map That's another way to add this kind of。



![](img/216341b3c3dcc759907e30f02f7a4659_48.png)

Scalar condition okay。How do we add the tax conditions？Now we have two modalities。

 one is image modality， the other is text modality。So during visualual language model， like the Vla。

 we discussed in previous lectures。We find it's possible to project image and language。

Both of them into tokens and as a result we can use cross attention to combine image and language。

 for example， the input feature we divide it into several edgees。

 each patch is a token so we can tokenize them。

![](img/216341b3c3dcc759907e30f02f7a4659_50.png)

So for the text， we also pass it through the the Q K V matrix。 we get the Q token query token。

 key token and value token so。We first do QK transpose。

 so QK transpose and we use that to the weighted sum for the output token。

 so the final dimension token dimension is still the same as the query which is the number of image tokens。

 so the output result is still an image。

![](img/216341b3c3dcc759907e30f02f7a4659_52.png)

But that already included the information from the language。



![](img/216341b3c3dcc759907e30f02f7a4659_54.png)

![](img/216341b3c3dcc759907e30f02f7a4659_55.png)

Okay so that's one way to add tax condition。Insert the text condition into by image generation。

There's another way to do joint attention in the previous method。Are they in？Actually。

 language and image， they are not symmetric。

![](img/216341b3c3dcc759907e30f02f7a4659_57.png)

So the image is treated as the bery。The language is treated as the key and the value。



![](img/216341b3c3dcc759907e30f02f7a4659_59.png)

So the language and image， they are not a symmetric。But in the joint attention。呃。

呃 the language and the image。

![](img/216341b3c3dcc759907e30f02f7a4659_61.png)

The image feature and the text feature are actually symmetric。

So they are passed through independent QKV transformations。

 so this is the QKV transformation for the image， this is the QKV transformation for the language。

 for the text。And then we cannate them after the transformation。

 okay so this is the query from the image feature， this is the query from the language feature。

 you can catate them together to get a combined image text feature for the query combined image text feature for the P combined image text feature for the value。

 and we feed them together to the attention okay。And after we get the output。

 we split it by passing them through different output transformations， so there's QKDO for the O。

 we also have independent WO for the image feature and also for the text feature。



![](img/216341b3c3dcc759907e30f02f7a4659_63.png)

![](img/216341b3c3dcc759907e30f02f7a4659_64.png)

So on the right hand side is another diagram showing this relationship， so image and text。

 they are passed through independent2V transformations and then contaminat it together。

 perform joint attention and then split it with separate WO matrices to perform NOP and for the next layer。



![](img/216341b3c3dcc759907e30f02f7a4659_66.png)

What about totally combining them together early so this is another approach。

 a single self attention to combine the image feature and text feature text condition so the tokens are early contaminated before we feed them to the QKV transformation。



![](img/216341b3c3dcc759907e30f02f7a4659_68.png)

Since the image feature and text feature are contaminated already。

 so we can beat them to the same2KV transformation， okay。

And after we pass them through the attention， we have a single output transformation。



![](img/216341b3c3dcc759907e30f02f7a4659_70.png)

So this is the early fusion for the image and text text text feature。

We can also perform pixelized condition okay we've talked about class condition so using a class。

 we talk about a language text condition using a sentence to describe what you want to generate。

Now we want to do pixel wise condition， for example。

 we want to generate something that follow the edge。Described here。

 this is using a any edge detector to find the edge。As a result， the generated image。嗯。

Together with a text prompt and exactly follow。The the edge from here。

We can also use input human pose and input human pose extracted from here This is the little head。

 this is the。The body， the hands。And then we can generate several images and the traffic in the kitchen following exactly the same。

Human pose or even a Lincoln statue following the exact input human pose。

And that is by using Control at， which is a new technique published last year。

To add the control by conditioning on pixels so how does that work。So this is how control networks。

Previously we have a neural net given noise we can predict the image。

 now we freeze the original network， but we make a trainable copy and we make a trainable copy。



![](img/216341b3c3dcc759907e30f02f7a4659_72.png)

And we insert the condition。From for the trainable copy。

Started with a zero convolution so that when the trading starts。

 this branch has no effect since this is zero convolution before and after okay？

And during the training they start to change and we make the trainable coffee。

 we call this part control net， so this part is controlling the main branch， so we have two branches。

 controlNe control is the main branch and the main branch is locked。

 the control net is a trainable copy of the original branch。



![](img/216341b3c3dcc759907e30f02f7a4659_74.png)

These are zero initialized one by one convolution such that the training is very smooth。

 the starting point is basically to nothing is on the branch and we only have a this retreat trade model。



![](img/216341b3c3dcc759907e30f02f7a4659_76.png)

![](img/216341b3c3dcc759907e30f02f7a4659_77.png)

So let's dive one step deeper to expand that unit， so we add these pixel wise conditions from here on the right hand side。

 it could be either the semantic mask， hanging edge。

 whatever pixel wise information you want to insert。



![](img/216341b3c3dcc759907e30f02f7a4659_79.png)

![](img/216341b3c3dcc759907e30f02f7a4659_80.png)

![](img/216341b3c3dcc759907e30f02f7a4659_81.png)

And we keep the original condition， including the text， the prompt， and also the times step。



![](img/216341b3c3dcc759907e30f02f7a4659_83.png)

So that's the original condition we copyied these down sample stages， so these are the down stage。

We copied the condition control branch from the original branch while we are freezing all the layers of the original branch。



![](img/216341b3c3dcc759907e30f02f7a4659_85.png)

And then for the up sample part， we just pass it through zero convolution。

 so we only copyied the half only copyied the first encoder block， but not the decoder block okay。



![](img/216341b3c3dcc759907e30f02f7a4659_87.png)

![](img/216341b3c3dcc759907e30f02f7a4659_88.png)

So this is how we add the HO wise condition beyond the tax condition and also time condition。

 which has been added to the original branch， which is frozen。

And this condition is also inserted at each wrinkleer stage of the control net branch。



![](img/216341b3c3dcc759907e30f02f7a4659_90.png)

系。So there's another technique classifier free guidance。

 which is try to trade to trade off between diversity and also fidelity Okay。

 so to condition on some class。We are trying to given this class we try to predict what is the image。

 but we can also truly another classifier given the image try to predict the class。

 we want to make sure the class is exactly the one we want to generate so。



![](img/216341b3c3dcc759907e30f02f7a4659_92.png)

We can add the classifier ragi during the sampling and also make sure the sample is classified as C。

So we not only want to run this generation model， but also we want to run this discrimininate model。

 make sure the generated image is exactly belong to the class。

So new sample distribution is defined in this way， so given this class we want to sample an image and also the predict this image。

It's also predicted as belonging to class C。And we add omega to the power of omega。

 which is the guidance graph。In the log space， the multiplication becomes the saw。

And to the power of omega becomes omega times log p， okay。

 so that's why we add omega to the power of square。



![](img/216341b3c3dcc759907e30f02f7a4659_94.png)

So this is basically the naive comparison between naive conditional sampling。

 the condition here versus classifier or guided the sampling。

 which is adding another term to given this image we want to classify to classify the class and make sure that belongs to see。

So this is the classifier gradient and the Str is controlled by this guidance Str so that's the。啊。

A classifier guided something。So this is comparing a small omega versus a larger omega。

 very small omega， the generator image is sometimes confusing， it is not dog。

But on the right hand side， the fidity is much better。largerger guidance of W lead to better quality。

 but less diversity。 So the diversity is very poor versus here has many diversities on the grass and the snow in the snow。

But I feel the diversity is much poor。So what is the limitation here？

By using such classifier guidance。We can only work on class condition。

 where there's no tax or pixel wise condition since we have to predict the classifier。

And we need to train additional network， which is a classifier network， which is cumbersome。

Can we just use one network no an instant and don't have to train a separate idifier network。

So that's the classifier for guide very widely used the technique these days。

To support diverse conditions， including the class condition， text condition， pixel wise condition。

 cetera， without using an actual classifier network。



![](img/216341b3c3dcc759907e30f02f7a4659_96.png)

So this is the original term defined in the classifier guidance has two terms multiplied together one is given the condition。

 predict the image， the other is given the image， make sure it's belong to type C， omega is the str。



![](img/216341b3c3dcc759907e30f02f7a4659_98.png)

![](img/216341b3c3dcc759907e30f02f7a4659_99.png)

We can apply base rule such that this term given the XT with probability healthy condition。

 we can rewrite it to be given C with probability held XT versus PXT okay so this is the condition model。

 this is unconditioned model and putting them together that's base rule。



![](img/216341b3c3dcc759907e30f02f7a4659_101.png)

啊，倍诉的。So basically we can run the inference twice， one is the conditional model。

 the other is the unconditional model， so in that way we can rewrite in at the top by inserting thec given XT to be PxT given C divided by PxT and to the power of omega。

 we still put it here。

![](img/216341b3c3dcc759907e30f02f7a4659_103.png)

![](img/216341b3c3dcc759907e30f02f7a4659_104.png)

And we find these two terms can be combined together to the power of omega plus one。

 so that we are combining these two terms together， since they're the same。So we have omega plus one。

 we nominate where we just move them to the right to the power of Oomega。



![](img/216341b3c3dcc759907e30f02f7a4659_106.png)

So in the log space， this division becomes a minus and subtraction。So we have omega plus one。

Log PX T Gal minus omega log PXT plus its condition plus C。

So what does that mean to the original model okay previously we are having the condition and the T right here now we just replace it with two terms we inference it twice one is given the T and C the other is given only the T no C so we have to run the inference twice。

Okay combinebine the results of the conditional and also the unconditional forward。

And what does that mean？We need to double the floors， okay。

Do it once with the condition and do it another time without the condition。

So that's basically the classifier free like is。And let's see how that works。

 so on the left hand side。There's no guidance， there something looks like a dog。

 but on the right hand side， it looks like a dog。So larger guidance W is also leading to better quality。

 but less diversity。But advantage is that it can generalize to any condition forms。

 not just class condition and generalize to different conditions。

Like pixel condition or text condition。And we don't need to train a separate network。

 we don't need to train a classifier， just the same diffusion model。

 we just need to run the diffusion model twice。So all the techniques we learn so far are gradually adding complexity。

 making it more computationally expensive， like adding the condition， et cetera。

 and later we are going to talk about how to reduce reduce the computation of fluxs。

 starting with latent diffusion models。Eventually you have a pretty high resolution image。

Which means when we are predicting a noise， we have to make pixel wise prediction。

 that's a lot of pixel noise pixels to predict。

![](img/216341b3c3dcc759907e30f02f7a4659_108.png)

And we pass it through an encoder。And then dens a small at a smaller resolution。

 like one/ eighth or one fourth a resolution so that you can have a much smaller compute。



![](img/216341b3c3dcc759907e30f02f7a4659_110.png)

Actually， that is a very widely used technique these days called the latent diffusion rather than directly to diffusion on the high resolution image。

 we first passing through a encoder to down sample by four times eight times even 64 times as our recent work called deep deep compression auto encoder so we have a much smaller latent space and you do diffusion in this smaller space which is much easier and much faster。



![](img/216341b3c3dcc759907e30f02f7a4659_112.png)

And after you denoise we're passing through a decoder to reconstruct the original image。

So diffusion only need to run in this smaller resolution latent space rather than on the high resolution original image space。



![](img/216341b3c3dcc759907e30f02f7a4659_114.png)

So that's a way to compress the image and only run inffusion in a compressed space。

And that is called latent diffusion， they only apply diffusion on a small resolution part。



![](img/216341b3c3dcc759907e30f02f7a4659_116.png)

![](img/216341b3c3dcc759907e30f02f7a4659_117.png)

to enable simpler denoising and also faster synthesis。And let's see how that changes our roadmap。

 So this is the original configuration in the。

![](img/216341b3c3dcc759907e30f02f7a4659_119.png)

The difference is that the image is fed to encoder and we feed the encoder's result as the z okay so we first added the noise they in space added the noise this is the sum passing through the model and predict the noise and try to match the noise so the learning target is exactly the same the only difference is that we added another term rather than directly feeding x0 to here we feed x0 to an encoder and get z0 and feed the z0 to the model to predict the noise。



![](img/216341b3c3dcc759907e30f02f7a4659_121.png)

![](img/216341b3c3dcc759907e30f02f7a4659_122.png)

![](img/216341b3c3dcc759907e30f02f7a4659_123.png)

And Z0 is in the latent space as a much smaller resolution。

So this is during the training and the forward。What about during the sampling and sampling time？



![](img/216341b3c3dcc759907e30f02f7a4659_125.png)

So everything is actually the same， except for the last one。

 we want to feed it to a decoder to decocode the original image。

 so previous way we have this XT and then we passing through the model to predict the noise。

We subtract the noise from this Xt and we do D noise， D noise。

 we added another noise to at the final de noise zt minus1。

 so this is from zt to zt minus1 all the way to z0。

And after we get z0 in the latent space at a smaller resolution。

 we pass it through the decoder and reconstruct the original image。



![](img/216341b3c3dcc759907e30f02f7a4659_127.png)

So the only change is the right part， the deco passes it through a decoder of low resolution so high resolution。

Everything else stays the same， but we can now generate much complicated and higher resolution image like here an astronaut in a jungle coat color palette。

And here' is a deep sea div and floating。This is stable diffusion Excel for high resolution image generation？

As you can imagine， the more we compress。The less workload。

 the smaller the number of resolution and the smaller the number of tokens。

So recently we invented this deep compressionoc code rather than compress open by eight times。

 and we can compress it by 64 times。What does that mean。

It means eight times more compression in each side and altogether we have how many fewer tokens。

64 times fewer tokens because H times W both two sides， so 64 times less tokens。

How does that impact the attention's complexity？4，000 times less flops right since the attention computation complex isdraically related to the number of tokens。

 we are reducing each side by eight times altogether 64 times less tokens and 4096 times less flops okay。



![](img/216341b3c3dcc759907e30f02f7a4659_129.png)

So this is original stable diffusions， variational auto encoder， VE。

 reducing the resolution by eight times passes through the diffusion model pretty slow。

This is our proposed approach using deep compression how to encoder 64 times compression on each side as it with the future model and make it much faster。



![](img/216341b3c3dcc759907e30f02f7a4659_131.png)

However， this is not straightforward my evil approach， for example。

 IVE under 64 times of compression， the quality is very poor， but using deep compression VAE。

 the quality is much better。On the left hand side， we are comparing the compression ratio。

 the higher the compression ratio the。More preferable， but at the harderter baseline on methods IVE。

 the LID deteriorates very rapidly。包。But the deep compression alter encoder stays very。

 very stable FID， even given 128 times compression ratioly。And how did we achieve that？

So reducing the resolution。You have a very naable approach， right， You can directly。

move information from spatial dimension to the channel dimension。Say every two by two pixel，4 pixels。

You can change it from two two times two times one into one times one times four。

So that's the explicit transformation from spatial to channel。Okay。

 so by explicit spatial to channel， we can add this explicit spatial to channel branch。嗯。

To the down山坡 block。And added this explicit channel to the spatial branch with the up whole block。

We call it residual auto encoding。So rather than using the weight， many weights to learn such stuff。

 we use this。Zero weight branch， no weight。zero weight branch as a residual bypass to learn this and we find adding this residualial auto encoding makes it a lot easier。

 for example， the RFIB without residualial auto encoding will deteriorate very fast in F64 but it remains very stable under high compressionion ratio。



![](img/216341b3c3dcc759907e30f02f7a4659_133.png)

![](img/216341b3c3dcc759907e30f02f7a4659_134.png)

A second technique is this three stage adaptation to high resolution。

 so we want to deal with high resolution like 4K by 4K image generation。

 So how do we have a auto encoder to support so much higher compute resolution without requiring a lot of training flos。

So we decoup it into three phases， the first phase which just perform low resolution between the whole both encoder and decor okay given an input image encoder encoded into a latent space and the decoder reconacted to the original image okay so this is low resolution full training。



![](img/216341b3c3dcc759907e30f02f7a4659_136.png)

And the second step in order to save the computation。

We perform high resolution latent adaptation only to the middle layer， okay。

 so the middle layer correspond to like classifier last layer， only human is middle layers。

And freeze the remaining layers and finally we add this guide loss to further polish to do some refinement only to the last layer of the decoder since that's only related to the low level features The low level feature is actually refine in the last stage。

 so we do such layer wise is sparse tuning not tuning all the layers but sparsely tunening in the middle layer or the late stage to save the computation and make it very fast to train such a auto encodeder。



![](img/216341b3c3dcc759907e30f02f7a4659_138.png)

![](img/216341b3c3dcc759907e30f02f7a4659_139.png)

![](img/216341b3c3dcc759907e30f02f7a4659_140.png)

So using this auto encoder， we can greatly accelerate the image generation execution models。

 so this is using the original latent space， the STVE， which is eight times reduction。

So it's pretty slow it generate only 17 images per second， but on the right hand side。

 we are using the 64。Times compression okay。F 64， reducing the number of。

Tokens from reducing the resolution from 512 to 8 by8 so we can confuse only 64 tokens compared with previously we have to confuse 4K tokens so it's a lot faster 19 times faster actually。

Comppar to wealth using in the original。Autto encodeder。 So auto encoder matters a lot。

 If you can apply such deep compression auto encoder。

 you can have much fewer tokens and quadraically reduce the computation fluxs for inference of diion models。

And another benefit is that now we can。Achieve high resolution image generation without using a lot of computes。

 for example，4K image generation。look at the ship， look at the details， how much detail你看啊。

 this is4K by4K啊gen。And compared with 1 k， this is astronaut in the jungle。

 the 4K has a lot more details， but a lot more computation if you don't use techniques like deep compression auto inder。

So based on deep compression auto encoder， we build a efficient image generation diffusion model called Saana。

Whi takes the mon of several factors， one is the linear PIP module using the linear attention that we previously described for high resolution。

 we have a lot of tokens and the computation complexity grows contractally with the resolution so a linear attention will be very feasible will be very helpful to generate high resolution will achieve speed up。

So this is the using the linear attention， this is using a linear DIT module using the deep compression auto encoder。

 and here is' using a modified complex human instruction， which we are going to talk about that。

So previous diffusion models are using encoder decor model like T5 as text encodeder。

 so we think recently there's a lot of progress of decoder only a large language model like。

LikeGPT model， G2， GT3， 3。5， everything after that or Google's， Jma。

 so can we use this decoder only model as a text encoder。For example， given an input to the Jma。

 a man is walking。

![](img/216341b3c3dcc759907e30f02f7a4659_142.png)

Jama's output focus on conversation he says this is a great start to make this more interesting tell me about the man and his walk。

 for example， where is he walking a busy saving street what is he carrying what is his mood the more details you give the more vivid and engage in the story can be so this is not quite related to image generation if he naively feed or prompt to JaA it is not basically related to image generation but focusing on conversation and storytelling。



![](img/216341b3c3dcc759907e30f02f7a4659_144.png)

![](img/216341b3c3dcc759907e30f02f7a4659_145.png)

In contrast， we add a complex human instructionend this fixed human instruction before the actual prompt。

A man is walking and now demo can give correct output saying a man in the world neither decade works bris down a。

Carul was still straight， he's had。Dung cast， he seeette framed by the setting sun and wear his faded blue scarfs along his neck。

 et cetera， gave a very detailed description。

![](img/216341b3c3dcc759907e30f02f7a4659_147.png)

Beyond the simple instruction we gave and how do we achieve that。

 this is using the prompt engineering we discussed in the previous lecture。

 so this is the complex human instruction we feed to JAMA okay not the example not only the prompt but also the example for in learning。



![](img/216341b3c3dcc759907e30f02f7a4659_149.png)

Even a user prompt generate an enhanced prompt that provide detailed visual description suitable for image generation。

 evaluate the level of detail in the user prompt， if the prompt is simple。

 focus on adding specifics of colors， shapes， sizes。

 textures and spatial relationships to create a vivid and concrete if the prompt is already very detailed。

 refine and enhance the existing detail slightly without overcomplicating。We also give some examples。

Mer prompt， a cat sneak we converted to enhancing version。

 a small fluffy white hat curl up in a round shape sneaking peacefully on a warm。

 sunny windowill surrounded by pot of blueing red flowers。



![](img/216341b3c3dcc759907e30f02f7a4659_151.png)

By using the in case learning example with two user prompt and finally please generate only the enhanced description for the prompt below and avoid including any additional commentary evaluations followed by our real human prompt a man is watching okay and in that way we can let this。



![](img/216341b3c3dcc759907e30f02f7a4659_153.png)

![](img/216341b3c3dcc759907e30f02f7a4659_154.png)

Decoder only language model to give the output but is preferable for the diffusion model to consume。

诶。😊，All right， and how does it echo with the visual language model that we previously discussed。

 for example， the Vla visual language model。Actually， we can use Vla to recaption the image。

 So given the image， we want to。This is original caption， which is actually very very short。

Top view written happy Valentine on a cart， chocolate cake， black food background， very simple right。

 but using a Villa or visual language model， it can be a very difficult capture like this is Villa 13 B the image captures a delightful scene of Valentine's Day celebration at the center of the image it's around chocolate cake。

 rich and inviting。The cake is adorned with a red heart on the top。

 symbolizing love and affectionion， the words happy Valentine's are elegantly withening in red icing on the cake。

 adding to the festive atmosphere， the cake is placed on the wooden table。Yeah。

 think you need a wooden table which provides a rustic charm to the second so you can tell it's a very detailed description that is unlikely to be labeled by a human labeler to give such detailed and。

F label without without hallucination， so this is the 13B。

 this is 3B will be fitted to different sides of Villa to vote based on their clipP score to prevent hallucination and try to find the best match clip score basically measures the similarity。

 the relationship how well does it match between the caption and the image。

So now everything begin to converge by using our visual language model， the Villa。

 we can generate more data， we can use the data to trim better saa so Saa and Villa can grow together so that's the beauty of such co design。

All right。

![](img/216341b3c3dcc759907e30f02f7a4659_156.png)

Now we have to build a Sanana based on the above techniques， we can accelerate Sana。

 we can accelerate 1K image generation by 25 times。

 accelerate 4K image generation by 100 times compared with the flux fluxta。

 which is a popular diffusion model these days， these Fls。



![](img/216341b3c3dcc759907e30f02f7a4659_158.png)

![](img/216341b3c3dcc759907e30f02f7a4659_159.png)

ThereS3， Pix art， Sanana。

![](img/216341b3c3dcc759907e30f02f7a4659_161.png)

And mean where is this 106 times acceleration come from， so it comes from compression auto encoder。

 linear DIT， kernel fusion， and also using the flow based DPM solve。

And the quality wise that involved previously and this is。



![](img/216341b3c3dcc759907e30f02f7a4659_163.png)

The for the flux model， this is for the S model， they are almost like a。



![](img/216341b3c3dcc759907e30f02f7a4659_165.png)

But let's see some generated results from Sanana 1。6B。The text， the logogos。

And the human face actually create a lot of details。

And here are some more examples like a blue porch， 356 parked in front of a yellow brick wall。Here。

 this one is probably more interesting。 a avocado wearing a royal crown。And robe。

Seated on a throne in a grand。Opulent setting。The scene is surrounded by other avocados。Also。

 adorned with cross。So high resolution， low cost。So let's continue to talk about image editing。

So image editing with diffusion model is pretty powerful。

 so for example here we want to give some input strokes here in power a room and now we want to gradually recover and generate an power and a room by denoing and it should be match the input stroke and how do we do that。

So these are separate spaces， one is the stroke， one is the image， they are in different locations。

 so what we do is we can perturb them with noise， so adding noise to the stroke such that the noisy image can have some overlap with the original space and then we do the reverse process to gradually deno we can move this blue dot closer and closer to the center of the to the green region which is the image region reimage space so that the output output look like the castle in this case。



![](img/216341b3c3dcc759907e30f02f7a4659_167.png)

![](img/216341b3c3dcc759907e30f02f7a4659_168.png)

![](img/216341b3c3dcc759907e30f02f7a4659_169.png)

![](img/216341b3c3dcc759907e30f02f7a4659_170.png)

So this is some example given this original， this is drone probably by a human。

 and then would be the prompt of fantasy landscape training in art station and this is re generated the image given the input stroke。



![](img/216341b3c3dcc759907e30f02f7a4659_172.png)

![](img/216341b3c3dcc759907e30f02f7a4659_173.png)

We also want to personalize the model， okay not only edit the model， but also personalize the model。

 say given a dog， we want to generate some dog swimming sleeping him in the bucket for this particular dog right it has gray hair。

 large ear and white flags will formulate exactly the same dog follow exactly the same dog。

Like getting a hair card， this is not a random dog。

 but we want it to be exactly this dog how do we do that？Actually， this is pretty challenging。

For example， we input and few images of this talk。The same plug in different setting。嗯。

But generate the image。I have a poor like this block no longer look like this one。

 the color three should be yellow， black and white。And also very few context。

 they are both white background versus less fidelity but able to generate new context。

 but three has changed versus both having good fidelity and also diverse contexts。

D booth achieved this functionality by fine tuning the model so we can we given a text to image model。

 given a few pictures， next three to five images。

![](img/216341b3c3dcc759907e30f02f7a4659_175.png)

Of the of the dog。Plus the dog itself， the language dog and passes through the dream Bo to fine whom that we got a new personalized text image model and this unique identifier V。

 and then we can say a V dog is in the beach that will generate this particular dog in the beach。



![](img/216341b3c3dcc759907e30f02f7a4659_177.png)

A we dog walking on a colorful carpet， and then we can generate this personalized we dog carpet。

So the limitation here is that one fine human model。It's specific it's to only one subject。

 so if you want to generate like a person like a friend playing basketball。

 you have to do the fine tuning again for your friend， and which is costly。

If you are interested in traininging free methods， there's plenty of publications later using traininging free methods to customize to perform personalized image generation。

Okay， now let's switch gear to talk about fast sampling technique。



![](img/216341b3c3dcc759907e30f02f7a4659_179.png)

noing diffusion implicit models so thenoing process is an iterative approach right from the noise to the data the idea is that can we use fewer steps to have a larger stride to reduce the number of iterations so previously the method is Markoving so each XT is only dependent on the previous time step。



![](img/216341b3c3dcc759907e30f02f7a4659_181.png)

![](img/216341b3c3dcc759907e30f02f7a4659_182.png)

I will train the model such that we only use these properties to the training。

 but at inference time can we find a non remarkovan forward process to accelerate it。



![](img/216341b3c3dcc759907e30f02f7a4659_184.png)

By reusing the same model during the training牌。So we want to make sure the Xt minus1 is not only related to Xt but also related to zero can we find in such a setting that we don't have to change the true the model but just change the change it at the in time。

Actually we can do that， this is the conclusion， so previously xt minus1 is related to Xt but now it's related to not only Xt noted that gipsilon which is related to Xt but also related to x0 okay and we can estimate zero in this equation。



![](img/216341b3c3dcc759907e30f02f7a4659_186.png)

![](img/216341b3c3dcc759907e30f02f7a4659_187.png)

So in that， we can have a larger stride timest from 0，10， 20， 30。

1000 pre if we just make one time step inement， now we can make the equipment of 10 to accelerate the denoisian process。



![](img/216341b3c3dcc759907e30f02f7a4659_189.png)

![](img/216341b3c3dcc759907e30f02f7a4659_190.png)

At the original TDPM， you can reduce the number of steps from 10 to 20 to 10。



![](img/216341b3c3dcc759907e30f02f7a4659_192.png)

The FID will explode， but using TPIM， the FID stays very stable until like 10 or 20 steps。

 still 20 steps still below 10。

![](img/216341b3c3dcc759907e30f02f7a4659_194.png)

This is a site 10 data set。 This is on the select a data set。 the FID is。



![](img/216341b3c3dcc759907e30f02f7a4659_196.png)

![](img/216341b3c3dcc759907e30f02f7a4659_197.png)

Both well maintained while having much fewer sampling steps。

 like 20 steps opposed to 1 thousand00 steps。Another approach to reduce this number of steps is by using dissillation so this is a four step model。

 we can distill that such that a single step in the student network can do the same as two steps in a teacher network okay we can do another generation of dissillation such that a student student which can directly use one step to model what a teacher have done in four steps so we can distill a deterministic sample to the same model architecture and each step。

 the student model is learned to distill from two adjacent supplement steps from the teacher。



![](img/216341b3c3dcc759907e30f02f7a4659_199.png)

![](img/216341b3c3dcc759907e30f02f7a4659_200.png)

every new student will reduce the number of sampling steps by two。



![](img/216341b3c3dcc759907e30f02f7a4659_202.png)

So in this way， we can reduce the training steps， but the FID stays much lower compared with。

The PDI and the original nine steel the version。

![](img/216341b3c3dcc759907e30f02f7a4659_204.png)

Okay， Cha three， now let's talk about acceleration techniques for diffusion models。

 let's start with using sparsity。We can exploit spatial sparsity to accelerate the influence of diffusion models in particular for photo editing。

The vanilla diffusion models waste many computations when we have to reize the entire image。

 even if we only edited a very small portion of that。Say in this case， we only added in 1。

7% of the pixels。You can tell where did we add it。We only added a sign right here。

And a sign right here， that occupied less than 2% of the peak source。

But the original stable diff has to go through the entire。

Model and run on on convolution on the entire input image okay。

But spatially sparse inference is basically saying we can just change whatever we edited for the not edited region we just really use the feature map from the original model since we only edit the sun we only re computeute the sign in green here and reuse the feature maps for the rest of the areas for the previously generated image and as a result this can save eight times the computation。

So this is how it works。So we'll build this spatial incremental generative engine size。

 incremental means only change the pixels that has been edited for those pixels that has not been edited。

 we just reuse whatever it was from the previous approach from the previous equation。

And so given the original image and we drew some。

![](img/216341b3c3dcc759907e30f02f7a4659_206.png)

Is of cloud on the top and this is a difference mass。

 we discretize that to four by four grid in this case and highlight the areas that has been edited。

So this is the original image。This is an edited image， so we only gather these pixels。

 these chunks that has been edited。And then only pass it to the convolution for this edited part okay and we scatter this to the original feature map to get the updated feature map。

 so that's the one layer of the site which only do compute。

 which only do convolution on edited blocks， we call it active blocks。

And we stack them to the batch dimension so it's easier to paralyze no sparse kernel is needed since each patch is best convol。

 and this can also apply to diffusion based transformers。

And we applied it to image in painting so which what is image in painting so we can draw a box in the image inside the image and we can paint whatever we want to the box now we want to paint a horse a photograph of a horse on a grassland previously there is no horse now we draw a box and we want to place a horse right here。

Without this approach， we need to generate the entire output image。

 which takes a lot of compute and pretty slow 300 milliseconds。

Now we only added the mass of the region， which was three times faster。

 four times faster and the quality match very well with the original inputing。



![](img/216341b3c3dcc759907e30f02f7a4659_208.png)

So this is another example we only edited 3% of the pixels added the coconut tree。

 so this is the baseline model， this is our model， the generated quality is pretty much the same while being for more than4x question。

So this is the real time demo showing that this technique can enable this interactive local editing。

 for example， adding a。Some cloud onto the image。Okay。

 now let's switch gear to talk about applying quantization to accelerate diffusion models。

 so we've talked about quantization using quantization to accelerate large language models。

 but large language model and diffusion model have a lot of difference。

 for example on single batch inference， large language model is bottlenecked by the memory bandwidth while the diffusion model is bottlecked by the compute。

So those methods like weight only quantization cannot accelerate diffusion models because they are compute bonded rather than memory bonded。

 if its memory bonded， large language model can benefit from like W 4A16 weight only quantization。

 but in order to achieve measured speed up for diffusion models。

 we need W4A4 quantization quant both the weight and activation to only4 bit without losing fidelity。

 which is even more challenging than W 4A16。And let's see how do we solve that problem？

So we observe the weight and activation， both have a lot of outliers。In diffusion models。

 we have seen this figure， sister figure in smooth qua lecture。So this is the distributionion。

 so the green is a 50 percent percentile， the yellow is 99 percentile and the remaining is the rest 1% so the red part is the outlier so the activation has a lot of outliers right here。

And the weight also has a loss of outliers， which make it both difficult contact。

So we can apply smoothing like we did in smooth qua to migrate the quantization difficulty from the activation to the wave to the activation is much smoother。

 a lot and less red compared with here。But the activation has more outliers。

Previously has only one outlier， now has two。This is a real distribution。

 a lot more red compared with tree。But luckily， the activations outlier is migrated。

 so we just need to migrate the weights at the outlier。

 we can do that by decomposing using a side branch， which is a low rank branch。

To absorb those outliers who is in full precision， but this is a very low rank only 32 ranks so this is very cheap。

So we can migrate。The outliers migrate the quantization difficulty to decide the branch such that after SVD the weight has a lot and less outlier compared with the four。

 so finally both the weight and activation are fourbid but it's very easy to quantize with no outlier and associated with a very low rank side branch。

And the good thing about this approach is that if you use lower fine tuning。

 you don't need to re quantrantetize the weight。But you just need to attend a few more ranks like 16 or 32 more ranks in full precision by whatever Laura you want to add to this module since a lot of people are using diffusion models with Laura。

 so this is very compatible with the frameworkM。Before that despite that。

 we actually observed naive implementation to a lot of overhead。

 like the yellow and the red region for this up and down projection go to the lower branch。

 this is the main branch。

![](img/216341b3c3dcc759907e30f02f7a4659_210.png)

![](img/216341b3c3dcc759907e30f02f7a4659_211.png)

This is the lower branch。We fused such overhead such that the latency overhead be 40% latency overhead is removed。



![](img/216341b3c3dcc759907e30f02f7a4659_213.png)

And we achieved that by actually fusing this down projection with the previous kernel since they shared the same input。



![](img/216341b3c3dcc759907e30f02f7a4659_215.png)

And refuse this up projection to the next layer for the compute since they share the same output okay and in that way we can reduce this overhead in red in yellow。

So this is the kernel fusion。So this is the speed up and the model size reduction， so the speed F16。

 we can reduce it by 3。6 times but the W 4816 method conventional AI 4 can also reduce the model size。



![](img/216341b3c3dcc759907e30f02f7a4659_217.png)

And also reduce the memory we can reduce a bit more since we' are also quantizing the activation。

 however， this is the beautiful part okay so this is the exciting part where the conventional W4A16 work can only reduce the memory but it doesn't lead to ending speedup it's actually slower because they still need 16 bit arithmetic but here we can use4 bit arithmetic either in4 or FP4 and can achieve three more than three times measured speedup on 149GQ。

Okay， and this is a single step latency， the baseline method is out of memory and the four。

 we can make it a 3。5 times faster than the four approach。



![](img/216341b3c3dcc759907e30f02f7a4659_219.png)

So this is the visual visualization comparing the baseline approach。It's all of memory on a 1490 GPU。

 and this is N for very high fidelity， but。It doesn't have any， it's still than more than a second。

 it's pretty slow well we can make to that just half a second。This is the Dar interval quantization。

 so the quality is really poor， actually the quality already start to degrade from IPP16 to NI4 approach。

But our approach can well maintain。In output quality pretty much the same as the original input while the memory is reduced previously 23 gigabyte now is only  six。

5 gigabyte。Half a second compare with 1。8 second。And this is showing that SVD Quaant is very compatible with the existing Laurara。

 we can just add a Laurara branch without having to do any re quantization。

 okay so this is F16 and our in full version using different Laura models micro realism pretty much the same。

The enemy children yarn different kind of styles well maintained the fiity or different lara models。

Finally， we can apply parallelism to exploit multiple GPUs to accelerate diffusion models。

For language model we talk about， we can use tensor parallelm to accelerate it by throwing more GPUs。

 we can just make it faster， what about of diusion models。

 how can we throw more GPUs to make it rank faster？



![](img/216341b3c3dcc759907e30f02f7a4659_221.png)

So these are two devices， we have one GP on the top， one GPU on the bottom。

 we wanted them to work together， generate the image fast， however。

 these two models have to communicate。

![](img/216341b3c3dcc759907e30f02f7a4659_223.png)

![](img/216341b3c3dcc759907e30f02f7a4659_224.png)

to do the attention， attend to each other， which will lead to large communication overhead。

 which we don't want， it will also negate the savings we may get from multiple GPUs。



![](img/216341b3c3dcc759907e30f02f7a4659_226.png)

So we want to reduce the number of communication。The inside here is that。

The input across adjacent time steps are actually very similar to the input here。

 the input here they are very similar to each other， so rather than directly communicating。

 we can actually communicate using the old the scale activation for those communication when we are attending to each other we can attend to the previous time step that's totally fine。



![](img/216341b3c3dcc759907e30f02f7a4659_228.png)

![](img/216341b3c3dcc759907e30f02f7a4659_229.png)

That's the insight， and we can exploit that to reduce the communication overhead and also enable the communication to overlap with computation since we are reusing the old time stepss future format that。

So originally the latency is 12 seconds with four GPUs， not even doing such paralyization。

 indeed making it four times faster， but it will generate four separate images due to lack of communication and duplicated subjects。

This is naive priorization across four GPUs， but using the distributionion。

 distributed the diffusion， we can make it four times。Three times faster。

 but the generating image quality is very good compared with the original one rather than generating four separate images separately。

So this is the speed up across one，2，4， eight devices。

 about more than2 x for four devices here on higher resolution。

 when speed up is even higher due to the communication overhead is saved。

With up to8 GPUs so and hurricane generation is about six times faster。



![](img/216341b3c3dcc759907e30f02f7a4659_231.png)

Right， so here's a summary for today's lecture we first introduce the basics of diffusion models and then we talk about how to add condition。

 how to diffuse in the latent space， including using deep compression。

 auto encoder to compress the tokens， how to perform image editing and personalization。

And then we talk about fast samplingling techniques， theDII and dissillation。

 together with acceleration techniques using sge， the spatial sparsity。

 the SVT quant quantization technique， and alsoion， distributed diffusion by using parallelism。

That's all for today's lecture。 Hope you have a long week， happy long weekend。

