# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p54 6_管理数据提取.zh_en -BV1L9Fde5EXS_p54-

![](img/8278703199b22badd2d7dbeeb5246f31_0.png)

Hi， my name is Brian Kaho， and this is the lecture on managing the data poll。

Like all the other lectures in this class， we're in a contrast between idealized settings and what happens in real life。

In real life， data can be very messy and when we talk about the data poll。

 we're talking about all the different components that go into going from a raw form of data into an analytic data set。

So in this process， some some of these steps are almost always required。

 You almost always have to pull an analytic data set from a larger， more complex data source。

 You often have to merge disparate sorts of data causing matching errors and things like that。

Often we have to summarize complex data types， so for example。

 you might have recorded voice data or text data that you need to convert into meaningful summaries。

In my personal area that I work in， often we're working with large complex brain imaging data。

 and we have to summarize that down into a handful of numbers that represent certain regions of the brain。

 for example。Another very common problem is going from data from that is convenient for one purpose into a convenient form for analysis。

 so for example， the way we might store the data for archival purposes is generally not what's right for analysis purposes。

 so in the process of converting there can always be errors。So as a manager。

 you're not going to actually probably execute any of these solutions。

 maybe you did that in your past， but now you're managing groups of people or individuals that are doing this for you。

 so in this lecture we're going to give you some simple tools that you can do to help ensure data quality in real life when you have these kind of messy data issues。

And in researching this lecture， I noticed that there were a lot of tools for the practitioners for the people that are actually going to be doing the merging and doing the actual data manipulations。

 but relatively few for managers。 So that's what we're going to focus on here。

 The first thing I'd like to mention is the simple act of creating what I like to call table one and these are basically just summary tables and these are a great way to catch errors and an Epi and biostatistics we call these tables table1 and the reason we do that is because whenever you write an Epi or biostatistics paper。

 there's always a first table that's main purpose is just to summarize demographic information in your sample。

So this is a great way to catch errors， but a couple of caveats get standard deviations along with means。

 medians and quantiles， the standard deviations will also help you catch errors。

 another important one and I'll give an anecdote about this in a minute is check your units。

And I'll give an anecdote just to remind exactly what I mean by that and then the other important thing I would say is usually your're meeting about these data tables maybe weekly。

 maybe monthly， but keep the old ones and always refer back to them。

 even subtle changes in these table ones can often highlight important meaningful changes。

 an errant record or something like that if means that are usually quite stable。

 jump up from one report to the next， that's often valuable information。

So now I'm going to go over this example that I alluded to earlier。In this example。

 we were studying brain volume as it related to people who were chronically exposed to lead。

 they worked in a chemical manufacturing plant where they were back when they were adding lead to paint and gasoline and that sort of thing。

We were interested in people's longitudinal change and brain volumes over time and when we started creating our table ones。

 we weren't keeping track of our units and it wasn't until much later on in the process。

 thankfully well before we had finished the paper but it wasn't until pretty long in the process before we realized we weren't keeping track of our units and that people's brains were declining at a rate that was way too fast to be reasonable。

 they were going from the size of a house to the size of a P for example， too quickly。

 and that was only because we hadn't track hadn't kept good track of our units。

 but once when we had a very helpful discussion about what the units were。

 and then because of that discussion on what the units were。

 we went on a long literature review on standard rates of brain decline in healthy adults。

 this really helped inform the paper， but more than anything it also helped us with data quality since we realized that there were some errant measurements。

Diving driving up results。

![](img/8278703199b22badd2d7dbeeb5246f31_2.png)

So。A second tool at your disposal after the modeling stage， just like we have the table1。

 which is before which we usually conduct before we do any modeling。

 after you've done some regression modeling regression diagnostics are an extremely useful way to detect data errors and my favorite examples of regression diagnostics are from lens to Fsky who's at North Carolina State。

 And if you look at this data set on the left， it actually goes on for a while， after that。

 if you were to look at it and do some basic scatter plots。

 you would see nothing out of the ordinary in the data， it would just look kind of like noise。

 However， if you do residual plot。

![](img/8278703199b22badd2d7dbeeb5246f31_4.png)

Which is plotting the errors of the fitted values from the regression model versus the actual observed outcome values versus the predicted。

 you see this crazy plot with Homer Simpsons on it。

 And this is his way of showing how residual plots can highlight hidden systematic patterns in our data。

 so residual plots are always a good thing to look at and always a good thing to look at for systematic patterns。

 errant observations， outliers and those sorts of things。 Of course。

 these always occur after you've done your modeling。

 you have to have a model in order to look at a residual。

 So let me give you some definitions of the some of the things that you might want to look at。

 especially from regression modeling， which is my sort of favorite kind of modeling。



![](img/8278703199b22badd2d7dbeeb5246f31_6.png)

![](img/8278703199b22badd2d7dbeeb5246f31_7.png)

![](img/8278703199b22badd2d7dbeeb5246f31_8.png)

So residuals， like I just said， these are the difference between the response。

 the outcome that you're studying and the fit of value， what your model predicts it would be。

 So what you want to look for in residual plots， you just want to make sure that there aren't any systematic patterns and you want to look for extremely large values that are well outside the general pattern of the residuals。

There's another quantity called the hat values， and they consider how variable a data row of explanatory variable is among its space of fellow predictors。

 so all hat values are going to tell you is simply how outside of the normal range of variability。

 this particular row of data is relative to all its other colleagues。So the DF fits。

 DF betas and cooks distance， these are all measures of things that are kind of related to sort of like cross validationation。

 and in all these cases what you do is you fit the model with a point deleted and then you fit the model with that point included with a row of your data entirely deleted and then with that row included。

Okay and then you look at how much your results changed by virtue of leaving that row in or out。

 And if you compare the fitted values， then you get what are called the Df fits。

 if you compare the slope estimates， then you get what are called the Df betas。

 and if you compare the slope estimates aggregated into one single number。

 one single metric that's called cooks distance。 but all of these are influence measures。

 all they're trying to do is tell you how much did things change when I deleted this data point from my model fitting That's also the same logic among the press residuals which are just residuals of the same sort。

 how big was the residual for this data point if I left it in versus I left it out。

 and these are often called leave one out residuals or cross-vald residuals。

 but all of these things are useful and your analyst or whoever you're working with。

 you should work with them so they produce these kinds of residual diagnostic plots with your regression。

 not only do they help you of value。Things about your regression model。

 but they help you evaluate things about errant data points， outlying observation。

 and then you can drill down and see what went wrong to cause those specific observations to have such a large impact on the model fit。

 for example， or to be so outside of the norm of all their peers。Another kind of interesting。

 in my mind， fascinating way to consider data quality is to use Benford's law and Benford's law is the so-called first digit law and I just mention it here。

 you can read up on it and sometimes people find it useful and it's a so-called phenomenological law about the frequency distribution of leading digits in many but not but of course not all real life sets of data and so what this means what Benford's law says is if you look at the final digit。

 say for example of telephone numbers， they don't follow a uniform distribution。

 they follow a distribution that looks something like this and you can try try some Benford laws's experiment and it's basically saying that the numbers should be uniform on a log scale rather than on the natural scale so what you can do in terms of data quality sometimes is if you're phenomenon that you're studying。



![](img/8278703199b22badd2d7dbeeb5246f31_10.png)

Whatever outcome that you're studying， if its digits should follow Benford's law。

 if you've checked in the past， then you can do it again and see if there was some systematic error causing the distribution of your the distribution of your points not to follow this law。

 again， this only is applicable when the digit should follow Benford's law as as an example。

 if you're looking at a particular city， the first digit。

 the leftmost digit of telephone numbers isn't going follow Benford's laws because it's going to be related to the area codes。

 But the rightmost digit does tend to follow Benford's laws so。



![](img/8278703199b22badd2d7dbeeb5246f31_12.png)

At any rate， it's a little subtle tool that you can use for assessing data quality errors。

 systematic data quality errors that's perturbing the distribution of the digits of your data。

The final thing you might want to try is actually checking specific rows of your data through so called data quality queries。

 DQQs。

![](img/8278703199b22badd2d7dbeeb5246f31_14.png)

Of course you can't check every single point because that's usually too time consuming。

 however you can check some and you can use statistical procedures like random sampling to get a random sample of rows of your data。

 check those rows individually and because it's a nice random sample。

 you can get an estimate of the proportion of bad rows in your data so you can use statistics to sample and understand how good or bad in general your data set is from a relatively small sample that you check by hand so these are some simple techniques that you can help to try and stay on top of the real life circumstance where your data is actually a messy mismatash of merging errors in that sort of thing since we all know that the true idealized setting doesn't occur in real life ever。



![](img/8278703199b22badd2d7dbeeb5246f31_16.png)

![](img/8278703199b22badd2d7dbeeb5246f31_17.png)