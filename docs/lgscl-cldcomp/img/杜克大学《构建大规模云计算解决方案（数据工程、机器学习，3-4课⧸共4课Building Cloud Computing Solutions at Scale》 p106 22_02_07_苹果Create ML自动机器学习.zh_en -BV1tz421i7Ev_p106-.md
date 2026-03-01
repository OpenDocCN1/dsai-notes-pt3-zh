# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p106 22_02_07_苹果Create ML自动机器学习.zh_en -BV1tz421i7Ev_p106-

![](img/e66a945aec9844ed32ff6cc4924e26d2_0.png)

To get started with Apple's CM， let's look at the official documentation。

 you can find this inside of Xcode， this is a handy way to really learn about anything that's happening with the Xcode development Orment。

 and notice it says creating an image classifier model now there's other ways that you can do things with C mail as well。

 but let's take really the basic case here which is that I want to classify a different image。

 let's say a giraffe for example， this would build out something called ML model。

And this is done through an autom system that Apple gives me access to。 and to train the classifier。

 I would just need to have at least 10 different copies of the image。

 So different images of each category。 and then this is all that would need to occur to train it。

 So you can see here it says use at least 10 images per category。 And then the more data you have。

 the better it will be able to perform。 And also if there's a more diverse set of images。

 maybe multiple angles or lighting conditions， this also can help it have better performance。

 And what's great about this is that it is anything that can be。😊。

Opened by Quicktime player so it could be a JPG file。

 a P&G file and also it says it's better to use images that are at least 299 by 299 pixels so you reasonably large sized file now notice for organizing the training data here it says to prepare your training data you would need to have essentially different directories full of the labels so in this case if I wanted to have a buffalo a cheetah。

 an elephant a giraffe I would go through here and know build out a directory for each one。

And then you also can test it to see how well the model performs in the real world and you would want to have at least 25 test categories for that as well。

 and so what I'm going to do is I'm going to open up this create email project and I'm going to use a template so to do that you want to first download Xcode if you haven't downloaded it open up Xcode and then you want to right click on the icon in your doc and so this is a little bit tricky to know if you didn't read the documentation but first open up Xcode then right click on the icon in your doc and then this kind of secret menu appears under theDevelop tools option I'm not sure why they do that but maybe it's in a developing feature and you can see that there's lots of different things that you can do anything from image classification to object detection to style transfer and then you would go through name it configure the training。

Session here， which is what we're going to do and then go through and do the testing data So a really。

 really awesome tool set that Apple kind of stealthily threw into our ecosystem and we're going to use it to train a cats and dog model。

 So the first thing I'm going to do is I'm going to show you that I'm going to open up this you know data set here so I'm going to go to create a mill。

😊。

![](img/e66a945aec9844ed32ff6cc4924e26d2_2.png)

And it's gonna pop open this crL dialog box here so let's kind of make this a little bit bigger and let's see what all the different things you can do so if we say all I can do image classification。

 I can do object detection I can do style transfer action classification so this would be maybe if I was a personal trainer and I had lots of different images of clients doing activities and I want to build my own image classification thing I can do that we've got activity classification sound classification。

 text classification， word tagging tabular classification so this predicts the categorical features given another datas values and then tabular regression so this would be like a numerical prediction or even a recommendation engine so what's really awesome about this is that as a data scientist myself instead of me needed to always write code I could use this to quickly。



![](img/e66a945aec9844ed32ff6cc4924e26d2_4.png)

Prototype out new solutions， so let's go ahead and get started and build our own classification system。

Okay， now that we have an overview， let's go ahead and get started here， pick image classification。

 and let's name our project。 So I'm going to call this cats。Hyhen dogs。And this is a project。

For classifying。Dogs versus cats。fairly classic D science program problem。

 I' going to save this on my desktop。

![](img/e66a945aec9844ed32ff6cc4924e26d2_6.png)

There we go and notice that it gives us this good overview window that has pretty much everything we need in this window。

 so it's going to ask for training data it's going to ask for validation data and testing data and so it's going to again need at least 10 different examples of each set。

 so what I did is I downloaded right here， the cats and dog data set from CAgle notice that if I go ahead and open this thing up here。



![](img/e66a945aec9844ed32ff6cc4924e26d2_8.png)

Let's go through here and open this thing up。We'll go to this and we'll look inside if there's a cat and a dog directory The problem though is that this could take quite a while to train because of the size right there's you know thousands thousands of files so what I'm going to do instead is I'm going to make this a little bit bigger here。

And I'm going to create a new folder called this Cats Dos small。

 and this is what I would recommend when you're dealing with you know。

 maybe first getting started here is first start with a really small size so that you don't overwhelm yourself and then we'll build a couple different things so first。

We'll build a cat directory here， so I'm going to go ahead again and say new folder and we'll call this cat。

And then we'll make another folder and we'll call this dog and then I'll just take maybe the first 100 images。

 so 0 to 99。 There we go， grab those， copy them and put those into the cat directory so I can just literally just paste that in。

There we go and this will put this into the sc directory。

 looks like I needed to kind of move this around， which is kind of nice about Mac and using drag and drop as I can。

Take these and move them into that directory。There we go。

 so now they're in the cat directory and then I'm to need to do the same thing for the dog so I can basically go back here to this overview。

 go to dog， do the same thing 0299。Go here。Take this and either copy it and paste it in or drag and drop it。

 whatever you want to do， I'm going to double click in here and just paste it in。There we go。

 Now I also want to have a test data set here。 So what I'm going to do。

Is I'm going to say new folder and I'm going to create this called test。Caaths and dogs。Like this。

 and then we'll do the same thing aside， so I'll do as well a new directory called cat。

we'll do a new directory called Dog。Just like that， and then I can grab， let's say 100。To200。

Let's go ahead and do that。And let's copy that and let's see this is dog pictures。

 so I'll drag that in too。The dog directory。And then I'll go to the cat directory and I'll grab again。

 100 to 200。So 100 to 200。And so what the test data is going to allow us to do is just get better metrics on how well our model is able to predict things so we'll go through there。

 Okay， so we've got all the prep set set up here and I would follow a very similar pattern when you're going through and building things yourself on your own machine so let's kind of drag all these things over to the side here so we can really easily kind of look at them there we go perfect Okay so first thing I'm going to do is choose my training data here。

And I can go through here and say select files， and all I need to do is go to the cat dogg small。

 which I prepared， which has 100。Examples of each。We'll go through and say， okay。

 notice that it found two classes of 402 items total。

And it automatically will split the data into a validation data set。

 So what this means is in human language is that it takes some of the data out to make sure that when it's training the model that it's accurately able to predict inside of there and then the test set。

 we can go through here and we can click on plus and we can say test cats and dogs throw that in there。

 there we go， we've got these items and so we've got some good things inside of here。

 now another thing to point out that's a really awesome feature of this training system is that if I wanted to basically enhance the training method so that it can recognize different kinds of scenarios like for example is the image cropped a little bit or maybe like there's a little bit of noise because I got a weird image from the internet or is was blurred or whatever。

 this can still actually train the model。To do an accurate prediction by adding all these different features now the more that you go through here and you add different aspects of noise or cropping it'll take a little bit longer to train but for now let's just pick a couple noise and cropping and look for max some iterations it's going to go through and train this for 25 different iterations of a run that looks good I'm going to go to this upper button here that says train。

And again， no data science experience necessary， no coding experience necessary。

 I could be a newcomer to image classification and I'm ready to go。

 so let's go ahead and click train and now let's go through here and train this model。

 it's processing the images here。Okay and now we can see it in kind of in real time it's able to classify things correctly and look that we're able to get a precision and recall these are just metrics that show basically the difference between false positives and false negatives and we're able to see that you know really really good accuracy here and if I want to look at the preview here what this will do is allow me to now test out on different scenarios so you know for example if I go back to this data here let's go ahead and show it some things that it hasn't seen yet so we know if we go past 200。

 these are all new images so like 233， this is something that's never seen before。

 let's go ahead and try this out and we can just kind of drop drop this here and it says 100% confidence it's a dog if I go through another one you know it's 100% confidence let's。

Again， 100% confidence it's a dog。 let's go ahead and find some cats。

 let's go through here and let's find this kitty here we put this in there we go 10% confidence。

 so I think the real takeaway here is that it's incredibly easy to be a machine learning practitioner by using Apples create ML and and this is just one of the things that can do it can do other things as well like maybe classification of tabular data so let's go through here in fact。

 and look at the output here and notice some different things So one is that it created a model for us and I can actually open it up in Xcode and build an ios application with it I can share it with other people or I can just download it if I click on get here notice that it creates a format called that email model and this email model actually can be converted to different formats for example it could be converted to on X format for example。

It could be deployed to Microsoft， Azure into the cloud somewhere。

 or it could be deployed into let's say AWS， so this is really， in fact， in a sense。

 does many of the things that a data science team would do in an organization and you can just do it on your desktop by dragging a dropping and putting these images inside。

All right， let's shift gears here and let's look at doing a different kind of classification。

 I have a project here where I have some information about NBA teams and if I go to this directory in Github。

 NoA Gi social power and B I've got this social power directory and I've got code in here。

 I also have data and in particular， one of the neat data sets that I have that we can play around with is this one which is NBA 2017 players。

 it shows salary data， how popular they are in social media and how popular they are in Wikipedia。

 so like how many people have you know viewed their page views here。

 there's other data sets that we can play around with as well。

 but this would be a good data set for us to explore I'm gonna click on raw here and this will let me see the raw view of it and then I'm gonna just save it as a different file so I'm going to say comma formatted file and I'm going save it on my desktop。

There we go and now that I've got this， you can see it's saved as CSV file。

 I'm going to go back to my project here and I'm going to close my other project and I'm going to create a new one。



![](img/e66a945aec9844ed32ff6cc4924e26d2_10.png)

And inside of this new project， I'm going to drag this file over here。

 I'm going to look for a different kind of Autom solution。

 in this case I'm going to pick something called tabular classification。



![](img/e66a945aec9844ed32ff6cc4924e26d2_12.png)

And so I'll go ahead and pick that， and I'll call this NBAA。

Social power as the project and we want to predict， for example。

 the position a player would would play， for example。

 let's go ahead and use that like what are the NBA positions that a certain player would play and I'm going to go ahead and create that on my desktop now in order to build out the training data should be pretty straightforward。



![](img/e66a945aec9844ed32ff6cc4924e26d2_14.png)

![](img/e66a945aec9844ed32ff6cc4924e26d2_15.png)

I would need to click choose here and give it this file。

 which is the CSV file and in particular we would now need to pick the target so what do we actually want to predict I'm going to pick I want to predict the position。

That I want to create a model that's going to figure out who's a point guard， who's a center。

 you know， who's a power forward， etc ceter。 And then I get to select which features。

 So these are basically what are the inputs。What do I want to choose that would predict you know what player position would be in Okay。

 let's look at the age here， let's take a look at that， how about how many field goals they make。

How about how many three pointers they attempted， let's go ahead and pick in as well。

 maybe free throws， offensive rebounds， defensive rebounds， assists steals， blocks， turnovers。

 how about as well， how many points they score？And then I think another one that would be a good one。

Would be how much they get paid， how popular they are on social media。

which would be these metrics right here So these all look like some fun features to play around with I'm going to go ahead and select them and notice that we have five classes that we're gonna to use here。

 here's the features and it's gonna automatically pick the correct algorithm it could choose from random forest boosted tree decisionry support vector machine logistic regression this all looks good I'm going to again go here。

 click on train and let's see what this can do in terms of training the model so this one says oh oh missing value encountered in Twitter favorite count so maybe what we can do is we can actually go back here and tweak this so maybe what we want to do is choose features here let's actually take out Twitter because it looks like there's some problems with that and maybe even let's go ahead and select this and let's go ahead and trade it again and see if that works。

And there we go， we're able to complete it and now if I look at the evaluation。

 we can see that we were able to correctly predict。

With 100% precision and recall which are metrics for basically classification accuracy that who would be a center who would be a power forward who would be a point guard who would be a shooting forward or I'm sorry small forward and who would be a shooting guard these are all able to be predicted successfully here which which is pretty neat and so again if I wanted to go through here and I wanted to kind of preview this I could put in different viewpoints here and then go through and use that for a model I also could go through here and download it as well and I can actually do this prediction so not only can you do image-based machine learning but you can also do textbased classification in fact in this case we're able to accurately predict based on those metrics which player in the MBA is in which position based on things like points and rebounds and other such metrics so。

There's a lot you can do with this create ML system if I wanted to create a new project again I could just keep going here and going through and exploring all of the different AutoM features。

 I think we're in a golden era or I would call it the industrial revolution for MLOps and I would hope you would go through and give this a try and explore some of the things you can do with both AutoM and Apple's createate ML。



![](img/e66a945aec9844ed32ff6cc4924e26d2_17.png)

![](img/e66a945aec9844ed32ff6cc4924e26d2_18.png)