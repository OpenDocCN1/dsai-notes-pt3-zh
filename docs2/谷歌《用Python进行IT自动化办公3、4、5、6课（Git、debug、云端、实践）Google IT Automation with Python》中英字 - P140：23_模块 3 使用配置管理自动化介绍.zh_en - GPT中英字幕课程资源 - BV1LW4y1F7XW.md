# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P140：23_模块 3 使用配置管理自动化介绍.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/31704a256857bcc4dbaa423f2a16c5aa_0.png)

No matter the size of your team or the number of computers in your fleet。

 knowing how to apply automation techniques will enable you to do your work much more effectively。

 As I shared earlier， I'm part of the site reliability engineering team that supports Gmail。

 My team is relatively small， but the service is pretty big。😊。

Without scaling our efforts through automation and tooling。

 it would be impossible to help Gmail meet its reliability goals。

And while you're probably not supporting such a large scale service right now。

 you'll definitely benefit from using the right automation for your needs。

Being able to automate the installation of new software。

 the provisioning of new workstations or the configuration of a new server can make a big difference even when you're the only person in your IT department In the coming videos。

 we'll kick things off by looking at some important automation concepts like what we mean when we talk about scale and how we can use configuration management to maintain the computers in our fleet and how we can all benefit from treating our infrastructure as code。

These concepts are the building blocks for letting us manage a growing number of devices without having to grow the team in charge of them。

 We'll then get to our first taste of puppet， the configuration management tool that we willll be teaching you throughout this course。

 We'll check out a bunch of different examples to see what puppet rules look like。

 We'll also learn about the underlying concepts and how you can get it to do the heavy lifting for you。

The concepts that we'll check out throughout this module will help you take your first steps in automating at a larger scale。

Knowing how to automatically manage the configuration of the devices in your fleet will let your team handle a lot more work with the same amount of people。

It also frees up time to do more interesting stuff since all the boring tasks can get automated by the end of the module。

 you'll have the skills to fix a bug in existing automation， which is great news。

 since that's exactly what you're going to do with code we provide。 Funny how that works， isn't it？

 Almost like we planned it。😊，Let's dive in。