# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p40 P40 05_整洁数据集的特征 -BV1z86nB9EGz_p40-

![](img/ee0a56716ef748b7cb32065a768f6255_0.png)

In this video we will focus on characteristics of a tidy data set Now a tidy data is one that is easy to work with。

We'll look at two different data sets and evaluate how tidy each of them are。

 and hopefully that comparison will help you to better appreciate the importance of tidy dataset sets。

 but you really won't come to fully appreciate them until you start working with data sets in Python。

So let's start by looking at a salary data set。 So here in my Python environment in Jupiter labb。

You can see I've got this data set right here。And across the top， we have columns。

And then we've got these rows here。Now， the first characteristic of a tidy data set is that it should have a data dictionary。



![](img/ee0a56716ef748b7cb32065a768f6255_2.png)

So this data set may not make a whole lot of sense initially if you spent some time reading through the headers。

 you could probably infer that these are survey results about how much people make。



![](img/ee0a56716ef748b7cb32065a768f6255_4.png)

But oftentimes， a data dictionary can be found from the location where that data is stored。

 So this particular data set I found on this website that's an article。

 how much money do you make and embedded in this article is a survey and in here you can see the questions how old are you What industry do you work in。

 job title。Your annual salary， and so on。So that makes it a lot easier to understand now when we look at the data。

 what we're looking at here because I've got a timestamp first of all。

 so it keeps track of when they either started or finish that survey。

And then the questions for each of those。Alright， so that's really helpful that we have that。

 It's not like a formal data dictionary， but at least it gives us some context for how to interpret this data and one of the key things that you should recognize from a data dictionary is what each row of the data set represents and now that we know that this comes from a survey we positive。

We can probably have a really good idea that each row is what one person responded to all the questions in here。

 Okay， so that brings us to the second characteristic of a tidy dataset set。

 which is that each row is an observation and each column is a characteristic or a feature of that observation。



![](img/ee0a56716ef748b7cb32065a768f6255_6.png)

![](img/ee0a56716ef748b7cb32065a768f6255_7.png)

So in other words， instead of having each column as an observation or one person who responded。

 we have those in the rows。 Okay， so each row is a person who responded here。

 and then each column is a characteristic。All right， so that's what we mean by observations。



![](img/ee0a56716ef748b7cb32065a768f6255_9.png)

All right， the third characteristic of a tidy data set is that there should be unique names for the rows and columns。



![](img/ee0a56716ef748b7cb32065a768f6255_11.png)

So when we read a data set into Python and create a panda's data frame。

 Padas will automatically assign numeric values to the rows if you're reading in data from like a CSV file or an Excel file。

 or you change the argument of how you read in the data。

 So we can see that the first row is labeled as0， the next row is 1 and so on。



![](img/ee0a56716ef748b7cb32065a768f6255_13.png)

![](img/ee0a56716ef748b7cb32065a768f6255_14.png)

And importantly， each of these row names are unique， so we're not going to see two zeros in here。

 we shouldn't see that。And similarly， each column should be unique。

 We shouldn't see any columns that have the same name as any other column in there。 Okay。

 and that brings us to the fourth characteristic of a tidy dataset set。

 which is that we should have concise and consistent column names。 Now。

 these column names are not concise。 For instance， we look at this question about what is your annual salary。

 And it is a long name there。 And the problem with that is that we often have to refer to columns by name。

 And we don't want to have to type all of that out。



![](img/ee0a56716ef748b7cb32065a768f6255_16.png)

![](img/ee0a56716ef748b7cb32065a768f6255_17.png)

So I've cleaned up this data set just a little bit。And change the column names。

 And this is much easier to look at。 So you can see we've got time age industry， job title。

 job context。 And then here's the annual salary。

![](img/ee0a56716ef748b7cb32065a768f6255_19.png)

All right， so these are much more concise。 Now， what about consistency， Well。

 you'll notice that I've removed all of the punctuation and spaces。



![](img/ee0a56716ef748b7cb32065a768f6255_21.png)

![](img/ee0a56716ef748b7cb32065a768f6255_22.png)

The only punctuation that I have in here is an underscore which represents the spaces。



![](img/ee0a56716ef748b7cb32065a768f6255_24.png)

Also， everything is lowercase。 So this particular convention for naming columns is called snake case。



![](img/ee0a56716ef748b7cb32065a768f6255_26.png)

![](img/ee0a56716ef748b7cb32065a768f6255_27.png)

And it's much easier to refer to columns by name when there are no spaces or punctuation in them。

 We can have that。 It's just harder to use them。 All right。

 the fifth characteristic of tidy data is that columns should have a consistent data type and pattern。

 Every observation in a column should be either text or a numeric value or a date time value or something else。



![](img/ee0a56716ef748b7cb32065a768f6255_29.png)

![](img/ee0a56716ef748b7cb32065a768f6255_30.png)

So if we look at this first column time， we would like to see all of these date time stamps be recorded in the same way。

 so we've got year month， day， an hour minute second and even millisecond there。



![](img/ee0a56716ef748b7cb32065a768f6255_32.png)

![](img/ee0a56716ef748b7cb32065a768f6255_33.png)

We don't want to see some rows that have month day year and then node time stamp in there。

 So this is nice。 This is tidy。 It's consistent in that regard。



![](img/ee0a56716ef748b7cb32065a768f6255_35.png)

![](img/ee0a56716ef748b7cb32065a768f6255_36.png)

Age is a bucket。 We don't want to see any specific ages。

 We want all these to be either an age range or a specific age。 Okay， so we want consistency there。



![](img/ee0a56716ef748b7cb32065a768f6255_38.png)

So we've got a date time type here， anything that's not date time or numeric like the annual salary and bonuses column。



![](img/ee0a56716ef748b7cb32065a768f6255_40.png)

![](img/ee0a56716ef748b7cb32065a768f6255_41.png)

Means it must be a character string。 And in pandas data frames， that's an object data type。

 All right， So we mostly have object data types in here as we look at these。



![](img/ee0a56716ef748b7cb32065a768f6255_43.png)

Now you'll see some of these NNs， and this brings us to the sixth characteristic of tidy data。

 which is that missing values should be labeled as missing。 We don't want to just leave them blank。

 and pandas will automatically do that。

![](img/ee0a56716ef748b7cb32065a768f6255_45.png)

![](img/ee0a56716ef748b7cb32065a768f6255_46.png)

So all these NNs mean that it wasn't recorded， the person didn't reply。

Or when you were cleaning up the data for whatever reason。

 it couldn't clean it up in the way you specified it。 And so it just said， hey。

 I'm going to replace this with a missing value。 Allright， so anyway。

 those are the six characteristics of a tidy data frame。

 Let's look at another example of a data set and evaluate the extent to which it is tidy or untidy。

So we're going to look at public sector debt data。 And here is a preview of what this data looks like。

 And you can see I've got a country name， country code series name， series code。

 and then these years and quarters in here。 All right， This is going to be harder to infer。

 So let's go ahead and look at where I got this data。 I got this from the World Bank's website。

 And this is the quarterly public sector debt data。I got it for every country that it has。

I got six series in here。 I've got their total debt as a percent of GDP and in US dollars， then。

Whoops， actually， these are domestic creditors and then just their total debt。

Percent of GDP U dollars and then to the external creditors， percent of GDP and US dollars。All right。

 so different ways of measuring their public sector debt。

 And then I got it for all the time that was available。And then you can see this preview of the data。

 Now， as we go ahead and click on。One of these series here， the one of these six series。

 we can read in more detail what each of these series are， and this is very helpful。

 This helps us understand what the values represent， the numbers represent。



![](img/ee0a56716ef748b7cb32065a768f6255_48.png)

Alright， so that's part of the data dictionary。 There's actually also a metadata part in here。

 And this gives us even。

![](img/ee0a56716ef748b7cb32065a768f6255_50.png)

Greater explanation of what we're looking at in here。 Okay。

 so this has a nice formal data dictionary。 It may not be in a single file。

 but it does have the pieces of information that we need to help us interpret what this data is。

 And then you can download this in different formats。



![](img/ee0a56716ef748b7cb32065a768f6255_52.png)

All right， So that's what I did。 And knowing that now helps us better appreciate what we're looking at here。

 So this row that we're looking at right here is for the United Kingdom。

 and we've got a country code of GBR。 The series name here。

 So this is to external creditors in US dollars。 And there's a code that matches up with that。

 And then we've got all these years。 Okay so this is in large values。 So is this right here。

 But we get to percent of GDP。 And we've got these numbers here that represent percentages。



![](img/ee0a56716ef748b7cb32065a768f6255_54.png)

![](img/ee0a56716ef748b7cb32065a768f6255_55.png)

![](img/ee0a56716ef748b7cb32065a768f6255_56.png)

Okay， so let's think about how tidy this data set is。 Well， the first characteristic。

 it does have a data dictionary。 How about the second characteristic rowsor observations and columns are features。

 Well we look at each row here and we can see that a row represents a single country。

For a particular way of measuring public sector debt。

And then we've got actually a bunch of observations here。

So we've got their public sector debt to external creditors for the first quarter of 1995 then the second quarter of 1995。

Now， maybe for some analyses， this row right here would be an observation。

 Maybe some machine learning algorithms you would want it like that。

 There's another way that we could look at this data set if we reshape it。 This， I would say。

 would be even tiier because now each row， you can see this top row here。

 This is for the United Kingdom。 We've got that percent of GDP。

 We've got the series code all that's the same so far。

 but now we've got the period label in a separate column and the value in a separate column。

 So there's way fewer columns here。 There's only six columns of data。

 rather than 120 or something like that123 columns。Okay， so I would say this is more tidy。

 Most of the time this would be more favorable to work with。 All right， well。

 let's go to the third characteristic。 unique names for rows and columns。 Well。

 we do have unique names for rows。 And again， these are just numbered from 0 up to the number of rows we have。

 And we're looking at specific rows here，620 through 625。 And we've got 123 columns。

 And you can see that。We've got unique names for each of those columns， so it's tidy in that regard。

What about having concise and consistent column names， Well。

 these names are concise and they're consistent， but they're not tidy in the sense that they still have spaces and a little bit of punctuation in them with those brackets in there。

So to clean this up a little bit， I removed the spaces and those brackets。

 And so here I have a different naming convention。 And this is called camel case。

 where everything's lowercase， except for the first letter of。



![](img/ee0a56716ef748b7cb32065a768f6255_58.png)

Every word after the first word。 So you can see country name here， there's no spaces。

 but that capital N represents a new word。 Okay， so Im。

 I'm being consistent here not mixing up like snake case with camel case。

 So this is more tidy because we've got more concise column names that are no spaces in it or punctuation。



![](img/ee0a56716ef748b7cb32065a768f6255_60.png)

All right， so okay， this is more tidy now。 And then the fifth characteristic is that columns should have a consistent data type and pattern。

 Well， we can see that we've got consistency in the country codes here and in the country names。

 one thing may be to go back to the previous data set。 the salary data。

 the country in here is inconsistent in how it's recorded。 So we have USA United States and USA。

 at least three different ways for representing the same country。

 so that's another way in which that previous data set is untidy。

 But this public sector debt data is consistent all throughout。

 So it gets better marks in consistency of data types in every column。

 Then the missing data should be identified and we can see that we do have missing values here And actually when we first read in the data before converting these columns to numeric values。

 you can see that they actually labeled missing values with two dots in there。

 So when we convert them to numeric values， it put。



![](img/ee0a56716ef748b7cb32065a768f6255_62.png)

![](img/ee0a56716ef748b7cb32065a768f6255_63.png)

![](img/ee0a56716ef748b7cb32065a768f6255_64.png)

![](img/ee0a56716ef748b7cb32065a768f6255_65.png)

![](img/ee0a56716ef748b7cb32065a768f6255_66.png)

![](img/ee0a56716ef748b7cb32065a768f6255_67.png)

![](img/ee0a56716ef748b7cb32065a768f6255_68.png)

N ends in there。 So those are six characteristics of tidy data frames。

 and we looked at two different data sets and evaluated how tidy they are。

 Hopefully that's helpful for you。 Like I said， you'll come to appreciate these characteristics more as you work with data frames in Python。

 and in later lessons， we'll talk about commands to convert untidy data to tidy data。



![](img/ee0a56716ef748b7cb32065a768f6255_70.png)