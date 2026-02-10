# 谷歌数据分析师第五课《通过数据分析回答问题》analyze-data（中英双字） - P25：25_03_02_查询中的查询.zh_en - GPT中英字幕课程资源 - BV1q14y1o7Yj

![](img/8ebcd6625c7453bd321aad7eb2d58ad5_0.png)

Hey， it's great to have you back。 In this video， I'll introduce you to another kind of SQL query。

 Subqueries。 a subquery is a sQL query that is nested inside a larger query。

 Have you ever seen one of those nesting doll toys。 They're also known as Matri Oshku。

 Russian nesting dolls。 Subqueries are a lot like nesting dolls。 No， really。

 your larger query could have a subquery in it。 And then that subquery could have a subquery。

 And then that subquery could have another subquery。 But when you stack them all together。

 they make one query with subqueries， you can combine different pieces of logic together。

 because the logic of your outer query relies on the inner query。

 you can get more done with a single query。 This means all of the logic is in one place。

 which makes it more efficient and easier to read。😊。

The statement containing the subquery can also be called the outer query or the outer select。

 This makes the sub query， the inner query or inner select。

 The inner query executes first so that the results can be passed onto the outer query to use subqueries can get a little confusing because there are so many layers。

 But if you keep in mind that the innermost query executes first。

 it will be easier to order your subqueries when you want them to execute。

 Subqueries can also be nested inside all sorts of other queries。

Usually you'll find subqueries nested in from or wear clauses。Let's try out some common subqueries。

 We'll start with the subquery and a select statement using the bike sharing data from an earlier example。

 For the first statement， let's say we want to compare the number of bikes available at a station to the average number of bikes available。

 We're going to use this query to pull the average number of bikes available。

 Then we're going to incorporate it as a subquery。Now， let's build our outer select query。

 We want to select the station I D and the number of bikes available。

Then we'll put the select query that's pulling the average number of bikes inside that outer query by using parentheses。

We'll also build from into the sub queryry before closing it with another parentheses and completing the outer query。

The end of the outer join query has asked to show what we want to call this column and a final from statement to indicate which table we're referring to。

Now， let's run it。And there。We've got a table with both the number of bikes available and the average number of bikes available at different stations。

It's really common to see subqueries nested in from and where statements。 So let's try those。 next。

 We could use a from statement to calculate the number of rides that have started at each station over time。

We'll start with our autoer query and input select station ID， name， and number of rides。

We'll use as to tell it how we want the table labeled。And from to tell it。

 where we're pulling data from。 But before we finish that query， we'll add a sub query。

We'll put our parentheses here and then select the start station ID。

Then we can tell it to count the number of rides from the trip data and group it by the start station I D。

After that， we'll close the sub query with the parentheses so that we can continue building the outer query。

 We'll use as again。😊，And then use En join and on to join it with the station I D data。And finally。

 willll tell it to put it in descending order。😊，Let's see what happens when we run that。

We now have the number of rides started at each station。Okay， one last example。

 let's use a where statement。The bike sharing company has two kinds of users。

 subscribers and one time customers。 Let's say we wanted a list of stations Subrs used。 As always。

 we start with the outer query。 Select the station I D and name from the public data set we're using。

 And this time， we'll use a where statement。We'll also use N so that we can specify multiple values in this where statement。

Then we'll put our sub query in the parentheses。We'll add select， from and where again。

 But this time we'll tell it that we only want data on specific customers。

It's good to note that you can use comparison operators in subqueries。

 even multiple row operators like in any or all。In this case。

 we'll use equals to indicate that we only want the subscriber user data。Now， let's run the query。

And we've got the station ID and names， four stations that fit our criteria。

So that's subqueries in action。 Subqueries can be challenging。

 There's a lot of layers to think through， and you might find yourself running into errors when you practice。

 That's totally okay。 Having to go through that challenge means you're growing。

 If everything was easy， we wouldn't find new ways to grow。 for me。

 it's all about how much work and how much time I need to put in to do it。

 So give yourself time to practice this new concept。Coming up。

 you'll get a chance to use subqueries to aggregate data， or you can move on to the weekly challenge。

You'll take everything you've learned like using Vlookup， different joins， and subqueries。

 and apply it to this upcoming assessment。We've been doing a lot of complex work。

 So if you want to take a moment to review these videos before moving on， feel free。

 And once you finish the challenge， I'll see you again for our next big learning adventure。

 See you soon。😊。

![](img/8ebcd6625c7453bd321aad7eb2d58ad5_2.png)

![](img/8ebcd6625c7453bd321aad7eb2d58ad5_3.png)