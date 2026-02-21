# UCB《数据挖掘和分析｜DATA 144 Data Mining and Analytics 2021》中英字幕 p29 [P29]lecture29-[T8 Groups and Pivot] Cross Classification-NdkThna1634.zh_en [BV1efBEBuEVg_p29]

Today。😊。

![](img/4e240d403566ceef8bdebef43b4be61b_1.png)

All right， so now we know about。Classifying by one attribute Okay。

 but then we have seen that when we're doing the classifying on the categorical variable。

 we can do an additional summary okay about other variables if you want to Okay。

 so it's still I guess。Remain as a question of， well。

 if I want to do summaries or like classification about multiple multiple columns。 Okay。

 what can I do， Okay， so the group method again proves to be helpful。

 So you can see that how I guess how powerful the group method could be。

 So we call this cross classification。 Okay， when we're doing this kind of summary across different multiple columns。

 Okay， we're still going do the group method we call a groups here。

 just because is about multiple columns now。 Okay， and it's gonna aggregate rows I share the combination of values in multiple columns。

 Okay， so first argument is the array for which the columns to group by。 Okay。

 and the second one just like before， it's gonna be the function name。 Okay。

 so let me show you without maybe。

![](img/4e240d403566ceef8bdebef43b4be61b_3.png)

Staying on too much on that lecture slide， okay？So we're gonna go back again using the toy example because that's always easier to work with because we only have five rows if you remember Okay so that's ice cream Oh never mind。

 I guess now we have six Okay， but never mind is small data set Okay so we are able to verify what exactly we're doing Okay Al so what we have seen before if you remember is doing a simple count right if I'm only doing the group method on a column Okay categorical column and then of course what we had done earlier as well is that what if I add one。

Argument like let's just do min right And then we're producing the price min Okay so we're doing this summary。

 Okay of the numerical variables。 that's what we have seen so far with the group method。

 Okay now if you remember like say here we have the flavor and the color Okay we'll have two categorical variables Okay maybe you want to do some kind of summaries across the two at the same time。

 So then that's where this groups remember there is s at the end groups method could be useful Okay that is helping us to make summary across two or even more categorical variables Okay so the way to use it is that the method is got groups。

 Okay， so you have to type do groups okay and then also in the input you actually have to make an array of all of the column that you want to work with okay so the way to do that like what we're showing here is you do make array flavor and color So when we do that it's gonna do well we didn't supply any other function about it right so。

Naturally is going to give us account tally and what it does。Is that now instead of just the flavor。

 we're looking at each combination of the flavor and the color and then we're giving account。

So if you have two or more categorical variables， this could be really useful because a lot of times your agrgregigation is not only about one one categorical variable right it could be multiple so for us the flavor and the cover are colors。

 for example， then we're getting the count over there。But also just like the group method。

 the group's method can also allow you to give any kind of function that you want to apply Okay here is being used or like being called on again the numerical variable that you might be interested in okay so for us we still have the price okay so any guess if after I run this line what the output going to be。

We're using the group's method。We're doing flavor and color and we are doing a max。

It's going to show the two rows that have two at the end。

What do you mean by two rows of the two nutss of the cross listings？Oh， okay， yeah。

 so Juliana's point is that it's going to give us the maximum count。

of whatever this table that we're getting。诶。Any thoughts？Agree， disagree， other ideas。

 I was thinking it would give the max price for each combination。Yeah。

 yeah so Samantha also send in the chat as well yeah so I agree。

 especially I think the group method and the group's method actually work in a similar fashion okay so whenever we're doing a so Juliana whenever we're doing a summary or like a function in the groups or group method that function is being applied to a numerical column over here okay so even though I agree it's tempting to think about is giving us the maximum count okay and I'm pretty sure if you do max like in front of this that probably will work give you the maximum count okay but if it's being applied into the group's method is giving us I think the maximum price of each each particular combination。

Okay， yeah， so for us here， as you can see from the title of I mean。

 the name of the column is price max okay， and then it's also four rows because we only have four different combinations anyway。

Makes sense。Sense yeah so again groups and groups they work very similar if you go back to our slides I mean it's two pretty much identical slides we just change the name of the function pretty much so hopefully that also makes the connection for you okay。

Alrighty， so let's bring it back to the NBA example。 hopefully a little bit more realistic。 Okay。

 so this is our data set。 Okay， player position team and salary。 Alright， so again。

 always try to drop the column that is not that useful like for us like if we don't like most likely we don't care much about the name of the player because we want to do summaries about position or team or position and team at the same time。

 Okay so what I'm proposing here is that we're gonna drop the player column So we do like dot drop and zero is remember the index of the first column so we're dropping the first column Okay and then we're doing the groups。

 Okay， the groups here is we're doing team and position together okay and then we do NP do average So based on our lesson earlier about the the max method here what this is doing is that it's gonna group based on team and position at the same time。

 Okay but then the average is going to be reported for the salary。Okay。

 so what this is function is doing and let's see the output here Okay， so see that the name of the。

The players being dropped， okay， and then we're looking at all combinations of team and position。

Okay， and then the average salary。So this is when I think groups is preferred than group because we're trying to do this kind of cross classification across multiple categorical variables。

However， if you only want to know the average of the by position then we don't even care about the team anymore。

 we can even drop that and then only use the group method okay so again the changes or like so this goes back to the earlier demo that we did okay so between group and groups I think the key difference now we know well the name is slightly different right but also just the goal of you what to want to do if you only want to do summary about one categorical variable regarding like numerical variable out there then you're going to do group and then if you are doing more than one like two or even more youre going to do groups。

But when you do groups， make sure that you have to pass all of the。

Coour names as array otherwise I think you's gonna get an error message of not recognizing anything。

 Okay， that's just a key usage over here。 Okay， and let me show you one more example over here。

 This is a pretty pretty large data set looking at age group gender education attainment。

 personal income and population count based on like its it's a tally in some sense about the different categories over here。

 different categorical variables， the age group gender education attainment and personal income in the US Okay so and in particular。

 we're looking at the data from 19202014 sorry okay all right。

 so one thing is that if it depends on what you want to do Okay like what about like say I wanted to know。

Let's just say like gender education attainment and personal income。

 I want to look at like groups of all of those together three variables。

 this is the example of like grouping based on more than two okay and I want to know the total population count。

Okay， so what this is doing is I would drop the H， okay。

And then I will be doing groups method okay this time I'm doing three column， the gender。

 the educational attainment and personal income altogether。

 I'm doing the song over all of the population count in order to get a total population count across all of them。

Okay so then this will give me my final table Okay。

 so this's just an example of what if you have more than two categorical variables that you wanted to do this kind of summary with in fact you can do it with I'm sure with the age as well because there's a categorical variable as well for us is really just a demonstration of how how you can do with more than one now more than two categorical variables。



![](img/4e240d403566ceef8bdebef43b4be61b_5.png)

Alright， that's good and。

![](img/4e240d403566ceef8bdebef43b4be61b_7.png)