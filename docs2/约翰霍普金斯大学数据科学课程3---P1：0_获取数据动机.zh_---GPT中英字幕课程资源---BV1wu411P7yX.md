# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P1：0_获取数据动机.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

Welcome to Getting data This is one of the more unique courses in our data science track and so I wanted to give you a little bit about motivation and prerequisites for the course you get an idea about what we're going to be talking about。



![](img/f12af61237e8cdf23e6027071abebe97_1.png)

![](img/f12af61237e8cdf23e6027071abebe97_2.png)

![](img/f12af61237e8cdf23e6027071abebe97_3.png)

This course covers the basic ideas behind getting your data ready to actually perform a data analysis on it。

 So this is a step that's often skipped when you're taking a class in machine learning or statistics。

 they sort of assume that the data are already ready to use they're in a nice neat format。

 So this class deals with the nitty gritty of finding the raw data in whatever form they are。

 whether they're in a database or whether they're in a raw image file or something else and extracting that data out and then is also concerned with tidy data principles and taking those raw data that are really complicated and may be formatted not so nicely and putting them into a nice tidy format that makes it easy to use them when you're actually doing data analysis。



![](img/f12af61237e8cdf23e6027071abebe97_5.png)

![](img/f12af61237e8cdf23e6027071abebe97_6.png)

![](img/f12af61237e8cdf23e6027071abebe97_7.png)

![](img/f12af61237e8cdf23e6027071abebe97_8.png)

![](img/f12af61237e8cdf23e6027071abebe97_9.png)

![](img/f12af61237e8cdf23e6027071abebe97_10.png)

![](img/f12af61237e8cdf23e6027071abebe97_11.png)

It also covers practical implementation through a range of R packages and we'll be talking about a big range of R packages in this class。



![](img/f12af61237e8cdf23e6027071abebe97_13.png)

![](img/f12af61237e8cdf23e6027071abebe97_14.png)

This course assumes that you've taken the data scientist toolbox installed all of the relevant tools and also that you've taken the R programming class or some similar class so that you have enough R programming background not to be intimidated。



![](img/f12af61237e8cdf23e6027071abebe97_16.png)

![](img/f12af61237e8cdf23e6027071abebe97_17.png)

You would also be useful if you've taken some exploratory data analysis and also maybe the reporting and data and reproducible research class Exploratory data analysis is relevant because you might want to plot some of the data while you're doing data cleaning and reporting data and reproducible research cover creating scripts that will reproduce your analysis。

 which is an important component of cleaning data， but these aren't required for you to be able to follow the course。



![](img/f12af61237e8cdf23e6027071abebe97_19.png)

![](img/f12af61237e8cdf23e6027071abebe97_20.png)

![](img/f12af61237e8cdf23e6027071abebe97_21.png)

![](img/f12af61237e8cdf23e6027071abebe97_22.png)

![](img/f12af61237e8cdf23e6027071abebe97_23.png)

So what you wish data would look like is something like this。

 so you can see here this is a file where you actually have in every single row。

 you have one observation and in every single column you have exactly one variable and so it's neatly organized into something that looks like a matrix which makes it very easy to import this into R or another programming language and start to perform more complicated statistical analysis。

But as we saw in the data scientist toolbox， real data look much different than that so for example。

 this is a fastQ file and in the FastQ file you might be interested in actually extracting sort of the sequence information from one line of this file or from each separate line of the file and so to get out that sequence information you actually have to parse this raw text file and extract out the bits that you actually care about and so one of the steps in sort of doing getting data is actually getting into these raw files。

 figuring out their structure and being able to extract the relevant bits。

Another thing that might happen is that you might get data that's actually quite neatly structured so for example this is the data from the API of Twitter and so what it is is it's actually data that's formatted in JSON format and so JSON formatted data is actually quite neat and organize and very easy to distribute but it's very hard to actually use to do downstream analyses in many programming languages so you might want to reorganize that data in such a way that it's easy to analyze and do things with and so that's another component of getting and cleaning data。



![](img/f12af61237e8cdf23e6027071abebe97_25.png)

![](img/f12af61237e8cdf23e6027071abebe97_26.png)

![](img/f12af61237e8cdf23e6027071abebe97_27.png)

![](img/f12af61237e8cdf23e6027071abebe97_28.png)

![](img/f12af61237e8cdf23e6027071abebe97_29.png)

![](img/f12af61237e8cdf23e6027071abebe97_30.png)

Finally， you might have situations like this where you have instructions like take one tablet by mouth and take one half tablet with grapefruit juice。

 these are actually free text instructions that you might want to be able to get into that free text and extract out a little piece of that information。

 say how many tablets that they've been instructed to take and categorize that by each record that you collected。

So the data might also be somewhere that you have to extract it out so even if the data is in a structured environment or an environment where you might want to analyze it。

 so here are a couple of examples， these are both databases。

 so MySQL and MongoDB are two very popular free databases where data might be stored。

 say for example， if you're working at a company and you might want to be able to go into that database。

 collect some of that data in its raw form and then process it in such a way that you can do analysis maybe on some subset of the data or create an algorithm that will allow you to apply predictive analytics to data that you collect from these databases。



![](img/f12af61237e8cdf23e6027071abebe97_32.png)

![](img/f12af61237e8cdf23e6027071abebe97_33.png)

![](img/f12af61237e8cdf23e6027071abebe97_34.png)

![](img/f12af61237e8cdf23e6027071abebe97_35.png)

![](img/f12af61237e8cdf23e6027071abebe97_36.png)

![](img/f12af61237e8cdf23e6027071abebe97_37.png)

![](img/f12af61237e8cdf23e6027071abebe97_38.png)

So again， the data may be in all sorts of places， it doesn't necessarily have to be data that's sitting on a file on your computer。

 so for example， this is a get request， which is a we'll talk about in this class。

 it's a request to try to get some information off of a website and so in this case it's getting information from an API。

 the Twitter API about specific tweets or specific users。



![](img/f12af61237e8cdf23e6027071abebe97_40.png)

![](img/f12af61237e8cdf23e6027071abebe97_41.png)

![](img/f12af61237e8cdf23e6027071abebe97_42.png)

![](img/f12af61237e8cdf23e6027071abebe97_43.png)

Data might also be available from other websites， so this is a website that we'll see relatively frequently in this class。

 which is the open data website from Baltimore， and so this contains a bunch of data sets that are very interesting and useful for you to be able to analyze and they're all free which is great。

 but you have to be able to get them off the web， get them from the API or from one of the downloadable files and clean them up so that you can do downstream analysis on them。



![](img/f12af61237e8cdf23e6027071abebe97_45.png)

So if you think about the whole pipeline of going from sort of a raw data that you might have in database all the way to the end to sort of the data that you might communicate to a a colleague or a collaborator or business partner。

 there's actually a large number of steps。

![](img/f12af61237e8cdf23e6027071abebe97_47.png)

![](img/f12af61237e8cdf23e6027071abebe97_48.png)

![](img/f12af61237e8cdf23e6027071abebe97_49.png)

And so what ends up happening in most statistics or machine learning classes。

 they focus on this data analysis step， which is an important component of the data processing pipeline。

 but they tend to skip over this early stage where you actually go from raw data to tigi data and that turns out to be one of the more important components in any kind of environment where the data aren't necessarily already pre-tidy for you so any kind of startup company or most large corporations or in almost every academic environment you'll want to know how to actually get at the raw data itself so that you can do the cleaning yourself you understand the principles of what's going on and that's what this class is all about。



![](img/f12af61237e8cdf23e6027071abebe97_51.png)

![](img/f12af61237e8cdf23e6027071abebe97_52.png)

![](img/f12af61237e8cdf23e6027071abebe97_53.png)

![](img/f12af61237e8cdf23e6027071abebe97_54.png)

![](img/f12af61237e8cdf23e6027071abebe97_55.png)

![](img/f12af61237e8cdf23e6027071abebe97_56.png)

![](img/f12af61237e8cdf23e6027071abebe97_57.png)