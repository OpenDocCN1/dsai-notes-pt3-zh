# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p104 20_02_05_无代码低代码自动机器学习第1部分.zh_en -BV1tz421i7Ev_p104-

![](img/870d5d5b9f0129ecad6036d31267de4a_0.png)

So let's take a maybe step by step。 Let me show you some of the things that you can do。

 and even I guess what I could do。

![](img/870d5d5b9f0129ecad6036d31267de4a_2.png)

Is is put。Inside of here。At the very beginning， I can put a section called resources， let's do this。

 we'll go through here and we'll call this resources。Be business intelligence。Data science resources。

For low code。No codes。So so step one， so I guess we can， yeah， we can use our。

We can use our notebook to take notes here。 So， so step one would be， let's look at Apple here。

Maybe I'll just do a section here that says。Apple， so what do they have that's interesting。

 I think one of the things that's very interesting about Apple。Is they have something called Cate ML。

And， and create ML L allows you to。Create machine learning models with low code or almost no code。

 And here's a picture of this is that they have a system that will accept images and allow you to create a model。

And so how does this work， this is really the feedback loop here as you ingest the data。

 like I talked about you do the training and you do an evaluation。

 so it's the same type of workflow and so let me just put a note here in this notebook we can say create a email。

To say crreed。Iel。And put a link here。Like this， okay。

 so we got we got C a Mill in there and what is it， why do we care about C Mill？

Especially if you into a low code， no code solution， well let's look at this。

 creating an image classifier model。What happens with an image classifier， We know high level。

You can train a classifier to give it many examples like an elephant， a giffe。Whatever。

And tell it to recognize the differences between those images。

So what's nice about this approach here is they only need about 10 images。

 but a little bit more could be helpful per category you put your data into a folder just like this and then。

Once you've collected that data and maybe even I can take a picture of this and we'll say。

Copy image address， notice that I can in my report， which is kind of neat is I can click this link。

Actually， click。This。And I can actually make this into a picture。

That if I was doing research for a company， I think it's。Like this。 we actually let me see。

 I think it was， I thought it was this。There was， there was a way to do the link。Of a picture here。

 But I think it's something like。This， maybe is that how do it。Or is it like this。If I。

 for some reason， I can't figure out the， I'll just do this。 Let's see， mark down link。



![](img/870d5d5b9f0129ecad6036d31267de4a_4.png)

Mark down image link。What is it again， you do。

![](img/870d5d5b9f0129ecad6036d31267de4a_6.png)

This。I'm so lazy， I can't even。Put this in here， so I'll just do this。

And then I will put in the path to that image。Here， which is。This， I believe。Does that work。Anyway。

 I'll fix that later we'll just keep this link in here for now。

 but basically that the core idea is that you want to organize your。

You're testing data into a directory structure。Put it into a project like this， image classification。

Choose the options for your new project。And then go through and drag that into this Gui， right。

 So again， no no code at all。 You're not there's no code that you're writing。

 You're just creating your images。Into a directory dropping in here。

 and then you have in this particular situation， the ability to add noise， blur， cropping， etc。

You then have some testing data， so this after you train it。

 you want to make sure that works right so you put the testing data inside。

After you're done with this。You can again， as I mentioned。

 add some some parameters to maybe enhance the data a lot of times when you're。

When you're doing a computer vision problem， you don't have enough data so you can select augmentation。

 which will allow you to get more data because you can flip damage and rotate it and do things like that。

Once you train it， it'll go through and give you results。

We don't have time to get into all the details here。

 this is something I would recommend trying on your own。

 but the core idea here is that you can use a lowcode nocode tool and come up with something that helps you do your business intelligence report。

 so maybe it's that you want to analyze competitor' product images and you want to train a classifier to detect。

Anytime you see a competing product。 And so you can go to a store and you train a classifier and you can take pictures of the products。

 And then you see， oh， this is a competitor's product is in the store。 So。

 so we need to investigate what this what this competitor's product is。 as just one example。

 So that's we'll just go through this step by step。 So we got。Apple here， that was one。

Who's next year we got？Let's go to。Let's just do this for links here。

And then we'll add another company。

![](img/870d5d5b9f0129ecad6036d31267de4a_8.png)

And I think we had。GCP， okay， so let's go to GCP next year。Under GCP。



![](img/870d5d5b9f0129ecad6036d31267de4a_10.png)

嗯。So that Google， there's a lot of powerful stuff that you can use。And let's start here with。

GCP console。And I think probably auto。OttoML might be one of the more interesting ones to。

 there's two forms of AutoML that I think business intelligence people would want to know about。

The first one would be Autoil table or AutoL vision。In Auto vision。呃。Here's an example of it。

 the way it works is。That you。Upload data into their cloud platform。Make a solid bear。In this case。

 I would say new data set。And you decide， just like the Apple example。

 I want to predict a particular label like one label， or I want to do multila classification。

 predict all the correct labels， or I want to do object detection。Once you let's just select that。

 for example。嗯。All you need to do is either upload the images or select a CSV file。

That points to those images that you put in cloud storage， so you just again。

 don't have to write any code， just drop it into the cloud storage。Say what the name of that file is。

 it's a cat， it's a dog， whatever the label is that you want to detect。

 maybe make this a little bit bigger Once you do that you go your data set it we go back here it will show up it'll be visualized and you can look through and filter and see the different pieces of data and analyze them and prepare your report。

And then you click on this train button and again， no code lowcode， just click train model。

 it'll train it， and then it'll come up with a result that looks like this where you will get a bunch of metrics that show you even if you're not an expert in machine learning what's happening and this is fairly easy to understand this confusion matrix is that it shows you when it was correct。

 if it's in blue， that's its accuracy and then these other sections are when it was misclassified and again。

 I can even look at each of these and it will visually show me when it was correct。

 the true positive when it was false negative， So it should have predicted it。

 but it didn't and then false positives right so and then later if I wanted to be also lowcode no code。

I can export this model。And make it run on a mobile device， right？

Maybe I'll just put a link to that here。And we'll say。Out mail。Vision there weve got a link to this。

What else can you do with the GCP platform？That's low code， no code。I've done this with MBA students。



![](img/870d5d5b9f0129ecad6036d31267de4a_12.png)

Is AutoM tables is another one that's pretty interesting so you can take tabular data。

 which is something you'll get all the time as a business professional。And with tabular data。

You can go through and upload it as well。 So I'll just show you real quick， how you would upload it。

 So I say new data set。We create a new data set。You could either import it from the Google BigQu system。

 which I'll show you briefly。Which allows you to。Do ad hoc queries on data inside of a console。

 you can upload it。From a CV file in cloud storage or upload， just take a file off your computer。

 upload it。 Now， what is， what does it do， Well， Well， this is， I think。

 the future of machine learning and why I think it is。

It'sOkay to not be an expert in software engineering if we look at a data set like this。

You ingest this data。And it shows you。All of the key things that you would need。 If I go to。

 let's go back to。There we go if I go through here。

 it shows me all of the attributes that are in my dataset sets of all the columns in a spreadsheet。

It will infer the type correctly。 So Autol will go through here and find out the numerical types。

 the categorical types， the text types。 it will even show through you know。

 basically descriptive statistics， like how many values are unique， etc cetera， and also。

If I click here， I think I can scroll。Over a little bit。That it will also show you the correlation。

 right， so this is something that is called feature engineering。

I can see that certain types have higher correlation with the target than I'm going to try to predict。

 So really the only thing I need to do。Is， is maybe look at this to make sure that。

Everything is correct in terms of the data types。And then， also。Select what I want to predict。

 I want to predict whether someone will be married or not。

 or I want to predict what their income level is or whatever， whatever I'm trying to predict。

 once I predict this， then I go to evaluation。And I look at the metrics here and I can see exactly。

The accuracy， so in this case， this is 83% accuracy or area under the curve for precision recall curve。

And then。I can also go down as well， look at the confusion matrix， what was it good at predicting。

 so it's pretty good at predicting whether you won't make a lot of money， it's less good， it's okay。

 but it's less good at predicting whether you'll be greater than 50，000。

But we can see here the feature importance right， so this is again。

 for a business professional maybe maybe yeah， maybe what I do here。Is I just。Do this。

 I take a picture of this。 Actually， Does it let me download this。



![](img/870d5d5b9f0129ecad6036d31267de4a_14.png)

Oh thats it gives me the well actually， yeah， this is pretty interesting， I can just download this。



![](img/870d5d5b9f0129ecad6036d31267de4a_16.png)

And then I can put this into my report so let's go through here and in fact， again。

 I don't even have to write any code， I just say add file， upload some of my code here。

 feature importance。

![](img/870d5d5b9f0129ecad6036d31267de4a_18.png)

Let's put this inside of here。

![](img/870d5d5b9f0129ecad6036d31267de4a_20.png)

Comit this change。And now I can put this link， and if you click on this。

 you can see the different features。And I even if I wanted to。

 could cheat a little bit and write a little bit of code。And so I could ingestion here， I could say。

嗯。Import pandas。S PD and say， DF is equal to。PD。readcsv and put that path in。

And then say Df dot head。I don't know，20。 I don't know how many rows there are。And so I've。

 I've actually got a little bit of raw data that I could look at， right in my， in my report。

 So it looks a little bit technical。 So， so I have some。And also， by the way， if I go back to this。

 I could， this is what I was going to show you earlier is if I do a screen cap。

I could actually do this。I could put this into my report。Without writing any code。

 just take a screen capture。Go to this project here。Create an issue。And say， new issue。Images。



![](img/870d5d5b9f0129ecad6036d31267de4a_22.png)

And then I like to just drag in a screen shot like this。



![](img/870d5d5b9f0129ecad6036d31267de4a_24.png)

And it， and it creates the URL for me。 That's what I was missing。

 And I'm so lazy that I don't want to do any work。 That's I I， I actually like no code， low code。

 And here we go。And I go to this and then maybe I put this under my exploratory data analysis picture。

 right， here we go。We got some exploratory data analysis。And then I say return。

Siff return and now now we actually have a nice graph and I didn't even make it right somebody else made the graph for me and I have a good feature analysis and I could say here。

These。Are some important features。You can see this data。Yin。This raw data。Can be。Ingests。Section。

Right。So I'm kind of building up this portfolio and then again。

 if I want to save this and I want to let other people see this。

 I can just go again to save a copy in GiHub。Go back to my。Report。Here。😔，And put it into business。



![](img/870d5d5b9f0129ecad6036d31267de4a_26.png)

Report。And check it in。And also， if I want to give you a copy to all this， can you can get a copy。

As well。 So I'll go through here。And put this into chat。I well。And just throw this in， there you go。

Okay， so so now that I。Actually， we should do this， this whole repo。Do this。

So so now that I've got this this whole report created again。

 this all the technical details are kind of hidden in here and maybe later I'll tease these out。

 but let keep let's keep moving so this is great right can I can do this with GCP。Autooml。

 but but what else， what else can I do and what are some other companies that I can use their tools well。



![](img/870d5d5b9f0129ecad6036d31267de4a_28.png)

If we look back here， what do we have next， we have AWS， okay， let's go to AWS next year。

 let's take some of their skills。

![](img/870d5d5b9f0129ecad6036d31267de4a_30.png)

So AWS has a lot of stuff that you can use。And it's amazing actually how many services they have。

And one of the first ones that we can log into here with。



![](img/870d5d5b9f0129ecad6036d31267de4a_32.png)

Is potentially the。Let's start with NLP。So with NlP， the main service。

That you can use is this comprehend service。And。If I click on launch comprehend。

 you can see we'll be able to do some NLP， which I'll do in a second。

 but I also wanted to show a different comprehend there's two forms of AWS comprehend。

 there's text based and there's also a comprehend medical。

So depending on what problem you're solving， you could launch a different one。

 the reason I wanted to show this is let's say you're working for a medical company。

You could actually just paste a medical record for somebody in your company again。

 not writing any code。Here's one， this is their medical record like this。And we say， analyze。

And inside of this， you can see all of the different text， so visually now we've created a report。

And I can take this report and I can give it to the doctor or to maybe the CFO of the company and say。

 oh oh， we have some really important facts here that we need to analyze and what I could do is maybe minimize this。

And take a picture， for example， of this particular output。Let's see here what's a good one to show？

Let's take this。Here's the， here's a good chart。And I could again， take a screenshot。And， and maybe。

I think yeah， it's just this good screenshot。 Okay， good。

 I got the screenshot and we'll go again back to。This repo， go to my issue here。Go to images。



![](img/870d5d5b9f0129ecad6036d31267de4a_34.png)

And put another one inside， so we'll take this new screenshot。



![](img/870d5d5b9f0129ecad6036d31267de4a_36.png)

And we'll throw that in。Great。So， now we have some， some details。

That we can put into our technical report。So we have another detail here。let's go through here。

We'll say。Maybe another section and we'll say this is a medical record。Paste that in。

Now we've got another chart。Right。But let's go back to the regular。Comprehend real quick and again。

One of the main ways to probably do this would be。To。

 let's say I was going to do research on a competitor。 right。

 This is a very business centric approach。 So I would probably start with Wikipedia is is a good source for doing research。



![](img/870d5d5b9f0129ecad6036d31267de4a_38.png)

![](img/870d5d5b9f0129ecad6036d31267de4a_39.png)

And let's say it was Nike， right， I want， I want to know what。Let's say I'm a shoe manufacturer。

And I want to see what。What I can learn very quickly so I can give this report to somebody in my company。

So I'm going to take maybe the first section here。And I'm going to copy it。

And then I will go to this input text here and just paste it in just like this。

And I'm going to say analyze the text and what it will show me is all of the entities inside。

 but I also can go through and find key phrases。Right。And I also could find syntax or sentiment。

And we can see that in fact， there maybe。One thing that I would want to look at is the sentiment。

 and in fact。What could be important here would be that。If it's a journal article。

 it should probably be。Neutral， but we see that this is actually a little bit positive。

 which is interesting so so I can then maybe look further and say I want to do some research。



![](img/870d5d5b9f0129ecad6036d31267de4a_41.png)

And what if I said？I look for news about Nike， so I go to let's say Google News or something like this and I type in Nike。



![](img/870d5d5b9f0129ecad6036d31267de4a_43.png)

So let's look at Nike here。And we find some news about Nike。

 and I want to see what my competitor is doing。And I want to see if people are writing good things about them or bad things。

Here we go， I'll copy this and I go back to this business analytics section。Or comprehend。

 analyze this。And I look at the sentiment。And I see that also， this is this is neutral。

 So it looks like。It looks like a lot of people are writing neutral articles about it。

 but maybe maybe I can find another article。Here's another one。

' let's just analyze a few and I can do this very quickly with because I don't because I'm not。

Writing code。I can do this very quickly， right， I just cut and paste。

And I just do some very quick research， let's see here。Yeah， this looks like a good one to analyze。

Sentiment here， same， pretty neutral。 So it looks like maybe， maybe this competitor。

People aren't writing very， very positive or very， very negative。 They're， they're more of a neutral。

 And， and maybe even I just go like this。 and I say， I did a little bit of analysis。

 and it looks like。A lot of content around Nike。It's pretty neutral， right？

That that's my initial findings for using these off the shelf。NLP tools。So again， go through here。

 let's add another section。It will say， you， Nike research。And paste this in。All right。

But what else can you do with？The Google。I'm sorry， AWS， well。

 there's a lot of other stuff we can do with AWS。 one thing you can do is they also have their they have some computer vision tools and one of them that's pretty interesting is recognition。

And with recognition。You can actually do lots of different computer vision tasks without needing to write any code at all。

 and here's one that could be pretty useful for， let's say we're still analyzing Nike。

Is if I go to text and images here， what I could do is I could go back to this article and I could just see。

 again， maybe I want to start looking at what kind of things my competitor is putting。

Into their product， well I can go here， and I can save a picture of this。I can go to recognition。



![](img/870d5d5b9f0129ecad6036d31267de4a_45.png)

I can upload it。Put it。

![](img/870d5d5b9f0129ecad6036d31267de4a_47.png)

Into this section。And and here we go。 so I didn't know this。 I couldn't read that。

 So now I know that this in fact has the word fees。 so maybe that's a new feature。

 So maybe this is something that we should start looking into right and in fact I I can grab this if I wanted to or this is probably the English version it's probably easy enough。

And maybe even I take a picture of the whole thing。

 so I could just take a picture of this and just say， okay， look。

 we're detecting that Nike has something called fees。

Maybe we need to to do a little more research on Nike to see if if we can figure out what they're up to。

 So let's add some more， we'll say computer vision。Research。For Nike。



![](img/870d5d5b9f0129ecad6036d31267de4a_49.png)

Here we go。And again， take a picture of this。And I think it was this screenshot。



![](img/870d5d5b9f0129ecad6036d31267de4a_51.png)

Here。😔，Let's double check。Actually， I can put it。Into the images， that's the better way to do it。

Comments。😔。

![](img/870d5d5b9f0129ecad6036d31267de4a_53.png)

![](img/870d5d5b9f0129ecad6036d31267de4a_54.png)

W。It's that's too big。 doesn'。 It doesn't like that picture。 It's too big。 So Ill。

 I'll just make it a little bit smaller。 We'll just do this。Let's make it smaller。Go back to images。



![](img/870d5d5b9f0129ecad6036d31267de4a_56.png)

Here。😔。

![](img/870d5d5b9f0129ecad6036d31267de4a_58.png)

And。There we go。Comment， put this in， there you go， got some computer vision research for Nike。

Refresh this。This collab notebook is struggling for some reason。Maybe what I'll do is go。Back here。

And。Not sure why this thing has got， got problems， exit。Okay， so。Here's my computer vision。

Research and pace in。All right。So so we can do like text recognition， you know， label recognition。

 scene detection， all kinds of stuff， like also I guess I could take that same picture。



![](img/870d5d5b9f0129ecad6036d31267de4a_60.png)

![](img/870d5d5b9f0129ecad6036d31267de4a_61.png)

And go through here。Do research and see information about it。And again， maybe。Maybe I。

 this is all I need to do is is just take a picture like this it says， okay， here's what I found out。

They're making footwear， it's a running shoe， it's a sneaker， and it's got the word fees in it。

 right or flies or something like that。And we go through here and do that。



![](img/870d5d5b9f0129ecad6036d31267de4a_63.png)

So the other thing， though， that you can do。

![](img/870d5d5b9f0129ecad6036d31267de4a_65.png)

With。With I think that's what I would screw up is is you put it into。I think the problem is。

Is that I want to put this into。Into the images section first。Or else it gets too overloaded。

So you let Google， I'm sorry， Gitthub do the hosting。Like this， okay。That's probably good enough。

 I have enough of these pictures。For my research， there we go。

 So we now we have additional information。 So what else can can AWS do Well。

 another thing that AWS can do。Is it also has that tabular data science right so we can go through here and we can go to a service called machinech learning。

And this machine learning service。Also allows you to ingest。Tabular data。

And the way this works is you put the data。Into Amazon first。And then you tell it to do an analysis。

And so if I go to Amazon machine learning and I say create new data sourceur and model。Pieces in。

Here's a location to the data， and I call this banking data。And I verify it。

 it does that same process it goes through and it looks at this data。And then。

 if I say yes for the column names in the first line。It will allow me to accept。This data。

 and then if I go to next， it'll ask me to， what do I want to predict？

which is the whole point of putting in here and if I go to the last section here。

 there's a target value， which is I want to predict whether they deposit money in my bank or don't this is banking customer data if I click yes and I click continue。

Itllll prompt me to to make some choices。 I just keep clicking continue。

And it'll say basically generate a machine learning model that does a prediction whether these customers will deposit money or not deposit money。

 I click review。And it will go through and it will train the model。 That's it。

 So I just upload some data， select the columns， select the thing I want to predict and it'll train the model and so what does it look like at the end is if I go to an end result。

Is that it will show me。The metric， just like with Google。And I also could。

Look at the evaluation results and dig in deeper so we can see that this is area under the curve and I could explore the performance and do trade offs as well and then save that threshold and then maybe give this to somebody else with again zero code zero code to do this prediction。

So let's go through another service on AWS we also have。Quickite， and so quick site。

What's great about QuicksSa？Is that it also has this low code。

 no code feel to it where you can just upload data sets。 And I think I have this。Data。

 I have some data that I just downloaded， so I'm going to say a new analysis。New data set。

And I'm going to upload a file note。Also， if if I'm working at an existing company。

 maybe they have the data in Salesforce or they have it in。

Spark or Jra or GitHub or something like this， but in my case I'll just upload the data。

 go to feature importance， take that data in here。

![](img/870d5d5b9f0129ecad6036d31267de4a_67.png)

![](img/870d5d5b9f0129ecad6036d31267de4a_68.png)

And it will give me a preview that shows me the columns and then what the values are。I go next。

And then I visualize。And and from here， I could then decide what kind of things I would want to chart。

 I think in this case， itll create some kind of a default visualization。

And show me some interesting metric。 There you go。 So so I have some， I have some kind of metrics。

 and you can play around with。Coloring and charting and all kinds of things。 and again。

 this gives me automatic insights。And it's something that I could then later share with other people in my company。

 I could click share and I could publish a dashboard。呃。Or I also could print this。 I。

 I can put this into a report。 I think I can do。A。I could put this into a PDF and then link it into GitHub or something like that。

嗯。So what's nice about these BI tools here is that again。

 it allows me to just upload the data that I pulled from some other source and this data came from some other machine learning tool so I could have many low code no code tools that I combine together。

 but let's for fun， let's just maybe even take a picture of this。Like this。

 And I think this one also， you can say。Duplicate visual。 I think there is another way to。

To actually export it as a。PDF or something。In a nutshell。

Those are some of the high level tools that you can use on AWS。



![](img/870d5d5b9f0129ecad6036d31267de4a_70.png)

![](img/870d5d5b9f0129ecad6036d31267de4a_71.png)