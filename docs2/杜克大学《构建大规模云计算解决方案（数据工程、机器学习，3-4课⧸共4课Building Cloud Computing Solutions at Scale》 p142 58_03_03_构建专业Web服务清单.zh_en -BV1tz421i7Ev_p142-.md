# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p142 58_03_03_构建专业Web服务清单.zh_en -BV1tz421i7Ev_p142-

![](img/b6ff5921aa6fbd9fe33b50e3fa7b8424_0.png)

So here。One way to think about。A professional， let's just talk about a professional。Is that。That you。

What you do is you build a service that， so if you're building a professional web service。

You need to have a checklist。And the checklist would be that。嗯。Is it automated right。

 so do you have an automatic deployment process and we have gotten into that automatic deployment that's a must have for professional cloud development。

Also do you have some testingine andlinting and we got into that， how powerful that is， right。

 that's very important。We also in the checklist。Want to make sure that that it's elastic right。

 And so that's that's one of the things and even as well adding some monitoring you know and logging as well。

 So so for example。What happens if it's having problems。

 how do you know it has problems right so these these are just some of the things that you would do in a professional web service。

And so even if you are doing like a pass， right？And in the past。

 you have one of these like Google App Engine， you have。Azure app services。Or you have beansan stock。

Bean stock still is you're the professional。You can't guess like you have to verify that。

TheThe thing is elastic。 and so what I would recommend would be this workflow。

 which is you have so so basically this is。Under elastic， we say， don't guess。Always check。

That's how you get yourself into trouble and so what we do， we would have GitHub。And inside of here。

The the human is。Checking the code in， and then we know that we can auto deploy to the cloud， right。

 great。But。And when we do the auto deploy， we also maybe do some great stuff in here， right。

 we go through and we， we link the code and we test it and we do some fun stuff here。

 But here's where the the next level is， is that I would use。Once it's been deployed。

I would actually trigger maybe even like a nightly test。Using either。

 there's two services that I've used。1 is called loader。IO， and I'll show you this right now。

 and the other is called locus。And why would you do this？Is because anything could happen。

Even if you are using the platform as a service tool that can like scale up and scale down。

 why guess， don't guess if you're constantly making changes。

 it's the same reason like why have a smoke detector in your house。Like you can just say， oh yeah。

 don't I already checked my house， there's no problems with it。Well， if you want to live。

 you have a smoke detector because you don't want to assume that what happened today will be what happened in the future。

 so instead if you have a nightly test that runs at midnight in let's say a staging environment。

Right here， let's say this is the staging branch。 can you can not just guess that your app is performing correctly。

 but you can verify it by doing a nightly load test。

 And so even I would say you're just making it easier because it probably will be very successful but don't guess right And so if you have monitoring and logging with like80 Cloudwach and you know that kind of things inside of here。

 you can I'll show you what I've done two different ways。

 I think I even have an application that I could show you for this too。 So if we go to。



![](img/b6ff5921aa6fbd9fe33b50e3fa7b8424_2.png)

Here's a example。Flaask locus， this would be good a good example I think。

 of some things that that you could take a look at。

 but basically just there's a walkthrough that goes goes through here。

 but but you could just add a very simple test that just make sure it doesn't work right like doesn't work because this is a functional test where the deployment process that doeslinnttin and testing could be testing the business logic but this test a higher level and why not。

 why not have it automatically at night go through and do a load test。

 The other one that I've used as well。Is a loader I O。 and I actually really like this one。

 this simple cloud based load testing， because what it does is you just sign in。

 and I think I even have an account here still。And。I don't know if I have an account， let's see。

Maybe I don't have an account anymore， but basically the the。The way it works is that。You。

We see if there's a picture of it。Here， but basically。You can just tell it to do a bunch of requests。

And it will it will do here you go， getting started， they'll have a picture here somewhere， I think。

嗯。Creating a test。 Here we go。 So yeah， here we go。 Here， here's a picture of it。

 So you would just add a test in like this。 So it looks kind of like the postman。 And again。

 you could tell it to run at night。And you do a request， and then basically once it does the request。

 it will actually scale up。And it will scale up to。

It'll show you a chart that shows you how much traffic your application can actually handle。You。

 here we goes。 Can I schedule a load test， Yeah， you can。 anyway， this web service itself。

 you could you could use， and it could it could do something very similar to what I was showing you earlier with the the flask this locust thing。

 It does the same basically does the same thing。 It spins up a bunch of of request and test your application。

 So I think it's。

![](img/b6ff5921aa6fbd9fe33b50e3fa7b8424_4.png)

It's not an either or like just because you're building on a service that has great elasticity。

 still， you need to verify it， my advice would be you have a nightly test in a staging environment and you always know what the performance capabilities are of your application。



![](img/b6ff5921aa6fbd9fe33b50e3fa7b8424_6.png)

![](img/b6ff5921aa6fbd9fe33b50e3fa7b8424_7.png)