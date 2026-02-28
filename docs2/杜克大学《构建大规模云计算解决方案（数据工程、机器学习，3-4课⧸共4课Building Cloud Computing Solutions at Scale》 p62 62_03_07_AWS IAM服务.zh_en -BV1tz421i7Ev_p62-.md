# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p62 62_03_07_AWS IAM服务.zh_en -BV1tz421i7Ev_p62-

All right， let's talk about aIAM service， which is one service that you can use to control your account。

 So one of the things to be aware of about the IAM service is it's a way to manage access to your infrastructure so if you go through and you set up a user account or a group account or role account that all is done so user group or role that's all done with this IAM service and this allows you to manage what resources can be access by who and also how they can access like so who can terminate any C2 instance。



![](img/0fe7ddeef97d5a8abbe39d453356eef9_1.png)

So with IAM， you can do things like manage users and their access， you can create users。

 assign them individual security credentials like access keys or passwords。

 you can also manage IM roles and the permission so you can go through an inside manage which let's say EC2 instance can make a specific API call and you also can have identity federation so you can use things like the corporate directory and hook that up into the AWS security ecosystem so let's talk about some of the credentials that you may come across in terms of the IAM system Well one of them is。

You could come across an email and password and that's how traditionally the root account is actually set up and we'll get into that in a second。

 there's also the IAM username。And with that， that would be for accessing the console。

And then another one is the access and secret keys， so these secret keys。

 what they're used for is for accessing the CLI and also the SDK and these are one of the ways that traditionally AWS accounts are actually compromised is that someone accidentally puts those keys into a source control repository that's public and then instantly gets hacked。

So this is a very important one to secure。And then also in terms of multifactor authentication。

 this is a way of adding an extra layer of security so you could use a phone or you could use a physical device and that is a second layer of security。

 And as we know we've heard in the news a lot， actually the phonebased authentication has been compromised in some situations。

 So really the most secure type of multifactor authentication is to get a physical device that generates a number that can be used。

 And then finally the other one is key pairs。 And so key pairs come up a lot when you're using things like EC2 and we've demoed this previously that would be that PEm file and you can use that to SSH into a machine。

 All right， let's talk about the differences between a root account and an IM account。

 And this is really commonly a mistake that's made at the very beginning is that people use a root account and never set up the IM account。

 So with the root account， some of the problems with it。

Is that you can't control the privileges and people have full access。

 so if you gave everybody your root account and one of the users in your company and I've actually had this before。

 accidentally puts the API keys or the secret access keys into a source control repository instantly your account has been taken over and you can't get it back。

And then in the case of IAM， you have a lot more granular control。

 and so a best practice here is to delete your root keys， never set up root access keys。

And and another thing to do is to make sure that you have a admin account that's set up inside of a inside this IM system。

 and then also that you enable MFA So you you make sure that there's two factor authentication and you use the。

The IAM credentials， not the root credentials to interact with AWS and again。

 this is because the root account is really only a temporary solution until you set up IAM and so when you start using IAM you're able to have a granular level of control and also it allows you to use this principle of lease privilege。

So let's get into authentication a little bit， so what is authentication？

This allows you to authenticate with an ID and an access key。

 and this is one method of authentication， and this gives you again， access to the API。

And it also gives you access to the CLI， the command line tools which we use in Cloud9 and also the SDK。

 so using things like Bodo with Con access， you use your account ID or your alias or your IM username and password and also with the console you can actually use the MFA as well so the console here this would be just a regular authentication and then for the programmatic accesses when you use those keys。

So let's talk about authorization right so authentication gets you in but what about authorization authorization is a way of deciding what services you grant to people and so the way you do that is you use something called an IAM policy and what this policy does is it is a way of setting up what resources a specific group or user can have access to and typically it's a good idea to do this via a group so you could say for example I have students and these students are that's a group and the students have access to read data only from Amazon S3 and then that's the only thing that the students could do and you're following the principle of least privilege so you're not giving people more things in the need that's how most security breach happen is that is that there's two high level of permissions and you grant people resources that they dont。

Don need to have access to。Okay let's talk about MFA a little bit。

 so what is it you may use it on other accounts， it's a way of increasing the security because now you have to log in with two different methods and also with AWS services and resources。

 they can be accessed with the console， the CLI or the SDK and so for an increased level of security if when you use this MFA system。

 this makes sure that users and systems have to be authenticated。

And so there's really a couple different options here。

One of them is a hardware device like and this would be a specific device that you could use that would generate numbers or the other one is you could have a software based device and this would be something where you could associate it with your phone and then your phone would have the ability to generate those credentials so one other thing to be aware of is that AWS has something called the AWS security token service and this is a web service that enables you to request temporary privilege credentials for IM users as well。

Okay so let's go into the I am users section here and talk about that a little bit。

 so this is a entity that you create in AWS and it provides a way of interacting with AWS and so by default there is no default permission so you have to specifically give a user ability to actually do something so a best practice is to create a separate user account with administrative privileges and so that's maybe one of the first things you should do when you set up your AWS account if you're using the free tier account。

 for example， if you're a student and a data science program and you want to set things up that one of the first things you should do is set up a new account。

 that's an administrative account so that you can control it from there and then if you wanted to give somebody else access to your system what you would do is you would set up an account where you give them specifically the privileges that they would need。

So let's talk about groups a little bit， so this is a collection of users and you can specify a permission for a specific group。

 so if let's just say that again this is a group here， a good permission that you could assign。

 maybe would be you can read content from Amazon S3， we know that that's the object storage system。

And so then if you assigned a new user and again， we'll call this a student。

Then you don't have to worry about your data being deleted or that somebody would spin up EC2 instances and you'd be responsible。

 you'll only have to worry about sharing the data with that user that might be a good starting point of privileges so a few different things to point out about a group is that a group can contain more than one user so many users and also a user can belong to many groups。

 but groups can't be nested so they can only contain a user not other groups。And also。

 there's no default group that's automatically included。 You have to specifically create that。Okay。

 let's get into roles here， which are often a misunderstood part of AWS， but basically with roles。

 it's a way of assigning things to specific resources so some of the things that you can do with roles is that you can create these temporary privileges。

And so what this means is that you could assign a role and we could call this AWS comprehend。

 for example。And what this role would do to an EC2 instance is when you spin up an EC2 instance。

That particular instance， when it's launched， let's say you only use it for two hours because it's a spot instance。

 it can make calls to that API for you and do things like natural language processing。

 but you don't have to manage the API keys and put them on the machine and this really solves a very complicated problem because one of the things that could occur in a company is that if you are using API keys and you're passing them around to machines。

 and then someone leaves that company then you would have to go and change all of the API keys on all of the machines。

 because that person if they had access to that machine they could make those same calls and so a better way to do it is do role-based privileges so that particular resource can do a very specific action and then when it goes away you don't have to delete the keys and also when you're changing users in your company。

You don't have to be constantly worrying about swapping keys out so this solves a very particularly complex problem so let's talk a little bit about policies I hinted at those a little bit。

 but basically you can attach a policy to anything from a user can have a policy a group can have a policy and also a role can have a policy and again all these these policies could be something like this user gets access to S3 read this group gets access to S3 read and write。

And then again， with something like a role， maybe we have a sageMaker role and we tell a sageMake instance that we wanted to only have read access to S3。

 we don't want our data scientist to be writing data to S3， because we don't want it to be destroyed。

 so when you're attaching that same policy to multiple IM users， if you notice you're doing this。

 put it into a group instead and then attach the policy to the group。



![](img/0fe7ddeef97d5a8abbe39d453356eef9_3.png)