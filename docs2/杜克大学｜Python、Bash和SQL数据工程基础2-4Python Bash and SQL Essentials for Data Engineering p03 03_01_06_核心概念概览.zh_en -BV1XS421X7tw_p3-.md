# 杜克大学｜Python、Bash和SQL数据工程基础2-4Python Bash and SQL Essentials for Data Engineering p03 03_01_06_核心概念概览.zh_en -BV1XS421X7tw_p3-

![](img/e8705d1ba65e647e9ebb4d2183a06387_0.png)

![](img/e8705d1ba65e647e9ebb4d2183a06387_1.png)

Welcome to course 2 Here are some of the key concepts in course 2。 First。

 we'll start off with the Ba Ci。 The Ba Ci is really important for one reason that I like to call the distance between two points the shortest distance is a straight line If you want to do something in a terminal really the canal line interface is the quickest possible way to do things。

 So it is important for data scientist， data engineers。

 machine learning engineers to know the bass Ci because it's the most efficient way to do things。

 Now， when you're writing a script， that's the next thing where to cover it's important to know that a script involves a few different components。

 One component is this chabang line。 the chabang line tells your script what language to use to execute it。

 and that's why inside of a chaang line you could do， for example， on OS10。

 you could write a chaang line script that uses the swift language and that would invoke the swift interpreter you could。

Also go through and invoke bash you' gonna evoke Python so you have the ability to know hook into that script and tell it what actually should be running the code that you're going to put below The other thing you have to do when you're writing a script is to make sure that you make it executable and so the way you do that in Linux is you saychad so basically change the characteristics of the script so that it adds an executable flag once you've added that executable flag then all you have to do is do dolash the name of your script and it could in fact be not even have a file extension on it and the Shaang line will make sure that the correct thing is actually executing that code so really important concept to know the ins and outs of building a script Now let's dive into confi files and variables which also come up quite a bit when you're building things in bash and in particular's say the most important one to be aware of is this bashrc。

File here why is it so important Well， this is where you can configure something so that every new invocation of a terminal will run what's inside of that bashRC So what's nice about this is you could actually build out things like aliases so you know if you want to go through and create a shortcut for some command you know for example CDd into this directory you know source of Python virtual environment you know you could create a very short alias like you know Stop which I like to build which is go to the my source directory and go to the top of it and source you know some Python virtual environment whatever it is you want to do and alias can be configured inside of there similarly。

A lot of times people will export variables and these variables could be let's say the API keys for your project so that you don't accidentally you know check those into GitHub and get that key compromise so that's a great place for the BacheRC now the dot profile is only going to be run once upon login and so that would be something that's maybe a setup initially for your project。

The other thing we'll cover in this course is the search and there's really a couple flavors of this。

 the first flavor is fine， which is real time。And so in the case of a realtime project search you would go through and build out the structure。

 you know make sure that you look at certain patterns and that can be really important because you're able to actually search every exhaustive search that you're looking for locate is also an interesting search utility because it allows you to do things on a metadata or a previous index of the file system so it gives you the ability to have speed right so you're able to actually rapidly go through and look at the results where if it was。

 let's say a terabyte file system it may take too much time to use fine so really again there's tradeoffs if you want to go for exhaustive go or find if you want to go for speed。

 you can go for locate。

![](img/e8705d1ba65e647e9ebb4d2183a06387_3.png)