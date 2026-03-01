# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p46 46_03_07_无服务器概念：函数.zh_en -BV1tz421i7Ev_p46-

![](img/025a5d61ad597d5805a16ac879b6f987_0.png)

So let me talk a little bit about the functions next here before I get into the ecosystem。

One of the things that is interesting about serverless。

Is that it capitalizes on this concept of a function。And so if I go here and I say serverless。

And functions。I think I've mentioned this before that with AWS， they're probably the leader。

In serverless， and they have something called AWS Lambda。AndWell what is AWS Lambda at its core。

 really you could think of it as something called FAAS or function as a service。

 and so what this means is that at the core of anything that you build thats serverless is the Python function。

And it could be really as simple as， for example， I could do this， I could say de， and I could say。

 you know hello。And then I， I take some payload。 We'll just say it's x。 And then I return back。

 let's say x plus one。 that that really is potentially。

All you would need to do to build out some kind of resource right it's just a couple lines of code and if I put that into AWS Lambda。

 I can then make it go all over the AWS ecosystem， I can attach triggers to it。

 I can build web services so really the heart of serverless is just a function it's really something that is a couple lines of code and it can accept an input。

 it can process it and it can return it back out and so that's a really key thing to understand about building serverless technology Now the concept of a function though is a very interesting concept because。

Outside of just building things in the cloud， this concept of a function also can be applied to other computer science techniques。

 so in particular， let's say that you want to do GPU programming and I'm going to show you an example of this in a second。

 Well， you can do the same thing you can just have a function and you can attach let's say a decorator on top that says essentially use a GPU and then now you can dispatch this function and run it let's say 10 million times very quickly across a GPU cluster and it's just that function and all you did was put a decorator on top。

 you also can build command line tools by just attaching a decorator on top of something and building something you can also build a web service。

So you could build a flask gap and it could again be just a function the other things you can do with a function。

 you can also do data science so if you go to pandas for example。

 pandas most operations that are helpful require you to build an apply function so you would do dot apply here and then the apply the function would go across every row and actually do those operations。

So this is really at the heart of actually thinking about serverless is that when you really get down to it in terms of cloud computing。

 it's a distributed system and it works really well with this concept of have a small piece of code and then I use that small piece of code to do something it could be a cloud function。

 it could be a GPU operation that has incredible scale like 10 million rows that I process all concurrently。

 it could be command and tool a web app data science application could be machine learning you could do an ML problem with it and sometimes it's just a few lines of code and I think this is really the key reason why serverless is such a fun technology is once you understand that the power of things is to encapsulate it in a very small amount of code and then connect those pieces。

Together， so that that's serverless and kind of setting the stage for some other stuff I'm going to talk about。



![](img/025a5d61ad597d5805a16ac879b6f987_2.png)

![](img/025a5d61ad597d5805a16ac879b6f987_3.png)