# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P13：12_绘制预测因素.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

One of the most important components of building a machine learning algorithm or prediction model is understanding how the data actually look and how the data interact with each other。

 so the best way to do that is actually by plotting the data and in particular plotting the predictors。



![](img/f30c2143e7b005ab47d103f12c3991c6_1.png)

So for this example， we're going to be using this wages data and so the wages data is actually data from the ISLR package。

 which you can find at this link and it's from the book Introduction to Statistical Learning。

 So we're going to be looking at this data and seeing how we can use it for prediction。

So if I load the ISLR package again I'm going have to install it first and then I can load it and I also load the GG P2 package because we're going be using that for some plotting and the caret package because we're going to be using that for model building the wage data is actually in the ISLR package and I can load it with data and a capital W wage and then I can look at a summary of that wage data to look at all the different variables that are in there so we have the year of the data that's collected。

 the age or the person who is the data is collected on in this case it's only mail people in this data。

 the marital status of those people， their race education。

 the region where the data was collected is just the mid- Atlanticlantic region and then the different kinds of job classes in their health so this gives you a little bit of information about what the type of data that we're going to be looking at and you can already see that we've detected a few interesting characteristics of this data just by looking at a summary here we know that they're all men we know that they're all in the mid Atlanticlantic region for example。

So then what we do is again， just like always， we're going to build a training set and a test set even before we do exploration。

 we're going to set aside the testing set and we're not going to use it for anything until we actually look at the data at the end of the model building experience and apply it just one time。



![](img/f30c2143e7b005ab47d103f12c3991c6_3.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_4.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_5.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_6.png)

So we're gonna to do all our plotting in the training set so one example is to use this feature plot plot that comes from the carrot package so this plot will plot basically all of the features against each other so this plot looks a little bit confusing for this data so I thought I'd just go through it So here I'm using as the outcome I'm saying the outcome is the wage and then I'm going to look at all these different variables age education and job class So first of all I have this y variables so that's the outcome that we care about and here are the different variables I've got age education。

 you can't read it very clearly in this plot， but if you make it yourself you can and job class here and so what this plot is this is the plot here。



![](img/f30c2143e7b005ab47d103f12c3991c6_8.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_9.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_10.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_11.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_12.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_13.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_14.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_15.png)

Of。The outcome Y versus the job class here。😡，So you can see you can do that for every box so if you want to see the plot of job class versus education。

 that's this plot here。 and it's the same plot here only with the axes reversed and so forth。

 so it shows you all of the variables that you have here plotted against each other and in particular what you're looking for here are all the plots corresponding to each of the variables plotted versus the Y variable and you're looking for any variable that seems to show a relationship with the Y variable So for example。

 you can see that there seems to be a trend here between education and salary for example。

 So this is a one way that you can look at all the data。

 Another thing that you can use is either Q plot function in the Gpl2 package or just the plot function base R。



![](img/f30c2143e7b005ab47d103f12c3991c6_17.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_18.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_19.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_20.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_21.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_22.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_23.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_24.png)

So here I'm plotting age versus wage and so you can see again it appears that there seems to be some kind of trend with age and wages but you also see one thing that you notice frequently from making plots like this here's some very strange patterns so you see there's this big chunk up here of observations that appear to be very different than the relationship down here for these chunks So one thing that we might want to do is try to figure out why there's that strange relationship between ages and wages before we build our model so one thing that we could do is for example using the G plot2 package color that plot by different variables so again I plotted age versus wage so on the x axis is age on the y axis is wage but now I've colored it by the job class and so you can do that with by passing the parameter color to the Q plot function and so what you see now is that most of the individuals that are up in this other chunk come from the information based jobs as opposed to the industrial jobs so that might explain。



![](img/f30c2143e7b005ab47d103f12c3991c6_26.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_27.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_28.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_29.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_30.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_31.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_32.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_33.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_34.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_35.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_36.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_37.png)

And a lot of the difference here between these two big classes of observations。

 so this gives you a way to sort of detect variables that might be important in your model because they show variation in the data。



![](img/f30c2143e7b005ab47d103f12c3991c6_39.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_40.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_41.png)

So you can also add regression smoothers so for example now what I've done is I've again made a plot of age versus wage but now I've colored it by education and so then what I can do is I can use the G underscore smooth function to apply linear smoother to the data you would have learned about this in exploratory data analysis but if not you can just see the function right here and so what that does is for every different education class it fits a linear model so you can see there's a purple line here and that corresponds to the people with advanced degrees and then you can see for example a green line here that corresponds to the people with some college and so forth and so you can see if there's a different relationship for different age groups。



![](img/f30c2143e7b005ab47d103f12c3991c6_43.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_44.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_45.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_46.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_47.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_48.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_49.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_50.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_51.png)

The other thing that you might that is often very useful is to break up things like the wage variable into different categories because sometimes it's clear that specific categories seem to have different relationships the way I tend to do that is with the cut2 function that's in the HMi package so if you load the HMi package and then use cut2 you can tell it with the G parameter how many groups to break the data into and itll break the data up into factors based on quantile groups so all the observations that land between 20 and 0。

1 and 91。7 on the wage variable will get assigned to this factor level and then all the values between 91。

7 and 118。9 will get assigned to this group and so forth and so what you can do now is you can actually use that in order to make different kinds of plots so now suppose I wanted to plot wage versus oh sorry wage groups versus age I can now use Q plot again but now I can pass it the box plot geometry and then I can say okay。



![](img/f30c2143e7b005ab47d103f12c3991c6_53.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_54.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_55.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_56.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_57.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_58.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_59.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_60.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_61.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_62.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_63.png)

I want to see the plot of these different wage groups versus age and sometimes that can make it easier to see different trends that are emerging。

 for example， you can see here a little bit more clearly the relationship between age and wage。



![](img/f30c2143e7b005ab47d103f12c3991c6_65.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_66.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_67.png)

The other thing that you might want to do is you might want to add on top of the box plots actually the points themselves the reason why you might want to do this is because sometimes box plots can obscure how many points are being shown here and so one thing that you can do is you can say both box plot and jitter and you can have arrange the plots so you can see both the box plot itself and you can see the box plot with points overlaid so that's what grid range is doing it's actually generating the two plots so P1 was the plot that we made on the previous slide and P2 is the plot we made here with points overlaid and grid range makes two plots side by side so you can see here with from the dots that there's a large number of dots and each of the different boxes and so that suggests that any trend that we observe may actually be real if you observe just a few dots covering one of the boxes it means maybe that particular box isn't very well representative of what the data actually look like。



![](img/f30c2143e7b005ab47d103f12c3991c6_69.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_70.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_71.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_72.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_73.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_74.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_75.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_76.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_77.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_78.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_79.png)

Another thing that's very useful is you can use the cut variable。

 the factorized version of the continuous variable to look at tables of data。

 so here I'm making a table comparing this factor version of wages to the job class and so I can see for example that there are more industrial jobs in the lower wage variable then there are information jobs and that trend reverses itself for the high wage jobs there are fewer industrial people and more information people you can also use prop table to actually get the proportions in each group so here it's the proportion by passing it one I say I want to get the proportion in each row so if I pass it to two here it would give me the proportion in each column。



![](img/f30c2143e7b005ab47d103f12c3991c6_81.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_82.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_83.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_84.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_85.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_86.png)

So here I see that 62% of the low wage jobs correspond to industrial and  38% correspond to information。

 and so you can use that to get an idea of how those proportions change across different wage levels。



![](img/f30c2143e7b005ab47d103f12c3991c6_88.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_89.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_90.png)

Finally you can use density plots to plot the values of continuous predictors so here again I'm using the Q plot function I'm plotting the wage variable and I'm plotting a density plot versus education so this basically shows where the bulk of the data is so on the X axis is the wage and on the Y axis is sort of the proportion of the variable that falls into that bin of the X axis and so you can see for example the high school grads tend to have more values that are down here in the lower part of the range and the advanced degree folks tend to be a little bit higher and there's also a group outgroup over here that tends to be very high for both the advanced degree as well as the college grads which are shown in blue so sometimes density plots can show things that box plots can't necessarily do it's also easier to overlay multiple distributions when you're doing density plots in other words if you break things up into a bunch of different groups and you want to see how all the distributions change by group density plots can be very useful。



![](img/f30c2143e7b005ab47d103f12c3991c6_92.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_93.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_94.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_95.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_96.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_97.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_98.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_99.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_100.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_101.png)

So one thing to keep in mind is to make your plots only in the training data。

 the test set again can't be used for exploration that would be similar to training your model on the test set。

 which as we talked about previously， will lead to overfitting things that you should be looking for in these plots is im balance and the outcomes or the predictors if you see all of the predictors tend to be one value in the one outcome group and not another outcome group。

 then you see that's a good predictor， but if you see that you only have three of one outcome and 150 of the other outcome。

 that means it's going to be very hard to build an accurate classifier between those two classes。

 you're looking for outliers or weird groups outing the data that might suggest that there's some variables you're missing and groups of points that are not explained by any of the predictors skewed variables which you're going to want to transform and look better。

 sort of nicely normally distributed if you're using things like regression models but that may not matter as much of you're using more machine learning methods。



![](img/f30c2143e7b005ab47d103f12c3991c6_103.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_104.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_105.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_106.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_107.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_108.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_109.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_110.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_111.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_112.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_113.png)

For more information on plotting in general， you can can look at the GGPloot2 tutorial。

 you can also take the exploratory data analysis class in this data science specialization。

 or you can look at the carrot visualization tutorial because that'll give you a little bit more information about prediction specific plots that might be useful。



![](img/f30c2143e7b005ab47d103f12c3991c6_115.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_116.png)

![](img/f30c2143e7b005ab47d103f12c3991c6_117.png)