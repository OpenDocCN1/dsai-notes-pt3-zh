# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P22：21_08 02 t置信区间例子.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/70d72436cfb0e9642473d4c7a4d9b360_0.png)

In R， typing data sleep brings up the sleep data that was originally analyzed in Gossetts biometric of paper。

 This shows the increase in hours slept for patients on two sleep medications。



![](img/70d72436cfb0e9642473d4c7a4d9b360_2.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_3.png)

R treats the data as two groups rather than paired。

 but here we're going to treat the data as if they were paired。



![](img/70d72436cfb0e9642473d4c7a4d9b360_5.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_6.png)

Here。

![](img/70d72436cfb0e9642473d4c7a4d9b360_8.png)

Data， sleep will load the data， Head sleep will print the first few rows of the data frame。



![](img/70d72436cfb0e9642473d4c7a4d9b360_10.png)

The variable extra is the extra hours slept。

![](img/70d72436cfb0e9642473d4c7a4d9b360_12.png)

Group is a group I D， and I D is a subject I D。 So one through 10 will give you subjects。

 I D 1 through 10 observation 11 is。

![](img/70d72436cfb0e9642473d4c7a4d9b360_14.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_15.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_16.png)

Subject I D 1 again， and so on。

![](img/70d72436cfb0e9642473d4c7a4d9b360_18.png)

Here I plot the data and again the code for the plot can be found in the R Markdown file。



![](img/70d72436cfb0e9642473d4c7a4d9b360_20.png)

I've connected each subject with a line。

![](img/70d72436cfb0e9642473d4c7a4d9b360_22.png)

I think it's pretty clear here the benefit from。

![](img/70d72436cfb0e9642473d4c7a4d9b360_24.png)

Acknowledging that these are repeat measurements on the same subjects。



![](img/70d72436cfb0e9642473d4c7a4d9b360_26.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_27.png)

If you do not acknowledge that， then what you are comparing is this variation。

 Group 1 variation minus this variation， group 2 variation。



![](img/70d72436cfb0e9642473d4c7a4d9b360_29.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_30.png)

If you do acknowledge that。Then you are comparing。

![](img/70d72436cfb0e9642473d4c7a4d9b360_32.png)

These subject specific differences when comparing across groups。

 the variation in these differences is much lower because observations within a subject are quite correlated。



![](img/70d72436cfb0e9642473d4c7a4d9b360_34.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_35.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_36.png)

Here， I grab。

![](img/70d72436cfb0e9642473d4c7a4d9b360_38.png)

The first 10 measurements， which are subjects 1 through 10。

 And here I grab the latter 10 measurements， which is subjects 1 through 10 on the second medication。



![](img/70d72436cfb0e9642473d4c7a4d9b360_40.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_41.png)

The difference then is group 2 minus group 1。

![](img/70d72436cfb0e9642473d4c7a4d9b360_43.png)

Here， the vector wide subtraction making sense because I grab them in the specific order。



![](img/70d72436cfb0e9642473d4c7a4d9b360_45.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_46.png)

The mean of the difference is just mean， and the standard deviation of the difference can be obtained with the function S here I define n to be 10。

My T confidence interval can be given like this。 It is the mean plus or minus。

 the relevant T quantile evaluated at n -1 degrees of freedom times the standard error of the interval。



![](img/70d72436cfb0e9642473d4c7a4d9b360_48.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_49.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_50.png)

Of course， we don't want to do this every time so we can just do the function T test of difference。



![](img/70d72436cfb0e9642473d4c7a4d9b360_52.png)

And T test。Where we pass at the two vectors and give it the argument paired equals true。

 or you can actually give it a form of model statement where you say outcome extra。



![](img/70d72436cfb0e9642473d4c7a4d9b360_54.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_55.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_56.png)

Is a function of the group。Where paired equals true， evaluated for the data frame sleep。



![](img/70d72436cfb0e9642473d4c7a4d9b360_58.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_59.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_60.png)

I formatted these results a little bit because it gives you much， much more output than this。

 But I concatenated them into a matrix。 And you can see that all of those commands give you about the same result。



![](img/70d72436cfb0e9642473d4c7a4d9b360_62.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_63.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_64.png)

The difference in the groups being somewhere。Between 07 and 2。46。

 So because this is a confidence interval， the interpretation is that if we were to repeatedly perform this procedure on independent samples。

 about 95 per cent of the intervals that we obtained。

 would contain the true mean difference that reing。 This， of course。

 assumes that this subjects are a relevant sample from a population of subjects that were interested in。



![](img/70d72436cfb0e9642473d4c7a4d9b360_66.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_67.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_68.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_69.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_70.png)

![](img/70d72436cfb0e9642473d4c7a4d9b360_71.png)

Suppose。