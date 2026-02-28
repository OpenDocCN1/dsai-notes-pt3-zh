# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p109 25_02_03_Ludwig自动机器学习深入解析.zh_en -BV1tz421i7Ev_p109-

![](img/7e21e04dfe6e84c743a10855bc69d152_0.png)

Let's talk through what Ludwig is。 It's a toolbox that allows users to train and test deep learning models without needing to write code so it's built on top of Tensorflows initially developed at the Uber company and if you take a look here you can see that there's a lot of different use cases involving Ludwig and if you want to take a look at some of the other examples of it we could go through here and take a look at the examples so I'm going to go here and bring over the examples directory and here we can see that there's a text classification problem and this text classification problem will take some text and then it will classify what the text is about It's about earnings。

 it's about acquisition， It's about coffee and then we can pass in using this command line tool here。

 a data set in this case it would be the input file and then a config file which is all the information。



![](img/7e21e04dfe6e84c743a10855bc69d152_2.png)

NeedTo build out the model。 So really it's a it's a configuration based Autom framework where you don't need to write the code yourself。

 You just need to say what the inputs are right here。

 text type level word encoder parallel and then also go through and say what you wanted to actually produce。

 So in this case， we want to tell it to classify。That text and tell it what category it actually is and it'll do it automatically you can see here there's other examples as well。

 you know natural language understanding machine translation so it can translate things from English to Italian right so this again is done on your laptop or your cloud computing environment without having to pay for the API usage so there's some huge advantages to using a open source toolkit like this with a framework like Luwig。



![](img/7e21e04dfe6e84c743a10855bc69d152_4.png)

![](img/7e21e04dfe6e84c743a10855bc69d152_5.png)

![](img/7e21e04dfe6e84c743a10855bc69d152_6.png)