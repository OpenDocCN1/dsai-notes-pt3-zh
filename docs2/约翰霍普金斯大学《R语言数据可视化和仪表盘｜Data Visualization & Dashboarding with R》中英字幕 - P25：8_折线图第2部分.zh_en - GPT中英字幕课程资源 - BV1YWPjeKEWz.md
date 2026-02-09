# 约翰霍普金斯大学《R语言数据可视化和仪表盘｜Data Visualization & Dashboarding with R》中英字幕 - P25：8_折线图第2部分.zh_en - GPT中英字幕课程资源 - BV1YWPjeKEWz

Now that we've toyed around with line charts with made up data。

Let's apply these skills to imported data。Again， continuing to work with the same R code file that we did for the last video。

One of the big questions in American political science in the last 20 or 25 years has been whether the Republican and Democratic parties are getting increasingly polarized or extreme。

With Republicans becoming more conservative and Democrats becoming more liberal。

Political scientists have come up with a way of measuring how conservative and liberal members of the U。

S。 Congress are based on their voting records。The name for this doesn't really matter。

 but it's called D DW nomininate score， and it's in the Volden and WiseM data set on legislative effectiveness in a column called DW No1。

With this measure， a lower score means that the member of Congress is more liberal。

 and a higher score means that the member of Congress is more conservative。

So one way to potentially assess whether American political parties had become more extreme over time would be to measure the average or mean ideology of members of the two parties across time。

If the distance is increasing， we might be able to interpret this as greater political polarization。

Follow along with me now as we assess this through using a visualization。

I start by loading the Vololden and Wiseman legislative effectiveness data into R。

And then for ease of interpretation， I'm going to recode the dim variable from a 10 indicator variable to make it read as Democrat or Republican。

Now I'm going to do a piping command that will sort and summarize this data。

 saving it to the object fig data。I start with the data source。

Tell R to group that by a Congress and party， then after I've grouped the data。

 I summarize the DW Nom1 ideology score on the basis of those groupings by calculating the mean。

Ignoorring missing data for these purposes。Again， if you need to go back and take a few minutes to untangle that data R command。

 go ahead and do it to make sure you understand all the different steps and what the final table really looks like。

What it means。So， if we。Look at the Fig data object after we've done this wrangling。

 we have an object with years， an ideology score and a party。

So we have the average ideology for Democrats and Republicans for all of the different years。

With the data prepared， we're ready to feed all that into a GGpl command that looks similar to what we've done before with the stock price example。

The data is the summary data set I created， the aesthetics are x for years on the x axis。

And y for the mean ideology score on the y axis。Grouped to draw two different lines。

And then with color， two color lines on the basis of the values in the party column。

We then add the G online function and we can manually control the colors using scale color Manual。

This is all review from what we've done in previous videos again。

 it's exactly the same thing just with different underlying data。

What you see in this figure is that there has been some moving a apart of the parties from Congress to Congress over time。

And this suggests greater partisan polarization between the two parties。

I should say that there are some political scientists out there that would take issue with the way I'm interpreting the data here。

 but just as an example for the purpose of teaching about data visualization。

 this gives you a good workout in making a line plot with original data。

