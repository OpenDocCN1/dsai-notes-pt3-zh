# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p06 06_01_03_Python并发编程的问题.zh_en -BV1tz421i7Ev_p6-

![](img/2f2b87c2d68b511326e5669b5c436f26_0.png)

So what is the deal with Python and concurrency Well。

 let's go back to the dawn of the Internet back in the 90s When I was in high school。

 I remember using a dial of modem that was so slow that it would take an hour to download an image。

 Now we take that for granted。 you can do a Google search for images and you get millions of images that appear and they take a millisecond to download。

 But back then we didn't have that level of speed or concurrency and really there was no concept even of multicore machines。

 And so Python implemented a shortcut called the gill。

 And what the gill does is it locks the threads in Python to one core。

 Now when you have one core in your machine that's not a big deal。

 but if you have 48 cores or 128 cores or some huge amount of cores。

 now all of a sudden you have a problem in terms of the ability to use those resources and so Python doesn't really become a good fit for certain kind of problems that are server problems。

This reminds me of a time in my career when I worked for a software as a service company and we dealt with big data and we had a really top notch developer work over the course of nine months developing a asynchronous or network asynchronous Python server that accepted a very high level of requests per second。

 let's say around 10000 requests per process， which is incredible but the problem was when you ran it on a machine that had four cores。

 only one of those cores was able to be utilized。 and so we were wasting。

 we're spending essentially four times more money that we needed to spend because we couldn't use the rest of those cores。

 So eventually what we had to do was use a different process。

 used a different language that was able to support the true level of concurrency。

 So that's really the issue with Python is that。I would not recommend using it to build servers with。

 but what you can do is use the cloud to do the level of concurrency for you so by using things like AWS Lambda and SQS。

 you can build a very concurrent system almost treating the cloud like it's its own operating system and really that's the takeaway with Python and concurrency is don't do it yourself。

 use another system like cloud computing to handle all of the important details。



![](img/2f2b87c2d68b511326e5669b5c436f26_2.png)