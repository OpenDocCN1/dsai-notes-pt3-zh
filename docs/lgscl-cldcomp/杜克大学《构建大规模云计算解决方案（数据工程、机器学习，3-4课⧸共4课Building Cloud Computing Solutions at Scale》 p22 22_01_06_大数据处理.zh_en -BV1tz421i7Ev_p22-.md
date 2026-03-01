# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p22 22_01_06_大数据处理.zh_en -BV1tz421i7Ev_p22-

![](img/5072cbce51fbe9e86f4517ec401bb4cd_0.png)

Let's talk through a big data processing pipeline that would be a typical pipeline that could occur in a company。

 First up， you can see that maybe you would want to create a descriptive dashboard that showed in the past。

 let's say the sales in a company or maybe the number of customers this is called historical dating data and so in this particular situation really you're looking at the past and you want to report what happened in the past and this is a critical component of a big data pipeline because you'll need specialized tools that can do those queries the next thing would be real-time。

 So what's happening you know in a ad bidding network where people are going back and forth and choosing what price to pay or dealing with。

 let's say spark data where you're doing predictions in real-time this is the real-time component of a big data processing system。

The third one is the future。 And so in that particular situation。

 this would be things like machine learning， you know deep learning。

 you know forecasting fraud detection recommendation engines and so really when you're dealing with big data you have to be aware of the historical the real time and to predictive and each one will use a slightly different set of tools and different technologies because of the nature of the timebased approach to big data processing。

 So let's talk a little bit further here and look at it。

 let's say a real- worldl data engineering problem a lot of times when you're dealing with data as a student or you're dealing with data and organization。

 you'll first start with your local computer and let's say it's a one gigabyte file you'll start to preprocess that data and then you'll start to realize that you'll need to use maybe a more specialized tool and so you'll have to break up that。

Process into many different steps and then do some kind of a parallel copy operation。

 let's say copy  a thousand files to the data lake S3 and then later。

You can have some kind of a sentiment analysis system get triggered automatically on an event of the copy to S3。

 Later this sentiment analysis result will go to let's say。

 a key value database and so you can see this is kind of a natural workflow that someone would do when they're dealing with a real worldld data engineering pipeline。

 and so it starts off small， but then as the real worldorld kind of crops in here that the cloud native tools here are used to solve the other component of the problem。

 so that's another key takeaway is that a lot of times as well with big data processing。

 it may involve both a laptop and a cloud in conjunction that feedback loop is what makes the big data pipeline。



![](img/5072cbce51fbe9e86f4517ec401bb4cd_2.png)

![](img/5072cbce51fbe9e86f4517ec401bb4cd_3.png)