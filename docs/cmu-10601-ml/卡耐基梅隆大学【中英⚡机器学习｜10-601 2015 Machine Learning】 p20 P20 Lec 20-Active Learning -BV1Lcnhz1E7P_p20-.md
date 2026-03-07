# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p20 P20 Lec 20-Active Learning -BV1Lcnhz1E7P_p20-

Okay， cool。 So today we'll talk about active learning。 But before doing active learning。

 I want to mention， first of all， So just a reminder at home number six is due on Friday and also your project review is due on Monday。

 and it's a reminder that you guys should definitely talk to your T A。

 yeah each of you has a mentor T A。 definitely talk to them。😊，And get them to help you， okay？

Cool and actually one comment what I want to make。 So some some of you asked me。 So when I did SVM。

 I didn't go for the derivation of the due， but I did post lecture notesds by entering。 I mean。

 you are welcome to read the derivation of the due， but you are not required to know it Okay。

 just because I think it's beyond the scope of the course。If we're curious。

 you can definitely read it and talk to us about it。Okay， cool， so talk about active learning。

 But I want to take a mini before doing so to talk about to to come up with more general remarks about semiupervised learning。

 which is what we talked about last time。 so I mean。

 both active learning and semivised learning we discussed and motivated by the for most modern machine learning applications such amount of such massive amount of data basically it's impossible to have humans or experts to annotate or label all the data for our learning task at hand。

 Yeah and so this is a motivation I mean that's why a lot of the research。

 a lot of exciting research in modern machine learning has been on designing learning techniques that somehow most effectively utilize all the available data。

 but somehow in the same time minimizing of expert or human intervention and semiupervised learning and active learning are two topics that have been well studied and there has been significant progress and are exactly trying to achieve is to somehow best utilize available data but minimizing it for expert intervention。

😊，and I just want to spend a couple of slides summarizing semiupervised learning。

 just a quick reminder of semiervised learning ge。 So in this case as typical we have some source of data we have a distribution of the underlying data and we see it in the training phase in addition to a small set of labeled examples which are drawn IID from the same from its underlying source and labeled according to fixed but non target function So in addition to this small set of ID labeled examples we also assume that the algorithm gets to see large amount of unlabeled examples coming from the same source。

😊，Okay， and the goal is typically is to try to find a classifier。

 that has a small error rate with respect to points that come from our underlying source。Okay。

 so that's a typical super a typical goal only do machine learning and we whether there is a distributional learning scenario。

Okay，And last time we discussed that what， okay， what unableta can do for us， right， in this setting。

 right， when unableta can help us in drastic ways is in the case where somehow our inductive bias or belief about the world。

 involves not only beliefs about how the target function looks like， for instance。

 is a linear separator。 But when our inductive bias also involves beliefs about how the target function relates to the underlying data distribution。

Okay， but the the moment un unable that can become helpful in very， in very substantial ways。

K we discussed three， very different types of technique。

 three different very different types of semivis techniques that people have looked at that are based on very。

 very different assumptions about how the target function would relate to the underlying data distribution。

Okay， and just take me two minutes to go for all of them。

 It's interesting to see all of them on one slide。 Okay so the first one is the semi supervisorvised Z algorithm。

 which is due to to and newas。 And here the underlying belief is that not only the target function separates say positive examples from negative examples。

 but it does so by large margin and and when the corresponding optimization problem。

 we talked about it is what we do if we see we have as input a small set of labeled examples。

 also lots of unlabeled data。 And what we do we just find the classifier。

 but gets the label data right or almost right。 and it trying to maximize the margin over both labeled and unlabeled points。

😊，K that's transactive as E M or semirovvisised E。 And it's based on the belief or the assumption where the target function does not cut through high density regions of the space。

 In other words， has a large margin。Okay， Vto belief a different Vto belief it makes anta informative。

Now， a different， very， very different type of belief that makes unable informed。

 I'm gonna skip to the third one here is a belief that underlies the codetrain learning algorithm。

 Okay， and we've been released in detail last time。

 So here we think about problems where we have two natural set of features right。

 for our problems like for webage classification might use the word inside the web page for classification we might use the words from the hyperlinks pointing to the web page from different from other web pages。

😊，Right， so here， right， we are thinking about So in this code learning world or multi learning world。

 We are thinking about problems So we have two very natural types of features that are somehow sufficient for correct classification principle and consistent agree agree with each other。

Okay， and we've seen that if this is underlying belief about the target function or the target function the underlying data distribution。

 then conceptualion is speaking in the iterative code training view。

 unlabeledta can then help us to propagate learning information from one view to another。

 right or we can also think about So we iterative code training view we can also think about just doing direct optimization This is like just one shot optimization where we can do which try to find a pair of functions H1 and H2。

 which would get the label data right and to agree as much as possible on ala data or get almost all the label data right and agree as much as possible on unlabeled data。

😊，this was something to make a comment last time when I talked about a few article guarantees for this work。

 I said that， well， the initial guarantees are above the case on the when the underlying distribution satises the independent given the label assumption or the expansion assumption。

 But actually， this is not needed for code training to to be useful。 So actually。

 when you have independent given the label or expansion。 and code training provides drastic benefits。

 We need only constant number of label examples to learn well。

 but actually code training is also useful is the distribution is less nice。

 maybe the cluster of distribution each individual satisfy independence given the label。

 when it's still helpful。 We need more label samples， but the code training idea is still helpful。😊。

I just don to make this come。 like last time I already talked about independence giving the label。

Okay， cool， So a different belief， right So this is in the code training world here。

 the belief is that we have these two views each agree with each other。

 and we are in principle sufficient for correct classification。 And when Alita becomes helpful。

 And as you can see， this is very， very different from the margin based type of assumption。

 So the large margin assumption which underlies the transductive SM。😊，Okay。Now。

 we also spent a little bit of time in last time talking about the very different type of assumption。

 And actual Travis will go for visitation in more detail。Very different and very interesting。

 actually， widely we use class of semiupvised learning algorithms are those based on similarity based semiupvised learning algorithms。

So here the somehow you assume that we have us input a similarity function。

 And let's assume that our similarity function is so good that we believe that similar points must have similar labels。

Okay， now this makes unbeled time informative because what we can do。

 we can create a graph where all the points in the graph。

 all the nodes in the graph are my data points。 Most of them will be unlabeled like the green ones over here are unlabeled。

 but I'm also gonna have some labeled onces。 Okay， and then algorithmically， what I do。

 I I will try to partition the graph。😊，In a way or all the points of the same label。

 like these two blue points going to the same part。 And more。

 the weight across the part is minimized right， because like the belief。

 the underlying belief is that two similar points must have similar label。

 So if I have an edge between two points and these that are similar。 So when I partition the graph。

 I want to make sure that I have very low weight across the cut right in order to satisfy the underlying belief。

 a similar points must have similar labels。Okay， so this， as you can see。

 And there are very interesting ways very interesting types of partitioning algorithms for doing so。

 yes。😊，In the self consistent rooms case。If the rule is like only 90%， correct？Yeah。

 then you use it toag to the next。 Yeah， multi Yeah。

 So that's actually right So I mentioned this a come of M last time， right， youre on here。

 but I made this comment。 Yeah， is， I know him so well。 He always ask the smartest question。

 So it's easy to notice when he's not in the room， but。😊，Yeah， in any case。 So right。

 So I did say that last time， So that's actually one of the problems with iterative co training right So and so yes。

 so when you do iterative code training， you couldn propagate kind of once you start propagating wrong information。

 you might basically you might not be doing so well。 And actually when I as a student。

 I did some experiments with this And you can show that know for a while。

 like if you do it co training for a while， the error the combined classifiers goes down but at some point startss going up because exactly because of this reason for iterative co training right But I mentioned there are some guarantees you can give nonetheless。

 there are some concept classes that you can learn like interval in the real line or rectangles in high dimension。

 So those are concept classes that you can learn there are called from positive examples only。

 and there are the property But whenever you predict say positive， you are confident about the label。

😊，Okay， and so if you have such learning algorithms， we may not predictories。

 but might predict only is like a small fraction of the times。

 But if when they predict they are confident， then would be safe。Right， so。

 and actually we did have a paper。 I had the paper in ys or4，10 years ago。

