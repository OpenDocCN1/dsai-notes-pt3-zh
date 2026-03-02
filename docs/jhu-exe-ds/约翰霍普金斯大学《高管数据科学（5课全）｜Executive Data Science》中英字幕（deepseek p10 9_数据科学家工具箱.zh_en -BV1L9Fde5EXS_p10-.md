# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p10 9_数据科学家工具箱.zh_en -BV1L9Fde5EXS_p10-

This lecture is about the data scientist toolbox， so by the data scientist toolbox。

 I mean the collection of tools that are used to store， process。

 analyze and communicate results of data science experiments。

And so the first thing that we're going to talk about is where do you actually store the data So data are typically stored in a database for a small organization that might be a single small Mysql database and for a large organization it might be a large distributed database across many servers And so I'm showing you here an example the Postgres database but there are a large number of other options The key take home message here is that in the database the data are stored and backed up usually most of the analysis that takes place and most of the production doesn't actually happen in the database it happens elsewhere。

 So usually have to pull it out with another programming language to pull the data out of that database and analyze it So the two most common languages for doing that。

 the first one is our programming language So the R programming language is basically a statistical programming language that allows you to pull data out of a database analyze it and produce visualizations very quickly。

 This forms the basis for our data science specialization。

 The other major programming language that's used for this type of analysis is Python So Python is another similar language that allows you to pull data out of data。



![](img/9e47115a16b6c676ea8bfb94764e0a2f_1.png)

analyze it， manipulate it， visualize it， and connect it to downstream production。



![](img/9e47115a16b6c676ea8bfb94764e0a2f_3.png)

So the other thing that you need to do to be able to use these languages and to pull them about is actually some kind of servers or some kind of computers that you can run those programming languages on。

 so you have the database which stores the data and then you have the servers which you will use to basically analyze the data and those servers will run the languages R or Python or and so forth here I'm showing you an example Amazon web services This is a set of computing resources that you can actually rent from Amazon and so many organizations that do data science actually just directly rent their computing resources rather than buy and manage their own。

 This is particularly true for small organizations that don't have a large IT budget。

So they would actually go out and just rent their computing resources that then they would be able to use to analyze data。



![](img/9e47115a16b6c676ea8bfb94764e0a2f_5.png)

Once you've actually done some low levelvel analysis and maybe made some discoveries or done some experiments and decided actually how you're going to use data to make decisions for your organization。

 you might want to scale those up， so there's a large number of sort of analysis tools that can be used to provide more scalable analysis of datas whether that's in a database or by pulling the data out of the database So two of the most popular right now or the Hadoop framework and the Sp framework and both of these are basically ways to analyze at a very large scale datas Now you can do interactive analysis with both of these particularly with Spark but it's a little bit more complicated。

 it's a little bit more expensive， especially if you're applying it to large sets of data so it's very typical in the data science process to take the database。

 pull out a small subsample of the data process it and analyze it in our Python and then go back to the engineering team and scale it back up with Hadoop or Spark or other tools like that。



![](img/9e47115a16b6c676ea8bfb94764e0a2f_7.png)

![](img/9e47115a16b6c676ea8bfb94764e0a2f_8.png)

![](img/9e47115a16b6c676ea8bfb94764e0a2f_9.png)

So the next tool that is in the data scientist toolbox is actually communication and so a data scientist or a data engineer has a job that's typically changing quite rapidly as new packages and new sort of tools become available and so the quickest way to keep them up to speed is to have quick communication and to have an open channel of communication so a lot of data science teams use tools like Slack to communicate with each other to basically be able to post new results。

 new ideas， be able to communicate about what the latest packages that are available and then data scientists are frequently going to the internet to search for how do I do this really what seems like a very simple task how do I match ideass together from two different log files that might not be something that they know how to do but there are a large number of sort of help websites like stackck overflow that allow people to go out and sort of search for the questions that they need to answer it even if they're quite technical and quite detailed and get answers relatively quickly and that allows people to sort of keep the process moving even though the technology is changing quite rapidly。

Once the analysis is done and complete and you sort of want to share it with other people in your organization。

 you need to do that with sort of reproducible or literate documentation What does that mean it basically means a way to integrate the analysis code and the figures and the plots that have been created by the data scientists with sort of plain text that can be used to explain what's going on one example is the R markdown framework。

 another example is iPython notebooks these are ways to sort of make your analysis reproducible and make it possible that if one data scientist runs an analysis and they want to hand it off to someone else they'll be able to easily do that。

You also need to be able to visualize often the results of a data science experiment。

 so the end product is often some kind of data visualization or interactive data experience。

 and there are a large number of tools that are available to build those sorts of interactive experiences and visualizations because the end user of a data science product is very often not a data science themselves is often manager or an executive who needs to handle that data。

 understand what's happening with it and make a decision。

 so there's a large number of tools I'm showing one here is shiny， which is a way to build quickly。

 data products that you can share with people who don't necessarily have a lot of data science experience。



![](img/9e47115a16b6c676ea8bfb94764e0a2f_11.png)

And then finally， most of the time when you do a data science experiment。

 you don't do it in isolation， you want to communicate your results to other people。

 so people frequently make data presentations， whether that's the data science manager。

 the data engineer or the data scientist themselves that actually explains。

 how did they actually perform that data science experiment， what are the techniques that they used。

 what are the caveats and how can it be applied to the data to make a decision like you'd like to？

