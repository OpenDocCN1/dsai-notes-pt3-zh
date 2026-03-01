# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p97 13_01_03_什么是数据漂移.zh_en -BV1tz421i7Ev_p97-

Let's talk through the concept of data drift， a very important concept for machine learning operations and what it does is it allows you to detect and alert to data drift on a new data set also lets you analyze the historical data for a drift and also you profile new data over time so why would you want to do this well a good example would be if you had an observation that was the baby weight right so let's say you have1 million babies the time of birth。

 the data is in let's say a data store like Amazon S3 and a year later you go through and you have another observation。



![](img/80c896c69e66362f8ba2f0b61d526d33_1.png)

Which shows that the baby is a lot heavier so it could be。

 I don't know 30 pounds and when it was born， the baby was 10 pounds。 Well。

 this is a good example of the drift here。 So the weight has actually changed significantly So if you initially trained a model here based on this data so this data set a here the change here is gonna to be a very large drift right so if it was initially 10 pounds and now it's 30 pounds youve essentially have three times the difference in the delta of the data So you have a very significant change here and what'll happen is that if you want to train a new model that new model will have to reflect those changes So this would be where you could put an alert and you could make sure that what you're trying to predict is still accurate so if you if you're trying to predict for example babies that could have the need for。

Hospitalization right if you train the model。On data that was this initial data。

 it may not apply for a baby that's one year older。

 so this is a really important concept data drift and it's something that you can monitor yourself and then alert for at a regular basis so it's almost like tire pressure or you looking at the elevation and airplane when you're flying an airplane。

 it's a monitoring mechanism but specifically for machine learning。



![](img/80c896c69e66362f8ba2f0b61d526d33_3.png)

![](img/80c896c69e66362f8ba2f0b61d526d33_4.png)