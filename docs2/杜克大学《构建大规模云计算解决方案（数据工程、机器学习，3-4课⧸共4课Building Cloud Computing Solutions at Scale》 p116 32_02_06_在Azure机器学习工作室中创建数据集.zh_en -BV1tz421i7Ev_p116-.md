# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p116 32_02_06_在Azure机器学习工作室中创建数据集.zh_en -BV1tz421i7Ev_p116-

![](img/4fd3e789d88251fee2512a75206f788c_0.png)

The first thing that we will need here to do machine learning in an automated fashion。

 that is automl what what are the core concepts of automl with Azure machine learning studio is we need a data set。

 but you sometimes this these requirements are kind of like obscure or kind of like abstract it away via the interface。

 And so let's go step by step， I think it's really useful to just go through and plow through all of these options and see where we'll land。

 what do we need and take it from there。 So I'm coming here like without any anything previously set up and I'm going to click auto automated ML Like I've already mentioned。

You can start an auto autoM run either from here on the author， on the left， on automated ML。

 I can create new auto ML run。And or start now here on the automated M Auto train and tunening model using a target metric。

 So you have basically three things that you can click all of these three things will land you on the same thing。

 I tend to just click here an automated M and then click new new automated M run again， if I go back。

 you have a bunch of different things。 I have a bunch of different things。 This is also pretty neat。

 you have documentation going on here。 What is automated M and how to create your first classification model。

 So you have a lot of good resources here。 you can feel free to click those and dive deeper into what is going on there。

 So we want to create a new automated M run， but we don't have a data set。

 I want to create a dataset set so。There's different ways to create a data set。

 You can have it from local files， from a data store from web files or from open data sets。

 Let's click open data sets。And see what we can find。

I really like how easy they make it because you can just from here， let's， let's take a look。

 I think housing。Housing is， yeah， employment is a good one。 employment。 So。

 so you start typing in a bunch of different data sets start coming up。

 I think I did one with marketing， well。How about bank， Well， somewhat limited。 we can。

 we can do employment。 Let's try employment。So we do employment， we do this one。that data setname。

 and employment。How about we do open employment and really interesting。

 they already slap a number one two dataset set version。

 This is interesting because if you alter this dataset set in any shape or form and you want to keep track of those changes then you can say hey。

 data set version number two and that that would work so。

I think this is kind of buggy because like I'm I'm starting an automated automated MLl run and said。

 hey， do you want to create a data set， Yes， I want to I create one from open data sets and now it is here so I can click there and click next。

 So that's one。 but you may have already some sort of dataset you want to use you can use from local files in which case if I click here or pop open。

A well， they prompts me for for information and a description， but well look at that， it doesn't。

It doesn't want me to go back， but I'm gonna unclick this one。

 I want to show you like a couple of different things that you can do here。

 I personally like the one。 but from local files is is is pretty self explanatory。

 you can upload stuff that is already present on your system。 you select it。 you give it a name。

 a description。 enough you go， but I want to use from web files， Web files。

 I think it's it's an interesting thing。 this might already be hosted somewhere。

 It might be in a Github repository somewhere。It gives you even an example here， example CSP。

 so I happen to have a GiHub repository。This GiHub repository is。Is right here on this tab。

 Let's let's make this a little bit bigger so you can， we can， we can see there what's going on。

 So it's the pramatic AI labs。Account， so。PA IM L slash wine ratings。

 and I happen to have this one over here。 It's called wine ratings from two months ago。

 So the link is over there。 if if I click on it， the GiHub user interface will say whoa。

 this is this is too large 12 mebytes we're not going to show you what the deal is。

What I really need is I don't need to really see the details of the CSP if I click here。

I w to see the the the actual blob， the raw blob。 So if I click in here， like there's a lot of stuff。

 But what I'm interested in is this guy right there。 Alright， so I've I've selected。

 I selected that wine rating CSB。 and I'm gonna go back to Aher machinechine learning studio。

 I'm gonna put this thing here。 That's the full link to my CSB file。

 This link can be anything that points to an actual data set。 and I'm gonna say。嗯。

I'm going to say Github data set wine ratings。 Again。

 it's useful to know that the dataset set version is automatically set one data set type， of course。

 I can it accept tab， let's take a look you know， you paring oops parsing parsing a data set like so materialize the data into pandas or spark data frame。

 This is really neat So I'm gonna say demo wine ratings data set from a。Public Github repo。

I'm not going to skip data validation。 so you can see what happens next。

 This is somewhat different from the open data sets that are that we imported just a second ago。

 So I'm gonna click next。 The description is always a。

Alls you to go back and see what the deal is about this data and and be able to recognize what is going on with that data in particular。

 So I'm gonna to click next。Alright， so it pares the data setting for this is because I didn't skip。

I didn't skip the validation。 So now we're getting into like the nitty grity details of the dataset。

 So I know for a fact， this is a the limited dataset set。

 that is this is a CSBA comma separated value file format。

 So I know it's the limited and it's separated by commas codinging is UTfaA。

 that's fine column heaters where well I know there's heaters。

 So you can you can actually set different datas and combine them this is just one files I'm gonna use use heaters from the first file and now look at that。

 So now I know it name grape and and region that's pretty useful。 skip rows。 Well。

 I don't need to skip any rows。 but if you needed to skip some rows， you could do that here。

 I'm gonna click next。😊，All right。There's a bunch of things that I don't need here。 This is really。

 really useful。 Azure Machine learning studio has gone and analyzed my data set。

 It will calm name and properties and types。 And look at this it kind of like gives you like a sample of like what it would find。

 it doesn't find anything for a grape。 I think this that's not going that well。

 So I'm just going going to drop it。 So。This， this is lighter here allows you to include it or drop it。

 column1 is the index that was generated by pandas， I think when I was parsing the CSB。

 So I'm gonna omit that grape is basically garbage at this point because I'm getting a bunch of nulls。

 This is entirely optional。 You can play around with this like not a a said un done kind of thing。

 you can back and and make this change。 So I'm gonna drop grape。Everything else seems pretty fine。

 We have strings and decimals and integers。 that looks okay I I click next。Alright。

 so it basically wants a confirmation setting like， hey， like this is the name。

 this is the this is the URL where this thing came from。 It's a comma separator value。

 the limited UTFA you heard from first， basically all of the stuff that we selected perfect。

 This looks okay。And。Paad and creates that so we've created a couple of data sets and I think we're getting closer to starting this automl run。

 we'll see what we need to do next， but so far pretty useful understanding the different ways and offerings that machine learning。

 the Aher machine learning studio offers so that you can create a data and play around with the different options。



![](img/4fd3e789d88251fee2512a75206f788c_2.png)

![](img/4fd3e789d88251fee2512a75206f788c_3.png)