# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p12 P12_W08.1_基于掩码的视觉表示学习_MAE__BEiT__iBOT__DINOv2_第1-2部分 -BV1RPZwB6EJZ_p12-

这份。I this recording。All right， let's begin。More really。这就是 start。Today we'll talk about。诶。要做 big。

So last time one of you asked me， okay， last time we saw like the state of the art selfupervised way to learn visual representations from images。

And somebody asked me， do we really need？To have this pipeline of augments are we do we still need to rely on event augments？

And I said， yes， as long as you do this type of discriminative。Tpe learning where we take an imageU。

 we take the views， we process them either with the same network。

 it's called either CME's network when the networks are have the exact same parameters or with this teacher student dynamic where students is updated through backward。

 the data is updated as an explanation moving as over the parameters of the student。

So in this type of visual representation learning， you do need。The augment。However。

 we can borrow some ideas from the field and the progress in advancements in natural language processing and try to come up with different strategies to incorporate masking。

So masking is the alternative to。Get away from the image documentations。

So we show that what I mean when I say when I refer to him as a conditions， I referred to。

Aund the precise crops of different scale， usually from 5% to 100% of ams。Or co detail。

 which is basically distorting the statistics of brightness and contrast over humans。

And additionally， for natural limits， you can distort the saturation and you have these parameters where you can control how much you want to do。

Distor those statistics。Okay。So we说 dino。So here， this is what I mean by discriminative way of。

Learning representations， so we want to match in some feature space。

 either if it's softm and we assigned classes or if it's directly on the feature space as we showed these other method called beyond。

Where you try to directly， minimize the mean square error between the two networks。诶。

So let's see how we can。Go one step further and stop relying on augmentation What is the difference？

What are the augments， the representations， sorry， what are the representations that we do learn from this kind of method？

So we started with the first method called MAD is the abbreviation or mask autoencoder。

So this is a quite simple method， so if you remember from the first two weeks we saw this idea of autoenrs。

So we try to， we have like。Any type of network that is decomposed in two networks。

 so the encodeder and the decoder。This is generally for auto encoders， so you have the input。

 you apply some perturbation of the input like Gausian noise。

 masking or something like that then you have like。

A vision transformer or a convolutional neural network where you have some compressed version of the input and you have some。

representationpresentations， and then the decoder network is responsible to move back from the continuous feature space or latent space。

 as it's called because it's kind of hidden。Because the network is not reallydirect optimized on the latent space。

And the second network is called the decoder。变的。In practice。

 you can imagine this with transpo convolution or convolutions plus upseling。

The bottom line is that you need to move back on the initial element space and then calculate the loss on the initial element space based on the undistored。

今す。So this is the first。Approachs that showed that。We can learn representations by directly。

Mimiking the pixel intensities， so directly on the image space， as we can say。

So what is so special about this method？What is really re attractiveive？Is the part that。

We can combine this idea with vision transformers。So the visual transformers process a sequence as a set。

 as we have discussed already on the course。And the big advantage is that if you consider。

If you treat the images as a sequence。You can discard。Tokens or elements of the sequence。

And you don't need to process them on the encoder network， so the image behind me。

 you see that the encoder network is not crossing the mass patch that are indicated with gray little squares。

So。The more。合います。Parties on the eight months。The more computational complexity I say。

 because I don't have to process this on the encoder network， is that clear？

So in the case of if I must。99% of those passes。In the extreme case。

 I only have to process 1% of the unmasked passes。The first word that。Kind of created this trade off。

Which gives you a lot of computation and。The main reasons that they aimed for such an approach is that this makes things even more scalable。

So you can imagine also you see the two networks are assymmetrictal。

 meaning that the encoder has mets a significantly increased number of parameters compared to the decoder network。

 so these are just two vision transformers。So， you cannot。Have the same method。

With the convolutional neural network because。You would need grid structure data so you cannot remove。

Those masked patch， as we saw some approaches from 2016 and 2017 where they tried to do something similar with in painting with convolutional networks。

 they didn't have this advantage of being able to discard。

And not to process this information on the encode。So the trick is that you cannot completely avoid these unmaked passes。

 you still need to add them， but you have the decoder which is responsible。

For reconstructing basically all those。Tokens or projected parties。Back to La at space。

So you don't just blindly mask the parties。 You need to remember which positions you have。

Which positions in the sequence you have masked and then you replace them。

So you see the number of input and output tokens， so the transform is always the same。

But then you have the additional step that we need to add back in the correct positions， the mask。

Toalkens， so you can imagine this is like similar to the Cs token or the end of It's like a trainable。

多见。But。In its layer of the decoder of the transformer of the decoder。This after proxy。The blue。

 which is the representation from the encoder and the mass token。

 you will have a different representation。Here as indicated with the rapid squares。Is that clear？

How do we win， okay。So then I need to ask a very important question。

What is the masking ratio that it would be。Let's say the opt。

What would be the intuition and how to pick the masking ratio or how much of the patch should they mask。

So let's go back to because as I said。诶。These methods are big upon the improvements of natural language。

 so there is a lot of analog and correspondences that we have to think。As to how we could process。

Signs。So， both signals。Both images and natural language can be regarded as different type of signals with different particularities。

 all right？So let's go back to the B approach， Does anybody remember the masking ratio if you want to train a bird model in natural language？

Approximately no。Yes。😊，Yeah，15%。谁家谁晚会。When you have。A sequence。Okay。

 do you also remember what are the tokens in natural language， what do they represent。

 what information do we？Represent with one element in the sequence。几年嗰个。Very what。

 and em bedding of over。 Yes， so these are word buildingsddings。So this is War one， War two。

 War three。More work。So we take a sentence， let's ignore the start of sentence and end of sentence because now we're trying to establish some intuition。

 we don't care so much about the technical details。So today is a great day。

We map all of those vector into the vocabulary and project them。

 and we end up with war embeddings and we can have as many word embeddings as the vocabulary of a land。

And then。We must。15% of them And will replace this with the。The mask in talkingken。

Which basically a vector， but we be trained alongside the network。 And after the proceeding。

 we tried to predict war3。 So the war。So the entry of the vocabulary。

 so ifabulary the vocabulary is the number of classes。

So it's a kind of supervised program where you have cross entropy， even though we call it masked。

Language modeling in the end， is just crossenttropy， and we are trying to predict。The entry。

 the index that correspond to this word emed。Any questions？Okay。

 so if we can regard two types of signals。诶。What is the fundamental difference？Between。Wars。

Sentences and ens as a signal。Any tuition。Yes， an image has a fixed size。Yes。

 we have the grid structure in the grid。Okay， and also the vocabulary。

Let's say vocabulary here is kinda also fixed。 And we have channels with like。

The vocabulary natural language， you mean like you have like a specific set of words。

In natural language， a set of words， in like in computer vision on images， it's a limited。

Like range of values， I' see。A range of values。 Can you be more specific So like if you're talking about pixels。

So you have specific， you mean we haveities， yet intensityities。So they。And NOP， we use ver beddings。

Computer vision be use directlying the data， and computer vision is more like continuous data。

ConueYou mean that the pixel insities have continuous ratings since there be samples from0 to 255。

 Yeah， that's partially true。 So let's stay on the。On the great track tour。

So you want to agree that you have some greed。1二。Very nice structure。And。

What is the intuition that we use， the inductive biases convolutional neural networks， what is this？

呃。It particularity of images。Signals that we try to leverage with compositionos。Yes。

 it's seen in images， the inductive voice that like the information is distributed spatial。Yes。

 this is equivalent to say that it's structured on the green。

 so especially if the green it's either one， two or three degree。ok but。What is happening here the。

How can I say without giving you the answer？What's the intuition that we use these commvolutional neural networks and we group these pixels together？

没什么意思。Okay， yes， influence the。D an answer， okay。So let's say we have。诶。Three different dimensions。

 okay， two different dimensions。 This is an image of 224 by 224。And then let's say， I want to。

Dam scale。So I only keep from its neighborhood。诶。One of the piecess I take。Small。Regions。

And I resize the image to。32 by 32 by down scale lay by a significant factor。Can we still see。

As humans， can we still see what's happening here， when we go from a small image。

 when we downscale ras， like las you had in the exercises like this SDF 10， Cy prop 10。

 all these data sets？Can you still visually identify the information？

So by reducing the information of a factor of， I don't know。224 devices by 32。With， seven， Yeah。

 okay， thanks。So by reducing the information by a factor of seven， yes what you missing saying？那そ。解し。

That course。なります。I'm not sure I。Okay， I think you start to get the intuition，I was about to say that。

Like in the pixel or in images。Ser， so I can reduce。The amount of information by seven times。

 seven times by a factor of seven， and I can still。Have the same。

I can recognize as human the same class， so this means。Okay。

 let's take the same example and say we have a text。And we remove 70% of the information。

Would we be able to understand the text？Probably not right。

So the difference lies in the redundancy between the different signals。

 and if you go one step further in videos， the redundancy is even higher。So if you take， let's say。

 20 frames per second， the redundancy between those frames is。Significantly larger。

 but we can already see that from a single， let's say， image。So you can have。5een。Masking ratio。

 and we are able to reconstruct。At least we asked the network this pretext us to reconstruct the rest of the text。

So in language， the inition result we need a la。But we need， it's more intuitive to use a larger。

Maybe significantly larger， and we see the different approaches， yes。This rescue。

I Wednesday or the future extractionurion easily not be Washington I on the piece of values like the things in place。

The future in extraction is it will depend on hos， but in this。It's thick tokens。

 we're just talking about the tokens here are the passes。

 so the projection of the passes are the tokens of the sequence。So。This would be in。 This would be。

Pts one， the projection of pot one， the projection of pots two， the projection of pot  three。

I don't know if you remember with vision transformers。

You have this input and you take these non overlapping practices。

So the in here is that we can mask a larger amount of information。Because even with。

Lets say 50% of the information data。We can still understand the object。All right。嗯。Nonetheless。

 they made like an extensive analysis either。😊，So the objective here is mid square error on the event space。

So they make an extensive analysis to different masking ratios here you can see from 10% to 90%。

 and they made some graph。诶 which is。Not at general conclusion that you should use for any method。

 this type of these ranges， so from 7 to 20% you see it's like almost the optimal ranges。

But this is like specific to these approach。But you should expect。

That all different masking based approaches that you will see in vision will have at least a larger amount of masking ratio。

So here they found that the optimal is around 75。For natural languages。

And for those who like this kind of。Different application fields， I used to train some models。

Some must encode vision transformers on microco paymentss and we found out that this behavior is not the same when you have these populations of cells。

 you need a much smaller masking ratio。So the redundancy is smaller。And the additional results。

 as you can see on figure eight on the right。That they still perform。Given that you fine tune。

 so by fine tuning， I don't know for those。We make a significant mistake。

Clarify and emphasize on the difference between。From me。So do you remember from the exercise class。

 what's the problem？So you train， you keep the representations fixed。Frozen。

 and then you only train one single linear layer。Without a lot of belts。So day everything and find。

Means that we train both。The network that you。Pretrain。

 so you it's like a it's like a different alternative to random initialization you initialize with the weights you learn from the pretext task and then you also train。

The backbone or the pre train network plus the classifier。嗯。So these results are on fine unique。

And you see here， there is a small。Disrepancy between those two。APros of inrov versus fine unit。

 we'll talk about that a lot today。And they can still have a better behavior than so here we're not only interested on the Y axis。

 which is the。The validation I receive， but we are interested。On how much we can scale。

 so given that we have an infinite amount of compute you you use in practice。

How do different over parameterized models scale？With respect to。

The validation accuracy with respect to the number of parameters they have。Okay。

 the number of parameters is not by itself。A comparison for the computational complexity for。

A specific architecture。But given that you have the same architecture so bit base。

 and you just change number of layers， number of heads， embedding dimension。

 only these three parameters。诶。Almost linearly scale up these three parameters。You， you can。

Compared between the number of parameters， but if you have， example。

 resonanceates or different conclusionvol this。诶。The X axises really make so much sense。

Do we have other metrics？说的。嗯。So they still have so the pre training from the masking what happens on Inet。

And the fine tuning。So one might ask， is this network just memorizing the data？

Like can you memorize with a bigger model， can you just memorize one million images and learn how to reconstruct them？

And to answer this question， okay。This is a pre training。

 supervised pre training on a huge private data set of 300 million imes。Which is。Stay surpassing。

This approach。So to answer the question， if the model is just memorizing the data， we need to。

One way to answer this question， at least visually。Is to inspect the reconstructions of the。

Validation data so then the data the model has not been trained with。总啲车系搭嗰度诶。

Validation images from the same dataset set。 So the same data distribution that the model is trained on。

 And we can see that the model can。Create。Pusible results。Even though。

They may not always correspond to the real class。And you can do， you can perform inference with。

Any number of masking ratio that you。So you have maybe 75% for training。

 but they also show that you have even a larger number of masking ratios viewing inferences。

So here we're going to。Have an idea of how the model。

Learns to reconstruct so how well the model performs on the pretext task。But maybe that。

Maybe or maybe not will give us some indication of the performance on the dance task as to whether it memorizes the data or not。

🤧诶。So the question here is， why does that so blurrry， do you remember？上。Sorry， because of MSE， yes。

 because of the training objective， because we saw that when you reconstruct。

The data with either L1 or L2 loss， but directly。On the image space。诶。The network generates。

Blad predictions。 So you should definitely。Have learned this during this course。诶。

But we don't really mind at this point because this is like a type of， let's say。

 a narrative pretex stuff， but we care about the intermediate representations learned from the encoder。

Because we want to use them。To。Classify im。嗯。So another intuition here is that。

Even though we mask pot。SinceSince we have unlabeled data。There is no indication that the。

 the patches that we must randomly refer to different object entities that may correspond to the semantics。

Yes。Can we have any with objects？So if have animals with different semantic。

cateategoorries or objects that we， let's say in the downtown town。

 who would like to recognize these objects。Either with assigning a single label to each pixel or just learning bounding boxes for these different objects。

When we just see if have another。So when we just around them leave？Mask。Part of the information。

So the red one correspond to the。The random parties that we want to mark。

There is no indication as they write that。The removal of these random patch corresponds to a semantic segment。

So in this example， we must something that we want to reconstruct and it would be useful to blur。

The intermediate representations that reconstruct this entity。But for example， these pots。

We have no indication it would not lead to a meaningful representation by constructing something that we don't really care for the downstream task。

Is that a bit more clear at the moment？however， still， even though we we have no。

Prior knowledge that this random masking will be beneficial。The authors argue that。

You can still learn various， hidden representations inside on the output of the encoder of the Vi transformer。

系。ok and。Maybe a last question that just small。嗯。A small emphasis。 So if we have like。

From zero is 100%。Making ratio。And here we have the。Complexity。嗯。

This would lead to it will not be probably linear， but it will have this kind of。Behavior。

 so this is the complexity when you don't mask the image。

 So it's like the baseline complexity it's just processing image with a vision transformer and this could be。

Let's say zero complexity if you mask all the image， you have nothing to personal on the encoder。

And the more。You must they much。The more you reduce the complexity of the encode。

 so this is the most attractive component of this architecture。Is that very。

 very clear and established？However， burn doesn't work。In exactly the same way。呃。Yes好。コ多で。Fsmatic。验收。

I would tell you the answer directly， so the best way to measure the complexity in practice is to establish。

Some references。So you say given hardware。Given a specific hardware， so let's say one GPU。

 a specific type。And a specific bag size。That fits。

For all the different models or for different setups for this model。呃。And given the data says deep。

 so let's say。100000 images。You perform inference France with。Let's say not just one。

 but a lot of those images， let's say data at least 10。

000 of those images and you measure the GPU time to process the images so you measure，二。今まジ。玩 second。

So you measuring a given hardware with a given， I don't know Pi or sca version。

 how many images you can process in one set。There are other metrics which like the flops。

 floating point operations per second， but this is the most accurate one。

So let's go to another approach again borrowed from natural language。Where we tried to。

Create a pretext task very similar to B。So the acrom is called Bayit。

 I don't remember what it exactly corresponds to。But the idea is slightly different now。We are not。

Directly relying on the image space。诶。At least for the pretex staff。But we try to assign its path。

To one specific entering the vocabulary， so similar to natural language where we have like 20。

000 words。Here we have this notion of visual vocabulary。 so we try to。To say。

 I also use the word overcing in the previous lectures， so we're trying to say that no matter。

Ws and how different and image spots can be， it has to be assigned in one of those 10，000 or 100，000。

Classesses。So this is like get more discreized objective where we want to train with personnelnta。

But在 question刚时 saidO。This begs the question， how can we assign image parties？

To discrete values in a set of visual vocabulary， so visual vocabulary or prototypes or code book。

 different papers use different terminologies， but they all correspond to the same thing we want for each part to have one。

Disretized class。I don't know if you have already understood it。

Nere network don't like discrete stuff。Eially during the optimization。Nonetheless， they use。

So they used and nowvi。Task， let's say before the free task。Which aims to mark。The passes。

In a given discrete code book or visual vocabulary。And they do this by training a auto encoder。

So this by itself is not enough because you have an encodeder， a decoder。

 it doesn't matter if it's a vision transformer or not。Any type of encoder and decoder you still。

Optimize。Both networks。To reconstruct the image， but now。

We will not keep this representation for the downstream task， we will just infer some vocabulary。

Would try to map。The latent space， which is a hidden， it's a continuous space。

 so you have just a vector of continuous values and we will try to map。Those。This latent space。

To a specific number of visual vocabulary。All right。So the question is how we do that。

 because if we do that during the optimization。As it's on right now， it's not。

Do you know why is there a problem if we disreize？This is this latestnt space here。Do you have any。

InWhy this would not work。If we just。Find a way to discize。诶。 okay， it's a bit not very obvious。诶这是。

So when you optimize the mean square error。You cannot propagate the gradient。Here。

 because dereittization is a non differentiable。呃Oper。Allright。

 so here we cannot just propagate the gradients in training end culture。

let's say in the vanilla case where this is just a latent space and we apply some sort of discretization。

So we need to solve another problem， how to discretize the latent space。

Which is the main difference between is Bay version1 and version 2。

 but let's say we do find a way to discretize this space and assign。It's in much parts to a specific。

Visual vocabulary， is it clear that then the pretext task is exactly the same as bird？

Get some of the。Describe how the。The pretex us would look like based on the image given that we have。

WWe solved the problem and we assign。Its parts to a visual entry。

Would somebody like to try to describe how this embedded approach work？

I don't know Maybe it's still always。If you take the sequence， which is the projected parties。

 and then you mask the similar way you would mask words。

 you just have to pick a different masking ratio for the reason we discussed。

It's a big larger masking ratio。This is just positional embedding， not so important for the method。

 you process this with a transform encodeder and you just apply crosscentro paint for the masked tonkens。

Is it clear？If yes， let's see how we can。Disretized space。

 so the two ways to discretize refer to debate version 1 and version 2。嗯。

And here I want to emphasize that。The discretization problem that leads to no differential rules。

So we get a basic train。冇咗力咯。So the first version is a bit complicated。

 I haven't read all those favor， but these acuries。

So they apply some of the mathematical approach which called。Ger soft much the relaxation。

But the most， and this is probably what they got wrong。Because then in the next version。

 so this BIT version2。This is the result of the first approach， we will see them later。

Along with other things， but I want to emphasize。诶。That this is the way to learn。

 this is the state of VR method。Back with some theory on how to disreittize。The latent space。

And still keep everything to still maintain that this process is differential。So you have these诶。

These back doors。And you compute everything is able to normalize as always and。

You have some cold book and bads。The code book and visual vocabulary are the same thing。

 So we define some。Vors that correspond to。Okay， let's think by， let's say we have 10，000 classes。

高 classic。And for each class， we have a vector of a specific dimension of B。

 so K here refers to the 10，000。And then we just find。For each individual ton， ton representation。

 we find。The closest vectors， so these are learnable vectors randomlyized in the beginning。

 but still learnable during the training。And we find。

The vectors using cosine similarity from nearest neighbor look it's basically cosine similarity because everything is bent to normalize and we find。

The。The entries of the code book will correspond to these 10，000 vectors。

And use those for the decoder， that's why you see different colorss here。无异议。

Un taps output to the encoder and this is so the arrows here correspond。

So each one of those representations of the tolkens will be mapped to one of those trainable vectors and will be used on the decoder。

And。The gradients， since the shapes are the same， will be just copied。So it's a small trick。

 but I find this to be a very useful technique。And it's the state of the art method to discretize the latest space in case you deal with problems in the future outside of this course where you。

Desire something similar。any question on how this approach works， Yes。

 can we just like extract the features and then try to map them to a district？Values。我的。わ。

How would you have let you do the training。Normally。

 and I extract features that are not like discrete values。And then we， we map them to。

 to some discrete values that we can then feed to the the ver。冇盾。

So let's say we have a about size of one and we take the algorithms。What do you want to do with them。

 like if you feed them directly。It would still be continued by。 Yeah， after that。

 like when we extract the features after we done know the decoder。

After we've done the whole training， we have some features and then we can use like we can map those features to some discrete values to do like to train on the latent space and then try to discretize the latent space after we were done with training。

This is a simple baseline， I guess。Somebody must try it。I don't know as to whether it can work。

But I know that this one is like the most。A theoretically justified method to create because here the code book。

 so these trainable embeddings。Are not war em beddings， so you know。

 like pots and beddings or into the beddings。Are like the prototypes。

Vs will be learned alongside training and they will be optimized for your specific。

Training data and task。While the discretization is a general method that you would apply。Later。

 it's like a nonleable discretization， what you said like the baseline just discretize the outputs。

And with this trick to copy the gradients back to the representations from the code combatddings。

We can。This is the best way that I would like you all to remember as a reference for the future。

But do you understand or is's like not at all clear？Okay。

 I will just repeat on one more time and question。common。These are initially in the beginning。

 randomly initialized vectors。So you do a forward path from the vision transformformer。

 you get n is the number of passes。This is the embedded dimension or the model。That。

You do if everything is as normalize， it's just a market certification。So basically similarity。

 so you see， for example， for these one， for this representation width。

Entry of the codebook has the closest similarity。And you use this one。

 so here you see the different colors correspond to this。Yes， varieties。

The deritization lies in the fact that here I know where it comes from why is。

Because we want to assign each path to one class。We one codebook entry for the pretext task that we said like a trade in a bird like fashion。

So let's say we want to kind of mimic。This idea of natural language。

Where we have this vocabulary and we try to translate this into vision。

 because this what people trying to do， they try to incorporate this idea of birds because we know that bear works extremely well for natural language and proteins and all this stuff。

And we try to find tricks。To do that in vision。So this paper is called vector quantized。

Variation of encoder or VQ VE。And I think it's a great approach though it's not directly。

Applic for all the things we've seen in the presentation。嗯。So one last time we have the sequence。

 we must。And then we predict the mass volume since we have the labels， let's say。

 we get these labels。It is like the visual copy there。So the second version this bait number， okay。

 they tried also another thing。They emphasize。Everything was sold before。

Ding that you have this discriminative task。Where you take the classification talking and then you try to match the cross entroroppy between the teacher and the student。

They try to create this hybrid of combining this。Mask based。The narrative approach with D。

 which is more discriminative， it's right to match the percentrop it。诶。This was a fresh step towards。

The state of the art， but。In their process by plainly combining these two objectives。

So we didn't illustrate any significant improvement by itself， but we would seeing this。

In the later webin。Here's a typical approach of transfer lagging or。

Training from scratch versus having an initialized network and that find unique。对C的。

