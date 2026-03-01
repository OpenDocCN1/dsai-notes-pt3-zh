# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p47 47_03_08_无服务器概念：生态系统.zh_en -BV1tz421i7Ev_p47-

![](img/e3a7af031502f96cb7a4f5794131780d_0.png)

The serverless ecosystem itself has a lot of traction。And in particular。

 probably the leader right now is AWS， and so let's just talk a little bit about， let's say with AWS。

 what are the things you can build with serverless technology。

 so we know that there's AWS Lambda which is a great way to build services。嗯。

There's also step functions and what step functions do is they will connect different Lada functions together。

 so basically you can take one Lada function。Hook it up so that the output goes another lambda function and you can encapsulate this in something called a step function。

And so you can chain together。Many different operations。

 So that's a little bit of the lay of the land with AWS。 Now。

 the other thing you can do with with a lambda。 we'll just call this L is you also have this thing called triggers。

 And this is probably the biggest shift that you'll see in building these things is that you can hook up a lambda function to let's say 25 plus things in AWS。

 So what can you do Well， you could trigger a web service you could also trigger an operation where if you put a file in S3。

 you could call your lambmbda function， you could also process data so you could take a stream of data and you could trigger it with lambda。

 There's a whole list of things that you can do， you can do timers。

 That's another one you can do is you can actually tell something to run at a certain interval。

 So in terms of AWS。 that's really the lay of the land is。Aus Lada step functions and triggers。

 that's the majority of what's happening on that ecosystem。

 So I guess I could call this AWS ecosystem。 There's another library though。

That's called Chaalice that I think I'll have time to talk about that that might be worth looking at as well that can also do some of these things。

 It's really， it's still AW Lada， but the people that wrote the Bodo API or the main the main SDK for AWS also wrote something called Chalice and it's it makes it easy to do some of these things I just discussed。

 So that's the AWS ecosystem。 Now let's talk a little bit about the GCP ecosystem。

In terms of the GCP ecosystem， they have some interesting technologies and we'll be able to get to。

 I think a lot of them today， so GCP。Ecosystem。There is something called Cloud run。

 which is one technology that in fact， there's a whole book on it right now called Cloud Run。

 And what this is is it's basically a Docker container。

That you can turn into a fullfledged service so you can basically go and build a container and just put it through we'll say cloud run and then make it turn into let's say an API So that means you can take any Docker container check it into their container registry and then make it into a service And so what this does is allows you to have a lot of control over what you build because you can explicitly put inside the Docker file。

 what packages you want to be installed what you want it to do all kinds of different things。

And in general。The Cloud run ecosystem is a really powerful developing ecosystem。 Now。

 the other thing that they have。 So you could call this maybe container as a service CAas。

 but basically you just take a container and it deploys it。

 They also though have cloud functions as well。 And so that does similar things to AWS where you can just put a piece of Python code somewhere。

 and then that piece of Python code can get a trigger and the trigger could be a web service。

 It could be maybe like a message that comes in via a pub sub。

 So in general they're really in parity。 And then also with the Azure ecosystem if I just talk about that real quick。

They're doing similar things with Azure they're really in pary as well。

 so Azure has cloud functions as well so you can build functions and they also have something called。

App services， which is a platform as a service， and this would take the。Like a flask gap。

 for example， and you could take that flask gap and you could deploy it without having to manage servers at all and so I actually have an example of that that I can just talk about really quickly here。

That shows how app services would work。 So if I go to here Flask email Azure serverless。



![](img/e3a7af031502f96cb7a4f5794131780d_2.png)

This is a great example of why you would potentially want to use something like flask。

In a serverless environment is that I can hook this up to GitHub。

I can have it listen to events using their build system， which is Azure pipelines。

 and then I could have a platform as a service offering called Azure app services。

 just kind of sit there and listen for when changes happen and then it can automatically deploy my changes。

 And so what's great about this is I don't ever have to manage servers spin of virtual machines set of networking。

 it's all managed at a high level by this ecosystem。 and again。

 the same thing exists on the Google platform they call it Google app engine and then on the AWS platform。

 they have a parodity service called El Beanstock。 But the concept is the same as that either this platform as a service or the functions really is where I think a lot of traction is headed。

 And so if you wanted to run this yourself。 You could just run this project and I have steps that you can go through where a step by step show you create a project。

You then go through and you say AZ web app up and then it spins up the app service。

 after the app service is spun up initially， you'll see that it'll host up a website。

 and then from here you could go through and set up the DevOs project inside of their pipeline so it'll automatically deploy once you do an automatic deployment。

 then if we scroll down here。

![](img/e3a7af031502f96cb7a4f5794131780d_4.png)

![](img/e3a7af031502f96cb7a4f5794131780d_5.png)

![](img/e3a7af031502f96cb7a4f5794131780d_6.png)

You could you could build out a config file that has the information that you would need to build the job and then finally the final step would be that after you run ran through it you could actually maybe add additional testing or lintting so you have a higher quality of your project so yeah again you could you could go through here and run this yourself。



![](img/e3a7af031502f96cb7a4f5794131780d_8.png)