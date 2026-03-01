# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p29 29_02_05_批处理vs流处理vs事件处理.zh_en -BV1tz421i7Ev_p29-

![](img/15edb52c50b877bd15eb98b115d03a6d_0.png)

One thing to look at with data engineering is this concept of batch data。Streaming data and events。

 there are three totally different types of operations that come up frequently when you're doing data engineering tasks。

 So a good example of a batch job would be a nightly job where let's say at night。

 you collect some data from the sales database and you perform some kind of a forecast that would be a great example of a batch job。

 And these are probably the most common and also simple to implement a streaming job is a little bit different in that the data is constantly being updated。

 and it makes it a lot more challenging to decide how to handle that data。

 a good example would be a stock ticker。 For example。

 you have the prices of the stock constantly being written somewhere。

 And then you have to decide what you're going to do。

 Are you going to do a forecast on the stream as it comes in or you want to take the streaming data and send it to some other location to do other processing。

Finally there's events a lot of times with cloud computing events are the preferred way to deal with data because you can respond and write code to an event。

 so for example， let's say you upload a image to an S3 bucket or some storage bucket where you can have a piece of code that's attached to that event and it could let's say convert it from a P&G to a JPG file or take a movie and then look for a certain audio out of it and extract it and translate it。

 you can have these events that get processed and the code is attached to it so with data engineering there's often these three paradigms to look at。

And in particular， batch streaming and events are often going to be the three choices that you'll have to choose from。



![](img/15edb52c50b877bd15eb98b115d03a6d_2.png)

![](img/15edb52c50b877bd15eb98b115d03a6d_3.png)