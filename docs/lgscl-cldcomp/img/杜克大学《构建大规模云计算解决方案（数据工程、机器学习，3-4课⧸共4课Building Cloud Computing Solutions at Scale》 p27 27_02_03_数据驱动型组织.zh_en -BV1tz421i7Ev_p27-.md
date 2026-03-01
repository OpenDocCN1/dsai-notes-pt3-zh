# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p27 27_02_03_数据驱动型组织.zh_en -BV1tz421i7Ev_p27-

![](img/d02ba50d5268e3ae4fecd13a46bda0e5_0.png)

Data driven organizations， let's talk through the AWS Academy data engineering material here first up。

 if we think about what a data driven organization is。

 this is a critical component to figuring out whether your organization is actually using data to make decisions so if we think through this module objective here。



![](img/d02ba50d5268e3ae4fecd13a46bda0e5_2.png)

![](img/d02ba50d5268e3ae4fecd13a46bda0e5_3.png)

It's going to be how to compare and contrast the data analytics and AI and ML pipelines。

 also how to describe the layers in the data pipeline。

 how to list ways in which data is acted upon and then also list responsibilities for a data engineer So what are the things that a data engineer would actually do versus a data scientist and then also dive into some modern data strategies So okay。

 let's go ahead and get right into it here， a quote from Gartner in 2022 says that through 2026 organizations will accelerate their investments in data and analytics by 45% to become more data driven in digital So we know that people are going to use data more frequently。



![](img/d02ba50d5268e3ae4fecd13a46bda0e5_5.png)

![](img/d02ba50d5268e3ae4fecd13a46bda0e5_6.png)

And some of the things that are important to think about are you know the decisions behind data scientists or data analytics or AIML。

 so for example is the systemic analysis of large data sets is this something you need to do like you need to find patterns for customers is there programming logic to answer questions from data。

 is it good for structured data with a limited number of variables and then with AI and AML。

 you're looking at things like mathematical models that do prediction also you're looking at how you can use large data to answer questions。

 we see this with GenAI for example， and then questions like unstructured data and where the variables are complex so a good example of this would be how to distinguish a data analytics approach from an AI approach。

 this example， you know when you're thinking about it could be a cat and dog。

 so if you had a large data set of images and you wanted to create。

A website that highlighted only dogs， How would you apply the data science to automatically identify which are dog pictures。

 if you're using traditional data analytics， you're going to need to create logic to identify the features that make a dog。

 a dog。 But if you think about it， there are different characteristics that a couple dogs would have。

That are still being recognized by humans as dogs。And how could you avoid making a cat fit into that model and with machine learning。

 you want to train your model by showing it as many pictures as possible that are labeled as dogs。

 and then they learn to identify these new unlabeled pictures as dogs。

 and so given the fact that there are so many dog images that are available。

 this could be a good problem for machine learning。

Another thing to consider would be your organization might want to use data analytics and also use AIM as part of a way to make decisions。

 so for example， in the AI approach， maybe you're going to use summarization and the analytics you're going to look at total customers。

So one of the ways you can think about this is that you can categorize analytics into four valuable categories。

 so first would be increasingly difficult to drive types like descriptive， diagnostic。

 predictive and prescriptive， the volume of data needed。

 the amount of compute and storage required and the complexity of the data science。

 these are all going to increase as you move from descriptive to predictive and then prescriptive decision support。

 so there's this really this analysis that you have to go through to figure out how to make more valuable insights。

And when you have more data， there's potentially fewer barriers to make decisions and so in this scenario you could have richer data sources are going to allow you to have powerful compute at lower costs and because you can use pay as you go infrastructure you have a lot of flexibility to try out different ideas and then cloud services are constantly changing and so this lowers the overall cost and complexity of using big data analytics and AIML in decision making and it's going to be a lot easier to make predictions so these are some of the things to consider。

Now， the other thing to think about is that。There's an increasing use of data and the application of AIM approaches are starting to interact with online systems like purchasing systems。

 for example， and so a few of the things to consider， like for example。

 on the slide would be to think about your online experience and some of the things like shopping for shoes or watching a movie or ordering a pizza online or using a credit card outside of a normal geographic region。

 these are all things where data science plays a role。

But more data doesn't necessarily equal more value and some of the problems that come into play are that higher data costs。

 there's more unstructured data， there's greater security risks， there's also slow query processing。

 in addition， there could be regulatory concerns， as you collect more data。

 especially if the data is personally identifiable information。

So data becomes less valuable for decision making over time。

The most valuable could be the near real time， and this could be， for example。

 flagging fraudulent credit card transactions， and then there's actionable would be within。

 let's say some seconds and then within minutes to hours。

 this is more reactive like what happened yesterday with our sales and then less valuable would be historical。

 it doesn't mean it's not valuable， but it could be potentially less valuable。

So the trade offs are how much should you invest to go faster and predict more accurately and then how much is this incremental improvement going to really justify that additional cost。

 also with the speed。Like how often do you really need the answer in real time and can you sacrifice the accuracy for speed？

And then in terms of accuracy。How accurate does the prediction actually have to be and then in terms of waiting for a better answer versus answering more quickly。

 you where does that lie with your organization？So some of the key takeaways here are that data driven organizations will use data science to inform decisions this includes data analytics and AI。

 the main sub distinction between data analytics and AI ML is that。

The way the analysis is performed with analytics， it's more of a programming problem with AI and ML。

 it's more of a learning problem， so there'll be a more mathematical approach。

 and so AI and ML is often very good for unstructured data because there could be many variables and you're able to infer information like for example。

 unsupervised machine learning you can find patterns inside the data and then with rapidly increasing availability of data coupled with decreasing costs this is where there is some opportunity for organizations to make data drivenrin decisions。

So let's talk next here about a data pipeline and this is really one of the core components of all data engineering is the data pipeline。

 so in the simplest you terms here you can think about it as a collection process then you store it you process the data so for example with st and processing you could change the column names so it would be a really good example of processing and then you do something with the data so maybe you go and build a dashboard this would be the simplest data pipeline you can think of。

Now， if you work backwards though， it's a great way to think about how to define your infrastructure。

 so there could be a number of variations and options to create a data pipeline and a key to do this is to start with a business problem that you're trying to solve versus just building something and hoping that itll be a good solution what you would then do is build that pipeline to suit the use case and then the cloud is going to be an easy way to start up different ideas or different infrastructure for different use cases and you don't have to spend a bunch of money on an infrastructure or tie to a single database or server you can actually start with the business use case and then build the pipeline to support it。

We also can think about the layers of pipeline infrastructure and what this means is that。

You need to make the stored data accessible for the people in the decision making process。

 and this could involve things like the infrastructure to process。

 analyze and visualize the data that is appropriate to the use case and then also building an appropriate infrastructure。

And you could do that by understanding the nature of the data and processing it and analyzing it according to that particular problem。

Some of the things to consider as well would be to look at the pipeline from the perspective of the data as it travels through it almost like water through a pipe。

 the pipeline has to support the ability to discover the details about the data in whether it's actually going to fit you could start with a hypothesis。

 for example and then experiment to see where it takes you you also。

The data may also need to be cleaned or normalized。And so you could merge multiple data sources。

 for example。You also need to look at the transformation as it moves through the pipeline。

 this could do things like modifying the format or changing names or making a catalog for the data。

 and then in each layer as part of the transitioning what you're going to do is you're going to take tasks that happen in multiple places and then you're going to combine those all so in a traditional data science architecture you have the extract transform load process and this would be something that could apply in this scenario as well。

You also can think about iteration when you're building the pipeline。

 so a key characteristic of drivingr insights with a data pipeline is that you always have to design your pipeline so that you can change it if you have a hypothesis about what you're going to find in the data you need to do an experiment and you might need to do different things with that data and you're gonna to have to change potentially how it's collected or change how it's stored or change how it's processed and if you cannot do that because you've got a hardcoded data pipeline。

 you've basically got yourself in a problem from the very beginning。

 So iteration and the ability to change is critical when you're building the data pipeline。

Another example here of a simple pipeline would be your developer and you're taking a data set to be ingested into a pipeline as a CSV file that's one of the more common kind of toy use cases and that could contain structured data right the columns in the rows and the developer would use a utility to compress it。

 let's say it's a very large CSV file and then it would upload that file to S3 and then the data science team within analyze the data and they could use even SQL select statements because Amazon S3 supports that so some of the key takeaways here are that a data pipeline provides the infrastructure for data-driven decisions and this includes things like layers that will ingest or process and analyze and visualize the data。

And data wrangling refers to the work to transform the data to prepare for analysis。

 this is a iterative process and a business problem should drive the pipeline design。All right。

 let's talk about the role of a data engineer here next in a data driven organization。

So if we think about what a dean engineer does。You really you have to think about the correct pipeline。

 so the person that's responsible for building the pipeline needs to ask a lot of questions about the nature of the data and the intent for processing。

That person would then classify the questions broadly into data engineering questions。

 so you're really reframing things so that they fit into the construct of software engineering。

 and then you get that data into the pipeline， you answer some data science questions。

 which a lot of times is about what it is you're trying to predict or solve。

 and then finally you're going to go through and get to your solution。

So if we think about some of the common data pipeline questions here。

 let's go through and think through what these would be， it would be。

 you know does the organization have data that addresses the need。

 Where is the data stored and then in what formats right this is kind of the start of any discussion about building the pipeline and then will I need to combine the data from multiple sources。

 So this could be complex right if it may seem simple first oh。

 we just need to take these two databases and combine the data to to get the thing that we need。

 But the data could be in different formats and different column names and duplicated data So there's some real issues with combining data from multiple sources。

 and then what is the type and quality of the data。And what's going to be the source of truth。

 And this is another problem that comes up quite a bit with a data pipeline is if there is no single source of truth。

 you're going to be constantly chasing your tail because somebody's constantly changing what the source of truth is。

With a security mechanism as well， you know who's going to need access to it and then in what state will need access to it like for example。

 do they need write access， do they need read access， they have right access。

 Can they be trusted to not mutate the data and destroy it and this is very common in an initial data pipeline。

And then what kinds of mechanisms are needed when you transfer the data。

 and then also is it important to have speed when the data is requested？And then finally。

 when you get to the data science side， it would be what can the data tell me how will I evaluate the results。

 what kind of visualizations do I need， What kind of formats and tools are the analysts working with do I need to use a big data framework like for example。

 Spark or databricks or AWs Athena And then what kinds of AI and email models will help me So in the case of a pretrained model。

 for example， this could be very helpful in the pipeline because it could do summarization and you could summarize big documents or you could get the sentiment of a document and put that into a catalog。

 And then finally， what's the simplest way to do AI or email。

 not the most complex and most accurate necessarily， but how do I first get something running So。

 for example， could I do zero shot classification to figure out what the labels are These are some of the tradeoffs that you would consider as a data scientist So to summarize here。

 some of the things to consider are that。There are some key takeaways in terms of data engineering to consider。

Data scientists and data engineers both work with the data pipeline and depending on the organization。

 some tasks。Would be better performed by one or the other。But in general。

 a data engineer is going to focus on the infrastructure and the data science Scient is focused on analyzing the data in the pipeline。

 but in some organizations that's the same role。All right。

 let's talk through some of the modern data strategies here next。

 if we think about a three prong strategy to build you could think about you're working for an organization and they want to use data as a strategic asset。

 so this could be a new initiative， you're going to spend a lot of time helping the organization to adapt to more traditional infrastructures that support data analytics and AIMl。

 so a good example of this would be if your data infrastructure doesn't exist and you want to start doing analytics。

 the analytics， if it fits right into the production system。

 it could actually slow down the production system right if every time somebody asks for an API call。

 it also sends analytics data。You could basically be taking down your system。

 So there's some trade offs here when you're thinking about the strategy。Now。

 if we think about modernization first， this will give an organization the ability。

To respond quickly to changes。In the business landscape and incorporate new features。

You could use AWS， for example， to do the heavy lifting。

 and you could also choose a data store that's going to match the problem you're solving。

In terms of unification。The idea here is that you're going to break down data silos。

 you're going to let other people have access to it。You're going to use， let's say。

 a data lake so you can run queries efficiently and you're going to have governance， right。

 You can't just have all of your data exposed to the internet because there could be legal problems。

 in fact。In the era of generative AI， someone could train on your data and maybe don't want them to train on your data。

There's innovation as well， so we think about moving to proactive decision making。

Maybe using pretrain models， also taking advantage of cloud services。

These are some of the things that could happen with innovation And really what this means is taking advantage of cloud surfaces that have。



![](img/d02ba50d5268e3ae4fecd13a46bda0e5_8.png)

AI and ML included。

![](img/d02ba50d5268e3ae4fecd13a46bda0e5_10.png)

So。Some of the key takeaways here are that organizations want to become data driven and as a result。

 they're going to have to modernize。Modernization oftentimes means moving to reactive to proactive。

 and that means cloud based unifying is about making a single source of truth。

And innovation is about looking for new ways to really find value in the data。

So really to wrap things up here， let's talk about。Some of the things that we covered。

 we talked about comparing and contrasting how data and AIM are different for decision processes。

 and we also talked about data analytics and AI and ML are helpful with predictions。

 but AI and ML by itself。Needs to learn from the data。Versus using， let's say， programming rules。

 and there's four main layers in a data pipeline。 there's ingestion， there's storage。

 there's processing。And there's analysis and visualization。

 and we also talked about some of the actions that take place with a data pipeline cleaning。

 transformation， and we also talked about some of the concerns between a data engineer。

 data scientists， although sometimes in fact they're the same person。

 and then we talked about modernizing， unifying and then doing an innovative approach for building modern data infrastructure。



![](img/d02ba50d5268e3ae4fecd13a46bda0e5_12.png)