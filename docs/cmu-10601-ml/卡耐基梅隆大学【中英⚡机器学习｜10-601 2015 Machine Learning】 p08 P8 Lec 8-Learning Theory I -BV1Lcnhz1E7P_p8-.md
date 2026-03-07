# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p08 P8 Lec 8-Learning Theory I -BV1Lcnhz1E7P_p8-

Foundations of machine learning and in particular we we've seen lots of algorithms in the class right and we've heard words like generalization guarantees and simple complexity。

 And we promise you guys that the algorithm that we talked about can be shown to work well or new examples come from the same source right So we talked about these things in the past today we're gonna demystify what those things mean。

😊，Okay， but and I'll actually talk very specifically about simple complexity for a very specific model that we've been talking about for class name supervised learning。

 Okay， but before doing so， I just want to give you just a one slide overview。

 bigger picture overview about what machine and if theory is about。 Okay， so more broadly。😊，Right。

 so I guess we are talking about foundations of machine learning。

 and that's why have a speedrait here for foundation。Okay， and so right。

 so what machine learning if you already study。 So basically。

A number of very important aspects of machine learning。

 So the goal of machine learning theory is to develop analyze models but help us understand what kinds of tasks can we hope to learn and from what kind of data and also to help us think about what are the key resources involved。

Like running time or data， the amount of data that we need to learn， okay。

So the goal number one here is to understand to develop models for understanding what kinds of tasks can we hope to learn and from what kind of data？

Okay， let's go number one。 Go number two of machine learning theory is to prove guarantees about practically successful algorithms like we've seen in the very first lecture。

 the ID3 algorithm for learning decision trees it's a practically successful algorithm and we might be interested in improving when does it succeed and how what is running time of the algorithm and the root condition does better than other algorithms and so on。

 right so if we know when to choose an algorithm does on another。

RightAnd let's go number two and another goal actually I think which is kind of important and interesting is so machine learning is a very dynamic field is incredibly vibrant it has changed quite a lot in the last 20 years so I'm always new learning paradigms。

 new new environment like for example， we have the age of big data right now So we have to design often new algorithms for new learning paradigms that will meet certain to these are criteria right and we need to be able to reason about the correctness of our algorithms and how to better how to trade off the resources involved。

😊，Okay， so it's very important to have principles to reason about ci in order to get when useful algorithms。

Okay， so we what machine learning theory does in a nutshell。

 and so it's very important for the success of machine learning。 Now， if you like math。

 also another nice aspect about machine learning theory is that it is connected to many areas has use in machine learning theory。

 you use tools and connect to many other areas。😊，Including we've seen the class algorithms。

 obviously， probably in statistics。 we've seen this a lot。Optimization， again。

 we've seen this complexity theory only improve harnessness of certain。Guarantees information theory。

 game theory and so。 lots of cool connections。Right， and。So it's very interesting intellectually。

 too。And the field itself is very vibrant。 So it has its annual conference， conference theory。

 Actually， last year， the conference was in Barcelona， and I chair the conference。

So that's kind of cool， right， So it has down sound annual conference and actually even more。😊。

Actually， some of them the general machine learning conferences like NPS and ICM L。

 a good fraction of the works in those conferences。I mean， not related to learning theory。

 So for many new learning problems， people propose and what does it they analyze， you。

 they often want to provide some guarantees Okay， so that we can be more confident that they are useful。

Okay， cool。 So that's just a high level of what the machine learning theory is about。😊，啊。Today。

 I'm gonna， as I mentioned， I'm gonna be very specific。

 and I'm gonna connect what they've done in the past in the class。 So namely。

 I'm going to talk about sample complexity or generalization guarantees or how to prevent overfiing for the problem of。

Supervised classification。this what we've been talking about so far。I mean。

 that what I'm gonna talk about can easily extend can be easily extended to function approximationlam more broadly。

 right where the output values might be real valid， for example， like in regression in last time。

 Yeah， but for simplicity and just to be concrete today。

 I'm gonna mostly focus on supervised classification and in fact。

 I'm only what I'm going talk about today， I'm only going be for binary classification or I have two labels like spanm or not spam。

and right then basically my presentation will be about sample complexity。

 I'll define very precisely in a moment and what I'm going to present is some very basic but core results that stem from the statistical learning theory framework of a and path model of vian。

😊，in addition to my slides and my presentation， you can， if you want to learn more about this。

 you can read Chapter 7 of Tom's book， which is very nicely written。And。Yeah。

 and if you want to see more， come and talk to me， take my learning your records and so on。

So lots of resources。Good。And by the way， please feel free to interrupt me any time。 Okay。

 so I tend to speak little a bit fast。 So slow me down if necessary。Okay， cool。

 So we're gonna talk about simple complexity for supervised classification。

 And I'm just gonna start with like in the next three minutes or so I'm gonna do a very quick review what supervised classification is just so that we are on the same page。

 I'm sure we are all experts by now， but just to start slowly。😊，Okay。

 so I'm thinking about problems where basically here's an example of a supervised classification problem。

 we are trying to decide to write a computer program to help us decide which email messages are spam and which are not spam right。

 and so this is supervised classification because the algorithm uses is labeled examples。

 So in this case， email messages labeled as spam or not spam。😊。

OkayAnd right so here we want to write the computer program to help us decide which email messages are spam and which are not。

 And from the point of view of today's lecture， what is really important is that we really want to come up with a prediction rule but does well allow new examples on future data。

 not only on the training set， obviously。Okay。And。You all know this by now。

I mean this is informally the problem but the example of a problem it an informal definition now in order to design a learning algorithm。

 the very first thing we have to do is to design a set of features for our problem right like we have to represent our data by using a certain set of features and I have here a toy example for the spam problem right so here I can use for example。

 the features based on keywords， spelling characteristics and so on and here I picked five features right and so I have a small training sample of I guess seven messages。

 seven email messages So this is the unlabeled part of my examples right we are my features for this example and this is a label part of my example for example。

 this example is not a spam。😊，呃，预买的。给。Right， and now given， so let's say that this is right。

 this is our training set。 now， given this very simple training set。

 if you think about it for a second and moreover， if you think about， yes， here as being。Like。

 if you think about yes， is being one and the no is being0 like on versus solve， right。Then if。

 I mean， you can just quickly verify that， for example。Oops， let me go back。 So for example。

 we can verify that we rule over here， which is we're gonna predict spam E two times money plus  three times B S。

-5 times loan is get 0。 So we can verify that we rule。Right， but with expand。

 if these quantities get over 0 and not spa Otherwise。

 you can verify this rule perfectly classifies our training set。给。

And I'm sure that you guys know by now， because it in linear separators a lot。

 You can also notice that this is actually a linear separator。 right。

 So this is a very specific decision rule is。😊，Is basically given by a linear separator。

 telling a separator， a linear decision start。行。So this could， for example。

 this could be something but maybe the logistic regressionggression algorithm that we talked about might output on this set of training samples。

OkayNow， of course， you guys know that now we we care about not only doing well on the training set。

 but we also， what we really want to do is to do a new examples that come from the same source。

 that our through go。 right， And so it's actually a good moment to just basically mention again。

 we've mentioned it several times。 that I'm gonna mention it one more time。

 is's particularly important in today's lecture。 so I want to mention again。

 But the two core question that we care about in machine learning at the following So the question number one is the algorithm design question。

Okay， so weve studied this a lot。 What， what is this， what this is about is。

How can we automatically generate rules that dwell on the training set。

 So how can we come up with fast algorithms。That come up with rules， like this one here。

But do well over the training data。Right， and there've seen quite a few algorithms。

