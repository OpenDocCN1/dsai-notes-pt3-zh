# 华盛顿大学《机器学习（分类，聚类和检索，第3-4课⧸共4课）｜Machine Learning》中英字幕 p139 17_使用KD树进行近似k近邻搜索.zh_en -BV1Sr421F7N7_p139-

。

![](img/5c07f751caa9acf9778f2344ab3a1227_1.png)

So the last way in which we're going to use Kd trees for nearest neighbor search is for approximate nearest neighbor search。

 And this is something that we're going to spend a lot of time talking about in the next section。

 but this idea， it' really important because so far everything we've been talking about assumes that out of all the articles out there。

 you want to find the nearest neighbor。But that assumption relies so heavily on first。

 assuming that it's important to find the nearest neighbor and not just a good alternative。

But also the fact that you really believe in your representation of your data。

 as well as the distance measure that you're using to compute these similarities because if you don't really have 100% faith in those to begin with。

 then what's the difference of finding the nearest neighbor versus one that's pretty， pretty。

 pretty close to that。So a question is， can we do things even more efficiently if we don't care about finding。

 according to our set， the nearest neighbor， which is a pretty good approximation。

 So within the context of K D trees， the way we can do approximate nearest neighbor search is as follows。

 Remember before we maintained the distance to the nearest neighbor found so far。

So this I'm going to call R equals distance。To nearest neighbor so far。

But now what we're going to do is we're going， instead of pruning。

Based on the distance the nearest neighbors so far， we're going to prune more aggressively。

 That's what's going to give us the added efficiency。 But at the cost of an approximation。

 And to prune more aggressively， instead of pruning based on distance R。

 we're going to prune based on a distance R over alpha where Al is。Some number greater than one。

And so this is。Going to be a smallest， smaller radius that we're using。

 So it means it's more likely that the distance to the bounding box exceeds R over alpha than it does just R。

Okay， so what are the properties of performing nearest neighbor search with this more aggressive pruning。

 Well， we know that。If we return a neighbor at some distance R。

 then there's no neighbor within R over alpha。 So what we're saying here is。

Let's say this is our query point， Xq。This is our distance， our。

This is the nearest neighbor that we're going to return。If we look at。

Let me draw in a different color， I think it'll help make this clear。So if this is r over alpha。

Then we know that there could be points here。 So these would all be。

Data points that were actually closer than the nearest neighbor that we returned。嗯。But， we know。

That there's no。Points within this box。 Otherwise， we would have found them。

 and that would have been our distance to the nearest neighbor。

And we're pruning all other things that fall further from that。Okay， so by doing this。

 we get a fairly good approximation。 And actually， this bound that we're stating here is rather loose。

 And in practice， we're often much closer to the optimal solution。 And importantly。

 it just saves a ton of searching， you have to do。 Of course， if alpha is reasonably large。 if alpha。

Becomes one， then it defaults back to our exact nearest neighbor search。Okay。So in a lot of cases。

 doing approximate nearest neighbor search is。Pretty much just as good as what you would do with brute force because there's so much noise in how you're thinking about computing distances to begin with and whether that's really relevant to let's say I'm sitting here reading an article。

 whatever you're going to present me as a pretty good approximation to the nearest neighbor is probably going to satisfy my needs for exploring other literature。

Okay， so we're going to talk a lot more about alternative ways to do approximate nearest neighbor search。

 but in ways that also scale better with higher dimensions， but within the context of Kd trees。

 this is a very effective way of performing approximate nearest neighbor search。

So to wrap up on kd trees first I want to say that they really are very cool and efficient data structure。

 but I also want to discuss a few other things， one is the fact that there are lots and lots of variants we talked about some of these in terms of heuristics for how to choose the splitting dimension and the splitting value and all sorts of other things and in addition。

 instead of just making these access aligned cuts， there are other ways of performing a kd tree while it's really these ball trees and different shapes you can plop down and what we're going to talk about next is you can think of as one of these alternatives to these access aligned cuts。

And the other thing that we've seen so far is the fact that in performing nearest neighborighs search。

 things rely very， very heavily on how you're representing your data and how you're computing the distance between two different data points。

And for both of these， kd trees and nearest neighbors search， things become much。

 much more challenging when you're in high dimensional spaces。So for kd trees。

 we talked about the fact that the number of inspections you have to do can be exponential in the dimensionality。

 so just as a rule of thumb typically kd trees are only useful if the number of observations you have is much much larger than2 to the D2 to the number of dimensions you have so in high dimensional cases often you don't have enough observations to really make a kD tree worthwhile。

And in terms of thinking about nearest neighbor search for getting the challenges just of kd trees in high dimensional spaces。

 things are really hard because from a really high dimensional feature vector。

 a lot of those features are going to be basically just noise and those can be swamping your distance calculations and so what happens is in that high dimensional spaces。

Basically， everything is far away from itself or each other。

 And so you really need techniques to learn which features are important or how do you think about waiting across the different features。

 and like we mentioned before， that's a really， really challenging task that requires a lot of domain knowledge or a lot of thought and exploration。

And lastly， I really want to thank Andrew Moore for the outline of these slides。

 the slides on KD treeses were built very heavily from a really nice presentation that he put together on KD trees。

 so thanks for the permission to use that。

![](img/5c07f751caa9acf9778f2344ab3a1227_3.png)

🎼。