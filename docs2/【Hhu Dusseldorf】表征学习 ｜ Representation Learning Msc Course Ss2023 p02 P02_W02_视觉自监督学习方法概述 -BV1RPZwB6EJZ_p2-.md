# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p02 P02_W02_视觉自监督学习方法概述 -BV1RPZwB6EJZ_p2-

All right， let's start。诶。So last week you discussed with Felix with the previous lecture about the connection between deep learning and representation learning。

So， get somebody。Te me what is the connection between these two？Initially looking nonrelay fields。

Like any ideas like why I was saying like deep representation learning。Yes。😊，Be using the models。的。

Yes， because the deep learning and the presidential learning are interconnected。

 even in the supervised case。If you won't optimize for some stuff。You basically。At least some。

Some layers， some initial layers from your model implicitly learned the representation and you don't apply any feature selection。

Anit feature engineering or anything were just。Giving， for example， the text or the images。All right。

So today well take a small review。Throughout the whole timeline regarding visual sub supervisorupvised presentation learning。

 we will mostly talk about。Images， but we also slightly cover videos as well， if in one approaches。呃。

Okay， before we start。In the exercise， you had to implement an autoenr。

 so basically you had the input and then you had to reconstruct the input。诶。

What would be the easiest way to improve the auto encoder as a baseline。

 like how can you improve like from purely imitating input to the output？Any ideas？

What can you add in the input so that it looks more different on the output you can add like noise。

 you know， augments。I just want to see' just want to say we didn't cover this in the exercise。

 but if you would like to improve the auto coder， you could inject some noise in your input data。

Like ocean noise or augmentations。Like intensity transformations。All right。

So the idea of self supervised learning was initially coined the 1990s in a paper from Muni Munich。

And it's。Pretty similar to the way we use the same term today。So selfupervised learning。

Is kind of general terms use the latest years？And its it basically it's a more specific term than an unsupervised learning because we don't have any labels from the data themselves。

Like like as a pairs like X being the input and y the label， we only have the data。

 but we kind of find the hack ways to create labels。And train with the。With an objective。

 as we would do in selfupvised learning， for example， reconstructionconside or cross enroppy。

It does that the label itself is obtained from the data。呃。So here we have the timeline。诶。So。

 last week。You discuss about。You bend your paper， mostly。フix。It was在。

Let's say the introduction of the concept of representational learning and another very important thing happened in 2012。

was kind of。The beginning of deep learning and computer vision， does anybody know？Okay。

 I will have it's the Alex net paper。It was the first large scale。呃， network。All right。双击。

A bit later。So from 2012 to 2016。The only way we would be using visual representation learning was through supervised learning and specifically supervised transfer learning。

So we have a large data set as shown on the slide。We are still operating in the same domain。

 so if we're working with natural images， we're staying on natural images， but we find。

And like larger scale。Dataets， for example， we want to have like a very good classifier for Cypher 10 or Hes and where。

Pre training with supervised learning in a labeled dataset set from the same domain with much more data。

 which is INe。For reference， INe has 1。2 million label data。And it's a。

Usually as far as you can get with。Some small single node with a couple of GPUus， at least in the。

University scale more or less， usually。嗯。So then around 2016， as far as。In parallel。

 there were a lot of papers regarding autoenrs and stuff like that。

 similar to what we seen in the images， but people started to come up with more handcrafted tasks。

 task for pre traininging。Well use the word pretext tasks for this pretext task is the task that the network is trying to solve。

And in the same time， it learns the representation encode their layer。

Encoder or backbone use system knowledge to indicate the initial layers。

Even though the pretex staff might have like one or multiple。MlPs or heads。本当。All right。

 so in the self supervised learning case。Which is more applicable， you still stay in the same domain。

 so let's say fill on the natural imaging domain。But you don't need to have supervised data。

 so if for example， we had dates with 10 million images without labels。

 we could leverage it for selfupervised learning as most of the big companies like Google or Facebook are doing。

So。Any questions regarding the difference between transfer learning and self supervised learning？

Right。嗯。O。So then we have an example。哦。Let's say。These are the training epos。

 and this is the accuracy。The percentage。For N class is classification problem。And we。And we have。

This behavior， if we do， if we directly。Start from around initialization and try to。Basically。

 do the same stuff with cross entropy and supervised training on the。

On the distribution of the task that we want to solve， we call this task， the downstream task。

To distinguish it from the pretext task。So pretext task is what we pretrain。

 so here there is no pretraining， so a network starts from random in civilizationization。

Kind of gets the point。So what would happen in the case of transfer learning？

So if you had some supervised model， how would this curve look like？Any idea？Yeah。

 probably it doesnt start from zero accuracy accuracy to have some。Okay， yeah。

 this is not zero definitely question this is like random guess。Yeah， that's correct。

 you can start broadly from a higher point。And then。Yes。

 the initial part of the the curve might be either。Yes， so what does it mean steeper。

 it makes it train faster， if here we need。100。Thousand declarations。Okay， we did es， so let's say。

200s， is the classifier or if the network， in this case。

 the Bagbo+ level classifier sees all the data one time。So we start from probably a higher point。

And we as importantly read。Much， much faster。The same accuracy and maybe we have some improvements。

Usually we have。Immprovveement， actually。If we are staying in the same domain。

 at least if we are switching for natural images。就。From a large scale。

 lateral images to a smaller scaled basis。So when you say transfer learning， yes。First supervisor。

No there's no pretext task in the beginning， we just do supervised tuning on the endX。

 so if it's Cypher 10， this is directly supervised training on Cypher 10。So， here。No。Ba view。

 let's say around the eastization。那你吃过来的。Yes。And as I said， we probably would have some。

 we will also train much faster， like that could be speaker。

But also we would have some performance gain。And this is how typically things were used to be done until 2016 and 2018。

And sometimes their Steve does。So the problem is that we are still staying in the same domain。So。

 for example。for example， in practice， all these supervised train models have been trained on Imnet。

 which means that for more domain specific application， different domains。Medical imaging， X rays。诶。

What kind of data， microscop images， MRIs， 3D images， which cannot directly leverage those weights。

Even though there are some。Small evidence。来。诶。You can use parts of those layers or parts of those supervised layers。

So round visualization is with blue。The difference here is just where're switching from。诶。

Bret train demon with weights。Too medical imaging。 I think X rays。So indeed。

 we can train faster even if we switch to another domain。But we cannot use all those layers。

 Can somebody speculate if we use like。The first， let's say， three， four layers or the last three。

 four layers from the innocent weights。If you had to choose between using the first。

34 layers versus the last 34 layers of a pretraining rest that which one would you choose Yes those Yes so this paper。

It's about using the first three or four layers。For different components， so rather we've seen a lot。

And in is another type of。呃，共的。嗯。So we can improve the speed and test the accuracy。

 but the test accuracy is marginal， mostly because we are switching to a completely new domain。

 so is' it clear when I say domain what I mean？For example， natural versus microcopy。

So this is a problem。And obviously the solution is visual self supervised learning here I have the official definition。

Pretext task is the terminology we will use throughout this semester。

 so you need to be very comfortable with it。So we designed some predesigned task and the goal is to implicitly。

By solving， by trying to solve this tasks to learn very relative features。

Relative to the downstream task， and this is the second critical point that you need to have all the time into your perspective。

That the downstream task redefs。What is the optimal pretext task？

And what is the simplest possible pre task that we had in the exercise， basically an autoenr？

And yeah， sometimes it works。 I think the exercise of how the。With linear problem。

 you had something like。40%， 4 50%。And the random gets for 10 classes was 10%。

Is it clear about the definition of the pretext from the down through task？So we are in 2016。

Colorization。Can somebody。Formulate the problem in terms of。Like black box。

 you input output what would be the input in the output。How you implement that。你是体二姐。对时间。And truth。

More channels like three channels for。Yes。😊，And what type of network would you use？

We like network or network architecture？Convolution layers but what kind of architecture since the input and the output should have the same size。

저 be like a 내가。收嘅。Okay， well a unit， yes。So basically we want these type of unit networks。

 as you probably suggested。That we have these encoder and decoder blockss and basically the output and the input have the same shape。

Okay， practically speaking， I don't remember if they actually copy the gray scale weight three times。

 they probably do or they feed one channel out of three channels。You can get the idea。

And this one was one of the first ones， but it didn't find many applications later on。嗯。

So another thing， another famous favor is about formulating this jigsaw puzzle where you have en nema。

And with some slight sees you pick。诶9。诶。Nine passes。

 as indicated from the green squares with some slight seedss。And then the network。

Its presented with these s parties and it tries reconstruct to place them in the correct order。

 you can frame it as a classification problem。So the authors from 2016 again。

They said that we are trying to ignore the low level statistics。

What do they mean by low level statistics， what do we mean when we say about low level statistics？

Yes。😊，系算。Pixel information， yes， I personally agree。

 but what would be some example here I give you some hints。就是这样子。From these months to this months。

What is the yeah。Yes， so the core histogram can be regarded as a low level statistic。

And even the texture， so color and texture are this kind of low when you read papers and they write about low level information。

 low level statistics。They mean information such as color and texture。And。

Here you write object localization。 So since youre trying to learn the correct order。

 we are trying to。Enncourage the network to learn some sort of localization。 So what would be the。

The downstream task for this specific pretext task。Any idea。Yes， object this section Yes。

 so for example here。They use object detection as downstream tag。Then we have image in banking。

What we do now。We don't crop， but we feel with。0ero or one or 255。 so we take some pixels。

 they don't need to be as indicated as figure 1 a， they don't need to be。Like a square。

 it can be any random mask。 So we randomly mask out。Some parts of the information of the en。

And we are asking the model， as you can imagine a unit。To， to reconstruct。诶。

This missing information to predict each pixel vibe。So this is again a unit。What would be。

 how would you formulate the objective， what objective would you use？Senior for the exercise。就。

What loss function would you use for this task？You did it last week。Yes。😊，Yeah， M Correro L2 norm。

So I hope that you found out from the exercise。诶。Basically。

 I should be the one who is asking that you can also see it in。Sub image， sub figuregu B。Oh no， C。

 sorry， this L2 minus square root is the same thing。In this purpose。

So what is the problem when you directly try to reconstruct？With L2 and mean square error。

 when you try to reconstruct the pixels。Yes。😊，看唔看。附近有。Los but。Yes。

 so everybody who's using this L1 or L2 losses directly on the。On the big sense。

Usually you have a very blurry output。诶ok。下一个之。Formulate the task。In a more mathematical way。

So let's say we have math where zero indicates the math。一さ。Which results will be dropped at one。

Inviates the un vi。And。We have the same shape as the has8s as a height and W use the weight。

Then we have an encoder。In this case， let's say a unit， a write encoder。And we have the V。

so I don't know you。We haven't talked about this in the di learningity class。

So we introduce a new network， so here it's written as adversarial laws， so this is a discriminator。

 as you would see in the literature of generate adversarial networks。And。We can formulate。The做 loss。

 and the。Reconstruction laws。诶。啦。呃 upper first。So as you suggested。

I will put the blackboard back down。 Just give me a second， right。So the construction low。第。

So this is a single C element wise not called， it's also called HaamA program in the literature。

And for those who are interested in the adversarial literature。And right down。

So he den the expectation。Can you read the characters。So， basically。This is how for famous。诶。

So when you have this type of adversarial losses， when the two networks have different objectives。

Here， I only showing you how you optimize the discriminator。So you would take the the output good。

And from the unit， so they construct with part of the A and you would feed it。In the discriminator。

But you would also think there is an limit。So there is a small trick here if you ever come across this type of networks or implementation。

Has anybody worked with Gs and wants to speculate what is not shown at this moment？

There's a small tree。When you train the discriminator。

You should do what you say as stop gradient or det gradients so don des ins。So， these。

Need to be detailed。So that basically the units should not be updated and the goal of the discriminator is to make ignoranceancies more realistic。

Okay， any questions here？Is it clear？Okay， so I would like to discuss。For a brief moment。

What is the purpose what do we achieve with these two lost terms？

You can also add the hyperparameter to balance。Those two。

But let's say L equal one to make our lives simple， what is the pros and cons for two laws。

 so for the construction laws。We all agreed， and it produces really blurry results。

What does it get right？It gets right the overall structure of the images， as you can see。

Number C here。It gets more or less the global structure or as you may read in the literature is the kind of low level frequencies。

 the low frequencies。And what about the adversarial laws？

It makes the images more realistically looking。Because basically， we're trying to。

Make an impossible for the discriminator dealing between the early months。

X and the generated one of f of。And at an large interpretationplication。Any questions？

So next one is about videos， How do。Formulate and。Predesign how you pre designign a task to learn a meaningful representation of videos all the previous one hardly applicable。

Does anybody have an idea， what did you do in the video， what would you enforce yet？Computing。Yeah。

 frame prediction is one， you give it like a sequence of n frames。

 and you are trying to predict the next one。This would be more closer to this one because then you would have。

 again， their construction laws。So basically， it's kind of image in painting where the image is the whole mask。

 yes。我。反对。Any it is here not possible。I mean， it's just a It is applicable。 It rather it。

Nobody has published something lately。Im in painting on videos。Like even for video prediction。

 there are a couple of literature， in principleol， you could definitely apply this。

Any other ideas apart from predicting the next frames or even interppoolating between two frames。

 this could also formulate the task。嗯。So in 2016， there were already some guide。i仲飞。说秘事。

He proposed this task where you have。So I hope it's clear when I'm talking about videos。

 we have a sequence of frames。嗯。So instead of predicting the next one as indicated。

They propose another task。Where basically they train a binary classifier。

 a convent which has like a binary classification held， and it does predicts。

If we have the original video， the frames that are sampled are consecutive or non consecutive。

So this is a very， very simple task。We are seeing 2016 so don't expect so much。

 even this kind of stuff that you can learn from powerful representation and use it for。嗯。Yeah。

 maybe it's a question， what would be the downstream task for a model that learns which models are？

Are indeed the frames individual are consecutive or non consecutive。

When does this presentation might be useful which type of video based data。啊。Any ideas。Never mind。

 they argued at this representation。Its very helpful for action recognition。

 so when you do an action， it plays a role if。The phrase。I am secretary。

And another think of we show in the paper experimentally theoretically。

 most of the staff in such you provide learning are experimental。😊。

So don't expect too many theoriesorem improve。They argue that the presentations that they learn by aiming to solve the pretext task are complementary compared to。

Supervised learning on email， supervised transfer learning in general。So by supervised here。

 I mean supervised transfer learning。As a prettyt。Any questions regarding how would you how you work with videos？

Even though this is very far from state of the art。2018。嗯。So there is this paper。

That they propose a two step approach in the first they train this kind of unit。

Bas in autocor unit like method。And then in the second step。They try to。

Do this gun geneative percent network dynamics to other discriminator and try to。

To distinguish between the。Oto encoded outputs， they auto encode images versus the real images。

Not so interesting， I'm just showing it for consistency。

This one where you will actually implement the next exercise is very easy and still surprising and works is just if you formulate the task where you take an image and you rotate it with multiples of 90。

 so either 0， 90， 1008 or 270。And basically， you have the four。For classes to classify。

So you have like a small conve， resnet， whatever， plus head。With the soft max and then for glasses。

And this works extremely well， I'm still surprised to this those works， so this was proposeding。2018。

And it has found a tremendous number of applications people are still using this thing。

 that's why you will also implement it into the next exercise。诶。

The principal as argued in this paper。From 2018 is that by learning the rotation。

 you learn more high level features or high level objects， as I'm writing here， heads， noses。

 eyes of the objects， but as well there are relative positions because they are also rotated。嗯。

Any questions regarding rotation prediction？No， I find quite。An easy exercise。

 I hope you would find it。对不。Okay。Then there is this kind of comprehensive experimental studies。

This is a paper from Google AI from Zur。So basically they say， okay。

 we have all these kinds of tasks。收。rotationtation is a rotation prediction from the previous slide。

 and Zigaw is from 2016， the one that I showed I did't present the other ones。

 but they're relatively。Similar。And they say。Let's see what happens across different architectures。

And they find that even between different versions of renets， so we one if V2 are。

I guess some reasons with。A higher number of parameters or slightly different layers。

 and the results are not even consistent。嗯。So all the literature in many， many tasks。

 including selfupvised learning， was developed until。The introduction of vision transformers in 2000。

呃9。啊，第算数ト。So all the literature before the vision transformer was basically publishedist and benchmarkmark for resonanceson and mostly Re 50。

But they found out that it's not even consistent across different pretext style and not even consistent across different architectures。

嗯。And we already know that it's not even consistent across different downstream tasks。

 Its downstream task may have a better。フてきた。嗯。Still。

 we can see that rotation prediction works quite well， except from the green one。

 which is this resite version1。It consistently outperforms the other handcrafted tasks。

 even though it's such a simple approach。O。Then。We define same supervised learning。

 which is the scenario where you have a small number of supervised data and a large number of unsupervised data from the same task and you would likely to integrate those。

诶。Unsupervised data。In your model。And it's called consistency loss。

FromI think it's a paper from Google。嗯。So basically we're trying to find ways to incorporate this information。

We write a bit。Of math， because I don't find the figure extremely helpful。噶。

So fit are the parameters。And we have a supervised objective。什么。拐吗？And we also have。I brother。

And then。按是不 by。郑添。诶。诶。So what is Q。So Q is the data transformation that need to be applied。就。

Let's try x2 so as I want to say that these data and these data are completely different。

Completely different images。So Q is a stoholastic data transformation。

I will use an notation from the paper。So we sample from a stoholastic data transformation。

What is an example for even transformations？But this is the simplest and commonly used example when we're applying on augments or emotional informations。

Y， Congress。Yeah，若是。Yeah， rotation is a good example here， so we saw before that they user the 90100。

 like the multius of 90 rotations as a data transformation， and then they tried to classify。But。

In this case， this unit need to have some some it is to be stohastic， okay。

 but the most important property is that it needs， I don't know if this is helpful。

So basically we want to enforce the consistency between a non augmented emails or non augmented representation of the images and an augmented representation so this is why even though these data are unlabeled and we don't know them。

 this y needs to be the same so basically the label information needs to be retained so that's why for example in these application rotations are not applicable thats for example。

 of course we can apply this。Color changes or cropping。Some particular range。For example。

 if you've got 1%。Probably doesn't make sense， because you lose。The information， but in general。

 all these data sets。This computer， vision， natural imaginging dataset sets are mostly objects。

Single objects placed in the center of the image， that's why。Cropping。

And random cropping of random scale usually works。So be very careful when you think about for each task what augments you need。

 so here let's say cropping and intense transformation。嗯。Okay。I may。

So this is the P of Subscript L is the data set。The La built dataset。C is the cross entropy。

 a common objective we use。So this is more or less stuff we have seen a lot in。

Deep learning in the first semester。Well is you the second。That eat all the time with the。

The expectation。So we have x2 sample from the unlabeled distribution at this。Subscript you。ForUnle。

And we also have。X hot。いう？And we take the x2， and then we apply the stochastic transformation。诶录啦。いた？

就。S would create timeline and work。嗯。So basically， this is an indication of。Dversionence。

So cross between these and these。呃Yes。We prevent that the uned con laws collapsed just。我白是。So。

 the right problem。Could let and always predict the same cost。俾大。

We prevent this using the same model。Yes， we are trained this same model M。诶再起。

But there's another very small indication that I haven't shown in theequ but it's shown here。诶。

There is this Tda here。So this indicates that the parameters。

Of the networks that see the nonaed Ebas are free， so basically there's a stop gradient operation。

呃Here。So this also prevents the network。Experimentally， at least， to collapse。So yeah。

 if you answer the question with Lewis County， nice。诶。So， usually。诶。Okay， let's write first with me。

C central is not symmetric。现在没还。安。And this is the symbol for theanthtropy。嗯。So basically。

 this is the first paper I have read that uses the indication of cross entropy。

 usually when we have two different augmentations。We tend to use scale divergence。

Does somebody know the connection between crosscent between care or divergence？So。

I will continue from here。So basically， cross entropy can be decomposed to decay KL divergence。

 this is the definition you。Wikippedia or whatever， inver like that vis。And this is the second term。

嗯。Which basically the entropy of P1。So when we have。Labels。

 we use this one hook and coating as a target， so P1 in the case of supervised learning are the labels in here。

Wein。诶。The entropy of。The labels， when you have the one foot coding distribution of the labels。诶。

The difference is that here it's slightly different because。Even though we have。

And on one potent coding distribution， the gradients are not flowing。

 so no gradients will be added from this term。If gradients are added。

 we tend to use KN divergence in the literature when we have the output of the network， for example。

One example is no less distillation， so we have a very large model。

And we take its output and make a very small model to mimic the output of the model。

 this is the case where we typically use。K and divergence and not cross entropy。

 so I find it really helpful。So if you read this paper， you can compare it with other papers。

 that's the closing point。嗯。And they write in the paper that this is a way to propagate labor information from labelbeled examples to unlabeled examples。

 this is a more intuitive explanation。Any question about the approach or the month？Alright。

And and then。Where is the tipping point。Which is one very core。

Point of features that we will emphasize in one or two lectures in the upcoming weeks。

 which is contrast with learning。We will only。Breef discuss about it or。For a couple of minutes。

 I just want to show you the math。Yes， I want question last last。O，我直接说了。是比较。Yes。

 so here I replaced F。Its like the model， I think it's regular F。😊，In the。

M is the model in the figure I use the term F， and here I use a different more statistical notation from the paper so I just replaced cross entropy to make it clear it's the same stuff we do on supervised learning。

This is a more。Statistically looking fiction， I don't like it， but I want to stick through the paper。

No。So I will only briefly discuss。On grass learning。AndG tonight we cover。

It extensive in the lecture， and you will also do exercise classes with it。

I just want to show it as the tipping point， so we have from 2016 to 2020 we have all these kind of handcrafted features and the bottom line is that a very simple one that works kind of out of the box for natural images is rotation prediction。

And everything else has some improvement， but it's not working that greatly。And then。

After this objective， it's called since loss or contrastive loss。

There is a totally new field coming up。So going back to the timeline for a brief moment。

So 2020 was a great year for computer vision。So， the fairs。Very big thing。He's a vision transformer。

So even though the transformer was used。In natural language， it was initially proposed。2017。

For natural language translation。And and then here。One year later， we have these there。

Which we cover in the next lecture， which is basically。

How to leverage all these large cor specs who not covers now， it took three years。Or。Finding out。

An established way to make transformers work for vision。And in parallel。We have。

This seems or compress。诶。Where even though the objective itself will write it down the Blackboard。

 it was not something new it existed for one or two years。

This is the paper who studied it at scale and sold all the white works， how to make it work。

And that's why it has a really high quality。So， basically。

All the advancers of 2020 came from these two fundamental papers on 2020。

 and even though in saying 2020 that something is published。

 it takes a lot of time to be adopted widely for all the other community， for example。

 if you work on medical imaging， all the publications and all the literature takes one to two years to see from the advancements from。

gooogle aI face goo aI on natural Li。诶。A very funny moment。

 it's because of these two publications in the middle of 2021 I decided to do my PhD。

And all the things that we will cover。😊，Are deeply connected to vision transformers and S are in the next three lectures。

诶。We cover the state of VR。后来。So we have theze month。

I was also extremely excited when I managed to create these email。So basically， we have a box of。

And images。 So here to make it very simple， I have two images， and for each image we have two views。

And then we compute the similarity。We pass the images from a backbone model， plus a small MLP。

 but it's not so important。So we take all these features and compute the similarity。So in general。

 this similaric matrix。The similar item is x。For two it views times the back size。

 but let's say we have two views。So we have two augment。

 two different stoholastic transformations of the same elements。And we compute this similarity magic。

 which is four by four in this case。And the objective for its one of the green squares。

Which is basically the similarities that we want to maximize。So， basically。If you see here。

 we want to maximize the similarity between Ima Juan V1 and Ima Juan V1。Yes。

 so basically we want to maximize the agreement between two different augmentations from the same event。

And these are also called in the literature as positive pairs。Positive pairs are not necessarily。有。

Created it from the same image， but it can also be。Imaziz。With the same label， let's say cut。诶。

But then it would be kind of supervised because we know the label。

 so we create a pair by picking two cuts and then trying to two different images of cardss and then trying to maximize their similarity or agreement。

 etc cetera。So for its green square， as indicated in the figure。We have these lost。And then。

 of course， we will average。All the losses from。The green squares。In the back。

 so from all the positive wants。But they lost。Looks as follows。

So Z indicates that we are talking about the features and not the images。

 specifically not just the output of the backbone that is indicated as A in the top right figure。

 but Z。There this D is just an MLP。So when nuclear repair to turn with a very high。

Dimenssion in the middle。 hidden dimension。These the temperature。So， temperatures scaled。So么 but。

Let's say this the temperature is just a hyperferroometer。We don't care so much at this point。Okay。

 here we have B。Similarity is the coine similarity。嗯。So， I just want to。呃。

Give you a very short introduction。Because I find a very critical point。

For the research regarding deep representation learning。So basically， this is what we're saying。

 maximizing agreement。The nominator， these are the items that they refer to a positive pair。

So we are only talking about the four green squares。And。This I basically is a mask。

 is a square mask with a shape of S that basically zeros out all the diagonal elements。

So basically these are。All the non diagonal elements of this。Square matrix of similarity。

So the problem is that。AndWithout the denominator， this can collapse。

Just by directlying maximizing the similarity。收。The big advancement of this paper is that it kind of got together all the different components that neededing and started them independently。

 the augmentation， how this G， MLP should look like and many other things。And。Yeah， this I。

 any questions regarding this equation？This love。对。Yeah。

 is it usually done in this like ordinaryary setup。Good just。To views， it's very common。

But size of two， no。two views， but maybe more than two。Basically， it， the bad size。

 if you say like for one bath， we take multiple two views from its sample。Yeah， basically。

 it's actually a very good point because in order for this loss to work。

 it's really sensitive to the bad size， so you need a bad size of at least 512 to make it work。

So this similarity metric。For back size， 52 it's 1024 by 1024， and then you need a lot of resources。

 a lot of GPUs， maybe GPU training。That's why it also comes with during the timeline with the advancements。

With the。Pyth in all these frameworks。All right。Then I would like to argue little bit to discuss a little bit about how much。

Does do this。Supervised， supervised learned features。Transfer。Two different downstream tasks。

And how they compare to different。Dancing tasks and also different pretext tasks。嗯。

So for the sake of this conversation， we will only take a look at the green Star。

 which is a supervised， basically supervised transfer learning， versus let's say the red cross。

 the method itself doesn't matter because it's from the fact things we will cover in the lecture。

 so for all the plot， the X axises the images accuracy， basically the task that is trained on。

The data distribution that they were trained on and then top one accuracy。

 either with fine tuning or linear probing。And the Y axis is basically the performance of four different tasks。

嗯。So。These are like different date in another data set for linear probing and fine tu。

 this is a few shorting， some other data sets and they also have some plots that look kind of similar for object detection。

 somatic segmentation。还三个人。So the bottom line， like the three main things you need to remember。嗯。

I highly argued in the literature that selfupvised land features are more transferable。

 but this paper in 2021 was the first one who kind of showed this in a large scale experimental study。

Second， there is not always a single self supervised method。At least given that we have a specific。

Pre training data set here Yu。我街个。Is the solution or the best possible choice for all the different dancing tasks？

And third， they provide some small analysis that。These features when they train a classifier on the downstream tasks are the classifiers they lead to more calibrated。

And less prone to overfitting on the downstream task。Any questions？And now we go to 2023。

Some of you are really interested to see how far can we boost the performance？So， this is。Latest。

Paper from Google， I think。Released a couple of one or two months ago where they trained a vision transformer with 22 billion per others。

And。If you just see this volume I S stands for internet， its。Just week。Lar proing。

So I hope from the exercise is clear to everybody about this linear program。

 you take the features from the pretrain model and then you train a single linear layer with standard perthroppy on ENe and it seems 89%。

With linear probing， frozen these are the features like backbone is not trained。就。

We will use this idea of linear probing extensively for all the exercises。

 so in this exercise we made implement these ideas。

 but everything we implement once and the next exercise will be given as a functioner。

 you can just call it。So。89 is。Yeah， the things that I have not discussed is that。😊。

This is also pre traineded in a much larger supervised data set that is' not even probably public。

Yes， is this so。Yes， dog gls。Yeah， yeah， it's not be stock one nightrs。

And the good thing is that it's with linear probing。

 so the information exists already in the features。We will talk later on in the course about。

How these。Largescape pretraining results in many。Kind of interesting properties。

That are learned in the features of the transformer。

And how far can we go with such supervised training？So basically。你。あ。Supervise and。す。

AsL starts for NS cell supervisorvis learning， sometimes I do this abbreviation。嗯。

So they trained this gigga version of the visual transformer in 142 million images。And achieve。

Validation accuracy， this linear probing of 86。5 on Li's net。

Kind of similar totally different data sets。Same。Okay， just to summarize。

It didnn't take so much for the lecture。Three main points is that the presentation are dependent。

 highly dependent of the downstream task。And then。Usually。

 at least sometimes most of the times it's also architecture dependent。

 even though with the latest models， maybe everybody is just adopting。The vision transformer。

 will cover it probably later in the course， even though we haven't。I actually talked about it。

 it's not significantly different from the transformer itself we have seen in the deep learning lab。

Second is that。Selfsupervised learning is it is well established at the moment that selfsupervised learning results in really transferable features。

 meaning that we can take these features and apply in another task， even in the different domain。

 not even in the same domain。And it tends to be better than supervised transfer learning because of the scale of the data is much higher than the data we can actually annotate with human annotators and supervised learning also has some noise because there may be。

Multiple objects in the class。So诶 human an will only un updateate one of。嗯。And lastly。

 which is kind of not true for the latest advancements。

As far as the approaches of the visual selfupervisor presentation learning approaches we have discussed in the course in this presentation。

 so far， there is no one that kind of，Domininate and is the best plan across。

Multiple downstreamet tasks， even though the last。Years， it looks like。There is was。All right。

 questions。There are some references， so all the papers that I present have some reference it's at the bottom of the page if you want to take a look at the math and explanation of the figure in the main text。

诶。But this is like a。Some fundamental blog posts and papers that I also use。Yeah。

 that's it for today。