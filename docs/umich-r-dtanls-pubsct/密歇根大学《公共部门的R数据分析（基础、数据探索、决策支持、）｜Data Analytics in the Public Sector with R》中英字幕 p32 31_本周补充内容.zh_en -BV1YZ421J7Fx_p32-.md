# 密歇根大学《公共部门的R数据分析（基础、数据探索、决策支持、）｜Data Analytics in the Public Sector with R》中英字幕 p32 31_本周补充内容.zh_en -BV1YZ421J7Fx_p32-

![](img/dc3bad5de5e43c27a5aae074b1b729de_0.png)

![](img/dc3bad5de5e43c27a5aae074b1b729de_1.png)

All right， my friends， I need to say one more thing to you about rates。

We've been talking a lot in our units on survey data and population data about many different kinds of rates。

And it's always important to compare rates in data rather than raw numbers when looking at differences across geography。

 across different subpopulations and across time， because the number of people in populations can vary and this of course influences the number of events or occurrences。

 so we need to when doing data analytics think about rates。A rate。

 which always has a numerator and a denominator， gives you a sense of the incident or occurrence of something that's in the numerator relative to a clear number of people in the population that's in the denominator。

Quick examples， the unemployment rate。This is the number of people who are not employed。

 divided by the number of people in the labor force。What's the labor force。

 this is defined as people 16 and older who are actively seeking work。

Then the numerator is divided by the denominator。And multiplied by 100。

 and this rate is actually a percentage。For example， the current unemployment rate in Spain is 15。

3% that is 15。3% of the available labor force。Looking for work does not have a job。

Many things that governments care about are relatively rare events and thus analyzing them as percentages present some challenges for interpretation because you'd be looking at percentages under 1% or 2%。

 they're hard to interpret and compare。So some rates include multiplying a resulting percentage by 1000。

 10，000 or even 100，000 to get a more interpretal number rather than a very small percentage。

For example， and we did talk about this before， the infant mortality rate is the number of babies who sadly die before their first birthday。

 divided by the number of live births， multiplied by 1，000。

 which in the end gives you the number of infant deaths per 1，000 live births。

An infant mortality rate of 5。5 means that there were 5。5 deaths by the first birthday for every 1。

000 live births。As another example， let's consider the rate of COVID 19 cases and deaths。

This will be calculated as a number of cases。Or deaths divided by the number of people in a population usually multiplied by 100。

000。Let's again， sadly， a lot of these statistics are not uplifting。

 but let's talk about COVID death rates worldwide， the COVID death rate for Peru is the highest in the world。

647 deaths per 100，000 people。Is the estimated mortality rate in peru？Some other examples， Brazil。

 that COVID mortality rate is 315 per 10，000， the United States is 308， Italy is 278。

 South Africa 171， Norway 60， Vietnam 44。And the most recently available data from China are one per 100。

000 people， death rate of one per 100，000， and again we always need to think about are the data being reported accurate。

 how are they collected， we'll talk more about that in other。Units in this course。

 is it the comparison of these rates， and we're focusing on mortality rates right now across these countries fair。

 I it fair to compare Norway's rate of 60 with Italy's rate of 278。Well。

 one thing that demographers and epidemiologists and data analysts who are creating rates for governments need to think about is。

What is the impact of the age distribution of the population？On the thing that we're measuring here。

 in this case， comparing death rates for different causes， including covid。

Really needs to consider what's the age distribution in the population I'm going to tell you a little anecdote now recently a columnist for the New York Times named David Leonard。

Wrote in a piece about how during the second year of the COvid pandemic in the United States quote。

COVID's racial gaps have narrowed and more recently even flipped over the past year。

 the COVID death rate for white Americans has been 14% higher than the rate for black Americans and 72% higher than the Latino rate。

 according to the latest CDC data。Mr。 Leonard presented data and graphics showing trends over time in the rate of COviD incidents and death。

Per 100，000 people by race and ethnicity。Almost immediately。

 epidemiologists and demographers and statisticians sharply criticized his analysis and conclusions。

Why would that be？Well， again， the answer is that because the age distribution of racial and ethnic subpopulations in the United States varies dramatically and because age is so strongly related to the risk of getting and dying from COVID。

 you can't fairly compare COVID rates by race or ethnicity without adjusting for these age differences。

For example， the population of blacks in the United States is a bit younger。

There are relatively more children， young adults and middle a people compared to over older people in the black population than the white population it's the same for the Hispanic population in the United States as well。

Also， black Americansic die younger on average and also currently of higher birth rates。Thus。

 it's not surprising that the white population might have more deaths from COVID on average per 100。

000 people than the black population， because those 100。

000 people on average are older and COVID mortality is so strongly related to age。

My point here is that adjusting rates for age is often very important。

What is age adjustment you might be thinking， well。

 age adjustment is a statistical process that's applied to rates of disease， death injuries。

 but also many other outcomes， which allows population and communities with different age structures to be compared。

We're not going to get into the technical weeds of how to do age adjustment or what is sometimes called age standardization there are actually several different types of methods。

My point today is simply for you to be aware that if you are creating rates or data visualizations of rates that compare subpopulations or different geographic areas or periods of time。

 that differ in regard to their age distributions， you need to recommend age adjusting these rates to make them comparable。

Mr。 Leonard was mistaken in his interpretation of COVID rates。

 and that's also he was mistaken in his conclusion that racial disparities in COVID mortality were narrowing and resolving in the United States。

Not knowing how to best create and interpret rates can not only lead to erroneous and misleading conclusions。

 but importantly， it can also lead to policy changes， the reallocation of resources。

And the declaration of a problem that is still important as solved。

 So just keep in mind that some rates need to be age adjusted or age standardized in order for you to avoid participating in misleading results。



![](img/dc3bad5de5e43c27a5aae074b1b729de_3.png)

![](img/dc3bad5de5e43c27a5aae074b1b729de_4.png)