# 马里兰大学【中英⚡深度学习基础｜CMSC828W-2020-Foundations-of-Deep-Learning】-p01-P1-Lecture-1---Deep-Learning-Foundations：-review-of-basic-DL-models-and-optimiza--BV15rpCz9Ed8_p1-

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_0.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_1.png)

You guys hear me Bill。Yes， yeah， yes， yeah， perfect。All right， so。

This is Foundations of deep learning course， my name is Joel Fazi and I'm very happy to be your instructor in this course。

 I hope you have had a good summer and I hope you and your family are doing well in these complicated situations。

So let's start， so today I'm going to first briefly talk about the structure of the course and also some topics that we are going to cover and then we'll basically dive into some technical portions of this lecture in terms of understanding basic deep learning models and optimization problem。

So first of all， this is an advance。Deep learning course。

 So you need to have some basic machine learning and deep learning background before taking this course。

 If you don't have such a background， I encourage you to first take some introductory course in machine learning and deep learning and maybe the next years you can take advanced courses in deep learning。

So topics that we are going to cover， these are pretty advanced and modern topics。

 including deep learning optimization， deep learning generalization， neural tangent kernels。

 lottery tickets， deep learning robustness in terms of adversarial attacks and defenses。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_3.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_4.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_5.png)

Then we are going to look into relaxing the IID assumption in terms of domain adaptation and out of domain generalization。

 we spend a couple of lectures on deep generative models， VAEs， GANS， flow based models。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_7.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_8.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_9.png)

And their mean Max optimization problems will spend a lecture on self supervised deep learning and a few lecture on deep reinforcement learning。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_11.png)

And we'll have one lecture on Ats and transformers and LSDMs。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_13.png)

Visian deep learning， explainable， deep learning， fairness。Graph neural networks， meta learning。

 federated learning privacy analytics so as you can see this is a very long list of topics these topics are very important and modern but in order to be able to cover these topics I definitely need your help so you need to read the papers that we are posting for each lecture before the lecture so I cannot emphasize it more that it is very important that you read these papers before coming to the class and some of these papers are pretty technical so in order to be able to digest these papers you should start reading it you know a couple of these before the lecture so don't wait until the last hour before the lecture because in that case probably it will be hard to understand and digest the concepts and techniques of these papers。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_15.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_16.png)

So another thing is that these papers and topics， it's a tentative list。

 so we may add or remove some of the topics along the bay。

 and this is the first basically draft of this course so we'll see how things turn out。

In terms of the questions， I don't want this course to be a monologue。

 even though we are in a virtual setup， probably most of you have taken some other courses with me。

 I like to get questions and have some dialogue within the lectures so you have two options。

 one is to use the raise hand bottom in in the Zoom or you can just post your questions in the chat box and I'll read your questions through the class and try to answer them。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_18.png)

Any questions so far？

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_20.png)

。Okay， good。 so let's look at course info。

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_22.png)

As I mentioned， I'm the course instructor and well have three amazing Ts for this course， Aya。

 Neha and Muk。They'll help me and you know you in different parts of this course， the topics。

 you know， it's basically the same topics that we saw earlier。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_24.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_25.png)

Lectures will be online so I'm recording these lectures and after each class I'm going to post these lectures。

 but I strongly encourage all of you to participate in these virtual lectures because as I mentioned I like to have a lot of Q&A type conversations during the lectures。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_27.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_28.png)

So office hours， my office hours will be right after Tuesday's lectures starting next week and TA office hours will announce it shortly。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_30.png)

In terms of the background， as I mentioned， this is an advanced course。

 so you need to have a strong background in linear algebra probability and optimization。

 and also you need to have some basic background in machine learning and deep learning。Otherwise。

 it will be hard for you to follow some of the lectures that you'll have。And obviously。

 you need to have some programming backgrounds in Python。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_32.png)

So the course is going to be heavily project oriented。

So we are going to have a mini conference in this course so how does it work so students that are going to form groups and similar to some other machine learning conferences will have a double blind submission and review process。

So basically。Each student also will act as a reviewer。

 so you will review three submissions in a double blind format and everything should be in a double blind format。

 otherwise there will be a heavy penalty on that。And each submission can have up to four students。

 so we encourage for you to form teams and collaborate with other students。

 I understand it is a little bit difficult especially since we are in a virtual situation。

 but we have Piazza that you can post your problems or projects and then see if other students are interested in joining your team。

So one thing to emphasize is all deadlines are final and we won't extend it because the deadlines are cascaded so if we extend one of them it's going to be hard to adjust every other deadline so here are the important dates for us the beginning of October you need to form your team and you need to select the topic a project in a week we are going to give you a feedback ups or downs and。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_34.png)

The first week of November， there's an abstract submission deadline so you'll post your abstracts and within a week of that you will have your full paper in ICML format。

And then the review period will start right after that。

 youll be assigned to three papers in groups and youll review these papers and after that we'll have a rebuttal period so we'll reveal these reviews to authors of the papers and have them basically write responses to the comments raised by the reviewers。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_36.png)

And after that we'll have a couple of days for discussions among reviewers and after that ACs。

 which would be my TAs and myself， will finalize the scores for each paper and also evaluate reviewers。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_38.png)

So we'll have another part lecture describingcrib， we already shared the Google sheet for you to sign up to  lectures。

 I'm going to basically share the notes， these scribe notes after each lecture so in addition to having the videos for the lectures you will have access to some scribe notes from the lectures。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_40.png)

In terms of the exams， we'll have only one exam and that is in fact required because this is a qualifying course。

 we'll have one final exam， it is take home and it will be on 3rd of December。

So in terms of the grading， we'll have 10% for the lecturescribe， we have 25% for the final。

 40% for the paper score and 25% for the review score。

 as you can see it is heavily project oriented 65% of your grades will basically come from the project and also the reviews that you'll be doing for other papers。



![](img/c7612ae3a665b1c11e4ede9fe7208ac4_42.png)

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_43.png)

All right so that is it for the course introduction if you have any questions I think it's a good time either to raise your hand or post it on the chat box。

Okay so I see that you know there's a conflict for some of you for office hours， you know。

 this is a very big class so it is very hard to find a time that works for everyone but I will try to some weeks I'll try to change the timing for my office hours so hopefully with high probability all of you will be able to attend in some of my office hours。

All right， so there's another question， what is the typical team size you' are expecting for the project。

 it is up to four， but we have。

![](img/c7612ae3a665b1c11e4ede9fe7208ac4_45.png)