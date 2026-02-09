# 约翰霍普金斯大学《R语言数据可视化和仪表盘｜Data Visualization & Dashboarding with R》中英字幕 - P13：12_分组和汇总数据.zh_en - GPT中英字幕课程资源 - BV1YWPjeKEWz

So far we have imported data with a tidy verse， filtered rows and selected columns。

 recoded data and renamed columns， and we've calculated new columns in our data。

A few more very important commands in the tidyverse for data wrangling are arrange。

 group by and summarize。A range can be useful if you're trying to whip up quick tables。

Using the tidyverse and arranges basically a fancy version of sort from the base R package。

With Ar range， you can change the order of the rows in a data set based on the values and one or more of the columns。

So for example， in this sample of data that we've been working with， the CCES data。

If I wanted to sort the survey respondents first by gender and then by seven point prior identification。

 I could use CCES pipes to arrange。Gender and then PID7 as the two arguments in the arranged function。

And of course， you could save your rearrange Tbble or data frame to a new object if you wanted to。

And to sort descending rather than ascending， you just put the variable that you want to sort by inside the descending commander。

 DESC。In quotation in parentheses。It's also sometimes useful to group data based on the values in some column。

And grouping doesn't change the order of the data， but it does change how the Tple will interact with other functions in the tidyverse。

You set up groups in a tablebble with the group by function。

 specifying the groups and the arguments for the function。Once you group data。

 you can see what the groups and the data are specified as if you look at the object created by the group by function。

And if you want to wipe out the groupings that you set， you use ungroup。

Group by is not really useful by itself， but it is useful in conjunction with other R functions in the tidyverse。

It's especially useful if you combine it with summarize， for instance。Summarizes used to。

 as the tidyverse documentation would describe， reduce the values in your table down to a single summary value。

And this means that you can generate summary statistics of columns in your data， things like means。

 medians， standard deviations， and so forth。What summarizemar does is create a new data frame and you specify different summary statistics for each column of this new data frame that you're creating。

This is a lot like the data frame command we saw earlier。

 but you're actually creating like a summary value for each of those。

Each of the ways that you specify that。First， in the summarize function。

 you specify the Tbble or the data frame that you're creating summaries for。

 and then you create the name of the summary。And you use an R function that creates some kind of summary statistic for that column。

So here I'm creating a summary table that includes the mean PID7 value for all the rows in the original Tbble and the mean response to the family income question。

And if you group your data first using the group by command and then you use summarize。

 the summarize function will create these summary statistics by group。

Obviously this can be kind of complex and there are lots of opportunities to make mistakes。

 so you want to make sure that you're practicing with these。

 looking at the cheat sheet and referring to the reference materials。Again。

 I haven't shown you anywhere close to everything that you can do to manipulate and transform data in the tidyverse。

 but you can take this as a starting point and use your meta learning skills to go out and do some self- learning at this point。

 trying out new functions and working with data。