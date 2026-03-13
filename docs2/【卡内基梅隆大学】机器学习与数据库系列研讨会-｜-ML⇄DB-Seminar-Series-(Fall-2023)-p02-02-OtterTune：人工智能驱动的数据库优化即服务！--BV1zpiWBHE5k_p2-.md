# 【卡内基梅隆大学】机器学习与数据库系列研讨会-｜-ML⇄DB-Seminar-Series-(Fall-2023)-p02-02-OtterTune：人工智能驱动的数据库优化即服务！--BV1zpiWBHE5k_p2-

![](img/9e76872ae7b5d2a4a41c2bffa1656712_0.png)

🎼The databases for Machine Learning and Machine Learning for databaseases Sear series at Carnegie Mellon University is recorded in front of a live studio audience。

😊，🎼Funding for this program is made possible by。🎼Ggle。🎼And from contributions from viewers like you。



![](img/9e76872ae7b5d2a4a41c2bffa1656712_2.png)

🎼Thank you。Hi guys， welcome to another session for our seminar series this semester。

 we're excited today to have distinguished Carnegie Mellon Data Group alumni。Dana Vananagen， Dr。

 Dana Vananagen， she finished her PhD at CMU in 2021 and since then she's gone off to be a cofounder with me and the CTO of Ottertune and so which in my opinion is the commator ML or AI for database tuning service and so she's here to talk about some of the things you've learned and some of things she's been doing at Ottertune so as always if you have questions for Dana please unmute yourself and say who are and fire your question off at any time and then if you can't unmute yourself post in chat and I will interrupt Dan and and ask her question so Dana the full short thank you so much for coming back。

All right yeah thank you Andy for having me again my name's Dana I'm the cofounder and CTO of Otterton along with Andy so today i'm just here to talk about Otterton and Andy gave a great intro I have been working on Otterton for a long time now and've working on it since 2015 so it's about eight years and I guess about three of those years has been between two and three is you know Otterton the commercial product。

😊，So with that。I've lost my mouse again okay。Here we are。So with that。

 let's get started with the talk。I'm going to start by discussing some you know background information。

 all kind of explain what you know a tuning service is and introduce Ottert to Di level。

 then I'm going to spend some time reviewing what Otter tune the academic version was and sort of what the algorithms were and you know what that looked like back then。

Then we'll kind you know， under keep it real， we'll go over some of the some of the assumptions and you know。

 incentives that didn't quite pan out， you know， from from the academic version to the commercial version and some of the stuff that we had to go back and really think about how to you know。

 fix once we're launching Altitude as a real product。And after that， we will conclude。All right。

 so we'll get started with some basic background about database tuning。So you know。

 I feel like I've said this sentence so many times because I you know。

 databases are just not notoriously hard to tune finding the you know。

 right knob configuration or you know the。😊，The most efficient queries or like the right partitioning scheme。

 it really depends on the workload and the hardware and the data and other factors。

 so it's it's you know traditionally a very manual problem that has been solved where。

People you know will hire human experts often in the form of DBAs to you know come help tune their databases。

 they might employ them full time， but you know ultimately like with you know the increasing complexity of today's systems you know their Postgres and MySQL are always adding more knobs finding these human experts is you know they're harder to find these days and they're also quite expensive to employ so you know at the high level what Autot brings to the table is just an automated service that uses machine learning to be able to you know automatically configure your database and optimize it。

All right so again the Autot is an automated database tuning and resource optimization service as we already covered it is based on research that out of Carnegie Bellen University that I worked on with Andy during my PhD and know at the CrosV just uses machine learning to help optimize and the configurations of the DBMS so one thing to note is that the academic project was only focus on configuration knobs and the commercial product we've expanded the offering and the types of tuning that we can provide to include Knobs indexes queries cloud configuration we also provide some you table level recommendations and statistics or stale so we provide like a whole lot more than we used to。

And as far as you know what we support right now， we currently support Amazon， RDS and Aurora。

 and specifically MySQL and Postgres as to why， you know providing like not supporting on prem databases was more of a strategic decision and that Amazon provides a lot of like you know normalization standardization around how you can apply knobs。

 you know how you can collect data so that actually simplifies it quite a bit so we're not know writing one off like clients。

 you know to go collect data from you know this place than that。Ds。

 somebody' asking you whether do you support Aurora serverless？We do， yes， we do。

 we also support Aurora serverless， we do。And okay， yeah， for both My SQL and Postgres。

 good question。So next I'm going to go ahead and hop into going over the you reviewing the academic version of Otterton。

So。Yeah。Oh， hellello， okay。I wasn't expectable of that I thought it was a little bit more staggered but that's fine so do you see the little hat there's like a little academic hat next to Ottert I just had that hat there to indicate that we're talking about the academic version of Ottert so hopefully that will help distinguish you know which version we're talking about。

So， you know。Basically to go over an overview of how Autottertune works in the very first step。

 the user will select the target objective that they wish to optimize for。In commercial Autoudoo。

 we highly recommend the query latency and that's what a lot of our customers choose。

 but this could be the throughput， it could be the CPU utilization， it's really up to you the user。😊。

And with that， we provide a you know a。An agent that users can deploy in their own environment and what that does is it will connect to the database and collect various forms of telemetry。

 including the configuration knobs， the database runtime metrics。

 commercial audititude also you know collects query information。

 so that is the purpose of the sort the clientside agent。So you know。

 the Autottertune will periodically collect this information from the database system and send it back to the tuning manager。

 which stores it in the data repository。And so there's something that we refer to in the paper as an observation period and it's just a period of time where you're you know collecting these metrics。

 I believe we collect metric information once a minute or maybe once every five minute。

 but the observation period this period of time where you want to observe a given configuration to before you knowquenching on the data and deciding which configuration to。

To suggest next。So again， we're going to include the most recent observation and that tuning data。

 we're going to crunch on the data， and then we're going to spit out the next configuration。

 the auditudton believes will improve you your system performance over the baseline configuration and configurations it' suggested so far。

And so as far as like what the differences between Ottertune。

 the academic project and commercial Autottertune， so again we support AWS so in the first step。

 the user must grant us a number of IAM role permissions， this is to collect CloudWatch data。

 RDS data， performance insights data and optionally they can provide this with right permissions so that we can actually apply configurations directly to the know their database on behalf of the user。

In addition， you know this is additional data that we collect down in step three。

 and then finally when you know we go generate new configurations。

 a commercial version of Otterton will also generate health checks， you know index recommendations。

 career recommendations and etc。Then a quick question。

 do you ever end up with a situation where the telemetry data can become much bigger than the actual database？

Well。😊，I don't think we're quite there yet， although I was just talking with our engineering team about。

How our storage is starting to explode I guess we collect about8 gigabytes of telemetry a day。

 so we're starting to have to think about that， but am I answering your question correctly？

Yeah yeah yeah no and the reason I ask is you know the Microsoft guys always complain if they start collecting all telemetry it'll be more than the customer data in less than a year so I was wondering if you're starting to see some versions of that problem especially if on the smaller databases which sometimes are very valuable then many enterprise valuable databases are not that big they might be sub hundred0 gigs and you could easily get there。

😊，Great， good。We're just starting to get there and we are probably going to have to put a customer policy in place soon。

 you know alerting them of how much history we can provide them because right now we provide the whole history so yes。

 that is starting to become a problem。So what I'm going to go over now is just kind of the motivation for Ottertune way back in the day in 2015 when when Andy and I started working on this problem so well Ottertune is it's an external tuning service meaning you know it's not like built into the codeb of My SQL or Postgres it can hook onto any database and the goal was to make it you pretty extensible right so maybe you have to provide it with the knob names and some basic metadata about the knobs but you don't have to provide it with any domain knowledge so you can you can pretty much you know take the same algorithm and use on Postgres use on MySQL。

Use it on， I don't know， cockroach and so on。嗯。And， you know， the。To make that happen。

 like a lot of the techniques that we came up with were you know automatic they you know。

 everything in that algorithm in the machine learning pipeline was pretty much automated。

And so you know the main idea behind Ottertune is you know tuning takes a lot of time and uses a lot of resources。

 so the idea was to leverage the training data who we've already collected from previous tuning sessions to help to new DM deployments that come along more efficiently。

And so the way that we do this is we're going to train models from the data in our all of the you know previous in historical data in our data repository and we're going to use that data to help us figure out you know which are the most important knobs and and also to try and find which of the workloads that we've seen previously is most similar to our current workload。

 and then the idea is that we can reuse the data from the most similar workload you know to help bootstrap and jumpstart the tuning process while there's a no data for the new deployment。

All right， so a little outline of the algorithm， so at a high level。

 this is the otter tune machine learning pipeline， two of the parts。

 the workload characterization and knob identification those run in as background processes and then the automated tuning component is the algorithm that's going to be interacting and generating configurations after each observation period。

So the workload characterization period or excuse me the workload characterization is a data reduction method。

 so basically what we're doing is we're feeding it all of the as you know somebody pointed out there's a ton of metrics we're going to feed in all of that metric data and try and prune and find a subset of metrics that captured the distinguishing characteristics of different workloads so for this we've used a factor analysis and clustering but there's you know this was back in 2017 there's been a lot of great papers published that use you know other techniques so at the high level is just a data reduction technique。

Similarly， for knob identification， we're going to analyze all of the data in our repository and we use the LAO algorithm。

 which is a feature selection algorithm to try and determine you the order order of importance of the configuration knobs and you know this is very helpful for trying to you decide which are the most important obs tune。

As。You know as I'll go over next， the automated tuning component uses a form of Bayesian optimization and the algorithm is much more efficient with fewer configuration knobs。

 so that's that's the real motivation there。All right。

 so for the automated tuner component it has two parts。

 so the first part it does the workload mapping so using the data output you know the set of metrics output by the workload characterization component it's going to you know compare those metrics across the different previous workloads that we've tuned in the past with the current target workload which is the workload that we're trying to tune and it's going to compare those metrics and basically figure out which is the most similar workload to the current one that we're tuning。

That's when we start part two so once we figured out that out we train a Gaussian process model off of the data we've collected so far from the target workload along with the data from the previous workload that we deemed you know most similar to the target so we're going to train them all all in that and in order to generate the next config and so the way that the algorithm chooses the next configuration to recommend is it trades off exploit and exploitation throughout the entire tuning session so sometimes it will choose exploration which means it's going to try data points that it knows very little about and then other times it will try exploitation which is where it's going to try。

Typically， data points that performed really well in the past that it does know about。All right。Next。

 we'll go over some of the assumptions that we made in the paper。

There's the right I was hoping I would highlight。You know， our machine learning research。

 along with many other papers， make certain assumptions that don't quite pan out in the real world。

So one of these is just that the optimization process is just a one time offline activity。

U we we also kind of assume that the DBA has， you know。

 the tools needed to deploy a copy of the database on， you know， similar hardware and sort of。

 you know， recreate that that workload。You know， separate from the production machine。

The workloads you know inevitably because it's really hard to get access to any sort of real data。

 we use benchmarks and because of that we only really see like the efficacy of these algorithms on you know benchmark data which is static you know it's fixed。

 basically we can get away with doing an observation period in five minutes we can just look at five minutes worth of data to determine you know whether like what the next configuration should be because it's just like very it's just static。

And finally， we sort of take for granted how difficult it is。

That like if we assume that there's a knowledge base of high quality data available or the ones like。

 you know， readily easy for us to access。And so this is。

 you know these are just a few of the items where there's a little bit of a disconnect between research and industry and it certainly doesn't mean that the you know research is not impressive by any means it certainly is impressive。

 but you know， Andy and I kind of， well especially Andy， but like myself。

 I still have you know one foot a little foot in the door in academia。

 I would love to see you know more problems being solved in research that are a little bit more relevant to the problem I'm working on now。

嗯。Yeah I think that brings us to the next section， so yes in this section i'm going to just give a few examples of you know like I just named the assumptions。

 let's dig a little bit deeper there。All right so challenge number one it is not practical to tune every database offline in a repeatable environment well there's I mean there's a lot of reasons for this。

 but at a high level the sort of two setups that that we looked at you know what while I was a PhD student were either。

Trying to tune the staging database and then take those you know take the optimal configuration for the staging database and apply it to the production database or do like sort of a workload replay where you're copying the workload we learned very quickly with one of our initial customers that staging databases honestly like for most of our customers and and ourselves staging and dev databases don't look anything like production database so what happened is we tuned the customer staging database and they got a 15% you know production in iOs which is cost savings you know because they're on aurora but then once we applied the same configuration to their production database we only saw you know 1% improvement and you know in retros right now I'm happy that it didn't make things worse but you know didn't help。

So。Yeah the other one I kind of touched on users can't capture workloads and replay them not easily Oracle has this database replay tools that's just amazing honestly。

 but sophisticated tools for replaying workloads and you know capturing the traces and making sure that you know。

I guess getting it's a repeatable environment and you're getting stable results that those tools don't exist to the best of my knowledge from MySQL and Postgres to the degree that for example。

 Oracle has them so this is you know this is another thing that didn't pan out。

So what ended up happening then right well interestingly what happened is a bunch of our customers tune their production databases directly we've you know kind of earned that trust and we have various safeguards in place to make sure that you know we don't harm or you know caused any degradation to their database I'll go into that later but this graph right here is just showing that actually 55% of our customers I collected this data on Friday。

 these are active customers who you know have applied configurations within。

I don't know that like the past week or so and 55 of them 55% are actually tuning their pro database directly unknown here like actually the way that I determine this is I look at the name of the database or the tags you know the AWS tags in the environment a lot of them will just saypro so unknown just means like there weren't any hints about what kind of database it was。

All right， you， can you say how you got the hints？how do you know what the type is？Oh， sure。I just。

 I hold on， sorry。Okay， let me go back here， there I am basically like。

So the database identifiers is the name that the Amazon lets you assign to a database and a lot of people will just name it like myprod DB or like I don't know EU EU somethingprod EU app app1prod so that's one way like if they have pro in the name of the database or if it's an aurora cluster it's the name of the Aurora cluster then that's one in the hints。

 the other is the Amazon lets you assign tags to various resources which can be helpful with like billing or just trying to figure out you know classify which of your resources you're using for production versus staging versus dev so a lot of people will use exactly those tags like Pro staging dev to distinguish their resources so that's the other hint。

Thanks。Yeah all right， yeah so collecting large amount of high quality training data is hard。

 yes it's very hard so you know。😊，你最佢。OhI should switch these points but that's okay so one problem is that like workloads are not static at all like honestly I just popped in looked for a customer you know for a few months for a customer immediately like here's this you know this image of the CPU utilization that I came up with like this is over the course of a month is you can see you know it looks like theres there's you know a period where the the workload demand increased over the course of the month and then kind of what's to say is like it's not a it's not a repeatable baseline it's not a repetitive pattern necessarily so this is you know one way in which like the data is just itself not as high quality and so how do we you know how do we solve this as a company well luckily this this is a pretty noisy example a lot of our customers you know we support My SQL and Postgres。

they have transactional workloads and they tend to be quite cyclic and you know exhibit like you know day night diurnal patterns so therefore like whereas we were using the observation period of five minutes in the research paper we now use an observation period of 24 hours because that usually kind of captures the full cycle of you know the workload。

 but what this means is you know whereas we were could capture 288 data points a day with the research we're now capturing one a day so you know collecting this data even though we're a company now we have real workloads you know we still don't have the data that we need actually next bullet we still don't have the data that we need to build generalizable models you know for that we need training data for diverse set of training data for workloads hardwares configurations and probably more。

So the， you know， what that means is that basically like a lot of。

A lot of our work on like the workload characterization。

 building those generalizable models and you know trying to reuse training data。

We just don't have the data available to be able to do that。

 so we have to you know try different strategies and I'll be going into those a little bit later in this presentation。

嗯。Yeah， and so we just own't yeah， last points we don't have the training data to use such techniques effectively。

So the other major differences of course is we have real customers and the number one rule of customers is you do not crash their databases weve I would say we spent a lot of time and put a lot of thought and effort into trying to build trust with our customers interestingly like when Andy and I you know in Bohan incorporated this startup。

There weren really any products like ours on the market you know like I think the distinguishing factor is we can actually take you know a configuration and and apply it on behalf of the user so we really do automate the full loop and there weren't I don't believe like any。

Companies that we could really look to for how they handled that。嗯。Yeah， so so， you know， overall。

 we have to be very careful with， you know what we're applying to the database。We。

We spend a lot of time thinking， you know， it's not just I would never like just throw the algorithm or just pass along to the sorry the knob characterization or sorry the。

The future importance algorithm for knobs I would never just you know take the opposite of that and hand it to a customer you know we we really do have to have to look at you know what we're。

What we're recommending and make sure that it's safe。嗯。

Customers care a lot more about stability than peak performance。

 peak performance is inevitably what we you know measure in research papers it makes sense。

 but at the end of the day like if you're getting a if the customer workload is stable and like you know performance is up a bit like customers are happy。

嗯。The other major thing that was hard for us was time to value so how how do we show the customer you know how do we show customers the benefit of using Autot and days I mean ideally it would be minutes but you know like I said once we change the tuning interval to 24 hours you know it could be weeks before before they they before the algorithm converges on you know a new optimal configuration so we we've had to think a lot like this was you know a lot of the incentive behind offering health checks among like index and query recommendations is just you know we need to provide value immediately and then the other thing that goes along with this is we also need to set customer expectations on the length of time these things will take。

A lot of customers just don't really they want something where they just click a button and everything works。

 but some of them will you know want to add every single knob like in in the whole entire you know selection of knobs that we like add one addd and I've seen like two customers in our time add the full selection and of course like if you do that I mean the time that would take to con or tune is just astronomical so you know we we've been trying to think about like the best way to educate customers about sort of like the behind the scenes。

 the machine learning without you know。Diveulging too much， I guess。

 so that brings on to keeping its straight。So。You know to overcome some of these challenges。

With' you it's it Dan or some questions questionss in chat， sorry， oh I'm sorry。

 that's my thought so Ash Katie， when I'm muting and asked your question？😊，Yeah。

 so I was just wondering so what happens if autoune itself crashes or do you like purchase the information somewhere or it's like the customer or it's like the database's responsibility to。

Verssus the configurations that Autot recommends。So I think okay so the question is like what happens if ottert crashes Yes luckily we haven't had to deal with that。

 but let's what does happen sometimes is like the the client side agent will crash and so I think that the question is like。

う。I is the question like how do we recover those configurations or how do we guarantee that they're applied or？

How do we recover the configuration？Oh okay， well so the the configurations are stored in our back you know stored in our backend database but is。

I would say like we can easily recover a similar configuration by just rerunning the algorithm on the same data of course。

 if we lose all the data， then we would be in trouble Okay thank you。

Amazon does versiongeoning for the configurations as well。

 so Amazon' is storing this stuff and that's persistent for us as well Okay， thanks。

And then Wayne asked， have you looked at evaluating the contribution and usefulness of a particular data point？

Rand do you want to extrapolate on that？And有。Well， you're very low， your volume。

All right I can't hear him。And so he' was asking。So he was asking， look， have we looked at， say。

 like for a particular data point？I guess across multiple data points in a time series is one more valuable than another。

NoNo， I don't。It says from a few slides go looking at five minutes of data versus one day of data。

Wait why do you choose one day versus five minutes？Oh oh sure。

 So the reason that we choose one day I probably just sped right through this is because most of our customers have periodic workload patterns where you knows there's really like no activity at night and it starts picking up in the morning gets busy you high demand in the afternoon and then goes down in the evening so we can kind of sort of generalize and try and pick good default values based on the characteristics of most of our customers workloads。

So that's why we pick the 24 hour tuning period specifically you can imagine that actually and we do have this sometimes and we're able to guard against it bit you know and ignore weekend data but a lot of times like over the weekend the data that we collect will not be as will not be representative of the actual workload because I don't know maybe the business isn't open depends on what it is right so those data points kind of are misleading for the algorithm that's a hard problem and we like I said we can we can ignore weekend data but that's about the best we can do it's just a matter of collecting more and more data at that point and I'll go in actually when I'm going go into this section will touch on that a little bit more。

It becomes less of a problem the smaller the search spaces。Any other questions， Sandy？

I have a question。Yeah。So I was wondering how Autotune is able to balance tuning parameters like where optimization objectives。

 maybe there's some optimization related to latency or the query of S query runs。

 there might be different optimization objectives as I understand that my conflict and the tuning parameters I'm assuming is like a limited set。

 maybe you have 10 or 20 parameters that you might choose to optimize for autoune。

 so with such a small set and the objectives that can vary how do you balance which values should choose for any given parameter。

嗯。Great question。The way that we do this which I'm actually going to go over in this section is we constrain knob ranges and this is most important for knobs which many of them are like resource related knobs right so knobs that control memory buffers you know knobs related to the number of processes so we basically like we know the customer hardware and we you know purposefully choose conservative knob ranges that are the values that these knobs are allowed to take during the tuning session they can take any usually any like value in between those ranges but not outside of them does that answer your question。

So I understand that the ranges exist， but do you somehow prioritize the performance objectives somehow。

 or do you allow the user to specify which is more important to them？

Oh yes yes so that is correct so when the user first starts using Autotune we have the tuning options panel where they go in and they can choose from a number of you know predefined target objectives that we've added over the past few years so that would include like the query latency inputput CPU utilization the Fer customers you know minimizing reridediOs is important we haven't actually gotten any requests for additional target objectives。

 but yes we do let the user define that。Thank you。😊，嗯。Okay。

Yeah so let's let's go ahead and jump in and oh and I'm running out of time okay I'll try and speak through a little bit all right so。

Sorry kind of rushing through the st step back the way that we solve a lot of these problems。

 which is kind of a no known research is we incorporate a lot of domain knowledge。

 The reason I say it's no known research is because you know that's kind of I went over some of like the。

I went over our goals with like the first audit to paper and we wanted to automate everything so that somebody who has no knowledge of the database can go in and use the algorithm and you know it spits out like they can use it without any domain knowledge。

But realistically like in the commercial product，corporating don't main knowledge has been very。

 very helpful on two fronts first。It's you know， sort of the way that we implement a lot of the safeguards。

 I'd already mentioned the knob constraints which I think I'll go over the next slide。

 but then it also allows us to to reduce the search base of configurations。

 which is incredibly helpful as because right now in research I frequently look at papers and the convergence time you know can be。

Dozens， hundreds， so you know we don't need to reach convergence at Autotune but we do need to start seeing a benefit and I do acknowledge the way that we do this by restrict using basically what we know about MySQL。

 what we know about Postgres， what we know about databases。

 what we know about workloads to you know try and really restrain the search base to values that that might be good。

嗯。So yeah， like in general， I think research is spot on like for most databases and workloads。

 there's probably 20 knobs that are really going to matter for that database。

 it certainly is going to vary by workload but you know trying like being able to narrow down the search base from you know hundreds of knobs to just you know 10 to 20 is very big。

So you know like we actually did this in the academic project but some of the ways that we do this are we remove you know knobs that really aren't tuneable and don't make sense to tune like it's the port or they required human judgment and you know could you know caused consistency issues and database and oh actually this is an interesting tidbit in the initial version of Autottertune we offered a database restarts so customers could actually tune you know parameters like shared buffer where it required restarting the database but in the history of like two years nobody had ever enabled it so we didn't you know the functionality still available in our backend but but we just don't expose that to users anymore until we can think of like a little bit more clever way to provide that。

嗯。We also do you know use like automated feature selection techniques。

 we have a data analyst who does look at the data and we you know。

We do some some automated analysis to determine you know the most important knobs， for example。

 but at the end of the day， like a lot of a distilled manual。

 Bohan and I and sometimes Andy are looking at all the knobs before they go into production。

And right now Autottertune recommends between 10 and 20 knops per database systems。

 you know for customers they're just getting started with tuning RDS Postgres MySqL have the most you know Aurora remove some of the storage parameters so that's why you know they decrease a little and then serverless I think removes a couple more so there are fewer knobs to tune with Aurora and Aurora serverless。

But you have a question with the audience， Matt Matthew， you want to ask you a question？Sure。

 I was wondering you're talking about configuration。

 I was wondering if you've done any machine learning on the output of explain for。

Maybe high frequency queries or。Any queries？I am not no， Andy have you or has both so we don't get。

Right now in auditing the commercial version， we don't get the output to explain from customers because you have to enable that。

There for Postgs's an extension enable for the CMU database group of research。

 which is separate from an autot tuneune， yes， we do ML on the output to explain and analyze。

So you can't。You can't generate your own queries as that in the product。

we can't generate query plans in the product， I do have a line I do have a student working in research to inject plan hits into Postgres using PG plan hits based on tuning optimizations。

 which is completely separate than the commercial product。Oh， thank you。

Right yeah so just going over the constrained knob ranges。

 this is just this couple of screenshots of our UI for the tuning options where you can select which knobs you want to tune and we provide for between 10 and 20 knobs that are the recommended knobs we come up with the bounds for users and honestly it's a lot of work to come up to save bounds so it's pretty valuable users if they click the show other knobs button at the bottom。

 they can go in and tune whatever othernobs they want but they have to pick out their own knob constraints。

Yeah， like I mentioned we do a lot of testing before adding you know new knobs and we really think about the。

You know， the range of allowed values。And this is especially important for knobs like work men。

 which are known to be a little risky de tune。Obviously have to use domain knowledge like the we know that those don't get you know that's not just a single memory buffer in the database that gets you know applied per connection or I think it's more complicated than that but these are important things for us to take into account when choosing this yep and customers are allowed to go in and change this but we are you know we know with high probability that those values that we provide customers are safe。

嗯。Yeah， so what you know how else do we incorporate domain knowledge so you know in order another way that we can help speed up the。

You know the convergence speed of the tuning process is to help the machine learning algorithm discover you know good regions in the search space so one example of doing this the domain knowledge would be you know we can take the the recommendation from PGT and you know use that when we're like bootstrapping you know when we're first starting the tuning process to try and kind of land around like a good search region。

嗯。Yeah and then and then even after that you know so it's it's helpful to try settings that are you know generally known to be good for most databases there' are no kind of best practice guideline settings it's it's helpful to try those at the beginning of the tuning session and then you can also try them later on we you know periodically kind of randomly will include some some heuristic based。

Recommendations when we like send off the full recommendation to the user。All right。

 so manual controls and feedback so we're going of。

Kind of done with the domain knowledge bit for now these are mostly just these are part of the tuning options panel。

 these are some of the safeguards and you know configurable things in the tuning options that we provide customers。

So the first would be the tuning mode up here so the tuning we have three tuning modes at the very bottom you'll see self-directed tuning this means like we we can't touch their you know their parameter group which is how we apply the configurations they basically we provide the command limit prompt to that they can copy and then paste in their own terminal you know and use the AWSLI to apply the knobs so that's self-directed we don't apply anything on behalf of the user the other two are where we do automate you know the tuning loop the first one is auto tuning so that's like fullfledged we don't ask for the user' permission you know when applying knobs of course the knobs you know are constrained to the values and that we showed in the previous slide but it's just kind of you know there's there's no。

huan in the loop there， whereas the second option which is in the slide or in the screenshot the currently selected one。

 it's called manual review and it's basically like you as the user or somebody on your team needs to review and approve this configuration to be applied and then we'll go ahead and apply to the database。

I think oh nice okay so I was curious like how you know who's who's choosing what so looks like only 12% of our active users that are you know actively tuning their databases are are choosing the selfdirected tuning mode which is pretty good if you look at it from a trust perspective so unsprisingly manual review is is quite a you know a bit more popular but about 30% of our customers just kind of let us go at it so that's's pretty impressive。

嗯。AndLet's see it's the second Oh yes， and then you know。

 what what we hear from some customers is what we heard for a while was like they。

We just provide a bunch of knob configurations and they don't really know what they mean they don't really know why this value is better than that value。

 so what we've been trying to do is like incorporate more explanations in graphs in some cases to kind of explain like why we're choosing this setting or you know why we're making this recommendation。

Oh performance improvement so you know like the big question is always like okay。

 so given all the noisy data and you know all of the all of the challenges that we discussed and in the second part of the talk like or are we even seeing any re providingroviding benefit to our users and the answer is yes and actually quite a bit of benefit so I guess for RES we're seeing on average I think it's about like 35 40% improvement whereas Aurora we're seeing maybe closer to 50% improvement？

And this is。Actually， this covers a number of target objectives so it's just whatever target objective they chose Andy had asked Andy had like mentioned hey。

 you should try and figure out like why Auroras more why are customers getting you know more benefit with Aurora than RDs and of course I didn't actually have time to like really look into it but I was thinking about it and I'm curious if like the difference in I think that RDs is closer to 20nobs Auroras closer to。

Maybe 12 I would have to double check but I'm wondering if the we're just tuning fewer knobs so people are seeing more benefit more quickly I really don't know so that's an open question that we're going to try and solve but very interesting。

You know， in some cases some people are seeing you know a lot of benefit。

 these are typically people that you know I'm guessing haven't really done any tuning on their database。

 so the number of people that have done zero tuning you know is around 40% quite a few people have done some tuning which is which is a bit surprising。

And so presumably like the low values here might be people who not only did some tuning but tuned it well。

 you know， hard to say concretely。Does Z rep like combine these stats of like whether I'm trying to optimize for CPU or you know。

 iOs and just kind of combines them all together？That's correct， yes。

So is this graph corresponding to the initial optimization page phase when Autot converges initially？

I I think the answer is yeah， so basically we consider the baseline configuration， you know。

 the configuration we're trying to be the first configuration that we ever received from the user。

So this is basically comparing the。I think bo so Bohan's the one to prepared this data and he probably like looked at the。

You know， the the data points， the time series parts that were relevant to the tuning sometimes where we were applying configurations。

 I don't know if you know， if somebody had their。Agent connected for three years I don't think it was looking at that data。

 but yes， it's just basically like the the best configuration that we recommended the percent improvement over the baseline configuration。

I guess what I'm trying to get at is once the model does converge initially and you have a good tuning set of parameters with the workload。

 I guess this depends on if the workload changes over time。

 but what's the marginal benefit over time as you continue to reoptimize what has your experience been with Auto team customers？

That's funny I actually took Andy's slide that kind of answers this' it's just at the end of the slide deck I can go over it quickly if we have time but that's that's actually one of the open problems that we're trying to solve now most of our users because audit tune once you get it set up is pretty seamless they just kind of let it run you know for a long time and it's really easy to turn on again once you've turned it off so that's not exactly answering your question like it。

I showed earlier that。Let me go back to it that workload that that was very。

I don't even see it in my slide deck anyway so it really depends on like how much the workload is changing how much how much it's shifting and that really varies between our customers I you know unlike where I can kind of see the workload patterns and I and I can tell that like a majority of our customers have this as far as you know analyzing。

😊，Like。How know workload shifts and when they when they need to start tuning。

 we don't have any like any solid analysis on that at the moment。But I'll just chime in。

 just chime in and say that like。It's very rare that we come across databases that are static。

 meaning they are not adding new features， which schema changes， query changes。

 or the volume of the data increases， it's very rare that databases are at least the ones that come to us at Otune are static where you don't need constant configuration now。

You can get these noob tuning most of the benefit in the beginning because the default on Amazon is so terrible for both RDS and Aurora。

 but this is why we sort of expanded beyond no tuunning。

 looking at query tuning index tuning these identifying incorrect indexes because that handles all things handles all the use cases where are the applications evolving and then people want to know whether their databases sort of still following best practices。

This is the gravel cany Oh sorry。This is And's graphicit。

Sorwordt of covers it a little bit I mean it covers two different tuning so initially the customer you know applied applied configurations they went through a tuning session we improved their query latency by 88% and then they applied it you know what is it like a few months later and we further improved the target objective however in this case I could see you know you can make the argument like well the workload didn't really change they just didn't tune it long enough the first time so it kind of does。

But。 the customer workloads are pretty noisy are pretty dynamic and are frequently changing and we can see that in the queries that you know the slow queries that we collect to。

嗯。Okay。So I think okay so you know like it's part of trying to trying to demonstrate you know our value to customers we've also come up with a health score it encapsulates more than you know just the target objective that they're tuning in thenob configurations so this will incorporate like their health with respect to like how we're scoring them for indexes queries database resources so if they you know have super high memory usage or something you know look at docs and points so in this way like this is you know it's kind of like a credit score is just a little bit peace of mind I don't have the credit scores that much peace of mind but it kind of works in that same way。

All right， so with that。We shall conclude。😔，Oh， yes， so a few open problems。I。

I would love to see more sample efficient tuning techniques out there there's a tuning paper that was published back in 2022 calledLma Tu that I just love and it's you know pretty like what they their research and their techniques are pretty relevant to you know stuff that we could actually apply。

You know， to the Otter tune commercial version。Workload synthesis， you know。

 trying to figure out how like all of this kind of goes back to like generate you know dealing with training data。

 dealing with sample efficiency， so trying to come up with benchmarks or workloads synthesis that can you know simulate workloads that are much you know more realistic than what we're saying with TPCC TPCH etc。

And another really interesting one is kind of the starting stopping criteria。

 which is sort of related to the previous question about like when when do you like stop tuning and you know when has the workload changed enough to where to where you want to pick back up tuning because there could be a benefit from enabling it again。

 these are just a couple of questions。诶。Of the money so that brings us to the conclusion。

 you know auto tune。Oh and it looks oh interesting I don't know if it looks like you didn't quite finish the conclusion。

 but that's okay because it's the conclusion so in conclusion basically we you know audit Tu started out as a research project was it was a really fun research project to work on actually we came up with a bunch of interesting techniques but ourselves you know and some of the other research that we see's a lot of like the assumptions and sort of the goals like you know people I see a lot of tuning papers come out you know focusing on different algorithms。

Yeah， you know， like maybe not the most important thing you know。

 on the industry side to solve for us， but so it's you know。

 this talk has been kind of like some of the modifications that we've made and to make opportunity a commercial product。

And with that。Any questions？Awesome， I will applaud and have of。Everyone here。

 so we have a few minutes questions for Dana， so if you have any questions please please fire away。

Yeah， I've got a couple，'ll start with Ju Dana， you mentioned earlier in the talk that one of the crucial elements if I got that right was for you to be able to look at a workload。

And compare against a database of workloads and say which workload is similar to mine so that I can better understand。

 is that a good starting point for the parameters？just categorizing a workload is complicated and Andy explained you don't get the explain output so you're basically getting the queries and perhaps some stats from it。

Are there some things you could disclose openly about how you compare to workloads and compute similarity between them？

So I think I'm sorry for the confusion in advance， my little hat next to the Otterton did not work as well。

 that that algorithm is only being used in the research version of Otterton。

So in the research version of Ba2， we basically came up with， you know。

 whole our different workloads were just different variations of TPCC， YCSB。

 you know and a whole bunch of other benchmarks that werere in like a allTP bench so it。

IWe haven't applied that algorithm in you know to the commercial version of Autoudttert because know for the reasons you're mentioning。

 I think a lot more work is needed we need ultimately we just need more data and able to in order to be able to build any sort of generalizable model to be able to you know。

Find similar previous data。And if you guys ever get interested in that。

 anticroygnoosis is a ton of really interesting work on transfer learning。

 for instance optimal optimization that will take some of those workloadbes cast it into these gigantic vectors at times that get used to encode things like lost language models and they seem to work reasonably well at least in some cases。

 so I've got a bunch of questions but see if others want to go others they'll pop back。

Into the queue。Yeah think obviously also the reason also it's hard to because the hardware varies so much right there's different instances and then you have to deal with provision iOs and other curs you can add so it's part of the reason well be a bit。

Yeah， in datapargeence is the other thing that squeezes things up。All right， other questions？

I have a question about the kind of compute resources that you need to run Autouneune and in the field。

Okay， just like what's our compute， how much compute do we use？Yeah。Honestly。Nothing special。

 nothing special。We're're not the so okay。The algorithm can be computationally expensive if if you include a lot of samples。

 so if you have a lot of data points that kind of controls like the complexity of the algorithm and so we limit。

Oh， I forget the exact number， but we don't look any further back than like。Maybe a few months。

 we only use the data from like the previous few months versus you know the whole amount of data that we've collected。

 so that does help quite a bit。And then I had a follow up about as I guess database systems change and you get maybe more tuning parameterss。

 I'm assuming most tuning parameters probably change stay the same over the years。

 but as you do get new parameters， how do you like what kind of a delivery model do you have to deliver audit tune updates？

Well， I think like I kind of alluded to it， it's pretty manual， for example like。It was in like。

Am I thinking there was some parameter that。Maybe in one of the later releases of Aurora like if you know and this is a common problem it's like if parameter x is set to zero then parameter y has no impact and you know they were wondering like well why are you telling me to tune parameter y if like if this is the case that you know x has no impact and honestly like that' that's another open problem it's hard to try and keep up with like all of those dependencies。

Luckily， you know， my SQL hasn't been releasing you know too many knobs lately so they've been easier to keep up with Postgres does really release a lot of versions。

 but in general there have been a few cases， sorry it's ultimately just pretty manual at this point。

Yeah so I guess the team needs to constantly be aware of the updates and the development updates we expect each database that supported。

That's correct， yeah so luckily like。Whoever's working on it。

 this sort of exercise typically happens when you know postgse releases a new version because you know they release much more frequently than MySQL。

 so whenever we need to go in and start supporting a new version。

 that's when we kind of do that review of the Knobs。Thanks for answering my questions。

Thank you wait time for one more question Jness you want to go forward it Yeah I think it's two sides of the same coin do you have you thought of optimizing things other than the main database like a replica or even consider whether you could look at the workload and say you know what you're on Postgre you'd better be you are better off even in the same ecosystem of it is Aurora RDS to move to MySQL or vice versa so if you tried to apply it like outside that main box。

Of just optimizing the MaP database。So we yes and no I actually like i'll split this into two parts so as far as。

One of the latter thing you mentioned is where we really want to be。

 what we really want to be able to do is be able to make instance type recommendations and you can imagine that that would generalize too you know。

Potentially like choosing between like， oh， when is you know。

 Aurora better suited for your workload versus RS？I think that that was like kind of one of your questions we are looking into the very early stages of that right now with our data analyst but。

You know， it honestly like if you see that future come out for us。

 like it's great we'll get funding then like that that's such a hard problem。Um。

So I' love this all but on the other side I think you also mentioned like if we tried tuning replicas I didn't really go into Aurora support but's it's actually kind of interesting we could do a lot there and the reason we don't is honestly for business and pricing reasons it gets a little tricky。

😊，But we have like so AWS allows you to tune at the instance and at the cluster level， for example。

 so you can imagine like。Some some like formula of tuning there。

 but typically what we tell customers is well just tune your read replica and tune your write replica you know tune your rather read replicas because in order to be able to do more sophisticated things like that we need to be collecting metrics you know like the。

The database metric data and we're having a hard time getting that information for Aurora for all of the replicas to be able to do something interesting there so it just hasn't been prioritized I don't know if that made sense but yeah no that makes an excellent dancers and awesome talk thank you。



![](img/9e76872ae7b5d2a4a41c2bffa1656712_4.png)

![](img/9e76872ae7b5d2a4a41c2bffa1656712_5.png)