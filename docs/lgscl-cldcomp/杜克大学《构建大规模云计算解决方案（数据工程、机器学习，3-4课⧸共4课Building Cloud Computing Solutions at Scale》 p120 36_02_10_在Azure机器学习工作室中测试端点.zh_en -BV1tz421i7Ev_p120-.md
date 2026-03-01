# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p120 36_02_10_在Azure机器学习工作室中测试端点.zh_en -BV1tz421i7Ev_p120-

![](img/7b1b19988d934d0b8d504220167715e0_0.png)

So we've deployed our model， withve trainer model， we selected our data。

 we have it up on running I hope with Azure and we're gonna find it here in endpoint so I'm here in endpoint and going I click here on test deployment before we left it like when it was running when it was like the deployment what going on So right now we're gonna to look at test deployment details。

 a bunch of different things we selected ACI， which is Azure container instance and then now we have rest endpoint look at that it's a full URL。

 we have keybased authentication enabled， we have a swagger URL which like if you want to look at the documentation how to interact with it and we have application Ins enabled。

Before anything。Let's let's test it out。So if we go here to test， we have example value grape。

 let's say， you know， grape， we can say about red wine and we say name this is。How about。

Some Alfredos red wine， how about that， then we can test it out。We're gonna get oh， we get。

 So what we're getting back is that what's， what's the score， the score will be。

 Like How about we do a， we can say。把。Npa Valley。嗯。How about we do govern。We test it out。

 Let's see if that changes。 Oh， so how about white。White wine。

So now you can just it out see if something happens， best value here。嗯。

The result doesn't really change。 So you can see there's。

 there's something to play there with the data。 So not only that you get the rest endpoint。

 Always a good idea to check that。 If that works out， There we go authorized no to no token match。

 that's pretty good。 That's what we want。 consumption option。 You get。Different examples。

 which is pretty neat。 So if I had to copy paste this in Python， it would send， look at that。

 it has my URL already there， my API key and my content type。

 this is already pretty good And if you want to check the logs on how that got deployed。

 That's perfect。 That's certainly going to show there。 but we enabled application insight。

 So what's the deal with that。 So we go here to details and we look at the bottom it will say application insights URL。

 So that will take me that will take me here and we're seeing metric server response time。

 server requests。 Well we sent a bunch we have four several requests availability。

 Everythings going perfectly there's no fail requests。

 let me make server response time seems to be like around 600 milliseconds。

 This is pretty decent really and the average one is 279。😊。

Miseconds so we're doing pretty well and that is how you would interact with an endpoint。

You have different ways to do that with with the consume tab here， R Python C sharp。

 and you can even do this on the command line if you're using curl and you want to pass in the primary key。

 et cetera。 That's certainly possible。 So that's how you double check yet that your deployed model on a Azure container instance is working and available。



![](img/7b1b19988d934d0b8d504220167715e0_2.png)

![](img/7b1b19988d934d0b8d504220167715e0_3.png)