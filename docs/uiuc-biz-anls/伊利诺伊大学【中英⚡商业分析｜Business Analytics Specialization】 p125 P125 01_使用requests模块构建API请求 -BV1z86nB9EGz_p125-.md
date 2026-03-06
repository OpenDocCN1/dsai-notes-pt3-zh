# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p125 P125 01_使用requests模块构建API请求 -BV1z86nB9EGz_p125-

In this lesson， I'm going to demonstrate how you can use an API to get data from an external repository and bring it into your local Python environment for analysis。

Now I'm going to show you how to do this using the Python requests module。And as you'll see。

 it's really easy to use the functions and methods in that module。

The hardest part is constructing the URL R to get the data that you want。

 The reason why that can be challenging is twofold。First of all。

 there's not a structured API language or a standard way of indicating what data you want that is universal across all APIs。

 similar to like a structured query language for relational databases。

 And the second reason why it's challenging to construct the URL is related to this nonstandardization and that's because one missing comma or one extra comma could result in your URL not working and you may not know why it's not working。

 So one of the most important things you can do is read the documentation about how to use the API。

And if it exists， it'll make it easier to learn how to construct the URL。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_1.png)

So to demonstrate this， let's go to the City of Chicago's data portal。

 So in a web browser I've navigated to data。cityofchicago。

org and scrolling down a little ways there are a variety of categories of data and I'm going to click on this buildingss category。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_3.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_4.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_5.png)

This brings me to another page that indicates there are 30 different results in here。

 And I'm going to click the top one building permits。

 And here's where I can read all about this building permits data set。

 There's a lot of information here。 I'm not going to go over all of it， but scrolling down ways。

 You can see that theres about 806000 rows of data，115 columns。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_7.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_8.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_9.png)

And then it gives me information about each of those columns。 And so that's really helpful。

 This is a really great data dictionary。Now， there's not necessarily a standardized place where documentation for using the APIs is located。

So you may have to do some searching。I've already looked around here and in this actions button in the top right hand corner。

 if you click on that。This will bring up a menu， and it has API in here。

 Clicking on that brings up another window where we can read about how to use this API。

 I'm not going to go over all the details about it， but there are a few key things。

 So the data format is Json。 We can change that to CSV， if we want， but I'll leave it at the default。

Now， this is really important。 It says the default API limit is 1000 rows of data。 Okay。

 and this data set has。About 805000 rows of data。 So you can't download all of it with a single API request。

 That'll be important later on。So we can only get 1000 rows at a time。

 but we want to be able to identify which thousand rows we want。 Let's keep that in mind。

 And let's look at this next thing here。 This is one of the most important things， the API endpoint。

 So this is the URL that we might want to use if we wanted to download all of that data。

 And if there wasn't a limit of how many rows we could download。

 we could simply copy that and it'd be really straightforward。 But since we can't do that。

 let's go to the API documentation link right here。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_11.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_12.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_13.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_14.png)

And this brings up a whole bunch of additional documentation。 Now。

 we're not going to take time to read through this。

 And you may feel a little bit overwhelmed at first， like me。

 But after reading through documentation for a few Apis。

 you'll see that there are often similarities。 So what we want to do is scroll down。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_16.png)

And just look at the fields。 Okay， so as I look at this。

 I can see that there's this application start date。

 If I want to get the most recent building permits， then maybe I can use this column somehow。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_18.png)

Okay， so application start date tells me it's a floating timestamp data type。 Okay。

 so it looks like I'm on the right track here。 It tells me how I can add on that column to indicate that I want data for a specific date。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_20.png)

Well， I doubt that this data is recorded at the millisecond level for when people actually apply to get their building permits。

 So I need to read some additional details。 And if I click on this detailed docks on the floating time stamp data type。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_22.png)

It tells me that I can use some SQL like operators for filtering the data。

As well as just some English words。Okay， so I'm going to go back。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_24.png)

Right above the fields here， I can learn more about how to use this API。

 So let's click on the simple filters right here。 This tells me that when I want to filter the data。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_26.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_27.png)

I simply have to take that initial endpoint， add a question mark on it。

 and then I can structure my filter much like a SQL filter。Okay， in this case。

 source is equal to N N。And then if I want to add on additional filters。

 I need to combine them using a Boolean and， which is the ampersand。 So in this example right here。

 it says source is equal to PR。 And then this ampersand region is equal to Virgin Islands region。

Okay， so that that little ampersand between filters is the key thing here。

 So that's helpful to keep in mind。 And then looking at this S O Q L queries is useful。

 It basically tells us that it borrows heavily from structured query language。

 And so when you want to indicate where a specific date value is。 I need to add this dollar sign。

 where。

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_29.png)

And scrolling down a little bit， it'll say like dollar sign where equals magnitude。 Okay。

 And then then after that， it's kind of the， the filter that we apply。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_31.png)

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_32.png)

All right， so that's helpful to keep in mind and then also paging through data because we can only get 1 thousand rows of data at a time。

 we need a way to say my first request， I'm going to get a thousand， the first thousand rows。

 the second request I want to get the second thousand rows and so on。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_34.png)

And the way you do that is by using the limit and offset。

 So the limit is the number of rows that you want， and the offset is。

Which set of thousand rows that you want， All right， So if I wanted the first thousand rows。

 I set it at 0。 If I want the second thousand rows， then I'd set this at 1000 and so on。 Okay。

 now that's really important。 That's a detail that I didn't find right away。

 And it caused me a little bit of frustration initially。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_36.png)

Okay， that's the hardest part， so once we have that though， let's go over to a Python environment。

And talk about how to put this all together。 The first thing that I need to do in my Python environment is import functions from the requests and pandas modules。

 The request module， obviously， for executing the API request。

 and then pandas for analyzing the data。 So I'll go ahead and run that cell。

 And if you haven't installed the request module， then you'll need to do so using your package manager。

 whether it's Pip or Conda。

![](img/430a2c8d7fa3b2c36f1198b571fd2e30_38.png)

All right。 And then here's the most challenging part， building the request。

 So rather than try and create one long character string。

I'm going to break it into separate components。So the first thing I'm going to do is just take that base URL。

 that endpoint that they gave us if I were to just take this and put it into the requests。

Get function。 Itd give me all the data if there weren't a limit on how many rows I could get。

 that since there's a limit， I'm going to indicate that I want to filter it by adding that question mark at the end。

Allright， and then I need to think about how many rows of data I want to get。 Well。

 I want to get it as many as I can at once， so I'm going to set the limit equal to 1000 and then offset equal to0。

 meaning I want the first thousand rows of data。 Now the challenge is that I don't know how the data is sorted。

 I don't know if it's going to give me the top rows or the bottom rows and you know if it's sorted by application date or not。

So I need to create some additional modifiers。So I'm going to create another variable modifiers。

And notice that this part right here， this ampersan dollar sign where equals。

That's one of the challenging things， right， We had to read the documentation to understand that if I want to add in additional filtering。

 I need to add this ampersan and then to use that SQL like where clause。

 I need to proceed it with a dollar sign and then include the equal after it。 And after this。

 I can just take application start date that column set it greater than an equal to and then in quotation marks 20240101。

 So I want to get things after January 1 2024。 So you can see that that part's very much like SQL right there。

All right， And then I need to think about how I want this data to be sorted。

 So I've indicated that I want everything after 2024 so far， but I only get 1000 rows。

 So let's sort it also by application start date。 We want to put it in descending order。Alright。

 and so you can see that's very much also like SQL。

 But in order to indicate that I'm using that to order it。

 I need to add this ampersand dollar sign order equals。 All right。

 so I'm going to order it by that right there。 and that should give me the most recent data first。

All right， so once I have all those pieces， I can then put them together into this URL variable by using an F string。

So I've got the F quotation marks and then my base URL up here。

 And then I'm manually typing out the dollar and limit。 Okay。

 don't need an amp or sand here yet because this is my first filtering variable。

 I'm going filter by 1000 rows my。Now， Ampersand dollar cent offset equals。This0 right there。

 And then I can just take the order and modifiers variables。

 It really doesn't matter the order that I put them in。 And that will be my URL。

 So I'll print it out so that you can see this big， long URL at the bottom。Now， that's the hard part。

 All right， so after that， what do we do， Well， let's submit the request。

 So I'm going to use the requests module get function。 Okay， this is a get request。

 I'm requesting data。 So I want to get something。 and I'm entering the URL in there。

 Now this is really cool because。😊，That little line of code right there will execute the request for me。

 Ka， it's going to go to the waiter and say。Here's exactly what is being ordered。

 The waiter will go get the data and will return back with the response and will save it in this variable。

 My response。And then immediately after that， we're going to display the status code。

So let me scroll up here and then I'm going to go ahead and run that。

All and pretty quickly we get this response of 200。 and as you may recall。

 that's the response code we want。 that means it was successful。All right。

 so that's really the hardest part in here after this。

 we need to convert the data to a data frame format so that we can analyze it。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_40.png)

So。Let me just take that right there。My response and it has this dot JSsonN method associated with it if I run that。

It will return the data that I requested in Json format， which looks a lot like a Python dictionary。

 It's surrounded by curly braces， and there's like key value pairs in here。Well， that's good because。

The pandas data frame method can take dictionaries and convert it to a data frame。 Allright。

 so I'm going。Do that right here。 And now we can see we've got 1000 rows。

 and it's indexed in a really nice way，0，999。 And these are all strings。

 They're all object in the D type column here。 So that's not necessarily what we want， because。

We want to be able to analyze things maybe by the date。And maybe look at the fee paid。Al right。

 so I'm not going to talk much about the code down here。

 but we'll do some additional processing of the data using pandas。

And we'll group it together and create a plot。And now we've got this plot that tells us how much was paid in total fees for building applications in Chicago for each week here。

 All right， So anyway， the point is， after youve performed the request。

 you've got that data right in your Python environment and you can use pandas to analyze it all you want。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_42.png)

So that' a lot of information， this is our first example though we'll go through some additional examples later on。

 hopefully you have a better idea for how to create URLs and implement the API request。



![](img/430a2c8d7fa3b2c36f1198b571fd2e30_44.png)