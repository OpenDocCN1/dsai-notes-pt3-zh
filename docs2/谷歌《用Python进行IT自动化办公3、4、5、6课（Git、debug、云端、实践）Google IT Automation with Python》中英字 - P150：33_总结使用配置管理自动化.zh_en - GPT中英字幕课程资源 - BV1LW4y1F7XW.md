# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P150：33_总结使用配置管理自动化.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/0f6d5638c8d89503a83a1c0945928c23_0.png)

We started our journey talking about what would happen if you needed to upgrade a package in a fleet of 1 thousand different servers。

If you'd never heard about configuration management before。

 an upgrade like that probably seemed like a super long and boring task， right？

But now you know that there's a bunch of tools you can use to make your life much easier when making large scale changes like that one。

 We've talked about the kind of automation that's necessary for provisioning。

 managing and adapting a fleet of computers in a scalable way。

We called out that an important concept in today's IT world is to treat our infrastructure as code。

 this lets us manage our fleet of computers in a consistent， versionable。

 reliable and repeatable way。To figure out how to get there。

 we've covered a lot of concepts related to configuration management。

Like how these tools use a domain specific language to help us clearly state what we want our systems to look like after the tools have run。

 we've mentioned that the language is declarative because we declare our goals rather than detail the steps to get there。

And most importantly， the actions taken must be item potent so that several runs of the same rules always lead to the same results。

All along， we've been using puppet as an example of how configuration management tools work。

We looked into the puppet DS SL syntax and checked out the most common resources， packages。

 files and services。 learn about other resources and other advanced techniques in future videos。

 But by now， you should have a pretty good idea of what puppet rules look like and how you can put into action。

 the configuration management concepts that we discussed with the concepts we've covered。

 you're probably starting to see how keeping your fleet of machines。

 whether they're virtual or physical， off of a pedestal is good practice。 If something breaks。

 goes down or catches fire literally or figuratively。

You can easily spin up a replacement because you know exactly what it's supposed to look like from the configuration。

 and you can deploy it easily using the automation。In the next module。

 we'll check out how you can deploy puppet in your infrastructure and look into some more advanced configuration management and change management techniques Before that。

 you'll have the opportunity to try out fixing a system where the configuration management isn't doing what it's supposed to。

You'll see what running the puppet agent looks like in practice and find out what's wrong with the deployed rules。

 and then get the automation to behave as expected。Cool， right， let's go for it。

