# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p163 07_03_04_构建短期租金预测模型.zh_en -BV1mS421X7yw_p163-

![](img/16628451bb7b749f79185cc54ff72378_0.png)

Yeah。Congratulations on last week's successful use of SQL to extract property location and pricing data for further analysis。

By getting the data out of the database for yourself。

You've demonstrated competency in one of the key business data analyst skills。

The next two weeks focus on applying Microsoft Excel to these data for analysis， forecasting。

 optimization， and financial modeling。All the Excel methods that you will need are explained in detail in written documents that accompany the videos and the guide and template spreadsheets。

I recommend reading the document on Excel Best practices before you begin working with the six template spreadsheets。

If you set up your formulas in the recommended way。

 it will be much easier to add new steps and to correct any mistakes as you go along。The first week。

 you will apply techniques from Cose1 and Cose 2 to create a predictive model from the data and use that model to set optimum short term rental rates for watershed properties。

The larger goal is to determine whether converting to short term rentals makes sense as a business for watershed to enter。

We will approach this question more directly in the second week。

By evaluating how much additional profit watershed could achieve in the first full year after conversion is complete。

Why we focus on the profits rather than revenues or cash flow or some other metric for success was explained in the week one video what watersheds owners care about。

Back in the business metrics for data driven companies course。

 we learned about hotel room revenue optimization。We saw that all else being equal。

 higher rental rates lead to lower occupancy rates。At that time。

 we did not explore any mathematical methods for representing this relationship。

Or for finding the optimal combination of rent and occupancy rates。Although in course one。

 we did touch on use of the Microsoft solver tool for optimization。

Now we return to this problem in the context of Watershed's desire to maximize potential profits。

To maximize profits， we first maximize expected rental revenues。

The goal is not to maximize rental rates or occupancy rates， but the product of the two。

We call both rental rates and occupancy rates optimized when their product is at a maximum。

The concept of optimization and how it is done in solver is explained in detail in videos and in a guide spreadsheet。

Before you can optimize rental revenues， you need to have a mathematical formula that relates a rental rate to an expected occupancy rate。

We have pairs of 244 rental rates with occupancy rates in the comparablearables data。

And the plan is to use a simple best fit line to model this relationship。However。

 you will find that using the raw dollar rents。And trying to relate them to occupancy rates does not work for forecasting。

In order to develop a best fit line that has a high enough predictive value to actually be useful for forecasting。

We need to put the rental rate data through a transformation called normalization。Normalization。

 in this case converts raw dollar rents into something we call percentile rents。

Normalization is an important and widely used technique that， however。

 has not been covered earlier in the specialization。

 we introduce and explain it here in its own videos and guide spreadsheet。

After you've established the strong linear relationship， the best fitt line formula。

Between normalized rents and occupancy rates， you will apply the solver optimization method to generate optimum rents for a sample of the watershed properties。

Don't worry， you don't need to run solver 244 times。

Once you have demonstrated that you know how to get the right answers in solver。

 we will provide you in the second week of the Excel portion of the capstone。

With a shortcut to generate quickly and easily the maximum rental revenues for the rest of the watershed properties。

Good luck。

![](img/16628451bb7b749f79185cc54ff72378_2.png)