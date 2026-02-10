# UCSD《数据科学原理 (DSC 10 Principles of Data Science Fall 2024)》中英字幕（deepseek - P24：DSC 10 - Principles of Data Science - LE -A00- - Lecture 24.zh_en - GPT中英字幕课程资源 - BV1hmAneGEZh

All right， and good morning， guys， I'm getting a little sick。 so excuse my voice。 I'll do my best。

We have homework due Tuesday and then the quiz is Monday。

 so try to do as much as you can before then。And the final project is out。

 so that's a good thing to work on whenever you get a chance。All right。

 today we're going to learn about this type of testing that we mentioned at the beginning of last class called permutation testing。

 it's the type of testing that they used to figure out that Obama's campaign website was better off a certain way than another way and that brought in a lot of donations。

And we're going to answer two questions based on this strategy the first question is about whether babies born to smoking moms and nons smokingmoking moms weigh different amounts and the second one is about the pressure drops of footballs coming from two different teams there was a football scandal called theflat gate that that refers to。

Okay， so the situation。I as follows like all the hypothesis testing we've done so far we'll call that standard hypothesis testing and what that means is you have a population and a sample and you're asking does this sample look like it came from this population so it could be like the eligible population and the jury or it could be like the population of half heads and half tails and the set of coin flips you actually have so in any standard hypothesis test you know the population。

In permutation testing， you don't know the population。

 instead you have two samples and your question is basically did these come from a common source。

 did both of these samples get drawn from the same population。

 even though you're not saying what specifically that population is。Okay。

 so standard hypothesis testing is a known population distribution and permutation testing is unknown。

But it means we're going to need a slightly different strategy to like do our simulation because。

For standard hypothesis testing， you know， like the null says it's drawn from a population that's you know。

 26% black， like there's concrete numbers that you draw from， but for permutation tests。

 you're not going to have that。 so we're going to need to be a little more creative。Okay。

 this is the first example， smoking in birth weight。And last time we looked at。

This data from a research study。That says whether each mother smoked or not and how much your baby weighed。

In ounces。And then。If you look at two different histograms on the same axes。

You see that like the ones where the mother smoked， that's blue。

 their babies tended to weigh a little less than the ones where the mothers didn't smoke。 that's red。

O。If you organize the data according to their mother's smoking status and take the mean of each group。

You can see that there is a noticeable difference in the means。It's about nine and a quarter ounces。

Okay。And so our question is like basically is9 and a quarter ounces a big deal。

 is that a significant difference for these two groups or is it just the case that like any two random groups might have had a difference like this。

 the way I think about this is like there's many ways you can split up the babies into groups So like we split them up by mother smoking status and non-s smokingmoking status and we found in  nine ounce difference right What if you split them up by whether their mother was left handeded or right handeded or whether they were born in the AM or born in the PM you would also have differences in the groups。

 but most likely those differences would be just due to random chance。

 and they would probably be a small difference in the groups， not probably not as big as 9 ounces。

9 ounces feels like a lot when babies are born at like 120 ounces。Percentage wise。Okay。

 but that's the question like is the nine ounces a lot or is it the type of thing that can be explained by random chance？

So the null hypothesis is that these all of these babies come from the same population。

Of just babies。 And in that population of babies， right， how much baby's way is the same。

 regardless of whether their mother smokes or not。 Like it's just one common。Distribution。

The alternative is like there's some set of weights or some distribution of weights for babies born to non-s smokingmoking moms and a different distribution of weights of babies born to smoking moms。

 and in particular the weights are lower on average for the smokers because that's what we saw in our sample so our alternative usually reflects sort of what you see in the observation。

And can this， the alternative says it's not just random chance。 Like there's a reason for it。

 basically。And the thing we're going to use to quantify how different the two groups are is how different their means are。

 subtract their means， and notice I'm doing no absolute value here and that's because the alternative is has a direction to it。

 right？So think about is big values of the test statistic or small values of the test statistic going to make you lean towards the alternative？

TheAltern is saying。Smoker weight， baby weight is lower than non smoker baby weight。嗯。

So if that was true right， non smoker weight would be a bigger number and the smoker weight would be a smaller number。

 so it would be big minus small， it would be some positive number。

 the bigger this number is the stronger evidence of the alternative。RightIf it's close to zero。

 that's evidence of the null。 If it's a negative number。

 that actually means sort of the opposite that smoker babies are weighing more。And in that case。

 we would also go with the null， right， because we don't have evidence of the alternative。

 So this should remind you of like the coin flipping example when you're trying to detect bias towards tails and you happen to see bias towards heads。

 you still call it fair。Okay， so basically。Thinking about do big values or small values of the test statistic make you lean towards the alternative is going to help us when eventually I have to calculate a P value。

Cause I want to say， like， how often do I see something equal to the observed。The observed is。

Nine and a quarter。or greater or further in the direction of the alternative。 and in this case。

 further in the direction of the alternative is greater。 so our question will be for the P value。

 how often do we see a difference of nine and a quarter ounces or more？😊，Okay， any questions so far？

Okay， this is where things get a little new。So like so far we've just set up our hypotheses。

 stated our test statistic， the next step in a hypothesis test is to do the simulation under the assumption of the null hypothesis and that has been pretty straightforward in all the examples that we've seen because the null hypothesis has had very concrete values associated with it right like just flip a fair coin or draw from a population that has this ethnic distribution right like you had numbers to do that so you just did it in code。

😊，But now it's like， I'm supposed to somehow generate new samples under the assumption that the null hypothesis is true。

 The null hypothesis is that both the smoking moms babies and the nonsmo mom babies come from the same population。

Right，But the problem is， I don't know what that population is。

So how am I supposed to draw samples from it？What I would want to do。

Is draw two samples from that population？Of the same sizes as our original smoking and non-smoking groups。

 right， if you had a proposed population and your question was like did these samples come from this proposed population。

 what you would do is you would look at other pairs of samples from that proposed population and say how different do they come out when it's just random samples and compare that to how different our actual two samples came out when it was based on smoking status。

Okay so。You want to be able to draw two samples from your population that are the same size as your original。

And compute the test statistic on those two random samples。

 the problem is what's the population that I'm going to draw from。

 you don't have a population so you can' draw。And the clever solution is you sort of make a population by putting your two samples together。

And this is similar to the like an idea that we've used before that like samples represent populations right so we have like a big set of smoking moms babies and we have another big set of non-s smokingmoking moms babies and we're asking like do both of these samples look like they were drawn from some larger population of just baby weights？

But like how much do babies weigh' what's the distribution of baby weights Well。

 I don't know exactly， but I do have like two big collections of baby weights。

 so I just put them together。 that's like one big collection of baby weights that includes babies of smoking and non-s smokingking moms so I just use that sort of constructed population will call it as my population and I draw samples from there。

Does that strategy make sense？Questions。开下。This aligns with the null hypothesis because the null hypothesis is basically saying the smoking status doesn't matter for the baby weight right so it makes sense to think of them all as coming from one big population because you're saying under the assumption that there's no difference between smoking or non-s smokingmoking baby weight。

 So it's just a whole bunch of baby weights。Okay， so this is a little。Sliidehow。

That illustrates this idea。Imine we had a data set of only seven plus4，11 babies。 Okay。

 there's emoji symbols。 The seven on the left come from non smoking moms。

 right and the four on the right come from smoking moms。We could calculate the mean of each group。

And calculate some observed statistic Okay， so our observed statistic comes from taking we did non smoking minus smoking。

 so 128 minus130 gives this negative2 number our data that we have。 It didn't come out negative2。

 It came out positive 9 right so it's different It's going to be different numbers。

 but this is just a small example to help you visualize it more concretely。Okay。

 now the idea is you put all these babies together to make one big population。

And from this population， you want to look at what would happen if I drew two random samples of the same size as my original。

Okay， so you have a population that consists of 11。Babies。

 right and you want to make a sample of size7 and a sample of size4。

So one way to think of doing that is just sort of randomly rearranging these 11 values。

Say you like shuffle them up。And then put the first seven over here and the last four over there。

Do you agree that that's like a random 7 babies， the way you do that， Put them all together。

 mix them up。 Take the first set。 Okay， that's a， that's a random 7 babies。

 These four over here are the other four babies。 And you can think of this as like a random splitting。

So you can think of the original data you have as like a non-random splitting right you have all the babies and you're dividing them into groups based on their mother's smoking status and you're going to compare that to the statistic that you get when you do a random splitting of the babies so what would the statistic come out like in this case。

 well this case I got 130 over here in 128 over there so it came out to positive too？

And the question is， is the observed value？Similar to the kind of thing you get from random splittings。

 like does the does dividing the babies by smoking status kind of look just like as if they were divided randomly or does dividing them by smoking status look different than random。

 That's the question we're asking。Okay， so we're going to do this many times。

 just reshuffle the population and resp it。Se me。Into two groups。

So the idea is get lots of test statistics。Right by doing this many times， and then we ask。

 is the observed like the ones we generated？Okay。And this gives you the empirical distribution to compare to。

off。Allright， now in that little illustration。I did this thing where I put all the data together。

 then I rearranged it and then divided it。This process of rearranging is called either shuffling as a non technical term or permuting as a technical term。

So permutation。Of a sequence is just a rearrangement of the elements there。 So here's a string ABC。

 right， you can rearrange it like BAC or like CA A B。

 There's actually six per mutations of those three letters if you want to try to write them out。Okay。

So I need permutations to do what I want to do with the。With the example。

 like make my constructed population， then rearrange it or shuffle it up。

 and then divide it into two random groups whose sizes are the same size as the original。

And the way we're going to implement this。Is。To randomly assign the weights to groups， right。

 we're just going to take our data in the babys data frame and shuffle one column。

 We're going to shuffle the maternal smoker column。

Whi basically is like the labels that go with each value and think of shuffling up that data or shuffling up the labels。

 I should say， and then using the shuffled labels to determine who goes in what group。Okay。

 so I'll show you how this works。The steps of a permutation test are shuffling the group labels。

This is the truths and falses that say whether the mother smokes or not。

 and what that does is essentially like in the illustration。

 gives you two samples from the constructed population that have the same size as the original samples。

Then for that random splitting for those two samples， you compute the difference in group means。

 which is your statistic， and you just do that lots of times until you get empirical distribution and then you compare that to your observed statistic to see if your observed statistic looks like the ones that came from the null。

Okay， so let me show you。How to do this in code， you want to randomly shuffle。

 say the maternal smoker column in the baby's data frame。Well。

Let's just look at a small example first。Say you have this data frame that has two columns。A，B，C， D。

 E in column X， and 1，2，3，4，5 in column Y。 Okay， you can think of AB，C。

 D E as like the labels that say whether or not the mother smoked。And you can think of one， two。

 three， four， five as being like the actual baby weights。

We already know about the data frame method dot sample。

So if you do dot sample and you say sample five rows because this data frame has five rows。

It'll give you the rows in a different order， so dot sample permutees。

 but it permutees full rows okay and that's not what we want here because each letter is still associated with the same number like a goes with one E goes with five D goes with four and so on right so that's not really like changing like how the babies are divided into groups that's just changing what baby is the first row and what baby in the second row but it's still the same set of babies。

Okay， so there's another Python function that's useful。 It's called NP dot random dot permutation。

 and it takes in a sequence like a series or an array and it returns a shuffled version of it as an array。

 So the X column of the data。Was the letters A through E？So if I feed that into NP。random。

permutation， it's just going to give me those five letters in a different order， probably。Okay。

 so this is random。 Here' are some examples。Why is it always giving me the same thing？No's not。

 but they tend to start with B。That's weird。O。Here's one doesn't start with me， okay。

I just shuffled the data from the X column and I added it as a new column to my data frame。Okay。

 so notice the relationship between the Y and the shuffled X column。

It's different than the relationship between the original y and the X column， right。

 It used to be that a was next to1。 Now A is next to three and D is next to1。

Okay so by shuffling one column， that's like changing the labels associated with each data value。

 which is essentially doing what we wanted of putting the babies into two random groups Okay。

 so let's see it。With the baby data。So I had my maternal smoker column。

And I had the birth weight column that was the original data that was given to me。

 And the way I think about this is the maternal smoker column sort of defines the。

The actual or the observed groups。this label is meaningful。

It talks about whether or not the mother actually smoked。

So depending on your value in the maternal smoker column。

 that tells you which histogram you're part of when I do the red histogram or the blue histogram。

 that's a meaningful value there。But the shuffled labels column just came from a random permutation。

Of the smoker column。what's the point of doing a random permutation？Because it's random， right。

 the association of labels to birth weights is like no longer meaningful， right。

 It doesn't mean that this 120 or not pound 120 ounz baby right， came from a smoking mom。

 It's just saying I'm going put this 120 ounce baby in in group true。

 and I'm going to put certain other babies in group true。

 And I'm going to put other babies in group false， right， So there's really no sort of。

Logical meaning。To who's in what group here。The groups are random。But because it's a permutation。

There's the same truths and falses as there were before just in a different order。

 so there's the same number of truths and the same number of falses。Do you agree？

You just mix stuff up， you don't change the contents， right， you just change the order。

 so there's the same number of truths and the same number of falses as before。

Which means if you use the label in this column to define two groups。

 those two groups will have the same sizes as if you use the labels in the original columns right if there were seven falses and four truths like in the little slideshow example and you mix those up you're still going to get seven falses and four truths So if you use the sort of mixed up labels to determine the groups。

 it's like getting two random groups that are the same sizes as the original。

And that's exactly what we wanted。 So this whole idea of permuting is just like a mechanism by which you can define two random groups。

 right， There's other ways that you could define two random groups。

 This is just a convenient way to do it。Does that make sense？Okay。Questions。Okay。

 so now that I have my two random groups or the the groups that came from the shuffling。

 I'm gonna look at how different they came out， right by。

to find two groups according to what shuffled label they happen to randomly get right so if some of the babies happen to get a label of false。

 some of the other babies happen to get a label of true。And there's a difference here。

Of about negative 1。5。 Okay， I'm subtracting in the same order that I subtracted before。Which was。

 I guess it was non smoker minus smoker。 So the false minus is true。

So that's the test statistic that you might get if the two groups are randomly determined。Okay。

 and I need to just do this many times to see what kind of test statistic I often get when the two groups are randomly determined。

Okay， so that's the test statistic for one experiment or one shuffling。

Here's a little function that does this， given a data frame of like the baby data frame。

 but with an extra column of shuffled labels， it organizes the babies into groups and calculates the difference in means of each group。

Okay， so this is the main simulation。I need to do it lots of times to figure out how often will a random shuffle result in a nine and a quarter ounce difference。

Okay， nine and a quarter plus， that's because of what we talked about before。

 with big values are further indicative of the alternative。So every time our simulation goes。

 we're going to reshuffle the labels because that's creating two new random samples from the same original data。

I'll add my shuffled labels as a column to the data frame。

And then I'll use that column of the data frame to determine two random groups。

 and I'll calculate their difference in group means according to the function I just had and I'll store the results in some array。

Okay， so this is。What the code looks like。The usual array to store my results。

A four loop that goes a bunch of times。 I'm doing 500 times。

 really you'd want to do as many as you can， but this is a big data set so I can only do 500 in a reasonable time and class。

shhuffled labels。This is taking the maternal smoker column。

 which had the truths and falses and mixing it up randomly。This is adding them on。

As a column of the data frame。And then this is calculating the difference in group means for the two groups that are determined by that shuffled labels column。

 so this is calling the function that I wrote earlier。

 and then this gives me a single number like in our example it came out negative one and half and I'm just going to append that number onto my array of differences。

And in the end， it's going to look like this。😊，Okay， so what is this saying？

It's saying when you just like split up the set of babies like any which way， like a random。

Splittting into two groups， they may have like。One group weighs like two ounces more than the other group。

 or maybe one group weighs two ounces less than the other group or one ounce。

 like one or two or three ounces。Of deference in either direction。

Is like the kind of thing that usually happens when the groups are just random and don't have any meaning button。

And what we're going to do is we're going to compare that to what we observed。

 which was a nine ounce difference and pretty clearly like a nine ounce black bar would be like off the edge of this screen。

 that's very very surprising if that happened by randomness alone， so it probably didn't okay。😊。

Notice that this distribution is centered as zero that kind of makes sense because the groups are random right when you take two random groups。

 there's no reason why like group A is going to come out bigger than group B in general like it's random right so about half the time group A is going to have a bigger mean and the other half of the time group B is going to have a bigger mean so it should be centered as zero。

It there's a lot of weight towards the middle， right。

You generally do have a difference that's small and it kind of tapers off as you go out。

Or how far does it go out is the question really？And then。Our black line。Way over here， right。

 what's the P value？Without running it， can you tell me the P value from looking at the picture。0。

 the P value is how often in the experiment did I see something 9 in a quarter or greater， right。

 What fraction of the time did that happen，0。 That's what P value means。Okay。So yeah。

 this is like super rare。We don't think that babies born to smoking moms generally weigh the same as babies born to nonsmoking moms right there's probably different distributions describing the weights of smoking moms babies versus the weights of nonsmoking moms babies okay the hypothesis test never tell you why right a logical plausible explanation is smoking causes lower birth weight right that couldn't be the case it can also be the case that like there's another hidden factor at play like people who smoke are more likely to drink caffeine and caffeine causes lower birth rate right there's always a possibility for some like hidden factor so we have to be careful before we ascribe like causation like this cause to that。

But it's definitely like something to look into further， right？

So this is how a lot of like research studies are done。

 they you know have some idea that this might matter and they do a test like this to figure out like we're onto something right and then they might need to sort of eliminate other potential factors like caffeine like you could do a similar experiment where you had a bunch of baby weights and you just said did your mom drink caffeine or not or how much or something and you can look for connections there。

Okay so。The baby smoking example is sort of our go to example for the permutation testing and this is a little summary that shows kind of what we did Okay。

 so we're given real data we're given real data。They come in two groups， right。

 the weights of smoking moms babies and the weights of non smoking moms babies。

 You can think of these as group A and group B。And through simulation， we repeatedly create。

Two random groups that are the same sizes as the original smoking group and the nons smoking group。

 okay the permutation， because rearranging things doesn't change what's there。

 right that sort of forces the groups to be the same size as the original and because it was a random permutation you get random groups。

And then for each pair of random groups coming from all the babies put together。

 you calculate the difference in group means， which is your test statistic。

 You do that many times to get a whole distribution of test statistics。

And then you compare that to the observed difference between the group means that's where you draw the black line and then you draw a conclusion from there。

All right， here's a concept check question for you guys。 The baby's data frame looks like this。

 I'm just showing you the first three rows。It has the maternal smoker column and the birth weight column。

 and what we did here was we shuffled the maternal smoker column。

And then we use a shuffled version of that column to split the baby weights into two random groups。

Would it have also worked to shuffle the birth weight column instead？Okay。The answer is yes。

 it would work either way and the idea is that like the whole point of shuffling and using the shuffled data is to split the data into two groups right we want to take this set of baby weights and put some in group A and some in group B and they need to be the same sizes as we had before so our mechanism for doing that before was like rearranging the labels but it's equivalent to rearrange the data。

 so if you think of you take that birth weight column and you like shuffle it and put the same numbers in some other order right and then you use the original maternal smoker column to define the two groups you're still going to get two groups that were the same size as they originally were because you haven't changed the number of true and false labels but which numbers fall in the true group and which numbers fall in the false group that's just going to be ran。

Another way to think about this is like if you need to sort of reassociate。嗯。

Two sets of objects think of like the people in this room。 almost everybody has a computer。

 So it'll say people and computers， right if I wanted to randomly assign people to computers， right。

 one strategy for me to do that is collect all the computers and redistribute them at random that's like leaving the people fixed and shuffling the computers Another strategy is I leave the computers on your desk and tell everybody to sit in a different seat next to a different computer right。

 that's leaving the computers fixed and shuffling the people you could even do both like collect all the computers sit somewhere random and then distribute them randomly。

 Like it doesn't add anything by doing that because random is random， but any of those work。

Does that make sense。Right。All right， on my favorite example。 did the New England Patriots cheat。

 So raise your hand， if you know of the story of Def F G。Okay， not too many。 It's getting older。

 I guess this was from 2015。The New England Patriots played the Indianapolis Colts for a spot in the Super Bowl。

 which is the biggest tournament in football。So the Patriots won this playoff game。

 and then they went on to win the Super Bowl that year。But after the game。

The the Patriots were accused of intentionally deflating their footballs and when you have deflated football with less air。

 it's easier to catch， so it was basically accusing them of cheating by letting out air of their footballs to give them an advance。

The scandal was called Deflate gate okay so I learned a lot about football when I learned about this example。

 one thing I learned is that they don't just give you footballs to play with each team brings their own footballs and you have to bring 12 footballs to the game and you play with your own footballs while you're on offense。

😊，And there's regulations about the footballs you can bring， including。

How how much air they have to have in them， Okay， so pounds per square inch is how we measure air pressure has to be between 12 and a half and 13 and a half pounds per square inch。

And they check this， the officials measure the pressure in each football。

 and they saw that the patriots。Were around 12 and a half pounds per square inch。

 which was acceptable because it was like in the range， but it was the bottom end of the range。

 and the cults were like in the middle of the rain。Okay。

 nobody wrote this down because nobody knew this was going to be like a major scandal。

 so this is very realistic data where you're just like working with what people remember and some incomplete data that they don't have everything。

 but we can still draw conclusions based on what we have。Okay。

 so notice the Patriots are the ones that were accused of deflating their footballs。

 but their footballs already started out less inflated okay so that means it's not going to be fair to compare like how much aed the Patriots football have versus the Colts football because we expect the Patriots to have less My question we're going to ask is about how much pressure the pressure dropped by right like all footballs lose a little bit of pressure from being used like grabbed and thrown and tackled and all of that。

But like， did one team's footballs lose more air than the other teams's footballs is a question we're going to be asking。

 Okay， so how did this become a thing， Well， one of the cults intercepted a patriot's ball and told the official that we think it's underinflated。

So at halftime， there was a significant break in the game。

 and two of the referees measured the pressures of as many of the footballs as they could。 right。

 It's really important to note they， they didn't get all of them， but they。Oops。

 they got some from each team。It wouldn' you wouldn't be able to draw any conclusions if all they did was measure the Patriots footballs because even if the Patriots footballs were down from 12 and a half to three。

 they could have argued， well， that's just what happens when you play football you have to have like a comparison point to say that like no。

 this doesn't just isn't just normal， basically。Another instance of real life data。

 They didn't get to all of them。 Like ideally， we would have had all the football data， but we don't。

 So we just have what we have。And this is what I was talking about before。

 the change in pressure is what matters， not the actual pressure at halftime。

Because the allegation was about deflation。Okay， so here's the data。We got 14 rows。

 which means they measured 14 of the 24 footballs at the halftime。This pressure number。Comes from。

An average of the two officials numbers。And then the pressure drop is the difference between。

The original starting amount， which remember wasn't recorded anywhere。

 it was just recollected for the Patriots that was 12 and a2， so this number 0。85 comes from 12。

5 minus 11。65 and for the cults it was remembered to be around 13。

 so the pressure drop there comes from 13 minus 12。53。你可。And the question is。

 did the Patriots footballs drop in pressure more than the Colts footballs？Okay。

 and this is a situation for a permutation test because you can think of the the data set of。

Pressure drops of patriots balls as like one sample and the pressure drops of Colts balls as another sample and we're asking like is this just like how footballs behave in a game like is this just what happens when you play football balls drop a certain amount and the amount that the patriot ones dropped is similar to the amount that the Colts ones drop。

So the null is that the drops in pressures for both teams come from the same distribution。

And it's only by chance that the Patriots footballs deflated more。Right。The alternative is like， no。

 the Patriots footballs deflated more than you would expect based on chance alone。

So notice the alternative has a direction to it， says the Patriots footballs were like too deflated。

 we're not questioning whether the cult's footballs were too deflated， right。

 so our test statistic is going to be the difference in means。

 but it's not going to have an absolute value because we care about which team had less pressure than the other。

Okay， so in most permutation tests， the statistic that you use is the difference in group means。

 and the only thing you have to consider is should it be an absolute difference if if you don't care about the direction。

 you're just saying same or different or should it be a non- absolutesol difference if you do care about the direction。

Okay， so we're going to。Look at the average drop in pressure for each team。

The Coltz balls dropped around half a pound per square inch and the patriots dropped like one point something。

 so there's a difference right， is that considered a big difference is our question？Okay。

 so how far apart are these numbers about 0。73， that's our observed difference of the means or 0。74。

 I guess。so it seems like the patriot balls dropped in pressure， 0。

74 pounds per square inch more than the Colttz balls dropped in pressure。Okay。

But is that amount of difference a big deal， That's what the permutation test tells us。

So what we're going to do is we're going to look at if we took the same set of football pressure drops。

And reassociated which pressure drops went with cultts and which pressure drops went with patris。

Right， we have。14。啊。Footballs。And we want to like， reassociate which of these numbers get。

 get a label of patriots and which of these numbers get a label of cults at random。Okay。

 so in the previous example， we shuffled the maternal smoker column which was the labels right here for some variety。

 we're going to shuffle the pressure drop column， which is the numbers but the thing we just talked about with the concept check question was like it doesn't matter which one you do。

 the point is which numbers fall with which label is going to be random。可以。

So one thing I like to do for permutation tests is only keep the two columns that I really need Any permutation test you're only going to need two columns。

 one is the numerical data here it's pressure drops in the previous example it was baby weights and then you're going to need another column that tells you what group does this number go in right So the labels here it's patriots cults last time it was smoker nons。

And you're going to take one of those columns。Here I'll take the pressure drop numbers。

And I'm just going to reorder them。 Okay， so this is the same set of numbers that come from this pressure drop column。

 but they're in a different order。 And now I'm going to put that on as a new column of my data frame。

 Okay， and I'm basically going to ignore。This middle column now。And look at these two columns。

 these two columns together。Toefine two random groups of footballs。Does that make sense？

So I'm going to look at the ones that have a label of patriots versus the ones that have a label of cults。

 how different were their average pressure drops？And how different are they？08 or 。09。Okay。

 not that different。There's some difference。Not that different。 Okay， now we got to see like。

 how does this usually come out， We just did it once。

 So now we're going do it in a four loop many times， okay。

I'll make a little helper function like I did before。Given a data frame of pressures。

 I'm going to group that data frame according to its team， take the mean of each group。

And then compare the patriots mean and the cults mean and subtract。So there's my helper function。

And this is me doing the simulation 5，000 times I can do it way more times than I could for the Baby weights example because it's a much smaller data set。

 it's only like 14 rows and that had thousands。可。And this is the code， right。

 permute the pressure drops。Add them on as a new column。

Calculate the difference in means based on that new column and then append it to my array of results。

Okay， so here's the array of results。 And as before， when you look at a histogram。

 you should see that it's centered at 0， with a lot of area in the middle。And the question is。

 where does the black line fall， Does it look typical of the， of the red histogram。

 So it's not as extreme as the last case where it was like way off the edge。

 but it's still pretty much in the tail。Right， let's look back at how we。How we set up our。

Test statistic。Okay， so our， our alternative was that the Patriot footballs deflated too much。

 basically。And our test statistic is。Mean drop for patriots， minus mean drop for cult。

So if the patriot balls deflated too much， their mean drop would have been a lot bigger than the mean drop for the cults。

 so this difference would have come out really big like a big number here indicates that the Patriots were cheating basically。

Does that make sense？Okay， and then I， I ask myself when I see this picture， is the。

 is the black line like too big for the red distribution。And it's not like absolutely too big。

 but it's like pretty big， right？It's on the far right side。And the P value。

Tells you how likely or unlikely it would have been to get something like this if the null hypothesis was true。

So the P value is if the null hypothesis were true。

 what's the probability you would have seen something as or more extreme？Than what you observed。

As or more means greater in this case right so it's like the area to the right at or to the right of that black line。

And this is how you might calculate it。😊，And it's really low。 It's less than 。01。Okay。

 so this is actually not only like significant， but it meanss it's below the 0。01 level。

 which is the terminology highly statistically significant。

 like we're pretty sure that the Patriots balls didn't just like naturally lose this much air basically。

So we're going to reject the null hypothesis as we don't think that this difference in pressure drops could have just been randomness alone。

 couldn't have just been due to random chance， or it's very unlikely that it was。But again。

 you can't say based on this that we're sure that the Patriots deflated their footballs。

 Can you think of an alternative explanation。Like it right。

 something a defective set of footballs that like loses more air than it should or something right。

 again， pretty unlikely given their professionals， but like right。

 you can't say for sure other ideas。Okay， so there can be like the physics comes into play with this with like the temperature and things so like we don't have that information of like where were the footballs measured。

 maybe like the Cols balls， where were they stored。

 maybe differently than the Patriots balls and where were they measured。

 what temperature were they measured like there's a lot of physical aspects that could make a difference if they weren't the same for both teams。

But probably they were the same for both teams， right？So the NFL actually like looked into this very。

 very carefully because this was a big scandal and accusation。

And they concluded the same thing that we did， which was that the average pressure drop of the patriot balls exceeded the average pressure drop of the cults balls by an amount sort of somewhere in this range。

 depending on various possible assumptions regarding the gauges used and assuming an initial pressure of 12 and a half for the patriots 13 and half for the cult so that's we that's what we used was these remembered initial pressures。

 but there's various。Assumptions you can make about the physics of it。

 And so that this is kind of like an interval， like a confidence interval for how much they think the。

The difference in pressure drop was， right？And they did more than just statistics like we' were analyzing this from a statistical aspect。

 but they also had physicists and things looking into it from other angles and in the end they basically said like this is too crazy that this would have just been chance。

 so they find they had some small consequence， a million dollar fine for Tom Brady and the suspension so you can read more about it on the Wikipedia article if you want any more context but I think that's a good example of how you can use these tools to help you analyze real life problems。

All right， we'll stop there， see you guys next class。



![](img/c62e8ff573b256883ac2432e42874b14_1.png)

![](img/c62e8ff573b256883ac2432e42874b14_2.png)