# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p35 6_使用统计模型探索数据（第一部分）.zh_en -BV1L9Fde5EXS_p35-

Statistical models can play many different roles in a data analysis in this lecture I'll talk about how to use statistical models to explore your data。

So exploratory data analysis can have two broad goals。

 the first is more basic and whereas you determineative whether you have the right data to answer your question and part of exploratory data analysis is to determine do you need to get more data do you need to change data sets or do you need to change your question or refine your question so what I'm going to talk about in this lecture is really how do we develop a sketch of a solution to your question assume your question is appropriate and is answerable we want to start sketching out a solution。



![](img/9b3c60f05312a4c9d0b3b15668b78387_1.png)

So in many ways， it is like， with filmmaking， you want to make a rough cut of your movie。

 right So there's the idea is it's not gonna be the final product。

 but it's gonna to give you a sense of how things flow how things work。

 And if you're gonna make an argument to someone， you're going for doing this versus that。

 And you want to build evidence to make your case。 This is gonna be a basic sketch of how that argument is going work out。

 so that's what we'll talk about in this lecture。 And so this lecture is really about using statistical models to help you to summarize your data and to eventually kind of make things do things like make inference。

 so the first thing we need to talk about is what is a model。 and why do we need them。

 Okay so models generally speaking are just constructs that we build to help us understand the real world。

 so for example， in biology， often people will use mice as models for humans。

 So we can't do experiments on humans。 So we we sometimes people do experiments on mice to。

To use to kind of give a sense of what might happen in a human being， for example。

 for things like drug development or whatever。 Now so that's a that's a physical type of model。

 we're not going be talking about those kinds of models， of course。

 but the models that we use are mathematical models in many cases and we use them to to kind of help us describe the population that we're talking about So if's if there's a population out there that we're trying to make inferences to or to describe in some way。

 we use a model to kind of help us do that because often the population is too complex to think about all at once。

 So imagine if you're trying to make a statement about the entire United States everyone in the United States all things that might go on between all the 300 so million people in the United States。

 it's impossible to think about so we need a model to help us simplify that to give to get us to allow us to think about it in a kind of a reasonable way。

 So the idea that the models will stand in for the population and they are much simpler form than what might actually be going on in the。

But they represent population features in relationships and the models help us by imposing structure on the population。

 so we might for example， assume that things are linearly related to each other we don't necessarily know that but it helps us to simplify kind of how we think about two different variables in the population and the important thing to realize and this is a well-worn saying in the field of statistics is that all models are wrong。

 but some are useful so it's important not to get hung up and finding the right model。

 but rather to focus on developing a model that's actually useful to help you tell your story about the population。

So。It might be useful to start at this point， which I think it was to ask， know。

 what's it like to have no model at all Okay so that way you get a sense of how bad things could be or how difficult it might be。

 if you didn't ever use a model， Okay so just take this as as a basic example。

 supposeupp you're developing a new product。 and you want to know how much people will be willing to pay for this new product so something you might do is just put out a simple survey。

 you might survey 20 people that maybe a representative of the group of people who would be willing to the larger population of people that would be willing to buy this product and ask them how much they'd be willing to pay And so you do the survey。

 and then someone comes at you and say okay， well， what did the data say Okay what did they tell us now so as an example I recently published a book called our Program for data science and before it was published on the website people could you could ask people to put their names their email addresses and ask them how much they'd be willing to pay for this book before it goes on sale And so here's what the。

To look like。So these are 20 numbers from from the survey that was put out on the website about my book。

 Okay so this is life without a model。 Okay， the answer to， you know， what did the data tell us。

 it's in here somewhere because this is the data that has to be in here somewhere。

 But the problem is so this there's no model to help us think about the data。

 So this is what I would call the trivial model meaning that there's no model。

 Okay and the problem is the trivial model is not useful because it doesn't provide any summary or any data reduction。

 Okay so put it this way if all models are going to be wrong you might as well try to find something that's useful rather than have no model at all that's almost certainly not going to be useful。



![](img/9b3c60f05312a4c9d0b3b15668b78387_3.png)

Allright， so just for the sake of example， let's use the normal model right So the normal model comes is based on the normal distribution and it's the familiar bell curve that we've seen many。

 many times okay the nice thing about the normal model is that it only requires two parameters to estimate there's the mean in the standard deviation and we can estimate that from the data by just calculating the mean in the standard deviation in the usual way so the first question we want to ask is what do we expect to see if the population we're truly coming from a normal distribution。

 what would that look like okay and it's always important to set expectations for models so I know it's it's very kind of tempting to kind get right into the data and see what they look like but you got to be able to set your expectations appropriately so that you know whether youre right or wrong in the end so here's what we would expect the data to look like if they were drawn from as representative sample from the population that was governed by a normal distribution。

 So here's the normal curve it probably looks very familiar to you now models are very useful because they can tell us a lot of different things about the population。

😊。

![](img/9b3c60f05312a4c9d0b3b15668b78387_5.png)

For example， this model， the normal model says that 68% of the population of readers would be willing to pay between $6。

81 and $27。59。 Okay， how do we know that， Because that's what the normal distribution based on this data tells us about the population but we can use the model to compute other quantities。

 too， for example， we might want to know well， how many people would be willing to pay more than 30。

 Okay so we can can we can use the normal distribution say that 11% of the population would be willing to pay more than 30 Okay so that's useful to know now the one thing about this picture that you have to just remember is that there is no data in this picture。

 now we use the data to draw the picture because we use the data to calculate the mean in the standard deviation。

 but there's no actual data in this picture。 so just keep that in mind。



![](img/9b3c60f05312a4c9d0b3b15668b78387_7.png)

Now， so but eventually we'll look at the data and we want to know how that data matches our expectation。

 which is what this picture is giving us。Now， before we actually get to the data。

 one of the things I just want to do is to show you what would data look like if it came from a normal distribution。

 Okay， now the nice thing about most software packages now is that we can just simulate data from a normal distribution and see what it looks like。

 So here's what that picture looks like。 I've made a histogram of 20 data points that come from exactly a normal distribution。

 and I plotted the theoretical normal curve over it。

 You can see that the histogram and the blue curve match very nicely with each other。

 This is all very nice and it's of ideal because it's simulated。

 so this is what I call drawing a fake picture。 Okay drawing a fake picture。

 I find to be terribly useful because it really helps to set expectations。

 and sometimes it's okay to even literally just draw it with your hand。

 You don't have to necessarily use a computer。 but draw a fake picture of what you're expecting to see with the actual data。

 Okay so this is what normal data looks like。 If we see a histogram that kind of looks like this。

 we might think， okay， a normal distribution is a pretty reasonable approximation。😊，For the data set。

 Okay so it's probably now one thing we can see from the fake picture is that the normal distribution probably isn't going to be perfect from the get over because particularly you can see in the left hand side there。

 that there are negative values Okay and it doesn't seem plausible that people would be willing to pay negative dollars for this book。

 And so maybe that's probably not the best model， but it may be still useful。

 remember no model is going to be right， but it may actually still be useful for helping us summarize the data。

Okay， so here's what the data actually look like okay I've got a histogram of all of the data points that were from the survey that's these 20 data points and I've overlaid with the blue curve of the normal distribution that's fitted to the data okay so you have to ask yourself how does the data match up with this normal distribution with this model okay now given what we've seen before with the theoretical normal curve with the fake data and the fake picture that we showed。

 how does this picture compare to the fake picture okay now？😊。



![](img/9b3c60f05312a4c9d0b3b15668b78387_9.png)

You might think it probably it doesn't look that good actually， right？

 So what's wrong with this picture。 Well， you got this huge spike in the histogram at around $10。

 Okay that's not predicted by the model。 The normal distribution doesn't have a huge spike right there。

 And furthermore， there are no values that are like either close to your or negative whereas the normal distribution has all these negative values in its functional form。

 so it doesn't look like the histogram really fits that well。

 And so what are we gonna do about that right so there may be multiple problems。

 There may be multiple explanations for why the histogram from the data doesn't look like what we' expect from a normal distribution。

 for starters， the data the data may not even be representative of the population。

 This is just a website that was up there and anyone who just happened to come by could fill in their name and say what price they'd be willing to pay。

 Who knows who these people were who knows if they were even prospective customers。

 people whod actually buy the product So the data collection process might have been very skewed We have have no real way。

😊。

![](img/9b3c60f05312a4c9d0b3b15668b78387_11.png)

![](img/9b3c60f05312a4c9d0b3b15668b78387_12.png)

Of knowing that。 But the other hand， it could be that the model clearly just does not fit well and we may need to revise the model too。

 and it may be easier in some circumstances to revise the models than to revise the data。

 especially if the data collection process was very expensive so one of the things we can do is let's try the gamma distribution。

 Okay so the gamma distribution is another model and one of this key features is that it only allows for positive values。

 So unlike the normal which has negative and positive values。

 the gamma distribution only allows positive values。

 so then we can just repeat all the steps that we just went right there we can set expectations。

 we can draw a fake picture and then we can compare our expectations to the data。

 Okay so I'll skip the first two steps there。 and I'll just show you。

 here's what the picture looks like with the data and the gamma distribution that's fitted on top of it。

 so you can see from this picture that fits not perfect either。

 okay you could argue it's a little bit better。 you've got like a little hump where that spike at 10 is but it's not it doesn't exactly fit it perfectly。

And still you have a bunch of the curve is kind of covering values where there's no data's between the kind of zero and five range。

 now but the important thing is that we have a different model and so a different model is going to yield different predictions so this model is telling us something completely different about the population then the normal model was so the normal model told us there was going to be a big hump kind of around 20 but this model tells us that the hums more like around between 7 and 10 so the model is telling us something very different about what the population is willing to pay for this product。

 for example， before we said that 11% of people would be willing to pay more than $30。 however。

 if we use the gamma model we find that only 7% of people would be willing to pay more than 30 So the importance of using models。

 different types of models is that they tell you very different things about the population and they result in very different predictions and so if you're interested in making these predictions and being accurate about them you want to make sure。



![](img/9b3c60f05312a4c9d0b3b15668b78387_14.png)

You have a model that's reasonably a reasonable approximation of the population and you can use the data to help you see if that fits well。

 So now we've looked at two different types of models to kind of tell us about our data and to tell us about the population so now you may want to keep continue to refine this。

 think about different models， obviously this last one didn't really fit perfectly So you might want to either refine your model or you might want to do another survey to kind of get more data to get a better sense and so you can kind of think about where to go from here。

 but the point of this whole exercise is that you get a little sketch of kind of what where you're going go and kind what your solution is going to be if your question was originally how much are willing are people willing to pay for this product you have a better sense now in terms of what the shape of that distribution might look like and what the population might be willing to do from here where you go it depends。

 you may have enough information as it is to kind set prices or to figure out how your。



![](img/9b3c60f05312a4c9d0b3b15668b78387_16.png)

marketketing campaign is going to go or you might want to go into more formal modeling so you can test the sensitivity of your assumptions of your expectations to various features so that's what we'll talk about more and we talk about formal modeling。

