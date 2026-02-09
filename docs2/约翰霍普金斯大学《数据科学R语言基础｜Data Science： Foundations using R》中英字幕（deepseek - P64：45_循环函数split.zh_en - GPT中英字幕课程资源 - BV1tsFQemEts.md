# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P64：45_循环函数split.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

T apply。Is useful because it splits up a vector into little pieces and it applies a summary statistic or function to those little pieces。

 and then after it applies that function， it kind of brings the pieces back together again。

 so split is not a loop function， but it's a very handy function that can be used in conjunction with functions like L apply or S apply and so I just want to mention it here。

 So split takes a vector， So it's kind of like t apply。

 but but it's like t apply but without applying the summary statistics。

 So what it does is it takes a vector or an object X and it takes a factor variable F which again identifies levels of a group and then it splits the object X into the number of groups that are identified in factor F。

 So for example， if F has three levels identifying three groups。

 then the split function will split X into three groups。😊。



![](img/dc7c6e2760b4fdbf84e1da0205801126_1.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_2.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_3.png)

And then once you've got those groups split apart， you can apply。

 you can use L apply or S apply to apply a function to those individual groups。



![](img/dc7c6e2760b4fdbf84e1da0205801126_5.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_6.png)

So here this is a simple example similar to what I had before with the T apply example I've simulated a normal 10 normal random variables of mean0。

 10 uniforms and 10 normals with mean 1 and I'm create my factor variable here and now I'm just going to split the vector into three parts because the factor variable has three levels so now you can see when I split the x vector。

 the first I get a list back and the first element is 10 normals the second element is 10 uniforms and the third element which gets a little cut off here is 10 normals again。

😊，So that's what the split function does。 So now I've got so split always returns a list back。

 and so if you want to do something with this list， you can use L apply or S apply。



![](img/dc7c6e2760b4fdbf84e1da0205801126_8.png)

So here， for example， it's common to use the L apply function in conjunction with the split function so the idea is that you split something that L apply function over it Now in this case this use of L apply and split is not necessary because you can use the T apply function which will do the exact same thing it's not any more efficient or any worse to do it this way。

 but the T apply function is a little bit more compact。



![](img/dc7c6e2760b4fdbf84e1da0205801126_10.png)

But the nice thing about the split using the split function is that it can be use to split much more complicated types of objects。

 So for example here I've got a data frame I'm loading the datas package I'm looking at the air quality data frame from the data sets package you can see this is the first six rows of this data frame I think there's about 100 some rows and the total in this data frame and you see there are measurements on ozone。

 solar radiation wind and temperature and then the month and then the day within that month and so one thing I might want to do is calculate for example。

 the mean of ozone， solar radiation， wind and temperature in within each month so within each month there's 30 some observations and I want to calculate the mean within each month so how do I do this Well what I'd like to do is I'd like to split the data frame into monthly pieces and then once I've split the data frame into separate months I can just calculate the means the column means using either apply or call means。

😊，On those other variables。

![](img/dc7c6e2760b4fdbf84e1da0205801126_12.png)

So that's what I've done here what I've done is I've split the air quality data frame and the factor I'm going to use to split is the month variable so the month variable technically speaking in the data frame is not a factor variable but it can be converted into a factor variable because it only takes the values5。

6，78 and 9 because the measurements are only taken in the kind of warmer months of the year so here I've split the air quality variable according to the month variable。

😊，And then I'm going to apply an anonymous function and the anonymous function here what it does is it takes the column means of just the ozone solar radiation and wind。

 so I'm not going to take the mean at temperature here。

 so I'm just going to take the column means of those three variables for each month each kind of monthly data frame so here you can see the results you can't see them all but you can see most of them you can see L applies returning a list back where each element of the list is a vector of length3 which is the mean for ozone and the mean for solar radiation and the mean for wind within that month and so you can see that for most of the months the ozone values NA。

 and that's because when I take the mean of that column and there are missing values in that column and I can't take the mean if there are missing values the result when I take the mean is that I just get a missing value back。



![](img/dc7c6e2760b4fdbf84e1da0205801126_14.png)

So one thing I can do is can so before I fix the missing value problem I can also call S apply here and the idea is that S apply instead of returning me a list it will simplify the result because each element of the returned list is a vector of length three they're all the same length so what it'll do is it'll put all these numbers into a matrix where theyre three rows and in this case five columns so here you can see the monthly means for each of the three variables in a much more compact format it's in a matrix instead of a list of course I've still got NAs for a lot of them because of the missing values in the original data。

So one thing I can knew is I'm just going to pass the NA。

rm argument to column means that will remove the missing values from each column before to calculating the mean and that now when I call S apply on the split list I can get the means of the observed values for each of the three variables for each of the five months so split is a very handy function for splitting arbitrary objects according to the levels of a factor and then applying any type of function to those split elements of that list and so here I split a data frame you can split other list can or other kinds of things too。



![](img/dc7c6e2760b4fdbf84e1da0205801126_16.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_17.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_18.png)

So the last thing I want to talk about is splitting on more than one level so in the past couple of examples I've only had a single factor variable and I've split whatever the object is a vector or data frame according to the levels of that single factor but you might have more than one factor for example you might have a variable that's that's gender so it has male and female and you might have another variable that has for example that's race and say you might want to look at the combination of the levels within those factors and so here I've got F1 which is a factor with two levels and so I've simulated a normal random variable with10 observations I've got a factor with two levels and each repeated five times and then I've got another factor with five levels each repeated two times so these are my kind of two category two group grouping variables here and I want to look at the kind of combination of the two so I can use the interaction function to combine all the levels of the first one with all the levels of the second one and so because。

😊。

![](img/dc7c6e2760b4fdbf84e1da0205801126_20.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_21.png)

There's two levels in the first factor and there's five levels in the second factor there's the total combination of 10 different levels that you can have when you combine the two together。

 so see when I call the interaction function， I get another factor that kind of concatenateates the levels of one with the other and you can see that it prints out that there's a total of 10 levels okay。



![](img/dc7c6e2760b4fdbf84e1da0205801126_23.png)

So now I can split my numeric vector X according to the two different levels so now one thing when I use the split function。

 I don't have to use the interaction function， I can just pass at a list with the two factors and it will automatically call the interaction function for me and create that 10 level interaction factor so I can just pass it a list of these two factors you can see that it returns me a list with the levels of the 10 different interaction factor levels and then the elements of the numeric vector that are within those 10 levels now of course there aren' although there are 10 levels between the two different factors。

 we don't exactly observe every single combination and so there are some empty levels here and you can see that some of these levels have nothing in them they have zero elements whereas other levels have a number in it。



![](img/dc7c6e2760b4fdbf84e1da0205801126_25.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_26.png)

And so one thing you can do， well first I could take this list and then L apply or S apply a function over it if I wanted to。

 but sometimes it's a little bit handy to not have to keep these empty levels so the split function has an argument called drop and if you specify drop equals true。

 it will drop the empty levels that are created by the splitting and this can be very handy when you're combining multiple different factors if you're only using a single factor。

 then it's not that argument doesn't really do anything because you're just use all the levels but usually but if you have multiple factors。

 then typically you're gonna to have empty levels just because you don't observe every single combination of the two factors so drop equals true will drop those empty levels and then you can have you'll be returned the list with only the levels that have observations in them。



![](img/dc7c6e2760b4fdbf84e1da0205801126_28.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_29.png)

![](img/dc7c6e2760b4fdbf84e1da0205801126_30.png)