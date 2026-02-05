# 吴恩达@斯坦福大学《深度学习｜Stanford CS230： Deep Learning ｜ Autumn 2018》中英字幕（豆包翻译 - P6：-06-Lecture 6 - Deep Learning Project Strategy.zh_en - GPT中英字幕课程资源 - BV19y421z7jz

![](img/f776297c139eb5c797ce41ac9b01375b_0.png)

All right， hey everyone， welcome back， I this people can hear me okay？



![](img/f776297c139eb5c797ce41ac9b01375b_2.png)

All right， so if as usual， you can take a second， enter your SUID so we know who's here。

So today's lecture will be a choose your own adventure lecture。

 So I think you know by now you've learned a lot about the technical aspects of building learning algorithms and then in the third course in the third set of modules you saw some of the principles for debugging learning algorithms and how you use these tools in order to be efficient in how you build a machine learning application what I want to do today is step through with you a moderately complicated machine learning application and throughout all of today's lecture。

 I'm going to you know step you through a scenario and then ask you to kind of choose your own adventure because if you' are working on this project what are you gonna do and to give you more of that practice in the next what are in a bit that we have on thinking through machine learning strategy。

And， you know， I've seen in so many projects there are sometimes things that a less strategically sophisticated team will take a year to do。

But if you're actually very strategic and very sophisticated in deciding what you will do next。

 right， how to drive your project forward， I've seen many times that what a different team will take to do。

 maybe you could do it in a month or two。And you know， if you are trying to， I don't know。

 write a research paper or build a business or build a product。

 the ability to drive a machine learning project quickly gives you a huge advantage and just you're making much more efficient use your life as well。

For today， I'd like to I'm gonna pose a scenario， pose a machine learning application and say。

 all right， I you are the CEO of this project。 What are you gonna do next。 So。

 but I'd like to have today's meeting be quite interactive as well。

 So can I get people to sit in groups of two in ideally3 or so。

 maybe plus -1 and try to sit next to someone that you don't work with all the time。 So。

 so if sitting next your best friend， I'm glad your best friend is in the class with you。

 But go sit with someone else， because I think。😊，I've done this multiple times。

 and the discussion is actually richer of you talk to someone that you don't know super well。

So actually take a second and you should use yourself。And just be your neighbor， I guess。

So the example I want to go through today is actually a continuation of the example I described briefly in the last lecture I told us of building a speech recognition system。

 right， So remember， I briefly motivated this trigger word wake word or trigger word detection system last time where。

You know啊。Right， I actually have both an Amazon E and a Google home。

 but you know it's a lot of work to configure these things to turn on and off your light bulbs。

 And so if you can build a chip to sell to say， a lamp maker to recognize phrases like， you know。

 let's say we call the lamp Rob， right。😊，Then you can recognize phases like Robert turn on。Right。

Ro turn off。 and you have a little switch to give distinct thing different names。

 Youre called Robertits or Laer or Alices or something。

 You can also have Laer turn on Laer turn off and just give your lamp a name and just say hey。

 Robert turn on So Robert it and detecting different names and turn on and turn off I'm just going focus on just for the technical discussion。

 I'm just going to focus on the phrase Robert turn on but it's kind of the same problem。

 you need to solve like four times to give it two names or to turn on and turn off。

 So I'm going abbreviate Robert turn on as RTO right So if you want to call your name Robert and tell your lamp to turn on。

 I think I was inspired by well Isaac Asimov wrote these robotic novel series and all his robots names started with R。

 So maybe R has robot turn on。And so。Let's see。 So let's say that you are the new CEO of a small startup with three persons and your goal is to build an is to build a circuit actually your goal is to build a learning algorithm that can recognize this phrase Rob turn on so that when someone you know buys this lamp and they say Robert turn on the lamp can turn on and just focusing on the task of building then you know to be CEO of the stuff you need to do a lot of things right。

 need to figure out how to do the embedded circuitry。

 figure out who the lampmakers sales general So there's all that stuff。 but so today。

 let's just focus on the machine learning aspect of it。 And so my first question to you。

 It's very openend and this is the life of a CEO right you wake up one day and you just got to decide what to do but so my first question to you open ended question is you other CEO you're gonna show up at work tomorrow in your startup office。

And you want to build a learning algorithm to detect the phrase Robert turn on for this application。

 so my question is， what are you gonna do So take take a minute to answer that by yourself first don't discuss your neighbor Yeah but you're going to show up in your office and then you're going start working on this engineering problem to build a neural network to do this。

 and do this as yourself don don don't pretend that this hypothetical whatever startup CEO with10 billion to spend whatever。

 just do's say yeah I don't think this is a terrible startup idea this is not the best idea。

 But I think this could work。 So you actually welcome to do this。

 But let's say you decide to do this。 And you go into your office tomorrow like what you do once you take。

Why should take， let's say two minutes to enter an answer that we we can discuss。In fact， I think of。

Yeah， yes。 one thing I really like about the answer is actually the readers existing literature part。

 right In fact， when you're starting a new project and I think。

When you start a new project like that， assuming you've not worked on trigger word detection before。

 you know， reading research papers or reading code Github or reading blog posts and this problem is actually a very good way to quickly level up your knowledge。

 And I think that。You know， it turns out that in terms of your exploration strategy， right。

 I want to describe to you how I read research papers， which is。So， this is。

Not a good way to review the literature， which is if。The X axis is time。

 and the vertical axis is research papers。 What some people will do is find the first research paper and read that until it's done。

 and then go and find the second research paper and read that until it's done。

 And then go and find the third research paper。 And just theres a very sequential way of。

Readeting research papers。 And I find that the more strategic way to， to go through these resources。

 everything ranging from blog posts， lots of good medium articles that explain things， right。

 research papers。All right， Github。Is if you use a parallel exploration process where this is actually what it feels like when I'm doing research on when I'm trying to learn about a new field。

 I'm not that exp right So I've actually done a lot of work on trigger word detection。

 But if I hadn't worked on this before then I would probably find you know three papers So again exercise this time and acid is different papers。

 and you know， read a few papers kind of in parallel at a surface level and skim them And based on that。

 you might decide to read that one in greater detail and then to add other papers that you start skimming and maybe find another one。

 you want to read in great detail。 and then to gradually add new papers to your reading with and read some to completion and some not to completion I was actually chatting with。

😊，One of my friends Peter， a former student at Berkeley。

 who mentioned that he was wanted to learn about a new topic。

 and he he was he told me was compiling a reading list of 200 research papers。 They want to read。

 that sounds like a lot。 you rarely read 200 papers。 But I think if you read 10 papers。

 you have a basic understanding。 If you read 50。 You have a pretty decent understanding。

 you read like 100。 I think you have a very good understanding of a few， but often this is。

Time well spent， because and。Some other tips again。

 this is I'm really thinking if you really are CEO of this startup and this is what you want to do。

 what advice would I give you when you're reading papers。

 other things to realize one is that some papers don't make sense and thiss fine even I read some papers I nope I don't think that makes sense and and it's not that uncommon for us to find papers from a decade ago that we learned that half of it was great and the other half of it you know was really talk about things that were not that important so it's okay authors you know usually papers are technically after it。

 but often what they thought was important， like maybe an author thought that using baal was really important for this problem but it just turns out not to be the case that happens a lot that happens sometimes and I think the other tactic that I see Stanford students sometimes not use enough is talking to experts。

 including contacting the authors。 So when I read the paper。あ。

I don't I don't bother the authors unless I've actually like tried to figure it out myself But if you actually spent some time trying to understand the paper and if it really doesn't make sense to you it's okay to email the authors and see if they respond。

 and people are busy。 maybe there's a 50% chance of respond。

 and that's okay because it takes you five minutes to write an email and there's a 50% chance to get back to you that could be time pretty well spent。

 but don't don't don't bother people unless you try to do your own work。

 I actually get a lot of emails from you know high school students that do not feel like they've done their own work I just So so just don't don't bother people unless you've actually tried to do。

Cool， so after looking at the literature and having a base。

 maybe downloading a open source implementation or getting a sense of an algorithm you want to try。

 it turns out the trigger word detection literature is actually one literature where there isn't consensus on this is a good algorithm。

 this is a bad algorithm right despite all the trigger word or wakeward detection systems that know some of you may use already。

 there isn't actually consensus in in the research for me today on like this is the best algorithm to try。

But so let's say that you read some papers， download some open source implementations。

 and now you want to start training your first system。 right last time we talked about this。

 we talked a little bit about how much time you would spend to collect data and you know。

 we said spend a small amount of time spend like a day or maybe two days at most to collect your first data set to start training up a model But my next question to you is what data。

Would you collect， right？In particular， what train。Death test data。Yeah。Would you collect。

 So you've decided on an initial neural network architecture and you want to train something to recognize this face。

 Robert turned on。 I think there's。Pvy， I don't think it's possible to download the data。

 I don't think anyone has collected the data with the worst robot turned on and posted down the Internet。

 So you have to collect your own data for this particular trigger phrase that you want to use。

 But you know， S CEO of this startup trying to build a neural net to detect the phrase robot turn on。

On。What data do you collect， Right？ So once you take， once you again， take， I don't know。

 let's say three minutes to write an answer。To this。Yeah， I think this is an interesting one。

 Robert turned on over and over and then data augmentation。

 data augmentation is one of those techniques that is a way to reduce variance in your learning algorithm because you're generating more data and having worked on this problem。

 I happen to know data augmentation works。 you is very useful for this problem。

 but if you didn't already know that fact， this is one of the things I would probably not do right away because I would train a quick and dirty the system validate that you really have a high variance problem before investing in the effort and data augmentation。

 So data on is one of those techniques that you know it never hurts。 rarely hurts。 usually helps。

 but I don't bother to make that investment unless you have collected the evidence that you actually have a high variance problem and that this is actually good use of your time。

はい。Here。I think this， this one actually。This are nice。

Re everyone started saying Robert Turn 100 times。 So really nice thing about that。

 You can get done really quickly。 When I'm working with teams。

 I actually think in terms of hours in terms of how long it takes us to do something。

 So this one you could probably do and like 30 minutes right。

 So you can get your data collect in 30 minutes and get going or if you run around Stanford and just ask。

 you know。😊，Friends or strangers to speak into your laptop microphone。

 you didn't spend a few hours to get a much bigger data than possibly a startups so I probably do that。

 I probably actually go and collect data in several hours rather thant only spend 30 minutes。

 but this is actually pretty interesting as well because unless you get it done really quickly that makes sense right？

So。嗯。Yeah， so let me actually share some more concrete advice。

 right And I think actually sometime back to prepare a homework problem that you see later in this course。

 Ken and Yuuns and I werere actually， you know building the system。

 partially to create a homework that you see later in this course。

 This is like this trigger word thing is a nice running example that we're using in a few points throughout this course。

 So here's one thing you can do。 And this is actually what what we did right which is collect。😊，哦。

Well， simplify a little bit。Yeah。Collect 100 examples。Of 10 second audio clips。

RightAnd so it turns out once you grab a hold of someone and ask them to speak into your microphone。

 you know， you can keep them for three seconds， which is how long it takes to say。

 Robert turnon or you can keep them for 10 seconds。

 which they're actually very willing to spend extra seven seconds with you But so if this is 10 seconds of audio data So this is 10 seconds of audio audio is just patterns of little changes in air pressure So if you plot audio。

 the reason it looks like this waveform is just the way you're hearing my voice is my voice or the speakers are creating very rapid changes in air pressure and your ear measures those very rapid changes in air pressure interpretses the sound。

 And so a microphone is is a sensitive device for recording these very。

 very high frequency changes in air pressure and this plot that you see in audio is just what is the air pressure at different moments in time。

 But so given a。A10 second clip like this。 if this is the three second section where they said Robert it turn on。

 then what you would like to do is to build a desk lamp。

 say they can sit here and the lamp is turned off， turn off， turn off， turn off， turn off， turn off。

And at the moment， they finish saying Robert turn on， you know， you turn it on。

 So this is the output label。 Y， really， right。And then and then it's not detecting a phrase right so what you want to do for the trigger word system is at you know pretty much the moment they finish saying Robert turn on。

 you want your learning algorithm to output a one that's your target label Y saying yep。

 I just heard this trigger word and for all other times you want to output zero because because an and then one is when you decide to turn on the lamp at that moment in time right？

So to collect a data， here's something you can do， which is collect。100 audio clips。

Of 10 seconds each。And， you know， when I'm prioritizing my work or my team's work。

 I would really you know， look at these numbers and think， Okay。

 let's say let's say actually if you are doing it， let's say you are running around Stanford and you want to collect 100 audio clips maybe 10 people。

10 clips per person or maybe 100 different people。 I would actually estimate， you know。

 if you go to Stanford cafeteria how long does it take to get one person you could probably get one person every minute or two。

 if you go to a busy place like a Stanford cafeteria。

 So you could probably get this done in like 100 to200 minutes。

 like two or three hours It's not that bad。 So you can get this done quite quickly。嗯。And so， and。

 and let's you collect 100 audio clips。 And actually， for the， for for the purposes of today。

 let's say。You collect  hundred0 audio clips to use for training。25。For your death set。嗯。

And0 for the test set iss actually not that uncommon if you're building a new product to just not have a test set because you go is to build something that yre convince。

 you know， just early prototyping phases of a project。 Sometimes I don't bother with a test set。

 if you goes to publish a paper， then， of course， you need a rigorously collected test set。

 But if you're just building a product。 but you don't need a rigorous evaluation。

 Sometimes you can just get started without dealing with a test set。

 So it's pretty really get started。嗯。And then。So taking that audio clip from above。

One thing you can do to turn this into supervised learning problem is to take so the phrase Robert turn on can be said in less than three seconds。

 So let's say you take three seconds as the duration of audio right So what you can do is clip out So let's say here was when robot turn on was said。

 So what you can do is the target label was0，0，0，0，0，0，010，0，00。

 What you can do is then clip out different audio clips of three seconds。 So here's when audio clip。

You can take that audio clip。This is X and the target label。

Theres zero because because Robert turn on was not said。嗯。

And you can take on a dis audio clip a different random of knee clipped，3 second clip。

 And that clip also。Has the target of a of 0。And。Neith， for this one。Right， which is a。3 second clip。

That come that that that ends at the well on the last part of the on sound。

 You would have a target label of one。Right， so and and when you learn about sequence models。

 or R andNs， you learn a better method than than this explicit clipping。 But for now。

 let's say you take these audio clips and turn it into So take a 10 second clip。

 And by clipping up around different windows， you can take your let's say hundred clips。

And because for each 10 second clip， you can take different windows。 You could turn those into。

 let's say， 3000。Training examples， right， So here I took a 10 second clip and and and shown。

 you know， took three， three different。3 second windows， but you take 30，3 second windows。

 then each 10 second audio clip becomes 30 examples。

 and now you've turned the problem into a binary reclass problem where you need to train a neural network that inputs a three secondcond clip and labels it as either zero1 does sense。

 And so this is an example of the more complex pipelines you might have if you're building a learning algorithm to take a continuous audio detection problem and turn into a binary reclass problem。

 which you've learned how to build various neural networks for And again， when you learn about RNs。

 you learn about other ways to process sequence data or temporal data。So go ahead。It'sterday account。

Mnually labeling the data。Oh， is this manly label in the yes， I I would。 Yeah， actually。

 if you have 100 examples， it's not that hard to just listen to it， you know。

 on your laptop with some audioplay software to figure out when when they finish seeing Robert turn on。

 And then at that moment to put a one in the target label because this is really when you want the lamp to turn on。

喂。冇 sense。cool。So。Any other questions， Actually， feel free to ask clarifying questions。 Yeah。

 go ahead。 I wonder if this is going to cause the problem that ones are two spas。 Oh， so。

 let me get back to that。Anything else。I a specific reason we only train them with three。

someOh I see why do we do three seconds and four， five seconds。

 there's another hyperpro you contest test so I think I' know。

You have to stand really slowly to take， I don't know， few seconds is this， right？

This Rob it turn on。 right。 So again， it's a design choice yeah。哎Yeah。All right。

Let's say you do this。Feded to supervis zing algorithm， train a neural network。

And let's say that when you classify this， when you run this algorithm， you end up with a。99。

5% accuracy。哎い。But you find that the algorithm has zero detections。Right。

And and and what I mean is that whatever audio you give it it just output zero all the time。

 So the algorithm just says nope， I never heard the phrase Robert turn on you know， so， so so。So。

 and so my question to you is， you know， and by the way。

 the reason I'm going through these scenarios is I found that。

A good way to gain good intuitions and and to become good at making these decisions is these are the decisions that project leader right。

 a tech leader or CEO needs to make。 These are actually like pretty much exactly the decisions you need to make。

 And I find that one of the ways to gain this type of experience if you you know。

 find a job with a good AI team and work with them for five years right and then you essentially live through this and you see what they do。

😊，But instead of needing you to go and spend five years to see 10 examples of this。

 I'm trying to step you through maybe one example in in， in one hour。 So， so instead of， you know。

 gaining this experience through work experience， which is great， but takes many， many years， many。

 many months， hoping to。😊，You， let's just put you in the position of making these decisions。

 You can learn from them much faster， but so。And and all the examples I'm giving are actually completely realistic。

 right， Theyre either exactly or very similar to things I have seen in in actual， you know。

 very real projects。 So question is your learning algorithm gives this result。

95% of nasty zero detections。 what do you do。😊，Let me mention some of the answers I really liked。

I think that。You know， when I think of building learning algorithms。

 the process is often specify a depth set and or test set that measure what you care about and then you don't always have to do it but it's good hygiene it sharpens clarity of your thinking if you have a very clear specification of problem and I think when inside out of this is that if your death set is really out of whack because it's so unbalanced that accuracy in your depth set doesn't translate to what you actually care about because you know presumably this is 99。

5% accurate on the depth set as well， but this performance is terrible so it's doing great on the depth set on your accuracy measure're giving terrible performance So I think of it as good hygiene this kind of good sound practice to just specify。

 make sure you at least have a depth set and evaluation metric that corresponds more closely to what you care about So making the depth set more balance equal numbers of positive and negative。

Would be a good step to that。 And then I think。You could also。

 there are a few people that talked about give higher weights to the positive examples right So。

 you know， one way to do this is to resample your training and your depth sets to make them more proportionate in terms of maybe closer to balance ratio。

 positive negative examples， that would be okay。 The other way to not do resling。

 we just give the positive examples a greater weight right I would probably resample Another thing you could do。

 you know， in the in the interest of。Speed， even if it's not the mathmatic most most sound thing to do is to change the target labels to be a bunch of ones after that。

 and this is a hack， this is not formally rigorous。

 but if you've implemented the rest of this code already， this might be a reasonable。

 you know a little bit hacky thing to do， but this is is this might work well enough， right I would。

I might not， I don't know if I would want to try to， you know。

 write an academic research paper with this method， maybe you can get away with it。

 But this is little thing that I think if you try to publish a paper with this。

Academic reviewers might raise their eyebrows and say， maybe， you know， maybe this is okay。

 but I think if you want something click and dirty that just works I think labeling the ones changing a bunch of labels to be one so thats say a clip here。

Right that ends just a little bit after robot turn on is still labeled one。

 that would be pretty reasonable， but this would be saying that for anywhere within maybe a 0。

5 second period after robot turn on finish is okay to turn on the light anytime within that period that you kind of want to be turning on the light。

 turning on the lamp。You know， say within half a second right after Robert turn on as has been said。

 right。And this would be a not this would be a way to just get more labels of ones in there。Right。

買 sense。With like rebalancing your data sets， like a class imbalance。

How does that translate to like when you deploy this。

 you're not going to see Robert turn on as much right like one out of 1。

000 might be reflective of what you expect to see。Yeah， this is gonna。 Yeah， right。 So I think that。

aboutSo if you actually yes， this is sort of a depth set and evaluation metric kind of question right So one of the couple of the metrics that people often use when actually working on this is when someone says Robert turn on what iss the chance that actually wakes up or the lamp turns on。

 And then the second is if no one is saying anything to the lamp， you know。

 how often does it randomly turn on by itself without you having said anything。

 So those are the two metrics people actually use sometimes you could also try to combine them a single number evaluation metric or something but I think that you could then define a data to measure both of these things。

 and then hopefully find a way to combine them into single real number， which I think。

 I think one of the ways we talked about in the videos as well。Does that make sense。

 but I think I think。So the question is really what is it that satisfies a using it right and and just one thing about the straightforward way of rebalancing is that if you don't do this。

 then your whole data set just as very few positive examples right and so if you throw away all the negative examples so that you cut down the number of negative examples until you have exactly equal numbers of positive negatives。

 you've actually thrown away a lot of negative examples。 this makes sense。

 and so one problem with the straightforward way of rebalancing is that you know in your audio clip and 10 secondd clip that were collected by running around Stanford you have one example of rapid turn on。

And so if you want exactly perfectly balanced positive negative。

 it means that you're allowed to only clip out one negative example。 all of this。

 You can say that's a negative and that's a positive。

 And you can't clip out more negative examples from this， So， so， so if you use a。

 if you insist on the perfect rebalance， You're actually throwing away a lot of negative examples that that could be helpful for the learning。

Right。嗯。So。All right。So。澳门。You know， a lot of the workflow of building learning algorithms is building learning algorithms feels more like debugging right because what happens in a typical machine learning workflow is you implement something and it doesn't work So you figure out what is the problem So you fix that like rebalancing or reweighting or adding more onces and so that fixes the current problem and then after fixing the current problem which is the one which is solve。

 say you then come across a new problem and you have to solve that and you fix that problem。

 somewhere across another new problem So I find that the workflow of when I'm work on a machine learning project。

 it often feels more like software debugging than software development because you're often trying to figure out what doesn't work and then trying to fix that and after you fix that problem then another bug surfaces and you squash that and you do that and you kind of keep doing that until the algorithm work So if I keep talking about you know your algorithm doesn't work what do you do next right that's kind of the theme of today's presentation。

But that that is what the workflow。 That is what your day to day work of developing a learning algorithm is usually like because it's like it doesn't work。

 you fix it。 It still doesn't work because you fix that， it still doesn't work。

 You fix it and you do that enough times until it works。

 right that is actually what often working on the learning algorithm works。 looks like。嗯。All right。

So let's say you fix that problem and you conclude through doing error analysis that your algorithm is overfitting。

so you know you've added a lot more ones， so the data is a little bit more balanced。

 so let's just add a bunch of ones like I did on that previous board right let's just add a lot of ones here。

 so the data isn't as unbalanced。And。Let see。嗯。Right， okay。嗯。Let's say that。Sorry。

Two pages of notes here。Okay， good， so let's say that you find that that the cheese now 98% accuracy。

On training。And 50% accuracy。On the depth set， right。

 So very large gap between your training and your depth set performance。

 And so clear sign of overfitting。 And so I think one earlier question。

 someone talked about data augmentation。 And so when you have this clear sign of overfitting。

 This is a good time to consider data augmentation。 And and。

 and so let's say you go ahead and do data augmentation。 So for audio。

 this is how you could do data augmentation， which is collect a bunch of background audio。😊，You know。

 so I guess if youre trying to build a lamp that might go into people's homes。

 then you could go into your friend' homes and you know， with their permission， record right。

 what the background sound of their home looks like。 You know， maybe people talk in the background。

 maybe the TV on in the background， whatever goes on people's homes。

 and then it turns out that if you take a， say a one second clip。一。Of Robert Tranon of RTO。And you。

Add that to a background clip。 then you can synthesize an audio clip of what it sounds like in your friend's houses。

 if someone were to suddenly pop up and say ro turn on against a background sound of your friend'shus and and it turns out that if you want to make the system robust。

 So actually， for example， have a know actually know someone that lives unfortunately closely to a train station。

 And so theirhus actually has a lot of train station noise for the cowtrain And so what you can do to make a system more robust is also take you know。

 a clip of say train noise like cowtrain noise。 and if you take that noise and take a in this case。

 let's say one second， one second or three second clip or someone saying robot turn on and you synthesize that on top of the train in the background。

 then what you end up with is a 10 second clip of someone saying robot turn on。Its a noisy。

 train in the background type of noise， right？And so。

In order to do data augmentation or data synthesis。

 you can take some one second clips of people saying Robert turn on in the quiet background and then take some one second clip of people saying random words right。

 let's say you know， Carinal right you Stanford and synthesize this against the train noise background and then you would have in this case。

 you would have what sounds like train noise， train noise train noise， train noise。

 Robert turn on train noises right And then you could generate the labels now as zeros there。

Once there。And then zeros there。Because if this is what actually sounded like in a user's home。

 then you want the lamp to turn on after robot turn on， but not after these random words。

 you can take different random words。Great以。So。Let's see。Right。So。嗯。

What I'd like you to do is evaluate three different possible ways to collect noisy data。

 to collect this type of background data and so。What I like you to do for the next question is。

 let's say you and your team， you know， have brainstormed。

braininstormed a few different ways to collect this type of background noise data。

And let's say you've decided that you would like to collect 10 hours of background noise data， right？

So I'm going to present to you three options。One is。You know。

 run around Stanford and place microphones around Stanford or your friends homes do this with consent and don't don't。

 you know， California actually you're not supposed to don't recall people about their knowledge and consent。

 right。Second is。お。Download clips online。Right， it turns out if you go to YouTube。

 there are these like。10 hour long clips of， you know， rain noise or cause driving around。

 right So you actually， again， if you do that， find something that's creative commons and of appropriately licensed。

 right， Another thing you could do is use a mechanical。😊，Yeah。Amazon mechanicalchanical Tu。

We can have people all all around the world be paid， you know。

 modest amounts of money to submit audio clips So for the next exercise。

 what I want you to do because and I want you to have this exercise of this discipline。

 which is what I want you to do is I want you to estimate， let's see。What time is it now， Okay。

 it's 12，30 PM right now。 What I want you to do is write down three numbers in the next exercise to estimate if you were to do this。

You know， let's say you were to go do this right now， right。

 By what time would you have finished if you were to do option 1， What time would you finish。

 you were to do option2， What time would you finish， You were to do option 3。

 If you go is to collect 10 hours of data through one of these mechanisms。Does that makes sense。

 So it's 1230 PM now。 So what I'd like you to do is just write down three numbers。

First number is what time is it， what time would it be？

By the time you collected 10 hours of data you know。

 from around Stanford what time would it be right and if you could do this in so if you think you'd do it by tonight。

 then write 9 PMm if you think itll do if you think it'll take you one week。

 then write the date one week from now or whatever it is。

 but just write down three numbers of these fee activity。why don you do this one relatively quickly。

 Can people do this in like maybe minute and a half。All right， Co。 This is interesting。Yeah。

 what do people think， actually， this is surprisingly large variability。 I'll mention one thing that。

Surprise me。 I'll give you my own assessment。 I think that。You know， when I'm leading startup teams。

 we tend to be very scrappy right And so I think that if it goes to collect 10 hours of data。

 if you have three friends with laptop， you can collect three hours of data per hour because you got three recordings going in parallel So if I were doing this with say two other friends you know I bet I bet we could get this done by tonight because if you need nine hours of data thats each person needs to collect three hours of data and you run around Stanford the keep the microphones running I be I bet I could get this done by 6 pm maybe maybe even earliert know。

嗯。Download clips online Its actually oh know， It's actually an interesting one。

 maybe bit about the same time。 It turns out one tricky thing about downloading clips online is that I think a lot of the there are people that have trouble sleeping night so they listen to highway noise or whatever And so there are these you know。

 20 hours of highway clips， highway noise on YouTube that you can find。

 but I don't know how those clips were generated。 And I suspect a lot of them loop meaning it's the same one hour play over and over。

 So I actually think is's harder than than one might guess they get 10 hours of non repetitive data。

 And it's one of those things， you know， if I take an R of highway sound and loop it。

 you can't tell the difference because oh highway sound sounds the same。

 I just can't tell one minute of highway sound from another one。

 But if you have one R of highway sound looped 10 times the learning hour where you perform much less well that。

Of 10 hours of fresh highway sounds。 So this， I would actually have a harder time doing。

 I think I probably， I， I would， if I were doing this， I， because of these problems。

 I would probably budget until sometime tomorrow。Right maybe maybe 9 PM or something。

 maybe that's doable。 I'm not sure。 The one surprise to me was some people thought they could do this by tonight。

 again， I've used Amazon Its actually a huge process to set up Amazon get people on board。

 and especially to get them microphone I don't have to implement something on flash。

 They can speak in their web browser and flash be supportive actually is actually not that easy to get a lot of Turkishs to do this。

 And the global supply of is also unlimited。 So I would， if I were doing this， I would probably。

I know， maybe a week or something hard to say。 I'm not sure。

 But so the specific opinion isn't that important。 but I want you to go through this exercise because this is how efficient startup teams should you know brainstorm list of things and then you all figure out how long you think it will take to do these things。

 And I think we can have a debate about how high quality the data is。

 I think you can get very high quality data from this and from this。

 I just then trust a lot of those online audio sources。

 but the business is really fast and you can get pretty high quality data。

 I would probably do this and collect background to get going But I think that part of the work though I see of you know。

 fast moving teams is pretty much exactly what you did。

 which is why we have that exercise of brainstorming the list of options and then really estimating what time can we get this done and then use that to pick an option right。

And then I want to just mention one last thing。Which is that。These differences matter， right？

You know， I've actually I've built a lot speech system， but a lot of machinery systems。

 but and I think by the way， if you do everything we just described and you see this later in a problem set。

 you can actually with this set of ideas， pretty much this set of ideas that you just went through today。

 you can actually build build pretty decent trigger word detection system or wakewater trade word detection system in fact。

 we'll ask you to do pretty much this in a later homework exercise。

 but now you know when you get to that homework exercise when you do R&Ns of you know how you could come up with this sort of process yourself if you didn't already know how to make these types of choices。

😊，What what time of my research do would like to think about language of how micro affects my results the beginning I it's micro is the as when run mess you have to think about it so my advice does your microphone affect your results my advice would be to get something going quick and dirty and then develop a depth set right with the actual types of data you think you get on your real microphone and then see if it is a problem and it may different microphones do have different characteristics and if it is a problem then go back and think about how you collect data that's more representative of how you test。

I want to mention one more quick thing。 Do want to handle cost surveys。

 I want to do something real quick， which is I want to tell you why these things really matter。

 which is。If this is a performance， right， let's say， actually， let's say era。And this is time。

RightAnd if this is today。And you're the CEO of this Santa。 remember。

 that's what we're doing in this lesson。 And this is six months from now。

 and this is 12 months from now。Right。You know， maybe of a competitor。 actually， maybe， maybe。

I don't know。 Maybe because we talked about this so much in this class。

 maybe two of you in this class are going to build this startup up， but a competitor。 But over time。

 most machine learning teams。You know， the error actually goes down over time as you work on problems。

 right I mean this is what I see in tons of practical projects。

 you work on the project improve the system and the error actually goes down over time as you work on this over the next 12 one if youre really CEO of a startup doing this。

 And it turns out that it's a startups， you have the discipline to constantly be the most efficient。

 don't do something that takes you two days， if you can get a similar result in one day。

 the difference is not that you're one day slower， the difference is that youre two x faster and having that mindset。

 if you can take this whole chart and compress it on the horizontal axis， then you。

I want to be the startup that makes the same amount of pro in six months until of 12 months， right？

Because if you're able to do this， then your startup will actually perform much better in the marketplace。

 assuming actress is important， which it seems to be a wake word。

 And so don't think of this as saving you a day here and there。

 think of this as making your team twice as fast。 and that's the difference between this level of performance and that level of performance。

 So that's why when I'm building teams and executing these projects I tend to be pretty obsessive about making sure we're very efficient in exploring the options and don't wait till tomorrow to collect data of dubious quality when you have a better idea of collecting data by today because the difference is not that you wasteted 12 hours。

 the difference are twice as slow as a company So I think so hopefully through this example on your ongoing experiences throughout this quarter can help you continue to get better at this last thing we want to do was we're about halfway through the course ahead we want to handle a survey an anonymous survey to get some。

Back from you about this class。 And whenever we get these surveys。

 we end up thanks to the previous generations of students feedback。

 we've already been gradually making class better。 So I think Ken and I actually read all of these questions ourselves and try to find ways to take your feedback to improve the class。

 So if can take you know five minutes felt the survey and you can hand it in just drop it up anonymously up in front but very grateful for your suggestions。

So。I think if you haven't entered。Your idea D yet， you could still do so。 but that's it for the day。

 So please start the survey and the anonymously。 drop out back in front。 Then we'll wrap up。 Okay。

 thank you。

![](img/f776297c139eb5c797ce41ac9b01375b_4.png)