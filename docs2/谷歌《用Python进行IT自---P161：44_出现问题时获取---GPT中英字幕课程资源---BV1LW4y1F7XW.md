# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P161：44_出现问题时获取警报.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/bb45e48049c34b070e92649e2b582e29_0.png)

We expect a lot from our modern IT services。 We expect them to be up and running 247。

 We want to be able to get our work done whenever and wherever。

 and for that we need our services to respond day or night， workday or holiday。

But even if the services are running 24/7， system administrators can't constantly be in front of their systems。

Instead， we set up our services so that they work unattended and deal with problems when they happen。

 Now to do this， we need to detect those problems so that we can deal with them as quickly as possible。

If you have no automated way of raising an alert， you might only find out about the issue when you get a call from a frustrated user telling you that your service is down。

That's not ideal。 It's much better to create automation that checks the health of your system and notifies you when things don't behave as expected。

This can give you advance warning that something's wrong。

 sometimes even before users notice a problem at all。 Okay， so how do we do that？

The most basic approach is to run a job periodically that checks the health of the system and sends out an email if the system isn'thealthy on a Linux system。

 we could do this using Chron， which is the tool to schedule periodic jobs。

 We pair this with a simple Python script that checks the service and sends any necessary emails。

 This is an extremely simplified version of an alerting system。

 but it shares the same principles is all alerting systems， no matter how complex and advanced。

 We want to periodically check the state of the service and raise alerts if there's a problem。

 when you use a monitoring system like the ones we described in our last video。

 The metrics you collect represent the state of your service。

 Instead of periodically running a script that connects to the service and checks if it's responding。

 you can configure the system to periodically evaluate the metrics and based on some conditions。

 decide if an alert should be raised。 raising an alert signals that something is broken and a human needs to respond。

For example， you could set up your system to raise alerts if the application is using more than 10 gig of Ram。

 or if it's responding with too many 500 errors， or if the queue of requests waiting to get process gets too long。

 Of course， not all alerts are equally urgent。 We typically divide useful alerts into two groups。

 Those that need immediate attention。 and those that need attention in the near future。

 If an alert doesn't need attention， then it shouldn't have been sent at all。 It's just noise。

 If your web services responding with errors to 50% of the requests。

 you should look at what's going on right away。Even if this means waking up in the middle of the night to address whatever is wrong。

 you'll definitely want to fix this kind of critical problem ASap。On the other hand。

 if the issue is that the attached storage is 80% full。

 you need to figure out whether to increase the disk size or maybe clean up some of the stored data。

 But this isn't super urgent。 So don't let it get in the way of a good night's sleep。

 Since these two types of alerts are different。 we typically configure our systems to raise alerts in two different ways。

Those that need immediate attention are called pages， which comes from a device called a pager。

Before mobile phones became popular， pagers were the divisive choice for receiving urgent messages。

And they're still used in some places around the world。Nowadays。

 most people receive their pages in other forms like SMS， automated phone calls， emails。

 or through a mobile app。But we still call them pages。On the flip side。

 the non urgent alerts are usually configured to create bugs or tickets for an IT specialist to take care of during their workday。

They can also be configured to send email to specific mailing lists or send a message to a chat channel that will be seen by the people maintaining the service。

One thing to highlight is that all alerts should be actionable。

If you get a bug or a page and there's nothing for you to do。

 then the alert isn't actionable and it should be changed or it shouldn't be there at all。

 otherwise it's just noise。Say you're trying to check if your servicess database backend is responsive。

If you do this by creating a query that returns all rows in a large table。

 your request might sometimes time out and raise an alert。 That would be a noisy alert。

 not really actionable。 You'd need to tweak the query to make the check useful。

 Sa you run a Cron job that copies files from one location to another every 10 minutes。

You want to check that this job runs successfully so you configure your system to alert you if the job fails。

After putting this in production， you realize there's a bunch of unimportant reasons that can cause this job to temporarily fail。



![](img/bb45e48049c34b070e92649e2b582e29_2.png)

Maybe the destination storage is too busy， and so sometimes the job times out。

Maybe the origin was being rebooted right when the job started so the job couldn't connect to it。

No matter why， whenever you go to check out what caused the job to fail。

 you discover that the following run had succeeded and there's nothing for you to do。

 You need to rethink the problem and tweak your alert。Since the task is running frequently。

 you don't care if it fails once or twice， you can change the system to only raise the alert if the job fails three times in a row。

That way， when you get a bug， it means that it's failing consistently and you'll actually need to take action to fix it。

All of this configuring and tweaking can seem like a lot of work。

You need to think about which metrics you care about， configure your monitoring system to store them。

 then configure your alerting system to raise alerts when things don't behave as expected。

The flip side is that once you've set your systems to raise actionable alerts when needed。

 you can have peace of mind。If no alerts are firing， you know the service is working fine。

 This lets you concentrate on other tasks without having to worry to set up good alerts。

 we need to figure out which situations should page。

 which ones should create bugs and which ones we just don't care about。

These decisions aren't always easy and might need some discussion with the rest of your team。

 but it can help make sure that you spend time only on things that actually matter。Up next。

 we'll talk about criteria that we can use to decide which situation should raise alerts and what to do about them。

