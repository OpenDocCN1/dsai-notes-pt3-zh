# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p50 50_03_11_AWS Lambda事件处理.zh_en -BV1tz421i7Ev_p50-

![](img/6022a8bb6730f6f20a80b044923d0934_0.png)

Let's go ahead and look at triggers and events here and in AWS Lambda in the console。

 you can notice that this API gateway is triggered but if I wanted to add a different kinds of trigger but went ahead and selected。

 for example， an S3 trigger。If we can go down here and find it。

 what it'll do is it'll ask me to list the bucket。And then also ask me to list what kind of event I'd want to monitor and then I could do things like look for images。

 for example， and then invoke a lambda function So what we're gonna to look at next here is an example of how to use something that does that kind of a trigger so in this particular repo I have some code here and we can take a look at it and what it does is it finds in particular the labels for an image that you put into a S3 bucket so we drop an image inside it goes through it uses the AWS recognition detect labels command and then it goes through and prints out those labels and then inside of this lambda handler what happens is that it listens for the event of an object being placed inside of the bucket so this is a great pattern here that can be used for many different kinds of applications and we can actually take a look at。

In action by going over to this particular lambmbda so let's go ahead and scroll over here and find that particular lambmbda here we go S3 bucket label and what's great about this is if I look through here I can just you see the same piece of code and in particular we can actually see where this S3 trigger is set up if I go through here notice that it says it's on object creation。

And actually the Lambda is called is called on the particular bucket Lambda trigger demo Duke okay let's go ahead and find that out so what I can do is I can open up a new console window here go to S3 and then find that particular bucket so let's see here I think it had the word Duke in it so let's go ahead and find this and here we go Lambda trigger demo Dukeke we can see that there's already a couple pictures in there where I've tested it earlier so I'm going to go over to this picture of of a tiger here and I'm gonna to go ahead and download this we'll go ahead and download this picture here Sure let's go ahead and do this go ahead and put that thing down great and now if I go over to this bucket and I again go ahead and drop an image in there let's go ahead and say upload I can select from the downloads that I just added okay here。



![](img/6022a8bb6730f6f20a80b044923d0934_2.png)

![](img/6022a8bb6730f6f20a80b044923d0934_3.png)

![](img/6022a8bb6730f6f20a80b044923d0934_4.png)

![](img/6022a8bb6730f6f20a80b044923d0934_5.png)

We go。We can go to that downloads directory， here's the picture and。



![](img/6022a8bb6730f6f20a80b044923d0934_7.png)

Go ahead and say upload perfect all right so it's uploading inside of this directory and then the next thing that I can do is actually see how it actually was called so if I go back to this Lambda the way to verify what it did is to look on the monitor window and then say view logs in CloudWatch。

And then this will allow us to see those print statements that show exactly what it did。

 So here we go， look here's the name of that file， Pels flickickr14。

5939 and notice that it said it found these labels and these labels are exactly the labels I would expect know it's a tiger。

 It's wildlife and it's able to automatically do those actions Now later maybe you would want to put this in some other location or put it into a database。

 but in general that's how a bucket works and in fact we can even look at this in action if I go to this diagram that I've got here which is serverless image label trigger and this is really what's going on as we have a bucket I drop this image into the bucket it goes it sets up that trigger we're able to use the recognition API it goes through and then writes off that computer vision label to some other location again。

 it could be a database it could be another S3。And one final thing to show here is if I go back to my cloud9 environment。

 I can select AWS and I can find that trigger， which again is called S3 bucket trigger S3 bucket label let's just double check that's the one we want S3 bucket label that's the one we want and if I right click on this I can say import and what import does is a pretty cool little command here is that it will grab that external function and actually pull down the source code right inside of my local environment and take a look at this inside here we can see that I've actually now have the capability to edit this if I wanted to even copy if I had special test functions inside of there it would put those inside of there So this is one of the great workflows is the ability to not only put things up into the cloud with cloud9 but also to test them like。

We just did and also to pull back into cloud9 and edit it。



![](img/6022a8bb6730f6f20a80b044923d0934_9.png)

![](img/6022a8bb6730f6f20a80b044923d0934_10.png)