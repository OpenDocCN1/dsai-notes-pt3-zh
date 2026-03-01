# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p69 69_04_06_ETL实际场景问题.zh_en -BV1tz421i7Ev_p69-

![](img/42aa85af24984633cc992e56cf69bd13_0.png)

But let's look at a real world problem。That I had to build before when I was building a social network several years ago from scratch。

 so one of the things that happens with a social network is how do you actually get a user to join your social network and one way to do that is that we now know it's called something it didn't used to be called something it's called influencer marketing。



![](img/42aa85af24984633cc992e56cf69bd13_2.png)

And you partner with people who are already on some existing social network。

 and you get that person with a large amount of followers to post to your platform， right？

And so one of the ways that you would need to first figure out who to partner with is to learn about who are the kind of people that if you partnered with these people。

 they would build out。effectivelyffectively the right signal to your platform。

 So this was something I built from scratch where I would go to a third party system。

And get a list of all of the people in sports in the United States and actually around the world as well。

 including European soccer players like Ronnaldo or。嗯。You other famous soccer players。

 So in this example， this is Joe Montana。And I have the information that he played for the 49ers and I put this into a database。

And then I have a nightly job that runs that goes into this jobs framework that I build and this job framework would have some。

 you know， something that can go through and run something periodically and most。

A machine learning or data engineering jobs frameworks， you tell it to run at a certain interval。

 and then you also tell it the data sources and then the data output。

 And so what I would do was I created a mechanical Turk job and this is a way of cleaning up the data I would ask people around the world effectively to find the social media handles and then I would take 10 of the results。

 and then I would figure out if most of the1 a quorum of them agreed on who Joe Montana's social media handle was。

 then I would create the full record and so here would be example of Lebron James it says Lebron James Twitter handle at King James Wikipedia handle King James。

And then it would go through and it put it into this database and then again I would go back and go to this nightly job and now I could do more interesting information so first there's a cycle here where I would have to get a rough record that isn't fully complete and I would need to augment it with a way to clean up the data and that was what the first aspect of the data engineering pipeline did。

Next， what I would do once I knew what the real social media handles were is that I could create a second。

Social media metadata handle， and this would go through and query Twitter。Facebook， Instagram。

 and it would find out metadata about， you know， that particular user。

 So one of the things that I would look for would be how many followers that they would have。

What would be their engagement ratio？And then what I would do is take that information and use it to build out a machine learning model and how would I do this。

 well I would look at the platform that I built and I would look at how much traffic was actually being generated so I would then look at the signals on that pattern on that platform the third-party platform and use it to predict how many page views would occur based on the users on my platform and so what we saw here is that we were able to have a machine learning model where it would predict the page views per post and one of the things that happened was that we were able to actually identify the right people to predict with and so here's a good example what happen was that using those same signals we were able to partner with。

NFL quarterback here's the logo of our company at the time。

 and he created some posts around the NFL draft and completely saturated our system because it was so popular。

And a good example of this what would be this overview is from a high level is you have the Amazon Meical Turk。

 it goes through and it finds the social media handles from these different platforms and then you can see this is a diagram of that we were able to predict which are the most successful users and the actuals where that we were able to get an exponential growth of traffic on our platform and this would just be a good example of the iterative process it takes to actually build a real- worldord data engineering pipeline but it really starts with this it starts with that you have to architect out。



![](img/42aa85af24984633cc992e56cf69bd13_4.png)

From a high level what your system does and often there'll be multiple loops。

 so there'll be the start which will give you the raw data and then you'll continually have to run multiple other jobs to complete the data and this could take maybe。

A year， I think this took almost a year to get the data pipeline completely right just because of how difficult it is to get fully complete data and I think that's one of the big takeaways with building。

This kind of a pipeline from scratch is the difficulty in doing ETL。

And identifying it and so what I can draw on next here is some of the things that were edge cases that I noticed in building a machine learning pipeline。

And doing this kind of work from scratch was， what are the edge cases to building these data engineering pipelines？

So one of the edge cases that comes up a lot is that it's easy to forget that the data input is the most challenging part of the problem when you're building machine learning systems。

And what this means is that in the first part of building a data pipeline。

If you don't have the data write， it could， on the back end， really cause a lot of。Extra work。

 and so when we were first inputting the data we used interns in our company to collect the data and they really didn't do that good of a job because it's a hard it's a really hard job and as a result。

 we would have， let's say， 50% of the records were bad records and a good example of this would be that。

Let's say there was a sports player and I'll pick one that's a really good example。 in the NFL。

 there was a player Anthony Davis。And this player。In the NFL didn't have a hugely popular career。

 but there's also a player in the NBA called Anthony Davis。

 and we know just a few days ago that Anthony Davis won a championship along with Lebron James。

 So these are very different people and they have very different social media handles。

 So this Anthony Davis had， I don't know， 10，000 followers。And the Anthony Davis and the NBA。

 even back then in 2014 or something like that or 15， he he had。

I think millions of followers at the time。So the signals would be very different， right。

 So if I captured his data。Here， and I put this into the machine learning system。

 This would give me accurate predictions about about later if we wanted to partner with him。

 but if I put if I mistakenly put，This NFL player in with only 10，000 followers。

 this now causes a huge problem downstream in that now my prediction accuracy is very poor so in this case I guess we would say this would be the mistake where it looks like the data is correctly input but it will cause poor accuracy in the model downstream。

This is really， it's a subtle problem that。The only way to really solve it was the humans had to go away。

 right， is that when you have humans involved in building things that it really can cause big issues because it's the work is so boring and if you're talking about。

They needed to create a repository of， let's say， 100。

000 users here that the work is so intense that they're going to be constant series of mistakes and then the results are if what we're trying to build as a machine learning prediction model that it really is going to have some significant problems。

So what is the solution？To make sure that you you don't introduce these kinds of errors where you con fuse the records or you switch things really the solution here is actually automation。

 So now I'll explain the solution here so what we're able to do was use that mechanical turk system and the way mechanical Turk works。

 And this is really now a bigger trend and in terms of getting the right data but it's basically a mixture of of humans plus technology。

 So here's the humans and then we also have some kind of。Data augmentation， AI。

We'll see this augmentation。And the case of mechanical Turk。It will say this is。T。

 what it does is you could ask， it really then becomes more of to fix it。

 this would be we'll just call this automation。And。And what we had to do was create a record here。Of。

The people， so we would say， look， I want you to we would have to tell a very specific story to the people that were were asking these questions around the world。

 we would say， you know， effectively go to Google，And search for this person's name。You know。

 search for x。And then， and then find。These three things find A， the Instagram handle， B。

 the Facebook handle， Facebook， Instagram。And then see。

 find Twitter and then use this information and it put it into the spreadsheet。

 So then we would ask 10 people， we would ask 10 people， and these would be random people。

To grab that data。And then if we had eight out of the 10 people would agree。

On the correct social media handles， then we would accept that record。

 and so we knew that the error rate was effectively zero。

If if we were able to get8 out of 10 people to agree。

 so I guess the fix here is that you really can't rely on just a human by themselves in putting data for a machine learning pipeline。

 you have to have more sophisticated tools and that's what one of the things that people are really starting to lean on is this mixture of the humans inputting the data in a larger system with some kind of data augmentation where you have a mechanicalrk system that can really hold it all and pull it into an API that's available for you。



![](img/42aa85af24984633cc992e56cf69bd13_6.png)