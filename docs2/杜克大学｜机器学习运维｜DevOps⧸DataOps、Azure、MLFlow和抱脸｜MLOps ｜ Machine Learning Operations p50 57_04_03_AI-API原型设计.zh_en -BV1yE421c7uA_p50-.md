# 杜克大学｜机器学习运维｜DevOps⧸DataOps、Azure、MLFlow和抱脸｜MLOps ｜ Machine Learning Operations p50 57_04_03_AI-API原型设计.zh_en -BV1yE421c7uA_p50-

![](img/ae7828a0db4fda8221c7ef055f4e540f_0.png)

🎼。

![](img/ae7828a0db4fda8221c7ef055f4e540f_2.png)

Hi， my name is Noah Gift and today I'm going to talk to you about how to use bash inside of the AWs Cloud shellll to prototype AI APIs。

 A lot of times it's easy to get caught up in a language like Python or C sharpharp or Ruby or whatever language you're using to develop APIs and before you know it' knee deepep in some API that you don't really understand yet。

 One of the things you can do with the AWs Cloud shellll is use Bsh to build out an initial prototype that lets you explore things very interactively and just try out ideas so that's what we're going to do we're going to use the AWs Cloud shellll to use the AWs comprehend service to pull some data down from Wikipedia do a little bit of sentiment analysis on it。

 do some entity extraction then put it through a bash pipeline so that we can actually figure out some really cool things and you can do these really。

 really quickly from the terminal。Figure out later what you're going to build with those prototypes that you've built in bash。

 okay， let's go ahead and get started。Okay， let's get started here with these AI services。

On AWS we have everything from advanced text analytics， automated code reviews， chatbots。

 forecasting， document analysis， you name it， there's a lot of things。

 What I like to do is I like to start with the Cloudhell and what's awesome about the Cloudhe is that you can try out and prototype ideas and if you want to look at some of the examples are fully baked you can go to NOAAginet AWS comprehend and you can see some of these examples here I'm going to go ahead and get started here and paste in the AWS comprehend detection so to start out with I'm going to say AWS and then I can say comprehend。



![](img/ae7828a0db4fda8221c7ef055f4e540f_4.png)

![](img/ae7828a0db4fda8221c7ef055f4e540f_5.png)

![](img/ae7828a0db4fda8221c7ef055f4e540f_6.png)

And what's nice is if I go through here and I just do a help。

 it will show me more about what this service can do and notice that it says these are the available subcommands so I can do batch detect dominant language classified document。

 all these really cool things here and all I need to do is just put this different subcomd inside so。

To get started with I want to go ahead and just paste an entire document inside and notice when you do a paste it tells you that it's gonna to give me a safe paste here and it says AW is comprehend detect sentiment and I have these new line characters that allow me to put each option here on another line I think this is a good way to build out really complex commands it' to have these new line extensions here because it just makes a lot more readable so here we go I say language code is English and that I say for the text I love C sharpp it's going to tell me whether this is negative positive or neutral。



![](img/ae7828a0db4fda8221c7ef055f4e540f_8.png)

![](img/ae7828a0db4fda8221c7ef055f4e540f_9.png)

Here we go。 it says sentiment positive， so very， very straightforward， in fact。

 and if you want to do AI work， I mean， why even getting into a language you can just get started and start pacing stuff inside of here now there are a couple things here that are a little bit tricky。

That are subtle and one of them is how do I get text into this if I want to play out with some more complex you know website or some other data source and that is a problem and we're going to solve it and then the other thing is how much can I pass into here so if we type in AWS comprehend。

One of the things that's nice is that it does do a really good tab completion。

 so I can start to partially type something， it goes through and it does this。 Now if I do help here。

One of the cool things is it shows me all of the descriptions of the things I can do so I can。

 for example， change you know the text input， I can change the language code， all these things。

 but one thing to be aware of is that each string that you pass in at least from this particular tool must be fewer than 5000 bytes。

 so if you are going to pass in a huge quantity of text， you have to be aware of that so。That is。

 in fact， what we're going to do next， and what I'm going to do is I'm going to install a tool called links。

And this is really way back in the day， something that a lot of people used and what linksx does if I do pseudo Yumman install links is it gives me the ability to browse websites from a terminal。

 so this was actually the way many of us used to browse the internet back in the late 1980s and early 1990s in fact I definitely have done this in my life and what's cool is we can also use it to do data science and so what I'm going to do now is I'm going to grab a little bit of a snippet here of code that I have and I'm going to walk you through what it does。

All right， let's take a look at what this code does it we use links。And then we put in the word dump。

 and this will just dump the text out to the standard out of bash and what I do is I look at this website。

 so let's go ahead and browse it first。This is Wikipedia， Albert Einstein。

 you one of the geniuses of the last several centuries here。

 one of the top geniuses did theoretical physics work helped create the nuclear power revolution and one of the things that we can do is pipe this by using links into the less command and notice here now I can browse and look at things。

 so even if you don't want to do data science， this is really cool to know that you can browse Wikipedia from the terminal by just using links and Wikipedia is fairly friendly with the Li command line tool。

So what we're going to do next here now that we know we can grab some content is I want to just pipe out you know how many lines are inside of your7。

690， but what about bytes， how could we figure that out well the word count command does give us the ability to grab it so if I type in bytes？

Here。😔，Notice that it's way over what the AWS comprehend tool will take， it's 432，000。

 it can only take up 5000， so what I can do here is I can create a variable because that variable can hold maybe an extraction of exactly 5。

000 bytes and so how would we do this， well first up。

 let's go ahead and build out a command line tool that pulls out 5000 bytes。

And let me walk you through it so I do that same dump command， but the head bash command。

 if you pass in dash C， it will actually pull out how many bytes you want and it'll stop right there so we can actually use this and notice it goes through and grabs some text out of here So it looks pretty good looks like we're able to get a little bit of the article here and play around with it at least from a teaching perspective here So now that I've got this。

 how would I use this with the previous command and if we look at the previous command one of the things that's complex about it is that it takes in a dash dash text so if I go up back here and I look at the command notice that this is a little bit complicated because we can't pipe it in we're gonna need to assign something to a variable Fortunatelyly pretty straightforward to do this and bash all we need to do is go to this command and essentially put。

The right syntax around us so put this character here and put this other character here like these these inside quotes here or back ticks and then I can just type in text equals so these back ticks will put the output of this command into this text variable。

And now if I just type in echo dollar sign。Text。We've got this inside of a variable which is pretty cool now in this case though I don't want to just get the word count。

 I actually want to get the entire text command and I want the raw text and so here we go I just swap it out。

Go through here， do the head dash， C。 And then if I do the echo， there we go。

 we've got all the raw text in here， which is again， pretty， pretty cool stuff。And。

What's awesome about this？Is that it gives us quite a bit of really awesome stuff here for us to play around with。

Okay， so now that I've got this thing here and we're able to play around with it。

 the next thing that I'm going to do is I'm going to put this into a more complex command。

 which is the AWS comprehend command so how do we do this well fairly straightforward here is that all I need to do。



![](img/ae7828a0db4fda8221c7ef055f4e540f_11.png)

Is I need to just do AWS comprehend， and so let's go ahead and grab just the parts we care about。

Which is this。 We need to say AWS comprehend a text sentiment， dash language， English。

 And then I just assign the text to this text variable。 Let's go ahead and paste it。 There we go。

 And we can see that that in general， people that write articles on。



![](img/ae7828a0db4fda8221c7ef055f4e540f_13.png)

Einstein feel like they do a pretty good job of doing neutral， but in fact。

 there's a very positive slant。 So let's say around a third of the content is extremely positive for Einstein where in theory you would expect it to be more neutral。

 And so as a historical figure。 he's very well liked。

 So that's kind of an interesting from a data science perspective but。

But what could we do beyond this， right？ Like， are there other things that we could do。

To make things a little bit more complex， well we can。

 So one of the things that I think is a fun thing to play around with is what if I go here and I use detect entities。



![](img/ae7828a0db4fda8221c7ef055f4e540f_15.png)

And then I say output as text， though this time。 So this time I want to use our bash capabilities to start to process something。



![](img/ae7828a0db4fda8221c7ef055f4e540f_17.png)

And notice what we find here is that we have Wikipedia， Albert Einstein， German。

 right if I just look at the first few characters here and we could even do more if I want to say let's say 25 entries you can see that there's even more entries that these are the key items or entities that are pulled out from this text and this again is just using a slightly different AWS comprehend subcommand and now this is pretty good。

 but what if I could actually just get this column。

 the one that has the entities and then find out how many times that entity occurs and I think this would be a really powerful way to get more information about what's happening in this Wikipedia article potentially to do more research or to build out something in another language so in order to do that。



![](img/ae7828a0db4fda8221c7ef055f4e540f_19.png)

I'm going to go over to a command of God called AI pipelinepeline。

 and you can see here that this is a little more complex and essentially。

 let me just first paste it in。And it's gonna to ask the same thing you know and notice once I paste this and I'll explain what it does so we can go ahead and paste this first thing is we do the entity extraction。

 I then pass in the English code I pass in the text we've already done this I tell it to output text and now here's where we get into the bash pipeline what I say is I say grab that column where the entity lives so that's the first thing we do now that I've got the entity I want to convert everything into a cleaned up version so we remove spaces only keep you know basically the alphabetical characters lowercase things and then also get rid of new lines once I've got that that should be pretty close I then sort it。



![](img/ae7828a0db4fda8221c7ef055f4e540f_21.png)

And the sortian allows me to then do a unique count。 So count how many times a entity appears。

 I then do a sort by the first column。 That's what this does。 and I reverse sort it。

 And then I see just the first few items right because if there's a lot of matches。

 I only want to watch a few of the top entities。 So let's go ahead and run this。

And what's nice is that it's getting something that I would expect。

 which is it shows me the most important entities counts them out and so you would expect an article about Einstein would have the word Einstein quite a bit and of course it does University is also covered quite a bit。

 German is covered quite a bit， Empire Albert Kingdom Zuric。

 So these are all things that are potentially interesting to me if I was going to do further data science on it。

 So you are not limited to using Python or using C sharpp or using R some other language to do some very complex data science。

 if you use the Cloudhell and use bash at the same time， you can very。

 very quickly at least prototype a solution using an AI API。



![](img/ae7828a0db4fda8221c7ef055f4e540f_23.png)

![](img/ae7828a0db4fda8221c7ef055f4e540f_24.png)