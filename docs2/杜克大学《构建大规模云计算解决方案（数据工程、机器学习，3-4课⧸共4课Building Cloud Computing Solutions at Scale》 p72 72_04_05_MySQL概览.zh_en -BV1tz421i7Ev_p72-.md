# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p72 72_04_05_MySQL概览.zh_en -BV1tz421i7Ev_p72-

![](img/5913aa031e6fd0cfbbce55f33b4a4ca0_0.png)

Here's a diagram that shows some hacking type ways to interact with MysqL。 So instead of only using。

 let's say a MysqL SDK or going into MysqL inside of a nice gui etc。

 there is more of like a traditional Linux hacker kind of style that you can do for data sharing because in some cases you may need to do something very quickly。

 let's say you only have MysqL installed python and bash。

 which which is pretty common for let's say some virtual machine you have access to or a container and how do you build something without getting into kind of package management hell and you know installing things left and right and uninstalling them。

 seeing what works。 Well， fortunately with Mysql， you can move very， very quickly。

 So one of the things you can do is you can dump files out to disk。

 So let's say you do a specific query inside your database。 So in this case。

 I'm doing a query of some。I dump those out to a file。 and once it's in a CSV file。

 then we can use our traditional tools like Linux or Python， etc。

 And another thing to point out is that the Pyon standard library itself is just truly an amazing collection of different features and you don't have to have third-party libraries to use Python in fact it's one of the advantages of it it's got everything built in so the standard library has in fact a web service so let's say you need to really quickly build out a web service that is able to process some of the data from a database well you do this query。

 dump it out disk then build a very simple bit of Python code to run a web service and then read in that CSV file and then you curl it to actually get the results and this could be something that was let's say a hackathon or you're working with some scientists in a lab and you want to build something very quickly This is a pretty good solution。

Additionally， you could build more and more of these kinds of solutions using the standard library Now another thing to mention with the kind of hacker way for MySQL is that you can also dump the entire database and this is also kind of an exciting way to work is that you could say MySQL dump get a bunch of SQL then go through use some Linux utilities to parse some of that data and then do another manipulation with standard tools like grab and sort and things like that So there's lots of ways to think about kind of hacking when you're working with data engineering in a traditional database by using just the tools that are available a lot of times we can get caught up into wanting to install all these libraries and do all these things but there are some traditional tools that can be very valuable to start with and see how far you get before you get into really industrial strength tools that may or may not be the best solution for a very quick problem you're trying to solve。



![](img/5913aa031e6fd0cfbbce55f33b4a4ca0_2.png)