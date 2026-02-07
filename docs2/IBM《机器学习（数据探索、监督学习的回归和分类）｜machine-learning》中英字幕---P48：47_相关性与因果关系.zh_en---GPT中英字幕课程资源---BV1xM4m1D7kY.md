# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P48：47_相关性与因果关系.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this section， we're going to go over correlation versus causation and their differences。

So in this section， we're going to cover correlation versus causation。

 the classic misunderstanding that we must always be guarding against。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_1.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_2.png)

How confounding variables will play a role in this confusion。

And then we'll also show some examples of spurus correlation where there's clearly no causal effect。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_4.png)

So let's begin our discussion of correlation versus causation by starting off with。

 does it rain more on cooler days， So we generally associate rain with cold weather。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_6.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_7.png)

And we want to think， does it actually rain more when days are cooler？



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_9.png)

Maybe it depends on where you are。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_11.png)

Some places have summer monsoon， so maybe the mechanism is as it gets warmer there。

 it'll actually rain more。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_13.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_14.png)

So warmer weather here increases evaporation， which can increase humidity。

 and in warm weather there is water in the air to for precipitation。

 and this mechanism would suggest warmer weather leads to more rain。

 so we want to keep in mind here the actual mechanism that's coming into play in terms of our cause and effect。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_16.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_17.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_18.png)

And on the other end， cooler weather decreases dew point。 I。e。 air can hold less water。

 And this suggests if humid air enters the air and cools， it will turn into rain。

 And this mechanism would suggest cooler weather would lead to more rain。 Now。

 this isn't a science lesson。 The idea being here that we want to actually think about the underlying mechanism when we are talking about cause and effect。

😊。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_20.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_21.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_22.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_23.png)

So how are correlations important？If two variables， x and Y are correlated。

 then x is useful for predicting Y。Not necessarily going to tell you the cause and effects。

 but it may be good in predicting another value。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_25.png)

So if we are trying to model Y and we find things that correlate with Y。

 we may be able to improve our modeling。 So it's worth noting that even if there's no causal factor。

 if the correlation is strong and we are not trying to directly manipulate our X or our features as a causal factor。

 It can still prove useful to make predictions， it just might be slightly more dangerous as this relationship if we don't understand the underlying factors may not hold in the future。

 also， we definitely want to make sure to。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_27.png)

Way against ever using it as a。Feature that we can tweak in order to adjust the outcome variable。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_29.png)

So we should be careful， like I just noted， about changing X with the hope of changing Y。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_31.png)

Once we get into causal effects， we may find that if we depend on correlation。

 we can be easily misled。Now， X and Y can be correlated for many different reasons。

Some different reasons include X causes Y， which is what we are looking for that is when causation equals correlation。

 and we can think about our marketing budget successfully leading to higher revenue。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_33.png)

We can have the inverse where y actually causes x， and we are mixing up the cause and effect。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_35.png)

So we could actually have been increasing our marketing budget because we had more revenue to spend。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_37.png)

Again， X and Y are both caused by something else。 There's a confounding external variable。

 So maybe when the holiday season hits， we also have increased budget for marketing。

 as well as more revenue coming in due to the holiday season， but not one causing the other。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_39.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_40.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_41.png)

Both being caused by the holiday season。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_43.png)

And then maybe X and Y aren't really related at all。 We just got unlucky in our sample。

 and this is spurious correlation。Confounding correlation is actually kind of a subset of spurus correlation。

And we can think of it as any time two values just really aren't related at all。

 maybe there's a confounding variable， or maybe it's just random that marketing spend versus revenue both going up at the same time。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_45.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_46.png)

So some more examples to think of， student test scores， let's say。

 are positively correlated with the amount of time studied， which makes sense。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_48.png)

But this doesn't necessarily mean we should get students to study more by curbing everyone's grades upwards。

 right， this would likely have the opposite effect。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_50.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_51.png)

It is more likely that studying is going to help students learn material。

 so studying causes better performance， not better performance will help us cause more studying。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_53.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_54.png)

Another example is customer satisfaction is negatively correlated with customer service call volume。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_56.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_57.png)

Now， obviously this doesn't mean that we should remove or hide all of our customer service numbers with the hope of improving customer satisfaction。

Right， it's not the fact that。There's。More customer service calls coming in。

 that is bringing down the customer satisfaction， but rather the customer satisfaction being low。

 bringing in more customer service calls。So let's discuss confounding variables A confounding variable is something that causes both x and y to change。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_59.png)

So x and y are correlated， even though x doesn't cause y and y doesn't cause X。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_61.png)

So let's think through some examples of confounding variables。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_63.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_64.png)

We know that the number of annual car accidents and the number of people named John are positively correlated。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_66.png)

And the compounding variable here is that both are correlated with population size。

 the more people there are in the world， which is always increasing。

 the more people there will be named John and the more car accidents there will be。

 and this is deliberately silly。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_68.png)

Second one is the amount of ice cream sold and the number of drownings in a week are positively correlated。

 and that's due to the compoundfounding variable that they're both positively correlated with temperature。

 right， Warer temperature means you'll probably sell more ice cream and more people will probably be in their pools or out in the beach where they can therefore be more likely to drown。

 Now， this is more along the lines of what we'll see in the real world。

 in the sense that there is actually some predicted power because they are both affected by temperature and when the temperature goes up more ice cream will be sold。

 So if more ice cream is going to be sold， you can use that to predict technically。

 the number of drownings。 But obviously， the real story and the underlying mechanism is much more complicated。

😊。

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_70.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_71.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_72.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_73.png)

And then our third example， it sounds plausible。 It's the number of factories a chip manufacturer owns and the number of chips sold are going to be positively correlated。

 Maybe you think I should own more， and therefore， I'll be able to sell more。

 but they're both really driven by the demand from the market， right。

 increasingncing the number of factories would not increase the number of chips made。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_75.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_76.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_77.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_78.png)

It would increase the number of tips made， but not necessarily the number sold。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_80.png)

So some fun spur correlations to look at these are correlations that are just coincidences due to the particular sample and would probably not hold on longer samples or different samples。

 we have the age of Missam Americaica is highly correlated with murders by steam。

 hot vapors and hot objects， this actually has a pearson correlation coefficient of 0。87。

 which is very high， but it is worth noting here the small variation in regards to the Missam Americaica winners。

 as well as understanding that the underlying mechanism is。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_82.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_83.png)

Pretty much nonsense。And then we have the worldwide non commercial space launches。

 it's correlated highly with the sociology Doctorates Awards。 there may be some。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_85.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_86.png)

More than coincidence there， but also we want to keep in mind for both of these。

 when we're working with something over time， you may end up with this voice correlation if things tend to increase or decrease in the same trajectory given the time period that it's elapsed over。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_88.png)

So let's do a quick recap of what we learned in this section。

 we discussed correlation versus causation and making sure that we understood that correlation while it may have predictive power must be separated from causation。

 where you can change X in order to change your outcome variable Y。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_90.png)

We discussed confounding variables how there may be an external variable besides x and Y that causes that correlation。

 such as the temperature increasing and both ice cream sales increasing and the number of drownings increasing。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_92.png)

And then we talked about different s examples of spurious correlations to see how you can have correlations randomly happen out in the real world。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_94.png)

That wraps it up for this section， and I look forward to seeing you in the next course。 Thank you。



![](img/33590fa2fb74fb2978f1da38fbf1dd7a_96.png)

![](img/33590fa2fb74fb2978f1da38fbf1dd7a_97.png)