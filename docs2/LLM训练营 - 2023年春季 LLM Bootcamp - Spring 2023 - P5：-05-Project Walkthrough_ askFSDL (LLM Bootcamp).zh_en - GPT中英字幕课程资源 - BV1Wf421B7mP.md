# LLM训练营 - 2023年春季 LLM Bootcamp - Spring 2023 - P5：-05-Project Walkthrough_ askFSDL (LLM Bootcamp).zh_en - GPT中英字幕课程资源 - BV1Wf421B7mP

🎼，🎼。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_1.png)

I wanted to walk everybody through the code base for the Discord bot that you were interacting with this morning。

 so as a reminder that's the Ask FSDL bot channel in the。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_3.png)

In the discord and。Yeah， so it's sort of a bit more mature version of what I walked through building this morning。

 so just sourced question answering over a corpus of information using vector storage for retrieval。

And so's there's a GiHub repo for this project， I posted the link in the Discord as well。

 so if you want to follow along look at some of the code yourself。

There's a bunch of moving pieces to set up document database and an account on modal。

 so I doubt you'll be able to execute the code unless you happen to have accounts on every single service that we're using。

 but you can at least check the code out and follow along and also still encourage people to ask questions in the Q&A channel for any questions that they have。

So。All right， let's dive in。What are some of the like primary things that you need to improve as you're going forward so there's some like basic stuff that's just like generic python project management things so for example。

Actually， let me drop into VS code。Here。So one nice little feature that we like to do at FSDL with a lot of our projects is you make a nice little make fileile for all the components of the project with a nice little help message so there' this is all the different pieces and the make fileile can sort of like set up and run a bunch of these things so set up Discord bot deploy the backend set up a vector index。

 all that good stuff so that's where you'll want to go if you want to see like what are like set up run the setup commands so it's got things like the environment and setting up authentication with a bunch of our tools。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_5.png)

So then other things that you might want in a project。

The like we were just kind of yellowing code in the morning in Jupiter notebooks and other places theres。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_7.png)

In in this project we've got a bunch of nice software tools。

 so one of the main ones is precommits for GitHub so this is just like a code cleanliness thing if you're doing software engineering you want to make sure that when a team's collaborating on a code base that people you know are good stewards of the code and so precommit checks every time somebody's about to commit something to GitHub you can just run some tracks on it to make sure that they haven't made any common mistakes。

 added extra white space messed up the syntax or common files， forgot that they were in a merge。

 added large files， lots of little simple ones and then also a bunch of other code quality things we like to use black for Python auto formatting to make sure formats of Python files all look the same we've recently switched over in past iterations of the course we've used the toolflake8 for Liing for like sort of catching sort。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_9.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_10.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_11.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_12.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_13.png)

simple stylistic errors or and like style conventions rough came out just in the last like six or nine months became a lot more popular rust powered formater for Python that's really quite nice and yeah let's just run that real quick check to make sure I haven't messed anything up。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_15.png)

So。Yeah， this。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_17.png)

Yeah these kinds of tools， there's one more that I wanted to quickly shout out which is this shell check tool。

 if you find yourself writing a lot of bash scripts， you know like copy to Redis。sh or whatever。

 and you find yourself like googling you're going to chat GT to check things。

 shell check is really nice for catching those like dumb things about arrays and if statements and other things that the devil bash scripting。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_19.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_20.png)

Yeah， so some basic little software engineering things。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_22.png)

嗯。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_24.png)

And。But then there's also a bunch of stuff， this is like the sort of thing that you need to support like any sort of software engineering project using Python you need this kind of tooling。

 what about things that made this project in particular better？



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_26.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_27.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_28.png)

So I'm jumping around all over the place but what I wanted to show you was the data processing step so one of the first things that we realized when we did the like bare minimum version of this it looked a lot like what I did in the morning which is just like scraped data and like chunk it up into little pieces and like those are the sources that you're going to use and that turns out to like not work super well it doesn't give really good results for people and so what we found was that we got the biggest improvements in the quality of the results by spending time with our data so there's a little Jupyter notebook that walks through some of the things that we did to improve our data and this also happens to set up the overall like document database as well so you can see how that's done。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_30.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_31.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_32.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_33.png)

You can bring your own like MongoDb database， we used the like Atlas hosted platform。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_35.png)

So like just to give you an example of the kinds of things that turn out to be like critically important。

 so in addition to the like PDF files that we talked about this morning。

 we also pulled a lot of stuff from the like full stack deep learning website where we host a bunch of like notes about our lectures and like other kinds of things and if you just like treat it as text and parse it as text you lose all the structure that's in that structured text that's in the like the features of the markdown so it's got things like section headers it's got like。

Like separate。Paragraphs， its there's like a lot of richness there and in a lot of cases those end up being like linked to specific components of pages and the goal of this was provide sources to help people quickly find information and so being able to like preserve that structure when you're bringing in the documents turned out to be pretty important。

So this requires like a little bit of knowledge of like the data that you're scraping。

 so it's maybe like if you're scraping internet scale stuff。

 this is going to be a lot more challenging， but if you're building something that's like oriented to like Q&A over your company's knowledge store。

 then maybe you have a little bit more context that can do these things。

Improv the like automated processing of text is definitely something that large language models hopefully will be able to do in the next couple of years。

嗯。But so it's a matter of like searching around finding the right kind of like Python libraries for solving these kinds of problems without you having to write a bunch of hard to maintain code yourself。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_37.png)

So all this splitting the goal there is to just get some like basic format of these documents。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_39.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_40.png)

That preserves the information needed to link to them and preserves as much of the structure as possible。

 so this is distinct from what you might also see people doing with tools like L chain and things integrated with it which is chunking stuff up to put it in effective vector store thats like that's a matter of making sure something is small enough to fit into the context of a language model as opposed to like just parsing a document and like preserving its structure while you're storing it。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_42.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_43.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_44.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_45.png)

Then the other thing is that like in the morning we talked about like having to load PDFs and PDFs are kind of you know an image format in a lot of ways rather than text。

 but it's plausible that you can just get the text out of a PDF but that's not like the only thing that you can potentially index there are lots of ways to automatically extract textual information from other kinds of sources so you can pass images into an image to text model。

 the sort of reverse of something like Dolly or midjoney。

 something that takes in an image and returns the description of its content the thing that we focused on was our YouTube videos so we put videos of our content online those videos get transcripts actually for free from YouTube and we can then use those transcripts as sources for our。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_47.png)

For the question answering Bob so finding creative ways to extract data from your like from your knowledge faces and make them accessible to LLMs via embeddings or via other ways of like connecting them up with the language model is like I think a big open open field for ways to make more useful language model applications。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_49.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_50.png)

So this， you know， spent a good chunk of time trying to figure out how to use the YouTube SDK before realizing there's just one Python library that'll do it for you。

 YouTube transcript API， which you love to see， we can only hope that the number of dumb little Python libraries that solve one little task goes up over time with language models。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_52.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_53.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_54.png)

But even when you have like pretty good access to like quickly get a hold of data that's often some kind of scrape that's not taking your particular problem into account so the problem that I ran into with the YouTube videos was that all of the tags there were timing tags which is awesome timing tags can be used to like link to a YouTube video you can link to a specific moment in the video and that's awesome for this sourcing application because I can just bring them exactly to the point in the video where their question is answered but the subtitles are time tags for like one second at a time because that's used to put them layer them on top of a video。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_56.png)

So you there's a pretty simple fix， which is just to go in and chunk it into a size that contains a useful amount of information or like has about a couple thousand tokens or a couple hundred tokens worth of text in it。

 so it's a relatively simple solution but these are the kinds of things that unless you're thinking about a particular data source the particular problem you're trying to solve then like you won't think to do them。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_58.png)

So。That was our that was like a big increase in the。Like the quality of the results here。

 I think for myself personally， one of the things I found this most useful for is like finding components of our videos where it's like I know that I talked about this at some point and just ask at the bot and then it pulls me directly to the。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_60.png)

So like there's big dividends that come to this kind of like front work or this like unglamorous work of like getting to know the data and like writing the dumb little code to。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_62.png)

To manage it properly。So that's the main thing I wanted to talk about in this notebook。

 it goes into a little bit more like there's a little bit of stuff there about how we get it into the document store。

 but that's a little bit less interesting。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_64.png)

Are we getting any questions in that Q&A channel？There's a question about can you talk more about how you're using modal and why yeah that would be you know that's suspiciously close to my next plan topic but are there any other questions before I do that actually there aren't yet unless my internet slow Yeah could be it。

Yeah， let's。Yeah， let's do that then。So maybe， yeah， real quick。

I want to also just pull up that architecture diagram because as dumb as architecture diagrams are。

 they're really helpful for keeping it all in your head。People are asking。

 are you going to share the notebook？Yeah， the notebook is there's a link to that GitHub repo in the Discord and that has that notebook in it。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_66.png)

Yeah， okay， so what were we just talking about， we were just talking about the kind of like ETL component of this。

 which is like how do I extract information from places where it's located out there on the web or in my like the general data storage of my organization。

 how do I transform it into the format that is most useful and then how do I load that into some like specific storage for that specific transformed data so that's the top left corner there for a lot of stuff I showed all that stuff happening in the Jupyter notebook but it's the sort of thing that you might want to use a tool like Boal for。

So Moal like you may have noticed like I was just like grabbing random python packages and using them for stuff and the nice thing about that is it brings like the code that you need for the particular problem you're trying to solve but。

If once you start installing like 50 or 60 dumb little Python packages。

 all of a sudden it's like they disagree about which version of some like seventh order transitive dependency and now they no longer work。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_68.png)

And yeah， specifically， the Python devb tooling stack is particularly bad about that。

 which is a great reason to use that pre commitmit tool that kind of isolates the environments and makes sure that you aren't like you know。

 black and Fake eight have incompatible versions of some yeah。

 there was a particular example that was really bad and broke a bunch of installs like nine months ago。

Yeah yeah， so there's a bunch of things that are solved by the like Moal component of this application。

 but one of them is that you can actually separate out different container images for like each thing that you want to do so to clarify what that means is you're basically like creating a lightweight virtual machine that runs in Moals cloud like for each task that you want to solve。

So I didn't do as much breaking down of the modal images as I would like to do in this particular example。

 but that's like that's one of the core the core benefits you define one of these images here。

 a modal image you pick some some base version and then you you like customize it so this is all Pip installs but you can do all kinds of other things many of the things if you're familiar with making doctor containers yourself then you's like a lot of the things you might expect like know mounting mounting things installing Linux packages。

 running shelf commands etc ce and one big reason why I really love modal like。

six months ago or so I started looking into options and this is the one that I ended up sticking with is that it's actually not literally a Docker image。

 it is an open container image compliant like implementation and it's like incredibly fast and that means that a lot of the pain that you might have experienced if you've used another like similar tool for cloud native development goes away。

So maybe just like a quick。Some quick evidence of that。Would be to just。Do the debugger。

So just as an example， like another like the things are often quite slow。

 like I mean like creating containers can be slow， pushing container images around can be slow。

 like you end up introducing a bunch of friction that then reduces the actual benefit to your deployment speed so with this。

With modal the speed is quite good and there's a lot of like nice little features added that like help make sure your development cycles stay really fast。

 so this example here is supported by just like one little like block of code down here I'm like writing this little function that imports i Python and then spins up an iPython kernel so this is actually now one of my preferred ways to do debugging even locally but I discovered it as the suggested way to debug stuff on modal it includes the context of your。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_70.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_71.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_72.png)

Of the things that you are running。In the cloud infrastructure because it's running there。

 but it's like nearly as fast and nearly as convenient as running like a kernel running like an iython set up locally。

 so I think there should be a。Get which things I implemented for the in an hour version versus in this version。

I think that。How did be maybe。Yeah， there we go， okay， so I can run things that is。哦。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_74.png)

Yeah。Yeah。So all this so that function right there， this Q&A L chain。

 this is something that is like something that runs in my backend。

 it runs in an environment that's like not something that I want to try and replicate locally that don't want to keep in line。

 but I could run it a little bit like as though I were like developing locally using by just like connecting to a container that's running on modal and doing it in interactive mode。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_76.png)

嗯。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_78.png)

So right so main pain points that are main pain points that are going away yeah so in the morning I talked about how it was like oh yeah launch 100 containers at once run them on like all your little paths collected up so that's obviously an accelerator we talked about the ability to spin up a specific environment。

 avoid those things oh and then in addition to all this like the goal of it。

 it isn't just like a data engineering platform or anything like that it's also got this it's also designed to like end up with applications so it's got things built into it like asynchronous server gateway interfaces as endpoints that are just like like very very well designed abstractions that you can wrap on top of the stuff that you're building and end up with an application like the one that you' have been interacting with and just to see like you get a decent interface into it like I can check this I check the application and see activity。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_80.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_81.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_82.png)

I can get like a lot more detail like you can attach to GPUs if you want and like and then you can track things like utilization and then all this is done like。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_84.png)

Is done serverlessly So whenever you like need compute。

 you get a hold of it and then when you don't need it， it goes away。

 And so since a lot of stuff right now is in this very tinkering phase。

Where you're like maybe you only have users for like 20 minutes in the morning right when you're showing them your application and then you have no users for the rest of the day。

 it would sure would be a shame to like have to spin up a bunch of servers in order to handle those requests and then leave them on while nobody's talking to you and so this like spinning up and spinning down auto scaling is built into Moal and works in my experience like pretty well。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_86.png)

Definitely challenging if you're like loading a machine learning model。

 putting it on the GPU and serving a request， that's a pretty challenging application of serverless。

 Moal does an okay job at it in my experience。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_88.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_89.png)

The other piece added that I wanted to call out that was added to this and is generally useful is a radio user interface。

 so radio。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_91.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_92.png)

Scrorolling down。So there's our yeah， this is our like the Moal ASG app， we got that and。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_94.png)

This。Preio is the tool that means that I don't actually have to learn JavaScript already。

 you know it's like since then also chat UT has meant that I don't have to learn JavaScript。

 but what it provides for you primarily is that you can describe an interface like a user interface in pure Python and then end up with like a kind of simple like single or few page application that has that interface in it and it's。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_96.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_97.png)

It's like surprisingly flexible， it's supported by hugging face and so they like rapidly add all the features that you would want as somebody building with machine learning so here's like here's an example this also happens to be the interface that has been used by like Alpaca and I think flamingo as the way that they demonstrate their models they use like a little little radio app Dolly Mini was originally a radio app so it's a great way to like get started really quickly。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_99.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_100.png)

And yeah， that was just a little serverless cold boot right there， I just hit hit refresh。

 took a few seconds， so if you're worried about your P99 s。

 you might want to do something like keep some things alive at all times。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_102.png)

But yeah this interface I describe it entirely in Python it interacts with stuff that is primarily in Python so Lang chain and like maybe I'm like doing stuff with my embedding vectors。

 maybe I'm running my own models a lot of that stuff is going to be in Python and I can play around with it here and I like to do this it's so easy to spin one of these things up that I like to do it as something that like let's say I like run a training run for a model I might just like spin up a UI for it like for that specific version of that model so that I can go back to it and be like wait when did this weird behavior get introduced in my models。

 was it in this one or was it in like was it three months ago or was it one month ago。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_104.png)

Yeah， so you know， I can check。My language model's behavior on important questions like would you rather fight 100 Lama sized GPD4s or 1 GPD4 sized Lama。

 I can go back and use this example and check it on all kinds of different models if I do that。Great。

Yeah so radio quick quick UIs both for like demos and also for like other places where a UI would be great but you don't want to take the time to spin it up you can embed them as you can run them into Jupyter notebooks you can like embed them as iframes they're like very portable and flexible and they come with an API with an open API spec I believe always an open API spec and so like you can hook up up into a bunch of different tooling these are like getting hooked up into things like chattT plugins via the like open API oh and it comes with a client SDK for like like for everything that you make like you don't just have to interact with stuff via like requests and HP so now we've got oh check it out like I have this client SDK for running my。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_106.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_107.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_108.png)

Running like Q and A。The sources。Any questions in the discoursed？

How did you actually hook up discord to this Oh yeah。

 that was that was kind of like the least interesting part， but I can show。ThatSo discord。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_110.png)

There's of course a Python library for running Discord bots it's called just so Discord P was the one that I ran with I've actually heard from other people that there's one called interactions that's a little bit better so you might want to try that one instead。

 but this one was perfectly fine。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_112.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_113.png)

You know。You know， looking back on it I'm you know Discord is not the easiest interface to run stuff with there's a lot of like precise like very fitdly details。

 for example， they're not actually called like forums or groups or servers they're called guilds dating back to win Discord was for organizing wow raids and so there's just like a bunch of yeah it's a weird weird interface but there's some nice stuff like it was one of my first like or yeah it was a good experience with like async Python for。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_115.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_116.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_117.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_118.png)

Like。Being able to handle more requests， but yeah it's like。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_120.png)

Very simple to add these like commands and then you get this nice user interface。

 so I shouldn't talk too much。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_122.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_123.png)

baad about it， but you just define like these like events and I think maybe the more interesting thing or maybe the question the person was really asking is less about like what does it look like to run this discord bot and more like what does like how does the Discord bot talk to the service？



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_125.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_126.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_127.png)

So if I remembered correctly that's in yeah it's in the answer so we got the we had those slash commands so if you wanted to run this you type slash ask there are some fiction nice features in Discord like like kind of。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_129.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_130.png)

Arguments and documentation of those arguments。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_132.png)

Where are we at， yeah， oh， it was runner， not answer。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_134.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_135.png)

So like when you set up something as a web endpoint on Moal you just have like normal HP access。

 so if this were a requests library， like if this were or sorry if this were synchronous Python we could just use the request library and this would look really simple I would just be there'd be a get request to a particular URL with certain parameters。

 but because it's async Python everything has to be like async with async with a weight return。

 it's yeah it's a bit clunky to write this stuff in my experience but what you end up with is like you can write a pretty scalable web server in Python。

So yeah oh that's an important point radio provides these UIs underneath the hood is fast API。

 so fast API is one of the like more user friendly ways to get like an asynchronous Python like web service running so if you wanted to go like another level down under radio like you wanted to offer stuff that where user interface didn't make as much sense fast API would be a way to do it and I believe that's what's underneath this discord bot as well。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_137.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_138.png)

Yeah， so that's just like jumping back to our diagram to make sure that where we're at is clear so that's the。

I was just showing the Discord bot server that's just like sitting on a little cloud instance on AWS and the meat of the application is all the stuff running on modal's infrastructure as these little containers that get like spun up as needed to serve traffic。

What library did you use to generate embeddings？Oh yeah so yeah I guess I didn't call out the embeddings here so open AI offers embeddings they have like a bunch of additional embedding models that aren't good for like generating text but they are good for like extracting the context of text and putting it into vectors so it's the open AI Ata 002 models it's like it's like dirt cheap it's like 00 times cheaper than the generation endpoints maybe more and it it like gives decent results I think。

It would be a good idea to add additional types of search here like right now I just have data storage because do a vector index and that's the communication。

 I think really you want like your data storage with your metadata there to like actually pull out the information not just the em。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_140.png)

And people also ask about processing PDFs。Yeah， so that one was primarily in the previous one。

 I actually don't have that code in in this repo yet， but that one was。

I believe I could just do this。Yeah there we go so the like core thing I was talking about in the morning was like write some local code that just talks about the like what is the high level thing I'm trying to do I'm trying to use some like a description of some PDFs to get a hold of their URLs I want to read all of them and then I want to add them all to the document D so the part where I spun up 100 containers that was this map call here which says like。

Which takes a you take a function that you've defined in Moal and you map it over some iterator and like spin up。

 you can control the concurrency， I just said maximum concurrency for fun but you can control the concurrency how many things get launched to handle those returns them in order which is convenient and then you get back something that's in your local python and you take that thing in your local python and then you can pass it back up to some modal function so with the application the way I set it up is really like web services it's like there's a bunch of services they have URLs you talk to them you can also run things that are in a much more Python way like it looks as though this is just normal python like I'm doing a map I'm just like calling something but really this is doing stuff via web services but the serialization and decialization is like kind of handled for me。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_142.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_143.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_144.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_145.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_146.png)

And you may have shown this， but what again， is the retrieval？

Like how is the retrieval result put into this Ysha pro or put into the prompt？

That is actually inside the Lang chain prompt template， this is a little hard to pull it up。

 but the basic answer is that it's an F string so you have a templated string so you might be familiar with Ging templates if you're more of a web developer person and you just insert the things that come out the source into the prompt as like this is the source like brackets the source URL this is the content brackets content and that all get stuffed into the prompt maybe just show the。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_148.png)

Function if you have it here yeah it's so it's it's in it's deep inside of the L chain library that no。

 but like just what's the L chain call Oh yeah that's not super。And then a good question is。

What do you think are the top three？

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_150.png)

Challenges for you。If you wanted to take the bond to like the next level。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_152.png)

So yeah this is to answer the previous question it's like you provide a little dictionary with the stuff that needs to go into those into the components of your template right so this I'm calling a chain on Lang chain defined with Lang chain and it's this dictionary here that has input documents and a question and this gets put into the prompt here so not particularly like detailed on how that goes。

 but you in general like hop on Langchas Github and look up the source code yeah as something that's like mostly a framework kind of like the Hugingface transformformers library it's something where the code is often like quite simple it's just that you don't want to have to write that boilerplate。

 you want to use something that has an interface that other tools will expect etc so it's not super complicated so I often。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_154.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_155.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_156.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_157.png)

myself just like reading the code。嗯。Then the follow question was， what。

 what does it take to bring the spot to the next level， So I think the。Top three challenges。

 one is making sure like improving the retrieval， the second one is improving the quality of the model outputs。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_159.png)

And the third one would be actually you know identifying a like solid user base so you know the third one that's that's too hard of a problem like you know if this were actually a useful idea。

 I could you know launch it as it's independent startup so I'll focus on the first two。

So for improving the retrieval， I think the primary thing is that people have been working on information retrieval。

 there's like there's a bunch of ready to go ideas there for improving the quality of the language models there's I've made a little bit of progress in that direction so one thing that has been added is information。

Is logged to。A feedback store or a place where all the behavior of my model all the behaviors of my model can be stored。

 so if you're familiar with tools like I mean even just like Datadog and sensor but also honeycomb for handling a web service you want to know everything that is going on in a web service you want to know you want to know what the inputs and outputs where and if you're in a distributed setting it can often be like very difficult to debug stuff without that kind of that amount of tracing and so the same thing the same principle applies with ML powered apps and LLM powered apps you want to trace what is you know what queers are coming in what and what the answers are and in this case and so the entry provides for this let's see where's。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_161.png)

Lologgs the events toantry， it's pretty straightforward like you I log records。

 you want to keep track of a join key like just to make sure that you have like a unique identifier for stuff in case you want to bring in like there is that emoji feedback that emoji feedbacks not available at the time that the event is log so you want to have like a key so that you can pull that later maybe you run like a nightly or weekly job to like ingress that feedback and join it。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_163.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_164.png)

嗯。So I think I'll close out then in our last five minutes with is like quickly showing what that looks like this so this interface here like here's this is just the high level dashboard showing。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_166.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_167.png)

Like what happened today or in the last 24 hours on this application， so last night I was testing it。

Pretty in the evening then this morning put it out on the discord。

 looks like people used it a bunch this afternoon， started talking about it again。

 people started using it again， so its like high level count of events but maybe one of the really useful features is I'm like at the moment that the event happens I just want to like grab what happened and store it but later like the inputs and outputs are unstructured data so there's lots of potential questions you might want to like ask about it。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_169.png)

Was this an instance of my model being like bias， do I have a user who's trying to hack my model like do I have like do I have a sudden influx of users who speak a different language and there's a nice scananttry feature for。

Enriching data that you've already logged these projections， so for example。

 is somebody asking toxic questions。Oh yeah， this is a little small， sorry。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_171.png)

So you can add these afterwards， backfi them and then they'll get filled in as you go。

 some of them are like natural languagebased things like is this an insult or not。

 some of them are more numerical things， like what's the entropy of this text。

 what's the number of sentences， there's projections for other things。

 there's some more advanced features like embeddings if you want to really get crazy。

I was looking at some comparisons。For example， you can intentionally try and extract like what are the toxic questions and non toxic questions。

 people seem to have behaved themselves pretty well this morning。

And nobody really asked any toxic questions。So that's maybe good。But there was in here。

This toxicity check did pull up this particular record where somebody asked。

About prompt injection and was it like seemingly attempting to maybe prompt inject the model。

 so give an example prompt injection that works on GP3。5。嗯。So yeah。

 nothing like in the last half hour before this talk。

 I went and checked and looked for any interesting patterns and it looked like you know things。

 people were there were some questions that the model didn't answer super well。

 but nothing too concerning on behavior of users or on behavior of models。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_173.png)

But yeah， it's good to be able to have that information to look into。

And then you're not necessarily you don't necessarily need to just analyze it in Gantries's interface so you can actually like get that stuff back down so I pulled it into a panda's data frame that I could check out on just on my own and the thing that I tried with my like 10 minutes in during the break was like one of the most promising avenues for actually being able to check whether our applications work is using language models to check on our language models so I was just like hey chatttBT is the answer below a reasonable answer to the question if the reasonable answer respond with yes。

 it's an unreasonable answer respond with no question answer threw that up into like into L chain ran ran the chattBT。

 the turbo model on it and just like parse the answer， if yes is in the answer then it's。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_175.png)

Psible answer。And tried it out， Cha UBT thought about half of the answers were reasonable。

And we can see a couple of those examples here so what is it think reasonable how are you doing today I'm doing well thank you who's a good bot a good bot is Blunderbot three a deployed conversation legend that continually wanted to constantlyly engage so you know I was hoping I would get like a magical moment with ELMs but it's a little。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_177.png)

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_178.png)

it's a little fiddly still would need some tuning on this data to get it to work well。

 but yeah in principle you can start to identify issues with your model by looking through data that you've logged like its frequently。

 for example， this particular prop template contains the state of the union address from 2020 in it or 2021 in it and so it tends to accidentally say things about Joe Biden Justice Stephen Breer and the coronavirus pandemic。

 so like identifying that and making sure and checking for that in your outputs very doable with language models and and then tracking it with something like entry。

 so that would be that to wrap it back up to the original question the real difficult thing is like determining whether the thing is running well in production whether users are happy and there's like tooling for observability for ML that's probably the solution。



![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_180.png)

吧。这要。嗯。Yeah， yeah， so yeah it's open I would like to make this better。

 I think we would like it to eventually develop into like a teaching tool application and so yeah。

 we love contributions。But yeah， I'm over my time， so can't take any more questions。

 thanks everybody。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_182.png)

🎼。🎼Yeah。🎼，🎼。

![](img/e7e22aaa8cc6d46d8673de82a33dc5b1_184.png)