# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p21 20_外部集成系统综述.zh_en [BV1TkurzMEmm_p21]

Welcome， we're going to focus this discussion on externally integrated data。



![](img/b965e2bee6de158c64e991827b1dc9a9_1.png)

Now one of the things you want to think about is APIs and microservices。

 APIs and microservices send data back and forth everywhere throughout the world throughout multiple companies。

 most of our social media， our favorite social media sites they have microservices for developers to come and do new and random apps or add- on to their platforms it's no different in large scale enterprises where they'll have internal APIs and then externally facing APIs to deal with partners and other type of financial transactions。

 this is obviously really huge in Fintech， but it's also big in other companies that deal with financial payments etc。

 so most of these APIs or microservices。

![](img/b965e2bee6de158c64e991827b1dc9a9_3.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_4.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_5.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_6.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_7.png)

Will be positioned so that they can manage the financial transactions。

 grab the data that's needed and not grab the data that's not needed。

 also anonymize things where it where it makes sense so this is just a very simple and basic view of how an API gateway would work for the purpose of handling thirdparty processing processing processing on the left side you'll see the customer dealing with the merchant or a partner company he spends money。

 did whatever they're going to do that payment goes through the API gateway and it then hits the instant data cash for approval。

 depending on what it is if it's like a big item that requires approval it will hit that API data cash and then if it's something that just needs to go straight to the enterprise system where they bought something that may be small it go straight there also depending on the transaction it may need to go to a bank or an other externally regulated。



![](img/b965e2bee6de158c64e991827b1dc9a9_9.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_10.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_11.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_12.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_13.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_14.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_15.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_16.png)

such as payments for legally purchased marijuana or things like that these are things that will go to a regulatory system to ensure that whatever they're doing is not on some banned government list helps protect from fraud criminal activities and other things of that nature now when you think about the bank piece if somebody's buying something with a debit card is going to hit the bank's API because it wants to make sure that the money is in the account and other examples like that right so。



![](img/b965e2bee6de158c64e991827b1dc9a9_18.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_19.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_20.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_21.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_22.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_23.png)

You could be buying from a FinTtech or from a different enterprise。

 depending on what all pieces are part of the transaction。

 it can hit multiple different systems in different companies。

 but they will go through those API gateways。

![](img/b965e2bee6de158c64e991827b1dc9a9_25.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_26.png)

All right， so here's at the tail end of this lesson。

 I want to go over intentionally left dark data and then managed dark data that comes through API。

 gateways， microservices for and from third parties。



![](img/b965e2bee6de158c64e991827b1dc9a9_28.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_29.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_30.png)

So looking at certain levels of PII， things like Social Security number。

 they'll go to specific companies and some companies won't get them depending on the level of information that they should be having。

 secret and intentionally redacted data thinking about compliance and regulatory items our companies purging and keeping the right data and not keeping certain data based on time。

 adherence to government policies and principles and in specific customer selections so that our favorite social media sites as they share our data。

 they reduce the information that is personally identifiable to you so that you are anonymized now looking at managing dark data。

 looking at element mapping， making sure that's correct and then relational data as it's mapped appropriately to our CDEs and our metadata it's similar to what goes on in our OLAP systems and our OLTP systems and then ensure the timeliness and ingestion of the data is proper sometimes depending on when data comes in we'll need those timestamps to ensure the batches come。



![](img/b965e2bee6de158c64e991827b1dc9a9_32.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_33.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_34.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_35.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_36.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_37.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_38.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_39.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_40.png)

correctlyly hopefully we can have data streamed versus batch data but sometimes depending on things things are batched right so and lastly as we're looking at completion and accuracy of data。

 it's important that as things go through the API we don't have those moments of failure or misconnectivity so that all of the data that's supposed to be there comes through and these are critical critical components and critical things that you'll want to think about as we're thinking about dealing with microservices。

 gateways APIs and how dark data can come in and dark data can be left out it just depends if it's intentional if it's unintentional if it's managed all of the above。



![](img/b965e2bee6de158c64e991827b1dc9a9_42.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_43.png)

![](img/b965e2bee6de158c64e991827b1dc9a9_44.png)

So thank you for your time。