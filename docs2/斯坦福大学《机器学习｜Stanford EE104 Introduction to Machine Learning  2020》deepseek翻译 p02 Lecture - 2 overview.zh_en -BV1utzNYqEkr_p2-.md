# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p02 Lecture - 2 overview.zh_en -BV1utzNYqEkr_p2-

![](img/ebba49bc590dd0c39e72ede25832b351_0.png)

Hello and welcome to lecture2 Overview and examples。

 So we describe in this section the general ideas and methods used in machine learning。



![](img/ebba49bc590dd0c39e72ede25832b351_2.png)

Attter high level。We're going to go over all of these topics again in much more detail later in the course。

 so really don't worry if some of this seems abstract at this point or if there are terms that you don't know。

We're going to go over the mathematics of it， we're going to make precise all of the details and spell it all out both in mathematics and in code so that you'll be able to know exactly what the details are in this section we're just going to describe in words。

 the principles of machine learning some of the ideas and some of the methods so at a high level the main idea of artificial intelligence is that you would like a computer to perform a very complicated task something such as medical diagnosis。

😊，In here we can imagine that we have a patient who has a medical history， a bunch of symptoms。

 a bunch of test results， and a bunch of data properties of the patient， their height， their mass。

 their gender， and so on。And we give all this information to a computer in some format。And。

We like their computer to come back and say。What's wrong with the patient is this。

We can think about two approaches by which you might write such a program one is called a knowledge based approach we write a program where we encode in the logic of the program the property is the world and what they mean so for example we would say something like if the patient is of this age and of this gender and as a smoker and as this range of blood pressure then。

And on and on， and on。These kinds of programs can work very well。

 they usually take extensive development by experts in this case。

 medicine or whatever the domain of expertise， whatever the domain of specialty is we're applying the program too。

😊，And it takes many years of work to achieve a working system that has flexibility enough to handle the sort of cases one。

Would like it to Machine learning is very different in its approach， instead of。

Humans encoding the properties of the world in。The program。

In machine learning we supply the program with historical data。

 that historical data consists of a large number of patient records and for each one of those records we supply all of the medical information the test results and so on。

 and we may supply also diagnoses given by a medical professional from all of that data。

 the machine learning algorithm develops， a predictor develops。😊，The ability to make predictions。

 and it uses that predictor to extrapolate so that when it's given a new set of patient data， it can。

Figuring out what the。Diagnosis should be for that new patient。

This class is about machine learning it's about the second of those two types so when we think about the task of machine learning。

 we divide up the process into two generic tasks。😊。

The first of those tasks is to build a model from the data。

We have to take the data and convert the data into a format which is easy for the computer to understand。

Some of that data is rather easy to convert， for example， the height is simply a real number。

Some of the data we may want to do something more sophisticated with it， for example。

 if we have an X ray image of a patient's arm。😊，We could simply give。The machine learning algorithm。

The image， the pixel data corresponding to that image。Or we could encode that image。

 describe additional features of that image in an automated way。😊，We could， for example。

 describe the center of mass， the position of the center of mass of the bone， we could describe。

 for example， the length and the width of various parts。Of the image。

A whole bunch of things we could describe， which we would。

Have to figure out how to what we would choose that would be informative features of that data。

In this class， there are essentially two things that we will do。

 we'll spend some time discussing how to construct sensible features for many standard classes of data。

😊，And then we will switch into a different approach where we discuss how to automatically generate features。

😊，From data。And it turns out that automatically generating features can be extremely powerful。

 and that's one of the key benefits of methods such as neural networks。

The second part of generating a model is to figure out what class of models we would like to have。😊。

There are very simple model forms that you've probably seen before。

One such model might be fit a straight line to the data。

 the sort of thing you would do with linear regression。

There we would need to describe the slope of the line and the intercept of the line and that's essentially two numbers used to describe the model those would be parameter values that parameterize that model。

Alternatively we might describe the model in a much more complicated way。

 we might describe the model as a tree， we might describe the model as a neural network with weights and activation functions These are all different types of models they all have parameterizations in terms of numbers and we would specify both the model form and what parameters are necessary those three things constructing mapping the data to features。

 choosing the model form and choosing the parameter values in the model。😊，Let is the。

Those comprise the first task in machine learning， building the model。

The second task that comes up in machine learning is testing the model or validating the model。

 proving that it works。😊，The key thing one has to do in order to do that is test the model on data that it。

Didn't learn from when we made the model， We don't wanted to test the model against data that we've already used to generate the model because that's cheating。

We will see。In more detail， exactly how one goes about testing the model to avoid this kind of cheating。

And what kind of tests one can do in order to get an effective analysis of whether or not we've done a good job at our modeling and at our prediction。

One of the things one might reasonably expect is that the process of building the model and testing the model is iterative if we test the model and we find out that the model doesn't work。

 the predictions that it's making are not very good， we need a way to update the model。😊。

And that's again， something that we're going to talk about later in the class。

I've used the term model on this slide extensively and I haven't really said what model is model can mean several different things。

 One of the things it is is simplyr， it's a predictor。

 it's a function that takes input data and gives you a predicted output value。😊。

It takes the set of symptoms of the patient and gives you a predicted diagnosis。

But there are other things that could also be a model might be a probability distribution。

 it gives you a distribution over sets of patient records to describe which ones are likely to occur and which ones are not likely to occur。

😊，And well see other things that aor can be as well。😊。

There's a taxonomy of machine learning models that is runs throughout the class and is really how most machine learning algorithms are。

😊，Categorized。The key categorization is that they're supervised models and there's unsupervised models。

😊，So in supervised learning， what we do is we're given some data。😊，呃。

We learn from it how to predict something。And this is one way to think about this is as a prediction model within the category of supervised learning。

 there are two subcategories。😊，And there are progression。In classification。

The only difference between those two is in the， the quantity that's being predicted is a。😊。

Wel number or wheel vector。In classification， the quantity that's being predicted。Bs in a finite。

Might be true or false。 It might be。One of  ten0 different possible diseases。

It might be one of 50 different animals。The other major category of models is unsupervised learning models。

And here the objective is not prediction， but simply to create a model of the data。😊。

So unsupervised models。😊，Just create a model of the data。They don't try to predict anything。

 but instead they give you the capability to tell whether or not an additional data record really belongs in the same category as all the existing records that have been seen。

😊，They also give you the capability of generating new examples， generating synthetic。😊。

Data records that look like real data records。For example， one might make a data model that。

Has learned。All of the paintings of Van Gogh。And then we would ask such a data model。

 please generate a new painting that looks like Vangoh might have painted it。

And these kinds of things are quite possible with modern machine learning techniques。

For supervised learning we can make two different kinds of predictions。

 we can either make what's called a point estimate where we predict a value。😊，We say。

 given all this data， that looks like an elephant or that looks like a dog。

Or we give a probabilistic answer， we say， given all this data。😊，Probability is 20%。

 that's a dog and 80% it's an elephant。Of course， if you've got a probabilistic estimate。

 you might then use it in order to construct a point estimate。You might say， well。

 if the probability is greater than 50%， I'm going to decide that it's an elephant rather than a dog。

One of the advantages of a probabilistic model of course is that it's more informative and as a result。

 you can make decisions that take into account your own tolerance of risk。😊。

These are broad categories， it's a broad taxonomy of models。😊，There are。

Many other categories have modeled， many other types of machine learning。

 some of which we'll touch on or see in examples in the class。

 and there are also things that don't really fit in any one of these categories。

 things which are between two categories。😊，And we'll see some of those as well。

Let's think about some examples here are some models and we can think about what kind of models each one of these particular domains would require。

😊，So， for example， we have the。Last10 days of rainfall data。Then we know the date。

 so we know what time of year it is。And we' need to predict tomorrow's rainfall。

So how might we go about predicting tomorrow's rainfall。

 we might collect data from the last 10 years。And we might divide that data into 11 day chunks。

The first 10 days we would use as data to index the record。

 and the last day would be data that the machine learning algorithm would try to learn as a function of the previous 10 days。

Given many such 11 day long examples。We would hope that the machine learning algorithm would be able to develop a way of mapping the previous 10 days to the next day。

😊，Of course， what it's predicting there is an amount of rain predicting。The numberumb。

And so this would come under the category of supervised learning because it's predicting a number it would come under the category of。

Reggression。Here's another example， determined from a photo of her face if the user is who she claims to be。

😊，What's the data that we're learning from， we've got a bunch of data。

Which is a bunch of different images of people's faces。And associated with each one of those faces。

 we have a name。Now。We give there。Machine learning， predictor。A new photo。

And it has to find in all of those faces that it's seen before。😊，Is this face？One of those face。

 and that would enable it to put a name to a face。So again， this is supervised learning。This is not。

😊，Regression， this is classification。Because there's only a finite number of possible people。

That the user could be。In is another example， estimate the probability of 10 possible diagnoses given some patient data and test results。

😊，Again， this is classification。😊，We're trying to figure out one of1 possible answers and we're given data and test results so this is supervised learning。

 its classification。😊，Here's a different example， we look to cluster customers into 22 different groups with similar buying habits。

😊，Now， this is interesting because we don't have。An idea of what possible buying habits are。

What we have is for each customer a list of what they bought。

But just describing somebody's buying habits as a list of what they've bought。That could be anything。

If we think about all the different products that a store might sell。

 one person buys a particular subset of them， another person buys a different subset of them。

 two people might not have apparently much in common。😊，And so we have to。Figure out。Well， what makes？

Listists of products similar。Is the right way to think about customers as some customers are really into breakfast cereal and others are really into bread？

Or is it more natural to think about customers as some customers like sweet things and some customers like savory things？

😊，Or maybe some customers like red things and some customers like green things。

Here we're starting to see that these are features that are features of the model that we would like our machine learning algorithm to tell us because we don't know what they are ourselves。

This is unsupervised learning。It's constructing a model which describes all of the customers。

And that model has a structure。Which allows us to put it into groups。

And it allows and the machine learning algorithm itself tells us what the natural groupings are。

Here's another example， estimate the risk of an automobile accident at a location given the hour。

 given the weather。😊，This is supervised learning， we have a whole bunch of historical data about automobile accidents at that location in different weather conditions at different times of day。

😊，And this is a probabilistic estimate that we're getting rather than a point estimate。😊。

Another example is an anomaly detector。It ratess how suspicious some data is。

The sort of thing we'd like to do with this so is， for example， look at network traffic。

Does this network traffic indicate that somebodys trying to hack into our network or is it just somebody busy downloading some？

Standard camp video。This is。Again， unsupervised learning。We build a model for data。And。We see， okay。

 most of the data we see looks like this。And then if we get a new piece of data。

It's an anomaly if it doesn't look like the data we've already seen。

That's what we mean by an anomaly。The last example is build a simulator that generates fake new data that looks like the given data again this is unsupervised learning this is Van Gogh。

 we've shown the machine， learning algorithm， a whole bunch of paintings and it's painting a new one。

😊，Of course， this has very specific applications beyond simply making nice pictures for us。

So for example。You'd like to。Make cars that can drive themselves。

One of the problems with that is that it takes an awful lot of testing。

And so if you have a way of generating。A simulation。Of driving down the road。

 then you can use that to test your machine learning algorithm。

Your machine learning algorithm that drives the car can be tested by another machine learning algorithm that generates fake road scenarios that look like real road scenarios。

So let's turn now to how we might measure the performance。Of a model。

This is the topic of performance metrics。😊，So， for example， if we're。😊，Having a model。

 if we have a model which is predicting a real number， this is supervised learning。

 this is regression。Then we might measure how far that real number is from the true real number。

If we're trying to predict。The amount of rainfall， then we might predict five centimeters and the real amount of rainfall when it actually happens。

 may turn out to be three and a half。And so we might take the mean square。Error。

In the amount of rainfall that we predicted。And we'd like to keep that small。

It would be a very reasonable quantity， of course it's square， which means that。😊，啊啊。

Both positive errors and negative errors are counted and if we just took the mean prediction error。

 then if we had an equal amount of positive errors and negative errors。

 then it might look like we got a very small errors so we take mean square。

Very often we take RMS root mean square prediction error so that that's measured in the same units as the error itself。

😊，And of course RMSS is a very nice era， it has lots of nice physical correspondences to things that we know such as energy。

😊，And sometimes that's relevant。For classification。

 we're trying to predict something which is only has one。

ItOnly has a few different possible outcomes， so if we're trying to tell the difference between dogs and cats and images。

We could measure the error rate， how often we're wrong or how often were right。

 we could try and minimize how often we're wrong。Another example。

 if we have probabilistic models is to say， well， a probabilistic model is a model that gives us the probability of different possible outcomes。

😊，It gives us a probability distribution。For those of you who've taken probability before。

 you'll know that one of the things you're interested in about probability distributions is a thing called the likelihood in the log or the likelihood in particular。

😊，That's a way of measuring how likely it was that the data that you saw could have actually been generated by the probability model that Ukraine claim generates it。

😊，We're going to say much more about that in a few weeks。Again。

 don't worry about it right now if you。Not heard of likelihood。So for some examples。

 you might have a predictor that predicts tomorrow's maximum temperature。😊。

And the way you might measure its performance is by RMS error， and if the RMS error is 1。

3 degrees centigrade， you may or may not be happy with that。

You might have a classifier that predicts the topic of a newspaper article from a set of 50 choices。

😊，With an error rate of 5%。So when we do machine learning。

 we're always doing machine learning from data， usually we'd like as much data as possible。😊，嗯。

We're also have in mind that we need to test。The machine learning model， a predictor。

Against data that we've never seen before。And so the standard way of doing this is that when one collects a whole bunch of data from experiments or from。

The field。One cuts it into two parts and puts one part aside。Never looks at that part。

The first part of the data were used to train the model。We use it to developout the predictor。

And once we've developed the predictor and we've taken it to the point where we're happy with the predictor。

 we think it's going to work well。😊，We tested on this。Reserved piece of data。

 this validation data set。To see how well it did on data that was never seen before。

 the data that one keeps aside is called a test set or a validation set。

So now we have two performance metrics， we have how well did it perform on the training set？😊。

And how well does it perform on the test set？Sometimes one can develop a model that performs really well on the training set。

 but very poorly on the test set。An easy way of doing this is that if you're trying to tell train a system to。

Tell the difference between dogs and cats， it could just remember all of the images that it seen。

And tell you， oh， that's when you told me was a cat and that's when you told me it was a dog。

And it doesn't help it at all when it sees a new image that。Isn't any of the images it's seen before？

In general， if you've got a model that does well on the training set， but poorly on the test set。

 you say it's overfit。It's learned properties of the training data that。

A specific to that particular data。😊，Rather than general properties of the underlying phenomena that you're trying to learn。

On the other hand， if you've developed a model using the test set and it works on the training set。😊。

Well， then you might say， well， it worked on that data which it'd never seen before。

 maybe it will work on some other data too。😊，That it's never seen before。😔。

So there are a number of different ways one might choose a model。嗯。

One of the common methods is to say， well。I'm going to choose a class of models。

 I'm going to choose a model structure or perhaps a form of model of a type of model。

 I'm going to say I'm only interested in models which are linear regression models。

 I'm only interested in models which are convolutional neural networks or I'm only interested in models that are trees。

😊，Those models are described by numbers， by parameters。What you do is you say， okay， well。

I'm going to define a loss function， a figure of merit。

 which tells me how well the model performs on one single data point。😊，It might be， for example。

The square of the error between the predicted amount of rainfall and the actual amount of rainfall。

And then we're going to choose the parameter values that enter into the model by varying them。😊。

And finding the ones that minimize。The average loss over all of the training data。

This is a very general scheme and it's extremely widely used in machine learning。😊。

And it's called empirical risk minimization。😊，And you can use this to fit all sorts of models and all of the models that we've talked about so far in this section can be fit using empirical risk minimization。

Let's look at this diagnosis example。Here the goal is to predict if a patient has a disease。😊。

Based on whether or not he or she exhibits10 symptoms。

But the historical data consists of is a large number of patient records。😊。

Each record contains 10 bos。Specifying the presence or absence of the 1 symptoms。

And it contains an additional boolean that specifies whether。😊。

That particular patient had that particular disease。😊，We have a very large number of these records。😊。

Each record has 11 billions。The machine learning algorithm。Ingests that data。It learns for a while。

And then it comes out with a predictor。What that predictor does for us is we take that predictor and then we give it。

Ten new bos corresponding to some other patient。Who would like to know whether or not they have that particular disease？

And it returns for us， a single boion。😊，Which is the prediction。

Whether or not that patient has the disease。This is supervised learning， this is a classifier。😊。

We're predicting an outcome that takes only two possible values。

And we're going to judge the model by its error rate。Because it can only give a true or false answer。

And we'll do that by having a separate set of test data。A separate collection of 11 Booles。

Which we didn't use to generate the model。Of course。

 a probabilistic model would return a probability that the patient had the disease and not just a boion。

And we might immediately think about how to make this more sophisticated。😊，We won't just give it 10。

Boollions describing symptoms would also give it other patient data。Test results。ADemographic facts。

😊，Information about。Where the patient lives， what the patient's habits are。All sorts of things。去你妈。

Give it random stuff。Patient's favorite colour。 patient sooe shoe size。Patientst's favorite movies。

Because you don't necessarily know。What's going to make the predictions better？

What you'd hope is that your machine learning algorithm could distinguish for you what's meaningful and what's not。

And we will see that machine learning algorithm can in fact do that。

It can tell you that that data was utterly uninformative。Now here's another example。

 this is a classic example， this is called the MNist MNIST data。😊，It's a collection of 60，000 images。

And these are all hand written digits， you can see in these images。

 there's quite a lot of variation in the way。Different people， like the same digit。

Our prediction algorithm would take all of these 60，000 images。And。Learn a classifier。

They would give us back。A prediction。Given a new 28 by 28 pixel image。

 it would give us back a prediction as to what digit was in that image？So this is a very well used。

Training set， test set， data set， it's considered easy by modern standards。

 you can do very well with very simple algorithms。And we will learn how to do that in this class。

It's worth talking a little bit about data because machine learning is such a widely used discipline。

😊，嗯。At the moment， there's been a huge amount of effort to collect data。😊。

Partly to partly by the research community and。Industry。

To develop better machine learning algorithms。And partly because people are trying to apply machine learning in very specific disciplines。

😊，In order to develop useful products， useful tools。So one of them is a thing called Caggle。

 Caggle is a website， it began as a startup it was acquired by Google a few years ago。

And what they do is they collect data， data sets。😊，And they went competitions to。

See how well people can develop predictors and they do the job of holding validation sets in escrowve so that people can't cheat。

😊，And you can sign up for Cagle， just give me your email address， you can download the data set。

 you can see how well you can do it at doing prediction。On the on the training set。

And then you can submit your predictor to them。To see how well you do on the validation set and compare your performance against。

The best， the state of the art。So Kaggal has many different data sets we will in this class we will set homework。

 quite a few of the data sets will come from KaGL。It's a very useful tool for learning。

And for developing machi learning algorithms。ImageNet dataset set is a very popular dataset set contains 14 million images of a variety of different things。

And in many different categories， and it's used for classification。Street View。

 Google Street View has a whole bunch of house number images， 600，000 images of digits。

 this is much harder than the MNIS data set because these are all photographs of the numbers on the front of houses。

😊，And you're probably aware that those things come in all sorts of strange formats。

 curly lettersters， strange shaped tiled images， pretty colors。

 all sorts of strange borders around them， and so identifying those kinds of images。😊。

It's much less structured， much less clean data one has to work with and one can still do very well with the methods that we'll show you in this class。

😊，As you know， many people are working on self driving cars。

 we're fortunate in that lift has open sourced。😊，Some of their data。

And that's a source of data that one can use to develop very specific。

 very focused algorithms for perception for self driving cars。And in particular。

 there's one would like to identify the sorts of things one sees on the road， pedestrians， bicycles。

 other cars， trucks。Road signs， traffic lights。These kinds of things。

That data is interesting because it doesn't only consist of。Images。And not even single images。

 but it consists of multiple different。Sensors observing the same thing。

So you have on a lift self driving car， I think you have six cameras and three LiDars and so the LiDar images give you a range measurements as pixel data。

And of course， cameras give you color。Measurements as pixel data。嗯。And everyone can。

Develop machine learning algorithms that use both types of data simultaneously。

One can also develop machine learning algorithms that take advantage of the fact that the image1 Cs now has something to do with the image1 Cs。

10th of a second from now as the car moves down the road。

And so there's a lot of scope there for developing things that are。😊。

Very much subjects of current research， but also very likely to be。Use is in practice。

And there are many other large data sets online now。😊，And simple， take any topic that's on your mind。

 you can Google for data sets and there's been a because of the surge and interest in machine learning。

 many data sets have become public。And so one has data which would previously have been hard to get and held by。

Specific companies that kept their data private now those data sets are being made public because everybody benefits if we could develop better algorithms。

To understand such data。I should say a word about software。

 much effort has gone into developing machine learning software。😊，These here I list torch， Kiss。

 Theo， Tensorflow。psychic Learn Spark， MLlib。Fluux。

 these are all different packages for doing machine learning。😊，嗯。They're in all different languages。

 they're in R Matlab， Python， Java， Julia， we're going to be using flux in Julia。

Many of these packages support GPU acceleration。That's useful because it turns out that when you're trying to learn。

Image classifierifies， for example that uses quite a lot of processing power and so you can gain a lot of benefit and reduced training time if you're using a package that can take advantage of GPU acceleration。

Such as flux。Also， many of these packages will allow you to run training on the cloud。

So if you don't have a very powerful computer at home， you can run training on the cloud。嗯。

But as you'll see in this class， even though there are these complicated packages。

 very extensive software packages， in fact， you can write the software to do machine learning yourself。

 we will show you how to do it。And so that if you wanted to， you could write everything yourself。

From scratch。We don't recommend you do so， lots of time has gone into making these packages fast and code you right will probably not be that fast。

In fact， the general philosophy of this class is to have you write as little code as possible。

The class is really about how machine learning works， how。To use these tools。

 how to formulate machine learning problems， how to think about machine learning problems。

 how to appropriately feurize data sets， how to think about what types of model one should use。

It's much more about those things than it is about how to effectively implement the algorithms。😊。

We will teach you how to effectively implement the algorithms。

But really the purpose of that is to demystify。The way these packages work rather than so that you should go and do it yourself。



![](img/ebba49bc590dd0c39e72ede25832b351_4.png)

![](img/ebba49bc590dd0c39e72ede25832b351_5.png)

![](img/ebba49bc590dd0c39e72ede25832b351_6.png)