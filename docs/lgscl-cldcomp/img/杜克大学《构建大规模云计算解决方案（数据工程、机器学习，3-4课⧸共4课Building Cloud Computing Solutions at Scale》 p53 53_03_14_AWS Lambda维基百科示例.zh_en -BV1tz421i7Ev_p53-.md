# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p53 53_03_14_AWS Lambda维基百科示例.zh_en -BV1tz421i7Ev_p53-

![](img/5d6854656cbe7063a44fd6054ad616cb_0.png)

Let's go ahead and build a slightly more complex AWS Lambda function here that accepts a Wikipedia entry。

 let's say Google or Facebook or Amazon or Netflix。

 some company and summarizes the content of the text。 So the way this works is import Jason here。

 import Wikipedia。And this particular Lambda function does all the work。

 And you can see here that I use this library Wikipedia summary after I grab the name of the company that will be summarized and I say I want to look at one sentence from Wikipedia and then I return back the response。

 So pretty straightforward function here。 So what I'm going to do。

I I'm going to build a new one inside of this directory so I'm going to type in Sam and knit to get started this will go through and ask me you know what source would I like to use I'm going to go through and say one quickstar template。

 I'll go through and say I want to create an image artifact and then for my base installation here。

 I'm going to choose Amazon Python 38 base so number four。And then for the project name here。

 I'm going to call this Wikipedia 2021， there we go。All right。

 so it's clo the template well what do we want to build here do I want to build Hello world P towards psychic Learn Tensorflow XG boost let's go ahead and use the Hello world Lambda image In start here and then looks like I'm ready to go if I go into this directory so I'm going to go into this directory here that was created you can see here it's called Wikipedia 2021 and in the beginning here。

You'll see that it created this hellello world directory and all I need to do is double click this file and I need to just swap this out with my existing code sample that I have here。

 which is in this AWS Lambda directory so I'll go ahead and copy this and swap this out into this location there we go looks like we're ready to go here and what's great about this process here is it's really straightforward to test things out and how do we know how I can test things out well the first thing that I'm going to do is I'm going to look at this requirements file here。

If you notice here， there's a Docker file， there's requirements file。

 I'm going to go ahead and put the Wikipedia Library。And then in order to test it。

I'm going to create a virtual environment， so I'm going to type in。

 I'm going to first change into this directory。 so let's go ahead and get in there first and go into the Hello world directory and notice this is where that requirements file is。

 So I'm going to say first Python 3。And we'll say dash M V E and V so I'm going to create a virtual environment。

 I like to put them inside my home directory in a dot directory so that they're hidden and they're far away and they're not going actuallyly get checked into a project and I call it something similar to what I'm creating so we'll just call this wki。

There we go I'll go ahead and source this so I'll go source tildalash wki bin activateate and then once I've got this set up I can do Pip installst so I can type in Pip install R requirements and this will go through and look at these two requirements files and kind of get this thing cranking now if I look at the read me notice that it gives me the instructions about really how to get started here and so the first thing that I'm going to do is'm I'm gonna say Sam build so if I go into this directory here I can type in Sam build and this will show me that oh I need to be up one level above not in the actual Lada directory I need to be in the template directory so we'll go and run Sam build again I'll see the up1 and now from here I'm in the right directory is going to build out this containerized version of my application and then what I can do is actually test this out so I can actually。

through here and say Sam local invoke and this will allow me to invoke this function and notice that it says。

 oh， you know you didn't give me the correct payload so you know what can I do here to kind of get this thing working Well there's a couple ways we could test this we can either do Sam local or if you remember from our other project。

You can also give it the ability to run locally in foreground mode so there's there's a couple really a couple different ways that you can get this thing to to be invoked or you also can give it a J payload so that's what I'm going to do is I'm going to basically go inside of here。

And I'm going to put a Jason payload here， so I'm going to say touch。

 we'll call this payload do Jason like this， and then I'm going to edit this payload and I'm going to tell it that I want the words entity inside of here。

And then we'll put in， let's say， for example， Google right that looks pretty good and then if I look at the Sam local invoke so Sam invoke and I do help。

That should， let's do dash H for help。They should give me。Oh sorry， Sam local help。

 so it's good to Sam local invoke H。And it tells me the different commands that I can run。

So let's go ahead and do this， we can see Sam local invoke here we go。

 this is what I want is I want this event here and so I'm going to go ahead and say Samlocal invoke payload。

ja so let's go ahead and try that Samloc invoke。Dash E payload。Jason， let's see what happens。

And it looks like。It's close， but we have some kind of an era here。

So let's go ahead and try this to be Amazon， let's go ahead and try that。There we go。

 so you can see that or another one would be。Twitter， we could try that。

 that might be a better name here。There we go so you can see that when I was able to invoke this with Twitter。

 it was able to tell me that in fact this is the first line here so a lot of times when you're first debugging something you may need to try a different couple of different payloads and kind of play around with it a little bit and really get a feel for you know how things work now one little trick that I'll point out here that could be helpful is if I do i Python。

And try to install here， notice that it says it's in a virtual environment so I can do a piip and saw of it。

So and that will put it in my virtual environment。And then what I can do is I can actually use this as a repple。

 so I'll type in I Python。And then I'll say import Wikipedia。And then I could say Wikipedia。

Dot summarize。Or summary and put in the word Google and you should see similar problems like oh it doesn't match that。

 but what about Twitter doesn't match the word Twitter and it looks like it does right and that's why we're able to get this summary So this is a great way to also debug things is to kind of play around with what it would look like from a terminal window So really we're pretty close here to being able to test this out and deploy it So what I'm going to do is I'm going to again you know look at this readme file here that the deploy and it says that do a Sam deploy guided great let's go ahead and do that let's go ahead and deploy this what do we want to call this we'll call this wiki 2021 and then we'll say us region east perfect repository for where we want to put this So I'm going to go over to ECR real quick and I'm going to make a repository where I could put this inside let's go ahead and just。



![](img/5d6854656cbe7063a44fd6054ad616cb_2.png)

![](img/5d6854656cbe7063a44fd6054ad616cb_3.png)

You knowMaybe maybe put a new one together real quick， we'll just call this one wiki。Make that easy。

Go ahead and create this repo， select it， which will allow me to select the URI and then go back and then we'll go ahead and paste that in。

There we go， sure， we want to deploy and just go through and follow the rest of the prompt。

 this looks good， this looks good。This looks good。Great。

 it's now building the container and pushing that container to the Amazon container registry and then also putting this thing into production。

 so this will be a full web service that will accept a payload that will be adjacent payload and I can test it many different ways and this is really the power of this cloud9 based deployment is that I can build this invocation locally test it out。

 play around with it， build little tools that talk to it plus invoke it remotely as well and once this thing is deployed。

 I'll show the the ways that we can go into this and actually test this out so this will take just a second here。

And then what I'm going to do while this is finishing up to deploy is I'm going to spin up the console for Lambda and find this thing。

 which should be appearing any second now， so once this thing is pushed。

 it's going to say waiting for the chain set to be created。Great。

 we can kind of make this a little bit bigger， you can see all the different stuff that it's doing and then it's going to say great previewing。

 do we want to do this， we do。Let's go ahead and say yes， by the way this is the guide to deploy。

 that's why it's prompting me step by step to do this now it's going to create the API gateway。

 it's also going to deploy the right IAM role and then it's going to put this thing into our production environment。

And so once we see this in production environmentment， you'll see that here we go。

 the creation is in process， it's creating it。And we can probably see this as it's getting created if we refresh。

 there we go， right， so already this thing is created nine seconds ago。

And it'll start updating it as it's being created right so we can kind of see it in real time that the window will be completed。

 there we go。And it looks like again， it's working here。And then when it's done。

 what will happen is there we go we can invoke this function remotely。

 so let's go ahead and refresh this thing real quick and basically in order to invoke it。

 all it would need to do is go to test。Right here and put in a test payload， in this case。

 we would say you know wiki。Go through and put in。You know， entity。

It we'll put in Google and then this will allow us to invoke this and we should get the same response right。

 it says， oh yeah， didn't it doesn't like Google so we're going to try Twitter。

Right and we can put Twitter here and it is able to invoke Twitter successfully there we go and I see Twitter is an American microblogging social network perfect and then again you can see here that this stack has been created。

 here's my you production endpoint here and so what we can also do now that it's been deployed just if I go back to this AWS environment and I go down to Lambda we can look at this last deployment here which is wki。

We can scroll here and if I right click on it。That I can right click go one more time don I show again。

If I right click on this thing that we should be able to say invoke on AWS。

And then this will allow me to also put in a payload that's similar to what I did remotely。

 so I can type in you know， entity here， for example。Here we go， entity。

And then do Twitter and let's see what happens。And we can see that I'm able to do that in vocation there we go and it's able to invoke it remotely in fact we can double check this by trying some other name here like for example。

 I don't know Pinterest or。Let's go ahead and double check what the name is of Pinterest real quick。

 Pinterest， okay。I'm going to go ahead and put that in there。Here we go， let's try that， whoops。

 Pinterest。Tourists， let's try this， invoke it。And there you go it found a new website name perfect。

 and then if I go back to my environment here and I go to the monitor。

 we should be able to look at the logs and verify that my cloud9 environment was invoking this function and let's scroll down there we go Pinterest is American image sharing site so really this is a roundtri feedback loop where you can rapidly develop applications using this SAbased system with Python。

 you can deploy it in a production man， a repeatable manner。

 and maybe the next step would be to put this into a system like AWS code build and do continuous delivery。



![](img/5d6854656cbe7063a44fd6054ad616cb_5.png)

![](img/5d6854656cbe7063a44fd6054ad616cb_6.png)

![](img/5d6854656cbe7063a44fd6054ad616cb_7.png)