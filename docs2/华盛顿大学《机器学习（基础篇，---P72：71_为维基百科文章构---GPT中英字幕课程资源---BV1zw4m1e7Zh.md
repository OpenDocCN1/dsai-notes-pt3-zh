# 华盛顿大学《机器学习（基础篇，第1课／共4课）｜Machine Learning》中英字幕 - P72：71_为维基百科文章构建并探索最近邻模型.zh_en - GPT中英字幕课程资源 - BV1zw4m1e7Zh

。

![](img/d07b66ce04f28abe3344c2f831bcf753_1.png)

In the lectures， Emily talked about nearest neighbor models and how they can be used for document retvals。

 so today we're going to actually do some cool document retrievals using a simple nearest neighbor model。

😊，So。Next， we're going to build。呃。Nearest。Neighbor。Mo豆。For document retrieval。

Here we go yous never bought for document retrieval again you could implement your own。

 but we have one already implemented here that we can use。

 which is great for this first course so when I use the one from GraphLb and it is called nearest Neighs。

嗯。So here nearest neighbors and just like the other models use a verb create to create a nearest neighbor model and so we're going to give it input the people table and we have to say。

😊，What features we're going to use。In the nearest neighbors。

 so the features are going to be the TF IDF， TF IDF。

 just like we've been using for the cosine distances above。And。

I'm going to provide a label column and this label column is going to be the name。

 so when I return my nearest neighbors it's going to return the actual label to the nearest neighbors so the name of the person and then will make the printout pertier so thats good it's there for us so it should only take a few seconds and we will have there we are we have a nearest neighbor model for。

😊，Documents retrieval， so now we can use it， so let's go ahead and use it。😊，So I'm going to。

Just create another header here and say applying the nearest。你不。Moel。For。Retrieval。

And that's see what we'll get。So the first question is。So let's do our first query who？

Is closest to Obama。So who are the closest people to Obama in the data。

 so if you just take aaneous neighbor model？We can use the method query the function query associated with that。

 which just queries the model with some input， so in this case Obama as our input and gives me back the nearest neighbors。

 so who' are the nearest neighbors to Obama， we compute it and it takes it's very quick and I say okay the closest person to Obama is Obama himself which makes sense。

 but after that we have Joe Biden。😊，who is the current US vice president。

 so the president is closest to the vice president， and then we find a few other politicians。

 including former President Bill Clinton， which we saw above。



![](img/d07b66ce04f28abe3344c2f831bcf753_3.png)

你个。

![](img/d07b66ce04f28abe3344c2f831bcf753_5.png)