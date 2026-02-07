# 吴恩达@斯坦福大学《深度学习｜CS230 Deep Learning 2025》中英字幕 - P3：Lecture 3_ Full Cycle of a DL project.zh_en - GPT中英字幕课程资源 - BV1J1x4zoEVK

![](img/2755254d033f8dd62623b4bbc2720a27_0.png)

![](img/2755254d033f8dd62623b4bbc2720a27_1.png)

So what I like to do today is chat with you about the full cycle of a deep learning project and as I promise in the first lecture。

 rather than me talking at you for an R in 20 minutes or whatever。

 would'd love for this to be much more interactive。

And so what I'm going to do is illustrate this in an example， but also。😊。

Asked you a bunch of questions along the way about what you would do if you are the one working on the project I'm going to use as an administrative example Okay so plan for this to be quite interactive and please interrupt anytime and ask questions since I think that's why I want to do this in person here at Stanford。

嗯。So。One of the reasons why developing machine learning or deep learning or other types of AI projects。

 including AI projects using large language models or agent AI workflows or whatever。

 is that AI projects are different than traditional software engineering projects。

So one of the biggest difference between AI projects of the many different flavors， civiled learning。

OwnB， you know， Gen VI base is that in traditional software projects。

 you write code and you control your code， right， write whatever code you want， compile it。

 your code does what you tell it to。But AI projects。Yeah。You know。

Involve both code as well as data that you train your algorithm on， and you almost never know。

What strange and wonderful things there are in your data？For example。

 if you're working on a face recognition application that's a running example I'm going to use today。

 then as you're just getting started on the project。

 you actually it's really difficult to know in advance what you find in the data is's the lighting of the face is good。

 do you struggle where people very long hair or people short hair do people making facial expressions make your system struggle。

 do people wearing glasses， make your system struggle So data is so rich that a lot of the time you can't predict in advance what your AI system is going to do。

 not because you don't control the code， you can write whatever neural network or whatever code you want but you don't know what's in the data。

 and this is why unlike traditional software engineering machine learning development is a much more itative process where you just have to build something see how it works and then through a process discover almost discover what is in the data and therefore what you should be doing to change your code。

Make your overall system perform。And this is also true， this is true。

 not just for deep learningbased systems， this is also true for modern large language models if there's been a lot of hype buzz about how OOs large language models are hard to control I think there's a lot of excessive hype about that kind of fear among being there's a little bit of that but one of the reasons why none of us know in advance what OMs do is because it was trained on a lot of data。

 more data than any human could possibly look at and we just don't know you know with precision what is in all that data that the arm was trained on and so because we don't know the data we can't really look at all the massive tens or trillions of tokens of data was trained on is hard to know exactly how large language model will perform。

Which is why building agent Genga applications or building large language models based applications is also very empirical or very experimental。

 meaning you just said to build something then see where it goes well。

 see where it goes poorly and they use that to fix problems and that's how you drive progress in sense so because you control your code but you don't really know is how to control the data and this is true both of the data you have stored in your hot disk you know kind of I don't know。

 terabyte the data stored in a hot disk I don't really know was in my hard disk。😊。

And the thing you really don't control is what data the world will give you in the future。

 so we deploy a system in the world， say face recognition we should talk about well people wear a thick heavy scarf that covers part of their face when it's winter。

 you just don't know there are all these things in data that will surprise you and you don't even control your past data that's already in hot as you certainly can't control your future data。

So it turns out that a lot of machine learning classes talk about。Building models。

And you learn a lot from the online videos about how to build powerful deep learning models。

But it turns out that building an overall machine learning system or a deep learning system。

Has a lot more work than just training models。 but if you look a lot of causess。

 there's actually a very strong focus on modeling because I think that's what acadeia has focus on right we can train models。

 evaluate models， published papers on models and so you find that a lot of courses focus on know training a good deep learning model and that is absolutely important。

 but because we know how to evaluate models， different research groups can benchmark different models lot of academic research work on that that's reflecting a lot of causess。

 but this is just a small part of what you need to do if you want to build an effective deep learning system and what I want to do today is go outside the small box of models to give your a broader view of what it feels like to develop a deep learning or AR or machine learning system。

And。is what it often this is what building a deep learning system。Would be like。Which is first。Yeah。

お。可以。Spspecialize the problem， figure out what we you're working on the running example I want to use today will be to build a face recognition system or face Re system for security。

 for deciding when to unlock a door and then you know Kia and talked about some face recognition which I believe face face architectures last week as well。

 but specific application going to talk about this is something I've worked on actually I built one of the commercial systems that that for this is。

😊，Yeah， this is a door。You know this is well you or a friend or maybe someone that you don't want to lead in approaching if we have a low camera。

 sorry bad drawing take a picture of whoever's approaching the door and decide whether or not to unlock the door right so face recognition to decide whos authorized enter like a restricted location like corporate office building or your holes or whatever and actually one common use case that one of my team's built was a key swipe keys so sometimes keycards gets stolen and so one of the systems we deployed you know fairly large office conflicts is was if you swipe a key we also just take a picture theres then student is called it to make sure that the key is helped by the person you know whose face is shown on the key so it makes it harder is someone to steal a key to gain unauthorized access to like an office complex so I'm going to use this as the motivating example for today。

And after。Especially on your problem。Tical process， then。はい。U。

Sometimes the open source models can download， but let's say for today that the open source models aren't good enough if you want to train your own model。

 but simple process we get data。You know。Design a model。没有。Tade model。And then we will iterate。

A fewD sets a bunch of times until the model looks like it's performing well enough。

And then after that， we have to deploy it。Yes。嗯。でし。Yes。嗯。Yes。And mon maintain a model。 Okay。

 so Im actually gonna to talk a bunch about multiple of these steps today， because I want you to。

Come away with a feel for when you're working on a real machine learning application。

What the important steps you will face are， right？嗯。And so， as I alluded。

Machine learning development is very a process。 So for these three steps。

We often drive a rapid development loop。Where we。没有。Is sorry。Yes。Design the model。Trainated。Okay。

Analyze the results and it may be design or update the model or the data or something and iterate around this loop many times before you are satisfied slide。

And all right， just one more detail， it turns out that for face recognition。

 the very common architecture， what you learn in detail about later in the online videos is a neural network called a Siamese network and what that does is a neural network that takes us input two pictures。

And two pictures get fed to a neural network or a deep learning algorithm。

And it's a job at the deepbuing algorithm room to tell us。

 are these two pictures the same person or different persons because if you're trying to set this system say for your hos and maybe you have。

 I don't know， a few family members or roommates you want to let in。

 then it's I don't know it'd be quite annoying if they retrain a neural network for every single home。

 so the most common way to do face recognition is of a neural network that inputs two pictures and the job of the neural network is says tell me are these two pictures of the same person。

And then the way you set of the system is input a few registration pictures So take a picture of yourself。

 take a picture of your roommate， take a picture of you know any family members you want to have access so then when someone comes。

 it can quickly check if the person that just showed up is one of the people that's authorized and then let them in and then the corporate key card swipe example if someone swipes a card and my card says this is Andrew's card then I'll quickly pull up my registration picture to double check if I am if I seem to be the same person as the Andrew that was registered so this is how。

This is a typical neuralia化。All right， so I have a question for you one thing one thing I'd like to do today is walk you through a number of scenarios and invite you to think about what decisions you would make if you are the CTO of a startup building these technologies right so so my question for you is。

If you're the CTO of a startuper building the next phase recognition system。

 and if your lawyers have said you aren't allowed to download data from the internet right so let's not download data from the internet for this application。

How would you go about getting data to train the system？ So what you need is。

A bunch of pictures of people。To train a neural network， to say， you know。

Are they the same person or not？So maybe take a few minutes to think about it and then I'll see if you raise hands and give some answers and one specific question I have as well is how long would you take to collect data？

The you start training a model。So I think。Well， you need to get data we design the model I guess。

 and then you need to train model， so what does the timeline look for you with specify the problem。

 you know， we design the model， how many hours or days or weeks which you spent to get data and how before you start running you know gradient descent。

I see a hand down。O， sureO。な。Next。现在该。はて。Let me leave it a bit more open ended。

 say you just graduated from Sanford and your CTO of a three person saws up building this thing。

That eventually hopefully you sell it all around the world。

 but your goal to just get started with the three of you working out of， Palo Alto， California。

And do it as your real self， what the reasons is that you have。All right。

 anyone want to venture an answer， so how would you get data to train the neural network？哥粉。他到是手么是。

我 like maybe我。This moment。好来，那被告补的时。那你只有签这个东。Yeah， cool video streaming services。

 by video streaming services， you're thinking like， you know， Netflix and Hulu。

 are you thinking like security videos unlike Zoom only that's see cool。Let say cool， cool， right。

 cool， right， with experience service。 How， How long do you think it will take to do that？呃。

我他不我个一个就是。按是应在是这个按1一。三都食。えクそ。这是个贵公。Yeah， good， right， cool。 Thank you， right， creative idea。

 Any idea ideas， How would you go about and get data。😊，我付人1。家先开 feel。て？Okay。There。是。でそいた。不买他见的我还。对。

Yes。Yeah， cool， awesome， right， stick a camera there。

 let people you opt in right to get the picture taken。够。I think I saw a hand up go for it。第七句。Sorry。

あの。I say， cool， how would you get users？结果对利是。That's it cool， right？Yeah， by your own people。

 you might like grab some friends and also they'll give you that LinkedIn photo give you some pictures from your camera girl。

 yeah， cool， I like that， that's fast， I like that。Any other ideas？Okay。是指标是不是。后续的是一些习能。Let's see。

 interesting， yeah， askll Stanford to send an email。Cool， right， I love Sanford。

 Sanford is a wonderful institution。 Also That's gonna take a while。😊，Really creative idea。

 I like the creative ideas。😊，So let me share with you one guiding principle for how I would encourage you to approach this problem with data collection I appreciate all the creative ideas actually one of the frameworks I often use to decide how I collect data is speed because。

😊，I find out。Especially you're building a startup。Right of in my opinion。

 one of the strongest predictors for whether a startuper will succeed and also whether a small innovative project in a large corporation。

 you can be a giant corporation， but it was a team of three working on a small innovative project in a big company。

 I find that one of the biggest predictors for the chance of success is just a speed of execution was just speed of things stuff done。

And so when I'm saving a team and brainstorming different tactics。

 I will gravitate toward the tactics that let me get the data very quickly and quickly usually means like one or two days。

 even if it ends up with an inferior， smaller lower quality dataset sets or whatever。

 because I don't really know what problems I'll see my data and the quicker I can get the data。

 train a model， see where it goes wrong， the quicker I can then discover what's wrong with my data and fix it。

True story chatting of a CEO that told me he once actually once he actually has spent I think was over $100 million。

 definitely more than tens of million dollars， spent a lot of money buying a company for his data and then he actually said。

 hey I spend all this money to get all this data you know can you help me figure out how to monetizes。

 how to make money off of this and I kind of look at boy I kind of wish hadn't done that and what I find is that the value of data is' just so difficult to know in advance what's important what's not important about data so for a lot of these tactics for example。

 I think student ideas is an interesting one but you know。Are student I photos weird in some way。

 right or are they too expressionist or people smiling too much in student I actually no idea。

 my standard I， I look really weird in my standard I。

OrAnd I think and actually like the idea of sticking a camera and just letting people come up and opt in and take a picture if you can do it quickly and I think in a big company or even in a small startup if it's important to respect user privacy or individual privacy。

 but if you can stick a camera in some place you know that doesn't kind of a what's the word invade people's privacy that don't want to be any part of this。

 but let people opt in take the pictures of permission if you can do that in days I find that to be valuable one the thing I' found for quite a few of my projects found that know Stanford students our community here is pretty consmopolitan with people from more around the world we're not fully representative of the world's distribution of people but we actually do a people from more around the world while Stanford people actually very nice so one thing I've done multiple times is when I need to collect data will go to places on。

ampus with high foot traffic。 sometimes like cafeteria is a very high foot traffic。

 And we just ask people， hey， were on the project。 Can I get a sample of your voice。

 can take a picture of you kind of really informed concern and tell people is okay if I do this I've been delighted how collaborative Sta are and I find that one thing I've often done is gone to my teams and said where two days collect data's like whatever is 1152 AM now。

 let's figure out what we can do by what day is it Tuesday Let's figure can do by Thursday 1152 AM So let's give us the 48 hours。

 let's brainstorm。 How could we collect data and it's find that the data isn't all there find that the data low quality but that velocity's us more quickly。

😊，Tade a model， figure out what's wrong with the data and then jigger or retweet how we collect data So I find that there's some teams that ask how can we collect the data we need and how long and then ask how long will that take that usually leads a much slower execution。

 I instead tend to go to my teams and say where two days or one day or maybe a week right some short time span like that and say what's the most creative you know respectful。

 responsible but creative a way you can use to collect data into short time span。

And one of the ways to think about that， too， is。Traing a model takes don' know let's say it takes two days maybe I should take more like one day right if you can train a model in a couple days。

 then I would not spend you know， like whatever， right two months。



![](img/2755254d033f8dd62623b4bbc2720a27_3.png)

To find data， to train them all though because then this becomes a huge bottleneck。

 because you can train them all relatively quickly， let's take a commensurate amount of time。

To design a model or design the data as train model and depending on how long it takes a train model。

 sometimes training model needs to run overnight， I actually see teams sometimes take one day iteration loops around this。

 the fast moving teams I work with we often go around this loop once per day for the smaller models。

 if we train a large air foundation model， sometimes training model takes weeks or even months。

 then the process can be different if if your model run is gonna be know two months。 then yeah。

 maybe it makes sense to spend a couple months to get the data really right。

 but for face recognition you could train that overnight or actually in a couple hours quite easily So it makes sense not to spend massive amount a time before you go into the train model that makes sense。

And。Because。Oh the what empirical means experimental right sorry I' used a word a few times a day。

 and I think we say that machine learning is very empirical process。

 meaning it's very experimental process。 we have to do it， see what happening inside what to do next。

 I know that sometimes others that criticize our field as like we never know what we're doing。

 we just try stuff and see what works。 and and you know there's a little bit of truth to that。

 I think understanding neural networks hyperpar architecture that is really valuable so we don't just try stuff at random but because we don't know what's in the data。

 we do try lot of things and then drive a dis process。

 understand what works and what doesn't and then use that to navigate forward。Does that make sense？

And then I'll just say there's one exception to the advice I'm giving here。

 which is if you're working on a project that you have worked on many times before so whatever I've built a bunch of face recognition systems so I kind of have a sense from previous experience and for reading research papers there's certain things I know it just not going to work if I have 100 images right so there's some face recognition systems I know I probably need at least 50。

000 images。Before you'll have any hope of working， so because of that prior experience。

 having gone through that loop a lot。I now have a basis to say okay， I do need 50，000 images。

 then I might invest up front and put more effort upfront to get those 50，000 images。

 but I think for most applications you work on for the first time。

 if you don't have academic literature to justify certain larger data investments or if you don't have the prior experience yourself。

 then I would focus on the speed of iterating around this loop。Make sense。嗯。All right。

 and to relate this to large language models based applications as well。A lot of us。

 a lot of you are probably， well， you may be building applications like prompting OMs and calling an API。

 like like an open eye or anthropic or Gemini or metaalma or whatever API to get things back from your own。

One of the reasons that too is a very experimental。

 very iterative empirical process is because when you write an OM prompt。

 you don't really know in advance how it's going to do because it was trained on data that none of us have really looked at and that too is why instead of theorizing for a long time about what prompt to use an OM。

 just try out and then as by doing that you then see the problems and then your focus can be on fixing the problems。

Sense。And in fact， there's a lot of discussion on responsible AI。

 how do make sure AI systems are safe or they don't have kind of unforeseen circumstances and because。

A lot of the theorizing， you know， you can only theorize so much。

 I find that if you want to build safe， responsible AI systems。

 one of the best ways to do that is to just build it。

And then experiment with it in a sandbox environment says don't let it all in the world until you've test it rigorously but yous go build something and then you know test it probe it in the safety of your own laptop don't let it and innocent users and have some weird impact on innocent third parties。

 but there's only by building and then probing it that you can figure out where can to go wrong where it' say inappropriate things would respond inappropriately to certain user queries and then that tells you where the problems are doing work on access。

Okay。系 yeah question。但是。中。127。Oh， sorry， sorry are you。So like when you。あまっ。はしと。他是。他。

Have you used that to figure out which one？这个。あ。Yeah right great question。

 So when you analyze something's wrong with your model。

 how do you use that to take the next step forward right that's a big topic that will talk at length multiple times in some of the videos and also in some future lessons but maybe long story short one of the things you could do is change your neural network architecture architecture you may realize that maybe the same example because in' working or read the literature architecture the other thing you can often do is change your data。

So data Sanric AI is the discipline of systematic engineering your data。

 the build of success AI system and it turns out that you build a face recognition system let's say I like your hat that hat and school but you let's say hypothetically you find that the system has really struggles recognizing people that are wearing hats then you may say all right I need to get more data with people wearing hats and so as often that looking at what goes wrong which we call error analysis that then gives you the insight to say oh。

 it works well on these types of data or these types of users but it struggles with these type of users into data so can I fix my data or get more data just on the subset of cases it struggles with and that's a very common motion there's a very common process but then driving the performance of the system and this is also why。

Blindly going out to grab more data will lily that's often not a good strategy because just too much data you get do I want more you know data with people with you know long hair or short hair or people with facial hair。

 sorry too much hair too many hair examples or you know don't want people with wearing a scarf covering part of the face or people that wear glasses where they don't wear glasses or people that you know are slightly turned away there's just so many different types of data you could invest effort to get more of that until you build a system。

 see where it goes well， see where it was poorly it's really difficult to decide where to get more data and just get more data of everything under the sun。

That's very slow and expensive。And I think part of the hype about the value of data has led people to have sometimes overly simplistic view of data right。

 you yes， of course I want more data， but just grabbing more data of all types of data is a very inefficient。

 very expensive way to improve my system。And even if you look at the way that frontier models are trained right now。

 it not a game of just grabbing more data of anything under the sun。

 it is identifying the subcagories where it's valuable to invest to get high quality data。

 which is why if you look at it turns out in AI there are two clear buckets of value in LMs right there's the general answering people's questions I think you openiIs doing really well there Gemini anthropic have momentum。

 but theres theing general questions and then one of the verticals is really valuable is AI for coding systems So I think you know qua has been ahead for a while but open AI you know I don't know Gemini 2。

5 pro some of the models are making really good progress in coding as well and if you look at the look at the work that the frontier teams are doing to improve coding building irerative agent workflows is part of it。

 but also finding clever ways to come up with coding related data is also part of it and if you want your。

To do better on coding， you don't grab data willing with low quality random internet chat。

 social media or whatever data right， but instead that having high quality coding related data is how you can have a focus effort to improve your elementsMS ability to code so a lot of these things are actually。

Oh yeah， yeah， I feel like the like more data is better， that is absolutely true。

 but it's also always simplistic， data is not monolithic。

 there' are subcasries of data and having a view on what piece of data to really invest in giving a lot more that's really important to being efficient and how you improve this system performance。

😊，Very friends。All right， we'll talk more about error analysis and this data， Any other questions？

Cool。Okay yeah， go for it。就给他们规章。中国这。好是。我。我的。Yeah。Yeah， right， so as you collect data。

 the quality of data matters a lot too。Which is why and I think data quality is。

Is tricky I think when building an application for the first time I would still focus on speed and collecting some data quickly。

 but as you then analyze where a system is going well what doing poorly。

 you often find that the quality of data really matters so。T to上 she told is now later。U。Com back。

 So so let's see。 let's go there。 Al right， let me， let me talk about L1。

 There's a lot of low quality random chat on the Internet。

 that's not that useful for training alarms， but I think， you know。

 this is actually now well known that if， if you can legally access very high quality。

Written author articles or books， they're highly edited。

 very insightful that's very high quality data for training homess and I'll give an example of later as well for face recognition it turns out that you know blurry images right would be a low quality and shop and focus images assuming that's representative of how you want to recognize people's faces so that really matters as well。

😊，All right， anything else。吼。All right， oh yeah， good friend。不是我给大家看。他もで。For example， in the space。

Sure。売し？And model just for object。I see。一共垂直。It's much faster。If I will ask。我是。Yeah， so right。

 just repeat for Mike， how important is it that the data collect is similar to the distribution of things you want to work on？

I think as important， but not as important as most people might think。

 So it turns out that it turns out one of the reasons neural networks have been so effective is because when you build a very large neural network you can throw all sorts of data into it。

 including data that is not perfectly tuned to your test set distribution and it often doesn't hurt So lot of your network is big enough so so you raise the example。

 whether we have it identify two identical objects right if it's genetic objects like don't know what the bubbles and markers maybe that's too far a you。

 but if we were to use let's say you know simulated cartoonish characters right that really different than real humans。

 my guess is it probably won't hurt。At all and may even hope a little bit。

 And so throwing in a lot of data if we train a large neural network with a lot of capacity absolute。

 even some slightly relevant data， it usually doesn't hurt and might even hope a little bit。

 but how much it hopes is another empirical question。

 that would be problem dependent and we often just have a try out。

 But I think maybe you know like in the past people used have an obsession that the data you trained on has come from exactly the same distribution as is usually you test on。

 that used to be how machi learning was done I don't know， like 1015 years ago。

 that's really not true today anymore。 I think we're very comfortable。

 And I think when when your networks were much smaller where it could train very small models。

There was a sense that you didn't want to distract the neural network with irrelevant data right because computer was expensive with few parameters and you distracted on irrelevant stuff。

 maybe it gets less good at the core task you really care about。

 But if you can train a bigger neural network， which is getting easier and easy these days。

 then is become much more okay to toss in some data that that hopefully isn't incorrect data。

 I think incorrect data with a problem， but just irrelevant examples or it's much less because big neural networks。

 is like a human brain right， I don't know the fact that。Whatever。

 the fact that I learned to play the piano， you know， probably doesn't make me worth it。

AI because because hopefully my brain is big enough to learn to play the piano and learn some stuff about AI。

 And I think as neural networks get big enough， they can learn some of the irrelevant things and also do well the Qs you really care about。

 But this was less true when if my brain was really small。

 then I don't know any our fans of Charlotte Holmes but I think Charlotte Holmes has an attic theory that your brain has only so much capacity you go to forget some stuff to learn new stuff。

 But when train very large neural networks， that's much less' true。Cool。All right。

 thank you for all the questions so what I want to do is just keep going through this flow right so we talked about your data design model trainer model we'll talk a lot more about error analysis later this quarter of how to figure out where your algorithm is still subpar and where to focus efforts improve it。

 but what I want to do is give you a sense of a deployment right。😊，So。All right。

So when you have trained a model is often a bunch of software engineering work to then maybe take your model hosting a cloud in a local server and have it run inference It's a very common architecture architecture for deploy machine learning model will be that you a neural network as a piece of software you deploy it。

 maybe on a cloud host a service so that your software can accept a picture or accept two pictures and reply back do I unlock the door or not this is in personal not So that's kind of bunch of software engineering work that needs to be done but in practical deployment settings I'll actually tell you it turns out that if you're building a practical phase recognition system。

 you probably find that if you are trying to unlock door to a corporate campus is too expensive or too slow to stream video 24。

7 to cloud to classify every frame at 30 frames per second to。If you。

 there's a person dead he should unlock the door floor。So in practical phase recognition systems。

 what we end up doing， actually right， so so actually let's take the example of someone walk out to the door to your home to your door at home and you want to see if there's someone there they should unlock the door for。

 right？😊，So。A lot of systems will actually have image on the camera。And then try to build a system。

All right。Right， so what we have so far。It's a system that takes this infinite image and maybe a reference image。

 neural network says。Do I unlock the door or not？But it turns out that if streaming video is too expensive。

 classifying every frame is too expensive will often end up with a system。Like this。嗯。反归なよ。

VAD sense of visual activity de。嗯。And what this does is a usually low cost lowpower inexpensive computer job to run to just very quickly maybe try to figure out is there a human face there。

 because it turns out actually if you're building something unlock your front door to you and your friends。

 if you look out my front door and my house like it's pretty boring know there's a wall we see over the street but nothing moves most of the time so there's very obviously almost all of the time it's very obvious that there's no one else on my front door trying to be let in and it'd be very wasteful to stream all that video to the internet for classification。

So visual activity detection is usually a low cost flow power system to just very quickly decide。😊。

Should I do the work？Of sending this to the larger face recognition system neural network that may be host on the cloud to have it do the much more computationally expensive work to decide you have 01。

 do I unlock the door on。Okay。So this type of。Optimization。

In order to make the system computationally feasible to deploy is fairly common and I'm going to give you two options for how to implement VD and I'm going to ask you to reflect on them and then tell me which one you would pick to get started Okay so option one。

Is a non machine learning based method。Which is。See if the number of pixels changed。Yeah。Yes。

Its greater than some special epsilon。Right， so if the camera stationery may be looking at the wall。

 most of the time， the pixels barely change because see all。 It's just a wall。

 And so you can read a little bit of code using。You know， some image library， like pill。

 Python imaging library or some simple read a few lines ago to just say。

Has the number of pixels whose RGB values that change more than sun threshold has more than 10% of the pixels change compared to what it looked like a second ago in order to see if there's anything in front of your camera to even decide to pass this to a more high part neural network。

Okay。Option two。Yeah。Yeah。Would be to train a small neural network。Okay。Okay。Okay。Yeah。是。Yeah。Yes。

Yes。Right so phase recognition is a pretty complex task you have to look at multiple cues and the face like at the eyes or the mouth the you know so that is a relatively large neural network。

 but just taking a quick glance is is there even a human in front of my door that's a much simple task so option two we' be trading a very small very low power very lightweight neural network to just very quickly tell you do you think there's a human there。

😊，And then use this train model to decide， is it worth passing on to a much more powerful neural network running the cloud with a lot more resources to make the final determination。

Okay。So if you are the， again， CT， a three person saw the building this。

 how would you how would you start， we'll give everyone a few seconds reflection on this now。

Get people's attention， get people's thoughts。系啊。All right， go for it。包。

This where people walked by every。不知道。呃，是。It's a change from。おこする。

So depends on what have to that and we can also。每个字。す活かす。是月份。这有是。空有。It's very。やば空。去搞护。Yeah， right。

 cool， all right， just just repeating ourmic。 so problem dependent depends on whether you're on street Well a lot of people walking past maybe consider other algorithms。

 they're even cheaper than smaller on it。Co。你这。就是非常矛盾。是是吗？对哎。会会他时。we。比如说是。啊。

While we put data and then。被法问。Yeah， cool great。 So use option one in the short term and then maybe replace that with option two or we have more data Yeah Co is very。

 very。这个是你。Well home we to so far is very simple only if that to I we kind a thing to say。And in。

Oh oh sorry， so use both options， I'll put both in the pipeline。 Oh， that's interesting I see。

Al right， so see if option one， let option one， see if anything change， if something changed。

 then passes on neural network， that's that could work。😊，see。Yeah， cool， yeah。

 that could work so it could cascade in multiple steps。要て。这个是新这。回那个老。

你 very don't to worry about some。If it's more3。Thiss cool。修法位。

yeah right yeah so how expensive is it to run this neuralne in the cloud so actually so I would usually want to design both of these to run at the edge being on the device Oh this one。

😊，So it turns out that a streaming video is fairly expensive think。Yeah， I feel like boy。

 I don't have numbers of tip and fingertips， but I think running this 247 is not feasible。

 so we definitely need something to filter it down but sending， you know， I don't know。

fewew images every minute is probably not a problem。Okay。Yeah。なか。Oh， sorry。好。All right。

 sample times sample certain frame of the video in order to get all of them， yes， I guess so。

 yes although。Yeah， although I think if you have a video by front door。嗯。

You need a way to sample other than random， I guess right。

 because lot time nothing happens unless you take one frame per minute， I guess， which be okay。

 but then we don't want someone waiting there for a full minute before we find each get onto sampling and then sending it So yeah okay。

谢谢老师。This。是所。といワだ。不是。这 by。Yeah， could we use the same images for training this network to train this the option2 network。

 maybe so actually one of those things I would say where to try before we know it works might be doable。

 depends longer on what data to be collected to train the brain neural network。Yeah嗯。Cool。

 if else right just take a color while， ahead。你小。Oh。对。就在人的。All right。

 yeah how about use option one and keep a really low threshold so we send very few images is what we mean？

Yeah， I think would thatd be reasonable to try。Well， right， so we don't miss too many people。

 but yeah。Let's take one last comment， thoughll share a perspective on how。更新之こ的と社困で。所以是这个。

Yeah right yes， yes， so one of the weaknesses of option one is if there's a tree swingwaying in the background or if you see a road and there's a cause that driveries by or if it's a busyiest tree。

 the causes driving by all the time or when the neighbor's cat comes and visits those will trigger this right so those are downsides。

So let me show you your perspective for how we' approach this and what we actually do。😊。

If youre the CTO of a SA implementing this。To me， it again comes down to speed， right？

And so what I would ask is how long does it take to implement option one and how long does it take to implement option two。

 and I think everyone made good points about the pros and cons of these two options。

And if you're actually doing this， the approach I would take is， you know， just awesome。

What can I do really quickly so I can then deploy it and see whether it works and I'll fix it if it doesn't work because I think these insights like what trees swing in the background affect it you know it turns out it turns out that actually does probably but maybe not if the wind isn't that strong or but but it's really difficult to know answers to questions like these because you don't really know until you stick on a bunch of cameras in front of doors and see the data then you can get more confident and how we option one works I don't know how often does the neighbor's cat actually come by and if there's cause the drys pause on the cause usually so far away that it doesn't matter because the number of pixels but cars is small right so all of these are very empirical questions it's really difficult to answer and the fastest way to get answers is just implement something quick and dirty and run it see what goes wrong and they fix it。

So what happens on and tell you what the experience of a lot of face recognition teams is because option one is so quick to implement。

 this is like I don't know， five lines of Python of aim right get an o to write it for you want to write the five lines of Python for you so you can implement this in you know 20 minutes。

 maybe even less whereas this I think will take you at least many hours。

 maybe longer to implement So my instinct would be the start of this。😊。

And it turns out having built me face recognition systems。

 I'll tell you this actually doesn't work well enough for all the problems people raise and so we wind up。

Going to this， but implementing this also gives you insights into where it's going wrong and I'll give you one example of one insight that you know we and many other face recognition teams have。

 which is it turns out that when you're approaching a camera that's trying to recognize your face。

There are some frames that are going to be really clear and in focus and a lot of frames are really blurry right if just look at video。

 someone walking toward the camera， sometimes just you know when I'm stepping sometimes the velocity of my face is higher and sometimes it's lower right that's just what it is and so sometimes my face is in focus sometimes it's more blurry。

And it turns out that if you can select out the high resolution frames and feed that to face recognition。

 you get much higher quality results right so this is the kind of stuff that I assume you know most people would not know about until you work on the system like this。

 but it turns out that when I always work on the system like that。

 having a system to not just do VAD but also capture the video and then deliberately select not just one that maybe five frames to the high resolution and in focuscus of the person that actually gave a significant boost to the accuracy of a face recognition system and I mentioned this as an example of the sort of discovery that you have only when you implement one of these systems。

 maybe even implement this system but you implement a system you see boy we trying to recognize a lot of pictures from very faces。

 maybe you could need to do something about that and this is driving that empirical process that may then lead you to train in your network。

Both to see if there's a face， but also to see if the picture of the face is in focus to select out that frame for downstream processing Does that make sense and this is why。

You find there for some meaningful fraction of questions I asked in class。

The thing that's the speedest to do is often the right answer。

 because that obsession with speed really lets you go in and figure out what's in your data and improve your system more efficiently。

は。嗯。So。Right。So yeah， so what happens in practice starts with this。

 discover how it doesn't work because it doesn't actually work and tell you that and then figure out。

 but use those learnings to do this。这好。我们对中。个呃就是。こし。呢个个。あ。

Yeah so is there a sense of what is a good classification accuracy of problems like these iss actually really difficult one of the common benchmarks you learn more about this in the third module on the online videos as well is building machine learning systems is easier if we have a reference level of performance like an aspirational target accuracy which is often human level of performance and so it turns out that the way you diagnose biass and variants which talk about later in thiscourse is easier if you know what' an achievable level of accuracy and very often we' used by a human expert we could do as achievable level of accuracy。

And then in the case of face recognition， definitely under controlleded environments were better than humans。

 So definitely actually the AI systems we build are way better than I am and recognizing human faces。

 And I think AI systems are better than I would say probably the vast majority of humans。

 maybe all humans at this point at really distinguishing of two pictures of the same。

 And then and then then it gets really difficult。 then actually gets more difficult once they even better than humans。

 but those are。😊，Yeah， but but at least， but until you're as good as humans and on certain tasks。

 using a human level performance is often a good benchmark and then if you're doing something that even humans can't do well。

 like it turns out you recommending online books or movies or whatever humans aren't actually that good at that I think most of us have a hard time recommending good movies even to our closest friends AI actually probably does it even better than many of us do as humans then those things is harder to establish a baseline。

Cool。2。Now。One。😮，Final aspect。I want to touch on is after deploying a model to monitor and to maintain the model。

Oh。One thing that often happens is you train a machine learning model works great， you。

 does well in your training set， does well in your test set works great， and then you deploy it。

 and then annoyingly the world changes and your system no longer works so we sometimes call this data drift or concept drift whether the distribution of data the world gives you is different than what youre having a training set or concept drift。

 which is the input output napping， your X or Y changes in the world compared to your training set。

 but to ground is if youre training a face recognition system now in you know I don't know when it's not too cold here in California you get faces of a certain distribution but as we approach winter if it's say rainow people wearing scars。

 rainjaers， people look different or maybe maybe we approach next summer more people are wearing sunglasses。

Then the data distribution changes or if we train the system based on data here in California。

 but we then decide to deploy it you know， in a different country where peoples dress differently or where their appearance is different。

 the world keeps on giving us different data and so。One of the jobs of。

 I think us as machine learning engineers is to put in place systems that monitor this type of concept drift or data drift and fix problems as they arise。

When you're out building machine learning systems， I have seen a segment of AI engineers that think their job is a do well in a test set。

And so I've been in a bunch of these conversations where the machine learning person would say， look。

 I did one to test it， my job is done。But then a private owner or business owner will say， no。

 your system doesn't work， look at all the ways it does not work。

And then if the machine learning person says， well that's not my problem， I do well on the test set。

 I think that's not a constructive way to move it forward。

 so I encourage you to think of yourselves if you're building machine learning system。

 I think of my job as building something that works and that can be different then building something that works on the test set So if ever your work on a product and someone says。

 you know I know you did well on the test set but your system doesn't work。

 I would encourage you not to respond but my job is to do on the test set or encourage you to think about why doing well on the test set doesn't translate to doing well on the application that people actually care about and thenll lean in and go and fix that。

And one of the common problems for why doing one a test set doesn't translate to doing one in real life is that the data distribution changes in which case you may need to update the distribution of data you're training on in order to capture whether has changed in the world。

And。Just a few other examples， I feel like you know。The world gives us new data all the time。

 So if you're building a web search engine sometimes sometimes sometimes the new politicians is elected or there's a new movement or some new video goes viral or I don't know Taylorlor swift releases a new album I don't know whatever and then people are suddenly searching for a brand I thought I thought I get a lot from that no swift easier but then suddenly a lot of people are searching for a brand new thing and so the distribution of data you get is's different because the world has changed've done a lot of work in factories or there's actually a reasonable chance a cell phone you have in your pocket may have been inspected by software that my team's wrote but you know sometimes the materials change or there' a new machine is solve in an in line and this machine makes a new type of stretch in a cell phone so data changes in inspection lines as well or。

One thing that actually surprised me when were working on self driving cars。

 one of the team is working with， we trained a lot in data in California。

And then when we took the cost of Texas， you and I as people。

 we can drive just fine in you California or in Texas。

 but it turns out the traffic lights look really different in Texas in California right so it' traffic lights horizontal vertical。

 I think part of it is that they are very high winds in some parts of Texas So while traffic lights tend to be strung up differently to be robust to high winds and so traffic lights look pretty differently in Texas So the models we chain in California。

 they don't work in Texas because they get new data， refresh the data。

So a lot of that is a process of。Monitoring and maintaining the model。

 even when something in the world changes。And。Before going on to monitoring the model performance and maintaining it。

 one interesting。Difference in performance between this and this is。

Option one is a very simple model， right， It basically has one parameter， which is epsilon。

The fraction of pixels that change。And so this， because it's so simple。

 is actually very robust to changes in distribution， for example。

Say is hot summer and a lot of people are wearing sunglasses， you know， well。

 the fraction of pixels that change， right， even when people are wearing sunglasses doesn't change that much。

 maybe it was Halloween and people are wearing crazy large costumes， maybe that would change。

 But this is actually a very robust algorithm because it's so simple in contrast。

 if you trained on data with no one wearing sunglasses because it's not sun's not that hot these days。

 right， then with everyone starts wearing sunglasses， this is actually less robust。

 So one of the advantages a very simple， non- machine learningway systems is。

They may be less susceptible to data drift。Because maybe I tune this parameter epsilon to limit a data set。

 but even when the data changes， this tuning quite robust， but if I train a neural network with。

 say thousands or tens of thousands of parameters， then are'm more likely to have overfit to people without sunglasses so if people sold sunglasses。

 you're more likely to have to update this model。Greatい。And。If you are building a。嗯。Sorry。在购。嗯。bo。

If you're building a system。It turns out to be incredibly helpful if you can get user permission to stream a little bit of data back to your cloud host service so that respecting user privacy。

 being careful often， transparent privacy practices。

 I think that privacy is really important right so do be transparent and do the right thing for users and if you're able to do that and get a little bit of data back to your cloud to plot dashboards。

😊，And maybe one practice that I've seen is when building a high stakes application one good practice would be to gather your team together and get a diverse set of opinions on all the things that could change all the things that could go wrong and built quite a few machine learning systems and I found that when we sit down and brainstorm all the things that could go wrong。

 including the data distribution changes， I don't think I have ever seen something go wrong in real life that we did not identify as a possible problem I might be wrong but at least right now when we sat down we really brainstorm all things that go wrong。

 I think I have yet to see something go wrong that was not on the list of every brainstormed and so if you brainstorm and thats true for safety critical applications well right it turns out creative teams you could actually think of all sorts of things that could change the data or things that could go wrong and then lets you try to design。

set of dashboards or metrics to put in place to monitor whether or not any of the things that you think might go wrong actually do go wrong。

 So we may put in place dashboards like how often it turns out reauthentation is a common thing。

 How often does a user need to authenticate twice before the let through does actually a sign of user frustration right So the dashboard to do that。

 How often does a user have to try twice。 it probably means something going wrong the first time How often do you accept versus reject the user and what is the latency of the system And I find that just as it's difficult to know in advance what's in your data is actually difficult to know in advance what dashboard would be the most useful and so the best practice I generally recommend is brainstorm lot things go wrong。

 brainstorm a lot of metrics and then just you know create very rich dashboards where this is。Time。

 latency。Time， re authenticthentation。Right。Time the number of zeros versus ones。

 and then draw plots。Over time。To see how these rates trend over time。

And if you're able to have a lot of dashboards in sample and just。

 you know look at some of the data for what you suspect and may be making a mistake。

 that often is then a good way for you to have a higher chance of spotting when there might be a problem。

And in the times that built large dashboards with 20，30 metrics。

 I found that it's surprisingly difficult to know in advance which dashboards would turn out to be useful。

 I think in expatory data analysis and data science，Again。

 because we often don't know what's in the data or what the data will give us in the future， we just。

 you know， frankly， plot a lot of stuff and then go and figure out from there what is interesting right So the cost of plotting something in the Jupyter notebook is fairly low。

 So let's just plot a lot of stuff have longer dashboards。 And if you end up with。You，30。

50 or 100 dashboards tracking these metrics over time。 Then hopefully in a few days or a few weeks。

 you figure out that a lot of them are really boring。

 So we figure out that while latency is just not the thing because we call host deployments。

 is very constant。 So well let's get rid of that because that's just a very boring part。

 I'm just not worry about that。 And so often pause a lot of things and improve back to then have a smaller number of metrics that we track and monitor for the long term and then eventually when you get a sense of。

No。This being the normal range for some metric， you can then also put in place upper and lower alarms so that if it ever goes above or below certain bounds。

 so trigger an alarm， like go page someone to take a look to figure out if something's gone wrong。

In makes sense and so unfortunately， just because we train a model a lot of time in a real world production setting doesn't mean you're done because you deploy it and then the world will give you surprising data and having a plan to monitor what happens as well as to maintain the model。

 meaning get you data， update the system to fix problems as they arise。

 that is often an important part of the practicalities of deploying machinery system as well。



![](img/2755254d033f8dd62623b4bbc2720a27_5.png)