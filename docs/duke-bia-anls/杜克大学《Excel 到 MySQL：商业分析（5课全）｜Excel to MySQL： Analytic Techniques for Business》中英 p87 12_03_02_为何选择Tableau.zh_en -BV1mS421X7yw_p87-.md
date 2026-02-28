# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p87 12_03_02_为何选择Tableau.zh_en -BV1mS421X7yw_p87-

![](img/48f052d1802bcaec61d96b1919d3ccbc_0.png)

Over the next few weeks， we are going to learn how to use the visualization software tableau to both find and eventually communicate answers to business questions。

Why do we choose Tableau as the software we think you should know by the time you finish this course？

 Well， let's hear from Ryan Mason， Lead of analytics tools in reporting at Square。

 the finance company who made those little square devices you can attach to your phone so that anybody with a mobile device can accept credit card payments。



![](img/48f052d1802bcaec61d96b1919d3ccbc_2.png)

Hi， I'm Ryan Mason。 I work at Square and I'm the lead of the analytics tools and reporting team。

 I ask Ryan， what are the main software tools you use in your job as lead of analytics。

 This is what he said。

![](img/48f052d1802bcaec61d96b1919d3ccbc_4.png)

![](img/48f052d1802bcaec61d96b1919d3ccbc_5.png)

So I'd say that the data that we work with in analytics at Square primarily comes from databases。

 from a variety of different services， ours live primarily in MySQL。

 although to access them we use both MySQL hive and Vertica。

 which is a high performance column store database。

 so interacting with those we have wrappers for writing queries in Ruby and Python that we use to kind of extract data and then interact with programmatically。

啊。And then once we have data to work with， we primarily use Tableau and some people use Excel the most widely used tool for analytics in the world。

Ryan is one of a growing group of data enthusiasts who has made Tableau one of his go to analytic platforms。

 That's because Tableau is an extremely powerful visualization tool that allows you to make visualizations of your data and seconds。

 whereasas other tools， like Excel may require minutes or even tens of minutes to make the exact same visualizations。

😊，Further， one of the things that makes Tableau unique is that when you make these visualizations。

 Tableau automatically uses best practices in visualization science to format the graph view so that you pay attention to the correct things。

It can do this because the founders were world leaders in visualization computer science from Stanford。

You may have noticed that the most recent versions of some more traditional analysis programs like Excel started incorporating more advanced visualization features as well。

 Many say Tableau was the main motivation behind these changes。

Tau was so unique when it started that other companies had to adapt in order to stay competitive。

Although other companies are trying to catch up， Tbau remains the leader in this area。

Especially given my background in neuroscience， I really like this aspect of Tableau。

One of the most important features of the professional version of Tableau is that it can connect to most kinds of databases and import data of insanely big sizes。

 Whereas Excel breaks after importing 1 million rows。 Tableau。

 at least the professional version of it， is ready made for big data。 In fact， under the hood。

 Tableau is actually running many of the same database queries。

 you will learn how to run by hand in course 4 of this specialization。😊。

Let's hear how Ryan describes his use of Tableau。So I use Tableau a couple of times a week and have for many years for me it's the fastest way to turn a table of data into a picture about what's going on and allows me to very rapidly interact with it to understand different slices in different views certainly I could construct all of the things that Tableau generates in SQL queries but manually writing them is quite tedious so what I like to do is start with a fairly large data set load it directly into Tableau interact with it to try and figure out what's going on and then maybe develop by hand some aggregate queries to monitor what's happening or maybe let Tableau do it depending on the scale。



![](img/48f052d1802bcaec61d96b1919d3ccbc_7.png)

Another feature that Tableau is famous for is it's very easy to make dashboards。

 much like dashboards and cars that allow drivers to monitor important things going on with the car。

 Business intelligence dashboards give you at a glance views of key business metrics or indicators real time as they are happening right now。

😊，Their goal is to allow anybody looking at them to immediately know whether something is going wrong or going right with the business。

 They are often designed and configured by an analyst。

 but them published to people all over the company so that everybody can keep an eye on them。

Programs like Tableau allow for these dashboards to be interactive so that people all over the company can play around with them and get a feel for what the data look like。

Here's an example of what a business dashboard might look like。

This is a sales dashboard from the Tableau website。

 The most important information is up here at the top， where it will get the most attention。

 You can see the total sales， the number of deals， the average deal size and the revenue per salesper。

But， of course， there's a lot of other interesting information on the dashboard as well。 Over here。

 you can see the revenue over time for each year， individually。You can also see the running total。

 And again， if you hover over， it even gives you more data。downown here。

 you see the sales team performance so you can actually see how each person on the sales team is doing。

😊，And over here， you have the revenue per quarter。Now。

 perhaps the most important part of this dashboard is that it's interactive。

 So anyone looking at this dashboard can change and play with the data to get exactly the information they need。

 App。 you can change the date。And the dashboard automatically updates to show you exactly the data you're asking for。

You can also change the country or the region。 let's say we just want to look at Latin America。

Or the sales team， let's say we just want to look at the enterprise sales team。

Each time the dashboard automatically updates and tells you exactly the information you've asked for。

This is a very powerful tool。As you can imagine now， after seeing one。

 dashboards of the potential be very useful and compelling tools for companies。 Let me tell you。

 especially when they are linked to databases， they can also save an analyst a lot of time and become an analyst's best friend。

😊，Let's hear what Tableau's dashboard functionality did for Ryan。

So we use both Tableau desktopk and Tableau server。

 so I think my favorite feature is that I can at one point do an analysis， build a dashboard。

 publish it on the web and allow people to interact with it whenever suits them with data that refreshes on a reasonable time scale so I can build something once and make it available and refreshed all the time so before I use Tableau I had a job where I had to every Monday run a bunch of SQL queries and copy and paste the data into Excel and then run pivot tables on it and then email it to someone so I got back quite a lot of time by being able to say here is a dashboard that has all of this information it's available whenever you want。

And then I also helped work on a tool to take a screenshot of that dashboard and email it to people so that they could get it in their inbox。

You heard Ryan talk about Tableau desktoptop and server and me talk about the professional version of Tableau desktop。

There are many different versions of Tableau， all the slightly different capabilities。

 There is a completely free version called Tableau Public。

 which includes a tableableau public interface you can have on your desktop。

This version lets you do almost everything the other versions can do。

 but your data can't have more than 1 million rows。 You have to save your data to their website。

 not your desktop， and you cannot connect databases only to Excel spreadsheets。

 text files and Microsoft access files。In my experience。

 connecting to really big data files can also sometimes be a bit slow。

There are also paid tableableau desktop versions， one for personal use and one for professional use。

 These both allow you to save data and workbooks to your desktop and have ways to share your work with others via online tools。

Luckily for us， Tblow has donated Tableau desktop subscriptions to our course。

 So you will get to experience firsthand how to use them。😊。

In addition to saving files to your desktop with a normal subscription service。

 the personal version allows you to save data to Tableau On， Tableau Ser in the cloud。

The professional version is the only version that can connect to databases and therefore is really the only one that can efficiently handle those really big specialty data sets。

 It is also the only one that can connect to Tableau Ser。

 Tau Ser is basically a way to share things locally at your own company in a very secure and controllable way。

No matter what version your company has available， Tableau is a very powerful tool that will dramatically improve the efficiency of your analyses。

 it will help you clean your data， find patterns in your data， test your hypotheses。

 and tell stories with your data。We've dedicated so much time to it in this specialization。

 because no matter whether you have a very strong， quantitative background or no quantitative background at all。

 we truly believe Tableau will provide a lot of new value for you。 With that。

 Are you excited to become a tableableau expert， I hope so。😊。



![](img/48f052d1802bcaec61d96b1919d3ccbc_9.png)