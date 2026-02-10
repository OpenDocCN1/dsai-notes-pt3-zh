# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P74：0_获取数据的动机.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

Welcome to getting data This is one of the more unique courses in our data science track。

 and so I wanted to give you a little bit about motivation and prerequisites for the course you get an idea about what we're going to be talking about。



![](img/a307f2d85fc400337b9c61f693511d7c_1.png)

![](img/a307f2d85fc400337b9c61f693511d7c_2.png)

This course covers the basic ideas behind getting your data ready to actually perform a data analysis on it。

 So this is a step that's often skipped when you're taking a class in machine learning or statistics。

 they sort of assume that the data are already ready to use they're in a nice neat format。

 So this class deals with the nitty gritty of finding the raw data in whatever form they are。

 whether they're in a database or whether they're in a raw image file or something else and extracting that data out and then is also concerned with tidy data principles and taking those raw data that are really complicated and may be formatted not so nicely and putting them into a nice tidy format that makes it easy to use them when you're actually doing data analysis。

It also covers practical implementation through a range of R packages and we'll be talking about a big range of R packages in this class。

This course assumes that you've taken the data scientist toolbox and installed all of the relevant tools。

 and also that you've taken the R programming class or some similar class so that you have enough R programming background not to be intimidated。

It would also be useful if you've taken some exploratory data analysis and also maybe the reporting and data and reproducible research class Exploratory data analysis is relevant because you might want to plot some of the data while you're doing data cleaning and reporting data and reproducible research cover creating scripts that will reproduce your analysis which is an important component of cleaning data。

 but these aren't required for you to be able to follow the course。



![](img/a307f2d85fc400337b9c61f693511d7c_4.png)

So what you wish data would look like is something like this。

 so you can see here this is a Excel file where you actually have in every single row。

 you have one observation and in every single column you have exactly one variable and so it's neatly organized into something that looks like a matrix which makes it very easy to import this into R or another programming language and start to perform more complicated statistical analysis。

But as we saw in the data scientist toolbox real data look much different than that so for example。

 this is a FastQ file and in the FastQ file you might be interested in actually extracting sort of the sequence information from one line of this file or from each separate line of the file。

And so to get out that sequence information， you actually have to parse this raw text file and extract out the bits that you actually care about。

 And so one of the steps in sort of doing getting data is actually getting into these raw files。

 figuring out their structure and being able to extract the relevant bits。

Another thing that might happen is that you might get data that's actually quite neatly structured so for example this is the data from the API of Twitter and so what it is is it's actually data that's formatted in JSON format and so JSON formatted data is actually quite neat and organize and very easy to distribute but it's very hard to actually use to do downstream analyses in many programming languages so you might want to reorganize that data in such a way that it's easy to analyze and do things with and so that's another component of getting and cleaning data。



![](img/a307f2d85fc400337b9c61f693511d7c_6.png)

Finally you might have situations like this where you have instructions like take one tablet by mouth and take one half tablet with grapefruit juice。

 these are actually free text instructions that you might want to be able to get into that free text and extract out a little piece of that information。

 say how many tablets that they've been instructed to take and categorize that by each record that you collected。

So the data might also be somewhere that you have to extract it out。

 so even if the data is in a structured environment or an environment where you might want to analyze it。

 so here are a couple of examples these are both databases。

 so MySQL and MongoDB are two very popular free databases where data might be stored。

 say for example， if you're working at a company and you might want to be able to go into that database。

 collect some of that data and its raw form and then process it in such a way that you can do analysis maybe on some subset of the data or create an algorithm that will allow you to apply predictive analytics to data that you collect from these databases。



![](img/a307f2d85fc400337b9c61f693511d7c_8.png)

So again， the data may be in all sorts of places， it doesn't necessarily have to be data that's sitting on a file on your computer。

 so for example， this is a get request， which is a we'll talk about in this class。

 it's a request to try to get some information off of a website and so in this case it's getting information from an API。

 the Twitter API about specific tweets or specific users。



![](img/a307f2d85fc400337b9c61f693511d7c_10.png)

Data might also be available from other websites， so this is a website that we'll see relatively frequently in this class。

 which is the open data website from Baltimore， and so this contains a bunch of data sets that are very interesting and useful for you to be able to analyze and they're all free which is great。

 but you have to be able to get them off the web， get them from the API or from one of the downloadable files and clean them up so that you can do downstream analysis on them。



![](img/a307f2d85fc400337b9c61f693511d7c_12.png)

So if you think about the whole pipeline of going from sort of a raw data that you might have in database all the way to the end to sort of the data that you might communicate to a colleague or a collaborator or business partner。

 there's actually a large number of steps。And so what ends up happening in most statistics or machine learning classes。

 they focus on this data analysis step， which is an important component of the data processing pipeline。

 but they tend to skip over this early stage where you actually go from raw data to ti data and that turns out to be one of the more important components in any kind of environment where the data aren't necessarily already pre-tidy for you so any kind of startup company or most large corporations or in almost every academic environment you'll want to know how to actually get at the raw data itself so that you can do the cleaning yourself you understand the principles of what's going on and that's what this class is all about。



![](img/a307f2d85fc400337b9c61f693511d7c_14.png)