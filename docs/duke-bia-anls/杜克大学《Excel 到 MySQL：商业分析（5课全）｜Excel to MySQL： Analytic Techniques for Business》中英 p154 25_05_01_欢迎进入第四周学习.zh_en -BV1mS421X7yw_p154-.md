# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p154 25_05_01_欢迎进入第四周学习.zh_en -BV1mS421X7yw_p154-

![](img/365136c0df736e49487bdea3579f2269_0.png)

Yeah。Welcome to the final week of managing big data with MySQO and Terraadata。

You have done a terrific job working through all the exercises that teach you how to write SQL queries。

 This week， we are going to learn a couple of additional tools that will make it easier for you to write queries that extract the specific data you want。

The first thing you are going to learn is how to write subqueries。 Subqueries。

 also known as inner queries or nested queries， are mechanism for breaking up the operations in an overall query into separate steps。

 By doing this， subqueries help solve a lot of problems we encountered with aggregation functions and joins and sometimes provide us with more elegant ways to represent the logic behind our set queries。

😊，You'll see that the first trick to subquaries is making sure you format them so that it's easy to see which parts of the query will be executed together。

The second trick is to write and interpret the subqueries starting with the innermost query first。

 working your way out step by step to the outermost query。

You will already know how this works after completing the first exercise of this week。After that。

 we will learn about a couple other logical functions that you might want to use in your analysis of business data。

 Then in the last phase of this week's assignments。

 we are going to talk about how to translate your analysis objectives into questions that can be addressed through queries。

 The first thing you need to do in order to accomplish these objectives is figure out the right questions to ask and come up with a plan about how you are going to answer those questions efficiently。

Here's Eliliot Cohen again， producer Dogogniian， giving us his opinion about how important this part of the analysis process is。



![](img/365136c0df736e49487bdea3579f2269_2.png)

The most important thing that we' found is that you have to go into every test with a question。

 you need to have a hypothesis and you need to know exactly what you're doing to test that because if you're just going in and looking。

 you're not going to either going to find things that don't matter。

 which is useless or you're not going to find anything which is equally useless。

 so find a testable hypothesis before you go in is the only really important thing I'd say。



![](img/365136c0df736e49487bdea3579f2269_4.png)

We are going to talk about resources you can use to design analysis plan based on specific hypotheses and questions。

 Then we are going to use the analysis plan we've created for a Doian project to practice turning business questions into SQL queries。

Many of the questions we will ask about Doian users will be similar to the questions business analyst at boxox asked about their users。

 here's Ryan Lucki again。Yes， our business analysts use SQL to query data that we have about how users use B。

 so both usage patterns， like how active were our users。

 how many active 30 day users do we have or seven day or how many pieces of content do they upload per week or are they active mostly on weekdays or weekends。

 based on their locale？What sort of collaboration do they do。

 How about the difference between how users in our free tier operate versus how users in our。

Business or enterprise class tiers operate。You will address questions that are very similar to these in the exercises you will complete this week。

I think one of the hardest parts about learning SQL is figuring out how to translate the words you would use to describe the analytical results you know you want to achieve in the actual SQL query language on a screen。

The best way to do that is through practice writing queries that are specifically designed to help you analyze and interpret the data you have in front of you。

So you will start that practice using queries related to our Dogniition analysis plan。

 which you will go through step by step。Then you will answer many similar queries using the Dillers dataset set In essence。

 we're going to practice， practice practice， and then practice some more by the end。

 you will feel confident claiming that you know how to write SQL queries to create business value。

Let's jump in and start， shall we？

![](img/365136c0df736e49487bdea3579f2269_6.png)