# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p22 P22 Lec 22-Learning Representations -BV1Lcnhz1E7P_p22-

talkk about。An interesting topic about learning representations or learning later interesting representation of the data。

 Its so the discussion will all be based on unsupervised learning。

 and we'll cover a couple of plastic techniques for learning representations。

 namely PC A principal component analysis and also kernel PC A。

 And I'll just mention in one slide of I C AE。😊，Another common technique to learn laptop。

But it's a bit more advanced。 So I'm not going go for details there。Okay， cool。

 So what's the motivation， Well， as I guess we all know by now。

 So the data these days is engage of big data。 we have massive amounts of data。😊，And actually。

 not only we have massive amounts of data， many， many， many data points。

 but also in many interesting applications， the data is very， very high dimensional。Right。

 so actually， I have on my slides， a couple of examples is actually， these are even older examples。

 a couple of years old。 So even there could be even better example these days。 But。

 let me go for a couple of them， So for example， if we went to the document classification。

 we could use say the classic representation where you guys know。

 name the bag of words representation where for each word in the English dictionary。

 you have a feature， right So then we would have thousands of features。 Okay。

 but people do natural language processing nameing NLP， they use even more features。 So for example。

 it's also common to use so called the so-called bygrams。

 which means for every pair of possible adjacent words will have a feature。😊，Okay。

 and then we're going mark down if that pair of adjacent word appeared in our document and how many times and so on。

 right， if we use pairs， if we use diagrams as features， then suddenly we have millions of features。

And even if we then augment with other type of contextual information。

 the data becomes even high dimensional。 Okay， so what's an example of the data is super high dimensional。

Okay， another， I mean， another example。 So some of you did the the Netflix is time。

 some of you are trying to do the Netflix for the project。 And also， for example。

 in the recommending recommender system。 And I'm sure this data is old。 by now。

 we could have at least half a million users。 and they could rate， say， about 20000 movies。

 So here you can think about having about half a million examples in 20000 dimensions。Okay。

 or so that's another example where the data is reasonably be high dimensional。Or if you are doing。

 say brain imaging， which is， for example， some spectrometer is doing。

Then you could potentially measure the brain activity in different locations in the brain。

 And you might be doing so at say half a millisecond， right， So when you get very， very。

 very high dimensional data。😊，Okay， or even even the image data。

 right if we have very high resolution image data， it's also very， very high dimensional。 Okay。

 so basically today， we have in the modern age， basically we have massive amount of data。

 And often the data is really， really high dimensional。 And so in this context。

 it's useful to try to learn some insightful but low dimensional representation of the data。Okay。

 and this is exactly what we're gonna talk about today。 So the topics that we're gonna cover today。

 PC A， kernel， PC A， I C， A。 So these are powerful and supervised learning techniques for extracting hidden potentially low dimensional structure from this high dimensional data sets。

😊，Okay， and why is it useful， Okay， why this be useful， so。Im already mention。

 I kind of implicitly mentioned why it's useful， But maybe do you guys want to volunteer to come up with a few reasons。

 I think hi dimension hard to process and。There a lot of competition。 But if you。you。

Look are nice temptation， and。But perhaps in a more meaningful reet。Excellent， okay， so your name is。

Se Sean， okay， so Sean already came up with a great reason。 Okay， cool other reasons。So one。

 one particular event he mentioned is computation， Right。

 So like it could be better use of resources or in particular running time， right。

 could also be better use of other resources like memory， right， you requires， I mean。

 if you upon the dimensional representation， you need less running time you you can run a faster algorithm。

 right， and you have need potential the storage， more efficient memory。

 from memory point of view and so on。 Yeah， other。And the海底东讯の。啊，对他 might be。Thispa。ItIt will。

Much harder three weeks。You extract features from。Right。

 so it might be difficult to visualize or to understand if it's very， very spas。

 living in high dimensions， might be very， very difference difficult to make sense of it。 Okay。

 there are algorithms that do that that I should say there is a whole literature called compressensing or some other algorithms that we didn't talk about in the class。

 like we know we do a regularization。 So there are some algorithms that for say。

 for supervised classification that target it to dealing with very high dimension of sparse data。

 Yeah， There are some algorithms。 But another approach is to somehow try to find the meaningful structure that high dimension in sparse。

 Maybe we can find first meaningful structure and well run or favorite algorithms。

 Right So with a different approach。 Yeah yeah。😊，経臣だ。Someud structure on high direction。我的得说。こした。

Yeah， we sold kernels do， right， I mean， so you could also go the other way around， yes。Yeah。

 but the topic today is to imagine if that we live in very high dimensions and there is a good structural or dimensional data set。

 I mean， it could be， as you are saying， it could be sometimes it can go higher， its even better。

Yeah， but the topic today is going in the upper direction。But you like， I mean。

It's not universally true， but if you project。Things， or if you， it's not universal。

 but in all dataset， there is a nice， lower hidden dimension structure。

 I'm just saying that in some data sets in meant and actually quite a few data sets， that'。

 that's the case。Okay， cool。 So okay， so let me also just basically summarize some of the reasons for which you want to do that。

 right So right if we somehow are able to find insight if somehow even very。

 very high dimensions data intrinsic in a very high dimension space。

 But some of it is a hidden and lower dimensional structure。

 It might be useful to first recover a structure。 potentially using unsupervised learning and might be useful for several reasons。

 So one of them is as Sean mentioned， if we do so when can use more efficient when you can make can be more efficient from running time point of view from a point of view。

 all computational resources involved even communication point of view。

 if we are in distributed Comp systems and so on right So basically bottom line。

 we can make use more efficient have the available computational resources that's one main reason。

 Another reason actually maybe can and this is some reason that many people like。

 we can visualize better the data sometimes is good to。😊，Standard data， also。yet another reason。

 actually， is， well， somehow， if we managed to in extract fewer dimensions that capture the data well。

 we might even also get a better generalization better statistical properties because we often know。

 okay， very roughly speaking， but the number of samples we need might scale with the dimension。😊。

Okay， so that's another reason。 And actually， another reason。 actually， is also。

 sometimes when we apply some of these techniques， we eliminate noise because the data might be living in a low dimensional manifold only linear a sub space。

 but up to some noise。 And somehow maybe after we do this some of this。

Dality reduction or learning representation techniques。 Maybe we get rid of that noise。

 So everything becomes nicer。Okay， and right， in general， like many， if we do PC A。

 if we manage to do effectively PC A or I C A， then we get lower representations of the data。

 and in general， all the ma learning algorithms can be run more efficiently。

 like we can learn clustering or regression or supervised classification more efficiently， right。😊。

G of its being， it's very useful to try to do so， basically。Lots of benefits。哎，可了。

And I'm going go through the classic techniques for doing so。 And actually， PCI is。Maybe the， the。

one of the most basic techniques for doing so。 So it stands for principle component analysis。

 And I'm just gonna have one slide high level description。 And when I'm gonna go for more details。

 So rather is speaking， what PC A or principal component analysis does。

 It's an unsupervised technique。 So only uses un labelbeled examples。

 And it's an unsupervised learning technique for extracting。😊。

Structure from a high dimensional data set。 And by structurally， we mean variance structure。

 We want to capture and to find the low dimensional subspace that captures as much。As possible。

 the variance or conveyvari information of the high dimensional data。Okay。

 and so another way to say it PC A is an orthogonal projection or transformation into a possibly lower dimensional subspace so that the variance of the projected data that subspace is maximized out of all possible sub This we might choose the same dimension。

😊，Okay， so this is rapidly speaking what PCA is。Okay， and let's go for a couple of examples。Okay。

 so for example， so let me go through the simplest possible example。

 which is this one here on the left。 So here is an example of data lives in two dimensions。 right。

 So intrinsically， so it's two dimensions。 And actually those So the first dimension is this one。

 So first feature is the second feature。😊，And。