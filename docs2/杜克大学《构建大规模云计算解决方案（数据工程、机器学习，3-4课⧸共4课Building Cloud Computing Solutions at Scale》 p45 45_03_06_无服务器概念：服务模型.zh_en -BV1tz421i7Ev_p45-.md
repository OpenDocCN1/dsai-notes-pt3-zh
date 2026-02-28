# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p45 45_03_06_无服务器概念：服务模型.zh_en -BV1tz421i7Ev_p45-

![](img/8d36a61880327717e51a1ad3a49bbee7_0.png)

So as I mentioned， serverless is probably my favorite topic in the cloud because if you like to build technology。

 this is probably one of the best tools that you can use。

 And so I'm going to talk about three different aspects of serverless the first I'm going to talk about the cloud service model。

Then I'm going to talk about functions and why they apply to serverless。

 and then I'm also going to talk a little bit about the ecosystem and then I'm going to get into some hands on examples。

To really explain serverless at the beginning， we need to talk about the service model itself。

And to do that， I can actually just draw this maybe at the bottom here to make it a little bit simpler。

So you have， when you're building things in a cloud， a spectrum。You have infrastructure as a service。

 which is the lowest level。You have the platform as a service， which is a little bit higher level。

 and then you have things like serverless。And the big distinction here between these different models is that infrastructure as code means that really you are getting the low level pieces so you could be getting the CPU。

 the storage， maybe also the network and you're controlling explicitly each of those components。

And this would be a lot like in the real world， going to a big store that has the raw ingredients like。

 you know， flour。Sugar。You know， meat， things like that， vegetables。

 you're basically getting the core ingredients， but then you have to cook the food yourself。

 And so that's really the way to think about infrastructure as a service。

 So on one hand if you own a restaurant， you could make a lot of money。

 because you could buy the food for cheap and then sell it for more money it's the same way with a cloud。

 if you buy things cheap using infrastructure as a service。

 you can construct things and then sell that to other companies。

 and that's actually done through something called Saas or software as a service。

 So it's a lot like the same example of a restaurant owner。

Now platform as a service is a little bit different and we can draw an arrow here。

Because platform as a service。Is something where it's a lot more like a restaurant where you could actually order the food。

 so you could go through and you just order what it is you want and it's almost like going to somewhere where you can tell the person making the food。

what it is you want in your burrito So if you have ever gone to a restaurant where they lets you decide what to put in the burrito。

 you can say I want chicken and I want some rice So you didn't have to buy the chicken。

 you didn't have to buy the rice， but you still have control over what it is you want to build in there。

 And so what are the options in the cloud that are similar a lot of these are our web servicebased component。

 So the technical analogy here would be a Google app engine or Ge would be a good example of a pass。

 Also a elastic beanstock， So we'll call this EB on AWS would be a good example。

 So these are services where you still have to do a little bit of work。

 but most of the servers themselves are actually handled by the cloud vendor。

 So I find myself leaning towards a lot of times wanting to use something like this。Because。

I don't want to go down to the low level a lot of times because it's a lot of work and that's not really what I'm trying to solve。

 I'm trying to solve for a problem。 Now serverless would be even easier and more of a high level and so the analogy here would be just like you order something in person and you can customize things。

 serverless is even easier， it would be like ordering takeout food。

So it would be like if you went to a restaurant on the phone and you call them up or you go on a website you say look。

 give me the food， bring it to my house， there's nothing to do。

 you ask for it and they give it to you。And what's nice about serverless and we'll get into this is that's really the lowest level of abstraction in terms of automation。

Or I guess you could say depending on how you define it。

 it's either lower or the highest level of abstraction and that basically what this means is that you can think in logic and the logic will directly correspond to what it is you're trying to build and so what are some examples of this the examples of this would be。

Functions。 And so these would be things like Google Cloud functions， AWS Lambda。

 and I'll get into this in a second and explain why this is so important。 So really。

 that's the main thing to think about when you talk about serverless it's that you're moving away from doing everything yourself and there's depending on how you define it。

 could you could still define serverless as platform as a service because you're not managing servers。

 but in general， it's moving away from doing things yourself。

 instead of spinning up virtual machines attaching storage。

 doing network connections to things you're using highlevel server that automate a lot of it。

 And so if you're a builder and you want to focus on building technology then this is probably the kind of technology that you want to focus on as I mentioned。

 the cloud providers themselves this is really where they're focusing most of their energy is on this。



![](img/8d36a61880327717e51a1ad3a49bbee7_2.png)

The platform is service and serverless。

![](img/8d36a61880327717e51a1ad3a49bbee7_4.png)