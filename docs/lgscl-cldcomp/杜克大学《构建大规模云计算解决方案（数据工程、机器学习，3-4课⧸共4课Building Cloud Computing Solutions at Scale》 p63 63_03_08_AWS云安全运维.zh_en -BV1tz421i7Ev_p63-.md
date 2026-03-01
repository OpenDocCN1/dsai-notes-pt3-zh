# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p63 63_03_08_AWS云安全运维.zh_en -BV1tz421i7Ev_p63-

![](img/93bfb860644924a70cc7cb00e8f99d03_0.png)

Let's now look at this next section here， which is trusted Advor。

So trusted Advisor is a system that goes through and provides a bunch of checks for you。

 and so a few different things it does as it looks at cost optimization。

 that's one thing it can help you can tell you whether you can save money because you have instances that are spinning around idle or whether you could use reserved instances。

 it also can give you performance things as well so it can give you hints about for example。

 maybe you can improve the performance of a service by checking the service limits or making sure that you have provision throughput or you have instances that are overutilized。

Another one you can do check with Truster Advisor of security and this is a really big one as well is is there something that you're not doing from a security standpoint that you need to fix like maybe open ports on a machine that you've launched and then fault tolerance so it also has the ability to help you in terms of are you designing an architecting your system correctly and setting things like automatic scaling health checks multiple availability zones up and then finally service limits。

 that's another one as well as do you have something that's going through and it's triggering service limits or you're using more than 80% so you've spun up more machines you're about to to spin up more machines then you actually have access to and so you need to go call support and get new service spun up。

Also， let's talk about Cloudtrail as well。 So Cloudtrail is a very powerful service that is very underutilized。

 and what this does is it's a tool that allows you to monitor and look at every single thing that's happening in your system so this would be a first spot that you would want to look for if you suspected there was some kind of a break in is go look at cloudtra and see if anything's happening。

 in fact I've seen this in situations where I've had a machine that was compromised or an account was compromised you can look instantly at the log files and you can see that there is unusual behavior happening like someone's trying to make API calls into your system。

 they've compromised an account and then they're trying to escalate the privileges and delete maybe the administrative account or find the root account So really this is an audit trail that can tell you exactly what's happening。

 who's doing it when something has occurred and even having the。

User name and also the timestamp So this is I would say one of the most valuable tools in terms of security that you must be looking at constantly in your account。

 So some of the benefits of it is it will give you access to user and resource activity。

It helps with compliance if you're working in an environment where they check that it's always on and it's a way of doing analysis and troubleshooting and also automating security so there's a lot of benefits to Cloudtrail One other final thing that I want to talk about is AWS config so AWS config is a service that is fully managed that allows you to do a few different things。

 One of them is it sets up continuous monitoring。It also goes through and it sets up assessment。

And then it also goes through and it sets up change management。

And also can go through and do operations troubleshooting。

So what this means is that this service is able to actually work with you and provides you a resource inventory。

 a configuration history， configuration change notifications and so this allows you to have an audit trail of what's actually happened in your system and these changes include anything from auditing security analysis resource change tracking and troubleshooting and so with this you can actually look at the different things that have occurred in your account and use it to handle change management so what this means is that。

You can track what resources have been configured， you can also get notifications with SNS and you also get access to the configuration history。

 So like who made this change when when was this IP addressed different and then finally the thing to be aware of with this is that when you use this AWS config system that it's going to be having a history of the different configurations that have been used and then you can evaluate those changes and make sure that they're actually the changes that you want So in a nutshell。

 security is one of the most overlooked things on AWS or any cloud environment there's a lot of very powerful tools that you can use and it's really important to utilize those tools and follow the best practices so that you don't have a problem where you have exposed your company's data to a nefarious resource instead if you follow these best practices you'll be in good hands。



![](img/93bfb860644924a70cc7cb00e8f99d03_2.png)

![](img/93bfb860644924a70cc7cb00e8f99d03_3.png)