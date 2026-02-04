# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P14：13_读取数据库文件解决方案（选修部分）第B部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/3d637859a16398a499b921fb6aa22bc6_0.png)

Let's go over the solutions for our lab on reading and data。



![](img/3d637859a16398a499b921fb6aa22bc6_2.png)

The first thing that we're going to do here， we're going to be reading in data from an SQL database。

 So we're going to pull in the SQL 3。

![](img/3d637859a16398a499b921fb6aa22bc6_4.png)

Library， in order to pull in from SQL3 databases， then we are also going to pull in panda's SPD。



![](img/3d637859a16398a499b921fb6aa22bc6_6.png)

![](img/3d637859a16398a499b921fb6aa22bc6_7.png)

So we have all the solutions here， I will bring them out one by one and the cell above。

 the first thing we want to do is create our path。

![](img/3d637859a16398a499b921fb6aa22bc6_9.png)

![](img/3d637859a16398a499b921fb6aa22bc6_10.png)

If we run this， we see that path is just going to be equal to a string。



![](img/3d637859a16398a499b921fb6aa22bc6_12.png)

The next thing we want to do is create a connection called ConN and this is similar to what we saw in our lecture and that's going to just be connected to the database specified in our path and the way that we do that is we use the SQL3 library that has a method called connection and we connect to the path。



![](img/3d637859a16398a499b921fb6aa22bc6_14.png)

![](img/3d637859a16398a499b921fb6aa22bc6_15.png)

![](img/3d637859a16398a499b921fb6aa22bc6_16.png)

![](img/3d637859a16398a499b921fb6aa22bc6_17.png)

All， and we you run this？Oops。

![](img/3d637859a16398a499b921fb6aa22bc6_19.png)

Keyboard went out for a second， let's pull that in。



![](img/3d637859a16398a499b921fb6aa22bc6_21.png)

And then if I look at what the con looks like。

![](img/3d637859a16398a499b921fb6aa22bc6_23.png)

We see it's just an eUite connection。The next thing is we're going to set query equal to this string and similar to before。

 this is just going to be equal to an actual string。



![](img/3d637859a16398a499b921fb6aa22bc6_25.png)

![](img/3d637859a16398a499b921fb6aa22bc6_26.png)

![](img/3d637859a16398a499b921fb6aa22bc6_27.png)

So we have our string and we're going to pass that string in order to get our observations。

 Pada's data frame， which is going to be this output output we just pass in this argument。

 the query itself。

![](img/3d637859a16398a499b921fb6aa22bc6_29.png)

![](img/3d637859a16398a499b921fb6aa22bc6_30.png)

![](img/3d637859a16398a499b921fb6aa22bc6_31.png)

And we also pass in the connection that we established to the database。



![](img/3d637859a16398a499b921fb6aa22bc6_33.png)

So we run that just above to see them one by one。

![](img/3d637859a16398a499b921fb6aa22bc6_35.png)

And we write observations， Let's just take the first five values。



![](img/3d637859a16398a499b921fb6aa22bc6_37.png)

![](img/3d637859a16398a499b921fb6aa22bc6_38.png)

And we see that we have a pandas data frame with all the all star data that's needed from that that was pulled from that SQL query。



![](img/3d637859a16398a499b921fb6aa22bc6_40.png)

The next question is more of a dude on your own at this point。

 so you want to create a variable tables which reads in all data from the table SQL master。

 so it's kind of running through all those steps without laying them out for you。

 so we're just going to be selecting star from the table called EQLite_ master and we're going to run that with this same connection that we established earlier。



![](img/3d637859a16398a499b921fb6aa22bc6_42.png)

![](img/3d637859a16398a499b921fb6aa22bc6_43.png)

![](img/3d637859a16398a499b921fb6aa22bc6_44.png)

![](img/3d637859a16398a499b921fb6aa22bc6_45.png)

![](img/3d637859a16398a499b921fb6aa22bc6_46.png)

And that's going to be all of our tables。

![](img/3d637859a16398a499b921fb6aa22bc6_48.png)

And just to see what that looks like again。

![](img/3d637859a16398a499b921fb6aa22bc6_50.png)

We can just run it like this and we see all the different tables。



![](img/3d637859a16398a499b921fb6aa22bc6_52.png)

We have the table type， the name of the table， root page and SQL。



![](img/3d637859a16398a499b921fb6aa22bc6_54.png)

Query that was used to create the actual data frame。



![](img/3d637859a16398a499b921fb6aa22bc6_56.png)

Finally， this will be a lesson in SQL in regards to seeing if you have everything that you need in terms of pulling in。

 using a more advanced query in order to pull in from SQL and then we're going to attach that using our pandas read SQL function so we wanted to analyze the all-star table to report the top three players in terms of their number of games played and then just to have some type of tiebreaker。

 I know for those that no baseball this probably doesn't make much intuitive sense but still the idea is just to be working with two numerical values in order to come up with some type of ordering we use if there are ties we're going to choose the player with the lower starting average lower starting position first。



![](img/3d637859a16398a499b921fb6aa22bc6_58.png)

![](img/3d637859a16398a499b921fb6aa22bc6_59.png)

![](img/3d637859a16398a499b921fb6aa22bc6_60.png)

![](img/3d637859a16398a499b921fb6aa22bc6_61.png)

![](img/3d637859a16398a499b921fb6aa22bc6_62.png)

![](img/3d637859a16398a499b921fb6aa22bc6_63.png)

![](img/3d637859a16398a499b921fb6aa22bc6_64.png)

![](img/3d637859a16398a499b921fb6aa22bc6_65.png)

![](img/3d637859a16398a499b921fb6aa22bc6_66.png)

So the query was， and we're not going to put this up here because it'll print at the bottom。



![](img/3d637859a16398a499b921fb6aa22bc6_68.png)

We'll do select player ID， sort of selecting player ID。



![](img/3d637859a16398a499b921fb6aa22bc6_70.png)

And we want the most games played， so sum of Game played。

 GP stands for gamess played as and we're going to call that some nu games played。



![](img/3d637859a16398a499b921fb6aa22bc6_72.png)

![](img/3d637859a16398a499b921fb6aa22bc6_73.png)

And then we're also going to pull in the average starting position as average underscore starting underscore position。

 We pulled that from our allstar full table。 We're going to group by player I。

 So we have two aggregation metrics。 We're going group those both by our player I and then we're going to order those by the number of games played first descending So from top to bottom and then average starting position uscending。

 So ideally， if you had a picture they would be first because that would be the position one and then so on and so forth again。

 the positions not meaning much in this context， and then we limit that to three because we only want the top three。

 So we have this more complex query。😊。

![](img/3d637859a16398a499b921fb6aa22bc6_75.png)

![](img/3d637859a16398a499b921fb6aa22bc6_76.png)

![](img/3d637859a16398a499b921fb6aa22bc6_77.png)

![](img/3d637859a16398a499b921fb6aa22bc6_78.png)

![](img/3d637859a16398a499b921fb6aa22bc6_79.png)

![](img/3d637859a16398a499b921fb6aa22bc6_80.png)

![](img/3d637859a16398a499b921fb6aa22bc6_81.png)

![](img/3d637859a16398a499b921fb6aa22bc6_82.png)

And all we got to do the same as any other query is pass that into PDd。readsqL。



![](img/3d637859a16398a499b921fb6aa22bc6_84.png)

Call that best Pass in our best query as well as our connection。 And when we run that。

 it's actually going to be a little bit clear if I write display。



![](img/3d637859a16398a499b921fb6aa22bc6_86.png)

![](img/3d637859a16398a499b921fb6aa22bc6_87.png)

Jiz。

![](img/3d637859a16398a499b921fb6aa22bc6_89.png)

You see the print above， that's when it's printed and below when it's displayed。

 it kind of has that cleaner panda's data frame output。

 we see our three top layers and that's it for this lab。



![](img/3d637859a16398a499b921fb6aa22bc6_91.png)

![](img/3d637859a16398a499b921fb6aa22bc6_92.png)

Thank you。 And look forward to seeing you again in lecture。😊。



![](img/3d637859a16398a499b921fb6aa22bc6_94.png)