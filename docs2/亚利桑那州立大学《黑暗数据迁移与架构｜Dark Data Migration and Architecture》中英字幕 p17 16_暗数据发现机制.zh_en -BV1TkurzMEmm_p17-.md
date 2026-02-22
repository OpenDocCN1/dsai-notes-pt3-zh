# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p17 16_暗数据发现机制.zh_en [BV1TkurzMEmm_p17]

Welcome in the course today， we're going to focus on discovery and using captive data in discovery so the situation that we're going to start with is that you're going to be an intelligence architect for a t-shirt company now your executive vice president comes to you and asks what are the top five performing cities in the United States？



![](img/b6e2a7ba9cd83c96c7e9167353488292_1.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_2.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_3.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_4.png)

The typical response to something like this is to run and grab as much data as you can around sales around profit ROi upfront costs cost before EBITDA all of those types of things。

 all those metrics that are specifically related to dollar sales， etc。

 even product sales right and you wouldn't be wrong to go grab those pieces of information but the question itself begs either two questions right is the executive vice president asking specifically about sales。

 product performance in relation specifically only to dollars。

 profit upfront costs and ROi and things like that。

 or are they actually saying which products are performing better and if that's the question we first need to define what is performance from our lens with it most probably starting with all of those things that we discuss but there's also。



![](img/b6e2a7ba9cd83c96c7e9167353488292_6.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_7.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_8.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_9.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_10.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_11.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_12.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_13.png)

A wider picture that we can narrow gaze around for the purpose of discovering the dark data that's there and building upon data products that we can build from that dark data。



![](img/b6e2a7ba9cd83c96c7e9167353488292_15.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_16.png)

So moving forward into that we have to start with understanding the problem right。

 so what is performance Does that include。

![](img/b6e2a7ba9cd83c96c7e9167353488292_18.png)

The time stamping of the records versus when the offers went out versus when all the marketing was sent。

Does response time play a part Does tribal knowledge stop us right if we're looking at software launch and impacts as we do system upgrades as our website or our mobile devices perform better does that enhance our sales as well does the design of our products have an impact so if we change the design has that had an impact and if that does have an impact our different cities now performing better because of any and all of these touch points and are they performing better over time now if we're looking at unanswered questions。

 we take all of those pieces and we add them to product mix so sometimes when we're looking at performance。



![](img/b6e2a7ba9cd83c96c7e9167353488292_20.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_21.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_22.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_23.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_24.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_25.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_26.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_27.png)

If we're just looking at sales。

![](img/b6e2a7ba9cd83c96c7e9167353488292_29.png)

Dep on the marketing， depending on personas， depending on the type of people that are buying our products。



![](img/b6e2a7ba9cd83c96c7e9167353488292_31.png)

A sale today could lead to five sales later， a sale today could lead to another person referring three or four other people。

 how much value is in a referral at this point， depending on the clientele depending on the city and the neighborhoods of the city。

 some cities in some people may refer others more， some people may buy more product。



![](img/b6e2a7ba9cd83c96c7e9167353488292_33.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_34.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_35.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_36.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_37.png)

In larger volumes or either by less product consistently over time and is there a value to different types of accounts these are all different questions so as we look at things like full year sales month over month sales year over year sales increase and decrease。



![](img/b6e2a7ba9cd83c96c7e9167353488292_39.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_40.png)

Is there a value in the people partially completing transactions online is one of the things we would then add to performance as well。

 because if they've partially completed it， do we get enough information from them to then add value to our marketing in the future？



![](img/b6e2a7ba9cd83c96c7e9167353488292_42.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_43.png)

So typically with those types of questions that you would get from your EVP you'd start with， okay。

 we'll give you first the sales， the ROI upfront costs， all of those types of metrics。

 but then we have to answer these deeper questions and those deeper questions also drive us into these more robust examples dealing with search engine optimization。

 search engine management account volume and deepening deepening of the relationships with your customers。

 how deep can we go， how many products can we satisfy their needs with so that they can continuously come to us and also continuously refer us to friends and share our information across the world becoming advocates of our brands。

 so looking at mobile apps。

![](img/b6e2a7ba9cd83c96c7e9167353488292_45.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_46.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_47.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_48.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_49.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_50.png)

Web apps， the last piece that we would then want to say what other dark data that we have that is captive would be outage information So we looked at first engineering performance performance in general distribution of new software or uplifts to the platforms that we have we looked at all the different metrics that we could have or create and we'll talk a bit more about those ingenerative data that we have could create from the captive data but then specifically if we have performance issues and outages those then affect our ability to capture not only information but capture the sale in those markets which within decrease that report on performance so that data is critical to the outage data because that also shows us where we have lost money that we could have attained and then the value of the loss versus the loss after or they gain after the losses they are ramp up once system support comes back online so these are all different examples of captive data and how you。



![](img/b6e2a7ba9cd83c96c7e9167353488292_52.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_53.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_54.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_55.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_56.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_57.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_58.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_59.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_60.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_61.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_62.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_63.png)

Use captive data and some examples of how captive data then turns into generative data as a support basis which we'll get into further Thank you for your time。



![](img/b6e2a7ba9cd83c96c7e9167353488292_65.png)

![](img/b6e2a7ba9cd83c96c7e9167353488292_66.png)