# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p68 20_报告写作.zh_en -BV1L9Fde5EXS_p68-

![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_0.png)

Hi， my name is Brian Kaho， and this is the lecture on Report writing as part of the executive data science series。



![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_2.png)

So report writing is。You know， often the case， you get reports that are just really problematic。

 And I think that's more of the norm than this than than getting clear， concise。



![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_4.png)

Reproducible reports that have a obvious and clear narrative in tell。

A clear story more often your reports are a little bit of a mismatash of thoughts and so in this lecture what we're going to talk about are some tools that will help at least certain aspects of the report writing。

 of course there's a lot to whatever specific area you're in to the art in that area of how your reports are going to get generated。

 but some of these tools are ubiquit and ubiquitous enough across scenarios that we can give some general recommendations。



![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_6.png)

So in a perfect world， reports will be clear and reproducible。

 kind of the two most important characteristics， and so we're just going to give three strategies for helping manage report writing。

The first one I can say， which is seems ridiculous。

 but it seems to help a lot and it's encouraged checking the signs。

 the magnitudes and the units of effects that are reported。

The second one is to focus on interpretation and interpretability of the report。

And the third is to use reproducible research tools。

So let me just briefly elaborate on this point on checking the signs， the magnitudes and the units。

So the signs， for example， what do I mean by that， I basically mean to check to make sure the directions of the effects are as anticipated。

And。This can often happen to the case。 The worst example of this is when the report only gives the output of a regression analysis with without actually interpreting the coefficients。

 Well， the most basic form of interpretation of the coefficient is just checking that it's in the direction that everyone would anticipate that it's in。

 So in this case， I said our brain volumes decreasing with increasing Alzheimer's disease symptoms。

 if you saw the opposite effect。 if you saw brain volumes increasing， then you would be worried。

 or at least you would that would merit some explanation。The second idea was magnitudes。

 we want to compare the magnitudes effects with other known effects。

 so volume loss is similar to a decade of normal aging is akin to the example we gave from before。

 so we've talked about this idea before of taking effects for things that you're studying that you don't know a lot about and contrasting them with the effects of things that you know a lot about like normal aging in this case。

The third thing is the units and I can't stress this enough， make sure that the units are known。

 they're written out explicitly and they're included on all graph axes。

 so just to give you an anecdote， one point we were all sitting around discussing an effect that we saw for brain volume and we realized that we had messed up the units at some point and people's brains were supposedly growing at the size of a house every year or something like that and you know it was only through the exercise of checking the units and you know making sure that the units of our coefficient really made sense relative to the context of the problem that we kind of caught that error and found that one of our variables had been multiplied by a strange constant and so at any rate。



![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_8.png)

The units， again， it's a simple thing， but just drill down on the units in any given problem。

 understanding the units really helps you understand the problem。



![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_10.png)

So the second point I made was to focus on interpretation and interpretability。 So again。

 I'm going to reiterate that comparing effects to other known effects is a great way to focus on interpretation and interpretability。

The second way to focus on interpretation and interpretability is to encourage so called parsimony。

Parsimony to me is a key ingredient to having interpretable models。

 and what I mean by parsimony is using the simplest possible model and no simpler。 In other words。

 I'm encouraging you to place a premium on simplicity。 So if you have a regression model。

 regression models tend to be pretty simple models that achieve 95% of the prediction performance of some complicated machine learning algorithm。

 You might want to just stick with the regression model because that 5% penalty of complexity is really a very high price。

 You're losing a lot of interpretability。For that extra 5 percent prediction。

So in this case I would suggest encouraging in the report writing。

 focusing on the regression results or maybe doing both， but especially reporting and giving。

Good interpretations of the regression coefficients。

 which are much more interpretable than the output of a complex algorithm。

The third idea that I find very useful is the idea of so called what I like to call effect critiquing。

And if you see a significant effect or something that's very exciting。

 then what you want to do is think like try to put yourself in the mind of someone who would be a skeptic of that effect。

 Try to be as skeptical and as critical as possible。 And once you're in that mindset。

 then try to come up with the counterarguments for that effect。 Okay。

 so we saw this effect on lead exposure and brain volume loss。

 But was it really due to something else， like the different body mass indices of the people who were exposed to lead to the people who weren't。

 So it's really not do to lead exposure is really due to body mass。 Okay。

 that would be an example of a critique。 So what would we do， Well。

 we might consider a model that then had lead exposure and body mass in the model just to see what impact looking at both simultaneously did on the effect that we're interested in the lead exposure。

 so the broader point in this case is to think like a critic of your effect and that。

Will inform additional analyses you want to do to counter those arguments。

 and I think if possible you could get other groups of people to serve in the role as an internal critic in order to try to help you generate new ways to poke and prod an exciting or apparently significant effect to poke and prod at it and see if it really is real。

Now reproducibility is a big topic around here， Roger Pang。

 one of the coinstructors in the series is one of the leading researchers and thinkers on the idea of reproducibility。

 but I love this tweet by this person Ben Hammer， who I don't know who said when you write code。

 keep in mind that you're collaborating with your future self so for reproducibility in a report you want to make sure that these reports can get regenerated you'll get the exact same numbers。

 the report contains the information available to reproduce all of the numbers and analyses in it。

Fortunately for the people that you're managing， there are a lot of tools available now that merge the data analysis and the report writing into a single document。

 and the two most popular in my mind are knitter， which is a tool for R specifically。

And the idea is knitting the analysis and the report writing together。

And then iPython notebooks are another one。And you should highly encourage the people you're managing to use tools like these。

 maybe not these specific tools， but I would recommend these specific tools。

 but tools like these in order to make sure that your reports are reproducible and they leave a documented trail of exactly how to go from the data to the final analyses。

So。These are three simple rules or three broad categories I think。

 that can help improve report writing across a broad spectrum of areas。



![](img/46a4e4ffb3e8bcaf3fea101eb468cfe7_12.png)