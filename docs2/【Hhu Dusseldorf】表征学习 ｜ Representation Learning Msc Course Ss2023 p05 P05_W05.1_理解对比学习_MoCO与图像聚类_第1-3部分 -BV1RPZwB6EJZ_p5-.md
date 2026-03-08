# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p05 P05_W05.1_理解对比学习_MoCO与图像聚类_第1-3部分 -BV1RPZwB6EJZ_p5-

Okay， it'。So last time Felix talked about the lower bound and all these proofs about contrastive learning and in the exercise basically how to implement the contrastive learning objective。

But now we'll take a closer look to actually what's happening during this。

Pretext task in contrasted learning， at least for the beginning。呃。So for。

Two views and box of n images。게 개 그런어。诶。We have these sort of similarity matrix。诶。

We want some of those elements in these simulate matrix， which we act as the positive pairs。Again。

 how we take positive pairs in this setup， we take demand and we apply。

The same stoholchastic transformation pipeline to eyes， we get two different augmentations。

 we show that the most important transformations are random crop and then resizing for。

Practical reasons。And also power litteriting， so distorting the statistics。

Of the mean values of the pixels so that the model is not able to have this。Information leak。

 so basically this shortcut learning from just matching the pairs by only matching the color histogram so this is what we saw last week。

So if you read the paper， this seems a loud paper。There is this objective fact and they say that they formulate it as a classification problem。

Okay， it's an the classification plot problem。At least in a super setting。

I know that we have like a network。And then it solve much。And。X。And then。收。

Over the dimension of the different classes。So here we have six classes。

And the distribution looks something like a base。Whatever。So this is before the soft marks。

And after we apply the soft muchs， what happens to these unorized logics like intuitively？

Why we apply soft masks and not just。Convert them， just divide with their sum to make all these values from zero to1。

So we're in the supervised learning setup。We have pair of data， x Y are the labels。

And we have some probability distribution。Basically， we want to convert the logics。

 the output that is un normalizedormalized age here to some probability distribution。

 why do we apply soft mask， Does anybody remember maybe from deep learning？Yes。😊，push。こちは。我すで。

Exactly。So， these。Will have like a much higher probability。 We intensify it。

 we increase their intensity。All然。So let's go back。In the setup of constructive learning。

Since we have a classification problem， we have to see how many classes do we have。

 does anybody know how many classes we have here for this example of four by four metrics？

How many classes do we have to classify among？Yes。😊，Almost， so basically， if you take the role。

 we exclude the diagonal elements。😊，So if you take the row， the first row， so we have hemas 1 U1。

 and the three different columns。This is a positive pair。Way to have。

 This is the positive path and have。Two negative pairs。So basically， the number of classes is three。

 we maximize。This similarity。And the denominator includes the negative pairs。

The soft much is basically where we apply。一s。From one。Two times n n is the bad size。

So the justification program。Another letter here。2 n minus1， these are。The classes of the。

Classification sort like this classification problem。So the politics bear。

Is just a similarity that we want to push together， so there is a connection between the logics。

Here in the supervis set。So basically the similarities。In its role。

 we act as the lawsuits in a supervised classification program。Any questions？Okay。

 it's a bit unintuive to understand that you can think that in each row we have similarities and they act as unormalized logicites where we want to make a classification problem。

So basically， the label here， if this is like。原告一张。你告先周斌。It。Okay， if we use just probability。B。大嘅路。嗯。

Why target。六。Why prediction？So basically the target is here。

Because this loss only shows what happens for a positive pair I， so the target is one。

So the probability be we push probability to one。Of the similarity， which acts as the logic。

 similarly。Like analog to having like a classification problem。

Is this connection established to some extent？All right。So， we have。

Two times the back size mind swam classes。And how many negatives？So since one class。

Acts as the positive we have。Number of negatives，6 times and minus-2。Do you agree with that。

One class should act as the positive where we want to push all the similarities。

So there are some problems here。嗯。So this similar me。Between the I and the Z。

How do we prevent that do you remember？In practice， what do we do。

 how do we measure similarity between two vectors？Yes。😊，所以。奥了吗。

What's the difference between the dog products theine？系。诶。All right。So this similarity here is。

Sim notation indicates that these two vectors before we take the dog product。

 we need to normalize them in some way。So we probably all know that after L2 norm。

As shown in the top right figures。This is an illustration on the three dimensional space。

So it will result in a sphere because all the vectors that live in this sphere have unit in a unit sphere。

We'll have a normal one。Right， so all the vectors that。

Reside in this hypersphere you have like a unit vector。Unit length， sorry。

Do we agree that all of the vectors after e normalization will have like。Unique length， okay。

All right。I want to emphasize to give you some intuition why。

We apply L Nor or any type of normalization in such supervised learning representation。

 learning pretext task， we will see this all the time and it's not properly shown in the different literature。

 papers， publications， whatever。So the idea behind it。Lies in the soft mask。

 so let's take again the supervised example。We have six classes。And we in the beginning。

 the network will assign。An randomly initialized network will assign。Uniformably the predictions。

So this would be like one divided by six， one divided by six。

So like a completely yearlyized network with no impact bias with roughly。Assign these probaities。

Do you agree。All right。So then after a couple of iterations or because of the inductive bias。

 for example， you have convolutional neural networks on natural imageses。

You have a slightly higher probability in the。Let's say in the desired class。

 but it's still very close to the other proities， so we want to intensify this different。But here。

We have similarities， similarities are dog products。And what is the problem with most progress？

So let's say we ignore these term。And we have。Two arbitrarily large do products。

So let's say we have D dimensions， in practice we have 128 dimensions。But we would have 206， 512。

1024， there's nothing。Methodd wise。From theory， from the theory that。

Limits us to use this 128 that we use in crashes。So。嗯。This kind of correlates roughly。

To another module。But the bottom line。Is that if we treat these D dimensions as independent？

Even if they have an expected value， a mean of zero。

So we have 128 dimensions with zero mean and unit variances。诶。You can prove。

 I will not show this now so this in the previous semester that the dot product will still have a mean of zero。

 but its variance， it's really high and if you assume that the variance of the dependent variables is one。

Then the variance of the dot product is D。What does this imply？It implies that this。

Dot product can get arbitarily solve。So以 already。Its。

More subtle than expect it to be because we have similarities and we have top products。

So do you understand we have pairs of dog products。

 So do you understand the difference why we don't apply any normalization or。

Scalating down factor here， why wouldn't we have bears？We need this scaling data。Is it here， okay。

For those who are interested。诶。The most popular nowadays operation for radioic learning with transformers。

 we haven't touched upon this topic in this course。AndIt had an exactly similar effect。😊。

So do you remember how the transformer operation is implemented？Does some of you member have。🤧。回议。

第一次。发月。So it has exactly this division here。Has exactly。The same motivation as alter normalization。

So basically here we have the huge matrix of dot products。

And each do product is scaled down with a square root of D。So， deep here is。理解。

This is small parentheses。I just want to show that there is some connections between。

The different modules we see throughout the course。All right， in the case of supervised learning。

 self supervised learning， we have everything in the hypersphere。

 so the only way that we can push two vectors。Okay， we are in the 128 dimensional space。

You can always think。Some intuitions in the two dimensional space or three dimensional space。

So let's say that this is a uni circle， which is not， but it's very hard to draw。

So since the vector me to live in the。In the unit circle， so they cannot。

Move here so this vector cannot reduce unit length。

They can we can only push them together if we bring them。Closeer。So after a couple of steps。

 if these are the augments from。Two different imagess before training， after training。

 there will be something like this。就BP one。Agree。Any questions so far？So the normalization helped。

As basically the model to ignore the magnitude。And just focus on the dot product。

 the dot product corresponds to this。Because I similarity of this angle。Okay。

And here I have a very nice illustration I found online about。The temperature。

 So you divide by the temperature and you say why we use the temperature of 0。1 or 0。5。

So if you check the paper， they say we play with values from 0。1 to one and we find that 0。

1 works better for large but sizes and 0。5 acts better for small bad sizes， something like that。

So this division with the temperature。You can visualize it。As a way to。Increase。

The average confidence that something so here we don't have lots to have similarities。

 but this is for a simple classification problem and this red line indicates，High temperature。

 so as temperature goes lower and lower， so 0。1。This the。

The Lord gets much more starter and much more confident。Okay， so now we know why we do the alization。

 we do the softm。But what is。Exactly happening after training。 So during the exercise we have these。

TSN visualization， I don't know how many of you manage to produce this plot。

 but it doesn't look that great。So basically TSEs。Just a small indication of how things would look like from the 128 dimensional space to two dimensional space。

诶。I don't trust these flow personally。诶。But it's interesting to see if we could have some indication。

 some undeniable evidence that something is happening， so let's start with the experimental pipe。

So this team from MIT analyzed。A small convolutional neural networked。

 I think some variation of Alex network， trained with the contrastive laws。

And they provide some theoretical as well as empirical evidence。That during this loss。诶。

The features are approximately asymptotically uniformly distributed in this。Hperphere。And second。

 that views from the same images， what we call as positive pairs so far。

Tend to get much closer together。 So the first plot is about。The uniformity。

So here you can imagine the different vectors indicating to these different。大年嗰支。

And here is the two features that are brought closer together， similarly to dimensions。

And they also argue that nicely if you're able to nicely separate everything in the hypersphere。

 then you can come up with very good linear classifiers。

 what we do with linear probing in the exercise that we train another linear layer to classify the images after。

😊，八十。Okay， so they say that positive fare should be mapped to nearby features。And below。

 I'm writing environmental unnecessary details。😊，Any idea。

 what do I mean by unnecessary date in practice？How do we。Inject what is necessary and unnecessary。

You implemented it last week。Yes， the all， exactly。So basically。

Independent of the two different distortions here。These two vectors need to map together。All right。

 so this is why they write about unnecessary degrees。As you will see。

 this objective is more than around。thanアピ。So first， they provide some empirical evidence。诵毒诶独立。

We have a histogram of distances， so mean square。A are distances。So basically mean square error。

If everything is L to normalize， it's very similar to cosine similarity。I would show that。

s bored at the moment。上到。Top left， we have a supervised model。

 so a model that is trained with human annotated data to classify different classes like images。

 dogs， whatever。Take the feature space of this learn model。 And here we have this。

The exact same architecture， but trained with contrasted learning。

So here with the dust vertical lines， we see the mean。I took this。

And this is much smaller than the supervised model。

What does that may indicate that empirically we can see that。

If we distribute everything in the Uniphere that。The positive pairs would be even closer than training。

The model with a supervised objective。I it here。And then they do some。

Low dimensional projections And they also see some sort of。Unniformity。

Because is this surgery is much more consistent than the top one， which is from supervisorsor。

Any questions？All right。Okay， we have some experiments， we can quantify this。诶。

With we can experimentally identify this， but can we come up with。三。Quantified。Results。

 because so far what I present is more qualitative。And the answer is yes。

 at least for the contrastive laws with these small networks。So they define。

So they take bunch of positive pairs， so augmentation from the same image。

 and they take the expectations like just the average。Over to these new square error。

And they define this alignment score。And the uniformity score is。Again， the same。

Mi square error or distance。Just pass from this。你史。你到。Some ex operation。诶。Why you do this？

It took me some time to figure out， I started to have some intuition。

So the idea is that here we have positive pairs and here we have。Randdomly random data。

Are probably negative pairs。So it's not。Basically， this term assigns different。

Portions of the metric of this uniformity metric。For small and large distances， because with rates。

 we raised everything to this。X to the minus d power。good same four。只有。So， basically， we。无异议。

Pay more attention， you put so much more effort to the pairs that lie close together or not the ones that are far away。

So let's say these four。一。第一。Science。And they set this T hyperparameter to two。So， basically。

And what does this tell us？If we consider that this would be the cosine similarity。

 since the cosine similarity lies from minus1 to1， the maximum cosine similarity that between two vectors is2。

So we want to ignore。Pairs of immas， for example。Anims with a cat versus ems with her airplane would be。

In this area here。So kind of down weighted wild animals。Of the cut。

And a dog with the exact same background like blue sky， green grass would be。Somewhere here。

Because we care about creating。不是啊为。Cats and dogs with the same background， for example。

This is like some small intuition while you at your。hy they apply this。Vadial based function。 in。

In machine learning theory， there is this idea of care methods。Vie of base function。

 which is nothing more than taking the exponent with this hyper of around your T。

So they define these care。Okay， let's ignore。So this is some really commonly used kernel function in standard machine learning algorithms like support spectrum machines would not go too much into it。

 I just want to make some。Small connection with。Probability distributions。

 because this is totally empirical， this has nothing to do with probability theory。诶。But inofar。

We can show some connection with the isotropic。Gaauussian distribution。

We will just not pay attention to this。 this is just a constant。I'm writing just for completeness。

So the connection between this hyperparmeter here and this hyperparmeter is probably obvious。Areee。收。

We can roughly say that the distance between two。Branandly sample pairs， kind of probably negative。い。

Conceptually to having a Gaian distribution， basically at distance。Or the。

Density assigned from x with a distance to the mean。But these two。

These two parts are just some proportional approximation， it's not some。strict。

Mathematical definition there are definitely not equal one。

 that's why I say it everything is like an approximation we don't actually have a uniform distribution or anything。

苏德斌。Here would be X prime， so basically I want to establish this connection。没对应。系。

Probably in the paper the I like nicely tied this metric。诶诶。Noor disturb。Any questions so far？

Well it brings us to the next part， so if you manage to work with the exercise。

 you probably saw and also Felix talked about the connection between the lower bounds of mutual information and how this is connected to the bad size。

So can somebody explain the connection with above the mutual information and bad size？

Does somebody remember what we discussed in the last lecture with Philip？Yes。我三。系想。Yes。

 and what happened in the extreme case where we have infinitely large but size？

We had like a kind of a very good approximation of commercial information。Right。

So this is what I want to establish this so practice。We trained with 512 or 1，000。But to get。

To squeeze the last bits of performance， you need a large pad size。

why do we need the large bad size because there is a connection between the bad size and the number of negatives？

So from its many bugs， we extract the negatives。So they are kind of couple。I have this fabric here。

So for n but size， we have two n minus2 negative sum。So the problem is not the batch size itself。

 is its connection to the number of negatives， so we need a lot of negative samples。

How about if we decouple those two values？We need to come up with a new notion of negatives。

And for that， they borrowed some idea that was published in 2018。😊。

This is the paper we're going to emphasize。It does that it's using a memory band。

 what is a memory band， it's basically a data structure。偶尔。So， this is the。Let's use the letter。Okay。

So this is 128。Vectctors， So the emdding dimension。And these are。Some initially， in the beginning。

 were randomly initialized。These values。Dran like something from a normal distribution， but。

As we move into different steps of training， we're going to update these vector。

So K here is the length of the cube。And it's much bigger than。Butt size。Weten define。

The length of the cube be much larger than the back size。In practice。

 we also need to make like a K and multiple of。诶。The bad size， but this is not really important。

So you can imagine for a bad size of 256。诶。The paper we will discuss about which has the abbviation called Moco uses 65。

000。所以。The hydroparmeter here is 65 k。And this is 206。So we use basically a huge number of negatives。

Even though the blood size stays 256。So how we do that。

We have a point there and at each eye direction。诶。We update those vectors。

So let's say if this is k and bad size is two in the first iteration， in the first iteration。

 we will update。Those two bodies。And then we move the pointer here。

But every time we use the whole cube as negatives， then in the second iteration。

 this is the first iteration， so here I'm illrating for bad size of two。And K。

 the number of rows here。So in the second idea we。We update these values， move the pointer here。你送。

So this is how we keep。Basically， we use the negatives。From the previous iterations。

We start with random initialization and as we move on。

 we create a dynamic cube or dictionary that is updated at every step。With the previous。

With the previous mini boxes。And in the end， we throw away when we。When we update these values。

We throw the oldest one。So after the point it moves here， it comes back again in the beginning。

Any questions about the queue？So they formulate contrastive loss as a dictionary lookup problem or query like lookup problem。

诶。There is a lot of inspiration from all these methods from information retrieval。

So they take this intoYC， what we say as a contrast log。They add the memory bank。

 which is much larger than the mini size I you be。And then。They found a problem， what is the problem？

We will use the word key for the output。Of the。With streets。But size。啊离。And here we have the cube。到。

No， this is not correct。So basically， the Q。Is updated。In the initial experiment。

The queue was updated。With the values。Past from the encoder。And this didn't provide stable results。

So they came up with this idea of the momentum encoder， so since they keep and。Basically。

She they update their dictionary。Y。They use the output of the encoder， even if you。

If we say that here this is N code there and here you just do。Tial dog be。

This didn't work in practice。So they came up with this state， they call it momentum encoder。

 we would use it。Extensively in representation learning， but it's also used in other fields like。

Reinforcement learning。As we call it exponential moving average over the parameter。

So the exponential moving average over the parameters。I prefer an notation of。Student teacher。

 so I will use this on。诶。So the teacher models and exponential moving average over the encoder or the student。

Would be updated。Only with a small ratio at its depth。So M is a value from。呃。

So we only update so any practice something 99%， so at each time we only pass1。

 1 percentage of the student parameters。就 the地址。And this is the only way they could make this approach work。

And then。They argue that this makes。TheThe teacher much more consistent， because we gradually。

We progressively update the dictionary。From all the previous its。

So also the values that we update need to be an like a moving average of the past iteration and this makes。

This way they create this。Consistent。Memory bar。So I tried to provide some indication why。

They not just use a memory band and de test the gradients and update the dictionary。

 but they also use an explanation moving average over the parameters theder。

 that's what they mean by momentum and code， we will also use the word。Teacher in the college。

Any questions？O。Yeah here explain。They're writing the favor。

That they hypothesize that it's attributed to their rapidly changing encode。

This may indicate because it's still a hypothesis that it reduces the representation's consistency。

 so I want to emphasize on the consistency part here。And EMA stands for exponentialonMoving average。

 usually over the parameters when we talk about modelss。So the objective that was initially。

This is the infancy of contrastive loss because this thing here， this expression where the keys。

These are the explanation moving average of the car and mini path and this is the whole cube。

I don't like this notation here， it can just replace。This there。We keep up done。

So if we were to rewrite these。诶Q。I love。The transport。ok。

We use the capital letter T for the transpose and the small leather T for the temperature。

I'm rewriting this with a capital end because I don't want you to。

Confuse this case here with this case here， so this is the output of the current mini baths。

And this is the。The whole。咩吧。AndAlso in implementation， this is a matter humplication。Why this is a。

That's magic multiification and happens everything。He must't back。

So I just want to reemphasize that Ke is built as a dynamic cu。And it's consistent。

This is to the code， I will also give you an notebook where you can study a very simplistic implementation without I removed everything related to。

Dist the data part， and I will just give you a no because。

The initial idea was to ask you to do implement as an exercise。

 but then we thought it's too much it would just give you if you want to study it。

Because some students。Said that they have a big gap between discussing about this model in the lecture and implementing themselves。

So I will just provide you with a pseudocode with this function， how it will work in actual code。

But not a complete solution with trained models in find。And in practice， we use a queue length of 65。

000， the momentum is something like 9% and they have a big temperature。

One small issue that is caused many times its bad normalization。So even if you have a great idea。

 you may still miss it because of some unintentional information looks or shortcuts。Ma合 been。

And over the last few years。诶。So personalization was invented between 2015 and 2016。

 and then bracelets came out and everybody used this normalization method。But as time goes by。

 goes by， it looks like we start to。Using it less and less。

And this is one more indication that it causes problems。

So the problem is that the model can exploit local information liqus。But it's kind of seating。

But you can you only have this problem， so this' local。

 you only have this problem when you do distributed training。

 so you have multiple GPUs and its GPUC only。So you have a mini box。

So of 256 and you can distribute this in as many GPU as you want and do the computations in parallel and then。

Compute the gradient。 And then。Take the average gradient。So this is something that is。

Completely unrelated to what we've talked so far。 It's like an engineering thing。

But for lots of data sets like emails N with1 million emails， you can't really avoid。

This fascinating part of。Distributed training。And it looks like the model could sit from the local batch of its CPUU。

 it could exploit information with the local information So there are different ways to。

Encounter this problem。 So sincear use this as it called in the literature synchronized ba normalization。

 So you have an intermediate step when you aggregate the statistics， so the average over the。

The means and the standard deviation。上吧。