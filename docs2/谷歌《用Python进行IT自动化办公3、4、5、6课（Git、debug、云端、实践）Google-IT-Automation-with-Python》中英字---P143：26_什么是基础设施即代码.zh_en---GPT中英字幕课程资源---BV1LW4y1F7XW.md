# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P143：26_什么是基础设施即代码.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/520d91b8ab95f611969ea521c571b782_0.png)

We've called out that when we use a configuration management system。

 we write rules that describe how the computers in our fleet should be configured。

 These rules are then executed by the automation to make the computers match our desired state。

 This means that we can model the behavior of our I infrastructure in files that can be processed by automatic tools。

These files can then be tracked in a version control system。Remember。

 version control systems help us keep track of all changes done to the files。

 helping answer questions like who， when and why。More importantly。

 they're super useful when we need to revert changes。

This can be especially helpful if a change turns out to be problematic。

The paradigm of storing all the configuration for the managed devices in version controlled files is known as infrastructure as code or IAC。

In other words， we see that we're using infrastructure as code when all the configuration necessary to deploy and manage a node in the infrastructure is stored in version control。

This is then combined with automatic tooling to actually get the nodes provisioned and managed。

If you have all the details of your infrastructure properly stored in the system。

 you can very quickly deploy a new device if something breaks down。Simply get a new machine。

 either virtual or physical， use the automation to deploy the necessary configuration and you're done。

The principles of infrastructure as code are commonly applied in cloud computing environments。

 where machines are treated like interchangeable resources instead of individual computers。

 This principle is also known as treating your computers as cattle instead of pets。

 because you care for them as a group rather than individually。



![](img/520d91b8ab95f611969ea521c571b782_2.png)

Apologies to anyone with a pet cow。And this concept isn't just for managing computers in huge data centers or globe spanning infrastructures。

 It can work for anything from servers to laptops or even workstations in a small I department。

 Even if your company only has a single computer working as the mail server。

 You can still benefit from storing all the configuration needed to set it up in a configuration management system。

That way， if the server ever stops working， you can deploy a replacement very quickly by simply applying the rules that configure the mail server to the new computer。

 One valuable benefit of this process is that the configuration applied to the device doesn't depend on a human remembering to follow all the necessary steps。

Rest assured， said the human， the result will always be the same， making the deployment consistent。

As mentioned， having infrastructure as code means that we can also apply the benefits of a version control system or VCS to your infrastructure。

Since the configuration of our computers is stored in files， those files can be added to a V C S。

 This has all the benefits that a version control systems bring。

 It gives us an audit trail of changes。 It lets us quickly roll back if a change was wrong。

 It lets others reviewed our code to catch errors and distribute knowledge。

 It improves collaboration with the rest of the team。

 and it lets us easily check out the state of our infrastructure by looking at the rules that are committed。

Not too shabby。I personally think this is one of the coolest things about IACC。

The ability to easily see what configuration changes were made and roll back to a known good state is super important。

It can make a big difference in quickly recovering from an outage。

 especially since changing the contents of a configuration file can be as dangerous as updating the version of an application。

I've had my fair share of outages caused by an innocent looking change， with unintended side effects。

But storing all the infrastructure in a version control system lets me quickly roll back to a previously known good version so that the outage length can be minimized on top of that。

 having the rules stored in files means that we can also run automated tests on them。

It's much better to find out in a test that a configuration file has a typo in it than to find out from our users in a complex or large environment。

 treating your I infrastructure as code can help you deploy a flexible， scalable system。

A configuration management system can help you manage that code by providing a platform to maintain and provision that infrastructure in an automated way。

Having your infrastructure stored as code means that you can automatically deploy your infrastructure with very little overhead。

 And if you need to move it to a different location， it can be deployed。

 deprevised and redeployed at scale in a different locale with minimal code level changes to sum all of this up。

 managing your infrastructure as code means that your fleet of nodes are consistent versioned。

 reliable and repeatable。Instead of being seen as precious or unique。

 machines are treated as replaceable resources that can be deployed on demand through the automation。

 Any infrastructure that claims to be scalable must be able to handle the capacity requirements of growth。

Performing an action like adding more servers to handle an increase in requests is just a possible first step。

 There are other things that we might need to take into account。

 such as the amount of traffic the network can handle or the load on the back end servers like databases。

 Viewing your infrastructure in this way， helps your I T team adapt and stay flexible。

The technology industry is constantly changing and evolving。

 Automation and configuration management can help you embrace that change， instead of avoiding it。

Before diving into concrete examples of what this looks like。

 the first practice quiz of the course is coming up。

These quizzes act as check points to help you make sure all the concepts covered in the videos are making sense。

See you on the other side。