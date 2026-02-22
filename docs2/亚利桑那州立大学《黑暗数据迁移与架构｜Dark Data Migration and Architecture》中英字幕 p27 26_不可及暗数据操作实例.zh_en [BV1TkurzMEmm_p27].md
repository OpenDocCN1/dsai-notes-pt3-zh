# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p27 26_不可及暗数据操作实例.zh_en [BV1TkurzMEmm_p27]

Welcome in this lesson we're going to take a stab at diving into creating a data product。

 using unattainable data， generative data captive data and everything that we have in our whole data ecosystem Now we're going to focus at a high level because all we're going to do is make a data product focused on a business target not necessarily on reviewing results monitoring results or the ability to look at the results of the data product and then make adjustments as we move forward it's specifically about setting the target so it's pretty much as high level as you can get now I wanted to go back to the t-shirt example。

 the t-shirt company where we're making custom t-shirts and start with this data from the census the you know the US census and you can see all the different data elements going from you know the ages the median ages。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_1.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_2.png)

And then the total population， households and all the stuff that goes in our household。

 average household size， et cea。

![](img/b42d2e99f26af55c4c0021c8c5f5a006_4.png)

Now I'm pulling out some pieces of information that are more relevant to us and on the left side where you see Ohio。

 these are all of our business data data attributes that we found that we've sold over the last full year in Ohio and on the left side on the right side is external data。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_6.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_7.png)

This external day is specific to Ohio， but it's everything we got from the Census Bureau so just at our first look you see the total number of t-shirt customers。

 the total number of sales， the t-shirt prices， the average the top five t-shirt。

 the average of the top five t-shirt prices and the weighted average between the two which we weighted a little bit higher to the top five because our goal is going to be sell the higher end products。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_9.png)

On the right side。You'll see total population， you'll see Ohio total population in the population over 18 years old。

 and then you also see households and average household size。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_11.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_12.png)

Now。Everybody doesn't buy a ts shirtt for us， we want to look at every person as that has the opportunity to at least buy one Thir and our goal is to get one T shirtt in everybody's hands。

People buy t shirts as gifts， people buy T shirts for other people。

 although in the household you have people who are under 18， which we won't target。

But in a household will target the whole household because household the head of the household。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_14.png)

Could buy T shirts for anybody in the household， and typically parents buy T shirts for their children and children like to go through a lot of T shirts。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_16.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_17.png)

So we also have data on search engine optimization， clicks， impressions， transactions。

 the total sales in the industry， all of that stuff。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_19.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_20.png)

And for us， we're going to focus on how we can use a mixture of this captive data， generative data。

 uncapture data and unattainable data so that we can make these data products。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_22.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_23.png)

All right， so here's the marketing analysis that we want to focus on。

Here's a few assumptions at the top right on the top left， each person buys one t-shirt。

 although we know not everybody will buy a t-shirt， each household buys two t-shirts。

 and we have to pair that assumption with the assessment that only 83% of the population has not even bought a t-shirt which leaves 17% who have bought t-shirts。

So if we're looking at it， we're saying we want every one person to buy a T shirt and every two people are go to buy a T shirt in the household。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_25.png)

Out of that， only 17% of them will buy our leadership is targeting that we should control 20 percent of the market。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_27.png)

By end of next year。One of the questions is is that attainable and it may or may not be。

 but currently we have only 13% of the market so we have to jump 17% in a year we have to figure out what's going to be our。

What's going to be our goal and how are we going to come about that total possible t shirt sales3 point four million。

So out of all the t shirts， we have to get to 3。4 million or we have the possibility to get to 3。

4 million based on our assumptions now we also already know that although we're saying it's possible to get 3。

4 million in reality。

![](img/b42d2e99f26af55c4c0021c8c5f5a006_29.png)

Only 1。83 million have sold。 so the possibility is much higher than what is the actuality。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_31.png)

So part of it is should we start having campaigns to get people more interested in t-shirts in general so that we can increase the amount of people who are buying t-shirts when we do that we understand that we will have to we will have to also think about we are also advertising for other folks and we will be allowing other companies to take take a bit of the profit when we do that type of advertising so if we go into the targets in total on the right side right now we're going to get into a bit of the numbers all right so we're going to take that 8。

46 which if we go back to the population over 18。

![](img/b42d2e99f26af55c4c0021c8c5f5a006_33.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_34.png)

That's where that double covers wrote up。then the 4。5 is the number of households。

 we're going to multiply that by two because we're saying each household has two shirts。

 we're going to come up with the number 17。36 from there we're going to go go to the industry numbers right that's 17 point and that's going to give us from that 17。

36 we're going to take only 17% of populations buying and then we're going multiply by our target because out of the 17 we only want 20% of it so we're looking at only little over 500000 t-shirts about nearly 600。

000。

![](img/b42d2e99f26af55c4c0021c8c5f5a006_36.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_37.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_38.png)

So from there we take those amount of t-shirts and then we look at what our price per t-shirt is。

 we're going to drop that down to the 17% again based on the population that it's actually buying and then we come out with 1。

12 million and we're saying that 1。12 million that volume of t-shirts is the amount of t-shirts that we should have as a controlling stake of the market based on growth over time for the next year since currently when we look at t-shirts sold that's more than half right so we're looking at growth over time for the next year。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_40.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_41.png)

And when we look at that 1。12 number we're going to say， man， that's a big jump from the 187。

000 Thirts， leadership， do you really want us to go for 20% of the market。

 that would be the question because we'll set ourselves up for failure。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_43.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_44.png)

Because at the end of the day that market's going to grow。

 especially if we're starting to pump out more advertising and more sales。

 so now thinking about other targets， so these are just some baseline numbers that I took 13%， 10%。

 10% total shirts sold， 10% of 13% of the sales， this lets us know that our products are actually selling for slightly higher than the market average。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_46.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_47.png)

We're also reing for 14% of the clicks in 8% of the transactions looking at impressions and then 3% higher average sale like we discussed before。

 one thing you'll want to consider is is there value for people partially filling out a shopping cart。

 is there value from impressions， is there value from referrals？



![](img/b42d2e99f26af55c4c0021c8c5f5a006_49.png)

These are all data points that we want to consider and we want to add into the mix if we're going to really put together a more robust data product this is a very basic one and this would be something that we would definitely add more insights and more intelligence to and come up with that number and that rubric where we would have product focused specifically on the market and a product also focus specifically what on how we're delivering towards that progress and we'll go through a more robust one later on so thank you for your time。



![](img/b42d2e99f26af55c4c0021c8c5f5a006_51.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_52.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_53.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_54.png)

![](img/b42d2e99f26af55c4c0021c8c5f5a006_55.png)