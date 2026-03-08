# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p07 P07_W05.3_理解对比学习_MoCO与图像聚类_第3-3部分 -BV1RPZwB6EJZ_p7-

I think it starts。诶。Okay， one more note， somebody asked in the break。

 what does this information leak or？More collapse。呃。

So I will give a very simple example of a classification problem where we classify similarities。

 again， not pairish of similarities。系。And there is。If this is the anthtropy。で。

The entropy being 0 means that， basically。Zero entropy means that we always predict with 100% probability one of those classes for all lees。

So independent of the image。The output would look like this。

Which corresponds basically to zero entropy and then maximum enthtropy。诶。Corresponds to。

What is the maxsymmetricmetrically correspond to？Scattering the probability。Equally， uniformly。

So this would be。参户一啲。诶。So we saw that bus normalization can cause this kind of effects and in generate it's a very。

Critical issue that happens with representation learning。When you don't have this。

Human annotating label data， and you cant do actually supervised learning where you know what is the carbon and though。

All right。So now we'll talk about Es clustering。嗯。So let's start from the definition。Actually。

Let from， let's take a step back。Even consider why。We have a bunch of models， so different methods。

 we will see different pre training methods， pretext tasks， objectives。

And we ask ourselves the question。好。Can we evaluate？All these learned encoders and learn features。

What do they actually learn from this difference？Pre training models like Slar。

 Moco and many other things that we will see throughout the course。

So we saw already two types of downstream task basically。

Clasification was like the downstream task and we saw like two evaluations。

 so one was the linear probing and the other memory fors like this。

You don't need to train a linear layer。For its feature。

 you just take basically a K and N classifier using the features。So for one test features。

 you decide about its label based on the 20 closest neighbors， so you take the majority voting。

 you see what are my 20 nearest neighbors have。What's the major label， and this is the label。

And recently， this is a more established。Evaluation technique for re classification。

Rather than linear probing because it seems to indicate better the downstream data set。

In many other tasks like sematic imation object the detection。And so on and the other way。

doesn't include。Labels， so you still need the labels if you do linear a probate in the end。

 is even class。So。Demolasty is a task where。We know in advance how many labels we have on the data set。

 so a set of images， we know in advance that we have 10 different classes， but we don't know。

We team correspond to this class， so it's an unsupervised problem。And the。We will use this。

To evaluate different pretext tasks。And in general， to give you some indication。

Of the things you can do in practice in real life， real work scenarios。Of the how useful。

Is to learn some representations。Especially some such low dimensional representations。So for any of。

224。By 224。You have these。Modern。唔搞啲。And then you take some features head。That are。

Just 128 dimensions。So it's a much more compact form of the data of the initial data。

 so here the dimensional is 224 by 224， so you can imagine that the scale is completely different instead of working on the image space with suits our analysis to the feature space of the learned representations。

So do we all agree that these representations were much smaller in size， all right？嗯。

So it was classing is one。I's a very。Challenging task。

Even if we know in advance or a priori the number of classes that we know， for example。

 that Amazon consists of 1000 classes， but we don't actually。No， it's still unlabeled。so the。

The illustration that I saw about Mocollabs to either distribute the probability uniformly over these classes or predict one class with 100% probability for all the images in the data set is a very typical problem in Is class。

嗯。What else do we want to know about？Okay， it's a challenging task and the properties that。

You have these。Very hard balance to achieve。In在。What is， if we ignore the images， what is the most？

Standard。Machine learning algorithm that handles。Data cluster。Have一旦だ。Yeah， somebody said。オケケ。

So why not just use Canix here？Do you think you have something？So basically， it performs。

Equally to让东。So Ca means is an algorithm that cannot war。On images。However。You can apply。

You can use all the features。Of all your images in the training unlabeled training dataset sets。

 and you can apply KVs， this is the points that we discussed。活。嗯。

So what is the simple baseline for deep image clustering， so deep in front of he clustering。

 it means that there is this some deep learning model that produces some sort of features and then you play on those features。

诶。Before 2018。People use auto encoders and use this intermediate。

Or bottle make presentation to use this for I classing。And there are other methods。But他 really。

Specific to image clusters that try to train a model from scratchs。

 so they learning model trained from scratchs。To learn。Doますか。But in fact。At least in principle。

 even classroom consists of two parts， which is different from all the other data classroom methods that you can apply came in。

So first， we need to learn。The features。And then we want to predict。Mostly。

 not predict for the beginning as they learn。Since we have the correct features， for example。

 the foreground for this standard。Vi on benchmarks， the foreground would be like the object。

Usually in the center。So after we extract。The important features we want to learn。The assignment。

We want to learn the assignments of those features。To this priority set of K clusters or classes。

And this is achieved with representation learning， with de representationpresent learning MaxL。嗯。And。

Since we did couple events lasting with these two steps， even though we cannot use gamingings here。

Can indeed， apply K means。In on the learn features， so to learn the class assignment。

So this we covered， it's called the re scan。The training data。They do contrastive learning。

Then they take the features， the learn features， representations。And they do came。

And we also have some similar results in the lab。That， if you take。The best。

Publicly available pre trained models。You can have。

You can outperform all the other methods that used to do。诶 class day。In one step。So so far。

 we know that this is the best way to do。In my class even if came means。

 as you see in the right part。does not assign。Basically， it creates imbalanced clusters。嗯。

So the embalas clusters are not。A problem by himself。problemble is。That。During EMS classrooming。

 we have no idea about the data distribution。诶。So we kind of relax the problem and decide that all the data sets are。

Basically， all the。K classes are uniformly distributed。

So an ideal cluster that I algorithm would assign the same number of samples to each class。

And this does not happen with cave beanss。But it's very important to identify that we can。

AndOutperform all the literature that try to do。This in one step。

 this is what we call end to end clusterary methods， even though we still use deep learning。

 if you do these two steps together。呃。It's really hard。

And cluster degeneracy is the same thing we discussed about mold collapse either。诶。

For ten glasses you either have you predict probability。

1 out of 10 for of the possible clusters or for all images independent of the agreement you assign。

A probability of one for all events。So Cans is good but can we do better， this is a question。

 and there is this paper from a lab in the Netherlands。诶。This fanfu is a very deep learning world。

So they proposed astrology。That helps us。Learn the class assignments。So， of course。

Here we do representation learning with CLL or as we see more advanced。

Sophisticated approaches that perform better。Then。We compute。In the feature space。

The nearest neighbors for each immenses， because we saw in the first part of the lecture that there is this alignment that was both empiricality and hereically song that。

Vis of the same email。Tend to be together on the hypersphere。And。To some extent。This applies also to。

Ebody is set the same label。The problem is that these nearest neighbors。

 so if who consider them as pairs， they may be noisy。So here you see for example。

 the reference in us is the first column and it's four nearest neighbors。

 but in practice it's not always the case like that。I just want to emphasize that。We want to enforce。

The model to be consistent。So basically when we。We have a tip consistency， for example。

 when we take augments of the same image and we push them together， we enforce consistency。

Or invariance to the。Augmentations of the image while here we will try to group together to help make consistent predictions for two images that are neighbors in the feature space and it's really likely even though they are noise。

 it's really likely that they share the same label。So even though it's not。

These pairs are not like perfect pairs， like having the labels and group everything that has the same label。

 which achieve a perfect clustering accuracy。We group them together。And that's why they needed， like。

 another。basically京。They derive an objective to group together as nearest neighbors。

 and then they do another step。To kind of。Fix the problem that these nearest neighbors are noisy。

But we' will look cover this in terms of the next exercise。

So their objective is very simple here they have the。The dot product or the similarity。

With editing normalization。And the problem is that if you ignore this part that this term。

Will always。Collapse in the sense that well assign everything all the images to one class。

So the counteract base， this is what you would implement in the exercise。

 you not do the subject time， so we' will not cover that。So the second term is a very。诶。

He's a strict that's called basically。Enoperreization。

 so you have another loss function here with a hydroparameter。And this is nothing rather than。

Cross entropy between。Weically the average of the。The image is on the parts。So， basically， they。

They counteract with this。By pushing the network to distribute their predictions uniformly。

And that's why。This lambda is the parameter that controls this balance that is very hard to see。

 so you can imagine that it's very hard to find a good value for this parameter lambda。

So the bottom line is that we have two lost terms， the second one tries to avoid collapse by spreading。

The predictions among the clusters and the first one pushes nearest neighbors together。

So this is our referzi， these are the nearest neighbors。And this is the。

The average of the batch of the reference。We denotation。

 but in practice we just take the average over the minibu。And they show。Some quite good results。

On top of taking nearest neighbors， they also applied augmentations。

So mining nearest neighbors and just computing the nearest neighbors and then they also apply augmentation to those images and they show。

Significant performance improvement。So this may indicate。得诶で。

The layer that is trained on those representation is also。Able to model some additional。

Augcumentation based variances。And this relates to the fact。That。They use this。This features。

They didn't use the best available models。But it's still a significant improvement， so came means。

 even though it's a good baseline。Subop for images and even for images for learning features of images。

So we ignore the such likely step and I just want to show you the improvement。

 there's a tremendous improvement over。Ca meanss， which is basically a nice approach。

And they also make some studies， for example， how the nearest neighbors。诶。Inlu the accuracy。

And they saw that it's not really sensitive to the number of neighbors。

So basically if you have good neighbors，' if you have a good model that groups together images。

 it doesn't matter if you take 20， 30 or 50。嗯嗯。So basically keep these thread here。

For different days。Another thing about clustering， I was also wondering a couple of months ago。

 how can we say how can we argue about accuracy since we just predict some clusters？

But how do these clusters correspond to the ground rules labels？So basically。And same with。

10 different clusters。So these are the clusters。And these are the I call them ground truth labels。

So for training， you don't need any label supervision， but for the evaluation。

You need some supervised validation or test data。And those they are labeled。嗯。

So how can we achieve these mapping？诶。From 10 different clusters。

 how can we find the optimal solution from how these 10 clusters map to these ground truth labels？

So there is a small trick here， we assume that this number is the same。

So if you assume that this number is the correct number。

 so we know in advanced the ground truth clusters there is。It has two names in the literature either。

 the linear sum assignment problem or the Hungarian Latintting algorithm。诶。So， given the。

The ground truth labels and the cluster it finds。The mathematically optimal one to one mapping。诶。

This algorithm is not related to deep learning or machine learning。

 it's just that it's really important to understand that we need this mapping。

You know the learning is not the solution to all possible problems。 So for example。

 this algorithm even though it's quite complicated that provides some resources， it's good to know。

诶哎。But in the end， we can have some measure of。Accur。

 so the accuracy is only possible because we learn this mapping。

And you can find more information here。This is some work in the lab。

 which is basically some additional answers we did here in the lab basically。

For a presentation learning， we have these text tasks， we learn these models， these encoders。

 So how do they perform。On Evas classrooming with。The initial question is like how maths label related information exists on those。

我得。So we have this fancy plot。And so for the purpose of this analysis。

 we ignore all the blue points which are like supervised return models。

And we see all this area here on the X axis is the classroom in accuracy of K means on the learn features。

And on the Y axis is a method that we proposed as an alternative to Qcan。

And the distance from the Dutch diagonal shows the improvement or kidneys。If you take the payment。

 we want to see that we have some。Significant improvements over scan as well。诶。

And you will also implement parts of those loss functions。

 loss of the tumor loss function of scanning， along we call teacher asem mutual information。

Baically it' based on point wise mutual information。诶。So we take two。A couple of different things。

So during the scan algorithm says that if you have the training data like Spher。

 you do selfsupervised learning with SCR on those data。

 why we argue that if you use the only existing publicly available pretraining models。

 they learn much better features than the ones， if you train a model yourself from scratchs on those small scale data sets of。

50000 or 100，000 images。So this is the first difference。And and then we focus on deriving a better。

 let's say， loss function that groups together instead of the scan loss which you have this parameter to control the balance。

So what you don't。Collapse to。诶。Assigning all class， all the images to one cluster。

And this is the loss you will also implement in the exercise we will ignore this part。

 I just want to connect。The same trick we talked about with moco， the symmatization of the laws。

 we also used it here and many methods adopted this。吹。So basically， you have embeddings。

So here you have the Iaz and here， you have the nearest neighbor which corresponds to the nearest neighbor in the feature space。

 then you have like only one head， just ignore the multiple heads now， we have one head。

 which is like the student head as corresponds to the substrate for the student and the teacher and we apply T through case softs。

We use a temperature of 0。1， so we increase a lot as I saw in this animation。

 the confidence of the output。On the self market。And then we have this loss function。

And you can imagine that the first time is similar。

 the denominator is similar to the first loss of scan。

 where you have this probability distribution and you have a top product。

It's exactly the same as they do in the first lo them of scan。

The devices of the denominator in our case。Is an exponential moving out over the teacher。Predictions。

And this。This time is also。From to。To collapse， assign all the probabilities in one class。

So we derived another hydroparrameter， so we。These term to the power that's called beta。And。

For Vita between 0。5 and one。Basically， we take more into account this term because here we raise this。

诶。This dot product of probability。diistributions， predictions， whatever。

 we scale it down by raising it to the power， so we kind of upweigh the average assignment of class probabilities from all the past iterations using these exponential and moving average。

我から。I guess it's a lot。Any questions about these two methods？Okay， we trying to ramp it up。

And basically， I just want to say that this is the last slide we are the first one to see。

So this is a supervised。Classification accuracy on EvensNe。

 these blue lines indicates only models were trained on Esnet so without external data。

So it's compared to what we did。So the state of V art is something like 90， 91%。

W scan was at 40% so without having the labels。Theyve gap。呃。Was from not 40%。29%。And with our method。

 without using external data， we managed to push the I to achieve in the end， 61%。

 which basically bridges the gap。Between those methods， without labels and without external data。诶。

Okay， I understand it's a lot， we will wrap it up。Any questions so far okay？We take something。

