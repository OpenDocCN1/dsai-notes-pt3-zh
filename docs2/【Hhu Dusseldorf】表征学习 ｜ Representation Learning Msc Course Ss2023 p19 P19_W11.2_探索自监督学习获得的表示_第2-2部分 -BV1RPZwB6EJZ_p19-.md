# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p19 P19_W11.2_探索自监督学习获得的表示_第2-2部分 -BV1RPZwB6EJZ_p19-

And these are actually the this is the so called DNA center where you get the gain part of the cell in different channelss。

Capture different。Properties of those。3。And we see， again， that some heads are。For example，就算呃。两人。

Like these sort of foreground mask。所以嗯。It's not just a method that works。😔，On natural images。

 it can work across different domains。All the evidence sponsor to the fact that。This is real。他个。

Are easy to grasp and they point to the fact that the model indeed captures some of the features that we would like to learn for the domain。

 even though we don't have。Any。Lbelbel information。

As in supervised or these clip models that have this text description， even though it can be noisy。

These are some visualizations again from。Our world。So， different colors should。

Fill map together because they correspond to drugs applied to cells。

Different drugss that are applied to cells that have similar effects than we know that in advance。

And we see how this is like a baseline， it's a non deep learning baseline baseline。

And these are two the masterculine order the design approach。And again， we see some。

Very rough Iience， like a low dimensional transaction that was called Yuma。

 it's really similar to TE and PCA。There's not a clear winner between visualization methods I just want to show。

You know， some intuitions and some properties of how these features can be useful as to， for example。

 classifying。Different perturbation or perturbation flame。

 it can be either genetic perturbation or different drugs。Could accelerate， for example， the drag ca。

Frameworks。By lines that we have right now。And this is just another visualization， so this is again。

 the nondelarding baseline line。And here we apply。We just take the features。

 but we apply some theoreticalarchical based classy。Some precomp pretty implemented。ア。

Sa it lab and we。买月你。Classify some。Similarly， looking biological properties。关的。

The baseline do that is kind of。佢拉屎。It's difficult used in the industry。

It's not based on mascuity learning。And it doesn't get the same type of features。

And these are data that the model has not been trained or， so it's kind of fun。

Out of domain because these are like a genetic per。Okay， and last year I would present。

Because right now I have mostly present。And then di on the math encoder。

 so I will now try to present and compare a bit to what two different self supervised methods。

Learn and focus and which one is better for Wi。So I was really interested about this and it's only two weeks ago that I learned that some people were investigating and were interested in the same stuff。

That呃。W you already discovered。Some方一下。So here we take different pretrain models。For example。

 this MophoP3 is the visual of the basis transformer。

 and we saw that even on the same task of auto distribution detection。

 just by switching the in and out distribution，You can get a completely different。今。

Given the same model， given the same pretrain distribution。

 just bytain the objective and given the same task。

 just switching you know the in and out distribution， so we were we are still。

It's an open area of reasons and we are really curious to why， for example。

 this model is the second best model on。These size have 10 and S are 100 as a distribution。

Why here it's one of the worst performing methods。So， there is that。Inddicate that these features。

Are not consistent even across the same task by switching the distribution。🤧。

So now we take a step back。And we would consider。We consider a bit the dynamics。

The objective is basically those models。We either have the standard augment pipeline with。Gs and至堆。

All we have masking， a so called mask， image modelling。Or you must part of the sequence。

 which are the past projections。And then。We try to predict those parties。说的一在。

So the work that I would present which one of the very few ones that exist at the moment。现在我所以。

H do to know that somebody published results on this direction。

 understanding the different such supervised curing models。🤧哎。

So we have two views in the first case of Car。Have the same model。We have the projector。B。

We have this project heard at B。You我 kind of。The I and the day。

And here we take the influence CEO Con Learn objective。And in the case of vision transformers。

 we can take the classification talking of。It goes Vi John Former and gives us。

A presentation for each talking。On the sequence。So typically I these methods to just take the classification talking in。

嚟到直点。The other alternative is this method to their patient on masking， like a mask withr or。

This is just the attending that they consider。So you have。Some sequence。Then you have your model。

As you can see there。And。You apply the loss on the emailAT space。

And you try to reconstruct those passes。I it say these classes。满。Take the A one loss。To共 track。

The八字实系诶。ます。And I gave you like a very small intuition that in because you have a much more reant information that the masking rate is much higher than a。

So one could regard these two types of pre training， so these two objectives。

Even though you self supervised learning， there's no human label on the loop。呃。

We could regard one of those as email level and the other as talking level。Which one corresponds to。

The other， so which one of those approaches correspond to。

Ema level objective and which one corresponds to document level objective， Do you have any idea？

So here since we mask the target。And then we reconstruct the talking this way I'm arguing that。

It is like a talking level objective。So the optimization happens at the talking level。

That's why we need the vision transformer necessary here， but not here。Right here。

The objective happens。Under a presentation of the whole image。

 either it's interested you take the features or it's a transformer and you take the classification talking。

And we saw that with the latest state of the art method based on vision like Dino V2。

 vision combined these two objectives。However， in this study that I would presented they it just only to study these two different pre trainingnic types。

the same data。And go better。嗯。So these are how the learn features look。

 so this is based on contrast learning。And this is based on masss modeling。

 so MIM stands for Mas modeling， which is this approach right here。So。

This is a different visualization of of what we have typically seen they visualize not just。

The CS tokykens obviously one point for its emails， they visualize the different tolkens。

So 196 to for 18 images。These 18 images can have these three different classes。

So we don't want to see， we're not interested to see。How different。

IAT space representations can be visualized and be clustered in the feature space。

 even though in a loaded dimensional。But we want to see how the dos， even from the same demands。

Our this trip we did。In the feature space。And。You see that theres a different trend。More or less。K。

And yeah， as I'm writing here on the left end。😊，The more clearly separable these tokens are distributed。

 the more easy to train a classifier， so with cleaner probing and all this stuff。

 so I think if we had like another visualization with Dno。

 these features would even look even more separate。Prob。Ba。

And now we take a small and we discuss about emails frequencies， so somebody from last week asked me。

What are how can I understand the frequencies？Two dimensional。Readed like a emma。

So I found this very nice visualization。So this is your internal element。This is the first frequency。

So the frequency means that if we can'。The pixel as a signal。

And then we want to see how rapidly or slowly。The pixel is changing。

 but instead of having like a one dimensional signal as you typically do in image processing。

 here we want to see how this pixel values so the intensity of the pixel is changing but not across time across the two different。

Across the two spatial and dimensions。So this is like the first， the second， and the third frequency。

Of those images after doing this for the analysis and then going back to the image space and then visualizing。

So to do this analysis， you take the signal， you go in the。P yeah space。

Where you have like the spectrum。And then you just take a low pass filter and then return back to Amon space。

And this way， one is able to。To see the distinction between the sky and the mountain。

 even from the lower frequencies。That's why I。We discussed about last week about this texture shape bias。

That the lower frequencies。Orrespond to。哎。Morris。More safe based representations。

Why the high frequency here， we have the。I think 50，50% of thems。5%。

The bottomtom 50% of the frequencies of the emails。And国会 to the。The original signal。

 you see that all these fine grain details， I don't know if you can see it from the projector。

 but this is like probably a tree or a。大读书。These fine grain details are missing。

 so these are the high level。呃。The high frequencies。And it's really。Beneicary thing。

image frequencies。Both for the analysis that we will show about centralvis learning。

 but also for generative modeling。So generalative modelly诶。When you want to generate these mud。

They even decouple the problem of。Having like a separate network to predict。

The low frequencies of A while assigning another model to。

To predict all the fine grain or high flavor slope。 So I another model to learn all these。

Findine grain， little details that you need for higher resolution in mat generation。Okay。

 just to see that you are following gets out of the。And tell me given these boxes。

 so it is like box number one and this is box number two。

Which one corresponds to high and low frequencies。Yes。This one， lovely Yeah for， Can you for？你是。公西。

清楚。Yes， signs of pixels are intense， these solid pixels and dens here， more or less homogeneous。

Right。And here you see these rapid big tension between black and white。跟 맞。

It's really nice to think that's why I use this guy use this gray k。😊。

Because black and white is going from zero to 155， so the most rapid sales you can have in eight month。

So here you can see that all these sweeters and changess from white to black are really。

Rapid changes in inities， that way。This is a very typical example of high frequencieses versus low frequency。

So any questions regarding that？收午了。你向见。On on the left。I have the。Different properties。

And we will try to map those properties。To either the contrastive or image based objective。

V is the mask he much modelly objective。So low frequency versus high frequency。Yes。

So low frequency versus high frequencies， there's anybody who wants to guess。What one correspond to。

Contrastly versus mascu model。嗯。Maybe if we go back in the picture。嗯。

So now we want to argue about low and high frequencies。So。You see that the low frequency。I have more。

G they give you more and more。And more an indication of， let's say the same。So face经。Sorry。不存。

Love frequency， okay， let's kind of group together low frequency and save or low frequency。

Sign correspond to say texture， let's go there first。四。Correct。

 so A and D is essentially the same thing。And。To get this safe based。Features。

 you need like a more global context， that's quite this immense level objective of contrastive loss or even with dying off that's happening on the representation of the whole image。

Is high linked to both low frequencies and safe base vi。While on the exact opposite direction。

The high frequency corresponds to the fine grade details or texture。

Can be learned from masked humans modeling。And again， okay， no。

 somebody want to guess about C based on what we discussed this long ranges。Global patterns。

Whi model would you map them。Because we said that yes。Yes， can you。Yes， so the global patterns。

 for the sake， you need the global patterns。So。There is a from some recent World was published in the International Conference of Learning Re Station or ICLR。

 an Excel。原罪。They are of these global patterns。I learned from the contrasted based。Approach。

So we govern from A to B。So this one， okay， this is first condition transformers specifically。嗯。

Does anybody have an idea So what is。Its are you here。一是嗯。So的 query。It's like。

Inside the self attention mechanism， I also need to present someone。A for able to avoid them。

I haven't image in the next slide， you guys on this one。So we want to see all these different。

So let's replace， let's ignore the work query， so how are the tokens？Distributed。So， something like。

没说完了。So wes are more homogeneously distributed as they ride。

So here let say collapse because they argue that different tokens inside payments should have distinct representations。

So in which case， the model is not incentivized to have different representations for the tokenm。

Any ideas。这是。Yes， so F corresponds to contractive laws because there is no talking based objective。

But the tokens have no incentive。To be separate， to have separate representations。

So even if you group together， you can still learn a global representation for the whole event。

While in the master， where you。Reconstruct tokens， it's time。

The tokens cannot collapse into the same representation。嗯。Yeah， and F and Z are kind of related。😊。

Okay， maybe we have already covered but do you remember which of the two。

Appros is better suit for this tense downstream task like sematictic segment， so number。

 so letter aids。Any guesses？No。他是对告你方这。Yes。You have any。Yeah， for semantic segment。

 you need to go to the pixel level local。第个。Okay， so you start to get some initial intuition。

Of this analysis。Okay， it works better for linear probing anybody yes。Yes， correct。If I contrast it。

 even if you use all these image based objectives like Dno and stuff for mass much modeling。

 it doesn't really matter if you use this。The approachs that they presented or the mo and called。And。

说的是病。0呃。Yeah， let's go to the scale a big first。So scalability。

 it means that you can have large models and a lot of data。Yeah， actually。

 these are very hard to guess， so I wouldn help。😊，哎。收。In the deep learning course。

 like when you start to learn about。The地确说 the。我帮过去女 network。You have this very example of。

Somea float。Some different realization。And then。You have this。Every level features。

So what is learned usually the first layers of convolutional neural network。Yeah。

 where if you look at most the。Foration online they tell you how these low level features year the layer。

Which can be like a tech force or similar things。And in the high level。Say layers。

 you have more high level features， so one。国告上面拉噶嘛报咁嘅。On the face and so on。

 okay the illustrations are not the best。没。So the latest layers correspond to higher level features。

 so more complex features。是的意思。Relate to。Later later。

Similar in self supervised learning correspond to this more。That's a global or high level feature。

 which correspond to contrast learning。And Taylorlor。Especially if you consider。

The analysis that we show about Dno and how you go from Dno to Dyno B2 and all these analysis about the centering because you don't have the negatives。

So you have a lot of instabilities。And these possible modes of collapse。か。So capability is。

More closely related to mass Nema model。Any questions？O。

So this is some illustration about theformity。嗯。So again。

 we emphasize that contrastive learning refers to global while massing mass modeling correspond to more local areas。

So this is a contrast based attention map。Or least specific query。

So even though these are like this more save base features。They对按就说。

They are more or less the same throughout the layers。可せ。Why in the case of mass as modeling。

 you have。More localized features。So this's another illustration that I found and all these analysis based on this。

Recently published war。え。Yeah in lot of two years， maybe we'll have more understanding。

They explain things， but。4的是。Have some。Caring understanding and。

So I have talked a lot about this divergence between linear roing and fine unit。

And this seems to be true even for this categorization of mass as modeling versus contrastive learning。

Or Danieliel based member。So you see that when you are on the X axis。

 the more right you are you are better at linear pro。

And the fact that the model is very good at linear probing doesn't mean that it's good when it's fine to different tasks。

So you see that there is this。应该。序。So the mass modeling methods are very good。

 especially when you find human object detection and somatic segmentation。诶。

While these immense level objectives， like cross people di on classical learning with since art。

Are more。Shoot it for linear Pro。So linear problem is more is more。Something you could do in a small。

Data at team， as we say， like。When you have like a few shots。

Data sets or like small data sets that you just need to train a layer on log。

 And this is like for the task that you。fin the whole level it some day。收没协。

This mass mass modeling is more suited for fine tuning and large model printing。And tasks like。

That this localization like so segmentation is。Something where this objective might be beneficial。

And this is the scalability analysis。So I don't know if you remember this mask encode there。

So the main advantages of these method that the main particularly attractive is that the vision transformer discards like the encoder。

 discards all the tokens that are mask。Only the decoder process of tools。

That's why you are able to skate the masking others， even in being skate。发让。And train there。

And so here the exactes are just。They different patient transformers。

Where if you want to switch from the tiny small base last huges。

You just change the embedding dimension， the number of heads。And the number of layers。

 So these are the three parameters we。That we control the complexity of the transformer and we scale them more or less in tandem。

This is a data about object detection。Compared to emails that documentationation sent。

And the last one。It's the same quantification from attention distance， so you want to see。

Even though in theory， you all the pixel cells， all the tokenins on the sequence are allowed to communicate with all the sequence。

There is this magic。We make police measures。How many pieces far away？但是。This specific layer or。

Ken is actually seen and it's aver beef。Between doing呃。He for one layer。你。

The 12 layers of the transformer。And they call this either effective researchurg field or attention results。

The DNA on matter， we just want to show that the mask images modeling。诶还是呃。

It's more localized information because you see。Effectively， you've seen。A much。

 smaller area around you as it's indicated from the attention distance。

Why these are more this contrastive base approach it just more global。

 so these are the results to indicate everything that I presented previously。And that's the end。

I hope you didn't take so much time， thank you so much。

