# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P17：16_创建新的变量.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

![](img/63674fd72a6f321a100fc57f6545e63c_0.png)

This lecture is about creating your variables。 Once you loaded the data set into R。

 sometimes you'll find that some of the variables that you are looking for are not actually in the raw data that youve loaded in。



![](img/63674fd72a6f321a100fc57f6545e63c_2.png)

So you may need to transform the data a little bit to get the value you'd like。



![](img/63674fd72a6f321a100fc57f6545e63c_4.png)

Usually you'll add those values back into the data frame。

 and this is particularly important when you're doing something like prediction where you want to create new variables that you might use as predictors。



![](img/63674fd72a6f321a100fc57f6545e63c_6.png)

![](img/63674fd72a6f321a100fc57f6545e63c_7.png)

Common variables that people create are missing this indicator。

 so pointing out where you might have missing data， that's one really common variable to create。

 also cutting up quantitative variables， creating variables that are factor versions of a quantitative variable corresponding to particular values that might be of interest or applying transformations to deal with data that have strange distributions。



![](img/63674fd72a6f321a100fc57f6545e63c_9.png)

![](img/63674fd72a6f321a100fc57f6545e63c_10.png)

![](img/63674fd72a6f321a100fc57f6545e63c_11.png)

![](img/63674fd72a6f321a100fc57f6545e63c_12.png)

![](img/63674fd72a6f321a100fc57f6545e63c_13.png)

So we're going to be using this Baltimore restaurantrant data set as an example， so again。

 you could go to the URL and then click over here on this export button to get the URL for a particular version of the data in this case I'm using the CSV version again。

 I see if the data directory exists then I download the file from the Internet and I load it into R using re CSsv。



![](img/63674fd72a6f321a100fc57f6545e63c_15.png)

![](img/63674fd72a6f321a100fc57f6545e63c_16.png)

Now I've got a data set rest data， which is the restaurant data that was created from this data。



![](img/63674fd72a6f321a100fc57f6545e63c_18.png)

And so one thing that I'm gonna talk about first before I get into analyzing the data is creating sequences sequences are often used to index different operations that you're going to be doing on data and so it's good to know how to create them the command that you use in R as seek and so usually what you do is you tell seek the minimum value and the maximum value and then there's two ways in which you usually specify how many values to generate one is to use the by command so by equals two means it creates it starts at one and then creates new values increasing each new value by 2。



![](img/63674fd72a6f321a100fc57f6545e63c_20.png)

![](img/63674fd72a6f321a100fc57f6545e63c_21.png)

![](img/63674fd72a6f321a100fc57f6545e63c_22.png)

![](img/63674fd72a6f321a100fc57f6545e63c_23.png)

![](img/63674fd72a6f321a100fc57f6545e63c_24.png)

![](img/63674fd72a6f321a100fc57f6545e63c_25.png)

![](img/63674fd72a6f321a100fc57f6545e63c_26.png)

Another way to do it is to specify the length of the vector and so what that means is it'll start at one and end at 10 and it will create exactly three values。



![](img/63674fd72a6f321a100fc57f6545e63c_28.png)

![](img/63674fd72a6f321a100fc57f6545e63c_29.png)

A third way is to say， suppose you have a vector X and it has five values in it and suppose you want to create an index so that you can loop over those five values。

 you might use the Cq along equals x， which will basically create a vector of the same length as x。

 but with indices consecutive indices that you can use for looping or for accessing subsets of datas。



![](img/63674fd72a6f321a100fc57f6545e63c_31.png)

![](img/63674fd72a6f321a100fc57f6545e63c_32.png)

![](img/63674fd72a6f321a100fc57f6545e63c_33.png)

![](img/63674fd72a6f321a100fc57f6545e63c_34.png)

So one kind of variable that you might want to create is a variable that indicates which subset another variable comes from So for example here we have this restaurant data we actually have the neighborhoods that the restaurants are in and so I might want to find all of the restaurants that are in two neighborhoods near me Roland Park and homeland and so if I use this percent in percent command it will allow me to find only the neighborhoods that are in those two or only the restaurants that are in those two neighborhoods that will return true if you're in that neighborhood in false if you're not and then what I'm doing is I'm appending this nearme variable onto the restaurant data so this allows me to now subset that data only by the restaurants that are near me。

 which is kind of a nice clean way of subsetting the data as opposed to always having to use this longer percent in percent command。



![](img/63674fd72a6f321a100fc57f6545e63c_36.png)

![](img/63674fd72a6f321a100fc57f6545e63c_37.png)

![](img/63674fd72a6f321a100fc57f6545e63c_38.png)

![](img/63674fd72a6f321a100fc57f6545e63c_39.png)

![](img/63674fd72a6f321a100fc57f6545e63c_40.png)

![](img/63674fd72a6f321a100fc57f6545e63c_41.png)

![](img/63674fd72a6f321a100fc57f6545e63c_42.png)

![](img/63674fd72a6f321a100fc57f6545e63c_43.png)

![](img/63674fd72a6f321a100fc57f6545e63c_44.png)

![](img/63674fd72a6f321a100fc57f6545e63c_45.png)

Another thing you might want to do is create binary variables， so for example。

 we might want to find the cases where we know the zip code is wrong。

 so again I'm assigning to the data frame， the variable zip wrongg and here I'm using the ifLs command。



![](img/63674fd72a6f321a100fc57f6545e63c_47.png)

![](img/63674fd72a6f321a100fc57f6545e63c_48.png)

![](img/63674fd72a6f321a100fc57f6545e63c_49.png)

So for the F else command， I first send it a condition in this case。

 I'm going to send it the condition is the zip code less than zero。 So if the zip code is less than0。

 we think that that zip code must be wrong and so the first thing that I return is true if the condition holds true So in other words all the cases where the zip code is less than zero I'll get a true and then this is what the function returns。

 if the condition is false So if the condition is false in other words。

 if the zip code is positive then I get a false So at the end of the day what I can do is then make a table of whether the zip code is wrong and whether the zip code is less than zero and you can see that in all the cases where the zip code is less than zero are greater than zero I get false and in the one case where the zip code is greater than zero or sorry less than zero I get true and so that might be a value that I want to filter out of my dataset and this makes it an easy way to filter those values out。



![](img/63674fd72a6f321a100fc57f6545e63c_51.png)

![](img/63674fd72a6f321a100fc57f6545e63c_52.png)

![](img/63674fd72a6f321a100fc57f6545e63c_53.png)

![](img/63674fd72a6f321a100fc57f6545e63c_54.png)

![](img/63674fd72a6f321a100fc57f6545e63c_55.png)

![](img/63674fd72a6f321a100fc57f6545e63c_56.png)

![](img/63674fd72a6f321a100fc57f6545e63c_57.png)

![](img/63674fd72a6f321a100fc57f6545e63c_58.png)

![](img/63674fd72a6f321a100fc57f6545e63c_59.png)

![](img/63674fd72a6f321a100fc57f6545e63c_60.png)

![](img/63674fd72a6f321a100fc57f6545e63c_61.png)

![](img/63674fd72a6f321a100fc57f6545e63c_62.png)

You also might want to make categorical variables out of quantitative variables。

 so for example we might want to break the zip codes up into consecutive numbers。

 so here I'm going to create a variable that I'm calling zip groups and so what I'm going to use is this cut command I'm going to apply it to a quantitative variable the zip code and I'm going to tell the cut command that I want to break that up according to some values a list of values that I give it in this case I'm going to break it up according to the quantiles of that zip code。



![](img/63674fd72a6f321a100fc57f6545e63c_64.png)

![](img/63674fd72a6f321a100fc57f6545e63c_65.png)

![](img/63674fd72a6f321a100fc57f6545e63c_66.png)

![](img/63674fd72a6f321a100fc57f6545e63c_67.png)

![](img/63674fd72a6f321a100fc57f6545e63c_68.png)

So what that will then return as a factor variable。

 so zip groups is a factor variable where it will break the variable zip code up into the zeroth quantile to the 25th percentile。

 the 25th to the 50th percentile， the 50th， the 75th and the 75th to the 10th percentile。

 and so for example， there are about 375 of the values that land between the 25th percentile and the 50th percentile。



![](img/63674fd72a6f321a100fc57f6545e63c_70.png)

![](img/63674fd72a6f321a100fc57f6545e63c_71.png)

![](img/63674fd72a6f321a100fc57f6545e63c_72.png)

![](img/63674fd72a6f321a100fc57f6545e63c_73.png)

![](img/63674fd72a6f321a100fc57f6545e63c_74.png)

![](img/63674fd72a6f321a100fc57f6545e63c_75.png)

And so then what I can do is I can make a table that shows you which of the zip codes fall into which of these different clusters。

 and so you can see say the low values fall into the first cluster and then the medium values fall into the next cluster and so forth。



![](img/63674fd72a6f321a100fc57f6545e63c_77.png)

![](img/63674fd72a6f321a100fc57f6545e63c_78.png)

![](img/63674fd72a6f321a100fc57f6545e63c_79.png)

So what this does is it breaks a quantitative variable up into a categorical variable。



![](img/63674fd72a6f321a100fc57f6545e63c_81.png)

An easier way to do that， I had to specify all the brakes with the quantile function in the previous version of cut if you go into the HMi package and you use the cut2 function。

 you can actually specify I want to break the zip code up into four different groups and I want to break them up according to the quantiles and so when I do that it will actually find out the quantiles for me and break it up into four groups according to the quantiles which is kind of a nice way to do it if you don't want to have to set the brakes in advance the cut2 function in the HMi package。



![](img/63674fd72a6f321a100fc57f6545e63c_83.png)

![](img/63674fd72a6f321a100fc57f6545e63c_84.png)

![](img/63674fd72a6f321a100fc57f6545e63c_85.png)

![](img/63674fd72a6f321a100fc57f6545e63c_86.png)

![](img/63674fd72a6f321a100fc57f6545e63c_87.png)

![](img/63674fd72a6f321a100fc57f6545e63c_88.png)

![](img/63674fd72a6f321a100fc57f6545e63c_89.png)

Another thing that you might want to do is you might want to create factor variables so for example。

 the zip code variable is an integer variable when you load it into R。

 but you might want to turn it into a factor variable in other words。

 it's not clear that being incrementing the zip code by one changes quantitatively the variable so you might want to turn that into a factor variable and the way that you do that is with the factor command so it takes an input of this integer variable and it turns it into a factor variable which I'm calling ZCF So if I look at the first 10 values of ZCF it shows me these values and they look just like they did before they look like the values that are the zip code values。

 but then it tells me how many different zip code levels there are there are 32 different zip code levels and if I look at a class of this variable it's a factor variable。



![](img/63674fd72a6f321a100fc57f6545e63c_91.png)

![](img/63674fd72a6f321a100fc57f6545e63c_92.png)

![](img/63674fd72a6f321a100fc57f6545e63c_93.png)

![](img/63674fd72a6f321a100fc57f6545e63c_94.png)

![](img/63674fd72a6f321a100fc57f6545e63c_95.png)

![](img/63674fd72a6f321a100fc57f6545e63c_96.png)

![](img/63674fd72a6f321a100fc57f6545e63c_97.png)

![](img/63674fd72a6f321a100fc57f6545e63c_98.png)

![](img/63674fd72a6f321a100fc57f6545e63c_99.png)

![](img/63674fd72a6f321a100fc57f6545e63c_100.png)

So a couple of other things that you might want to know about factor variables so here what I'm going to do is I'm going to create just a dummy vector so that we can see some other properties of factor variables。

 I'm going to create a vector of yeses and nos and so I'm going to do that randomly I'm going to generate a size 10 vector of yeses and nos。



![](img/63674fd72a6f321a100fc57f6545e63c_102.png)

![](img/63674fd72a6f321a100fc57f6545e63c_103.png)

![](img/63674fd72a6f321a100fc57f6545e63c_104.png)

![](img/63674fd72a6f321a100fc57f6545e63c_105.png)

And I'm going to turn that into a factor variable， and I'm going to by default。

 what it's going to do is it's going to treat the lowest value alphabetically as the first value in the factor variable。

 but suppose I want it to treat second the yes values of the lowest value。



![](img/63674fd72a6f321a100fc57f6545e63c_107.png)

![](img/63674fd72a6f321a100fc57f6545e63c_108.png)

![](img/63674fd72a6f321a100fc57f6545e63c_109.png)

![](img/63674fd72a6f321a100fc57f6545e63c_110.png)

Then I can tell it to take the levels and create them in this order。And so for example。

 what I can do is I can releve that variable and make the reference class be equal to the yes value。

😊。

![](img/63674fd72a6f321a100fc57f6545e63c_112.png)

![](img/63674fd72a6f321a100fc57f6545e63c_113.png)

Another thing that you can do is you can use the as that numeric command to change that factor variable back into a numeric variable if you want to use it in certain kinds of models。

 this can be a useful thing to do and one thing that itll do is it'll start with sort of the lowest value and call that one and then the next lowest value and call that two and so forth。



![](img/63674fd72a6f321a100fc57f6545e63c_115.png)

![](img/63674fd72a6f321a100fc57f6545e63c_116.png)

![](img/63674fd72a6f321a100fc57f6545e63c_117.png)

![](img/63674fd72a6f321a100fc57f6545e63c_118.png)

![](img/63674fd72a6f321a100fc57f6545e63c_119.png)

![](img/63674fd72a6f321a100fc57f6545e63c_120.png)

So cutting produces factor variables， we saw before that I wanted to create the zip groups variable where I cut the zip codes up into four separate groups by their quantiles and so if you make a table of them you'll get to see this table and the class of this object zip groups is now a factor variable。



![](img/63674fd72a6f321a100fc57f6545e63c_122.png)

![](img/63674fd72a6f321a100fc57f6545e63c_123.png)

![](img/63674fd72a6f321a100fc57f6545e63c_124.png)

You can actually use the mutate function to create a new version of a variable and simultaneously add it to a dataset。

 This is part of the plier package。 So what I'm going to do here is I'm going create a new data frame。

 This new data frame is I'm going to apply the mutate function to the old data frame and I'm going to add a new variable zip groups which is equal to a function of one of the variables in the original rest data data frame and so what happens now is the new data frame will be the old data frame rest data with the new variables added so now I can make a table of the zip groups and I can see that it appears in this new data frame rest2。



![](img/63674fd72a6f321a100fc57f6545e63c_126.png)

![](img/63674fd72a6f321a100fc57f6545e63c_127.png)

![](img/63674fd72a6f321a100fc57f6545e63c_128.png)

![](img/63674fd72a6f321a100fc57f6545e63c_129.png)

![](img/63674fd72a6f321a100fc57f6545e63c_130.png)

![](img/63674fd72a6f321a100fc57f6545e63c_131.png)

![](img/63674fd72a6f321a100fc57f6545e63c_132.png)

![](img/63674fd72a6f321a100fc57f6545e63c_133.png)

![](img/63674fd72a6f321a100fc57f6545e63c_134.png)

Another thing that you're probably going to do with quantitative data is in an exploratory analysis。

 maybe apply some different transformations， so here's a list of the most common transformations taking absolute values in square roots。

 you might take the ceiling or the floor if you want to round values up or down to the nearest integer you can also use the round function to round to as many digits as you'd like or the significant function to round to as many significant digits as you'd like all the standard sort of calculator functions like cosine and Sr and R as well as logs which are commonly used when you have skewed data or data with a lot of outliers and then you can also exponentiate data as well There's a lot more about this at these two links that I provided here at the bottom and Jack's lecture notes as well as this St methods page。



![](img/63674fd72a6f321a100fc57f6545e63c_136.png)

![](img/63674fd72a6f321a100fc57f6545e63c_137.png)

![](img/63674fd72a6f321a100fc57f6545e63c_138.png)

![](img/63674fd72a6f321a100fc57f6545e63c_139.png)

![](img/63674fd72a6f321a100fc57f6545e63c_140.png)

![](img/63674fd72a6f321a100fc57f6545e63c_141.png)

![](img/63674fd72a6f321a100fc57f6545e63c_142.png)

![](img/63674fd72a6f321a100fc57f6545e63c_143.png)

![](img/63674fd72a6f321a100fc57f6545e63c_144.png)

![](img/63674fd72a6f321a100fc57f6545e63c_145.png)

Even more further notes are available from thePlier tutorial as well as the lecture notes that focus on transformation from Angie Jay as well。



![](img/63674fd72a6f321a100fc57f6545e63c_147.png)

![](img/63674fd72a6f321a100fc57f6545e63c_148.png)