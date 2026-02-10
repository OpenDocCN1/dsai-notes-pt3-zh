# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P80：22_保持局部结果.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

🎼Yeah。In our last video， we talked about how to avoid having expensive operations inside our loops。

So if we have to parse a file， we do it once before we call the loop instead of doing it for each element of the loop。

But what if parsing the file is taking a lot of time， even when it's done outside of the loop。

 Remember that to make our scripts get to their goal faster。

 we need to avoid having our computer do unnecessary work。 So how can we avoid expensive operations。

Like parsing a file， downloading data over the network or going through a long list。

 If the script gets executed fairly regularly， it's common to create a local cache。

 In an earlier video， we said that a cache is a way of storing data in a form that's faster to access than its original form。

So if we're parsing a large file and only keeping a few key pieces of information from it。

 we can create a cache to store only that information。

 or if we're getting some information over the network。

 we can keep a local copy of the file to avoid downloading it over and over again。

 creating caches can be super useful to save us time and make our programs faster。

 but they're sometimes tricky to get right。We need to think about how often we're going to update the cache and what happens if the data in the cash is out of date if we're looking for some long term stats。

 we can generate the cash once per day and it won't be a problem。

This might be the case for data like how much memory was used on computers across the fleet over the last month。

How many employees each department and a company has or how many units were sold of each product over the last quarter。

 But if we're trying to look at data where the value as of right now is super important。

 we either can't use the cache or it has to be very short lived。

 This could be the case for monitoring the health of computers to alert when something crosses a threshold。

Checking the stock levels to see if there's enough of a product to sell or seeing if a username already exists in the network when trying to create a new one。

 Sometimes we can add a check to validate if we need to recalculate the cash or not， for example。

 if our cache is based on a file， we could store the modification date of that file。

 when we calculate the cache and then only recalculate the cache if the modification date of the file is newer than the one we had stored。

 if we don't have a way of checking if our cache is out of date or not。

 we'll need to add in logic to our program that tries to make a sensible decision。For that。

 we'll take into account how often we expect the data to change。

 how critical it is that the latest data is used and how frequently the program that we're running will be executed After taking all these factors into account。

 we might decide that the cache needs to be recreated once per day once per hour or even once per minute。

Yes， even once per minute might make sense if you have a script that can get executed several times per minute。

And needs to do an expensive operation that can be cached。 That way。

 only the first execution in a minute will spend time on this operation。The rest will be very fast。

 but the cache is never more than a minute out of date。

 And keep in mind that caches don't always need to be elaborate structures storing lots of information with a complex timeout logic。

Sometimes they can be as simple as having a variable that stores a temporary result instead of calculating this result every time we need it。

 for example， say you're generating a report that prints how many users there are in each of the different groups in the network。

Now， some of these groups may contain other groups in them。

 and some groups may even be part of several groups， for example。

 the Java Release Engineers group would be part of the Release Engineers group and the JavaDevelopers group。

How can we avoid counting unique users more than once if they show up in multiple groups。

 we could have a dictionary with the group as the key and the amount of users is the value。That way。

 we only need to count the members of a group once， and after that。

 just use the value in the dictionary。

![](img/97747a70cc2310df2bb09d414b792775_1.png)

To sum all of this up， remember that you'll want to look for strategies that let you avoid doing expensive operations。

First， check if these operations are needed at all， and if they are。

 see if you can store the intermediate results to avoid repeating the expense of operation more than needed。

Up next， we'll look into a practical example of how to deal with some code that's running slower than expected。



![](img/97747a70cc2310df2bb09d414b792775_3.png)