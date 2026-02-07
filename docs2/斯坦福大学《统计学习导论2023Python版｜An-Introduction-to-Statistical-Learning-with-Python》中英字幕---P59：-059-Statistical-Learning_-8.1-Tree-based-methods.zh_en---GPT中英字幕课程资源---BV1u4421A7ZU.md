# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P59：-059-Statistical Learning_ 8.1 Tree based methods.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/74e71836d48d810868b5bb506b4250f2_0.png)

Welcome back， so today we're going to talk about chapter 8 of the book。

 treee based Meod for Aggression classification。As we'll see。

 their methods for supervised learning would stratify or segment the predictor space in order to make predictions。



![](img/74e71836d48d810868b5bb506b4250f2_2.png)

And they form what are called decision trees in their in their。



![](img/74e71836d48d810868b5bb506b4250f2_4.png)

Sttraatification。And we'll talk about those methods。

 which are actually from the they started in the mid-'80s， I'd say。

 and some of the names that associated with that。

![](img/74e71836d48d810868b5bb506b4250f2_6.png)

![](img/74e71836d48d810868b5bb506b4250f2_7.png)

Well， first of all， the software package which started in the method is called CART。



![](img/74e71836d48d810868b5bb506b4250f2_9.png)

For classification and regression trees。And the， these the first two authors of Kt are Leo Bman。

 who was a。well known statistician from Berkeley and Jerry Friedman。

 who' is our colleague here at Stanford。嗯。And Friedman actually was one of our teachers。

 Trevor the 80s 80s and Trev and I were graduate students here and that's when the court book came out right and actually we're we hope to talk to Jerry in this course I mean you'll get a chance to hear them talk about the development of trees and how that happen in the 80s。

 So that's the first part of the sections on trees and then we'll talk about bag and boosting in random forests which are which combine trees in a more modern way。

 it's interesting because trees were used widely for a number of years as one of the primary learning tools now trees are used widely as building blocks in some of the more modern learning tools So they've been around for a log time and they're going to stay around。



![](img/74e71836d48d810868b5bb506b4250f2_11.png)

Right， so in a little more detail， the good side of trees， as you'll see， they're simple in a sense。

 especially if they're small and hence they can be useful for interpretation， but on the other hand。

 when you look at them as supervised，Learning techniques for prediction。

 they're typically not competitive with the best methods it around。

 but they can be made competitive when they're combined in ensembles of trees。

And we'll talk about that in the second part of the lecture， in particular。

 bagging random forest and boosting， and they were methods which had developed in the 90s and beyond。

 which improved the prediction performance of trees substantially。



![](img/74e71836d48d810868b5bb506b4250f2_13.png)

ok。

![](img/74e71836d48d810868b5bb506b4250f2_15.png)

So let's start the beginning， the basic idea of a decision tree。

 and this applies to both regression and classification。

 we'll start with regression and a little later we'll consider classification。



![](img/74e71836d48d810868b5bb506b4250f2_17.png)

![](img/74e71836d48d810868b5bb506b4250f2_18.png)

Okay， so before we actually see a tree， let's think about how we would stratify some data。

 so here's the baseball data。

![](img/74e71836d48d810868b5bb506b4250f2_20.png)

The response is salary， and which we've color coded。



![](img/74e71836d48d810868b5bb506b4250f2_22.png)

In this graph， from low salary being blue and green。



![](img/74e71836d48d810868b5bb506b4250f2_24.png)

To higher salary being yellow and red。

![](img/74e71836d48d810868b5bb506b4250f2_26.png)

For baseball players and each player has， we've measured two predictors a number of years。

 He's been in the league in the baseball League and。



![](img/74e71836d48d810868b5bb506b4250f2_28.png)

The number of hits he hits per season， okay， so we want to predict salary from those two predictors。



![](img/74e71836d48d810868b5bb506b4250f2_30.png)

![](img/74e71836d48d810868b5bb506b4250f2_31.png)

So if I asked you to stratify this population and was try to separate the high from low salary players。

 what would you do？

![](img/74e71836d48d810868b5bb506b4250f2_33.png)

Well， if you look at it， it looks like。The higher salaries are up here， right。

 and the lower ones are maybe in this L shape。 So one might think。Here's a place you might say， well。

 let's split around here。This split separates the predictor space into two regions， right？



![](img/74e71836d48d810868b5bb506b4250f2_35.png)

The higher salaries， we see some yellow and red up here。

 although mixed with some blue and green and the lower ones on the left。

 So that does a pretty good job of putting the low salary players on the left。



![](img/74e71836d48d810868b5bb506b4250f2_37.png)

Doesnt do a great job on the right。 So it might do a further split。

 Rob So it looks like you've cut it five years So years is a number of years in the league right now in the league。

 Yeah， so which makes sense because the players are doing that league longer or can expect it to have a higher salary。



![](img/74e71836d48d810868b5bb506b4250f2_39.png)

![](img/74e71836d48d810868b5bb506b4250f2_40.png)

![](img/74e71836d48d810868b5bb506b4250f2_41.png)

Whereas ones in the league lower have lower salary。

But those with warrior years in the league seem to be a bit mixed。 right， They're bit mixed。

 So it looks like when our job isn't quite done。 maybe we could do a refinement by stratifying in this way。



![](img/74e71836d48d810868b5bb506b4250f2_43.png)

Right。And now we have three regions。 we've got。We've got the high salary players up here。

And what are these players， These are ones who have been in the league more than maybe your own five years and who have more than maybe 125 hits。

 They're the ones who have the highest salary。 And then the medium category looks like it's down here。

 right， They've got also more than roughly five years of experience， but fewer number of hits。

 and then the lower is on the left。

![](img/74e71836d48d810868b5bb506b4250f2_45.png)

![](img/74e71836d48d810868b5bb506b4250f2_46.png)

So with just two simple cuts， you've made a pretty good segmentation there。

 exactly and this is the idea of a decision tree， which actually we'll see on the next slide。



![](img/74e71836d48d810868b5bb506b4250f2_48.png)

![](img/74e71836d48d810868b5bb506b4250f2_49.png)

When we applied a decision tree technique to that data。

 we got exactly this tree and this tree is very much like what I do in the previous slide。



![](img/74e71836d48d810868b5bb506b4250f2_51.png)

And just。So on the next slide I've got the caption for this figure and throughout the notes we have a detailed caption for a lot of the figures。

 I'm not going to read out the caption in the course。

 but it's just there for your reference if you want to。If you want us to read the details。

Let's look at this tree and interpret what it's saying。 I mean， what the layouto is， first of all。

This， this is is a series of splits。 at the top。 we have。 We have all the data the top。

 And this year's less than 4。5 is a split。 It's a partition into。On the left。

 the players who are in the league for less than 4。5 years are on the right。

Players in the league for more than 4。5 years。 So this is pretty much the split we saw。



![](img/74e71836d48d810868b5bb506b4250f2_53.png)

That I made here， right？This split here is， I said it 5， but that's roughly 4。5 is between 4 and 5。

 So this split at the top of the tree is a partition into the left and right regions。



![](img/74e71836d48d810868b5bb506b4250f2_55.png)

![](img/74e71836d48d810868b5bb506b4250f2_56.png)

![](img/74e71836d48d810868b5bb506b4250f2_57.png)

So。This tree says we're going to first of all going to split players on the years of experience。

 those with fewer than 4。5 years are assigned to the left node。



![](img/74e71836d48d810868b5bb506b4250f2_59.png)

![](img/74e71836d48d810868b5bb506b4250f2_60.png)

And those with more than 4。5 are assigned to the right。

 hit number at the bottom so the number of the bottom is the is the I think the average log response。

 I think we took logs here。 So it's the average log salary of the players who fell into that bin。



![](img/74e71836d48d810868b5bb506b4250f2_62.png)

On the right。

![](img/74e71836d48d810868b5bb506b4250f2_64.png)

We do a further split on hits。Among the players who have more than 4。5 years experience。

 those who also have fewer than1 17。5 hits。

![](img/74e71836d48d810868b5bb506b4250f2_66.png)

Are assigned to this branch otherwise to this branch。So we had up with three bins。

From highest salary， medium salary and lowest salary。



![](img/74e71836d48d810868b5bb506b4250f2_68.png)

And these are exactly the。哦。Almost exactly the three regions that I drew here just by hand。



![](img/74e71836d48d810868b5bb506b4250f2_70.png)

![](img/74e71836d48d810868b5bb506b4250f2_71.png)

O。So here actually is the detail is the partition that corresponds to that tree。

And it's again very much like one I drew by hand， the splits being given。 there's the top split。

 And here's this split on the left。 So this was found by an algorithm。 It's found by an algorithm。

 And actually， the algorithm we're going to describe is going to build。



![](img/74e71836d48d810868b5bb506b4250f2_73.png)

A much larger tree。 and then it's going to prune it from the bottom to give this three no tree。



![](img/74e71836d48d810868b5bb506b4250f2_75.png)

![](img/74e71836d48d810868b5bb506b4250f2_76.png)

But so the automatic algorithm is going to do what we has to be quite sensible in this example to divide into three regions。



![](img/74e71836d48d810868b5bb506b4250f2_78.png)

Okay，Some terminology， of which I've already been using the nodes at the bottom are called terminal nodes because they're terminal。

 they're not further split。 You notice I'm calling these trees， but they're upside down。

 right the leaves。Or at the bottom or at the top， it's just for convenience。

The nontermo nodes are called internal nodes， which in this case are we have two inter nodes internal nodes in our tree。

 but usually internal nodes， the terminal nodes are the ones of interest because they're the ones that describe the partition of the predictor space。



![](img/74e71836d48d810868b5bb506b4250f2_80.png)

![](img/74e71836d48d810868b5bb506b4250f2_81.png)

![](img/74e71836d48d810868b5bb506b4250f2_82.png)

So how do we interpret that tree？Well， we split first on the years of experience。

 so that's saying the most important factor is determining salary is years of experience。

 those with less experience could have lower salary。嗯。On on that left branch。

 we didn't split any further。 So it looks like the the。

The number of hits isn't important in determining salary for the players less experience。

 but on the right， where we have the players with more experience。The hits is important。

Notice what we're saying here is that this is not a symmetric tree， right， we split。

W to give us the left pocket。But then on the right， we。



![](img/74e71836d48d810868b5bb506b4250f2_84.png)

We split again this bucket into two more buckets on hit。

 so the point being that number of hits seems to be important for those with more than 4。

5 years experience， but not important for those with fewer than 4。5。



![](img/74e71836d48d810868b5bb506b4250f2_86.png)

![](img/74e71836d48d810868b5bb506b4250f2_87.png)

![](img/74e71836d48d810868b5bb506b4250f2_88.png)

嗯。Now， again， this gets to the point that I said earlier。 it's a very simple tree。

 which makes it it's very easy to display and interpret。 right， There's no equation。

 One thing that scares nonsatitistician collaborators that we have scares them sometimes if they don't know much math and you write an equation down for a model。

 you know， it's not very， it's intimidating， not very attractive to them。

 One I think about a tree is that the。The tree is the model， right This is the summary of the model。

 and we don't need an equation to summarize it。So it's something thats simple to understand。

 by people who aren't comfortable with mathematics。



![](img/74e71836d48d810868b5bb506b4250f2_90.png)

On the other hand， it's probably much simpler than it。



![](img/74e71836d48d810868b5bb506b4250f2_92.png)

It deserves to be， right， And for that reason。Well。

 for one of those reasons the predictionary of trees is not very good compared to other methods。

 and we'll see we can improve it substantially if we combine ensembles of trees。

So I haven't said in detail how we actually got that tree。

 I said that the tree that we saw there actually was very close to the one that we got just by intuitively splitting the feature space。

 but how does the automatic tree growing algorithm work？



![](img/74e71836d48d810868b5bb506b4250f2_94.png)

![](img/74e71836d48d810868b5bb506b4250f2_95.png)

![](img/74e71836d48d810868b5bb506b4250f2_96.png)

Well， the idea is we want to divide the predictor space into non overlapping regions， some J regions。

 some number J。Which we'll have to pick as well。 in the case of the previous， in the example。

 J was three。And having grown the tree， the prediction， as we've see。

 in just the average of the response value is of fall in each of the terminal nodes。



![](img/74e71836d48d810868b5bb506b4250f2_98.png)

But how do we actually decide on the splits on the shape， the partition of the feature space， Well。

 if we thought in the most general way， we could think about trying to divide the feature space into boxes。

 meaning that the edges of the regions are parallel to the axes。



![](img/74e71836d48d810868b5bb506b4250f2_100.png)

We't want to do that for interpretation if we had a region which was a circle。

 it'd be really hard to interpret and predict space。喂。Even considering ourselves into boxes。

 turns out the。The tree building process is difficult。

 so let's pose exactly the problem we might want to solve。

We define our boxes as R1 through our J for some number of boxes J。

Then we might want to find the boxes so that if we sum up the variation of the observations around the mean of each box。

 so the RJ is the set of observations falling in the Jth box。

And why hat RJ is is the average of such the response of those observations So those are the averages at the terminal nodes in the tree right exactly so each box represents one of those terminal leaves where you're going to represent the observations by an average。

Right and we have， in this case， J such terminal leaves。

 and we're going to choose a set of boxes that so the total variation of observations around their mean in a box is as small as possible。



![](img/74e71836d48d810868b5bb506b4250f2_102.png)

![](img/74e71836d48d810868b5bb506b4250f2_103.png)

That makes sense， right， because we want the boxes to be homogeneous。



![](img/74e71836d48d810868b5bb506b4250f2_105.png)

And to have observations which are very similar in each box， and across boxes will be very different。



![](img/74e71836d48d810868b5bb506b4250f2_107.png)

So this looks like a reasonable way to pose the box finding problem。



![](img/74e71836d48d810868b5bb506b4250f2_109.png)

It turns out， actually， that's too hard to solve computationally。 If you say I want to say， find the。

The 10 boxes that， that。Have the smallest value of this criterion。

 It's actually computationally infeasible。 About 10 might be solvable， but certainly beyond。

 you know，1020 or 50， it gets very hard， especially if you think about how many ways you can make boxes。



![](img/74e71836d48d810868b5bb506b4250f2_111.png)

![](img/74e71836d48d810868b5bb506b4250f2_112.png)

It's， you know， the the number just boggles。 It just gets big very fast。

 So exactly so trees use an approximation， sort of an obvious method， top down greedy approach。

And it's top down because it starts to the top with a whole set of observations。

It splits them in the two pieces one at a time at each level。It's greedy because it doesn't find。

The best split among all possible splits， but only the best split at the immediate place is looking。

So let's go through the details of the tree growing process I've got on this slide。

 but might be easier to go back to the little tree we have there and just talk through it there。



![](img/74e71836d48d810868b5bb506b4250f2_114.png)

So。What we do is we start at the top with a full set of data and all the predictors。

 and we look for the predictor and the split that produces the smallest criterion。

 the one we had written down， which is the summ of squares。



![](img/74e71836d48d810868b5bb506b4250f2_116.png)

![](img/74e71836d48d810868b5bb506b4250f2_117.png)

![](img/74e71836d48d810868b5bb506b4250f2_118.png)

Of the response around， of each response around is the average in the node。

 So we're going to make a split to produce two nodes。



![](img/74e71836d48d810868b5bb506b4250f2_120.png)

We look at all possible predictors and all split points that produce the smallest criterion value。

 And we went。 So that's before we had three nodes here。

 So there'd just be a mean in the lift and a mean in the right。 exactlyly， right。

 So we're starting with the full data with actually， with the only one node。

 We're going to split it into2。 And the winner was this was the predictor years at 4。5。

 producing these two branches， the left and the right。 And then the process is repeated。

 We look we find the。

![](img/74e71836d48d810868b5bb506b4250f2_122.png)

![](img/74e71836d48d810868b5bb506b4250f2_123.png)

![](img/74e71836d48d810868b5bb506b4250f2_124.png)

The best split we can among the left and right nodes in the winner was hits。At 117。5。So again。

 in each case we're doing the best we can in a greedy sense。

 and that produced these three terminal nodes。

![](img/74e71836d48d810868b5bb506b4250f2_126.png)

![](img/74e71836d48d810868b5bb506b4250f2_127.png)

So let's go back to the。So I've said that in more detail in this slide。And then the question is。

One question is。When do we stop， we could decide to stop to just。Do a small number of nodes。

 I create maybe three nodes like in that tree。Or we could grow a larger tree。

