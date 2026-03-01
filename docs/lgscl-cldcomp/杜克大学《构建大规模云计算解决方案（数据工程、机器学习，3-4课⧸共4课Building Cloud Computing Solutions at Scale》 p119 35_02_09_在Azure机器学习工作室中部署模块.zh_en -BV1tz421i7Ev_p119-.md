# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p119 35_02_09_在Azure机器学习工作室中部署模块.zh_en -BV1tz421i7Ev_p119-

![](img/22c818952e17f702f3c2da868676b3a9_0.png)

So our auto ML run is still going on pretty strong。 It's been a few minutes still。

 and we have here something that previously run。 So let's take a look at that。

 We're going to go to experiments。This is the same type of run that I did before。

You can see here I get a bunch of information， the precision， you get a bunch of graphs。

you get different types of views， you can save the view， you can make some changes。

 let's take a look at this thing that completed like a couple weeks ago。

When the current automl run completes， you will see a status of completed。

 You could certainly see something like error， but you will get important and critical information like what is the best algorithm。

 So behind the scenes， again， these system is just trying a bunch of different algorithms trying to see which one will get you the best accuracy。

 In this case， this is the best accuracy that we got。

 and this was achieved by these specific algorithms。 So if I go back to or into models。

 you will see that we have a ton of different models。

 We have even different several pages of models that were tried。And there we go。

 That's the first page。And you get these， you know run 59。

 so you can see 59 times this thing run and you can see 11 minutes，4 minutes，5 minutes。

 So that is why this takes a long time。 So it tries different algorithms for for the same train to train the same same data set and try to see which ones the more accurate。

 So let's click on this one。Which is the best one， it seems the best accuracy。

 and there's an explanations。So the explanation is something that you can run and it tells you that it gives you a bunch of metrics。

 I think you can explore the data set there we go。So you can see name and index。

 I think you can change these things， there we go feature， I want to say grape。

Select so if we you can see some some of these change a little bit index。 what's the index。

 I think that's the number。 Yeah， there you go， so like your access value so you can you can play around with this and get lost for like a good hour trying to look at everything around your data set yeah metrics。

 look at that accuracy， there's a lot of stuff that you can take a look here and look so if the neat things is that if I make these smaller。

 you can you can see all of the all different all of the different graphs。

 like I'm making it bigger so that it's easier to to read on in the recording so。Not only that。

 if we go back to model， we have this standard scalealar wrapper， light GVM， perfect。You could say。

 well， okay， this is pretty good。 Like I like this。 How， What do I do now， Ohh， I can deploy。

 Let's hit deploy。 Let's test。The deployment。Success with the Github data set。呃。Test， deployment。

 I to do that。The compute type you can select a container instance or Kubernetes。

 Kubernetes allows you to scale。 We don't need that container is fine。 you can enable authentication。

 I strongly suggest you enable authentication always because otherwise this might get very expensive if someone finds that endpoint this will basically publish this model live on the internet for anyone to find it out and if someone does and start sending requests while you're gonna get built and enable authentication prevents unauthorized access to it advanced。

 I don't need that usually a good idea to enable application insights if you want to start gathering metrics and start to debug and get some some cool information about that I'm gonna click enable this is something that you can come back and change。

And then that's it。 you， you can enable SSL or not。 That's fine。 This is good。 I'm going deploy it。

Deploying model。 this is， this is pretty useful。 So it takes a second for， for the deployment。

But once it's deployed， you have a live HtTP API that you can interact with。

 you can send requests and because we enabled the application insights， you get all of these graphs。

So that will start having points we were here in experiments before and then we went to models。

And now we're generating endpoints。 So that's what we'll trying to see next on our deployed endpoints on a azure container instance。



![](img/22c818952e17f702f3c2da868676b3a9_2.png)