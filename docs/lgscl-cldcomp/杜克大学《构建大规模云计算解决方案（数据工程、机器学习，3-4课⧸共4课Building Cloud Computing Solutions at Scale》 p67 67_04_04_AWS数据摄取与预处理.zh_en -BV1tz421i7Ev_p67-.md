# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p67 67_04_04_AWS数据摄取与预处理.zh_en -BV1tz421i7Ev_p67-

Ingesting and preparing data， let's go ahead and dive into this topic。 First up here。

 we're going to talk about the objectives of this module。

 They are to distinguish between the process of extraction， transformation and loading or ETL。



![](img/0aeabb40352b705ee664752cbd9dc00b_1.png)

And it's also about defining data wrangling in the context of data into a pipeline。

 so this is a traditional process that many people probably have had some experience with if you're a DevOs or Opsperson。

 but we're going get into the specifics for data engineering。

 and we'll also talk about the key tasks in each of these data wrangling steps like discovery。

 cleaning， enriching data， validating it， publishing the data。



![](img/0aeabb40352b705ee664752cbd9dc00b_3.png)

Okay， let's get into E TL and ELT。 So first up here。

 what we have is this concept of ingesting data is going to involve storing and processing data。

 So what this means is that。

![](img/0aeabb40352b705ee664752cbd9dc00b_5.png)

For example， the ingestion process incorporates extracting the data from a source that isn't already available in the pipeline。

 then loading that data into a temporary storage location。

 then processing the data by transforming it before or after the data is loaded into permanent storage。

 the type and scope of transformations and where they occur in the pipeline are highly dependent on the business need and the nature of the data being ingested。

 So a classic example of this would be you have two databases。And you have the source database。

 you pull some data from the database， you transform some columns， you manipulate the data。

 turn it into some format， and then put it into another database。

 So this is something I've done in my career。 I can't even count how many times how many different companies。

Now， if we get into the specifics here， though， we can see there's a little bit more information that's important beyond just this concept。

 We have the ability to really dive into the details of what this means。

 So it means that the traditional method of ingesting and querying the data for analytics was ETL and with ETL。

The data is going to be extracted from the source transform like it just talked about in a structured format that's ready to use in some analytics application and then is loaded into structured storage like a data warehouse。

 and then the data scientists or analysts would then query the data warehouse and might even perform additional transformations and processing as part of the analysis。

Also， in thinking about design principles and patterns for data pipelines。

 that data stores are going to evolve from handling just the structure data， right。

 This is kind of the traditional way of dealing with things。

To actually handling high volumes of unstructured data， and this does involve some more complexity。

And when you think about this， the move from structured data in a relational database towards unstructured or semistructured in data lakes is really the big issue that we're dealing with and there are tools and methods for ingesting the data into a pipeline。

That have been evolving to solve this problem。 And the E TL techniques have continued to evolve as well。

 and they're still very valuable， but things are changing。

 and the trend is going to be around collecting high volumes of unstructured and semistructured data。

 so。Machine learning is a perfect example， people are building large language models and the desire to make that data available for a variety of uses leads to a different approach for data ingestion ELT so with an ELT approach notice the ETL and ELT the last two characters are switched with an ELT approach the data is extracted from its source and transformed only enough so that it can be consumed but it's actually stored in a relatively raw state in the data lake and the transformations that might be needed for specific use cases are done later。

 and then the consumers will access the data and build analytics solutions with it。

So if we think about this， what this means is that the ETL stores the data that's ready to be analyzed so it can save time for an analyst and if the analyst is going to perform the same transformations on the data all the time。

 it might be important to incorporate those transformations into the ingestion process。

 So with ETL you're going to trade that transformation processing time before the data is available for a faster ability to query it so for example dashboard would be a classic example。

 and then another advantage of performing the transformations up front is that you can filter out PII or personally identifiable information。

 I think the industry has been very cavalier about this for quite some time。

 but really that era is over you don't store personally identifiable information it's a huge risk to your organization and so as a result the rule is never store sensitive data you want to reduce the risk without the need to evaluate additional security。

Msures。So with ELT， the process to get the raw data into your pipeline can be a lot quicker because you're not going to transform the data as much before it's in the data lake。

 which again would be something like AWSS3 and with ELT。

 your tradeoff is that you get the raw data available more quickly。

 but you spend more time transforming it。 So really there's this tradeoff here between the two methods and an advantage of storing the raw data and only transforming it downstream is that the changes is to the transformation。

 for example， a additional fields or formatting can be run against every historical data that was loaded when the transformation is updated and if the transformations occur before you load the data。

The changes can apply to the new data that's ingested。

 but it might be impossible or difficult if you apply them to historical data。

So a few things to think about here， one of them is that in modern architecture。

 so ETL and ELT approaches， things get a little bit blurry and each role with the pipeline might perform a different part of ingestion and transformation by using different tools and also different ways of accessing the data。

For example， a data engineer could be doing common cleaning operations and transformations before loading。

Additional transformations might also occur。If the data is pulled for a particular analytics use case。

And some of the other things to think about would be the data set evolving as well。

And if there's going to be a lot of analysts that are going to do the same kind of transformation。

 you know what do you need to do to improve the performance and cost， like for example。

 cash in it in the case of a dashboard because it could be very expensive to do that query each time。

 and so as a data engineer， you have to monitor those pipelines。

And see how they're accessed and used and how to modify the processes to optimize the value。



![](img/0aeabb40352b705ee664752cbd9dc00b_7.png)

So some of the key takeaways here are that ingestion。

Is going to be pullinging the data into the pipeline and applying transformations。And an ingestion。

That uses ETL flows， works really well with structured data。But for the ELT flows。

 the unstructured is going to be destined for something like a data lake and ETL and ELT processing within a pipeline are going to have to evolve as well。

 so this is a classic problem in software engineering。



![](img/0aeabb40352b705ee664752cbd9dc00b_9.png)

Okay， let's talk about data wrangling here。

![](img/0aeabb40352b705ee664752cbd9dc00b_11.png)

And so when we think about data wrangling， it reflects the complexity and the messiness of transforming large amounts of unstructured data or sets of unstructured data。

So again， multiple databases， for example， into a single database and this content that we're going to cover is going to dive into that。

 so for ML applications， for example， you're going to have to do a lot of this because you may not have data that's suitable unless you massage it。

So a few things to consider would be an organization can query the data from an on premise database to find。

 for example， if patients are overdue for a visit，And if you're using public healthcare data sets。

 the company might combine the health data that identifies demographic risk factors for heart attack with customer data to personalize information。

For the patient who shares the risk factor。 And then if the patient has， let's say， a mobile app。

 they could have a real time alert。 And so what you're seeing here is that this is one of the things that happens as a data wrangler is you're pulling all this together。

And when you're thinking about the overall ingestion and data wrangling。

 it could be as simple as using a spreadsheet， manipulating columns and using those values in the spreadsheet。

 and you could even upload it directly to S3， but a traditional E process is going to be using things like scripting。

 automating transformation steps。And those analysts and data scientists will be working with data in a very consumable state。

But data wrangling has actually been around for quite some time， but with an ELT。

 this is really about， again， getting this loosely transformed data and you don't yet know exactly what it's going to be doing and you're going to use tool updates to really give your pipeline some of the capabilities to deal with this。

Now， if we think about a modern data architecture， a few things to consider are that。

The landing zone bucket， let's say S3 would be the temporary storage and you're going to use it to clean and validate the data。

 and then you can use that data for additional use cases。

 so it could be like an ELT where you would then take that data and transform it into a highly structured state like let's say a data warehouse like Redshift and then a data engineer or data scientist would then structure enrich and validate that data。



![](img/0aeabb40352b705ee664752cbd9dc00b_13.png)

So some of the takeaways here are that data wrangling is a multistep process and the steps are going to overlap and iterate depending on the data sources and the use cases and the steps for data wrangling include discovery。

 structuring， cleaning， enriching validation and publishing so with data science。

 you can think of the data science pipeline as ingestion， exploratory data analysis。

 conclusion or in some cases modeling and then conclusion。

 so there's some similar workflows that happen with data wgling as well and you can see with the discovery phase。



![](img/0aeabb40352b705ee664752cbd9dc00b_15.png)

Okay， let's talk about data discovery here。

![](img/0aeabb40352b705ee664752cbd9dc00b_17.png)

And really the idea here is that it's going to be iterative， just like with data science。

 it's a exploratory data analysis you don't really know what you're looking for。

 but again with data discovery。You don't really know yet what it is you're doing and you want to find the sources that you think could be useful。

 this could take actually maybe a couple hours or it could take a year depending on the kind of problem that you're dealing with。

 And so the key steps are going to be deciding if a source seems to serve your business purposes identifying the relationships that exist。

 what are the formats is a CSV parquet， is it optimized row columnar。

 how much of the data do you want， where you going to organize it。

 Can you actually build some metadata around the data。

 There's a bunch of different things that are important when you're going through this discovery process。

The other thing to think about as well would be different scenarios in your organization about some things you would want to cover if you're going through a data discovery process。



![](img/0aeabb40352b705ee664752cbd9dc00b_19.png)

So know， maybe it's a spreadsheet that you initially start out with and you know put that into a spreadsheet to get some more ideas of the data。



![](img/0aeabb40352b705ee664752cbd9dc00b_21.png)

Okay， so really in a nutshell， the things to consider are that data discovery is iterative。

 and data engineer is going to have to figure out what are the relationships between the sources as well。

 and then you're going to need to identify tools and resources that you'll need to move forward。



![](img/0aeabb40352b705ee664752cbd9dc00b_23.png)

So let's talk next about data structuring and if we think about data structuring。

 a few things come to mind like one of them is you're going to have to have an infrastructure to organize that data。

 you're also going to need to parse the source files and convert them so strings or patterns So this is a mapping problem so you're going to have to figure out what thing maps to another and then you're also going to have to figure out how to parse the files into relevant fields and attributes。



![](img/0aeabb40352b705ee664752cbd9dc00b_25.png)

And you really， this is a big component of the complexity of going through and structuring the data。

And so in an example， potentially you would rename columns where you would perform additional data wrangling steps before you would compress a file that then would get uploaded to S3 bucket。



![](img/0aeabb40352b705ee664752cbd9dc00b_27.png)

So data structuring is about mapping the raw data from a source file or files into a format that is going to support you storing it at scale and combining it with other data。

 and then during the structuring step you're going to have to parse files。

 map fields to a larger targets， and then also organize the data set。

 and then finally you're going to have to figure out a way to optimize the file size。



![](img/0aeabb40352b705ee664752cbd9dc00b_29.png)

Okay， now let's get into data cleaning here。And cleaning is a very important step because。

The data is never going to be exactly the way you want it and some of the things that you're going to have to consider with data cleaning are removing unwanted data。



![](img/0aeabb40352b705ee664752cbd9dc00b_31.png)

Fillling in missing data values， validating or modifying data types， fixing outliers。

 And so if you think about depending on who does the cleaning， it's going to be very different。

 So if you think about some of the things that could go wrong。

 It could be a field is corrupted or there's bad characters。

 It could be that there is missing data inside as well， I mean。

 there's just a wide variety of problems that happen with data cleaning。



![](img/0aeabb40352b705ee664752cbd9dc00b_33.png)

And another cleaning task could be， for example， you know。

 mapping different fields from one format to another format and changing the date formats。 I mean。

 there's really no end to the kind of problems that happen with data cleaning。



![](img/0aeabb40352b705ee664752cbd9dc00b_35.png)

So really the takeaway here is that data cleaning is about preparing raw data for use in a pipeline and cleaning is done per source and there's going to be things like removing duplicates。

 fixing values， existing data types。

![](img/0aeabb40352b705ee664752cbd9dc00b_37.png)

Now， if we think about enriching within data wrangling， this is an important topic。

 and the steps could be a lot more complex， it could be thinking about processing merged fields。

And then adding additional calculations into those fields like maybe creating a synthetic column you know that is the combination of two different fields and creating some new feature。

And some of the things to you think about as well would be with when you're enriching the data。

To consider how that would represent itself down into a later problem like a machine learning problem。



![](img/0aeabb40352b705ee664752cbd9dc00b_39.png)

So if we think about the key takeaways， it's that you're going to be pulling data from different sources to create a data set you need。

 and during enriching you might merge sources， additional fields， or even calculating new values。



![](img/0aeabb40352b705ee664752cbd9dc00b_41.png)

![](img/0aeabb40352b705ee664752cbd9dc00b_42.png)

So let's talk about validation now， So this is an important step as well because during the cleanest process you want to make sure that an email has a value of the correct data type。

 but during validation， you want to verify whether the email address and the domain represent even valid values right so it's very common when people ask for email addresses that people will put in。

 let's say a bogus value。Like， you know， bo@bogus do com right。

 and people don't like putting in their email addresses。 Now。

 can you figure out whether the things that you've entered are actually valid email addresses and also data engineer is going to focus on tasks that validate the accuracy of automating the structure。

Cleaning or even enriching and also making sure that there's no fields that have personally identifiable information。

So some， you know， validations that you can think about would be， again， you know。

 mapping things from one to another then verifying that， in fact。

 the value that you see is actually a valid value。

![](img/0aeabb40352b705ee664752cbd9dc00b_44.png)

So in a nutshell， the purpose of validation is to ensure the integrity of the data。

And also the validation task could actually overlap with a cleaning task and so the idea here is that you want to make sure the data is not only valid。

 but it will load successfully as well， and this is going to be an iterative process and you're going to have to fix errors and then rerun。



![](img/0aeabb40352b705ee664752cbd9dc00b_46.png)

Let's talk now about data publishing， so publishing。

 the idea here is that you need to write data to appropriate folders or partitions and apply the file management techniques and as part of the publishing process。

 you're also going to make sure that storage locations have set up。



![](img/0aeabb40352b705ee664752cbd9dc00b_48.png)

Things in a way that they're going to have the least privilege access for the user to do their work。

 where you don't want to give them more abilities than you need。The other thing to consider would be。

The next step would be that let's say a data engineer would sign into their account。

 designate a bucket， and then you could upload those into the different regions。And finally。

 if you look at a service like AWS gluelu， what's nice about that is that it can make a repeatable process and the glue will crawl and then create a data catalog and what's nice about the data catalog is then you don't have to actually query the data again because you just have to query the catalog and then the data that you need is the data that actually gets activated。



![](img/0aeabb40352b705ee664752cbd9dc00b_50.png)

So in a nutshell， the data publishing is about making the data available for you within a pipeline to publish the data。

 you want to move it to a target storage based on decisions you made during the structuring step and to continue to make the data available。

 you need to set up a method to update the data on a timely basis as well so we talked about a lot of stuff here and really we should wrap things up now and go over some of the key concepts and the mod talked about the extract transformative load or ETL。



![](img/0aeabb40352b705ee664752cbd9dc00b_52.png)

Also， we talked about extract load and transform or ELT， and we talked about the steps involved。



![](img/0aeabb40352b705ee664752cbd9dc00b_54.png)

And so in a nutshell I think one of the ways to really get this information and solidify it is to do your own data wrangling and do your own data engineering。

 and you can go through these different steps when you're craning pipelines to ensure that you're going to create a reproducible and reliable process。



![](img/0aeabb40352b705ee664752cbd9dc00b_56.png)

![](img/0aeabb40352b705ee664752cbd9dc00b_57.png)