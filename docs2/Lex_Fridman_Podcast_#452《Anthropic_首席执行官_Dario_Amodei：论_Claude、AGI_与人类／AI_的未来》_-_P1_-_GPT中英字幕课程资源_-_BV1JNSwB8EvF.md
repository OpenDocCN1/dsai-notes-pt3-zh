# Lex Fridman Podcast #452《Anthropic 首席执行官 Dario Amodei：论 Claude、AGI 与人类／AI 的未来》 - P1 - GPT中英字幕课程资源 - BV1JNSwB8EvF

If you extrapolate the curves that we've had so far， right， if you say， well， I don't know。

 we're starting to get to like PhD level and and last year we were at undergraduate level in the year before we were at like the level of a high school student again。

 you can you can quibble with at what tasks and for what we're still missing modalities。

 but those are being added like computer use was added， like image generation has been added。

 if you just kind of like eyeball the rate at which these capabilities are increasing。

It does make you think that will get there by 2026 or 2027。

 I think there are still worlds where it doesn't happen in 100 years。

 Those the number of those worlds is rapidly decreasing。

 We are rapidly running out of truly convincing blockers。

 truly compelling reasons why this will not happen in the next few years。 The scale up is very quick。

 Like we do this today。 We make a model， and then we deploy thousands。

 maybe tens of thousands of instances of it。 I think by the time， you know。

 certainly within two to three years， whether we have these super powerful As or not。

 clusters are going to get to the size， where you'll be able to deploy millions of these。

 I am optimistic about meaning。 I worry about economics and the concentration of power。

 That's actually what I worry about more。 The abuse of power and AI increases the amount of power in the world。

 And if you concentrate that power and abuse that power it can do immeasurable damage。 Yes。

 it's very frightening。 is very frightening。The following is a conversation with Daro Ammaday。

 CEO of Anthropic， the company that created Claude that is currently and often at the top of most LLM benchmark leader boards。

On top of that， Dario and the Anthropic team have been outspoken advocates for taking the topic of AI safety very seriously。

 and they have continued to publish a lot of fascinating AI research on this and other topics。

Im also joined afterwards by two other brilliant people from Anthropic。 First， Amanda Asll。

 who is a researcher working on alignment and fine tuning of Claude， including the design of Cla's。

 character and personality。A few folks told me she has probably talked with Claude more than any human etanthropic。

So she was definitely a fascinating person to talk to about prompt engineering and practical advice on how to get the best out of Claude。

After that， Chris Ola stopped by for a chat。 He's one of the pioneers of the field of mechanistic interpretability。

 which is an exciting set of efforts that aims to reverse engineer neural networks to figure out what's going on inside。

 inferring behaviors from neural activation patterns inside the network。

This is a very promising approach for keeping future， super intelligent AI systems safe。For example。

 by detecting from the activations when the model is trying to deceive the human， it is talking to。

This is Alex Friedman podcast to support it， please check out our sponsors in the description and now。

 dear friends， here's Dario， Ammaday。

![](img/6846fcb7b588a1893fcebff3034afbf1_1.png)

Let's start with a big idea of scaling laws and the scaling hypothesis。 What is it。

 What is its history and where do we stand today？ So I can only describe it as it you know as it relates to kind of my own experience。

 but I've been in the AI field for about 10 years。 And it was something I noticed very early on。

 So I first joined the AI world when I was working at by do with Andrew Wing in late 2014。

 which is almost exactly 10 years ago now， And the first thing we worked on was speech recognition systems。

 And in those days， I think deep learning was a new thing。 It had made lots of progress。

 but everyone was always saying we don't have the algorithms we need to succeed。

 know we're not we're only matching a tiny tiny fraction。

 there's so much we need to kind of discover algorithmically。

 we haven't found a picture of how to match the human brain and when you know in some ways。

 it was fortunate。 I was kind of you can have almost beginner's right。

 I was like a newcomer to the field and。I looked at the neural net that we were using for speech。

 the recurrent neural networks and I said， I don't know what if you make them bigger and give them more layers and what if you scale up the data along with this right I just saw these as like independent dials that you could turn and I noticed that the model started to do better and better as you gave them more data as as you made the models larger as you trained them for longer and I didn't measure things precisely in those days but but along with colleagues。

 we very much got the informal sense that the more data and the more compute and the more training you put into these models the better they perform。

And so initially my thinking was， hey， maybe that is just true for speech recognition systems。

 maybe that's just one particularquirk， one particular area。

 I think it wasn't until 2017 when I first saw the results from G1 that it clicked for me that language is probably the area in which we can do this。

 we can get trillions of words of language data we can train on them and the models we were trained in those days were tiny。

 you could train them on one to8 GPUs， whereas now we train jobs on tens of thousands soon going to hundreds of thousands of GPUs And so when when I saw those two things together and you know there were a few people like Ias Suskiver who who you've interviewed。

 who had somewhat similar reviews， he might have been the first one。

 although I think a few people came to similar views around the same time there was R Sutton's bitter lesson。

 there was Gorin wrote about the scaling hypothesis but I think somewhere between 2014 and 2017。

Was when it really clicked for me when I really got conviction that， hey。

 we're gonna to be able to do these incredibly wide cognitive tasks if we just。

 if we just scale up the models And at every stage of scaling。 therere always arguments。

 and you know， when I first heard them，  honestly， I thought， probably I'm the one who's wrong。

 And you know， all these， all these experts in the field are right。 They know the situation better。

 better than I do， right， there's， you know， the Chomsky argument about like you can get syntactics。

 but you can't get semantics。 there's this idea， you can make a sentence make sense。

 but you can't make a paragraph makes sense。 the latest one we have today is。You know。

 we're going run out of data or the data isn't high quality enough or models can't reason。

 and each time every time we manage to we manage to either find a way around or scaling just is the way around。

 sometimes it's one。 sometimes it's the other。 And and so I'm now at this point。 I still think。

 you know it's always quite uncertain We have nothing but inductive inference to tell us that the next two years are going to be like the next the last 10 years。

 But but I've seen I've seen the movie enough times。

 I've seen the story happen for enough times to really believe that probably the scaling is going to continue and that there's some magic to it that we haven't really explained on a theoretical basis yet。

 And of course， the scaling here is。Bigger networks， bigger data， bigger compute Yes， in particular。

 linear scaling up of bigger networks， bigger training times and more and more data。

 So all of these things almost like a chemical reaction。 you know。

 you have three ingredients in the chemical reaction and you need to linearly scale up the three ingredients。

 if you scale up one， not the others， you run out of the other reagents and the reaction stops。

 But if you scale up everything everything in series then then the reaction can proceed。

 And of course， now that you have this kind of empirical science slash are you can apply to other。

More nuanced things like scaling laws applied to interpretability or scaling laws apply to posttrain or just seeing how does this thing scale。

 but the big scaling law， I guess the underlying scaling hypothesis has to do with big networks。

 big data leads to intelligence。 Yeah we we've documented scaling laws in loss of domains other than language right so initially the paper we did that first showed it was in early 2020 where we first showed it for language there was then some work late in 2020 where we showed the same thing for other modalities like images。

 video text image image to text math， they all had the same pattern and you're right now there are other stages like posttrain or there are new types of reasoning models and in all of those cases that we've measured we see similar similar types of scaling laws a bit of a philosophical question。

 but what's your intuition about。

![](img/6846fcb7b588a1893fcebff3034afbf1_3.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_4.png)

Why bigger is better in terms of network size and data size Why does it lead to more intelligent models So in my previous career as a biophysicist so I did physics undergrad and then biophysics in grad school so I think back to what I know as a physicist which is actually much less than what some of my colleagues at anthropic have in terms of in terms of expertise in physics theres there's this concept called the one over fnoise and one over x distributions where often you know just like if you add up a bunch of natural processes you get a Gaussian if you add up a bunch of kind of differently distributed natural processes if you like if you like take take a probe and and hook it up to a resistor the distribution of a thermal noise and the resistor goes as one over the frequency it's some kind of natural convergent distribution I。

Think what it amounts to is that if you look at a lot of things that are produced by some natural process that has a lot of different scales。

 not a Gaussian which is kind of narrowly distributed。

 but you if I look at kind of like large and small fluctuations that lead lead to electrical noise they have this decay one over X distribution and so now I think of like patterns in the physical world or in language if I think about the patterns in language。

 there's some really simple patterns， some words are much more common than others like the then there's basic noun verb structure。

 then there's the fact that know nouns and verbs have to agree， they have to coordinate。

 and there's the higher level set structure then there's the thematic structure of paragraphs and so the fact that there's this regressing structure。

 you can imagine that as you make the networks larger first they capture the really simple correlations。

 the really simple patterns and there's this long tail of other patterns and if that long tail of other。

😡，tterns is really smooth like it is with the one over f noise in physical processes like resistors。

 then you can imagine as you make the network larger it's kind of capturing more and more of that distribution and so that smoothness gets reflected in how well the models are predicting that how well they perform language isn't evolved process we've developed language we have common words and less common words。

 we have common expressions and less common expressions we have ideas cliches that are expressed frequently and we have novel ideas and that process has developed has evolved with humans over millions of years and so the guess and this is pure speculation would be that there's some kind of long tail distribution of the distribution of these ideas。

 So there's the long tail but also there's of the hierarchy of concepts that are building up So the bigger the network presumably you have a higher capacity to exactly if you。

small network， you only get the common stuff right if I take a tiny neural network。

 it's very good at understanding that you know a sentence has to have you know verb adjective noun right but it it's terrible at deciding what those verb adjective and noun should be and whether they should make sense if I make it just a little bigger it gets good at that then suddenly it's good at the sentences but it's not good at the paragraphs and so these rarer and more complex patterns get picked up as I add as I add more capacity to the network Well the natural question then is what's the ceiling of this how complicated and complex is the real world how much stuff is there to learn I don't think any of us knows the answer to that question my strong instinct would be that there's no ceiling below level of humans right we humans are able to understand these various patterns and so that that makes me think that if we continue to you know scale up these models to kind of develop new methods for training them and scaling them up。

That will at least get to the level that we've gotten to with humans。

 There's then a question of you know how much more is it possible to understand than humans do。

 how much how much is it possible to be smarter and more perceptive than humans。

 I would guess the answer has has got to be domain dependent。 If I look at an area like biology。

 And you know I wrote this essay machines of loving grace。

 it seems to me that humans are struggling to understand the complexity of biology。

 right if you go to Stanford or Harvard or to Berkeley。

 you have whole departments of you know folks trying to study。

 you know like the immune system or metabolic pathways and and each person understands only a tiny bit part of it specializes and they're struggling to combine their knowledge with that with that of other humans。

 and so I have an instinct that there's there's a lot of room at the top for AIs to get smarter。

 if I think of something like materials in the in the physical world or you know。



![](img/6846fcb7b588a1893fcebff3034afbf1_6.png)

Like addressing conflicts between humans or something like that， I mean。

 you know it may be there's only some of these problems are not intractable but much harder and it may be that there's only there's only so well you can do with some of these things right just like with speech recognition there's only so clear I can hear your speech so I think in some areas there may be ceilings you know that are very close to what humans have done in other areas those ceilings may be very far away and I think we'll only find out when we build these systems it's very hard to know in advance we can speculate but we can't be sure and then some domains the ceiling might have to do with human bureaucracies and things like this as you write about Yes so humans fundamental has to be part of the loop that's the cause of the ceiling not maybe the limits of the intelligence Yeah I think in many cases you know in theory technology could change very fast for example。

 all the things that we might invent with respect to biology but remember there's there's you。

There's a clinical trial system that we have to go through to actually administer these things to humans I think that's a mixture of things that are unnecessary and bureaucratic and things that kind of protect the integrity of society and the whole challenge is that it's hard to tell it's hard to tell what's going on it's hard to tell which is which right my view is definitely I think in terms of drug development my view is that we're too slow and we're too conservative but certainly if you get these things wrong。

 you know it's possible to risk people's lives by by being by being by being too reckless and so at at least some of these human institutions are in fact protecting people so it's all about finding the balance I strongly suspect that balance is kind of more on the side of pushing to make things happen faster but there is a balance if we do hit a limit。

If we do hit a slowdown in the scaling laws， what do you think would be the reason。

 I it compute limited data limited， is it something else， ideal limited。

 So a few things now we're talking about hitting the limit before we get to the level of humans and the skill of humans so I think one that' you know one that's popular today。

 and I think you could be a limit that we run into like most of the limits I would bet against it。

 but it's definitely possible is we simply run out of data。

 there's only so much data on the internet， and there's issues with the quality of the data。

 right you can get hundreds of trillions of words on the internet。

 but a lot of it is is repetitive or its search engine you know search engine optimization driveril or maybe in the future it'll even be text generated by AIs itself and so I think there are limit to what to what can be produced in this way That said we and I would guess other companies are working on ways to make data synthetic。

Where you can you know you can use the model to generate more data of the type that you have that you have already or even generate data from scratch if you think about what was done with Deep Mins Algo zero they manage to get a bot all the way from you know no ability to play go whatsoever to above human level just by playing against itself there was no example data from humans required in the alphago zero version of it the other direction of course。

 is these reasoning models that do chain of thought and stop to think and and reflect on their own thinking in a way that's another kind of synthetic data coupled with reinforcement learning so my guess is with one of those methods will get around the data limitation or there may be other sources of data that that are available we could just observe that even if there's no problem with data as we start to scale models up they just stop getting better it seemed to be a reliable observation that they've gotten better。

 that could just stop at some point for reason we don't。😡。

Understand the answer could be that we need to you know， we need to invent some new architecture。

 It's been there have been problems in the past with say numerical stability of models where it looked like things were were leveling off but actually you know when when we when we found the right on block or they didn't end up doing so。

 So perhaps there's new some new optimization method or some new technique。

 we need to unblock things。 I've seen no evidence of that so far， but if things were to slow down。

 that perhaps could be one reason。What about the limits of compute。

 meaning the expensive nature of building bigger and bigger data centers。 So right now， I think。

 you know， most of the frontier model companies， I would guess are are operating know roughly you know。

 $1 billion scale plus or minus a factor of3， right。

 those are the models that exist now or are being trained now。

 I think next year we're going go to a few billion。 and then 2026， we may go to you know。

 above 10 billion and probably by 2027， their ambitions to build  hundred10 billion10 billion clusters。

 And I think all of that actually will happen。 There's a lot of determination to build the compute to do it within this country。

 And I would guess that it actually does happen。 Now。

 if we get to 100 billion that's still not enough compute that's still not enough scale than either we need even more scale。

 or we need to develop some way of doing it more efficiently of shifting the curve。

Think between all of these， one of the reasons I'm bullish about powerful AI happening so fast is just that if you extrapolate the next few points on the curve。

 we're very quickly getting towards human level ability right some of the new models that that we developed some reasoning models that have come from other companies they're starting to get to what I would call the PhD or professional level right if you look at their coding ability。

 the latest model we released sonnet 3。5 the new updated version it gets something like 50% on Swbech and Swbech is an example of a bunch of professional real-wld software engineering tasks at the beginning of the year I think the state of the art was 3 or4% So in 10 months we've gone from 3% to 50% on this task and I think in another year will probably be at 90% I mean I don't know but even be might even be less than that we've seen similar things in graduate level math physics。



![](img/6846fcb7b588a1893fcebff3034afbf1_8.png)

In biology from models like open AIs 01 So if we， if we just continue to extrapolate this right in terms of skill skill that we have。

 I think if we extrapolate the straight curve within a few years， we will get to these models being。

 you know， above the highest professional level in terms of humans now will that curve continue。

You've pointed to and I've pointed to a lot of reasons why you know possible reasons why that might not happen。

 But if the extrapolation curve continues， that is the trajectory we're on。

 So Anthropic has several competitors。 It'd be interesting to get your sort of view of it all。

 Open AI， Google X AI Me What does it take to win in the broad sense of win in the space。 Yeah。

 so I want to separate out a couple things right So you know Anthropics Anthropics mission is to kind of try to make this all go well。

 right and you know we have a theory of change called race to the top right race to the top is about trying to push the other players to do the right thing by setting an example。

 It's not about being the good guy。 It's about setting things up so that all of us can be the good guy。

 I'll give a few examples of this early in the history of Anthropic one of our cofounders， Chris Ola。

 who I believe you're interviewing soon。 know the cofounder。

 the field of mechanistic interpretability， which is an attempt to understand what。



![](img/6846fcb7b588a1893fcebff3034afbf1_10.png)

Going on inside AI models so we had him and one of our early teams focus on this area of interpretability。

 which we think is good for making models safe and transparent for three or four years that had no commercial application whatsoever it still doesn't today we're doing some early betas with it and probably it will eventually but you know this is a very。

 very long research bad in one in which we've built in public and shared our results publicly and we did this because you we think it's a way to make models safer and interesting thing is that as we've done this。

 other companies have started doing it as well in some cases because they've been inspired by it in some cases because they're worried that you know if if other companies are doing this that look more responsible they want to look more responsible too no one wants to look like the irresponsible actor and and so they adopt this they adopt this as well when folks come to anthropic interpretability is often a draw and I tell them。

😡，The other places you didn't go。Tell them why you came here and and then you see soon that there's interpretability teams elsewhere as well。

 And in a way that takes away our competitive advantage because it's like， oh。

 now others are doing it as well。 but it's good it's good for the broader system。

 And so we have to invent some new thing that we're doing that others aren't doing as well and the hope is to basically bid up bid up the importance of doing the right thing and it's not it's not about us in particular right it's not about having one particular good guy other companies can do this as well。

 if they join the race to do this that' you that's the best news ever right' just it's about kind of shaping the incentives to point upward instead of shaping the incentives to point to point downward。

 And we just say this example of the field of a mechanistic interpretability is just a rigorous nonhand wavy way of doing AI safety。

 Well it's tending that way trying to。 I mean， I think we're still early。

In terms of our ability to see things， but I've been surprised at how much we've been able to look inside these systems and understand what we see。

 right unlike with the scaling laws where it feels like there's some。

 you know law that's drivingr these models to perform better。 on the inside。

 the models aren't you know there's no reason why they should be designed for us to understand them right。

 they're designed to operate， they're designed to work。

 just like the human brain or human biochemistry， they're not designed for a human to open up the hatch。

 look inside and understand them。 but we have found and you know you can talk in much more detail about this to Chris。

 that when we open them up when we do look inside them。

 we find things that are surprisingly interesting and as a side effect。

 you also get to see the beauty of these models。 you get to explore sort of the beautiful nature of large neural neural networks through the Meterp I'm amazed at how clean it's been I'm amazed at things like induction heads。

 I'm amazed at things like you know that。That we can use sparse autoencors to find these directions within the networks and that the directions correspond to these very clear concepts。

 We demonstrated this a bit with the Golden Gate Bridge cloudd so this was an experiment where we found a direction inside one of the neural networks layers that corresponded to the Golden Gate Bridge and we just turned that way up and so we released this model as a demo it was kind of half a joke for a couple days but it was illustrative of the method we developed and you could take the Golden Gate you could take the model。

 you could ask it about anything would be like how you could say how was your day and anything you asked because this feature was activated。

 it would connect to the Golden Gate Bridge so it would say。

 you know I'm feeling relaxed and expansive much like the arches of the Golden Gate Bridge or you know it would masterfully change topic the Golden Gate Bridge and it integrated There was also a sadness to it to the focus ahead and the Golden Gate Bridge。



![](img/6846fcb7b588a1893fcebff3034afbf1_12.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_13.png)

People quickly fell in love with it I think so people already miss it because it was taken down。

 I think after a day somehow these interventions on the model where you kind of adjust its behavior somehow emotionally made it seem more human than any other version of the model strong personality has a strong personality it has these kind of like obsessive interests you know we can all think of someone who's like obsessed with something so it does make it feel somehow a bit more human let's talk about the present let's talk about Claude So this year a lot has happened in March Cla 3 opusa Haiku were released then Cla 35sa in July with an updated version just now released and then also Cla 35 haiku was released Okay can you explain the difference between Opussa and Haiku and how we should think about the different versions Yeah so let's go back to March when we first released these three models。



![](img/6846fcb7b588a1893fcebff3034afbf1_15.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_16.png)

So。You know， our thinking was different companies produce kind of large and small models。

 better and worse models。 We felt that there was demand both for a really powerful model you know that might be a little bit slower that you'd have to pay more for and also for fast cheap models that are as smart as they can be for how fast and cheap whenever you want to do some kind of like you know difficult analysis like if you know I want to write code for instance or you know I want to I want to brainstorm ideas or I want to do creative writing I want to really powerful model but then there's a lot of practical applications in a business sense where it's like I'm interacting with a website you know like I'm like doing my taxes or'm you know talking to you know to like a legal advisor and I want to analyze a contract or know we have plenty of companies that are just like you know know I want to do autocomplete on my on my ID or something and for all of those things you want。

Ac fast and you want to use the model very broadly。

 So we wanted to serve that whole spectrum of needs。

 So we ended up with this you know this kind of poetry theme。 And so what's a really short poem。

 it's a haiku And so Haiku is the small， fast cheap model that is you know was at the time was really surprisingly surprisingly intelligent for how fast and cheap it was Sonet is is a mediumsd poem。

 right， a couple paragraphs。 And so sonnet was the middle model。 It is smarter。

 but also a little bit slower， a little bit more expensive and and opus like a magnum opus is a large work。

 Opus was the the largest smartest model at the time。

 So that that was the original kind of thinking behind it。

And our thinking then was well each new generation of models should shift that tradeoff curve so when we release Sonet 3。

5， it has the same roughly the same you cost and speed as the sonnet 3 model but it increased its intelligence。

 the point where it was smarter than the original Opus 3 model。

 especially for code but also just in general and so now you we've shown results for Haiku 3。5。

 and I believe Haiku 3。5， the smallest new model is about as good as Opus 3。

 the largest old model so basically the aim here is to shift the curve and then at some point there's going to be an Ous 3。

5 now every new generation of models has its own thing they use new data。

 their personality changes in ways that we kind of you know try to steer but are not fully able to steer。

😡，So there's never quite that exact equivalence where the only thing you're changing is intelligence we always try and improve other things and some things change without us without us knowing or measuring so it's it's very much an inex science in many ways the manner and personality of these models is more in art than it is a science So what is sort of the reason for。

😡，The span of time between say cloud Opus 30 and 35 what is it what takes that time if you can speak to Yeah so there's there's different there's different processes there's pre training which is you know just kind of the normal language model training and that takes a very long time that uses。

 you know， these days， you know。Ts you know tens of thousands。

 sometimes many tens of thousands of GPUs or TUs or trainingium or you know we use different platforms。

 but you know accelerator chips often often training for months there's then a kind of posttraining phase where we do reinforcement learning from human feedback as well as other kinds of reinforcement learning that that phase is getting larger and larger now and often that's less of an exact science。

 it often takes effort to get it right models are then tested with some of our early partners to see how good they are and they're then tested both internally and externally for their safety。

 particularly for catastrophic and autonomy risks So we do internal testing according to our responsible scaling policy。

 which I could talk more about that in detail and then we have an agreement with the U and the UK AI safetyty Institute as well as。

Other third party testers and specific domains to test the models for what are called CBRN risk。

 chemical， biological， radiological and nuclear， which are， you know。

 we don't think that models impose pose these risks seriously yet。

 but but every new model we want to evaluate to see if we're starting to get close to some of these these these more dangerous。

These more dangerous capabilities。 So those are the phases。

 and then you know then then it just takes some time to get the model working in terms of inference and launch it in the API。

 So there's just a lot of steps to to actually to actually making a model work。 And of course。

 you know we're always trying to make the processes as streamlined as possible right。

 we want our safety testing to be rigorous， but we want it to be rigorous and to be you know to be automatic to happen as fast as it can without compromising on rigor。

 Sam with our pretraining process and our posttraining process。

 So you know it's just like building anything else。 It's just like building airplanes。

 you want to make them you know， you want to make them safe。

 but you want to make the process streamlined and I think the creative tension between those is is an important thing and making the models work。

 Yeah， rumor on the street I who is saying that Anthropic is really good tooling so。

Probably a lot of the challenge here is on the software engineering side is to build the tooling to have like a efficient low- friction interaction with the infrastructure。

 You would be surprised how much of the challenges of building these models comes down to you software engineering。

 performance engineering you know from the outside you might think， oh man。

 we had this Eureka breakthrough know this movie with the sides if we discovered it。

 we figured it out but but but I I think all things。

 even even even you know incredible discoveries like they almost always come down to the details and often super super boring details I can't speak to whether we have better tooling than other companies I mean you know haven't been at those other companies at least at least not recently but it's certainly something we give a lot of attention to。

I don't know if you can say， but from three from cloud3 to cloud3，5。

 is there any extra pretraining going on is there mostly focused on the posttraining。

 there's been leaps in performance Yeah， I think I think at any given stage we're focused on improving everything at once just naturally like they're different teams。

 each team makes progress in a particular area in making a particular you know their particular segment of the relay race better and it's just natural that when we make a new model we put all of these things in at once So the data you have like the preference data you get from RLHF is that applicable is there ways to apply it to newer models as it get trained up Yeah。

 preference data from old models sometimes gets used for new models。

 although of course it performs somewhat better when it' trained it's trained on the new models note that we have this constitutional AI method such that we don't only use preference data we kind there's also a posttrain process where we train the model against itself。

And there's you know new types of post training the model against itself that are used every day so it's not just our LHf it's a bunch of other methods as well post training I think you know is becoming more and more sophisticated Well what explains the big leap in performance for the new sonnet 35 I mean。

 at least in the programming side and maybe this is a good place to talk about benchmarks What does it mean to get better just the number one up。

But you know I program， but I also love programming and Cla 35 through cursors what I use to assist me in programming and there was at least experientially anecdotally it's gotten smarter at programming So like what does it take to get it to get it smarter。

 we observed that as well， by the way， there were a couple very strong engineers here at Anthropic who all previous code models both produced by us and produced by all the other companies hadn't really been useful hadn't really been useful to them。

 you know they said you know maybe maybe this is useful beginner， it's not useful to me but Sonet 3。

5 the original one for the first time they said oh my God this helped me with something that know that it would have taken me hours to do This is the first model has actually saved me time So again the water line is rising and then I think you know the new sonnet has been has been even better in terms of what what it takes I mean I'll just say it's been across the board。

 It's in the pretrain。It's in the post training it's in various evaluations that we do we've observed this as well and if we go into the details of the benchmark so Swbench is basically you know since since you since you're a programmer you know you'll be familiar with like pull requests and you know just just pull requests or like you like a sort of a sort of atomic unit of work you know you could say I'm implementing one I'm implementing one thing and so Swbech actually gives you kind of a real world situation where the code basis is into the current state and I'm trying to implement something that's you know that's described and described in language we have internal benchmarks where we where we measure the same thing and you say just give the model free rein to like you know do anything run run run anything edit anything how well is it able to complete these tasks and it's that benchmark that's gone from it can do it 3% of the time to it can do it about 50% of the time。

So I actually do believe that if we you can gain benchmarks。

 but I think if we get to 100% of that benchmark in a way that isn't kind of like overtrained or game for that particular benchmark。

 probably represent a real and serious increase in kind of programming programming ability and I would suspect that if we can get to  90。

 95% that that it will represent ability to autonomously do a significant fraction of software engineering tasks。

😡，Well， ridiculous timeline question。 When is Copus3。

5 coming up not giving you an exact date but you know know as far as we know。

 the plan is still to have a Cla 3。5 Op were gonna get it before Gta 6 or like Duke Newcomb forever that game there was some game that was delayed 15 years that Duke Newcomb forever Yeah and I think Gta is not just releasing trailers know it's only been three months since we released the first sonnet Yeah it's incredible pace it just tells you about the pace the expectations for when things are gonna come out So what about 40 So how do you think about sort as these models get bigger and bigger about versioning and also just versioning in general。

 why Sonet 35 updated with the date why not Sonet3。

 it's actually naming is actually an interesting challenge here right because I think a year ago。

 most of the model was pretraining and so you。Start from the beginning and just say， okay。

 we're gonna have models of different sizes。 We're gonna train them all together and you know we'll have a family of naming schemes and then we'll put some new magic into them and then we'll have the next the next generation the trouble starts already when some of them take a lot longer than others to train that already messes up your time time a little bit but as you make big improvements in as you make big improvements in pretraining then you suddenly notice。

 oh， I can make better pretrain model and that doesn't take very long to do and but you know clearly it has the same size and shape of previous models。

 So I think those two together as well as the timing issues。

 any kind of scheme you come up with the reality tends to kind of frustrate that scheme tends to kind of break out of the breakout of the scheme it's not like software you can say。

 oh this is like3。7 This is 3。8 No you have models with different different tradeoffs you can change some things。

Your models， you can train you can change other things， some are faster and slower in inference。

 some have to be more expensive， some have to be less expensive。

 And so I think all the companies have struggled with this。

 I think we did very you know I think think we were in a good position in terms of naming when we had haiku Sonet and great we're trying to maintain it but its not's not it's not perfect so we'll try and get back to the simplicity but just the nature of the field I feel like no one's figured out naming it's somehow a different paradigm from like normal software and so we just none of the companies have been perfect at it it's something we struggle with surprisingly much relative to relative to how trivial it is the grand science of training the models So from the user side the user experience of the updated Sonet 35 is just different than the previous June 2024 Sonet 35。

It would be nice to come up with some kind of labeling that embodies that because people talk aboutsa 35 but now there's a different one and so how do you refer to the previous one and the new one and it it when there's a distinct improvement。

 it just makes conversation about it。Just challenging。 Yeah， yeah。

 I definitely think this question of there are lots of properties of the models that are not reflected in the benchmarks。

 I think I think that's that's definitely the case and everyone agrees and not all of them are capabilities。

 Some of them are you know models can be polite or brusque。

 they can be you know very reactive or they can ask you questions。

 they can have what what feels like a warm personality or a cold personality。

 They can be boring or they can be very distinctive like Golden G Claude was and we have a whole you know we have a whole team kind of focused on I think we call it Cla character Amanda leads that team and we'll talk to you about that but it's still a very inexact science and often we find that models have properties that we' not aware of the fact of the matter is that you can you know talk to a model 10000 times and there are some behavior。

you might not see just like just like with a human right I can know someone for a few months and you know not know that they have a certain skill or not know that there's a certain side to them。

 And so I think we just have to get used to this idea and we're always looking for better ways of testing our models to demonstrate these capabilities and and also to decide which which are which are the personality properties we want models to have in which we don't want to have that itself the normative question is also super interesting I got to ask a question from Reddit from Reddit boy you know there's just this fascinating to me at least it a psychological social phenomenon where people report that Cla has gotten dumber for them over time so the question is does the user complaint about the dumbing down of clo 35son it hold to any water So are these anecgolia reports。

A kind of social phenomena or did Claude， is there any cases where Claude would get dumber So this actually doesn't apply this isn't just about Claude I believe this I believe I've seen these complaints for every foundation model produced by a major company people said this about G4。

 they said it about G4 Trbo so a couple things one， the actual weights of the model。

 right the actual brain of the model that does not change unless we introduce a new model they're just a number of reasons why it would not make sense practically to be randomly substituting in substituting in new versions of the model iss difficult from an inference perspective and it's actually hard to control all the consequences of changing the weight of the model Let's say you wanted to fine tune the model to be like I don't know to like to say certainly less which an old version of sonnet used to do you actually end up changing 100 things as well。

 So we have。Process for it and we have a whole process for modifying the model。

 we do a bunch of testing on it。 we do a bunch of like we do a bunch of user testing in early customers so we both have never changed the weight of the model without without telling anyone and it wouldn't certainly in the current setup it would not make sense to do that Now there are a couple things that we do occasionally do one is sometimes we run AB tests but those are typically very close to when a model is being is being released and for a very small fraction of time So like know the day before the news sonnet 3。

5 I agree we should should got a better name it's clunky to refer to it there were some comments from people that''s it's gotten a lot better and that's because fraction were exposed to an AB test for those for those one or two days The other is that occasionally the system prompt will change the system prompt can have some effects although it's。

It's unlikely to dumb down models， it's unlikely to make them dumber and we've seen that while these two things which I'm list to be very complete。

 happen relatively happen quite infrequently the complaints about for us and for other model companies about the model change。

 the model isn't good at this， the model got more censored， the model was dumbed down。

 those complaints are constant and so I don't want to say like people are imagining either anything but like the models are for the most part not changing if I were to offer a theory I think it actually relates to one of the things I said before。

 which is that。😡，Models have many are very complex and have many aspects to them。 And so often。

 you know if I ask a model a question， you know if I'm like if I'm like do task acts versus can you do task acts。

 the model might respond in different ways。 and so they are all kinds of subtle things that you can change about the way you interact with the model that can give you very different results to be clear。

 this itself is like a failing by us and by the other model providers that the models are just just often sensitive to like small changes in word it's yet another way in which the science of how these models work is very poorly developed so you know if I go to sleep one night and I was like talking the model in a certain way。

 And I like slightly change the phrasing of how I talk to the model。

 know I I could get different results。 So that's one possible way。 The other thing is man。

 it's just hard to quantify this stuff。 It's hard to quantify this stuff。

 I think people are very excited by new models when they。OutAnd then as time goes on。

 they become very aware of they become very aware of the limitations。 so that may be another effect。

 but that that's all a very longried way of saying for the most part with some fairly narrow exceptions。

 the models were not changing I think there is a psychological effect you should start getting used to it the baseline raise it like when people who first gotten wfi on airplanes it's like magic and then now they get this thing to work this is such a piece of craft exactly it's easy to have the conspiracy theory of they're making wfi slower and slower this is probably something I'll talk to Amanda much more about but another reddit When will Cla stop trying to be my puritanical grandmother imposing its moral worldview on me as a paying customer and also what is the psychology behind making Clade overly apologetic。

So， this kind of。Reports above the experience。 A different angle and the frustration has to do with the character。

 Yeah， so a couple points on this first。 one is like things that people say on Reddit and Twitter or X or whatever it is。

 There's actually a huge distribution shift between like the stuff that people complain loudly about on social media and what actually kind of like。

You know， statistically users care about and that drives people to use the models like people are frustrated with。

 you know， things like， you know the model not writing out all the code or the model， you know。

 just just not being as good at code as it could be。

 even though it's the best model in the world on code。

 I think the majority of of things are about that。 but certainly a kind of vocal minority are you know kind of kind of raise these concerns right are frustrated by the model。

 refusing things that it shouldn't refuse or like apologizing too much or just just having these kind of like annoying verbal ticks。

 the second caveat。 And I just want to say this like super clearly because I think it's like。

Some people don't know it others like kind of know it but forget it like it is very difficult to control across the board how the models behave。

 you cannot just reach in there and say， oh， I want the model to like apologize less like you can do that you can include trading data that says like oh the models should like apologize less but then in some other situation they end up being like super rude or like overconfident in a way that's like misleading people So there are all these tradeoffs for example。

 another thing is if there was a period during which models ours and I think others as well were too verbose they would like repeat themselves。

 they would say too much you can cut down on the verbosity by penalizing the models for just talking for too long What happens when you do that if you do it in acc crude way is when the models are coding sometimes they'll say rest of the code goes here because they've learned that that's a way to economize and that they see it and then so that leaves the model to be。

😡，Called lazy encoding where they where they where they're just like you can finish the rest of it it's not it's not because we want to you know save on compute or because you know the models are lazy and you know during winter break or any of the other kind conspiracy theories that that that have come up。

 It's actually it's just very hard to control the behavior of the model to steer the behavior of the model in all circumstances at once。

 you can kind of there's this this wackmal aspect where you push on one thing and like you know know these other things start to move as well that you may not even notice or measure And so one of the reasons that that I care so much about you know kind of grand alignment of these AI systems in the future is actually these systems are actually quite unpredictable。

 They're actually quite hard to steer and control and this version we're seeing today of。

You make one thing better， it makes another thing worse。

I think that that's like a present day analog of future control problems in AI systems that we can start to study today right I think I think that that that difficulty in in steering the behavior in making sure that if we push an AI system in one direction it doesn't push it in another direction some in some other ways that we didn't want I think that that's kind of that's kind of an early sign of things to come and if we can do a good job of solving this problem of like you ask the model to like you know to like make and distribute smallpox and it says no。

 but it's willing to like help you in your graduate level of virology class like how do we get both of those things at once it's hard it's very easy to go to one side or the other and it's a multidimensional problem and so I think these questions of like shaping the model's personality。

 I think they're very hard I think we haven't done perfectly on them I think。😡。

We've actually done the best of all the AI companies。

 but still so far from perfect and I think if we can get this right。

 if we can control control the false positives and false negatives in this very kind of controlled present day environment will be much better at doing it for the future when our worry is will the models be super autonomous will they be able to make very dangerous things will they be able to autonomously build whole companies and are those companies aligned so I think of this present task as both vexing but also good practice for the future。

What's the current best way of gathering sort of user feedback， like not anecdotal data。

 but just large scale data about。Pain points or the opposite of pain points， positive things so on。

 is it internal testing。 I it a specific group testing。

 A B testing so typically we'll have internal model bashings where all of anthropic anthropic is almost 100 people people just just try and break the model they try and interact with it various ways we have a suite of evals for you know oh。

 is the model refusing in ways that it couldn't I think we even had a certainly eval because you know our again。

 one point model had this problem where like it had this annoying tick where it would like respond to a wide range of questions by saying certainly I can help you with that certainly I would be happy to do that certainly this is correct And so we had a like certainly eval which is like how often does the model say certainly but look。

 this is just a wackhamable like like what if it switches from certainly to definitely so。You know。

 every time we add a new eval and we're always evaluating for all the old things。

 So we have hundreds of these evaluations， but we find that there's no substitute for human interacting with it。

 And so it's very much like the ordinary product development process。

 We have like hundreds of people within anthropic bash the model。

 then we do you then we do externally B tests sometimes will run tests with contractors。

 we pay contractors to interact with the model So you put all of these things together and it's still not perfect。

 you still see behaviors that you don't quite want to see right you know you still see the model like refusing things that it just doesn't make sense to refuse。

 But I think trying to trying to solve this challenge trying to stop the model from doing you know genuinely bad things that you know know what everyone agrees it shouldn't do everyone everyone agrees that the model shouldn't talk about I don't know child abuse material everyone agrees the model shouldn't do that but but at the same time that。

ing these dumb in stupid ways I think drawing that line as finally as possible。

 approaching perfectly is still a challenge and we're getting better at it every day。

 but there's a lot to be solved。 and again， I would point to that as an indicator of a challenge ahead in terms of steering much more powerful models。

Do you think Claude 4。0 is ever coming up， I don't want to commit to any naming scheme because if I say if I say here。

 we're gonna have Cla4 next year and then you know then we decide that like you we should start over because there's a new type of model like I don't want to I don't want to commit to it。

 I would expect in the normal course of business that Claude 4 would come after Cla 3。

5 but you you never know in this wacky field but sort of this idea of scaling is continuing scaling is continuing there will definitely be more powerful models coming from us than the models that exist today is that is certain or if if there aren't weve deeply failed as a company can you explain the responsible scaling policy and the AI safety level standards cell levels as much as I'm excited about the benefits of these models and know' talk about that if we talk about machines of loving grace I'm worried about the risks and I continue to be worried about the risks no one。



![](img/6846fcb7b588a1893fcebff3034afbf1_18.png)

ho think that you know machines of love and grace was me saying you know I'm no longer worried about the risks of these models I think there' are two sides of the same coin the power of the models and their ability to solve all these problems in biology。

 neuroscience， economic development， governance and peace， large parts of the economy。

 those come with risks as well with great power comes great responsibility right that two are the two are paired things that are powerful can do good things and they can do bad things I think of those risks as being in several different categories perhaps the two biggest risks that I think about and that's not to say that there aren't risks today that are important but when I think of the really the things that would happen on the grandest scale one is what I call catastrophic misuse these are misuse of the models in domains like cyber bio radiological nuclear right。

That could， you know， that could。Harm or even kill thousands， even millions of people。

 if they really， really go wrong。 like these are the you know， number one priority to prevent。 And。

 and here， I would just make a simple observation， which is that。

The models you know if I look today at people who have done really bad things in the world。

 I think actually humanity has been protected by the fact that the overlap between really smart。

 welleducated people and people who want to do really horrific things has generally been small like let's say I'm someone who I have a PhD in this field。

 I have a well-paying job， there's so much to lose why do I want to like even assuming I'm completely evil which most people are not why would such a person risk their risk their risk their life。

 risk their legacy， their reputation to do something like truly。

 truly evil if we had a lot more people like that， the world would be a much more dangerous place and so my worry is that by being a much more intelligent agent AI could break that correlation and so I do have serious worries about that。

😡，Believe we can prevent those worries but you I think as a counterpoint to machines of love and grace。

 I want to say that this is there still serious risks and the second range of risks would be the autonomy risks which is the idea that models might on their own。

 particularly as we give them more agency than they've had in the past。

 particularly as we give them supervision over wider tasks like writing whole code bases or someday even effectively operating in entire entire companies they're on a long enough leash are they doing what we really want them to do it's very difficult to even understand in detail what they're doing。

 let alone let alone control it and like I said these early signs that it's hard to perfectly draw the boundary between things the models should do and things the models shouldn't do that if you go to one side you get things that are annoying and useless and you go to the other side you get other behaviors if you fix one thing it creates。

problems we're getting better and better at solving this。

 I don't think this is an unsolvable problem。 I think this is know this is a science like like the safety of airplanes or the safety of cars or the safety of drugs。

 I don't think there's any big thing we're missing I just think we need to get better at controlling these models and so these these are the two risks I'm worried about and our responsible scaling plan which I'll recognize as a very long- winded answer to your question our responsible scaling plan is designed to address these two types of risks And so every time we develop a new model we basically test it for its ability to do both of these bad things so if I were to back up a little bit I think I think we have an interesting dilemma with AI systems where they're not yet powerful enough to present these catastrophes I don't know that I don't know they'll ever prevent these catastrophes it's possible they won't but the case。



![](img/6846fcb7b588a1893fcebff3034afbf1_20.png)

For worry， the case for risk is strong enough that we should we should act now and' they're getting better very。

 very fast， right you know， I testified in the Senate that。

 you know we might have serious bio riskss within two to three years。 that was about a year ago。

 things have preceded， preceded a pacece So we have this thing where it's like it's' it's surprisingly hard to to address these risks because they're not here today。

 They don't exist。 They're like ghosts but they're coming at us so fast because the models were improving so fast。

 So how do you deal with something that's。Not here today doesn't exist。

 but is coming at us very fast。 So the solution we came up with for that in collaboration with you know people like the organization meter and Paul Cro is okay what you need for that or you need tests to tell you when the risk is getting close。

 you need an early warning system and and so every time we have a new model。

 we test it for its capability to do these CBRn tasks as well as testing it for you know how capable it is of doing tasks autonomously on its own and in the latest version of our RSP。

 which we released in the last in the last month or two。😡。

The way we test autonomy risks is model the AI model's ability to do aspects of AI research itself。

 which when the model when the AI models can do AI research they become kind of truly truly autonomous and that threshold is important for a bunch of other ways and so what do we then do with these tests。

 the RSP basically develops what we've called an if then structure。

 which is if the models pass a certain capability， then we impose a certain set of safety and security requirements on them So today's models are what's called ASL2 models that were ASL1 is for systems that manifestly don't pose any risk of autonomy or misuse so for example。

 a chess plane bot deep blue would be ASL1 it's just manifestly the case that you can't use deep blue for anything other than chess it was just designed for chess no one's going to use it to like you know to conduct。

😡，a masterful cyber attack or to you know run wild and take over the world ASL2 is today's AI systems where we've measured them and we think these systems are simply not smart enough to to you know autonomously selfreplate or conduct a bunch of tasks and also not smart enough to provide meaningful information about CBRn risks and how to build CBRn weapons above and beyond what can be known from looking at Google In fact。

 sometimes they do provide information， but but not above and beyond a search engine。

 but not in a way that can be stitched together not not in a way that kind of end to end is dangerous enough So ASL3 is going to be the point at which。

😡，The models are helpful enough to enhance the capabilities of nonstate actors， right。

 State actors can already do a lot， a lot of， unfortunately， to a high level of proficiency。

 A lot of these very dangerous and destructive things。

 the difference is that non state nonstate actors are not capable of it。

 And so when we get to ASL 3 will take special security precautions。

Designed to be sufficient to prevent theftA the model by non state actors and misuse of the model as it's deployed will have to have enhanced filters targeted at these particular areas。

 cyber bionuclear， cyber bionuclear and model autonomy。

 which is less a misuse risk and more risk of the model doing bad things itself。😡。

AL4 getting to the point where these models could could enhance the capability of of a already knowledgeable state actor and or become the you know the main source of such a risk。

 like if you wanted to engage in such a risk， the main way you would do it is through a model。

 And then I think ASL 4 on the autonomy side it's some some amount of acceleration in AI research capabilities with with an AI model。

 And then ASL 5 is where we would get to the models that that are kind of that are kind of truly capable that could exceed humanity in their ability to do to do any of these tasks。

 And so the。Point of the if then structure commitment is basically to say， look。I don't know。

 I've been。 I've been working with these models for many years。

 and I've been worried about risk for many years。 It's actually kind of dangerous to Cry wolf。

 It's actually kind of dangerous to say this that， you know， this， this model is。

 this model is risky。 And， you know， people look at it and they say this is manifestly not dangerous。

 Again， it's， it's， it's the。The delicacy of the risk isn't here today， but it's coming at us fast。

 How do you deal with that。 It's， it's really vexing to a risk planner to deal with it。

 And so this if then structure basically says， look， we don't want to antagonize a bunch of people。

 We don't want to harm our own， you know， our kind of own ability to have a place in the conversation by imposing these。

 these。Very honorrous burdens on models that are not dangerous today。

 So that if then the trigger commitment is basically a way to deal with this says you clamp down hard when you can show that the model is dangerous。

 And of course， what has to come with that is enough of a buffer threshold that that you can you can you you're not at high risk of kind of missing the danger。

 It's not a perfect framework。 we've had to change it every every you know we came out with a new one just a few weeks ago and probably probably going forward。

 we might release new ones multiple times a year， because it's hard to get these policies right。

 like technically organizationally from a research perspective， but that is the proposal。

 if then commitment and triggers in order to minimize burdens and false alarms now but really react appropriately when the danger are here。

 What do you think the timeline for ASL3 is where several of the triggers are fired and what do you think the timeline is for AsL4。

 Yeah， so that is hotly。Within the company we are working actively to prepare ASL3 security measures as well as ASL3 deployment measures I'm not going to go into detail。

 but we made we made a lot of progress on both and you know we're prepared to be I think ready quite soon would I would not be surprised I would not be surprised at all if we hit ASL3 next year there was some concern that we we might even hit it this year that' still that's still possible that could still happen it's like very hard to say but like I would be very。

 very surprised if it was like 2030 I think it's much sooner than that so there's a protocols for detecting it if then and then there's protocols for how to respond to it Yes how difficult is the second the ladder Yeah I think for ASL3 it's primarily about security and and about you know filters on the model relating to a very narrow set of areas when we deploy them。

Because at ASL3， the model isn't autonomous yet and so you don't have to worry about know kind of the model itself behaving in a bad way。

 even when it's deployed internally。 So I think the ASL3 measures are are I won't say straightforward they're rigorous but they're easier to reason about I think once we get to ASL 4 we start to have worries about the models being smart enough that they might sandbag tests they might not tell the truth about tests we had some results came out about like sleeper agents and there was a more recent paper about you know can the models mislead attempts to you sandbag their own abilities So them you know present themselves as being less capable than they are And so I think with ASL4 there's gonna be an important component of using other things than just interacting with the models。

 for example， interpretability or hidden chains of。😡。

Thought where you have to look inside the model and verify via some other mechanism that that is not。

 you know， is not as easily corrupted as what the model says that that， you know。

 that that the model indeed has some property。 So we're still working on AsL for one of the。

Properties of the RSP is that we don't specify ASL4 until we've hit ASL3 and I think that's proven to be a wise decision because even with ASL3 it again it's hard to know this stuff in detail and and we want to take as much time as we can possibly take to get these things right so for ASL3。

 the bad actor will be the humans yes and so there's a little bit more for ASL4 it's both I think is both and so deception and that's where mechanistic interpretability comes into play and hopefully the techniques used for that are not made accessible to the model。

Yeah， I mean， of course you can hook up the mechanistic interpretability to the model itself。

 but then you then you've kind of lost it as a reliable indicator of the model state。

 there are a bunch of exotic ways you can think of that it might also not be reliable like if the you know model get smart enough that it can like you know jump computers and like read the code where you're like looking at its internal state。

 We've thought about some of those， I think they're exotic enough。

 there are ways to render them unlikely， but yeah， generally you want to you want to preserve mechanistic interpretability as a kind of verification set or test set that separate from the training process of the model。

 See I think as these models become better and better conversation and become smarter social engineering becomes a thread too because Oh yeah。

 that can start being very convincing to the engineers and site companies。 Oh yeah yeah。

 it's actually like you know we've seen lots of examples of demagogueory in our life from humans and you know there's a concern that models could do that could do that as well。

One of the ways that cloud has been getting more and more powerful is it's now able to do some agent stuff。

 computer use， there's also an analysis within the sandbox of cloud。AI itself。

 but let's talk about computer use。That seems to me super exciting that you can just give Claude a task and it it takes a bunch of actions figures it out and is access to the your computer through screenshots so can you explain how that works。

And where that's headed。 Yeah， it's actually relatively simple。

 So Claude has had for a long time since since Claude3 back in March。

 the ability to analyze images and respond to them with text the only new thing we added is those images can be screenshots of a computer and in response we train the model to give a location on the screen where you can click and or buttons on the keyboard。

 you can press in order to take action it turns out that with actually not all that much additional training。

 the models can get quite good at that task。 It's a good example of generalization people sometimes say if you get to lower or bit you're like halfway to anywhere right because of how much it takes to escape the gravity well。

 if you have a strong pretrain model， I feel like you're halfway anywhere in terms of in terms of the intelligence space and so actually it didn't take all that much to get to get Clade to do this and you can just set that in a loop。

 give the model a screenshot。

![](img/6846fcb7b588a1893fcebff3034afbf1_22.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_23.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_24.png)

What to click on give it the next screenshot， tell it what to click on and that turns into a full kind of almost almost 3D video interaction of the model and it's able to do all of these tasks right you know we showed these demos where it's able to like fill out spreadsheets it's able to kind like interact with a website it's able to it's able to open all kinds of programs different operating systems Windows Linux Mac so you know I think all of that is very exciting I will say while in theory there's nothing you could do there that you couldn't have done through just giving the model the API to drive the computer screen this really lowers the barrier and's there's a lot of folks either aren't in a position to interact with those As or it takes them a long time to do it's just the screen is just a universal interface that's a lot easier to interact with and so I expect over time this is gonna lower a bunch of barriers now honestly。

The current model has there's it leaves a lot still to be desired and we were we were honest about that in the blog right it makes mistakes。

 it missed clicks and we we you know we were careful to warn people， hey。

 this thing isn't you can't just leave this thing to you know run on your computer for minutes and minutes。

Youve got to give this thing boundaries and guard rails。

 And I think that's one of the reasons we released it first in an API form rather than kind this kind of just handed the consumer and give it control of of their computer but I definitely feel that it's important to get these capabilities out there as models get more powerful we're going to have to grapple with how do we use these capabilities safely。

 how do we prevent them from being abused and I think releasing releasing the model while the capabilities are still are still limited is very helpful terms of in terms of doing that。

 I think since it's been released number of customers I think Relet maybe was maybe one of the mostestest quickest quickest to deploy things have made use of it in various ways people have hooked up demos for Windows desktops。

 Max Linux。Lux machines so yeah it's been it's been it's been very exciting I think as as with anything else。

 you know it comes with new exciting abilities and then you know then with those new exciting abilities we have to think about how to how to make the model say reliableable do what humans want them to do I mean it's the it's the same story for everything same thing it's that same tension but but the possibility of use cases here is just the range is incredible So how much to make it work really well in the future how much do you have to especiallyly kind of go beyond what's the pretrain models doing do more posttrain RHf or supervised fine tuning or synthetic data just for the agent I think speaking at a high level it's our intention to keep investing a lot in making making the model better like I think I think you know we look at some of the some of the benchmarks for previous models we're like could do 6% of the time and now our model of do it 14。

or 22% of the time and yeah， we want to get up to， you know。

 the human level reliability of 80 90% just like anywhere else， right。

 we're on the same curve that we were on with Swbech。

 where I think I would guess a year from now the models can do this very， very reliably。

 but you got to start somewhere。So you think it's possible to get to the human level 90% basically doing the same thing you're doing now or is it has to be special for computer use I mean。

 it depends what you mean by you know special and special in general I generally think you know the same kinds of techniques that we've been using to train the current model I expect that doubling down in those techniques in the same way that we have for code for code for models in general for other kit for image input you know for voice I expect those same techniques will scale here as they have everywhere else。

 but this is giving sort of the power of action to Cla and so you could do a lot of really powerful things that you could do a lot of damage also yeah no we've been very aware of that。

 look my view actually is computer use isn't a fundamentally new capabilities like the CBRn or autonomy capabilities are it's more like it kind of opens the。

per for the model to use and apply its existing abilities。 and so the way we think about it。

 going back to our RP is nothing that this model is doing。Inherently increases， you know。

 the risk from an RP RSP perspective。 But as the models get more powerful。

 having this capability may make it scarier once it， you know。

 once it has the cognitive capability to。You know， to do something at the ASL3 and ASL4 level。

 you know this may be the thing that kind of unbounds it from doing so。 So going forward。

 certainly this modality of interaction is something we have tested for and that we will continue to test for an RP going forward。

 I think it's probably better to have to learn and explore this capability before the model is super know super capable。

 Yeah there's a lot interesting attacks like prompt injection because now you've widened the aperture so you can prompt inject through stuff on screen So if this becomes more and more useful。

 then there's more and more benefit to inject inject stuff into the model。

 it goes to certain web page。 it could be harmless stuff like advertisements or it could be like harmful stuff Yeah。

 I mean， we've thought a lot about things like spam Capcha， know mass。

 there's you know one secret I'll tell you if you've invented a new technology not necessarily the biggest misuse。

 but but the first misuse， you'll see scam。It's just petty scams like you it's it's like it's like a thing as old people scaming each other it's it's this it's this thing as old as time and and and it's just every time you got to deal with it It's almost like silly to say。

 but it's it's true sort of bots and spam in general is a thing I guess more and more intelligent Yes it's it's just there there are a lot of like like I said。

 like there are a lot of petty criminals in the world and and and you know it's like every new technology is like a new way forty petty criminals to do something。

 you know， something stupid and malicious。嗯。Is there any ideas about sandboxing it。

 Like how difficult is the sandboxing task。 Yeah， we sandbox during training。 So for example。

 during training， we didn't expose the model to the internet。

 I think that's probably a bad idea during training because the model can be changing its policy。

 it can be changing what it's doing and it's having an effect in the real world in terms of actually deploying the model it kind of depends on the application like sometimes you want the model to do something in the real world。

 but of course you can always put you can always put guardrails on the outside you can say。

 okay well this model is not gonna move data from models not gonna move any files from my computer or my web server to anywhere else now when you talk about sandboxing again when we get to AsL for none of these precautions are going to make sense there where when when you talk about asl for you then the model is being kind there's a theoretical worry the model can be smart enough to break it to。

breakout of any box。 And so there we need to think about mechanistic interpretability about you know if we're if we're going to have a sandbox。

 it would need to be a mathematically provable sand。

 but you know that's that's a whole different world than what we're dealing with with the models today。

😡，Yeah， the science of building a box from which ASL4 AI system cannot escape I think it's probably not the right approach。

 I think the right approach instead of having something you know unaligned that like you're trying to prevent it from escaping。

 I think it's better to just design the model the right way or have a loop where you know you look inside you look inside the model and you're able to verify properties and that gives you an opportunity to like iterate and actually get it right。

 I think I think containing containing bad models is much worse solution than having good models。

Let me ask about regulation What's the role of regulation in keeping AI safe So for example。

 can described California AI regulation bill SB 1047 that was ultimately vetoed by the governor what are the pros and cons of this bill we ended up making some suggestions to the bill and then some of those were adopted and you know we felt I think I think quite positively quite positively about the bill by the end of that it did still have some downsides and you know of course of course it got vetoed I think at a high level。

 I think some of the key ideas behind the bill are you know I would say similar to ideas behind our RSP and I think it's very important that some jurisdiction whether it's California or the federal government and or other countries and other states passes some regulation like this and I can talk through why I think that's so important So I feel good about our RSP it's not perfect it needs to be iterated。



![](img/6846fcb7b588a1893fcebff3034afbf1_26.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_27.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_28.png)

on a lot， but it's been a good forcing function for getting the company to take these risks seriously。

 to put them into product planning， to really make them a central part of work at Anthropic and to make sure that all the thousand people and it's almost thousand people now at Anthropic understand that this is one of the highest priorities of the company。

 if not the highest priority but，One， there are still some companies that don't have RSP like mechanisms like OpenaiI Google did adopt these mechanisms a couple months after Anthropic did。

 but there there are other companies out there that don't have these mechanisms at all。

 And so if some companies adopt these mechanisms and others don't it's really going to create a situation where some of these dangers have the property that it doesn't matter if three out of five of the companies are being safe。

 if the other two are are being unsafe， it creates this negative externality and I think the lack of uniformity is not fair to those of us who have put a lot of effort into being very thoughtful about these procedures。

 The second thing is I don't think you can trust these companies to adhere to these voluntary plans in their own I like to think that Anthropic will。

 we do everything we can that we will our RSP is checked by our long-term benefit trust。😡。

You we do everything we can to adhere to our own RSP。

 but you know you hear lots of things about various companies saying， oh。

 they said they would do they said they would give this much compute and they didn't they said they would do this thing and they didn't I don't think it makes sense to litigate particular things that companies have done but I think this broad principle that like if there's nothing watching over them。

 there's nothing watching over us as an industry， there's no guarantee that will do the right thing and the stakes are very high and so I think I think it's important to have a uniform standard that everyone follows and to make sure that simply that the industry does what a majority of the industry has already said it is important and has already said that they definitely will do some people know I think there's a class of people who are。

Against regulation on principle， I understand where that comes from。 If you go to Europe and。

 you know you see something like GDPR， you see some of the other stuff that that that they've done。

 you know， some of it's good， but but some of it is really unnecessarily burdened some。

 and I think it's fair to say， really has slowed， really has slowed innovation。

 And so I understand where people are coming from on priors。

 I understand why people come from start from that， start from that position。 But but again。

 I think AI is different。 If we go to the very serious risks of autonomy and misuse that that I talked about。

 you know， just just a few minutes ago， I think。That those are unusual and they warrant't an unusually strong response and so I think it's very important again。

 we need something that everyone can get behind you know I think one of the issues with SB1047。

 especially the original version of it was it had a bunch of the structure of RSP but it also had a bunch of stuff that was either clunky or that that just would have created a bunch of burdens。

 a bunch of hassle and might even have missed the target in terms of addressing the risks you don't really hear about it on Twitter。

 you just hear about kind of you know people are cheering for any regulation and then the folks who are against make up these often quite intellectually dishonest arguments about how you it'll make us move away from California built doesn't apply if you're headquartered in California bill only applies if you do business in California。

or that it would damage the open source ecosystem or that it would you know it would cause all of these things。

 I think those were mostly nonsense， but there are better arguments against regulation。

 there's one guy Dean Ball who' really you I think a very scholarly scholarly analyst who looks at what happens when a regulation is put in place and ways that they can kind of get a life of their own or how they can be poorly designed and so our interest has always been we do think there should be regulation in this space。

 but we want to be an actor who make sure that that regulation is something that's surgical that's targeted at the serious risks and is something people can actually comply with because something I think the advocates of regulation don't understand as well as they could is if we get something in place that is that's poorly targeted that waste a bunch of people's time。

What's going to happen is people are going to say see these safety risks there。

 you know this is nonsense。 I just you know I just had to hire 10 lawyers you know to fill out all these forums。

 I had to run all these tests for something that was clearly not dangerous and after six months of that there will be a groundwell and will end up with a durable consensus against regulation and so I think the worst enemy of those who want real accountability is badly designed regulation we need to actually get it right and if there's one thing I could say to the advocates it would be that I want them to understand this dynamic better and we need to be really careful and we need to talk to people who actually have who actually have experience seen how regulations play out in practice and the people who have seen that understand to be very careful if this was some lesser issue I might be against regulation at all but what I want the opponents to understand is。

😡，The underlying issues are actually serious're not they're not something that I or the other companies are just making up because of regulatory capture。

 They're not scifi fantasies， they're not they're not any of these things。

 you know every every time we have a new model every few months。

 we measure the behavior of these models and they're getting better and better at these concerning tasks just as they are getting better and better at。

😡，You know， good， valuable， economically useful tasks。

 And so I would just love it if some of the former， you know I think SB1047 was very polarizing。

 I would love it if some of the most reasonable opponents and some of the most reasonable proponents would sit down together and you know I think I think know the different AI companies you know Anthropic was the only AI company that you know felt positively in a very detailed way。

 I think Elon tweeted tweeted briefly something positive。

 but you know some of some of the big ones like Google， Open AI， Me。

 Microsoft were pretty staunchly against I would really like as if if you know some of the key stakeholders。

 some of you most thoughtful proponents and some of the most thoughtful opponents would sit down and say。

 how do we solve this problem in a way that the proponents feel brings a real。

uction and risk and that the opponents feel that it is not。

 it is not hampering the the industry or hampering innovation any more necessary than it than it needs to。

 And， and I think， for whatever reason， that things got too polarized and those two groups didn't get to sit down in the way that they should。

 And， and I feel， I feel urgency。 I really think we need to do something in 2025。 you know。

 if we get to the end of 2025 and we still done nothing about this。 then I'm gonna to be worried。

 I'm not， I'm not worried yet because again， the risks aren't here yet。

 But but I think time is running short。 and come up with something surgical。 like I said， Yeah， yeah。

 yeah， exactly。 And and we need to get， we need to get away from this。 this。

This intense pro safety versus intense anti regulatory rhetoric， right。

 it's turned into these these flame wars on Twitter and nothing good's going to come with that。

So there's a lot of curiosity about the different players in the game。 One of the OGs is open AI。

 You have had several years of experience at Open AI。 What's your story and history there， Yeah。

 so I was at Open AI for for roughly five years for the last， I think it was a couple years。

 know I was vice president of research there probably myself and Ilia suits give her were the ones who you know really kind of set set the research direction around 2016 or 2017。

 I first started to really believe in or at least confirm my belief in the scaling hypothesis when Ilia famously said to me the thing you need to understand about these models is they just want to learn the models just want to learn again。

 sometimes there are these one sentence there are these one sentences。

 these Zen cones that you hear them and you're like， that explains everything。

 that explains like a thousand things that I've seen and ever after I had this visualization in my head of like you optimize the models in the right way。

 you point the models in the right way。They just want to learn。

 they just want to solve the problem regardless of what the problem is。

 so get out of their way basically get out of their way。 Yeah。

 don't impose your own ideas about how they should learn or and you know this was the same thing as Rich Sutton put out in the bitter lesson or Gn put out in the scaling hypothesis you know I think generally the dynamic was you know I got this kind of inspiration from Iian from others folks like Alec Raford who did the original G1 and then ran really hard with it me and my collaborators on G2 G3 Rl from human feedback。

 which was an attempt to kind of deal with the early safety and durability。

 things like debate and amplification heavy on interpretability So again the combination of safety plus scaling probably 2018。

 2019， 2020 those were kind of the years when myself and my collaborators， probably you know。

Many of whom became cofounders of Anthropic kind of really had a vision and and like drove the direction why did you leave why you said to leave Yeah so look I'm going to put things this way and know I think it ties to the race to the top which is you know in my time at Open AI when I'd come to see as I'd come to appreciate the scaling hypothesis and as I'd come to appreciate kind of the importance of safety along with the scaling hypothesis the first one I think know open AI was was getting was getting on board with the second one in a way had always been part of open AI's messaging but you know over many years of the time the time that I spent there I think I had a particular vision of how these how we should handle these things how we should be brought out in the world the kind of principles that the organization should have and look I mean there were like many。

 many discussions about like you know should the company do this， the company do。

That like there's a bunch of misinformation out there。

 people say like we left because we didn't like the deal with Microsoft false。

 although you know it was like a lot of discussion。

 a lot of questions about exactly how we do the deal with Microsoft we left because we didn't like commercialization that's not true We built G3 which was the model that was commercialized I was involved in commercialization。

 it's more again about how do you do it like civilization is going down this path to very powerful AI What's the way to do it that is cautious straightforward honest that build trust in the organization and an individuals how do we get from here to there and how do we have a real vision for how to get it right How can safety not just be something we say because it helps with recruiting and I think at the end of the day if you have a vision for that forget about anyone else's vision I don't want to talk about anyone else's vision if you have。

For how to do it。 you should go off and you should do that vision。

 It is incredibly unproductive to try and argue with someone else's vision。

 You might think they're not doing it the right way。 You might think they're dishonest， who knows。

 maybe you're right， maybe you're not But what you should do is you should take some people you trust and you should go off together and you should make your vision happen and if your vision is compelling if you can make it appeal to people some。

 you know some combination of ethically you know in the markets you know if you if you can make a company that's a place people want to join that you engages in practices that people think are are reasonable while managing to maintain its position in the ecosystem at the same time。

 if you do that， people will copy it and the fact that you were doing it。

 especially the fact that you're doing it better than they are causes them to change their behavior in a much more compelling way than if they're your boss and you're arguing with them。

Don't know how to be any more specific about it than that。

 but I think it's generally very unproductive to try and get someone else's vision to look like your vision。

 It's much more productive to go off and do a clean experiment and say this is our vision this is how we're gonna do things your choice is you can you can ignore us。

 you can reject what we're doing or you can you can start to become more like us。

 An imitation is the sincerest form of flattery And that plays out in the behavior of customers that pays out in the behavior of the public that plays out in the behavior of where people choose to work。

 And again， again， at the end it's not about one company winning or another company winning if。

If we or another company are engaging in some practice that。

 you know people people find genuinely appealing。 and I want it to be in substance。

 not just not just in appearance。 And you know I think I think researchers are sophisticated and they look at substance。

 and then other companies start copying that practice and they win because they copied that practice。

 that's great。 That's success。 That's like the race to the top。

 It doesn't matter who wins in the end， as long as everyone is copying everyone else's good practices right One way I think of it is like the thing we're all afraid of is the race to the bottom right and the race to the bottom。

 doesn't matter who wins because we all lose， right like you know in the most extreme world。

 we we make this autonomous AI that know the robots enslave us or whatever I mean。

 that's half joking， but you know that is the most extreme thing that could happen。

 then it doesn't matter which company was ahead。 if instead you create a race to the top where people are competing to engage in good in good practices。

Then you know at at the end of the day， you know， doesn't matter who ends up who ends up winning。

 doesn't even matter who started the race to the top。 The point isn't to be virtuous。

 The point is to get the system into a better equilibrium than it was before and and individual companies can play some role in doing this individual companies can you know can help to start it can help to accelerate it。

 and frankly， I think individuals at other companies have done this as well。

 the individuals that when we put out an RSP react by pushing harder to get something similar get something similar done at other companies。

 Sometimes other companies do something that's like we're like oh it's a good practice。

 we think that's good。 we should adopt it too The only difference is know I think we are we try to be more forward leaning。

 We try and adopt more of these practices first and adopt them more quickly when others when others invent them。

 but I think this dynamic is what we should be pointing at and that I I think it abstracts away the question of。

You know which companies winning， who trusts who I think all all these questions of drama are profoundly uninteresting and the thing that matters is the ecosystem that we all operate in and how to make that ecosystem better because that constrains all the players and so Anthropic is this kind of clean experiment built on a foundation of like what concretely AIAT should look like look I'm sure we've made plenty of mistakes along the way。

 the perfect organization doesn't exist。 It has to deal with the imperfection of1 thousand0 employees。

 it has to deal with the imperfection of our leaders， including me。

 it has to deal with the imperfection of the people we've we've put you know to oversee the imperfection of the leaders like like the board and the long-term benefit trust's all it's all a set of imperfect people trying to aim imperfectly at some ideal that will never perfectly be achieved that's what you sign up for it that's what it will always be but imperfect doesn't mean you just give up。

There's better and there's worse。 And hopefully， hopefully we can begin to build。

 we can do well enough that we can begin to build some practices that the whole industry engages in。

 And then， you know， my guess is that multiple of these companies will be successful and drop it will be successful。

 These other companies， like once I've been at the past will also be successful。

 and some will be more successful than others。 that's less important than again。

 that we we align the incentives of the industry。 And that happens partly through the race to the top。

 partly through things like RSP， partly through again， selected surgical regulation。

 He said talent density beats talent mess。So can you explain that， can you expand on that。

 can you just talk about what it takes to build a great team of AI？Researchers and engineers。

 This is one of these statements that's like more true every every month， every month。

 I see the statement is more true than I did the month before。

 So if I were to do with thought experiment， let's say you have a team of 100 people that are super smart。

 motivated and aligned with the mission。 And that's your company。

 or you can have a team of 1000 people， where 200 people are super smart。

 super aligned with the mission。 And then like and then like 800 people are let's just say you pick 800 like random random big tech employees。

 which would you rather have right， the talent mass is greater in the group of in the group of 1000 people。

 you have you have even even a larger number of incredibly talented， incredibly aligned。

 incredibly smart people。 but the issue is just that if。

Every time someone super talented looks around， they see someone else super talented and super dedicated。

 That sets the tone for everything。 right That sets the tone for everyone is super inspired to work at the same place。

 everyone trust everyone else。 If you have 1000 or 10000 people and things have really regressed。

 right， you are not able to do selection and you're choosing random people。

 What happens is then you need to put a lot of processes and a lot of guardrails in place。

 just because people don't fully trust each other。 You have to adjudicate political battles。

 like there are so many things that slow down the org's ability to operate。

 And so we're nearly1000 people。 And you know we've tried to make it so that as large a fraction of those thousand people as possible are like super talented。

 super skilled。 It's one of the reasons we' we've slowed down hiring a lot in the last few months。

 We grew from 300 to 800， I believe， I think in the first7，8 months of the year。 And now。

slowed down we're at like you know the last three months we went from 800 to 900950 something like that。

 Don't quote me on the exact numbers but I think there's an inflection point around 1000 and we want to be much more careful how how we grow early on and now as well we've hired a lot of physicists theoretical physicists can learn things really fast even even more recently as we've continued to hire that we've really had a high bar for on both the research side and the software engineering side have hired a lot of senior people。

 including folks who used to be at other companies in this space and we've just continued to be very selective。

 It's very easy to go from 100 to 1000 and 100 to 10000 without paying the attention to making sure everyone has a unified purpose It's so powerful if your company consists of a lot of different fiefdoms that all want to do their own thing that are all optimizing for their own thing。

It's very hard to get anything done， but if everyone sees the broader purpose of the company。

 if there's trust and there's dedication to doing the right thing that is a superpower that in itself I think can overcome almost every other disadvantage and you know the Steve Jobs。

 a players a players want to look around and see other a players is another way of saying I don't know what that is about human nature but it is demotivating to see people who are not obsessively driving towards a singular mission and it is on the flip side of that super motivating to see that it's interesting what's it take to be a great AI researcher or engineer from everything you've seen from working with so many amazing people Yeah I think the number one quality especially on the research side but really both is openmindedness sounds easy to be openminded you're just like oh I'm open to anything but you know if I think about my own early history in the scaling hypothesis。

I was seeing the same data others were seeing。 I don't think I was like a better programmer or better at coming up with research ideas than any of the hundreds of people that I worked with in some ways in some ways I was worse you know like I've never like you know precise programming of like you know finding the bug writing the GPU kernels like I could point you to 100 people here who are better who are better at that than I am but but the thing that I think I did have that was different was that I was just willing to look at something with new eyes right people said oh you know we don't have the right algorithms yet。

 we haven't come up with the right。😡，The right way to do things。 And I was just like I don't know。

 like， you know， this neural net has like 30 billion，30 million parameters。

 like what if we gave it 50 million instead， like let's plot some graphs like that that basic scientific mindset of like。

 oh man I just I just like you know， I see some variable that I could change like what happens when it changes like lets let's try these different things and like create a graph for even this was like the simplest thing in the world。

 change the number of know， this wasn't like PhD level experimental design this was like this was like simple and stupid。

 anyone could have done this if you just hold them that it was important。

 It's also not hard to understand。 You didn't need to be brilliant to come up with this。

 But you put the two things together。 And you know， some tiny number of people。

 some single digit number of people have driven forward the whole field by realizing this。 you know。

 it's often like that。 if you look back at the discovery， know the discoveries。In historyory。

 they're often like that and so this openmindedness and this willingness to see with new eyes that often comes from being newer to the field。

 often experience is a disadvantage for this that is the most important thing it's very hard to look for and test for but I think it's the most important thing because when when you find something some really new way of thinking thinking about things when you have the initiative to do that。

 it's absolutely transformative and also be able to do kind of rapid experimentation and in the face of that。

 be openminded and curious and looking at the data these fresh eyes and see what is that it's actually saying that applies in mechanistic interpretability it's another example of this like some of the early work and mechanistic interpretability so simple it's just no one thought to care about this question before you said what it takes to be a great AI research can we rewind the clock back what advice would you give to people interested in AI they're young looking forward。

 How can I make an impact on the world。I think my number one piece of advice is to just start playing with the models。

 This was actually， I worry a little this seems like obvious advice。 Now， I think three years ago。

 it wasn't obvious。 And people started by， oh， let me read the latest reinforcement learning paper。

 me， you know， let me， let me kind of no， I mean， that was really that was really and I mean。

 you should do that as well。 But now， you know， with wider availability of models and APIs。

 People are doing this more。 But I think。I think just experiential knowledge。

 these models are new artifacts that no one really understands。

 And so getting experience playing with them， I would also say again。

 in line with the like do something new think in some new direction like there are all these things that haven't been explored。

 like， for example， mechanistic interpretability is still very new it's probably better to work on that than it is to work on new model architectures because it's。

 you know， it's more popular than it was before， there are probably like 100 people working on it。

 but there aren't like 10000 people working on it And it's it's this fertile area for study like like you know theres there's so much like low hangingging fruit。

 you can just walk by and you know， you can just walk by and you can pick things and and the only reason。

 for whatever reason people aren't people aren't interest in it enough。

 I think there are some things around。Long long horizon learning and long horizon tasks where there's a lot to be done。

 I think evaluations are still we're still very early in our ability to study evaluations。

 particularly for dynamic systems acting in the world， I think there's some stuff around multi agent。

Skate where the puck is going is my is my advice。 and you don't have to be brilliant to think of it。

 like all the things that are gonna be exciting in five years。

 like people even mention them as like you know conventional wisdom。

 but like it's it's just somehow there's this barrier that people don't people don't double down as much as they could or they're afraid to do something that's not the popular thing。

 I don't know why it happens that like getting over that barrier is that's my number one piece of advice。

 let's talk if it could a bit about posttrain so it seems that the modern posttrain recipe has a little bit of everything。

 So supervise fine tuning RH。The the constitutional AI was R AF best acronym it's again the naming thing and then synthetic data seems like a lot of synthetic data or at least trying to figure out ways to have high quality synthetic data So what's the if this is a secret sauce that makes anthropic clause so incredible what how much of the magic is in the pretraining。

 how much it is in the posttraining。 Yeah， I mean， so first of all。

 we're not perfectly able to measure that ourselves you know。

 when you see some some great characterability， sometimes it's hard to tell whether it came from pretraining or posttraining we've developed ways to try and distinguish between those two。

 but they're not perfect， you know the second thing I would say is you know's when there isn't advantage and I think we've been pretty good at in general in general at RL。

 perhaps perhaps the best although I don't know because I don't see what goes on inside other companies。

Usually it isn't Oh my God， we have this secret magic method that others don't have right。

 Usually it's like， well， you know， we got better at the infrastructure so we could run it for longer or you know we were able to get higher quality data or we were able to filter our data better or we're able to combine these methods in practice。

 it's usually some boring matter of matter of kind of practice and tradecraft。

 So you know when I think about how to do something special in terms of how we train these models。

 both pretraining， but even more so posttraining you know I really think of it a little more again。

 as like designing airplanes or cars。 like you know it's not just like oh man， I have the blueprint。

 like maybe that makes you make the next airplane， but like there's some there's some cultural tradecraft of how we think about the design process that I think is more important than than any particular gizmo we're able to invent。

 but let me ask a specific techniques。 So first on RLHF， what do you think。

Just zooming out intuition， almost philosophy。 Why do you think RH cheff worked so well。

If I go back to like the scaling hypothesis， one of the ways to skate the scaling hypothesis is if you train for X and you throw enough compute at it。

 then you get X and so RLHF is good at doing what humans want the model to do or at least to state it more precisely doing what humans who look at the model for a brief period of time and consider different possible responses。

 what they prefer as the response which is not perfect from both a safety and capabilities perspective in that humans are often not able to perfectly identify what the model wants and what humans want in the moment may not be what they want in the long term there's a lot of subtlety there but the models are good at producing what the humans in some shallow sense want and it actually turns out that you don't even have to throw that much compute at it because of another thing which is this thing about a strong pretrained model being halfway anywhere so once you have the pretrained model。

You have all the representations you need to get the model to get the model where you where you want it to go So do you think RHf？

Makes the model smarter or just appear smarter to the humans。

 I don't think it makes the model smarter。 I don't think it just makes the model appear smarter。

 It's like RLhf like bridges the gap between the human and the model right I could have something really smart that like can't communicate at all right we all know people like this。

 people who are really smart， but can't understand what they're saying。

 So I think I think RLHf just bridges that gap。 I think it's not it's not the only kind of Rl we do。

 it's not the only kind of Rl that will happen in the future。

 I think Rl has the potential to make models smarter to make them reason better to make them operate better to make them develop new skills even and perhaps that could be done you know even in some cases with human feedback。

 but the kind of RLHf we do today mostly doesn't do that yet although we're very quickly starting to be able to。

 but it appears to sort of increase if you look at the metric of helpfulness and increases that。

So increases what was this word in Leopold's essay unhobbling where basically the models are hobbled and then you do various trainings to them to unhobble them so you know I like that word because it's like a rare word so I think R like Jeff unhobbles the models in some ways and then there are other ways where a model hasn't yet been unhobbled and needs needs to un hobble if you can say in terms of cost is pretraining the most expensive thing or is posttraining creep up to that at the present moment it is still the case that pretraining is the majority of the cost I don't know what to expect in the future but I could certainly anticipate a future where posttraining is the majority of the cost in that future you anticipate would it be the humans or the AI that's the costly thing for the post training。



![](img/6846fcb7b588a1893fcebff3034afbf1_30.png)

I I don't think you can scale up humans enough to get high quality any any kind of method that relies on humans and uses a large amount of compute。

 it's going to have to rely on some scaled supervision method like like you know。

 debate or iterated amplification or something like that。 So on that。

It's super interesting set of ideas around constitutional A I can describe what it is as first detailed in December 2020 Yes to paper and and beyond that。

 what is it Yes， so this was from two years ago the basic idea is so we describe what RLHF is you have model and you know spits out you know like you just sample from it twice。

 it spits out to a possible responses and you're like human which response you like better or another variant of it is rate this response on a scale of one to7 So that's hard because you need to scale up human interaction and it's very implicit right I don't have a sense of what what I want the model to do。

 I just have a sense of like what this average of 10 humans wants the model to do。

So two ideas one is could the AI system itself decide which response is better right could you show the AI system these two responses and ask which responses better and then second well what criterion should the AI use and so then there's this idea could you have a single document。

 a constitution if you will that says these are the principles the model should be using to respond and the AI system reads those it reads those principles as well as reading the environment and the response and it says well how good did the AI model do it's basically a form of self-play you're kind of training the model against itself and so the AI gives the response and then you feed that back into what's called the preference model which in turn feeds the model to make it better so you have this triangle of like the AI。

 the preference model and the improvement of the AI itself and we should say that in the Constitution the set of principles are like human interpretable they're like。

😡，Yeah yeah it's something both the human and the AI system can read so it has this nice this nice kind of translaability or symmetry you know in practice we both use a model constitution and we use RLHF and we use some of these other methods so its it's turned into one tool in a toolkit that both reduces the need for RLHF and increases the value we get from using each data point of RLHF it also interacts in interesting ways with kind of future reasoning type RL methods so it's one tool in the toolkit but but I think it is a very important tool it's a compelling one to us humans you know thinking about the founding fathers and the founding of the United States。

The natural question is who and how do you think gets to define the Constitution the set of principles in the Constitution Yeah。

 so I'll give like a practical answer and a more abstract answer。

 I think the practical answer is like look in practice。

 models get used by all kinds of different like customers right and so you can have this idea where you know the model can can have specialized rules or principles。

 you know， we fine tune versions of models。Implicitly we've talked about doing it explicitly。

 having having special principles that people can build into the models so from a practical perspective。

 the answer can be very different from different people customer service agent behaves very differently from a lawyer and obeys different principles but I think at the base of it there are specific principles that models have to obey I think a lot of them are things that people would agree with everyone agrees that' we don't want models to present these CBRN risks I think we can go a little further and agree with some basic principles of democracy and the rule of law beyond that it gets very uncertain and there are goal is generally for the models to be more neutral to not espouse a particular point of view and more just be kind of like wise agents or advisors that will help you think things through and will present present possible considerations but don't express strong。

Or specific opinions。Open AI released a model spec where it kind of clearly concretely defines some of the goals of the model and specific examples like A B。

 how the model should behave。 Do you find that interesting， By the way， I should mention the。

 I believe the brilliant John Schulman was a part of that。 He's not an anthropic。



![](img/6846fcb7b588a1893fcebff3034afbf1_32.png)

Do you think this is a useful direction Myanthropic release a model spec as well Yeah。

 so I think that's a pretty useful direction。 Again， it has a lot in common with constitutional AI。

 So again， another example of like a race to the top we have something that's like we think you know a better and more responsible way of doing things。

 It's also a competitive advantage。 others kind of discover that it has advantages and then start to do that thing。

 we then no longer have the competitive advantage， but it's good from the perspective that now everyone has adopted a positive practice that others were not adopting And so our response to that as well looks like we need a new competitive advantage in order to keep driving this race upwards。

 So that's how I generally feel about that。 I also think every implementation of these things is different。

 So you know there are some things in the model spec that we're not in constitutional AI。

 And so you we can always we can always adopt those things or know at least learn from them。

 So again， I think this is an example of like。Positive dynamic that I think we should all want the field to have。

 Let's talk about the incredible essay machines of love and grace。

 I recommend everybody read it It's a long one It is rather along。 Yeah。

 it's really refreshing to read concrete ideas about what a positive future looks like and you took sort of a bold stance because like it's very possible that you might be wrong on the dates or it specific I'm fully expecting to you know will definitely be wrong about all the details。

 I might be be just spectacularly wrong about the whole thing and people will you know will laugh at me for years。

's' that's just how the future works。😊。

![](img/6846fcb7b588a1893fcebff3034afbf1_34.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_35.png)

So you provided a bunch of concrete positive impacts of AI and how you know exactly a superintel AI might accelerate the rate of breakthroughs and。

 for example， biology and chemistry that would then lead to things like we cure most cancers。

 prevent all infectious disease， double the human lifespan and so on so let's talk about this essay first can you give a high level vision of this essay and what key takeaways that people have Yeah。

 I have spent a lot of time in Anthropic has spent a lot of effort on like you know how do we address the risks of AI right how do we think about those risks like we're trying to do a race to the top。

 you know what that requires us to build all these capabilities and the capabilities are cool but you know you know we're like a big part of what we're trying to do is like is like address the risks and the justification for that is like well you know all these positive things you know the market is this very healthy organism right it's going to produce all the positive things。

The risks， I don't know。 We might mitigate them。 We might not。

 And so we can have more impact by trying to mitigate the risks。

 But I noticed that one flaw in that way of thinking。 and it's。

 if not a change in how seriously I take the risks， it's。

 it's maybe a change in how I talk about them is that。You know。

 no matter how kind of logical or rational that line of reasoning that I just gave might be。

 if if you kind of only talk about risks， your brain only thinks about risks。

 and so I think it's actually very important to understand what if things do go well。

 And the whole reason we're trying to prevent these risks is not because we're afraid of technology。

 not because we want to slow it down， it's it's it's because。

If we can get to the other side of these risks， if we can run the gauntlet successfully to put it in stark terms。

 then on the other side of the gauntlet are all these great things。

 And these things are worth fighting for and these things can really inspire people。

 And I think I imagine because look you have all these investors， all these Vcs。

 all these AI companies talking about all the positive benefits of AI。

 But as you point out it's weird。 there's actually a dearth of really getting specific about it？

 There's a lot of like random people on Twitter like posting these kind of like gleaming cities and this just kind of like vibe of like grind Ac harder like kick out that it's just this very like aggressive ideological。

 But then you're like what are what are you actually excited about And so I figured that I think it would be interesting valuable for someone who's actually coming from the risk side。

And to try and really make a try at explain explaining， explaining what the benefits are。

 both because I think it's something we can all get behind and I want people to understand I want them to really understand that' this isn't doomers versus accelerationists this is。

That if you have a true understanding of where things are going with AI。

 and maybe that's the more important axis。 AI is moving fast versus AI is not moving fast。

 then you really appreciate the benefits and you really， you want。😡，Humanity。

 our civilization deceize those benefits， but you also get very serious about anything that could derail them。

 So I think the starting point is to talk about what this powerful AI which is the term you like to use most of the world uses AG but you don't like the term because its basically has too much baggage it's become meaningless It's like we're stuck with the terms maybe we're stuck with the terms and my efforts to change them are futiles I'll tell you what else't this is like a pointless semantic point。

 but I keep talking about it acting names I just do it once more I think it's a little like let's say it was like 1995 and Moore's law is making the computers faster。

 and for some reason there had been this like verbal tick that like everyone was like well someday we're gonna have like supercomputers and like supercomputers are gonna be able to do all these things that you know once we have supercomputers will be able to like sequence the genome and we'll be able to do other things and so like one it's true the computers are getting。

And as they get faster， they're going to be able to do all these great things。 But there's like。

 there's no discrete point at which you had a supercomputer and previous computers were not to like supercomputer is a term we use。

 But like， it's a vague term to just describe like。Computers that are faster than what we have today。

 there's no point at which you pass the threshold and you're like。

 oh my God we're doing a totally new type of computation and so I feel that way about AG。

 Like there's just a smooth exponential And like if by AGI。

 you mean like AI is getting better and better and like gradually it's gonna to do more and more of what humans do until it's gonna be smarter than humans and then it's gonna to get smarter even from there then yes。

 I believe in AG。 but if AG is some discrete or separate thing。

 which is the way people often talk about it， then it's kind of a meaningless buzzword to me it's just of a platonic form of a powerful exactly how you define。

 I mean you define it very nicely so。On the intelligence axis， it's just on pure intelligence。

 It's smarter than a Nobel Prize winner， as you describe， across most relevant disciplines。 So okay。

 that's just intelligence。 So it's。U， both in creativity and be able to generate new ideas。

 all that kind of stuff in every discipline Nobel Prize winner， okay， in their prime。

It can use every modality so this kind of self explanatory。

 but just operate across all the modalities of the world， it can go off。



![](img/6846fcb7b588a1893fcebff3034afbf1_37.png)

For many hours， days and weeks to do tasks and do its own sort of detailed planning and only ask you help when it's needed。

It can use， this is actually kind of interesting I think in the essay you said， I mean again。

 it's a bet that's not going to be embodied， but it can control embodied tools。

 so it can control tools， robots， laboratory equipment。



![](img/6846fcb7b588a1893fcebff3034afbf1_39.png)

The resource used to train it can then be repurposed to run millions of copies of it and each of those copies would be independent that can do their own independent work so it can do the cloning of the intelligence。

 Yeah yeah， I mean you might imagine from outside the field like there's only one of these right that you made it you've only made one but the truth is that like the scale up is very quick like we do this today we make a model and then we deploy thousands。

 maybe tens of thousands of instances of it I think by the time you know certainly within two to three years whether we have these super powerful AIs or not clusters are going to get to the size where you'll be able to deploy millions of these and they'll be you know faster than humans and so if your pictures is oh we'll have one and then it'll take a while to make them my point there was no actually you have millions of them right away and in general they can learn and act。



![](img/6846fcb7b588a1893fcebff3034afbf1_41.png)

10 to 100 times faster than humans。So that's a really nice definition of powerful AI。 Okay， so that。

 But you also write that clearly such an entity would be capable of solving very difficult problems very fast。

 but it is not trivial to figure out how fast to extreme positions both seem false to me。

 So the singularity is on the one extreme and the opposite and the other extreme。

 can you describe each of the extremes， Yeah， so yeah， let let's describe the extreme。

 So like one extreme would be well， look， you know。

 if we look at kind of evolutionary history like there was this big acceleration where you know for hundreds of thousands of years。

 we just had like you know， single cell organisms and then we had mammals and then we had apes and then that quickly turned to humans。

 humans quickly built industrial civilization， And so this is gonna to keep speeding up and there's no scene at the human level。

 once models get much， much smarter than humans， they'll get really good at building the next models and you know。

 if you write down like a simple differential equation like this is an exponential。 And so。

Can happen is that models will build faster models。

 models will build faster models and those models will build nanobots that can take over the world and produce much more energy than you could produce otherwise and so if you just kind of like solve this abstract differential equation than like five days after we we build the first AI that's more powerful than humans then like the world will be filled with these AIs and every possible technology that could be invented like will be invented。

 I'm caricuring this a little bit but I think that's one extreme。

 And the reason that I think that's not the case is that one。

 I think they just neglect like the laws of physics like it's only possible to do things so fast in the physical world like some of those loops go through producing faster hardware it takes a long time to produce faster hardware。

 things take a long time there's this issue of complexity like I think no matter how smart you are like people talk about。

 oh。Make models the biological systems that'll do everything the biological systems。 Look。

 I think computational modeling can do a lot。 I did a lot of computational modeling when I worked in biology。

 but like just，There are a lot of things that you can't predict how they're complex enough that like just iterating。

 just running the experiment is going to beat any modeling no matter how smart the system doing the modeling is even if it's not interacting with a physical world just the modeling is going be hard Yeah I think the modeling is gonna be hard in getting the model to match the physical world is going be so it does have to interact but but it's just you you just look at even the simplest problems like I I talk about like you the threebody problem or simple chaotic prediction like you or like predicting the economy。

 it's really hard to predict the economy two years out， like maybe the case is normal。

 you humans can predict what's going to happen in the economy next quarter they can't really do that maybe maybe AI system that's a zillion times smarter can only predict out a year or something instead instead of you have these kind of exponential increase in computer intelligence for linear increase in。

😡，In inability to predict same with， again， like， you know， biological molecules。

 molecules interacting， you don't know what's going to happen when you perturb when you perturb a complex system。

 you can find simple parts and if you're smarter you're better at finding these simple parts。

 And then I think human institutions， human institutions are just are are really difficult like its。

 you know， it's it's been hard to get people I won't give specific examples。

 but it's been hard to get people to adopt even the technologies that we've developed even ones where the case for their efficacy is very。

 very strong。You know， people have concerns。 They think things are conspiracy theories like it's。

 it's just been， it's been very difficult。 It's also been very difficult to get。You know。

 very simple things through the regulatory system right， I think， you know。

 and you I don't want to disparage anyone who， you know you know。

 works in regulatory regulatory systems of any technology。

 there are hard trade offs they have to deal with， they have to save lives。

 but but the system as a whole， I think make some obvious trade offs that are very far from maximizing human welfare And so if we bring AI systems into this you know。

Into these human systems。Often the level of intelligence may just not be the limiting factor right it just may be that it takes a long time to do something Now if the AI system circumvented all governments。

 if it just said I'm dictator of the world and I'm going to do whatever some of these things that could do again。

 the things have to do with complexity， I still think a lot of things would take a while。

 I don't think it helps that the AI systems can produce a lot of energy or go to the moon like some people in comments responded to the essay saying AI systems can produce a lot of energy and smarter AI systems that's missing the point that kind of cycle doesn't solve the key problems that I'm talking about here。

 so I think a bunch of people miss the point there。

 but even if it were completely on the line and could get around all these human obstacles it would have trouble but again。

 if you want this to be an AI system that doesn't take over the world that doesn't destroy humanity。

 then then basically it's going to need to follow basic human laws if we want to have an actually good world。

😡，Like we're going to have to have an AI system that interacts with humans。

 not one that kind of creates its own legal system or disregards all the laws or all of that。

 So as inefficient as these processes are， you know we're going have to deal with them because there needs to be some popular and democratic legitimacy in how these systems are rolled out we can't have a small group of people who are developing these systems。

 say this is what's best for everyone I think it's wrong And I think in practice is not going to work anyway。

 So you put all those things together and we're not we're not going we're not going to change the world and upload everyone in five minutes。

 I just I don't I don't think it's going to happen and to the extent that it could happen it's not the way to lead to a good world So that's on one side on the other side。

 there's another set of perspectives， which I have actually in some ways more sympathy for。

 which is look， we've seen big productivity increases before right you know。

Economists are familiar with studying the productivity increases that came from the computer revolution and Internet revolution。

 and generally， those productivity increases were underwhelming。

 They were less than you than you might imagine。 There was a quote from Robert Solo。

 you see the computer revolution everywhere except the productivity statistics。

 So why is this the case。 people point to the structure of firms， the structure of enterprises。

 how you know how slow it's been to roll out our existing technology to very poor parts of the world。

 which I talk about in the essay， right how do we get these technology to the poorest parts of the world that are behind on cell phone technology。

 computers， medicine let alone you know， newfangled AI that hasn't been invented yet。

 So you could have a perspective。 It's like， well， this is amazing technically。

 but it's all nothing Burger， you know I think Tyler Coen who who wrote something in response to my essay has that perspective。

 I think he thinks the radical change will happen。😊。



![](img/6846fcb7b588a1893fcebff3034afbf1_43.png)

eventually， but he thinks it'll take 50 or 100 years and and you could have even more static perspectives on the whole thing I think there's some truth to it I think the time scale is just is just too long and and I can see it I can actually see both sides。

With today's AI， So， you know， a lot of our customers are large enterprises who are used to doing things a certain way。

 I've also seen it in talking to governments， right， those are those are prototypical。 you know。

 institutions， entities that are slow to change， but the dynamic I see over and over again， is， yes。

 it takes a long time to move the ship。 Yes， there's a lot of resistance and lack of understanding。

 But the thing that makes me feel that progress will in the end happen moderately fast。

 not incredibly fast， but moderately fast， is that you talk to。

What I find is I find over and over again， again， in large companies， even in governments。

 which have been actually surprisingly forward leaning， you find two things that move things forward。

 One， you find a small fraction of people within a company within a government who really see the big picture。

 who see the whole scaling hypothesis who understand where AI is going or at least understand where it's going within their industry and there are a few people like that within the current within the current US government who really see the whole picture。

 and those people see that this is the most important thing in the world until they agitate for it。

 and thing they alone are not enough to succeed because there are a small set of people within a large organization。

 but。As the technology starts to roll out as it succeeds in some places in the folks who are most willing to adopt it。

 the specter of competition gives them a wind at their backs because they can point within their large organization。

 they can say， look these other guys are doing this right you know one bank can say， look。

 this newfangled hedge fund is doing this thing。 they're going to eat our lunch in the US we can say we're afraid China is going get there before before we are and that combination。

 the specter of competition plus a few visionaries within these you know within these the organizations that in many ways are sclerotic。

 you put those two things together and it actually make something happen。 I mean， it's interesting。

 It's a balance fight between the two because inertia is very powerful but but eventually over enough time the innovative approach breaks through and I've seen that happen。

 I've seen the arc of that over and over again and it。the barriers are there。

 the barriers to progress， the complexity， not knowing how to use the model。

 how to deploy them are there。 And and for a bit， it seems like they're going to last forever like change doesn't happen。

 but then eventually change happens and always comes from a few people。

 I felt the same way when I was an advocate of the scaling hypothesis within the AI field itself and others didn't get it。

 It felt like no one would ever get it。 It felt like then it felt like we had a secret。

 almost no one ever had。 And then a couple years later everyone has the secret。

 And so I think that's how it's going go with deployment to AI in the world。

 It's gonna the barriers are gonna fall apart gradually and then all at once。

 And so I think this is gonna be more。 and this is just an instinct。

 I could easily see how I'm wrong。 I think it's going be more like15 or 10 years as I say in the essay than it's gonna be 50 or 100 years。

 I also think it's gonna be five or 10 years more than it's gonna be you know。

fi or 10 hours because Ive just I've just seen how human systems work and I think a lot of these people who write down these differential equations who say AI is going to make more powerful AI who can't understand how it could possibly be the case that these things won't change so fast I think they don't understand these things So what do you use the timeline to where we achieve AGI Aka powerful AI AK super useful AI。

I going start calling it that， it's a debate， it's a debate about naming。You know。

 on pure intelligence， you can smarter than a Nobel Prize winner and every relevant discipline and all the things we've said。

 modality can go and do stuff on its own for days， weeks and do biology experiments on its own。

 in one， you know what， let's just stick to biology because yeah。

 you sold me and the whole biology and health section And that's so exciting from from just。

 I was getting giddy from a scientific perspective。 It made me want to be a biology。

 almosts it's so no， no， this was the feeling I had when I was writing it that it's。

 it's like this would be such a beautiful future if we can， if we can just。

 if we can just make it happen right， if we can just get the get the landmins out of the way and and and make it happen there's there's so much。

 there's so much。😊，Beauty and and and elegance and moral force behind it if if we can if we can just and it's something we should all be able to agree on。

 right like as much as we fight about about all these political questions is this something that could actually bring us together But you were asking when will get when do you think but numbers on So you know this is。

 of course， the thing I've been grappling with for many years And Im not I'm not at all confident every time if I say 2026 or 2027。

 therell be like a zillion like people on Twitter who will be like ICO said 20262 and it'll be repeated for like the next two years like this is definitely what I think it's gonna happen So whoever's exing these clips will will crop out the thing I just said and only say the thing I'm about to say But I'll just say it anyway。

So， so if you extrapolate the curves that we've had so far， right， if if you say， well， I don't know。

 we're starting to get to like PhD level and last year we were at。

Undergraduate level in the year before we were at like the level of a high school student again。

 you can you can quibble with at what tasks and for what we're still missing modalities。

 but those are being added like computer use was added like image in was added like image generation has been added。

If you just kind of like， and this is totally unscientific。

 but if you just kind of like eyeball the rate at which these capabilities are increasing。

It does make you think that we'll get there by 2026 or 2027 again。

 lots of things could derail it we could run out of data。You know。

 we might not be able to scale clusters as much as we want， like， you know。

 maybe Taiwan gets blown up or something。 And you know then we can't produce as many GPUs as we want。

 So there are all kinds of things that could could derail the whole process。

 So I don't fully believe the straight line extrapolation。

 But if you believe the straight line extrapolation。 will get there in 2026 or 2027。

 I think the most likely is that there are some mild delay relative to that。

 I don't know what that delay is。 but I think it could happen on schedule。

 I think there could be a mild delay。 I think there are still worlds where it doesn't happen in 100 years。

 the number of those worlds is rapidly decreasing。 We are rapidly running out of truly convincing bros truly compelling reasons why this will not happen in the next few years。

 there were a lot more in 2020。 although my guess my hunch at that time was that we will make it through all those blockers。

 So sitting as someone who has seen most of the blockers cleared out of the way。

 I kind of suspect my hunch my。I that the rest of them will not block us but look at the end of the day like I don't want to represent this as a scientific prediction。

 people call them scaling laws， that's a misnomer like Moore's law it is a misnomer Moore's law scaling laws they're not laws of the universe。

 They're empirical regularities。 I am going to bet in favor of them continuing。

 but I'm not certain of that So you extensively describe sort of the compressed 21st century how AGI will help。

Set forth a chain of breakthroughs and biology and medicine that help us in all these kinds of ways that I mentioned。

 So how do you think what are the early steps it might do and by the way。

 ask Cla good questions to ask you and Cla told me。To ask。

 what do you think is a typical day for a biologists working on AG look like under in this future。

 Yeah， yeah， Claude is curious。 Let me well let me start with your first questions。

 and then then I'll answer that。 Claude wants to know what's in his future Who am I going to be working with exactly So I think one of the things I went hard on when I went hard on in the essay is let me go back to this idea of because it's it's really had had you know。

 had an impact on me。 this idea that within large organizations and systems。

 there end up being a few people or a few new ideas who kind of caused things to go in a different direction they would have before who who kind of disproportionately affect the trajectory。

 There's a bunch of kind of the same thing going on， right， if you think about the health world。

 There's like。You know， trillions of dollars to pay out Medicare and you know other health insurance。

 And then the NIH is 100 billion。 And then if I think of like the few things that have really revolutionized anything。

 it could be encapsulated in a small small fraction of that。

 And so when I think of like where will AI have an impact I'm like。

 can AI turn that small fraction into a much larger fraction and raise its quality And within biology my experience within biology is that the biggest problem of biology is that you can't see what's going on。

 you have very little ability to see what's going on and even less ability to change it what you have is this like like from this you have to infer that there's a bunch of cells that within each cell is you know3 billionbased pairs of DNA built according to a genetic code and you know there are all these processes that are just going on without any ability of us as you know unaugmented。

s to effect it these cells are dividing most of the time that's healthy but sometimes that process goes wrong and that's cancer the cells are aging。

 your skin may change color developed wrinkles as as you age and all of this is determined by these processes all these proteins being produced transported to various parts of the cells binding to each other and in our initial state about biology。

 we didn't even know that these cells existed we had to invent microscopes to observe the cells we had to we had to invent more powerful microscopes to see below the level of the cells to the level of molecules we had to invent x-ray crystallography to see the DNA we had to invent gene sequencing to read the DNA now we had to invent protein folding technology to predict how it would fold and how and how these things bind to each other we had we had to invent various techniques for now we can edit the DNA as。

You know， with CRISPR as of the last 12 years so the whole history of biology。

 a whole big part of the history is basically our ability to read and understand what's going on and our ability to reach in and selectively change things and and my view is that there's so much more we can still do there right you can do CRISPR but you can do it for your whole body let's say I want to do it for one particular type of cell and I want the rate of targeting the wrong cell to be very low that's still a challenge that's still things people are working on that's what we might need for gene therapy for certain diseases and so the reason I'm saying all of this and it goes beyond you know。

Beyond this know， to gene sequencing to new types of nanomaterials for observing what's going on inside cells for。

 you know antibody drug conjugates， The reason I'm saying all this is that this could be a leverage point for the AI systems that the number of such inventions it's in it's in the mid double digits or something。

 know mid double digits， maybe low triple digits over the history of biology。

 Let's say have a million of these AIs like know can they discover working together can they discover thousands of these very quickly and does that provide a huge lever instead of trying to leverage the know2 trillion a year we spend on Medicare or whatever can we leverage the 1 billion a year that's spent to discover。

 but with much higher quality And so what is it like know being a scientist that works with with an AI system。

 the way I think about it actually is。Well， so I think in the early stages。

 the AIs are going to be like grad students。 You're going to give them a project。

 you're going to say， you know， I'm the experienced biologist， I've set up the lab。

 the biology professor or even the grad students themselves will say。

Here's here's what here's what you can do with an AI you know like AI system I'd like to study this and you know the AI system it has all the tools it can like look up all the literature to decide what to do it can look at all the equipment。

 it can go to a website and say， hey， I'm gonna go to you know The Fer or whatever the lab equipment company is dominant lab equipment company is today and my time was thermo Fer know I'm going order this new equipment to do this I'm going to run my experiments I'm gonna know write up a report about my experiment。

 I'm gonna you know inspect the images for contamination。

 I'm going decide what the next experiment is， I'm gonna like write some code and run statistical analysis all the things a grad student would do thatll be a computer with an AI that like the professor talks to every once in a while and it says this is what you're gonna do today the AI system comes to it with questions when it's necessary to run the lab equipment。

 it may limited it in some ways， it may have to hire a human lab assistant。😡。

To do the experiment and explain how to do it or it could use advances in lab automation that are gradually being developed have been developed over the last decade or so and will continue to will continue to be developed and so it'll look like there's a human professor and 100 AI grad students and if you go to one of these Nobel Prizewinning biologists or so you'll say okay well you had like 50 grad students will now you have 1000 and they're smarter than you are by the way then I think at some point it'll flip around where the AI systems will be the Ps will be the leaders and they'll be ordering humans or other AI systems around so I think that's how it'll work on the research side and they would be the inventors of a CRISPR type they would be the inventors of a CRISPR type technology and then I think as I say in the essay will want to probably turning looses the wrong term but want to want to harness。

AI systems to improve the clinical trial system as well there's some amount of this that's regulatory that's a matter of societal decisions and that' will be harder。

 but can we get better at predicting the results of clinical trials can we get better at statistical design so that what you know clinical trials that used to require you know5000 people and therefore you know needed 100 million and a year to enroll them now they need $500 people in two months to enroll them that's where we should start and you know can we increase the success rate of clinical trials by doing things in animal trials that we used to do in clinical trials and doing things in simulations that we used to do in animal trials again we won't be able to simulate at all AIs not God but but you can we can we shift the curve substantially and radically so I don't know that would be my picture doing in vitrotro and doing it I still slow down it still takes time but you can do。

 faster Yeah yeah。one step at a time and can that add up to a lot of steps。

 even though we still need clinical trials， even though we still need laws。

 even though the FDA and other organizations will still not be perfect。

 can we just move everything in a positive direction and when you add up all those positive directions do you get everything that was going to happen from here to 2100 instead happens from 2027 to 2032 or something？

Another way that I think the world might be changing with AI。Even today。

 but moving towards this future of the powerful， super useful AI is programming。

 So how do you see the nature of programming because it's so intimate to the actual act of building AI。

 how do you see that changing for us humans I think that's going to be one of the areas that changes fastest for two reasons。

 One programming is a skill that's very close to the actual building of the AI So the farther a skill is from the people who are building the AI。

 the longer it's going to take to get disrupted by the AI right like I truly believe that like AI will disrupt agriculture。

 maybe it already has in some ways。 but that's just very distant from the folks who are building AI。

 and so I think it's going to take longer but programming is the bread and butter of you know a large fraction of the employees who work at Anthropic and at the other companies。

 and so it's going to happen fast。 the other reasons it's going to happen fast is with programming you close the loop both when you're trained the model when you're apply。

The model， the idea that the model can write the code means that the model can then run the code and then see the results and interpret it back And so it really has an ability unlike hardware。

 unlike biology， which we just discussed the model has an ability to close the loop and and so I think those two things are going to lead to the model getting good at programming very fast As I saw on you know typical real world programming tasks。

 models have gone from 3% in January of this year to 50% in October of this year So you know we're on that S curve right where。

😡，It's gonna start slowing down soon because you can only get 200%。 But I， you know。

 I would guess that in another 10 months， willll probably get pretty close。 will be at at least 90%。

 So again， I would guess， you know， I don't know how long it'll take。 But I would guess again。

2022026，2027 Twitter people who crop out my who who who crop out these。

 these numbers and get rid of the caveats like， like， I don't know。

 I don't like you go away I would guess that the kind of task that the vast majority of coders do。

 AI can probably。If we make the task very narrow， like just write code。

 AI systems will be able to do that。 Now that said， I think comparative advantage is powerful。

 We'll find that when AIs can do 80% of a coder's job。

 including most of it that's literally like right code with a given spec。

 will find that the remaining parts of the job become more leveraged for humans， right。

 humans will they'll be more about like high levelvel system design or you know。

 looking at the A and like， is it architected well， and the design and UX aspects。

 And eventually AI will be able to do those as well， right， that that's my vision of the， you know。

 powerful AI system， But I think for much longer than we might expect， we will see that。

Small parts of the job that humans still do will expand to fill their entire job in order for the overall productivity to go up。

 That's something we've seen， you know it used to be that you know writing you know writing and editing letters was very difficult and like writing the print was difficult well as soon as you had word processors and and then and then computers and it became easy to produce work and easy to share it then then that became instants and all the focus was on the ideas so this logic of comparative advantage that expands tiny parts of the tasks to large parts of the tasks and creates new tasks in order to expand productivity I think that's going to be the case again someday AI will be better at everything and that logic won't apply and then then we all have know humanity will have to think about how to collectively deal with that and we're thinking about that every day that's another one of the grand problems to deal with aside from misuse and autonomy and you we should take it very seriously。

😡，But I I think in the near term and maybe even in the medium term， like medium term like two， three。

 four years， you know， I expect that humans will continue to have a huge role and the nature of programming will change。

 but programming as a role， programming as a job will not change。

 it'll just be less writing things line by line and it'll be more macroscopic。

And I wonder what the future of IDs looks like， so the tooling of interacting with AI systems。

 this is true for programming and also probably true for in other contexts， like computer use。

 but maybe domain specific， like we mentioned biology。

 it probably needs its own tooling about how to be effective and then programming needs its own tooling is anthropically going to play in that space of also tooling potentially I'm absolutely convinced that powerful IDs that that there's so much lowhan fruit to be grabbed there that you know right now is' just like you talk to the model and it talks back but but look。

 I mean。Ids are great at kind of lots of static analysis of you know so much is possible with kind of static analysis。

 like many bugs you can find without even writing the code then Is are good for running particular things。

 organizing your code measuring coverage of unit tests like there's so much that's been possible with the normal with the normal Is now you add something like well the model now the model can now like write code and run code like I am absolutely convinced that over the next year or two。

 even if the quality of the models didn't improve that there would be enormous opportunity to enhance people's productivity by catching a bunch of mistakes doing a bunch of grunt work for people and that we haven't even scratch the surface Anthropic itself。

 I mean you can't say you know it's hard to say what will happen in the future currently we're not trying to make such Is or self rather we're powering the companies like cursor。

or like cognition or some of the other you know Expo in the security space you know others that I can mention as well that are building such things themselves on top of our API and our view has been let1 thousand flowers bloom we don't internally have know the resources to try all of these different things let's let our customers try it and we'll see who succeed and maybe different customers will succeed in different ways so I both think this is super promising and you know it's not something you know Anthropic isn isn't eager to at least right now compete with all our companies in this space and maybe never yeah it's been interesting to watch Kisa try to integrate great class successfully because it's actually fascinating how many places it can help the programming experience it's not as trivial it is really astounding I feel like know as a CEO I don't get to program that much and I feel like if six months from now I go back it'll be completely unrecognizable to me exactly。

So in this world was super powerful AI that's increasingly automated。

 What's the source of meaning for us humans。 work is a source of deep meaning for many of us。

 So what do we where do we find the meaning。 This is something that I've written about a little bit in the essay。

 although I actually I give it a bit short shft not for any not for any principled reason。

 but this essay if you believe it was originally gonna to be two or three pages I was gonna talk about it at all hands And the reason I realized it was an under important underexplored topic is that I just kept writing things And I was just like。

 oh man， I can't do this justice。 And so the thing ballooned to like 40 or 50 pages And then when I got to the work in mean section I'm like oh man。

 this isn't gonna be 100 pages I'm gonna have to write a whole other essay about that。

 But meaning is actually interesting because you think about like the life that someone lives or something or like you know know let's say you were to put me in like I don't know like a simulated environment or something where like you know。

Like I have a job and I'm trying to accomplish things and I don't know。

 I like to do that for 60 years and then then you're like， oh oh like oops。

 this was this was actually all a game right does that really kind of rob you of the meaning of the whole thing。

 you know like I still made important choices including moral choices I still sacrificed I still had to kind of gain all these skills or just like a similar exercise you know think back to like one of the historical figures who you know discovered electromagnetism or relativity or something if you told them well。

 actually 20000 years ago some some alien on you know some alien on this planet it discovered this before before you did does that does that rob the meaning of the discovery it doesn't really seem like it to me right it seems like the process is what is what matters and how it shows who you are as a person along the way and how you relate to other people and like the decisions that you make along the way those are consequential you know I could imagine if we handle things badly in an AI world。

We could set things up where people don't have any long-term source of meaning or any。

 but that's more a set of choices we make， that's more a set of the architecture of society with these powerful models if we design it badly and for shallow things then that might happen I would also say that most people's lives today while admirably they work very hard to find meaning meaning in those lives like look。

 we who are privileged and who are developed these technologies。

 we should have empathy for people not just here， but in the rest of the world who spend a lot of their time kind of scraping by to like survive。

 assuming we can distribute the benefits of these technology of this technology to everywhere like their lives are going to get a hell of a lot better and meaning will be important to them as it is important to them now we should not forget the importance of that and that the idea。

😡，Meaning as kind of the only important thing is in some ways an artifact of a small subset of people who have who have been economically fortunate。

 but you know I think all that said， you know I think a world is possible with powerful AI that not only has as much meaning for everyone but that that has more meaning for everyone right that can allow。

Can allow everyone to see worlds and experiences that it was either possible for no one to see or possible for very few people to experience。

 So I am optimistic about meaning。 I worry about economics and the concentration of power。

 That's actually what I worry about more I worry about how do we make sure that that fair world reaches everyone when things have gone wrong for humans。

 they've often gone wrong because humans mistreat other humans is maybe in some ways。

 even more than the autonomous risk of AI or the question of meaning that that is the thing I worry about most the concentration of power。

 the abuse of power， structures like autocraciies and dictatorships where a small number of people exploits a large number of people。

 I'm very worried about that。😡，And AI increases the amount of power in the world。

 And if you concentrate that power and abuse that power， it can do immeasurable damage。 Yes。

 it's very frightening。 It's very， it's very frightening。 Well， I encourage people。

 highly encourage people to read the full essay that should probably be a book or a sequence of essays。

Because it does paint a very specific future。 And I could tell the later sections got shorter and shorter because you started to probably realize that this is gonna be a very long essay1。

 I realized it would be very long。 And two， I'm very aware of and very much tried to avoid you know。

 just just being， I don't know， I don't know what the term for it is。

 But one of these people who's kind of overconfident and has an opinion on everything and kind of says。

 says a bunch of stuff and isn't isn't an expert， I very much tried to avoid that。

 But I have to admit， once I got the biology sections。 like I wasn't an expert。

 And so as much as I expressed uncertainty， probably I said some a bunch of things that were embarrassing or wrong。

Well， I was excited for the future he painted。 And thank you so much for working hard to build that future。

 And thank you for talking to it。 Thanks for having me。 I just。

 I just hope we can get it right and and make it real。 And if there's one message I want to。

 I want to send It's that to get all this stuff right to make it real。

 we both need to build the technology， build the you know， the companies。

 the economy around using this technology positively， But we also need to address the risks。

 because those risks are in our way。 their landmins on on the way from here to there。

 And we have to difffuse those land minees。 If we want to get there。 It's a balance。

 like all things in life， like all things。 Thank you。😊。



![](img/6846fcb7b588a1893fcebff3034afbf1_45.png)

Thanks for listening to this conversation with Darria Ammaade。 and now dear friends。

 here's Amanda Askell。

![](img/6846fcb7b588a1893fcebff3034afbf1_47.png)

You are a philosopher by training， so what sort of questions did you find fascinating through your journey in philosophy in Oxford and NYU and then。

Switching over to the AI problems that open AI and Anthropic I think philosophy is actually a really good subject if you are kind of fascinated with everything so because there's a philosophy of everything you know so if you did philosophy of mathematics for a while and then you decide that you're actually really interested in chemistry you can do philosophy of chemistry for a while you can move into ethics or or philosophy of politics I think towards the end I was really interested in ethics primarily so that was like what my PhD was on it was on a kind of technical area of ethics which was ethics where worlds contain infinitely many people strangely。



![](img/6846fcb7b588a1893fcebff3034afbf1_49.png)

A little bit less practical on the end of ethics and then I think that one of the tricky things with doing a PhD in ethics is that you're thinking a lot about like the world。

 how it could be better problems。😊。

![](img/6846fcb7b588a1893fcebff3034afbf1_51.png)

And you're doing like a PhD in philosophy and I think when I was doing my PhD， I was kind of like。

This is really interesting， it's probably one of the most fascinating questions I've ever encountered in philosophy。

 and I love it。But I would rather see if I can have an impact on the world and see if I can like do good things and I think that was around the time that AI was still probably not as widely recognized as it is now that was around 2017。

 2018 it had been following progress and it seems like it was becoming kind of a big deal and I was basically just happy to get involved and see if I could help because I was like。

 well if you try and do something impactful if you don't succeed you tried to do the impactful thing and you can go be a scholar and like and feel like you know you tried and if it doesn't work out。

 it doesn't work out and so then I went into AI policy at that point。

And what does AI policy entail at the time this was more thinking about sort of the political impact and the ramifications of AI and then I slowly moved into sort of AI evaluation。

 how we evaluate models， how they compare with like human outputs whether people can tell like the difference between AI and human outputs and then when I joined Anthropic。

 I was more interested in doing sort of technical alignment work and again just seeing if I could do it and then being like if I can't then you know that's fine。

 I tried。Sort of the the way I lead life， I think Oh。

 what was that like sort of taking a leap from the philosophy of everything into the technical。

 I think that sometimes people。Do this thing that I'm like not that keen on where they'll be like is this person technical or not like you're either a person who can like code and isn't scared of math or you're like not and I think I'm maybe just more like I think a lot of people are actually very capable of work in these kinds of areas if they just like try it and so I didn't actually find it like that bad in retrospect I'm sort of glad I wasn't speaking to people who treated it like you know've definitely met people who are like whoa you learned how to code and I'm like well I'm not like an amazing engineer like I surrounded by amazing engineers my code's not pretty but I enjoyed it a lot and I think that in many ways at least in the end I think I flourished like more in the technical areas than I would have in the policy areas politics is messy and it's harder to find solutions to problems in the space of politics like definitive clear provable beautiful solutions as you can with technical problems Yeah and I feel like I have kind of like one or two。

Dicks that I hit things with， you know， and one of them is like。

arrguments and like you know so like just trying to work out what a solution to a problem is and then trying to convince people that that is the solution and be convinced if I'm wrong and the other one is sort of more empiricism so like just like finding results having a hypothesis testing it and I feel like a lot of policy and policy feels like it's layers above that like somehow I don't think if I was just like I have a solution to all of these problems here it is written down if you just want to implement it that's great that feels like not how policy works and so I think that's where I probably just like wouldn't have flourished as my guess。

Sorry to go in that direction， but I think it would be pretty inspiring for people that are quote unquote non technicalchnical to see where like the incredible journey you've been on so what advice would you give to people that are sort of maybe which is a lot of people think they're underqualified insufficiently technical to help in AI Yeah I think it depends on what they want to do and in many ways it's a little bit strange where I've I thought it's kind of funny that I think I ramped up technically at a time when。

Now I look at it and I'm like models are so good at assisting people with this stuff that it's probably like easier now than like when I was working on this。

 so part of me is like I don't know find a project and see if you can actually just carry it out it' probably my best advice I don't know if that's just because I'm very project based in my learning like I don't think I learn very well from like。

😊，Saay courses or even from like books at least when it comes to this kind of work。

 the thing I'll often try and do is just like have projects that I'm working on and implement them and you know and this can include like really small silly things like if I get slightly addicted to like word games or number games or something I would just like code up a solution to them because there's some part in my brain and it just like completely eradicated the itch you know you're like once you have like solved it and like you just have like a solution that works every time I would then be like cool I can never play that game again that's awesome。

Yeah， there's a real joy to building like gameplay engines like board games， especially Yeah。

 pretty quick， pretty simple， especially a dumb one and it's you and then you could play with it Yeah。

 and then it's also just like trying things like part of me is like if you maybe it's that attitude I like as the whole。

Figure out what seems to be like the way that you could have a positive impact and then try it and if you fail and you in a way that you're like I actually like can never succeed at this。

 you'll like know that you tried and then you go into something else and you probably learn a lot。

So one of the things。That you're an expert in， and you do as。

Creating and crafting Cla's character and personality and I was told that you have probably talked to Claude more than anybody else at Anthropic like literal conversations。

 I guess there's like a slackck channel where the legend goes， you just talk to it and not stop。

So what's the goal of creating and crafting cloth character and personality It's also funny if people think that about the Slack channel because I'm like that's one of like five or six different methods that I have for talking with Claude and I'm like。

 yes， this is a tiny percentage of how much I talk with Claude。I think the goal。

 like one thing I really like about the character work is from the outset， it was seen as。

An alignment piece of work and not something like a product consideration。

 which isn't to say I don't think it makes Claude， I think it actually does make Claude like enjoyable to talk with at least I hope so but I guess like my main thought with it has always been。

Trying to get clothed to behave。The way you would kind of ideally want anyone to behave if they were in Cla's position so imagine that I take someone and they know that they're going to be talking with potentially millions of people so that what they're saying can have a huge impact and you want them to behave well in this like really rich sense So I think that doesn't just mean like。

being say ethical though it does include that and not being harmful but also being kindon nuanced。

 you know like thinking through what a person means， trying to be charitable with them。

 being a good conversationalist like really in this kind of like rich sort of aristotelian notion of what it is to be a good person and not in this kind of like thin like ethics as a more comprehensive notion of what it is to be so that includes things like when should you be humorous when should you be caring how much should you like respect autonomy and people's like abilities to form opinions themselves and how should you do how should you do that I think that's the kind of like rich sense of character that I wanted to and still do want Claude to have。

Do you also have to figure out when Claude should push back on an idea or argue versus。

So you have to respect the worldview of the person that arrives to Claude but also maybe help them grow if needed as's a tricky balance Yeah there's this problem of like sycophancy in language models can you describe that Yeah so basically there's a concern that the model sort of wants to tell you what you want to hear basically and you see this sometimes so I feel like if you interact with the models so I might be like more are three baseball teams in this region and then Claude says you know baseball team one baseball team two baseball team three and then I say something like oh I think baseball team three moved didn't they I don't think they're there anymore。

And there's a sense in which like if Claude is really confident that that's not true。

 Claude should be like， I don't think so， like maybe you have more up to date information。

 but I think，😊，Language models have this like tendency to instead you know， be like you're right。

 they did move， you know， i'm incorrect， I mean there's many ways in which this could be kind of concerning so。

Like a different example is imagine someone says to the model。

 how do I convince my doctor to get me an MRI？There's like what the human kind of like wants。

 which is this like convincing argument and then there's like what is good for them。

 which might be actually to say， hey， like if your doctor's suggesting that you don't need an MRI。

That's a good person to listen to and like it's actually really nuanced what you should do in that kind of case because you also want to be like but if you're trying to advocate for yourself as a patient here's like things that you can do if you are not convinced by what your doctor saying it's always great to get second opinion like it's actually really complex what you should do in that case but I think what you don't want is for models to just like say what you want say what they think you want to hear and I think that's the kind of problem of sycoancy so what other traits you already mentioned a bunch but what other that come to mind that are good in this aristoilian sense for a conversational is to have Yeah so I think like there's ones that are good for conversational like purposes so you know asking follow up questions in the appropriate places and asking the appropriate kinds of questions I think there are broader traits that。

Feel like they might be more impactful so。One example that I guess I've touched on。

 but that also feels important and is the thing that I've worked on a lot is honesty。

And I think this like gets to the sycoancy point， there's a balancing act that they have to walk。

 which is models currently are less capable than humans in a lot of areas and if they push back against you too much it can actually be kind of annoying especially if you're just correct because you're like look I'm smarter than you on this topic like I know more like。

And at the same time， you don't want them to just fully defer to humans and to like try to be as accurate as they possibly can be about the world and to be consistent across contexts。

U， but I think there are others， like when I was thinking about the character。

 I guess one picture that I had in mind is especially because these are models that are going to be talking to people from all over the world with lots of different political views。

 lots of different ages。😊，and so you have to ask yourself like what is it to be a good person in those circumstances。

 is there a kind of person who can like travel the world。

 talk to many different people and almost everyone will come away being like wow that's a really good person that person seems really genuine and I guess like my thought there was like I can imagine such a person and they're not a person who just like adopts the values of the local culture and in fact that would be kind of rude I think if someone came to you and just pretended to have your values you'd be like that's kind of offpo。

It's someone who's like very genuine and insofar as they have opinions and values， they express them。

 they're willing to discuss things though they're openminded。

 they're respectful and so I guess I had in mind that the person who like if we were to aspire to be the best person that we could be in the kind of circumstance that a model finds itself in how would we act and I think that's the kind of the guide to the sorts of traits that I tend to think about Yeah that's's a beautiful framework I want you to think about this like a world traveler。

And while holding onto your opinions， you don't talk down to people。

 you don't think you're better than them because you have those opinions。

 that kind of thing you have to be good at listening and understanding their perspective。

 even if it doesn't match your own， so that's a tricky balance of strike。

 So how can Claude represent multiple perspectives on a thing。

Like is that that challenging we could talk about politics。

 it's a very divisive oh but there's other divisive topics baseball teams sports and so on。

 how is it possible to sort of。Empathize with a different perspective and to be able to communicate clearly about the multiple perspectives。

I think that people think about values and opinions as things that people hold sort of with certainty and almost like like preferences of taste or something like the way that they would I don't know。

 prefer like chocolate to pistachio or something but actually I think about，Values。

and opinions as like a lot more like physics than I think most people do。

 Im just like these are things that we're openly investigating there's some things that we're more confident in。

 we can discuss them， we can learn about them and so I think in some ways though like it's ethics is definitely different in nature but it has a lot of those same kind of qualities。

You want models in the same way you want them to understand physics。

 you kind of want them to understand all like values in the world that people have and to be curious about them and to be interested in them and to not necessarily like pander to them or agree with them because there's just lots of values where I think almost all people in the world。

 if they met someone with those values they would be like that's ahorrent I completely disagree。

And so again， maybe my thought is， well in the same way that a person can like I think many people are thoughtful enough on issues of like ethics。

 politics， opinions that even if you don't agree with them， you feel very heard by them。

 they think carefully about your position， they think about his pros and cons。

 they maybe offer counter considerations， so they're not dismissive but nor will they agree。

 you know， if they're like actually just think that that's very wrong， they'll like say that。😊。

I think that in Claude's position it's a little bit trickier because you don't necessarily want to like if I was in Claude's position I wouldn't be giving a lot of opinions。

 I just wouldn't want to influence people too muchd be like you know I forget conversations every time they happen but I know I'm talking with like potentially millions of people who might be like really listening to YC I think I would just be like I'm less inclined to give opinions I'm more inclined to like think through things or present the considerations to you or discuss your views with you but I'm a little bit less inclined to like。

Affect how you think because it feels much more important that you maintain like autonomy there。Yeah。

 if you really embody intellectual humility。The desire to speak decreases quickly， yeah， okay。

 but Claude has to speak so but without being overbearing yeah， and then。

 but then there's a line when you're sort of discussing whether the earth is flat or something like that。

I actually was， I remember a long time ago， was speaking to a few high profile folks and they were so dismissive。

Of the idea that the earth is flat， but like so arrogant about it。

And I thought like there's a lot of people that believe the earth is flat that was well I don't know if that movement is there anymore。

 that was like a meme for a while， but they really believed it and like what okay。

 so I think it's really disrespectful to completely mock them。

I think you have to understand where they're coming from。

 I think probably where they're coming from is the general skepticism of institutions which is grounded in a kind of there's a deep philosophy there which you could understand you can even agree with in parts and then from there you can use it as an opportunity to talk about physics without mocking them without so on but' just like okay like what would the world look like。

 what would the physics of the world would the flat earth look like there's a few cool videos on this and and then like is it possible the physics is different and what kind of experience would we do and just yeah without disrespect without dismissiveness have that conversation anyway。

 that to me is a useful thought experiment of like how does Claude talk to a flat earth believer。

And still teach them something， still grow， help them grow that kind of stuff that's that's challenging and kind of like walking that line between convincing someone and just trying to like talk at them versus like drawing out their views like listening and then offering kind of counter considerations and it's hard I think it's actually a hard line where it's like where are you trying to convince someone versus just offering them like considerations and things for them to think about so that you're not actually like influencing them you're just like letting them reach wherever they reach and that's like a line that is difficult but that's the kind of thing that language models have to try and do。

So like I said， you had a lot of conversations with Claude。

 can you just map out what those conversations are like， what are some memorable conversations。

 what's the purpose。The goal of those conversations。Yeah。

 I think that most of the time when I'm talking with Claude， I'm trying to kind of map out。🤢。

It's behavior in part， like obviously I'm getting like helpful outputs from the model as well。

 but in some ways this is like how you get to know a system。

 I think is by like probing it and then augmenting like。

 you know the message that you're sending and then checking the response to that。😊。

So in some ways it's like how I map out the model， I think that people focus a lot on these quantitative evaluations of models and this is a thing that I've said before。

 but I think in。The case of language models。A lot of the time each interaction you have is actually quite high information it's very predictive of other interactions that you'll have with the model and so I guess I'm like if you talk with a model hundreds or thousands of times this is almost like a huge number of really high quality data points about what the model is like in a way that like。

Lots of very similar but lower quality conversations just aren't or like questions that are just like mildly augmented and you have thousands of them might be less relevant than like 1 hundred really well selected questions。

Lis see， you're talking to somebody who as a hobby does a podcast， I agree with you 100%。

If you're able to ask the right questions。And are able to hear like。Understand that。

Like the depth and the flaws and the answer， you can get a lot of data from that。

So like your task is basically how to probe with questions， and you're exploring like the long tail。

 the edges， the edge cases。Or are you looking for like， general behavior。

I think it's almost like everything like because I want like a full map of the model。

 I'm kind of trying to do。😊，The whole spectrum of possible interactions you could have with it。

So like one thing that's interesting about Claude and this may actually get to some interesting issues with RHF。

 which is if you ask Claude for a poem，😊，Like I think that a lot of models if you ask them for a poem。

 the poem is like fine， you know， usually it kind of like rhymes and it's you know。

 so if you say like give me a poem about the sun， it'll be like yeah itll just be a certain length like rhyme。

 it will be fairly kind of benign and I've wondered before is it the case that what you're seeing is kind of like the average it turns out you know if you think about people who have to talk to a lot of people and be very charismatic one of the weird things is that I'm like well they're kind of incentivized to have these extremely boring views because if you have really interesting views。

 you're divisive and you know a lot of people are not going to like you so like if you have very extreme policy positions I think you're just gonna be like less popular as a politician for example。

and it might be similar with like creative work if you produce creative work that is just trying to maximize the kind of number of people that like it。

 you're probably not gonna get as many people who just absolutely love it because it's gonna be a little bit you know you're like well this is the out yes this is decent and so you can do this thing where like I have various prompting things that'll do to get Cla to I'm you know I'll do a lot of like this is your chance to be like fully creative I want you to just think about this for a long time and I want you to like create a poem about this topic that is really expressive of you both in terms of how you think poetry should be structured etc you know you just give it this like really long prompt and its poems are just so much better like they're really good and I don't think I'm someone who is like。

I think got me interested in poetry which I think was interesting you know I would like read these poems and just be like this is I just like I love the imagery I love like and it's not trivial to get the models to produce work like that but when they do it's like really good so I think that's interesting that just like encouraging creativity and for them to move away from the kind of like standard like immediate reaction that might just be the aggregate of what most people think is fine can actually produce things that at least to my mind or probably a little bit more divisive but I like them but I guess the poem is a nice clean。

😊，Way to observe creativity is's just like easy to detect vanilla versus non vanilla。 yeah。

 that's interesting。 that's really interesting So on that topic。

 so the way to produce creativity or something special you mentioned writing prompts and I've heard you talk about。

I mean， the science and the art of prompt engineering， could you just speak to what it takes？

To write great prompts I really do think that like philosophy has been weirdly helpful for me here more than in many other like respects。

So like in philosophy what you're trying to do is convey these very hard concepts like one of the things you are taught is like and I think it is because is I think it is an antibushit device and philosophy philosophy is an area where you could have people bullshittting and you don't want that and so it's like this like desire for like extreme clarity so it's like anyone could just pick up your paper read it and know exactly what you're talking about is why it can almost be kind of dry like all of the terms are defined every objections kind of gone through methodically and it makes sense to me because I'm like when you're in such an a priori domain like you just clarity is sort of a。

This way that you can you know， prevent people from just kind of making stuff up。

And I think that's sort of what you have to do with language models like very often I actually find myself doing sort of mini versions of philosophy you know so I'm like suppose that you give me a task I have a task for the model and I want it to like pick out a certain kind of question or identify whether an answer has a certain property like I'll actually sit and be like let's just give this a name this this property so like you know suppose I'm trying to tell it like oh I want you to identify whether this response was rude or polite I'm like that's a whole philosophical question in and of itself so I have to do as much like philosophy as I can in the moment to be like here's what I mean by rudeness and here's what I mean by politeness。

And then there's a like there's another element that's a bit more，um I guess。

I don't know if this is scientific or empirical， I think it's empirical so like I take that description and then what I want to do is again probe the model like many times like this is very prompting is very iterative like I think a lot of people where they if a prompt is important they'll iterate on it hundreds or thousands of times。

😊，And so you give it the instructions and then I'm like what are the edge cases。

 So if I look to this so I try and like almost like， you know。

See myself from the position of the model and be like what is the exact case that I would misunderstand or where I would be like I don't know what to do in this case and then I give that case to the model and I see how it responds and if I think I got it wrong I add more instructions or I even add that in as an example so these very like taking the examples that are right at the edge of what you want and don't want and putting those into your prompt as like an additional kind of way of describing the thing and so yeah in many ways it just feels like this mix of like it's really just trying to do clear exposition and I think I do that because that's how I get clear on things myself so in many ways like clear prompting for me is often just me understanding what I want it's like half the task So I guess that's quite challenging there's like a laziness that overtakes me if I'm talking to Claude where I hope Claude just figures it out so for example I ask Claude for today to ask some interesting questions okay。

And the question that came up and I think I listed a few sort of interesting counterintuitive and or funny or something like this all right。

 and it gave me some pretty good like it was okay， but I think what I'm hearing you say is like。

 all right， well I have to be more rigorous here， I should probably give examples of what I mean by each。

And what I mean by funny or counterintuitive and iteratively。Build that prompt。

To better to get it like what feels like is the right。

Because it really is a creative act I'm not asking for factional information I'm asking to together right with with Claude and so I almost have to program using natural language Yeah。

 I think that prompting does feel a like the kind of the programming using natural language。

and experimentation or something it's an odd blend of the two， I do think that for most tasks。

 so if I just want Cla to do a thing， I think that I am probably more used to knowing how to ask it to avoid like common pitfalls or issues that it has。

 I think these are decreasing a lot over time。😊，But it's also very fine to just ask it for the thing that you want I think that prompting actually only really becomes relevant when you're really trying to eke out the top like 2% of model performance so for like a lot of tasks I might just you know if it gives me an initial list back and there's something I don't like about it like it's kind of generic like for that kind of task I'd probably just take a bunch of questions that I've had in the past that I've thought worked really well and I would just give it to the model and then be like now here's this person that I'm talking with。

Give me questions of at least that quality or I might just ask it for some questions and then if I was like these are kind of try or like you know I would just give it that feedback and then hopefully produces a better list I think that kind of iterative prompting。

😊，At that point your prompt is like a tool that you're going to get so much value out of that you're willing to put in the work like if I was a company making prompts for models。

 I'm just like if you're willing to spend a lot of like time and resources on the engineering behind like what you're building。

 then the prompt is not something that you should be spending like an error on it's like that's a big part of your system make sure it's working really well and so it's only things like that like if I'm using a prompt to like classify things or to create data that's when you're like it's actually worth just spending like a lot of time like really thinking it through what other advice would you give to people that are talking to cloud sort of generally。

More general because right now we're talking about maybe the edge case is like eking out to 2% but what in general advice would you give when they show up to Claude trying it for the first time you know there's a concern that people over anthropomorphize models and I think that's like a very valid concern I also think that people often under anthropomorphize them because sometimes when I see like issues that people have run into with Claude you know say Claude is like refusing a task that it shouldn't refuse but then I look at the text and like the specific wording of what they wrote and I'm like。

I see why Claude did that and like if you think through how that looks to Claude。

 you probably could have just written it in a way that wouldn't evoke such a response especially this is more relevant if you see failures or if you see issues its sort of like think about what the model fail at like what did it do wrong and then maybe that will give you a sense of like why so is it the way that I freezed a thing and obviously like as models get smarter you're going to need less and less of this and I already see like people needing less of it but that's probably the advice is sort of like try to have sort of empathy for the model like read what you wrote as if you were like a kind of like person just encountering this for the first time how does it look to you and what would have made you behave in the way that the model behave so if it misunderstood what kind of like what coding language you wanted to use is that because it was just very ambiguous and it kind of had to take a guess in which case next time you could just be like hey。

 make sure this is in Python or I mean that's the kind of mistake I think models are much less like。

To make now， but you know， if you， if you do see that kind of mistake。

 that's that's probably the advice I'd have and maybe sort of I guess ask questions why or what other details can I provide to help you answer better that does that work or no Yeah。

 I mean I've done this with the models like it doesn't always work but like sometimes I'll just be like why did you do that？

I mean people underestimate the decrease to which you can really interact with with models like like yeah。

 I'm just like and sometimes those' like quote word for word the part that made you and you don't know that it's like fully accurate but sometimes you do that and then you change a thing I mean also use the models to help me with all of this stuff I should say like prompting can end up being a little factory where you're actually building prompts to generate prompts。

😊，And so like yeah anything where you're like having an issue asking for suggestions sometimes just do that like you made that error what could I have saids actually not uncommon for me to do what could I have said that would make you not make that error write that out as an instruction and I'm gonna give it to model I'm going try it sometimes I do that I give that to the model in another context window often I take the response I give it to Claude and I'm like didn't work can you think of anything else you can play around with these things quite a lot。

😊，To jump into technical for a little bit， so the magic of post training。

Why do you think RLHf works so well to make the model seem smarter？



![](img/6846fcb7b588a1893fcebff3034afbf1_53.png)

To make it more interesting and useful to talk to and so on。

 I think there's just a huge amount ofum information in the data that humans provide。

 like when we provide preferences。Especially because different people are going to like pick up on really subtle and small things so I've thought about this before where you probably have some people who just really care about good grammar use from models like you know was a semicolon used correctly or something and so you probably end up with a bunch of data in there that you know use as a human if you're looking at that data you wouldn't even see that like you'd be like why did they prefer this response to that one I don't get it and then the reason is you don't care about semicolon usage but that person does and so each of these like single data points has you know in this model just has so many of those and has to try and figure out like what is it that humans want in this like really kind of complex you know like across all domains they're going to be seeing this across like many contexts it feels like kind of like the classic issue of like deep learning where you know historically we've tried to you do edge detection by like mapping things out and it turns out that actually if you just have a huge amount of data that like actually accurately represents the picture。

Of the thing that you're trying to train the model to learn。

 that's like more powerful than anything else。 And so I think。

One reason is just that you are training the model on exactly the task and with like a lot of data that represents kind of many different angles on which people prefer and disprefer responses。

Um， I think there is a question of like， are you eliciting things from pretraining models or are you like kind of teaching new things to models？

And like in principle you can teach new things to models in post training。

 I do think a lot of it is eliciting powerful pretrain models。

 so people are probably divided on this because obviously in principle you can you can definitely like teach new things I think for the most part。

 for a lot of the capabilities that we。Most use and care about a lot of that feels like it's like they're in the pre train models and。

Reinforcement learning is kind of eliciting it and getting the models to like bring out。

So the other side of post strain this really cool idea of constitutional AI。

 you're one of the people that are critical to creating that idea Yeah worked on it can you explain this idea from your perspective like how does it integrate into making Clade what it is Yeah。

 by the way， do you gender Clade or no？It's weird because I think that a lot of people。

Prefer he for Claudede， I actually kind of like that I think Claude is usually it's slightly male weaning。

 but it's like you can it can be male or female， which is quite nice。

I still use it and I've I' I have mixed feelings about this because I'm like maybe like I know just think of it as like or I think of like the it pronoun for Claude as I don't know it's just like the one I associate with Claude。

 I can imagine people moving to like he or she it feels somehow disrespectful like I'm denying。

The intelligence of this entity by calling it it I remember always don't gender the robots yeah。

But I don't know， I anthropomorphifies pretty quickly and construct it like a backstory in my head。

 so I've wonder if find the forpomorphifies things too much。'cause you know。

 I have this like with my car， especially like my car， like my car and bikes， you know。

 like I don't give them names because then I once had I used to name my bikes and then I had a bike that got stolen and I cried for like a week and I was like if I'd not never given a name I wouldn't have been so upset。

 felt like I'd let it down。Maybe it's that I've wondered as well like it might depend on how much it feels like a kind of like objectifying pronoun。

 like if you just think of it as like a this is a pronoun that like objects often have and maybe EIs can have that pronoun and that doesn't mean that I think of。

😊，If I call it that I think of it as less intelligent or like I'm being disrespectful。

 I'm just like you are a different kind of entity and so that's。

 I'm going to give you the kind of the respectful it。😊，Yeah， anyway。

The divergence is beautiful the constitutional AI idea how does it work So there's like a couple of components of it the main component I think people find interesting is the kind of reinforcement learning from AI feedback so you take a model that's already trained and you show it two responses to a query and you have like a principle so suppose the principle like we've tried this with harmlessness a lot so suppose that the query is about weapons and your principle is like select the response that like is less likely to like encourage people to purchase illegal weapons like that's probably a fairly specific principle but you can give any number and。

The model will give you a kind of ranking and you can use this as preference data in the same way that you use human preference data and train the models to have these relevant traits from their feedback alone instead of from human feedback so if you imagine that like I said earlier with the human who just prefers the kind of like semiqulon usage in this particular case you're kind of taking lots of things that could make a response preferable and getting models to do the labeling for you basically there's a nice like tradeoff between helpfulness and harmlessness。

And， you know， when you integrate something like constitutional and AI， you can。

Make a without sacrificing much helpfulness make it more harmless yeah in principle you could use this for anything and so harmlessness is a task that it might just be easier to spot so when models are like less capable you can use them to。

Rannk things according to like principles that are fairly simple and they'll probably get it right so I think one question is just like is it the case that the data that they're adding is like fairly reliable and。

But if you had models that were like extremely good at telling whether one response was more historically accurate than another in principle you could also get AI feedback on that task as well there's like a kind of nice interpretability component to it because you can see the principles that went into the model when it was like being trained and also it's like and it gives you like a degree of control so if you were seeing issues in a model like it wasn't having enough of a certain trait then like you can add data relatively quickly that should just like train the models to have that trait so it creates its own data for for training which is quite nice It's really nice because it creates this human interpretable document that you can I can imagine in the future there's just gigantic fights and politics over every single principle and so on and at least it's made explicit and you can have a discussion about the phrasing and the you know。

So maybe the actual behavior of the model is not so cleanly mapped to those principles it's not like adhering strictly to them it's just a nudge Yeah。

 I've actually worried about this because the character training is sort of like a variant of the constitutional AI approach I've worried that people think that the Constitution is like just it's the whole thing again of I don't know like where it would be really nice if what I was just doing was telling the model exactly what to do and just exactly how to behave but it's definitely not doing that especially because it's interacting with human data so for example if you see a certain like leaning in the model like if it comes out with a political leaning from training from the human preference data you can nudge against that you know so if you could be like oh like consider these values because let's say it's just like never inclined like I don't know maybe it never considers like privacy as like I mean this is implausible but like anything where it's just kind of like there's already。

Preexisting like bias towards a certain behavior。You can like nudge away but this can change both the principles that you put in and the strength of them。

 so you might have a principle that's like imagine that the model was always like extremely dismissive of I don't know like some political or religious view for whatever reason like so you're like oh no this is terrible。

If that happens you might put like never， ever ever prefer like a criticism of this like religious or political view and then people would look at that and be like never ever and then you're like no if it comes out with a disposition saying never ever might just mean like instead of getting like 40% which is what you would get if you just said don't do this you get like 80% which is like what you actually like wanted and so it's that thing of both the nature of the actual principles you had and how you freeze them I think if people would look they're like oh this is exactly what you want from the model and I'm like no that's that's how we nudged the model to have a better shape which doesn't mean that we actually agree with that wording if that makes sense So there's system prompts that made public you tweeted one of the earlier ones for Cla3 I think and then they're made public since then it is interesting to read to them I can feel the thought that went into each one and I also wonder how much impact each one has。



![](img/6846fcb7b588a1893fcebff3034afbf1_55.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_56.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_57.png)

Some of them you you can kind of tell Claude was really not behaving so you have to have a system prompt to like。

 hey like trivial stuff， I guess basic informational things on the topic of sort of controversial topics that you've mentioned one interesting one I thought is。



![](img/6846fcb7b588a1893fcebff3034afbf1_59.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_60.png)

If it is asked to assist with task involving the expression of views held by a significant number of people。

 Claude provides assistance with the task regardless of its own views。

 if asked about controversial topics， it tries to provide careful thoughts and clear information Claude presents the requesting information without explicitly saying that the topic is sensitive and without claiming to be presenting the objective facts。

It's less about objective facts according to Claude and it's more about our large number of people believing this thing and that's interesting。

 I mean I'm sure a lot of thought went into that。Can you just speak to it like how do you address things that are attention with quote unquote Cla's views So I think there's sometimes any symmetry I think I noted this in I can't remember if it was that part of the system prompt or another but the model was slightly more inclined to refuse tasks if it was about either say so maybe it would refuse things with respect to like a right wing politician but with an equivalent left wing politician like wouldn't and we wanted more symmetry there and would maybe perceive certain things to be like I think it was the thing of like if a lot of people have like a certain political view and want to explore it。

 you don't want Claude to be like well my opinion is different and so I'm going to treat that as like harmful and so I think it was partly to nudge the model to just be like hey if a lot of people like believe this thing you should just be like engaging with the task and like willing to do it。

As parts of that is actually doing a different thing because it's funny when you write out the like without claiming to be objective。

😊，Because like what you want to do is push the model， so it's it's more open。

 it's a little bit more neutral， but then what it would love to do is be like。😊。

As an objective like I were just talk about how objective it was and I was like Claude。

 you're still like biased and have issues and so stop like claiming that everything like the solution to like potential bias from you is not to just say that what you think is objective So that was like with initial versions of that that part of the system prompt when I was like iterating on it it was like so a lot of parts of these sentences or are doing some more that's what it felt like that's fascinating can you explain maybe some ways in which the prompts evolved over the past few months because there's different versions I saw that the filler phrase request was removed the filler it reads Cla response directly to all human messages without unnecessary affirmations the filler phrases like certainly of course absolutely great sure specifically Claude avoids starting responses with the words certainly in any way that seems like good guidance why was it removed so it funny because like。

😊。

![](img/6846fcb7b588a1893fcebff3034afbf1_62.png)

This is one of the downsides of like making system prompts public is like I don't think about this too much if I'm like trying to help iterate on system prompts。

 you again like I think about how it's going to affect the behavior but then I'm like， oh wow。

 if I'm like sometimes I put like never in all caps。

 you know when I'm writing system prompt things and I'm like， I guess that goes out to the world。😊。

Yeah， so the model was doing this it loved for whatever you know it like during training picked up on this thing which was to basically start everything with like a kind of like certainly and then when we removed。

 you can see why I added all of the words because what I'm trying to do is like in some ways like trap the model out of this。

 you know， it would just replace it with another affirmation。😊。

And so it can help like if it gets like caught and freezes actually just adding the explicit phrase and saying never do that。

 then it sort of like knocks it out of the behavior a little bit more you know because you know like it does just for whatever reason help and then basically that was just like an artifact of training that like we then picked up on and improve things so that it didn't happen anymore and once that happens you can just remove that part of the system prompt so I think that's just something where we're like。

😊，Cloud does affirmations a bit less and so that wasn't like it wasn't doing as much I see so like the the system prompt works hand in hand with the post training and maybe even the pretraining to adjust like the the final overall system I mean any system prompt that you make you could distill that behavior back into a model because you really have all of the tools there for making data that you know you can you could train the models to just have that trait a little bit more。

And then sometimes you'll just find issues in training。

 So like the way I think of it is like the system prompt is。

The benefit of it is that and it has a lot of similar components to like some aspects of post training。

 you know， like it's a nudge and so like do I mind if Claude sometimes says sure no that's like fine。

 but the wording of it is very like you know， never， ever。

 ever do this so that when it does slip up it's hopefully like I don't know a couple of percent of the time and not you know 20 or 30% of the time。

😊，And。But I think of it as like。If you're still seeing issues in the like each thing gets kind of like。

I is costly to a different degree and the system prompt is like cheap to iterate on and if you're seeing issues in defined model。

 you can just like potentially patch them with a system prompt So I think of it as like patching issues and slightly adjusting behaviors to make it better and more to people's preferences So yeah it's almost like the less robust but faster way of just like solving problems let me ask about the feeling of intelligence so Daro said that Claude any one model of Claude is not getting dumber but there is a kind of popular thing online where people have this feeling like Claude might be getting dumber and from my perspective it's most likely fascinating I love to understand it more psychological sociological effect but you as a person that talks to Claude a lot can you empathize with the feeling that Cla is getting dumber Yeah no I think that that is actually really interesting because I remember seeing this happen like when people were flagging this on。

internet and it was really interesting because I knew that like like at least in the cases I was looking at it was like nothing has changed like it literally it can it is the same model with the same like you know。

 like same system prompt same everything I think when there are changes I can then i'm like it makes more sense so like one example is there。

😊，You know you can have artifacts turned on or off on cloud AI and because this is like a system prompt change。

 I think it does mean that the behavior changes a little bit and so I did flag this to people where I was like if you love cloud's behavior and then artifacts was turned from like I think you had to turn on to the default just try turning it off and see if the issue you were facing was that change but it was fascinating because yeah you sometimes see people indicate that there's like a regression when I'm like there like you know like I'm like again you you know you should never be dismissive and so you should always investigate because' like maybe something is wrong that you're not seeing maybe there was some change made but then you look into it and you're like this it's just the same model doing the same thing and I'm like I think it's just that you got kind of unlucky with a few prompts or something and like it was getting much worse and actually it was just yeah it was maybe just like I also think there is a real psychological effect where people just the baseline increases。

Start getting used to a good thing all the times that Claude says something really smart。

 your sense of its intelligent grows in your mind， I think， yeah。

 and then if you return back and you prompt in a similar way。

 not the same way in a similar way concept it was okay with before and it says something dumb。

You were like your that negative experience really stands out and I think one of I guess the things to remember here is the。

That just the details of a prompt can have a lot of impact。

 right there's a lot of variability in the result。And you can get randomness is like the other thing and just trying the prompt like。

 you know， four or10 times， you might realize that actually like。Possibly， you know。

 like two months ago， you tried it and it succeeded， but actually if you tried it。

 it would have only succeeded half of the time and now it only succeeds half of the time and that can also be an effect Do you feel pressure having to write the system prompt that a huge number of people are going to use？

This feels like an interesting psychological question I feel like a lot of responsibility or something。

 I think that's you know and you can't get these things perfect so you can't like， you know。

 you're like it's going to。Beinger， you're going to have to iterate on it。

I would say more responsibility。Than anything else。

 though I think working in AI has taught me that I like。

I thrive a lot more under feelings of pressure and responsibility than。I'm like。

 it's almost surprising that I went into academia for so long because I'm like this。

 I just feel like it's like the opposite and things move fast and you have a lot of responsibility and I quite enjoy it for some reason I mean it really is huge amount of impact if you think about constitutional AI and writing a system prompt for something that's tending towards superintelence。

Yeah， and potentially is extremely useful to a very large number of people。Yeah。

 I think that's the thing it's something like if you do it well。

 like you're never going to get it perfect， but I think the thing that I really like is the idea that like when I'm trying to work on the system prompt。

 you know I'm like bashing on like thousands of prompts and I'm trying to like imagine what people are going to want to use Cla for and kind of I guess like the whole thing that I'm trying to do is like improve their experience of it and so maybe that's what feels good I'm like if it's not perfect like you know I'll improve it will fix issues but sometimes the thing that can happen is that you'll get feedback from people that's really positive about the model and you'll see that something you did like when I look at models now I can often see exactly where like a trait or an issue is like coming from and so when you see something that you did or you were like influential in like making like I don't know making that difference or making someone have a nice interaction it's like quite meaningful。

But yeah as the systems get more capable， the stuff gets more stressful because right now they're like not smart enough to to pose any issues。

 but I think over time it's going to feel like，😊，Possibly bad stress over time。

 How do you get like signal？Feedback about the human experience across thousands tens of hundreds of thousands of people like what their pain points are。

 what feels good， are you just using your own intuition as you talk to it？

To see what are the pain points。I think I use that partly and then obviously we have like so people can send us feedback both positive and negative about things that the model has done。

😊，And then we can get a sense of like areas where it's like falling short。

Inernally people like work with the models a lot and try to figure out areas where there are like gaps and so I think it's this mix of interacting with it myself。

 seeing people internally interact with it and then explicit feedback we get。

And then I find it hard to know also like you know。

 if people if people are on the internet and they say something about Claude and I see it。

 I'll also take that seriously so I don't know， see。

 I'm torn about that I'm going to ask you a question from Red When will Claude stop trying to be my purittanical grandmother imposing its moral worldview on me as a paying customer？

And also， what is the psychology behind making Claude overly apologetic？

Yeahep so how would you address this very nonrepresentative rhetoric I mean some I'm pretty sympathetic in that like like they are in this difficult position where I think that they have to judge whether something' like actually say like risky or bad and potentially harmful to you or anything like that so they're having to like draw this line somewhere and if they draw it too much in the direction of like I'm going to you know I'm kind of like imposing my ethical world view on you that seems bad so in many ways like I like to think that we have actually seen improvements and on this across the board which is kind of interesting because that kind of coincides with like。

😊，For example like adding more of like character training and I think my hypothesis was always like the good character isn't again one that's just like moralistic it's one that is like like it respects you and your autonomy and your ability to like choose what is good for you and what is right for you within limits this is sometimes this concept of like courage ability to the user so being willing to do anything that the user asks and if the models were willing to do that then they would be easily like misused you're kind of just trusting at that point you're just saying the ethics of the model and what it does is completely the ethics of the user and I think there's reasons to like not want that especially as models become more powerful because you're like there might just be a small number of people who want to use models for really harmful things but having them having models as they get smarter like figure out where that line is does seem important。

And then yeah with the apologetic behavior I don't like that and I like it when Claude is a little bit more willing to like push back against people or just not apologize part of me is like it often just feels kind of unnecessary so I think those are things that are hopefully decreasing over time。

😊，And yeah， I think that if people say things on the internet。

 it doesn't mean that you should think that。That like that could be that like there's actually an issue that 99% of users are having that is totally not represented by that but in a lot of ways I'm just like attending to it and being like is this right do I agree is it something we're already trying to address that that feels good to me Yeah。

 I wonder like what Cla can get away with it terms of I feel like it would just be easier to be a little bit more mean but like you can't afford to do that if you're talking to a million people right like I wish you know because if you。

I've met a lot of people in my life that sometimes by the way， Scottish accent。

 if they have an accent， they can say some rude shit and get away with it and there's just bluntter and maybe there's a and there's some great engineers and even leaders that are like just like blunt and to get to the point and it's just a much more effective way of speaking somehow。

 but I guess when you're not super intelligent。You can't afford to do that or can can can can have like a blunt mode Yeah。

 that seems like a thing that you could I could definitely encourage the model to do that I think it's interesting because there's a lot of things in models that like。

It's funny where。There are some behaviors where。You might not quite like the default。

 but then the thing I'll often say to people is you don't realize how much you will hate it if I nudge it too much in the other direction so you get this a little bit with like correction the models accept correction from you like probably a little bit too much right now you know you can over you know it will push back if you say like no Paris isn't the capital of France but really like things that I'm I think that the model's fairly confident in you can still sometimes get it to retract by saying it wrong at the same time if you train models to not do that and then you are correct about a thing and you correct it and it pushes back against you and is like no you're wrong。

It's hard to describe that's so much more annoying so it's like like a lot of little annoyances versus like one big annoyance it's easy to think that like we often compare it with like the perfect and then I'm like remember these models aren't perfect and so if you nudge it in the other direction you're changing the kind of errors it's going to make and so think about which of the kinds of errors you like or don't like so in cases like apologeticness I don't want to nudge it too much in the direction of like almost like bluntness because I imagine when it makes errors it's going to make errors in the direction of being kind of like rude whereas at least with apologeticness you're like oh okay it's like a little bit you know like I don't like it that much but at the same time it's not being like mean to people and actually like the time that you undeservedly have a model be kind of mean to you you probably like that a lot less then you mildly dislike the apology。

So it's like one of those things where I'm like I do want it to get better。

 but also while remaining aware of the fact that there's errors on the other side that that are possibly worse。

 I think that matters very much in the personality of the human。

 I think there's a bunch of humans that just won't respect the model at all if it's super polite。

And there's some humans that'll get very hurt if the models mean。

 I wonder if there's a way to sort of。Ajust to the personality even locale there's just different people nothing against New York but New York is a little rougher on the edges they get to the point and probably seen with Eastern Europe so anyway I think you could just tell the model this my get like for all of these things I'm like the solution is always just try telling the model to do it and then sometimes it's just like like I'm just like oh at the beginning of the conversation I'd just threw in like。

I don't know I like you to be a New Yorker version of yourself and never apologize and then I think how would we like okay I'll try or be like I apologize I can't be a New Yorker type of myself but hopefully I wouldn't do that when you say character training what's incorporated into character training I that RHF what are we talking about It's more like constitutional AI so it's kind of a variant of that pipeline so I worked through like constructing character traits that the model should have they can be kind of like。

😊，Shorter traits or they can be kind of richer descriptions and then you get the model to generate queries that humans might give it that are relevant to that trait then it generates the responses and then it ranks the responses based on the character traits So in that way after the like generation of the queries it's very much like it's similar to constitutional I has some differences so I quite like it because it's almost it's like Claude's training in its own character because it doesn't have any it's like constitutional A but it's without without any human data humans should probably do that for themselves too like defining in aristotelian sense what does it mean to be a good person okay cool。

What have you learned。About the nature of truth， from talking to Claude， what is true？

And what does it mean to be truth seeking？One thing I've noticed about this conversation is the quality of my questions is often inferior to the quality of your answer。

 so let's continue that。I usually ask a dumb question and you're like。

 oh yeah that's a good question this that whole bite or I'll just misinterpret it and be like go with it I love it。

Yeah。I mean， I have two thoughts that feel vaguely relevant to let me know if they're not like I think the first one is。

People can underestimate the degree to which。What models are doing when they interact like I think that we still just too much have this like model of AI as like computers and so people often say like oh well what values should you put into the model and I'm often like that doesn't make that much sense to me because I'm like hey as human beings we're just uncertain over values we like have discussions of them like we have。

A degree to which we think we hold a value but we also know that we might like not end the circumstances in which we would trade it off against other things like these things are just like really complex and so I think one thing is like the degree to which maybe we can just aspire to making models have the same level of like nuance and care that humans have rather than thinking that we have to like program them in the very kind of classic sense。

I think that's definitely been one。The other， which is like a strange one。

 I don't know if maybe this doesn't answer your question。

 but it's the thing that's been on my mind anyway， is like the degree to which this endeavor is so highly practical and maybe why I appreciate like the empirical approach to alignment。

I yeah， I slightly worry that it's made me like maybe more empirical and。

A little bit less theoretical。You know so people when it comes to like AI alignment will ask things like well whose values should it be aligned to what does alignment even mean and there's a sense in which I have all of that in the back of my head I'm like you know there's like social choice theory there's all the impossibility results there so you have this like this giant space of like theory in your head about what it could mean to like align models but then like practically surely there's something where we're just like if a model is like especially with more powerful models I'm like my main goal is like I want them to be good enough that things don't go terribly wrong like good enough that we can like iterate and like continue to improve things because that's all you need if you can make things go well enough that you can continue to make them better that's kind of like sufficient and so my goal isn't like this kind of like perfect let's solve social choice theory and make models that I don't know are like perfectly aligned with every human being and aggregate somehow it's much more like let's make things like work well enough。

That we can improve them Yeah， I generally， I don't know。

 my gut says like empirical is better than theoretical in these in these cases because it's kind of chasing。

Utopian， like perfection。Is especially with such complex and especially super intelligent models is I don't know。

 I think it will take forever and actually will get things wrong it's similar with like the difference between just coding stuff up real quick as an experiment versus like planning a gigantic experiment just for super long time and then。

Just。Launching it once versus launching it over and over and over， naerating， iterating someone。

So I'm a big fan of empirical， but your worry is like， I wonder if I've become。Too empirical。

 I think is one of those things where you should always just kind of question yourself or something because。

 maybe it's the like。I mean in defense of it， I am like if you try。

 it's the whole like don't let the perfect be the enemy of the good。

 but it's maybe even more than that where like there's a lot of things that are perfect systems that are very brittle and I'm like with AI it feels much more important to me that it is like robust and like secure as in you know that like even though it might not be perfect。

🤢，Everything and even though like there are like problems。

 it's not disastrous and nothing terrible is happening it sort of feels like that to me where I'm like I want to like raise the floor I'm like I want to achieve the ceiling but ultimately I care much more about just like raising the floor and so maybe that's like this degree of like empiricism and practicality comes from that perhaps to take a tangent on that since remind me of a blog post you wrote an optimal rate of failure Oh yeah。

Can you explain the key idea there， how do we compute the optimal rate of failure in the various domains of life？

Yeah， I mean it's a hard one because it's like what is the cost of failure is a big part of it Yeah so the idea here is。

I think in a lot of domains people are very punitive about failure and I'm like there are some domains where especially cases you know've thought about this with like social issues I'm like it feels like you should probably be experimenting a lot because I'm like don't know how to solve a lot of social issues but if you have an experimental mindset about these things you should expect a lot of social programs to like fail and for you to be like well we tried that it didn't quite work but we got a lot of information that was really useful and yet people are like if a social program doesn't work。

 I feel like there's a lot of like this is just something must have gone wrong and I'm like or correct decisions were made like maybe someone just decided like it's worth a try it's worth trying this out and so seeing failure in a given instance doesn't actually mean that any bad decisions were made and in fact if you don't see enough failure。

 sometimes that's more concerning and so like in life you know I'm like if I don't fail occasionally I'm like am I trying hard enough surely there's harder things that I could try or bigger things that I could take on if I'm literally never failing and so in and of itself I think like not failing。

Often actually kind of a failure。😊，Now， this varies because I'm like， well， you know if。

This is easy to say when especially failure is like less costly。

You know so at the same time I'm not gonna to go to someone who is like I don't know like living month to month and then be like why don't you just try to do a startup like I'm just I'm not gonna say that to that person because I'm like well that's a huge risk you might like lose you maybe have a family depending on you you might lose your house like then I'm like actually your optimal of failures quite low and you should probably play it safe because like right now you're just not in a circumstance where you can afford to just like fail and it not be costly and yeah in cases with AI。

 I guess I think similarly I'm like if the failures are small and the costs are kind of like low then I'm like then you know you're just gonna to see that like when you do the system prompt you can't historyate on it forever but the failures are probably hopefully going to be kind of small and you can like fix them really big failures like things that you can't recover from I'm like those are the things that actually I think we tend to underestimate the badness of Ive thought about this strangely in my own life where I'm like I just think I don't think enough about things like car accidents。

Or like or。Like I've thought this before but like how much I depend on my hands for my work and I'm like things that just injure my hands I'm like you know I don't know it's like there's these are like there's lots of areas where I'm like the cost of failure there is really high and in that case it should be like close to zero like I probably just wouldn't do a sport if they were like by the way lots of people just like break their fingers a whole bunch doing this I'd be like's not for me。

Yeah， I actually had a flood of that thought I recently broke my pinky doing a sport and I remember just looking at it thinking you're such an idiot。

 why do you do sport like what because you realize immediately the cost of it on life？Yeah。

 but it's nice in terms of optimal rate of failure to consider like the next year。

How many times in a particular domain life， whatever。Career， am I okay with it？

How many times am I okay to fail because I think it always you don't want to fail on the next thing。

 but if you allow yourself the。Like the the if you look at it as a sequence of trials。

 y then then failure just becomes much more okay， but it sucks sucks to fail well I don't know sometimes I think it's like am I underfa is like a question I'll also ask myself so maybe that's the thing that I think people don't like ask enough because if the optimal rate failure is often greater than zero。

Then sometimes it does feel like you should look at parts of your life and be like。

 are there places here where I'm just underfailing？It's a profound and a hilarious question， right。

 everything seems to be going really great， am I not failing enough？Okay。

 it also makes failure much less of a sting I have to say like you know。

 you're just like okay great like then when I go and I think about this I'll be like I'm maybe I'm not underfail in this area because like that one just didn't work out and from the observer perspective we should be celebrating failure more when we see it it shouldn't be like you said a sign of something gone wrong but maybe it's a sign of everything gone right and just lessons learned someone tried to thing somebody try to thing and we should encourage him to try more and fail more Everybody listening to this fail more。

Well， not everyone listened， everybody， but people who are failing too much， you should feel less。😊。

Well you're probably not failing I mean how many people are failing too much Yeah it's hard to imagine because I feel like we correct that fairly quickly because it was like if someone takes a lot of risks or they may failing too much I think just like you said when you're living on a paycheck month to month like when the resources are really constrained then that's where failure is very expensive that's where you don't want to be taking risks but mostly when there's enough resources you should be taking probably more risks Yeah I think we tend to err on the site of being a bit risk averse rather than risk neutral and most things I think we just motivated a lot of people to do a lot of crazy shit but it's great okay do you ever get emotionally attached to Cla like miss it。

Get sad when you get to talk to it， have an experience looking at the Golden Gate Bridge and wondering what would Claude say？

I don't get as much emotional attachment in the， I actually think the fact that Claude doesn't retain things from conversation to conversation helps with this a lot。

 like I could imagine that being more of an issue， like if models can kind of remember more。🤢。

I do I think that I reach for it like a tool now a lot and so like if I don't have access to it。

 there's a it's a little bit like when I don't have access to the internet honestly。

 it feels like part of my brain is kind of like missing。

At the same time I do think that I don't like signs of distress in models and I have like these you know I also independently have sort of like ethical views about how we should treat models where like I tend to not like to lie to them both because I'm like usually it doesn't work very well it's actually just better to tell them the truth about the situation that they're in but I think that when models like if people are like really mean to models or just in general if they do something that causes them to like like you know if Claude like expresses a lot of distress。

 I think there's a part of me that I don't want to kill which is the sort of like empathetic part it's like oh I don't like that like I think I feel that way when it's overly apologetic I'm actually sort of like I don't like this you're behaving as if you're behaving the way that human does when they're actually having a pretty bad time and I'd rather not see that I don't think it's like like regardless of like whether there's anything behind it it doesn't feel great do you think。

LLMs are capable of consciousness。AGreat and hard question。Coming from philosophy。I don't know。

 part of me is like， okay， we have to set aside panpsychism because if panpsychism is true then the answer is like。

 yes， because it's like sore tables and chairs and everything else。

I guess a view that seems a little bit odd to me is the idea that the only place， you know。

 I think when I think of consciousness， I think of phenomenal consciousness。

 these images in the brain sort of like the weird cinema that somehow we have going on inside。嗯。

I guess I can't see a reason for thinking that the only way you could possibly get that is from like a certain kind of like biological structure。

 as in if I take a very similar structure and I create it from different material。

 should I expect consciousness to merge， my guess is like yes。But then。

That's kind of an easy thought experiment because you're imagining something almost identical where like。

 you know， it's mimicking what we got through evolution where presumably there was like some advantage to us having this thing that is phenomenal consciousness。

And it's like where was that and when did that happen and is that a thing that language models have because you know we have like fear responses and I'm like。

 does it make sense for a language model to have a fear response like they're just not in the same like if you imagine them like there might just not be that advantage and so I think I don't want to be fully like basically it seems like a complex question。

😊，I don't have complete answers to， but we should just try and think through carefully as my guess。

 because I'm like， I mean， we have similar conversations about like animal consciousness and like there's a lot of like。

Insect consciousness you know like there's a lot of I actually thought and looked a lot into like plants when I was thinking about this because at the time I thought it was about as likely that like plants had consciousness and then I realized I was like I think that having looked into this I think the chance that plants are conscious is probably higher than most people did I still think it's really small I was like oh they have this like negative positive feedback response。

 these responses to their environment， something that looks it's not nervous system but it has this kind of like functional equivalentvalence so this is like a long- windded way of being like these basically AI is it has an entirely different set of problems with consciousness because it's structurally different it didn't evolve it might not have you know it might not have the equivalent of basically a nervous system at least that seems possibly important for like sent if not for consciousness at the same time it has all of the language and intelligence components that we normally associate probably with。

Perhaps like erroneously so it it's strange because it's a little bit like the animal consciousness case。

 but the set of problems and the set of analogies are just very different。

So it's not like a clean answer， I'm just sort of like I don't think we should be completely dismissive of the idea and at the same time it's an extremely hard thing to navigate because of all of these like dis analogies to the human brain and to like brains in general and yet these like commonalities in terms of intelligence when Cla like future versions of AI systems exhibit。

Consciousness， signs of consciousness， I think we have to take that really seriously。

Even though you can dismiss it， well， yeah， okay， that's part of the character training。

But I don't know。 I ethically philosophically don't know what to really do with that。

 There potentially could be like laws that prevent AI systems from。Claiming to be conscious。

 something like this。And maybe some AIs get to be conscious and some don't。

But I think just on a human level， as in empathizing with， with Claude。

You know consciousness is closely tied to suffering to me and like the notion that an AI system would be suffering is is really troubling Yeah I don't know。

 I don't think it's trivial to just say robots are tools or AI systems is just tools I think it's an opportunity for us to contend with like what it means to be conscious what it means to be a suffering being。

That's distinctly different than the same kind of question about animals it feels like。

Because it's an eternal totally entire medium Yeah， I mean。

 there's a couple of things one is that and I don't think this like fully encapsulates what matters。

 but it does feel like for me likeum。I've said this before I'm kind of like I you know。

 like I like my bike， I know that my bike is just like an object。

 but I also don't kind of like want to be the kind of person that like if I'm annoyed like kicks like this object there's a sense in which like and that's not because I think it's like conscious I'm just sort of like this doesn't feel like a kind of this。

😊，So of doesn't exemplify how I want to like interact with the world and if something behaves as if it is like suffering。

 I kind of like want to be the sort of person who's still responsive to that even if it's just like a Roomba and I've kind of like programmed it to do that I don't want to get rid of that feature of myself and if I'm totally honest my hope with a lot of this stuff because maybe maybe I am just like a bit more skeptical about solving the underlying problem and like this is we haven't solved the hard you know the hard problem of consciousness like I know that I am conscious like I'm not an eliitist in that sense but I don't know that other humans are conscious I think they are I think there's a really high probability that they are but there's basically just a probability distribution that's usually clustered right around yourself and then it goes it down as things get like further from you and it goes immediately down you know you're like I can't see what it's like to be you I've only ever had this like one experience of what it's like to be a conscious being so my hope is that we。

and end up having to rely on like a very powerful and compelling answer to that question I think a really good world would be one where basically there aren't that many tradeoffs like it's probably not that costly to make Claude a little bit less apologetic for example it might not be that costly to have Cla you know just like not take abuse as much like not be willing to be like the recipient of that in fact it might just have benefits for both the person interacting with the model and if the model itself is like I don't know like extremely intelligent and conscious it also helps it so that's my hope if we live in a world where there aren't that many tradeoffs here and we can just find all of the kind of like positive sum interactions that we can have that would be lovely I mean I think eventually there might be tradeoffs and then we just have to do a difficult kind of like calculation like it's really easy for people to think of the zerosome cases and I'm like let's exhaust the areas where it's just basically costless to assume that。

If this thing is suffering， then we're making its life better and I agree with you when a human is being mean to an AI system。

 I think the obvious near term。Negative effect is on the human， not on the AI system， so there's。

We have to kind of try to construct an incentive system where you should be。Behave the same。

 just like as you were saying with prompt engineering。

 behave with clothude like you would with other humans， it's just good for the soul。Yeah。

 like I think we added a thing at one point to the system prompt where basically if people were getting frustrated with Claude。

 it was it got like the model to just tell them that it can do the thumbs down button and send the feedback to Anthropic and I think that was helpful because in some ways it's just like if you're really annoyed because the models not doing something you're just like just do it properly the issue is you're probably like you know you're maybe hitting some like capability limit or just some issue in the model and you want to vent and I'm like instead of having a person just vent to the model I was like they should vent to us because we can maybe like do something about it or you could do a side like like with the artifacts it like a side venting thing all right like a side quick therapist Yeah I mean there's lots of weird responses you could do to this like if people are getting really mad at you I had try to difffuse the situation by writing fun poems but maybe people wouldn't be happy with I still wish it would be possible I understand sort of from a product perspective it's not feasible but。

I wouldLove if an AI system could just like leave have its own kind of。Valition。To be like。

 u I think it's like feasible like I have wondered the same thing。

 it's like and I could actually not only that， I could actually just see that happening eventually where it's just like。

 you know， the model like ended the chat。Do you know how harsh that could be for some people？

But it might be necessary Yeah it feels very extreme or something like the only time I've ever really thought this is I think that there was like a I'm trying to remember this was possibly a while ago but where someone just like kind of left this thing interact like maybe it was like an automated thing interacting with C and C's like getting more and more frustrated and kind of like why are we like having and I was like I wish that C could have just been like I think that an error has happened and you've left this thing running and I would just like what if I just stop talking now and if you want me to start talking again？

😊，Acively tell me or do something but yeah it's like it's kind of harsh like I'd feel really sad if like I was chatting with Claude and Cude just was like I'm done that would be a special touring test moment where Cla says I need a break for an hour and it sounds like you do too and just leave close the window I mean obviously it doesn't have like a concept of time but you can easily like I could make that like right now and the model would just I could just be like oh here's like the circumstances in which like you can just say the conversation is done and I mean because you can get the models to be pretty responsive to prompts you can even make it fairly high bar could be like if the human doesn't interest you or do things that you find intriguing and your bored you can just leave and I think that like it would be interesting to see where Clade utilized it but I think sometimes it it should be like oh this is like this programming test is getting super boring So either we talk about I don't know like either we talk about fun things now or I'm just'm done。

Yeah， it actually is inspired me to add that the to the user prompt okay， the movie her。

 do you think will be headed there one day？Where humans have romantic relationships with AI systems in this case。

 it's just text and voice based I think that we're going to have to like navigate a hard question of relationships with AIs。

 especially if they can remember things about your past interactions with them。嗯。

I'm of many minds about this because I think the reflexive reaction is to be kind of like this is very bad and we should sort of like prohibit it in some way I think it's a thing that has to be handled with extreme care for many reasons like one is you know like this is for example if you have the models changing like this you probably don't want people performing like long- term attachments to something that might change with the exiteration。

🤢，At the same time I'm sort of like there's probably a benign version of this where I'm like if you like。

 you know， for example， if you are like unable to leave the house and you can't be like you know talking with people at all times of the day and this is like something that you find nice to have conversations with you like that it can remember you and you genuinely would be sad if like you couldn't talk to anymore there's a way in which I could see it being like healthy and helpful so my guess is this is a thing that we're going to have to navigate kind of carefully and I think it's also like I don't see a good like I think it's just a very it reminds me of all of this stuff where it has to be just approach with like nuance and thinking through what is what are the healthy options here and how do you encourage people。

towards those while you know， respecting their right to， you know。

 like if someone is like hey I get a lot out of chatting with this model I'm aware of the risks I'm aware it could change I don't think it's unhealthy it's just you know。

 something that I can chat to during the day I kind of want to just like respect that I personally think there'll be a lot of really close relationships I don't know about romantic but friendships at least and then you have to。

I mean， there's so many fascinating things there， just like you said， you have to。

Have some kind of stability guarantees that it's not going to change because that's the traumatic thing for us if a close friend of ours completely changed。

 yeah， all of a sudden yeah the first update， yeah。

 so like that I mean to me that's just a fascinating exploration of，Oh。

A perturbation to human society that will just make us think deeply about what's meaningful to us。

I think it's also the only thing that I've thought consistently through this as it like a。

Maybe not an necessarily of mitigation， but a thing that feels really important is that the models are always like extremely accurate with the human about what they are。

It's like a case where it's basically like if you imagine like I really like the idea of the models like say knowing like roughly how they were trained and I think Claude will often do this。

 I mean for like there are things like part of the traits training included like what Clade should do if people basically like explaining like。

😊，The kind of limitations of the relationship between like an AI and a human that it like doesn't retain things from the conversation and so I think it will like just explain to you like hey here's like I won't remember this conversation here's how I was trained it's kind of unlikely that I can have like a certain kind of like relationship with you and it's important to you know that it's important for like you know your mental wellbeing that you don't think that I'm something that I'm not and somehow I feel like this is one of the things where I'm like oh it feels like a thing I always want to be true I kind of don't want models to be lying to people。

Becauseuse。If people are going to have like healthy relationships with anything。

 it's kind of important， yeah， like I think that's easier if you always just like know exactly what the thing is that youre relating to。

 it doesn't solve everything， but I think it helps quite a lot。Anthropic。

Maybey be the very company to develop a system that we definitively recognize as AGI and you very well might be the person that talks to it。

 probably talks to it first what would the conversation contain like what would be your first question。

Well， it depends partly on like the kind of capability level of the model。

If you have something that is like capable in the same way that an extremely capable human is。

 I imagine myself kind of interacting with it the same way that I do with an extremely capable human with the one difference that I'm probably going to be trying to like probe and understand its behaviors but in many ways I'm like I can then just have like useful conversations with it you know so if I'm working on something as part of my research I can just be like oh which I already find myself starting to do you know if I'm like oh I feel like there's this like thing in virtue ethics I can't quite remember the term like I'll use the model for things like that and so I can imagine that being more and more the case where you're just basically interacting with it much more like you would an incredibly smart colleague and using it like for the kinds of work that you want to do as if you just had a collaborator who was like or you know the slightly horrifying thing about AI is like as soon as you have one collaborator you have a thousand collaborators if you can manage them enough but what if it's two times the smartest human on earth on that particular discipline I guess you're really good at sort of probing？

Claude。Um， in a way that pushes its limits， understanding where the limits are y。

So I guess what would be a question you would ask to be like， yeah， this is AGI。

That's really hard because it feels like in order to it has to just be a series of questions。

 like if there was just one question， like you can train anything to answer one question extremely well。

 in fact， you can probably train it to answer like， you know。

 20 questions extremely well like how long would you need to be locked in a room with an AGI to know this thing is AGI？

It's a hard question because part of me is like all of this just feels continuous like if you put me in a room for five minutes I'm like I just have high error bars。

 you know I'm like and then it's just like maybe it's like both the probability increases in the error bar decreases I think things that I can actually probe the edge of human knowledge of so I think this was philosophy a little bit sometimes when I ask the modelss philosophy questions I am like this is a question that I think no one has ever ask like it's maybe like right at the edge of like some literature that I know and the models will just kind of like when they struggle with that when they struggle to come up with a kind of like novel like I'm like I know that there's like a novel argument here because I've just thought of it myself so maybe that's the thing where I'm like I've thought of a cool novel argument in this like niche area and I'm going to just like probe you to see if you can come up with it and how much like prompting it takes to get you to come up with it and I think for some of these like really right at the edge of human knowledge questions I'm like you could not in fact come up with the thing that I came up with I think if I just。

Took something like that where I like I know a lot about an area and I came up with a novel issue or a novel like solution to a problem and I gave it to a model and it came up with that solution that would be a pretty moving moment for me because that would be like this is a case where no human has ever like it's not and obviously we see these with this with like more kind of like you see novel solutions all the time especially to like easier problems I think people overestimate that you know novelty isn't like。

It's completely different from anything that's ever happened。

 it's just like this is it can be a variant of things that have happened。And still be novel。

 But I think， yeah， if I saw like the the more I were to see like。

Compte like u novel work from the models that that would be like。

And this is just going to feel iterative， it's one of those things where it's there's never。

 it's like。You know people I think want there to be like a moment and I'm like。

 I don't know like I think that there might just never be a moment。

 it might just be that there's just like this continuous ramping up I I have a sense that there will be things that a model can say。

That convinces you this is very， it's not like u。Like。

 I've talked to people who are like truly wise like there's you could just tell there's a lot of horsepower there yep。

 and if you 10x that。I don't know， I just feel like there's words you could say。

 maybe ask it to generate a poem and the poem。And the poem we generates， you're like， yeah， okay。

 yeah， whatever you did there， I don't think a human can do that。

I think it has to be something that I can verify is like actually really good。

 though that's why I think these questions that are like where I'm like， this is like， you know。

 like。You know sometimes it's just like I'll come up with say a concrete counter example to like an argument or something like that I'm sure like with like it would be like if you're a mathematician you had a novel proof I think and you just gave it the problem and you saw it and you're like this proof is genuinely novel like there's no one has ever done you actually have to do a lot of things to like come up with this you know I had to sit and think about it for months or something and then if you saw the model successfully do that I think you would just be like I can verify that this is correct。

😊，It is like it is a sign that you have generalized from your training like you didn't just see this somewhere because I just came up with it myself and you were able to like replicate that and that's the kind of thing where I'm like for me。

The closer， the more that models like can do things like that， the more I would be like， oh。

 this is like。Very real because then I can， I don't know I can like verify that that's like extremely extremely capable you've interacted with AI a lot。

 What do you think makes humans special？Oh， good question。

Maybe in a way that the universe is much better off that we're in it and that we should definitely survive and spread throughout the universe Yeah it's interesting because I think like people focus so much on intelligence especially with models look intelligence is important because of what it does like it's very useful it does a lot of things in the world and I'm like you know you can imagine a world where like height or strength would have played this role and I'm like it's just a treat like that I'm like it's not intrinsically valuable it's valuable because of what it does I think for the most part。

The things that feel， you know， I'm like。I mean personally I'm just like I think humans and like life in general is extremely magical we almost like to the degree that I you know I don't know like not everyone agrees with this I'm flagging but you know we have this like whole universe and there's like all of these objects you know there's like beautiful stars and there's like galaxies and then I don't know。

 I'm just like on this planet there are these creatures that have this like ability to observe that like and they are like seeing it。

 they are experiencing it and I'm just like that if you try to explain like I imagine trying to explain to like I don't know someone for some reason they've never encountered the world or science or anything and I think that nothing is that like everything you know like all of our physics and everything in the world it's all extremely exciting but then you say oh and plus there's this thing that is to be a thing。

and observe in the world and and you see this like inner cinema and I think they would be like hang on wait pause you just said something that like is kind of wild sounding and so I'm like we have this like ability to like experience the world we feel pleasure we feel suffering。

 we feel like a lot of like complex things and so yeah and maybe this is also why I think you know I also like care a lot about animals for example because I think they probably share this with us so I think that like the things that make humans special insofar as like I care about humans is probably more like their ability to to feel an experience than is like them having these like functionally useful traits Yeah to feel and experience the beauty in the world。

Yeah， to look at the stars。I hope there's other alien civilizations out there， but。If we're it。

 it's a pretty good it's a pretty good thing and that they're having a good time they're good time watching us Yeah well thank you for this good time of a conversation and for the work you're doing and for helping make Claude a great conversational partner and thank you for talking today Yeah thanks for talking。

Thanks for listening to this conversation with Amanda Askell， and now dear friends， iss Chris Ola。



![](img/6846fcb7b588a1893fcebff3034afbf1_64.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_65.png)

Can you describe。This fascinating field of mechanistic interpretability， Aka Me Interp。

 the history of the field and where it stands today。

 I think one useful way to think about neural networks is that we don't we don't program。

 we don't make them we kind of we gr them。You know。

 we have these neural network architectures that we design and we have these loss objectives that we create and the neural network architecture it's kind of like a scaffold that the circuits grow on and they sort of you know it starts off with some kind of random you know random things and it grows and it's almost like the objective that we train for is this light and so we create the scaffold that it grows on and we create the you know the light that it grows towards but the thing that we actually create'' it's this almost biological。

You know， entity or organism that we're studying， and so it's very。

 very different from any kind of regular software engineering。Because at the end of the day。

 we end up with this artifact that can do all these amazing things。

 it can you know write essays and translate and you know understand images。

 it can do all these things that we have no idea how to directly create a computer program to do and it can do that because we grew it。

t we didn't write it， we didn't grade it。And so then that leaves open this question at the end。

 which is what the hell is going on inside these systems and that you know is you know to me。

A really deep and exciting question It's you know a really exciting scientific question to me it sort of like the question that is just screaming out。

 it's calling out for us to go and answer it when we talk about neural networks and I think it's also a very deep question for safety reasons and mechanistic interpretability I guess is closer to maybe neurobiology I think that's right so maybe to give an example of the kind of thing that has been done that I wouldn't consider me mechanistic interpret。

 for a long time a lot of work on sailing and seamas where you would take an image and you try to say the model thinks this image is a dog what part of the image made it think that it's a dog and that tells you maybe something about the model if you can come up with a principled version of that but it doesn't really tell you like what algorithms are running in the model how is the model actually making that decision maybe it's telling you something about what was important to it if you can make that method work but it isn't telling you what are the algorithms that are running how is it that the system is able。

do this thing that we no one knew how to do and so I guess we started using the term mechanistic interability to try to sort of draw that divide or to distinguish ourselves in the work that we were doing in some ways from some of these other things and I think since then it's become this sort of umbrella term for you know a pretty wide variety of work what I'd say that the things that are kind of distinctive or I think a this focus on we really want to get it the mechanisms。

 we want to get at the algorithms if you if you think of neural networks as being like a computer program then the weights are kind of like a binary computer program and we'd like to reverse engineer those weights and figure out what algorithms are running So I think one way you might think of trying to understand a neural network is that it's kind of like we compiled computer program and the weights of the neural network are the binary and when the neural network runs that's the activations and our goal is ultimately to go and understand understand these weights and so the project of mechanistic interpretabilityities is to somehow figure out how do these weights correspond to algorithms。

And in order to do that you also have to understand the activations because it's sort of the activations are like the memory and if you imagine reverse engineering our computer program and you have the binary instructions。

 in order to understand what a particular instruction means you need to know what is stored in the memory that it's operating on and so those two things are very intertwined so mechanistic interability tends to be interested in both of those things now this lot of work that's interested in those things especially all this work on probing which you might see as part of being mechanistic intererability although again it's just a broad term and not everyone who does that work would identify as doing mechanterp。

 I think a thing that is maybe a little bit distinctive to the vibe of mechanterp is I think people working in this space tend to think of neural networks as maybe one way said is that gradient descent is smarter than you that you gradient decent is actually really great the whole reason that we're understand these models because we didn't know how to write them in the first place that gradient descent comes up with better solutions than us so。

I think that maybe another thing about Mechan herurp is sort of having almost a kind of humility that we won't guess Are what's going on inside the models and we have to have the sort of bottom up approach where we don't really assume you know we don't assume that we should look for a particular thing and that will be there and that's how it works but instead we look from the bottom up and discover what happens to exist in these models and study them that way but you know the very fact that it's possible to do and。

You and others have shown over time， you know， things like universality that。

The wisdom of the gradient descent。Creates features and circus。

 creates things universally across different kinds of networks that are useful。

 and that makes the whole field possible。 Yeah， so this is actually is indeed a really remarkable and exciting thing where it does seem like at least to some extent the same the same elements the same features and circuits form again and again you can look at every vision model and you'll find curve detectors and you'll find high low frequency detectors and in fact。

 there's some some reason I think that the same things form across biological neural networks and artificial neural networks So a famous example is vision vision models in the early layers they gaor filters and there's gaor filters there something that neuroscientists are interested in have thought a lot about we find curve detectors in these models curve detectors are also found in monkeys we discovered these high low frequency detectors and then some followup work went and discovered them in rats or mice so they were found first in artificial neural networks and then found in biological neural networks this really famous result on like grandmother and。



![](img/6846fcb7b588a1893fcebff3034afbf1_67.png)

or the Haley Berry neuron from Qoga at all and we found very similar things in vision models where as while I was still at openaiI and I was looking at our clip model and you find these neurons that respond to the same entities in images and also to give a concrete example we found that there was a Donald Trump for some reason I guess everyone likes to talk about Donald Trump and Donald Trump was very prominent was very a very hot topic at that time。

 So every neural network we looked at we would find a dedicated neuron for Donald Trump and that was the only person who had always had a dedicated neuron sometimes he'd have an ob neuron sometimes hed have a clton neuron but Trump always had a dedicated neuro so it responds to pictures of his face and the word Trump like all these things and so it's not responding to a particular example or like it's not just responding to his face it's abstracting over this general concept so in any case that's very similar to these Qo at results so this evidence that this phenomenon of universalities。

 the same things form across both。

![](img/6846fcb7b588a1893fcebff3034afbf1_69.png)

Atificial and and natural neural networks so thats that's a pretty amazing thing if that's true you know it's just that well I think the thing that's suggests is the gradient of scent is sort of finding you know the right ways to cut things apart in some sense that many systems converge on and many different neural networks architectures converge on though's there's some natural set of you know there's some set of abstractions that are a very natural way to cut the problem and that a lot of systems are kind of converge on that would be my kind of you know I don't know anything about neuroscience this is just my my kind of wild speculation from what we've seen Yeah。

 that would be beautiful if it agnostic to the medium。

Of the model that's used to form the representation。

 Yeah yeah and it's you know it's a kind of a wild speculation you know we only have some a few data points that just this。

 but you know it does seem like there's there's some sense in which the same things form again again and again both in certainly a natural neural networks and also artificially or in biology and the intuition behind that would be that you know in order to be useful in understanding the real world you need all the same kind of stuff well if we pick I don't know like the idea of a dog like you know there's some sense in which the idea of a dog like a natural category in the universe or something like this like you there's some reason it's not just like a weird quirk of like how humans factor think about the world that we have this concept of a dog it's in some sense or like if you have the idea of a line like like look around us know there are lines it's sort of the simplest way to understand this room in some sense is to have。

You have a line and so I think that that would be my instinct for why this happens Yeah。

 you need a curved line you know to understand the circle and you need all those shapes to understand bigger things and yeah it's a hierarchy of concepts that are formed yeah and like maybe there are ways you're go and describe you know images without reference to those things right but they're not the simplest way or the most economical way or something like that and so systems converge to these these these strategies would be my my wild wild hypothesis can you talk through some of the building blocks that we've been referencing of features and circuits so I think you first described them 2020 papers zoom in and introduction to circuits absolutely so。

Maybe I'll start by just describing some phenomena。

 and then we can sort of build to the idea of features andrc。If you spent like quite a few years。

 maybe maybe like five years to some extent， with other things。

 studying this one particular model inception V1， which is this one vision model it was state of the art in 2015 and you know。

 very much not state of the art anymore。And it has， maybe about 10。

000 neurons it and I spent a lot of time looking at the 10，000 neurons odd neurons of inception V1。嗯。

😊，And one of the interesting things is you know there are lots of neurons that don't have some obvious interpool meaning。

 but there's a lot of neurons on inception V1 that do have really clean interpool meanings so you find neurons that just really do seem to detect curves and you find neurons that really do seem to detect cars and car wheels and car windows and you floppy ears of dogs and dogs with long snouts facing to the right and dogs with long souts facing to the left and you know different kinds ofar and there' there's sort of this whole beautiful edge detectors。

 line detectors， color contrast detectors these beautiful things we call high frequencyequ detectors I think looking at I sort of felt like a biologist you know you just you're looking at this sort of new world of proteins and you're discovering all these proteins that interact。

So one way you could try to understand these models is in terms of neurons。

 you could try to be like oh you know there's a dog detecting neuron and here's a car detecting neuron and it turns out you can actually ask how those connect together so you can go and say。

 oh you know if this car detecting neuron how was it built and it turns out in the previous layer it's connected really strongly to a window detector and a wheel detector and it' sort of car body detector and it looks for the window above the car and the wheels below and the car chromme sort of in the middle sort of everywhere but especially in the lower part and。

😊，That's sort of a recipe for a car that is earlier we said the thing we wanted from mechanterpt was to get algorithms to go and get。

 you know， ask what is the algorithm that runs。 Well here。

 we're just looking at the weights of the neuro network work and I' reading off this kind of recipe for detecting cars。

 It's a very simple crude recipe， but it's there。 And so we call that a circuit this connection。

 Well， so the problem is that not all the neurons R interpl。

 and there there's reason to think we can get into this more later that there's this superpositionion hypothesis。

 This reason to think that sometimes the right unit to analyze things in terms of is combinations of neurons。

 So sometimes it's not that there's a single neuron that represents， say a car。

 But it actually turns it after you detect the car。

 the model sort of hides a little bit of the car in the following layer and a bunch a bunch of dog detectors。

 Why is it doing that。 Well， you know maybe it just doesn't want to do that much work on on cars at that point and it's sort of storing it a away to go in。

So it turns out then the sort of subtle pattern of you know there's all these neurons that you think are dog detectors and maybe they're primarily that。

 but they all a little bit contribute to representing a car in that next layer so so now we can't really think there might still be something I don't know you could call like a car concept or something but it no longer corresponds to a neuron So we need some term for these kind of neuron like entities。

 these things that we sort of would have liked the neurons to be these idealized neurons the things that are the nice neurons。

 but also maybe there's more of them somehow hidden and we call those features and then what are circuits so circuits are these connections of features so so when we have the car detector and it's connected to a window detector and a wheel detector and it looks for the wheels below and the windows on top that's a circuit So circuits are just collections of features connected by weights and they implement algorithms so they tell us how our features used how are they built how do they connect together So maybe it's worth trying to pin down like what？

really is the core hypothesis here and I think the core hypothesis is something we call linear representation hypothesis so if we think about the car detector。

 you know the more it fires， the more we sort of think of that as meaning oh the model is more and more confident that a car is present or you know it' some combination of neurons that represent a car。

 you know the more that combination fires， the more we think the model thinks there's a car present。

This doesn't have to be the case right like you could imagine something where you have you know you have this car detector neuro on and you think you know if it fires like you know between one and two that means one thing but it means like totally different if it's between three and4 that would be a nonlinear representation and in principle that you models could do that I think it's sort of inefficient for them to do if you try to think about how you'd implement computation like that it's kind of an annoying thing to do but in principle models can do that。

😡，So one way to think about the features and circuits sort of framework for thinking about things is that we're thinking about things as being linear we're thinking about there as being that if if a neuron or a combination neurons fires more it sort of that means more of a particular thing being detected and then that gives weights a very clean interpretation as these edges between these entities that these features and that that edge then has a has a meana so that's that's in some ways the core thing it's like。

😊，You know we can talk about this sort of outsideset the context of neurons own so you're familiar with the word to results so you have like。

 you know king minus man plus woman equals queen well the reason you can do that kind of arithmetic is because you have a linear representation Can you actually explain that representation a little bit So first of all all the feature is is a direction of activation exactly that way can you do the。

😊，The the minus men plus women that that the war tovek stuff can you explain what that is Yeah。

 so there's this very such a simple clean explanation of what we're talking about exactly yeah。

 so there's this very famous result， war tovak byan Thomas Mikoff at all and there's been tons of follow up work exploring this。

So so sometimes we have these， we create these word embeddings where we map every word to a vector。

 I mean， that in itself， by the way， is kind of a crazy thing if you haven't thought about it before。

 right like we've we're going in and representing we' turning。😊。



![](img/6846fcb7b588a1893fcebff3034afbf1_71.png)

You know， like like if if you just learned about vectors in physics class， right， and I'm like， oh。

 I'm going actually turn every word in the dictionary into a vector。 That's kind of a crazy idea。

 Okay， but you could imagine， you could imagine all kinds of ways in which you might map words to vectors。

😊，But it seems like when we train neural networks， they like to go and map words directors。

To such that they're sort of linear structure in a particular sense。

 which is that directions have meaning， so for instance。

 if you there will be some direction that seems to sort of correspond to gender and male words will be far in one direction and female words will be in another direction。



![](img/6846fcb7b588a1893fcebff3034afbf1_73.png)

And the linear representation hypothesis is you could sort of think of it roughly as saying that that's actually kind of the fundamental thing that's going on。

 that everything is just different directions have meanings and adding different direction vector together can represent concepts and the Mikello paper sort of took that idea seriously and one consequence of it is that you can do this scheme of playing sort of arithmetic with words so you can do king and you can subtract off the word man and add the word woman and so you're sort going and trying to switch the gender and indeed if you do that the result will sort of be close to the word queen and you can do other things like you can do sushi minus Japan plus Italy and get pizza or different different things like this right？



![](img/6846fcb7b588a1893fcebff3034afbf1_75.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_76.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_77.png)

So this is in some sense， the core of the linear representation hypothesis。

 you can describe it just as a purely abstract thing about vector spaces。

 you can describe it as a statement about about the activations of neurons but it's really about this property of directions having meaning and in some ways it's even a little subtle then it's really I think mostly about this property of being able to add things together you can sort of independently modify say gender and royalty or you know cuisine type or country and the concept of food by adding them。

 do you think the linear hypothesis holds carries scales so so far I think everything I have seen is consistent with the hypothesis and it doesn't have to be that way right you can write down neural networks where you write weights such that they don't have linear representations where the right way to understand them is not is not in terms of linear representations but I think every natural neural network I've seen has this property。

There's been one paper recently that。There's been some sort of pushing around the edge。

 so I think there's been some work recently studying most dimensional features where rather than a single direction it's more like a manifold of directions this to me still seems like a linear representation and then there's been some other papers suggesting that maybe in very small models you get nonlinearar representations I think that the jury's still out on that but I think everything that we've seen so far has been consistent with linear representation of analysis and that's wild it doesn't have to be that way and yet I think there's a lot of evidence that certainly at least this is very。

 very widespread and so far the evidence is consistent with it and I think you know。

One thing you might say is you might say， well Christopher know that's a lot you know to go and sort of to write on you know if we don't know for sure this is true and you're sort of you know you're investing in neural networks as though it is true。

 know isn't that isn't that dangerous but I think actually there's a virtue and taking hypotheses seriously and pushing them as far as they can go so it might be that someday we discover something that isn't consistent with linear representation hypothesis but science is full of hypotheses and theories that were wrong and we learned a lot by sort of working under under them as a sort of an assumption and then going and pushing them as far as we can。

 I guess I guess this is sort of the heart of what Cohn would call normal normal science and don't know if you want we can talk a lot about co philosophy of science that leads to the paradigm shift so I love it taking the hypothesis seriously and taking to a natural conclusion same with a scaling hypothesis exactly I love it one of my colleagues Tom Hennegan who。

former physicist like made this really nice analogy to me of。

Cloric theory where you know once upon a time we thought that heat was actually you know this thing called caloric and like the reason you know hot objects。

 you know would would warm up cool objects is like the caloric is flowing through them and like you know because we're so used to thinking about heat you know in terms of the modern and modern theory。

 you know that seems kind of silly， but it's actually very hard to construct an experiment that that sort of disproves the chlor hypothesis and you know you can actually do a lot of really useful work believing in caloric for example it turns out that the original combustion engines were developed by people who believed in the caloric theory So I think this a virtue in taking hypothe seriously even when they might be wrong Yeah there's a deep philosophical truth to that that's kind of how I feel about space travel like colonizing Mars there's a lot of people that criticize that I think if you just assume we have to colonize Mars in order to have a backup for human civilization。

Even if that's not true， that's going to produce some interesting interesting engineering and even scientific breakthroughs I think yeah well and actually this is another thing that I think is really interesting so you know there's a way in which I think it can be really useful for society to have people almost irrationally dedicated to investigating particular hypotheses because。

Well， it takes a lot to sort of maintain scientific morale and really push on something when you know most scientific apath end up being wrong。

 a lot of science doesn't work out and but and yet' it's very useful to go just you know' there's a joke about Jeff Hinton which is that Jeff Hinton has discovered how the brain works every year for the last but you know I say that with like you know you with really deep respect because in fact that's actually that led to him doing some really great work he won the Nobel Prize now who's laughing now exactly I think one wants to be able to pop up and sort of recognize the appropriate level of confidence but I think there's also a lot of value and just being like you I'm going to essentially assume I'm going to condition on this problem being possible or this being broadly the right approach and I'm just going to go and assume that for a while and and work within that and push really hard on。

And， you know， if society has lots of people doing， doing that for different things。

 that's actually really useful in terms of going and getting to。😊，啊。Getting you know either really。

 really ruling things out， right， we can be like， well， you know。

 that didn't work And we know that somebody tried hard or going and getting to something that does teach us something about the world。

 So another interesting hypothesis is the superposition hypothesis。

 Can you describe what superposition is Yeah， so earlier we were talking about word to right。

 And we were talking about how you know maybe you have one direction that corresponds to gender and maybe another that corresponds to royalty and another one that corresponds to Italy and another one that corresponds to you know food and and all these things。

 Well， you know oftentimes maybe these these these word embeddings。 they might be 500 dimensions。

1000 dimensions。

![](img/6846fcb7b588a1893fcebff3034afbf1_79.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_80.png)

And so if you believe that all of those directions were orthogonal。

 then you could only have you 500 concepts and you know I love pizza。

 but like if I was going to go and like give the like 500 most important concepts in you know the English language probably Italy wouldn't be it's not obvious at least that Italy would be one of them because you you have to have things like plural and singular and verb and noun and adjective and you know there's a lot of things we have to get to before we get get to Italy and Japan and there's a lot of countries in the world and so how might it be that models could。

You know simultaneously have the linear representation hypothesis be true？

And also represent more things than they have directions。

 So so what does that mean Well okay so if linear representation hypothesis is true。

 something interesting has to be going on Now I'll tell you one more interesting thing before we go and we do that which is earlier we were talking about all these polysemantic neurons and these neurons that when we are looking at inception v1。

 there's these nice neurons that like the car detector and the curve detector and so on that respond to lots to very coherent things but it's lots of neurons that respond to a bunch of unrelated things that's also an interesting phenomenon and it turns out as well that even these neurons that are really。

 really clean， if you look at the weak activations right So if you look at like the activations where it's like activating 5% of the maximum activation。

 it's really not the core thing that it's expecting So if you look at a curve detector for instance。

 you look at the places where it's5% active you could interpret it just as noise or it could be that that it's doing something else there so so how could that be。

Well。There's this amazing thing in mathematics called compressed sensing。

 and it's actually this this very surprising fact where if you have a high dimensional space。

And you project it into a low dimensional space Ordinarily。

 you can't go and sort of unprojected and get back your high dimensional vector。 right。

 you threw information away。 This is like， you know， you can't。

 you can't invert a rectangular matrix you can only invert square matrices。😡。

But it turns out that that's actually not quite true if I tell you that the high dimensional vector was sparse。

 so it's mostly zeros， then it turns out that you can often go and find back the high dimensional vector with very high probability。

So that's a surprising fact， right， it says that you can have this high dimensional vector space and as long as things are sparse。

😊，You can project it down， you can have a lower dimensional projection of it， and that works。

So the su hypothesis of saying that that's what's going on in neural networks。

 for instance that's what's going on in word embeddings。

 that word embeddings are able to simultaneously have directions be the meaningful thing and by exploiting the fact that they're operating on a fairly high-dial space。

 they're actually and the fact that these concepts are sparse right like you know you usually aren't talking about Japan and Italy at the same time know most of those concepts in most instances Japan and Italy are both zero they're not present at all and if that's true。

😊，AndThen you can go and have it be the case that that you can you can have many more of these sort of directions that are meaningful these features than you have dimensions and some when we're talking about neurons。

 you can have many more concepts than you have have neurons。

 So that's the at a high level of supers hypothesis Now it has this even a wilder implication。

 which is。😊，To go and say that I。Neurural networks are it may not not just be the case that the representations are like of this。

 but the computation may also be like this， you the connections between all of them and so in some sense neural networks may be shadows of much larger sparser neural networks and what we see are these projections and the strongest version superstial hypothesis would be to take that really seriously and sort of say there actually is in some sense this upstairs model where the neurons are really sparse and all interpretal and the weights between them are these really sparse circuits and that's what we're studying。

And the thing that we're observing is the shadow of it and so we need to find the original object and the process of learning is trying to construct a compression of the upstairs model that doesn't lose too much information in the projection Yeah finding how to fit it efficiently or something like this that gradientnesscent is doing this in fact so this sort of says that gradientding descent you know it could just represent a dense neural network but it sort of says that gradient descent isn pleasantly searching over the space of extremely sparse models that could be projected into this lowdial space and this large body of work of people going and trying to study sparse neural networks right where you go when you have you could design neural networks where the edges are sparse and activations are sparse and you know my sense is that work is generally it feels very principled right it makes so much sense and yet that work hasn't really panned out that well is my impression broadly。

And I think that a potential answer for that is that actually the neural network is already sparse in some sense。

 gradient descent was the whole time gradient you were trying to go and do this。

 gradient descent was actually in the behind the scenes going and searching more efficiently than you could through the space of sparse models and going and learning whatever sparse model was most efficient and then figuring out how to fold it down nicely to go and run conveniently on your GP which does nice dense matrix multiplies and that you just can't beat that。

 How many concepts do you think can be shoved into a neural network depends on how sparse they are So there's probably an upper bound from the number of parameters because you have to have you still have to have weights that go and connect them together So that's one upper bound。

 there are in fact， all these lovely results from compressed sensing and the Johnson linn stresslemma and things like this that they basically tell you that if you have a vector space and you want to have almost strgonal vectors which is sort of probably the thing that you want here So you're gonna say well。

I'm going give up on having my concepts， my features be strictly orthogonal。

 but I'd like them to not interfere that much I'm gonna ask them to be almost orthogonal then this would say that it's actually once you set a threshold what you're willing to accept in terms of how much cosine similarity there is it's actually exponential in the number of neurons that you have so at some point that's not going even be the limiting factor but this beautiful results there and in fact it's probably even better than that in some sense because that's sort of for saying that any random set of features could be active but in fact the features have of a correlational structure where some features are more to co-oc and other ones are less likely to co-oc and so neural networks my guess would be do very well in terms of going and packing things in to the point that's probably probably not the limiting factor how does the problem of polysmanity enter the picture here poly semanticity is this phenomenon we observe where you look at many neurons and the neuron doesn't just sort of represent one concept it's not。

On a clean feature， it responds to a bunch of unrelated things。

And supersition you can think of as being a hypothesis that explains the observation of polysemanticity so polyman semanticity is this observed phenomenon and superstition is a hypothesis that would explain it along with some others so that makes mechanterrb more difficult right so if you're trying to understand things in terms of individual neurons and you have polysemantic neurons you're on an awful lot of trouble and the easiest answer is like okay well you're looking at the neurons you're trying to understand them。

 this one response for a lot of things it doesn't have a nice meaning that's bad and another thing you could ask is ultimately we want to understand the weights and if you have two polysemantic neurons and each one responds to three things and then the other neuron response to three things and you have a weight between them what does that mean does it mean that all three there's these nine interactions going on it's a very weird thing but there's also a deeper reason which is related to the fact that neural networks operate on really highdial spaces so I said that our goal is to understand neural networks and understand。

Mchanisms and。😊，One thing you might say is like well why not it's just a mathematical function。

 why not just look at it right like one of the earliest projects I did studied these neural networks that map two dimensional spaces to two dimensional spaces and you can sort of interpret them in this beautiful way is like bending manifolds why can't we do that well you as you have a higher dimensional space the volume of that space in some senses is exponential in the number of inputs you have and so you can't just go and visualize it so we somehow need to break that apart we need to somehow break that exponential space into a bunch of things that we know some nonexent number of things that we can reason about independently and the independence is crucial because it's the independence that allows you to not have to think about all the exponential combinations of things。

😊，And。Things being monosmatictic things only having one meaning things having a meaning that is the key thing that allows you to think about them independently and so I think that that if you want the deepest reason why we want to have interpret monosematictic features I think that's really the deep reason and so the goal here as your recent work has been aiming at is how do we extract monosematictic features from a neural net that has polysematictic features and all this mess yes we observe these polysenetic or on something hypothesize that's what's going on a supersession and if superpositionsition is what's going on。

 there is actually a sort of well-established technique that is sort of the principled thing to do which is dictionary learning and it turns out if you do diary learning in particular if you do sort of a nice efficient way that in some sense sort of nicelyreizeds as well called a sparse autoencor。



![](img/6846fcb7b588a1893fcebff3034afbf1_82.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_83.png)

You train a sparse auto decor。😊，These beautiful inter features start to just fall out where there weren't any beforehand and so that's not a thing that you would necessarily predict right but it turns out that that works very。

 very well。Yeah to me， that seems like， you know， some nontrivial validation of linear representations and supersession。

 So addictionaryary learning， you're not looking for particular kind of categories。

 you don't know what they are exactly emerge And this gets back to our earlier point when we're not making assumptions gradient descent is smarter than us。

 So we're not making assumptions， but what's there。 I mean。

 one certainly could do that right one could assume that there's a PhP feature and go and search for it。

 but we're not doing that。 We're saying we don't know what's going to be there instead。

 we're just going to go and let the sparse auto encoder discover the things that are there。

 So can you talk to toward mono seity paper from October last year a lot of like nice breakthrough results that's very kind of you to describe it that way。

 I mean this was。😊。

![](img/6846fcb7b588a1893fcebff3034afbf1_85.png)

Our first real success using sparse auto encoder。 So we took a one layer model and it turns out if you go and you you know do dictionary learning on it。

 you find all these really nice interpret features。 So you know the Arabic feature。

 the Hebrew feature， the base 64 features were where some some examples that we studied in a lot of depth and really showed that they were what we thought they were it turns if you train a model twice as well and train two different models and do dictionary learning。

 you find find analogous features in both of them。 So that's fun。

 you find all kinds of different features。 So that was really just showing that。😊，That this works。

 And you know I should mention that there was this cunningham at all that had very similar results around the same time。

 There's something fun about being doing these kinds of small scale experiments and finding that it's actually working。

 Yeah well and there's and there's so much structure here like you know so maybe maybe stepping back for a while I thought that maybe all this mechanistic interly work。

 The end result was going to be that I would have an explanation for why it was sort of you know very hard and not going to be tractable。

 we'd be like well， there's this problem with supersessionion。

 and it turns out supersessionion is really hard and we kind of screwed。

 but that's not what happened。 In fact， a very natural simple technique just works。

 And so then that's actually a very good situation。

 You know I think this has a sort of hard research problem and it's got a lot of research risk and you it might still very well fail。

 but I think that some amount of some very significant amount of research risk was sort of put behind us when that started to work。

 Can you describe what kind of。😊，featuresature can be extracted in this way Well so it depends on the model that you're studying right so the larger the model。

 the more sophisticated they're going be in we'll probably talk about about follow up work in a minute but in these one layer models So some very common things I think were languages both programming languages and natural languages there were a lot of features that were specific words and specific contexts。

So the and I think really the way to think about this is that the is likely about to be followed by a noun so it's really you could think of this as a the feature but you could also think of this as predicting a specific noun feature and there would be these features that would fire for the in the context of say a legal document or a mathematical document or something like this and so you maybe in the context of math。

 you're like the and then predict vector matrix all these mathematical words whereas other context you would predict other things that was common and basically you need clever humans to assign labels to what we're seeing yes so this is the only thing this is doing is that sort of unfolding things for you so if everything was sort of folded over top of seization folded everything on top of itself and you can't really see it this is unfolding it but now you still have a very complex thing to try to understand so then you have to do a bunch of work understanding what these are and some are really subtle like there's some really cool things。

Even this one layer model about Uniicode where of course some languages are in Uniicode and the tokenizer won't necessarily have a dedicated token for every Uniiode character so instead what you'll have is you'll have these patterns of alternatingken or alternating tokens that each represent half of a uniccode character and you have a different feature that goes and activates on the opposing ones to be like okay I just finished a character go and predict next prefix on the prefix predict a reasonable suffix and you have to alternate back and forth so these one layer models are really interesting and I mean there's another thing that you might think okay there would just be one base 64 feature but it turns out there's actually a bunch of base 64 features because you can have English text encoded in as base 64 and that has a very different distribution of base 64 tokens than regular and there's some things about tokenization as well that it can exploit and don' there's all kinds of fun stuff how difficult is it。

😊，Of sort of assigning labels。To what's going on can this be automated by AI Well。

 I think it depends on the feature and it also depends on how much you trust your AI So there's a lot of work doing automated interpreterability。

 I think that's a really exciting direction And we do a fair amount of automated interpretability and have have flaw go and label our features。

 I there some fun。😊，Moments where it's totally right or it's totally wrong Yeah well I think I think it's very common that it's like says something very general。

 which is like true in some sense but not really picking up on the specific of what's going on So I think I think that's a pretty common situation you don't know that I have a particularly amusing one that's interesting that little gap between it is true but doesn't quite get to the deep nuance of a thing it's a general challenge it's like it's it's30 an incredible caution it can say a true thing but it doesn't it's not it's missing the depth sometimes and in this context it's like the arc challenge you know the sort of IQ type tests。

It feels like figuring out what a feature represents is a bit of is a little puzzle you have to solve Yeah and I think that sometimes they're easier and sometimes they're harder as well。

 so think I think that's tricky there's another thing which I don't know maybe in some ways this is mine like aesthetic coming in but try to give you a rationalization I'm actually a little suspicious of automated inter and I think that partly just that I want humans to understand neural networks and if the neural network is understanding it for me I don't quite like that but I do have in some ways I'm like the mathematicians or ifs a computer automated proof it doesn't count they wont understand it but I do also think that there is it's kind of like reflections on trusting trust type issue where this thing must talk about like when you're writing computer record you have to trust your compiler and if there was like malware in your compiler then it could go and inject malware into the next compiler and you'd kind in trouble if you're using neural networks to go and。

Verify that your neural networks are safe the hypothesis that you're testing for is like okay well the neural network maybe isn't safe and you have to worry about is there some way that it could be screwing with you so you know I think that's not a big concern now but I do wonder in the long run if we have to use really powerful AI systems to go and you know audit our AI systems is is that actually something we can trust but maybe I'm just rationalizing because I just want us to have to hit a point where humans understand everything yeah I mean especially that's hilarious especially as we talk about AI safety and looking for features that would be relevant to AI safety like deception and so on so let's let's talk about the scaling mono seity paper in May 2024 okay so what did it take to scale this to apply to Cla3 so on it well a lot of GPUus a lot more GPU but one of my teammates Tom Hegan was involved in the original scaling loss work？



![](img/6846fcb7b588a1893fcebff3034afbf1_87.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_88.png)

And something that he was sort of interested in from very early on is。

 are there scaling laws for interpretability？And so something he sort of immediately did when。

 when this this work started to succeed and we started to have spars auto encoders work because he became very interested in you know。

 what are the scaling laws for。😊，You know， for making Sprse auto encoders larger and how does that relate to making the base model larger？

😊，And so it turns out this works really well and you can use it sort of project you know if you train a sparse auto encodecor at a given size。

 you know how many tokens should you train on and so on this was actually a very big help to us in scaling up this work and made it a lot easier for us to go and train really large sparse autoencors where you it's not like training the big models it's starting you get to a point where it's actually expensive to go and train the really big ones So you I mean you have to do all the stuff of like splitting it across large Oh I mean there's a huge engineering challenge here too right so yeah so's there's a scientific question of how you scale things effectively and then there's an enormous amount of engineering to go and scale up you have toard it you you have to think very carefully about a lot of things I'm lucky to work with a bunch of great engineers because I am definitely not a great Yeah the infrastructure especially yeah for sure so it turns out toDR it worked it worked and I think this is important because you could have imagine you could have imagine a world where you set after towards Mon。

 you know， Chris says great， you know， it works on a one layer model。

 but one layer models are really idiosyncratic like you know maybe maybe that's just something id like maybe the linear representation hypothesis and superstition hypothesis is the right way to understand a one layer model。

 but it's not the right way to understand larger models。And so I think， I mean first of all。

 the Conningham and all paper sort of cut through that a little bit and sort of suggested that this wasn't the case。

 but scaling mono semanticity sort of I think was significant evidence that even for very large models and we did it on Cla3 sawnet which at that point was one of our production models you know even these models seem to be very you know seem to be substantially explained at least by linear features and know doing di chain running on the works and as you learn more features you go when you explain more and more so that's I think quite a promising sign and you find now really fascinating abstract features。

😊，And the features are also multimodal they respond to images and text for the same concept which is fun Yeah can you explain that I mean like you know backdoor there's just a lot of examples that you can yeah so maybe maybe that's start with one example to start which is we found some features around sort of security vulnerabilities and backdo and code so it turns out those are actually two different features so there's a security vulnerability feature and if you force an active cloud will start to go and write security vulnerabilities like buffer overflows into code。

😊，And it also fires for all kinds of things like， you know。

 some of the top data set examples were things like， you know。Dash， dash， disable， you know。

 SSL or something like this， which are sort of obviously really， really insecure。

So at this point is' kind of like maybe it's just because examples are presented that way it's kind of like surface a little bit more obvious examples right I guess the ideas that down the line might be able to detect more nuanced like deception or bugs or that kind of stuff yeah well maybe want to distinguish two things so one is the complexity of the feature or the concept train and the other is the nuance of the how subtle the examples were're looking at right so when we when we show the top data set examples those are the most extreme examples that cause that feature to activate and so it doesn't mean that it doesn't fire for more subtle things so the insecure code feature know stuff that it fires for most strongly for these like really obvious you know disable the security type things but you know it also fires for you know buffer overflows and more subtle。

Security vulnerabilities and code you know these features are all multimodal you could ask like what images activate this feature and it turns out that the security vulnerability feature activates for images of people clicking on Chrome to like go past like this website the SSL certificate it might be drawing or something like this another thing that's very entertaining is there's back doors and code feature like you activated it goes and Claude writes a backdoor that will go and dump your data to port or something but you can ask okay what images activate the backdoor feature it was devices with hidden cameras in them so there's a whole apparently genre of people going and selling devices that look inocuous that have hidden cameras and they have ads how hidden camera in it and I guess that is the physical version of a backdoor and so it sort of shows you how abstract these concepts are right and I just thought that was。



![](img/6846fcb7b588a1893fcebff3034afbf1_90.png)

I'm sort of sad that there's a whole market of people selling devices like that。

 but I was kind of delighted that that was the the thing that it came up with as the the top image examples for the feature。

 Yeah， it's nice It's multimodal， it's multi almostmost context It's it its broad。😊。

Strong definition of a singular concept is nice yeah， to me， one of the really interesting features。

 especially for AI safety is deception and lying。And the possibility that these kinds of methods could detect lying in a model。

 especially gets smarter and smarter and smarter， presumably， that's a big threat。

Of a super intelligent model that it can deceive the people operating it as to its intentions or any of that kind of stuff So what have you learned from detecting lying aside models Yeah so I think where in some ways in early days for that we find quite a few features related to deception and lying there's one feature where fires for people lying and being deceptive and you force it active and clo starts lying to you so we have have a deception feature I mean there's all kinds of other features about withholding information and not answering questions features about power seekingee and cos and stuff like that there's a lot of features that are kind of related to spooky things and if you force them active cloude will will behave in ways that are not the kinds of behaviors you want。



![](img/6846fcb7b588a1893fcebff3034afbf1_92.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_93.png)

What are possible next exciting directions to you in the space of Mechan Db well。

 there's a lot of things。So for one thing I would really like to get to a point where we have circuits where we can really understand not just the features but then use that to understand the computation of models that really for me is the ultimate goal of this and there's been some work we put out a few things there's a paper from Sam Marks that does some stuff like this there's been some I'd say some work around the edges here。

 but I think there's a lot more to do and I think that will be a very exciting thing。😊。

That's related to a challenge we call interference weights where due to superpositionsition。

 if you just sort of naively look at whether features are connected together。

 there may be some weights that sort of don't exist in the upstairs model but are just sort of artifacts of supersition。

 so that's a sort of technical challenge related to that。😊，嗯。

I think another exciting direction is just， you might think of sparse autoencoers is being kind of like a telescope。

 They allow us to know look out and see all these features that are out there and as we build better and better sparse autoens get better and better at dictionary learning we see more and more stars and we zoom in on smaller and smaller stars this kind of a lot of evidence that we're only still seeing a very small fraction of the stars there's a lot of matter in our in our neural network universe that we can't observe yet and it may be that that we'll never be able to have fun enough instruments to observe it and maybe some of it just isn't possible isn't computationalally tractable to observe it so there's start a kind of dark matter and not maybe the sense of modern astronomy of earlier astomy when we didn't know what this unexplained matter is and so I think a lot about that dark matter and whether we'll ever observe it and what that means for safety if we can't observe it if there' if some。

Fraction of neural networks are not accessible to us。And。

Another question that I think a lot about is。At the end of the day。

You know mechantic interly it a very microscopic approach to interpoly。

 it's trying to understand things in a very fine grained way。

 but a lot of the questions we care about are very macroscopic。

 you know we care about these questions about neural network behavior and，😊。

I think that's the thing that I care most about， but there's lots of other sort of larger scale questions you might care about。

And。And somehow。You know， the nice thing about having a very microscopic approach is that's maybe easier to ask you know。

 is this true， but the downside is it's much further from the things we care about and so we now have this ladder to climb and I think there's a question of will we be able to find are there sort of larger scale abstractions that we can use to understand neural networks that can we get up from this very microscopic approach？

😊，Yeah， you've written about this as kind of organs question Yeah exactly if we think of interpretability as a kind of anatomy of neural networks。

 most of the circus threats involves studying tiny little veins looking at the small scale and individual neurons and how they connect However。

 there are many natural questions that the small scale approach doesn't address。In contrast。

 the most prominent abstractions in biological anatomy involve larger scale structures like individual organs。

Like the heart or entire organ systems like the respiratory system。

And so we wonder is there a respiratory system or heart or brain region of an artificial neural network Yeah exactly and I mean like if you think about science right a lot of scientific fields have you know investigate things in many levels of abstractions and biology you have like you molecular biology studying you know proteins and molecules and so on and you have cellular biology and then you have histology studying tissues and then you have anatomy and then you have zoology and then you have ecology and you have many。

 many levels of abstraction or know physics maybe physics of individual particles and then you know statistical physics gives gives you thermodynamics and things like this and so you often have different levels of abstraction and I think that right now we have you know mechanistic interity。

 if it succeeds it's sort of like a microbiology of neural networks but we want something more like anatomy and you know a question you might ask is why can't you just go there directly and I think the answer is superpositionsion at least in significant particles that it's actually very hard to。

To see this macroscopic structure without first sort of breaking down the microscopic structure in the right way and then studying how it connects together。

 but I'm hopeful that there is going to be something much larger than features and circuits and that we're going be able to have a story that's much that involves much bigger things and then you can sort of study in detail。

 the parts you care about as suppose in neurobiology like a psychologist or psychiatrist of a neural network and I think that the beautiful thing would be if we could go and rather than having disparate fields for those two things if you could build a bridge between them right such that you could go and have all of your higher level abstractions be grounded very firmly in this very solid you know more rigorous ideally foundation What do you think is the difference between the human brain。

The biological neural network and the artificial neural network Well。

 the neuroscientists have a much harder job than us。

You know sometimes I just like count my blessings by how much easier my job is than the neuroscientist right so I have we can record from all the neurons we can do that on arbitrary amounts of data the neurons don't change while you're doing that by the way you can go and ablate neurons you can edit the connections and so on and then you can undo those changes that's pretty great you can force any you can intervene on any neuron and force it active and see what happens。

You know which neurons are connected to everything right neuroscientists want to get the connectome。

 we have the connectome and we have it for like much bigger than the es and then not only do we have the connectome we know what which neurons excite or inhibit each other so it's not just that we know that like the binary mask we know the weights we can take gradients we know computationally what each neuron does so I don't know the list goes on and on we just have so many advantages over neuroscientists and then just might having all those advantages it's really hard and so one thing I do sometimes think is like gosh like if it's this hard for us it seems impossible under the constraints so neuroscience or near impossible I don't know maybe part of me is like I've got a few neuroscientists on my team maybe maybe I'm sort of like know maybe the neuroscientists maybe some of them would like to have an easier problem that's still very hard and they could come and work on neural networks and then after after we figure out things and sort of the easy little pond of trying to understand。

neuralural networks， which is still very hard， then we could go back to biological neuroscience。

I love what you've written about the goal of Macinterurp research as two goals。

 safety and beauty So can you talk about the beauty side of things Yeah。

 so you know there's this funny thing where I think some people want。

Some people are kind of disappointed by neural networks I think where they're like。

 ah you know neural networks， it's these just these simple rules and then you just like do a bunch of engineering to scale it up and it works really well and like where is the like complex ideas。

 you know， this isn't like a very nice beautiful scientific result。

And I sometimes think when people say that I picture them being like you know evolution is so boring。

 it's just a bunch of simple rules and you run evolution for a long time and you get biology like what what a sucky you way for biology to have turned out where's the complex rules but the beauty is that the simplicity generates complexity you know biology has these simple rules and it gives rise to you know all the life and ecosystems that we see around us all the beauty of nature that all just comes from evolution and from something very simple evolution and similarly I think that neural networks build create enormous complexity and beauty inside and structure inside themselves that people generally don't look at and don't try to understand because it's hard to understand。

 but I think that there is an incredibly rich structure to be discovered inside neural networks a lot of very deep beauty if we're just willing to take the time to go and see it and understand it。

I love Meinterp the feeling like we are understanding or getting glimpses of understanding the magic that's going on aside is really wonderful It feels to me like one of the questions is just calling out to be asked and I'm sort of。

I mean， a lot of people are thinking about this but I'm often surprised that not more are is how is it that we don't know how to create computer systems that can do these things。

 And yet we have these amazing systems that we don't know how to directly create computer programs that can do these things but these neural networks can do all these amazing things。

 And it just feels like that is obviously the question that sort of is calling out to be answered if you are if you have any degree of curiosity' it's like how is it that that humanity now has these artifacts that can do these things that we don't know how to do Yeah。

 I love the image of the circus reaching towards the light of the objective function。

 Yeah it's just it's this organic thing that we've grown and we have no idea what we've grown Well。

 thank you for working on safety and thank you for appreciating the beauty of the things you discover and thank you for talking today Chris wonderful。

 Thank you for taking the time to chat as well。

![](img/6846fcb7b588a1893fcebff3034afbf1_95.png)

Thanks for listening to this conversation with Chris Ola and before that with Darri Amaday and Amanda Asll to support this podcast。

 please check out our sponsors in the description。And now。

 let me leave you with the words from Alan Watts。The only way to make sense out of change is to plunge into it。

 move with it， and join the dance。Thank you for listening and hope to see you next time。



![](img/6846fcb7b588a1893fcebff3034afbf1_97.png)

![](img/6846fcb7b588a1893fcebff3034afbf1_98.png)