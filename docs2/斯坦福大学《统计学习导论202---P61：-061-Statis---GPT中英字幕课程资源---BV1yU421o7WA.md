# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P61：-061-Statistical Learning_ 8.R.2 Random Forests and Boosting.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， yeah we are back again。 we've learned about trees and how to use trees in our。

 and now we're going to see how to use trees in the context of random forests and boosting and we'll see this gives us pretty powerful predictors。

So there's two packages， random forests boosts and GBM， which does boostting。

 we'll start off with random forests。So。As we know， random forests。

Will actually build lots of trees and then average them and reduce the variance of bushy trees by averaging。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_1.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_2.png)

So we load the random forest package， and we're gonna to use the Boston housing data again。

 And that's in the mass package。 So we'll get that up。 We'll set a random seed， and。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_4.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_5.png)

Let's have a look， we see we got 506 observations in the Boston housingous data。And。

We're going make a train set of size 300， so we'll use the same construct as we used before and we got there we've got indexes for training。

 let's just look at the Boston housing data so we can we can query。

 we can run a help query on that and we see it's it's the the 506。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_7.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_8.png)

Surs of Boston。 and for each suburb， we' got。Demographics and things like crime per capita。

 types of industry， average number of rooms per dwelling， average proportion。

 the age of the houses and various things。And what we're going to use as a response is the median value of owner occupied homes for each of these counties。

For each of these suburbs。 Okay， so it's a， it's a data set's been around。

 It was based on the 1970 census in， in Boston。Okay， so。

So well start off with the random forest and same kind of strong construct as before the response is me V median value。

 and to be modeled as dot which means as a function of all the other variables and we want to use the train subset and very fast random forests and we can just print out the random forest gives us a summary。

And。It tells us the number of trees。 So that was 500 trees were grown。

 and they bushy trees each of them。 So as you can see， that was pretty fast。

And it gives you a summary of the fit。 It gives you a means mean squared residual and the percentage variance explained。

And when we studied random forests in the notes， we talked about the out of bag errors。

 So these are out of bag mean squared residuals。 So each。

 each observation was predicted using the the average of trees that didn't include it。

 So these are sort of debiased estimates of， of。Of predictionary。So。

One of the tu the pretty much only tuning parameter in a random forest is。The variable called M。

 the argument called M， which is the number of variables that are selected at each split of each tree when you when you come to make a split。

So if M， for example， is four of the 13 variables in the Boston housing data。

4 are selected at random。Each time you come to split a node，4 would be selected at random。

 and then the split would be confined to one of those four variables。

And so that's how random forests decorelates the trees。

 So what we're going to do is we're going to fit a series of random forests。 The 13 variables。

 So we're going to have M range through the values 1 to 13。And then we're going to record the errors。

 and so we set up two variables to do the recording of the errors。

 and then we go in a loop for Mtry and 1 to 13。 We're going to fit the random forest with that value of Mtri。

 and here well just restrict the number of trees to be 400。For no good reason。

 except that 400 is sufficient here， and we give Mtri as an argument and of course it's fit on the training data。

And we can straight away plug in， extract the mean squared error because that's out of bag error that's on the object。

 so we do that。And then we predict on the test data。

 So there's Boston minus train passed as the data in the argument to predict。

And fit be the fit of the random forest。And， and then we compute the test error。

 So these with construction again。Boston minus train。 and we compute the mean squared error。

 So it's mean of M V minus pre squared。 M V will be picked off。The data frame， Boston minus train。

So these commands that we' still in the loops that's not actually executed。 and they we'll。

 well just。In case it takes long， we'll， we'll print out the value of M try as it's going。 Okay。

 so here we go。 And look how fast that is。So it's 13 times 400 trees have been grown near and it's done。

And now we can make a plot。 And so we actually use a matte plot command because we've got two columns。

 We've got test dot error and out of bag dot error， U dot error。

 So we see bind them together to make a two column matrix。

 Then we make a single plot with matte plot。And you can see we put some other arguments in the matrix。

 We told it to use。Plottting character 19， which I I like。 We gave two colors， red and blue。

 and type equals B means type equals both means it plots both points and connects them with lines。

And， and we gave it a Y lab mean squd error。And we can put a legend。

In the top right corner and we see the red points are out of bag and the blue points or test error。

 Now， ideally， those two curves should line up pretty much and it seems like the test error is a bit lower。

 but be warned there's a lot of variability in these test error estimates And so since the out of bag was computer on one dataset and and the test error on a different data and they' weren't very large。

 these differences are pretty much well within with the standard errors。

 and don't get fooled by the fact that that the red curve is smoothly above the blue curve。

 These error estimates are very correlated because the random forest with m equals 4 is very similar to the one with m equals 5。

 And so so that's why these curves are each of the curves is quite smooth。ok。

What we do see is that M try round 4 seems to be about the best， at least for the test error。

 for the out of bag error around about 8。 So somewhere in the middle。

 it's quite a flat plateau there。And。And， and， and with very little， with very few tears， we've。

 we've fit a very powerful prediction model。 This is the random forest here。 and。

 and got pretty good performance。 So as a point， two points to note here。

 On the left hand side is a performance of a single tree。 So this will be a bushy tree。

 But that's a performance of a single bushy tree。 And the mean squared error on the out of bag is 26。

 And we drop down to about just over 14 Yeah。 So it's almost's just a little bit above half。 So we。😊。

It reduce the error by half。 And， and likewise， for the test error in the。

 these errors are somewhat different， but。By by using a random forest。

And on the right hand side here， we use all 13 verbals， so this is actually baggging。

 which was random forests and baggging were due to Leobriman Bagging came out earlier and random forests were a later enhancement。

And so。These are all produced using the random forest function in R。Now， random forests。

 as we learnedt the in the course notes and lectures。

 random forests reduced the variance of the trees by a。

 so it grows big bushy trees and then gets rid of the variance by a boosting on the other hand。

Is really going off to bias。 And so boosting grows smaller stbiia trees and then， and。

 and and goes at the bias。So we use the package GBM gradient boosted machines in R。

 So we load up that package and we're going to use the same data set here and so。

There we give a call to GBM。Pretty much the same as the call to random forest。

 GBBM asked for the distribution， which is Gaussian， because we're doing square alo。

 We are Were going to ask GB BM for 10000 trees， which sounds like a lot。

But these are going to be shallow trees。And that's given by interaction depth。

 So interaction depth is the number of splits。 So we're going to say we only want four splits in each of the trees。

So it' will do best first split in and it'll stop it after four splits and then shrinkage is 0。

01 so that's how much we're going to shrink the tree step back。So I just chose these parameters。

 One would normally fiddle around with these parameters to decide which to use。And so its Jeep， well。

 look at that 10，000 trees fit in in a few seconds。So we can do a summary。

And what summary does is it， it actually gives a variable importance plot。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_10.png)

And。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_12.png)

And it's。ThereThere's two variables that seem to be the most important。 There's the number of rooms。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_14.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_15.png)

And。This， this， oh， the second variable is。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_17.png)

Ett， which is the percentage of lower status economic status people in the in the community。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_19.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_20.png)

And so those are the two most important variables they aren't all labeled in this plot here because because of the font size we using。

 we reduce the size font size we would have seen them all labeled。

 So the variable importance plot is a good way of seeing。

 it seems like these two variables are by far the most important。

 Then the other variables play a lesser role。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_22.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_23.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_24.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_25.png)

嗯。We can do partial dependence plots。 So let's plot these top two variables。 and so。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_27.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_28.png)

This shows us， it's a kind of a roughly relationship。 And it shows us that。The。

 the higher the proportion of lower status people in the co in the suburb， the lower the value of。

 of the house housing prices。Not， not a big surprise there， and。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_30.png)

Reversed relationship with the number of rooms。 The average number of rooms in the house increases。

 The price increases。 So no big surprise is there。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_32.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_33.png)

Okay， so what we， we get I'll end off the session by。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_35.png)

By by predicting our boosted model on the test dataset normally one would use cross validation in boosting to select the number of trees。

 we won't do that， yeah， we'll leave that up to you to do you'd have to run the cross validation yourself and in fact these other tuning parameters like the shrinkage parameter is a tuning parameter one would probably use cross validation to select that as well and so there's a little bit more work and fiddly stuff to be done with boosting over random forest but often it's worth it。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_37.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_38.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_39.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_40.png)

So。What we'll do yeah， is we'll just。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_42.png)

Look at the， the test performance as a function of the number of trees。

 And so we make a a grid of number of trees in steps of 100 from 100 to 10000 by。Okay， so we use。

Seek to do that。And then we run the predict function on on the boosted model。

 and it takes end or trees as an argument。 and so。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_44.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_45.png)

It was pretty quick and it's produced a matrix of predictions on the test data。

 there are 206 test observations。And you see， we've got 100 different predict vectors at those100 different values of。

 of tree。And so then we compute the test error for each of those and we use the apply function。

 so we use our width command again， and we use the apply function。And now premats a matrix。

 but met v is a vector。 And so this just recycles this vector。

 So that's a little bit of trickery that I often use in R。 It's handy。 So so that recycles it。

 So this is actually a matrix of differences。 And then we apply to the columns of these squared differences。

 the mean。 And so that'll compute the column wise mean squared error。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_47.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_48.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_49.png)

for these guys。 and， and I did that。 And then we'll。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_51.png)

嗯。We'll make a plot and we see the boosting error plot and it pretty much drops down and drops down lower it looks like than the random forest。

 This is a function of the number of trees and then seems to level off。

 and it doesn't appear to be increasing。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_53.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_54.png)

IfIf you really ramped up the number of trees to a much bigger number。

 it would slowly start to increase， but this is evidence of the claim that Boostin is reluctant to overfi and it certainly seems to be the case here。



![](img/91834ccc0f0261ca1a76a05ef0293a2f_56.png)

![](img/91834ccc0f0261ca1a76a05ef0293a2f_57.png)

嗯。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_59.png)

If we go back and re plotot our。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_61.png)

Random forest。

![](img/91834ccc0f0261ca1a76a05ef0293a2f_63.png)

Performance。So。Here we go。And， and now we can go back and， and include。嗯。

Boosted results in that plot。Wexii。It's doing about。No no， that's not what I wanted。Okay。

 I I did the wrong plot。 So there's our what I'm actually what I'm intended to do was there's our boosted plot and I'm going to include the best test error from the random forest over there。

 So there we go。 and we see that boosting actually got a reasonable amount below the test error for for the random forest。

Okay， so there we have it， random forests and boosting two powerful methods。

Our experiences at boost in， especially if you're willing to go through the tweak in and and the tu in。

 will usually outperform random forests， but random forests are really dead easy。

 They won't overfi the only tuning parameter is the Mtri。

 but the number of when I say they won't overfit by by increasing the number of trees in random forests it won't overfi it'll it'll just。

Once it stabilizes， it's stabilized and adding more trees doesn't make much difference。

 with boosting not the case。 you've got genuine tuning parameters， a number of trees。The。

 the shrinkage parameter and and the depth， but both very powerful methods。

