# 纽约石溪大学【中英⚡数据科学｜CSE519 2024 Data Science Fundamentals】 p19 P19 Lecture 5： Correlation (Fall 2024) -BV1s7Gaz5ETS_p19-

Okay， the clock on here now says 9，30。 So we'll start。 First of all。

 are there any questions about anything on the homework， Okay， yes。



![](img/031b428ad3fa5f74f141ae9be1874cec_1.png)

And the。

![](img/031b428ad3fa5f74f141ae9be1874cec_3.png)

Second can year as to。Bnk company， according to。

![](img/031b428ad3fa5f74f141ae9be1874cec_5.png)

Its a good measure。はい。

![](img/031b428ad3fa5f74f141ae9be1874cec_7.png)

like some like w。FTV， they have red date。

![](img/031b428ad3fa5f74f141ae9be1874cec_9.png)

With the time steps。So it's date and time in the date column of prices are CB。

 and the other no is they don't have any timet mentioned， but they just have the dates mentioned。



![](img/031b428ad3fa5f74f141ae9be1874cec_11.png)

So when I try to filter the data， these two companies are some that are not being able to get filtered because of the extra time they have。



![](img/031b428ad3fa5f74f141ae9be1874cec_13.png)

在一分。

![](img/031b428ad3fa5f74f141ae9be1874cec_15.png)

他就是在。说给这个。Do finders and data them use it to extract the dimension。



![](img/031b428ad3fa5f74f141ae9be1874cec_17.png)

Then it is converted to not time automatically and the aero course。

 so like I'm not able to filter these two companies out because of the extra time times they have。😊。



![](img/031b428ad3fa5f74f141ae9be1874cec_19.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_20.png)

Okay， so I' here are a couple of different things in the question。

 So let me start with what I think I hear and then if I'm wrong， I want you to correct me again。

 The first question is one is the what I want you to do in one of these parts is to order the companies by how interesting they are and the reason for this is okay。

 here's your question， I don't know how much people know about the stock market。

 how many companies are in the S&P 500。

![](img/031b428ad3fa5f74f141ae9be1874cec_22.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_23.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_24.png)

Okay，500， I think that's a little trick。 I think it may be for some reason when I do these things。

 I think it may be a little bit of a rounding error on that， but it's big O of 500。 we agree。

 and some of these companies you have heard of and some of these companies you haven't。

 and I think that it is good for your you know to look at these things if you have companies you care about okay it will look more like just random numbers the random numbers than if you're looking at you know the 495th the biggest company which very well you may never have heard of。

 So that's why I want you to rank these based on how big and interesting they are。



![](img/031b428ad3fa5f74f141ae9be1874cec_26.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_27.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_28.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_29.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_30.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_31.png)

Now your question here was saying something， I think。

 that in this data set there was some kind of an artifact where two of the companies in there had like an extra data field or missed a date field。

 is that right sorry the？😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_33.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_34.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_35.png)

Exact。Yeah， these are the legal companies that I could see。

 they were not getting journal out because I was okay， so what I think you're saying and again。

 correct me if I'm wrong， is that however the guy built this data set on a couple companies he or she left what you call a timestamp。

 which they didn't done the other companies。

![](img/031b428ad3fa5f74f141ae9be1874cec_37.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_38.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_39.png)

And the question is what do I do with it， okay， could I throw these companies out。

 that's I guess part of what you're saying saying your pandas couldn't read it， throw them out， okay。

 is there another way around this problem yeah？😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_41.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_42.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_43.png)

Okay， so you're saying coerce them into a date time object。

 or I would say go through and delete the time field。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_45.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_46.png)

O。That that I can kind of imagine， I mean， and maybe I don't know if this is a twogbe answer。

 So let me know。 but if you're telling me that there are a bunch of records that were kind of scraped by this whoever assembled this thing。

 and for some reason they scraped two of the companies in a slightly different way。

 one possibility might be to clean up the artifact that was introduced。



![](img/031b428ad3fa5f74f141ae9be1874cec_48.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_49.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_50.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_51.png)

Before you go and do your regular processing。

![](img/031b428ad3fa5f74f141ae9be1874cec_53.png)

So I guess think about it。Again， the timestamp here I mean it significant we exact but if there was a data that times are delete that Okay。

 would it be wrong to delete the timestamp we will talk about data cleaning I believe next week it happens to be something I like okay but there is this question here of what should you。

 you know， this is a good example of what is a cleaning problem Okay。

 the guy who assembled this data set was。😊。

![](img/031b428ad3fa5f74f141ae9be1874cec_55.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_56.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_57.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_58.png)

Did something dumb and left a timestamp in there for some reason。 Okay， and， you know。

 what do you do with it。

![](img/031b428ad3fa5f74f141ae9be1874cec_60.png)

It sounds to me from what you're saying that this timestamp doesn't really convey that much information。

 and if so， then it should probably be dispatched， okay。

 but that's a question of understanding what it is and why it's there。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_62.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_63.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_64.png)

So you guys figure it out。 you tell me if you know if this， oh my God， this is it could be。

 oh my God， this is such an error， if we include these companies in any way。

 it will ruin all the analysis， okay， that these two companies are based on Mars and in Mars。

 they have a different time system and。😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_66.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_67.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_68.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_69.png)

It could be that it ruined everything。 in which case youre right dropping the company。



![](img/031b428ad3fa5f74f141ae9be1874cec_71.png)

It could be that this was a processing artifact and that if you delete this column。

 it makes this field， it makes no difference， okay and then you can treat them all the way that you treat everybody else。

😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_73.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_74.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_75.png)

And this is a judgment call。 I'm not going to tell you one is right and one is wrong。

 This is why I want these assignments to be somewhat open ended。 Okay， and again。

 the hope is over the course of the semester， we developed better and better judgment。 Okay。

 any questions。😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_77.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_78.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_79.png)

Any other questions about the homework？O。How many people have gotten started on it？😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_81.png)

See some twitching， have you not gotten started on it？

I recommend getting started on it okay because you know because you know。

 especially if your skills in Python and data exploration are relatively limited， okay。

 this will take longer than you think it will， Any questions？



![](img/031b428ad3fa5f74f141ae9be1874cec_83.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_84.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_85.png)

Oh and one thing that I will tell you when it comes to taking longer than you think it will， okay。

 one principle for this analysis in this course it's very important is this phenomena called kiss。

 does anyone know what the acronym Ki stands for？😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_87.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_88.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_89.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_90.png)

What was it， keep it simple， come as stupid， okay， that means you， okay？

It's important that when you're doing these things。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_92.png)

You make a， I would say， make a quick pass through this， okay， and do something quick。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_94.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_95.png)

Before you you know， but set up a pipeline so later you could optimize and fix something if you later have more time for doing it or something like that。

 so this question on the fields， okay is a good example of this somehow。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_97.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_98.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_99.png)

If he comes， if he came and encounter this thing and said， oh my God， okay， I can。

 My thing can do 498 of the companies。 It can't do 500 of the companies。 What should I do。

 Should I sit and agonize， Should I wait there I can as professor in class。



![](img/031b428ad3fa5f74f141ae9be1874cec_101.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_102.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_103.png)

The answer is what's the simplest thing to do？

![](img/031b428ad3fa5f74f141ae9be1874cec_105.png)

Probably it was to drop the other two companies， right， and you move on and later on。

 if he now has an idea how to rescue them，😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_107.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_108.png)

He can go and fix this up later and come back and do that。

 so I strongly encourage people to keep it make a quick pass simply through everything rather than get stuck on doing。

 making sure everything is right， or done with the greatest possible depth okay Any questions about that。



![](img/031b428ad3fa5f74f141ae9be1874cec_110.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_111.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_112.png)

Any other questions about the assignment？Prices and their just a crisis of the。ああ。

They will have different， right？Okay， so he say that there is a data set that is called prices and there is a data set called adjusted prices。

😡。

![](img/031b428ad3fa5f74f141ae9be1874cec_114.png)

What is the difference， the difference is one of them is adjusted Okay now what does that mean Okay。

 again， there's this phenomena in stocks of stock splits。



![](img/031b428ad3fa5f74f141ae9be1874cec_116.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_117.png)

That when you have a what you call， when you have a stock price that gets too high per share。



![](img/031b428ad3fa5f74f141ae9be1874cec_119.png)

Companies for。To encourage more investors to make it seem more reasonable will instead take one of their old shares。



![](img/031b428ad3fa5f74f141ae9be1874cec_121.png)

And divide it into three or five or seven or two new shares。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_123.png)

And they will take your old share and give you three new shares in exchange。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_125.png)

Now what's the result？😡，What is the change in value to you？😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_127.png)

Nothing， it's the difference of， you know， you know， I have I had a $10 bill。

 I give it to the bank they give me $101 bills am I richer， okay， the answer is no。😡。



![](img/031b428ad3fa5f74f141ae9be1874cec_129.png)

![](img/031b428ad3fa5f74f141ae9be1874cec_130.png)

But if you now want to compare the price。😡。