# UCB《计算机视觉与计算摄影学｜CS 194-26 Computer Vision and Computational Photography 2022》中英字 p19 -P19-19-Generative Models-10_31.zh_en -BV1w7UfBdELA_p19-

All right， folks。Let's start。Okay， so today we are。I believe this might be our last。

Neural network lecture。 we will。Get to。Im this is。And try to put it all together。

And it is kind of a little magical thing。 So we're going to try to go slow and make sure everyone's。

😊，On board。And。We will actually go start way back when we talked about texture。ok。Remember。

 when we talked about texture， we talked about。Texture being。Samples drawn from a distribution。Right。

 so here， all of these images。They're different images。 They look different。Right。

 their distance between them and， you know， L2 distance is going to be very big。Yet。

There is something in common between them， right， Theyre all drawn from some。Distribution。

Of this kind of brown brick。应该。And so this is a good thing for us to kind of keep in mind。

That there is some sort of a。A set。Of images， all encompassing。This idea of this lecture。

Or something like this。 There is。There is some infinite， true， infinite texture up there in the sky。

 right， of this。Of this。Banana bread。Its just that we don't have access to it。Right。

 what we have access to are just samples drawn from that。That。Big infinite texture， okay。

But it's clear that the samples。They share something in common。 And what do they share。

What do they share。2。Who can tell me what they share。What。Coer is one thing。 Okay， what else。I。

 they share statistical properties， right。There is some statistics that you compute on all the samples from this texture。

 and those statistics should be similar。Right。Because they are drawn from。

The same texture distribution， okay。So， even though。There is no。

Pixel to pixel correspondence between them。 There is some statistical features。That are in common。

Okay， and remember Eish， we were talking about Eish and he was trying to find these textstones in this。

 you know， histograms of textstones in some way to， to capture these statistics， whatever is shared。

Okay， and we are going to continue with that。 And we are going to， you start with thinking about。

Texure synthesis。Last time we talked about texture synthesis。In this kind of。

Language model kind of way， like the following Shannon， right。

 So we basically just find similar patches and just keep， keep growing， Keep adding like。

 like in a text predictive sense。Today， we' are going to talk about texture synthesis。

But from a more eish like view。From the view of。Trying to find a set of features， a set of。

Statistics。That all， all the samples from this distribution should share。Right。

 and once we have these set of statistics， now we can just generate infinite number of these。

 of these textures， because， well， you just generate something。You know。

 you start with some sort of a noise image， and then you just coerce that noise image。

 You push that noise image to have the same statistics。Does that make sense。Okay。

 so this is what we call parametric texture synthesis。 Last Yes。

 last time it was non parametric because last time we were basically just finding bits and pieces of things that we have seen before。

This is parametric。 We want to have some set of statistics， some sort of set of parameters。

 like in the statistics class。That we hope should be shared by all the samples that we want to。

 we want to generate。应该。And a generative model， a parameter generative model， is a model。That。😡。

Figures out what are the statistics， What are the parameters that that that are shared by， you know。

All samples of this banana bread texture。 And then you just basically just sample randomly。

 you just sample。Random instantiations of these textures by just varying the parameters and just making sure that the statistics are consistent。

你该。And basically， most of the thing we're going to talk about today are going to have this。

This flavor。And the first paper is， I think， a very， very key fundamental early paper。

 Higggerberggen， Se graph 95。It was one of the first papers on textures。 And this is。

 so on the left is the input texture。 On the right is。Something that was synthesized。 Okay。

 a generated example from the same texture， okay。So let's， let's look at how they did this。

So what they did is they say， okay， let's， you know， let's remember our early vision models。

Let's remember， we have our filter banks。So we basically think of， okay。

 we have bunch of filters that are being convolved with the image。Okay。

 and so the argument here is that let's。Let's use these features as our statistical units are texts in。

 in the Ulish parleys， okay。And let's see if we can， somehow。

Compute some statistics of these features。That。Will be the same for all the samples of of detection that we are looking for。

 Okay， so。What they're doing here is a little bit different from what we did before with just a filter bank。

 They basically make it into a pyramid。 It's called the zero pyramid。

 It's basically a multi scale filter bank decomposition。 Its just that it's， you know。

 it's in a pyramid。 So it's faster to compute and blah， blah bh， but it's basically the same thing。

 So this is basically These are your filters。 This is your input image。 And this are the outputs。Of。

Cvolving these filters with this image。So the whole bunch of different outputs and because it's a pyramids。

 now， some images are smaller， Some images are bigger。

 but other than that is basically the same as we talked about before， okay。那。😡。

Now we are ready for the algorithm。 The algorithm is beautifully simple。 This is。

 this is a just gorgeous paper， okay。😊，Step number one。为。Have。We have our input image。

 our input texture。Okay。And our goal。Is to。Create more of this texture。

So what we're going to be doing is we're going to start。With。White noise image。

 What is a white noise image， Basically， you go。At every pixel。

 and you just pick a random number and you basically put that random number in that pixel。

 And then you go to the next pixel and take another random number。Okay。

 so basically really completely random image。你该。So， our output image。

We initialize it as a noise image。没开。And now， what we want to do is we want to convince this noise image。

To become an image of this texture。O。Now， remember， we don't want it to be exactly the same。

 We don't want them to match pixel by pixel。 In fact， they。

 they cannot be matched because this one is bigger and this one is smaller。 So， you know。

 that's not even possible。But what we want is we want to somehow figure out。What statistics。

We can extract from this image。That if we impose the same statistics on this noise image。

 it will have nothing left to do but to become an image of that texture。Remember， youlish。

 she was talking about。If we have， if we have two images that are matching their first and second order statistics。

 then humans cannot tell them apart。 They， they see that those are images from the same texture。

 Remember that。So this is kind of like turning this around and say， okay。Let's match the statistics。

Such that hopefully， when everything is done， this image will not be distinguishable from this image。

They will both be images from the same texture。Questions。So， farly good。O。So how would do we do it。

So first， we are basically going to convolve each image。With our filter bank of our， you know。

 oriented featuress， V1 filters。And this is， this is the output of our input texture。

And this is the output of our noise image。应该。Nothingth fancy so far。嗯该。Step 2。Remember。

 in the very beginning。And you talked about histogram equalization。Right。

 what is histogrammic global。Could somebody tell me。呀。

So what should an equalized histogram look like。Ft， right。

Do you guys remember what histogram matching is。Very related concept。Anyone。呀。关。Exactly。

 you just steal a histogram from one image and you say。

 I wanted my other image to have the same histogram。Okay， well。

That's basically what they're doing here。 What they're doing is that they remember we had these images。

These are。Images that are basically outputs of our convolutions。Right。

Something between like negative one or one or something， right。

But we can still think of them as images。We can think of them as images。

 and we can compute histograms of those of these feature maps as if they were images。

 Nothing prevents us from doing them。Here are the histograms。Right。And now。

 what we are going to be doing。Is were going to match。The histograms of the noise image。

With the corresponding histograms of the。Of the input texture image。So we are basically going to say。

This histogram here。I'm going to reshape it。To be more like the histogram of the input。Okay。

 I'm going to move around the image values such that。Afterwards。

 this histogram is going to be as close as possible to this histogram。

And I'm going to do it for every single channel。Every single channel。

 including actually the the input original input image as well， okay。So basically。

 the features here that they're thinking are。Could have the valuable features。

 the important features to preserve。Our histograms。Of filter outputs。你该。So far so good。So。We come。

 we convol the two images。Into this set of。3月份。channelsnel。

We match the histograms from the input image to the output image。Also， notice， because。

Because histograms are， they don't care about the size of the image， right。

 It doesn't matter that this image is smaller and that image is bigger because the histogram is fixed size。

 The histogram is， what's， what's the size， What's the size of the histogram。In an image。0 to to 55。

 exactly。 So， you know， I mean， this was was between negative1 and one， But， you know。

 you scale it to something that is actually an image and and yeah， 0 to 55。

 So it doesn't matter what the size of the image is， okay。你该。😡，So far good。Now。

These are the changed altered statistics。But we need to push them back into， you know。

 combine them back into the original limit。Well。Luckily。This steerwell pyramid。

Has the same property as a lapplian pyramid that we studied before。They're very related， actually。

In that， you can collapse the pyramid。To get back the original image。So， the next step。

Is you collapse the pyramid。And get back to them the， the original input image。

 And look what happened。Now the noise image。Is no longer white noise。Now。

 the noise image has a lot of the structure。As the input image。你该。And now you just do it a few times。

Few iterations， I think，5 to 10 iterations。 So you take it again。You convo it with your filter bank。

 You， push it into your pyramid。 Again， you match the statistics， collapse。And repeat。

 rinse and repeat。Until。Basically， what you're forcing is you're forcing these histograms of filter outputs between those two images to be as close as you can get them to be。

And。😡，Kind of very cool result of this and kind of making， you know， Eish happy， hopefully。

 is that indeed， when you do that。😊，These two images start to resemble each other。 I mean。

 they are different images， but they are images that look like they were drawn from us the same direction。

So in sense， he was right in in in this， in this idea of his。 Okay， you basically， you。

 you force some statistics to be the same。And then even though the， you know。

 they are actually different images， they look to us to be the same。你该。Questions。Yes。No， no， no。

 it's just the full， full image。Histogram matching。Is。Basically。

 very similar to histogrammaticization。 It's a little bit more complicated， but。

You should be able to derive it， for example， on a midterm， if you were to ask to be derived。

Hes to get matching。 It's， it's not that hot。It just， there， yeah， you don't look at the patches。

 It just， it just。At this point， all， you know， it's basically just just the histogram And you're basically just making sure that。

Your， your your different brightnesses in your image correspond to that particular。 I mean。

 think about it。 It's like instead of the historyt being flat。

 now the histogram is going to be like this。 whatever， whatever you want it， you you know。

 you can convince it to be that。 So it's， it's a transformation。

 It's a transformation of your pixel values into other pixel values。Based on。

Some cumulative distribution function， yeah。你可呀。Right， so remember the Laplaceian termm。

Remember how we were able to collapse the laplastian pyramid。Right， we just， in a sense， just add。

Add this， add the level different levels of the plastic pymid together。 And boom。

 we get that original image。Yes。In fact， that's what we did for， for， for， for the stitching， right。

Now， of course， if you just， if you expand the pyramid and then directly collapse it。

 you get back the original thing because there is nothing lost， right， But if youre， for example。

 if you're doing stitching。You expand into the pyramid。 You do the stitching。Then， you collapse。

And you get something different because right， Because this the within the different bends of the pyramid。

 things have changed。And the， the procedure of collapse。

 it's kind of you can think of it as like negotiating between the different frequencies of the signal。

 something that will make them most happy to be in the same image。 right， So you basically。

 you make the image。What they called overcomplete。 So the pyramid is larger than their original image。

Then you do some mummbo jumbo with the values of the pyramid。 Then you collapse it。

 And now the collapsing is kind of like a compression。 It's like， okay。

 you have done some weird stuff with me。Right， now I need to somehow negotiate it back into one image。

 which means that like， I need to have a make sure that。

Things are agreeing with each other because it's kind of a compression。So。

This is basically the same thing as happening with a lapplaceian pyramid with a steer pyramid。

 Its just that the steerable pyramid， instead of like a lapplaceian filter。

 there is just a whole bunch of different oriented filters。

 So you can think that it's basically collapsing things along different orientations。

So it's like different frequencies and different orientations。 So the lapplian， theable pyramid is。

 is kind of like a lapplian pyramid with， with orientation sensitivity， also added it。

So it's even more overcomplete。Right， because a single image。

A single image now is represented as all of this stuff。But in a sense。

 it's very similar process where you just basically collapse it back， boom， boom。

 boom when you get their rich knowledge。Okay， and if you play around with it， like。Histgram。You know。

 matching， then when you collapse it， it's going to be a different image， right。

 It's going to be a different image trying to basically make all of those changes consistent with each other。

And that's basically what's。What's doing this magic。

It's this collapse when you have all these statistics。And I said， okay， now I need to find an image。

Find a projection of all of the statistics onto an image。That will be， you know， most。Most agreeable。

Does that make sense。Questions。Yesし。证明だ。喂 so。Even if you could make all the histograms match exactly。

 which it's not。Doesn't quite happen this way， right， it somehow， you always， you know。

 if you have like。A bunch of pixels that have the same value。You cannot make them like， for example。

 even like a histogramization， if you ever ran histogram equalization code in， in， in Python。

You will see that the， the resulting histogram is not completely flat。Because like。

 let's say you have a， you have。200 pixels that have the same value。You know，27。Right。

Then it's going to have a bump because like historicalization cannot split pixels that have the same value。

 They all have to go to the same bin。Right， so it's never going to be exactly the same。

But even if it was exactly the same， remember， when the collapsing happens。

There is some negotiations going being be that happens， right。

 So because the collapsing is like a compression， you expand it， and then you can track。

So that compression will actually upset some of the statistics。 So then after that， when you expand。

 the histograms are not going to be matching again。So it's a an iterative procedure， because of that。

It's kind of this， you know， expand collapse， expand collapse， expand， expand collapse。 In a sense。

 it's not unlike， you know， what happens with a neural network where you， you know。

 you kind of send your information to a whole bunch of。You know。

 filters and they compute all the stuff。 And then you do。You know， then you collapse it using。Using。

 you know， in the next layer and stuff like this， right， So it's， it's kind of a same， same idea。你该。

Let's see some results。啊， yeahno， first。What。One way to think about it。Is。

You have your data in image space。😡，Okay， so this is your input image。

And what you're trying to do is you're trying to have a set of parameters。

That somehow control the most important things about this texture。In this case， it's basically just。

Histograms of this filter out。你该。So， now。When you start with a noise image。Its parameters。

TheIts histograms of filter outs are going to be somewhere far away from， from that gun。

And basically， the argument what， we're trying to make here is that if I can somehow bring these statistics to be the same as the statistics of their real image。

Good things are going to happen。 So if I can just push this there。What it will do is it will project。

This random noise image。On to。Let's call it an image manifold。

 a set of images that all represent this particular texture， right。

 It's not going to be the same image， Of course， because remember this this， this model space。

 this model is usually much， much smaller。Than the actual image， The image is big。

 Your histograms of filter output whichs are going to be much， much smaller， right， It's a really。

 it's， it's a very compressed。Prametric representation， okay。

So there is no way that if you match those statistics， you will get the same image。

Which is actually a good thing because you don't want the same image。

 You want a different image drawn from the same distribution。And the， the hope is that。

By pushing this statistics over there， you will push this noise image to somehow project onto this image manifold。

 right， So this are this， there's a manifold of images that have the same model response。

 So every every image along this。😡，You know， high dimensional curve。Has the same model。

 This has the same parameters。Okay， and so what we are doing is we are basically just projecting this guy boom to here。

And as we said， because you， you know， it's。It's not an exact thing。 It's an interview process。

 It's not that you're gonna project it in one step。 You're going gonna。And then eventually。

 hopefully you'll get， you'll get there。Yes。Everyone happy。Time for results。All right。

 here are some results。Kind of ugly。嗯嗯。Can we， can we show turn some of the。Front lights off。Yeah。

 much better。 Look at this。 This is 19801995。Most of you haven't even been born yet。 This is。

 this is quite good。 You know， look at this。Input output， input output。's， that's pretty good。

 right for， for how stupid it is。 All he's doing is just taking some random piece of noise。

And forcing the histograms to be the same。Right， it is a very， very simple。

 That's why I love this paper When I first read。 It's such a beautifully simple paper。😊，And it just。

 it just works。Some more examples。Look at this。's， it's been getting like shading and， and shadows。

Now， you know， there are limitations， so。那。😡，Doesn't work on everything。

 It doesn't really work on very structured things。 So， for example， this coral just just doesn't。

Doesn't work， okay。Any questions。有。啊，在结婚。It doesn大代。那个还。That's right。But his statement is not random。

 It's just it averages， it averages them all， yes。快啲。 remember， again， it's not random pixels。

We are talking here about statistics。 So say histograms this is statistical， too。

Just like a histogram of your upcoming exam。You cannot use it to decode how everyone has done。

But it gives you valuable statistical information， right。

It gives you kind of a sense of how well the class is doing。 So the same thing here。

A histogram of an image。Gives you an overall sense of how many bright things there are。

 how many dark things there are。 And remember here， we are doing it， not just a histogram on pixels。

Whi is basically just how many red， how many blue， how many dark， how many black。

 but we're also doing it on the histogram of these oriented filters。

 which basically is going to tell you how many horizontal bars there are。

 how many vertical bars there are， right。😡，So it basically， remember。

 when we talked about it's kind of。G guessssing which texture is which by looking at the histogram。

 It's the same idea。 The histogram of a texture gives you actually quite a lot of information about what's in there。

在。Yeah。Cool， okay， so now maybe somebody could explain to me with this new found knowledge。

Why is this a failure， Why is it not be able to do the quarrel。有。Like that you described。

Youre essentially it's。6为你他 many。But it doesn't know the vertical line needs to be next to the horizontal。

Exactly， remember when Eish was having his conjecture about how the statistics that need to be preserved for people to think that it's the sameject。

 he said first and second order statistics。 Well， here this histogram is just the first order of statistic。

 It's how， how many vertical bars are there in this image in general。

We haven't talked about second order statistics。The relationship between， you know。

 a vertical bar and a horizontal bar， for example。Okay， well， that's exactly what。

Simantelli and Parttilla did a few years after。Which they said， okay， let's。

Let's basically add secondary statistics as well， not just first order statistics。O。And indeed。

You know， well， so their statistics were， again， they had， I mean， in this case， it was a wavelelet。

 but it's basically the same kind of pyramidal structure。 And then they said。

 we're not just going to look at the statistics of all the。

 all the different histograms of all the images， but we're also looking going to look at pairs of。

Bearers of image。 bears of。Locationations and compute statistics of those， as well。And， indeed。The。

The results now here you you read them top to bottom。

 The is the results on on structure textures became much， much better。可。

So you can see thats it's definitely much improved。But there was a big butt。This thing。

Just like Hger and Bergen was such a beautifully simple optimization。 You just， you know。

 expand things into a pyramid， match histograms， collapse and rinse and repeat。😊，You know。

 any high school student can do it。This partil in Chimanelli was a horribly complicated。High。

 you know， optimization thing，6000 parameters all had to be optimized at the same time。 Really。

 really complicated。Took a long time。Half the time didn't converge。 It was just a nightmare。So。

Basically， while it was。Everybody agreed。 Okay， this is the right way to do this。

 And this is kind of。You know， you should be proud of us。

Nobody actually did it because it was just so painful， so hot。你该。And this is where。We fast forward。

To 2050。20 years later。Convolutionional neural networks。Showed up on the scene。

And these folks from Germany， Leon Gdis and colleagues。They thought， you know。

 maybe we should kind of。Think back。2。Higre and Begen， Parttilla and Simonimmanelli。

 and see if we can read try。Their ideas。But now。Maybe we have a better set of representations。

 better set of features， better set of texts than we had before。Remember before the features were。

 you know， oriented filters。Now。We can just。Take our convolutional neural network。

And that could be our feature， right。It's basically it's not just one level of oriented filters。

 It's a whole bunch of levels， right， So it's not just filters just doing oriented， you know， edges。

 But it could go all the way up to something， you know， something more sophisticated。 In fact。

 what they is， they just took。Took a network from like imagenet。

 like pre took an image preed network and used the features in that image network network。

As the representation。 So now basically， we take instead of just。Filterters overient edges。

 We take a whole image network network and use the features in that network。As our statistics。

Does that make sense。OK。How do we use those features as statistics。 Okay， same story。

What we want to do now is we want to。Have a representation of our image。

 And then we take a noise image。 and we want to push the representation of the noise image。Towards。

Theyre original， and hopefully it will do the projection。 So the same story， except now our model。

Is not histograms of， of filled oriented edges， But our model now is some sort of a statistics of our CNN features。

But whats statistics？Okay。So。What， what can we do。Well。Let's look again at our， you know。

 standard Alexnet。RightSo this is an input image。 These are the different level layers。You know。

 at the first convolution level level。We have。You know， large images。

And how many filters are there are 64 filters， right。After a bullying。You know。

 they're half the size， and they're still 64。Poull 2， there is 1，28， pool 3，2，56， and pool 4 is 5，12。

 okay。So these are basically all of the。All of the features that we have。Okay。

 now we need some way to somehow aggregate them to， to compute statistics over them， right， because。

Altogether， this is basically defines an image。 if I take all of these images。😡。

All of these features， I can invert them。 And I'm just gonna get back their original image。

 That's not， that's not good。 We want our model to be somehow compact， compressed。And so。

 what they proposed。For a texture feature。Is what's called the Graham matrixx。😡，So what they did。

Is they basically take all the features。啊。Of all of the levels， okay。And they basically make a。

A this kind of a product matrix out of this。Where at every。

I guess it's it's an inner product  critic， right at every， at every entering entrance。

 every place in this matrix is a dot product。Between。A pair of features。

So this is exactly the second order statistics。 Well， first and second order statistics。

 where we are basically kind of。Be doing a dot product。Between all of our features。嗯该。Okay。

 this is basically what the grand matrix is defined as。那自己翻一看吧问。A better representation here。 Okay。

 so。You get a grand matrix for every resolution， okay。

And it's basically the gram matrix is across your channels。Okay。

 so the gram matrix for the lowest level is going to be the smallest because there' is only 64 channels。

 So it's basically 64 by 64， right， You basically， you dot product all of the。

 all of the features with each other。你该。And it's the biggest at the core at the courseser level。

 because there is 5，12 to 5，12。呃，架格。你可。Question。😡，Is the spatial information。

Contained in this gram matrix representation， or is it been。Removed。Like what is up and what is down。

 what's left and what's right。Is it in there or not。有。That is true。 That is true， but it's very。

 very indirectly because the features。You see， you take this like all the spatial information is this。

 right？ And what you're doing is you're taking。All of this guy， like， what is， what is like the the。

 the1，1 position of this matrix。You take all of this one guy。Or1，2。

 And you don't do a do product with the second fill， the second channel。So you take this。

 you multiply it by that。😡，Dot product。 What's the result of a dot product。It's a scalar， one number。

 So you take all of this。All of this spatial information。Get one number out of it。 Bo。

 You put it right here， right。So， so it's actually， it's a huge amount of compression。 And， in fact。

 it's not。 it's， it's very much inspired by Higgar and Bergen's histogram， right， because remember。

 histogram is also。It's a type of operation that gets rid of all the spatial stuff。 right。

 Histogram is just statistics of， of， of， of of， of， of pixel brightnesses。 Here。

 it's kind of the same come， the same deal。Getting rid of all of their。Sppatial stuff。

 and just getting。Statistics of， of， of how the different channels interact with each other。应该。

Questions。I happy。O。就那我。Comes the other cool thing。Which actually made them。Able to。

 to optimize this story。Because they realized they could just use gradient descent。As optimize。

They didn't have to do some complicated， you know， global opt member jumbo。 They just said， okay。

 we can use the same gradient descent。Here is our input image。为。We take， we compute gra matrix。

At every， at every level of our， of our CNN features。Now we have the same story。

 We have the random noise image。We can also。Compute。It's gram matrix， right。We're applying the same。

 you know， pre traineded CNN network there， okay。And now， what we want to do。Is now we can have。

We can have a loss。 We can have an optimization。 An optimization basically says。

Could you please make the gram matrix for this noise image。

To be as close as possible as the gram matrix of the input image。Right。

 reminds me of of the Higriin burger， this same kind of motivation， right。Just basically。

 make this thing。As close as possible。Well， and because it's it's， it's back prop。

The way to make these as close as possible is to， you know， fiddle around with the pixels。

To make the pixels such that the gra matrix statistics are going to be closes。

 So it's kind of like higher level histogram。Maagic。😡，You're saying， okay， I need to somehow change。

Well， these are pixels。 These are just features of CNN。

 but I need to make those features such that those gram matrix match。And then， after that。I say。

 okay， well， to make these features match， I need to make these features match to make these。

 I need to make these。 And then finally， actually， I need to go back all the way to the pixels to make sure that the pixels。

😊，Get me the features that get me the gram matrixes that are going to be matching。And so。

 we are going to。Try to push this image。To be more and more statistically gram matrix statistics similar to the input image。

And from that。You get something like that。Very cool， very simple trick。Questions。No。

 the loft is on all of them。The losses， yeah， there is， yeah， it's， it's on。

 it's trying to match all of them， all the levels together。

 But the losses is only in the gra matrices。 It's only in the statistics。So it's basically。

 it's free to do whatever it wants to do with an input image。As long as the statistics are， the see。

Other questions。Yes。3次。えじ。Well， but that's the thing， right。

 that's exactly what we want to generate textures。Right。

 and the whole thing for texture is that it texture doesn't， you know， you don't want。

 you don't care。 So， in fact， it， it gives it freedom to just do whatever it wants to do as long as the statistics are the same。

 The same as the Higgin burger。You don't want the locations。

 Loations force you to be copying from the real image。

 We want actually something that is not the real image。

 but is in this with the same statistics as the real image， which is exactly what what's happening。😡。

O。So far so good。Okay， so here are。Here are the results。And when they talk about it， they。

They tried the， they asked the the， the audience to guess which one was the real image and which one was the synthetic one to show that。

 you know。You are often。Can get it wrong， although I think I can get it right。

 So these are the the actual answers。 So this， you know， this is， this。

 this is reasonable textureious in results。Not bad。 I still think that， you know。

 my non parametric method is better。 I think it's still better。 But that's not the point。

Because this paper， is actually synthesisesis paper。Nobody noticed。 Nobody paid attention。

Flew under the wire。Okay， except I noticed because what。

 what was very cool about it is that it kind of showed。That。😡。

If when you're doing imagenet recognition。The network is actually doing less than what you think。

 because what， what， what they did is they say， look。Take an image。Use this method to computer。AA。

 you know texture synthesize a different image。And the network doesn't care。

It still thinks it's a dog。Okay， so it's basically， it's like， it's not really doing that much。

 It's basically still doing text recognition。It's not doing。 It's not doing figure ground。

 It's not actually detecting the dog。 It's just looking for a dog like texture。

 So I think that was actually a very cool result that they showed。😊，Okay， but still。

 nobody cared until this paper。Okay， and this is the paper that even you were probably old enough to remember。

 Yes， do you remember this paper。But this paper is a tiny， tiny little dealt on the previous paper。

 watch。Okay， so this is the image。 and you can make it into what style is this。Startry night。

 What about this。Picasso， yeah， a little bit cubist。 What about this。screamam。 You have muk。This one。

 I don't know。 could be anything。 I guess Turner。And this is like， I don't know， some。

 some earlier Russian Fiinsky。Okay， okay， so what do they do， What do they do is。It's the same idea。

They take。A piece of， you know， a painting， a style thing。And they represented using a grand matrix。

You know， you can。Do texture synthesis。 You can sample from that gram matrix and get。

 get some other image that doesn't quite look like a star night， But that's not what they do。

 Instead， they say， okay。I have my style image， and then I have my content image。

 which is lovely view of， of Ting and I'm sorry that the resolution is crappy。And the idea is。

We're going to combine。Sppatial features from the content image。

With the grand features from the style image。Together in their single image。

How are we going to do it。Trivial吧。We are going to take the same thing we did before。O。

We have our style image here。We are going to have。The， the， the content image here。

 this is going to be the， the our， you know， noise image that we're going evolve into。

 into what we want to be。And what we are saying here is， it says。Before we said， okay。

 this image needs to have the gram matrixes need to match this image。Now。

 we're just adding a one more constraint， which says， oh。And the spatial features。

And in some level of the， of the， of the feature pyramid need to be similar to the features of this image。

我开。So， basically， you're saying。Match these guys。 match the， match the gra matrices。

 match the match the， you know， the low level statistics， the the or the， you know， the。

 the texture statistics。And。Actuallyctua， match the features here。Now， this， these。

 these two things are， of course， kind of conflicting。Right， this is pulling you one way。

 This is pulling you another way。 Well， so you have some sort of alpha and you basically trade off how much it needs to be in this style and how much it needs to be in this content。

And blah， blah， blah， blah， blah， the same sort of back prop。Da， you get something like this。你该。So。

Here is kind of what happens if you can have different weights of the。

 of the of the of the content and the style。 if you have too much style and it basically like the texture synthesis。

 if you have too much content， it's basically very close to the to the original。 But again。

 look at this。 It's made up。Of little bits and pieces from the style image。 So like。

It's still that the gram matrix is still pulling you towards having the。

 the little bits and pieces be in this time。Okay， now which level do you use for the。For the content。

 Well， you can use different ones。 So here the argument is that。

The lower levels will preserve more of the content and the higher levels will allow more of a artistic。

Artistic change。 So here is。Here is the window。 And then if it's， if it's the second compf level。

 it's basically just a little bit of color change。 And if it's the fourth one， it's actually。

 you can see that it's kind of moving things around， which is kind of cool。😊，你可以。嗯那你跟。

Play around with the different styles。This is really cool。 Look at this。Pretty neat， right。Right。

 it's basically kind of the gram matrix have captured the， the， the oil， the oil stroke style。

 And then you're just forcing it to have the same content。你可以。Questions。Yeses。Oh， it doesn't。

 It doesn't preserve the long lines。The long lines， they come from the。The long lines come from the。

 from the content， content image。I see， the long lines are in there。Well， if you remember。

The texture synthesis results。They were actually not that great。Right。

 so do they have a brick wall here。 Yeah， look at this。

So here it's actually not really doing it that well。So it's not actually doing that well for， for。

 for exactly these things。 But for texture transfer， it doesn't matter because in texture transfer。

 the the content image provides the driver that provides the content for you。

 So you don't need to really worry about long lines。 But good question。Other questions。O。没有。

If second。So you don't train。 The model is a pretrain model。 The model is， is just like Alexnet。

 like imagenets models。Doesn't really matter what model。So you don't actually train the model。

 You just back prop。At， at inference time。You back prop to get to， to the resulting image， right？

 and your back prop by basically saying。These are the concept。

 I want the gram matrices to be matched。And I want one of the con levels to be matched。

So it's basically， there are two matchings。 You're matching the kind of the texture on one side and the content on the other side。

 And you're just。Getting the black prop to。To find you some happy， sad， happy medium， okay。Okay。

 so now while we are here， I can tell you one more kind of。

One more thing to kind of complete the picture。That we talked about Gs。

 We talked about conditional Gs， but there is also unconditional Gs， which is。Also。

 actually not that different， which is basically， you start with a random noise image。

And you basically try to generate。Bunch of things from that random noise image。Like dogs。

 for example， by having a generator， okay。The generator is basically producing some fake images。

What fake images it doesn't know。 The only， the only。

And the only supervision it gets is from the discriminator。

And the discriminator is basically comparing whatever the generator generated with。

 with the training set。 And the training set is， you know， a bunch of dogs。Right。So here。

 you could also think of that as being a very similar thing where the discriminator。

Is learning features。That basically tell a dog from a nondo or a realistic image。

 from a non realisticistic image。And then it's telling the generator because the generator actually never sees any real images in its life。

 It never seen the。 It starts with a random noise image。 all it see。

 All it hears about is what the discriminator told it。And so basically。

 the discriminator is persuading the generator。2。To somehow。Match the statistics。

Of the training sets such that the discriminator will say， okay。

 I don't see a difference because all the statistics that I thought were important。

The generator has produced。So even Gs are actually a very similar story。Of matching statistics。你该。

So far so good。So， again， we have this story。Of。Having。An image。And that we are trying to。

Projected into the sum。Model space。And then you try to stay have a。A random image。And where。

Trying to get the representation of the random image to be close to their original image。

 And that projects the random image onto the manifold of， of real images， okay。Well。

 with this in mind。We are finally ready for diffusion。Okay， which is actually not that。

 not that different。From what we have been talking。About already。Okay。

 so last lecture we talked about。啊。Part T and。Basically。

 using the language model to make pictures by， you know， turning。

 turning pixels as essentially words。Right， so we have a language model。

We add some pixel inside of words， and then we have something that generates images。So today。

 we' are going to talk about。The other direction。You have an image generator。

And then you steer it about with some language。Okay。

 but the image generator is going to be not that different from what we have already been talking about。

唔该。So， you know， how do you generate 100 images where you said， okay。

 the simplest thing is to basically just generate one white noise just like on your TV， right。

Just every pixel is random。 So that's very easy。Okay。

 but what if you want to have hundred images of raspberries。Well， that's much harder， right。So。

 this is easy。This is hard。So far so good， okay。Because。You know， convincing。

Convincing a random noise image。To become raspberries。Is not an easy fit。 Now。

 we have talked about this in the context of texture。But here， this is not just texture。 Okay。

 the raspberries have some texture in them。 But， you know。

 there is also the shape of the raspberries， these long range connections。

 There's all this stuff that that actually is not texture， right。

 So this nice separation into like gram matrix and not gram matrix is， is not going to work anymore。

唔该。So。Even though going this way is hard。Guess what's easy。Going the other way out。How easy is it。

And， somebody tell me an algorithm to go from there to there。Yeses。

just keep adding noise until the noise just overwhelms the signal。Like this。哦。答案 easy是 busyO。😡，我。

The cool thing。About。About diffusion。Is。That it allows you to reverse this process。你开。So。

The at training time。What we're going to do is we're just going to take a whole bunch of training images。

And just noise them up。More and more and more noise until they get completely random， okay。And now。

What we want to do。Is we want to dennoise this noise image。And you have seen， you know。

 we have a polarization network。 We have upseling network。 You can imagine that there is also。

 and there are actually denoising networks。 In fact， you know。

 my pixel phone has a denoising network in there。 right， You take a noisy image。

 like you take it in the dark。 There is a bunch of noise。

 And it basically like image to image translation kind of network that basically removes the noise。

 right。And my images， my pixel images look much better， okay。And you train it on basically。

 a whole bunch of。Image， real images and images with noises， right， That's easy。Okay。

 but all of those denoisising networks， you know， they assume have just a little bit of noise。 like。

 they don't work like we're complete things like this， right。But。😡，The cool thing about diffusion。

Is that。If you just。Try denoing things a little bit。And then you take whatever that。

Intermediate thing was。 And then。I play denoing again。

 and then I play denoing again and denoing again。Magically， in the end， you end up with。A real image。

Now， it doesn。 It's not going be the input image。 It's not going to be any given image because it just there's too much noise。

 but it's going to be an image。 It's going to be on the manifold。Of natural images。 It's kind of。

 again， we're like projecting。We're projecting our random image。On the manifold。Of real images。

Using this kind of iterative procedure， okay。So basically， all that's happening here。Is it just you。

 you have a little bit of a dennoisr and you apply it。You know， one step at a time。To the。To the。

 to the noise image and you get something。 and you apply it。You know。

 you can train it on a different image。And you can apply it again， and you can do it again。

 and you could do it again。 And then you basically have a whole bunch of。train data。

On how to go from noise to raspberrys。And， of course。This， this model is basically just。

Just a network， the diffusion network。 is's basically essentially the noiseiser with a unit， not。

 not， not different from what you guys already know， right。And you just， basically。Train it。不尔。

For all sorts of images。 So for this image。You basically say， okay， you， you know。The noiseis， okay。

 you need to go this way。Then you apply it again and it says， okay， now you have to go this way。

And you have to go this way， right， Basically， you just chain out the you chain your denoisers。

And then， the end。You get a raberry image。你该。So。K of对。The， the， the， the， the， the the denoiser。

Somehow inside of here， there contains these。This statistics。

 the sufficient statistics that know what raspberry images look like。Or the statistics about。

 you know， the distribution of raspberry images。And you just apply them1， you know， one step。

One small step at a time。And magically， you get。You get a good image。It's。

 it's still kind of amazing to me that why it actually works。I， I can't really give you。

Any more intuition about why it actually works。 But it， it does。O。😊，Questions。有。被个楼。Yeah。

 so what you do is， is。Is you actually， usually， you add up new noise。 So you， you know。

 the new noiser pushes you to get to some kind of a deno damage。But it's not going to be very good。

But it's it， but on the other hand， there isn't really any noise there anymore。

 So what you do is you， you add in some noise before you do it at the next step。 So it is， again。

 kind of this iterative thing where you， where you kind of okay， Let's， let's do it again。

 Let's do it again。 Let's do it again。So if every step。

 you actually add in a little bit of noise so that every step is a property noiser。有。You。Yeah单。No。

 no， no， you actually for training， you actually， you do it， you do it for exact same pair。Yeah。

 yeah。 So you basically， you， you have a clear between a raspberry and a particular noise image。

 So you're training for the spare of raspberry noise image。 Yeah。

 there is no discriminator because if you have a discriminator， you might as well do again。So like。

 this is a replacement to gas。Right， because the discriminators are complicated。 Yeah，That。

 I don't know。 This is you， you can。Luckiily， now there is a actually open source model called stable diffusion。

You can， you can check it out yourself and play with it and see。I think not that many。 I think。

Maybe on the order of 10。T， yeah， I don't know， but。Question。有。No no， they don't compare to anything。

At。At， at， at， at inference time。It's like， it's like， you know， you， you， you。

 you cross your fingers and you just dennos。 you know， you just， you just go， right。

 That's the whole thing。 you're sampling。You don't know。 You don't have a at inference。

 You don't have a ta。 You don't have a goal。 You're just saying， okay。

 I want some raspberries and just boom。 Let's just， let's just go get some raspberries and just。

 let's see where those vectors lead me。Because at training time， we remember， we have。

We have a whole bunch of these trajectories。Sorry， yeah， see， these are all raspberry trajectories。

Right。So it's basically， it has learned。Which way to go towards raspberies？Right， so。

It has seen a whole bunch of random images that ended up being raspberries， because， well。

You start with the raspberries。 You turn them into random images。 And now you， you go back。

 It's kind of a cycle， right。So you have a whole bunch of these things。 And really， look。

 a lot of neural networks is really just interpolation。 So you can think of it as interpolation。

 You have a lot of these training trajectories。 And now you're going to be at new， you know。

 a new time at test time， you have a new random image。 You haven't seen it before。

But it's going to be maybe close to some of the things you have seen before。

 And so you're basically going to interpolate。 And somehow you're going to get to。

Some reasonable spot。Does that make sense。All right。Okay， so that's good for raspberries。不不不不不不。Okay。

 but what if we want。You know， what if we want apples。Also， whatever we want peaches。

 whatever we want mangoes。Now， we could have a separate。

Separate denoiser network for every category that we care about。 that's possible。

But turns out you can do a simpler thing。You can have the same denoiser。And you just condition it。

On the class。Right， and so it said， okay。The noer， I'm looking for an apple now。 Give me。

 give me the noisings that will push me toward an apple。Or give me a mango。

 And it will give you a different push， push you in a different direction to get your mangoes。应该。那。

If you want something a little bit more sophisticated， for example， Raspberry beret。

 Raspberry beret is not a beret made of raspberries。 It's， it's a type of beret with。

 which is like raspberry collar， okay。So， to know that。You know， you actually need。Lguage model。

 So we are back to our yes， last last lecture where it's kind of we have a long language model which tells us。

 oh， Raspberry beret is a type of clothing， not a food。O。And so then we can basically just use that。

When we are training， we have a whole bunch of images。 The images have a whole bunch of captions。

And we are going to be training them。With those captions。

And so now our denoiser can basically figure out given a caption which way to go。Okay。And。

There we go。 Here are some raspberry beres。You can also do berets of raspberries。Just for fun。 And。

 you know， it's actually， you know。It's not bad， right。And so， you know。

 you can do have a lot of fun。 Remember Steve's guacamole pancakes。😊。

Not quite the same as what he did。 but， you know， it kind of。Legiit。Squirrl the side of a nutshell。

Basically， a lot of cool stuff you can do， okay。So。So this is， this is part T。

 basically language model with a little bit of pixels。Imgen is what does the other way around。

 diffusion。With a little bit of language or with basically steering， steering， steered by language。

Andli， Dali too， which is actually historically， was the first one to， to， to be published。

It's basically a combination between those two， okay。So。Basically， you know。

 when part T is just generating。Generating， you know， visual words that， that shape like an image。

Dalli represents an image as a， as a feature vector。And the feature victory is strain with。

 with a word model with， with with a clip model， okay。So basically。

 every image is represented by some high dimensional vector that contains。The image and the text as。

 within one vector。And the cool thing that。If you have such a vector。You can sample nearby vectors。

And you can get something that is kind of in the same style， but different。Right， so basically。

 like doing like a random walk around the vector will get you things that are actually。

Reasonably close。你开。Here is another example。Redoing the classic paintings。

And you can see that there are some bugs。嗯嘿。😊，And， you know， sometimes the。

 the latte art is not quite。Not quite what you want。And sometimes， you know， the guacamole pancakes。

 you know。The guacam is， the color of the guacamole goes to the nose。But it does do oops。

 It does do some really amazing things sometimes， right。😊，Whi is， which is。

 which is quite amazing okay。And here is some， some local。

 local artist Daniel Baskin has been playing around with Dallly and。Like， she's， you know。

 imagining what would。You know， they， they were planning to send the bart on the all the Golden Gate Bridge into Mar County and then the Marine County like voted it town。

 But she was like， imagineative Bart was going on Golden Gate Bridge。

 that that's what it looked like。 And it's kind of really impressive。 The compositionality， right。

 It knows what a train is。 It knows what the Golden Gate Bridges。

 And it's able to find to combine them together in a way that， you know， that looks reasonable。😊，你看。

I've been playing with it myself。 And， and to me， the most interesting thing is actually not the text。

But the whole feeling that it's able to do。 Okay， so here is a hole。 And I say， okay。

Man holding a heavy box。Okay， so I had to filter blur the images because at that point。

 open air didn't allow faces。 But， but it's， it's， it's quite impressive。 And look。

 it created my hand。 Can you turn off the lights。It created in my hand that wasn't actually in the original。

 right， and。You know， it's not bad。 It's not bad。 This one is really， really impressive。

 Look at this。It's， it created my hand。But it also created my sleeve of， of。

 of my shirt that wasn't an original。 And the sleeve of the shirt has a similar texture as the actual shirt。

And then， look， it has layers。 You have the hand on top of the scarf， which is on top of the laptop。

Right， so， and a lot of these things are not textual things。

 The text is really kind of secondary here。 it's actually getting a lot of this。Of this。

Higher level statistics， really， they're capturing statistics of what should go with what。

Birthday cake。 Look at this。 It's like， I'm holding it up。 It's， it's， it's quite amazing。

Look at this。 There is， there's shading here。 Look at the shading and the shadow。 Okay。

 they have whatever 6 fingers that， but， but it's， it's quite impressive。

 The amount of things it gets right。So here I have women's hands。

But that's not too surprising because， you know， I'm， I'm very fair。 I'm actually albino。

 And so this is like a very low， low chance that this would be a male。

 but it actually happens more with female。 So its okay， with this kind of fair skin。 You know。

 you probably woman。 So put some painted things。 No， it's， again， remember， it's， it's。

 it's basically computing statistics。 And it's enforcing statistics。 And it says， okay， fair skin。

 nails， high correlation。 right， That's what it's doing。嗯。And some things are really amazing。This is。

 this is， this is quite something， right， Like imagine。

 and this risk kind of brings us to the point that。You know， people say， oh， Dolly is amazing， right。

 or Iogen is amazing。 And notice， like all of his Doli part Iogen and a whole bunch of other things。

😊，You know， the， the way they， they do this is all very different。

Like the the algorithms are all very different。 What is in common between all of these methods。

 though， Who can tell me。Huge amount of data。Unbelievable amount of data， like 600 million images。O。

It's， it's really about the data because like， how can you get this to work， Because basically。

 the only way to get this to work is probably there is a few images。

Of people holding their self portraits。And then it basically has figured out the statistics。

 the correlations of。When you're holding up， you know。

 when it says self origin and you're holding up something。

 it's probably the pixels here should correlate with the pixels up there。Right， it's totally just。

 just， just。You know。Counting statistics， it's basically just glorified histograms over a whole bunch of statistics。

Fed on a truly ginormous amount of data。And sometimes， it totally doesn't work。And sometimes。

 it's being funny。Mh。But， but the， the language part actually is。If I say so， you know。

 it's actually the weakest part of that whole process。 So again， I think a lot of people say， oh。

 it's all about the language。 The language is what made this word， not really。

 languageguage is actually kind of sucky。Like， for example， here， you can see that， okay。

A man with red scarf and green beret boarding an Amtrak train。Which in the beginning， it's like。

 oh yeah， it's pretty good， right， But why is it not so good。It's， it's a red scarf。

 but it's a greenberry， not a redberry。 And instead， it's like。There is a lot of green。

 but the beret is usually red。 And frankly， this is not an amtrak train。

 This is like a French string。And if I just basically do a bag of words。You know。

 you get basically similar results。 So it's not really that the。

 the language part is really doing so much， you know， N LP。And it doesn't really know how to count。

Not really。那主咧。Compositionality sometimes works。 But I think usually it works when you have。

 you're composing an object with a C。 But if you're composing two objects。Not really working。

You know。I wanted。I wanted to have， you know that that the boticelli sculpture。 And instead。

 it was basically this， right。Or the， you know， the Musa didn't really work out。And when I really。

 really wanted it not to do something it。We wentnda ahead and did it。Right， so。

 so I think the the the。You know。I think that kind of the， the， the。My feeling is that it's really。

 it's looking for a lot of correlations。 And in a lot of data， there is a lot of correlations。

But it's still， I think it's closer to texture synthesis than it is to like object synthesis。

 What I mean， look at this。 So this is Luxembourg Palace in Paris with triangular windows。 Okay。

 well， this was maybe a little bit of a tall order。 I mean， regular windows I I never seen。

 but notice what it did。 It's， it's so the word triangular。And says， you know。Let me push up the。

 the， the， the triangular texture feature whenever I see。 And so， look at this。Tangle， triangle。

 triangle， triangle。 You know， there is a lot of triangles here。

Compared to if I wanted the round windows， for I say circle windows。The triangles are all gone。Yes。

 it does have like one circular or window， maybe another ones。

 but it also just made everything circular。 Everything is， is smooth and nice and curvy。

 So I think it's really doing something that is very much close to texture。😊。

It's looking at some features。Visual features。 And it sees how those visual features correlate。With。

 with， with words。And that's really how it looks。So it's basically just doing a lot of correlations。

Of， of， of， of， of from lots and lots of data。And if you didn't believe me， I talked to the the。

 the first author of Dalhi。 and he said， yeah， you know， we。You don't need a text really。

 It's the whole filling at least still works。 I mean， it's text as nice if you want to。You know。

 if you want to。If you want to prompt it， but， but for fulfillfilling， it doesn't need okay。

Questions。😡，No questions。Yeah one question。