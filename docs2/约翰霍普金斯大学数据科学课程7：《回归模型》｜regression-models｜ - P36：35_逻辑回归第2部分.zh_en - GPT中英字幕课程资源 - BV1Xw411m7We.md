# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P36：35_逻辑回归第2部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/85f36dad4cf12d73cc3afad5db3608eb_0.png)

Okay， so let's look at logistic regression curves and think about how R is fitting the data。



![](img/85f36dad4cf12d73cc3afad5db3608eb_2.png)

So here I'm going to mut。

![](img/85f36dad4cf12d73cc3afad5db3608eb_4.png)

Use the package manipulate。And I have my beta 2 and my beta 1 set here。

And so here's my logistic regression curve。Looks like an S kind of， and here's beta 1。

Let's see what happens as I render it。Or as I change it， it notice as I。



![](img/85f36dad4cf12d73cc3afad5db3608eb_6.png)

As I get it closer up to higher values， it becomes more peaked。



![](img/85f36dad4cf12d73cc3afad5db3608eb_8.png)

And then if I go negative， it actually flips around。



![](img/85f36dad4cf12d73cc3afad5db3608eb_10.png)

Okay。Then my beta zero curve， what happens to this， it just shifts it along。

It's hard to tell because I'm keeping the。That don't。



![](img/85f36dad4cf12d73cc3afad5db3608eb_12.png)

The X axis here is always the same， but it's just shifting the S curve to the left or to the right。



![](img/85f36dad4cf12d73cc3afad5db3608eb_14.png)

Okay， so let's think about what R is doing when it's trying to fit logistic regression curves。



![](img/85f36dad4cf12d73cc3afad5db3608eb_16.png)

So。

![](img/85f36dad4cf12d73cc3afad5db3608eb_18.png)

Imagine I have a bunch of zeros and one。 So all my x axis one is up here and0 was down there。

 So imagine for this regressor， this X regressor here， I have a bunch of。



![](img/85f36dad4cf12d73cc3afad5db3608eb_20.png)

![](img/85f36dad4cf12d73cc3afad5db3608eb_21.png)

![](img/85f36dad4cf12d73cc3afad5db3608eb_22.png)

A bunch of zeros down there， but maybe I had occasional one。



![](img/85f36dad4cf12d73cc3afad5db3608eb_24.png)

But then over here I have。A lot more ones and then right here I have some zeros。Okay。

 so what R is trying to do Okay， so it knows as I head。



![](img/85f36dad4cf12d73cc3afad5db3608eb_26.png)

We can see as a head to larger x values。

![](img/85f36dad4cf12d73cc3afad5db3608eb_28.png)

It becomes increasingly likely that my outcome is a one as I head towards smaller x values。

 it becomes increasingly likely that my outcome is a0。 So R， what R is trying to do is then move。



![](img/85f36dad4cf12d73cc3afad5db3608eb_30.png)

![](img/85f36dad4cf12d73cc3afad5db3608eb_31.png)

Is trying to move the S curve， it's trying all different sorts of S curves。



![](img/85f36dad4cf12d73cc3afad5db3608eb_33.png)

Right， all different sorts of logistic curves to find the one that best。



![](img/85f36dad4cf12d73cc3afad5db3608eb_35.png)

Matches up with the associated probabilities。

![](img/85f36dad4cf12d73cc3afad5db3608eb_37.png)

Okay， and that's all that logistic regression is trying to do。



![](img/85f36dad4cf12d73cc3afad5db3608eb_39.png)

And it does it with the principle of so-called maximum likelihood。

 which again is something if you take the inference class from the data science specialization。

 you'll know a little bit more about， but so just imagine these points staying there。



![](img/85f36dad4cf12d73cc3afad5db3608eb_41.png)

![](img/85f36dad4cf12d73cc3afad5db3608eb_42.png)

![](img/85f36dad4cf12d73cc3afad5db3608eb_43.png)

And I'm going to get rid of them okay， and then just see how what R has under its disposal is to be able to move these two sliders and then define the S curve that fits that data the best。



![](img/85f36dad4cf12d73cc3afad5db3608eb_45.png)

![](img/85f36dad4cf12d73cc3afad5db3608eb_46.png)

Okay， and so that's all that logistic regression is doing。 And then this function。

 this is the fitted function out， right， is， this is the function。



![](img/85f36dad4cf12d73cc3afad5db3608eb_48.png)

E to the。Beta n plus beta 1 x over1 plus E to the beta n plus beta1 x。 That's the， that's the。

Logistic regression model， but convert it back to the probability scale。Okay。

 so I hope this helps you understand a little bit of behind the scenes what logistic regression is trying to do。



![](img/85f36dad4cf12d73cc3afad5db3608eb_50.png)