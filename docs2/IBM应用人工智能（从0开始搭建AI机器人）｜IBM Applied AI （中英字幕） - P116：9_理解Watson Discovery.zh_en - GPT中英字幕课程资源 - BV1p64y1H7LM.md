# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P116：9_理解Watson Discovery.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

🎼。Welcome to Module2 of our course on Building AI applications。



![](img/11ce409dfa8ea556d57a303efb43ba9f_1.png)

In this module we'll explore Watson Discovery， one of the coolest services available on the IBM Cloud。

You can think of Watson discoveryy as an advanced insight engine。

The key goal of Watson discoveryy is to leverage Watson's artificial intelligence capabilities to extract insight out of your data Most companies have a wealth of data The real challenge is extracting insight and discovering actionable information。



![](img/11ce409dfa8ea556d57a303efb43ba9f_3.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_4.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_5.png)

This is why the data scientist' role has become so prominent in recent years data is everywhere。

 the ability to it to improve your business is where the real value lies。 Okay， I hear you。

 this still feels somewhat abstract， so let's consider a practical example。



![](img/11ce409dfa8ea556d57a303efb43ba9f_7.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_8.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_9.png)

Watson Discovery allows you to load your own data， but it also comes with a convenient Watson Discovery news data set containing news articles from the past 60 days this huge collection is automatically maintained and updated for you。

 allowing you to easily analyze the news Now imagine that you are a journalist。

 a writer or anyone who needs to analyze the news having access to over 10 million news articles is nothing short of amazing。



![](img/11ce409dfa8ea556d57a303efb43ba9f_11.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_12.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_13.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_14.png)

But it's also quite overwhelming how do you go about querying such a huge data set to extract insight out of it？



![](img/11ce409dfa8ea556d57a303efb43ba9f_16.png)

That's where the magic of Watson Discy kicks in Discovery has the ability to apply artificial intelligence algorithms to enrich the raw data that you imported。

Or in the case of the news collection that was imported for you。

 such enrichments including extracting keywords from the documents， tagging concepts。

 extracting specific entities such as a country， companies， and even people。

 as well as sentiment analysis， was a news article about a particular company， positiveitive。

 neutral， or negative。

![](img/11ce409dfa8ea556d57a303efb43ba9f_18.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_19.png)

Discovery allows us to query this enriched data we can build our own queries through natural language。

 a visual builder， or by using a specific syntax employed by discovery known as the discovery query language in the case of Watson discoveryover news we even have some sample queries for immediate gratification and to show us how said syntax is specified。

 what's also great about these sample queries is that they give you an idea of the sort of insight that you can extract using Watson discoveryover for example。

 using this news collection we can find out the top 10 companies in the news who received the most positive coverage or AI companies that were recently acquired。

 or even the most mentioned people in the tech industry imagine trying to do this manually without a service like discoveryover the reason why these queries are possible is because Watson discoveryovery enriches the documents。



![](img/11ce409dfa8ea556d57a303efb43ba9f_21.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_22.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_23.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_24.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_25.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_26.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_27.png)

Take an article about Tesla for example， Watson will read the article。

 determine whether it's positive， negative or neutral， detect relevant people， for example。

 Elon Musk， and companies mentioned within it， for example， Tesla and Mercedes Benz， and so on。

 you'll get more familiar with the Discovery query language in the labs for this module。

 but I want to give you an idea of what it looks like。



![](img/11ce409dfa8ea556d57a303efb43ba9f_29.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_30.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_31.png)

Let's zoom in on this particular query for the most positively talked about companies in the media。



![](img/11ce409dfa8ea556d57a303efb43ba9f_33.png)

We start off with enriched textex， which is the text of a news article。

 plus all the nice enrichments Watson added for us from there we select the entities within the document。

 entitiesities are special values that were detected by Watson。



![](img/11ce409dfa8ea556d57a303efb43ba9f_35.png)

Think companies， people， cities， etc we then filter for a specific type of entity in our case。

 companies， but we only want the subset of mentions that are positive。

 so we use the sentiment analysis enrichment to ask for a high positive sentiment score。



![](img/11ce409dfa8ea556d57a303efb43ba9f_37.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_38.png)

Finally， we specify that we want to aggregate the results through the name of the entity。

 for example， Netflix or Facebook。

![](img/11ce409dfa8ea556d57a303efb43ba9f_40.png)

If we wanted to find out the people who received negative media coverage。

 we could simply change the entity type filter to be person instead of company and adjust the sentiment score requirements。

 sometimes you'll find the same name in both the top positive and negative lists。

 this is not uncommon for very famous politicians as they tend to receive polarizing coverage in the press so they might receive lots of positive mentions。

 but also a lot of criticism， don't worry too much about getting the details of the query language right away。

 there are simpler ways to query discovery using either natural language or visual mode。



![](img/11ce409dfa8ea556d57a303efb43ba9f_42.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_43.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_44.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_45.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_46.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_47.png)

Nevertheless， it's important that you know that the advanced option is there if you need it。



![](img/11ce409dfa8ea556d57a303efb43ba9f_49.png)

And the more you use discovery and play with it， the more familiar you'll become with its powerful query language。



![](img/11ce409dfa8ea556d57a303efb43ba9f_51.png)

Having access to news data is great， but most businesses are likely to be interested in being able to query their own data and documents。

 Discovery allows you to easily connect various data sources to create your own collection。



![](img/11ce409dfa8ea556d57a303efb43ba9f_53.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_54.png)

There is integration with Salesforce， SharePoint， B， and IBM Cloud Object storage， for example。



![](img/11ce409dfa8ea556d57a303efb43ba9f_56.png)

You can also get discoveryovery to crawl a website for the information。

 as well as uploading documents directly， including PDFs。



![](img/11ce409dfa8ea556d57a303efb43ba9f_58.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_59.png)

Your business might have domain specific entities， so Discovery even offers you the ability to create custom machine learning models for the identification and classification of entities that are pertinent to your specific business。



![](img/11ce409dfa8ea556d57a303efb43ba9f_61.png)

There is a more advanced topic that will require integration with another Watson tool。

 namely Watson Knowledge Studio， which allows you to create and train models as far as this course goes。

 we are not going to leverage such functionality but it's important that you know it's there if you need it。

 In fact， feel free to explore discovery and what it has to offer beyond what we cover in this course by perusing the official documentation。



![](img/11ce409dfa8ea556d57a303efb43ba9f_63.png)

![](img/11ce409dfa8ea556d57a303efb43ba9f_64.png)