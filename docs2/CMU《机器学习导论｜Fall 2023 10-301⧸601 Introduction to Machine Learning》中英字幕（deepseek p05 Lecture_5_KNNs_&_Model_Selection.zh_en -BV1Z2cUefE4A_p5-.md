# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p05 Lecture_5_KNNs_&_Model_Selection.zh_en -BV1Z2cUefE4A_p5-

Everyone， we're going to go ahead and get started for today。

 so today we're going to wrap up our discussion of KNNs。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_1.png)

As you might recall， Matt left a few things unsaid。

 so we're going to finish that up and then talk about one of the most like fundamental problems in machine learning。

 which is like，Figuring out what model to use， we're going to teach you about a ton of models in the coming months and a very natural question is how do you pick between them？

 So we're going to cover that in the back half of today's lecture。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_3.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_4.png)

Geez， a whole host of announcements reminders， so reminder that homework two is do this Friday and just because the wheel keeps turning homework three will also be coming out on Friday homework3 is a little special well relative to homeworks 1 and2 at least it is a written only homework so there is no programming component you get a little bit of a break from that the flip side is you can only take two late days on homework 3。

 the reason is that we want to get you your feedback on homework 3 in time for you to study for the exam I will have a lot more to say about that shortly but this is the reason why we change our late day policy for homeworkworks3。

6 and nine。Relatedly， I have a very important scheduling note。

 I hate to drop this on you on such short notice， but as we were preparing homework three for you all。

 we realized， hey， it would be good if we taught you the stuff you needed to do homework three first。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_6.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_7.png)

Funny so we're going to have lecture on Friday instead of recitation that homework3 recitation is being bumped to next Wednesday。

 this is going to be a normal lecture with participation polls so please do your best to attend I know for some of you that might be difficult you might have conflicts with our otherwise optional recitations but do your best if you can make it I don't want to spoil too much but I promise it'll be fun。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_9.png)

Okay， some Q&A。😡，So we get this question a lot right around now， which is man， homework two is hard。

 homework two is sort of fundamentally different than homework one and it might be a challenge for some of you right so the question is where can I turn for help？

And let me start by saying it always makes me really sad to hear this like that's not my intention。

 it's not my intention to make your lives difficult。

 it's not my intention for you to feel like any stress about our homework assignments。

 like really we hope that these are like formative learning experiences for you all。

 but we get it grades matter and so you know。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_11.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_12.png)

We're really glad that you're asking this question or you some of your peers。

 whoever it might be this hypothetical student， we're very glad that they're asking this question because you know we and I really do mean this in the royal sense。

 the royal we here we want to help you right R Ts R Ts are actually very invested in helping you they're always sort of staffing office hours and frankly I think they welcome the challenge of having lots of you attend their office hours so do go if you can you know we would love to help you normally there's two of us I guess Matt had some childcare emergency this morning normally there's two of us so there's one of us able to take your questions after lecture I'll do my best and in general you know this is why we do this job we love to teach you guys things we are also somewhat maybe too diligent on piazza maybe our Ts are too diligent on piazza I'm not that diligent on piazza but in addition。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_14.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_15.png)

this your peers for the most part would love to help you looking a little bit ahead after exam one。

 we'll probably put together some sort of peer tutoring system as we have done in previous semesters and it's always like really heartwarming to see how many of your peers want to help you。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_17.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_18.png)

That being said， we would not love it and again I really do mean this in the Royal we very。

 very much so we would not love it if you violated our academic integrity policy by breaking the collaboration rules that we laid out on the first day of class so again。

 I want to stress these two bullet points here， you must always write your own code from scratch and a good way to make sure that you're collaborating appropriately is to work together on some sort of impermanent surface like these multiplying whiteboards。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_20.png)

I'm pretty sure we only had one on Monday， you can work at one of these impermanent surfaces。

 but when you're done， erase everything， take no pictures and try your best to do this on your own。😊。

All right。Let me stop here， are there any logistics questions before I move on to content？😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_22.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_23.png)

Yeah， said the word exam。Yeah， I did。We'll talk about it probably next week。😡，And。

You do know we have exams in this class， right that's not like the first time， okay。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_25.png)

All right， so where were we on Monday Matt had sketched out some sort of pseudocode in the style that we've been doing in this class with a train and predict method for the one nearest neighbor model and we talked a little bit about how it's kind of odd the training procedure is just storing data it's like the memorizer it's kind of memorizing the data but how it uses that stored data differs in that it's trying to do some sort of geometric similarity computations and that gave rise to this notion of a decision boundary in some real valued feature space。

 we can actually plot figures like this that tell us how our classifier would predict every possible input so here the red shaded area would be predicted as negative by our classifier and the blue shaded area would be predicted as a plus or a positive。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_27.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_28.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_29.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_30.png)

Poin。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_32.png)

So relatedly， I want to start this morning by getting you all warmed up。

 I think 930 is a ridiculous time to have class anyway。

 and so let's spend the first few minutes thinking about this problem This problem is in fact your first two poll questions so go ahead and pull open the poll at M let me write it down here Okay so you've forgotten it's at M course。

 org or you can find the link on the。😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_34.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_35.png)

Schedule page。And so my questions to you are thinking about the two kinds of models we've。

Discusst to date。Can you achieve zero training error using a one nearest neighbor model and can you achieve zero training error using a decision tree classifier on these two data sets。

 and we want you to sort of sketch out the decision boundary if you don't have some sort of device that you're taking notes on。

 break out some pen and paper and try and do your best to copy these figures。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_37.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_38.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_39.png)

Of course， here are your options， A for both of these polls。A is yes。

 B is no and C is both yes and no， which is clearly the ridiculous answer here All right。

 so let's take I don't know， five minutes， talk to your neighbor， try and figure this one out。

 try and convince them that you're right and then we'll reconvene and see what you all have to say about this。

So I was like what's going on outside， it's like really loud guys know there's a career fair going on right now。

God， so glad that part of my life is well over for now， I guess anyway。

 let's reconvene and see what you all have to say about this so does anyone who cared to answer well。

 let's just ask it open endeded does anyone care to share what they came up with for poll question one。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_41.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_42.png)

Yes or no， yeah， all the way in the back， nice and loud， Yes， all right， and why is that？



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_44.png)

You can go down here around the of a circle。Ooh， interesting， so I could draw a circle。

 is that the decision boundary that a K nearest neighbor or a one nearest neighbor model would learn？

What do we think？Like a perfect circle like this。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_46.png)

Okay。More jagged， right， it would be some sort of。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_48.png)

Like weird polygon shape consisting of line segments， right this is what we discussed。

I guess maybe there's like a little bit there and something like this and this here。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_50.png)

Where， you know， you would draw this vnooid diagram and then shade in the corresponding areas。

 So here， the stuff on the inside of these red。Shapes I'm just going make this one a diamond the stuff on the inside of these red shapes would be classified as negative the stuff on the outside would be positive and so to go back to the actual question here the answer is in fact yes we'll talk about why in just a moment but for the one nearest neighbor model this is what the decision boundary well some approximation of what the decision boundary would look like give have an answer for two is that what you're jumping at。

😊。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_52.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_53.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_54.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_55.png)

Okay， hold on to that for right now， does anyone care to share what they got for two？Yes or no。

 and then the decision boundary or an explanation。Yeah， right here。

It's because if we decide like to spread on any one of the attribute which like say X one。

 see that data and sub that we cannot agree any that in any of way we。I like this assertion。

 so the assertion here is that if we make one split on either x1 or x2。

 we cannot perfectly classify this data， and so the statement you're making here is can a decision stump classifier achieve zero training error to which the answer is no。

 but that's not the question here。Yeah。We said yes。

 because you could so once you classify on one axis you made like a rectangular split but then you can split the next rectangle into two pieces and you can kind of there it and you capture each point in a single product that's exactly right and so what would your decision boundary look like。

ofrian like painting would be monrian and like anything， I love this answer。

It might look something like。Like this。Okay。Sure， I think this is absolutely a possibility。

 It's a bit odd。 It might be more sensical to connect a few more of these line segments and have a slightly fewer splits。

 but I think your answer is definitely a valid one and you know depending on how you broke ties or what youre splitting mechanism was you absolutely could end up with these like very infinitesimally small boxes around one class or another。

 frankly， like I could have drawn these boxes the other way and said the stuff inside the blue is positive so on and so forth。

 So regardless， the answer is yes， and the crucial the crucial observation that I want you all to take away from this exercise is that the decision treat。

😊，Decision boundary is made up of axes parallel lines。

 so either horizontal or vertical line segments， this is because of the nature of the splits that we're making so the splits here look something like X I less than C or X greater than C depending on how you want to structure your splits here。

 and so this is always going to give you axes parallel line segments whereas the decision boundary can learn these sort of arbitrary diagonals。

😡，All right， what questions do you have about this before I move on？Yes。

 are we assuming that you can split on multiple times Yes。

 this is absolutely the case when you have real valued features that even after you've split on them once。

 they still have some information， they still have some mutual information to provide about the labels。

Yeah。😊，that case would be value think the criteria in that case for value data would depend on。

That's exactly right You would choose different values of C The question that I think Matt posed to you all yesterday was how would you go about choosing which values of C to compare do you have to compare all of the infinitely many values of C and the answer is no will again leave that。

😊，As a slightly open ended exercise for you all。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_57.png)

Oh， hey， I love it when the answer is just on the next slide。 Yeah。

 so it turns out the one nearest neighbor model always can achieve zero training error because。😊。

I can't tell you how many times I get asked this question。For the end time。

 a data point is always its own nearest neighbor in you know Euclidean space。

 depending on your distance metric， the closest you can get to yourself is right on top of you。

 that is a zero distance， so data point is always its own nearest neighbor。W hang on， wait a minute。

 always achieve zero training error。Is this a good thing， yeah？



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_59.png)

Sure that's right， yes， yes。I will say we don't care if you get the right answer as long as you don't get the toxic answer。

 but I understand that you may want to。Yeah， yeah， absolutely。For the first question。

 the one year's paper like it seems like there's two different boundaries so if you just sleep with one neighbor and not another like like if you have two roots that are very far away from each other。

 you have one neighbor， how would it able to distinguish and be？

Like in the minus if' not like we have1 nearest standards we want and have one for bus that way。Okay。

 you're jumping ahead a little bit， you're thinking of k means， which is a similar。

But a fundamentally different problem。 So we'll get to that in like。Two months。

 so hold on to that thought for a very long time I'm going to remember no， okay， so yes。

 the answer to both of these is yes， thank you for highlighting that。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_61.png)

All right， so always has zero training error。This should send off alarm bells in your brain。

 what is this indicative of？Yes， altogether overfitting great answer。

 This is indicative of the nearest neighbor model's liability to overfit to training data。

 So let's talk about what we can do here。 Well， here's a bit of a silver lining or maybe a positive spin on this it turns out there's this very nice theoretical result。

 It's a very classic result。 It's quite old much older than me much older than Matt。

 but who knows this is a very famous result that says the generalization error of the or sorry the true error rate of a one nearest neighbor model approaches basically the best that you could possibly hope to do as the amount of data you have increases So there's a lot of good intuition in this theoretical result we're not going to prove it。

 The proof is not too difficult if you do want to review this paper but it's outside the scope of this class Instead the intuition here is twofold one as you get more data。

Become more resilient to overfitting this is a really great intuition that as you get more data。

 you're allowed to use these sort of more complex models。

 these models that give you sort of ridiculous looking decision boundaries because the increased exposure to training data in the limit of infinite training data will tell you what the right decision boundaries is here。

😡，The other interpretation that comes straight from the paper。

 I like it's a bit pity you can think of half of all the useful information for this classification task existing in whatever the nearest neighbor might be and again this makes a lot of assumptions about the kinds of problems you're learning you need some notion of like continuity and some notion of well it needs to be a binary classification problem。

 but nevertheless this is a very nice takeaway about the one nearest neighbor model however。

 I suspect many of you are maybe screaming in your heads why would we ever just stop at one neighbor and this is the you know question that we left off Monday's lecture with I think when we were doing that little exercise with the folders many of you intuitively were using while certainly more than one neighbor however many neighbors you were considering is maybe up to your own personal judgment regardless。

If we only use one neighbor， we're just throwing out information。

 we're throwing out a bunch of the other useful classification information in our training data set。

 and so that gave rise to this K nearest neighbors algorithm， again。

 the training method looks a lot like the memorizer we just store the training data。

 but now instead of looking at just a single nearest neighbor。

 we look at what the majority vote amongst the K nearest neighbors is。😡，All right。

 so here's how you might express that pseudocode in words。😡，And you know。

Here's another question I get a thousand times in various contexts it's already come up you know like in a half different ways in the decision tree learning algorithm and I'm tired of answering this question so let me open this up to you all turns out in a K nearest neighbor model you can get ties you can get ties if you do something stupid and choose an even value of K but even if you don't choose an even value of K if you have a multiclass classification problem say there are three classes if you choose K equals3。

 you can get a tie so we need to think about general ways that we can break ties in these K nearest neighbor models so let me open this up to the floor what do you all think about this what are some possible ways that we could break ties here。

you weight oh， I love this answer， this is a great one we can take a distance。😊，Waited。Majority vote。

靓妹。All right， what else？这个。Ooh， I like this one。And thumb number， maybe one。Some number。Of neighbors。

What else？😡，没。We wait the weigh the points by the rent。We wait the points by how， oh， interesting。

 So this is rank weighted as opposed to distance weighted majority vote。 I like this suggestion。

 So now we don't care sort of how close or far they are。

 We care more about the closest one than we do about the furthest one。 I like this answer。

 That's a good answer。😊，What else？Yeah， oh hey， that's not a terrible approach。

 it's certainly more efficient than some of these alternatives。Randomly。嗯。

Find the average distance to each god within the neighbor and find that who was couch。

I think that devolves into distance weighted。I could be wrong。

 but like I think you're just scaling distance weights by some。Average by some like constant factor。

I like the idea， though。I think I had one more in here。

 maybe a simplest one yeah yeah well okay that's related to the second one。

 we can take a majority vote in the entire training data set that's add K or n minus K nearest neighbors add all of the nearest neighbors yeah sure。

I guess break ties consistently or well， yeah， sure， we'll say consistently somehow。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_63.png)

I think the one that I had that isn't among these suggestions， I'll just give it to you right now is。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_65.png)

支。Use a different。Distance metric。And I guess if you were being like。

Very generous with how you define some number。 If you let some number be negative， for instance。

 you can also break ties by using fewer neighbors occasionally。

 So these are some really great suggestions and they are all viable ways of breaking these ties。

 And so we'll talk about how you pick between these different ways of breaking ties because that's always the next question I get。

 So we'll talk about how to break these ties between our tie breaking methods shortly。😊。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_67.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_68.png)

Instead， what I want to do right now is give you a bit of an example of these how this KNN model behaves on this Fishsure IIS data。

 I want to apologize in advance the color scheme here is not great both because the blue and the green look very similar and they're all sort of mixed in together and I know some of you might struggle with the y equals zero class and the y equals two class so I apologize in advance hopefully the next few slides make this process a little more clear。

 but what we're showing here is the Fishsure Iris data set for Monday with all three classes previously we were just looking at the y equals zero。

The Iris Satosa class and the y equals one， the Iris Virginiaa class。 now we have the。

I don't know what the third class is called Now we have all three classes here right And so what do we get right when we look at this one nearest neighbor model。

 the number to keep your eye on， by the way， as I flip through these slides is up here。

 when we set K equal to one， we have this frankly comically ridiculous decision boundary right there are just these like weird。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_70.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_71.png)

Islands， let me， change colors here because that's just not gonna help。 We have these weird。

 like islands of green in this sea of blue that are saying like， oh， you know。

 if you're at this point here， we think you're a green。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_73.png)

Iris， but you know if I'm even slightly wrong in my measurement。

 like I you know have this hard time physically measuring what your sL width and sL length are。

 if I'm just sort of slightly wrong Oh you're a fundamentally different species of iris which I think is a ridiculous belief it doesn't capture sort of what we believe reality to be like right And so this decision boundary is maybe overly complex fitting outliers in our data set fitting some sort of statistical noise as opposed to the signal that we actually care about learning and so let's see what happens and again。

 the number to keep your eye on is up here as we increase k from one to two well that didn't do much better some of these islands went away。

 but we still have these little pockets of green let's keep going shall we K equals3 K equals5 getting a little better and we have this large sort of like。

Hut through the blue region at K equals 10 and as we keep going to like oh K equals 30 looks pretty good。

 maybe one more K equals 50 right， this might be the decision boundary that you as a human would draw for this data set right you have sort of this nice split between the red and the blue points and then you know you try and split the difference between these green and blue points somehow looks like you know there's this。

😊，Group of green points here and there's this group of blue points there and you might want to try and bisect those somehow so like this is actually a pretty reasonable approach or a pretty reasonable value of k。

 it gives us a relatively clean decision boundary that we might believe to be the true signal in the well hang on what。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_75.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_76.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_77.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_78.png)

Oh。Oh dear， what happened here？Where did I go wrong？Yeah， just of majority vote。

 That's exactly right。 This is a good observation。 There are exactly 150 data points in this data set。

 and I actually think there's a three way tie between 50 red points。

50 blue points and 50 green points。 And I just chose blue somewhat randomly to break that tie。

 And so yes， this。😊，Classifier， this sort of KNN model can devolve into a majority vote。

When you get to large values of k， frankly， you probably don't even need to get all the way up to K equals n like the behavior is probably very similar up to。

 you know K equals some value close to n here and so what we've just observed is some sort of tradeoff or some sort of。

😡，Excuse me。😡，Sliding scale from the extremes of overfitting when k equals1 to these extremes of underfitting when k equals n and again we'll revisit how to navigate that trade off in the back half of this lecture but before we do that。

 let me just stop here， does everyone sort of follow the intuition about there being some sort of sweet spot for the value of K let me ask a more direct question what questions do you all have at this point。

😡，Yeah。Oh this is a really great question if one of your classes is severely underrepresented。

 then yes， like they could easily get sort of wiped out from this decision boundary entirely if you set k equal to some large value and that's definitely a problem in what we would call imbalanced data sets you might want to consider what the largest value of k you should reasonably use is based on the minority group or you might reasonably argue that yeah。

 the majority vote classifier in imbalanced data sets is a pretty good model like you know 99% of your data points behave one way。

 I not just predict 100% of them behave that way。😊，Anything else here？Whats the time Oh hey。

 that's a great question and I think。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_80.png)

it's two slides away so hold on to that thought let's start with this question so my question to you all is what is in words。

 what do you believe the inductive bias of a KNN model with Euclidean distance is I think before I have you jump in here。

😡，Inductive bias is a very tough idea to explain。The way that I like to think about it is what assumptions does the model make to help it pick the right classifier。

 help it pick which decision boundary it should use to hopefully generalize well to unseen data points and the other aspect of inductive bias that I want to highlight here is that there are lots of correct answers。

 There are lots of different assumptions that every model makes。

 and so it's sort of hard to succinctly summarize them all in one sentence so I have an answer it's behind a white box here。

 but I want you to think about what assumptions the model is making that help it to generalize Like I said。

 there are lots of right answers let's hear from you all What do you think about this。

 What are some assumptions that the KNN model makes yes。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_82.png)

That's exactly right close points should share similar labels that is one assumption that this model is making what else？

Think about the weird thing that I specified here， what behavior is inherent in the Euclidean distance model Yeah。

 variables should be the same change in variable should be the same I like this idea what was I think there was a hand in the back。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_84.png)

No， okay， anything else？Yeah。😊，Yeah， this is the fundamental assumption of the Euclidean distance that like I can be on one side of the point or the other at anywhere in the like hypersphere in my you know D dimensionsional space I treat equally and this is related to the suggestion that was brought up earlier and this is what I have behind the slide that the features are all equally weighted in some sense。

 I don't care if you are you know in which dimension in which direction you are far away from my data point they will all affect my prediction equally and that can lead to some。

Well， some strange behavior right so imagine you have this you know Iis data set。

 this cartoonish depiction of the iris data set with you know sepL width and sepL length measured in centimeters right now。

😊。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_86.png)

If you had that same data set， but for some reason， you decided to measure these d ss in meters。

 well what you're doing is you're reflecting the exact same information but because of how you compute Euclidean distance you end up with fundamentally different nearest neighbors and correspondingly fundamentally different predictions I think if you work it out like this point is now a lot closer to the red points whereas before it was maybe closer to the blue points so your predictions here would look fundamentally different depending on feature scale。

 feature scale can dramatically influence your model here and you might argue that this is sort of an undesirable behavior。

 you might argue that this is what you want but regardless a very common technique in many machine learning models is to do feature normalization or feature standardization that is to bring all of the features into a similar scale。

Before making predictions， so that's a very common approach。Like I said。

 there are lots of correct answers to this。Or you know。

 maybe there are lots of different ways that you can phrase this idea here。

 let me again stop what questions do you all have here？Yeah， right here。

Like do you start with one getting point at random and then just find air late and that one has a least one that you find the next one that's closest or how do you determine what a starting point is or determine like whether two points one on the same class this is a good question how do you determine like which？

Data point to compute the distance to first， I would argue that like a naive implementation。

 you have to compute the distance between your query point and every data point just to make sure you don't miss some nearest neighbor that's the naive implementation there are much more clever implementations we'll talk about well I'll briefly mention one in just a second。

 but basically you can use data structures cleverly to help narrow which data points you actually need to measure the distance between。

😡，So we'll touch on that in just a second great question though， is there another one over here？



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_88.png)

All right， so let's break this down in terms of some pros and cons。

 I think this is a helpful way to think about some of these early models that we've been talking about。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_90.png)

Much like the decision tree， a KNN model is relatively intuitive。

 you can describe what it's doing in one short sentence and you can justify its predictions to people without machine learning exposure relatively easily as well。

 you know I think that this person has heart disease because they share many of the same features as this other person who had heart disease。

It has this nice property of not having any training time。

 we're going to think about lots of complex models that require you know long periods of time to train we don't have that issue here and it has these nice theoretical results which again I think is underappreciated。

 many of the models that are used in practice today don't have any of these nice guarantees。😡。

Of course， these theoretical results stem from a whole host of assumptions that are maybe unrealistic in some cases。

 but regardless， if we can make some assumptions， we can get nice guarantees。

So what are some tradeoffs here， well， the no training time doesn't come for free。😡，It means。

At prediction time， we have to pay the piper。We are not doing any work upfront。

 but when it comes to computing the prediction of some data point。

 well there are two factors when you think about computational cost。

 you think about storage and you think about time you need to hold all of your training data in memory which can be sort of very expensive in you our modern world of big data right you need to be able to refer to each data point to compute the distance to it。

 and then you finding these K and nearest neighbors。

 you know if you use some naive sorting algorithm， if you compute the distance between your query point and each data point and then you use some naive sorting algorithm。

 this ends up looking like large some large computational runtime。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_92.png)

But here's what I mentioned earlier， you can make clever use of something like a Kd tree which basically groups points into different subsets that are all close to one another and that way you can eliminate the need to search or compute the distance between some portion of your training data set the way to think about this at a high level is you're doing more training work you have to organize your data into this Kd tree object but once you've done that you can get more efficient predictions you can get more efficient test time costs so there's some inherent tradeoff here between how much you care about not training versus how much you care about slow predictions you can also this is a fancy way of saying make random guesses at what the nearest neighbors are if you like do some presorting of your training data you just kind of like。

Do an insertion and then look around the query data point。

And here's the last one which we mentioned in the inductive bias bit。Unfortunately。

 or maybe appropriately affected by feature scale， we can address this with normalizing or standardizing our features。

😡，All right， what questions do you all have at this point？

So way we've introduced this so far no training is it possible to kind of realize the points have training that's exactly what I was getting at with this notion of a KD tree you're just sort of putting them in a data structure that groups them based on how close they are to each other and that way when a new point comes along。

 you don't need to search in regions of the space that you know to be far away。All right。

 I know you all have this question。 I told you not to ask it。 I told you we were gonna get to it。

 and now we're gonna get to it， which is how on earth do we go about picking K right。

 do I have to plot a bunch of different decision boundaries and just sort of eyeball which value of K looks good to me That's a bit unsatisying。

 It's a way of selecting K for sure， but maybe not the best way And so let's just。

Revisit what exactly K is and to do this I'm going to introduce some terminology。

 but there's a bit of a caveat or a bit of a warning here we're going to talk about model selection every value of k corresponds to a different model we'll talk about what that word means。

 but it's kind of weird to talk about it here because。😡，From your perspective。

 you really only know two models。 Well， I guess you know， some fictitious models。

 but the two models that you actually know are decision trees and cans。

 You also know the majority vote model and the memorizer model。😡，But regardless。

 you haven't really dived deep into the， you know， depths of possible models and possible hyperpara that we'll talk about in just a second。

 So this is more of an idea to keep in the back of your minds going forward once we do talk about more complicated models。

So some notation because what on earth do I mean when I say model and let me back up and say I've been using this word somewhat loosely already in this lecture。

 so I'm going to try and be a little bit more consistent for this section because it is going to matter right so the model you can think of as the collection of all possible classifiers your algorithm your machine learning method could return to you the fancy word for this is the hypothesis set or the hypothesis the hypothesis space but it's some collection of all the possible functions that your algorithm is considering as good fits to the data so well we'll talk about some examples in just a second。

😡，The model typically， not always， typically consists of these parameters。

 So some number of parameters rather， so if a model is a big set of classifiers。

 if it's a whole host of possible functions that it could return to you。

 the parameters specify one particular classifier， each setting of the parameters。😡。

Typically corresponds to a different classifier that is considered by the algorithm that lives inside your hypothesis space。

😡，Outside of parameters， you have this other aspect of a machine learning model。

 which we'll call hyperparas if a parameter specifies a specific classifier from your model space。😡。

The hyperparameter you can think of as growing or shrinking your hypothesis set。

 your hyperparameters govern what classifiers your algorithm is actually considering the big practical distinction between these two is if it can be learned at training time if it can be learned with a training data set。

 then it's typically a parameter， but if it needs to be specified before you can do any training。

 if you need to make some decision about your algorithm。

 then it's typically a hyperparameter so let's see some examples of this using the few models that we've actually learned right so for a decision tree。

 there's no concise way of really saying this it's the set of all possible decision trees right like if you have you some finite number of features and they all take on some finite number of values you can enumerate all the possible。

😡，Decisionions trees， you can enumerate every possible way of splitting on all of these finite features。

 and that'll give you some number of decision trees potentially limited by one of these hyperparameters。

 which we'll talk about in just a second。😊，The parameters， again， a little hard to specify in words。

 but it's like the structure of your tree， you know your algorithm decides the ID3 algorithm。

 let's say， decides what features to split on in what order and also what the predictions at each leaf node are。

 you know all of the various components of a decision tree your ID3 algorithm can pick out for you。😡。

Unlike these parameters， there are certain things that you need to pick out for the ID3 algorithm。

 like stopping criteria， splitting criteria。😡，Other， you know。

 various early termination things like max depth or。When we talk about like maximum information gain。

 minimum information gain， so there's lots of hyperparameter that you need to pick out before you can do any decision tree learning。

Here's a bit of a weird one， so for a K and N model。

 each specific value of k corresponds to a different set of classifiers。

 a different set of decision boundaries。😡，How do I pick from amongst those decision boundaries。

 well in some sense， each distinct data set， each different data that I possibly could have seen is going to give rise to a different decision boundary。

😡，All of the possibilities in the infinite combinations of training data sets that you could see make up all of these different classifiers。

😡，And here's the real wony thing the K&N model is what's called a nonparmetric model。

 it technically doesn't have any parameters you need to learn at training time。

 the way to figure this out is there's no training right you don't need to learn any sort of numbers or values to use a KNN classifier but you do need to pick a value of K。

😡，But you also actually need to do more things， right， In addition to picking a value of K。

 you need to pick like a distance metric， and you need to pick。A tie breaking scheme。

Tiebreaking method， right？I don't know， maybe we could think of a few more。

 but these are sort of the big ones right you need to make some decisions before you can even begin to use this canN model。

😡，All right， so I get it， this terminology is definitely a bit tricky。

 we're going to try and do our best to be consistent about how we refer to models and parameters and hyperparameters throughout this class。

 but let me stop here， what questions do you all have at this point？😡，挂。Yes。

 how come every value k gives a different hypothesis space。

 but then different values of NAA are all in the same space。

Different values of maxstep will give you subspaces in some sense。

 but they won't give you identical spaces。Well。You would consider them different models This is actually a bit nuanced like let's say you have five features。

 five categorical features then a max depth of six is the same as a max depth of 10 is the same as a max depth of 100 right so there are certain values of hyperparameters that will give you identical models。

 but meaningful。😡，Differences like a max step of four versus a max step of three will give you subsets of the models。

This behavior depends on what exactly your hyperparameter is controlling。😡，Yeah。

That's another type of model。Like very things incredible。

So a parameter will never give you a different model。

 a parameter will give you a different classifier。😡，This case you have an example of the can。

 you look at it in background and explain what and what some of the parameters when you perspective the parameters。

嗯ん。So another well the issue is we haven't really talked about very many models right like the one that I could give you is like a majority vote classifier in a majority vote classifier you learn one parameter that is what the universal prediction should be there's actually no hyperparameters。

Think in a majority vote model that you actually need to care about。

Maybe you need to specify the tie breaking mechanism， that's a hyperparmeter。

What's the ofYeah absolutely that falls into our。Splitting criteria here， yeah。

 the ID3 algorithm specifies you use mutual information。All right。

 I've got a bit of an aside here about parametric versus non parametric models。

 The big idea is that like。They learn parametric models learn parameters。

 hyper or non parametric models don't the easy way to tell the difference between these kinds of models is usually。

Once you've learned the parameters for a parametric model， you don't need to store the data。

 the parameters tell you everything you care about for the purposes of making predictions for nonparmetric models you typically do need to hang on to the training data set and then there's this nice theoretical results it's sort of related to the theoretical results that I mentioned before nonparmetric models given enough data can recover any。

😡，True target function。This is a bit more of like what I'll call an aside， but it's a fun fact。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_94.png)

Allright so model selection versus what we'll call hyperparameter optimization here's the big takeaway these two terms you'll see them sort of used separately for the purposes of this class we're going to consider these to be identical tasks what do I mean by that well it's related to this idea that I was saying earlier that different settings of the hyperparameters correspond to different models they correspond to different hypothesis sets that you're searching over and so if I change if I'm asking the question what is the best hyperparameter setting to use I'm equivalently asking what is the best model to use so these two tasks for the purposes of this。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_96.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_97.png)

Lecture for the purposes of this course， we will consider them identical。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_99.png)

In other contexts， you might hear these things used to mean different things， but for our purposes。

 they mean the same thing， and we're going to see an example of that in just a second of how you can basically take the exact same procedure to do model selection and apply it straightforwardly to hyperparameter optimization。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_101.png)

So let's actually take a look at what that method might be， right。

 So here's the question we're going to ask。 We're going to ask ourselves。

 how do we pick the right value of K。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_103.png)

This is going to be the premise for our model selection or hyperparameter optimization example here。

 so just to revisit， we remember that for small values of k we had these like ridiculous complex decision boundaries that were very liable to overfi for large values of k k equals n。

 we got simple sort of nonexistent decision boundaries that were very liable to underfi。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_105.png)

So this is a fundamental question of how well your model are really like the inductive bias of your model。

 what assumptions is it making to cause it to generalize。

 how well will it generalize under different values of K。😡，So there are some theoretical results。

 let me just briefly share these with you as well， similar results to what we had for a one nearest neighbor model。

 basically if you set K as some function of the amount of training data you have。

 remember the takeaway from the one nearest neighbor model。

 theoretical result was that more data allows you to use a more complex model and that's exactly what you know this function says as long as K grows sort of slower than n。

You can use sort of increasingly or decreasing values of k so here's an example。

 here's a function of n that meets this theoretical requirement you can use you know the floor of the square root here's a。

😡，Here's a very common heuristic use three use five use some small odd number that'll get you pretty far right but like these are just heuristics what we're fundamentally asking here is a question of model selection so let's take a look at our first model selection algorithm right supposeupp you have some data you have some data set D what you could do you can imagine。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_107.png)

I you could partition it into two sections， you could partition it into a training dataset and a test dataset right you have these capital M candidate models that you need to choose between so what you could do is you could take your training data set and train you could train a classifier from each model you could use your training data to pick out one classifier from H1 one classifier from H2 so we'll call these lowercase H1 and lowercase H2 so now you have capital M classifiers one from each model and you basically want to compare them you want to figure out which classifier does the best which classifier will do the best in practice right which one will generalize well。

So what we could do is we could do what we've been doing sort of all along what we've been asking you to do in this homework too right you could take your test data and you could evaluate how well each classifier does on your test data。

 compute this test error metric here， and then pick M hat， the optimal value of N。

 the one that minimizes your test error。😡，But wait a minute， here's a question。

Your test data set is meant to approximate the true error of your model。😡，So if I do this。😡。

Is my best models test error rate still a good approximation of its true error rate？Oh good。

 I see lots of shaking heads， does anyone care to share why， why they think the answer is no？

Is it because I put a very leading question mark on the title slide？You get all the way in the back。

 absolutely， you are cheating， don't cheat， you are biasing your model towards the test data set。

 here's a good rule of thumb。😡，If your test data let let me rephrase that if data has been used in any way to guide the selection of a classifier。

 it is no longer capable of estimating its performance that's a nice rule of thumb if your test data in any way works itself into the training procedure。

 it is no longer a viable test data set so instead here's what we do in practice right we do validation and these terminologies will get a little sort of jumbled up here but the way to think about it is you take your data and instead of splitting it into two bits。

 you split it into three sections， a test data a validation data set and a training data set and you do you know basically the same procedure except you use each subset of your data for its assigned purpose you train using your training data you select。

😡，From amongst your trained classifiers using the validation data， and then at the end。

 you use your test data set to make some sort of assertion about how well your model will do in practice。

😡，Now there are lots of caveats to this， for instance。

 a lot of the time we don't actually care about reporting a test error。

 sometimes we just want the best possible model and we'll see how it does in practice right so maybe you only need a training data set and a validation data set in that case so。

😡，Regardless， this is what we would argue is the right way or a right way of handling model selection questions。

 and we can do this。😡，4our， both model selection tasks and hyperparameter optimization tasks。

 it's the exact same procedure， except instead of specifying capital M different models。

 I specify capital M different hyperparameter settings， I try k equals1， I try k equals 2。

 I try K equals 3， all the way up to K equals n。😡，Hey hey look Matt did that Matt did that for you all here so what we can do is we can plot the training error rates and validation error rates for the Fisher irris data set using different values of k and what we would look for here is the value of k that minimizes this validation error。

 something like right here which I guess like this is a log scale so maybe that's like 30 or something which is pretty close to what we eyeballed from those figures except now we have a much more quantitative justification for why we think this is the right value of k to use。

Okay， that was a lot， when we stop here， what questions do you all have about this？😡，嗯嗯。

What if there is relation between the validation set and the test set？

What if there is a correlation between the validation data set and the test data set？

The staff on the validation set is not completely independent from the testing。

This is an interesting question， right， what if there's some inherent connection between our test data set and our validation data set？

So there's like a fundamental machine learning assumption that our data points are sampled independently。

 that is like required to make a lot of these models work in some sense。

 So if that assumption is broken well。😡，The short answer is your test error will no longer be a good metric for the true error that like。

 you can imagine the extreme case that your validation data set is just an exact duplicate of your test dataset。

 There's 100% correlation between them。 Well， then it's certainly not going to be a good estimate of your test error。

 your true error。Yeah。😊，I think strategies to create your different sets for training knowledge yes。

 this is a great question。How on earth should we partition our data Hey。

 don't you love that when you sort of predict Yeah anyway so this is a very open endeded question certainly I would say that it partly depends on your task so there are heuristics right like you'll read in papers。

 something like a 702010 split for training validation and test data sets that's a very common split you might see 801010 as well so 80%。

 10% and 10% So sampled uniformly at random。😊，There's this notion of like validation through time。

 if you're working with time series data sets， you don't want to sample sort of future data points and use those to train predictions for previous data points。

 and so for time series data， you might want to do this sort of sampling such that the training data only consists of data points that occur before the other two or something like this。

😡，So there are other ways of partitioning related to the task。

 here's another very general purpose way that we'll call kfold cross validation and it saves us from having to。

 well in some sense it saves us from having to decide what percentage of our data to use for what task so what we're going to do and I apologize we're overloading K here。

 this is capital K for K fold， not lowercase K for K andN so what you do is you split your data into K equal folds here。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_109.png)

And you use each one as a validation data set once。😡。

Here's some really weird notation you can imagine learning a classifier from all of your folds except D we're going to call that H minus I。

 the classifier you get when you train on everything except I and then you compute the validation error on the data set you left out D this will give you some error rate which I'm calling EI here。

 and then when you average all of these individual fold errors。

 you get the crossval error so here's a little cartoon for that right let's say K equals4 you split your data set into fourth。

 you train on the last three folds， you predict on the first fold you train on folds one，3 and4。

 you predict on fold two so on and so forth， you get four different errors。

 you get four different validation errors and then you average them all together this gives you a cross validation error rate that you can use instead of the validation。

😡，Aror rate to select models each model， when you do this。

 each model will give you hopefully a different cross validation error。

 and you pick the model with the lowest cross validation error。😡。

Now it doesn't actually look like we've saved ourselves a decision right we still need to decide what value of k to use so here's a very common heuristic we can let k equal n。

 this is sort of the extreme every data point is used as its own little validation data set of one data point and this in some sense does save us a decision right we typically when we talk about cross validationidation。

 consider you know leave one out cross validationation this you don't get for free for sure it requires lots of training you requires training each of your model K times and if K is equal to n that could be a huge number right you could have that be tens of thousands。

 hundreds of thousands millions of data points you do get some savings here in the sense that this is easily parallelzed you can set different processes off for doing individual training runs。

 but still it's quite computationally expensive。😡，All right so here's one way that we can choose to partition our data set。

 we can do crossvalidation， so here's a big table that summarizes what we've just talked about。

 you have some training process that gives you a training error rate。

 you have some validation or crossvalid process that allows you to compare models。

 and then you have testing that tells you how well your model will do in practice。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_111.png)

Okay， let me stop here， we've got a little bit more to cover related to model selection and hyperparameter optimization。

 but what questions do you have at this point？😡，Yeah。

 I have a question going back to multiplecra parameterss。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_113.png)

You know what， that's too many slides， just ask your question set of class。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_115.png)

And I'm assuming it's defined by something， I think you implied that it was defined by the parameters。

 but you said that Canan has no parameters。So is there a fourth category called Kata it's defined by your。

It's defined by your algorithm in some sense， it's defined by the machine learning method like once you can you can argue that that's a hyperparameter in some sense。

 like once you've picked that you want to use a decision tree algorithm once you've picked that you want to use ID3。

 well sort of implicit in that you've specified a hyperparameter。

 but you've also specified the like method you're going to use right so like。😡。

KNNs is a method and neural networks， broadly speaking， are a method for doing machine learning。人。

Your neighbor there。So for K folds validation with the set you'd be like choosing for the validation holds to be like a subset of the total data set yeah that's exactly right oh sorry this is a good point you should be doing K fold you should be doing cross validation using the union of your training data set and your validation data set。

If you care about estimating your true error， you still need a held out test data set。

 that's a good point here。We'll actually touch on that in just a sec。Yes。

it will be computationalal considering the moisture。

 which is about it would be more important to everything。Yeah。

 so again the default here is just some like heuristics like you'll see in machine learning papers five folds cross validation。

 ten0 folds cross validation， we just you know as a society have some preference for multiples of five those are very common choices。

😊，If you really wanted to， you could do hyper hyperparameter optimization because that is what K is right it's a design choice you need to make before you make a design choice。

 but we run the risk of infinite regress there so let's not do that。😊，Okay。By。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_117.png)

All right， so two sort of interesting observations here。😡，One。

 I left this question somewhat underspecified， how do we pick the models we want to compare or you know another way of asking that question is how do we pick which hyperparameter settings to try？

😡，For simple models like K andN this question is really sort of answered for us in some sense we can try them all right。

 we can try every value of k from 1 to n and as long as n is not super large or even if n is super large。

 maybe we like evenly divide it so that we take you know K equals1 K equals 10 K equals 100。

 we can divide our space up somehow。😡，But for many real world machine learning models。

 there are going to be very， very complex hyperparameter。

 they're going to be real valued hyperparameters or hyperparameters that can take on much more than n different values and there might be you know tons and tons of them for a neural network even a simple model that you guys are going to train in a few weeks there will be like 20 hyperparameters we're going to tell you what most of them are。

 but if you wanted to start from scratch， you would maybe have to test every possible combination of all 20 hyperparameters right so how do we go about doing this well here's the big idea we want to pick good hyperparameters to test right we want to start off by having some subset of the hyperparameters that we think are going to be competitive。

😡，But how do we know that a priority， how do we know that without doing some hyperparameter testing right well here are some options we could imagine just dividing our space。

 our hyperparameter space into evenly spaced grids where we basically try you know some consistent set of values for each possible hyperparameter。

😡，We could do this randomly we could use my favorite method Bayesian optimization。

 this is what I study in grad school， we could use my least favorite method。

 which is graduate student descent， which is what I did in graduate school this is where you send your army of graduate students to individually test a bunch of different hyperparameters and then report back to you what the right one is don't do that so we're going to compare the first two methods because these are sort of nice and simple but I want to make you aware that there are more complex methods here and here's a very simplistic hyperparameter optimization tasks right you have two hyperparameters that are both real valued one is on the X axis here and one is on the Y axis。

You can consider taking evenly spaced grid points， maybe three different values for one hyperparameter and three different values for the other and try every possible combination of them right that's one possible way of selecting your candidate hyperparameters。

😡，Another way is just uniformly at random pick points in the space。😡。

So here's a question for you all。Which one do you think will be better this is in fact your third poll question don't pick a in this poll and in real life don't pick a B better than a you can pick between grid search and random search let's say you can take two minutes to make this decision talk to your neighbor see if you can come to some consensus here and I will be keeping an eye as your。

😡，Answers roll in。You picked a， please don't。What。Oh my god。Oh good。

 that worked Only one of you is picked aang now。All right。

 this is very interesting and if you haven't had a chance to respond。

 go ahead and just put your responses in right now， I'll update this in a sec。

 but it's actually pretty close 50- well let's call it 60% of respondents have selected B and 40% have selected C。

 does anyone care to suggest why they think whatever answer they chose， why you think B。

 let's start with someone who selected B， why do you think B would give you a good set of hyperparameters to try？

😡，Yeah， right here， I think it covers Yeah， it covers it more evenly and in some sense it like it might get into corners that you know。

 random search missed， right？Anyone who selected C careed to justify why they liked C。Yeah。

 right here， I think in grid search you might end up choosing like because you go in like specific values。

 some of these values might not be helpful or might even worse the error rate。

 but because you keep searching in the create you not be able to spend that space such space So this is an interesting observation that once we've observed what these hyperparameter values。

How they behave we might need to go back and revisit this selection we might use the information we learned from these hyperparameters to pick better hyperparameters to try that's a good observation you also mention something which is that grid search picks frankly a very small subset of the possible values to test each hyperparameter is only tested three times in some sense there are combinations in which they're tested。

 but each hyperparameter only has three values that are investigated whereas for random search for each individual hyperparameter we get a much better or a much more diverse spread of values that are tested and so here are some empirical results from this paper cited over here I don't want to say that this is a universal truth but on a lot of sort of problems that these researchers investigated they found。

😡。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_119.png)

This trend that there are typically some number of important hyperparameters and some number of unimportant hyperparameters。

 and if you do grid search， you can waste your time testing a lot of unimportant hyperparameter values。

 whereas random search， I think the better argument is that random search just tests more values。

 so it's easier to figure out what the important and unimportant hyperparameters are for any given problem。

😡，Now， like I was saying， I don't know how generalizable this observation is you could very easily have a machine learning task where all of your hyperparameters are important and frankly。

 this version of grids this version of grid search is a bit cartoonish right there are better versions of grid search known as like quasi random。

😡，Sampling methods that， you know， space out your points to be something like like this， right。

 which is still technically a grid。But we'll give you better coverage of the space so we can do some sort of quasi random methods to better improve grid search。

 but those are relatively complex and if you know randomly sampling does a good job。

 why not just do that？😡，All right so that's all I had for you today。

 don't forget I will see you back here on Friday for a lecture on Perceptrons。

 otherwise keep plugging away at homework two and see you on Friday。😡。



![](img/3f7ed6a0e0ee8fb8842834310590ed0a_121.png)

I'll take any questions you have here at the front now。

