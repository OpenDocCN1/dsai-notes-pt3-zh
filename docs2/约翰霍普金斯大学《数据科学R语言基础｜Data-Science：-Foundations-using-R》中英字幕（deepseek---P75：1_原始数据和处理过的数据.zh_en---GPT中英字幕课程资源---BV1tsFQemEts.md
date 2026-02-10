# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P75：1_原始数据和处理过的数据.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

This lecture is about raw and process data。So I'm going to be talking a little bit about how raw data might be different。

 depending on who you're talking to， so some people might consider one version of the data raw and some people might consider another version of the data raw。



![](img/5345a522111dd6cf3a573f79de9ee19d_1.png)

So first I was going to talk about the definition of data。

 so as we saw in the data scientist toolbox， data are values of qualitative or quantitative variables belonging to a set of items。

 so the set of items might be the population or the set of objects that you might be interested in。

And the values correspond to variables， and the variables are the things that you're measuring。



![](img/5345a522111dd6cf3a573f79de9ee19d_3.png)

And you might measure them in qualitative terms or in quantitative terms。

 so usually when we think about variables， we think about things like this。

 if you look down here at the bottom， we think about country of origin。

 sex treatment and quantitative variables like height weight and blood pressure。

A lot of these measurements are actually derived from much lower level measurements。 So， for example。

 if you think about blood pressure， blood pressure is actually measured by calculating a pressure measurement。

 And so there's actually a lot of low level things that go into calculating that pressure measurement。

And so those low level things are the kinds of things that we're going to be talking about in raw versus process data。



![](img/5345a522111dd6cf3a573f79de9ee19d_5.png)

So the raw data are the original source of data， they're often very hard to use for data analyses because they're complicated or they're hard to parse or they're very hard to analyze data analysis actually includes the processing or the cleaning of the data if you go and obtain a data set that's actually a raw image file and you process it and turn it into a nice data frame that then you use to analyze an R that data processing actually is part of the data analysis or data science pipeline In fact。

 a huge component of a data scientist job is performing those sorts of processing operations。

The raw data may only need to be processed once， but regardless of how often you process it。

 you need to keep a record of all the different things that you did because it can have a major impact on the downstream analyses。

The process data is data that is ready for analysis。

 so the processing data of the data might include merging， subsetting。

 transforming or you might go into a file and extract out a part of an image or you might go into a file and extract out a little bit of text from a freeform text field。

 or you may do a number of other things。Depending on the field that you work in。

 there may be standards for processing， so for example， in the area where I work genomics。

 there are a lot of really standard preprocessing techniques that need to be applied before you can analyze data。

A critical critical component is that all steps should be recorded。

 I can't state this strongly enough， preprocessing often ends up being the most important component of a data analysis in terms of effect on the downstream data and so paying attention to all the steps that you did is critically important if you're going to be a a data scientist who's careful about understanding what's really happening in the entire data processing pipeline。



![](img/5345a522111dd6cf3a573f79de9ee19d_7.png)

So I'm going to give you one really quick example of a processing pipeline just to illustrate what I mean by there being different levels of raw data。

 so this is an illina highse machine， so what this machine can be used to do is to sequence DNA and so that sequencing is much。

 much faster now than it used to be in the past。When the original human Genome project got started。

 it took almost a decade and maybe an over billion dollars to sequence one human genome。

 and that same process can now be performed in about a week for about $10000 using a machine like this。

 So it's an example of how data are becoming more and more cheap and easier to collect。



![](img/5345a522111dd6cf3a573f79de9ee19d_9.png)

And so the way that this machine works in a very， very rough overview is you end up with you can imagine how you could start with fragments of DNA。

 so it starts with little fragments of DNA which are bound to a slide so each fragment might be 500 letters long so you can think of your DNA as a string of 3 billion letters and so you take a small chunk of that 500 letters and bind into this slide。

And then there's a chemical process by which multiple copies of that same sequence are made。

And so what ends up happening is this process is performed through sequencing by synthesis and so what happens is the complementary base or the complementary letter to each letter in the sequence that's attached to the slide is attached one at a time and each different letter AC T and G get a different color So what happens is for each little cluster。

 you get a color at every single new nucleotide that's synthesized。

 and so those colors create a series of images and so for example。

 when you're synthesizing the first nucleotide you might get this image。

 then this image at the second one and this image at the third one and so forth。

If you zoom in on one specific little dot， that corresponds to the sequence of exactly one of these little clusters of sequences that are exactly the same。

And so what you can do is you can follow along from image to image。

 you can see what the color is in that image and then that image and then that image and in that image and what you end up with is for each image the color corresponding to each letter。

 whichever one is the brightest is the one that you assign to that sequence so for example。

 in the very first letter for this particular fragment is going to be a C because you can see that of these four letters right here。

 the C is actually the highest and then in the second nucleotide you can actually see that the highest letter out of these four or the most bright letter is the G and so the next letter that we assign would be a G and so forth。

So the final thing that you end up with is something like this fastQ file that I've showed a couple of times in the class。

 so the Fast Q file is a text file where for each of these little fragments that you got on the plate。

 you actually see a specific set of letters， ACs， T's， and G's。

So you can think about the raw data being at several different steps。

 so the raw data might be these image files down here。

 so you have to process those image files in order to get these profiles here for each different fragment and then after you have the profiles。

 you have to process those in order to make predictions about which letters should go into the sequences that actually end up right here So any of these stages could be considered raw and in each of these stages there are a number of computational steps that can have a major impact that must be applied and so one thing to keep in mind when you're doing data analysis is frequently you might end up analyzing these so-called reads that come off of this machine or you might even analyze something that's downstream。

 say some counts based on adding up some of those reads。When you do that。

 you're glossing over the fact that all of these processing steps happen beforehand and so those processing steps can have a major impact and part of this course is sort of understanding what those processing steps are so you can make sure that your analysis isnt being driven by artifacts caused by the way that you go from the raw data to the Ti data so that's what getting data is all about is taking raw data and turning it into process data。



![](img/5345a522111dd6cf3a573f79de9ee19d_11.png)