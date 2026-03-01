# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p58 10_可能出错的地方：混淆.zh_en -BV1L9Fde5EXS_p58-

![](img/e129b09e4242cf3e17c5606db100f3a3_0.png)

Hi， my name is Brian Caho， and this is the lecture on confounding as part of our executive data science series。

😊，I'd like to thank Jeff Lee， who wrote these slides and I'm giving the lecture。



![](img/e129b09e4242cf3e17c5606db100f3a3_2.png)

So sometimes you see unexpected patterns in data。And as an example， we have here。

 the number of people who drowned by falling into a pool by the film's Nicholas Cs appeared in over time。

 and there's a strong correlation just by happenstance。

 So what are some of the reasons that we see these see spurious correlations in data。

 probably this example isn't the best because this isn't really an example of confounding and will go over why in a few slides。



![](img/e129b09e4242cf3e17c5606db100f3a3_4.png)

But one potential reason we see associations that maybe don't make sense or are not real is because of the idea of confounding and confounding is one of the central topics and statistics。

 and I would say it's one of the core reasons that observational data analysis is hard。

Let's go through a simple example that Jeff concocted just to illustrate the principle of confounding here we see a picture of Jeff playing with his son Dexter。

And he points out that he has big shoes and he's literate， he claims he's somewhat literate。

 but I've seen him read， he's literate， and Dexter has little tiny shoes and is not literate because he's a little kid。

So imagine conducting a data analysis with some variables and you see an association like that。

 well in this example you might say， okay， well， is shoe size associated with literacy？

But there's another variable， which is age。 In this case， Dexter is young and。Jeff is older。

 middle age， he claims。 And so that is ultimately the。terIntermediary between the relationship。

 So we might put it in a graph like this where we have shoe size， literacy and age。

 and we have the arrows in the sense that age corresponds to shoe size。

 Young people have smaller feet。 olderer people have bigger feet。

And age corresponds to literacy as we age and develop， we develop our reading skills。

And so this is the idea of confounding that the confounder exists between what you are using to predict and what you are predicting。

And it the name confounder comes because it can confound， in other words。

 it confounds the relationship that you're trying to look at。

So here's another funny example he came up with that came from the X KcD comic book。

 where sales correlate with geography， but so do lots of other things。

 And this is basically what this。Comic is illustrating is that whenever you look at any of these heat maps。

 right what you see are very consistent hotspots and those hotspots tend to just be where most people live and the comic says pet peeve number 208 geographic profile maps which are basically just population maps。

 in other words， whatever you're trying to study and geography is being confounded by the number of people that live in that area。

So confounding， just to reiterate and to summarize this lecture。

 confounding is the idea that a relationship between a variable you're interested in and an outcome。

Is spurious and really due to a third variable that really is associated with the other two。Okay。

 and so it's very often the case that we find relationships in our data set and have to be able to navigate through things like confounding to figure out whether these associations are real or whether they're fake。

And just to give you a sense to foreshadow some later lectures， how do we deal with confounding。

 how do we address it， Well， the big way that we address it is through things like adjustment。

In the first case， from the shoe size example， if we had a bunch of people and we had their shoe sizes and we had a bunch of people and we had their reading levels。

 okay， if we fit a model that had shoe size would get a positive association。

 But if we adjusted for age， right， if we adjusted for age， then that association would go away。

Same thing here where if we looked at geography as it was associated with whatever they were looking at subscribers to Martha Stewart living in this case。

 and we accounted for population density at that geographic location。

 then the relationship would go away。 Okay， so adjustment things like adjustment using models is going to be one of the ways that we look to to address confounding。



![](img/e129b09e4242cf3e17c5606db100f3a3_6.png)

![](img/e129b09e4242cf3e17c5606db100f3a3_7.png)

![](img/e129b09e4242cf3e17c5606db100f3a3_8.png)