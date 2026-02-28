# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p60 60_03_05_基于AWS IAM的云安全.zh_en -BV1tz421i7Ev_p60-

![](img/57d270e123b113b935f9828020b8d65c_0.png)

One of the more fundamental things that you're going to need to do is create users。

 create groups and create roles。 So let's go through and look at the IAM console and take a look。

 so inside this IAM console you have this ability to again create users groups。

 roles and policies and also you can look at their different credentials。

 So what I'm going to do here is I'm going to go to users and you can see that if I go through and I create a new user。

 this can be， let's say CP user。I have the choice whether I want to give them access to an API so if I'm setting this up for myself。

 this is a good idea I would go through here and select programmatic access and also I want to select whether I want them to have access to the console so depending on what it is you're doing many cases maybe you don't want to give someone on your team access to the console you just want to have them work on a project where they use programmatic access to S3 Likewise it may be the case that maybe you're working with a business professional and they don't need access to the programmatic access keys which introduce the security hole so it's really up to you to decide how you want to set that up now again the principle of least privilege is very。

 very important so let's go ahead and create this user here and we'll give them access to both we'll say CP user。

Next， typically what's a good idea is to then create a group so in this case。

 let's go ahead and create a policy if we wanted to and we could choose which services let's say it's S3 we could say that we want this group to have maybe only read access to S3 and then I could review this policy great it looks fine and then from here I could assign that policy if I wanted to to that user so that's definitely one way to do it another one is I could also just search my policy right so I could either create it by hand or I could go through here and just select an Amazon S3 policy。



![](img/57d270e123b113b935f9828020b8d65c_2.png)

![](img/57d270e123b113b935f9828020b8d65c_3.png)

If we go over here that looks like that is what I want and I can go ahead and again select that once that's selected now I can go through and I can assign that policy if I want to to that group so again with when you're creating these new groups here we would go through here and we'll call this students。

Go go through and say next step and then I could also attach that policy here。

 so we'll use that same thing I was using for S3 access great create group and now that I've created that students group。

 what I can do is I can add a user so I can go through and I can search for a user In this case。

 I didn't create users before so let's go ahead and finish that workflow that I abandoned we'll go through here and we'll call this CP student。

We'll give them， again， access。We'll say next and then we'll assign them to that group that I just created。

 which was students， there we go。And we'll review and we'll create the user now the first time you create it。

 it'll give you access to the ability to download all this as a CSV。 if you want to。

 you can also email those instructions so that's really the gist of it is users groups remember that you should always do group levell permissions when you want to assign a bunch of people the same thing and that allows you to have centralized access of it and it also lets you have a really simple way of taking away control So let's say that that group that you've set up here the CP students it had some problems and there's some people that arebusing their privileges well really easy to change all that I just go to the students group here and I actually go to permissions and I go through and I detach the policy and now nobody in that group has access to do anything so they could still log in even their API keys aren't going to be able to do anything because they have no permissions to read from S3 So very powerful way to take away。

Permissions the final thing I want to show here is a is if you go to roles。

 and this comes up quite a bit if you're let's say you're writing Lambda functions or you're using EC2。

 you're gonna need to give it the correct permissions to make an API call。 And typically。

 that's what happens。 You want to make an API call on your behalf。

 So let's go ahead and do one of those。 Let's let's pick a lambda right。

 That's my favorite way to write code。 We'll pick a Lambda。😊。

And I have to now tell it what I want it to do so for prototyping it's not a horrible decision to give administrator access。

 but you have to be very careful that you're not doing something very dangerous。

 probably a safer approach though would be to very specifically add what it is you want it to do so let's say you're writing a Lambda function that needs to read some data from S3 you just go through again and say S3 read access so maybe it's going to respond to some events。

From S3 rights， and then that's it， and then we would say lambmbda。Roll S3 read， right。

 You give it some kind of a useful role name here so that you can remember it when you associate it with it。

 And you could say， you know， this is a role I set up for giving。My lambda function。Access。

To read from S3， there we go， and we can go through and create this role。

And once you've got that set up now， if I go back to Lambda and let's go through and let's go make a Lambda real quick。

 let's go to Lambda， we can associate that role so if I go here and let's say that Marco function that we wrote earlier。

 I want to make it a little more powerful so a Marco is going to get the ability to talk to S3 how would you do that so you'd look where there's this execution rule and you can see this existing rule that has no privileges and so instead what we're going to do is we're going to find that role。

That we created， which was， I think it was called Lambda。

Rll S3 read and then if I associate this to save it， that's all I have to do。

 And now if I write some code that reads from S3， I've got access。

 So what we did here is we showed how I am rules can associate users groups with certain policies that give them the ability to do something and also we showed how roles can be set up for both EC2 or Lambda functions and again the very big takeaway is principle of least privilege always assign just the amount of privileges you need to do something otherwise that's how you get into big security gaps。



![](img/57d270e123b113b935f9828020b8d65c_5.png)

![](img/57d270e123b113b935f9828020b8d65c_6.png)