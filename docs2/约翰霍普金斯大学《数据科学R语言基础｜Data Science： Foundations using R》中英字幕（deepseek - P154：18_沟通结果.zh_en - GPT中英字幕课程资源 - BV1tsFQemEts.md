# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P154：18_沟通结果.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

This lecture is not so much about reproducible research per se。

 but it's more about how you can communicate your results in a way that people can understand them and can check your results if they need to so particularly when you're doing a large data analysis or a complex kind of project and you do your work in a reproducible manner you're going to generate a lot of content and a lot of files and a lot of output and a lot of data and those all cannot be presented at once and so when you present your kind of findings to another person you there's a kind of hierarchy of information that you're going to want to present ranging from kind of least specific to most specific so the bottom line is that you know most people are these days are very busy people like managers and organization leaders are going to be very busy and so they are going to have to kind of accept content that you present at a kind of a kind of。



![](img/68187dfd2bf7628147f52e38ae51bc5d_1.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_2.png)

hiierarchical manner so the idea is that know in many times when you present a data analysis it will be in an oral form like a presentation or in a meeting。

 but often the kind of early results or intermediate results are presented via a medium like email and it's so useful to break down the results of an analysis and to kind of different levels of specificity or granularity and so here's a link to just some general advice on kind of how to get email responses from busy people。

 but the basic idea is that you don't want to kind of blast a ton of information to someone in one go because it'll be overwhelming and people will be less likely to read what you have to say。



![](img/68187dfd2bf7628147f52e38ae51bc5d_4.png)

So if you think about what a typical research paper might look like。



![](img/68187dfd2bf7628147f52e38ae51bc5d_6.png)

You know there's a hierarchy of information built into a research paper。

 so typically the first level is going to be the title。

 which is descriptive of what the paper is about， hopefully it's interesting and tells you a little bit of what's going on。

 but there's really no detail in a title just to kind of the topic that's covered。



![](img/68187dfd2bf7628147f52e38ae51bc5d_8.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_9.png)

The next will be the abstract which will usually be a couple hundred words about what the paper is about you know what motivated the problem。

 what they did to solve the problem， what kind of the bottom line results were so that's gonna to be in the abstract then of course you have the paper itself the body of the paper will show you you will have the methods more details about what you really did there will be the more detailed results any sensitivity analyses know things like that will be in the paper and a much longer discussion of the implications of the results。



![](img/68187dfd2bf7628147f52e38ae51bc5d_11.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_12.png)

But of course， even the written paper does these days for a complex data analysis doesn't specify really all the details that need to be used that are needed to reproduce the findings。

 So then you typically might have some supplementary materials which have a lot more of the details about what was done。

 And then if you really really want to kind of do what was done to a level of precision that is kind of useful you probably need to get the code。

 the data and all the gory details of kind of what happened。

 So that's kind of like the range of things that you might be able to present from least specific to most specific。

 So not everyone's of course is going to be writing a research paper。

 but there is an analog to kind of most presentations of data analysis。 and so。



![](img/68187dfd2bf7628147f52e38ae51bc5d_14.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_15.png)

If you're going to be emailing results to a person， either a colleague or a manager。

 then the first line of information is the subject of the email right so the subject of the email is kind of like the title and you want to have it kind of concise you want to be descriptive and at a minimum you want to have one right so leave don't send an email without a subject so it's not specific as to what the email is about if you can summarize kind of what you've done in one sentence then it may be useful to put that in the subject。



![](img/68187dfd2bf7628147f52e38ae51bc5d_17.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_18.png)

That way people reading the subject can kind of get a sense of what's happening and maybe even make a decision based on that alone the next level of information。

 of course， is the email body and you don't want to go even though there's no technical limit on the size of the email body。

 you don't want to go too crazy with this， but you want to provide a brief description of the problem。

 maybe if someone doesn't if the person may not remember if they're working on many different things at once。

 they may not remember what the problem is precisely that you're working on so give them a little context。

 give them a little description recall if there was a meeting previously you know talk about what was proposed and know and what you actually did summarize some of your findings in your results and maybe for a total of one to two paragraphs this whole the email body。



![](img/68187dfd2bf7628147f52e38ae51bc5d_20.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_21.png)

If you need the person that you're presenting the information to to take some sort of action based on the results of this presentation。

 then you should try to suggest some options that and make them as concrete as possible right and if there are questions that need to be addressed if you want them to kind of come back with an answer。

 it's usually best to try to make them yes， no questions are as simple as possible。



![](img/68187dfd2bf7628147f52e38ae51bc5d_23.png)

After the email body of course you might be able to attach something that's quite a bit longer a PDF file or another type of documented and so this can be like a report containing more detailed analyses。

 figures， tables， things like that， this can be derived from an R markdown file you can use it something that you create with knitter but of course even in the report like this where you may be allow you know a couple of pages to present things you still want to stay concise you don't want to spit out pages and pages of code and tables and results。



![](img/68187dfd2bf7628147f52e38ae51bc5d_25.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_26.png)

We know that your code is available because if you use something like knitter。

 then obviously you have to kind of put the code in with the results。

 but you don't necessarily have to present it all in the report。

 Your opportunity to do something like that， of course。

 will be if you if you if someone really wants to look at what what you did precisely。

 you can give them a link to some sort of repository like Github or project website that will have all of the details all your code files。

 all your data sets， all your kind of all the nittygrity like that， all your software environment。

 things like that。 And so。So that's kind of the level of the different levels of detail that you might want to present to someone And so people who are truly interested in everything that you did or really want to know kind of the details they might go to your GitHub repository and start pulling your code and start looking at it and looking at the detailed results but someone who wants kind of top line top line summaries they'll read the email they'll look at the subject they'll read the brief description and might flip through the report and so the point is a different people are going to be interested in different levels of detail about what you've done and so you want to be and so you want to present people with those different levels so that they might be able to choose the level that they are most interested in and so this is just a kind of a generic template for kind how you might present an analysis or data or a project that you've worked on not every presentation will kind need all these different levels but I think I find this to be a useful breakdown of the different types of presentations that you can。



![](img/68187dfd2bf7628147f52e38ae51bc5d_28.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_29.png)

![](img/68187dfd2bf7628147f52e38ae51bc5d_30.png)

Make。