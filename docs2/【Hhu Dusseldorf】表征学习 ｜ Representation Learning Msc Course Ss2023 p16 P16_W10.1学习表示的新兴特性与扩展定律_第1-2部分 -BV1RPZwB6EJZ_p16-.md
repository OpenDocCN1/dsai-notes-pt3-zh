# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p16 P16_W10.1学习表示的新兴特性与扩展定律_第1-2部分 -BV1RPZwB6EJZ_p16-

ok。Today we talk about。We'll continue talking about where we were left in the previous lecture。

 so last time I made like a very thorough introduction into the clip of rosese。

Now we will investigate more into the representation so different。Pre training models and objectives。

 but let's start from where we were left off from last time。嗯。So we had this idea of。

Not needing all the time to train ahead on top of some pretraining model with linear probing or fine the whole model。

So now we gather paired data from the web。And train and text and coder on top。So does somebody。

 can somebody explain a bit how this figure works in a very high level， what do we do。

 what is the objective here？诶。Okay， so very briefly， we take one text representation。

 so for each sentence we have a singular representation and then for each image we have a singular representation。

And then， we compute。All the similarities in the mini bagss。

So this square matrix indicates all these ims and text similarities where text similarities is a singular representation for the whole sentence。

And then we do nothing different from contrastive learning。

 so we maximize the similarity between all the diagonal elements。

 and we consider all the non diagonal elements in the mini boxs as negatives。So the main advantage。

Of this method is that it enables us。Pform zero shot。Learning how to say we can。

Given some additional information， which in the case of image classification is just the label names。

We can produce on the fly representations from the text encoder。

So these are produced on the fly for itse as we want to predict its label， even for a single image。

That's why in the literature， you will find these models as open vocabulary models because they are trained on。

On these pair data sets of sentences。And they don't have like a le vocabulary。Like。

They're based models， for example， where they have like a large but still limited vocabulary。

 for example， 30，000 words。To predict during preing。The tricky part we discussed last week was that。

The user， the who is。Trying to predict。For example。

 the classification task needs to design some text prongs and we can see that you can have like a very significant performance boost by tuning the text prongs of the clip model instead of naV providing the class label so for example for satellite images it's better to provide description such as a satellite image of。

Or for。A flower based data set， a description that is like。A flower with a label。

And then label ID or label name would be much more informative for the model。

 and you can see even an average performance boost of 5% without。诶。

Actually find tuning or training any classifier or go。嗯。So these are all really nice。

 but we want to know。What is the main contributing factor to the success and。

both in terms of success。as well as in terms of robustness towards natural distribution shift。

 so we saw that this model is very good at classifying sketches and now we are trying to investigate why these representations。

It enables us like what is the main factor where this originates from？

So there is a follow up work from another group。In 2022。

Where they try to analyze all the different possible factors of success。Those models。

And so you see in terms of training size， data distribution， language supervision at less time。

 or the contrastive loss itself。And the bottom line of this large scale study was that。

The objective itself is not really important， what is important is that you have a very diverse training distribution。

So again， we go back to the。Data， acquisition， curation and collection。

 which they did to construct this 400 million per。 So it doesn't really matter It doesn't really matter if we train with。

Seupvised learning or contrastive learning based on C or。Even supervised learning。

🤧And to illustrate this。They create some smaller scale controlled experiments。So， first。

On the top row， they took all the imageses from Inet， this one million images。

And they mapped them to their original。Caption that can be found online。And at the same time。

 they took the biggest EmATS captioning data set which has this acronym YFCC。So this is。

 by definition， a data set for IAT captioning as a task。And they isolated the。

The label corresponds to the target。So now we have basically。

The image in terms of a single class name， as well as a description and the same for the largest。

E much capturingtion data it would consist of。14 million。Paired data。And again。

 the solid lack of supervision is not the reason of robustness。How do they do that they provide？

Informative plot。Again， how we quantify robustness against naturally distribution。

We take different imagenet。Altered subsets of Enet like these cartoons that Ive sold last time or these natural corruptions or these。

What else。Or these different types of rendering。Or sketches。So these are on the Y axis。

 the four different。Nural distributed success of Enet， so they have the same classes。

 but the data distribution is significantlyly different and the green dots correspond to the email captions。

 so training。On predicting not just the label with supervised learning。

 but as an image captioning approach。And the dotted line is the idea of performance that we never get even with the best model。

Nonetheless， they show。That if you look at both these two approaches。

 so they train these 40 million data set either with a click objective。

As well as purely sinceclLr naive contrastive learning， plus some classification on top。

 so this is what the table is showing you。And。They， they show that。

It doesn't really make a difference， so it's not a matter of the objective。

And it's because of the data。Any questions here？So again， the most important part。Is that。The green。

The green dots are similar to the blue dots， so this is like supervised contrastive learning as we typically do。

 and this is IAT captioning based training with C。So you see they both follow the same trend。

On the x and Y axis， and then the P squares as well as the yellow ones also follow the same trend。

So it doesn't really matter which objective you use or if you use the class names or the whole captions and terms to key。

Any questions？Okay， now we saw that keep。Based like language withmas pretraining is heavily impacted from black data sets。

We want to see what's happening。😔，Large data and models came。

 so if we could somehow go to larger models。We are really likely to have better zero shot imagenet classification performance。

Whatt happened？So these are the different clip vision transformers。

So this is the last one that they trained the bitlar。

These dotted lines indicates us some fine tuning for very few echos on larger he dimensions，s 166。

Just in the last step， I was starting with 336 image sizes。

And we want to see how much can you scale up so effectively。We want to emphasize a lot。

On the connection between representation learning， whether it's language or vision or audio and scaling。

 so how much can we keep on improving the models by scaling out the data sets and the models？

So even more recently， there is a new war。But considered an open source version。

Following the training principles of clay， but an open source。Version of the data that's called Ly。

 which was produced in a slightly different way， so they used one pretrain model and they filter。

Ema is based on similarity。And they even create another subset of 2 billion emATs and text descriptions in English。

And they said， okay， now we have this。To very large。And diverse data sets。It's great from the web。

And let's see what's going to happen， how big models can we train？

And what they found out was first the data。ItUse from the study of the paper。

Hows this accuratecro WID？Is more strongly correlated。呃。と言いますね。

Because of the way that this is generated， so last time I said how they collected queries from Wikipedia and then。

They found images that have this type of text online。While this data itself was produced based on。

On nearest neighbor similarity from a pretrain model。So the data。

 acquisition and curation already impacts the different downstream tasks。

So they argue that this one is more suitable for retrieveval based staff。

 but this one is more suited。Or email classification。

But let's see what's happening in different models and scales。

So the acronym open clip needs open data sets and open weights。

But it's more or less the same contrastive learning objective with。Demon and likely。他 두代理。🤧。

So on the X axis， we see the computational complexity。They don't use flops。

 floating operation per second use。Another magic is' called Mu。嗯。I forgot about the afternoon。

Mean aggregations。Something。And instead of just on the Y axis。We have the imagenet error。

 so by error we mean one minus the accuracy。So it's kind of the same。嚟嗌说。And they try to。

 so these plot are both on log K， both on the Y axis， even though it's not really easy to see。

And as well as the X axis。And they cried。To see if you scale up on compute。And models。

 so larger models and larger computing power。If you can have like。If you have like a linear trend。

 at least on the log log scale， in terms of the zero source performance on inventorynet。

So this type of。Predictions or trends discovering this trend are is called in the literature as power loss。

 whatever I right here， so given see the compute which is。

The complexity for one image multiplied by the images that are seen from the model。

If we can have some estimation of the total zero shot。Eor on on。诶。So， this is got power though。呃。

And we always visualize the log part。Because if you take the lock on both sides here。你脑。So。

 beta and Al to。广三。You can also see them in the plot there they found the vi。

So if you take the log on both sides， you end up with。No。And then。You can。This is just广。

可 you can treat他。And then you can fit a linear line， like a linear line based on the data points。

 but on the。Is there a question？本西。The compute is， they take into account both the computational。

Complexity to process one image。And multiied by the images that the model sees through time。

 so this is something equivalent to the training efforts， is that on really large data sets。

The notion of echos。ItSts to make sense for both practical reasons。So if you have 400 billion data。

For 400 million data， the notion of EO doesn really is not really applied， you can still do it。

 but they do in practice we just sample randomly eat mini bagss。

And they provide some control experience to show that it doesn't really make a difference because it's like。

A huge。Collection of images is a random sample is the same as。

From the whole data set is the same as epoC based training。嗯。

So how many samples the model receives is more or less。

How much we train the model and this is how much compute we need to train the model。

But do you all see the linear trend that is visualized here， so if we fit the linear lines？

Here we have this constant， which are the。This two。A is the data that I have shown here。

So we always use a the log log plots to visualize its strength。

It's easier to see the linear behaviors。And I would like to point out the difference between the two colors。

 so the blue and purple lines。Which looks something like this。More or less。So this is open tea。

Trained online on。And this is。T from opening eye。Fraing on this w I T。も好。明年的。So。

Which behavior is more desirable？So in terms of the slope of this line。What what we would desire。

 like what would we want the models do we want to have like。A flat behavior。

They let's say both are lean， like which behavior would be desire or in terms of the slope， yes。时。

Yes。We want the skipper one because it indicates that we need less。诶 compute， so less。

Computation complexity times sample sync。就就。So by training more， the loss goes down much much faster。

Faster general around with the steepest。And this is where they point out the differences。

 so on the left， we have the image error and the right， we have this robustness。

Cartoons and everything from him as that base。The natural distributed substance。

So the main gift here is that。The data set that was produced from open AI has like a steeper curve。嗯。

Because告最我直在。But see even with the open source， you can get like even larger models。T it for more。诶。

The other difference is that this coefficient indicates the curve。

 that the slope of the curve is more predictable。😊，For the robustness studies， so 0。11 is much。

 much closer to 0。13， so we can easily argue about the robustness solely from the error。

On natural distributed versions of this data。Any questions so far？

We will see a lot of love love plots today， so this is typically referred in the literature as scaling laws。

诶。And this is just a table wearing movie it。Which enables us to identify。So here we scale up。

The model is indicated with a different。So this is the size of the dose。

I'm not really easy to distinguish on the projector， but it's when we see more samples。

And then we have different。Mars of different dataset sets， so because this is really hard to see。

 I want to identify some very key notes based on the table version of this one。So given the smallest。

Vision transformer。The Bay 32。We can already see。诶。by嗰边咧。In the small version of the dataset。

 so we take a subset of 80 million imagess。And then by going column wise， So we start with。

3 billion samples seen by the model。And then we basically train for more and more and more。

 and you can see that from 13 billion samples to 34， you already see the bottleneck。

 so the performance satsurs。W because。The model doesn't have the learning capacity， as we say too。

Give us better performance， even though we scale up the compute。呃。In terms of seeing more samples。

So they即。The main。Conlusion in these scaling laws and studies is that there are some key parameters that need to be scaled up in tandem。

 so simultaneously。And if we scan the rows， you can see that going even with the same iterations。

 going from 400 million samples to 2 billion samples also。

Gives you a saturation in terms of performance。嗯。And you can already see this， even。

With a large version of the vision transform routes has more than 100 million parameters train parameters。

So here you can see that there's these。冇住咧。And a very important point。

Is that using these scaling laws since we fit this line on the log log scale。

 we can make predictions， so this is usually called extrapolation。

And can somebody imagine why this extrapolation， like predicting how the model。

 how a bigger model with more compute will perform？

Can you imagine why this would be helpful in practice？W why。嘅系力为。

a priori prediction of the performance of the larger model with more compute。Why would that help me？

Yes。😊，It's very expensive to train。都是。Yes， so basically。The more we scale out。

 the more the training costs。So if these experiments。Let's say， if this。

Give these special experiments costs。Its the first roll costs some a couple of hundreds of dollars。

This would be on the scale of $100，000。So。You can already imagine both from the exercise classes and stuff how many times we need to tune all these hyperbarameter and everything so itrating on the scale of。

So this model has more than 1 billion parameters。So iterrating on this scale with so much compute and so many parameters becomes really infeible。

Intractable event for very large corporations。So that's why we can。

Do these couple of experiments and predict some behavior of the model on the large scale and then do only one experiment。

So this saves us a lot of。Compute power， which translates to。Saving costs， yes。

It doesn't show up in there。Yes， so the leader trend is when you scale up everything。

 so this is like a more informative version of all the different experiments。嗯。

So you can imagine if this would be the first point。The next point。

 so 3 billion samples with the small model， okay， let's take this one， so from 57 。

55 you scale up both the samples see。And the model， so you from 57， 55， you go here。

So these are like the two points of。You measure this is like a more thorough version of the plot theyre not exactly people and that's right。

So the bottle nexts appear。When you scale all but one， when you fix one dimension。pos机。And。Yes。

 you can see many bottle leg effects that I have identified with these red squares。So how to predict？

为。Do this the socal extrapolation。For different models。

 with D withAs and different types of sample seen。And then we can decide to lung。Those are p mess。

And。Does anybody know what is the limit of this， can somebody imagine what would be the limit of extrapolating？

Like what is the extent of extrapolation？Like how much can we？Predict。In the curve。

There is a small limitation。So the idea is that we want to extrapolate and use this line to predict。

Relatively up。The closer that we are to the existing models。

 the more accurate these extrapolation is。Because it's still a prediction， it' not like。

This power noise will be。系。scale down in large ranges。

 so this would be I can imagine that this would be the most type prediction。

 and this would be the least type prediction。So keep that in mind。Yes。Youre in the back。

We see in relation to。啊，不是把。So。Can you repeat this with the boundary。Extrapolationpolation？For the。

According to use the。You see multidial the。Scaring。Thats right。You can secure the number of samples。

 We can secure the。Yeah， so here we scale up the model， we use this big Z。

So we want to predict this point。So we choose a number of samples。We compute the G Max。

 the computational model complexity， then we multiply with the numbers。😊。

Of samples we want to train the model， so how much we want to train the model。

And then we could predict this point。So this would be。

 okay this is for 3 to 4b on sample seen for the models。

 and then we can predict how better the model we perform in terms of the IATnet or the Inet robustness subset？

When you care how。Incre of the accuracy is。Now， if you scale up in this log pot。

 it follows the linear， so the error goes down， there is one minus accuracy， so accuracy goes out。

Yeah， so error is one minus accuracy， they just reverse the plug can make the same plot with one minus the Y axis。

Yes， what about the other question？I guess the similar is， so once you have this extrapolation？

Do they usually then try and trade the biggest model they can or is how do they decide how far to。そし。

Because like you say， how do you chocolate that。Yes， so it's。

Kind of a trade of where you have to wait。How much compute you have。

 how much you can train the model， how much this will cost you。

 and then you decide on a prereation that is confident enough and it also fits your resource requirements。

So。It's literally really。There are a lot of trailers here to be made and a lot of design choices。

So that's why I want to emphasize on the intuition of those models。

 even though you may not work after attending this course in this case， necessarily。

 you can still apply something similar in a smaller scale。So in a real life application。

 let's say we're somewhere in the beginning of those data points and then you want to。

You have like in a real world example， you are allocated a maximum data set a maximum。

Cost for your experiments from your corporation。And then you， you have to。呃。

Be very considerate and careful and knowledgeable about how much you can experiment。

Any other questions？Okay， and I just want to quickly say that there's a strong connection to natural language processing。

On these sating lows， so a similar behavior can be seen in natural language by controlling these three parameters。

 so data set size。Number of parameters and compute。And long story short。

 you have a similar power load giving you in the log lock scale， giving you this。

This behavior on the test loss。嗯。Another consistent finding from vision and language。第三。

So here it's a bit different scale talking process， so the more we train the model basically。

 it's just that we count， the talking that the model is processing。

 not the numbers of images see that it see。And the Y axis is does the test loss cross centralroppy how much you can predict words。

And the color indicates the more yellow is， the color， the more parameter。The model that。

This is really counterintuitive to what it was believed in the literature in the scientific community the last 10 years。

So everybody believe that a smaller model is more efficient。Because it's easier to train。But in fact。

 the last years， we've found out that larger models tend to be more sample efficient as we say。

 so if you follow the more yellow line， which is the bigger model compared to the blue line。

 so the X axis is what happens during training。So the yellow， the la。The latter models。

Tend to learn faster， so they need less samples to get a lower test error even。From the beginning。

 more or less。TrainingSo this is another finding both consistent in natural language and vision。咩。

And then you can see similar bottlecks。So you have diminishing returns by deviating from this yellow tariff。

When you refuse the number of。Samps on your data。And here you have increasing returns by。

Using smaller models。So long story short。The team based scaling laws that they presented are quite consistent。

Like in line with the。With the corresponding。Findings from natural language processing and pretraining these large scale transformer models。

ItJust a small note in natural language， we have this。Gerative based tasks。

 so these tasks are more like this GT like models， generative free training models which have this decoder which tries to predict。

Not marking the input， just predicting the next。A couple of words for in the sentence。

🤧So let's go back to clip。This is a good indication or example that you can。

kind of play around with this model you can consider those sort of break we're not going to ask this type of questions just for you to see something that everybody can understand。

彼呃。By infu。 So by manipulating like a human， manipulating the das。You can see。

Push the model to make like a very。But prediction and also with very high confidence。

So I was a bit curious about this and I wanted to see somebody。Played a bit more with that。

 so this is just a single blog post， so in just one image So I want to see if。

Other people have experimented some kind of stuff， and this is the next some sort of。

Game that we're going to play。So you should be able to imagine what the keep model will predict on this different scenario。

So we have only two classes， cup and egg。And I we。After you reply。

 I will tell you the answer for the different setups。Okay， let's start with the first one。

Do you who believes it's。say I go back， whatever， number， okay， email's number one。

Raise your hand if you think that the model classifies the image as egg。K12。4 time 6。Okay。

So the rest probability believe that the model classifies da as a cap。😊，So the answer is。

 I can't be but readily than just letting you know the answer， So the answer is egg with the。

P video of a。不是。Number two， so instead of drawing like the character of the word Cup。

We now draw sketch， because。You know， remember all these analysis that tape is very good to natural distribution shift and can recognize cas and all these different cartoon。

So。Who believes。That the model is classifying emails number two as an egg， raise your hand。Okay。

 more people are confident now。The answer is A。Does anybody want to guess if the probability is higher or lower？

老二。Unlike it， the is 93， So it be。So this already indicates that the model is more sensitive to。

Characters inside the image and drawings， but this is just playing around with the model we can really make like a very。

 very general conclusion， it's just to help us understand something。Inverse number 3。

Who believes that the model recognizes an egg， raise your hand？Okay， you're all correct。

So this person played a lot with this speaker of the cup and only when the bottom part of the egg was removed from the imagema。

 then the model was able full basically the model by predict a cup。

You can see their links if you want to see all the different experiences I justterry picked some of them。

不足。So let's make it a bit more challenging， I don't know if you can really see from the projector。

 so this is image number four。This is like start to the damage the。Size is not great the projector。

 but。We still have to decide。So for。Who raise your hand if you think the model classifies this image as an egg？

1，2，3，4，5。You find were correct。So we have a。And actually。

 with a very high probability of 98% compared to the previous prediction。😊。

Which means that the model kind of understands this concept of programe background。To some extent。

 I'm not making any， it's like more of a fun break， it's not like。

General staff will ask you this topic in the exam。So number five。

So here there is a neck on the back of the picture。

 but because of the projector and the screen so it doesn't look so solid。So。

Who raise your hand if you think that the model classifies in symbols as an egg？Okay。

 everybody correct。😊，To cut with 99% of the。O。Number six， this is。And you take。呃。

So it's a combination of number three， just with the cut again next to the side。😊，But， you know。

 you have。As clip， you have two options you have to decide in any case。

 you cannot say it very hard to say it。So raise your hand if you think the model classifies this image as an egg。

And one， two， three， four， five， you guess correct？😊。

It still classified language doesn make with 80%。😊。

Again you can find more samples from this guy online。

 he has a lot of screenshots and a lot of angles， I just picked some of them。

So it's really not clear what does this model learn， what is it sensitive to？

It's really hard to guess in advance。But I think you did a pretty good job actually how of you。😊，滚。哼。

So now we're talk about it more like。Yes。😊，你该是的。It can't say like， it hasn't to。Yeah。

 because you provide two label names all the time。 So he has to assign 100% probability to these two。

 I there any research tomorrow that have a option to say this is hard？And options be answer。Yeah。

 this is the probability。You see， for example， number three， the probability is much， much slower。

 so the model finally becomes less confident， but there is no other quantification yet can other plus。

This is。The one cannot predict。Don't know， in this case。Yes， you can。

 but just that the model hasn't been trained with like。

It always needs to assign the probability that that's a big issue with I mean if you have such a glass bullet。

The crash was that。그게。Probably being my overhead。It's just that。In general。

 all types of pre trainings in neural networks are not really good at deciding that this is like not for me。

 I don't want to decide。This is all the literature about over conflict and predictions because you have to assign this 100% probability one way or another。

诶。So the answer to that is the assignment we are seeing from last time。

 so this anomaly or out of distribution detection， so we want to filter out these images。

Before the model we see them。And it will make like this type of bad predictions。嗯。

Any other questions， I see you like the game？😊，しし。So anyway what？Yeah， yeah， there are more examples。

 you can take it up。😊，诶。So now we are trying to intentionally tune manipulate the images。

 but in an algorithmic way。So we take the cross entropy。Of the test images。

 and we propagate the gradients in the image space of the validation images on Imanet。

 actually in all these data sets。Which are indicating with the red。And。In the end， you can see we。

We almost reach chance level， okay slightly above chance level， so this is。诶。

So the model are like when you algorithmically manipulate the images。The model。Has a very hard time。

 even though this type of。Distribution shifts are not natural because it's not like naturally occurring images in the real world。

 such as this guy I played with the cat and the stickers and everything， or the eye example。So。

 this is like。A very open question is the scientific community whether these type of attacks。

 theyre calledvers attacks， so manipulating the images to fool the network by instead of minimizing crossanroppy to maximize proanroppy。

