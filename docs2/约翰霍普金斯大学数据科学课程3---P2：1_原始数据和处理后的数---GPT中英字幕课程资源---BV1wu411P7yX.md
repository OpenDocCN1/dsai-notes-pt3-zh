# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P2：1_原始数据和处理后的数据.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

This lecture is about raw and process data。So I'm going to be talking a little bit about how raw data might be different。

 depending on who you're talking to， so some people might consider one version of the data raw and some people might consider another version of the data raw。



![](img/b9359cd17eb29c8e6716f7532c482a83_1.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_2.png)

So first I was going to talk about the definition of data。

 so as we saw in the data scientist toolbox， data are values of qualitative or quantitative variables belonging to a set of items。

 so the set of items might be the population or the set of objects that you might be interested in。



![](img/b9359cd17eb29c8e6716f7532c482a83_4.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_5.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_6.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_7.png)

And the values correspond to variables， and the variables are the things that you're measuring。



![](img/b9359cd17eb29c8e6716f7532c482a83_9.png)

And you might measure them in qualitative terms or in quantitative terms。

 so usually when we think about variables， we think about things like this。

 if you look down here at the bottom， we think about country of origin。

 sex treatment and quantitative variables like height weight and blood pressure。



![](img/b9359cd17eb29c8e6716f7532c482a83_11.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_12.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_13.png)

A lot of these measurements are actually derived from much lower level measurements。 So， for example。

 if you think about blood pressure， blood pressure is actually measured by calculating a pressure measurement。

 And so there's actually a lot of low level things that go into calculating that pressure measurement。



![](img/b9359cd17eb29c8e6716f7532c482a83_15.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_16.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_17.png)

And so those low level things are the kinds of things that we're going to be talking about in raw versus process data。



![](img/b9359cd17eb29c8e6716f7532c482a83_19.png)

So the raw data are the original source of data， they're often very hard to use for data analyses because they're complicated or they're hard to parse or they're very hard to analyze data analysis actually includes the processing or the cleaning of the data if you go and obtain a data that's actually a raw image file and you process it and turn it into a nice data frame that then you use to analyze an R that data processing actually is part of the data analysis or data science pipeline In fact。

 a huge component of a data scientist job is performing those sorts of processing operations。



![](img/b9359cd17eb29c8e6716f7532c482a83_21.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_22.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_23.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_24.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_25.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_26.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_27.png)

The raw data may only need to be processed once， but regardless of how often you process it。

 you need to keep a record of all the different things that you did because it can have a major impact on the downstream analyses。



![](img/b9359cd17eb29c8e6716f7532c482a83_29.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_30.png)

The process data is data that is ready for analysis。

 so the processing data of the data might include merging， subsetting， transforming。

 or you might go into a file and extract out a part of an image or you might go into a file and extract out a little bit of text from a freeform text field。

 or you may do a number of other things。

![](img/b9359cd17eb29c8e6716f7532c482a83_32.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_33.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_34.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_35.png)

Depending on the field that you work in， there may be standards for processing， so for example。

 in the area where I work genomics， there are a lot of really standard preprocessing techniques that need to be applied before you can analyze data。



![](img/b9359cd17eb29c8e6716f7532c482a83_37.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_38.png)

A critical critical component is that all steps should be recorded。

 I can't state this strongly enough， preprocessing often ends up being the most important component of a data analysis in terms of effect on the downstream data and so paying attention to all the steps that you did is critically important if you're going to be a data scientist who's careful about understanding what's really happening in the entire data processing pipeline。



![](img/b9359cd17eb29c8e6716f7532c482a83_40.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_41.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_42.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_43.png)

So I'm going to give you one really quick example of a processing pipeline just to illustrate what I mean by there being different levels of raw data。

 so this is an illina highse machine， so what this machine can be used to do is to sequence DNA and so that sequencing is much。

 much faster now than it used to be in the past。

![](img/b9359cd17eb29c8e6716f7532c482a83_45.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_46.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_47.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_48.png)

When the original human Genome Project got started。

 it took almost a decade and maybe an over billion dollars to sequence one human genome。

 and that same process can now be performed in about a week for about $10。

000 using a machine like this。 so it's an example of how data are becoming more and more cheap and easier to collect。



![](img/b9359cd17eb29c8e6716f7532c482a83_50.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_51.png)

And so the way that this machine works in a very， very rough overview is you end up with you can imagine how you could start with fragments of DNA。

 so it starts with little fragments of DNA which are bound to a slide so each fragment might be 500 letters long so you can think of your DNA as a string of 3 billion letters and so you take a small chunk of that 500 letters and bind into this slide。



![](img/b9359cd17eb29c8e6716f7532c482a83_53.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_54.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_55.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_56.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_57.png)

And then there's a chemical process by which multiple copies of that same sequence are made。



![](img/b9359cd17eb29c8e6716f7532c482a83_59.png)

And so what ends up happening is this process is performed through sequencing by synthesis and so what happens is the complementary base or the complementary letter to each letter in the sequence that's attached to the slide is attached one at a time and each different letter AC T and G get a different color So what happens is for each little cluster。

 you get a color at every single new nucleotide that's synthesized。

 and so those colors create a series of images And so for example。

 when you're synthesizing the first nucleotide you might get this image。

 then this image at the second one and this image at the third one and so forth。



![](img/b9359cd17eb29c8e6716f7532c482a83_61.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_62.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_63.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_64.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_65.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_66.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_67.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_68.png)

If you zoom in on one specific little dot， that corresponds to the sequence of exactly one of these little clusters of sequences that are exactly the same。



![](img/b9359cd17eb29c8e6716f7532c482a83_70.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_71.png)

And so what you can do is you can follow along from image to image。

 you can see what the color is in that image and then that image and then that image and then that image and what you end up with is for each image the color corresponding to each letter。

 whichever one is the brightest is the one that you assign to that sequence so for example。

 in the very first letter for this particular fragment is going to be a C because you can see that of these four letters right here。

 the C is actually the highest and then in the second nucleotide you can actually see that the highest letter out of these four or the most bright letter is the G and so the next letter that we assign would be a G and so forth。



![](img/b9359cd17eb29c8e6716f7532c482a83_73.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_74.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_75.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_76.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_77.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_78.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_79.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_80.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_81.png)

So the final thing that you end up with is something like this fastQ file that I've showed a couple of times in the class。

 so the FastQ file is a text file where for each of these little fragments that you got on the plate。

 you actually see a specific set of letters， ACs， T's， and G's。



![](img/b9359cd17eb29c8e6716f7532c482a83_83.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_84.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_85.png)

So you can think about the raw data being at several different steps。

 so the raw data might be these image files down here。

 so you have to process those image files in order to get these profiles here for each different fragment and then after you have the profiles you have to process those in order to make predictions about which letters should go into the sequences that actually end up right here so any of these stages could be considered raw and in each of these stages there are a number of computational steps that can have a major impact that must be applied。



![](img/b9359cd17eb29c8e6716f7532c482a83_87.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_88.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_89.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_90.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_91.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_92.png)

And so one thing to keep in mind when you're doing data analysis is frequently you might end up analyzing these so-called reads that come off of this machine。

 or you might even analyze something that's downstream。

 say some counts based on adding up some of those reads。



![](img/b9359cd17eb29c8e6716f7532c482a83_94.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_95.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_96.png)

When you do that， you're glossing over the fact that all of these processing steps happen beforehand and so those processing steps can have a major impact and part of this course is sort of understanding what those processing steps are so you can make sure that your analysis isnt being driven by artifacts caused by the way that you go from the raw data to the Ti data so that's what getting data is all about is taking raw data and turning it into process data。



![](img/b9359cd17eb29c8e6716f7532c482a83_98.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_99.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_100.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_101.png)

![](img/b9359cd17eb29c8e6716f7532c482a83_102.png)