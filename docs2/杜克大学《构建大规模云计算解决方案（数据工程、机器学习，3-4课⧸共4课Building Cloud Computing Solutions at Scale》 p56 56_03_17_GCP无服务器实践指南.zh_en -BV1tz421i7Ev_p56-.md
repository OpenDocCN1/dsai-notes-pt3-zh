# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p56 56_03_17_GCP无服务器实践指南.zh_en -BV1tz421i7Ev_p56-

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_0.png)

Let's move on to a。Next topic here， which is the GCP cloud， so I covered these two and in particular。

嗯。GCP has some pretty cool stuff that we can play around with。

And so here's a function that I'll just talk us through real quick where。呃。

Basically this is a change machine， so what it does is it is a function that will return back the correct amount of change and so I'm going to invoke this I mean I could basically very similar do the same thing on the ABs cloud but I'll do this one in particular for the GCP cloud So what I'll do here is open up GCP。

And let's go to their cloud functions。And I'm going to log into the console， go to the console。

And to build out cloud functions pretty straightforward， actually。

You just go to a search bar here and type bin functions。And they should pop up in a second。

Once it fully refreshes here。There we go， Cloud functions and inside of cloud functions in order to create one。

不会。Create say create function。And what I can do， but that's annoying is I can say。

New function name and what' would call this。Deops。Change machine or something like that。

And I would decide what region I want to do and just like any other cloud function microservice。

 I could decide what the trigger would be in this case the trigger would be a HCP web service and I then have the choice as well whether to use authentication or unauthenticated invocations。

 I think for demo is unauthenticated as the way to go and so。

I'll go ahead and say on unauthenticated invocations。I'll go ahead and save that。Go to next。

And notice that we have a choice here of Python 3738， no Java go donet， all kinds of stuff。

 so I'm going to select Python 38 here。And in particular。

 you can see this is like a hollow world type。You know， template that they give you。

 but in our situation， I already have some code。That I'm going to throw in there。

 So what I'm going to do。Is I'm going to go to this and I'm going to put in this this payload here。

 which is kind of a fun little project。 Well what this does is it allows us to pass in a。

Adjason payload。That has the word a amount in it。And some。

 some coin amount or some raw amount like $1。34。 And then what happens is it gives us the correct change and it kind of prints it out here。

 So notice that the entry point has to match。 So in this case this is hello world， hello world。

And also。I think this is an advantage that this interface has a little bit over the Lambda is you can put the installs right here。

 which is pretty nice， so I'm going to go ahead and say deploy。

And what this will do is put this thing into production。And boy。

 that is really annoying feature of that window popping up a bunch。 So basically。

 once this thing is been deployed。Then I can actually start prototyping out this code here。And。

The things to look at are。Of testing and so under the testing window。

 it really wants that function thing to appear。So under the testing window here。

What I would do is put in my payload and so that payload would look something like this。

 it would be a amount， I'll make this a little bit bigger。This is like conspiring to。22。Reset。

 I don't know， stop popping up。And we go here and we see mounts。We say $1。34。And in theory， this。

 there we go。It gives me a 134， it looks like it's valid Jason。And if I say test。We can。

 we can scroll down here and there we go。 You can see that it actually returns back the correct amount of change。

 And if I want to change it to other things I can you know， go through here and。Give it。

 I don't know，$10 and。And 44 cents and then test that out and see there's bunch more quarters， right？

So we have a neat little service here to test out。We can do a lot more as well。

 and this really shows the power of these cloud based development environments if I click on this icon activateivate Cloudhell。

What I can do here is get into testing this function out via a command line tool and so let's go ahead and take a look at this real quick and what I can do is look at this command in this command in particular allows me to invoke it via the Cloud shellll which is pretty awesome right so let's say that I built some kind of a computer vision pipeline and I have it triggered inside of here or I have。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_2.png)

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_3.png)

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_4.png)

You know， some kind of proprietary thing， I can again just treat it like it's a piece of logic that's deployed。

 it's just waiting for me to run it whenever I want to run it and I can invoke it via Kamelan tool to me is this is actually pretty awesome so I'm going to change this up here。

And I'm going to type in DevOs change machine。Like this。And what we can do。Is actually invoked this。

Like this。And it will take a second and it's going to ask me to authenticate， which is fine。

 so we'll go through here and authenticate。Great， it's going to ask me to do this。

 I'll go ahead and authenticate， that's fine。

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_6.png)

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_7.png)

Allow this copy。Now if I go back here， I can enter this off code and what we'll do is I can now go through and execute that cloud function。

There we go， so now I can just you know basically go through here and just start tweaking things around。

And I can just run it as many times as I want。So I think this is an awesome workflow that this is an intentionally simple application。

 but it shows how you could integrate this into a lot of different applications now the other thing that we can do here is we can do more than just invoke it you via passing a payload in we can also invoke it as a web service because it's got that trigger built in and so if you look at this。

Here， notice how this trigger。Right there is the URL。

 So I if I basically just copy this trigger here。And I say。嗯。You know， basically。Export， URL。Equals。

This。Like that。I could say echo dollar sign URL。 There we go。

 So we got this URL step stepped in here。 And then if I go to a curl command。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_9.png)

I can basically curl this and do some more tricky stuff to it。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_11.png)

If I go back to my cloud shell。I can tee up this command， let's see if we can get this working。

 so I'm going to curl， I'm going to put in the amount 134。And then in terms of the actual URL。

I'll just do this。 I'll just say trigger。I'll just put in。呃。The dollar sign URL just like that。

 right， And in theory， this should work。 There we go。 So then I can actually put in， you know。

 different things。 I mean， I guess I could be fancy here。And。

And and even like let multiple things swap， like create different variables。

 I mean I guess I could try that real quick。 So what I could do is I could。I could say。You know。

 open editor。Here。😔，And I could first grab this command。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_13.png)

And I could make a little edit command in here too。Build a。In vocation and assilates。

I'll scrollcro this up a little bit here and。Make this come up here。And I could write a very simple。

Sll command That allows me to。Via terminal， new terminal， there we go。 Okay， so I can just say。嗯。

Touch。Invoke dot S H。And then where's my invoked dosage command。W。

 we've got lots of different projects open here。There we go。 Invoke data S。

 and let's just put this inside of there and just tweak it a little bit。 So basically， I could do。

A dollar sign here as well。Right so I could say。Dollar sign。嗯。Change or something like that。

 There we go， change。And。😔，And if I just grab this。I could。Say。嗯。Export。Actually。

 I think this should be in my environment already， echo。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_15.png)

I have to go back to this terminal， which is kind of annoying， but I'll just say export。

Dollar sign change。Equals 134 like this。Oh， I don't need a dollar sign right there， there you go。

 export， set this variable up， echo it just to make sure it looks right。Change。Now。

 I might have to do。Quote in there。Like this。That looks right and then。

If I put in this cha in like this。Does that work？OhOh， I screwed something up。Post。

 I think it's because。I need to do this。 I need to swap。 I need to swap those and say。

These are the inner quotes。Orre or or this， I believe。Anyway， well， something similar。

Getting into the Ba scripting is less of the whole point here is that you can easily build out these invocations via web service or you can invoke it via command line and it's a great way to interact with your cloud function。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_17.png)

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_18.png)

If you want to take a look at that， there's an example。

Here that's allows you to invoke this cloud function。 Now。

 there is another one that I have as well that's inside of here that I can take a look at since I have some time。

That allows me to do something a little more complex。And hopefully it works。

 I think I have to look at the last invocation here。 So I think。The last， there's a translation。

APpiI here。That。I believe it's this one， this is a pretty good one。And。Inside of this。

 if we look at the source code。What it will do is a little bit more magic here。

 so let me just close this。So this is a。A good example of a slightly more complex。Function that。

I install a library called Wikipedia and I also install a library called Google Cloud Translate。And。

If you look at the code here， the source code here。嗯。You'll notice that。Inside of this。

 I can actually translate whatever is passed in and then I have a request here that allows me to pass in entity and language so basically what website would I like to translate or what web page in Wikipedia and then also what language so。

I believe I can actually double check this。By going back to here。

And going to Cloudhell and looking at some。

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_20.png)

An example here， so I can say GC， I can say history。GrP GC。And we can see here that theres。

 I think this is the1 I called earlier。 Let's go ahead and try this。嗯。

And this would be a slightly more complex cloud function。

And so it's going to ask me to do this again。 So we'll go ahead and authenticate this real quick。

And off， sure。

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_22.png)

Allow。

![](img/13537fd61cc5dcfb0eb9ba3675cba85d_24.png)

Cy。😔，Pasteted them。And if I run it again here。In， in theory。It should look something like this。

So so basically can you can go through and translate， I don't know if this yeah， there we go。

 so you can see that in this particular function can I can pass pass in you know。

 names into this function。And。Right， so I can say， look， go to Google。Go to Wikipedia。

 grab the Google page， grab 20 sentences and translate it to Spanish right and so we go here。So。Now。

 Google maybe maybe Google doesn't match something， so we'll have to do maybe another one like。呃。

Amazon， thetray Amazon。So maybe AWS。Oracle， that's a good one。 We have to find a name of。

There you go， let's try workacle。Yeah， so' it doesn't necessarily have a ton of air handling well。

 we know one of them works we know this one works so and then if I wanted to change to different languages。

 I could just look at the different versions of languages so I think like maybe is it Italian is that IT maybe let's see if that works okay there we go。

 there's Italian， we could also see C I think is probably Chinese no。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_26.png)

嗯。Are you as maybe Russian。Just guessing， I don't know exactly the different languages。There you go。



![](img/13537fd61cc5dcfb0eb9ba3675cba85d_28.png)