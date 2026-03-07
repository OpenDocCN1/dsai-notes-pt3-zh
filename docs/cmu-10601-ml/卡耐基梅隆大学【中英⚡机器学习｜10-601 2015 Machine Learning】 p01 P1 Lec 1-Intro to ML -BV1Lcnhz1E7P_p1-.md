# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p01 P1 Lec 1-Intro to ML -BV1Lcnhz1E7P_p1-

Okay， well， welcome。You're in the machine learning class。Which is 10601。

And there are a couple different machine learning classes this semester。

 So if you think you should be in a different machine learning class and you accidentally came to the wrong one。

 my feelings won't be hurt， but this is the one we're in right now。My name is Tom Mitchell。

 I'm one of two professors who are going to be team teaching the course， The other is Nina Balkkin。

 and I'll introduce her and the other TAs in a moment。

 but I wanted to just start by welcoming you and saying a few things about machine learning。And。

If I can， I have a new laptop computer， and I'm still debugging my own skills for using it。

 So every once in a while， you'll see odd things happen on the screen。So like this。

 what's this about？And。It's not even on my screen， but that's okay。

 So machine learning is a subject close to my own heart。

 It's about the question of how do we build computer programs that automatically improve what they're doing through some kind of experience。

😊，So to have a well defined。Problem in machine learning。

I'd say we need to have three things specified。 We need to have some performance task that the computer is performing。

And some metric for what it means to do that better or worse。

 and then some kind of experience from which the program can train， so for example。

 you're very familiar with spam filters and you're probably aware that spam filters are trained using machine learning。

 so if we took that as an example we'd say the task。Is to。

Take an arbitrary email as input and produce a label spam or not。That's the task。

The performance metric we would like to optimize， I could make up several random spam filter programs。

But there's some performance metric that， for example， you know what your own spam filter。

 your own notion of spam is。 And so theres some。If you were， for example。

 to label a set of emails as ones that you consider to be spam or not。

Then we could say our performance metric we might use to make well defined learning problem is to match as closely as possible。

The labels that you've assigned to the emails， that is for the program to learn to match as closely as possible your own labels。

 So that would be a performance metric。And the type of experience， Well。

 it could be just what we said。 It could be the experience the program is going to learn from is a set of labeled emails。

 This one's spam， This one's not spam。 Here's another spam。And so， there is an example。

Of a well defined。Machine learning problem。We could make another one also with spam。 We could say。

 for example， we could change the performance metric。Maybe you。

Don't really want to minimize the number of errors the spam filter makes compared to your gold standard。

 Maybe you actually。Are more worried about losing a good email。Inter your spam folder。

 then you are about accidentally looking at what is actually spam。

So you might actually have a slightly different performance metric that you'd like to optimize that gives a bigger penalty。

 if the program accidentally labels non spam as spam， than if it does it the other way around。

So that would give you a different， again， well defined problem。 We also could change the experience。

 So， for example。So far， we're talking about training a spam filter by giving examples of emails with labels。

 spam not。Some computer programs， and we'll learn about them this semester。

 can also take unlabeled examples。Unlabeled emails。As additional data。

And there are algorithms that can perform better learning algorithms that can learn better if they're given both those labeled examples and a whole bunch of unlabeled email。

Which seems kind of like magic。But by the end of the semester。

 you'll understand what's the principal underlying that？And， in fact， what kinds of situations。

What kind of formal structure a problem could have that makes unlabeled data。

Be actually useful for training a spam filter。 And spam actually is an example of a。

Of a problem that has the structure that makes unlabeled data useful。Okay， so theres。呃。

Roughly speaking， what we mean by machine learning。

 we could make up a lot of examples of machine learning problems and characterize them this way。

We talked about spam。 We could also talk about。Self driving vehicles。

 S we want to make a self driving vehicle。Learning system。It's going to， for example。Learn。

 given the camera and other sensor input， it's going to learn what direction to steer and whether to step on the brake。

So that' would be another function， actually， just like the spam filter was a function from emails to labels。

Here， my robot would be a function from sensor observed data to recommended。Control actions。

So let's see if we wanted to make that a well posed problem， then we'd have to say what the task is。

 I guess I just did that。 We'd have to say what our notion of performance is。

Maybe we want to get you to school to class， to CMU on time for noon。For class， in every case。

 no matter where you start out。And the fraction of times that you're late for class would be the penalty function。

And what kind of experience Well， again， we could。Do that several ways， but the。

Most supervised kind of experience you could imagine would be if we trained the car by actually driving it。

And letting it observe our own steering and break commands。While it was also。

Perceiving the sensory input。 And that way， it could。Construct a large set of labeled examples of。

 here's what my sensory data is。 And in this case， the person。

 the trainer did this steering command and this brake action。Get a large set of that。In fact。

 if you're training in car， I recommend that kind of training instead of say。

 letting it drive randomly and crash into things。 But you could imagine， again。

 there are different variants on how we could set that up。Okay。

 so that's machine learning in a nutshell。 It's about how do we build computer programs that perform some task and improve their performance in some well definedfin metric。

 according to some type of experience。So， during the。Yeah， good， I see what's going on here。嗯。

So let me just quickly go through a number of examples of problems of the type that you will。嗯。

Be covering algorithms that you'll be familiar with by the end of the course。 So， for example。

 one common use of machine learning methods is to do what people call data mining historical databases。

One example could be medical records。 this slide describes a project we did with McGee Hospital here in Pittsburgh some time ago。

 which has a large database of medical records for。Babies being born。And from that historical record。

They have many examples of。The medical state of the mother during the nine months leading up to the birth and then an indicator about birth。

 and they were interested， for example， in whether the birth would happen as a normal birth or as a birth that requires surgery called a ceessarean section。

And so this slide just shows an example of using machine learning to learn rules that characterize in this case if you're a prospective mother and happen to have these three symptoms。

 then your chance of having a surgical birth instead of a natural birth is 63%。

 at least in their database， so this is an example of mining historical data structured data in this case。

 structured in the sense that，The data is described by a set of fields with values。Unlike， say。

 images or sounds。Whiever。We'll refer to as unstructured data。

