# UCB《机器学习导论｜CS 189⧸289A Introduction to Machine Learning Fall2024》claude-3.5 p27 L27- Causality.zh_en -BV1H4421S7bs_p27-

![](img/2363949c6bbe943856fbcbd09954e4d1_0.png)

但是。都谢这。可以。Yes。个辩意。好费。いやし？所以说。这个是。当是。哇。HiI'm teaching right now and I cannot get the baby。The slide。

 which is the second time in a row。I'm in the Anderson Auditorium F295。Okay， thank you。



![](img/2363949c6bbe943856fbcbd09954e4d1_2.png)

给我写实。Okay。It's okay now。 Yeah， I was panicking because last time it wouldn't work at all。

 It was This time it was just a setting， but I never had to do that before。



![](img/2363949c6bbe943856fbcbd09954e4d1_4.png)

Lisson。Okay， so I was just like freaking out， okay， now what's happening though it is。

 but it's yeah I think it's I think it's good， thanks for swinging by okay there now we're good okay。

 thank you so much。

![](img/2363949c6bbe943856fbcbd09954e4d1_6.png)

Okay， thank you。😊，Okay let's get started， so today is not from the textbook but I think an important topic on which to get a basic understanding of you could take a whole advanced graduate course and so we're just going to I just want to give you some of the intuition and a little bit of the formalism and in some sense the take homeme messages that causality is really hard and most people who are trying to analyze data they've collected without collecting it in a specific way for causality are almost certainly going to go wrong but there's decades of work in this area anyway I think it it's a fun topic so there's some optional reading from a textbook that's freely available so basically I created these slides from parts of chapters 9 and 10 I've listed it as optional reading so you don't need to but if you'd like to reinforce your understanding or have any further understanding you can go check that out。

this is working okay so right， so first I'm basically going to give you some intuition about how to think about causality about what can go wrong and then I'm going to give you a little bit of one of the formalisms for causal analysis called structural equation models there's actually about three or four formal formalisms you can use to think about causality but I'm just going to talk about the one I think it's actually maybe they're all suitable for antroductory course but I can't go through all of them so it'll just go through this one。

😊，Okay。So far， what we've learned to do in this class， at least in the supervised setting。

 is take a data set with X and Y and build like a regression model in this case could be a classifier。

 but for causal， let's think about a regression model where， for example。

 you you try to predict the sales price from。From some features the sales price of a house。

 from some features about the house， maybe the zip code， the square footage， how many floors。

 how many bedrooms， and so forth。And here you can see that this model。

 we've got the actual sale price versus the predicted sale price。 So it looks like a fantastic model。

 And let's suppose even this is on the on a holdoutet I actually don't remember now。

 but oh no this is actually for the training data， but even if it was on a test set you could ask and then we use max and likelihood as we learn in this class and suppose we get a 99% accuracy with crossval does this tell us anything about whether this is a causal model or those features that are input to the model are they causally responsible for the sales price or are they just predictive。

 And what is the difference so and I'm sure you've heard throughout your whole life in the media and wherever else about causation versus correlation and that's kind of the way that you can easily go astray。

 but it's kind of more nuanced topic than that。 And so of course what this shows is we have a good correlation between。

The predicted price and the actual price， but it tells us nothing about causality and so it could still be useful。

 predictive models can be useful， even if they're not causal， and in some sense。

 all the success of machine learning speaks to that So most of machine learning models。

 we don't know to what extent they're causal if any。

 and yet they're still very powerful and the main underlying reason for that is that if you have a test set that comes from the same distribution as the training set then you don't need causality in your model if you predict well on the training you can predict well on the test set where causality would be very helpful is if the distribution of the test set was quite different from the training data set that's like an advanced topic of machine learning called domain shift adaptation when the distribution of the inputs is different and there are tricks in machine learning to try to correct for that but fundamentally if you had a causal model。

 you wouldn't need to correct for it， it could actually naturally handle that。 but we can more。

Never find a causal model。Right， and so in fact， I don't know for sure。

 I might have shown this in the first class， but a few years ago， Zillow， who knows about Zil。

 you're all too young to buy houses， but one day you might if Zillow is still around people who are buying houses are interested in the market go look at the predicted sales price or the recently sold price of houses and Zillow was is one of these companies with an online platform that makes these predictions and so forth。

 and they were actually trying to use their own data analysis to flip houses and make money。

 but actually they completely bombed and lost more than $500 million and so I don't know why。

 but I can speculate that what they thought was causal was actually not causal maybe that's not what happened。

 but it's almost sure that that is what happened is that the model they built did not generalize to houses that were not sort of similar to the same training distribution。

 this is a really famous example So what are the axes It's the Nobel。It's per 10 million population。

 so normalized by population， on this axis， it's chocolate consumed。

And so Switzerland has the most Nobel Pris per capita and the most chocolate consumed。 Canada。

 my home countrys kind of far down， not so much chocolate， not so many Nobel Prizes。

 we got United Kingdom somewhere in there。 And so I think there's actually I should have dug it up。

 there's a website where you can find strong correlations between any two kind of completely crazy variables such as chocolate consumption in Nobel Pris。

 and so you know someone who naively looks at this might think that if I increase the chocolate consumption in my country。

 I'm running this country， we're gonna get Nobel Prizes。

 I think you're all smart enough to know that even without learning anything about causality that that's obviously not the case。

 but can somebody given intuitive explanation for why this is happening。

Do you already know the example？Okay， okay。Wait， are you suggesting that the Nobel Prize Committee is biased to the geographic region of the sales price。

 I although we do not know the answer here， I don't know the answer， but I'm skeptical on that one。

 I have a more plausible one， yeah。别下次。Exactly， exactly， so this is a consequence。

 maybe this is I'm not sure maybe this has actually been shown。 In fact， I suspect it has been shown。

 and it's certainly very plausible。 It's exactly what this fellow just said is that to make to get Nobel prizezes。

 you need to have a rich scientific capacity which costs money and chocolate is sort of a luxury item that costs money And so there's this hidden factor that increases both of those is that if I'm a wealthy nation。

 then people in that nation will indulge more in chocolate than in a poorer nation and I'll have a better scientific infrastructure and ability to fund science。

 And so I'm more likely to get Nobel Pris。 And so so that makes a lot of sense that this is eventually what we're gonna learn is is going to be called a confounding variable economic wealth is a confounding variable when looking at the causal relationship between chocolate consumption and Nobel prizes。

 And so we're gonna to learn about how to handle。Confounding variables so that we don't go wrong in a causal analysis and conclude that increased chocolate consumption will increase Nobel prizes or I suppose you could even think of it the other way having more Nobel prizes creates more chocolate consumption。

 I never thought of that direction， but in any case from such a plot we can't know anything and the key is going to be to understand what other variables might be at play and how they're causally related to each other and so something that really irrespective of your stance on COID policy something that drove me nuts in the pandemic was I knew people with PhDs and statistics and math and and then I don't expect the journalists to do better like my friends who know about causal analysis but were like just like trying to make a point would plot things like this on Facebook and so forth where they'd say the percentage of people wearing in masks in public is anti-correlated with the incidents of COVID and we don't know maybe that's true or not。

 but by the end of this class。Hopefully just from the last example alone。

 you know that the title of this article should not say a powerful argument。

 it should say like an incorrect manipulative argument right and people try to use this all the time in the media and you probably know this but maybe by the end of this class the next time you see it you'll just be like what are these people doing and especially the people who should know better？

😊，Okay， so there's a really classic example that helps to explain some of these concepts it's called Simpson's paradox and this is one of the classic examples of Simpson's paradox is actually real data here。

 I don't know I think somewhere I have a citation that I don't remember the year but like this is often where is causality important in things in many things。

 policymaking but in medical decision making， you conduct a study like your pharma or a hospital and you say I have two different treatments。

 A and B， so two kinds of maybe their drugs maybe they could be any two different kinds of treatments for kidney stones and you collect the data and you see that of the people there were 350 people that got treatment A and 78% of them got better from their kidney stones and those who receive the other treatment。

 also 350 people 289 of them or 83% had a success rate？So 83， we all know is higher than 78。

 And so you might be tempted to claim that clearly treatment B is the better treatment。

 And that's the end of your study。 You close it down。 And now whoever comes in the hospital。

 you just give them treatment B， But and like that actually feels really reasonable， but in fact。

 it's completely wrong。 Does anybody have an idea of what might go wrong。Yeah。你老。

You know that this really represents the entire park。Yeah， that's one issue。

 but let's assume that' is the correct population。 What else like maybe think back to the previous slide to give you a hint。

 The hint is there's a confounding variable here， much like economic wealth was a confounding variable for the chocolate consumption in Nobel Prize。

 the confounding variable here is what kind of kidney stone you have。

 So the data I just showed you was irrespective of the size of the kidney stone。 I'm going like this。

 I don't know where my kidneys are were of two kidneys， right。

I think they're like back here okay and so it turns out that you can kind of roughly separate for therapeutic reasons into large and small stones and what you'll find is that among all the large people with large stones。

 those who got treatment A， 73% were better， which is higher than those people who had large stones and got treatment B and similarly for those patients who had small stones。

 it was a 93% success rate for treatment A， which is higher than treatment B So the trend is just completely reversed right if we looked at all the data not knowing anything about the fact that there were different size kidney stones。

 we would conclude treatment B was better and now we conclude treatment A is better in each of those groups And so what's sort of the real answer here。

 the real answer is to separate out by the large and small stone and as we go through the lecture。

 we're going to find out why you need to separate out that way， but basically if this is going be。

The crux the problem of all causal analysis is you're going to have to know that this is a confounding variable for this analysis and because you know。

 if you know that it is and you're correct， then as we'll learn separating out the analysis by each possible value of the confounding variable is the correct way to do things and now and what's going to be on one of the last slides is we almost never know what is the confounding variable。

 but sometimes we can make educated guesses and make progress but we can never really quite be sure。

 but nevertheless just being able to think this way is very helpful when you see analyses that other people do or you're trying to think along these lines as well。

So so right， So what's going on here， though， like how how like this is this is actually this is what's called Simpson's paradox because it seems paradoxical that it went from treatment B being best to treatment A being best。

 And so what's actually happening here is if we look among all the people with large stones23% of them。

 only 23% were assigned to treatment B。 But the people with small stones。

76% of people were given treatment B。 And how was that decided， it was decided by the doctor。

 So the doctor apparently knows that if you have a small stone， B is likely to work well。

 And more people have。Right now which way sorry And so the issue is that this treatment was not given at random as it would be in a randomized control study。

 you've probably heard of these that like the pharma uses as the gold standard for a causal analysis。

 So here are the doctors actually using his or her intuition and knowledge to prescribe the treatment that would be better based on his or her knowledge of whether it was a small or large stone And so if the doctor assigned B more often to small stones and the small stones are just easier to treat than large stones then it's going to look like treatment B is better because you haven't accounted for the fact that small stones are easier to treat and that the doctor was giving treatment B more to small stones。

So there's actually a famous example。 I didn't dig it up。

 I think one of the classic examples from sinceson's paradox is admissions at Berkeley and different departments by gender。

 You can go look it up about that。 I don't even remember the details but right。

 let's stick with this one for now， Okay， does that make sense Any questions。😊。

And so we're going to start to see figures like this and they look a lot like a graphical model and as I'll note a bit later quite precisely is the graphical model shows you statistical dependencies between random variables。

 causal models actually show you causal relationships between variables andre not those two kinds of graphs。

 graphical models and what are going to be called structural equation models which is just looks like a graphical model but you can give it a causal interpretation。

 they look very similar but only one of them has a causal interpretation and so here we again see that basically the size of the stone。

 it causally influences both the treatment success and what treatment gets taken and because this variable points to both the variables we're trying to assess whether there's a causal relationships between them that if we ignore it as we did in the first column we're going to go astray so that's sort of one of the main themes of this lecture is if you're trying to look at the causal relationship。

Between two variables and you have what's called a causal， a confounding variable， I mean。

 meaning it points causally to both of these， and you have to know that you can't actually deduce that in any way with cross validation with anything。

 you have to know it from domain knowledge then。呃。If you have this。

 then you need to basically account for that in your analysis。

 and we're going to do that formally later in the lecture， see how to do that。

So here's a visualization that I really like of Simpson's paradox just to kind of drive the point home and the example I gave before it was the confounding variable was was binary right。

 the confounding variable was you either a small kidney stone or a large kidney stone。

 Here we have a potential confounding variable of age where the relationship between your cholesterol level and your exercise level is anticorrelated right so for each age group。

 So for age group you're probably you guys are probably you guys mostly between 20 and 30 Anyone won to ask in mind。

 don't want to embarrass anyone who is above or below I assume you guys are somewhere in here。

 let's just say around 20 So for you and similarly I'm up here。 for both of us， the more we exercise。

 the lower or cholesterol。And that makes sense， it's just that the trend is different for every age group。

So but if I don't know about age and I just collect all this data and I forget the age variable。

 I get a blob that has a correlation literally in the other direction。

 I went from anticorlation to positive correlation。

 And now it looks like the more I exercise the higher my cholesterol level。 So again。

 this is like this Simpson's paradox so called paradox where if you're not aware of these important confounding variables here age。

 then you can just be dramatically lead astray like and it's not even that you will find there is no causal relationship。

 you will find it goes in completely the wrong direction。 So you got to be super careful。

 So right and so a couple of classes ago， you learn from Sa about graphical models and graphical models are basically a way to efficiently represent joint distributions over many random variables here。

 A B E JM。 and the idea was naively if you wanted to model the joint density over all these。😊。

You would need like a huge set of numbers。 But by making use of conditional independence。

 such as you saw like in an HMM and other such things。

 you can reduce the number of parameters to efficiently model the joint density of those variables。

 And now nothing。nothing in these models has anything to do with causality。

 And so this is where you need to get to be really careful because there's a lot of similarities between graphical models and these little pictures that I'm showing you today that are causal models and so in general。

 these models do not reason about causes， they're just modeling joint distributions and one of the main themes of today's lecture in addition to teaching you Simpson's paradox is going be to show you what is the difference between just probability distributions and other entities that have more to do with causality that we'll get to in a second And so with some additional assumptions we can sort of use the machinery of graphical models and layer on top some extra assumptions and once we do that。

 they're basically going to impose causality on the graphical model formalism。

 then we have what are called structural equation models and we're going to go through those in a second。

 is this like a fancy term for a fairly simple idea。So but so formally。

 we can think of Simpson's paradox like like this， which is that and I put the paradox in quotes because it's not if you understand the topic of causality。

 it's not a paradox。 It's only paradox when you look at it casually and things flip in the opposite direction。

 but so this is saying that the probability of success Y。

 given that you had treatment A is if I look at it just like this without looking at the size the kidney stone size variable X。

 then I see the probability of treatment success， given a is less than the treatment success。

 given B， and formally Simpson's paradox as saying when I condition on the confounding variables。

 and then look at the treatment success between A and B， it flips the sign。

 So that's formally what it means to say you have an instance of Simpson's paradox。

And right it's the same thing here， flip you flip the sign like basically this slope went from negative to positive。

 depending on whether you slice and dice by age。And so， and so mathematically。

 there's no contradiction here， right？ So there's no reason that。

Like there's nothing you could show me statistically that says there's a paradox here。

 There's no two equations that disagree with each other， according to the tenets of statistics。

 And so that's the sense in which there's no paradox。

But the paradox arises because we tend to think about conditioning on things as performing an action and that's really one of the key themes in causal analysis is to distinguish between statistical conditioning versus doing something。

 making an intervention and we're going to learn more about what exactly that means。

 but often people are trying to do causal analysis with observational data。

 just some data that's been collected and without further knowledge you can't get at causality and we'll figure out what you need to inject in it into that analysis in order to get some causal analysis。

But so like some of the kind of key phrases that are really important to understand what's going on here is that in this study which was an observational study。

 we observe the doctors in the hospital and we see who gets treatment A or treatment B but nobody like the study has no control over that right like there's nobody in the study that tells which doctors what to do。

 the doctors are just using their natural inclination and training and knowledge to say this person will get treatment A or that treatment B and apparently they will give B more for small kidney stones and so thats this conditional this way this observational setting which was the case here is in contrast to an interventional setting where we can perform actions。

 It's not just passively observing and so the gold sort of the classic example of that is the randomized control example and what randomized control trial or randomized control study。

And that's on the next slide， but before I get to that。

Let's think about this example where have this confounding variable。

 meaning that it causally points to the variable treatment success and causally points to what kind of treatment a person gets。

 And so given I told you what the explanation was for why Simpson's paradox arises here。

 How might I fix it if I think about this graph， can you think of some way I could fix this like how could I fix the problem here so that I don't get a Simpsons paradox。

嗯。Yeah， so what you described is a way to take the data that I had and do the analysis differently。

 and you're correct。 But suppose I want to maybe I didn't I perhaps didn't use the words on the slide when I was speaking。

 Imagine I want to redesign the experiment。 Like I'm going collect the data different。

 and you're correct in what you said， But it's it's an answer to what we'll learn in the second part of the class。

 So but imagine I get to redesign the experiment。 How could I redesign it in a way where I would not get a Simpsons paradox。

Exactly， exactly the problem was the doctors are using secret knowledge to assign B more to small stones。

 what we want to do is we want to prevent them from doing that。

 we want to randomize the connection between size of the stone and treatment and if we can do that and generate data having randomized that。

 then we basically have a randomized control trial that will not have this problem to questions yeah。

just。So yeah， let me clarify， so you can do causality in two ways。

 One is you can take observational data such as we had here and you can try to do causal analysis and we're going do that in a second right now what I'm saying is like the true actual gold standard way so it turns out that's highly problematic。

 you can do it if you have the right assumptions， but you can basically never know you have the right assumptions So in some sense doing causal analysis on observational data is kind of impossible。

 we're going to go through it and show how you could do it with the assumptions and then we're going learn about why you don't really ever know if those assumptions are true or not and so if you're actually a drug company you're not allowed to do observational data So drug companies have to design the experiment to generate data in a way that breaks this edge and so and that's the gold standard and now you might ask well so why would anyone ever try to analyze observational data if you can do this。

And the reality is it's usually very expensive to design a study like this。

 and so the main like most studies in the world have not been designed in this way。

 and people want causal analysis and so they try to squeeze it out of there。

 but if you really care about causal analysis and you have the budget to do it。

 you should break this link and you should generate the data in a way that does this randomized control study。

So right so randomized controlled trial is the gold standard way to get at causality by generating data that will not give you a Simpsons paradox because it breaks this edge here that simply would not happen and as someone correctly phrased it。

 you're basically interfering with the doctor's knowledge of what treatment to give and it's actually for that reason as just as a side comment it never thought of that before。

 but I'm pretty sure that in most clinical trials as you go through there's different checkpoints。

 and if at some checkpoint it's shown that one treatment is actually significantly better than the other and a causal manner。

 it becomes unethical to continue the study precisely because you're not allowed to pick the better treatment that are as more likely to succeed。

 And so that's why sometimes studies get stopped early because it's literally ethically not responsible to force this to be randomized。

 you're then giving like a worse treatment when you already know that it's better just to collect more data。

Right， so and the point here is we're going to break this edge by disallowing the doctor's internal decision。

 and that's why you get these double blinded studies。

 the doctor doesn't even know often what someone was given。So in this， I mean。

 you may want to balance all kinds of things。 some things you can't control。

 The main main point here， though， is to break this link。

 and that does not require anything about controlling the size of different sets。

 But there is an issue of statistical。 Are you wellpowered statistically in all kinds of other considerations。

 But I'm not going to go into those in this lecture。

 And there are sort of orthogonal to the main issue of causality。Right。

 so we're going replace the doctor's sort of internal decision system of treatments with a random like some randomized thing doesn't have to be a coin flip。

 but it has to be randomized so that there is no longer a link between the confounding variable and the variable you're trying to look for a causal analysis on In principle。

 you could break this link instead of this link like in a theoretical sense that would be sufficient。

 but we can't usually break the link between the size of the stone and the recovery because that's like some fundamental link So we can't really do that。

 even though theoretically from this graph that would be an okay thing to do。 And so right。

 so now in a randomized control study， the doctor can more frequently assign treatment B for the smaller stones and we cannot therefore arise at a Simpson's paradox。

Oh。Yeah。The goal is precisely to， here is the exact setup， it's not cycles。

 it's precisely we're going to go into these terms more carefully in a second。

 but if you're looking for a causal relationship between two variables and there's a third variable that causally does point to both of them。

 formerly it's a confounding variable and you need to break one of the links from the confounding variable to the two variables under consideration for a causal relationship。

Either link， yeah。And it's， I mean， I think intuitively。

 you can see why is like it's fine if it only affects one of them because you can't trick you into thinking that the two are kind of related in some causal manner。

 if it's only pointing one。 But if it's point at two， then you can be fooled。

 if it doesn't make sense， I think if you sit with it over dinner without a beer。

 it will make more sense。嗯。Right，And so in the language of causality。

 we call this like an intervention or an action。 We're intervening on the doctor's ability to prescribe treatments。

In other words， and we're breaking the link from this confounding variable to one of the two variables under consideration。

 And so as I was sort of highlighting before， it's vastly easier to extract causal information when you have interventional data in which you've broken the link from the confounding variable So if you've done that correctly then you can get at causal analysis。

 However even here you need to know what the confounding variable is to break that link and that's also still problematic so you can still go wrong。

 you may not be aware of like what other variables might be confounding variables have I broken them。

 but if you can sort of hedge your bets by conducting these trials in certain ways much more easily than you can with observational data。

Okay so that's the intuition， basically trying to get at more of the guts of why causation is not correlation。

 this idea that you have a confounding variable and if you don't account for it。

 then the sort of the sign of the correlation be go from positive to negative and just your analysis can go completely wrong。

 so let's learn a little bit of the formalism now。And so， and so right。

 so there's this notion of doing an inter invention or making an action on a variable。

 And so how are we going to formalize this like notationally。

This is for the language of structural equation models。And again。

 one of the key things in this kind of。Analysis is to distinguish the idea of conditioning on a variable from intervening on a variable。

 And with a language that we have at hand right now， that of statistics。

 all we can talk about is conditioning。 So we're gonna to have to introduce a new notation for this new formalism that will allow us to describe when we've intervened on a variable。

And it's going to look like this。 So now it could be that the probability of treatment success is not conditioned on the random variable A。

 It's conditioned on the fact that I've intervened on random variable A and set it equal to1。

 So in other words， I've forced this patient to get treatment A instead of treatment B。

 And so there's a really big difference between taking observational data and asking what the conditional probability is。

 versus intervening on a variable in setting its value And as we're going to see the fact that when those are not equal to each other is basically when we can go wrong。

 and these will not be equal to each other， if there's a confounding variable that we haven't accounted for。

And we'll see that more in a second。Right， and so we're going slowly make our way towards these structural equation models。

 which are going to be causal models with a causal graph and they're going to kind of come with a pseudocode as well that tells us how to generate the data so in some sense。

 a structural equation model as you'll see in just a few slides。

 is equivalent to like me if I give you a structural equation model。

 I don't have to give you the graph， but that's a nice way to visualizing things I can instead give you the key element。

 which is a program that tells me how to generate the data。

 And so you can think of a structural equation model is writing like pseudocode that would in a step by step manner。

 generate the data。 And if I have that， then I have essentially a generative causal mechanism and it's a language in which I can describe it。

 It's not a method to extract causality， It's a method only to describe a particular causal model And it's a separate question to say how would I learn a correct structural equation model And that's。

More or less impossible。 nevertheless， you can see there's a whole field about this。

 And so I think in some way， the point of this lecture is not to say here's how you can do causal analysis on observational data。

 almost the point of this lectures to say here's how people think about it And here's why it's really hard and you most likely you can't do it so we're gonna keep going with these structural equation models And so just to get a sense like some intuition here。

 imagine someone wants you to help analyze I don't know their marketing data or maybe something more interesting in some scientific data and they want you to do a causal analysis and they say I can give you one of two things。

 which one do you prefer one I can give you like an Excel sheet perfectly organize with all of the data that I have or two。

 I can actually give you pseudocode that would generate that data's kind of a weird。😊，Question。

 is it obvious which one you should want。啊哈。Yeah， in some sense。

 you clearly want the code because the code can generate the data。

 but the data cannot generate the code。 And so sort of in that sense。

 clearly one of them is much much stronger information than the other。 And in addition。

 you could generate more data if you wanted to。 So this is like a bit of a strange conceptual question。

 but it's meant to get at the fact that the power of the structural equation model is precisely that it sort of this piece of code that describes how one would generate the data if that model is correct。

And so right the code contains more information because we can generate the data from the code。

 but not the other way around， but even more importantly， like really importantly。

 what can I do if someone gives me the code， I can intervene on a variable in the code so maybe the code says you know make your cardiac arrest equal to like this plus this and now I want to see well。

 does this variable cause cardiac arrest， yes or no， if I have the program。

 I can just change the value of that variable and see if it changes what's happening to the rate of cardiac arrest。

 so in some sense I have this ability to do interventions or to do things with that model and that's exactly why they're powerful models is I can do these interventions on the code but again the crux of this is that's only valid if the model itself is valid and you have the right causal relationships。

It's a bit of a catch 22， but so here's an example of a structural equation model written as pseudocode and as soon as you're given the pseudocode。

 you can always back out of this to one of these graphs to see what points to what by just extracting it from the code。

 but what all of these structural equation models have is you should think of they have a set of random seeds at the top。

 these are not the variables of interest in this case they're just Bnoulli half Berullia a third。

 Berrnoullia a third and the variables of interest are exercise X whether someone's overweight or not W and heart disease H if they have it。

😊，And so in this structural equation model， to get one example of x W H。

 you would sample a value of u1 from this Bernoulli。

 U2 from this Bernoulli U3 from that Bernoulli now you would set the value of x to u1。

 then you would set the value of W as follows if x was equal to1 then you'd set it to0 and otherwise you would set it to the value of u2 And so what you can see here is w causally depends on x because depending on what x is。

 it will influence the probability of W。 And so that's the sense in which you can see because this is a generative program what the causal influences might be。

 And then I take so now I've set the value of x of w of H。 and so H I say again。

 I look at x if x is equal to 1 then 0 and otherwise you get the value u3。

 And so similarly H also causally depends on x。 So we know that x points to W causally and x points to h causally and as far as I can tell there's no other causal。

Here， so that would be the kind of causal graph。 And I could generate as much data as I wanted by each time sampling a new value of U 1。

 U2， U 3。 So this is sort of like a graphical model， but it's。

 it's a generative model in which I've assumed a causal interpretation。

So this induces a joint distribution over the random variables。 X W and H。

 These are just nuisance variables。 so we don't care about them。

 And so we do have a joint distribution here。 just as we would have in aographical model。

 But here because of the assumptions implied by the structural equation model。

 it also has a causal interpretation。 And so we can compute various probabilitybabilities of interest。

 So how would we compute the probability that heart disease is equal to1。 So let's take a look。

 So it says if x is equal to 1， then there's no probability of it。

 So what's the probability of x1 is u1。 So I have to take I want it not to be x1。

 So I need one minus u1， So that's a Bnoulli 50%。 So I need 1 minus a half。

 and I get a half takes care of this part because I want the probability that it's one。

 And then if that's not true， then I need the probability of u3， which is a third。

 So the probability of heads is equal。heart disease is equal to 1，6。And similarly。

 I can look at the probability of that H equals  one when w equals1。

 So what's folded that H equals1 if W equals1。 So if w equals 1， it means that x1。

X was not equal to one。呃。now I'm getting confused。 probably if w is equal， if W is equal to one。Oh。

 my goodness。呃レ。If w is equal to1。啊。If w is equal to1， it means that x1 cannot be equal to1。

Otherwise， W would be equal to 0。 So we already know from the fact that W equals 1。

 We know that x is not equal to1。 And therefore， we know this is not true。

 So we get rid of this clause， which have given us the half， and we're left just with the else。

 which gives us the third。 Okay good。 It's like simple， but sometimes confusing。

 So right what we've shown is the probability induced there's this joint probability distribution induced for which the probability of heads is 1。

6， probability of heads given the knowledge of W is one third。

And so what we can conclude is the probability of heads conditioned on the fact that W equals1 is greater than the probability that head。

Heart disease is equal to one。 And so you might think， like。

 does this mean that W causes H because this probability where I condition on W is bigger than the one where I don't。

So who knows the answer to that question？I'll give you， I'll give you a hint。 I。

 I was describing this model。 and I actually kind of without drawing it。

 I explained how you could see which variable causally influenced another variable by looking at this。

 So if I look at this， is it true that W causes H。And好。Right， so if I change the value of W here。

It has nothing to do with what happens to age。Casly。

 what was happening in this computation that I was doing was that if I know something about W。

 then it tells me something about X， which tells me something about this。

 But all this tells me something is not causal。 It's just revealing information in the giant density or the conditional density。

 but it's not that argument I was making was not a causal argument。

 It was just like using the rules of probability。And so， in fact， we can read off from here， right。

 if I change the value of W， it literally has no effect on this part of the code。 right。

 If you ram this， you type this up as pseudocode and you suddenly set W to something else。

 H for that would be unchanged。And so the point is that if it were causal and I intervened on W。

 then it would have an effect on H。 And because we can see from the code that it doesn't we can conclude that w does not cause H。

 And so you can see these things in the model and we'll draw the graph in a second where you can also see that they don't point to each other。

 And so the answer is no。 But from this what we're going to also do is we're going to get this insight that conditioning is different from doing。

 And those are those two notations。 And so let's actually go through the exercise of intervening on W in the pseudocode might as we much do in a real experiment in hospital。

 So let's take the same structural equation model。 But what we're going to do is we're going to obliterate that line of code and we're going replace it and say w is always equal to one。

 And when I do that， again， just to emphasize whatever happens to H is unchanged because there's no dependency on W。

 And that's how we know it's not。 so。When we do this in this new program。

 so this had been one structural equation model with one program。

 I've now altered the structural equation model and therefore I've altered the program with this one line。

 The probability of H is still equal to 16 because that was the same the same argument applies as here。

And so what I but I'm going write it differently， which is that I'm going to because I'm going to condition on the fact that I intervened on W equals 1。

 And so now it's not just probability of h equals1 is probability of h equals1 conditioned on the fact that I intervened on W and set it equal to1。

 and so this is how this notation gets used when I intervene on a variable。

 I use this notation now to imply that I'm not conditioning but I'm actually doing something to the variable and the key point here is that the probability of H conditioned on W。

 which is something you would get from observational data is in this particular case。

 different from the probability of H， given that I intervened on W。

And so they're not equal right so the probability of H that given that I do W equals1 is16 and the probability of down here is one third。

 And so those are not equal to each other。 that's because this one I'm doing something to the variable。

 And here I'm observing and doing a conditioning analysis。

 And this this can seem really weirdly I don't know for a long time。

 this was very nuanced to me and I couldn't quite understand it。

 And then one day it clicked and now it seems obvious but I I don't know now when I teach how obvious or not it is。

But but this is one of the fundamental。Issues， And so it's going to turn out to be the case that when these are not equal when there's a confounding variable at play。

 If there hadn't been a confounding variable at play， then conditioning would be like doing。

And that's going to come in to be key for us in just a moment is because in some sense。

 what we want to ask， if we want to do causal analysis on observational data。

 then we cannot have any of these do statements because these do statements mean we have the money to intervene。

 And so one of the key things we're going to want to do is to convert these do conditionings into just regular probability so that we can in a sense use interventional analysis on observational data。

So I showed you two different programs， two different structural equation models。

 one was before I made this change， it was just these four steps and in that case I could read off the graph that x doesn't depend on x gets set without any reference to W or H so it doesn't get pointed to by anything these are just nuisance variables remember they're like random seeds to generate the data。

 these are the variables of interest and W has some dependency on x and then otherwise just on a random seed。

 but not on H so w gets pointed to by x and H depends on x。

 but not on w so x also points to H and that's the way in which I can draw one of these causal structural equation models that has a causal interpretation from the program but as you may note if I gave you just this graph you can not generate the data right you actually need the code but the graph is a convenient way to see which variables are causally influencing other variables and so we often describe the structural equation。

With both of those parts。And unlike a graphical model in causal analysis， you cannot have a cycle。

 So graphical models you have directed graphical models and undirected graphical models did say go over both of those。

MaybeAnyone know， he went over just directed graphical models， Okay I see。

 so it turns out there's you can have undirected graphical models they're much more unwieldy to work with because you have usually an intractable normalizing constant so they're harder to do。

 but you can have both versions， but when you have a graphical model that you want a causal interpretation for。

 which is the structural equation model than you cannot have any cycles。

And one variable causes directly causes another is causal for another one。

 if there's a like a link between them， that would be like a direct causal relationship。

 but even if there's a set of paths that connect to variables， a directed path。

 then that's still a causal relationship， just not a direct one。

RightAnd so from the graph it's just easier to read off the causality and so if you want to look like in general these are simple examples with just three variables。

 they could be arbitrarily large and so in general。

 if you wanted you had some big large graph and you wanted to know for this variable。

 does that one cause have a causal effect on it， you'd have to basically look is there any directed path from that variable to the other variable looking through the whole set of the graph？

So right， so the structural equation model is this like pseudocode。

 which is a list of assignments to sample from the joint distribution。

 given these sort of nuisance variables written before as mu here they're written as capital N and it has to be an acyclic set of assignments because otherwise you couldn't generate a sample you'd have to start cycling and you wouldn't know when to stop and so these are two examples and often we'll talk about this model M as some pseudocode and then it can be convenient to have a notation of what happens when you intervene on one of the variables here I'm setting this particular variable to8 so I might write it like this is meaning it's the same model as here but I've intervened and done an action on Z to set it equal to8 and then when we have these kinds of models we can talk about the probability of an event after applying an action or applying it which is the same as a do operator and so you'll see this kind of notation as probability of some event。

given that I did something， or I might see it as that you might have this sort of context of an overall model in which you're doing interventions setting x equal to x。

So right， and as we saw it， like X could be something like the you know age as age changes。

 the trend with cholesterol changes， but it's often in many cases， like a treatment for some disease。

 maybe it's like which laundry detergent on the laundry detergent is a let's forget that。

 let's think about the treatment case。 And so so for now we're gonna to talk about one of the main things people are interested in quantifying。

 which is causal effects。 So if you run a study， you want to know kind of two things right you want to know that this treatment has a causal effect on the success of the patient getting better。

 but you also want to quantify how much it matters right like if it matters only a tiny little bit。

 you're not going spend another $10 billion getting it through the last step of like the FDA requirements right So there's this notion of is something causal for that is this variable causal for that one。

 but then there's a separate more new。question of like， well。

 how causally how much does it causally influence that variable。

 And that's what we mean when we talk about causal effects。

 And so this here is called the causal effect of x on Y。

But the thing we actually care about when we run these studies is what's called the average treatment effect。

 which is given by the expectate so this is something like treatment for a kidney stone given that I gave treatment A or given that I gave treatment B and what I want to know is what's the expected treatment success。

 given that I gave treatment A or comparative I gave treatment B and the difference between those two things is the primary quantity of interest for almost all causal analyses is to quantify how different the outcome is。

 not just is it different， but how different is the outcome if I give treatment A versus treatment B and so this is sort of where if you have the correct structural equation model。

 you can actually get at this or if you have interventional data。So right。

 just to emphasize this average treatment effect is how much the treatment causally increases the expectation of the outcome variable relative to having had no treatment。

And so here treatment zero versus one with like this sort of kidney stone treatment A versus B。

 So is it clear like that why this is a quantity of interest， it's like。

 how much does variable X causally make a change in Y？And so this is like one of the， okay。

 this is sort of the really fundamental question in causal analysis is how can I estimate this thing。

 like in what situations can I estimate it， So clearly， if I can make use of do operators。

 meaning I can make interventions， then I can just compute it， right。Then I'm fine。 So。

 but the question is， how can I ever compute this if I can't use a do operator。

 Can I actually compute it from observational data， Did you have a question。嗯。

Let's not go into that like that's quite nuanced， I think there's enough moving pieces today， yeah。

 this is a pretty common example that is very broadly applicable and yeah you have to get a bit more nuanced to go beyond that。

So but yeah， so the real question， so equivalently， I'm going to rephrase this and say。

 when and how like imagine I have observational data， can I ever express these due interventions。

 which are actions as only conditional probabilities。

And I just told you that conditioning on x is not the same as doing X。 And so if this is not true。

 I can't just drop in the conditional for the do。 I just prove to you in that structural equation model example that conditioning on a variable is not the same as intervening on the variable So theres are not the same and the thing I care about to get the average treatment effect involves these do operators。

 And so the trick is if I have observational data， can I somehow turn the language of do operators into the language of conditional probability so that I can compute this。

 And the answer is yes， I can if I have the correct assumptions as I keep stating over and over。

 so here's where I'm now going I've said it many times but just to be crystal clear here。

 So imagine I'm considering whether there's a causal relationship between x and Y。

 then if there's a third variable that points to both of those variables in a causal graph。

 So the causally effects。Each of them， then this thing is called a confounding variable。

 and we saw this example of the stone size。 and if there is a confounding variable for the relationship between x and Y。

 then that's exactly when conditioning is not the same as doing。

And so the key here is going to be to， and the flip side is if there is no confounding variable。

 they are actually equal。 And so what we need to do is get rid of the confounding variable in some way is going to be the whole key here。

 I feel like I'm losing my voice。嗯。This is just another example that we saw before。

 and just the point of putting both of these here is to say。

 I don't know what the relationship between these is。

 and I'm trying to figure it out and irrespective of whether there is an arrow here or not or which way it goes。

 what I know is x is a confounder because it points to both of them。

So that's the definition of the confounder， it doesn't depend on what connection is here。

 it's just that this points to both of these and I'm trying to understand the causal relationship between these two variables。

Right， and so。How are we going to estimate this average treatment effect with only observational data in which I cannot intervene。

 I cannot make a do operator。嗯。So what I need to do， as I said。

 is I need to eliminate the confounding variable。 and what I'm going to have to do in a way is kind of isolate my data from its influence。

 And it looks a little different than it did earlier in the lecture Earlier in the lecture。

 I said you need to break this or this。 So what's the difference between earlier in the lecture and now。

It was a slightly different setup when I broke one of the links before。

It it's actually related was my， the answer is related to what I said to you earlier。

 So basically earlier， I said， imagine I get to redesign the experiment。

HowWhat should I do And I was trying to explain a randomized control trial。

 I need to break one of these two links and then generate the data in that way with the link broken。

 Now I'm saying you don't get to do anything differently。

 You're stuck with the data you have So there's no interventions here。

 I'm not going to break the link with a do operator by randomization。

 I have this observational data and I need to in my analysis。

 essentially protect myself from this confounder variable。 So it's a different setup。 In this case。

 I'm saying how do I manage with observational data to get a causal analysis to get the average treatment effect before I was saying how might I redesign how to collect the data So that's why these look a little bit different。

And so it's actually quite simple， intuitively， is what I need to do is I basically need to say for every value that the conunding variable can take。

 I need to do the analysis separately and then I need to kind of combine those in some manner unless I care about them at the individual level and that's really the main intuition here and so once we do that we can average appropriately as we'll see in a second。

So right， so this is one of the main equations that is used to， in a sense。

 get rid of Simpson's paradox where you have observational data。

 you have a confounding variable And instead of just looking over all kidney stone sizes and computing the success of A and B。

 which you're going to do is you're going to break it down according as we saw on that chart。

 what's the breakdown for small stones， what's the breakdown for large stones And so here Z is that confounding variable And if I want to know the causal effect of treatment A versus B or let's say if a on treatment success Y。

 I need to average out over all the possible values that Z can take So in the case of cholesterol Z was age and in that case。

 the sum would be over age 10， age 20， age 30， age 40 and like all those values in the case of the kidney stones。

 Z is just big and small。Ha two terms in the first term。

 it's the conditional probability of treatment success， given that I had treatment A。If this is a。

 we can do it for right， we'll do this once for a treatment A and we'll it a separate time for treatment B。

 let's just assume this is for treatment A。 then I sum over this equation once where z is equal to small stone。

 So this is really what I'm doing I'm saying what's the treatment success given that I had treatment A and given that I have a small stone and this is just when I'm averaging to account for the fact that fewer people may have small stones or larger stones so when I'm averaging the effect for each value of the confounding variable I'm taking into account how many people had that value of the confounding variable So basically this is like probability that someone had a small stone versus a big stone and then this is the conditional analysis and so when I'm basically intuitively what I'm doing is when I break it down for each value of the confounding variable I'm breaking these links here and there is no confounding variable because I've just held it constant and so while it's constant it is the case that the conditional is the same as the do and。

This is just to average for the correct number of people。

 and so essentially I'm averaging over all those values of like here large and small and then putting them together。

 and that's how I get the causal effect is I do it once for each value of the confounding variable because that makes sense。

う。Does this does this formula like forget the left hand side。

 Does this part of the formula look familiar to anyone。

Sometimes people get confused because I'll show you on the next slide。 it looks a lot like something。

 but there's a small difference， but in any case， what this means is that if I know the confounding variable。

 then I can analyze and get the causal effect for each value of the variable average them and that will give me one of these。

 which is one of these， then I do it again for the other value of X。

 and now I can get the average treatment effect using just conditional probabilities。

 even though I didn't have interventional data。嗯。嗯嗯。嗯。😊。

What do you mean then you expect to see that's I don't know what that means？嗯。嗯。Oh， I see。 Yeah。

 yeah。Yeah。Yeah。I see。 that's a good question。 I never thought about that。

 I actually don't do causal analysis because I think it's bogus。

 but I think it's really good to know this lecture。 I think it's super useful to know this material。

 but I also think most on the one it's bogu， on the other hand it's how we get drugs so it is super important to know wide to randomize control trials work so yeah I'm not teaching you things that I think our uses I don't work on causal analysis because of all the caveats in this lecture。

 I think what you said is a I think that is exactly what I would do so I don't know for a fact what people do but just to reiterate to the class this imagine in the Simpson paradox kidney stone data。

 probably a small stone was say 70% and probably big stone was 30% and what this student was cleverly asking was suppose I knew in the larger population that it was different from that。

 It was actually 80 and 20 should I use those probabilities here I would say yeah if you want to know the treatment effect in the correct population you would change that。

 And I think that would be mixed。😊，Make sense， and I think that would be a valid correction。So。

 but as I've said many times， like in order to use this adjustment formula， it requires knowledge of。

Of the structural equation model so that I know which are the confounding variables。

 So critically here， I have to distinguish Z as this thing I know to be a confounding variable。

 I don't know what's a confounding variable unless you give me a structural equation model and that's like the crux of the whole problem here and in some sense it's a bit of the crux of randomized control as well but this's a bit easier there but here it's just like yeah sorry this just a small aside one I taught this and someone said this looks like the law of total probability and I stared at well and I couldn't figure out immediately why it wasn't。

 but if you just use the laws of statistics and total probability you'd break this looks like y given x and it looks a lot like this but the difference is this conditioning of x isn't here。

 So if you're tempted to think you didn't need any causal reasoning and you could have just used the rules of probability this is just to show you that you couldn't but a little bit of a side I want to just go back a slide and say the point is。

that I need to know what the causal graph is in order to do this analysis and to be fair。

 I don't actually need to know the pseudocode of how it gets generated。

 I just need to know the causal， the graph part of it because I need to know if there's a confounding variable and I don't need to know the details beyond that。

 I just need to know as a confounding variable which I can read off the graph。

So so now I talked about a confounding variable。 But what if there's like other variables in the mix。

 Should I correct for all the variables that I can。

 Like what might happen if I start correcting using the adjustment formula for other variables is it going to help me。

 is it going to hurt me。 And so it turns out that there's other variables that have different names。

 they're not called confounders one of thems called a mediator。

 and I should not control for that in the injustment， or I will shoot myself in the foot。

 And so here's an example， It says that smoking creates tar deposits in the lung。

 and tar deposits in the lung create cancer。 but also it says that there's probably some other elements of smoking that also cause lung cancer。

 And now if this is true， then if I if I get rid of the effect of Z。

 I'm actually getting rid of one of the effects that is on the true causal path between smoking and lung cancer。

 So it's not the case that Z is pointing to both of these。

 there's actually a causal path going through Z。That's why we call it a mediator。

 It's mediating the effect of smoking on lung cancer。 It's a mediating effect。

 And this is a separate effect。 So both of these are contributing to why people get lung cancer。

 And if I remove the effect of this one， I will actually get a smaller causal average treatment effect。

 then is the correct one， because I'm actually removing correct information because I can I should only be doing that for the confounding variables。

 And according to the definition of a confounding variable， it is not this。 And furthermore。

 hopefully， you can see some intuition about the mechanism here of why that might also lead you astray。

And so right， if I control for that， I'm going to get a smaller average treatment effect than or yeah。

 treatment effect is such a funny word。 But here because you're treating with smoking to see if you get lung cancer。

 But this the same， we always call it the treatment effect。

 but you'll get a smaller causal effect as measured by the average treatment effect of smoking on lung cancer。

 if you treat the tar deposit as a confounding variable in the adjustment formula。嗯。

And so it's called a mediator。Okay， now I'm just going to go over one other type of variable that has a completely different intuition to it。

 It's called a collider variable。 And so right， so just to be clear， the confounding variable。

 it had to point to the two things under consideration。

 The mediator is on a directed path between them and。The collider is pointed to。

 It's like the opposite of a confounder。 confounder points to both of them。 The collider。

 both of them point to the collider。 and the collider is like has given some people's lack of knowledge of this has given some really wacko results in some studies。

 So collllider variables are those that have incoming causal effects from the two variables。

 We're trying to understand a causal relationship between。 And if you condition on a collider。

 meaning you put it in the adjustment formula。 not only will you。

 you're not going to just reduce the average treatment effect。

 you're going actually flip it around to go in the other direction。 And so。

Sometimes called Berkson's law。And so I have an example here。

 So the example is basically the way to think of this is。How does someone end up in the hospital。

 this basically says if you have pneumonia， there's a causal link to being in the hospital。

 if you have a broken leg， there's a causal link to being in the hospital。And that makes sense。

 I think， to everybody。 but there's like another bit of information here， which is that。

You don't usually end up in in the hospital because of both of these， right。

 Like usually you have either pneumonia or you have a broken leg。

 And so what we call that is that either pneumonia or a broken leg is sufficient cause for being in the hospital。

 I don't need both of them， I just need one of them。 And so if I tell you that I have a broken leg。

And。Then it explains away the other causes。 Like basically。

 if I tell you I have a broken leg and I ended up in the hospital。

 it's very unlikely that I also have pneumonia。 like like that's just， I mean， it's possible。

 but it's unlikely。 And so this is what we mean by knowing one explains away the other。

 And so what happens in such a scenario is if you condition if I use the knowledge that I have a broken leg and that I'm in the hospital。

 And then I ask for whether there's a link between pneumonia and being。Sorry， between these two。

 then they start to look anti correlated。 but that's only because I conditioned on being in the hospital。

Like， if I hadn't told you I was in the hospital， they wouldn't be anti correlated。

 It's a little nuanced， a little hand wavy。 but like this。

 this is the argument and it's backed up formally。 And so the point being here is if I were to treat this as a variable in the adjustment formula that I correct for or a condition on or I think of it as a confounder。

 What will happen is it will make these look anticorrelated with each other。 when， in fact。

 there's no causal link between them at all。嗯。Because if I tell you I have a broken leg and I tell you I'm in the hospital。

 then you know that I don't。 It's very unlikely I have pneumonia so。It's unlikely。

 but they wouldn't look anti correlated。 They， they would， they would not look correlated。

 But here they'll actually look anti correlated。 is the issue。 It's not that。 yeah。

 like in the random population， there will be some co occurrenceres。

 but they won't generally look correlated。 here。 They will look anti correlated， yeah。Okay。

So the first half of the lecture gave you some intuition about Simpson's paradox and how things can go wrong。

 and I gave you some of this formalism of the structural equation model which is written as a program which corresponds to a causal graph and from the causal graph I can read off different kinds of variables。

 the one I care most about is this confounding variable because I want to put those in the adjustment formula so that I can compute the average treatment effect on observational data so we have this sort of intuition and the other thing that I showed you is how is doing something different than conditioning on something and that those are not equal to each other unless you have a no confounding variables when two variables are confounded by a third variable than doing is not the same as conditioning but we showed that you could break it up using the adjustment formula with knowledge of the confounding variable to kind of go from conditioning statements to do statements。

And so but as I've said over and over， all of this formalism is only as good as that structural equation model is an accurate picture of reality right like I'm treating it as like I read off the structural equation model。

 this is a confounder so it goes in the adjustment formula This is a collider so it does not this is a mediator so it does not and now I have some data how do I know like how did I get that structural equation model and how can we create an accurate structural equation model and after I've created it。

 how do I know if it's correct or not and so in all the rest of this class which was about non-causal machine learning。

 we can estimate how good a model is， for example， by using cross validationidation or nested cross validationidation。

 we get some estimate of the accuracy but there's no analog of doing that for a structural equation model you cannot make use of any of those tools you have to use basically domain knowledge and expertise So there's no way you consider sit it your computer have a holdoutet and ever figure out if you have the correct structure。

😊，Equation model you could get a good graphical model。

 but you wouldn't have any causal layering on top of it。So to get these causal effects。

 you need to make assumptions about what this sort of causal narrative is as encoded by the structural equation model and if you have a causal graph。

 then you can read off what are the correct variables to put in the adjustment formula and so forth and so the punchline here is that there is bodies of work on how to build these structural equation models and so forth。

 but they all have lots of assumptions baked in and in general it's extremely extremely hard to extract causality from observational data。

 but if you take more advanced courses， the economists have some clever tricks for getting things and then of course we do have randomized control studies and so forth which can make things easier so that's the punchline here is to just give you some understanding of this area so you don't go get misled trying to do causal analysis or trying to interpret。

Anyything you've done in mainstream machine learning as some sort of causal analysis and so we'll wrap up here for today I think yeah it said last slide okay yeah if you want I think there's in the I don't even I not sure I remember this but if you want a proof of the adjustment formula I'm skeptical that is anybody here want the proof of the adjustment formula Yeah well if you want it is there is also in the reading so the next lecture the last lecture is going to be the closest thing to my heart perhaps which is on specifically within computational biology I'm going to tell you about alpha fold and protein structure prediction and protein engineering so see you on Thursday。

And I'll stay here for office hours if there's any questions because I think there's nobody coming in based on last class。

哦。系。嗯。か。Mh。😊，回家。I'm trying to encode a situation。With causal knowledge and to do that， I need to。

This is。F。And then you're right in real life。The nutst's kind of one of the gaps is like。

 what would you ever know？program looks like in real life at I。e。

 how would you ever know what the structure it create？还不能。You have to already。我 the result。真是。肯定是て。そ。

まずす。啊。然。あで不す。要你啊。いきえさ。你。就在这村子那。

![](img/2363949c6bbe943856fbcbd09954e4d1_8.png)