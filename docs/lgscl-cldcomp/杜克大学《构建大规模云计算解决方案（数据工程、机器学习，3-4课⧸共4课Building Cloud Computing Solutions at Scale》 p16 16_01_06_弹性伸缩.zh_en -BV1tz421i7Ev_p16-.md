# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p16 16_01_06_弹性伸缩.zh_en -BV1tz421i7Ev_p16-

![](img/87ef930ac6edd5cf70bfe4d81d874eba_0.png)

Elasticity is a core attribute of modern best practices for cloud computing？ Why is it so important？

 Well， here's a good example， Let's say that I have a load balancer right here。

 And as increased request come in， I automatically can add a new node based on the CPU metrics of each machine。

 So one of the things I could do is I could say when any of these nodes get to 75% CPU automatically increase nodes from。

 let's say 5 to 10 expansion。 So you know if I start out with five。

 I can get all the way up to 10 before I get some kind of an alert and I do things differently。

 and what this does is allows me to fully automate when a increased demand comes。

You know why does this happen well， let's say it's Christmas right that could be a good example。

 you know there's increased retail sales or there's the Super Bowl or you know there's some kind of you know big。

 big event here and instead of me having to have a person go through and potentially make a mistake。

Automatically my cloud based system can scale up to meet those demands and this is a critical。

Component of engineering in a cloud environment correctly。 If you can't do this。

 you're not doing software engineering best practices for the cloud。

 So this is a key factor in realizing whether you're important。

 you're doing the important things in cloud computing so。

That's the scale up part well another thing though is if in your scenario here instead of having increased requests we actually have a lower amount of requests what happens if I've scaled out the Super Bowls over I could be spending let's say you know $10。

000 an hour based on you know the load that I have I don't want to just leave all that running I can also set a rule that says。

If the machines， for example， diminish a lower than 25% CPU then remove nodes all the way down until let's say three and say I would want a maximum of three nodes running and this can also scale in and so elasticity doesn't just mean being able to scale out it also means being able to scale in and really what is this all about well。

 this is about money and if you can optimize the infrastructure of your company so that it scales up and scales down you as the software engineer are very valuable to this organization because you've automated things that previously took a lot of people to do and really this is one of the fundamental ways you know you're doing the right thing with cloud computing is that you have elasticity with your infrastructure。



![](img/87ef930ac6edd5cf70bfe4d81d874eba_2.png)

![](img/87ef930ac6edd5cf70bfe4d81d874eba_3.png)

![](img/87ef930ac6edd5cf70bfe4d81d874eba_4.png)