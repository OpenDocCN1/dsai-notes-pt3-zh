# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p65 27_高层架构解析.zh_en [BV1TkurzMEmm_p65]

Welcome， in this lesson， we're going to go over a high level design of an analytical system。

So the first thing we want to do is focus on outcome attainment。

Will our design support our value as expected？We will be able to extract dark data。

 use it to create data products to support our analytical systems and will our design remain vigilant against future failure against failure and will it be future proof can we scale it up and can we expand it we'll focus on customer usage customer engagement if we don't get adoption that means the system is useless and you don't want to design useless。

Design useless systems right， we want to make sure we get full utilization and that we get full utilization of every aspect of what we put out as a product。



![](img/16441d8eabac9b05df7874d021b4714a_1.png)

Now again， starting with this conceptual design we're going to zero in on the big data area right in that analytical vertical。

 we're going to zero in on that and then we're going to show what something looks like at a high level and sort of a basic look of what an analytical system would look like。



![](img/16441d8eabac9b05df7874d021b4714a_3.png)

H love architecture of something like this。 We have our operational systems， we have our flat files。

 our flat files could be JSON objects， they could be they could be anything。

 they could be spreadsheets， they could be even emails。

 they could be rot data but flat files come in you have some processing processing could consist of like a data store it could consist of an ETL process feeding a data store extracting it from a data store and then and then it sends that data to a data warehouse now is it could be a house or warehouse or a lake right so if we're talking data lake we're talking unstructured data。

 NosQL， we're talking warehouse we're talking SQL MysQL MSsQL whatever it might be So in here you have raw data metadata。

 this is gonna be Mm somewhere managing the data model then you're gonna talk about summary data in there as well right so what are the summarize fields and values that will send up stream to users right。



![](img/16441d8eabac9b05df7874d021b4714a_5.png)

So looking at this， when we think about the metadata， the raw data。

 there's also referential data that helps us get to the summaries or referential data that helps us build data products or also helps us enrich the data that could come from a number of other sources。

 but it all sits and resides in that warehouse。

![](img/16441d8eabac9b05df7874d021b4714a_7.png)

Now out of that warehouse we move upstream to the data Mars right so we have sales。

 marketing engineering， these are all different types of data and wherewith you have different segments and things that allow for special analysis right so when you think about sales if someone was to say you know we're a company that sell across the United States and someone was to ask what states perform best for sales。



![](img/16441d8eabac9b05df7874d021b4714a_9.png)

The question to say perform is different than the total sales。Sales performance is one thing。

 but performance of our products is a whole not animal right so when we're talking about what performs better。

 it's more than just that sales number， it's also referrals depending on the type of product are people sort of gaming the system buying our product and returning it。

 buying and returning it so we have to include those types of numbers if it's something like an accounts where services are people gaming our services how are people getting over on our systems all of that is included when we start talking about performance versus just simply sales so product performance is critical when we look at it from the lens of sales these are just things we want to think about as well as when we think about performance for marketing same thing and all these are aspects of dark data that you' want to think through when you go to the analytical piece so going into marketing and we're thinking about our marketing campaigns we have clickthrough rate cost per click spend on keywords and things like that when we're talking about SE。



![](img/16441d8eabac9b05df7874d021b4714a_11.png)

![](img/16441d8eabac9b05df7874d021b4714a_12.png)

![](img/16441d8eabac9b05df7874d021b4714a_13.png)

![](img/16441d8eabac9b05df7874d021b4714a_14.png)

![](img/16441d8eabac9b05df7874d021b4714a_15.png)

![](img/16441d8eabac9b05df7874d021b4714a_16.png)

![](img/16441d8eabac9b05df7874d021b4714a_17.png)

![](img/16441d8eabac9b05df7874d021b4714a_18.png)

Search engine marketing。But the performance of our campaigns。

 our marketing campaigns lies with all of those data points plus the number of applications right so you have the response rate。

The click through， which includes click through applications， et cetera。

 But then the performance piece， includes average daily balance of things。

 If people have accounts with you or of its products。 again， the return or the keep of the product。

 right， So that all plays a part of the marketing， because when you're thinking about marketing and the sales as they work in parallel and they support each other。

Tings you want to think about are we could be selling to certain markets that have higher rates of return or selling to certain personas that have higher rates of return and return。

 I mean， returning of the product not necessarily return on the dollar or the investment and then last thing with engineering。



![](img/16441d8eabac9b05df7874d021b4714a_20.png)

![](img/16441d8eabac9b05df7874d021b4714a_21.png)

Think about the engineering data this is how much it costs this is well a few things。

 how much does it cost engineer something， how long does it take and how well has something been engineered that plays a part as well because if we've determined that the product itself is effective and not necessarily the marketing of the sales then we have to go into engineering and understand how we need to make those adjustments and at the end of it you have the user analysis and the regular analysis and these pieces will allow you to visualize and internalize the data for you to make better decisions and all of that are different segments of dark data that you need to build into the beginning of in the beginning of the build in the data warehouse where you have metadata。

 raw data and summary data and it goes up the system via ETL and other processes so this sort of a highlevel overview and why and how we would build it like this and then how dark data helps us attain value and do better analytics from these types of systems Thank you for your time。



![](img/16441d8eabac9b05df7874d021b4714a_23.png)

![](img/16441d8eabac9b05df7874d021b4714a_24.png)

![](img/16441d8eabac9b05df7874d021b4714a_25.png)

![](img/16441d8eabac9b05df7874d021b4714a_26.png)

![](img/16441d8eabac9b05df7874d021b4714a_27.png)

![](img/16441d8eabac9b05df7874d021b4714a_28.png)

![](img/16441d8eabac9b05df7874d021b4714a_29.png)

![](img/16441d8eabac9b05df7874d021b4714a_30.png)