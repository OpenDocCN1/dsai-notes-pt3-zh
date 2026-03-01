# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p54 54_03_15_构建无服务器数据流水线.zh_en -BV1tz421i7Ev_p54-

![](img/60dc29d205a50134c3427e3cf55d9444_0.png)

As well。So basically this particular project is an interesting project because let me just。

 well first of all， you could look at another video I did on this earlier。

 but we'll do it again is that this is a CloudWatch timer that will run at a periodic interval and then what'll happen is it'll read inside of the DynamoDB database。

 which is a key value database。And then this thing will then put messages into an SQS system。

 And SQS is a place where you can put messages。Where you can essentially never overwhelm it because it can it can take an infinite amount of messages basically。

 And then I have a lambda that's triggered so that there's a one to one where every single time。

I get a message in SQs It fires off a Lada。 So it basically executes my Python code。 You could， even。

 I think， tell it to get batch messages like 10 at a time。 But conceptually， it's one to one。

 And then from here， you can do anything you want。 You could do comprehend。

 You could do natural language processing yourself or whatever service you want to call。

 And then I put this into a bucket。 But this general architecture is is a really basic serverless architecture that that's fairly straightforward to set up。

 So what I'm going to do is I'm going to go through here and set this up。



![](img/60dc29d205a50134c3427e3cf55d9444_2.png)

So I'm going to go to。

![](img/60dc29d205a50134c3427e3cf55d9444_4.png)

Console here and just start spinning this thing up step by step。 So the first thing that I would do。

Is I would go to cloud 9。And kind of get this thing working。I think I I had set one up earlier。

 I'm just going to use this project because it it's probably already got my SSH keys。



![](img/60dc29d205a50134c3427e3cf55d9444_6.png)

Okay， so while that's spinning up。What， what I'm going to do here is look at this notebook。

 So that's the architecture。 But let me open up another。



![](img/60dc29d205a50134c3427e3cf55d9444_8.png)

And if we look at this notebook， the main thing that I'm going to do is I'm going to create a Lada function Well in in the console。

 So I'll go back to the console。And go through。And pretty。Create a new lambda function。

And we'll just， we'll call this one。Prodducer。9，19 or something like that。

And then I'll change the runtime to Python， although I think in this case。

 I want to do Python 36 because that's what Lambda supports。And then this is the part that's tricky。

Is dead。The Lambda itself， if it needs to do anything like talk to another service。

 it has to have also a role， just like elastic Beanstock or E C2 or code build。

And so I've already had one earlier， so I'm going to use an existing role。

I'm going to select this one right here， I have an admin role that I use for prototyping。

If you want it to be very secure， you would only give it the permissions that it needs to execute what it is you're building。

 but for prototyping I like to give it an admin role。Okay， so I've got this sample project here。

What I'm going to do is I'm going to go to this code here。

 which I think I have some producer code here。And I'm basically going to need to populate SQS。

 And so I'll just copy this in。And throw this， throw this inside so we can take a look at it。

 So copy this。And then put this inside。 And let's just walk through。

What it is that this actually does。I am Port Bodo 3。

I use Jason just to do Jason stuff and then this Dynamo Db library。

Allows me to talk to a key value database， which I'm going to create in a second。

 and it's going to talk to a table called Fang for Facebook， Amazon， Netflix， Google。

And then I'm going to have a queue called a producer， and I'm also going to make an instance。

 So because。Bdo 3 is an easy way to talk to AWS， I can just in line of code。

 make an instance of either one。And then I set up some logging。

 and this is always a good idea for serverless is to create some logging so that you know what's going on。

 And then from here we will scan a table and all this does is it goes back to this dynamo table right here。

And we will grab the information inside of it and get everything out of it。

 So this is like a lazy way to retrieve the data， which is like just give me everything that's in this table。

And then once I've got that， the other thing I'm going need to do is I'm going to need to send messages to a queue。

That will hold all of the things I find out of the database。And that's what this La code does。

 is just sends it to a queue。And then the next thing I'll do。

Is I will say for everything that's in the dynamo Db table， put it into one by one into the queue。

 Now， I could have done additional things， right so because I'm pulling it from Dynamo。

 I could add additional information or delete certain things。 I mean， I can do anything I want。

 But for ease of use in explaining this。 I'm just going to take something from the table。

 put into the queue And then the thing that does all the work is this is that this is the entry point where it doesn't actually accept at an event that it does nothing。

 all it does is it。Pulls data from the table and puts it into the queue。 That's it。

 So that's really all I need。 The only thing though I'm going to need to verify is do I have a table in dynamo Db。

 And do I have a Q in S Q S。 So let's go check that out。

Let's go to first to Dynamo Db and take a look at this。And from here。

We can look at the tables that exist。 and there is actually a table called Fang already。

 but let me just show you how to create a table to it's really， it's almost like a Google sheet。

 there's not a lot to it。 You don't need to be overwhelmed by it。

 you can just say like demo right And then for here this just has to be a globally unique I so that you it's like a Python dictionary so I could just say GUI globally unique I and then say create。

So again， it's almost as simple as creating a spreadsheet。 Once you do that。

 you can add things by hand。 It takes， let's say 20 seconds to create it， but oh。

 actually it's already done so now I can go through here。

And I can say create item and I can just say， for example。Apple。Append。I could say， you know， banana。

And I could say， like。More。I can put whatever I can put whatever I want， you know。

 inside of this thing， I can have nested ones or I could say， you know。

It's literally just a dictionary， basically， it's the dictionary data structure。And I also can。

Delete it easily as well by just going to demo and saying deletete table。



![](img/60dc29d205a50134c3427e3cf55d9444_10.png)

And so I'll just type the word delete。I'll be lazy and not type it。 I'll just paste it。



![](img/60dc29d205a50134c3427e3cf55d9444_12.png)

Enter the word delete。 Okay， I have to enter it。 Okay， so now this fang table。

Because it's got just a name inside of here， these are just names of companies， Amazon， Google。

 Microsoft， Netflix， I could put whatever I want， I could put Oracle or whatever company I want to put inside of here。

And that's it。 so Ive got I've got Dynamo Db table set up and it's very easy in Bodo to read and write to dynamo DB again。

 think of it like a spreadsheet。Now， I'm gonna go to S Q S。And S Q S。

 I need to have a queue called up called producer， which。I don't have one set up。

But let's just first show you how to cr a queue， it's pretty easy。Is there's two kinds。

 there's PIFO and standard。This is probably not what you want when you're using a queue because it's a first in first out。

 and it's really like a specialized。Qe process， more likely what you want is something where you can just throw a fire hose of stuff about it。

 And this is more sloppy， I guess， and and this is more precise where if you really needed to have first in first out delivery like you're doing payroll transactions or credit card transactions or something。

 okay， maybe you would use this。 But what's great about this is you literally can't blow up a queue。

 there's no way you can send more information than it can accept like it's not possible。

 it takes just a tremendous like hundreds of thousands or millions per second or something just absolutely ridiculous that you'll more than likely never run into。

And so inside of here， I would just say producer。Like this。

As the Q and then you could just leave all this stuff default。And say， great， and that's it。

And once you have the queue created to use it， you just say send and receive messages and you can just say like hello and just send a message and then it's pretty straightforward is that in this queue here if I want to look inside。

 I can say pull for messages and look you can see there's a message and what is in the message body hello so it's a fairly straightforward process that but the main idea is that' it's almost like an email inbox like you're just collecting a bunch of information so I'm going to delete this here。

And。We can say stop polling because there's nothing inside the queue right you even can purge the queue as well。

 So if you wanted to purge all that means is that just if there was something inside the queue like you had 1000 messages。

 you can also just delete it which is really only used for development right Okay。

 so we got a queue setup， We have dynamo Db set up。

 So pretty much we can get this Lambda cooking here right because we know that the lambda。

 this is all of the work right， it's very straightforward to pull all the data from dynamo Db。

 it's just producer table scan。 That's it。So I'm going to go ahead and save this。And then to run it。

 I just need to add a trigger so I can either。I can either run it myself。Or I can。

I can run it manually instead of here。Testing it。 So let's go ahead and run it this way first。

 So I'm going to go through here and just say。You know， fire。And then all this will just be empty。

Will you say a fire queue。And this will just send an empty payload because it doesn't accept anything。

We'll format this。And， and then this will actually run， it'll scan that table， or it should。Oh。

 no module named Python Jason logger。 So we did run into one problem， which is irritating。

Is that I do use a third party library。That it needs that。 I didn't install。And so。嗯。We can fix that。

 though， by importing this into the cloud9 environment and fixing it。

 And I'll show you how I typically do that。 And this is a little bit clumsy。

 and it's irritating that they do this。 that there may be a newer way that they do this。

 but this is the way that I that I install packages is if we go back to here。

What I can do is just close all this other stuff。 I don't need any of this anymore。

 this is some other project I was working on。But。I can go to this AWS's resource tab here。

And I can go to whatever we called this thing， which was。Producer。9，1，9。 and I just refresh。

And it should populate over here in the peas。Where's this thing。Refresh this。More。There we go。

 So this one。 And if I right click on it， I can say import。

 and I can literally import it into my project， which is， which is pretty nice， actually。

And so once I've imported it， notice that this is the problem is this library。 So how do we fix this。

 Well， the way I do this is I will install the package in a certain way so that it's bundled inside。

 which is again， I hope they fix this that there's an easier way to do it。

 But this is the way I do it。 So I would CDd into multicloud。No， not that。 I was Cd into producer。

And then。一。Inside of here， we would。Look at this template。There's a couple ways we can solve this。

 let's see。So， this is the template。I guess they changed this a little bit， because。

It's going to require。AAnother package that's one level above its。So。Let's see if this works。

So this doesn't have a virtual environment as well， which is kind of irritating。

 let's see if this works。 So So this is one way that it might work is that you say requirements T X T。

And then inside of requirements。You say Python， you put in the package that it needs Python， Jason。

Loger。Which I think that's the name of it。Let's double check。Yeah， I think this is the name。Yeah。

 Python Jason logger， okay， so that's the library。And let's see if this works， if I do。嗯。

If I create a virtual environment， so I'll say Python 3。

Dash in virtual environment and I'll make it above because I don't want to check this virtual environment inside of there。

 I'll say tilda slash dot。Producer，91，9。I will source this。

So I'll say I'll source this environment and this is the tricky part that that's kind of weird and I'll show you what what I do is that。

And again， there may be a easier way to do this is I don't actually install it into the virtual environment。

 I just use the Python packaging tool from the from the virtual environment。

 I install it one directory above， which should be something it can pick up。

 So let me see if this works。 So I do PIip install。Dash R requirements。 And I say dash dash target。

Let's just double check I have this command right。Yeah， target。I do this。 I do target above。

And does this work？So the reason why is that it needs to look a directory above this to find its library。

And so I think it will grabl this inside of here。Which is， which， again。

 is a little bit weird that it would grab all that。In the directory above here。But， okay， and。

Now if I go here again。I can actually deploy it and it should grab that directory above。

Say deploy ploy。That was easy。And let's see if that works。 So if I refresh。This， oh。Yeah， well。

 that was old。Let's see if this works here。So it did， it did give it the new file。

And let's see what that does， did that work？Is still having a problem。Yeah。

 usually that works if it's in a subpack。And this is the thing that's irritating about the Lambda environment。

 so what I'm going to do to fix this is I'm going to do it a different way。

 I'm going to copy this code that I have in here。And I'm going to just recreate it from cloud 9。

 which is a little bit easier。 So instead of this。I'm going to。Deactivate this environment。

And I'm going to just make one from this wizard。 So this wizard here。



![](img/60dc29d205a50134c3427e3cf55d9444_14.png)

I can click this button。And what it does is， is it creates the package structure that makes it easier to package the dependencies with it。

 And again， this is a little bit clumsium， but weird。 So let's just call this producer。And I'll say。

Cud 9。Cloud9， producer Cloudine， there we go。And if I go through here， I can say Python 36。



![](img/60dc29d205a50134c3427e3cf55d9444_16.png)

And for trigger for now， I'll just say none。The rule， I will want to use the in admin rule。

 and I'll finish it。So this is a little bit trickier initially than I expected it to be。

But we can easily fix this。 So this is given us an empty function。

 I'm going to put that same source code in there。And the only thing I'm going to need to do is do the same thing that I did before。

 But Im， I'm I'm going to C D up here。 I'm going to C D into this。Producer Cloud 9。

And notice that the directory structure is a little different because this is where the Lambda lives。

 and so what I'm going to do is I'm going to source this structure they set up for me here。

And then I'm going to do the same thing I just did。 So。

 so I think the problem was there wasn't the upper level directory。 And that was what the issue was。

 So I'm going to say source V E And V。Be an activate。And then I'm going to see the into this。

And then I'm going to do that that fancy。Thing that I did before。 So go。Prodcer cloud 9。

Requirements will put in here。😔，Python， Jason logger。Okay。So I got that working。

And then I'll do that same command。 So I'll just say。Pippenaw requirements。I'll do that command。

But let me just double check where I'm at。 Okay， yeah， so I want to do it。

 but I want to do it one level up。Because the requirements file is up in the next level up as well。

 So I'm going to say install the requirements from the directory above me。

And then also put the packages in the directory above me。Okay。

 so so if we look in here it put all that stuff inside of this， this directory。

 So we have an outer folder that holds all the packages and then inside we've got our lambda。

Now I should be able to deploy it， so a little bit confusing。

 but we found a fix I right click and I do deploy and it should take a little bit longer because it's copying a bunch of files there。

Now， one thing we can do whilst deploying。Is that you can actually test this locally。

Because if I go here and I say run。Run local。Note remember， it doesn't take a payload。

 It's just an empty payload， but it will call out to the cloud 9 instance， a call to Dim Mo Db。

 pull this stuff from table and put it into the SQS。 This will run this。

 so let's just go ahead and run it。Here。😔，There we go。 Look， so it did all that。

 It went over there and how do we know， let's go back to SQS and S QS。We should see if I pull it。

If I say sendend receive messages and I say pull， there should be like five or ten0 messages in here。

So there we go。 There's a bunch of messages and look and what are the messages。

 they're the names of these companies， right so so I can even test this locally just from in this environment。

 So so we got the first part set up and we figured out why you need this certain directory structure。

 which is pretty irritating。 But for now， that's how they want you to do it unless they've fixed it。

So the only other thing I'm going to need if I go back to this GitHub project again。

Is we we've set up this part of it， which is。We set up this and we set up this and we set up this。

 so we set these three pieces up。But what we haven't set up is tell it to run。

 you know at some interval， probably one minute in a real company is too much， but for demoing。

 it's good because it'll just keep cranking things so I can see it in action。

 so I'm going to go back here。And I'm going to go to this function here。

 and I'm going to add a trigger。 and the trigger is pretty easy。 I just go to Cloudwach。

And I tell it to。I think it's called events。🤢，It's called。See。😔，Event bridge， Cloud watchch events。

 And you can just set a rule。 I already got， I already have one set up on one minute timer。

 but you can see it's just this。 It would be rate one minute。

 But I would probably say once a day for something like this is better。

 But just so we can see it working， I'm going to say add。

 and it's going now pump the queue full of messages over and over and over again。 Okay。

 so while that's working， we need to build the second piece now。 So we got this， this， this and this。

 we got four of them run。 now I need to consume the messages inside of this queue。

And then do some kind of natural language processing API and then put the results into S3 buckets。

 So I need to do step 2。And then for step 2 is pretty easy。 Actually。

 I would just go to the example source and find。I think it is going to be this one， maybe。

Let's look at this。Yeah， this looks like the code and I'll explain it in a second。

 so I'm going to just grab this。And copy it。And then I'll do one more。

 I'll create one more inside of。This， this area here。 So again， I just go to this plus icon。

 I can close all these other ones I don't need them anymore。And then I can say， okay。

 make another lambda and we'll call this one consumer。



![](img/60dc29d205a50134c3427e3cf55d9444_18.png)

Cloud 9。Next runtime will be Python 36。Go through no trigger。We use a role， the existing admin role。



![](img/60dc29d205a50134c3427e3cf55d9444_20.png)

And say finish。 Okay， now that this is。Running here。I'm going to just paste it in。

And the only thing that we really need to do。First， let me just explain what the code does。

 so the code， we're going to need to install Bodo。3， Wikipedia， pandas。

 and then that Python J logger， right， Those are the the pieces of code that we'll need to install。

And then this is just utility functions that。I'm going to use to talk to the queue and so what we do is we make a connection to SqSQ。

 In fact， I think I can even get rid of this。 I don't think I use this。

 which is a bad software engineering practice， I don't know why I left it in there but this I do need which is a delete queue message after you're done grabbing the message from the queue you should delete it so you don't rerun the job again。

And then what this code does。Is it grabs the names from。The Wikipedia URL。

 and then it puts it into a data frame。And then what we do is we call out to AWs comprehend service。

 do natural language processing and then apply that to a data frame。

 and then I write that information to S3 bucket and then here's an example of a Lada handler just like this and says make panda's data frame with Wikipedia snippets。

 perform sentiment analysis and then write it so basically it's going to。

Call Wikipedia based on the name of the company that appeared in the SQS database。

 grabbed the page information。Put that into a data frame， perform the sentiment analysis。

 and then write that out to an S3 bucket called Fang sentiment。So that looks pretty good。

 but the biggest question mark is I'm going to need to do the same thing I did before。

 which is get those packages installed， which again is a little bit irritating。

 This is the most irritating part of all this。 So I'm going to go back here。

And I'm going to go into consumer cloud 9。And again， we see it gives us a virtual environment。

 which at least they do that。 so I can say source V E and V。Been activated。

And then I will see the into consumer cloud。 Or actually， first。

 let me put the right requirements in here。 So we know that it's going to need。嗯。Python Jason logger。

It's also going to need pandas。 It's going to need Bo a 3， which I think we already have installed。

 And then it's also going to need。Wikipedia。So it looks like those are the main libraries。

 so four libraries， okay？And then I can do the same thing。 I can just run history， and I can be lazy。

And just copy this， right， so I can， I can now Cd into this。Run this command， Pip install stall。

 The requirements fall above me and then put the packages above me as well。Okay。Now。

 this one I can't test locally because it only gets triggered based on messages that appear in SQS。

So what I will do。Is I will。嗯。Just deploy， assuming that this works。

 and I will go to consumer right click on it and then say deploy。And this should take a second。 Now。

 how， how then do I get this thing to trigger on that cu， and by the way， before we do that。

 let me go back to the queue。 And there should be a lot of messages into this cu now， because。嗯。

It's been running for a while， and so there is， there's a bunch of messages in this queue。

And message is available 30， right， So we we see that theres there's a bunch of of messages that that are appearing inside of here。

Because it's constantly pumping these messages into the queue。

What I'm going to need to do is go to this function here。And。Not the producer， but the。

I'm going to need to go to the other function， which is the consumer。

And I need to add a trigger that tells it that every time。There's a message in the queue to。

Which will be the producer cu to grab。A message at a time。 In this case。

 you'll see the maximum number of messages。 We'll just do one at a time。

 grab it and then put it through all the stuff that we have。

 So we'll go ahead and say add and it should be instantaneous。

 It should instantaneously just start draining the queue and it should， in fact。

 be so quick that there should be nothing left here very， very quickly， and let's see here， though。

 if we say pull for messages and there's a problem messages available。

 It should really quickly just drain everything in the queue。 let's double check。

Although it does take a second for this to get set up。Create so yes， still creating。 That's why。

 But as soon it is done creating。Then。It should， it should process all of the messages in the queue。

There we go。 So it's done。 So if I go back here。There should be theory。Let's see what's available。

 Poll for messages。I don't see anything。 So it looks like it already got rid of all of them。

Which is what I would expect。 Yeah， so they're gone。 They just。

 it process everything in the queue and and then what we would do next。Is we could look at the logs。

 so this consumer here。We can go to monitoring。Which is always very。

 very important to know about monitoring。 we can look at the logs in CloudWch and we can see exactly what this did。

And we notice。That's。It is actually processing divnce。 There we go。 That looks good。

 So it's able to do all this stuff。That looks good。 They was able to process this。

Writing messages to the bucket。 So now we can just check S3。 That would be the next thing to check。

 So I'm going to go to Amazon S 3 here。And。Let's look in that bucket called things sentiment。

 There we go。And we can see that we can even sort by last modified。There we go。 Google sentiment。

 and and we can actually see that it's putting stuff in there。 So what we could do。

To make things a little bit trickier is I could go back to my cloud9 environment because I'm lazy。

And I could just pull this in in into here。 so I could just kind of get rid of all this stuff。

 which is irritating。And， and just do like， literally。AWS S3。Cp dash R。This would it be F sentiment？

Things， sentiments。Would it be S3。😔，Does that work， let's see。Actually， before I do that， let me see。

 I want to be into the environment directory， which which is like we'll show all this stuff and let's see。

If that will work。Is this the command？Oh， unknown option。So did it do anything？

Let let's look up the documentation， So AWS S3， C， Dsh help。What is it？Okay， let's see example。😔。

Would be C。 That looks good。So。Okay， they're giving me all。 Oh， here we go。 Estri sink。

They will be local to remotes。I think， I。S 3 C， O dashsh recursive。

I think that's all I need to do is add a dash recursive， okay， so let's try this。

Let's see if we can get all those files here。In this， a dashcious recursive。Will that work？😔，Okay。

 there we go。 So we're able to copy those files locally。

 and then I can even just look at them inside of here so we can see。

 I don't know when these were from， but。If we go back here， we can look at the latest。Timetamps。And。

Last modified， Google was new。So we can go back here。And we can look at Google。

 we can just even look at it inside of here， and we can see that it has a CSV format。

And then it has the snippet of code， which is what it got from Wikipedia。

And it also has the sentiment associated with it。 So we have a。A full end to end data pipeline。

 and we can communicate back and forth with the data in S3。So what did we build， we built this。

 we built a timer that is constantly going through and triggering this producer Lambda。This producer。

 Lambda。Reads the data， which is the company names from Dynamo Db。When it grabs it。

 it puts it into SQS， and then this is an event based workflow where every time a message appears。

 it immediately calls automatically the consumer Lambda。

 which goes through and grabs the message from SQS， so parss the message。

Does whatever we told it to do in this case， do。Comprehend analysis。

It then extracts that and puts it as a file name into S3。

So this could be all these things could be swapped off for different pieces。

 This obviously is probably too much， you know， one， probably once a day is fine。

 And then additionally。This doesn't have to be compred。

 it could be your own natural language processing system or whatever。

 it could be video or it can be anything you want。 And so what I'm going to do now to clean this up and this is very important to do is I'm going to go back to everything and just delete it all so。

Otherwise I'll get charged for these services， so I need to go to Lambda。And I need to。

Find the producer。 That's probably。Well， first of all。

 delete the old producer that we didn't get working， we'll delete that。Then I'll delete the producer。

That has the trigger every minute。 So first， I'll go here and disable that trigger so we can just delete it。

And then I'll also just delete this whole function。 just to go here。This actually。

 I think I can just delete the whole application， just say。Consumer。And delete it。

So we could either delete the whole stack here， that's one way to do it。

And then I could also go here to the producer and delete their stack as well because it has。

Infrastructure is code automation associated with it as well。And then once I've got that working。

 I also should go back to S QS。Is well and delete that queue。And just kind of clean， clean that up。

 delete it。 We'll just say delete。And delete the producer queue as well， just to be safe。Delete that。

 And it just it's always a best practice once you've。



![](img/60dc29d205a50134c3427e3cf55d9444_22.png)

Gone through and created a bunch of stuff to clean everything up。And。That's it。 That's。

 that's the the final project。

![](img/60dc29d205a50134c3427e3cf55d9444_24.png)