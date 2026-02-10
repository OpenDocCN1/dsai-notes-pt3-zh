# 密歇根大学《使用Python的统计学（理解并可视化数据、因果推断、建模）｜Statistics with Python》中英字幕 - P76：10_访谈：因果关系与相关关系.zh_en - GPT中英字幕课程资源 - BV1dV411Q7j3

![](img/a6a1d545429d9d7fb465657fa8142081_0.png)

Welcome， my name is Brednda Anderson and today I get to welcome two special guests。Danny and Johan。

They're here to share with us their passions about statistical modeling。

 and in particular their connections to causation and correlation。Welcome， thank you。So first。

 let's begin with Danny。I looked up your official title， it says research associate professor。

Survey Research Center， Institute for Social Research。

 and then also Research Asiate professorfes of Staistics by courtesy。

This is all at the University of Michigan， so maybe you can just start out by sharing a little bit about yourself and what you really do。

Thanks， Brenda。Big picture， I'm a statistician and methodologist。

And I developed tools to best learn how to improve education， health and well being。

Good thing that's the area in which I develop statistical tools。

 there's essentially two types of tools I help develop data collection tools and data analysis tools。

 those are two really big areas of our field as statisticians。

I developed these tools for other researchers to use to answer questions about what treatments are best。

And what interventions are best to improve disorders？And。

The particular area that I focus in is in settings in health。

 education and wellbeing where scientists are interested in making sequences。

Of intervention decisions also not right up front， but along the path， that's right along the path。

 so if you if you go visit a doctor for your anxiety disorder。

And the doctor first has to decide how to first treat you。

Maybe that might be to recommend behavioral intervention and then 12 weeks later when you come back to see the doctor if things are going well。

 the doctor has to decide whether you ought to continue going to behavioral intervention or if things are not going well。

 the doctor might decide whether to add medication so anytime scientists are interested in making those types of sequences of decisions。

I help develop statistical tools。To help answer questions about making those decisions wonderful。

All right Johan now your official title is As professor of Staistic and you are right down the hall for me so I see your door open all the time and you almost always have someone in there that you're conversing with lots of different people so maybe you can share a little bit about what you really do so like you said I'm in the statistics department and so I also work on statistical methods methodology the people that are in my office most of the time that you often hear me talking to those are for the most part probably my PhD students I work with six wonderful PhD students and in fact that's where a lot of a lot of my time actually get spent day to day is working with these students。

And they work on a bunch of different projects， things that I'm interested in。

I work a lot with genomic data and I have， for example。

 one student that works with single cell sequencing data， I also work with social science data。

 I have a student that is working with Twitter data to see if perhaps that can be used in conjunction with survey samples to learn more about populations of interest It sounds very exciting know I can drop in on some of your conversations but your graduate students are there in dialoguing with you and it's always seems like a good time Oh yeah yeah yeah I love working with them wonderful Well you know that this course is the third course in our statistics with Python specialization。

And we're focusing on fitting statistical models to data。

Now our learners have seen sort of an introduction as to what that means why do we fit statistical models to data and they've seen a brief list of some things that are important to keep in mind some considerations and of course along that lines is the idea of causation versus correlation so I wanted to invite you here so we could rely on your expertise and focus a little bit on those concepts about association versus causal relationships and maybe post to you first to share with our learners if you were in an elevator and going up 12 flights and you had that time to kind of just give the big idea correlation versus causation and that idea give me your elevator pitch so I don't know who wants to go first。

Me yes， okay， so one example that I like to use to show the difference between what is。

 I'll say just an association versus what is causation is to think about say that you're interested in the relationship between say social anxiety and time you spend on social media so you could go out。

 you could collect some data and you could see in the data and this is just hypothetical。

 but you could see in the data that people who spend more time on social media also have more social anxiety and then you could think about well。

Why is that okay， so it could be that。Being a more anxious person。

 you don't want to go outside as much， you spend more time inside。

 so you spend more time on social media。But it could also be the opposite。

 it could be that going on social media， you see everybody else having a great time and you don't feel like that's you and now you're becoming more of an anxious person。

It could be both and it could also be neither it could be that younger people spend more time on social media。

 older people don't younger people tend to be a bit more anxious。

 older people don't and so actually there's there's no causation one way or the other so I think it's important to remember。

You'll hear your statisticians say a lot， association is not causation right that means that you can have other explanations。

 but it's also important to remember that even if you have causation， it could be going one way。

 it could be going the other way， it could be going both。Very good， all right。

 we've reached the 12th floor now we couldn't go down the elevator and so now Danny gets to give me his elevator pitch and just connections to these ideas days of association versus causation。

That's right， I'd love to try to connect it up with the example just given so in my area we're trying to make decisions about sequences of intervention。

 so if I could go back to that anxiety example I used， if we just observe clinicians。

 which includes doctors， nurse practitioners making their own decisions about what treatment children with anxiety disorders ought to get。

 if we just observe them， if we just go videotape and record what treatment decisions they make。

And then we go back and we analyze the data and we look at it and see， well， you know。

 children who got behavioral interventions do better than children that got medication。

It's not necessarily true。That that's the case， it might be true。

 but we have a little more work to do。And in my setting。

 it's not just about the first treatment decision。We can repeat this conversation or this concept later on。

 12 weeks later when they come back among the children who weren't doing well。

 we might observe some of them got more of the intervention they started with like a higher dose。

 and other children switched to a different treatment there again it might be that the children who switched to a different treatment did better。

 but that's if we just observed the data that's not necessarily true so。That would be correlation。

More recently in my research， what we've tried to do which is really interesting is we now flip coins。

 we actually bring in randomized trials and what's really novel about my current area of research is we' randomize upfront to say behavioral intervention versus medication and then sometime later if the child's not doing good will randomize again and what we're trying to do there is we're trying to really get at the issue of causation directly through our data collection process and so that's really where I spend a lot of my time working with correlation versus causation is making the case for these kinds of trials to try to get slightly better answers to cause to questions about cause So certainly the establishment of correlation versus or association versus causation is really a lot due to where the data came from how it was collected and what kind of that would be true All right Well maybe now that we have our elevator pitches we could maybe do a little more deeper dive maybe you could share a little bit more about a project that's more directly related。

With this idea of causal inference， something along the lines to give us a little more concrete examples or applications all right no how you want to go first Yeah sure so one one project that I'm working on right now and as we just discussed there's a big difference between observational data and experimental data the big difference being that with experimental data。

 you can essentially know for sure whether what's going on is causation or not where with observational data you need to worry about is it just an association that's there maybe by confounding or is it something that is causal。

So one experiment or one project that I'm working on is。

A way to be able to actually integrate both types of data。

So if you've got a whole bunch of observational data， which。

Is the great thing about observational data is that it's usually easier and cheaper if you have a lot of that can you somehow use it to actually improve an experiment that you're doing so that you don't have to recruit quite as many people don't have to spend as much money on the experiment so the basic idea is that you'll take the observational data and you'll do some sort of statistical modeling and you'll essentially come up with the best guesses that you can of what's going to happen inside the experiment and those best guesses maybe they're right maybe they're wrong hopefully more often they're right than wrong but。

No matter what happens， you're going to be able to use them inside your experiment to make your experiment a little bit more powerful。

 but at the same time making sure that you won't mess up the experiment。

 meaning that you're not going to introduce any of the biases from the observational data。

Sounds exciting so you've done this in kind of what field or what area have you it's actually the the experiments that we've been looking at are from。

it's an educational example okay we've got some educational software and inside the educational software they they'll randomly assign people to get one version of the software versus another to see which is more effective and then the observational data that we have is we have a whole bunch of past data on how a whole bunch of students responded to to the software but not it was' an experiment right just observed interesting what a good way to combine both ways of gathering data and using in anapp ways to get answers out about our world around us that's really cool it's awesome All right Danny you get to now share a little bit more about an application or area that's something that can connect to these concepts of modeling and causation correlation association right？

I'd like to give an example of a project that's got me really excited these days and I'm switching gears a little bit。

 it's still all about sequences of intervention decisions， but here it's a little bit different here。

 it turns out that many schools across the state of Michigan when you look at the mental health services being provided by the school professionals at those schools。

 it turns out they're not providing evidence-based practices to their children。

And this is not just in the state of Michigan， this is a common thing across our country and what this particular project tries to do。

And it's the first of its kind to ever do this is it's asked the question， how do we get schools。

 the school professional， the mental school professionals to adopt an evidence based practice？

Such as cognitive behavioral therapy。What we realized in building up to study and designing it is that there's not just one thing we're going to try to do。

It might be a sequence of things we're going to attempt to do to get them to adopt an evidence based practice。

 so the intervention we're talking about here is at the level of the school。

And the outcome we're talking about here is at the level of the mental health professional within the school so there's a clustering design this is really exciting so here's what we did。

 what we did is we first randomized over 100 schools across the state of Michigan we randomized them to first get a coaching intervention where we go in and we coach them to adopt the evidencebased practice versus some other lower intensity lower support intervention that's not coaching coaching is very expensive。

And then after four months， if the school hasn't yet adopted the evidence based practice to a relatively low bar。

The schools that have not yet adopted it， we rerandomized them to two different interventions。

 one of them is called facilitation and one of them is to stay the course with what we were doing and the facilitation intervention is an intervention that helps address organizational barriers at the school so was a school professional having trouble getting a room to do the cognitive behavioral therapy。

 does a school professional not have the support of the principal？

Sort of I call them more business sea levell barriers and what's really novel about the study from the statistics point of view is this is the first of its kind study ever where we rerandomize at a higher level。

 but our outcome is at a lower level it's at the outcome of did the school professional adopt cognitive behavioral therapies and so day to day what I'm doing with students is I'm developing how do we analyze the data that arises from such trials and we actually have to develop new analytic methods to do that？

Because of the structure of how you're gathering your data because of the structure of how you're gathering your data。

That's right that's exciting and very important and what we need to do that's so neat。All right。

 well we have a lot of learners out there that are going to be going on this journey of learning about lots of different statistical modeling techniques and so maybe you could just share a little bit of advice on what you might want to let them know about learning statistics。

 learning about statistical modeling and taking a course like this online and so if you would maybe reach back to when you were studying statistics which we're always learning right we're still studying statistics and learning ourselves。

 but any advice you might have for a learner of statistics in our course。I am happy to go first。

When I first introduced myself， I introduced myself as a methodologist and statistician。

 the reason I did that， and the reason I do that now in general when I introduce myself is because so often these days I think that learners of statistics view statistics as being all about data analysis。

But the beauty of our field。Is that statistics is necessary every stage of the research process of the scientific process from deciding what questions we can answer。

To deciding how to collect the data， to the analysis。

 which is the well known part to communicating the results。

And understanding what you ought to say can't say when you're communicating those results。

 we play an extremely pivotal role in every stage of that scientific process and so I think that's what I would tell learners it's a rather big picture idea but when you're learning Python or when you're coding in your stats classes you might be focused on the analysis which is appropriate that's a really important piece。

 but just every once in a while maybe take a step back and appreciate the beauty of our field our field is really about the entire scientific process and a lot of what Johan and I do in causal inference。

Is about every step of the way， so for example， in causal inference。

 you know this whole notion of causal inference methodology， it's really a language。

It's more than an analysis method， it's a language about what questions can we answer and how do we frame them and so and that's across the whole spectrum so that's really my sort of advice for learners That's great。

 that's great。

![](img/a6a1d545429d9d7fb465657fa8142081_2.png)

No and you said it so beautifully I don't know that I actually have a lot to add after that。

 but I'll just especially reemphasize one point you made。

 which is the importance of statisticians and others working together is early in the process as possible so and this is something that you especially want to do if you're a statistician is make others aware that you can be helpful to them even before they have data that's right I would agree wholeheartedly and if I could just build on that because I think that is exactly right when you're analyzing a Twitter data set for example you know take a step back and ask yourself well what extra data could I collect to enrich what I'm doing right now is that even possible。

 try to sort of take a step back away from the analysis of the data you're working on right now and that kind of closes the loop because then you might。

Be able to work with another scientist to go collect that data and now you're in the ground running like Johanna saying at the beginning stages and I think that's the beauty of our field is we really get to do the whole process yes we do get to work with many people who have that subject knowledge in an area that maybe we're not as subject experts in。

 but we get to bring that expertise that we have and working together as a team that's exactly right。

In my area。I'm always on these interdisciplinary teams where I'm just one of like five people。

 there's a psychiatrist， there's a psychologist， there's a computer scientist and sometimes there's two statisticians。

 there's me I'm a rather applied statistician and sometimes there's a very theoretical one and we need all of these to really get a high quality research product that's so true very true。

Excellent advice for all of us to keep in mind as we are going through this journey of learning some more statistics。

All right， well， would it be appropriate for me to say that I'm quite confident that after hearing our dialogue today that this is directly related to our increase in knowledge on these areas that are important in statistical modeling。

 causal versus association， and so I thank you for sharing with us today your passions and your interests。

Thank you， Brenda， for the opportunity。