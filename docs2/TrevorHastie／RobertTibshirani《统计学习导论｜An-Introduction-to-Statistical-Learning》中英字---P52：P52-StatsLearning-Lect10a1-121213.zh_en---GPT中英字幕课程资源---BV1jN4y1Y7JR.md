# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P52：P52 StatsLearning Lect10a1 121213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_0.png)

Welcome back so today we're going to talk about chapter8 of the book。

 treee based Meod for Aggression classification。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_2.png)

As you'll see their methods for supervised learning with stratify or segment the predict your space in order to make predictions。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_4.png)

And they form what are called decision trees in。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_6.png)

Straatification。And we'll talk about those methods。

 which are actually from the start in the mid-'80s， I'd say。

 and some of the names that associated with that。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_8.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_9.png)

Well， first of all， the software package which started in the method is called CART。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_11.png)

For classification and regression trees。And the first two authors of Kt are Leo Bman， who was a。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_13.png)

well known statistician from Berkeley and Jerry Friedman， who's our colleague here at Stanford。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_15.png)

嗯。And Friedman actually was one of our teachers in the 80s back in 80s and Trev and I were graduate students here and that's when the court book came out right and actually we hope to talk to Jerry in this course I mean you'll get a chance to hear him talk about the development of trees and how that happened in the 80s so thats the first part of the sections on trees and then we'll talk about bagging and boosting and random forests which are which combine trees in a more modern way it's interesting because trees were used widely for a number of years as one of the primary learning tools and now trees are used widely as building blocks in some of the more modern learning tools so they've been around for a long time and they're going to stay around。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_17.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_18.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_19.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_20.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_21.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_22.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_23.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_24.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_25.png)

Right， so in a little more detail， the good side of trees， as you'll see， they're simple in a sense。

 especially if they're small， and hence they can be useful for interpretation。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_27.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_28.png)

But on the other hand， when you look at them as supervised。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_30.png)

Learning techniques for prediction， they're definitely not competitive with the best methods it around。

 but they can be made competitive when they're combined in ensembles of trees。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_32.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_33.png)

And we'll talk about that in the second part of the lecture， in particular。

 bagging random forest and boosting， and they were methods which were developed in the '90s and beyond。

 which improved the prediction performance of trees substantially。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_35.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_36.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_37.png)

Okay。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_39.png)

So let's start the beginning， the basic idea of a decision tree。

 and this applies to both regression and classification。

 we'll start with regression and a little later we'll consider classification。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_41.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_42.png)

Okay， so before we actually see a tree， let's think about how we would stratify some data。

 so here's the baseball data。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_44.png)

The response is salary and which we've color coded。

In this graph from low salary being blue and green。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_46.png)

To higher salary being yellow and red。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_48.png)

For baseball players and each player has， we've measured two predictors a number of years he's been in the league in the baseball League and。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_50.png)

The number of hits he hits per season， okay， so we want to predict salary from those two predictors。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_52.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_53.png)

So if I asked you to stratify this population and I was tried to separate the high from low salary players。

 what would you do？Well if you look at it， it looks like。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_55.png)

The higher salaries are up here and the lower ones are maybe in this L shape， so one might think。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_57.png)

Here's a place you might say， well， let's split around here。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_59.png)

This split separates the predictor space into two regions， right？



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_61.png)

The higher salaries we see some yellow and red up here。

 although's mixed with some blue and green and the lower ones on the left。

 so that does a pretty good job of putting the low salary players on the left。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_63.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_64.png)

Does do a great job on the right， so it might do a further split Rob so it looks like you've cut it five years So it years is a number of years in the league right now you're in the league yeah。

 so which makes sense because the players are doing the league longer can expect it to have a higher salary。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_66.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_67.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_68.png)

Firstas ones in the league lower have a lower salary。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_70.png)

But those with warrior years in the league seem to be a bit mixed right， they're bit mixed。

 so it looks like when our job isn't quite done， maybe we could do a refinement by stratifying in this way。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_72.png)

Right。And now we have three regions we've got。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_74.png)

We've got the high savvy players up here。And what are these players。

 these are the ones who have been in the league more than maybe own five years and who have more than maybe 125 hits。

 they're the ones who have the highest salary， and then the medium category looks like it's down here right they've got also more than roughly five years of experience。

 but fewer number of hits and then the lower is on the left。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_76.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_77.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_78.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_79.png)

So with just two simple cuts， you've made a pretty good segmentation there exactly。

 and this is the idea of a decision tree， which actually we'll see on the next slide。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_81.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_82.png)

When we applied a decision tree technique to that data。

 we got exactly this tree and this tree is very much like what I drew in the previous slide。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_84.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_85.png)

And just。So on the next slide I've got the caption for this figure and throughout the notes we have a detailed caption for a lot of the figures。

 I'm not going to read out the caption in the course。

 but it's just there for your reference if you want to。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_87.png)

If you want us to read the details。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_89.png)

Let's look at this tree and interpret what it's saying， I mean what the layout is first of all。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_91.png)

This， this is is a series of splits。 at the top we have。 We have all the data the top。

 And this year's less than 4。5 is a split。 It's a partition into。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_93.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_94.png)

On the left， the players who are in the league for less than 4。5 years are on the right。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_96.png)

Players in the league for more than 4。5 years。 So this is pretty much the split we saw。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_98.png)

That I made here， right？This split here is， I said it five， but that's roughly 4。5 is between 4 and5。

 so this split at the top of the tree is a partition into the left and right regions。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_100.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_101.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_102.png)

So。This tree says we're going to first of all going to split players on the years of experience。

 those with fewer than 4。5 years are assigned to the left node。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_104.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_105.png)

And those with more than 4。5 are assigned to the right。

 hit number at the bottom so the number of the bottom is is I think the average log response。

 I think we took logs here， so it's the average log salary of the players who fell into that bin。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_107.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_108.png)

On the right。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_110.png)

We do a further split on hits。Among the players who have more than 4。5 years experience。

 those who also have fewer than1 to 17。5 hits。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_112.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_113.png)

Are assigned to this branch otherwise to this branch。So we ended up with three bins。

From highest salary， medium salary and lowest salary。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_115.png)

And these are exactly the。哦。Almost exactly the three regions that I drew here just by hand。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_117.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_118.png)

Okay。So here actually is the in detail is the partition that corresponds to that tree。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_120.png)

And it's again very much like the one I do by hand。 the splits being given。 there's the top split。

 And here's the split on the left。 So this was found by an algorithm。 rights by an algorithm。

 And actually， the algorithm we're going to describe is going to build。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_122.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_123.png)

A much larger tree， and then it's going to prune it from the bottom to give this three no tree。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_125.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_126.png)

But so the automatic algorithm is going to do what we and has to be quite sensible in this example to divide into three regions。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_128.png)

Okay， some terminology which I've already been using。

The nodes at the bottom are called terminal nodes because they' terminal， they're not further split。

 you notice what I'm calling these trees， but they're upside down， right， the leaves。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_130.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_131.png)

Or at the bottom or at the top， it's just for convenience。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_133.png)

The nontermo nodes are called internal nodes， which in this case are we have two internal nodes in internal nodes in our tree。

 but usually internal nodes， the terminal nodes are the ones of interest because they're the ones that describe the partition of the predictor space。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_135.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_136.png)

So how do we interpret that tree？Well we split first on the years of experience。

 so that's saying the most important factor is determining salary is years of experience。

 those with less experience could have lower salary。嗯。On that left branch。

 we didn't split any further。 So it looks like the the。

The number of hits isn't important in determining salary for the players less experience。

 but on the right where we have the players with more experience。The hits is important。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_138.png)

Notice what we're saying here is that this is not a symmetric tree， right we split。

W to give us the left pocket。But then on the right， we。

We split again this bucket into two more buckets on hit。

 so the point being that number of hits seems to be important for those with more than 4。

5 years experience， but not important for those with fewer than 4。5。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_140.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_141.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_142.png)

嗯。Now again this gets to the point that I said earlier。

 it's a very simple tree which makes it it's very easy to display and interpret right there's no equation one thing that scares nonsatitistician collaborators that we have scares them sometimes if they don't know much math and you write an equation down for a model you know's not very it's intimidating not very attractive to them one nice thing about a tree is that the。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_144.png)

The tree is the model， this is the summary of the model。

 and we don't need an equation to summarize it。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_146.png)

So it's something that's simple to understand by people who aren't comfortable with mathematics。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_148.png)

On the other hand， it's probably much simpler than it。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_150.png)

It deserves to be， right， and for that reason。Well。

 for one of those reasons the predictionary of trees is not very good compared to other methods。

 and we'll see we can improve it substantially with combined ensembles of trees。

So I haven't said in detail how we actually got that tree。

 I said that the tree that we saw there actually。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_152.png)

It was very close to the one that we got just by intuitively splitting the。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_154.png)

The feature space， but how does the automatic tree growing algorithm work？



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_156.png)

Well， the idea is we want to divide the predictiveor space into non overlapping regions。

 some J regions， some number J。

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_158.png)

Which we'll have to pick as well， in the case of the previous in the example， J was three。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_160.png)

And having grown the tree， the prediction as we've see in just the average of the response values of falling each of the terminal node。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_162.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_163.png)

But how do we actually decide on the splits on the shape the partition of the feature space， well。

 if we thought in a most general way， we could think about trying to divide the feature space into boxes。

 meaning that the edges of the regions are parallel to the axes。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_165.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_166.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_167.png)

We want to do that for interpretation if we had a region which was a circle。

 it'd be really hard to interpret and predict space。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_169.png)

对。Even considering ourselves into boxes， it turns out the。The tree building process is difficult。

 so let's pose exactly the problem we might want to solve。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_171.png)

We define our boxes as r1 through our J for some number of boxes J。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_173.png)

Then we might want to find the boxes so that if we sum up the variation of the observations around the mean of each box。

 so the RJ is the set of observations falling in the Jth box。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_175.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_176.png)

And why hat Rj is is the average of such the response of those observations so those are the averages at the terminal nodes in the tree exactly so each box represents one of those terminal leaves where you're going to represent the observations by an average right and we have in this case J such terminal leaves and we're going to choose this set of box that so the total variation of observations around their mean in a box is as small as possible。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_178.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_179.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_180.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_181.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_182.png)

That makes sense， right， because we want the box to be homogeneous。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_184.png)

And to have observations which are very similar in each box， and across boxes will be very different。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_186.png)

So this looks like a reasonable way to pose the box finding problem。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_188.png)

It turns out actually， that's too hard to solve computationally。 If you say I want to say， find the。

The 10 boxes that that。have the smallest value of this criterion。

 it's actually computationally infeasible about 10 might be solvable， but certainly beyond， you know。

10 or 20 or 50， it gets very hard， especially if you think about how many ways you can make boxes。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_190.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_191.png)

Its you know the number just boggles， it just gets big very fast。

 so exactly so trees use an approximation， sort of an obvious method， top down greedy approach。

And it's top down because it starts to the top with a whole set of observations。

It splits them in the two pieces one at a time at each level。It's greedy because it doesn't find。

The best split among all possible splits， but only the best split at the immediate place is looking。

So let's go through the details of the tree growing process I've got on this slide。

 but might be easier to go back to the little tree we have there and just talk through it there。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_193.png)

So what we do is we start at the top with a full set of data and all the predictors。

 and we look for the predictor and the split that produces the smallest criterion。

 the one we had written down， which is the summ of squares。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_195.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_196.png)

response around of each response around is the average in the node。

 so we're going to make a split to produce two nodes。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_198.png)

We look at all possible predictors and all split points that produce the smallest criterion value and so that's before we had three nodes here so there'd just be a mean in the lift and a mean in the right exactly right so we're starting with the full data with actually with the only one node we're going to split into two and the winner was this the predictor years at 4。

5 producing these two branches the left and the right and then the process is repeated we look we find the。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_200.png)

![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_201.png)

The best split we can among the left and right nodes in the winner was hits。At 117。5。So again。

 in each case we're doing the best we can in a greedy sense and that produced these three terminal nodes。



![](img/7098aa5283d1c84e0d60c8f33f1ea5a9_203.png)

So let's go back to the。So I've said that in more detail in this slide。And then the question is。

One question is。When do we stop， we could decide to stop to just。Do a small number of nodes。

 I create maybe three nodes like in that treat。Or we could grow a larger tree。

