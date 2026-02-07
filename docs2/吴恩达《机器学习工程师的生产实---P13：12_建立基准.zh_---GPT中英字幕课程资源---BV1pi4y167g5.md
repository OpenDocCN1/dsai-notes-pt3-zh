# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P13：12_建立基准.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

![](img/5d8892260017f5b683172c6ec14c6281_0.png)

When starting work on a machine learning project， one of the most useful first steps to take is to establish a baseline and it's usually only after you've established a baseline level performance that you can then have tools to efficiently improve on that baseline level。

Let's dive into some best practices for quickly establishing that baseline Let me use a speech recognition example Let's say you've established that there are four major categories of speech in your data。

 clear speech which is when someone speaks without much background noise。

 speech with car noise in the background as if they were in a car when they use your speech recognition system。

 Sp with people noise in the background， so live their outdoors with other people's talking in the background or speech on a low bandwidth connection kind of what it sounds like if you are using a cell phone with a very bad cell phone connection if your accuracy on these four calories of speech is 948987。

 70% accuracy you might be tempted to say wow， it does worse on low bandwidth audio so let's focus our attention on that。

But before leaping to that conclusion， it'd be useful to establish a baseline level of performance on all four of these categories。

You can do that by asking some human transcriptionist to label your data and measuring their accuracy。

 what is human level performance on these four categorieslories of speech in this example。

We find that if we can improve our performance on clear speech。

 up to human level performance looks like there's a potential for a 1% improvement there。

If we can raise our performance up to human level performance on audio of conoids in the background。

Maybe 4% improvements。2% improvement。And。Suchly zero% improvements on low bandwidth with audio。

And so whereas we had previously said without the human level performance we may have thought working on low bandwidth audio was most promising with this analysis we realized that maybe the low bandwidth audio was so goble even people。

 humans can't recognize what was said and it may not be that fruitful to work on that instead it may be more fruitful to focus our attention on improving speech recognition with con noises in the background so in this example using humanle performance which I sometimes abbreviate to HLP human level performance gives you a point of comparison or baseline that helps you decide where to focus your efforts on con noise data rather than on low bandwidth data。

It turns out the best practices for establishing a baseline are quite different。

 depending on whether you're working on unstructured or structured data。

Unstructured data refers to data sets like images， maybe pictures of cats or audio like a speech recognition example。

 or natural language like text from restaurant reviews unstructured data tends to be data that humans are very good at interpreting in fact humans evolve to be very good at understanding images in audio。

And maybe language as well。 And because humans are so good at unstructured data tasks。

 measuring human level performance or HLP。Is often a good way to establish a baseline if you are working on unstructured data In contrast。

 structured data are the giant databases or the giant Excel spreadsheets you might have such as if you run an ecom website the data showing which user purchased what at what time and for what price that would be stored in a giant database and this type of data stored in a giant Excel spreadsheet or some more robust database would be an example of structured data or your product and inventory data that would also be stored as structured data because humans are not as good at looking at data like this to make predictions we certainly didn't evolve to look at giant spreadsheets。

Human level performance is usually a less useful baseline for structured data applications。

I find that machine learning developments best practices quite different depending on whether you're working on an unstructured data or structured data problem keeping in mind this difference。

 let's take a look at some ways to establish baselines for both of these types of problems。

We've I already talked about human level performance as a baseline。

 particularly for unstructured data problems。Another way to establish a baseline is to do a literature search for save the art or look at open source results to see what others report they are able to accomplish on this type of problem For example。

 if you' are building a speech recognition system and others report a certain level of accuracy on data that's similar to yours。

 then that may give you a starting point using open source you may also consider coming up with a quick and dirty implementation not just escape system but just a quick and dirty implementation that could start to give you a sense of what may be possible Finally if you already have a machine learning system running for your application that the performance of your previous system performance of your older system can also help you establish a baseline that you can then aspire to improve on What a baseline system or a baseline level of performance does is it helps to indicate what might be。

In some cases， such as if you're using human levelve performance。

 especially on unstructured data problems， this baseline can also give you a sense of what is the irreducible error or what is base error In other words。

 what is the best that anyone could possibly hold for in terms of performance on this problem such as helping us realize that maybe the low bandwidth audio is so bad that it's just not possible to have more than 70% accuracy as in our earlier example and by helping us to get a very rough sense of what might be possible。

 it can help us be much more efficient in terms of prioritizing what to work on Sometimes I've seen some business teams push a machine learning team to guarantee that the learning algorithm will be 80% accurate or 90% or 99% accurate before the machine learning team has even had a chance to establish a rough baseline This unfortunately puts。



![](img/5d8892260017f5b683172c6ec14c6281_2.png)

Machine learning team in a very difficult position if you are in that position I would urge you to consider pushing back and asking for time to establish a rough baseline level of performance before giving a more firm prediction about how accurate the machine learning system can eventually get to be it helps you to make your case feel you to tell them that I ask you to do so and I think establishing that baseline first will help set you and your team up better for longterm success。

😊，Now that it talks about the importance of baseline。

 there are a few additional tips I want to share with you about how to get started quickly on the machine learning project。

 let's go on to the next video to take a look at some of these tips。😊。

