# 【加州大学伯克利】计算机视觉：视觉数据的深度学习 ｜ Cs 198 126： Deep Learning For Visual Data p16 P16_讲座16-高级目标检测和语义分割 -BV1Va8zzfEtk_p16-

![](img/1bc743f7c830211a5220e3095fa77b46_0.png)

Great。嗯。嗯。All right， we can probably get started。Those are you guys that were here for the last two lectures。

 vision transformers and the one before that was on like attention。

 how that's used in transformers kind of。The first part may be like a little bit of an overview。

 so yeah， you can kind of get into it。The timeline for today is kind of to review CNNs。

 their motivation， what makes them good， what makes them bad。

 then the transformer things that have been kind of。

Pushing forward the state of the art of computer vision we're going to first start off with like the NLP context like Bert how those embeddings are kind of generated what the purpose of that is then move on to vision transformers then compare vision transformers versus CNNs and then the Sw transformer which is an improvement upon vision transformers or kind of computer vision applications so we're going kind of talk about window attention patch merging then shift window attention which is the big thing in Sw transformers and with positional embeddings and then kind of talk about overall findings if we have time we can talk about some advanced segmentation methods but yeah that's going to be kind of a chry on talk if we get to that or not。

Yeah so starting off the tool suits the task we want to choose the correct tool， the correct model。

 the correct network to use to suit whatever task we have at hand so we talked about CNNs earlier they gain popularity about a decade ago the kernel goes over the image certain stride length creates a convolution with reduced dimensionality the way the CNN works is it detects edges in general image contours so general features in earlier layers and as it continues it kind of gets intuition for more specific features this is finally passed into an F network and you have a final output prediction we spent decent amount of time the last couple classes on this kind of earlier on so just going skim through this so we didn't talk about too much is that CNNs have translational equivaris what this means is that。

Kin of adheres to what is called a 2 d neighborhood structure so because we have a kernel which is sliding along this image a certain stride distance depending on where our kind of。

Region of interest is in the image the CNN will capture this at different points along its stride movements right so they respect locality they won't start by comparing the two opposite edge of edges of an image they'll start on one side and as the kernel progresses as the stride continues it'll learn more and more information so CNNs are translation equivariant like our eyes this means that if something if the region of interest changes position from one image to another or undergoes some type of augmentation either like a rotation in the illumination a size or a translation to different parts if I'm looking at somebody on the left side of the room versus the same person if they move to the right side of the room my eyes act as a stride right so I'll see them if I'm scanning from left to right this applies to many augmentations and we'll see how this kind of varies as we go into the transformer architecture as well so CNNs yeah the biggest takeaway。

That they're transitional equivariant， which means that as this image moves。

 our output is also translated， right， which can make sense similar to how our eyes work。

So something that's very interesting is that CNNs have shown a propensity for textual bias over shape。

 this is extremely interesting because it asserts that CNNNs can still classify perfectly given a shape augmentation while texture is constant right what this means is that if we augment the shape of a certain thing while we remain texture as as constant by applying textural filters to an image by stylizing images as it's called their performance can decrease or increase depending on our shape and texture bias that we are applying to this so this bottom example shows this well right we have a texture image of an Indian elephant this is the kind of like skin of an Indian elephant then we have a content image the tabbycat and our network classifies this correctly and as you can see all of the kind of classes that it。

They're similar to this。Are all in that kind of like cat fox animal category right however。

 if we apply this texture to this image， we classify this as an Indian elephant and our two other。

Classes that we've determined this could be are also correspond to the texture it doesn't see this shape at all this textural bias is kind of good in some ways but it can be bad in others there's been a couple studies shown on this but yeah I thought this was extremely interesting we take a stylized image and a content image by applying this style to this content this would misclassify different cities you can misclassify different kind of images as well so this is an interesting thing that we want to keep in mind as we go into transformers。

So going into the context of transformers for NLP tasks right we talked about this extensively when we were talking about attention last class I believe was vision transformers but for NLP transformers specialize in longrange dependencies right we talked about self-attention way to tie important things in a sentence together by performing attention within a sentence specifically focusing on the priors that we have based on prior words that we encountered in a sentence attention lets us focus on certain parts of the input and self-attention like we talked about lets us do this within a sentence so for example full versus empty just changing one word means that the reference for it changed so these two sentences are identical except for the last word so I poured the water from the bottle into the cup until it was full in this case it refers to the cup I poured water from the bottle into the cup until it was empty right so in this case it is referring referring to the bottle so in order to capture the。

These kindin of trends over time， self attention lets us do this in a very methodical way。

 and we kind of talked about this in the last two classes。

We also talked about this calculating attention right we have a query key value system where we have a query we want to determine its similarity to different keys。

 we want to update our value priors based on that dot product right so we're multiplying the soft maxedq times k dividing by the distance to kind of course font to the size of these matrix multiplications we want to account for this size so that this is standardized pass it through softmax scale our values by this and our output is。

Based on the magnitude of our values as corresponded to the other values so essentially you can think of it as cuning the value weights by determining whether your query and your key are similar or different so in a perfect world you could have if you really know what you're looking for if you really know what you're doing your key in your value could be the same value yeah we talked about this extensively we're going to be introducing a slight shift to this so we're going to be introducing a bias term the denominator for this specifically for shifted window transformers。

But now right we want to talk about something something new before we talk about how the tool suits the task right if we want to do some NLP stuff where we have a lot of text we use a like a transformer we can use like BRT to generate embeddings use those to capture long range dependencies for like very simple 2D image classification tasks we want a CNN with a kernel right now what if we wanted to do something to handle both NLP tasks and vision tasks or just like a general architecture that can handle both of these。

That's where the transformer comes in right we can use transformers for various tasks specifically vision transformers for computer vision tasks so yeah this paper is extremely good and image is worth 16 by 16 words this is talking about how authors wanted to deviate very little from the classical NLP kind of Bt transformer architecture so we still have 1D token inputs where're flattening basically an image into patches of 16 by 16 pixels and we're passing these as our embeddings through a linear layer which will generate our embeddings and then passing those embeddings into our transformer model the positional information now is learned by the model we don't have a positional embedding that we're passing it we talked about this during the attention lecture how we can use sign cosine different metrics to figure out positionality of different words in our sentence but that is something that a transformer is able to automatically figure out this is going to relate to the bias term。

we're going to talk about when we go into the shifted window transformer essentially this output once we kind of tokenize this picture into an embedding is a classification head multilayer perceptron to finally predict class attention also matters in this kind of vision transformer architecture as shown on the right this is straight from the paper where you can see we have an input here we have a attention focusing on the subject again we have an input attention focusing on the subject here we have a lot of things going on this is a misclassification so as you can see we don't really have attention on a onespec kind of target exactly exactly you can think of it exactly like that so we're saying that an image is worth a 16 by 16 kind of subset that we're flattening making a 1D embedding。

Out of and sliding that through our our transformer model so we're basically just kind of like shifting the information that we have。

 but we're keeping the transformer architecture the same so we're able to apply this to kind of a computer vision task。

So yeah now let's talk about vision transformers versus CNNs so vision transformers selfatten layers are global right so this is global to the entire image only the MLP will compare neighboring pixels so the last layer the multilayer perceptron。

Also to a transformer an embedding is an embedding it doesn't matter if it's an image or a word it's just quite literally a vector and whose dimensionality kind of captures different information about its input so it doesn't care whether this is an image or word the transformer architecture will stay the same this kind of ties back into the last thing that we were talking about in terms of one tool that suits multiple tasks right can we come up with something that is generalizable we can come up with something that is instead of being super specializedized something that can handle a whole bunch of inputs this also reduces inductive bias in a model compared to CNNs so inductive bias is kind of assumptions that our model is making and we want to reduce this in order for a certain model to be generalizable and this further ties into generalizing assumptions based off of training data into a model of a specific domain so for example for our NLP model that we talked about a couple of lectures ago if we are assuming certain priors for that those are not going to apply。

To when we try to apply the same transformer architecture to a computer vision task right so for those of you that have heard of Om's Razor as well。

 if two models are explaining training data equally well the simpler model is preferred as a generalization we want a model that doesn't assume priors about our knowledge or about our data and instead can be generalized to multiple tasks。

 this kind of also ties into if we're talking about like the grand scope of artificial intelligence of which this decal is like a very very small subset of people at like Facebook AI research and Laon they're trying to push forward like artificial general intelligence so some kind of thing that like captures general intelligence as we know it and in that kind of vein of thought having generalizable models is a very good thing on smaller data sets however it could be inferred and it data shows that CNN's outperformed transformers transformers really shine when a lot of data is present。

If we have a very small task， there's no reason why we would need a very complicated。

 very processing heavy transformer architecture if we have a small like 128 by 128 pixel image a CNN should be able to perform just fine for that especially if for just trying to figure out like the gist of an image however we talk about this during our attention lecture as well if we have like a whole book though we want to sort through a transformer using attention allows us to really speed up this processing。

 we don't need to constantly like go through the entire kind of subset of our universe of text we can focus on specific things during this process so a smaller data CNNs outperform transformers this makes sense but the assertion is that ViT's model human eyesight more than CNNs right they prioritize shape by default so while we talked about earlier we talked about the CNNs will prioritize texture going back to the tabbyca example。

This is very clearly non an elephant this is a cabby cat with an elephant's textural kind of component laid on top of it and a CNN will misclassify that however VITs will model human eyesight better because of this reduced inductive bias right now they're prioritizing shape over texture this is a strong benefit of vision transformer models and most of the kind of computer vision applications as we further technology are becoming more and more complicated is where kind of transform is shine architecture。

How does that idifies？Right so because we have a stride that stays the same shape and the same or our stride stays the same as we pass along an image and our kernel stays the same size we're learning things about the image very generally as we kind of go across an image so we're not we're not gaining new information about how like one patch will relate to another patch right because we're just moving a single stride and a single fixed kernel size across our image so that's where like the bias comes into play if we're able to generalize multiple parts of the image like having like global selfattention like vision transformers do this will reduce our our bias。

Essentially which they may。Exactly， yeah， that's why like on a first pass of CNN like you're going to get really general features only once you like make multiple passes。

 you start like combining or you run through like multiple DcNN layers or you going to like actually start learning higher order features yeah。

All right， so a very interesting field is adversarial attacks。

 so adversarial robustness and this is kind of a third metric that I don't believe we've talked about before but we're going to be introducing in this lecture is being able to distort an image kind of by introducing noise into it so that。

Certain classifiers are no longer able to classify these images because of the noise we've introduced but visually these are unimpaired or unobstructed This is actually relating to a project that I did as part of MLB my first semester this was kind of looking at the Carlini Wagner attack who was a Berkeley graduate who's currently working at Google brain who released kind of his own method for adversarial attacks the Carlini Wagner attack so yeah there's a lot of interesting literature in this field but because they prioritize shape over textural bias vision transformer seemed naturally robust to visual distortions so for example we have like a little panda here we introduced some noise and now our classifier is really confident that this is a gibbon even though it's。

Visually like we can very clearly see its's a pando but by introducing targeted noise into an image we can we can kind of change the entire classification this ties into this as well right if we have like a slight augmentation right the left side pretty clearly looks like a cat like a cat with like a little pointy ears if we make the nose a little more defined now it's looking a lot like a dog right so just by changing a couple pixels our entire classifier even our human eyes。

Can't really tell what's up right so there's a lot of factors that factor into decision making in natural scenarios so selfdiving cars in a storm aren't super reliable right their sensor suites have noise introduced to them and you don't want to misclassify stuff right you don't want to misclassify a like a like stop sign is like a person or something like that could have really bad implications。

But even the human eye isn't infallible like personally like the left one really looks like a cat to me and the right one definitely looks like a dog so these are very。

 very small changes in lighting pixels things like that vision transformer limitations however show in other fields of CV so in this case like image restoration semantic segmentation where patches are passed in and processed one at a time so border information can be lost right we're kind of focusing on the main we're putting our attention on the main source of information the main subject so fine Gr pixel analysis within a patch also is weak so essentially if we take。

If we take like a certain like image， I we break this into blank。

Certain patches we only have information now we're treating each one of these patches as its own data point so anything within this patch any information within this patch we're treating is like the same so like these are all the same this is all the same this is all the same this is all the same so if we wanted to do something where we need like really fine grain pixel analysis within a patch we're not able to do that right so that's that's kind of where like both CNNs and vision transformers are a little weaker。

But yeah， in terms of adversarial robustness， because like the ITs are learning as humans learn by prioritizing shape over texture。

 they seem to be naturally robust to vision distortions。

 but there has to be a lot more kind of experimentation done on this。呃。

Yeah because you can think of this noise filter that's being applied as essentially a textual bias that you're applying to this image。

 but yeah， that's why it's misclassifying however， ideally vision transformers won't have this problem。

All right。That isn't always lit。 There are problems with vision transformers。 The problem is。

Let's let's look at the original kind of vision transformer architecture right we're breaking an image into 16 by 16 pixel patches to create patch vectors with a linear projection we're passing these through combining them with positional embeddings and passing this into a transformer right this is like a very。

 very simple this is how our transformer architecture works right we have a regular transformer architecture afterwards we can black f that for now lastly we pass it through a classification head to give us kind of our final prediction is this a bird a balloon a blue sky in this case you know could be a little bit of everything but we're again we're breaking the image into these 16 by 16 patches。

This generates right 16 image tokens as we break it down。

 given the size of you know our image depending on how we break this down where each image each 16 by 16 patch contains 256 pixels but the extraction of patches is a problem specific to image not text right in text we're not really like breaking up our thing by patches we're just kind of passing in these words or sentences as embeddings for bigger image the number of image tokens will grow extremely quickly。

 which is okay for bigger GPUs or if our task only requires the precision of 16 by 16 patches right so for image classification we want to predict one label for the entire image so you want to take in this image on the left and say oh this is a balloon right so we're trying to like。

Yeah， if this is our image we're trying to say， okay， the subject of this image is a balloon。

 However， for task like semantic segmentation， we want to classify each pixel right we had a lecture about this earlier。

 we want to say okay， these pixels are people this outline is a balloon and the rest is a sky right so we actually want to classify each each kind of subpel but if we're doing this thing where we're taking 16 by 16 patches we can't really do that right because we're treating this entire kind of。

Input as its own self contained like data point so we don't actually have information about what's going on in this we're just kind of like combining it into one hoops。

😡，We're just kind of combining this into one data。And this will grow exponentially right if a 16 by 16 patch is too big for certain tasks。

 obviously we just instead of 16 by 16 patches， just use every pixel as its own patch right and pass that into a transformer however this will grow extremely quickly on like an n squared scale right because as we go from like a regular 128 by 128 images to much bigger images 1920 by 1080 now we have 2 million tokens now if we are passing in a 4K image 3840 by 2160 we have 8 million plus tokens and these are extremely long sequence length to be passed into a transformer requires a lot of processing power and it's just not very fun for us as consumers of transformers right so these are problems with the typical vision transformer。

How can we fix this Shi windows begin to swing Yeah that was a pretty bad pun but essentially the shifted window transformer was introduced in mid 2021 so not too long ago where they proposed a method to alleviate problems with vision transformers using nonoverlping windows to perform self-atten within groups then smartly combine these groups these windows together and then perform attention within these so essentially you start off with like really fine kind of not quite pixel by pixel things but really small groups then you combine these these tiny groups called patches into windows you perform attention within these windows and then you combine these windows together and then perform cross attention So now you're performing attention within two things that previously were not attended to I guess you could say Yeah so using the shifted windowing scheme allows for cross window attention connections way to。

I broke this chart so Ill not be using of that， but if we had this image。

 which we're going to come back to later， but if we had this image as 224。By 224。Pixels， right。

 we want each of these patches to be sorry， we want each patch。To be four pixels，54 pixels， right。

 this is kind of like a classic for the swing transformer。

 So we have a lot more granularity than our previous。

Previous model our vision transfer file right so we have four by four pixel patches right we want to combine this so each each of these patches is one going to be this。

So we're defining now a window of 49 kind of patches7 by seven and then we have eight by eight of these windows to get to our kind of 24 or 224 by 224 model right so we have these seven by7。

Kind of amalgamation of patches， which forms one window and we have eight by eight kind of sections that we havet heard。

That is kind of like the the big motivation for this so essentially we have our image here right we have these these patches that we're making of pixels now we have these big kind of four by four。

Sections of patches that we call windows and then we're shifting these on top of each other to classify that is kind of the overarching goal of this and we're gonna kind of dive into the details of this in a bit but because we are developing a hierarchical feature map that yields an improved global representation of the model we now know that because we're doing cross attention we're prioritizing certain features over other features right that's kind of like an inherent benefit of this model which allows us to develop a better understanding of what this global representation is of our image the second benefit of this is that now instead of n squared computational complexity increase with a respect to image size we now have a linear computational complexity because we're keeping the size of our is the same right the only thing that we're doing is we're combining the windows so instead of having n squared complexity where n is the number of vectors that we're passing in now we have。

M by N where M is the number of number of patches that we packed。

And this going to be explained further as well， but yeah this is an example of image segmentation a lot of like self driving companies and technologies use this I think it's a very。

 very cool field I think Ryan did a kind of a presentation on this earlier。And yeah。

 this flexibility allows the Sw transformer to really excel at image classification object detection。

 semantic segmentation we're going to walk through a full example of a Sw transformer。

To kind of talk about the motivation behind it as well as give like a very solid example so this is a swim transformer swim large patch for Windows 722422 k to 1 k that is a very big name but essentially we're going break this down the motivation behind the swing transformer also is that we start with smaller patches and then we merge them into bigger patches in later stages right so by combining our windows。

ASwin tiny model there's two types of models Sw tiny has C equal to 96 so a capacity of 96 Swwin largege has capacity of 192 C is the capacity of the model where C is the size of the embeddings when the image patches are initially converted into a 1D token you can also think about this as the number of hidden connections we need in our feed4 neural network so the amount of information essentially that we're capturing you guys might have when we were talking about the Bt model Bt has a capacity of 768 right so this that's the length of your embedding the dimensionality of that right 224 here represents the image size we have three channels because this is an RGB image so our input image size is 224 by 224 by3 patch4 means that the image is broken into4 by4 pixels but each of these four by four size patches actually is its own image right because we're literally just cutting this image up so this also has a three channel kind of component。

Each patch has 48 feature dimensionality including the RGB colors。

 these then undergo linear transformation， converting them to a c dimensional vector so in this case。

 because we're using swimlar model， these are going to be converted into a 192 size vector and we know from previous classes that linear transformations allow us to take like a three dimensional thing and convert them into like a c by one dimensional like vector or a1 by c dimensional vector I guess in this case。

Window 7， this means that we're partitioning the image into a non overlapping way where M equals7 so we have8 by8 non overlapping windows total right where each we have a 40 49 patches per window so we have eight by8 windows right so 64 windows or each window has。

49 patches if that makes sense and each patch is a4 by4 by3 image The math works out on this 64 times 49 is equal to3136 patches and this is the same as if we just are breaking the 224 by 224 image into4 by4 patches so 224 divided by four squared right the last thing is 22k to 1k this just means that the model is trained on imagenet 22k which is like the number of class labels it has and then fine tuned on imagenet 1k right so hopefully yeah。

 this gives you like an idea not only of what this like super long title means but also the significance of each of these things and kind of putting this into perspective is honestly like one of the most important parts of understanding the swing transformer architecture。

Okay， so the architecture overview you guys might be familiar with kind of the transformer architecture by now and it's kind of been the focus of our last three classes。

 but essentially now there are two parts to the swim architecture on the left we have window kind of multi attention and on the right we have shifted window attention we're going to start by kind of going over regular window attention WMSA and then we're going to move on to shifted window we have a multi multilayer perceptron at the end with an input and output layer with some amount of hidden layers in between and this uses a Jelu activation function right so we know that Relu is a rectified linear activation function right kind of looks something like。

系 was this。Wow， that's sweet yeah kind of looks something like this。 However。

 Jelu is a Gaussian activation function。 An interesting fact actually is that Jelu was developed by a student a PhD student I think at Berkeley Dan Hendrix So yeah super cool things coming out of Berkeley and Jelu is like pretty much like the status quo for like any kind of transformer architecture these days So that is very。

 very cool it's been cited in a bunch of different papers but yeah before passing into our MLP we pass the output of our window MSA into our layer norm which normalizes the distributions of intermediate layers this enables smoother gradients。

 faster training better generalization after you see right to kind of put this into perspective if we have like okay I'm really bad at drawing this stuff like you have like a really complicated this is like a three dimensionional surface。

And this is the surface you're trying to like minimize on it， right？

This is like a pretty bumpy surface it has like a bunch of bumps like here and there what layer norm does is it essentially applies like a smoothing operation to try to smooth this so when you're calculating your gradient。

The process is a lot smoother， so it's smoothing out your gradientding surface。

Does it only like a way that's statistical different on your batch。So yeah。

 this does like we kind of compare I think batch norm to layer norm in the last one。

 but this this specifically focuses on like intermediary layers。

 whereas batchcheorm will take like an entire batch after when like kind of iteration of training and then smooth it out so layer norm is between these two steps batchche norm would be like somewhere after。

If that any sense， so it's like a different part of the process。But yeah。

 we've talked about MLPs before， so on what Windowsed MSA is， right？

This SA were windowed multi head self attention blocks and this is performed within each window right so we have8 by eight windows now within this window we're performing WMSA。

And the way this works is M is the number of windows the attention spans。

 so instead of calculating attention across all of our windows and we might have you know like this is one token。

 this is another token， this is another token， right？😡。

We'll have like a bunch of these kind of token embeddings instead of calculating self attention across all of them。

 we only want to calculate it across a certain M value in this case M is2 right n here is the number of patch vectors and the process results in end vectors。

So yeah。We know that in our example， given that this is our example。

 we're taking 49 by 49 because we have two of these windows right each of these were 49 patches we're computing self-atten cross attention within both of these 49 by patches so the total number of do products that we're computing is 49 times 49 and since the number of patches however in each window is fixed we know the number of patches in each window is guaranteed to be 49 and that's not changing complexity will become kind of proportionate to image size or sorry sorry complexity will become linear to image size and not quadratic as it is for VIT because as we increase image size for VT we're recomputing each dot product across the size I guess that we're adding if you can imagine increasing image size is like adding a border around the image we have to compute cross attention between each kind of part of the image that we're multiplying against。

In this case， however， as n increases or sorry as M increases right。

 kind of the n here will stay the same because we're keeping the number of patch vector the same at the end of this stage one is done。

And we can move on to stage two， which is shifted window multi have self attention。

This is going to be kind of a more clever way this is the purpose of the paper if you guys do want to check out the paper we can post a link to the Ed afterwards。

But yeah now this is an author's example of how the patch merging process works so we know how window attention works right you're literally just taking the dot products between two different patch patch windows right we're gonna to use an author simpler example for kind of understanding how patch merging works so if you have M equals four windows right and you have a small image that can be broken into eight by eight patches so this is total eight by eight patches we're breaking into four window four windows with 16 patches per window so 64 total patches。

Each of these has a four by four patch once the tension is finished stage two begins and the first thing we want to do is undergo a merg process where we want to concatenate the features of each group of two by two neighboring pixels。

 so each little two by two block we want to concatenate into one kind of one。

Like window one smaller window this creates new patch borders and remakes windows so。

To kind of put this into perspective， this is our original image， right，8 by8， this is one window。

The first step is advancing each patch border by two pixels right so the top left patch border is is shown here and we want to do this for each of the four patches right so for this for this patch over here this previous patch we advanced this by two pixels on each side。

And this is done for each of these。F windows right by advancing the the patches now right we want to take these new intersections with our image and use those as our new patch borders so this results now in nine windows three on each kind of level。

But Sw has a solution to address this increase from four windows to nine windows。

 and its solution is to like cleverly combine these windows together and the way it does this。

Is shown on the next slide， but before going into that， I do want to show that。

This is our initial kind of breakdown of windows after we do our little like padding pseudo padding and remake our windows now we have nine windows right and keep in mind a window is the kind of modem under which we perform self-atten so selfattention will be performed within each of these windows right so keep that in mind each one of these kind of smaller subset is its own patch。

Okay so keeping the edges of the new windows that intersect the image right we know that we're going to be kind of introducing the entire size because we're introducing we're increasing dimensions by two on each side we're going to be increasing the total dimensions to4 but something we want to keep in mind this is where we left off on the last slide the way that we're combining these into a smaller amount of。

Patches is by combining our two by two patches， so each of these two by two patches into one patch。

 so now in the shifted window phase we're resizing our patches by combining these features。

This reduces the number of patches from eight by eight that we had before。

 eight by eight to now four by four， right？This reduces the number of kind of total elements that we have from 64 total elements to 16 total elements。

 so we're actually reducing our dimensionality by a factor of four， right？However。

 because we're reducing each component right heightened width by this certain factor of two。

 we also want to scale our depth or like our C dimension by two so essentially we're reducing the number of patches to one fourth of the original but we're doubling the size of the embedding size during this patch merging stage right so while we're reducing the breakdown of our our patches we're shifting。

We're shifting the actual boundaries that we're using for each of these patches we're keeping the embedding size and doubling it so that the total number of features that we have we're not actually losing information we're just reducing dimensionality while keeping the total amount of information that we have consistent I'm going to also kind of pull up the paper that corresponds to this so that you guys can can see an example later but this is kind of the most important part of the swing transformer architecture you're performing a two by two merging of patches so each of these patches is a four by four pixelel image now you're merging these and by doing that you're reducing the dimensionality but you're increasing the C kind of value your。

Kind of other dimension by running this through a linear layer right so we know that linear layers allow us to change certain dimensions depending on their structure and we're using that property to in like a kind of creative way。

All right， so the next thing to talk about is optimization post patch merging。😡。

So this optimization technique doesn't use padding but instead rearranges blocks to only have four windows so you can think of this as this right so we're increasing our boundary by two on each side essentially shifting this down shifting all of our windows down by two right if they start off on the top left but now if this was our entire image and these were our four windows when we do this shift we're left with a like two two by whatever this is a length of two kind of border around our image the naive solution for this would be to zero pad this before performing our attention but the authors of this paper came with a very creative solution which is rearranging these blocks to provide savings and compute power so once we do this shift if we have an image or kind of a section A C and B by doing something called a cyclic shift where we move C to here a to here and B to here so moving like across the image to now。

Calculate attention within this entire thing。 so we don't have to recompute this this kind of。

Area of information so essentially we're taking this image we're performing a cyclic shift to move it to this part we're calculating attention and then moving it back marking that this has already been calculated which provides savings and compute power so instead of having to do an entirely new operation to get whatever values for this were we're shifting。

Then calculating attention like normal， so keeping like our time complexity constant then moving this back。

This is a very smart thing， and this is an optimization that the authors propose。

The last thing we're going to kind of talk about not quite last thing。

 but is positional embedding right where we learn patch position information instead of it being provided so envision vision transformers we provided like a sign cosine some metric of。

Positional information， and we included that into our embedding。In this case。

 I talked about adding a biased term at the bottom right where before we knew we take our query。

 we take the kind of like do product with the key the keys that we have。

 we softax all of that well first we divide those by the distance and then we softmax the whole thing and multiply our value to kind of perform an informed search。

 right？Now we're adding a bias term to the bottom What can that do within an M byM patch window assuming that this is our patch window we have like know certain dimensions of this seven by seven patch window a patch can be at most six patches away from another patch plus or minus6 if we assume like a constant scale right especially what this is saying is that I started this patch right where can I look for other patches along this row I can look at like plus one plus two plus3 plus four plus5 plus6 right if I was here it would be minus1 minus2 minus3 minus4 minus5 on this six and for each of these movementekness we have a zero so if I don't want to move then at zero right so for performing this cross attention calculation do I really have to look at kind of every single possible pixel that I could use no right because I'm only performing attention within this patch so this。

Now including a bias vector of 13 by 13 components where I have my plus or minus6 in this direction plus or minus6 in this direction basically this is encapsating the possible kind of places upon which I can calculate selfatten so by including this bias term at in our attention calculation and by creating a smaller matrix of 13 by 13 dimension so in this case because it's 7 by 7 there's plus plus6 or minus6 directions that I can go to plus of course zero so that's 13 in both directions so that's the 13 by 13。

Possible directions I can go to so essentially i'm limiting the scope of the attention I can calculate which is all right in fact it's preferable because I want to calculate self attentionten hopefully this makes sense kind of explaining how positional embedding can be done smart so these are a lot of optimizations that the authors thought about which are quite quite very clever。

Are there any questions kind of about this or the kind of last couple slides， sorry。

 this is a lot of information。Yeah。嗯。他在。I my time just about I very much to do a channel size8 years ago。

他上距离。来交给他自。这个需。我。That was a really good question。Yeah， so the channel size is still there。

When we're calculating our attention， right this is actually this  four by four by three is actually a 48 dimension feature vector because of the channels。

Yeah， so yeah， yeah， it will。Yeah what is changing is kind of the information contained in this so as we combine these now the channel size will change right we'll be doubling it potentially or like having it depending on the linear transformation that we're applying to。

So very similar to what we talked about with like CNNs and advanced architectures on that front。

Okay this is kind of where the math comes into play which is a little confusing but this is the combination of patches and then finally kind of landing into a prediction so if we have seven by7 windows and 8 by87 by7 patches per window and eight by8 windows currently encoded in c equals 192 because this is a swing large model then we have you know 3136 patches we do the merging process where we reduce the number of patches by one fourth we talked about this earlier right we went from 64 to 16 patches when we reduced dimensionality from8 by8 to4 by4 kind of drawing this out really quickly we have eight by8 but now we are。

Making this into four by four and combining this， this， this， this， this right， et cetera， et cetera。

Were reducing that dimensionality， so we're having each dimension which now results in 784 patches we double the encoding size though right through our linear embedding so we're doing two times 192 to get 384 encodings even though we have 784 patches now our dimensions。

Our height divided by eight times with divided by eight and2 c that is the end of stage two and stage three and four。

😡，Sorry， we're kind of doing the same thing。We're once again having the dimensions。

 So we get height divided by 16， with divided by 16， then height divided by 32， with divided by 32。

 right， And every time we do this stage， we're doubling the information that we're containing in our encodings to keep this constant。

 right， So now we're going from 2 C to 4 c then to 8 C after stage 4， we have 224。

 which was our original originally， we had a divided by 4 after stage 2，3 and 4。 Now we're doing 2。

24 divided by 32， which results in 7 by 7 tokens and an embedding size now of 19 1。

92 times 2 times 2 times 2， right， So that represents stage 2，3 and 4 to get 7 by 7 tokens and 15。

36 dimensions。 M now equals 7 by 7 tokens。 So when we get an M equal to our past size。

Right our window size， when we have the same amount of tokens as patches in a single window we know we finish the process right this makes sense because now we've broken up this image essentially into like a representation equivalent to our initial kind of patch breakdown the last component is an average pooling layer right so taking these certain components pulling them together and finding the average of each subset and a norm to get a single representation with 1536 embeddings Lastly we have a classification head to convert this embedding to the right class so the moOP classification head at the end is kind of what gives our final prediction。

Okay taking a step back swim transformers manipulate windows so that attention is performed on certain subsets but cross attention happens between regions as windows are combined and moved and shifted This begs the question are we hurting some of the things that makes transformers what they are right are we reintroducing inductive bias by kind of making these similar to cs in that now we have what is essentially like not quite a slighting window but now we have shifted windows which is you know kind of the same thing are we reintroducing this inductive bias as we're doing this there have been studies done on this and it shows that they perform pretty well in regards to corruption robustness and that swim models still have a shape bias far lower than VT right so VTs have a quite a high shape bias which we're。

Very glad for right we want to prioritize shape over texture。

 but swim models have a lower shape bias than vision transformers right so that could be something that we've introduced by shifting windows。

 which isn't super ideal However， they don't fall prey to the issues that CNNs do like being weak against adversarial attacks that should be against against adversarial attacks so are we getting closer and closer to the goldilocks of the shape texture bias right we want something that is able to identify changes in shape and able to identify changes in texture much like human eyes but we want kind of a model in the middle。

 we don't want something like a CNN where it's so far towards the texture side that by just laying over another texture on top of an image and middle misclassify but at the same time we want something that doesn't have the same problems as vision transformers and that we don't want like high computation costs as well as not being able to classify certain subsets of an image。

The beauty of transformers is in their genericness they can capture patterns accurately no matter the data type or domain or use case right it's the same transformer architecture whether're using this for vision applications or like NLP applications right these are basically looking at patterns no matter what the data is because of the kind of self-atten calculations more data results and more performance right we talked about this earlier transformers are good if you have a ton of data and VIT showed clearly visible improvements up to 64 layers so as you scale the model you're improving performance right which is what we expect for transformers lastly S is scalable it has linear time complexity n byn time complexity as you have an end and then an end that is kind of changing as you scale the size of your image reattention and other techniques can help transformers get even better if you know we calculate attention once but we can recalculate attention on the same parts but yeah we talked about this this is like。

Very first example last week where we're trying to do like a French to English translation using a transform model Andre Carpay who is the former head of AI at Tesla also kind of cites this paper as as very cool so yeah a lot of really cool things happening in this field food for thought specialization is for insects this is by an author that I forgot but essentially what are the benefits and drawbacks of having a model that can take in any kind of data process it and pull out patterns right is generalizability the future of AI kind like a general AI that is able to a black box model where I can pass in whatever and ask it for whatever and itll be able to synthesize these patterns accordingly I can ask humans a whole bunch of questions right is this chair the same color as this chair I can ask like if you're bilingual like what does this mean in this language right can we create a model that model the human brain by being able to have one model that can do a whole bunch of things depending on the input and the output that you want right is godilo's novel what we want。

ant task precision for self driving cars， do we want a really robust like Goldilocks model is a self driving car going to need to like。

 you know， do these translations， right？A whole bunch of considerations that we want to make Overall the field of adversarial robustness is still developing just shape and texture aren't enough features to prove invariance to certain attacks so you know some other kind of future stages can be testing Sw against Carlini Wagner or more advanced adversarial attacks that's basically it that is all of it that thank you guys for coming hope you learned something new these slides and this recording will be posted yeah thank you guys for coming。



![](img/1bc743f7c830211a5220e3095fa77b46_2.png)