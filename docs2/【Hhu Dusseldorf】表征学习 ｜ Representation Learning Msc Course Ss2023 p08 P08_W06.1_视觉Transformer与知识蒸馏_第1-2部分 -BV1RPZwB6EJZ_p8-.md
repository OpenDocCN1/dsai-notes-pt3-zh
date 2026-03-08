# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p08 P08_W06.1_视觉Transformer与知识蒸馏_第1-2部分 -BV1RPZwB6EJZ_p8-

はい。All right。They will be talking about。Two main topics。The first one is vision transformers。

 and the other is knowledge distillation。诶。As we discussed in the。

In the group that we will not cover。We will not spend one lecture just focusing on the transformers again。

 but I sent you a couple of links。To read through。嗯。So let's start from the vision transformer。

 what do we mean by vision transformer？Yeah。We have any month。With two spatial dimensions。

 high widths。占就是预水率。Free channels。But the transformer， as we received from。🤧Natural language。

Of or whatever application， What is they put in the output of the transform like a。要带个 data啊啲。

Except what is like the expected say， if you just have a transformer encoder。In natural language， or。

In any application。Any ideas？G help。呃。So， we have。都嘅。Which is basically the elements of the sequence。

Okay， also the bad size of。We will not pay attention。 We will ignore it from now， everything is。

In depend， everything has happened for any image on the bat in the same way。

And we have these de modeled。Dimvention。And then based on the heads， these demos。

Please for its head for the computation。In。一。Attention has we health。Diffically， the model。

Divide by the number of。系い。嗯。Okay， and here we have。

A holy muds with two dimensions and three channels。诶。No。诶。So this question， how to fix。They must。

 in a transformer， took。The whole learning community， something like three years to figure it out。

Even though the answer is really。诶。Intuitive once you know the answer。

So the simplest case would be to take its。Pixel independently。So the three values and treat it as a。

As是到。However。诶。This would result in an enormous amount。Ofトけ。And。

If you can recall the self attention operation。If you have。It's say。Let's use another M。

The sequence length， so if you have M elements of the sequence or M tokens。

 the computational complexity is M squared。So it's impossible with the hardware to process。

He speaks it independently。As a sequence。嗯。So the idea。Is to take to consider non overlapping。Bsses。

So we take the thoughts。This is typically 14 or 16， even animals of 224。

So let's say in the simplest case， 60。And we take 16 by 16 classes。点该电啲市民。こ all。华为荣叉S机。Yeah。

 so basically see the RB values in the。In a essential and natural limits are correlatedlate。

 so you don't want to separate them as distinct torkens。诶。

So if we have these dimensions of hive width。And three Chinas。How many do will it result？Any idea。

So let's say the pot size is divisible with the le size， there's no。Fing here。Any ideas？Here we have。

So in the。呃。Wes dimension， we have。We's divided by part size。B by font size。So， this would result。所为。

呢摆使。So these are this is we use the letter。诶。And the elements。Of the sequence。

So basically end here is the same。As here， so we have。As many tokens as the。

High times weights divided by path size square is not clear we take this non overlapping patch again。

Okay， so we found。The answer to M， So let's say what is the model now？Yes，Do you。

I want to out of the three channels。Time。Yes， so basically this is。诶 sixteen。Times 16。

 so part size time part size times。3。So this would become a vector， if you like。

Whichs basically answers to the following question that。Let's say the， not the model yet。Is P square。

大。し。给见人。16 by 16 by3 in general Peacequa by sea。So this is still。A lot。So if you do this sification。

 this is 256 times three， like 700。I the dimension of patch。Sorry。

 so D is just the dimension of a single patch Yeah。

 so let's say we just take these non overlaping patch and then we just plot everything。So basically。

 this dimension is still two maths for a model。So， we have another。Let's say parameterometer or。

A layer to reduce these dimensions to whatever size we want。

 so for so far we just control with the pad size who will discuss the role of the pad size for different locations and transformers。

But with' still another way to control exactly the input。😊，So let's say if this is 760， something。

 whatever， and I just want to use like a small dimension， like 256。

What is the answer you just take a linear layer， so basically you take these non overlapping patches。

In morning too easily you just。Fla you treat them as a vector and you just。

Applying a linear layer on top。So then。You have this projection that's saying， yes。

 are we using local information there？Because we take this normal。Up to this step。

 it's exactly the same information。So the way you choose those using， yes， with a linear layer。

 but it's like a train of linear weight matrix。So let's say you kind of。Learn。This projection。

 but yeah in the Army municipalization， of course， you lose some information。

So basically from D to D model， it's just a linear layer that controls this。Inion。And then basically。

 its token is a projected parts of all these non overlapping passes。So the question is。Have we seen？

Something like this before。And the answer is。呃Yes。So basically， if you think about it。

This is the whole process， but once you have Token Time D model。

 then it's just a transformer you just add positional encoding， positional embeddings。

 and you pass them in the self attention layers。🤧呃。So， the question is。Have we seen this pattern of。

Pot season and then projection。Does it remind you of？Any other。Module we have seen。Okay， I will help。

 I know it's not intuitive at the beginning， but it will get。superup intuitiveitive。So， basically。

Let's ask the different question， what is the difference between these operation I just described。

 so non overlapping patches class a linear layer versus a convolutional layer。Over as not yet。

Here but here the M&P， so the linear layer， whatever， so the linear layer。Will process。

All these boxes yes。呃，声。think the version by all information goes into a single operation。

That just the。不申请。系系。我ごいます。Yeah， but this is also through the wholely match， it does got。Okay。

 basically， this qua size is really similar to the kernel in a convolution。

 So the the fundamental and then we have like。This linear layer。Basically， the output signs。诶。

So the difference here， it can be yes。安で。张系。没是。When we do this。

 we don't think these the number of chance。不さ。で的。TheThe output channelss。Yeahre kind of。

 so the answer is。那 it's。You can just apply a convolution operation。

 It's just that the difference is that basically here the path are not overlapping while usually residents have like。

Overlping parties。So if you， if you just write in p or you know con2 d and then path size is equals 16 and then try equals 16。

 it's exactly the same operation。 So this is kind of。Very similar to。A convolutional later。

So basically for path size， its strip， it's a convolutional layer。

 you can implement it as a con layer。嗯。Okay， but that again。When you compared to。This。诶。多 games。

Which is high times width divided by Pasi Square， it's just a transformer encoder。Yeah。

 and of course， you need the similar to bed， you need this classification talkingken。So basically。

 I haven't talked about the output， but they put in the output of the transformer is the same。

So the output is always to ends。I'm demoed。But you have one downstream task。

So you usually add just one more token that refers it's like a trainable。

You know vector and then refers to the output of widths we will use for classification yes。

Use linear near layer to reduce。Yes， the linear layer reduces from。D to the model。But then you。

 afterwards， you can just add one more token with dimension D model afterwards。y我。我0。是不这。

Because you lose information is what the other students said， instead of just losing information。

 you kind of learn this trainable projection， which is basically a convolutional layer with non overlapping passes。

Any other question？All right。Yeah， and then。You just take the output of the。Classification talking。

 And then you can run the。And MLP， like two linear layers because they're non linear activation and then。

Project to your classes So you have like 10 classes，100 classes， whatever。

So the first question is what is the role of pot size？Can somebody have some initial idea how size？

Indicate so first， let's consider the complexity。So， M。

Like the sequence length determines the complexity here。So you see that if we。Have the pad size。

🤧The complexity is。Is increased。It not just increases increase to the square。

 so if we use like half of the bad size， we have four times more computational complexity。

So it's a really sensitive parameter regarding the hardware， the available resources that you have。

🤧ok。So， the transformer learns some。cororrelations， at least the self attention layer。

 some correlations between the tokens， and here the tokens are projected patch。

 so basically we control。The degree to weeks， we want to learn different。诶。

Correlations between the patch。What does that mean in practice usually for。

Sematic segmentation or object detection， you really care about more fine grain details between the patch so a small patch size makes more sense。

 so you want to model small。Interactions。Still global interactions， but we。

More fine grain information that can be captured with a small bad size。

 but then you have a lot of complexity。嗯。While learning a specification。

 you't get it's not so sensitive to this path size。不然不是。So you can think of it like。

the part size the term is the number of。Puzzs where you have to combine them。

 so this all to all self attention operation。Combines all these patch together。Smaller butt size。

More complex， puzzle to solar。All right， so they just applied these chains。

So you can either implement this as a comfortably operation。

 or you can use like different libraries too。Do this kind of rearranging of。Prick cells into tokens。

嗯。And then they train this kind of vision transformer on Enet。

And then they want to see what is the correspondence to。The， the land。Feters。

From traditional convolutional neural networks。So they use some visualization techniques。

And the main point is to leadership restrain。This kind of。Corsence， so basically。

We will talk about induct biases in a bit。But let's say visually。

 they look like they learn similar things。So this is a visualization of Alexanderand。

 this is the first neural network in 2000。To beat the aim recognition of talents。

And they identify these kind of。Two streams of information， where they argue that。

The high frequency are the gray scale features。And the lower frequency are the。

But this is still really。Visual， there is no quantitative matter。

 They just want to show some initial。Ors。So next， we' will discuss。We will argue about the。

The comparison versus the convolutionary neural networks regarding their effectiveive fee。

So the main parameter。That increases。That controls basically the receptive feed for n layers is the kernel size。

So here we just have the fat size in the first layer， and then we have all two all。

Interactions that are learned， global interactions。But CNNs， as you can see on label on the right。

So here I just add 24 convolutional layer with the3 by3 kernel。 so you can see that。

The more layers you add， you increase the receptive fifth linearly。🤧And。

Does anybody know I have this question how you can increase the re field in convolutional neural networks have we seen like two or three waves？

For that。Okay， maybe not all in the course Yes increase in color size。诶。Yes。

 increasing the current size。And with the same amount of layers。Also adding more layers。

 obviously you see this。诶。And you can also add this pooling operations because we saw this kind of down samplingling。

Where you just take the average over the feature maps in a small area like two by two or four by four。

So this also increases their acceptive feed。There is another technique， which is called。

Dd convolution， but we will not talk about it just if you want。Think of ways to。

Increase the recipe you in the CM。And on the left， we have the vision transformer trained on。

The same data and for they have like 16 attention layers。

 and for each layer they take just one of the heads and visualize the compute this beam attention distance。

So， they compute。And how many pixels far apart does it see。

 so the main yeast here is that even the very first layers。At to。

Really far away because that is not possible。So if we withdraw draw。诶。So this is the area。

Where it's significantly different from CNNs。This is what they want to emphasize。🤧。Okay。

 now it's time to talk about the inductive bias， with is the inductive bias。

 let's start from a convolutional neural network。Any idea？Yes。😊，I think CNN always assume。来。有佢边。嗯哼。😊。

Local in overwe。圣diment。's timeNo， I just want to emphasize that it's over which of these three dimension。

Over。Yes， whichs basically where the sliding happens， so if you had like a 3D image。

You will have like a third dimension。So this would be the depth， not like the 3D one。

So I just want to emphasize that it's not just for natural images， it's for any type of images。

 so basically any type of。Greed structured data。Where。Pixels or information that is structured。

Nearby on they put data on the grid。Probably。Can be grouped together， can be。

We can map them in the same， let's say， output。And okay， so we have this locality idea。

 something else， do you have to add something。嗯。And as a result。What is the。

The envariance you can learn。From a convolutionary what type of invariance？

You can have a convolution of your network。Yes。😊，比如。如 say。You have to decide。And going。

But I guess it depends on the task， but let's say on the simple way we have a classification。

Should always be。老么。And this thread should always be the same compared to the blue down。

Yeah还是 change没。Yes， what you want say。I say like it's shift in。Like we slide in this direction。Yes。

 safety or translation or sifting。Yeah， this is slightly different from rotating。

To do like a film on the whole limit。So the classic example。第个。So this is the object。

 I will not grow something but。This is the CNN。This is why。Okay something smaller than it。And then。

This is like。Both。Translation in。Basically because we have two decomvolution that the carrier is6 in both dimensions。

直播。Ororiz not and correctly。I will just try to see。对是。safety and this is like map。

In the other example， we have the object here。This is F。This is name咩。This is F。所思。The whole limits。

 so the object moves。And then you apply to CNN。And then， you get。第。And then you get some al Y。

So it's true that it's task dependent， so in general， a CNM by itself fits translation equivariant。

So this sixth will be reflected in the output features， but it will be still there。

So the C by itself is translation equivariant， but if your downstream task is image classification。

All these features will be processed from the same layer， from the same linear layer。 So in the end。

 it becomes。Related to image classification becomes translational invariant。Not everywhere。

W if you want to do segmentation it becomes translation every， so it's also that dependent。🤧。Okay。So。

Does the transformer or the vision transform in era have an inductive bias？Yes。

I'm not sure if the S is not， but。The assumption is now that the information can the patches can also relatelay to each other They are not local next to each other。

 So the maybe there's less impactive bias because that。

You could learn local relationships and also relationships that are further。嗯哼。😊。

So it definitely has an inactive bias， but it's as you said。

 less strong than the convolutional neural networks。So first， since the first layer it's。

Exactly the same as a convolutional layer， it's the initial step。By itself。

 introduces this inductive bias given that the fat size。So it's the bad size deternce。

In which dimension of patches we learn this information。

 but then all the tokens will communicate at each layer， even from the first layer。

 all the tokens so all the partss projection will communicate with each other so in this respect。

🤧It's still。你问。So there are global parts based representation that will be led even from the first layer。

 do we agree on that？Okay。🤧So we discussed about CNNs。So it's gather that this。

Les related to this locality and in general， like email specific inductive biases。

 but there still are。So self attention are。Enable us to learn global， path based。Representations。

🤧However。I want to emphasize on another thing that's not so oftenly scar。Which is。The MFP inside the。

The transformer real。So you have anlkcans。The model。呃，那就好。This movie have。Self attention。

 This is the state global。まデ river。停子。And then。You have an MP。Right。Where you。You process。你惊。

It's talking independently。And the first layer increases this de model dimension。

 and then the second decreases it back to the model。

 so basically the hidden dimension as far as like engineering recall it。

Usually four times higher than this D model， but in the end。So the MP is just like a。Yeah。

 two layers with one hidden dimension。And going。And not in。Yeah。

 there's a lot of research about which is the best nonlinear activation function。

 we don't go into that。But in the end。You increase the dimension。

I think four times and then you reduce back。So in the end， you have the model。原件。

And then you have S connections， layer normal， stuff like we were just focus on the role of MLB。

everybody observed that this operation is global。However， this operation is not。

It love one it's a not one。How can you see that so if you define the linear layer in you specify the in dimension。

 so the model and then the output dimension， let's say the model types four whatever。이边节冇得。

So this all the trip， like the last dimension mentioned。

Is the one that you you will have the matrix communication so all the other dimension。

 So here we just have one， but you can have like here back size， for example。

So this MLLP will be applied independently for each bos and independently for each token。

 so basically you can think that this MLLP is shared between all the different。

Token based representations。So all the talkkens， we see the same M&P。So this operation is。Both local。

 and also。诶。Translation， equi。So， I'll give an example。3。

So these are just three of the top ends with the same D model dimension。

So no matter if I sift those elements。And then apply the MLLP。

It doesn't matter it's still translation equival because then for each。

Input they get the same output。So， for example。而费师。All the details。You know， to。To the one position。

If I do。你 two。3。And then I don't know something blank， whatever。诶。Here we get at2。F 3。You。

So basicallyically， even if I see it。If I translate。The talking representations， some positions。

They will still be the same out because they start the same head。

 that's why they argue in this is the first effort。Hes from the first flavor that applied all the。

Anys war 16 by 16 words， 16 refers to the bad size。

 and this is fair and they argue that these MLP layers are both local。

Since they are talking independent and translation equivalant。Is that clear really？喂 can you食鬼啦，你。さな。

Because this head。So basically if each topping has its own head。Then this stuff wouldn't make sense。

 but they share the same head， it's the same idea that convolutional layers share the same filters。

The same。Wais。So the same weights pass from all the events and here the same weights here。

 the linear layer。Process all the sequence independently was just a new design of the energy itself。

Yeah， it's just that it's not obvious。Also by reading about the transformers or also by reading about vision transformers。

 I just want to emphasize that this is the global operations that learn these path based representations。

 like the correlations。That are global， but net operation is local。

This social can be regarded as another。Reason why we held this layer。

 somebody would argue why you have this layer in the first place in transformer。🤧And。Positional。

Encos or embeddings， it's exactly the same， so basically。For each parts， projected parts you have。

What position。That needs to be learned for these path。

So we still use positional and or embeddedbed even in vision。

Any questions about the inductive biases？At least I hope I gave you some initial。Conceptual idea。

 those dynamics。Other the differences。🤧。So the next part would be no distillation。

 does anybody have a question regarding the vision transformers？Yes。

 so as far as now as one problem on vision transform。In contrast to language。

 the images are scalingating in by two dimensions。And so you need more computational power for user transformers than for。

Like you have patron songs， right。It depends on the。

Basically what the terms is the complex is a sequence length， in language。You can define， like， a。

These models， like， how many。Tokens or war embeddings they want to process in one shot。

 which also determines the complexity of the。So basically in lectureal language， you can restrict。

The number of words in a sentence， so let's say it's like a maximum 120 words。

 and here you control the complexity with this linear layer。

After so the path size and the linear layer， but mostly the linear layer。

 but are you and your able to train them class Yes， yes， you can train them basically。

I don't know if I had pictures somewhere or anything。So basically。

 if you play with the same parameteric number of heads。

 this D model dimension and the number of layers。So it's much more flexible。

Let's say to scale all these three parameters， so you have the number of layers。

 you have this the model。Sos basically the dimension where all the computation is happening。

But thens。And you have the number of heads also you can scale them。

 so if we models you really need more heads and you just scale these parameters and there are some variants that are established with stuff it's called for example。

 vision transformer small， less layers， less heads， less dimension， smaller dimension。

 and then vision transformer base。A bit more heads， a bit more embedding dimension。And then you can。

 and they just create basically they scale these parameters。Together。

And they create different barriers， so everybody uses the same variants and it's easier to compare between。

 for example， pre training object。Okay。So now we talk about knowledge。

 is there anybody who wants a break？ok咁点。So knowledge desillation。

What is the general problem we face in real life so maybe you can train one model that fits all your hardware or your resources？

诶。So in the visual transformer scale， let's say what you have。

The vision transformer the large version， so let's say 16 heads， 16 layers， hidden dimension of 1024。

And then you want to both deploy some model。Both for a large number of users。

 which means infinite needs to be extremely fast。And also with more strict requirements。

 So let's say during inference we can only have。One GB of memory， for example， in a。Okay。

 not a mobile phone， but yeah， a mobile phone has some， sometimes some processors related to。

Kind of a small CPUU for this kind of activities where you have like really limited memory so you cannot use these models。

In this kind of。Computationally restrictive environments like mobile phones or some integrated secrets that can be somewhere inside like a factory from some camera to detect some objects or。

So there's a lot of real life applications that require you to。Either use smaller models。

Its like the simplest case or what we will say in this in。

In parallel wes the perspective of representation learning。

Copy or pass or inject the knowledge from a bigger model to a smaller model。

 so this is called knowledge ftillation。So you want to transfer the model。

Either from one and usually bigger。Or。And sample model we'll talk about that。

 but the idea is you're going to pass all the information to one and typically smaller model。

All right， how do we do that？Okay， first some applications because we will ask about different applications。

 so so far I talk about knowledge disillation with respect to modern compression。

 so this is the example that I explained where you have like this。

Mobile is you with really limited requirements。Another idea is that maybe you have some train weights from selfupvised learning to supervised learning in one domain。

 so let's say some even the weight and you want to。Transfer this knowledgelets。To a model of sex。

Other type of data sources like depth based information。🤧And。The third is a very common technique。

It's called enemble， so an assemble of models， it means it's typically defined in the supervised case。

And it's a very common strategy， for example， in machine learning or deep learning competition。

 so if you have ever used these platforms like Kaggle。

So 99% of the users developed like a simple model。With some convolutions or depends on the Emmas or vision control。

 it doesn't matter， so they have some model， they have some data。

And they train the same model on the same data with 10 different random municipalizations。

So this is what is called and sample of models。So by and， we mean。Exact same model。

 exact same hypo parameter set。Different initialization， and then we aggregate。Basically。

 there results。Like a weighted average of those results for the task。

And this tends to work quite well， so it is like fair。Area about knowledge installation。

 So the idea is that instead of having， for example，10 different models to do inference。

 which requires 10 times the number of inference so if you need one second for one model。

In a real life application that you need 10 seconds， this is maybe too much for some users。

And node like enem node ref fillllation aims at injecting this information from different models in a single model。

Yeah。嗯。So in this case， you have different options like should you use the features？Or the logicits。

 so by logics， you mean we typically mean the output of the classifier network before normalization。

 this is what we call logics。And then should you use the features so from the previous layers。

 so let's say the output of the CLS token of the transformer or the output of the MLP head。

Contrain the obligation。Or should you copy the output after the soft Max where you compare this annualized logicitude to probability distribution？

Or even to。Instead of having this。So a train model will have a distribution。Among all those classes。

うん。SoShould you just take this kind of soft target as an output or should you just use the arc maxs similar to like a one foot distribution？

That you do in。When you have like human out day to day that you just。If this is the glass index9。

In the soft in the cross center， we just post the index 9。

 which is basically one foot distribution where you have 100% probability in class with index 9。

So there are some design choices that are not clear and there are different approaches。

 as we will see in this。🤧咳。So this is the first paper that came out in 2015 from Hinton wondering February in deep learning arena。

So basically， he proposes to combine the cross entropy between prediction and real labels。

So in the softm， before applying the softm， you can divide with some temperature parametermeter。

So you propose a temperature of Juan。Pro basicallyically， no temperature。

When using the real data and then a higher temperature when using the soft targets from a bigger pretrain network。

So the soft targets is basically the output the probabilitying distribution of。

A bigger or in general， a network that has already been trained。

And then you can apply some way between these two lawsuit。So this is a typical way。

 and they also show a this application at least in 2015。But when they just apply this one hot。

 what we call like a hard target， this led to significant overfitting。So so far from 2015。

 we have this inside that soft targets allowed a new model to generalize decently well。诶。

Does anybody know a similar technique？In supervised learning that allows you to create this sort of。

Soft targets， have we discussed that？Yes。😊，Yes， so labor smoothing。

 What does labor smoothing do instead of。Having this。One whole distribution。

Where you say that class9 refers to correspond to the do。It assigns some probabilities of 100。

