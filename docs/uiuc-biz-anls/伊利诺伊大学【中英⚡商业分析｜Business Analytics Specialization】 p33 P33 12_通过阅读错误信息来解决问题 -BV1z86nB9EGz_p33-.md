# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p33 P33 12_通过阅读错误信息来解决问题 -BV1z86nB9EGz_p33-

![](img/387d5fbb51508d3d7b19fb176a2d79cf_0.png)

Let's talk about error messages。 Now， error messages may be scary because they are red。

 They' are sometimes filled with a lot of technical information that you don't understand。

And you may have had experience with error messages in the past that have resulted in corrupted software or broken hardware。

 And you may have lost something。 So it brings up some negative feelings with them。Well。

 in this video， I want to encourage you to think of error messages when dealing with Python for data analytics as learning opportunities。

But I want to share with you some tips so that you can learn the most from them。

 So let's look at some concrete examples。I am using Python in this Jupiter lab environment to import functions from the pandas module。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_2.png)

Read in data in a receivables file that。Is stored as a comma separated value format。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_4.png)

And then I'm displaying this data frame here， and I've got this quantity column。

And then I want to add up the values in that quantity column and save it as a variable total quantity and use that variable to return a string or a sentence。

That tells me the total quantity。Now， as you look at this， you'll notice that。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_6.png)

The variable total quantity in here is a little bit different because it has two underscores。

 So when I run this， I'm going to get an error。

![](img/387d5fbb51508d3d7b19fb176a2d79cf_8.png)

Okay， so here's the error and this brings me to my first tip。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_10.png)

The first tip is to read error messages， no longer just to think of it as a red light that means it didn't work。

 And then you ask someone else。

![](img/387d5fbb51508d3d7b19fb176a2d79cf_12.png)

Go ahead and read the error message。

![](img/387d5fbb51508d3d7b19fb176a2d79cf_14.png)

But this brings me to my second tip。 when you read error messages。

 don't read them from top to bottom。 Read them from the bottom to the top。

 The most useful information is usually at the bottom。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_16.png)

And even if you don't know exactly what it means， you might be able to discern enough to understand what is happening。

 So this tells me that there is a name error。 The name total quantity is not defined。 Okay。

 that should make sense， given that I told you that we have an extra underscore in this variable total quantity。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_18.png)

![](img/387d5fbb51508d3d7b19fb176a2d79cf_19.png)

![](img/387d5fbb51508d3d7b19fb176a2d79cf_20.png)

And then as you go up further， it tells you the line that it's on and additional information about the cell that it's in and the line in the cell。

Okay， and then something that may not make sense， trace back most recent call last。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_22.png)

All right。So it looks kind of scary， but it's really not bad， right， Okay。

 so those are the first two tips。Let's look at another type of error message I'm going to try reading in a CSV file and saving it as a data frame。

But I'm going to use the read Excel function。On a CSV file。 and that's not going to work。

 So when I run this。I get a pretty long error message here。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_24.png)

And this brings me to my third tip。 Feel free to ignore a lot of the error message。 Okay， so again。

 we'll start from the bottom and work our way up。

![](img/387d5fbb51508d3d7b19fb176a2d79cf_26.png)

![](img/387d5fbb51508d3d7b19fb176a2d79cf_27.png)

Says value error， Excel file format cannot be determined。 You must specify an engine manually。

 The key thing is that it may be enough for you to recognize that， oh， yeah。

 I'm using read Excel on a CS SV file。 if， if you go up above that， you can certainly try。

 But if it starts getting too technical， then ignore it。

 A lot of the times all this in here is going to be for software engineers and developers。

 And so feel free to ignore a lot of what is in error messages。

 The fourth tip is to keep in mind that with experience。

 error messages will be more meaningful for you。

![](img/387d5fbb51508d3d7b19fb176a2d79cf_29.png)

![](img/387d5fbb51508d3d7b19fb176a2d79cf_30.png)

![](img/387d5fbb51508d3d7b19fb176a2d79cf_31.png)

Initially， you'll get some error messages that won't make sense to you。

 but as you see them more often， then they'll start making more sense。

 So just recognize that you will learn from experience。 All right。

 those are the tips for learning from error messages。

 make sure to use them as learning opportunities， and you'll find that they'll provide some really valuable information to you for answering your questions about using Python code。



![](img/387d5fbb51508d3d7b19fb176a2d79cf_33.png)

![](img/387d5fbb51508d3d7b19fb176a2d79cf_34.png)