# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p19 P19 Lec 19-Semi-supervised Learning -BV1Lcnhz1E7P_p19-

Alright， so today we'll talk about semivise learning。And。

We started talking about this last time in the context of semi providersviss again。

 but we they'll talk about it more generally。EAnd in terms of readings。

 there is a very nice survey by Jerry Zoo that has a ancoia of machine learning。

 and I'll post on the website。Okay， cool。 But just to put this into context so for most of the classes you guys know。

 we've been talking about learning from fully labeled data， right This is for most of the class。

 except and in particular for most of the class， we've been talking about the distributional learning setting。

 So except except for a couple of lectures one lecture by one lecture by me。

 Tom had the lecture about semivised kind of name phase and also had a lecture bottom line learning。

 except for also lecture for most of the class really refer to distributional supervised learning setting where we assume that there is some source of data。

 for example， there is an underlying source or underlying distribution over the space of email messages this span section。

 And when we assume that in the training phase first， a random sample of。😊，Data。

 so first to get a random sample from the data distribution。

 And to assume that this random sample is first labeled by an expert。

And then so the learning algorithm gets a fully labeled sample。

 So gets an I D sample drawn at random from the underlying distribution。

But it available according to something that an target function。 Okay。

 what the learning algorithm does it outputs a hypothesisthe function。

 which could be like theory or a linear classifier and so on。

 And our goal was to make sure that the hypothesisthes function that we output has smaller rate or new samples that come from the same underlying source。

😊，Right， so this is basically the model we've been talking about。 and this is。this framework。

 we've been analyzing algorithms like knife base， logistic regression， SGM， other boost and so on。

 right， So we provided both algorithms on。😊，Efficient algorithm results。 And also。

 we talked about fundamental sample complexity issues， addressing questions of the type。

 How much data do you need to see in order to be confident that if to apply these algorithms like knife base logistic regression as theM other on the sample。

 when anti to put a classifier that has smaller rate respect to new samples that comes from the same underlying source。

Okay， so this is a typical the usual graphic supervised learning paradigm。

 Its been long study in machine learning。 And this is what we've mostly been talking about so far。😊。

Okay。啊。However， as I mentioned last time。 So this service has been great。

 This super fully supervised learning scenario has been great。

 A lot of progress has been made and lots of applications。 However， as I mentioned last time。

 this is this paradigm is basically institution for the modern than age of big data， right。

 And we discussed that most modern machine applications have。😊。

Massive amount of raw or unlabeled or unde data， right。 So， for instance， I mean， for really。

 for most machine learning applications， we have so much data that is impossible or hopeless for humans to sit down and annot of label to。

 according to our desired learning task。C， for example， there are， I mean， we comes computerization。

 There are huge collections of images on the Web， you know， there are all sorts of。Lots in many。

 many video sequencing like lots of video data， for example， from advanced cameras。

 where about cameras and phones。 So what's huge amount of data。 things I need to。

Of information extraction。 There are decents of pages on the Web， Also on computational biology。

 I mean data is acquired。呃，呃，利率。Defin， right to have so much data。

 And it's hopeless to have humans on talk。😊，And so that's why there has been a lot of effort and interesting machine learning in the past 15 years or so in designing learning techniques that most effectively utilize available data that minimize the need for expert of human interventions。

😊，Okay， and this been a major theme， machine learning。

 And today and next time we'll be talking about two paradigms with attempt to do this some。啊，你个仔大位呢晚。

Ex intervention mainlyly today we'll talk about center learning。

 and next time we'll talk about interactive learning。And。

We are actually learning paradigms where there been great both at the algorithmic level and。

Exact this is for issues。 How going mess most effective will be available data or available data。

 but maybe。Ill like prevention。O。And。We've been for this last time。

 but just to be against concrete and specific。 So in the semisvised learning scenario。

 So in addition to a set of labeled examples drawn a random from the underlying distribution。

 So in addition to the typical channel where first random sample of examples is labeled by an expert。

 according to our target function。 So in addition to this set of in addition to having a small I set of labeled examples drawn a random from the underlying distribution。

不要是信用法。The algorithm gets to see a large。Set of unlabeled examples thrown them from the same underlying distribution。

 Right， in addition to this typical channel， we also see assume where the algorithm gets to see a large I sample from the underlying distribution。

Okay， and when the goal of the algorithm is again， to output a classifier with has smaller rate of respect to the given unknown target function in the respect of the given unknown underlyingline。

Ca of it's formerly the the model， basically in addition to random labeled samples。

 the A also gets to see a large I D sample from the underlying data source。

 and the gold remains the same as before to with a classifier of smaller。

Very systems for learning use。逼当嘅。Okay， and as we discussed。

 this has been a major topic of research in machine in the past 15 years with lots of activity。

 Many methods have been proposed。 many celebrity papers。

 lots of workshops There have been even books written and surveys other topics。

 So lots of great activity has happened on top in the past 15 years。😊，And like。

 it's one of those topics that has both widespread spread applications and nice foundational understandings。

😊，And。So let's go。And。O， in terms of the class today， what I want to do。 So last time we。

 we already discussed the trans as VM algorithm， which is a specific type of semivis algorithm。😊。

And in terms of the class do what I want to do I to go through this。

3 major types of semi supervisorvis technique。So。I already mentioned last time。

 So one of them would be transactive as VM， and another one would be the co training method due to Abram and Tom and a different set of techniques。

 kind of the graph based methods。G basically mis supervised learning method。 Okay， they are all very。

 very different types of technique。Or somehow exploit the enabled data in very different。

 but also very interesting。And so I think they are all very interesting。 So that's why。

 I'm gonna go to each of them。And then I guess at the end of the lecture。

 I'll step back and try to think a little bit more high。 what is on。

 in what sense is unable to helping us because this will be all very， very different techniques。

 And we can think a little bit more。 I there a fundamental underlying principle people。

 but might time time foremost。😊，But you can talk about the opinion public。Okay。Right。

 and I think we are three of the major。Type of techniques that have been used for incorporating all and semi supervised learning。

 There are other ways in which a level that can be informative。 But for my lecture today。

 I'm mostly focusing on very aggressive methods。SoBut other ways， I can know like。

Srman's work or some even other ways。 But those are not aggressive。

 So I'm really focusing on my can very aggressively use unbel data。Allright。

 so let's go slowly through for them。啊。Cool， so the first one is and this something we already discussed last time and we discussed this last time because it was very natural given that we talked about SVM right before it。

 the very first one is a transactive SM method to I'm gonna actually before even were talking about this method。

 let me just mention just a little bit I mentioned it last time。

 But I mentioned again So in the semi supervisorvis in scenario at first。

 you might it's a bit puzzling or unclear with unbel data can do for us。

 right because somehow it is missing the most important information。

 really what we don't to do is to predict the label。

 right But unablebel data is actually missing but most important information the label， right。

 So when it's really unclear in what sense And when and why unable can help us。

 especially in substantial ways。😊，Okay， you can maybe see more minor uses。

 but if you want analytics to help in substantial ways， it' a bit unclear what it can do for us。Okay。

 and it turns out that。at a very high level speaking。

 then we'll come back to this later after we go for each of the techniques。

 So the very high level speaking， actual level that can help us if somehow we have if our beliefs about the problem or our inductive bias is not only about the core of the target function。

😊，But is are linear separatepar or decision team。And so on。 So like， anybody is helpful。

