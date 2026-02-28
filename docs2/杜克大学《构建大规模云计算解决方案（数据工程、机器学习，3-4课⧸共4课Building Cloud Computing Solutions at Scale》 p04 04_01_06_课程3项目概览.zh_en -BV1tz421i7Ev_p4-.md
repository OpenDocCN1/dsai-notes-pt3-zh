# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p04 04_01_06_课程3项目概览.zh_en -BV1tz421i7Ev_p4-

Let's walk through the project overview of what will be built in this course First you're going to create a serverless data engineering pipeline。

 this will allow you to leverage the best practices in cloud computing and also take advantage of emerging technology Let's go through an overview of what that looks like。



![](img/a7ea1880a70997ac1a682e6933f37c53_1.png)

![](img/a7ea1880a70997ac1a682e6933f37c53_2.png)

You can see from this diagram at the very beginning there's a timer that kicks off the initial run of the serverless job Next。

 the producer Lambda will pull some data from a serverless database dynamodDB and then put that information into a QSQS later the queue will automatically fire off a Lambda function that's listening there's a one to one correspondence between a message that goes in the queue and an invocation of this Lambda function and then you'll go through and perform sentiment analysis using the AWS comprehend API and then put the result into an S3 bucket so this is a very typical serverless AI pipeline that you can build yourself and this will be the final project that you'll build out in your portfolio。



![](img/a7ea1880a70997ac1a682e6933f37c53_4.png)