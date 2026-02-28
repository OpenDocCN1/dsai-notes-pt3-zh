# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p68 68_04_05_在AWS Glue中使用Amazon Athena.zh_en -BV1tz421i7Ev_p68-

![](img/4da8c038286b13e70319e17bcefe5034_0.png)

What I'm going to do is I'm going to go to this query data and Athena。



![](img/4da8c038286b13e70319e17bcefe5034_2.png)

With Amazon S3。I'm going to click on my work。And then what I'm going to do is I'm going to go through and run this lab so you can see that we're going to use glue and a glue it is an automatic ETL system that's serverless it integrates with Athena redshift and also EMR。

 so Athena is a serverless。Data data query tool， redshift is a data warehouse and then EMR is basically spark or Hadoop。

 it's a map reduced system。 And so what we're going to do is we're going to use glue to make sure you understand how to do that we're going to crawl some stuff and then we're going to query it using Athena So I'm going to go ahead and say start lab here。



![](img/4da8c038286b13e70319e17bcefe5034_4.png)

And that will take just a second to start it up。

![](img/4da8c038286b13e70319e17bcefe5034_6.png)

Yes。Sure。

![](img/4da8c038286b13e70319e17bcefe5034_8.png)

Oh， okay。 so， so let me， yeah， let me fix this real quick。 What I will do is。嗯。I will good question。



![](img/4da8c038286b13e70319e17bcefe5034_10.png)

What I can do here is。I think I didn't publish them yet for you， so I'm going to go to Vquaium。



![](img/4da8c038286b13e70319e17bcefe5034_12.png)

![](img/4da8c038286b13e70319e17bcefe5034_13.png)

嗯。And then I'm going to go to UN C here。I'm glad you asking me this。And。I'm going go to assignments。

 Let's go to。Do you know Linux。And good assignment。Go here， publish。That's why。

I don't know why they do this， they hide these。At first， so。You now， very good question。There we go。

 So you should now get access to this。 Is that correct。If you refresh。These should start a period。

There we go。Yeah， it should or maybe log out a log by getting it。 I think it's instant。

 it should be instantaneous。But yeah， that would。Okay， perfect。 and people see it。 Okay， great。

 So great question。 and and I'll publish the rest the other ones later that that that we have access to。

 great question so。Now that that's there next， I'm going to click on AWS here。



![](img/4da8c038286b13e70319e17bcefe5034_15.png)

And。OhWhat I'm going to do is is is probably just put these side by side。 so I'm going to。



![](img/4da8c038286b13e70319e17bcefe5034_17.png)

Go like this so I can see this one。And then I'll put this one right next door so we can kind of look at both at the same time。

 okay。So the first step here is。Let's let's get in here in this scenario。

 your data analyst working at。International Development Agency。

 we're figuring out some drought relief data。Or this could be know coronavirus or whatever currently is happening in the world。

 you can see here at the diagram is that the IAM system has to make sure that the user has access to these resources。

 glue， Athena and S3 so the first thing we're going to do is we're going to crawl data inside of glue and so that is again what glue is designed for and I know many people that are doing data engineering in real companies and this is actually one of their tools it's a great tool。

So first step， we're going to go to glue， so I'm going to go here。Type in glue。

And you can see here it's a fully managed ETL system。And next up。

 what we're going to do is we'll choose Get started。

And then we're going to add tables using a crawler， so add tables using a crawler。

And then we're going to type in weather。Right here。

And then the next step here is specify crawl our data source and so we're going to click data stores and what that means is that we can choose S3 as a data store or I've actually used this before in consulting projects。

 JDBC which you could point it to some external database that lives in the other side of the world and you could periodically pull in that data and index it and transform it so it's a very flexible and powerful system also could talk with Dynamo。

 we're going to leave it， I believe it S3 and we're going to grab this NOAA data which stands for the。

Some kind of scientific。Thing， I know somebody that works there。 I is。

 I don't know exactly the acronym。 So we go here next。And then。Will will say。No， next year。That是。

Why that's popping up the seeless paint。Pete the sin here。Next。Addd Crawler。

Maybe you have to make it bigger。 It's some。Okay， yes， so I just have to make a little bit bigger。

 Okay， so then I go back here。And I say choose an existing role。So， again。

This is something they created for us just to simplify things， but if you were using this。

 you would need to make a rule make sure that your're。Your IEM rule had the ability to talk to。

 for example， S3。And then we're going to go to next。And then we're going to select run on demand。

 So this is another really interesting component of glue is if you are doing this on a real project。

 probably to start with you want to say run on demand so that you can just test it out and basically what's going to do is going to crawl something for you。

Later once you get the system working， then you would go and turn it。

 make it run at an hourly interval or a monthly interval or something like that。

 so we'll say next here and then for the database， we're going to say add a database。

And we're going to put in a name of a database and we'll call this weather data。

Essentially what this is doing is。It's allowing us to have a catalog。

 and then we're going to scroll down here。And we'll say next。And I believe that's all set up。

 we don't have to do anything else。 Okay， so now it says run the crawler so were going to tell AWS glue to run it now and you'll see it what we'll say run it now。

And basically it's going to go inside of S3 and it's going to look inside of that folder and it's going to find all the metadata about what's inside that folder。

 So if there's files in there that have data， it'll find the types。

 it'll find the names of the columns and that's again the power of something like this is you could write all this code to do this yourself for sure but why would you do that if you could just click a button and do the work of 50 people and this is really the part of the cloud I think that is very disruptive is is many organizations right now have tons of software developers。

Recreating poorly what is already just a few button clicks of the cloud。

So next up here we can say read。We can read more if you want to do that， we crawled that said， okay。

 after one minute， it'll change to ready。And then we can refresh this。 So the thing still starting。

 and then we can actually。We'll see that a table has been created。

 so we'll just kind of let this thing go here for a second。Let's see。There we go。

 maybe even I'll expand it a little bit。Status， one minute elapsed。Yeah。

 I think there we go stopping。 So I think it created it。 Okay， so now。

 now it created that information。And now what we're going to do is we're going to， we're going to。

You'll see the table added column， right？嗯。And what we're going to do inspect the data AW glue captured。

 So if we click on this。We can， I believe we can inspect it by going to the tables。No， yeah。

 go to tables here。And then you can see like it figured out all this data right。

 so it figured out here's the name of the column， here's the data type。

 it even shows you like what kind of data is it。So pretty powerful system that automatically does something that you would have to write some Python code to do。

 for example。And so now we're going to go to databases。We're going to go to weather data。

And we're going to choose tables and weather data。And I guess that's what I just looked at and we see this。

And you should see something similar to this， right， we have this。And now we're going to edit it。

 And again， this is another cool thing about this is you can edit the schema on the fly here。

 And so we're going to。Now tell it， we want to clean up the data a little bit here。We're going to。

Let's see here。嗯。So we want to change the columns by selecting them and entering new names。So。

 we are going to。Choose edit schema。Here， and then。We just change， yeah， we're going to change these。

 so I'll just scroll this over a little bit。Like this。

 And we'll say that's going to be called station。Oh。

 I guess have to work hard here and actually type something so station。And then next step would be。呃。

第。And then。Tpe。Observation。So， so this would be。Very similar to if you had like， let's say。

An existing database。 and you had maybe columns that were a certain name。

 and then you were talking to another database you wanted to integrate。

 you could then change the name of their columns so that they would be the same name so would be easy to integrate the data that might be one example。

Let me see my mess in this up here。 So we got station。Date type， observation， Imfl。

And then we have S flag， and then we have Q flag。And then the next one is time。Like that， okay。

And we're going to say save。So we've now changed the schema so that it's got meaningful names here。

And now we're going to query the data using the glue catalog。

 so we're going to go to the tables icon here。And then we're going to click on this CSV。

 and then we're going to view the data so from the action menu。Is there a view data here。

 Where is this view data。Few properties。WhatWhat am I missing this？ So check the table box。

 There we go back here。 So check this。 Oh， there we go。



![](img/4da8c038286b13e70319e17bcefe5034_19.png)

And go to view data。

![](img/4da8c038286b13e70319e17bcefe5034_21.png)

Preview the data。嗯。Okay， and then this will say get started。And。What's cool about this is that。

You must specify a storage bucket to hold the results from the queries that we run。

So were going to go to S3 now。I'm going to open this up on another tab。And we're going to go to here。

And I believe there's a bucket， Yeah， right here， if I click on it。嗯。Let's see。

 So the bucket properties。There should be an iron here。我' see。Select the bucket name。

To copy bucket Arn。Where is copy bucket bucket Arn？I think， I don't。An overview。

Why am I am I messing or is it heater， There you go， copy bucket arm。 Okay。

 so now that I've got that， we're going to return to Athena。

And we're going to do set up a query result location。We'll go here。And we'll past that in。

And I believe if I do a control A， I can just swap this out a little bit。And just changed this。

To S 3。Slash slash control A， and then do a back slash as well。And I don't think I need to。 so yeah。

 you have to do this， swap that at the beginning。 and I believe it should look， yeah。

 and then these aren't completed。 so we'll go and say save。

And now what I can do is for the list of databases we'll choose the weather data。

 so we got that and then choose a table CSV。We got that and then there's a little ellipsis here and this is a little tricky to find this allows us to query it like create a default query。

 so we're going to click on this。And I believe we just say preview table。

 and then it creates a select statement for us。So， again。

Pretty awesome is that if there was petabytes of data in here， like we have already cataloged。

 we have already indexed it， we know it's inside like right look。

 we can see this is all the preview data and I can run this query。

And it's going to show me all this data。 So and you can see here。

 this is the first 10 records of that table。So next step。

 what we're going to do is we're going to create a table for data after 1950。

So we're going to create an S3 bucket to store the external data。

The bucket should be in the same region。Follow the。The information。I believe what we're going to do。

Copy the following query。 Pae it。 Remember to place your bucket。 Okay， so let's go S 3 now。



![](img/4da8c038286b13e70319e17bcefe5034_23.png)

And let's create a bucket， and we'll call this bucket。呃。Whatever today is March， March 1。UNCC demo。

This may not work for you because it's all bucket names are unique。



![](img/4da8c038286b13e70319e17bcefe5034_25.png)

Okay， so we got this， I'm going to click on it。I'm going to copy this bucket。Actually。

 I think I just need to copy this part of the name right here。Here we go。

So now I'm going to go back to Athena。And I'm going to put this into a query。

 so I'm going to make a new query。And I'm going to paste this first， I'm going paste this， this in。

什么呢。Put a SQL query in here。不s。So I'm going to copy this。

Pe it in here and then take this bucket name so it'll be if you're doing the same thing。

 it would be whatever bucket you created。And then we're going to create a new table。

And we're going to put。And we're going to put the results of this into this bucket。

 which would be that。For me。So we're going to say。Here's the format of the data。

Here's our external location。And。Oh， I missed， I missed an important part。 the the wear clauses。

 which is the one that actually。Finds us the date we're looking for。 so basically we're saying。

Just give me the data between 1950 and 2015 and then put it into this bucket that I created。

So now that we've done that， I think we say return。And I can。Sceve。Wait，Actually， this should。

 this should just work here。 Let's， let's see her。 I don't know why this。

 the the run query is not working。Let's try。Let me， me， let me do this。

 Let me just paste this in one more time here。Pete that in。

And then I'll go back to the bucket name that I had， which is this one。And we'll paste this in here。

Okay。And maybe I put format queries I don't have to do。Sure， I'll format the query。

And then I believe I can just do a control enter to run the query。 There we go。Control enter。

And then it's going through this， it's going through。All the data inside of the original S3 bucket。

Filtering based on our query。And then。It's going to put the results， I believe， into。呃。

Into that other bucket。Let's let this thing crank here。So again， you can imagine。The complexity。

You're working with petabytes of data and someone hires you they're oh look。

 you're a graduate of a data science program， let's have you。You know， query this data。

I think many people would reach for Python first， right， You'd go through in。And hey。

 let's just start playing around some Python code you could be at it for months trying to figure out how to get this done versus if you use the right tool for the job。

 step1， you index it， step two cook it up to a serverless query system like Athena so behind the scenes here it's spinning up servers doing all kinds of stuff and then running the SQL query and then you can use the skills you already have。

 just write some SQL statements and then go through and filter in that data so we can see here that it was successful about look I can click on this and I can say preview table。

And then we can we can look inside of our table here and you can see all this data that was able to get from that that time period and I think if I go back to S3 now and I refresh this。

That。You can see that it put actually， this is a pretty big data set。 Wow。

 I don't actually how big is this data set。If I go back into S3 here， that we're querying。This。

Unsaved here。Those don't look that big， but， but I guess the。Yeah， because this is just the metadata。

 but in this scenario put we copied the real data to here。And I， I think if I went to properties。

It should tell us well anyway， we can see here these are big files。

 These are our parquet files or like compressed data files here。

 but now now we have now we have the ability we create easier ways to partition the data and then query it。

 So so next up here， we're going to run a query from the selected data。

 So we're going to put this in here。 So we're going to say。Go through here。嗯。

And run another query against the table that we just created this late 20th。Again。

 we'll say control enter to run it。Query was successful。

And then we can also go to the view that we set up here into the data and then go through here and say preview。

And then， this will show us。That result。 So you can， you can essentially treat this gigantic。Da lake。

As a database and and use big data tools to query the data。

 And you can see a fairly straightforward process。

![](img/4da8c038286b13e70319e17bcefe5034_27.png)