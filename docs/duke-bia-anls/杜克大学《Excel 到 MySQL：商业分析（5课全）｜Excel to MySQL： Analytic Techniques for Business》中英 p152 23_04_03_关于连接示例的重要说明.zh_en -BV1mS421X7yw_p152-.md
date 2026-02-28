# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p152 23_04_03_关于连接示例的重要说明.zh_en -BV1mS421X7yw_p152-

![](img/07d03e688cd9963a1d773a88badcc743_0.png)

Hi， again。I bet you're really excited to start joining some tables， and I'm excited for you， too。

 I think you're really going enjoy it。 And it's going to be fun。

 but I did want to tell you something before you keep going。😊。

I wanted to let you know that some of the examples I just showed you in the past two videos and some of the examples you're going to use in the rest of this course are not standard。

 You're not going to see them in Escul textbook， for example。

 And the thing that's not standard about them is that I showed you examples that have nu values and duplicate rows in columns that are supposed to be used to link tables together。

In theory， that should be impossible that certainly violates the concepts of set theory， for example。

 which says that there shouldn't be any duplicate rows。

 And if you declare a column to be a primary key in a database。

 it usually prevents you from having any duplicate rows。

 and it prevents you from having any nu values。 So why did I use those examples。

 I use those examples because that's what can happen in real life。

Sometimes companies need to collect data faster than having the perfect database will allow。

Sometimes it's more important to have some imperfect data than to have no perfect data。

 This happens a lot in startups， in particular。Sometimes they don't want to declare a column to be a primary key because they can't risk not collecting any data at all。

 it's too early in the company and they need to make sure they have something。When this happens。

 usually they fix any problems and there's so little bad data that there's no incentive to fix the database immediately。

 they have other things to worry about。I wanted to make sure you knew how to handle these types of situations。

 We're going to see it in our Doognition data， for example。

 it looks like at the very beginning they might have had some issues when they were testing and so some null values and some primary or some duplicate rows snuck in because they didn't declare a column as a primary key this is a very small part of the database and so it usually doesn't affect your analyses where it will affect your analyses is in these edge cases when you're doing these outer joins that have that end up being impacted by these duplicate rows and by these null values because they have multiplicative effects。

As a data analyst， it is not your job to make a perfect database， in fact。

 you're usually not making a database in the first place。

 what it is your job to do is to create value out of whatever data a company has stored in any type of database。

I wanted to make sure you could do that。That's why I didn't clean up the Do dataset set to make it look like a textbook。

 I didn't take out the null values， and I didn't take out the duplicate rows。

 You might want to do that if you're an analyst in that company and you had time。

But I wanted to make sure you knew what to do about it。

And by learning what to do with these edge cases， I do believe that it will help you really understand how joints work。

 which make it much easier for you to use the standard scenarios where data look pristine and there are no problems。

 so I hope you will enjoy this opportunity to use real data rather than textbook data。With that。

 go become join masters。