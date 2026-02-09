# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P112：54_规划未来资源使用.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

。

![](img/8e40fb605f1709d20289124ad1c33dc5_1.png)

![](img/8e40fb605f1709d20289124ad1c33dc5_2.png)

We discussed in earlier videos what we can do when our programs are misusing resources like memory。

 disk， network， or CPU。But sometimes it's not a question of misusing resources。

 but rather missing resources。 A database server is expected to use more disk storage as more data gets stored。

Or a web server is expected to use more network bandwidth as the service grows in popularity。

 If you're dealing with a service that's expected to grow and will require more resources in the future。

 it makes sense to spend some time thinking about what that might look like。

 Planning ahead will prepare you for when you need additional resources。

 Instead of having to scramble for them at the last minute。

 Let's say the database growth is expected to be 1 MB per day。And you have 500 MB of free space。

 You can use that storage for almost two years。But if the growth is expected to be 10 megabytes per day and you only have those 500 megabytes available。

 then you need to start figuring out a plan that will allow your database to keep growing at that pace。

Otherwise， you'll run out of space in a couple of months。

Once you figured out the current usage and the expected growth。

 don't forget to write this down so you can refer to it in the future and check if anything has changed。

If you find that you'll soon be running out of space。

 what you'll do next will depend on what the system does and the importance of the data。

 You might decide that you don't really want to store all that data and instead。

 clean up anything that's not really necessary。Or you might decide that you really need to have a lot more storage available In that case。

 you might opt for buying a network attached storage or NAS that can be attached for your server for additional disk space。

 migrating to a different type of storage takes time and can be tricky to do right under pressure。

 so it's important to do this kind of planning in advance and not wait until the disk is completely full。

This means monitoring the usage growth of the computer to see if there are any trends that need attention。

 if the service using the database suddenly becomes very popular。

 the daily growth can increase so much that we'll need to find a better solution sooner than we thought。

Our monitoring system should trigger an automatic alert when that's the case。

 an interesting strategy for making the best possible use of resources is to mix and match the processes that run on the computers so they make use of all the available resources。

 If you have a process that's CPU intensive and takes almost all the available CPU on a computer you can still run processes that are Io intensivetenive。

 reading and writing a lot of data to the hard drive。



![](img/8e40fb605f1709d20289124ad1c33dc5_4.png)

![](img/8e40fb605f1709d20289124ad1c33dc5_5.png)

![](img/8e40fb605f1709d20289124ad1c33dc5_6.png)

Or if you have a service that requires a lot of RA。

 you can pair it with another one that uses very little memory and mostly sends and receives data over the network。

An alternative for having to deal with all these resources。

 like figuring out when to buy more and how to distribute them。

 is to migrate those systems to the cloud， setting up your service to run in the cloud will require some initial setup time。

 as well as an ongoing cost for the cloud resources you're using。

But while this is more expensive than what you paid when running the service on premise。

 you're basically delegating all your capacity planning needs to your cloud provider。 That way。

 if the initial setup doesn't have enough space， you can simply attach a bigger hard drive。

Or if the program needs more RA， you can just deploy the service in a virtual machine with more memory assigned。

 if you decide that moving to the cloud is a good way to go for your company。

 remember that you'll also need to plan for that。 migrating your services to run fully or even partially in the cloud requires work on your side。

 So you'll need to decide if and when to make the leap to avoid your service having an outage because it ran out of resources。

 So with us， you're doing great， We're coming towards the end of the module。

 and I hope you' are as proud as we are of the progress you've made。😊。

You're thinking ahead and learning some seriously important skills that will serve you well out there in the wild。

Which brings us to our last topic， making sure that problems are properly addressed in the long term。

