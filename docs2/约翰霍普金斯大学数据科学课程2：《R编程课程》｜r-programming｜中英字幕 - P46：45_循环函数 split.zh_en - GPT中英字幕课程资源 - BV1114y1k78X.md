# 约翰霍普金斯大学数据科学课程2：《R编程课程》｜r-programming｜中英字幕 - P46：45_循环函数 split.zh_en - GPT中英字幕课程资源 - BV1114y1k78X

T apply is useful because it splits up a vector into little pieces and it applies a summary statistic or function to those little pieces。

 and then after it applies that function， it kind of brings the pieces back together again。

 so split is not a loop function， but it's a very handy function that can be used in conjunction with functions like L apply or S apply and so I just want to mention it here。

 So split takes a vector， So it's kind of like T apply。

 but it's like T apply but without applying the summary statistics。

 So what it does is it takes a vector or an object X and it takes a factor variable F which again identifies levels of a group and then it splits the object X into the number of groups that are identified in factor F。

 So for example， if F has three levels identifying three groups。

 then the split function will split X into three groups。



![](img/7044923c9cfa237c4cff81d4f3576895_1.png)

![](img/7044923c9cfa237c4cff81d4f3576895_2.png)

![](img/7044923c9cfa237c4cff81d4f3576895_3.png)

![](img/7044923c9cfa237c4cff81d4f3576895_4.png)

![](img/7044923c9cfa237c4cff81d4f3576895_5.png)

![](img/7044923c9cfa237c4cff81d4f3576895_6.png)

![](img/7044923c9cfa237c4cff81d4f3576895_7.png)

![](img/7044923c9cfa237c4cff81d4f3576895_8.png)

![](img/7044923c9cfa237c4cff81d4f3576895_9.png)

![](img/7044923c9cfa237c4cff81d4f3576895_10.png)

![](img/7044923c9cfa237c4cff81d4f3576895_11.png)

And then once you've got those groups split apart， you can apply。

 you can use L apply or S apply to apply a function to those individual groups。



![](img/7044923c9cfa237c4cff81d4f3576895_13.png)

![](img/7044923c9cfa237c4cff81d4f3576895_14.png)

![](img/7044923c9cfa237c4cff81d4f3576895_15.png)

So here this is a simple example similar to what I had before with the T apply example I've simulated a normal 10 normal random variables of mean0。

 10 uniforms and 10 normals with mean 1 and I'm create my factor variable here and now I'm just going to split the vector into three parts because the factor variable has three levels so now you can see when I split the x vector the first I get a list back and the first element is 10 normals the second element is 10 uniforms and the third element which gets a little cut off here is 10 normals again。

😊。

![](img/7044923c9cfa237c4cff81d4f3576895_17.png)

![](img/7044923c9cfa237c4cff81d4f3576895_18.png)

![](img/7044923c9cfa237c4cff81d4f3576895_19.png)

![](img/7044923c9cfa237c4cff81d4f3576895_20.png)

![](img/7044923c9cfa237c4cff81d4f3576895_21.png)

![](img/7044923c9cfa237c4cff81d4f3576895_22.png)

![](img/7044923c9cfa237c4cff81d4f3576895_23.png)

So that's what the split function does。 So now I've got a so split always returns a list back。

 and so if you want to do something with this list， you can use L apply or S apply。



![](img/7044923c9cfa237c4cff81d4f3576895_25.png)

![](img/7044923c9cfa237c4cff81d4f3576895_26.png)

So here， for example， it's common to use the L apply function in conjunction with the split function so the idea is that you split something and then L apply a function over it Now in this case。

 this use of L apply and split is not necessary because you can use the T apply function which will do the exact same thing it's not any more efficient or any worse to do it this way。

 but the T apply function is a little bit more compact。



![](img/7044923c9cfa237c4cff81d4f3576895_28.png)

![](img/7044923c9cfa237c4cff81d4f3576895_29.png)

![](img/7044923c9cfa237c4cff81d4f3576895_30.png)

![](img/7044923c9cfa237c4cff81d4f3576895_31.png)

![](img/7044923c9cfa237c4cff81d4f3576895_32.png)

![](img/7044923c9cfa237c4cff81d4f3576895_33.png)

But the nice thing about the split using the split function is that it can be use to split much more complicated types of objects。

 So for example here I've got a data frame I'm loading the datas package and I'm looking at the air quality data frame from the data sets package see this is the first six rows of of this data frame I think there's about 100 sum rows and the total in this data frame and you see there are measurements on ozone。

 solar radiation， wind and temperature and then the month and then the day within that month and so one thing I might want to do is calculate for example。

 the mean of ozone， solar radiation， wind and temperature in within each month so within each month there's 30 some observations and I want to calculate the mean within each month so how do I do this well what I'd like to do is I'd like to split the data frame into monthly pieces and then once I've split the data frame into separate months I can just calculate the means the column means using either apply or call means。

😊。

![](img/7044923c9cfa237c4cff81d4f3576895_35.png)

![](img/7044923c9cfa237c4cff81d4f3576895_36.png)

![](img/7044923c9cfa237c4cff81d4f3576895_37.png)

![](img/7044923c9cfa237c4cff81d4f3576895_38.png)

![](img/7044923c9cfa237c4cff81d4f3576895_39.png)

![](img/7044923c9cfa237c4cff81d4f3576895_40.png)

![](img/7044923c9cfa237c4cff81d4f3576895_41.png)

![](img/7044923c9cfa237c4cff81d4f3576895_42.png)

![](img/7044923c9cfa237c4cff81d4f3576895_43.png)

![](img/7044923c9cfa237c4cff81d4f3576895_44.png)

![](img/7044923c9cfa237c4cff81d4f3576895_45.png)

![](img/7044923c9cfa237c4cff81d4f3576895_46.png)

On those other variables。

![](img/7044923c9cfa237c4cff81d4f3576895_48.png)

So that's what I've done here what I've done is I've split the air quality data frame and the factor I'm going to use to split is the month variable so the month variable technically speaking in the data frame is not a factor variable but it can be converted into a factor variable because it only takes the values5。

6，78 and 9 because the measurements are only taken in the kind of warmer months of the year so here I've split the air quality variable according to the month variable。

😊。

![](img/7044923c9cfa237c4cff81d4f3576895_50.png)

![](img/7044923c9cfa237c4cff81d4f3576895_51.png)

![](img/7044923c9cfa237c4cff81d4f3576895_52.png)

![](img/7044923c9cfa237c4cff81d4f3576895_53.png)

![](img/7044923c9cfa237c4cff81d4f3576895_54.png)

And then I'm going to apply an anonymous function and the anonymous function here。

 what it does is it takes the column means of just the ozone solar radiation and wind。

 so I'm not going to take the mean at temperature here。

 so I'm just going to take the column means of those three variables for each month each kind of monthly data frame so here you can see the results you can't see them all。

 but you can see most of them can see L applies returning a list back where each element of the list is a vector of length3 which is the mean for ozone and the mean for solar radiation and the mean for wind within that month and so you can see that for most of the months。

 the ozone values NA and that's because when I take the mean of that column and there are missing values in that column and I can't take the mean if there are missing values。

 so the result when I take the mean is that I just get a missing value back。



![](img/7044923c9cfa237c4cff81d4f3576895_56.png)

![](img/7044923c9cfa237c4cff81d4f3576895_57.png)

![](img/7044923c9cfa237c4cff81d4f3576895_58.png)

![](img/7044923c9cfa237c4cff81d4f3576895_59.png)

![](img/7044923c9cfa237c4cff81d4f3576895_60.png)

![](img/7044923c9cfa237c4cff81d4f3576895_61.png)

![](img/7044923c9cfa237c4cff81d4f3576895_62.png)

![](img/7044923c9cfa237c4cff81d4f3576895_63.png)

![](img/7044923c9cfa237c4cff81d4f3576895_64.png)

![](img/7044923c9cfa237c4cff81d4f3576895_65.png)

![](img/7044923c9cfa237c4cff81d4f3576895_66.png)

So one thing I can do is can so before I fix the missing value problem I can also call S apply here and the idea is that S apply instead of returning me a list it will simplify the result because each element of the returned list is a vector of length three they're all the same length so what it'll do is it'll put all these numbers into a matrix where theyre three rows and in this case five columns so here you can see the monthly means for each of the three variables in a much more compact format it's in a matrix instead of a list of course I've still got NAs for a lot of them because of the missing values in the original data。

😊。

![](img/7044923c9cfa237c4cff81d4f3576895_68.png)

![](img/7044923c9cfa237c4cff81d4f3576895_69.png)

![](img/7044923c9cfa237c4cff81d4f3576895_70.png)

![](img/7044923c9cfa237c4cff81d4f3576895_71.png)

![](img/7044923c9cfa237c4cff81d4f3576895_72.png)

![](img/7044923c9cfa237c4cff81d4f3576895_73.png)

![](img/7044923c9cfa237c4cff81d4f3576895_74.png)

So one thing I knew is I'm just going to pass the NA。

rm argument to column means that will remove the missing values from each column before to calculating the mean and that now when I call S apply on the split list I can get the means of the observed values for each of the three variables for each of the five months so split is a very handy function for splitting arbitrary objects according to the levels of a factor and then applying any type of function to those split elements of that list and so here I split a data frame you can split other list can or other kinds of things too。



![](img/7044923c9cfa237c4cff81d4f3576895_76.png)

![](img/7044923c9cfa237c4cff81d4f3576895_77.png)

![](img/7044923c9cfa237c4cff81d4f3576895_78.png)

![](img/7044923c9cfa237c4cff81d4f3576895_79.png)

![](img/7044923c9cfa237c4cff81d4f3576895_80.png)

![](img/7044923c9cfa237c4cff81d4f3576895_81.png)

![](img/7044923c9cfa237c4cff81d4f3576895_82.png)

![](img/7044923c9cfa237c4cff81d4f3576895_83.png)

So the last thing I want to talk about is splitting on more than one level so in the past couple of examples I've only had a single factor variable and I've split whatever the object is a vector or data frame according to the levels of that single factor but you might have more than one factor for example you might have a variable that's's gender so it has male and female and you might have another variable that has for example that's race and say you might want to look at the combination of the levels within those factors and so here I've got F1 which is a factor with two levels and so I've simulated a normal random variable with10 observations I've got a factor with two levels and each repeated five times and then I've got another factor with five levels each repeated two times so these are my kind of two category two group grouping variables here and I want to look at the kind of combination of the two so I can use the interaction function to combine all the levels of the first one with all the levels of the second one and so because。

😊。

![](img/7044923c9cfa237c4cff81d4f3576895_85.png)

![](img/7044923c9cfa237c4cff81d4f3576895_86.png)

![](img/7044923c9cfa237c4cff81d4f3576895_87.png)

![](img/7044923c9cfa237c4cff81d4f3576895_88.png)

![](img/7044923c9cfa237c4cff81d4f3576895_89.png)

![](img/7044923c9cfa237c4cff81d4f3576895_90.png)

![](img/7044923c9cfa237c4cff81d4f3576895_91.png)

![](img/7044923c9cfa237c4cff81d4f3576895_92.png)

![](img/7044923c9cfa237c4cff81d4f3576895_93.png)

![](img/7044923c9cfa237c4cff81d4f3576895_94.png)

![](img/7044923c9cfa237c4cff81d4f3576895_95.png)

![](img/7044923c9cfa237c4cff81d4f3576895_96.png)

There's two levels in the first factor and there's five levels in the second factor and there's the total combination of 10 different levels that you can have when you combine the two together。

 so see when I call the interaction function， I get another factor that kind of concatenates the levels of one with the other and you can see that it prints out that there's a total of 10 levels okay。



![](img/7044923c9cfa237c4cff81d4f3576895_98.png)

![](img/7044923c9cfa237c4cff81d4f3576895_99.png)

![](img/7044923c9cfa237c4cff81d4f3576895_100.png)

![](img/7044923c9cfa237c4cff81d4f3576895_101.png)

So now I can split my numeric vector X according to the two different levels so now one thing when I use the split function。

 I don't have to use the interaction function， I can just pass in a list with the two factors and it will automatically call the interaction function for me and create that 10 level interaction factor so I can just pass it a list of these two factors you can see that it returns me a list with the levels of the 10 different interaction factor levels and then the elements of the numeric vector that are within those 10 levels now of course there aren' although there are 10 levels between the two different factors。

 we don't exactly observe every single combination and so there are some empty levels here and you can see that some of these levels have nothing in them。

 they have zero elements whereas other levels have a number in it。



![](img/7044923c9cfa237c4cff81d4f3576895_103.png)

![](img/7044923c9cfa237c4cff81d4f3576895_104.png)

![](img/7044923c9cfa237c4cff81d4f3576895_105.png)

![](img/7044923c9cfa237c4cff81d4f3576895_106.png)

![](img/7044923c9cfa237c4cff81d4f3576895_107.png)

![](img/7044923c9cfa237c4cff81d4f3576895_108.png)

![](img/7044923c9cfa237c4cff81d4f3576895_109.png)

![](img/7044923c9cfa237c4cff81d4f3576895_110.png)

![](img/7044923c9cfa237c4cff81d4f3576895_111.png)

![](img/7044923c9cfa237c4cff81d4f3576895_112.png)

![](img/7044923c9cfa237c4cff81d4f3576895_113.png)

And so one thing you can do， well first I I could take this list and then L apply or S apply a function over if I wanted to。

 but sometimes it's a little bit handy to not have to keep these empty levels so the split function has an argument called drop and if you specify drop equals true。

 it will drop the empty levels that are created by the splitting and this can be very handy when you're combining multiple different factors if you're only using a single factor then it's not that argument doesn't really do anything because you're just use all the levels but usually but if you have multiple factors。

 then typically you're gonna to have empty levels just because you don't observe every single combination of the two factors so drop equals true will drop those empty levels and then you can you'll be returned the list with only the levels that have observations in them。



![](img/7044923c9cfa237c4cff81d4f3576895_115.png)

![](img/7044923c9cfa237c4cff81d4f3576895_116.png)

![](img/7044923c9cfa237c4cff81d4f3576895_117.png)

![](img/7044923c9cfa237c4cff81d4f3576895_118.png)

![](img/7044923c9cfa237c4cff81d4f3576895_119.png)

![](img/7044923c9cfa237c4cff81d4f3576895_120.png)

![](img/7044923c9cfa237c4cff81d4f3576895_121.png)

![](img/7044923c9cfa237c4cff81d4f3576895_122.png)

![](img/7044923c9cfa237c4cff81d4f3576895_123.png)

![](img/7044923c9cfa237c4cff81d4f3576895_124.png)