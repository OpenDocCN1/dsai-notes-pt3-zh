# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p84 84_04_06_使用Amazon S3.zh_en -BV1tz421i7Ev_p84-

![](img/f2b9188e7103244a47759d464e9719e2_0.png)

Okay， we're back at the AWS management console and what we're going to do is demo how to get data into S3。

 how to synchronize it and how to move it back and forth really S3 is a workhorse for doing operations especially if let's say you data scientist。

 data engineer working in a data science program or just need to do something with a lot of data it's important to know how to use S3 So to start with let's go over to S3 and we'll just type in the word S3 here there we go。

Step1， we need to create a new bucket。 And again， remember that these buckets have a unique name。

 So what we're going to do here is we're going to say a weird name here。 So we'll say big。



![](img/f2b9188e7103244a47759d464e9719e2_2.png)

Blue website name  one， two，34， just for the sake of this demo。

And now what I'm going to do is I'm going to put that in text editor so I can get it later。

 and then I'm going to go through here and just leave everything by default Great， that looks good。

And in this case I don't want to do a website， so I'm going to leave everything private。

 so that way no one can access it except for my account so now that I've got that I've got this big blue website name bucket here。

 how do I get data in there well one of the ways I can do it is just uploading it literally so I'm going to go here and I'm going to upload a file just some random file here we go NBA endorsement data that looks like a good file I' put in there great。

 I've uploaded that next here。

![](img/f2b9188e7103244a47759d464e9719e2_4.png)

![](img/f2b9188e7103244a47759d464e9719e2_5.png)

![](img/f2b9188e7103244a47759d464e9719e2_6.png)

![](img/f2b9188e7103244a47759d464e9719e2_7.png)

I'm gonna leave everything by default because I don't want anyone to have access and I'll leave it as a standard piece of data。

 So this will be available and multiple availability zones and I't I don't have to change anything。

 So let's go ahead and upload that and immediately you can see now have access to it。

 So that's one of the really powerful things about S3 is it's an infinite storage system。

 this could be deep learning training data could be SQL files。

 It could be you know customer data could be whatever it is you need。

 we've got it pretty easy to set up。 Now how do I connect to that and move things around and again。

 this is an infinite storage machine。 So how do I get more data in there。

 Well to do that I'm going again go to cloud9 environment。



![](img/f2b9188e7103244a47759d464e9719e2_9.png)

And in cloud9， what I'm going to do is I'm going to use a command to synchronize that data locally。

 so I'm going to type in AWS S3 syncnc。And then I'm going to put in the name of that bucket。

 so it's going to be S3。And the name of that bucket that was created was big blue website name 12，34。

 and what I can do here is just do dot。And but actually before I do that。

 why don't I create a directory and we'll call make this directory files here。

 I'll CDd into this files directory and you can see it's been created right there。

And then I can go through and run that command and you notice how I put a hashtag right there。

 that's a good way to save a command so you can use it again。

And then I'll use dot and what this does is it puts it in my current working directory。There we go。

 And you can see that that file is already been loaded there。 And in fact。

 I can now inspect it inside of this cloud 9 environment。

 You can see that it's got some CSV data inside。 So how would I get data back and forth and you know work on things Well。

 pretty pretty easy now if I wanted to。I could actually make another copy of this file here。

 let's go through here and we'll make this we'll make maybe there's one file。

 let's make two files here great now I've got a couple files。

 well this could be gigabytes of data or terabytes of data back and forth depending on what machine I'm on。

To get it back over there， I just run that same sync command。

 And what this does is it's going to now make sure that that bucket has all of the latest data。

 There we go。 And so that's a one way sync。 But what if I want to sync it the other direction。

 So all I all I got to do is just swap these two things， let's sync it the other way。

 Let's sync what's in this current working directory。To that directory。

There we go and you can see it's very quick。 it's been able to upload those new files。

 and if I do a refresher， we've got these two new files in there so really powerful workflow to create buckets。

 put things in there， upload them by hand， then open up cloud 9。

 use the command line tools and you can get access to those files and go back and forth using the S command。

 very， very powerful workflow， especially if you work heavily with data。



![](img/f2b9188e7103244a47759d464e9719e2_11.png)

![](img/f2b9188e7103244a47759d464e9719e2_12.png)