# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P21：20_合并数据.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

Sometimes you'll load in more than one dataset set into R and you'll want to be able to merge the dataset sets together。

 And usually what you'll want to do is match those data sets based on an I D。

 This is very similar to the idea of having a linked set of tables in a database like Mysql。



![](img/7df318c525d97f62966d16e47bb68d9d_1.png)

So what we're going to be talking about here is data from this peer review experiment。

 and so this is an experiment that I was actually an author on。

 and so we collected data on people who submitted answers to questions like SAT questions and then people who reviewed those answers and tried to decide whether they were right or not。

 and this was a model system for how the peer review system works in scientific studies。



![](img/7df318c525d97f62966d16e47bb68d9d_3.png)

![](img/7df318c525d97f62966d16e47bb68d9d_4.png)

![](img/7df318c525d97f62966d16e47bb68d9d_5.png)

![](img/7df318c525d97f62966d16e47bb68d9d_6.png)

So what we can do is download the peer review data。

 the peer review data is actually available from my Dropbox account。

 and so we can get the reviews and the solutions from this data set and so we download these two files and so they're two data frames one corresponding to all the SAT problems that were solved by people in the study and one by all the people corresponding to all the times that those problems were reviewed。

 so we read them both into two data frame so we can look at the reviews data frame which has these variable names。

So you can see one of the variable names for this data frame is solution ID。

 and that corresponds to the ID that appears in the solutions dataset set。

 You can see the solutions data also has a problem ID and a subject ID those will be matched to other datasets that we're not going to be talking about in this particular example。

So the first thing that we might want to use is the merge command to merge these datasets together So again。

 if we look at the names of these two variables， we can use the solution ID in the you use variable or data and the ID variable in the solutions dataset to merge these datasets together So the important parameters to merge are X and y so those are two data frames。

 and then you can use either by or by dot x by dot y to tell merge which of the columns it should merge by by default it merges by all of the columns that have the common name So for example。

 in this data it would try to merge by ID， start， stop。

 time left and so forth because those variables also appear in solutions because ID is here， start。

 stop and time left even though those variables might not necessarily mean the same thing。



![](img/7df318c525d97f62966d16e47bb68d9d_8.png)

![](img/7df318c525d97f62966d16e47bb68d9d_9.png)

![](img/7df318c525d97f62966d16e47bb68d9d_10.png)

![](img/7df318c525d97f62966d16e47bb68d9d_11.png)

![](img/7df318c525d97f62966d16e47bb68d9d_12.png)

![](img/7df318c525d97f62966d16e47bb68d9d_13.png)

![](img/7df318c525d97f62966d16e47bb68d9d_14.png)

![](img/7df318c525d97f62966d16e47bb68d9d_15.png)

![](img/7df318c525d97f62966d16e47bb68d9d_16.png)

![](img/7df318c525d97f62966d16e47bb68d9d_17.png)

![](img/7df318c525d97f62966d16e47bb68d9d_18.png)

So what we're going to do instead is tell merge which are the variables it should merge on So it merges the reviews and the solutions for the X data frame in this case is the reviews data frame we're going to merge on the solution ID and in the solutions data frame we're just going merge based on the ID here I'm going to tell it all equals true。

 which means if there's a value that appears in one but not in the other。

 it should include another row but with NA values for the missing values that don't appear in the other data frame and so we can look at the top of this new merge data set and you can see now that the solution ID is now taken the place of the ID and it's ordered by that variable and then this ID variable is the ID variable that's left over in the reviews data so this is the reviews main ID that appears here in this data so you can see that this is。

ge the two data sets together based on their common ID so that then you can analyze it as one data。

The default again is to merge based on all column common column names so if you do an intersection of the names of the solutions data frame and the names of the reviews data frame。

 you get these four variables and so if you try to merge without telling it what to merge on the basis of it will try to merge on the basis of all those four variables so what ends up happening is the ID variable will match up sometimes between the two data sets but the start and the stop times won't necessarily match up so what it ends up doing is it just creates a data frame that's larger that applies multiple rows one for each row of reviews and each row of solutions。



![](img/7df318c525d97f62966d16e47bb68d9d_20.png)

![](img/7df318c525d97f62966d16e47bb68d9d_21.png)

![](img/7df318c525d97f62966d16e47bb68d9d_22.png)

![](img/7df318c525d97f62966d16e47bb68d9d_23.png)

![](img/7df318c525d97f62966d16e47bb68d9d_24.png)

![](img/7df318c525d97f62966d16e47bb68d9d_25.png)

![](img/7df318c525d97f62966d16e47bb68d9d_26.png)

![](img/7df318c525d97f62966d16e47bb68d9d_27.png)

You can also use join in the plier package to join dataset sets together it's a bit faster than merge but it' a bit less full featured in other words in other words it。



![](img/7df318c525d97f62966d16e47bb68d9d_29.png)

![](img/7df318c525d97f62966d16e47bb68d9d_30.png)

Only can merge on the basis of common road or common namess between the two data sets。



![](img/7df318c525d97f62966d16e47bb68d9d_32.png)

And so you couldn't merge the two dataset sets we talked about just a minute ago because we need to merge by solution ID and ID and join will only merge on the basis of ID。

 even though it's faster。 So here's an example I created two made up data frames with a common I identifier。

 but I've sampled them So they're in different orders。

 And so what I can do is I can join the two data sets together。 It will join them by ID。

 And then I can use the arrange command to arrange them in。



![](img/7df318c525d97f62966d16e47bb68d9d_34.png)

![](img/7df318c525d97f62966d16e47bb68d9d_35.png)

![](img/7df318c525d97f62966d16e47bb68d9d_36.png)

![](img/7df318c525d97f62966d16e47bb68d9d_37.png)

![](img/7df318c525d97f62966d16e47bb68d9d_38.png)

![](img/7df318c525d97f62966d16e47bb68d9d_39.png)

![](img/7df318c525d97f62966d16e47bb68d9d_40.png)

Increasing order by ID and so you see I've arranged the two dataset sets together in that way。

 you can play around with these commands to see how you can join dataset sets together。



![](img/7df318c525d97f62966d16e47bb68d9d_42.png)

The nice thing about thelier package and the reason why I bring it up is that if you have multiple data frames。

 it's relatively challenging to do it with the merge command， but if they have a common ID。

 it's very straightforward to do it with the joinin All command。



![](img/7df318c525d97f62966d16e47bb68d9d_44.png)

![](img/7df318c525d97f62966d16e47bb68d9d_45.png)

![](img/7df318c525d97f62966d16e47bb68d9d_46.png)

So what I do is I create my three data frames in this case and I put them all on a list so one big data list of data frames。

 so it's a data frame list with three data frames in it。

 and then I just use the command join all which merges all of the different datas on the basis of the common variables in this case。

 ID。

![](img/7df318c525d97f62966d16e47bb68d9d_48.png)

![](img/7df318c525d97f62966d16e47bb68d9d_49.png)

![](img/7df318c525d97f62966d16e47bb68d9d_50.png)

![](img/7df318c525d97f62966d16e47bb68d9d_51.png)

So that's a nice way to merge together multiple data sets very quickly the R data merg page is very good as is the plier page for merging datas together before you start doing this intensively it's worth paying attention to whether you're performing different kinds of joins。

 whether you're doing sort of left joins or right joins and the best way to learn more about that is to go read about joins in databases。

 for example， here this is the information about joining for SQL database joins。😊。



![](img/7df318c525d97f62966d16e47bb68d9d_53.png)

![](img/7df318c525d97f62966d16e47bb68d9d_54.png)

![](img/7df318c525d97f62966d16e47bb68d9d_55.png)

![](img/7df318c525d97f62966d16e47bb68d9d_56.png)

![](img/7df318c525d97f62966d16e47bb68d9d_57.png)