# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p06 Lecture_6_Perceptron.zh_en -BV1Z2cUefE4A_p6-

![](img/223aea760bce52b872e46ca99b14c6fe_0.png)

All right good morning everyone thank you all for joining me on this Friday。

 thank you for remembering that we have lecture so today we're going to introduce a new machine learning model and we're also going to introduce like a whole new paradigm for machine learning that looks really different from the kinds of stuff that you've been working with so far where we like hand you some nice curated data we're going to think about an alternative version of this problem known as online learning。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_2.png)

![](img/223aea760bce52b872e46ca99b14c6fe_3.png)

![](img/223aea760bce52b872e46ca99b14c6fe_4.png)

![](img/223aea760bce52b872e46ca99b14c6fe_5.png)

![](img/223aea760bce52b872e46ca99b14c6fe_6.png)

![](img/223aea760bce52b872e46ca99b14c6fe_7.png)

Before we do that some reminders don't forget your second homework is due today I guess you have like 12 and no 14 and a half more hours so you know get un started yet still got plenty of time homework three will also be coming out later this afternoon again the big reminder here is that you can only take at most two late days on homework three and the recitation that would be here today will be on Wednesday。

 same time same place。

![](img/223aea760bce52b872e46ca99b14c6fe_9.png)

![](img/223aea760bce52b872e46ca99b14c6fe_10.png)

All right， some excellent questions that came up after lecture and I think also on Piazza。😊。



![](img/223aea760bce52b872e46ca99b14c6fe_12.png)

I mentioned， I think， during our model selection discussion that。



![](img/223aea760bce52b872e46ca99b14c6fe_14.png)

The premise of our splitting the training splitting the data into training validation and test data sets。

 particularly using like a really large percentage of our data for training the premise of that is that more training data is good right and so a reasonable assertion is shouldn't we after we've decided on the right model to use combine our training and validation data sets to have more training data and the answer is absolutely yes right so if I were to sort of rewrite that sketch from。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_16.png)

![](img/223aea760bce52b872e46ca99b14c6fe_17.png)

![](img/223aea760bce52b872e46ca99b14c6fe_18.png)

![](img/223aea760bce52b872e46ca99b14c6fe_19.png)

Wednesday's lecture， we might add in some fourth step where we've selected the right model to use and then we train the best possible classifier from that model by using union of our training and validation data sets while still keeping our test data separate because we do still want a good estimate of the test error。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_21.png)

![](img/223aea760bce52b872e46ca99b14c6fe_22.png)

![](img/223aea760bce52b872e46ca99b14c6fe_23.png)

Here's another question so we've sort of talked about all the possible combinations of regression and classification tasks and categorical and real value features。

 except for this one， which is can we use KNNs with categorical features。

 the answer to which is a resounding yes， you just need to select the correct distance metrics。

 something that works on categorical features， I'm not going to talk too much about this because we put together a nice homework question for you all to explore this idea for yourselves。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_25.png)

![](img/223aea760bce52b872e46ca99b14c6fe_26.png)

![](img/223aea760bce52b872e46ca99b14c6fe_27.png)

Okay， so I want to go back to this Fisher irris data set。

 we introduced this on Monday to talk about K andNs and。



![](img/223aea760bce52b872e46ca99b14c6fe_29.png)

![](img/223aea760bce52b872e46ca99b14c6fe_30.png)

You know， we went through this whole thing about like learning these sort of really crazy wonky looking decision boundaries and using like what I would argue is a slightly more complex model in the form of canNs and that led to this great discussion on model selection and all this other cool stuff that we can do when I think you know when Matt put up this picture for the first time。

 many of you were like wait a minute why don't we just do something simple right like this looks like pretty clearly。

Something that I could just draw a line through right stuff on the right side here classifies as y equals one stuff on the upper left classifies as y equals zero。

 and then we can just be done with it right why do we need to go through that whole righammarole of like computing nearest neighbors and then computing more nearest neighbors for higher values of K when instead we could have just learned a line。

And that's exactly what we're gonna to do today So before we do that we need to review a couple concept well we need to establish a notation like standard for this class and then we're just gonna do a little bit of a warmup review activity so in this class we are going to make a choice about our notation for vectors that is by default all vectors will be column vectors so when we write just like a vector a it's a column vector when I write something like a transpose it's a row vector so something like this here and again some notation hopefully this is all review for you。

 but just in case we'll say that the dot product or sometimes we'll say the inner product between two vectors will be something of this form note crucially that because we define our vectors to be columns by default dot products we write as a transpose B as opposed to a be transpose that would be an outer product here the inner product is a transpose B you just multi。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_32.png)

![](img/223aea760bce52b872e46ca99b14c6fe_33.png)

![](img/223aea760bce52b872e46ca99b14c6fe_34.png)

![](img/223aea760bce52b872e46ca99b14c6fe_35.png)

All the elements with their corresponding counterpart in the other vector and you add them all up together。

This will allow us to define things like norms， specifically the L2 norm this is going to come up a lot。

 this is like some measure of the magnitude of this vector a like how big it is and it's，😡。



![](img/223aea760bce52b872e46ca99b14c6fe_37.png)

![](img/223aea760bce52b872e46ca99b14c6fe_38.png)

The dot product between the vector and itself square rooted。



![](img/223aea760bce52b872e46ca99b14c6fe_40.png)

We'll also talk a lot about the L2 norm squared because that square root is annoying but here's the more complete version of that and here's another very important definition you know if you're in sort of 2D you have lines that can be perpendicular to one another the like multidimension or higher dimension corollary of that is orthogonality so two things being at a right angle vaguely speaking happens when these two vectors in multidimensional space their dot product is equal to zero again something that's going to come up in today's content。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_42.png)

![](img/223aea760bce52b872e46ca99b14c6fe_43.png)

Okay so we're gonna be thinking a lot about lines and planes and hyperplanes today。

 so I figured to you know set the tone for today's lecture we could start with a little exercise so what I want you to do in the next I's say four minutes here is I want you to either on the slides or on a piece of paper where you sketch out some axes I want you to draw the following region on this 2D Euclidean plane here that is the region defined by this inequality W1 x1 plus W2 x2。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_45.png)

![](img/223aea760bce52b872e46ca99b14c6fe_46.png)

![](img/223aea760bce52b872e46ca99b14c6fe_47.png)

Plus， B is greater than zero。For those values of W and B。

 and then I want you to draw the vector on that same set of axes。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_49.png)

![](img/223aea760bce52b872e46ca99b14c6fe_50.png)

All right， so like I said， let's take four minutes here， however you want to do this is totally fine。

 you can work with a partner， you can try and figure this out on your own。Ohoops。

 we'll reconvene in four minutes and see what you'll have to say about this。



![](img/223aea760bce52b872e46ca99b14c6fe_52.png)

Alrighty I'm hearing a lot of silence so I hope that means you all have an answer let's reconvene here does anyone care to share what they believe to be the correct or corresponding region to that inequality I don't necessarily know what the like maybe you could just like put your arm up in the like corresponding direction vaguely。

😊，Something like this， is that what we're trying to get at here？另外。Something like this。

Now we all just look like we're dabbing， hang on。I'm I'm seeing a lot of lines going from left。

 bottom left to upper right is that？What you guys got？

Am I looking at this figure backwards I'm seeing okay so all right。

 let's just do this in words who wants to describe their decision boundary Yeah sure hit me。😊。



![](img/223aea760bce52b872e46ca99b14c6fe_54.png)

![](img/223aea760bce52b872e46ca99b14c6fe_55.png)

嗯。So zero， two， all right， let's call that here。And then for。Or zero。 so let's call that here。

All right， and so you drew。Some line that looks like this， I think I might know the answer。

 but do you want to describe how you got this as the well。

 let's start with how you got this as the line。

![](img/223aea760bce52b872e46ca99b14c6fe_57.png)

That's kind of element as for parents ask to move live and an encourage line。

Sure yeah slope intercept form totally a valid solution I thought you were going to say something about like plugging in x1 equals0 and x2 equals zero。

 but this is also totally valid， I guess the remaining question is which side corresponds to the inequality if you do a test point like。

😊，What happens if I put in zero zero here？Inequality is false。

 so it has to be the side that doesn't contain zero zero All right， someone else。

 what does the vector W1 W2 look like？

![](img/223aea760bce52b872e46ca99b14c6fe_59.png)

And I'm sorry， is there any chance you could turn me down a little bit in the back there， thank you。

 yeah， right here。Very start。

![](img/223aea760bce52b872e46ca99b14c6fe_61.png)

再说。Oh， hey， that's exactly right。 And this is what I was hoping you would say The vector here。

 if you just sort of well hang on， that wasn't great。 This is two。 So this is like one。

 So it's really more like。😊。

![](img/223aea760bce52b872e46ca99b14c6fe_63.png)

This vector， but yes， the key takeaway that I want you to remember is that this vector is orthogonal to the line perpendicular to the line defined by those coefficients。

 w1 and W2 and in fact that relationship will always hold between the line and the weight vector W。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_65.png)

![](img/223aea760bce52b872e46ca99b14c6fe_66.png)

![](img/223aea760bce52b872e46ca99b14c6fe_67.png)

here's the answer what do you know I guess I forgot to shade it's stuff on this side still that satisfies this inequality All right cool I'm going to assume that I'm insane and that many of you are holding your arms up in the right way。

 so we're all on the same page about this geometry how are we going translate this into a machine learning context though all right so let's establish a few more words just in case some of you haven't heard these terms before in 2D。

 some equation like this is going to define a line you can convert this into slope intercept form to be something that you might be more familiar with but you know just adding a dimension we have instead of a line like a plane in 3D like a sheet of paper and then once we start getting into higher dimensions a I need to re revert to my vector notation because it no longer fits on the slide so an equation that looks like W transpose x plus B。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_69.png)

![](img/223aea760bce52b872e46ca99b14c6fe_70.png)

![](img/223aea760bce52b872e46ca99b14c6fe_71.png)

![](img/223aea760bce52b872e46ca99b14c6fe_72.png)

![](img/223aea760bce52b872e46ca99b14c6fe_73.png)

Ealing zero will define a hyperplane， however， you want to imagine that in higher dimensions。



![](img/223aea760bce52b872e46ca99b14c6fe_75.png)

So this was the big takeaway from our exercise that this weight vector W。



![](img/223aea760bce52b872e46ca99b14c6fe_77.png)

In any dimension is always going to be orthogonal to this hyperplane and actually I forgot to mention this。

 the other crucial observation here is that it always points in the direction where that inequality or that quantity on the left is greater than zero。

 so it always tells you which side of the hyperplane is the positive side and which side is the negative side。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_79.png)

![](img/223aea760bce52b872e46ca99b14c6fe_80.png)

![](img/223aea760bce52b872e46ca99b14c6fe_81.png)

![](img/223aea760bce52b872e46ca99b14c6fe_82.png)

Relatedly， when I say positive and negative sides， what do I mean by that。

 well all of these linear equations， all of these lines， planes， hyperplanes， whatever。

 they split your space， whatever dimension you're in into two parts。

 what we'll call a positive half space and a negative half space。

 and they're just defined by whether or not this quantity W transpose x plus B is greater than or less than zero。



![](img/223aea760bce52b872e46ca99b14c6fe_84.png)

![](img/223aea760bce52b872e46ca99b14c6fe_85.png)

![](img/223aea760bce52b872e46ca99b14c6fe_86.png)

![](img/223aea760bce52b872e46ca99b14c6fe_87.png)

And remember， the vector W rooted at the origin， always points towards the positive half space。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_89.png)

Okay， let me again stop here， we're going to talk about how this relates to machine learning in just a second。

 but before I move on， what questions do you all have？😡。



![](img/223aea760bce52b872e46ca99b14c6fe_91.png)

Yeah， right here。I'm going to go with no， I think if you call the line a hyperplane。

 you would get looked at like you were insane。Yeah。

 I think we reserve the word hyper to four or greater dimensions。



![](img/223aea760bce52b872e46ca99b14c6fe_93.png)

All right， so how are we going to translate this sort of geometry。

 this like linear algebra review into a notion of machine learning and the way that we're going to do this is we're going to talk about linear decision boundaries So before we were just thinking about these lines or these planes or hyperplanes as being these abstract quantities now we're actually going to use them to make predictions specifically we're going to think about you know these two。



![](img/223aea760bce52b872e46ca99b14c6fe_95.png)

![](img/223aea760bce52b872e46ca99b14c6fe_96.png)

![](img/223aea760bce52b872e46ca99b14c6fe_97.png)

Half spaces defined by。

![](img/223aea760bce52b872e46ca99b14c6fe_99.png)

Our hyperplanes as a positive region and a negative region or a portion where we classify the two binary classification problems。

 we classify the two classes differently。

![](img/223aea760bce52b872e46ca99b14c6fe_101.png)

And so the goal of today's lecture is going to be to learn classifiers of this form where I have this decision boundary defined by w transpose x plus B and all I need to do is take the signine a bit I need to check whether or not for some query vector X W transpose x plus B is greater than zero which I would classify as positive or w transpose x plus B is less than0 which I would classify as negative and again here I'm assuming well I'm assuming two things I'm assuming that the sine function returns either minus1 or plus one and I'm assuming your labels are encoded correspondingly so the big question that we want to talk about today is how are we going to learn these parameters W and b I'm going to throw one more wrinkle at you first though which is。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_103.png)

![](img/223aea760bce52b872e46ca99b14c6fe_104.png)

![](img/223aea760bce52b872e46ca99b14c6fe_105.png)

![](img/223aea760bce52b872e46ca99b14c6fe_106.png)

![](img/223aea760bce52b872e46ca99b14c6fe_107.png)

Well， we'll talk about the traditional machine learning setting in just a second， but you know。



![](img/223aea760bce52b872e46ca99b14c6fe_109.png)

![](img/223aea760bce52b872e46ca99b14c6fe_110.png)

The traditional setting in which you get just a fixed amount of data and you have to maybe do some sort of partitioning and then training on your training data。

 that's all well and good， but in many settings that's not realistic。

 that's not how you acquire data。😡，In many settings。😡。

So that would be what we would call the batch setting。

 but an alternative to this is where you have deployed some machine learning model in the real world and now you're getting sort of more data as it's being used as you sort of test new data points as new maybe customers come in you're getting more data and you know it seems like a bit of a shame to just throw that away so what if we could incorporate new data continuously into our model and this is what we would call the online setting and you know。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_112.png)

![](img/223aea760bce52b872e46ca99b14c6fe_113.png)

![](img/223aea760bce52b872e46ca99b14c6fe_114.png)

![](img/223aea760bce52b872e46ca99b14c6fe_115.png)

![](img/223aea760bce52b872e46ca99b14c6fe_116.png)

![](img/223aea760bce52b872e46ca99b14c6fe_117.png)

I've done a lot of talking so let me turn it over to you all what are some examples of online learning that you might be able to speak about some things that you might be familiar with Yeah right here Yeah more broadly than。

Does recommend have two Cs what once gosh？Recomander systems， yeah， not just Netflix。

 but all sorts of social media platforms can improve their performance both sort of at a population level and at an individual level as you rate more things。



![](img/223aea760bce52b872e46ca99b14c6fe_119.png)

Right here。😊，I mean， sure， yeah， targeted advertising， I think is a like subset of this， maybe。

Targeted advertising。Yeah， Google Ma sort of what I learned or allow。OhOkay， yeah。

 I think this is again maybe like a recommendation sort of thing like。😊，Google Maps or you know。

 route。Preferences。What else？

![](img/223aea760bce52b872e46ca99b14c6fe_121.png)

嗯。😊，Sure， yeah， I think in I'm going to write this slightly broader。

 but again you're hitting on a big point here， which is like time series like data or time series effects that is like you make some measurement and then you make another measurement。

 some amount of time later and you make another measurement， some amount of time later。

 you're getting more and more information about whatever phenomenon you're trying to model here。

 any other any other suggestions， yeah right here。

![](img/223aea760bce52b872e46ca99b14c6fe_123.png)

Oh I really like this suggestion。 Yeah， reinforcement learning we have not talked very much about this。

 we will we'll spend a lot of time talking about this later in the semester。

 but this is a setting in which you are sort of actively making decisions to gather data all right so this is a really great list and I hope you all take away that this is like a very important paradigm for learning So what does learning in this online setting look like Well what we're going to say is we have some amount of time steps some number of iterations it doesn't have to be actual time but frequently it is what we're going to do is we're going to iteratively receive some unlabeled data point X X T here and we're going to have to make a prediction about it so we're going to use our current belief that is。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_125.png)

![](img/223aea760bce52b872e46ca99b14c6fe_126.png)

![](img/223aea760bce52b872e46ca99b14c6fe_127.png)

At least for this lecture some classifier parameterized by the weight vector W and the intercept term B here。

 we're going to use those to make a prediction on this unlabeled data point。

 our prediction will be why hat， then we get the right answer。

 we get you know whether or not the individual watch the movie clicked on the ad。

 whether or not their condition improved under the treatment or didn't we get the right answer。

 and if we made a mistake， some kind of mistake we incorrectly classify the data point。

 then we're going to pay some penalty and update our parameters and the goal out of all of this is to sort of learn a better and better classifier to the point where we minimize the number of mistakes we're making over time。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_129.png)

![](img/223aea760bce52b872e46ca99b14c6fe_130.png)

All right， so here's the premise， let me again stop before we talk about maybe like the simplest possible algorithm you could imagine for this setting。

 before we do that let me again stop here， what questions you all have。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_132.png)

![](img/223aea760bce52b872e46ca99b14c6fe_133.png)

![](img/223aea760bce52b872e46ca99b14c6fe_134.png)

Yes。嗯。第个。呃，毛。对他们1几天。Oh this is a really great question and we'll talk about that in a few slides。

 but the big idea is it shifts my decision boundary off of the origin in one direction or another it's you know the intercept term it's where it meets the。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_136.png)

![](img/223aea760bce52b872e46ca99b14c6fe_137.png)

Notion of the Y axis in whatever dimension you're working in。



![](img/223aea760bce52b872e46ca99b14c6fe_139.png)

Yeah， right here。哎，我れ。嗯。Oh yeah I mean this is a great question so what can we do if our like actual data doesn't lie in a nicely sort of bisected region which is you know we eat some air。

 we just sort of have to live with it I will say that like there are a lot of nice properties of linear decision boundaries they're sort of simple learning is efficient。

 they're resilient in some sense to overfitting。😊，But they can definitely be over simplistic and they might underfi data as well。



![](img/223aea760bce52b872e46ca99b14c6fe_141.png)

What else？

![](img/223aea760bce52b872e46ca99b14c6fe_143.png)

嗯。😊，Yeah， this is a really great question， so in a few lectures we'll talk about a probabilistic alternative to this where instead of being like 100% certain that stuff on one side is a plus and stuff on the other side is a minus。

 we'll talk about making sort of probabilistic guesses or estimating probabilities that things are pluses or minuses。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_145.png)

Yeah。啊。对啊。Okay拜。What we're going to demonstrate here is that we're not sort of starting from scratch each it that we are hanging on to some previous information as we make these updates。

😡，All right so on that note actually we can talk about what these updates are going to be so here is what we'll call the online version of the perceptron。

 so here's the algorithm， the model itself is the perceptron。

 the perceptron learning algorithm proceeds like this What I'm going to do is I'm going to initialize all of my weights and my intercept to zero。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_147.png)

![](img/223aea760bce52b872e46ca99b14c6fe_148.png)

And then， like I said， in this online setting， we're going to receive， excuse me。😡。

Some unlabeled data point。We're going to use this decision boundary。

 this sign of W transpose x plus B to come up with my model's prediction。

 and one thing to note here I'm arbitrarily breaking ties in favor of plus one here。

 this is again completely a design choice， but you do need to specify the behavior of points on your decision boundary as well。

😡，We're going to observe this true label and then here's the sort of actual update here's where we're doing something you know that we might consider learning we're going to consider two kinds of mistakes if we make a mistake on a positive point here's the update we're going to add the feature vector X to my current weight vector and we're going to increment my intercept term by one。

😡，And if we make a mistake on a negative point， we're just going to do the opposite of that。

 we're going to subtract the feature vector and we're going to subtract one。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_150.png)

All right， this is kind of strange and potentially a little unintuitive as to why we're doing this。

 we're going to go through an example in just a second。😡，But before we do that。

 let let me actually simplify this update a little bit because you might note we're making a positive change when we make a mistake on a positive point and we're making a negative change or a subtraction when we when we make a mistake on a negative point so I can just sort of encode that more succinctly by saying if we make a mistake。

 we multiply the feature vector by Yt， the true label which is either plus one or minus one and I can have sort of one consistent update rule for。



![](img/223aea760bce52b872e46ca99b14c6fe_152.png)

Either kind of mistake here。

![](img/223aea760bce52b872e46ca99b14c6fe_154.png)

Okay， so let's see how this plays out right let's see how this algorithm works here's some data that consists of oh。

 just three points， I guess。😡。

![](img/223aea760bce52b872e46ca99b14c6fe_156.png)

![](img/223aea760bce52b872e46ca99b14c6fe_157.png)

And we're going to start with using no intercept。 we'll talk about how the intercept affects this procedure in just a second and you know we're going to initialize our weight vector to zero and。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_159.png)

Iing to pick a point。You know。It feels kind of rude。But， like。



![](img/223aea760bce52b872e46ca99b14c6fe_161.png)

We asked you to come in on a Friday。For like， a lecture。And。You know。You're probably thinking a。

 this is gonna to be like some actually helpful stuff for my learning and it's gonna to get to hang out with the Ts Well。

 I have good news for you you're gonna get to hang out with your Ts and because you all came here on Friday when you didn't have to we're going put on a little show for you so instead of doing this boring math which it's in the slide you can do it on your own time we're gonna to play a little bit of a game Matt。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_163.png)

Matt will be my lovely assistant and what we're going to do is what we've done many times already we're going to use you as our data set and we're going to define a very large decision boundary in this space and we're going to run this perron learning algorithm and here's the real rub I'm not going to know what that decision boundary is Matt is going to define it for us and we're just going to see if the algorithm can do what it promises which is learn the true decision boundary in this space so with that Matt surprise me。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_165.png)

![](img/223aea760bce52b872e46ca99b14c6fe_166.png)

![](img/223aea760bce52b872e46ca99b14c6fe_167.png)

![](img/223aea760bce52b872e46ca99b14c6fe_168.png)

Okay， so you might not believe us， you might be thinking to yourself。

 oh come on like Henry already knows what the decision boundary is。

 so he's just going to cheat and you know， like it'll be this kind of game where like it looks like he doesn't know what's going on。

 but actually he does。

![](img/223aea760bce52b872e46ca99b14c6fe_170.png)

![](img/223aea760bce52b872e46ca99b14c6fe_171.png)

![](img/223aea760bce52b872e46ca99b14c6fe_172.png)

![](img/223aea760bce52b872e46ca99b14c6fe_173.png)

Well， it turns out as I just learned that。😊。

![](img/223aea760bce52b872e46ca99b14c6fe_175.png)

When Henry and I were negotiating how to cheat in this exercise this morning。

 we actually had set it up all around so just so you know Henry。

 you genuinely don't know what the decision now okay and that means you guys are actually in the wrong place can you go here and you come down here and so this is our weight vector and can you hold up the origin for us。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_177.png)

![](img/223aea760bce52b872e46ca99b14c6fe_178.png)

![](img/223aea760bce52b872e46ca99b14c6fe_179.png)

![](img/223aea760bce52b872e46ca99b14c6fe_180.png)

Okay， so this is the origin00。And don't tell him what we're doing here。

 so the true and you're going to go great there。Great， okay， so the true weight vector。Is。

Let me think about it Okay， so can you。CanYou take this。



![](img/223aea760bce52b872e46ca99b14c6fe_182.png)

I can't say numbers here， so we're going to go。Like right back there。

And then we need our decision boundary orthogonal to our weight vector。

 right so can we send the decision boundary？

![](img/223aea760bce52b872e46ca99b14c6fe_184.png)

Q here。All right。

![](img/223aea760bce52b872e46ca99b14c6fe_186.png)

![](img/223aea760bce52b872e46ca99b14c6fe_187.png)

Actually wait let's try the oh yeah there we go now we're good to go all right。



![](img/223aea760bce52b872e46ca99b14c6fe_189.png)

And can you pass this forward？

![](img/223aea760bce52b872e46ca99b14c6fe_191.png)

There we go。 Oh， there we go。 Yeah， thank you， thank you。 Okay， so now。



![](img/223aea760bce52b872e46ca99b14c6fe_193.png)

Okay so you guys just learned how linear decision boundaries work and with that in mind you can see the weight vector and you can see the decision boundary。

 so think for a second， am I a positive point or a negative point okay， think for a second okay。

 raise your hand if you are a positive point。😊。

![](img/223aea760bce52b872e46ca99b14c6fe_195.png)

![](img/223aea760bce52b872e46ca99b14c6fe_196.png)

Okay。Very good right you you guys are yeah， so all the positive points are on the side of the decision boundary。

 raise them very confidently now since all the positive points are on the side of the decision boundary where the weight vector is actually pointing Okay。

 now raise your hand if you're a negative point。😊，Okay， you guys。You're so negative， negative。Yeah。

 we'll say you're you're like here's the decision matter， so negative okay and。

You might actually be classified as neither positive nor negative。 Okay， very nice。 that's special。

 Okay， so now we have to wrap up the decision boundary so that you can't see it and the weight vector so you can send the weight vector back to the origin。

 The decision boundary should come all the way back across here and we'll hopefully not tangle up our origin or our zero point here。

 Okay， great and。😊。

![](img/223aea760bce52b872e46ca99b14c6fe_198.png)

Now maybe you you too， since he recognizes you you guys should move somewhere else。

 oop sorry about that let's not break any。

![](img/223aea760bce52b872e46ca99b14c6fe_200.png)

Expensive iPads or anything so you should just like move somewhere random in the room just so that he's completely completely caught off guard here and thank you。



![](img/223aea760bce52b872e46ca99b14c6fe_202.png)

![](img/223aea760bce52b872e46ca99b14c6fe_203.png)

All right and we're ready to begin so remember whether you're plus or minus because Henry is going to make use of that so you have to know whether you are plus or minus don't forget that's your true label that was the true decision boundary all right Henry all yours。



![](img/223aea760bce52b872e46ca99b14c6fe_205.png)

![](img/223aea760bce52b872e46ca99b14c6fe_206.png)

![](img/223aea760bce52b872e46ca99b14c6fe_207.png)

All right， okay。So啊。But I'm going to feel back first a little bit too。This on All right。

 I'm gonna peel back the curtain a little bit， too， because I was gonna cheat。

 I was gonna have a predefined list of points here。 But now Matt has gone row on me。

 So I don't know what to do。 So I'm going to play out the algorithm。

 I'm going to pick people in the audience and ask them what their true label is。 Well。

 I'm going to make a prediction using。😊。

![](img/223aea760bce52b872e46ca99b14c6fe_209.png)

![](img/223aea760bce52b872e46ca99b14c6fe_210.png)

![](img/223aea760bce52b872e46ca99b14c6fe_211.png)

The perceptron learning algorithm here， and then I'm going to ask them what their true label is。😊。



![](img/223aea760bce52b872e46ca99b14c6fe_213.png)

![](img/223aea760bce52b872e46ca99b14c6fe_214.png)

So you're the origin Matt you specified we're not using a bias here right oh no。

 I didn't use we're not using a bias term here so that's to make to hityas life very difficult so the decision boundary and weight vector will always be passing through the origin here。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_216.png)

![](img/223aea760bce52b872e46ca99b14c6fe_217.png)

![](img/223aea760bce52b872e46ca99b14c6fe_218.png)

Hi， how's it going， you will be X1， can you hold this plate up very high？



![](img/223aea760bce52b872e46ca99b14c6fe_220.png)

All right， so my first query point is going to be here and if I use I took the algorithm off。

 but my weight initialization is all zeros， which means my prediction for this point is going to be the sign of zero given how I broke ties you will be classified as a positive point so my question to you is are you a positive point？

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_222.png)

Oh， okay， you've already got me once I see。 so what we're going to do is I have made a mistake on a negative point。

Oh gosh， I wore the wrong pants for this today what we're going to do is we are going to draw。



![](img/223aea760bce52b872e46ca99b14c6fe_224.png)

![](img/223aea760bce52b872e46ca99b14c6fe_225.png)

A vector。Rg。The origin to this point， and this is going to be a vector that corresponds to the update that I am going to be making。

 so if I could get you to pass this along back up to our origin there，😡，All right， so。

And good my scissors that I'm also carrying through these oh Jesus all right。

 so all right this is going to be the point， the vector pointing to the negative mistake I made however。

 remember when we make a mistake on a negative point we subtract it from our weight vector and so our new weight vector is going to be this flipped about the origin so what I'm going to have you do is try and maintain the length of this as well as you can I got you here and we're just going to flip it over。

😊，2。

![](img/223aea760bce52b872e46ca99b14c6fe_227.png)

Oh gosh， oh， I'm so sorry， the opposite point here。

 which I guess would be roughly this individual right here。



![](img/223aea760bce52b872e46ca99b14c6fe_229.png)

And so now our weight vector， if you'll also yes， you are going to be doing a lot of holding things。

 we'll also point in that direction， let's pull that nice and tight here and let's also keep track of what our decision boundary looks like as we go shall we so now what we're going to do is we're going to have the decision boundary passing through the origin be a straight line that is perpendicular to this yellow ribbon here？

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_231.png)

![](img/223aea760bce52b872e46ca99b14c6fe_232.png)

![](img/223aea760bce52b872e46ca99b14c6fe_233.png)

![](img/223aea760bce52b872e46ca99b14c6fe_234.png)

Oh good， Matt， you're being such a helpful assistant， Oh yeah， no problem all right。



![](img/223aea760bce52b872e46ca99b14c6fe_236.png)

That you want to really pull back to Curt， this was my job last year。

 so now Matt is getting his just desserts。All right， so after one update。

Maybe like a little more down。One more up。

![](img/223aea760bce52b872e46ca99b14c6fe_238.png)

All right， good enough， let's pull it nice and tight here。We think that looks about perpendicular。

 right， what do we think？And so this is my current belief about the decision boundary。

 how am I doing？😡，Trying to cheat Henry， I don't know。

 I mean trying to cheat it's it sounds like I don't know just making me do this the real perceptron algorithm might not be able to ask。

 how am I doing。

![](img/223aea760bce52b872e46ca99b14c6fe_240.png)

But if we had to offer an opinion， we might say，h okay， okay， not terribly impressed so far。

 if not so impressive。

![](img/223aea760bce52b872e46ca99b14c6fe_242.png)

![](img/223aea760bce52b872e46ca99b14c6fe_243.png)

All right， let's pick someone in this cluster next。



![](img/223aea760bce52b872e46ca99b14c6fe_245.png)

Let's say， right。

![](img/223aea760bce52b872e46ca99b14c6fe_247.png)

Here， perhaps。Ohoops， hang on。啊。

![](img/223aea760bce52b872e46ca99b14c6fe_249.png)

Why don't you hold this up nice and high you will be my second guess and now one of the beauties of this little exercise is that I don't have to do any math here right I can look at what my current belief is。

 I can look at which way the weight vector is pointing and I know I know that you are a positive point hey we got one okay let's see here so I did someone over there I did someone over here maybe I should go。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_251.png)

![](img/223aea760bce52b872e46ca99b14c6fe_252.png)

![](img/223aea760bce52b872e46ca99b14c6fe_253.png)

![](img/223aea760bce52b872e46ca99b14c6fe_254.png)

Like that way， yeah，'s let'ss do someone over here。



![](img/223aea760bce52b872e46ca99b14c6fe_256.png)

是。Oh。See， this is why he shouldn't run the。The path， let's see。



![](img/223aea760bce52b872e46ca99b14c6fe_258.png)

Let's do someone over here so maybe you。

![](img/223aea760bce52b872e46ca99b14c6fe_260.png)

And you hope， oh， no， sorry， not that much。 X3， not x 8， nice and high。 All right， so once again。

 I predict you using this belief to be a negative point。 How am I doing Oh， good， Okay。

 so we're narrowing in on this。😡。

![](img/223aea760bce52b872e46ca99b14c6fe_262.png)

Oh， I know someone over there。So here's a little trick， right。

 because I don't actually know where the decision boundary is I'm。



![](img/223aea760bce52b872e46ca99b14c6fe_264.png)

![](img/223aea760bce52b872e46ca99b14c6fe_265.png)

If I were being honest， I would tell you that I'm randomly selecting these points。

 but I'm actually using a bit of a technique here to try and figure out which points I'm not so certain about。

 which points would allow me to make to gain information about，😡。



![](img/223aea760bce52b872e46ca99b14c6fe_267.png)

![](img/223aea760bce52b872e46ca99b14c6fe_268.png)

![](img/223aea760bce52b872e46ca99b14c6fe_269.png)

![](img/223aea760bce52b872e46ca99b14c6fe_270.png)

My prediction。So say， for instance， this point right。



![](img/223aea760bce52b872e46ca99b14c6fe_272.png)

Here。All right， can I get you to hold up your point nice and high？



![](img/223aea760bce52b872e46ca99b14c6fe_274.png)

I'm going to say you live right on my decision boundaries， right？😡。



![](img/223aea760bce52b872e46ca99b14c6fe_276.png)

Which means according to my tie breaking procedure， or I classify you as a positive point。

 are you a positive point。😡。

![](img/223aea760bce52b872e46ca99b14c6fe_278.png)

![](img/223aea760bce52b872e46ca99b14c6fe_279.png)

Oh， good， good， okay。Let's see here， so we're narrowing in on this。



![](img/223aea760bce52b872e46ca99b14c6fe_281.png)

How about？Someone down here， would you hold this up nice and high？



![](img/223aea760bce52b872e46ca99b14c6fe_283.png)

So my belief about him is a negative point， are you a negative oh， you are a positive point， Okay。

 so now what we're going to do is。

![](img/223aea760bce52b872e46ca99b14c6fe_285.png)

![](img/223aea760bce52b872e46ca99b14c6fe_286.png)

The thing I brought two colors of ribbon， what we're going to do is we're going to hand you one end of this。



![](img/223aea760bce52b872e46ca99b14c6fe_288.png)

And because I made a mistake。Let' sit on a positive point。



![](img/223aea760bce52b872e46ca99b14c6fe_290.png)

Matt is right， I probably don't need scs for this， but regardless。

 could I get you to hold that end of it nice and ta and then。



![](img/223aea760bce52b872e46ca99b14c6fe_292.png)

Thank you。

![](img/223aea760bce52b872e46ca99b14c6fe_294.png)

Yeah， yeah， yeah。 let's let's just do this with our hands here。 Al right。

 so this is the mistake to a positive point that I made。

 So what I'm going to do is I'm going to add that to the end of my current weight vector。😊。



![](img/223aea760bce52b872e46ca99b14c6fe_296.png)

So， let me。Get this end here and you can let go， we're just going to remember the length。

And let me sneak around you here。

![](img/223aea760bce52b872e46ca99b14c6fe_298.png)

All right。Oh very good， all right， so I need you to hold on to that at that end and h。



![](img/223aea760bce52b872e46ca99b14c6fe_300.png)

Let's see here， it was roughly this line here， is there any chance I could get you to move back one seat？

See this works much better when it's not Friday and people come to class and it's really nice and dense here。

 I get you guys to keep pulling that nice and ta here， Alrighty perfect。



![](img/223aea760bce52b872e46ca99b14c6fe_302.png)

All right， and so now what we're going to do is' going to make one more update here。

 which is I'm going to take my weight vector， thank you very much， keep holding those two ends。

 you're going have a fun time here and so now if I add these two vectors together this is my current weight vector and so now we get to get these Ts to earn their keep you have to go sort of all the way up here。

😡，Go on。And reteth all the way down there。We're just going to keep updating our belief to make sure that our decision boundary remains perpendicular to this weight vector。

😡，Keep going。 Keep going。哎呀。Okay， it was a pretty big swing so。



![](img/223aea760bce52b872e46ca99b14c6fe_304.png)

Any think a little bit more， maybe， maybe maybe one more。



![](img/223aea760bce52b872e46ca99b14c6fe_306.png)

For me to tell from this angle， what do you think Matt， maybe one's pretty orthogonal to me， y， okay。

 okay， and so here's an interesting observation。While they're tightening that up a little bit。

 here's an interesting observation x5 was it x5 here x5 nice and high now my previous mistake。

 the point that I had classified as a minus， I'm now classifying as a plus I' have shifted my decision boundary somewhat significantly to try and correct this mistake that I made。

😡，And well， I guess I'm not going to cheat， I guess I'm not going to ask how I'm doing。

 Let's keep going， shall we， how about I feel like I haven't really done much over here。 Let's。

 let's go over here， shall we。

![](img/223aea760bce52b872e46ca99b14c6fe_308.png)

![](img/223aea760bce52b872e46ca99b14c6fe_309.png)

Actually， can everyone hold up their plates if you have one， did I。

 I haven't asked someone down here， good。Let's go maybe down here。



![](img/223aea760bce52b872e46ca99b14c6fe_311.png)

Oh， I did ask someone down here， okay， that's what I thought， someone over here then。



![](img/223aea760bce52b872e46ca99b14c6fe_313.png)

![](img/223aea760bce52b872e46ca99b14c6fe_314.png)

And I think you got， I think did we get that point correct？When we class we did get that point。

 correct， yes。

![](img/223aea760bce52b872e46ca99b14c6fe_316.png)

Maybe you right here， so again， I would classify you as a negative point， how am I doing oh good。

 all right。

![](img/223aea760bce52b872e46ca99b14c6fe_318.png)

![](img/223aea760bce52b872e46ca99b14c6fe_319.png)

1，2，3。

![](img/223aea760bce52b872e46ca99b14c6fe_321.png)

F five， six， just trying to find people where there are actually seats。



![](img/223aea760bce52b872e46ca99b14c6fe_323.png)

Oh， sorry， I'm trying to find。Places where there are actually people so we don't have to move too many of you around。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_325.png)

![](img/223aea760bce52b872e46ca99b14c6fe_326.png)

， let's see here， let's go。

![](img/223aea760bce52b872e46ca99b14c6fe_328.png)

Let's go here， maybe。So。It's pretty close， but I would categorize you as a negative point。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_330.png)

How am I doing Oh okay， so you are a positive point I've made a mistake on a positive point here。

 which let's make one more update。

![](img/223aea760bce52b872e46ca99b14c6fe_332.png)

![](img/223aea760bce52b872e46ca99b14c6fe_333.png)

I get you to hold that。

![](img/223aea760bce52b872e46ca99b14c6fe_335.png)

That's a big update here， big update incoming， all right， so I'll get you to hold on to this end。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_337.png)

All right， so this is going to be the next update to my weight vector so I'm going to do。

 I'm going to tear this right here， get you hold on to that and I'm going to add it to the end of my current weight vector。

 so I'll take this blue end from you。😡。

![](img/223aea760bce52b872e46ca99b14c6fe_339.png)

![](img/223aea760bce52b872e46ca99b14c6fe_340.png)

![](img/223aea760bce52b872e46ca99b14c6fe_341.png)

And hand it， oh， you can let go。

![](img/223aea760bce52b872e46ca99b14c6fe_343.png)

Thank you。I'll hand it to you and that means that other end， let's see。

 roughly maybe the individual with the Yankees hat there。



![](img/223aea760bce52b872e46ca99b14c6fe_345.png)

![](img/223aea760bce52b872e46ca99b14c6fe_346.png)

Oh nice and tight。Yeah， that seems about， right？good enough all right。

I'm going to update my weight vector one more time。

 pass that all the way back up to that individual as well。

 hold on nice and tight all right we got plenty of yellow ribbon right good good okay。

 and one more time for all time's sake。😡。

![](img/223aea760bce52b872e46ca99b14c6fe_348.png)

![](img/223aea760bce52b872e46ca99b14c6fe_349.png)

![](img/223aea760bce52b872e46ca99b14c6fe_350.png)

Well nice and tight please， thank you。

![](img/223aea760bce52b872e46ca99b14c6fe_352.png)

Isn't this what I had before？Veryre close， wow， yeah。2。All right， if this all goes wrong。

 it's because Matt went rogue on me。

![](img/223aea760bce52b872e46ca99b14c6fe_354.png)

Let's see， I guess you will。Yeah。

![](img/223aea760bce52b872e46ca99b14c6fe_356.png)

Maybe a little more down here。What do you think it looks about perpendicular， Yeah。

 as long as he gets yep。

![](img/223aea760bce52b872e46ca99b14c6fe_358.png)

![](img/223aea760bce52b872e46ca99b14c6fe_359.png)

All right， so once again， the thing to note here is that this person that I had previously classified as a negative is now correctly classified to be positive and in the interest of time。

 let's just say this is all the data that I receive， my algorithm terminates。

 how did I do for real this time？😡，那是。Can we do like one more point？



![](img/223aea760bce52b872e46ca99b14c6fe_361.png)

You want to do one more point， okay， u let's see here something close to the margin。

 like something close to the margin so。Let's see here maybe this point right here。

 it looks like I would classify you as a plus point， you want to hold this up nice and high？



![](img/223aea760bce52b872e46ca99b14c6fe_363.png)

That is a plus point。Okay， well， I'm out of plates now， Matt， so I'm genuinely out of data points。

 why don't we just in the interest of time do this by show of hands。

 how many of you are positive points？Oh okay， well I got it on the right side so your I'm like super close your hair is super good and I can tell you exactly I think almost exactly what went wrong Can we show so you're a positive point too Oh right。

 there's a giant gap here and no one satAT here。

![](img/223aea760bce52b872e46ca99b14c6fe_365.png)

Okay。

![](img/223aea760bce52b872e46ca99b14c6fe_367.png)

And so you were kind of missing all of this information and that's。

 I think where we find negative points， hold your hands up。

So it's just like like your air50 degrees off maybe you're a negative point really Oh okay I came very close that I'm actually very pleased with that I think once you see the actual error you did spectacular and so if I were able to make a few more updates。

 I guess maybe somewhere in like area here if we hit one more point here yeah。



![](img/223aea760bce52b872e46ca99b14c6fe_369.png)

So this you're positive， right， no， they they meant they are negatives。

Do you remember I think positive right so well he held his hand up for a negative but okay。

 so this individual here is positive that's right， which means I would have made a mistake which means I would have moved the weight vector somewhere over here maybe and then you would have been exactly right and then I would have been exactly right Which one of you was holding the weight vector。

Oh all the way back there Okay， I would have been close Alrighty。

 thank you guys for playing along hopefully this goes a little better in the afternoon section， but。



![](img/223aea760bce52b872e46ca99b14c6fe_371.png)

Thank you， thank you what I want to highlight is two effects one I did reasonably well。

 we can just get rid of these here， I'll maybe hand them down over to Matt。



![](img/223aea760bce52b872e46ca99b14c6fe_373.png)

![](img/223aea760bce52b872e46ca99b14c6fe_374.png)

I want to highlight two things about this algorithm， one I came pretty close， so game me。

 but also the updates we were making behaved in a very specific way。

 we were always trying to correctly classify the most recent mistake that I was making。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_376.png)

Sometimes at the expense of making mistakes on points that I knew to be。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_378.png)

One class or another right I believe your prediction over here was sort of flip flopping back and forth。

 even though when I first made a mistake on you， I swung the decision boundary to correctly classify you Also if you have a plate bring it back to me at the end of class we'll keep going for right now。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_380.png)

![](img/223aea760bce52b872e46ca99b14c6fe_381.png)

![](img/223aea760bce52b872e46ca99b14c6fe_382.png)

Oh also， I do want to say like here is a well curated example that shows you exactly how this was supposed to go。

 but again I encourage you to flip through this， what you'll see is that you learn a linear separator that perfectly classifies this set of six points just iterating through all these updates here。



![](img/223aea760bce52b872e46ca99b14c6fe_384.png)

![](img/223aea760bce52b872e46ca99b14c6fe_385.png)

![](img/223aea760bce52b872e46ca99b14c6fe_386.png)

![](img/223aea760bce52b872e46ca99b14c6fe_387.png)

![](img/223aea760bce52b872e46ca99b14c6fe_388.png)

All right， so one notable omission and a question that was raised that was quite excellent is how exactly does the decision boundary affect all of this？



![](img/223aea760bce52b872e46ca99b14c6fe_390.png)

Sorry， how exactly does the bias term affect all of this。

 So we just saw an example with no bias again， largely to make sure that we could always pass through the origin here。

 but notably we will have sort of。

![](img/223aea760bce52b872e46ca99b14c6fe_392.png)

Data sets that are not split cleanly along the origin here right there's no sort of single vector or single decision boundary that I could draw that passes through the origin that even really does a good job at classifying this data set and so what we need is some notion of this intercept term and basically how you update your intercept shifts where your line intersects the y axis。

 but that's not very helpful in higher dimensions that doesn't generalize intuitively。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_394.png)

![](img/223aea760bce52b872e46ca99b14c6fe_395.png)

![](img/223aea760bce52b872e46ca99b14c6fe_396.png)

![](img/223aea760bce52b872e46ca99b14c6fe_397.png)

To higher dimensions。And what you should think about。



![](img/223aea760bce52b872e46ca99b14c6fe_399.png)

More concretely is that increasing B moves the decision boundary towards the negative half space。

 What it does is it increases the region， if you want to think about it it's a little tough to wrap your mind around they're both infinite spaces but I'm increasing the amount of space that I categorize as positive because I made a mistake on a positive point。

 that's when I increase my intercept Similarlyly when I make a mistake on a negative point。

 I decrease my intercept term and that shifts the decision boundary towards the currently positive side so here's a nice example。

 you have some weight vector pointing along let's say this diagonal， if I increase sorry if I。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_401.png)

![](img/223aea760bce52b872e46ca99b14c6fe_402.png)

![](img/223aea760bce52b872e46ca99b14c6fe_403.png)

![](img/223aea760bce52b872e46ca99b14c6fe_404.png)

![](img/223aea760bce52b872e46ca99b14c6fe_405.png)

![](img/223aea760bce52b872e46ca99b14c6fe_406.png)

![](img/223aea760bce52b872e46ca99b14c6fe_407.png)

![](img/223aea760bce52b872e46ca99b14c6fe_408.png)

![](img/223aea760bce52b872e46ca99b14c6fe_409.png)

Decrease B， so now B is less than zero， I move it towards the positive points towards the positive side。

 and similarly， if I increase B， I'm moving it towards the negative。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_411.png)

![](img/223aea760bce52b872e46ca99b14c6fe_412.png)

![](img/223aea760bce52b872e46ca99b14c6fe_413.png)

Side that I'm classifying as。

![](img/223aea760bce52b872e46ca99b14c6fe_415.png)

Right right， so here's a high level intuition for how the。😊。



![](img/223aea760bce52b872e46ca99b14c6fe_417.png)

Intercept affects my decision boundary next let's talk about this perceptron algorithm。

 let's try and break it down in a few different ways this is in fact your first poll question and I mentioned this briefly but I want to sort of make this a little bit more explicit now。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_419.png)

![](img/223aea760bce52b872e46ca99b14c6fe_420.png)

![](img/223aea760bce52b872e46ca99b14c6fe_421.png)

So one of the things you might have noticed about this algorithm is that。



![](img/223aea760bce52b872e46ca99b14c6fe_423.png)

All right， maybe it's wrong to say it doesn't have any hyperparameters。

 but it's actually relatively light on hyperparameters。

 maybe you can point to the tiebreak mechanism as a hyperparameter how I predict on the decision boundary but in general this algorithm doesn't have a ton of hyperparameters and so does that make it resilient to overfitting does that make it I guess does not suffer from overfitting is the statement in the question here so let's go ahead and take two minutes talk this over with your neighbor don't select B B is the toxic option here but otherwise let's see what you all think about this。



![](img/223aea760bce52b872e46ca99b14c6fe_425.png)

![](img/223aea760bce52b872e46ca99b14c6fe_426.png)

All right， let's see where you all have come down on this one。Oh。

 this is you know what surprisingly closer than I would have guessed you're coming in at around 38 now now 40% true。

 60% false， lets let's hear from both sides does someone who answered true care to share why they believe this statement is true？



![](img/223aea760bce52b872e46ca99b14c6fe_428.png)

Yeah in the back there if I use all the data， I will always get the same line every time that's actually not true the order of my data can matter。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_430.png)

If I yes， if I get the same data in the same order。

 I will always learn the same decision boundary that's true。

 that doesn't necessarily seem like an argument for why it is resilient to overfitting。

 did someone have a different answer。😡，Yeah。😊。

![](img/223aea760bce52b872e46ca99b14c6fe_432.png)

关不。Yeah， I mean this is sort of the key observation that like I am still fitting to a training data and depending on whether or not that training data is like in some way representative of my test data or if I'm being like too reactive to my mistakes right notice that I was always swinging my decision boundary in such a way that I was making correcting previous mistakes that might be a sign that you're overfitting。

 there's lots of you know potential examples you could give here you know like imagine you have some minus points here and some plus points here。

 while your perceptron might learn sort of this decision boundary。

Whereas maybe if you had sampled a few more points or if you had sampled different points。

 you would have found that the true decision boundary looks something like。

This instead and so depending on how you draw your training data， you could absolutely overfit to it。

 but actually I still do want to hear from the true crowd because I think there are some arguments for why this model is resilient to overfitting yeah right here。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_434.png)

Yep， in the brown。Yeah， I think this is like the best or maybe like a good justification for true that the perceptron is learning strictly speaking a decision boundary。

 whereas when we contrast that with decision trees and can nearest neighbors they can learn sort of highly non nonlinear decision boundaries。

 and so maybe the statement in the question isn't quite right because that doesn't really have anything to do with the hyperparameters。

 but I think in general， the perceptron learning algorithm is maybe more resilient to overfitting than those alternatives。

 but it's not completely you know not a concern in this setting。



![](img/223aea760bce52b872e46ca99b14c6fe_436.png)

![](img/223aea760bce52b872e46ca99b14c6fe_437.png)

![](img/223aea760bce52b872e46ca99b14c6fe_438.png)

All right， great work everyone let's keep going here。

 we're going simplify our algorithm in a few ways coming up here， one this is going to come up a lot。

 it's kind of annoying that we have to treat our intercept term differently from all of the other weights。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_440.png)

In some sense， it's just another parameter that we have to learn and so why can't we just learn it along with all the other ones right so what we're going to do is we're going to prepend a one to all of our feature vectors actually doesn't matter if you put it at the beginning or the end。

 but let's just say for a convention we put it at the beginning here and what that's going to allow me to do is it's just going to allow me to fold this intercept term here at the top of my weight vector。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_442.png)

![](img/223aea760bce52b872e46ca99b14c6fe_443.png)

And now you can see that if I define this theta to be my new sort of set of all parameters。

 weights and the intercept term， I can do theta transpose this modified augmented x and that sort of captures exactly this operation W transpose x plus B I'm always adding in a B because of this prepened one so what that allows me to do is it allows me to sort of clean up this algorithm a little bit instead of having sort of two separate updates。

 I can just say the update rule is theta plus y times the augmented feature vectors。

 the feature vectors with an extra1 added to them。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_445.png)

![](img/223aea760bce52b872e46ca99b14c6fe_446.png)

![](img/223aea760bce52b872e46ca99b14c6fe_447.png)

All right， so now this is maybe the final form of our online Perceptron learning algorithm。

 we'll talk about how we can extend this to the batch setting or the more traditional setting that you all have been considering here's just again trying to really drive that point home preending a one automatically handles the intercept here。



![](img/223aea760bce52b872e46ca99b14c6fe_449.png)

![](img/223aea760bce52b872e46ca99b14c6fe_450.png)

All right， let's again stop。

![](img/223aea760bce52b872e46ca99b14c6fe_452.png)

We've done this exercise a few times， let me just reiterate the assurances I made on Wednesday's lecture that there are lots of right answers here。

 there are lots of assumptions the Perceptron learning algorithm is making to help it generalize。

 what are some of those assumptions， what are some assumptions about the true target function the perceptron makes。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_454.png)

![](img/223aea760bce52b872e46ca99b14c6fe_455.png)

Specifically in the online setting， so let's think about how the online version affects those assumptions as well。

😡，In the back again。The data that we're PD in is not far。

We turning to decision session boundary in a way that we a negative point of we make。

They of a negative height and。two word negative。If we make a mistake on a negative point， yeah。

 we tend to shift our decision boundary towards the negative side。

 I don't quite understand what that has to do with sparsity when we when we say sparsity and machine learning we typically mean like many of the features are zero。

把这的题。嗯。That there's some notion of like。We're getting positive and negative points on both sides we're not in like a。

Like a really skewed setting okay I can see the argument for that I think the algorithm will still work in the limit of like as long as you eventually sample some number of negative points you can get it to work that's an interesting idea though was there something here。

Yeah， truly I don't makes sense okay that were our data points are coming to us like from some like we're not sort of systematically sampling our space。

 I like this idea。Thatて。Here's a big one that I think we need to definitely note down。



![](img/223aea760bce52b872e46ca99b14c6fe_457.png)

The true decision boundary。Is linear？In the features。

I want to hang on this point about ordering a little bit more， why don't I take this one first yeah？



![](img/223aea760bce52b872e46ca99b14c6fe_459.png)

I'm sorry。There are no outliers Oh， this is an interesting。

 this is maybe related to the previous point that。

![](img/223aea760bce52b872e46ca99b14c6fe_461.png)

![](img/223aea760bce52b872e46ca99b14c6fe_462.png)

The true decision boundary is linear。There are no exceptions to this。

Maybe I'll make that like a sub bullet under the previous one what about the ordering matters so like if we do assume that we are not you know making some sort of systematic sampling that we really are getting random samples。

 how did the weight vector react to the order in which I sampled points？😡。



![](img/223aea760bce52b872e46ca99b14c6fe_464.png)

Yeah。Yeah， that it's always trying to fix the most recent mistake。

 let's say I like what you said there， the most recent mistake。



![](img/223aea760bce52b872e46ca99b14c6fe_466.png)

![](img/223aea760bce52b872e46ca99b14c6fe_467.png)

Is the。Most。Relevant。Rella event。All right， so what we're saying here is that despite all of the previous knowledge I had about the earlier misclassified data points。

 as long as I'm updating my weight vector to improve， not always correct。

 but improve my prediction on more recent mistakes then I'm making the optimal update。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_469.png)

Now I think there's you know maybe some justification for that and some justification against it like you might want to remember previous data points。

 but who knows maybe you care about getting like the next prediction right and maybe you believe the next data point will look more like earlier data points or more like more recent data points than previous data points。

 anything else here， anything else about the ordering。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_471.png)

Anything else in general？Yeah。还有吗。Yes that's exactly right。

 I think we saw that in our example with this individual x5 here。

 their prediction was flip flopping between plus and negative as we were adding new as we were updating our weight vector again。

变的话之 that。Is that a sign that it's overfitting， that's an interesting interpretation。

 maybe we're overfitting to more recent data points， but the fact that we can make mistakes。

 the fact that we don't always get zero training error is maybe some argument that it's not overfitting。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_473.png)

I'll just leave this one more bullet here because I think it was sort of touched on earlier that in some sense order。



![](img/223aea760bce52b872e46ca99b14c6fe_475.png)

Matterters。This is maybe like a bullet above the most recent mistakes。

 but yeah order matters in that if I had observed or sampled my data points in a different order。

 I would have had a different sequence of updates that could result in a different decision boundary now if I always get the points in the same order I'll always learn the same decision boundary but order matters。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_477.png)

Okay， so again， I want to highlight this back here。

 there are lots of true statements about the assumptions that my model makes and some of these may be more or less appropriate to your specific task so it's important to think about like the implications of I don't know。

 I would say especially this decision here about whether or not that's like appropriate for say like a recommender system versus like a medical diagnosis prediction machine。



![](img/223aea760bce52b872e46ca99b14c6fe_479.png)

![](img/223aea760bce52b872e46ca99b14c6fe_480.png)

Oh。Was this on my slides？

![](img/223aea760bce52b872e46ca99b14c6fe_482.png)

Was the okay good， good。 Sometimes I do that Sometimes I like I hate that when I like ask you a question and the answer is like right there。

 no one wants to say it because like everyone's kind of looking at it like yeah。

 okay this is what I had。 it's the decision boundary is linear and recent mistakes are more important than older ones。

 sorry about this， I'll fix this in post So here is the online version of the algorithm but I want to stress that you can apply this to our traditional machine learning setting what we would call the batch setting where you're just sort of giving all of your data points all at once and you can do that by just sort of shuffling your data or assigning your data points in arbitrary ordering。

 say from X1 to XN and then while you haven't converged just loop through all of your data points just go through them in order maybe you want to shuffle them in between but regardless as long as you haven't converged just keep doing the online updates。

😊。

![](img/223aea760bce52b872e46ca99b14c6fe_484.png)

![](img/223aea760bce52b872e46ca99b14c6fe_485.png)

![](img/223aea760bce52b872e46ca99b14c6fe_486.png)

![](img/223aea760bce52b872e46ca99b14c6fe_487.png)

Excuse me， and so my question to you all is what does convergence in this setting mean。

 what are some possible criteria for convergence？😡。



![](img/223aea760bce52b872e46ca99b14c6fe_489.png)

Yeah， right here。Yeah， I think this is the easiest one。

 certainly like if our data is linearly separable， if we can find some line that separates it。

 well once we find that line， we're never going to make another mistake so we're never going to make another update and we can sort of check that by saying if I loop through my entire data once。

 and I don't make any mistakes well then I've converged any other possible definitions of convergence。

 yeah。😡。

![](img/223aea760bce52b872e46ca99b14c6fe_491.png)

say time。Yeah， that's exactly right， maybe I'm like keeping track of like the number of mistakes I make in some loop through my data。

 that's a little dangerous because any single update could dramatically change how many mistakes I make from one iteration to the next。

 but it's definitely an idea， anything else。欢迎。I love this answer， use a validation data set。

 measure some sort of validation error and see if you can find not just， you know。

 maybe in the past five updates， but like if you've。



![](img/223aea760bce52b872e46ca99b14c6fe_493.png)

Found a minimum validation error and all subsequent updates just make it worse or they don't make it better。

 let's say then maybe that's a good place to sort of revert back to and stop there one more idea。



![](img/223aea760bce52b872e46ca99b14c6fe_495.png)

这这对。Yeah， absolutely you could look at maybe like the magnitude of your weight vector because you'll note that like。

Given the way that we're doing these changes， you can sort of argue that like the weight vector might keep growing and growing and that smaller and smaller updates are actually being made to it。

 so that's an interesting observation。All right， here's your second poll question。

I confess this is maybe an artifact of a bygone era。

 but nevertheless it's an interesting idea that I want you all to think about。😊。



![](img/223aea760bce52b872e46ca99b14c6fe_497.png)

Oh hey I changed up the options on you just to keep you on your toes A is the toxic option instead of B this time。

 but again true false I want you to think about how you can express your weight vector W let's say after convergence at the end of the Perceptron learning algorithm so yeah once again let's take I don't know two minutes here and then we'll reconvene and see what you all have to say。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_499.png)

![](img/223aea760bce52b872e46ca99b14c6fe_500.png)

![](img/223aea760bce52b872e46ca99b14c6fe_501.png)

![](img/223aea760bce52b872e46ca99b14c6fe_502.png)

You know， it'd probably be too obvious if we planted Ts where I needed points to be。

 like you would just be like， oh。What is Rashift doing sitting over there？Anyway。

 just an idea for next time。

![](img/223aea760bce52b872e46ca99b14c6fe_504.png)

You should plant volunteers， that's what we should do。

 You should get like some number of you guys to sit strategically。

Anyway let's reconvene this one is much more compelling 1% of you have selected a don't do that 90% of you have selected B and 9% of you have selected false let me maybe ask the more direct question if this statement is true what do the values C1 C2 all the way up to CNN。

😡，Ohhu should probably be an N instead of an M there。 What do those values correspond to。

 How can we in words interpret them， Let's go。

![](img/223aea760bce52b872e46ca99b14c6fe_506.png)

![](img/223aea760bce52b872e46ca99b14c6fe_507.png)

Now， let's go here。Right， upset。Okay， so the assertion here is that this should be one。

0 and negative one， I like the spirit of that answer。

 but I think we're maybe missing a little bit from that anyone care to build on that。



![](img/223aea760bce52b872e46ca99b14c6fe_509.png)

Yeah， right here。That算。So what should it be？啊，要得。你个发块。廿一十月。That's exactly right。

Multiped by the sign of itself So if it's negative。

 it's the number of times that you misclassified it and it's a negative point， if it's positive。

 it's the number of times that you misclassified it and it's positive。

 so this is some counter for the number of times that you misclassified it Now when I say that this is some artifact of a bygone era it turns out that the fact that you can express W in terms of X's means that when I compute W transpose X this is like C1 X1 transpose X plus C2 X2 transpose X so on and so forth and the fact that my predictions only depend on these dot products between feature vectors is relevant there are cool tricks that you can do with that fact but those are outside the scope of this class so we're not going to talk about。

All right so I don't know why that plus is still there I want to leave you all with a very interesting result I think like I mentioned when we were talking about KNNs。

 one of the underappreciated facts one of the underappreciated aspects of many machine learning models especially these nice simple ones is that we can make some sort of nice theoretical guarantees about them and so that's what we're going to use these last five minutes here for we're going to talk about a theoretical guarantee on the number of mistakes that your perceptron learning algorithm makes so remember the whole premise of online learning is we're trying to minimize the number of mistakes our algorithm makes through a particular data right and so we'll say that a data is linearly separable I've kind of been using this term without defining it but I think it's intuitive it's linearly separable if I can find some line or hyperplane that perfectly classifies my dataset。



![](img/223aea760bce52b872e46ca99b14c6fe_511.png)

![](img/223aea760bce52b872e46ca99b14c6fe_512.png)

![](img/223aea760bce52b872e46ca99b14c6fe_513.png)

Here's a maybe more interesting idea though， given a linearly separable data set。

 there are actually infinitely many lines， infinitely many hyperplanes that I can draw that perth well。

😡，I think that's true maybe not well regardless， there are in many general settings。

 infinitely many lines that I can draw that perfectly separate this data。

 I can just sort of pivot them you know infinitesimally small in the region where they're separated by。

However， we might intuitively like linear separators that do a better job of separating my data points what do I mean by that well imagine you have this linearly separable data set right here are a bunch of linear separators there's something like this there's maybe something like this and then there's maybe something like this and I think maybe intuitively many of us prefer that last option that sort of bisects them as opposed to you know these decision boundaries that get maybe like unnecessarily close to one data point or another right and we can quantify that using this notion sorry now let me get rid of these lines using this notion of a margin which we'll call the distance between linear separator and its nearest。

😡，Data point in the data set and so here， I guess these two points are equiistant from this linear separator and so this margin we would call gamma。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_515.png)

All right， so here's the statement of the mistake bound。

 which is if the data points seen by the algorithm are linearly separable。

 crucially they need to be linearly separable， and then have some margin， oh sorry。

 they need to be in a ball of radius R， this is not super hard because as long as your feature values are finite。

 there's always going to be some R that holds all of your data points。😡。



![](img/223aea760bce52b872e46ca99b14c6fe_517.png)

![](img/223aea760bce52b872e46ca99b14c6fe_518.png)

![](img/223aea760bce52b872e46ca99b14c6fe_519.png)

And crucially， if they have a margin of gamma that automatically implies they're linearly separable。

 if they were not linearly separable， I wouldn't be able to find some decision boundary with any margin at all。

 so given that they have some margin they're linearly separable and I don't have any you know infinite feature values。

 then the algorithm makes at most this many mistakes are over a gamma squared。😡。

What do we interpret from that well， consider the batch learning algorithm what this means is that as long as my training data is linearly separable。

 eventually I will converge。😡，I think under all of the definitions we gave。

 eventually I will find some linear separator that has made the upper bound of mistakes and will thenforth make no more mistakes and so under many of the definitions that will mean we converged in some finite number of steps of course not all data sets are linearly separable and so this is maybe a bit unrealistic but still it's a nice guarantee that we can make under certain assumptions。

😡。

![](img/223aea760bce52b872e46ca99b14c6fe_521.png)

All right and then the last two slides I have here are hopefully review for many of you but it's just computing the equation for the distance between a plane and a point this generalizes to sort of arbitrarily many dimensions but here's the big takeaway this last result here is how you would go about computing the distance and then you would use this you would minimize this to find the margin of your data set All right so I'll leave you all with this have a great weekend everyone and I will see you all back here on Monday。

 please don't forget about your homework and you know what don't tell any of the next class about what's about to happen because I want them to be surprised too。



![](img/223aea760bce52b872e46ca99b14c6fe_523.png)

![](img/223aea760bce52b872e46ca99b14c6fe_524.png)

![](img/223aea760bce52b872e46ca99b14c6fe_525.png)

![](img/223aea760bce52b872e46ca99b14c6fe_526.png)