# Jeremy《深度学习基础到稳定扩散模型｜Deep Learning Foundations to Stable Diffusion》中英 p02 Lesson 9A 2022 - Stable Diffusion deep dive.zh_en -BV1Mp421S7xg_p2-

Hello everyone， my name is Jonathan and today I'm going to be taking you through this stable diffusion deep dive notebook looking into the code behind the kind of popular highlel APIs and libraries and tools and so on to see what exactly does the generation process look like and how can we modify that。

 How do each of the individual components work？😊，So feel free to run along with me if you haven't before this might take a little while to run just because it's downloading these large models if they aren't already downloaded and loading them up and so we're gonna to start by just kind of recreating what it looks like to generate an image using say one of the existing pipelines and hugging face so we gonna to basically have copied the code from the core method of the default stable diffusion pipeline and so if you go and view that here you'll see that we're going to be basically replicating this code。

 but now we'll be doing it on our own sort of notebook and then we'll slowly understand what each of these different parts is doing。

 So we've got some setup we've got some sort of loop running through a number of sampling time stepss and wegene an image So this is supposed to be a watercolor picture of an otter it it very。

 very cool that this model can just do this but now we want to know how does that actually work what's going on。



![](img/0629c20054834ad43432bab705e8969b_1.png)

![](img/0629c20054834ad43432bab705e8969b_2.png)

So the first component is the auto encoder。 Now， this stable diffusion is a latent diffusion model。

 And what that means is that it doesn't operate on pixels。 It operates on。



![](img/0629c20054834ad43432bab705e8969b_4.png)

So in the latent space of some other autoencoder model in this case。

 a variational autoencoder that's been trained on a large number of images to compress them down into this latent representation and bring them back up again。

 So I have some functions to do that we're going to look at what it's like in action just downloading a picture from the internet opening it up with P So we have this 512 by 512 pixel image we're going to load it in and then we're going to use our function defined above to encode that into some latent representation and what this is doing is calling the Vae do encode method on a tensor version of the image and that gives us a distribution and so we sampling from that distribution and we're scaling by this because that's what the authors of the model did scale the latents down before they fed them to the model and so we have to do that scaling and then the reverse when we deding just to be consistent with that but the key idea is that we go from this big image down to this4 by 64 by 64 latent representation so we've gone from。



![](img/0629c20054834ad43432bab705e8969b_6.png)

![](img/0629c20054834ad43432bab705e8969b_7.png)

![](img/0629c20054834ad43432bab705e8969b_8.png)

![](img/0629c20054834ad43432bab705e8969b_9.png)

![](img/0629c20054834ad43432bab705e8969b_10.png)

This much larger image down。 And if we visualize what the four channels here。

 this four different 64 by 64 channels， what that looks like。

 we'll see that it's capturing something of the image right you can sort of see the same shapes and things there。

 but it's not quite a direct mapping or anything。 for example。

 there's this weirdness going on the beak。 Some of the channels look slightly stranger than the others。



![](img/0629c20054834ad43432bab705e8969b_12.png)

![](img/0629c20054834ad43432bab705e8969b_13.png)

![](img/0629c20054834ad43432bab705e8969b_14.png)

![](img/0629c20054834ad43432bab705e8969b_15.png)

So there's some sort of rich information captured there。 And if we decode this back。



![](img/0629c20054834ad43432bab705e8969b_17.png)

What we'll see is that the decoded image looks really good。

 You really have to look closely to tell the difference between our input image here and the decoded version so very。

 very impressive compression right This is a factor of8 in each dimension So 512 by 512 down 64 by 64 it's like a factor of 64 reduction in data but it's still somehow capturing most of that information。

 It's a very information rich representation and this is going to be great because now we can work with that with our diffusion model and get nice high resolution results even though we only working with these 64 by 64 latents Now it doesn't have to be 64 by 64 you can go and modify this to say what if this is 640 and encode that down and you'll see that it's just that same factor of 8 reduction。

😊。

![](img/0629c20054834ad43432bab705e8969b_19.png)

![](img/0629c20054834ad43432bab705e8969b_20.png)

![](img/0629c20054834ad43432bab705e8969b_21.png)

![](img/0629c20054834ad43432bab705e8969b_22.png)

![](img/0629c20054834ad43432bab705e8969b_23.png)

![](img/0629c20054834ad43432bab705e8969b_24.png)

![](img/0629c20054834ad43432bab705e8969b_25.png)

And there we go。 now we have 80 by 64， and this just has to be a multiple of eight。

 otherwise you'll get， I think， an error。

![](img/0629c20054834ad43432bab705e8969b_27.png)

![](img/0629c20054834ad43432bab705e8969b_28.png)

Okay， so we have our encoded version of this image， and that's pretty great。😊。



![](img/0629c20054834ad43432bab705e8969b_30.png)

The next component we're going to look at is the scheduler。

And I'll look more closely at this later but for now we're going to focus on this idea of adding noise right so during training。

 we adds the noise to an image and then the model tries to predict what that noise is and we're going to do that to different amounts。

 So here we're going to recreate the same type of schedule you can try different schedulers from the library oops and these parameters here beta start beta end beta schedule that's how much noise was added at different time steps and how many time stepss are used during training。

For sampling， we don't want to have to do a thousand0 steps so we can set a new number of time steps and then we'll see how these correspond with the Sch dot time steps attribute。

To the original training time steps。 so here we're going to have 15 sampling steps and that's going to be equivalent to starting at time step 999 and just moving linearly down to time step 0。

We can also look at the actual amount of noise present with the sigmas attribute， so again。

 starting high， moving down and if you want to see what that schedule looks like。

We can plot that here， and if you want to see the time steps。

 you'll see that it's just a linear relationship。

![](img/0629c20054834ad43432bab705e8969b_32.png)

So there we go， we're going to start out at a high noise value and we're going to slowly slowly try and reduce this down until ideally we get an image out。

Okay， so this sigma is the amount of noise added， let's see what that looks like。

 so I'm going to start with some random noise that's the same shape as my latent representation mind coded image。



![](img/0629c20054834ad43432bab705e8969b_34.png)

And then I'd like to be equivalent to sampling step 10 out of 15 here so I'm going to go and look up what time set that equates to and that's going to be one of the arguments that I pass the scheduler do add noise function so I'm calling schedule do add noise giving it my encoded image the noise and what time step I'd like to be noisy equivalent to and this is going to give me this noisy but still recognizable version of the image and you can go and say okay what if I look at somewhere earlier in the process right does it look more noisy what about right at the beginning right at the end and feel free to play around there。



![](img/0629c20054834ad43432bab705e8969b_36.png)

![](img/0629c20054834ad43432bab705e8969b_37.png)

![](img/0629c20054834ad43432bab705e8969b_38.png)

![](img/0629c20054834ad43432bab705e8969b_39.png)

![](img/0629c20054834ad43432bab705e8969b_40.png)

Okay so this adding noise， what are we actually doing， what does the code look like。

 let's inspect the function， and you'll see that there's some setup for different types of argument and shapes。

 but the key line is just this noisy samples is equal to original samples plus the noise scaled by the sigma parameter。



![](img/0629c20054834ad43432bab705e8969b_42.png)

![](img/0629c20054834ad43432bab705e8969b_43.png)

So that's all it is， it's not always the same， different papers and implementations will add the noise slightly differently。

 but in this case that's all it's doing， so schedule it don't add noise。

 just adding noise that's the same shape as the latent scaled by the sigma parameter。



![](img/0629c20054834ad43432bab705e8969b_45.png)

![](img/0629c20054834ad43432bab705e8969b_46.png)

Okay， so that's what we're doing。 So if we want to start from random noise instead of a noisy image。

 we're going to scale it by that same sigma value so that it looks the same as an image that's been scaled by that amount。

 But then before we feed that to the actual model， we then have to handle that scaling again。

 You could do it like this。 But now we have this。

![](img/0629c20054834ad43432bab705e8969b_48.png)

Scale model input function associated with the scheduler just to hide that complexity away。



![](img/0629c20054834ad43432bab705e8969b_50.png)

Okay， so now we're going to look at the same kind of sampling loop as before。

 but we're going to start now with our image。 We're going to take our encoded image。

 We going annoise it to some time step， and then we only can denoise from there。 So in code。

 we are now preparing our text and everything the same as before。

 which we' will look at were setting our number of inference steps to 50 right I inference steps is equal to 50 here。

 and we say I'd like to start at the equivalent of step 10 out of 50。

 So I'll look up what time step that equates to。 I'll add noise to my image equivalent to that step。

😊。

![](img/0629c20054834ad43432bab705e8969b_52.png)

![](img/0629c20054834ad43432bab705e8969b_53.png)

And then we're going to run through sampling。 But this time we're only going to start doing things once we get above that start step。

 So I'm going to ignore the first 10 out of 50 steps。 And then beyond that。

 I'm now going to start with this noisy version of my input image， and I'm going to dennoise it。

 according to this prompt。And the hope here is that by starting from something that has some of the sort of rough structure and color of that input image。

 I can kind of fix that into my generation， but I've got a new prompt。

 a National geographic photo of a colorful dancer。 And here we go we see this is the same sort of thing as the parrot。

 But now we have this completely different actual content thanks to a different prompt。

 And so that's a fun kind of use of this image to image process you might have seen this for takinging drawings。

 adding a bunch of noise and then denoising them into fancy paintings and so on。 so again。

 this is something that there's existing tools for this right the strength parameter and that the image to image pipeline that's just something like this what step are we starting at How many steps are we skipping。

😊。

![](img/0629c20054834ad43432bab705e8969b_55.png)

![](img/0629c20054834ad43432bab705e8969b_56.png)

![](img/0629c20054834ad43432bab705e8969b_57.png)

![](img/0629c20054834ad43432bab705e8969b_58.png)

![](img/0629c20054834ad43432bab705e8969b_59.png)

![](img/0629c20054834ad43432bab705e8969b_60.png)

But you can see that this is a pretty powerful technique for getting a bit of extra control over like composition and color and a bit of the structure。

😊。

![](img/0629c20054834ad43432bab705e8969b_62.png)

Okay， so' that's that trick with adding noise and then using that as image to image。



![](img/0629c20054834ad43432bab705e8969b_64.png)

The next big section I'd like to look at is how do we go from a piece of text that describes what we want into a numerical representation that we can feed to the model。

So we're going to trace out that pipeline and along the way。

 we'll see how we can modify that for a bit of fun。So step number one。

 were taking our prompt and we're turning it into a sequence of discrete tokens。 So here we have。

In this case， 77， because that's the maximum length。Disrete tokens。

 it's always going to be that if your prompt is longer。

 it'll truncate us and if we decode these tokens back。

We'll see that we have a special token for the start of the text， then a picture of a puppy。

 and then the rest is all the same token， which is this kind of end of text padding token right so we have this special token for puppy。

 this special token has its own meaning end of text。

 and the prompts are always going to be padded to be the same length。

So before in the code that we were using there， we always jumped straight to these circle output embeddings。

 which is what we fed to the model as conditioning and so somehow this captures some information about this prompt but now we want to say。

 well how do we get there， how do we get from this sequence of tokens to these output embeddings。

 what is this text encoder forward past doing？Right so we can look at this and there's going to be multiple steps。

 and the first is going to be some embedding。 So if we look at the text encoded text model that embeddings。

 we'll see there's a couple of different ones， we have token embeddings right and so this is to take those individual tokens token408 or whatever and map it into a representation that's a numerical representation So here it's a learned embedding there are sorry about 50000 rows one for each token and for each token we have 768 values So that's the embedding of that token and if we want to feed one in and see what the embedding looks like here's the token for puppy and here's the token embedding 768 numbers they somehow capture that meaning of that token on its own and we can do the same for all of the tokens in our prompt So we feed them through this token embedding layer and now we get 77768 dimensional representations of each token。

Now these are all on their own and no matter where in the sentence is it is the token embedding will be the same。

 so the next step is to add some positional information Some models will do this with some kind of like learned pattern of positioning but in this case the positional embedding is just another learned embedding。

 but now instead of having one embedding for every token we have one embedding for every position out of all 77 possible positions。

And so just like we did for the tokens， we can feed in the position IDs。

 one for every possible position， and we'll get back out and embedding for every position in the prompt。

Combining them together， there's again multiple ways people do this in the literature。

 but in this case it's as simple as adding them， that's why they made them the same shape so that you can just add the two together and now these input embeddings have some information related to the token and some related to the position。

😊，So so far we haven't seen any big model just to learned embeddings。

 but this is getting everything ready to feed through that model and so we can check that this is the same as if we just called the embeddings layer of that model which is going to do both of those steps at once。

 but we'll see just now why we want to separate that out into individual ones。Okay。

 so we have these individual tokens and they have some positional information we have these final embeddings now we'd like to turn them into something that has a richer representation thanks to some big transformer model and so we're going to feed these through and I made this little diagram here each token is going to turn into token embedding。

 combined with the positional embedding and then it's going to get fed through this transformer encoder which is just a stack of these blocks and so each block has some magic like attention has some feed forward components。

 this additions and normalizations and skips and so on as well。

 but we're going to have some number of these blocks all stacked together and the outputs of each one get fed into the next block and so on and so we get our final set of hidden states these encoder hidden states。

 aka the output embeddings and this is what we feed to our unit to make its predictions。😊。

So the way we get this， I just copied the text encoded text model。 forward method。

 pulled out the relevant bits。 We are going to take in those input embeddings。

 combined positional and token embeddings and we're going to feed that through the text model do encoder function with some additional parameters around attention masking and telling it that we'd like to output the hidden states rather than the final outputs So if we' run this we can just double check these embeddings are going to look just like the output embeddings we saw right at the beginning。

 So we've taken that one step， tokens to output embeddings and we've broken it down into this number of smaller steps where we have tokenization。

 getting our token embeddings combining with position embeddings。

 feeding it through the model and then that gives us those final outputs。

So why have we gone through this trouble。 Well， there's a couple of things we can do。 One demo here。

 I'm getting the token embeddings， but then I'm looking up。

Where is the token for puppy and I'm going to replace it with a new set of embeddings and this is going to be another just learned embedding of this particular token here。

23，68 right I'm kind of cutting out the token embedding for puppy slipping in this new set of token embeddings and I'm going to get some output embeddings which at the start look very similar to the previous ones。

 in fact identical but as soon as you get past the position of puppy in that prompt。

 you're going to see that the rest have changed right so we've somehow messed with these embeddings by slipping in this new token embedding right at the start。

And if we generate with those embeddings， which is what this function is doing。

 we should see something other than a puppy。And sure enough drum roll。



![](img/0629c20054834ad43432bab705e8969b_66.png)

We don't， we get a cat and so now you know what token 232368 means we've managed to slip in a new token embedding and get a different image。

 Okay， what can we do with this， Why is this fun Well a couple of tricks first off。

 we could look up the token embedding for Skunk right which is this number here。



![](img/0629c20054834ad43432bab705e8969b_68.png)

![](img/0629c20054834ad43432bab705e8969b_69.png)

![](img/0629c20054834ad43432bab705e8969b_70.png)

And then instead of not just replacing that in place of puppy。What if I make a new token a bidding？

That's some combination of the embedding of puppy and the embedding of skunk， right。

 So I'm taking these two token embeddings。 I'm just averaging them。

 and I'm inserting them into my set of token embeddings for my prompt。

 in place of just the word puppy。 And so hopefully when we generate with this。

 we get something that looks a bit like a puppy， a bit like a skunk。

 And this doesn't work all the time。 but it's pretty cute when it does。

 There we go puppy skunk hybrid。😊。

![](img/0629c20054834ad43432bab705e8969b_72.png)

![](img/0629c20054834ad43432bab705e8969b_73.png)

![](img/0629c20054834ad43432bab705e8969b_74.png)

Okay， so that's not the real reason we're looking at this。

The main application at the moment of being able to mess with these token embeddings is to be able to do something called textual inversion。

😊。

![](img/0629c20054834ad43432bab705e8969b_76.png)

![](img/0629c20054834ad43432bab705e8969b_77.png)

So in textual inversion， we're gonna have our prompt tokenizer and so on。

 but here we're gonna have a special learned embedding for some new concept right and so the way that's trained is going to be outside of the scope of this notebook but there's a good blog post and community notebooks and things for doing that。

 but let's just see this in application here So there's a whole library of these concepts so diffusion concept library where you can browse through tons and tons and tons look over 1400 different community contributed token embeddings that people have trained so I'm going to use this one here。

 this verb style here's some example outputs and then these are the images it was trained on So these pretty little bird paintings done by my mother I've trained a new token embedding。

😊。

![](img/0629c20054834ad43432bab705e8969b_79.png)

![](img/0629c20054834ad43432bab705e8969b_80.png)

![](img/0629c20054834ad43432bab705e8969b_81.png)

![](img/0629c20054834ad43432bab705e8969b_82.png)

![](img/0629c20054834ad43432bab705e8969b_83.png)

![](img/0629c20054834ad43432bab705e8969b_84.png)

![](img/0629c20054834ad43432bab705e8969b_85.png)

They tries to capture the essence of the style and that's represented here in this learnedbed bin。

 So if you download this and then upload it to wherever your notebooks running， I have it here。

 Learnembed。 bin we can load that in and you'll see that it's just the dictionary where we have one key that's the name of my new style and then we have this token embedding 768 numbers and so now instead of slipping in the token embedding for cat we're going to slip in this new embedding which we've loaded from the file into this prompt。

 So mouse in the style of poppy tokenize get my token embeddings and then I'm going to slip in this replacement embedding。



![](img/0629c20054834ad43432bab705e8969b_87.png)

![](img/0629c20054834ad43432bab705e8969b_88.png)

In place of the embedding for puppy and when we generate with that。



![](img/0629c20054834ad43432bab705e8969b_90.png)

We should hopefully get a mouse in the style of this kind of cutesy watercolor on rough paper image。

 And sure enough， that's what we get。 Very cute little drawing of a mouse in an apron。

 apparentlypparently。 Okay， so very， very cool application again。

 There's a nice inference notebook that makes us really easy。

 You can say a cattoy and the style of verb style you don't have to worry about manually replacing the token embeddings yourself。

 But it's good to know what the code looks like under the hood， right， how are we doing that。

 what stage of the text embedding process we're modifying。😊。



![](img/0629c20054834ad43432bab705e8969b_92.png)

![](img/0629c20054834ad43432bab705e8969b_93.png)

![](img/0629c20054834ad43432bab705e8969b_94.png)

![](img/0629c20054834ad43432bab705e8969b_95.png)

![](img/0629c20054834ad43432bab705e8969b_96.png)

![](img/0629c20054834ad43432bab705e8969b_97.png)

Very fun to get a bit of extra control and a very useful technique because now we can kind of augment our model's vocabulary without having to actually retrain the model itself。

 we're just learning a new token embedding， it's a very very powerful idea and really fun to play with and like I said there's thousands of community contributed tokens but you can also train your own I think I link the notebook from here but it's also in all the docs and so on here's the training notebook。

😊。

![](img/0629c20054834ad43432bab705e8969b_99.png)

![](img/0629c20054834ad43432bab705e8969b_100.png)

![](img/0629c20054834ad43432bab705e8969b_101.png)

![](img/0629c20054834ad43432bab705e8969b_102.png)

![](img/0629c20054834ad43432bab705e8969b_103.png)

Okay， final little trick with embeddings rather than messing with them at the token embedding level。

 we can push the whole prompt through that entire process to get our final output embeddings and we can mess with those at that stage as well So here I have two prompts。

 a mouse and a leopard tokenizing them， encoding them with the text encoder so that's that whole process and these final output embeddings。

 I'm just going to mix them together according to some factor and generate with that and so you can try this with you know cat and a snake。



![](img/0629c20054834ad43432bab705e8969b_105.png)

![](img/0629c20054834ad43432bab705e8969b_106.png)

And you should be able to get some really fun different time areas and a snail， apparently。Okay。

 well I can't spell but yeah have fun with that doesn't have to be animals。

 I'd love to see what you create with these weird mixed up generations。😊。



![](img/0629c20054834ad43432bab705e8969b_108.png)

![](img/0629c20054834ad43432bab705e8969b_109.png)

Okay， we should look at the actual model itself， the key unit model， the diffusion model。

 what is it doing， what is it predicting， what is it accepting as arguments。

 so this is the kind of call signature we call our units forward pass and we feed in are noisy latents the time step and this's like the training time step and the encoder hidden states right so those text embeddings that we've just been having fun with so doing that without any loops or anything I'm sitting in my scheduler getting my time step getting my noisy latent。



![](img/0629c20054834ad43432bab705e8969b_111.png)

And money text embeddings。 And then we're going to get our model prediction。

 and you'll look at the shape of that and you'll see that this prediction has the same shape as the lant。

And given these noisy lants， what the model is predicting is the noise component of that。

And actually， it's predicting the noise component scaled by sigma。

 So if we wanted to see what the original image looks like。

 we could say while the de noiseise lant is going to be the current noisy lant minus sigma times the model prediction。

😊，Right and so when we're denoising， we're not going to go straight to that upper prediction。

 we're gonna to just remove a little bit of the noise at a time。

 but it might be useful to visualize what that final prediction looks like。

 so that's what we're doing here making a folder to store some images preparing our text scheduler and input and then we're going do this loop but now we're going to get the model prediction and instead of just updating our latents by one step we're also going to store an image and decoding these to images an image of the predicted completely dennoed like original sample so that's this predicted original sample here。

 you can also calculate this yourself latetnt sixarrow equal to the current lant minus sigma times the noise prediction。

Right so those two should work equivalently but this loop is going to run and it's going to save those images to the steps folder which we can then visualize and so once this finishes in a second or two on the left we're going to see the kind of noisy input to the model at each stage and on the right we're going to see the noisy input minus the noise prediction right so the denoised version。

So we' just give it a second or two to run， it's taking it a little bit longer because it's decoding those images each time。

 saving them。But once this finishes， we should have a nice little preview video。



![](img/0629c20054834ad43432bab705e8969b_113.png)

Okay， here we go。 So this is the noisy latent。 And if we take the model's noise prediction and subtract it from that。

 we get this very blurry output。 And so you'll see as we play this。😊，Oh。

 I've left some modifications in from last time。 sorry， when you see this。

 this guidance scale will be back at。

![](img/0629c20054834ad43432bab705e8969b_115.png)

I think it was eight。In the next section we'll talk about classfactoratory guidance and so I've been modifying that example。

 my bad I might cut this out of the video we'll see。😊。



![](img/0629c20054834ad43432bab705e8969b_117.png)

So I' go to wait a few seconds again for that to generate。And I'll do so as patiently as I can。



![](img/0629c20054834ad43432bab705e8969b_119.png)

Okay so here we go again the noisy input， the predicted denoise version。

 and you can see at the start it's very blurry but every time it gradually converges on our final output and you'll notice that on the left these are the latent as they are each step they don't change particularly drastically a little bit at a time but at the start when the model doesn't have much to go on its predictions do change quite a bit at each step it's much less well definedfin and then as we go forward in time it gets more and more defined。

 better and better predictions and so it's got a more accurate estimation of the noise to remove and we remove that noise gradually until we finally get our output。



![](img/0629c20054834ad43432bab705e8969b_121.png)

![](img/0629c20054834ad43432bab705e8969b_122.png)

Quite fun to visualize the process and hopefully that helps you understand why we don't just make one prediction and do it in one step right because we get this very blurry mess but instead we do this kind of iterative sampling there。

 which we'll talk about very shortly before then though。

 the final thing I should mention classify free guidance， What is that。



![](img/0629c20054834ad43432bab705e8969b_124.png)

![](img/0629c20054834ad43432bab705e8969b_125.png)

![](img/0629c20054834ad43432bab705e8969b_126.png)

![](img/0629c20054834ad43432bab705e8969b_127.png)

Well like you saw when I accidentally generated the version with a much lower guidance scale。

 the way classify free guidance works is that in all of these lipss。

 we haven't actually been passing one set of noisy lants through the model。

 we've been passing two identical versions。

![](img/0629c20054834ad43432bab705e8969b_129.png)

![](img/0629c20054834ad43432bab705e8969b_130.png)

And as our text embeddings， we've not just been passing the embeddings of our prompts。

Right these ones here， we've been concatenating them with some unconditional embeddings as well。

 and what the unconditional embeddings are is just a blank prompt right no text whatsoever。

 so just all padding passing that through So when we get our predictions here。

 we've given in two sets of latents and two sets of text embeddings were going to get out two predictions for the noise So we splitting that apart one prediction for the unconditional like no prompt version and one for the prediction based on the prompt。

And so what we can do now is we can say well my final prediction is going to be the unconditional version plus the guidance scale times the difference right so if you think about it if I predict without the noise。

 I'm predicting care if I predict with the noise sorry with the text encoding with the prompt I get this prediction instead and I'd like to move more in that direction I'd like to push it even further towards the prompt version and beyond so this guidance scale can be large than one to push it even more in that direction and this it turns out is kind of key for getting it to follow the prompt nicely and I think it was first brought up in the glide paper AI coffee break on YouTube has a great video on that and yeah really useful trick or really neat hack depending on who you talk to but it does seem to work and the higher the guidance scale the more the model will try and look like the prompt kind of in the extreme versus that lower guidance scale it might just try and look like a generic good picture。

😊。

![](img/0629c20054834ad43432bab705e8969b_132.png)

![](img/0629c20054834ad43432bab705e8969b_133.png)

![](img/0629c20054834ad43432bab705e8969b_134.png)

![](img/0629c20054834ad43432bab705e8969b_135.png)

Okay， we've been hiding away some complexity in terms of this schedule do step function。

 so I think we're going to step away from the notebook now and scribble a bit on some paper to try and explain exactly what's going on with sampling and so on and then we'll come back to the notebook for one final trick。

Alright， Sir here's my take on sampling。And to start with。

 I'd like you to imagine the space of all possible images。 So this is a very large。

 high dimensional space for 256 by 256 by three image。 That is 200000 dimensional。 And my paper。

 unfortunately， is only two dimensional。 So we're gonna have to squish this down a fair bit and use our imagination。

Now， if you just look at a random point in this space。

 this is most likely not going to look like anything recognizable。

 It'll probably just look like garbled noise。But if we map an image into this space。

 well see that it has some sort of fixed point and a very similar image。

 almost pixel equivalent is going to be very close by。

Now there's this theory that you'll hear talked about called Manifold theory。

 which says that for most real images like a data set of images。

 these are going to lie on some lowerdial manifold within this higher dimensional space right in other words。

 if we map a whole bunch of images into the space they're not going to fill the whole space。

 they're going to be kind of clustered onto some surface Now I've drawn it as a line here because we' stuck with 2D but this is a much higher dimensional plane equivalent so each of these ones here is some image and the reason that I'm starting with this is because we'd like to generate images we'd like to generate a plausible looking images。

 not just random nonsense and so we'd like to do that with diffusion models So where did they come in。

Well， we can start with some image here， some real image from our training data。

And we can push away from the manifold of like plausible existing images by corrupting it somehow。

 So， for example， just adding random noise， that's equivalent to like moving in some random direction in this space of all possible images。

 And so that's going to push the image away。And then we can try and predict using some model what this noise looks like。

 right， How do I go from here back to a plausible image， What is this noise that's been added。

 And so that's going to be our， our big unit that does that prediction。

 That's going to be our diffusion model。Right， and so that's in in this language going to be called something like a score function。

 right， How do I get from wherever I am， What's the noise that I need to remove to get back to a plausible image。

Okay， so that's all well and good。We can train this model with a number of examples because we can just take out training data。

 add some random noise， predict， try and predict the noise。

 update our model parameters so we can hopefully learn that function fairly well。

Now we'd like to generate with this model， right， So how do we do that， Well。

 we can start at some random point， right， Like let's let's start over here。 And you might think。

 well， surely I can just now predict the noise remove that。 And then I get my output image。

 And that's great， except that you've got to remember now we're starting from a random point in the space of all possible images。

 It just looks like garbled nonsense。 And the model is trying to say， well。

 what does the noise look like。 And so you can imagine here for training。

 the further way we get from our examples， The sparse of our training will have been。

 And also it's not like it's very obvious how we got to this noisy version right。

 we could have come from this image over here。 added a bunch of noise we could have come from one over here。

 one over here。 And so this model is not going to be able to make a perfect prediction at best。

 it might say， well。😊，Somewhere in that direction， right。

 it could point towards something like the data set mean or at least the edge that's closer。

 but it's not gonna be able to perfectly give you one nice solution。 And sure enough。

 that's what we see。 If we sample diffusion models just in one step。

 we get the predictions Look at what that corresponds to as an image。

 It's just gonna to look like a blurry mess。 maybe like the mean of the data or， you know。

 some sort of garbled output， definitely not gonna to look like a nice image。

So how do we do better and the idea of sampling is to say well， there's a couple of framings。

 so I'll start with the existing framing that you'll see talked about a lot of score based models and so on and then we'll talk about some other ways to think about it as well。

So this process of gradually corrupting our images away， adding a little bit of noise at a time。

 people like to talk of this as a stochastic differential equation。

 stochastic because it's some randomness right picking random amounts of noise random directions to add and a differential equation。

 because it's not talking about anything absolute， just how we should change this from moment to moment to get more and more corrupted So that's why it's a differential equation and with that framing the equation of。

 well， how do I go in our back to the image。That's framed as solving an ordinary differential equation that corresponds to like the reverse of this process。

Now， you can't solve O D Es in a single step， but you can find an approximate solution and the more sort of sub steps you take the better your approximation。

 And so that's what the samples are doing。 Given like， okay。

 we see this image over here because my prediction rather than moving the whole way there in one go will。

Remove some of that noise。 right do a little updates。

And then we'll get a new prediction And so maybe now the prediction is slightly better。

 It says up here。 So we move a little bit in that direction。

 and now it makes an even better prediction because as we get closer to the manifold。

 as we have less and less noise and more and more of like some image emerging。

 the model is able to get more more accurate predictions。 And so in some sort of number of steps。

 we divide up this process， and we get closer and closer and closer until we ideally find some image that looks very plausible as our output。

😊，And so that's what we're doing here with a lot of these samplesrs。

 they're effectively trying to solve this ODE in some number of steps by breaking the process up and only moving a small amount at a time。

Now you get sort of first order solvers where all we' doing is just linearly moving within each one and this is equivalent to something called Oers method or Ula method。

 if you're like me and you've only ever read it。 and this is what some of the most basic examples are doing just linear approximations for each of these little steps but you also get additional approaches。

 So for example， maybe if we were to make a prediction from here。

 it might look like something like this and if we were to make a prediction from here。

 it might look like something like that。 So we have our error here， but as we move in that direction。

 it's also changing So there's like a derivative of a derivative a gradient of a gradient and that's where this second order solver comes in and says well if I know how this prediction changes as I move in this direction like what is the derivative of it then I can kind of account for that curvature when I make my update step and maybe know that it's gonna to curve a bit in that direction so that's where we get things like these so-called second order solvers and higher order。

The upside of this is that we can get， you know， do a larger step at a time because we have a more accurate prediction。

 We're not just doing a first order， linear approximation。

 We have this kind of curvature taken into account。

 The downside is that to estimate that curvature for a given point。

 We might need to call our model multiple times to get multiple estimates。 And so that takes time。

 So we can take a larger step， but we need more model evaluations per step。

A kind of hybrid approach is to say， well， rather than trying to estimate the curvature here。

 I might just take a linear step， look at the next prediction。

 but I'll keep a history of my previous steps。 And so then over here， it predicts like this。

 So I have now this history and I'm going to use that to better guess what this trajectory is So I might keep a history of the past you know three or four or five predictions。

 and know that since they're quite close to each other。

 maybe that tells me some information about the curvature here。 And I can use that again。

 take larger steps And so that's where we see the linear multistep sampling coming in just keeping this buffer of past predictions to try and do a better job estimating then the simple one step linear type。

 first order solvers。Okay， so that's the score based sampling version。

 And all of the variance and innovation comes down to things like。

 how can we do this in as few steps as possible， You know。

 maybe we have a schedule that says we take larger steps at first and then gradually smaller steps as we get closer。

 You know， this， I think， now some dynamic methods。

 And can we estimate how many steps we need to take。 and so on。

 So that's all trying to attack it from this kind of。Score based O D E solving framework。

 But there's another way to think of this as well。 And that's to say， okay， well。

 I don't really care about solving this exact reverse O D E， right。

 All I care about is that I end up with an image that's on this manifold。

 like a plausible looking image。 And so。I have a model that estimates how much noise there is， right。

 And if that noise is very small。Then that means I've got a good image。

 And if that noise is really large， then that means I've got some work to do。And so。

 this kind of starts。Bringing up some analogies to training neural networks。

 because in neural networks， we have the space of all possible parameters。

 and we're trying to adjust those parameters not to solve the gradient flow equation。

 although that's， you know， possible and theory that you might try and do that。

 We don't care about that。 We just want to find a minima。

 We want to find a point where our loss is really good。 And so when we training a neural network。

 that's exactly what we do。 we set up an optimizer。 we take some number of steps。

 trying to reduce some loss。 And once that loss gets sort of you know， levels off。

 reduce that of time and levels off。 Okay， cool， I guess we found a good neural network。

 And so we can apply that same kind of thinking here to say， all right， I'll start at some point。

And I' have an estimate of the gradient like maybe pointing over here。

 but remember that estimate is not very good。 just like the first gradients estimated when training in neural network are pretty bad because it's all just these randomly initialized weights。

 but hopefully at at least points in a useful direction。 So then I'll take some step。

 and the length of this step。 I won't try and do some fancy schedule。

 I'll just offload this to sort offthes shelf optimizer So I have some learning rate。

 maybe something like momentum that determines how big of a step I take and then I update my prediction take another step in that direction and so on。

 So now instead of following a fixed schedule we can use tricks that have been developed for training neural networks adaptive learning rates。

 momentum weight decay and so on。 and we can apply them back to this kind of sampling case。

 And so it turns out this works okay I've tried this for stable diffusion needs some tricks to get it working。

 but it's a slightly different way of thinking about sampling rather than relying on sort a hardcoded OD solvever that youve figured out yourself just saying why don't we treat this like an optimize。

Problem where if the model predicts almost no noise。 that's good。 We're doing a good job。

 And if the model predicts lots of noise， then we can use that as a gradient and take a gradient update step。

 according to our optimizer and trying and sort of converge on a good image as our output。

 And this is you can stop early once your model prediction is sufficiently low for the amount of noise。

 Okay， cool I'm done。 And so I found you know in 1015 steps。 you can get some pretty good images out。

 yeah， so that's a different way of viewing it。 not so popular at the moment。

 but maybe hopefully something we'll see。 yeah， just a different framing。 And for me。

 at least that helps me think about what we're actually doing with these samples we trying to find a point with the model predicts very little noise。

 So starting from a bad prediction moving towards it getting better by looking at this estimated amount of noise as our sort of gradient and solving that。

Just kind of iteratively removing bits at a time。So I hope that helps elucidate the different kinds of samplers and the goal of that whole thing and also illustrate at least why we don't just do this in a single step。

 why we need some sort of iterative approach， otherwise we'd end up with just very bad blurry predictions。

Alright， I hope that helps。 Now we're gonna head back to the notebook to talk about our final trick of guidance。

Okay， the final part of this notebook guidance， how do we add some extra control to this generation process right so we already have control via the text and we've seen how we can modify those embeddings。

 we have some control via starting at a noisy version of an input image rather than pure noise to kind of control the structure but what if there's something else what if we'd like a particular style or to enforce that the model looks like some input image or maybe sticks to some color palette it would be nice to have some way to add this additional control。

And so the way we do this is to look at some loss function on the decoded denoise predicted image。

 right， the predicted denoise neat final output and use that loss to then update the noisy latent as we generate in a direction that tries to reduce that loss。

 So for Dan we're going to make a very simple loss function。 I would like the image to be quite blue。

 And to enforce that。 my error is going to be the difference between the blue channel， right。

 red green blue blue is the third channel of the color channels。

 and the difference between the blue channel and0。9。 So the closer all the blue values are to 0。

9 the lower my error will be。 So that's going to be my kind of guidance loss。

 And then during sampling here， what I'm going to do。 Everything is going to be the same as before。

But every few iterations， you could do it every iteration， but that's a little slow。

 So here every five iterations I'm going to set requires gra equals true on the latents。

I'm then going to compute my predicted denoise version。 I'm going to decode that into image space。

 and then I'm going to calculate my loss using my special blue loss and scale it with some scaling factor。

Then I'm going to use torch to find the gradient of this loss with respect to those latents。

 those noisy lants。And I'm going to modify them， right， And I want to reduce the loss。

 I'm going to subtract here This gradient multipplly by sigma squared because we're going to be working at different noise levels。

 And so if we run this， we should see， hopefully， it's going to do that same sort of sampling processes before。

 But we also are occasionally modifying our latents by looking the gradient of the loss with respect to those lants and updating them in a direction that reduces that loss。

 And sure enough， we get a very nice blue picture out。

 And if I change the scale here down to something lower。😊，And run it。 We will see that。Sca is lower。

 so the loss is lower。 So our modifications to the lant are smaller。 We'll see that we get out a。

Much less blue image。 There we go。 So that's the default image。

 very red and dark because it's the prompt is just a picture of a campfire。

 But as soon as we add our。Our additional loss or guidance。

 we're going get out something that better matches that additional constraint that we've imposed right so this is very useful not just for making your images blue。

 but like I said， color palettes or using some classifier model to make it look like a specific class of image or using a model like clip to again associate it with some text so lots and lots of different things you can do now a few things I should note one we decoding the image back to image space calculating a loss and then tracing back that's very computationally intensive compared to just working in latent space and so we can do that only every fifth operation to reduce the time but it's still as much slower than just your generic sampling。



![](img/0629c20054834ad43432bab705e8969b_137.png)

![](img/0629c20054834ad43432bab705e8969b_138.png)

![](img/0629c20054834ad43432bab705e8969b_139.png)

And then also we're actually still cheating a little bit here because what we should do is set requires gra equals true on the latents and then use those to make our noise prediction。

 use that to calculate the de noise version and。

![](img/0629c20054834ad43432bab705e8969b_141.png)

Decode that， calculator loss and trace back all the way through the decoder and the process and the unit back to the latent right The reason I'm not doing that is because that takes a lot of memory so you'll see。

 for example， like the clip guided diffusion notebook from the hugging face examples。

 they do it that way， but they have to use tricks like gradient checkpointing and so on to kind of keep the RA usage under control for simple losses。

 it works fine to do it this way because now we just tracing back through dennoise latntence is equal to latetnts minus sigma times as noise prediction So we don't have to trace any gradients back through the unit but if you wanted to get more accurate gradients。

 maybe it's not working as well as you've hoped you can do it that other way that I described。



![](img/0629c20054834ad43432bab705e8969b_143.png)

![](img/0629c20054834ad43432bab705e8969b_144.png)

![](img/0629c20054834ad43432bab705e8969b_145.png)

But however you do it， very， very powerful technique。

 fun to be able to again inject some additional control into this generation process by crafting a loss that expresses exactly what you'd like to see。

😊。

![](img/0629c20054834ad43432bab705e8969b_147.png)

![](img/0629c20054834ad43432bab705e8969b_148.png)

Alright， that's the end of the notebook for now if you have any questions feel free to reach out to me。

 I'll be in the forums and you can find me on Twitter and so on but for now enjoy and I can't wait to see what you make。

😊。

![](img/0629c20054834ad43432bab705e8969b_150.png)