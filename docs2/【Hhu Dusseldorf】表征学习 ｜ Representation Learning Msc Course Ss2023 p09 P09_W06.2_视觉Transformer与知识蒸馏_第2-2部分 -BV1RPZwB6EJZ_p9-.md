# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p09 P09_W06.2_视觉Transformer与知识蒸馏_第2-2部分 -BV1RPZwB6EJZ_p9-

So you reduce probability， for example， here to 90%。

And you distribute the 90% over the remaining classes。uniformly。

And this is a regularization technique that works quite well in the supervised learning。Of models。

 So you can kind of。Draw some connections between this kind of。

Soft distribution between all the outputs from a train model。Compared to。诶呢似情。

So it's not at all very clear， even though we know it definitely works why taking multiple random initializations and then combining their output to work in the first place。

So we use exactly the same architecture。T0 or n in general ensembles， as we say。

And then we just offered their prediction。So。In the probability distribution。

 we just combine the outputs of those models。And this results。い呢。

In a much better prediction than any of those 10 or any individual models trained。

So this is still a mystery in this is like an example on sites for 100。

 this is a paper from Microsoft。So。This is the mean and standard deviation of all these 10 individual models。

So，81 points。51 training supervised learning。诶。And this is the average of the ensemble， as we say。

So they train the models separately and then take the average because if you take the average and then train then it doesn't work so basically you just train them independently and then。

Aver interpretation， and you see that there is a significant gain from 81 to 84。

87% is this simple example of treating class firearm alone。sycle 1 hundred0。嗯。

So the next question is。Why does it even work？Better to match the output of an ensemble even better than matchinging the true label。

 so the true labels are the true data distribution which we want to parameterize with the neural network。

And still experimentally。Really accepted that these enem models。Works better than modeling。The exact。

Human annotated， for example， in a supervised case， data distribution。嗯。So in the second experiment。

诶。They do what is called assemble node istillation。

 so they train one single model to match the output of this averagevari that we it had like the average of the ensemble。

And it takes scores much better than the initial models， even though。Slightly worse on the end。

 So between。Averaging older models but stayed significantly better than training the models independently。

So this is still a mystery。 that is like a huge。For of the published is regarding some theoretical explanation regarding this one。

 is there a question？So。If you just like increasing。1 times you train 10 separate models。 But yes。

 but in contrast to that， you could train one big model。hi the size of all the。Time冇。咁前。So yeah。

 let's say this model is the best model you design for an application。 So first you design a model。

 so it's not possible to get a better solution using one model。Yeah。

 let's say this model you first tune the model， the hyperparmeter and everything and you say okay。

 this is the best performance I got， and then I repeat the same experiment 10 times， it's not。

So basically， instead of training a bigger model， let's say if you have like a bigger model。

 you can just train a bigger model 10 times and still at the ensems。

 this independent of the choice of model。嗯。What is now the compassion here？你你。🤧So， basically。

I don't remember if it's crossentroppy or KLrgence we'll discuss about this， so basically the output。

 instead of matching you know the crossenttropy from the real labels this one how can you do it how enemble Yes。

 you mark the average of the ensemble of the models。So the advantage is that after all。

 like if you want to deploy， let's say the model you don't need the1。The tender the ensemble yes。

 you the one that was trained on the outer of the ensemble Yes。

 and you still get significant performance improvement over training just one more platform you know  81。

51 to 83。81 is like a significant improvement yes。And in the end。

 you didn't change your hypoparmeter， you didn't change your model， you didn't change anything。

You know， we created the examples， and then you might be up to the assignment， so it's。🤧Not so many。

Theorists can understand it regarding this one， I will not cover the theory。

 but you can check this blog post or the paper the blog post places。

A more a larger version of what I described here， so this is still no distillation from an en。

And it's still a mystery， so the inside that they provide in this work is that the idea of multiple views。

 so having one object like a computer and taking different pictures。

which basically multiple views in the input space of the RTB of the images。

Can be also translated or this kind of structure can be seen to some extent。诶。From different。Okay。

 here they only consider CNNNs， so different CNNNs would。发布是。

Would basically create these multiple view features， so for example。There are many。

Let's say high level features， as they saw for the cars， so one model can capture。

Like the wheel of the car， the other will capture the lights or different parts of the car that all the models are able。

To。Classify the image as a car but。街到腐。Cpturing different kind of features。

That correspond to different parts of the image， and this is the idea of。

They argue this kind of views。But in the intermediate layers of the convolutional layers。

There's some small inside。🤧。So the next question is， okay。

 we have multiple models in where you gave them， but so far。Okay。

 let's ignore the application of assembly knowledge disill and say we have two models。

The next question is like， is it necessary to train a very big model and then distill its knowledge to a smaller model？

So the answer is not necessarily。So there's one。It's called be your own teacher。

 It's a quite complicated paper， but they were the first one to show this idea that。Yeah。So in the。

 in the red box。They train a big model。And then they displayill it to a smaller model。

And the second idea。They use。The outputs from the deepest layers train the smallest layers。

We will not cover this approach， it's just the first one to show that using the same network。

 you can have even some small hyperrs gain and significant， maybe hyperrs gain and also train。

🤧At least four times faster。Sting with residents。So here's how they did。

So instead of having a classifier at the end of the network， after its computational block。

 so for the transform this would be the self-at layers， the transformer layers。

 here after it's correct block， they have basically multiple classifiers。

And the early layers try to mimic the next layers。So， this。

Indexing the sum refers to different blocks。But in any case， they also match both the features and。你。

The probability distribution is soft target。嗯。So if you remove the sounds。In the red box。

This cross sensorpy， so basically the supervised class。

This case like is what you have to do in the next exercise。So basically。

 this is what you already know how to do from supervised learning， so here you will have。

A teacher model that is much better and much bigger than the student。

Just so the reference forward the next exercise。And we will discuss。

A bit about gay diversity for this way。So when you have the one model and you don't train a bigger model。

 we refer to these as online knowledge distillation or otherwise cell distillation。

And in the next lecture， we will combine the perspective of knowledgeL distillation with supervised learning to see more advanced。

Approaches to do such supervisorvis learning most scaling methods。So this is the alternative。

Way we have seen already in the last lecture we talked about this mock approach and the exponential moving average over the parameters。

So this is a form of。Sent distillation， so you have the model and the exponential moving average of the model。

So this can be regarded also as a form of self distillation。嗯。

Yeah now it's time to talk about he divergence。什么。嗯。Wass it。

So this is the definition of k divergence。So if you have two probability distributions， P and Q。

 we use this symbol to indicate the closeness or the divergence。And intentionally。

 we don't use the word distance。Why， because when you say distance？In mathematics。

ThePropers of the distance doesn't need to be symmetric。But here。

Here I have a small illustration to show that。Given this red P distribution at Q blue1。The。

The care dirgence even quantitatively significantly different， so basically care dience has two。

 let's say， directions。So B Q or QB。So。I would like to emphasize a bit more because I find it very hard to distinguish。

Which direction should we take？🤧。So to use straight lab。嗯。We have like a very simple problem。

We had this。Forreal distribution， which is a multivariate Gaussian。With two modes。

 so each mode is like one valet you like with two min。So this is like。Both plots are so far the same。

🤧诶。So in the first case。We train an optimal queue， so we parameterize。You need model distribution。

 to say。Not the mixture of Gausian， but the same Gaussian distribution。To model this direction of。

K and diversity so B。Is this distribution？And Q is the unalal one， and in the second case。

 we do the opposite。So this is an example from the deep learning book from He Goodfeellow。

And in the in。Okay， does anybody have a guess， has a guess， what's going to happen， yes？one。文年。

P X and the other one is seeking the moment So just one to。Okay， which one is the one。

 I think is me seeking and the right one is the most seeking。Yes， that's correct。Nice。

Maybe not the best illustration， but。You get the point。So here the distribution queue。

Tries to capture both modes。And even though here， there is no probability density on likelihood assigned since he tries to maximize。

Both and。Mo of the so it tries to capture the whole distribution。And in this case。

 it will focus on one of the ps， so I will draw randomly just one。Something， I I don't know。

Whatever you get the point that it focuses on only one of the modes of the distribution。

So the question is。Where should we use like if we have the pizza， it's like a pretrain。

Model and the student， which is like the small model we want to train， or even if it's the same size。

Should we use one or the other？So in supervised learning， it's quite clear that we want to capture。

Basically the whole data distribution and not just one of the modes。So here I'm enjoying the。

I'm mathematically describing the connection between K and dirgence。Which is this term here。

And if you just decompose the two terms。This is the enthroppy。比。Including the miners。

This is the cross I pin。P就。So let's say in the supervised case。Which one is the teacher P or Q。

You should be able to answer this question。Easily。So P&Q。

 which one is the teacher basically the data distribution in supervised learning where you have this one called distribution？

No which one。Yeah， P is the1 hot distribution and Q is the prediction of the model。嗯。

And what happens if you take the gradient here？So if you take the gradient with respect。To Q。

This term drops out because there is no parametermeter to be optimized yet there are no gradients with respect to the。

Basically to the data distribution in selfupervised learning。诶。I hopepe it's clear。嗯嗯。

So which one is the one that you should use if you want to do knowledge distillation。

 should you use the student or the teacher？In general。

 it's not clear it's basically what you want to achieve if there's not always one answer。

 so they also argued in this example in this book that sometimes you may only want to capture one of the modes and this would make sense and sometimes you want to capture the whole data distribution。

🤧。So experimentally in this exercise that you will implement this week， I didn't find like a。

A great difference between the two approaches， even though I didn't spend so much time。The point is。

嗱诶。When you have like a randomly initialized students。And the trained teacher。

 which one of those distribution in the beginning， are more s。ideas。

IfYou have a teacher and they are an initialized student and they have two probability distribution。

 which one is the sharpest one？More sharp， it means more people。yes。

 the teachers has a Saer distribution because the student initially would be almost uniformly distributed among these different classes。

嗯。So， I want to emphasize that。Basically when the teacher is yeah， let's。

 so when the teacher is here。And it has this initial distribution。来啦。It will not be one hot。

 but it's。Usually tends to be quite sharpp and confident。

 even though it's not exactly one thought it may have different。Probabilities to some other classes。

 whatever。But in general， it's quite confident or sharp， whatever。So basically。

 I want to emphasize that。S piece here， if you use the teacher here。All these parts will drop out。

And the student will try to match this peak。So this is the。Some sort of situation。

And in practical terms in the exercise， I didn't find the great difference。

 but maybe you can experiment with both antenna which one work best for you。Oh。

So the next thing to discuss is how can we achieve so far we talked about the logic space or the probability distributions。

 but this is not the only way where we can pass the knowledge from different models。

 so for some printer models we may not even have the different heads that point to some number of classes or clusters。

我来这儿。So this is one approach。Where呃。Basically， you use contrastive learning。

 so you take the features。From the student and the teacher and you apply contrast learning。

 So what does contrast learning do， it pulls。Together in the feature space， positive pairs。

 What is a positive pair， the features of the student。

of the same images and the features of the teacher of the same images。

 so you pull them together and you can train a student network even without this idea of cross Enpyia and modeling the soft targets。

 even if you don't have the head in general。嗯。So we have covered the last two lectures and I told you like contrasted learning is quite general。

 so here is an example where you can model even an ensemble of teachers。And you just apply。

So basically for its pair。So， students。It's like the central view。

So you consider everything as a view， you can say u1， view Q then。确是我。So you teacher one。

Use iter two， so in general， it is like the ensem of different random missileized models and it's time you take the pairs。

So this would be a positive pair in contrastive learning that would be one loss function in this latic。

So I is the index of the different teachers， and this is just the contrastive learning objective we have seen so far。

So instead of taking augments of the same events。We have these asems， so this is like the features。

So view from Tier1 is the features。From the first。Separately trained model。 and then the second。

现在在 care。And then average you sum all those together， and this is a supervised objective。

So just want to show you just in the case when you don't have。These heads。

And you want to train directly on the features。And in this paper， it has worked。Slightly better。

 even with。The cross Central it delayed。Here they apply this idea in a specific modality。😊。

I will move on， they just passed the information from a pretrain re on image to a small CNN that was the part of the encoder in a segmentation problem that affects。

That them as is and they had some。Small improvement。But we're looking at size on that。🤧。

So this is the summary of all this part， so model assemblies can boost performance。

 with sell distillation， we don't always require fix and large data。

 this is what we will do in the next lectures in selfupvised learning。And you can capture。

Multiple views in the feature space with these model and samples is the paper from Microsoft。

And lastly， the distillation can be implemented in the feature space， for example。

 with contrasting learning。So this is the last part where I want to bring these two things together。

 so we talked about vision transformers， knowledge installation， so there are a lot of approaches。

That referred to and。Vision transformer based this specifically for vision transformers。

🤧So this is the first one。嗯。Maybe need to draw something。

So here you have the fast based projected tolkens， here you have the class tokens where you do cross centropy。

The output with after this blue corresponds to a small。Head。

 it's a small levelP or a linear layer soft ones。And then the idea is that。And we can add as many。

Tis or tokens as we know， so let's add one more token。So this is just a random initialized vector。

 they call it distillation talkingken。诶。Train on the random municipalized spectrum。And then。

Let's take the output after the transformer。 So during all these self attention layers。

 all these dos communicate with each other at each transformer layer。

 So in the output let's take this。There is features from this distillation token。

 and let's try to math。The output from another pretrain model， so another teacher。

So this is only possible when you have a vision transformer architecture because you are。

You accept in the end just one sequence。In the same way in natural language。

 you have the start of sentence， end of sentence， segment， level representation。

Msking toms and all these things here you can just our retireer present one toolken and try to mask its output。

From editor。🤧。So。诶。They have shown that it works quite well。😔，When you have a pretrained teacher。

And they also saw that in this case， as opposed to what Hinton sold in 2015。

 it's better to take the hard targets from the pretrained teacher。

 no matter if it's a CNN or another transformer and use it to match this probability distribution。

So both for decades are。Girl center will be here。So one is the supervis， and the other is the。

From the teacher。here are the numbers。So the main result。Is that。Hard distillation as it called。

 so just to take the one foot distribution over the prediction of the teacher。

 it works better just in this case that's why I told you there is no one solution in general and second。

That。Distilling， basically modeling the output。Of a pretrained CNN with a vision transformer work sometimes even better than training just。

With a supervised objective。And here are some improvements。嗯。

So this is imagenet and these are like different transformer variants。

 so you can just take the page using transformer as a reference。🤧Yeah。

And you see here instead of just doing cross entropy。You add these and you have。0。4% improvement。

And okay， in power， I would like to emphasize that this 0。4 sounds trivial。

 but if you consider that imagenet。As like 100000， let's say， images on the test set， maybe 50。

000 or 100，000， this 0。4% is。Something like 400 images are classified correctly in addition to the previous model。

🤧。So this idea was used later。To。Kind of model either the learned features invariances from learn features。

 so we use again this distinction option。But now they use it in another context。

They try to mark the output of a model that。Is free or a very unique data set that you are unable to classify the image based on the texture？

And you can only classify the image based on the same。So this is the data set。

 how it looks like it's called stylizing that。 So basically they remove。

All the features that relate to texture。By creating these additional samples with different configuration techniques。

So the only way。You can classify these imagess correctly is by learning。Save based representations。

And then they took the output of this model。Of a train resident on this stylized imagenet to train a vision transformer。

呃。So basically， this is another technique in representation learning in general。

 where you want to introduce some additional invariances or model。

Inductive biases from other models to have like。The desired characteristics that you want。ok。

And okay， now we will talk about the state of the art。😊，Which is basically。How can we efficiently。

Disttill a very large visual transformer to a small visual transformer。

So the hint here is that we are not leveraging all those representations。

 all those token based paths based representation in the vision transformer。

 we only take the classification token。So even though this specific token communicates with all the other tokens。

There is nothing happening with these outputs。🤧诶。So basically。

 what if we additionally match not only the classification talkingken。

 but also the path level outputs？The but level。诶。Out the presentation from the transformer。

 and this is what the state of the art is doing。So instead of just taking the out to the CLS talking glucoseroenttropy。

 they have another head for both models。So this can be also trained。

This can also be an financial moving efforts or a large model。 It doesn't matter。

 This is a teacher in general。 It can be also。Ss bigger modern。

So you just pass the out from another head that is responsible to have like probability distribution over the paths based representations。

So even though in language， you can map all the words in a specific vocabulary， so let's say 100。

000 words。So you can intuitively think that here we map all the passeses in。These type of clusters。

So this。S center is happening in some。High dimensional space like 10000。

 So basically the model has to classify all the parties。

 no matter how diverse they can be in one of those。10000 classes do like cross。

we will talk about this more in depth in the course。

 but this technique in general is called mass image modeling。If you want to do。Satitiulation。

But if you just want to do distillation， you remove the mass parameter。Here you have the teacher。

 Let's consider the loop。 So you take an email， you take an a， you ignore this part。

 you have these two。试惯思。So this is a student we want to train from Sc， this is a big teacher。

And then。We bus those。Blow views from the head and then we mark。With cross entropy， all these。

Pots based representations， and we take the average we take we grade。嗯。

And these are some results so they can pass the model from 1 billion parameters to 300 billion parameters without losing any performance almost nothing。

And。And went a little bit fast， so this is a summary that transformers are much more flexible。

Because we don't work directly on La that space， but we project these parties and in the end we have some tokens and then we can add additional tokens which enables us to。

Do more tricks regarding distillation and different techniques you see through of course。

 like masking and everything。And Mama modeling helps us to distinguish the model from very large networks。

Much more efficiently and faster and。Basically。The last two years is like a Y adoptedic technique in a computer vision。

And I also showed this idea of passing inductive biases or desire characteristics from other met networks such as these regime trained on。

This stylized data。Yeah， that's it from my side， any questions？Okay。That's it for today。

