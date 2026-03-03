# 【人工智能访谈会 2023】斯坦福大学—中英字幕 p22 p21 Stanford Webinar - Building Safe and Reliable Autonomous Systems -BV14XB8YYEb1_p22-

![](img/f17d22bda88905ff86e38a00a489ca60_0.png)

![](img/f17d22bda88905ff86e38a00a489ca60_1.png)

I want to introduce Dr。 Corso， he's a postdoctoral researcher here in the aeronautics and Astronautics Department at Stanford University。

 he's in particular in the Stanford Intelligence Systems Laboratory under Michael Kokenurffer。

 that is the lab here that has the best pronounceable acronym which is sizzle。

He is also the executive director of the Stanford Center for AI Safety。

 which is broadly the topic we're going to be talking about today。

His research is focused on the use of algorithmic decision- making for safety critical applications。

 emphasizing the creation of robust， reliable autonomous systems。

 and this is a really important topic and obviously it's been important for a long time and that's something that Anthony and I will talk about a little bit。

 but it's also something that's come to greater prominence and we are working with Anthony to create a seminar that we'll be offering in the last week of July on this particular topic we'll talk a little bit more about that at the end of the presentation。

 but if you're interested in learning more about it。

 there is you should see a little button right there on your screen that you can click and that will take you to the course page which has a rough description of what that will look like。

All right， with that， again， I want to remind you at any time， feel free to ask your questions。

 but I'm going to just kick it off Anthony again， thank you for joining us here today。

 and I think probably the place to start is if you could just introduce yourself a little bit more by talking about your research。

Yeah thanks Pax and it's great to be here thank you all for choosing to spend 45 minutes with us talking about this important topic。

 so I did my master's and PhD in the aeronautics and Astronautics department。😊。

Here at Stanford and a lot of the research that I did was thinking about the ways in which we can use AI or algorithmic decision making to improve both the safety and efficiency of transportation systems so something like a million people every year die in car accidents and so you know if we can improve the safety of things like driving cars then we can save a lot of lives and so the topic that I mostly studied was around the use of AI systems to perform these tasks safely but then the question naturally arises how did you check whether or not you've built a very safe systems so I did my dissertation work on developing algorithms that allow you to stress tests and ensure the safety of these really high stakes systems and since then I've carried on as a postdoc and have continued to think about kind of the areas in which we use AI systems that influence and effect a lot of people and we really need to make sure that they are robust。

Lable before deploying them。That's great so Anthony I think maybe we can take a step back so there are kind of a couple there are a couple things there we already have a good question just about some of the terminology about what means for a system to be robust but I think maybe we start is can we can we dig a little bit deeper on autonomous systems so you primarily worked with systems in transportation so cars。

 airplanes， drones， those kinds of things could you talk a little bit more about autonomous systems and what you're thinking of what that broadly covers and what the risks are involved with those you've already touched on it in terms of car accidents。

 but can you build on that a little bit。Yeah， absolutely。

 so I think of autonomous systems is really any system that's going to perform a task that historically has been done by a human so this can be driving cars is a prime example and autonomous systems although we've had autonomous systems for a very long time people think are becoming much more aware of them with the advent of AI and machine learning。

 which are techniques that allow computer systems to learn from data and basically enable us to process information in real time and enable this higher level of autonomy we've been seeing over the past couple of years the problem is。

 however， that a lot of these technologies although they are absolutely amazing and enable us to do incredible things often fail in kind of unexpected ways they tend to be a little bit more brittle than say humans are so they may work in a very controlled say laboratory setting but as soon as you deploy these systems and the environment changes ever so slightly you can begin running into problems and this is of course very dangerous if you're deploy。

These systems in a domain like driving where people's lives serves。

Could you I actually have something I want to circle back onto about safety。

 but could we elaborate on the brittleness of some of these systems。

 can you build on what that means， so it' at the core it just means they fail in ways that humans might not or is it that they fail differently than humans or they're more likely to fail or they just don't they don't generalize。

 I guess would be the term maybe the way humans might。Yeah， so it can be a little bit of both。

 I'll start with maybe an example。 So you know folks showed that， for example。

 you can maybe if you collect data from you know a certain geographic area。

 let's say for maybe we're building a system that can identify pedestrians on the if you collect a bunch of data from a certain geographic area and then you train a machine learning model to detect pedestrians。

 you're likely to build a very reliable model that can detect pedestrianly well。

 The problem is if you then try to deploy that model and say a different geographic domain where things are slightly different。

 So maybe the crosswalk looks a little bit different or people tend to wear different clothes or something like that。

 and all of a sudden what we see is that these machine learning model performances can drop pretty dramatically。

 even though the differences in kind of the environment are quite quite and humans don't really have this problem。

 we're able to generalize fairly well across a variety of factors。😊。

That's great and and thank you again， I want to remind you if you have questions。

 feel free to post them， we're already getting a ton of those。

 but I want to build on this maybe a little bit more and circle back to something before we kind of move on is when you initially said it part of what got you interested is not to ensure the safety of AI systems but the way in which AI systems or autonomous systems can improve our safety right so could you elaborate on that that kind of the flip side。

 so it's not just that you're trying to ensure that systems are safer but it's also the case that maybe AI systems can do things more safely than humans potentially in certain domains could you elaborate on that。

Absolutely， so like one of the reasons I'm so excited about AI in general is this possibility that we can have systems that perform。

 for example， much， much better than a human at a variety of tasks you really care about So I think a great example of this would be healthcare So if you could have an AI system that was maybe even just as good as as the world's best doctor you could deploy that system very widely across the world riding healthcare access to people who wouldn't otherwise get it or likewise flying aircraft or flying or driving vehicles these are things that although humans do fairly well。

 we can really improve the safety of and that can be really beneficial for everyone。 but of course。

 as soon as you start thinking in those terms， you you have to be careful because what we're talking about with AI systems is it allows it to allows us to scale these systems out to like a ton of people and so then any risk that's inherent in the system is now a risk affecting many。

 many， many more people and so we have to be extremely careful before actually deploying these systems out into the world。

So that's really interesting so part of it part of what the particular challenge of these systems is how scalable theyre they are right so if I make a mistake as a driver I'm a single driver and that potentially has local consequences but it's not like I am driving everyone's car whereas what you're proposing is or what people are trying to achieve is a system that will be deployed across all the United States all of the world and so and actually along those lines another issue that another sort of problem that AI systems tend to face is that it can be fairly susceptible to what we call adversarial attack or basically like intentional manipulation by people and so you can do there's been some research where people can for example will print out a sticker that just kind of looks like maybe a sticker you would see out in the world posted on a stop sign it can make a machine learning system think that that stop sign is now a speed limit 45 sign and so this could be extremely dangerous and like you said it's not just going to affect that one system but if all the cars on the road or using。

the same algorithm， then they can all be influenced by this one sort of attack。

 and so that's one of the reasons why we need to be extra careful with sort of testing and verification of these systems。

So I do I want to there's one particular question I think is maybe before we kind of move on is there's a question about if there are additional risks for say big trucks or little you or different kinds of vehicles on the road。

 and so could you just talk a little bit about when you're thinking about deploying these systems mean？

How how generalizable are these systems across the class of vehicle those kinds of things I mean what what are some of those considerations again。

 we're probably I guess here we're talking about cars but it could apply to airplanes right I mean can the same system go in a 747 versus Asssna and what are some of those considerations Yeah so I think of AI safety is sort of like you know you have to multiply sort of like the likelihood of a failure event occurring times the magnitude of the consequences of that failure event and together that gives you sort of like your overall risk so if you think about a system like aircraft which has an extremely high consequence if something goes wrong because know very bad things can happen if you do something wrong on an aircraft so you need a correspondingly extremely small probability of failure So the FAA for example tries to ensure that their systems fail no more than one in about a billion hours of flight time。

You know extremely extremely safe as we've all come to expect now on the flip side of that。

 if you're thinking about you know deploying a machine learning model to say for example。

 serve ads to users as they come to your website the the risk of making a mistake there is relatively low if you serve someone the wrong ad perhaps they just don't on the thing that you sell them and so the risk is kind of low so we can tolerate much higher rates of failure and domains like that and I think that there's basically a whole spectrum here now everyone you know once their machine learning model or A system to be as reliable as possible but it becomes all the more important as those consequences get higher and so to the question around。

You know， variety of road vehicles and things like that。

 we have to think about you know what is the domain in which they're going to be operated and so for example are they going to be driving downtown city streets in New York or are they going to be driving an open pit mine where there aren't any other people around and so the context really matters when it comes to safety。

That's great and we're getting a lot of really good good questions。

 but I want to maybe before getting to some of those I do want to I want to address something that's the conversation we're having right now is very and where your specialty is is thinking about these autonomous systems how to build safe systems and also how to verify the safety of those systems。

 but right now obviously one of the hot topics on Twitter around AI safety is the question of existential risk right is AI going to you know know this is like the Terminator or Skynet scenario could you talk a little bit about what you're talking about and what you'll be teaching this summer and how it might or might not relate to that question of existential risks。

Yeah， absolutely。 So maybe first， I'll briefly articulate what I think the argument around existential risk is。

 And then I'll talk about how the summer seminar might might not relate to that。

 So the basic idea is that you know as we build more and more capable and competent autonomous systems that are more widely integrated into our society the risk is that either due to these problems of a lack of robustness or what's often called a misalignment in their objective。

 So we ask super competent AI system do one thing。 and in pursuit of that one thing it maybe destroys a lot of other things that we care about。

 And so you know you know， this is something that that people are are beginning to think more about as systems get better and better over time。

 But the topic of my research is a little bit divorced from in that。

 I think about systems that are literally on the roads today。 So， for example。

 you can you can go to I think Phoenix and San Francisco and actually get a self-driving car with no safety driver in it。

 you can get in that car and it will take you from。

pointA to point B so I'm sort of most concerned about the systems that are out there in the world today。

 but what I will say is that many of the problems that exist in these systems like a lack of robustness or security flaws and things of that nature could exacerbate this problem of existential risk down the line when we have more and more concrete systems so I think thinking about these problems early on is really important to kind of mitigating those risks going forward as well。

That's great and do you know this is kind of again on that high level。

 you know at this level where where does ethics， this is a question that came in earlier from one of the participants。

 where does ethics come in or that that question。You know。

 how do you consider that or think about that or is that maybe at a level up from these very concrete sort of technical problems that you're trying to address？

Yeah， so that's a fantastic question and it's an extremely important piece of the whole deployment of AI systems ensuring that these systems are deployed in a way that's equitable and fair to all groups and in fact you can even think about the risk that say an AI system will behave differently different subgroups of people based on gender or race or something like that as essentially a lack of robustness to various subgroups and so this is a problem that we absolutely need to mitigate。

 it's a problem that comes from the data sets that we have humans have generated。

 we have bias in our society and that do show up in the datas that we made but it can also be issues with the model models that we use to train on those data sets that will pick up on spurious correlations and things of that nature so these are the types of problems that we need to address and that we'll be talking about in the seminar。

Can we dig on a little bit deeper on those， we're getting a lot of really great questions so I'm just going to summarize So there are some a lot of questions about kind of specific applications。

 particularly around say use in warehouses or industrial machinery。

 So I think maybe we can come back to that in the end but my sense is is some of what you're working on applies across these kinds of machines so though your expertise is really in working self-driving cars with A with airplanes or drones My senses it applies across the kind of fundamental theoretical concerns that you're addressing do apply across those domains is that could you actually before we do that。

 could we then perhaps take a step back and just you've already articulated it。

 but maybe articulating it again So there are kind of two aspects to this there's building and there's verification is that correct。

Could you just elaborate you just touched on that， so could you elaborate when you're thinking about designing an AI system。

 what are the kind of steps or the different aspects where you're thinking about safety and just building out on those？

Yeah， absolutely that's a great question。 so first to your original point I do think that a lot of what we're about to talk about here basically applies across all sorts of application domains because a lot of the core underlying technology is very very similar So yeah as Pax mentioned。

 you know you have two phases I would say very broadly speaking when designing an autonomous system for a high stakes application The first is just building that system and so when we build that system。

 we have to kind of do a variety of things to ensure that we're building kind of the best possible system so maybe that means we're collecting data。

 making sure we have enough data of our data is diverse enough to cover all the aspects of problem we're trying to solve we need to ensure that we're using kind of the latest and greatest。

Methods， engineering methods that are known to kind of behave in a safe or more reliable way and then once we've done that so maybe we've created a system that we think is very safe because we've used all of the practices we've collected data。

 we've done some preliminary experimentation and things seem to be going well but the second phase of this before deployment it is we really need to understand what what can go wrong and what are the risks if we deploy it。

And this can be a whole separate challenge， so I'll actually give sort of a short anecdote to illustrate this so my advisor Pro professoror Michael Coconerffer helped develop the next generation of aircraft collision avoidance so these are systems that are onboard all commercial aircraft that basically ensure that if there's the potential for some midair collision that alerts both pilots to make a maneuver to that does not happen。

And so he started working on this project。I believe around 2011 and they built prototypes of it and they designed an extremely safe system。

 but it took an additional eight years of verification and validation to build enough trust in that system to get the FAAs stamp and this is already when the system was safe enough。

 they just had to ensure they had to build the trust in it in order to make sure everyone was confident that what they were deploying was going to actually be safe and so both of those aspects the designing of the system and the test and evaluation are both crucial pieces of eventually deploying a safe system。

And so and we're going to get into this when we talk through the class but can you talk a little bit more about the verification piece。

 I know you've done a lot of work around that， really interesting work around formal verification as well as I'm going to get this wrong but like is rare event or robust training。

 so could you talk a little bit about you know maybe focusing on your research but the kinds of things that are important for verification。

 well to ensure that a system is safe， but also and we got a question about selling AI。

 but it's kind of related to your last point， but also in communicating or showing and demonstrating that safety to people who might be using it？

Yeah， that's a great question。 So I'll talk a little bit about my dissertation work because it's very near near and dear to my heart And so this is around you know basically the analysis or the testing of extremely safe system。

 So for example， if we're designing a self-driving car we want to make sure that that self-driving car is much。

 much safer than a human So for example， maybe we want it to be 10 times safer than the average human driver。

 And what that means is that that this will have a basically a failure rate of something less than one in 10 to the seven。

 So one in 10 million chance of say causing a collision for every hour on the road。😊。

And so this poses a real challenge because you know， if I make a system。

 how do I know that it's going to fail only one in 10 to the seven rather than one in 10 to the six you know。

 I would have to drive that car hundreds of millions of miles to ensure that it was hitting that correct level of safety。

And so this is the problem that we call in sort of the research community。

 the problem of rare events， so these failure events are extremely rare and if we were to just sort of naively go throughout our day。

 maybe simulating our autonomous vehicle and sort of nominal conditions。

 we're very unlikely to encounter these failure events。

So the focus of my dissertation work was around how can we actually increase the likelihood of encountering one of these failure events and the way we did this was actually。

Handing control over the environment and in the environment in this case with just of maybe pedestrians on the road。

 other vehicles on the road， maybe weather and lighting conditions。

 things that could affect the performance of of our automated vehicle and we would hand over those aspects of the environment to another AI agent and that AI agent would be trained to try to uncover failures of the system so it would actually try to manipulate the environment in such a way as to cause our autonomous vehicles to fail so it's kind of a little bit backwards we think of AI as you doing what it can to say avoid collisions or something like that。

 but this was using AI to actually cover the weaknesses of our automated vehicle and we can do and when we do that we can uncover a whole bunch of possible failure modes and when we do we can basically allows us to understand what are the weakness of our system are we okay with the failure modes that will we found or do we need to go back to the drawing board and fix some of these issues before we deploy it。

And that's great and so and could we okay， so there's this kind of the question you've got rare events。

 you're going to be testing is something that's so safe that in theory that you know the kinds of events that cause a failure are really really rare。

 and so how do you how do you uncover those before they happen I'm assuming this could also in theory be applied to non-AI systems right I assume a similar model could be used to stress test structures to stress tests。

 not stress tests but to test the modeling of a structure or just the design of a mechanical system。

Indeed， so you definitely could do that the difference is that oftentimes in more traditional systems you don't need this approach because you can reason about the safety of the system from sort of first principles like you know what it's made up of maybe it uses GPS we know the characteristics of GPS we can kind of reason about its safety in that way the difference here is that you know now these say autonomous vehicles are based off these very complex machine learning components which are these black box models that are very difficult to reason about and so we need to kind of begin coming up with other ways of testing these systems and what I described as one way that's really interesting so again it's I'm going to call it and this is not technical because I got technical kind of traditional systems you can reason as you said from first principles we understand the physics well enough of this mechanical system that we can predict the failure points with an AI system we can't reason about it based on first principles so we need to we need to test it in simulations could we build on that because I know you've also or Michael's lab。

Also done work around formal verification， could you tell us a little bit about that。

 what that means and？How you're using that or how people could use that to test systems。Yeah。

 absolutely so so formal verification is just like a fancy research term for mathematical proofs so what we're doing in formal verification is trying to construct a mathematical proof that the system has the safety behavior that we wanted to So for example we might try to construct a proof that our vehicle will never collide with another vehicle Now this may sound challenging or and it is and oftentimes what's required to do these formal verification proofs is to make a bunch of assumptions maybe we will assume that pedestrians can only move so fast and that they'll only move in a particular direction and so on and so forth and so we make all these assumptions and then we prove that our system under those assumptions will never ever be involved in a collision Now the problem is number one that if those assumptions are ever violated then we no longer have those guarantees but that could be okay because at least we know we're safe when the assumptions are holding and then when the assumptions are violated we can perhaps take some esive maneuver or identify。

😊，Or alert someone that there could be a potential problem。嗯。

And so that's what we mean by formal gratification。

 and it's been a really useful tool to basically proving properties of various components that have gone into aviation systems as well as autoomic vehicles to kind of provide a boundary over which we know we are safe and that could be really。

 really useful。That's fantastic， yeah， and I think those are two really interesting things and I should point we have a link to Anthony's bio there and so if you want to dig in deeper。

 I think there are some links to your CV and some of the papers that you've published or also the Sizzle。

 the Stanford and Telellic and Systems Labor as well if people are interested in sort of digging deeper into some of those topics。

We're getting a lot of good questions， but I think you know maybe we can actually circle into and come back to some of these questions。

 but I want to circle into the course that you've been planning and trying to develop for this summer and so maybe you can just walk through because I think in walking through that you're going to be expanding on this conversation we've been hand and talking about having and talking about kind of what goes into building a safe and verifying a safe system so can you talk through what you're thinking about in terms of the content this is a short oneweek class right so it it is technical but it's obviously you know it's not a semester long already。

So could you tackle that？Absolutely， so the reason I'm putting together this course。

 maybe I can start there is because I think that there's a lot of great resources out there on the internet through SPPD。

 for example， where you could learn about how to apply machine learning and AI to solve a variety of problems。

😊，And I remember taking one of these courses several years back and thinking wow。

 this is really incredible I can't believe how sort of straightforward and easy it is to apply these techniques and solve real world problems The issue is that in the years since then and I've now built a lot of machine learning systems and AI systems you begin to discover that the devil is often in the detail so there's a lot of issues that can go wrong when you actually go to try to deploy or build the system for realworl problem and so I've kind of collected you know a number of learnings from my years and doing research in this topic and I wanted to put those learnings into kind of one place where someone who's maybe taken some machine learning courses can go to get up to speed on kind of latest kind of advancements but also current issues around guide。

And so to that end， you know we've outlined basically a five day course today will consist of about two hours of lectures on the first day we're going to be talking about sort of an introduction to the use of AI and safety critical domains and I'll walk through some examples of times where AI has failed or machine learning models have failed and then talk about how what are some of the techniques that we can use to build much more robust machine learning models that don't suffer from some of the problems that we've seen quite so much。

Can you define robust a little bit， that was one of the first questions what？So when I say robust。

 what I mean is that the model will or an AI system will have similar performance。

 even when the environment in which it's operating in changes ever so slightly， so like I said。

 you know a robust model， say for a time to striv will do just as well in the morning as it does in the afternoon when the lighting conditions are different and people's behavior are slightly different that's what sort of we mean by robustness。

And。Great， so then the next two days will be around model evaluation and verification so on the next day we'll be talking about techniques for explaining these machine learning models so as I said。

 you know often these are these very complex neural networks that have you know billions potentially of parameters that are used to process images and they're often thought of is too complex to really think about but people have been developing ways to sort of peer inside the black box a little bit and try to understand a little bit more about how these machine learning components are arriving at the that they。

we'll also be talking a little bit about this question of failure identification。

 so using these sort of adversarial techniques to kind of stress test your system to uncover the ways in which it might fail as a tool to kind of eventually build safe systems。

And then we will be talking about methods in formal verification as well。

 so certifying or mathematically proving that our neural networks are resilient to say adversarial attacks and have other properties that would be desirable。

 we'll get to play with some libraries that people have developed to do this so you can actually use it in real world projects that you might be working on。

On day four， then we're going to move into a discussion on uncertainty quantification machine learning。

 so I'll say a little bit about what I mean， so uncertainty quantification is basically you know what happens when your machine learning model say encounters a situation it's never seen。

Would you want on the one hand for it to just decide what it thinks is best and go forward full steam or would you want it to identify the fact that it's in a novel situation and perhaps maybe alert a human supervisor or basically do something that it knows to be and in the latter case that's the use of uncertainty quant where it's uncertain about what it's doing and so you put on the brakes and make sure things are okay and so there's a bunch of techniques for building this style of reasoning about uncertainty into the machine learning components or the AI systems that you build。

The just to pause you there。 So it's certainly quantification is it's the idea you're in a new or novel situation。

 It's one recognizing， I suppose， is probably a problem just recognizing it's a new situation。

 And then two is knowing how to respond to that and it can be we think our systems is still reliable in this or it's alert a human or I know I don't remember if this is something that sizzsle works on。

 but it could be something like reverting from the AI system to a model that's much safer or to a safer parameters or something like that。

 Indeed， yeah， often these systems are built with like what they call fallex strategies。

 So like if everything else goes wrong。We have a fallback strategy that we know to be safe。

 though it's going to be much less effective than your AI policy But the real challenge often is identifying the situations that are novel。

 You would think that this should be again， is something easy to do because humans do it very regularly。

 We know when we're in a situation situation that we don't understand。

 But machine learning models have kind of a bizarre attribute where they may be extremely confident in decision they're making。

 even though it's very uncertain and they're wrong。 So， you know there's there's potential for。

 you know major downsides if you don't take this into account explicitly。That's great。

 I'm sorry to interrupt you， I just thought that was one more worries a little bit more。Yeah。

 and'm happy to more questions about that。 And then we'll kind of tie it all together on the last day where we'll talk about for example。

 the。Aircraft collision avoidance system that I mentioned earlier we'll use that as a case study to think about how you put all these pieces together in a way that could hold a very reliable system and then I'll talk a little bit about some of the upcoming regulation around AI so there's actually some there's a big law that's soon to be signed in the EU and then there's been some discussions here in the US and thinking about the ways in which AI might be regulated and how some of the techniques of describing perhaps will fit into that regulation because you might be required in the future to do many of the things I'm talking about to ensure that people say unharmed for the systems that we build。

Thanks Anthony， it's a really interesting course and again it's focusing on kind of these autonomous systems。

 I guess one thing is do you see so we're talking in the primary use case we're talking about is autonomous vehicles like cars or aviation we got a lot of questions about working in warehouses maybe industrial machinery。

 does this still apply I mean in some sense that's a much more controlled environment than a road where you have pedestrians where the entire kind of infrastructure is not built around AI whereas when you go into a factory the infrastructure can be designed around the systems themselves and so I guess broadly the question is how do these apply to those kinds of systems that or situations that are more controlled do you think it's still applicable to people who are interested in machine learning and industrial applications。

Yeah， absolutely。 So I think， you know， almost everything will apply。 So I mean。

 it's just to varying degrees。 So as you mentioned in the autonomous driving setting。

 you're in a very open and uncontrolled environment。 So lots of stuff can go wrong。

 Lots of things can change over time。 And I think it's one of the reasons why it's taken such a long time to get autonomous vehicles out on the roads operating safely。

 in a much more controlled environment。 you do have the luxury of perhaps controlling the the environment in which the AI system is operating in But it's never so straightforward as that。

 things will always change and and you want your your AI system。

 say that's controlling a robotic arm to be somewhat resilient to the small changes that occur on the factory line or changes to the environment。

😊，Lighting conditions， seasonal changes， things like this。 you might， for example。

 not be so worried about you know I talked a little bit about what I called adversarial attacks。

 but there's some sort of intentional manipulation or AI system。

 maybe that's less of a concern in the in the warehouse domain than it would be in the driving domain but nonetheless know you still want to have as robust of a system as possible in both those applications is's just sort of varying that's really interesting how do you even I guess in one sense one question of fault up there is how do you reason do you reason for first principles you talked about using AI systems to kind of play an adversarial role in manipulating a simulated environment how do you even figure out what parameters in that environment to sort of adjust as you're talking one thing that comes to mind is say you're working in a warehouse and say that warehouse has windows that are facing you might not think you wouldn't necessarily think about daylight or。

time conditions being a significant factor， but it could be。

 but how do you approach even thinking through what the environment is and what are the important changes to control for or to test for？

Yeah， that's a great question and there's no easy answer it's going to be a combination of the experts in the domain so people who like have worked in the warehouse space before and they understand like what things might change。

 what are the common kind of situations that might arise that maybe would be challenging for a human to handle and then you can infer that it would also perhaps be challenging for this AI agent you can look at a bunch of examples and this is what we'll do in the course。

 we'll look at a bunch of examples where you have these what we call distribution shifts so where things in the environment change ever so slightly and the machine learning models。

 performance drops quite a bit and so we'll look at a bunch of examples of that and you'll see for example。

 changes in lighting condition or color scheme like things like this。

 you can build a little bit of an intuition around what types of factors and influence certain types of machine learning models and then in the last piece of this is like you absolutely need to monitor your systems as you deploy them so you don't know everything that's going to arise。

And so it's really important to build in this element of number one。

 quantifying your uncertainty during operation， so as we talked about。

 making sure the system is aware when things change and can potentially alert。

 say a user and then also having systems that are monitoringing the performance of these systems over time and if you see the performance dropping。

 for example， then you know something has shifted to be its time to retrain your model or intervene in some way。

That's great。 So maybe even revisiting when I talked to you when I had mentioned earlier。

 kind of the aspects of it， there's building， there's verification and then is monitoring almost maybe a third thing there right。

 you're verifying it in advance once it's deployed is making sure you have and this is what you're talking about in terms of uncertainty quantification you're building into that system a way to monitor to flag situations that are outside what would be normally considered what would be considered normal Yeah yeah so that's like one aspect of what we call runtime monitoring is that uncertainty quantification piece that can alert when something has gone off nominal but another thing you can do is just every every so often every week or re-evaluate your say model on a new set of data So it's sort of like just a repeated validation process So doing the same thing you did before you deployed it on an iterated base and ensure that things are staying at a high。

I love little performance。So this would be， so in other words， the AI system is running。

 it's doing its thing， it's not retraining itself as it's doing it。

 it's not so to speak of learning to environment， but what you're doing is collecting more data than retesting it on the new data。

 exactly。Yeah， you know this is a little bit of I just find it as a really fascinating idea and it's related to that is this idea of I think it's called distributional shift is what you've talked about so I guess the idea is it's related to this to uncertain or novel situations but it can also be that maybe the AI system is working well but say the camera that's recording is degrading and so the quality of the image is changing。

 can you talk a little bit about that and maybe this idea of distributional shift or maybe I'm focusing on the wrong thing。

 but just how that can affect the safety or the continued operation in the machine it might not just be changes in environment could be changes in the sensors I guess yeah absolutely so it could be changes in the sensors and I've talked a lot about sort these physical changes in the environment like changing lighting conditions and things like that。

 but distribution shift can be something that happens say like imagine for example that we have an AI system that's helping you diagnose。

New diseasesise at a hospital or something what would you think would happen to that system at the beginning of the COVID-19 pandemic。

 for example， where a you know a new virus altogether has shown up on the scene。

 it would make these systems go haywire because it's not they've never seen that before and so it can be things like that where like the distribution of inputs that it's seeing is shifting because of a new thing in the world or anything like that。

Interesting yeah so it's a completely new I hadn't even thought about that if there's a new disease or something like that that's introduced it could completely change the way it's diagnosing everything that's really so that's great Anthony we're nearing the end of our time so maybe you we've gotten a couple questions about this so maybe if we in these last couple minutes if you we could do just to kind of a big kind of zoom out and away from the kind of specific things and just maybe get your thoughts on what the future of autonomous systems are。

 what you're hopeful about and what you're worried about。Yeah。

 absolutely so as I said at the top you know I'm really hopeful that the use of that AI systems can basically do a bunch of things that humans historically have done so they can do them perhaps more quickly。

 more efficiently at a larger scale and this can bring a lot of great resources to a lot of people so I think that's like the thing that everyone is shooting for but there are a ton of risks and I think something we haven't even talked about today though I'm sure everyone has kind of encountered it recently is things like chatGT so these generative AI systems that are able to produce content text or images or videos and things like that and these types of systems when deployed without you much oversight can lead to very strange and bad things happening so they can exhibit toxic behavior。

 they can discriminate against people， they can you know deal people's like copyrighted information。

ing images that are in the style of an artist or something like that that can be used to intentionally produce misinformation and they can do this at scale like we talked about you know it's something that human typically does but now you can do it incredibly fast and widespread so I'm a little bit worried that especially generative AI systems are being deployed very widely very quickly and we're not exactly sure what kind of influence is going to have on our information ecosystem system so now there's a ton of AI generated content out in the world and it's not always so obvious when you're interacting with so that's definitely one concerns that I have。

Do you think that this course， so coming back to the course。

 do you think that some of these principles could also apply to people who are thinking about something。

 you know， we were talking about cars and machines， you know。

 things that are interacting with the physical environment and humans there is you know。

Is that something that you think some of these principles can apply to something like chat GT Can can you do testing for kind of emotional harm to humans。

 That's a real，'s I guess it's a tricky question， It's much less a less tractable problem maybe Yeah。

 yeah is much less cut and dry because it's not clear。

 these systems are very general purpose like it can do a lot of different things。

 whereas the systems I was just describing earlier have like sort of one task you can kind of check its performance against And so you know I think many of the techniques can and will apply to things like chat GT。

 but it's just a more challenging domain because you know it's very difficult to quantify like the harms on a soetal scale and all of these things。

 but I think。You know still you want chat， for example。

 you want chat GT to be more robust in that it shouldnt its behavior shouldn't substantially change when it's interacting with DI。

 you would want it to express uncertainty when it doesn't know some things。

 sometimes it does I don't know if you'veve seen it， they'll say oh。

 I'm not sure about this and you would want it to be truthful and honest and things like that so I think many of the in principle many of these techniques apply but it does get a lot messier when we're talking about these really largescale generative AI systems。

How can you know do you foresee these generative AI systems being applied in domains like autonomous vehicles or does that itself pose too great a safety risk I'm sorry now we're going a little bit off it's fine I certainly hope not that they are not because it's you know I've seen so many examples of failures of reasoning failures of logic with these systems that we don't want to put them behind the wheel or behind the aircraft it's possible that you know if we you know five。

10 years from now as these systems get better and better they will be more human like and their reasoning capabilities and therefore could be trusted to do something like this。

 but we're definitely not there yet and I think it's really important for。

For these tasks that are safety critical and have high stakes。

 that we still stick with the kind of systems that have been designed for this bespoke purpose。

 not these general AI systems。Well， thank you。 Thank you， Anthony， for joining us today。

 and thank all of you who joined us today for this fireside chat with with Anthony。

 though there's no fire。 I guess the Zoom side chat， the online side chat。 Well， thank you again。

 everybody。 Thank you， Anthony， and we really appreciate your time。

 and maybe we'll see you again soon。😊，Yeah， thanks everyone， appreciate it。



![](img/f17d22bda88905ff86e38a00a489ca60_3.png)

![](img/f17d22bda88905ff86e38a00a489ca60_4.png)