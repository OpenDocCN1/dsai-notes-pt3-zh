# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p49 49_03_10_AWS Cloud9导论.zh_en -BV1tz421i7Ev_p49-

![](img/5275a67e56e01bfee3d9e0a5855db33f_0.png)

AWS cloud 9 is a cloudbased I， and you use it for writing。

 running debugging code in the AWS environment。 It's one of my favorite environments because it allows me to get very close to the same kind of an environment that my code will actually be running in。

 that's really the innovation here with these cloud based tools。

 So let's go ahead and create a new environment。 I'm going go ahead and say create a new environment。

 We'll go ahead and call this Devops。 And then it's always a good idea to put a description here。

 So this is。😊，It iss for a DevOs project。And then for the next steps here。

 the important thing to know is that the defaults are a great set of defaults it'll create a new EC2 instance for you。

 it will give you a free tier eligible virtual machine and also it will set up Amazon Linux here which is in Amazon Linux too this would be the recommended environment for running your code and what's great is that when you're going to deploy let's say a flask web application it's going to be running most typically on Amazon Linux too so you really are getting a parodity of where your code will run in production also this is an important thing to be aware of is that with a cost savingaving settings here the default it'll automatically hibernate and save your work and so it's a really efficient way to be developing your code and then this is kind of a neat little secret trick here is that whatever account you're logged in as by default it'll use those privileges so if you're。

ggedIn as let's say a personal account with admin role。

 then it'll allow you to call all of those AWS services for you and this is really powerful because you can let's say look at the buckets and S3 or do invocate or invoke a AWS Lada function from the command line or run sageMaker or whatever it is you need to do so it's a great service integration Now one other thing I'll point out here with the instance type is if you go through here and select other instance。

 you can see that there's some really powerful machines if you start scrolling down here know 128 gigs of Ram 32 core or you can even all the way go up to bare metal machines of course you'll have to pay for that but if you need those resources you can use them in this cloud based environment So I'm gonna go ahead and again leave the defaults go ahead and say next step and then launch this environment and typically it takes let's say 30 seconds or maybe a couple minutes to set this。



![](img/5275a67e56e01bfee3d9e0a5855db33f_2.png)

And then you can get ready to start writing code So what I'm going to do is I'm going to shift over to an environment I've already got set up here。



![](img/5275a67e56e01bfee3d9e0a5855db33f_4.png)

And in particular， there are a few things that are important to be aware of on the right here you can actually go through and invite people to your project so you can actually invite another user by by saying share here and they can actually do pair programming with you on your project this is an incredible feature for you know teams that are working remotely also there's a debugger so I can go through and I can maybe set breakpoints on my code and then and get access to it and likewise another killer feature here is that on the left here you have the environment so this shows you everything that's open with files right so if I start closing these files here you'll see that they'll go away and then also it will let me kind navigate it through and maybe you rightcl and download a file or preview file so there's a very rich integration for the AWS environment。



![](img/5275a67e56e01bfee3d9e0a5855db33f_6.png)

![](img/5275a67e56e01bfee3d9e0a5855db33f_7.png)

Now another thing to be aware of is as I mentioned before in the terminal here。

 if I type in AWS and I type in S3 and I do D help， notice that it has the ability to you know。

 in this case actually AWSS3 help， it will show me that it can go through and do different operations on AWS。

 same thing if I want to type in another command， you know I can go through here and I can type AWS help and it goes through and it gives me all these other ways to interact with the AWS environment。

So for AWSS3， for example， if I type in LS， it'll list all the buckets that I have in my account and I don't have to authenticate。

 I don't have to do anything special， is a really great feature for me now one other thing to point out here is notice that there's a source control tab here and you can see that I have a project already set up so I'm going to go ahead and CDd into that project and I go through here and I do an LS if I type in get info。

I'm sorry， get。Remote dash V， you'll notice that I'm able to see that this is actually a remote repository that I'm poll。

And if I do a very small change here， let's say I go to the readme file。

 I edit this thing a little bit and I say， you know。Making a change， right？Notice that。

I can actually keep track of these changes it'll show me here that I made a change in source control and if I click on this source control tab。

 you'll see that it'll actually let me do a diF and this is a great feature that allows me to also have some of the same tools that I would have in let's say a desktop type。

 you know source control editor and finally if I click on AWS here in this tab。

 one of the nice things about this tab。Is that I can explore all of these other features of AWS including S3 right I can look at the buckets that I have available。

 kind of go through here and navigate you know what's inside of particular buckets and files and things like that which is really powerful and even go through here and download it I also can go to AWS Lambda and this is something that is really a great feature here is that I can actually invoke one of these Lada functions by clicking on it let's go ahead and take one of these things here like I don't know hello world here if I right click on it I could go through here and double click on it and basically tell it to invoke on AWS and actually start to call a specific session maybe use a sample payload like send a kinesis payload for example to it and this allows me to have a really rich integration with a particular environment and even I can send a payload right let's say I have a J。

and payload that I want to send in I can go ahead and do this so you in a nutshell here the AWS environment is really with cloud9 is a great integration and allows you to very efficiently build solutions and and in my opinion it's really the recommended way to develop things on the AWS platform。

 might well use the tools that are designed for the job that you're running。



![](img/5275a67e56e01bfee3d9e0a5855db33f_9.png)

![](img/5275a67e56e01bfee3d9e0a5855db33f_10.png)