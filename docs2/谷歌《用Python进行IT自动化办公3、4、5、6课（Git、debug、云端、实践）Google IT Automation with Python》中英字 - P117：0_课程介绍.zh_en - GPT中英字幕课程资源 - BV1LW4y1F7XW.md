# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P117：0_课程介绍.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/5ead660b698e371bd96b4f17a4ea8c89_0.png)

Say you're in charge of a fleet of servers。 Everything is full steam ahead until one day。

 you discover that there's a security vulnerability in one of the applications used。

Now you need to upgrade all the servers to the latest version。If you have 10 servers in the fleet。

 it's probably not too much trouble to log into each one of them， one after the other。

 and install the new version。But what if you have 100 servers。

 this would get super boring and you'd likely end up making mistakes。

 leaving some servers with the wrong version installed，Now， imagine having to do this on10 servers。

 There's no way you're going to log into each of them to upgrade the software。

 So what can you do instead？In this course， we'll look into how we can apply automation to manage fleets of computers。

 We'll learn how to automate deploying new computers， keep those machines updated。

 manage large scale changes and a lot more。We'll discuss managing both physical machines running in our offices and virtual machines running in the cloud。

If this sounds overwhelming， don't worry。 I'll go step by step with you along the way。

 I'm feeling Vdeville， and I'm a site reliability engineer at Google working on the team that supports Gmail。

If you've never heard about site reliability engineering before。

 let me tell you a bit about what we do。SREs focus on the reliability and maintainability of large systems。

 and we apply tons of automation techniques to manage them。

This lets teams with only a handful of engineers have a big impact。

 scaling our support as our service grows。We're small， but mighty。

 My job includes a lot of different tasks。 Sometimes I spend my time collaborating with partner teams on the reliability aspects of a cool new feature。

 like scheduling emails to send at a later time on Gmail。 All days， I write software。

 creating tools that help automate how we manage the service。And when I'm not doing that。

 I might do research or architectural design for a new project。

I'm also part of the on call rotation for the service。If problems come up when I'm on call。

 I'm in charge of fixing them or finding the right person to fix them if I can't。

 So what will we cover in this course？We'll start by looking into an automation technique called configuration management。

 which lets us manage the configuration of our computers at scale。Specifically。

 we'll learn how to use puppet， the current industry standard for configuration management。

We'll look at some simple examples and then see how we can apply the same concept to more complex cases。

You'll be a puppet master in no time。Later on， we'll expand our automation skills by looking into how we can make use of the cloud to help us scale our infrastructure。

We'll learn about the benefits and challenges of moving services to the cloud。

 We'll check out some of the best practices for handling hundreds of virtual machines running in the cloud。

 How to adapt our services to that and how to troubleshoot them when things don't go according to plan。

Heads up。They rarely do。Before we move on， I should probably tell you a little bit about myself。

I discovered I was interested in IT and technology as a teenager。

So when I decided to enlist in the Navy right after high school。

 I signed up to be an information systems technician there。

I served in the Navy for four years supporting IT and networks resources around the world。

 After leaving the Navy， I went to college and then joined Google in the IT support department。

The transition from working in a very structured environment like the military to a place like Google was initially a bit hard to wrap my head around。

 I had to become much more comfortable in dealing with ambiguity in the problem spaces that I was working in。

 which meant learning to trust my own sense of judgment and prioritization。😊，All along the way。

 I kept learning new skills and growing as a person and an engineer。

So I'm excited to be here to help you take the next step in your IT career to help you keep growing your automation skills by learning how to manage fleets of computers using configuration management and how to work with the cloud。

Modern I is moving more and more towards cloud based solutions and having a solid background in how to manage them will be even more critical for it professionals in the future。

 In this course， we'll use quicklabs， which is an environment that allows you to test your code on a virtual machine running in the cloud。

 This lets you experience real world scenarios。 where you'll need to interact with one or more remote systems to achieve your goal。

 We'll build on top of the many tools that you've learned about throughout the program。

 like using Python for automation scripts， using Git to store versions of code or figure out what's going on when a program doesn't behave as expected。

 You'll see some complex topics and videos that may not 100% sync in the first time around。

 That's totally natural。 Take your time and rewatch the videos a few times if you need to。

 You'll get the hang of it。😊，Also， remember that you can use the discussion forums to connect with your fellow learners and ask questions anytime you need。

We're about to begin our journey， learning how we can apply automation at large scale。

 So let's get started。