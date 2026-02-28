# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p43 43_03_04_流水线自动化.zh_en -BV1tz421i7Ev_p43-

Automating the pipeline， let's go ahead and talk about how this works in data engineering。



![](img/bfc356984b150f2170a7039a27881ea9_1.png)

In this module， we will discuss the benefits of automating your pipeline。

 also the role of continuous integration and continuous delivery and how it applies to a pipeline。

 and we'll also talk about states of AWS step functions。

 and then we'll dig into using step functions to build and automate a data pipeline。



![](img/bfc356984b150f2170a7039a27881ea9_3.png)

So first up here， let's dive into automating the infrastructure deployment。

 an important aspect of automation。

![](img/bfc356984b150f2170a7039a27881ea9_5.png)

If you look at things like standard best practice。You want to automate your environment。

 One of the things I like to say is if it's not automated， it's broken。

 this includes the provisioning， the decommission and the configuration of resources to make sure that a system is going to be stable。

 consistent item potent And so in the past， let's say a cimmin would be manually notified if there was a crash of a server and then that particular human would have to launch a new server。

 and that's a real problem because what if the human on vacation instead of following that pattern。

 another pattern is to use Cloudwatch to automatically detect a crash and then when that crash is detected。

 the admin is notified and a new server with the same configuration is launched in parallel。

 all this happens at the same time and there's no human involved。

 That's really the key here is this full automation。AWS offers built in monitoring。

And also automation tools for this particular type of infrastructure and also to take advantage of these resources。

 you can make sure that your infrastructure is responding quickly to change so you can automatically detect the unhealthy resources launch replacement resources and you can even be notified when resources are changed so the manual step is a antipattern。

 you don't want that， and if you're able to use automation。

 you can improve the stability and consistency as well as the efficiency of an organization。

Now let's talk about infrastructure as code， which is a huge component of this and in general。

 repeatability is one of the reasons why you want to use infrastructure as code because you get the ability to deploy an exact replication of the same environment over and over and over again so you could use cloud formationation template to roll out maybe a development environment and then you could also test the scaling in the application and then afterwards let's say that test is successful you can use the exact same template with just a few changes and they could even be triggered from the environment to launch the resources that have been thoroughly tested in development into production so you're able to closely map。

All that hard work that you put into the development environment into production。

 And if you build infrastructure with code， you're going to gain the benefits of repeatability and reusability when you're building your environment and a single template can be used to deploy network load balancers。

 autoscale groups， elastic cloud instances， E C2 network load balancers that distribute the traffic etc ceter。

 So this one template or a combination of templates can build these complex environments repeatedly。

 so you do the work once， but you benefit from it many times， and if you do this with AWS。

 you can create environments that depend on conditions and you can build things specifically to the context where you're creating it and you can design a template to use different As。

 for example， and you can launch into a development environment or production environment and the repeatability and reusability of this infrastructure helps you deploy consistent。

Infra packages for， let's say， data analytics and ML workload。

 So it's really critical to have infrastructure as code in a modern cloud environment for data engineering。



![](img/bfc356984b150f2170a7039a27881ea9_7.png)

So the key takeaways here are that。You want to automate your environment to make sure that it's stable。

 consistent and efficient and as I said earlier， if it's not automated， it's broken。

 so you can even say it's a bad pattern， antipattern to not have automation and the consistency is particularly beneficial if you're running repeat repeat workloads that require identical processing methods and when you're repeating and reusing。

The two benefits are going to come into play with infrastructure as code。

 and if you're using these templates to deploy the infrastructure。

 you can ensure that the production of ornament is an exact mirror of a development orment。



![](img/bfc356984b150f2170a7039a27881ea9_9.png)

Okay， let's dive into CICD here a little bit because this is part of DevOs。

 the idea here is that you automate every phase of what you do and you have continuous integration。

 you have continuous delivery， you have continuous monitoring and improvement and you have infrastructure as code。

 these are the foundations of DevOs。

![](img/bfc356984b150f2170a7039a27881ea9_11.png)

And so， you know， I think it's important to just define really quick。 what is it。 Well。

 it's a combination of philosophy， practice， tools。 but the core is that you want to move quickly。

 you want to evolve and improve at a faster pace than organizations that are using traditional software development and infrastructure management。

 This speed is going to enable organizations to better serve their customers and compete more efficiently in the market and continuous integration and continuous delivery are to Dev ups best practices and in particular。

 continuous integration。Is a software development practice in which developers regularly merge the code into a central repo and then the delivery or the CD is a software development practice where the code changes are automatically built tested and prepared for a production release So the idea here is every time you check in a piece of code you're improving the system because you're exercising the building and testing and deploy aspects of your code。

 So it's actually strengthening your system as time goes on and continuous delivery is going to expand on C because you're deploying all the changes to a testing environment。

 a production environment and both after the build stage is complete and when that C is properly implemented developers have deployment ready build artifacts that have already gone through this test process and that code can be deployed in a way that requires less manual intervention or even zero。

Intervention and also you can look at continuous monitoring and improvement because of the fact that you have this automation。

 so you're actually getting a feedback loop that helps you continuously improve。



![](img/bfc356984b150f2170a7039a27881ea9_13.png)

Now， if you look at the concept of CICD here， let's dive into some of the details。Well。

 with continuous integration， every time you make a change is going to be verified with an automation of the building test process In the past。

 let's say a developer would be working on what I would call like a golden image or a golden project for months and months and months and they only merge the code changes into the main branch after the feature was completed。

 there's some real problems with this because when you're batching the changes it can be difficult to merge business logic and test logic。

 but if you're doing continuous integration you can be making multiple changes per day and teams are able to be more productive and help themselves develop features faster。

 so continuous integration is going to require teams to write automated testing to improve the quality of the software that's being released and the teams must also write tests that reduce the time that is going to take to validate the new version of the software is good。

And in particular， there are a few different definitions of continuous integration。

 And it's commonly thought that C stops at a build stage。

 And one of the things to bring up is that continuous delivery is going to extend the continuous integration to include testing in a production like environment。

 So this is critical。 Not only are you getting that business logic in the C phase。

 But in the Cd phase， you're actually exercising the configuration for the infrastructure and with cloud。

You're able to define the infrastructure as code。 and so you're getting this amazing verification testing every single time you do at deploy。

 so in fact。Speed is an advantage versus a disadvantage and so by moving the code through the system。

 you're essentially like cleaning the system out， testing out for edge cases and continuous delivery can extend all the way to a production deployment through some kind of you know manual intervention where the code is checked in and then when it's ready to be released。

 Someone just essentially pushes go and then it goes and gets delivered to production so continuous delivery is a huge advantage。

Because it helps teams gain a greater level of certainty that their software is going to work in production and continuous deployment is an automated release of software to the customers。

And this automation extends from the check in through the production without human intervention。

 and the continuous deployment is going to reduce the time it takes to deliver business value For example。

 a new feature an update， etc ceter。 and a development team can get customer feedback very quickly。

 and this fast feedback loop is actually going to give you a competitive advantage because you're able to iterate and release software quickly to customers。

 So there's actually a significant advantage with speed， not only does it improve the in product。

 but it allows you to get feedback on that product and then make changes in the future。



![](img/bfc356984b150f2170a7039a27881ea9_15.png)

So the key takeaways here are that C CDD spans the development and deploy stages of the software development lifecycl。

The continuous delivery is going to improve on continuous integration by helping teams gain a greater level of certainty that the software work in production。



![](img/bfc356984b150f2170a7039a27881ea9_17.png)

![](img/bfc356984b150f2170a7039a27881ea9_18.png)

Al right， so let's talk about automating with step functions。

So the idea here is that step functions can help you coordinate components of distributed applications and microservices by using visual workflows The step functions provide a reliable way to coordinate components and step through the functions of an application and the service has a graphical interface that can visualize the different components as a series of steps。

 and that step function automatically initiates and tracks each step and even retries if there's an error。

 and so the application runs in the correct order and as expected and it also integrates with higher levelve services like Amazon Athena which is a service that lets you query things in SQL。

And you can actually use step functions to start and stop a query and get the query results and with step functions you can do a one time or scheduled data query and then receive the results back from S3 so Athena is serverless so you don't need to set up or manage infrastructure。

 you're only going to pay for the queries that you need。🤧。

Now let's talk about how step functions work here。In general， you're going to define a workflow。

As a series of steps and transitions between each step and a workflow is called a state machine and the states are elements in a state machine。

 so the state machine is an object。That has a set of。

Operating conditions that depend on the object's previous conditions to determine the output。

This means that an individual state can make decisions based on the input。

It can perform actions and then pass that output to other states。

And the tasks do all the work in the state machine。

 and a task performs work by using an activity or lambda function。

and then passes those parameters to the API actions of another service。

 and each state machine starts with an input and that state transfers the input and passes it to the next state。

 and this is a huge step。I that with step functions console。

 you can visualize that state machine and get almost real time information on what's happening inside。

 So this is really a huge win for something like a data pipeline。

 which can be very complex because you have a chain of reactions。One thing goes into another， et cea。

 but you can look at each of the inputs and outputs of those steps。

So let's talk a little bit about the step function interface here in general。

 the workflow studio allows you to drag and drop like Legos and the actions panel will let you look at the different AWS APIs and you can provide different flow states as well like try this or try that or go sequentially in order。

And then the other thing to be aware of is that you can choose a state from the action or flow panel to add to the workflow。

 drag it and drop the state to the workflow in the canvas area。

 and then a line is going to show you where it's going to be placed in the workflow and then when you add a new state to the workflow its code is automatically generated so the idea here is that within a workflow。

 you can drag and drop states to move them to different places。In a workflow。

 and if your workflow is complex， you may not be able to view all of it in the Canvas panel。

But you can use the controls at the top of the canvas to zoom in or out。

 and then you can view different parts of a workflow graph and you can drag that workflow graph into the canvas。

And if you have already added a state to the workflow。

 you'll want to configure it and you can choose the state。

 you want to configure and it's configure issueu options appear in the inspector panel and to see that workflow code。

 you would choose the definition panel and then that code is going to be associated with the selected state that's highlighted and if you look at the different state types that are available in the functions they perform。

 these will all give you an overview of what is actually happening with the service。

So let's get into the state types here next， every state has a different function so a task is a single unit of work performed by a state machine and all the work in the state machine is done by task using an activity or Lambda function。

In terms of pass， this would be passing input to the output， This is optional。

 and you could add fixed data into the output。 There's also choice。

 so you could add branching logic to your workflow and in the configuration tab of the inspector panel。

 you can configure rules to determine which state the workflow will transition to There's also parallel。

 you could add parallel branches to your workflow。 There's also weight。

 so you can pause the workflow for a certain amount of time or even to a specified time or date。

 you can map， you can dynamically iterate steps for each element of an input array like for example。

A map state will process the same steps for multiple entries of an array in a state input。

 there's also succeed， this would stop the workflow with a success， and then there's fail。

 which would stop your workflow with a failure。And a thing to be aware of with a pass state。

 it's going to pass the input to an output without doing any work and these are good for constructing and debugging state machines。

 almost like a print statement and the slide in terms of looking at it in the console which show things like a single pass state and when you're looking at a state machine run。

 it helps sometimes to inject some fixed data which you can use for a testing purpose。

A few things to be aware of are that a choice state is going to add branching logic to a state machine and a choice state must have choice fields。

Where the values are non empty arrays and each element in the array is going to be an object called a choice rule and a choice rule is going to contain the following。

 It's going to contain a comparison。 This would be two fields that specify an input variable to be compared。

The type of comparison and the value to compare the variables to。

 and then the next field is the value of a field that's going to match a state name and a state machine。

Now the parallel state is also going to create a parallel branch in the state machine and a parallel state causes step functions to branch out and these start with state that's named in a branch called start at field and this happens concurrently so the workflow will wait until all the branches reach terminal state before it processes the parallel state next field。

 and then the weight state is going to delay the state machine from continued for a specific amount of time。

 almost like a sleep and you can choose either a relative time which is specified in seconds from when the state begins or an absolute time which is specified as a timet and you can use a weight state as a form of timer for your workflow。

You can also use the map state to run a set of steps for each element of an input array。

 so while the parallel state processes multiple branches of a step step by using the same input。

 a map state can process the same steps for multiple entries of an array in the state input。

And a succeed state will be able to stop a running state successfully， and this would be useful for。

 let's say a choice state that does nothing except for runs a task and because a succeed state is a terminal state。

 they're not going to have a next field and they don't need an infield。

A fail state is going to stop the running state machine and market as a failure。

 which is great for you from an instrumentation perspective because of all the great debugging information you get and the fail state is going to require the type field as well。

 and so basically the fail state is going to allow the following optional fields a cause so this could be a custom failure string that you use for operational or diagnostic purposes。

 So monitoring instrumentation there's also an error and this could be an error name that can be used for handling like retry。

 a catch， operational diagnostic etc and because a fail state is always going to exit。

 It's not going to have a next field and it's not going to require an infield。

Stef functions are integrated with Athena to build workflows including Athena queries and data processing operations and this integration is a great way to build reproducible scalable data processing pipelines as part of a larger application and you obviously can call these from the CLI as well and it's a great way to trigger it and if you look at raw data in let's say tab separated value or TSV value that data is ingested daily and as the information is ingested。

 the glue crawler could provide updates to the raw data catalog and then you could use Athena to unload the statement to convert the data into a parquet format and then after conversion you could send the location of the parquet file into SNS notifications and then SNS could notify a downstream application to take further action and then one common example would be to initiate a Lambda function that uploads the Athena transformation。

Into let's say， redshift。

![](img/bfc356984b150f2170a7039a27881ea9_20.png)

So let's talk about some of the things that we covered here in general。

 we covered that step functions allow you to do a visualization of complex workflows and to coordinate the components of a distributed application of microservice so really they're invaluable for building cloud-based data engineering pipelines almost like a secret weapon and you also can define a workflow as a state machine and there's a series of steps and transitions between each step and then also step functions are integrated with Athena to build workflows that include Athena queries and data processing operations。

 Another thing I'll point out here as well about this is that。Using rust。

 which is now generally available， is also a secret weapon on top of another secret weapon because of the performance aspects of it。

 you can get millisecond response time。 you can use some of the lowest sized lambdas as well。

 And so I would say the combination of step functions with rust and also with cargo Lambda is really an emerging pattern for 2024。

 2025。

![](img/bfc356984b150f2170a7039a27881ea9_22.png)