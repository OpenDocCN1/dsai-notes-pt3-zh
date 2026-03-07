# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p09 P9 Lec 9-Learning Theory II -BV1Lcnhz1E7P_p9-

嗯。I guess a couple of brief announcements。 homework number 4 is out has been posted on Monday。

 and I guess Will has homework number one gra around here。 so you guys can pick it up。嗯。Great。

 so today we're going continue to talk about sample complexity results。

 So we've already seen this several times。What's going on with my。Okay， just a second。Okay， cool。

 so we've already seen several times in the course。

 But the two key questions that we care about in supervised machine learning are the algorithmm design question。

 How can we。Like， how can we。Design computational efficient algorithms that dwell over the training set。

 So this is question number one。 and the question number two。 And this is the focus for last lecture。

 and the question number two is sample complexity or confidence bound Orization guaranteeees question。

 which is asking how many samples do we need in order to be confident。

 but the rule but as well over the training set， were also dwell in the future。 So in other words。

 how many samples do we need in order to not overheat。

Okay and we talked about this last time and we and as I mentioned last time。

 in order to even ask this question， we need to have a precise model right and onetra what we talked about is a classic distributional learning setting which is captured by the statistical learning theory framework of Ani and the Pa model of V and I'm just going very briefly in three minutes reviewed what we discussed about last time and then go on from there。

😊，Okay， so。In this model， we， so I guess for my class today。

 I'm gonna focus on supervised classification where the label space is discrete。

 Even it even think about it as being binary for today's lecture。 Okay。

 and so we think about classification problems。 For example。

 the type to classification email messages as being spam or not spam or some other image classification task and so on。

😊，So， and the， the motor that we have in mind is as follows。

 So in these distribution learning scenarios， we assume that there is this there is。

Some underlying probability distribution over a space of uned examples。 So in other words。

 all our examples come from some source。Right， so we have some distribution of the space of un examples。

 For instance， about the space of email messages。 if you want to do expanded action。

And in the training phase， first， a random sample， a small random sample。

 V examples are labeled by an expert。For example， as being spam or not spam for the spam detection problem。

 And when with random sample is given as an input to a learning algorithm。

 which then produces hypothesis function or a classifier。

But is then used to classify new subsequent examples。

 that would come from the same underlying source。Okay， right。

 and what like my classifier my output say could could be like a linear separator。

 right right on my algorithm My output could be like a linear separator in the case of logistic regression or decision tree。

 if it's the I D3 algorithm and so on。Right， so that's Victoriactorial the model。

 and let me write it also a little bit more formally in this models I assume that we have a feature space right so for example。

 it can be R。 so we have a feature space and we have a distribution D over the feature space。😊。

And we assume that in the training phase， first， a small sample， random sample。

Done re from his distribution is labeled according to some fixed， but non target function。Okay。

 so here， the distribution D is fixed， but unknown。Right， or the space。And we assume that。

In the training phase， basically， we first get to see a small random sample。

 So we get to see examples of the form X 1， label of X 1， X 2， label of x 2 and so on， X M。

 label of X M。Right， and we you assume that all these examples like I are drawn independently and and they are identically distributed from the underlying distribution D。

 So there are I D examples。Okay， and we also assume whether they labeled according to some fixed。

 but target function， C star。Okay， and the go， I mean， what the algorithm can do， obviously， just。

 it can just do some optimization about the given sample。

But the true goal of the learning algorithm is stop with the hypothesis function。

 But that's all new examples that come from the same underlying source。Okay， and so formally。

 we discussed about this in detail。 What we care about is outputing a hypothesis function H。

 but has more error rate with respect to the underlying distribution and the underlying hidden nano target function。

Okay。And by notion of error， it just mean this very classic0 and error or classification error laws。

 which just， which is just defined as a probability that my hypothesis H predicts differently from the target function on an example that comes the random from the same underlying source。

Right， and do you solve at Victoria， We can think about it that way。Okay。

 so that's the true goal to output put a hypothesis function with a smaller rate with respect to the hidden amount target function and the underlying distribution。

Now we also discussed this in detail last time in order to hope to achieve any generalization。

 in order to hope to do any learning， right we saw a small number of labeled examples。

 we need a bias because there is no free lunch like we can never get something for nothing and within these frameworks the statistical and if frame or called the Pa model。

 the bias is expressed through a hypothesis space age。Right， so what we imagine is that we。

 we imagine that we are fix fixing a hypothesis based age。

 like linear separators or decision trees or your favorite other favorite。Hypothesesis space， right。

 And then the implicit hope is that somehow the target function is close to some function in the hypothesisthesesis space。

几。And actually， there are two cases to think about。 So the first case is a simplest case from， from。

 I guess， formal point of view from from it simplifies the math quite a bit。

 So the simplest case where。We see what we have been so insightful that indeed。

 the target function belongs to my hypothesisesis space。 So that's called the realizable case。 Okay。

 and then in that case， we right， So thats a simpler case。

 And the case for the target function does not belong to the hypothesis space。

 It's called the agnostic case。 But even then the implicit hope is that the target function will be close to some function in the hypothesis space because this will only be our search base。

😊，Okay。And we also talked about this for this hypothesis， for this bias to be useful。

 We need to ensure that somehow the complexity of the hypothesis space H is not too large。

 if H contains all the functions in the world， then this is not a very useful bias。

 So're gonna fix a space H whose complexity in a certain sense is not too large。Okay， cool。

 So that's the formal setup。 Now， again， So recall， we use label samples。

 Dont random from the underlyingline distribution。😊，Right， labeled according to some things。

 but an non target function。But our goal is talk with a hypothesis function with as well or new examples that come from the same source。

Now。Right down our hypo function， small error rate。And again， we discussed this last time， obviously。

 because we don't know the underlying distribution and we don't know the target function。

 there is no no way for us to actually measure the error rate of a given hypothesis precisely。Right。

 that's something we cannot compute precisely。But instead， what we can do。

 we can compute the empirical error or the training error of any given hypothesis function， so。

The empirical error is formal written on the slide， right， and it is defined as。Anybody volunteers。

 So what is a training error of a hypothesis。See it on the slides。

 but maybe somebody can help me out。What is in particular of a hypothesis age。Make sure。

The train get， yeah。It is the number of samples that So we are trying to。Do have the training sure。

And。can that we see how many of thes are exactlyact so and will normalize it by the number of training samples。

 right， So we get a fractions。 So training errors is just a fraction of misclassified examples。

With the hidden target function。 Okay， yes。What happens okay， good some evaluation。 take on here。

 I'll try see if it's possible。 Okay， cool。So， right。

 so to really care about is outputing a hypothesis function with has small true error rate。

 But we cannot measure that instead of we can measure the empiricalical rate of a hypotheses。

 which as you are。Most stuff I said is just the empirical error of a hypothesis is just the fraction of training samples that our hypothesis misclassifies。

 Okay， so we can measure the training error and but our trigger is to guarantee something about the true error。

 And so it turns out in order to do so， we can use sample complexity statement。

 So what sample complexity help us do is to relate the empiricalicular error of hypothesis H with the true generalization error of a hypothesis H And what they help us do so uniformly for all our hypothesises in the hypothesisthes space。

😊，Okay， so we thought sample complexity results can help us too。Yeah。

