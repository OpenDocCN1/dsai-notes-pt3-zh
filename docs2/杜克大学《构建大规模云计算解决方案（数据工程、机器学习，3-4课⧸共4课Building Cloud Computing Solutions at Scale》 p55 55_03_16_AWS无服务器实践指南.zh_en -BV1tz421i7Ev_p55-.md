# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p55 55_03_16_AWS无服务器实践指南.zh_en -BV1tz421i7Ev_p55-

![](img/0eae15c402c45839b1040c363e408177_0.png)

To get started with serverless， which is a best practice， let's go through and document。

A little bit about。You know， serverless and microservices and what's the point and why is this even anything to do with Devops Well。

 to start with a serverless and microservices are DevOs best practices so Devops。

And microservice are closely related together。And part of the reason behind this。Is that。

In the old days， let's say from 1970。To even。I would say。Potentially，2000 and。5， something like this。

 this is we'll call this。Pre cloud era， right， and。In this era。

 we even people are still hyping these technologies。

 they're hyping these kind of like monolithic frameworks。

And so this is where you hear about web frameworks in particular and this is like this is I would call this like legacy thinking right this is a thinking that everything should be this giant monolithic。

 you know you'll see that everything has to be a relational database， you know RDB。

 you know plus almost as well a CGI web request model also templating you know in people are using like templates for the server itself is essentially translating。

Json data back and forth。 So this is all like a legacy way of thinking。

 and it's really expensive computationally。 So we know that。It's low efficiency。As well， and。

It also is difficult to debug， debugging is difficult。

And also has lots of security holes right so this is really， I think the old way that the new way。

 so we'll just say， you know the modern era， and I would say probably 2010 you know maybe even we say 2010 to potentially even let's just say let's just only cover the next 10 years so we'll say 2030 is this DevOs world and the DevOs world says look all that stuff。

 hey， it got us to where we're at now， but really there's some big problems and one of them is that a microservice is a lot easier to maintain in that it does a specialized task and that's really one of the reasons for a microservice also the complexity is low。

 so this is really a key component of this Also the other thing that's about a lot of these frameworks。

Is that it's almost like a cult where you're caught into this world where everyone has to talk the same language。

 but a microservice like flask， for example， really lets you get out of that cult and think for yourself where you can use this microservice and any environment you want。

 So flask， for example， fits really well with potentially any cloud。

 you can have the same flask gap and and it can be applied you know in a container or it can be applied as maybe a microservice or or whatever it is you're building。

 So I think this is also a big takeaway here is that you know less is more in the Devops world。

 And also that the runtime。Should be encapsulated with the microservice and then further。

Even flask in a way is a little bit legacy， although it's a microservice in that。

Is really not event driven。 And so that's something we'll talk about as well as that a lot of the Lambda services allow you to or Google Cloud allow you to respond to an event。

 which this world is only basically polebased where you're in a loop and you're just constantly just burning down trees in the forest somewhere to get your server to run。

 where this can just be waiting for you patiently and not doing things。 So this is another， I think。

 often not talked about problem with this legacy world of web frameworks that everybody's pushing still surprisingly。

 is that this is bad for the environment So if we took a look at the word green this is horrible we have really inefficient servers that we know that there's the sciences that climate change is real。

 It's not fake and we have these really expensive servers that are just running for no reason where if we built in。

based architecture， the events are a much more specialized way to run。

 so this's just another thing that's kind of a not necessarily talked about enough and even if you don't believe in climate change。

Still， why would you want to pay extra money when you could do an event based architecture so I think that's a key takeaway here so now that we know the the architecture of microservice is the DevOs and why the legacy world needs to be abandoned。

Let's dive into a repo here in this serverless cookbook。And in particular。

 this cookbook has a few different things that we can run。

 the first one would just be this Marco Polo AWS Lambda function。

And what I'm going to do here is also do a quick sketch。Of what the point is with with。

These serverless functions， so I talked about polline right？

And I think the best analogy that I will use that I typically talk about for what are we building is events。

 and again， this is directly in opposition from 1970 to 2005 where the legacy world of you know web frameworks。

 the new world is events and the way events work is that it's much like what would happen in your house。

In terms of your garage。 So we have a house here that's got some windows， and we have a。

Door here and then inside of this， we have a garage and inside the garage， there's let's say。

 a light bulb like this。Now think about all the different ways that a light bulb in your garage could be triggered well let's look at one so one is the door opens right so this open event could be we could subscribe essentially this light bulb to the open event and then all of a sudden the light bulb turns on right so that's that's one week we could handle this and just like the example of the really poor performing you know legacy architectures of web frameworks。

you don't want to just leave your light on in your garage 247 just to burn you know electricity why would you do that you're going to have a high electricity bill instead why don't you respond to an event which is the door opens and then the light bulb triggers and then the light bulb maybe stays on for like two minutes right that's a pretty elegant architecture。

But that's only one of the events that you can do。 The other thing you can do is you can say that you can manually turn it on like why not。

 why not also whenever you want to， you just click the light on。

 you have to do something in a garage and that you click off right So that's a second kind of event and there's even a third kind of an event that you could do which is a timer where and again this works this really is something that's very common in the cloud is you could say listen from midnight you know to one in the morning。

I want you to turn on。Just so that it's like a deterrent for burglars and I want this timer to turn on and then it'll turn off at 1 AM。

 So this is such a more powerful and more efficient approach。

 So serverless is basically let's look at all these benefits。 it's more powerful。

 So it's got more power。So we'll say power is greater， we also it's more efficient。As well。

 because you're only doing being charged for when you run it and also it has the ability to to be。

Solve more problems， right And so you know， it's part of a more complex potential solution that you can build。

 So there's many benefits to using serverless。 So let's let's now dive with that kind of background behind us。

 let's dive into building a function in Lambda。 So first I'm going to log into my account here。

And do。My off。Really quick。And。Here we go。 Let's go ahead and log， log in real quick。All right。

In AWS， if you want to run a Lambda function， what you can do is just go to Lambda。And in fact。

 now Lambda support containers， which is pretty awesome。So look， you can say look container image。

 right， which is totally awesome。We're going to do one from scratch here。

 and I'm going to call this Marco。嗯。Marco 2030 to represent the future of how we should be building services。

 I'm going to select Python 38。And then if I create a function here。

The way it works is that it'll give me a IDE that allows me to play around with。

This particular service， so let's go ahead and create this function。And it creates this version here。

 I'm going to click on it。And then I can go to the code section here。

And actually start writing out my function。 so it's it's kind of similar to like a visual studio code development environment。

 the key takeaway here though， is this event again。

 this is where everything happens magically and if I test it。

 it's just gonna to send adjacent payload into this event， but if I want to do a trigger。

 which if I go to。Configuration and I go to triggers。

 this is where you would set up again back to the light bulb analogy right if I want to set in these any of these three kinds of triggers。

 I was set in the trigger there so let's see how you do this you would go here and you could say I want to create a web service trigger or I want to have an IoT device trigger or I want to do voice recognition trigger or I want to do you know event bridge which is basically events I could do a trigger on that that would be a timer there's tons of different ways I could trigger。

 There's S3 is another one where where you could have a bucket。

You put an image into the bucket it triggers the some kind of event and then let's say you have Amazon recognition label the image or something like that there's lots of ways to trigger or SQS is another one where if you wanted to build a highper processing engine you could use SQS and you could just process you millions of requests if you needed to essentially SQS handles unlimited amount of traffic。

Now that we know that， what I'm going to do is go back to my serverless cookbook here。

And I'm going to go to this Marco Polo Lambda。And just kind of copy this out。

 so let's go ahead and put this first part in。And put it into the code。

And notice what I'm going to do here is I say。If the event has the word， if it has a name in it。

And it has Marco in it， return back polo， otherwise return back no。

I'm going to go ahead and deploy this。And then I'm going to click on test and and all you do to create a test is is put in adjacent payload here to test it out。

 So let's go ahead and do this and we'll say name。Is Marco。Here we go and we'll evoke it。And。

When we invoke this thing， you should see that the polo word appears back right so pretty pretty easy to test and now let's do a bad request so let's have one called Bob。

And then。Here。If we put Bob in， Bob should get a no。This thing says no， there we go， right？

Pretty easy to test a Marco Polo function and so I like to do the Marco Polo because it's just intuitive right is I have an event it has to match if the event matches I do one thing if I don't。

 I do another thing so。What's what's neat about this Lambda service is that we can。

 we can expand it and make it do even a little more magic by。😊，A couple different things。

 one we can invoke it via the command line， and so I'm going to create a second environment here。

Using cloud9， which is similar to GiHub code spaces。I have one。呃。

I could either set up a new one or have one already existing。

 I'm going to create a new one real quick to show how to do it and we'll just say Lambda。

Central or something right where I want to play around with my lambda functions。And by default。

 I believe we can just say everything here。Amazon Linux 2 we' use Amazon Linux 2。

 and then we'll say next， there we go。

![](img/0eae15c402c45839b1040c363e408177_2.png)

What's nice about these cloud environments and why I mostly do my code for a particular cloud environment in their cloud shell is that they already have the tools preinled。

 like I'm lazy， I don't want to do a bunch of work you know， again。

Like install the SDK and all the stuff like it's all ready for me and it has the right role based privileges to do these invocations。

And so in here， we'll just take a few seconds here。And。Let's let this scroll。



![](img/0eae15c402c45839b1040c363e408177_4.png)

What this will allow us to do is if I go， while this is spinning up。

 I'm going to go back to this command。Which is this lambda invoke。



![](img/0eae15c402c45839b1040c363e408177_6.png)

And I'll show you how cool this is。 So here we go。 This thing should be ready in a second。Okay。

 so this thing's woken up now。

![](img/0eae15c402c45839b1040c363e408177_8.png)

🤧嗯。So why it's awesome， There's a lot of reasons why it's awesome。

 But one of them is that you have the shell that's got AWS already installed right。

 So if I wanted to list my buckets and S3， there you go。 I can list my buckets In this case， though。

 I want to run this command。😊，Which is this， I want to invoke this lambda Now this。

 I actually want to invoke this one， which is called 2030， so let's go ahead and do this one。



![](img/0eae15c402c45839b1040c363e408177_10.png)

![](img/0eae15c402c45839b1040c363e408177_11.png)

Well let's just say 2030。And in particular here。Li's a look at the different things that I'm going to do。

 so I'm going to say payload。So I'm going to basically make a payload。

And I'm going to put in the word name Marco， and then I'm going to tell this command to take capture the output of。

What happens here and then just basically print it out。

Now I could just take this part out to be lazy initially。嗯。嗯。Pilload lambmbda invogue Marco Polo。

Function， not found Marco Polo。😔。

![](img/0eae15c402c45839b1040c363e408177_13.png)

h， that's weird， I'm not sure why it's not finding this function。呃。I certainly seem to。

Have maybe I'm misspelling it， let's try again。嗯。And， let's see。Did I spell it differently， maybe？

I have different caps or something。 Oh， Marco， that's why。 Okay。

 so let's let's go ahead and run this。 There we go。 So it ran it and look， it createates this output。

And notice that there there we go， polo， and if I want to say， you know。Bad out。

We can put in the wordB and we can actually also test this out。There we go， bad out。

 and then it has there we go， no， right。In my opinion。

 these lambdas are one of the coolest things you can possibly play around with because of。

How much awesome things you can do and this is again just an intentionally simple script。

 but imagine you have at your fingertipt， basically infinite concurrency because these lambda functions can run basically true parallelization where Python itself。

 the language has some real big critical flaws like you can't do true concurrency with threads。

 but if you use the cloud， the cloud itself can do true concurrency so you can invoke concurrency from a Camillan tool。

 for example。So this particular function here， one of the other things we can take a look at as well is if we go to monitor。

Now I can actually go to the logs。And I can look at these logs actually right here。

 which is pretty awesome， and I can see everything is happening。



![](img/0eae15c402c45839b1040c363e408177_15.png)

And if I go to the log stream it'll show me all the invocations and I can track down exactly everything that's happening。

 so here we go we've got the different statements， I believe that this is the one that I care about here Now notice that there's no log messages inside of here it just shows me the invocation so how would I change that a little bit。



![](img/0eae15c402c45839b1040c363e408177_17.png)

In Lambda， the way you would write logs is you just do a print statement and so what I can do here。

 this Marco 2030， let's actually tweak it and make it a little smarter。

And so I'll go here and I'll just put a print and say。You know。Prince。This was the， the raw vent。

Like that。 And then I can put in the name of the event。

 So this is why F strings that we we talked about are so powerful is that they allow you to quickly build like a log statement。

And then I could even put line by line some debugging， and I could say Prince。Here， and I could say。

诶。This。Events。Was。Marco。What just do。Like that。And then I could do another one below here， the said。

Prince。You know。This event。Was。Not。Marco like that。 So so basically it just shows shows me。

The execution path of what's what everything is doing， so we'll deploy this。

And if I go back to my environment here。I can execute it。And instead of seeing Bob。

 let's put in Sally。And there we go。 it'll overwrite this， and we can look at this。 We can see no。

And then if I go back to my CloudWtch logs here and we refresh。

 we should see additional messages here， it'll take a second for them to populate。But we should see。

 we should see basically new messages that have more。Output inside of them。 So this one， here we go。

 There we go。 the event was raw event was， this was Sally。 This event was not Marco。And。H。

We could go iterate from there and there and there。

So that's really it in a nutshell why it's so powerful now what else can we do that's cool？

Another thing we can do if we go back to our serverless repo is that there there is a。

Another thing that's pretty awesome。I guess maybe let's do this before I go away is let me grab this and I'll just put this as a file in there as as a template and I'll just say。

This is a logging version， so we'll just say create new file， AWS Lambda。嗯。Marco。Logs， there we go。

 just so there's another version of this。All right。Let's go to this one， though， the step function。

 so what a step function does。It allows you to chain multiple。

Lamb us together and capture the input of one and put the output into another。

 And so the how do you do this Well， the way you do this is you。

And I guess this link here is not working， but basically it's this is the way the code works is that step by step here。

 I can just say here we go， here's the first function。

 here's the second step function and I just put these in together so I'm actually going to build this from scratch。

 so I'm going to go and grab these together。I'm going to go to step functions here。

And let's go to step functions。And I'm going to say create state machine。

And I'm going to just do a regular step function here and notice that what I can do is just paste it in like this。

And notice that this word starts at Marco， this is Marco Polo， and I take one function here。

And then after I take the output， I go to the polo function。

And then I do a finish operation right so I'm able to chain together something pretty complex。

 so let's go ahead to next year。And we'll just call this a Marco polo。You know， step function。

Like this。And now for the role， because we're not calling any APIs。

We don't need to do anything tricky， I'm just going to say create new rule。And then。I'm going to。

Go ahead and create the state machine。Okay， perfect now that I've got this。

 how do I execute it what I can do is say start execution and similar in testing is I have to initially this initialize this thing somewhere and and where I'll initialize it is by first you know putting inside of here an initial payload so I'll want to do name here at first and we'll say name and inside of this will'll say。

You know， Bob again。Or in fact， actually， let's actually leave this by default。

And I'm going to start this execution and what's going to happen is that this will fail。llFirst。

 you can see that the input goes here， but it's going to fail because my function here isn't smart enough to handle that because if we go back to the lambda that is' calling。

Notice， let's look at the code for this lambda iss it does nothing， right， this lambda code just。

Excepts a payload like that。 And and if it doesn't match the word name， it just blows up。

 I don't handle that that problem， and it returns back a dictionary， which is name polo。

 So in this case， it can't work。 But what's cool about this is look。

 look how I can easily spot every single execution， what the state is。 So from a Devops perspective。

 the fact that I can。Look at my pipeline step by step and see exactly what's happening really is powerful。

 And again， this is so different than let's say a legacy web framework that doesn't have these tooling。

 This is really the modern way to develop applications so let's go ahead and fix this so let's go ahead and create a new execution and I'm going to put in the word name here。

And then I'm going to put in。Bob， so let's see what happens when we put Bob in。

 let's go ahead and start this execution and this should be a little bit different so it got。

To Marco， we see what the input is， it says name， so it was at least able to accept it。And then， oh。

 now it failed a little bit further。 So why did it fail， Well， let's look， if we scroll down here。

 we see that this lambda was successful， but then it entered。



![](img/0eae15c402c45839b1040c363e408177_19.png)

The Polo Lambda。

![](img/0eae15c402c45839b1040c363e408177_21.png)

And what is the portal lambda do？It's expecting。That this code will have the word polo in it if it doesn't。

嗯。Then it basically returns back a nun value， which we don't know how to handle。

 So we have another problem that we need to fix right so it's it's stuck here。

 So how do I fix this Well， let's let's go back to another execution and let's just fix this。

 Let's put in Marco。And what will happen is that it will be able to fully pass through all of these phases because step one is we put in the word Marco and what does it return back out it returns back polo。

This one's expecting that you put in the word polo。 and if you put in the word polo。

 it will then return back Marco， right So it just transpos what goes in one function。

 goes out the other， and then it runs a finished operation。 and we can see the finished。

If we go back here。Is if we edit our step function here。That's just that final step right。

 which is it returns back finished， you could put in anything you wanted to to do at the end。

 but this shows how。You could build some really cool tools with incredible debugging and logging by using AWS Lambda end or AWS ST function。

 and as I mentioned earlier， maybe as a wrap up here that，What's awesome about the new lambmbdas？

Is that you can you can you can build them now with Docker container。 So if we go to container image。

 for example， and I just type in you know。Python container。And I could say enter a image URL。

 what we could do is just browse a container and we can see here we go as a flask demo you know or whatever anything from my Amazon image repository or I also could check in my own container and override it and build things in here。

 So there's a lot of new things that are developing with the Lambda functions as well。

 the last thing I'll show you。With with this is that if you go to this tab here， AWS resources。

 one thing that you can do is you can actually import。A a function remotely。

 So if I go to AWS resources here， click on this and I go to Marco。Two， three，0， which is。Well。

 let's just grab one， let's just grab this one， I can actually say double click on it。



![](img/0eae15c402c45839b1040c363e408177_23.png)

![](img/0eae15c402c45839b1040c363e408177_24.png)

And what's nice about it is I can later if I want to。

Tweak this code and actually add more information to it right so that's the that's the other thing that's great about this environment is I can go through here and say this is an event。

 you know。Put put some other。You knowUpdates to it。You know， Prince。

And we'll just say have stringing this。Is not a match。Right， something like that。

 And then what I can do here is I can actually test， I can save this and actually test it out local。

 So test out my。Let's just refresh this here， test this out local， so if I right click。

 I can say run， run local， and I can do test this this whole workflow out to say you know， name。

And we'll just say Marco， what happens here？We're able to run it。

Sometimes you have to kind of wake it up， the debugging takes a second to kind of wake it up。

But there we go。Let's see。 I the first time。I do it。

 I've noticed sometimes you have to just do it a couple times then it wakes up。哼。Anyway。

 I'm not sure why this thing is not invoking。It could be because I used Python 38， maybe。But。

But in general， most of the time this works。 There we go。 So it was I must have been waking up。

 So there we go。 And then if I type in Bob here。Run this。

 we can see that this is the other patch pathway right， and then if I want to deploy this。

 I can go through here and right click and do a deploy。And what's awesome is that's pretty quick。

 and then I go back to my functions here。And here's Marco Polo 9，00， look。

 I just updated it four seconds ago。And then I can test it out， go to this。And。

And and test test the same piece of code if I wanted to or even look at the code and you'll see the codes exact I added that code there。

 so really powerful development environment。 So that's probably good as a stopping point for this section。



![](img/0eae15c402c45839b1040c363e408177_26.png)