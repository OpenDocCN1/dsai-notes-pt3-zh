# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p15 P15_W09.2_多模态表示学习__鲁棒性与视觉异常检测_第2-2部分 -BV1RPZwB6EJZ_p15-

in。Which you need vision based information， so it's hard to get this from back。

And these are images from microscopes。So just to give you three examples of where these models。

We perform poorly。へ。You can see here both of them。As is the crucial short performance。

With different number of labeled training。So in this case we。We train I think， aly。on golf。诶。

Parahood care corresponds to how the model having more and more data approaches as sympatheticically as they perform。

And you can see that even with zero salt is very clear， piece has a similar performance。

having four labeled。Examples for class for email。Which means that this type of zero shot。A is really。

Even though you don't train anything。Okay。So in the beginning of the presentation， I presented。

There is its scores。And here it's the zero shot keep scores。And you can see that the。

The big advantage is the robustness of this model。It's not。

All about classifying images from the validation of I set。But also， learning。是。对啦。就这一个设置。かい。关于种。

And on the left side。😊，一。This is like a more qualitative illustration for some。这个样子。

And this is a more predictable quantitative approach。So these are， I'm enjoy on the board。

So this is the image。Mation accuracy。And this is the。And this is the average。I。Over this6 or 7。You。

 over these7。Distribution。Two data set that have a significantly different distribution。

Let let's say this is a。So this is the idea of behavior where。

The model is not influenced by the fact that you change the distribution。

 it has exactly the same accuracy， so ys it means if the model has 80% accuracy name then。

Still have be class all these。都。This is the supervised case。So this is the。Iデ。

The supervised case or different models。Our free。This is the。The approach of zero shot， I think。

So keep with your shot。I think they use the the best model。the。So the same model。

So the same supervised。That has 85%。Icur see your name wasn' it？We score something like。最低？关映在。

The you made model would score。Like 7。So it is clear what this graph on the left illustrates in a more quantitative and principled way。

And the different points here。Are the different wirelesss and vision transformers？

They are all trained with the same objective， so different architectures。Frank。片。

Contraive language image object。Okay， now we'll talk about a completing new topic。

This is called a normal detection。Do you have any questions regarding C？开企。

So we're seeing new tasks so far， we have discussed about。Ias class frame where we have some sort of。

A priority determined classes。稍人。そ forりません。And we tried to find， we tried to map。

The images into this 1000 cluster。Without having。Pairent label data as。

So now we'll do something different。How was something different。This is a low dimension。Fature。

To be like a Tna block。えモデル？A very good model is learned some sort。So， we imagine that theres some。

Some features， some learned features either。Supervise learning。ゲモ。And the model LED some sort of。

Data representation。え？So here we don't have like a free trading data distribution。

Downstream data distribution。 So this is a。The training data， we train the model。So let's forget for。

That there's like a larger。plic费定。Let's say that these are。The images that we have available。

Either if it's supervisor。是不是8。So these are presentations from our email。地身。嗯。InIn practice。

Some cipher， the cipher data sets， but you can imagine that this would be。

X ray emailma is from one hospital。That correspond to a specific。

Modality from some specific company with。三诶。Care thousand。For example， about the contracts for beMs。

How the patient is center。Given these images that we have available。

 which we hold those images in distribution。I typically use this table。So take us a aim to indi。

And we want to be able to detect。So let's say we have a very， very good。Or segmentation。

We want to be sure that this model is only dealt with images from the same hospital or in general。

 from the same。イすてくさ。To detect outliers。Before we actually fit the data in the classifier。

Why because the model。Thankss to。Maybe we have like some undesired behavior。For example。

 if there isn't。大部。Xray must coming in from another hospital。不大理。我本利。食啲。This would probably affect。で。

That supplier not we have on the extract ray here。どちの税。You have a generalization。一思。

Really depended on the scale， but there are like hundreds of publications when we don't have the scale。

 for example。This education I'm talking about。You wouldn't have this。Me to边咯。X ray。

So you want to be able to。今 this that are。Outliers。Or even。

Maybe somebody does like a mistake in a real life case and provides。在。Xray。A knee Xray， for example。

 and your classifier is dealt with completely。诶 say。Wrong1分。not be trained。

 you don't really want this outcome。So this is like。A task to detect。反正我是上不。Outliers。

We will call them is out。上品。So we want to detect。诶啲三，系。There are ones on the block。细。

Which is the out。We have three。Ts referring to the same task or other distribution。の大す。

No well be detection or a normal detection。So we try to identify samples。的。Probably outliers。你是大。

Let's see what we do about。And here there are some more general。So be great。C。On的。

On the data distribution。来。How the institution can be shifteded。

So that the samples are considered out of distribution， how different。

Should what is the threshold that anyone can consider in and out？Depen on the label or。

If the as they call， it equal equal biopsy。电医箱。Not really important pretty fine for you。

For the next task， what he be there out of disagree。So there was this guy in 2016。

I love I think in the US in the US。Who did some empirical observation？W was the beginning。

All the literature that。OD or。Given that we have a classic。So for now。

 forget everything we've talked about about learn the presentation。

We have a classifier that is trained with supervised learning on our domain of interest。Excepts。

 even mistakes， whatever。We have sea glasses。And during test time。We have different。

We have a pro distribution we take the output， which's called logics， and then we have Fl。

a probability distribution over these different classes， like how much。Es with me go past whatever。

And he observed that。A very good indicator。The。Of classifying the images as in and out distribution。

Was to use the maximum software control。Which means。Just taking the art much。Like position one， zero。

3。So during classification， we say this is the highest probability。This position 3。

 position 3 corresponds to an airplane。Instead， we use the probability itself。So it says 0。8。

And this has the agration MSP。ます。And he7。对。T samples。Have here with the dogs。跟 you系。Given the。

Supervised training of the institution。The model text will assign higher probabilities。現 marginで。

ID你们。So this is the maximum of much probability。And here you take a normalized histogram over all these values for all the different in。

So if you integrate over all these。Do different。Get the。

So the distribution samples tend to have like。Much higher。万事。そのベ。There's another score。So so far。

 we assume that there is a classifier that's pretrained with supervised。And we take the much。

And later on， I think in 2018。And there was another approach。

That enables to define the score So the score。哎，关的是。score。当是。

The score is responsible for defining a metric。To classify this。We tried to come up with metrics。

defineine。To try to distinguish between those countries。example these probabilities， if we take them。

 we can see that。We can detect pretty much a lot of data that are in and obviously。

The alternative would be this Mahalanobis based score。嗯。This basically leverages the fact。那在。

Supervised classifier tends to cluster their images that belong to the same class together on the feature space。

 and they form something very close to。オシでする。So this is like a way to feed this。你史要求。

So we fit the oceanussian distribution for each class。These some。

Cont like samples contained in class3， which can be like a dog。We never to fuck the。

These tend to be together。By fitting a Gaussian distribution with the。Class wise mean。

 so we only take those features and calculate the means。On the equation this been。四。

So this each class has on me。So of course， we need to know。We supervise。I here。It me。

And based on these mean。A shared variance between all those different clusters。So the same volume。

What they， what they said。国会までき。So the the combined management staistic is a。

If we have like 200 dimensions。200 by 200 matrix。Where 200 is like the feature dimension。

And at its position， I J you see the covariance between。To dimension。

Instead of taking something as simple ashan noticevic。えまマチンそのビティ。We thank， we send。呃，Take个。At this。

 let's say， which is weighted。In different ways， based on these class wise means。Instead。要そです。夫认。你四。

first， in both cases。I'd like a supervised class buyer and take them maximum of mobility。

And in the second case。You need the supervised data to compute the means for each class。

In order to compute this class wide means。You need to label the data。Have if the data are unlabeled。

The alternative is a very， very simple method that works quite well is the nearest neighbors。So。

 we use。The similarity。Between the。The training set。So here I haven't shown these， but this like。

I' only drawn the training set in the first slide。So， here the。The or stocks first。training data。one。

The in distribution test data。We want to classify the blue answers industry。这关系。

Should be out of the street。So the the main， the bottom line。第二张。Instead of。细啲。

For each sample independently。It maximum social proulability。The mahalom is distance。

 given that we have the labels。To take into account all the。Statistics of the class。

 of the features of the class that help this me。And if we have no information about the data whatsoever。

We just take the distance for each point， for example。いポ。好。So we take the distance either。

 so this is the in distributionribut data。Train data。

 And these are two test samples by Iing two different symbols。So we take the distance。To the nearest。

三啲。The distance or similarity incorrect。It's nice similarity because everything isnt too normal。

So you can imagine that these are the features from this。

CCNR or Moco or click features that you have from。Read。Even training。

We said supervisorvised Le on agencies。Just some features。

 learned features have been learned during their presentation。Preface。大。We decide on。

We decide how much the data belong to the institution。It'Based on these two distances。

So with some threshold， we decide。Which distance is considered in distribution our distribution。

So we have these three basic scores。Maha of maximum ofconslability。

Mahaa nobi distance and near neighbors。You can also hear。

 you can also take the average over all the training data。第事。The distance of the closer。

And we want to。Basically， decide。How what would be the magic？I the metric， this is the score。

The metric， for example， in immuno classificationification， is the accuracy。But in this task。

We cannot directly define the accuracy。さも？メ？But in any case。

Anoral detection can be formulated as a binary classification app。

 where the two classes are the in distribution or the an sample。

So we can treat it as a binary classificationification tab。So， this is the short called。

Comp future metrics。So， for。Preic。I the。个人。And the rows respond to the actual。から。

So we consider us positive。Ladies。And as negatives， out of this。上中。那个。In general。

 I want you to have binary classification there。A lot of metrics that are defined for teacher。

Based on。The different types of errors that you allow your classifier to make。

But these metrics are only viable。Or binary。In our case。We will use two important metrics。

The true policy rate。This is basically。So basically， given that the data are easy。

How much did I get correct？So we measure how many data we predict as new distributions that are actually in。

W is。我哋。对对一家都在。PSo P positive sample。 So given that we have 10，000 images that are in distribution。

 how many of them did we compute？Did we classify correct？And the same thing for the fault。

Wills be great。I know， not the same， but given that。Even that the data are in distribution。How much。

店。So given that the data are normal roe outliers of。How much of those data will we classified as it？

So you can imagine an example of。We need to accept some sort of threshold for Italy。

So you can imagine， for example。Different thresholdhold in different application with these。なで。工で。

How with what probability should I accept？COVID tend to be positive or negative。说的。

I don't let the bio spread out， so they're probably you need a very， very high threshold。怀 on。

On a segmentation model， even if it gets like a。已经。It doesn't really cost you so much in real life。

There's always some sort of threshold， which is very highly defined in this application。就。

We would like to find。Some scores on these tasks that are a big。Tresful independent。So for that。

 here I also have like an illustration。The through positive rate。

 you imagine it as dividing all the sum that belong to the semi cycle。黄子在。另婚证据。In our case。

 two positives are correctly classified in this。啲。Bes the abbreviation。

Out of distribution samples classifiedify design。So the same way that I said about the soft much probability。

In any case we have like a scanner， which is a score independent of the three scores that I talked about。

S score。几啦。You make。キスト不然。Of all these different scores。岁月仙。Let's say this is the distribution。

This is the。course。诶 this诶。夜都会到。Is like the threshold where you have to accept。好。

How many errly classified samples can you withstand for your。And。The quarter you talk about。

He's based on that care。Can你 imagine诶。Ass， so these are like the true positive samples。

 So you can imagine。As trying to float。I grew up。Going from the。2 positives。都 where the。

Fals negative。So by moving around in this care。We increase the ratio of true positives up until this point here where we start to have the false negative。

Yeah， sorry。So going from here and sliding through the threshold。We move on until this point。

 where we have the first。44。就。The moment we move the threshold。Further up to this point。

 we start to accept some all these samples as in this distribution。Because we have like a fresh here。

So the rate of the false positive starts to go up。And呢。We have this point here， where we。系。我哋。

All the distribution samples correctly。And no matter how much。

 no matter the threshold we might choose in the whole range。The number of twopo leaves。

So distribution samples that are classified correctly and stay the same。

And by sittinging all these these。The threshold by seeking all the different thresholds。

We get the so called。receiver operating。So again， driving margin。Having a threshold going from here。

Here。Maybe you can draw the board。So in the beginning， you have zero。for positive and true force。

What take to understand。So we have the true posing and four positive grades。And。In the beginning。

诶我哋应该只。Imagine this plot。All the images that I'm classifying are correct， classified。😊。

How until this point。We are hitting this point。Which is like the。

We I started to having like this false。到自啲。And here I go on this side。

So here I accepted one sample that is false positive。But at the same time， I'm also accepting。More。

电视。So this。Proly。零啦。This point。You can imagine it as。外晓。

Where I accepted all the true positives from the interview。And。I cannot go higher。

I have classified all the。类似。So is is the connection between these plots on the slides。他有。Cca。

Receive a operating curve a bit more clear。What does it happen？So， it's。呃。

That is threshold independent， so basically we consider all the different thresholds。

Based on the application， So the application defined。话。I will。0，1。For different applications。

 you find。Different。Po positive brain that will influence also the true positive brain。

 So it's like a trade of。去好。Some real light。And yeah， this is a discreized version that I showed you。

为 you発 toも。For一 example。But for a very large number of samples， this becomes。五零。Like this。

So the advantage of this care is a distress independent。

TheSince we want to have like one quantitative metric like accuracy image specification。

 we compute all the area under。This R C care。And this is the metric that's called our road。

This is an area under the receiver operator。Will you say special independent。Yes， yes。

 we kind of take account all the possible thresholds。And we kind of make it thresholdly independent。

JustFUA。追。Also。关于 sensitive。symbolbal。Because as you shown the。The two let's say， distribution。

Itdepend if you have 100 samples。10 million samples。

 we just take into account how these are distributed。So the more samples you have。

 the more representative。This distribution would look like。

Our score takes into account the data as a probability。That's why we say that。

Inensitive to the glass violence。The interpretation is。嗯。Detroy the block。

But the main interpretation is。How烦 from there around。F。You are at each point in this graph。

So they're un classifier。Last five because you pick like randomly。Consider its data in this。

You always move on the di end。So from this point to this point， if there are ten samples。

You are identify five of them as in distribution， five of them are。And the main interpretation is up。

as far as possible to。From the random classifier。flashlash fire。Would go on the out。Here。

 so through this all the time。And then you would reach point one。Okay。

 some people draw this line as well。So your have understand a perfect classifier would never score。

Poitive， so it was never classified。Other of distribution data。Only go up。

 that's why you see this do。On the upper left part for the。Can。So that。

These are the main things you need to do to work with a normal detection。

So I have a lot of slides how people used to do that。So in the supervised case。

 we have the maximum soft much probability and thehaob over。诶。We will work on the last case。

Supervise all the detection with these cake based models， because we want to show you。

And I think definitely can be you with those representations。So this is an example very quickly。Of。

A free train model with someupvised learning or distribution。I think this is。a band or something。

Here you can see this visualization that I showed on the blackboard on these different classes of the distribution like cats。

Airplane， dos， whatever。Here is the coine similarities。いgram。So they are not normal life。

So this could for grounds。Is indicate how as the institution。A close to the day distribution。

So here it's just the best step。But the nearest neighbors computed over their in distributionsbut trainings。

You can see that the more far away。Histograms are from each other， the better。

The all the classification， the more we can identify， the more we can distinguish。ビトインリス。

Binary classes in and around。Another。important lot。We is from paper from 2021。第三。

So this is like a PCA， PCA is like a low dimensional projection of the features。

So they saw that take if you train。Supervised model from scratch。

Or your in distributionri data directly。It doesn't need。Very well separated classes。

As much as if you train on a bigger landscape scale data set like E。

So here are the features again from the same Cy 100 dataset。

Pretrain on a larger data services implemented。This is a Vi transport freetrained on。

But the features are on site。And they saw that。The clusters are very well separated。

the more well separated are the clusters。The more likely is that you have a very good。说这代。

Something experimental。And in the third case， they take this model and they perform additional fine tuning。

 as we would say， like supervised fine tuning of those model。Specifically for the industry。

So find tuning directly on Cy。And they show the least visually and experimentally。だって。么得。

AServised fine tuning。En enableables us to tighten these clusters。From babies。And as a result。

 to have like a better detector。So pre trade models。This is supervise between up and there。

Have helped us a lot。To start from a。A very good feature space。 And then。我度对嘅 email面。

More tight clusters。But the next question would be。How。You work and improve。The feature spaces。

 if you don't have。Sample label samples。Supervise all the detections that you type in the clusters。

To unsupervise。Which is what we will do using the clip models and the text encoder on。S。

So this is just some quantification from their results。嗯。may questions between the lecture？

Given a freetrain model。Like a visual pretrain model。How can we define all these score？

You take the distances or the cosine similarity。mean let's say the closest。

In distribution training set。foreign。the different。s number one。And number two is that。え。

pe you will see in depth in the exercise。That these clip models， because they are trying to text。

 are really reliable。detectors。Every train on larger ladies set。We have worked a lot in the lab。

With different。先把。As to how to leverage this。っでマ。The different cases。 So be if you are completely。

Unsupervised you have some distribution data， but you don't know their labels。So there we take this。

One nearest its neighbors on the feature space。From its best data to the industry。

The second block of approaches。Whether you have。Unlabeled in distribution data。But。

The label names for the to be。And then。Thanks and order from you。

And do these three different approaches。We discussed unency on the exercise。So for example。

 the first one was called Su label。Proability is very simple。You take the institution class names。

Produce。There。Thanks for Center's presentation。And you map your image from the training folder。

desire。So basically the same way you would do zero shot。E must litigation。You can directly do。

Or the detection。The maximum much probability over the。Over the different。的即。Different classes。

Last case， we show that。You don't need to find。The whole network， the whole visual back。

 which could even be a billion parameter model。You could just either use the bahala notice distance directly。

Or the variation of the maous that you receive from。That's called relative how movies。全然？also。

 another thing we saw is that you。We only do linear property。Of training the whole。

Instead's a fine tu the whole billion parameter after。And yet state of the art。

Last thing we have already shown。佢吔屎。How different pre training models？With respect to。

Let's how the different。Before these guys from 2021。So that they decide clusters。Le to a very good。

Lets fire。I believe。Ken years， neighbors， leanar probing fine。你说得。Tide the classster。

they distribution accuracy。The better the out。And they show these。Inner behavior。

a supervised case where you have the labels to train。因这个。That higher。And we even sold this。This。三。

Natural emies。Even without any tu， so here we have a chain。Based on the 20 years。でいた。

And here we have the out of the nearest neighboril so that the nearest neighbor similarity。

 we use it as all score。And we show that this idea is inner behavior is even true when you don't do any task specific。

放 you的。我哋。Those are very important。嗯团点。That's it for。

