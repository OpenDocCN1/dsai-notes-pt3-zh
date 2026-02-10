# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P22：21_08 02 t 置信区间示例.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

![](img/9e0c404442996cb86ef8c51e8883b8bd_0.png)

In R， typing data sleep brings up the sleep data that was originally analyzed in Gosetts biometric of paper。

 This shows the increase in hours slept for patients on two sleep medications。

R treats the data as two groups rather than paired。

 but here we're going to treat the data as if they were paired。



![](img/9e0c404442996cb86ef8c51e8883b8bd_2.png)

Here。

![](img/9e0c404442996cb86ef8c51e8883b8bd_4.png)

Data， sleep will load the data， Head sleep will print the first few rows of the data frame。

The variable extra is the extra hours slept。Group is a group I D， and I D is a subject I D。

 So one through 10 will give you subjects。 I D 1 through 10 observation 11 is。



![](img/9e0c404442996cb86ef8c51e8883b8bd_6.png)

Subject I 1 again and so on。

![](img/9e0c404442996cb86ef8c51e8883b8bd_8.png)

Here I plot the data and again the code for the plot can be found in the R Markdown file。

I've connected each subject with a line。I think it's pretty clear here the benefit from。

Acknowledging that these are repeat measurements on the same subjects。If you do not acknowledge that。

 then what you are comparing is this variation， Group 1 variation minus this variation。

 group 2 variation。

![](img/9e0c404442996cb86ef8c51e8883b8bd_10.png)

If you do acknowledge that。Then you are comparing。These subject specific differences when comparing across groups。

 the variation in these differences is much lower because observations within a subject are quite correlated。



![](img/9e0c404442996cb86ef8c51e8883b8bd_12.png)

![](img/9e0c404442996cb86ef8c51e8883b8bd_13.png)

Here， I grab。

![](img/9e0c404442996cb86ef8c51e8883b8bd_15.png)

The first 10 measurements， which are subjects 1 through 10。

 And here I grab the latter 10 measurements， which is subjects 1 through 10 on the second medication。

The difference then， is group 2， group 1。Here， the vector wide subtraction making sense because I grab them in the specific order。

The mean of the difference is just mean， and the standard deviation of the difference can be obtained with the function S here I define n to be 10。

My T confidence interval can be given like this。 It is the mean plus or minus。

 the relevant t quantile evaluated at n -1 degrees of freedom times the standard error of the interval。

Of course， we don't want to do this every time so we can just do the function T test of difference。

And T test。Where we pass at the two vectors and give it the argument paired equals true。

 or you can actually give it a form of model statement where you say outcome extra。

Is a function of the group。Where paired equals true， evaluated for the data frame sleep。



![](img/9e0c404442996cb86ef8c51e8883b8bd_17.png)

![](img/9e0c404442996cb86ef8c51e8883b8bd_18.png)

I formatted these results a little bit because it gives you much， much more output than this。

 but I concatenated them into a matrix and you can see that all of those commands give you about the same result。

The difference in the groups being somewhere。Between 07 and 2。46。

 So because this is a confidence interval， The interpretation is that if we were to repeatedly perform this procedure on independent samples。

 about 95 per cent of the intervals that we obtained。

 would contain the true mean difference that reing。 This， of course。

 assumes that this subjects are a relevant sample from a population of subjects that were interested in。



![](img/9e0c404442996cb86ef8c51e8883b8bd_20.png)

Suppose。