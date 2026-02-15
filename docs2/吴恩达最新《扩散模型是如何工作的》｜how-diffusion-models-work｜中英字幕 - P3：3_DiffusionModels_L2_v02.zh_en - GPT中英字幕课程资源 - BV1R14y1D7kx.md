# 吴恩达最新《扩散模型是如何工作的》｜how-diffusion-models-work｜中英字幕 - P3：3_DiffusionModels_L2_v02.zh_en - GPT中英字幕课程资源 - BV1R14y1D7kx

![](img/9a75ada4473cacc9d609a51652223f60_0.png)

In this video we'll talk about sampling， we'll get into the details of it and how it works across multiple different iterations。



![](img/9a75ada4473cacc9d609a51652223f60_2.png)

![](img/9a75ada4473cacc9d609a51652223f60_3.png)

So before we talk about how to train this neural network。

 let's talk about sampling or what we do with the neural network after it's trained at entrance time。

So what happens is you have that noise sample， you put it through your train neural network that has understood what a sprite kind of looks like and what it does is it predicts noise。

 it predicts noise as opposed to the sprite and then we subtract that predicted noise from the noise sample to get something a little bit more sprite like Now realistically that is just a prediction of noise and it doesn't fully remove all the noise so you need multiple steps to get high quality samples that's after 500 iterations we're able to get something that looks very sprite like。



![](img/9a75ada4473cacc9d609a51652223f60_5.png)

So now let's step through this algorithmically， so first you can sample a random noise sample。

 and that was that original noise you had in the beginning。

And then you want to step through time and actually you're stepping backwards through time all the way from the last iteration 500 where it's completely noisy all the way down to one。

 and just think of your ink drop， you're actually going backwards in time。

 it's fully diffused initially， and then you're going back all the way up to when it was first dropped into the water。

Next you'll sample some extra noise we'll actually touch on this in a minute。

 so don't worry about this just now。Here is where you actually pass that original noise that sample back into your neural network and you get some predicted noise and this predicted noise is a noise that the trained neural network wants to subtract from the original noise to get something that looks more spritelike and finally there's a sampling algorithm called DDPN which stands for denoing diffusion probabilistic models。

 a paper written by Jonathan Ho AJ Jane and one of my good friends Peter Raal and this sampling algorithm essentially is able to get a few numbers for scale that's not super important。

 but what is important is that this is where you are actually subtracting out that predicted noise from the original noise sample and again you're adding that little extra noise back in which we'll return to in a moment All right let's jump to the notebook So you'll see here some setup code I think all that's really important here is that you're importing Pytorch in a lot of utilities from Pytorch we also import some helper functions here that we had written。



![](img/9a75ada4473cacc9d609a51652223f60_7.png)

![](img/9a75ada4473cacc9d609a51652223f60_8.png)

For the neural network so I'm just going to hit shift enter to run that cell so that we import everything and now here's setting out the neural network which we're going to use for sampling we'll go into the details of this later so I'm just going to run this and no need to really follow everything that's going on there just yet。



![](img/9a75ada4473cacc9d609a51652223f60_10.png)

![](img/9a75ada4473cacc9d609a51652223f60_11.png)

![](img/9a75ada4473cacc9d609a51652223f60_12.png)

Here we're setting up some hyperparameters and that includes those time steps that you've seen there。

 so that's the 500 time stepss， Beta 1 and Beta 2 are just some hyperparameters for GDPPM。

And here you can also see the height， this is the 16 by 16 image and again it's just a square image。

 so I'm going to run this shift enter again。And this is just a noise schedule defined in the DDPM paper and all a noise schedule is is it determines what level of noise to apply to the image at a certain time step so this part is just constructing some of the parameters for the DDPM algorithm that you remember those scaling factors。

 those scaling values as1 s2 S3 that's being computed here in the noise schedule and it's called a schedule because it is dependent on the time step remember you're looking through 500 times steps because you're going through those 500 iterations that you see here of slowly removing noise。



![](img/9a75ada4473cacc9d609a51652223f60_14.png)

![](img/9a75ada4473cacc9d609a51652223f60_15.png)

![](img/9a75ada4473cacc9d609a51652223f60_16.png)

So I'm just going to run that here， so just dependent on that time step that we're on next。

 I'm just going to instantiate the model。

![](img/9a75ada4473cacc9d609a51652223f60_18.png)

That unit， which we will come back to。

![](img/9a75ada4473cacc9d609a51652223f60_20.png)

And then here is the sampling algorithm， the denoise Add noise that you had seen previously。

 which is really the main important part is that it is removing the predicted noise。

 which is what the model thinks is not a sprite from the original noise。



![](img/9a75ada4473cacc9d609a51652223f60_22.png)

So we can run that shift enter， shift enter to load that model。



![](img/9a75ada4473cacc9d609a51652223f60_24.png)

And then here is what we had just stepped through that sampling algorithm。

 and specifically here is running the model to get the predicted noise。



![](img/9a75ada4473cacc9d609a51652223f60_26.png)

And then running the deep noise Now let's visualize what sampling looks like over time。



![](img/9a75ada4473cacc9d609a51652223f60_28.png)

This may take a few minutes depending on what kind of hardware you're running on。

 and we're going to speed this up in the video in the next video you'll also see a more efficient sampling technique as well。



![](img/9a75ada4473cacc9d609a51652223f60_30.png)

All right， let's see it in action。Wow， look at those sprites。

 so you should definitely pause and try these yourself。



![](img/9a75ada4473cacc9d609a51652223f60_32.png)

All right， so there's one more extra detail， so right now you have your neural network that's predicting noise from your original noise sample you subtract it out great and you get something a little bit more sprite like。

 but the thing is this neural network expects this noisy sample。

 this normally distributed noisy sample as input。And once you've denoed it like this。

 it's no longer distributed in that way， so actually what you have to do after each step and before each next step is to add an additional noise that's scaled based on what time step you're at to get passed in as the next sample。

 the next iteration into your train neural network。And empirically。

 this actually helps stabilize the neural network so it doesn't collapse to something that's close to the average of the data。

 meaning it doesn't look like this thing on the left when we don't add that noise back in。

 the neural network just produces these average looking blobs of sprites versus when we go added it back in。

 it actually is able to produce these beautiful images of sprites。



![](img/9a75ada4473cacc9d609a51652223f60_34.png)

So here in the algorithm is where this happens， so we actually sample a random noise again at each time set based on the time set。

And then down here。We actually added back in with that scaling factor S3。



![](img/9a75ada4473cacc9d609a51652223f60_36.png)

So now let's take a look at the notebook。So now in this function， denoise add noise。

 we are talking about the add noise part and what that is is this Z that you randomly sample。

 that's that extra noise。And you scale it by some factor， and then you actually do add it back in。



![](img/9a75ada4473cacc9d609a51652223f60_38.png)

And again， that all happens down here in your main algorithm。



![](img/9a75ada4473cacc9d609a51652223f60_40.png)

Alright， so let's pick up where we left off then， so for the incorrect way where we don't add the noise back in。

 we actually just set z to0 and we pass that in， it only subtracts the predicted noise from the original noise and it doesn't add any extra noise back in and let's run this with shift enter shift。



![](img/9a75ada4473cacc9d609a51652223f60_42.png)

And again， this will take a couple minutes， Alright， so let's take a look at。



![](img/9a75ada4473cacc9d609a51652223f60_44.png)

But this does instead。Oh， no， bs。

![](img/9a75ada4473cacc9d609a51652223f60_46.png)

So this is obviously not what you want， so make sure you add that extra noise back in。

And so you should definitely pause and try these yourself and compare it to the other method where you do add that extra noise。

And in the next video， we're going to cover that neural network architecture that you。



![](img/9a75ada4473cacc9d609a51652223f60_48.png)