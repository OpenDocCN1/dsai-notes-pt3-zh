# 杜克大学《Python、Bash和SQL数据工程基础1｜Python Bash and SQL Essentials for Data Engineering》 - P3：03_01_05_核心概念概述.zh_en - GPT中英字幕课程资源 - BV1KW421R7Kz

![](img/8abcdef8877946f5de4d409094627b4a_0.png)

Hi， welcome to course1， I'm going to talk about some of the key concepts in course one that are important to master。

 Let's start off with the pandas versus Python you know dilemma and this is really common sometimes it's hard to know when do I use pandas when do I use Python and even when do I use neither and what we're gonna to cover in this course is that there's a different style when you're working with pandas when you're working with regular Python in particular let's take a look at this this is a very small function in Python notice I define it and I call that process what is this function take well it takes in X this is one of the simplest functions you could possibly build because all it does is returns back x plus one so if I put in one return back two if I put in two or return back three this kind of function works very well with pandas because in pandas you don't loop through things you apply。



![](img/8abcdef8877946f5de4d409094627b4a_2.png)

![](img/8abcdef8877946f5de4d409094627b4a_3.png)

![](img/8abcdef8877946f5de4d409094627b4a_4.png)

Ply a function to each row in a data frame so you can think of it as a spreadprintsheet for example。

 Google Sheets， Excel， and instead of you going through and manually typing all the things。

 you select all the rows and you do some kind of operation it's much。

 much more efficient likewise with pandas， this is really the core of pandas is if you want to process something you don't loop through it。

 you go through and apply a function to it and so in this case if I applied that work。

All those values would be transformed and adjusted to the new input so really when you're dealing with pandas think about a function that applies to a column Now if we talk about Python。

 typically the most common way to do anything when you're manipulating something in Python is to use a four loop a loop through some kind of a sequence in this example we say4 I and range one through 10 go ahead and do some work this is a loop and inside that loop you may do something like well if you know three is equal to you know a know then go ahead and do some other thing and you do these conditional statements and so that's probably one of the most important things to master and Python is a loop and then some kind of condition and then breaking out of that loop and so really it depends on what problem you're in and you use the right tool for the right job now there is a third scenario here that I think is very important to talk about and when you're talking about big data。

One thing to be aware of is that you may not be able to use the regular Python pandas library because pandas can require anywhere from。

 let's say five to 10 times the amount of memory of the data structure that you're working with and so you may need to move to a bigger data tool like using。

 for example， Spk is a very common one that people use for big data because it can operate on large data sets and can pull in compute and storage systems to work in parallel so there's yet another solution that you should be aware of if if you do start to get into problems with big data。

 pandas as well may not be the right tool for you Now let's talk about the second core concept in course1 this is the idea of an editor versus a terminal and why you should know both of these to be successful with an editor what's important to know about is that it can do very complex。

Things like suggest the code you should type and in fact we're at a period now where things like GitHub codepilo for example。

 can go through and it can help you build out solutions and tell you import this library or complete this you can also go through and get Linting automatically inside which is really helpful tells you what bugs you're writing so really an editor in my opinion is a must have if you're building something in a project and why not use the best tool for the job I think visual Studio code or those types of editors are really great editors to work with and even further that we're seeing now that a lot of these tools are available in cloudbased environments like GiHub codespaces for example is a great place that you can actually develop code in and you can actually use the visual Studio code environment inside of codespaces there's also things like Cloud9 in AWS that allows you to do。

So really using the right tool for the right job is critical to being successful likewise with a terminal you also in my opinion do need to know the terminal。

 even though it's a commandlightbased tool， the reason for this is it's quick it's efficient and in particular vim is most likely on every system you're ever going work with and so the way I like to think about it is just like when you're in the kitchen。

 you're cooking dinner， you may use a large knife for one thing and a small knife for another。

 this is a small tool very quick， very efficient and especially for editing things like a bash RRC file really inviable to use something like a vim or to edit some kind of a configuration file or build something very quickly you may not have the ability to use an editor because you're in a terminal only environment so know both master both and you will be extremely productive。



![](img/8abcdef8877946f5de4d409094627b4a_6.png)