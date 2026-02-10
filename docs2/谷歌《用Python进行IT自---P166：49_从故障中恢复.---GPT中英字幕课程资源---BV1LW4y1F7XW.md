# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P166：49_从故障中恢复.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/db4245bb44798149ffdd13114bd4599f_0.png)

When dealing with a complex system， there's a lot of ways it can fail。

If we want our service to be reliable， we need to make sure that we can get it up and running as quickly as possible when bad things happen。

Well need to have good backups and a well documented recovery plan Backs here doesn't mean just copies of your data。

 It also means backups for the different pieces of your infrastructure。

 including the instances that are running the service and the network that's used to connect to the service Backs of the data。

 your service handles are extremely important。 If you operate a service that stores any kind of data。

 It's critical that you implement automatic backups and that you periodically check that those backups are working correctly by performing restores。

This helps make sure that you're backing up the right data and that you have well documented processes for recovering it when things fail。

 What about the rest of the infrastructure？If you store all your infrastructure as code。

 you already have a backup of what your infrastructure should look like。

But if your service goes down for some reason， deploying all that infrastructure from scratch might take a while。

That's why many teams keep back or secondary instances of their services already up and running。

That way， if there's a problem with the primary instance。

 they can simply point the load balancer or the DNS entries to the secondary instance with minimal disruption to the service alternatively。

 it's common practice to have enough servers running at any time so that if one of them goes down。

 the others can still handle the traffic。Or on a larger scale。

 have the service running on different data centers around the world so that if one of the data centers has a problem。

 the service can still be provided by the instances running in the other data centers。

 If you're running a service on premise， you might want to have two different connections to the internet。

This way， if the connection offered by one of your ISP goes down。

 you can still connect to the internet through the other one。 when you're running on cloud。

 you can mostly rely on your cloud provider having enough network redundancy。

 But if you really care about your service staying up no matter what you might want to run your service on two different cloud vendors so that if one of the providers has a large outage。

 you can still rely on the other。 Now， imagine you're running your service in one data center。

 Unfortunately， that datacenter has just suffered a natural disaster and all of your instances are down。

 what do you do。First step， deep breath。 Don't panic。 You need to recover your service from scratch。

 deploying it in a different data center and getting all your data from backups。

 As long as the backups are available in other data centers and your infrastructure is fully stored in a version control system。

 This should be possible。 But figuring out how to successfully bring up the whole system from scratch can take a while。

So you don't want to have to scramble to do it when disaster hits。Instead。

 you should have a documented procedure that explains all of the steps that you need to take。

 and since systems evolve over time， you need to make sure that this documentation stays up to date。

One way to do that is to once in a while， pretend that you need to recover your service。

 follow the documented steps， and check if anything is missing or outdated。Systems will fail。

 100% availability is simply not an achievable targets。

 but being prepared for a failure will let you recover your service quickly and keep your users happy Upp next。

 we've gathered some resources to give you more info on how to debug problems on the cloud and to be ready for when things fail。

😡，After that， the last quiz of the course awaits you。

