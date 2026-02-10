# IBM数据工程专业证书第1课：《数据工程入门课程（IBM）》introduction-to-data-engineering - P20：19_可选数据湖仓解析.zh_en - GPT中英字幕课程资源 - BV1G94y1y7oT

So last week I'm having dinner at this restaurant and I'm looking around， the place is packed。

 everyone's getting their orders on time， and I couldn't help but think about the logistics that go into a restaurant turning raw ingredients into these delicious meals。



![](img/cd5bc24c8a5d74e236030b437219b176_1.png)

![](img/cd5bc24c8a5d74e236030b437219b176_2.png)

![](img/cd5bc24c8a5d74e236030b437219b176_3.png)

![](img/cd5bc24c8a5d74e236030b437219b176_4.png)

So let's think about this for a minute。So in a commercial kitchen。



![](img/cd5bc24c8a5d74e236030b437219b176_6.png)

We have raw ingredients being delivered by trucks。

![](img/cd5bc24c8a5d74e236030b437219b176_8.png)

![](img/cd5bc24c8a5d74e236030b437219b176_9.png)

2 hour。Loading dock on large pallets， right， So a truck comes in to the loading dock。



![](img/cd5bc24c8a5d74e236030b437219b176_11.png)

![](img/cd5bc24c8a5d74e236030b437219b176_12.png)

They drop off the pallet and the truck is back out on the road to deliver more ingredients to other restaurants。



![](img/cd5bc24c8a5d74e236030b437219b176_14.png)

So that's the easy part。 Now we actually have to unwrap this pallet and process it， right。

 We have to sort everything on it。 We have to label all of our ingredients。



![](img/cd5bc24c8a5d74e236030b437219b176_16.png)

RightAnd then we also have to make sure that each item is routed to the correct storage area。



![](img/cd5bc24c8a5d74e236030b437219b176_18.png)

![](img/cd5bc24c8a5d74e236030b437219b176_19.png)

So these things could be going into a pantry for dry goods。



![](img/cd5bc24c8a5d74e236030b437219b176_21.png)

Or it could also be going into large walk in fridges and freezers for things like fresh vegetables and meats。

 And we also have to organize those storage areas， right So we've got to make sure that ingredients that are expiring first are used first。

 We've got to make sure certain ingredients are separated from one another for contamination reasons。



![](img/cd5bc24c8a5d74e236030b437219b176_23.png)

![](img/cd5bc24c8a5d74e236030b437219b176_24.png)

![](img/cd5bc24c8a5d74e236030b437219b176_25.png)

And we also have to make sure that certain ingredients hit a very certain temperature also for food safety。



![](img/cd5bc24c8a5d74e236030b437219b176_27.png)

And by the way， we need to do all of this as quickly。



![](img/cd5bc24c8a5d74e236030b437219b176_29.png)

As possible。

![](img/cd5bc24c8a5d74e236030b437219b176_31.png)

Right， to minimize things like。Food waste。To minimize。Spoilage。



![](img/cd5bc24c8a5d74e236030b437219b176_33.png)

That we could see from the ingredients just sitting on the truck or on a pallet， right。

 And without this process， the cooks in the kitchen。



![](img/cd5bc24c8a5d74e236030b437219b176_35.png)

Can't really do their job as effectively or safely。



![](img/cd5bc24c8a5d74e236030b437219b176_37.png)

They'd be spending a lot of their time just looking for ingredients and less time actually cooking and serving out meals。



![](img/cd5bc24c8a5d74e236030b437219b176_39.png)

![](img/cd5bc24c8a5d74e236030b437219b176_40.png)

To their customers， right。Okay， so what does this have to do with data？😡。



![](img/cd5bc24c8a5d74e236030b437219b176_42.png)

Well， if we think about it， this very same process also exists within data architectures of。



![](img/cd5bc24c8a5d74e236030b437219b176_44.png)

![](img/cd5bc24c8a5d74e236030b437219b176_45.png)

Organizations。

![](img/cd5bc24c8a5d74e236030b437219b176_47.png)

So you've got all sorts of different data coming into your organizations from different sources。

 such as in different cloud environments。Different operational applications。 Now， we even have。

Social media data， right？All this is coming into our organization。

 just like a kitchen has ingredients coming from different suppliers。



![](img/cd5bc24c8a5d74e236030b437219b176_49.png)

Okay， so constantly have data coming in。 We need a quick place to dump all different types of data in different formats for later use。

 So we have。

![](img/cd5bc24c8a5d74e236030b437219b176_51.png)

![](img/cd5bc24c8a5d74e236030b437219b176_52.png)

Data lakes。Now， these lakes allow us to cheaply and quickly capture raw structured。And。

Unstructured and even semistructured data。Okay， so now just like in the kitchen。

 we're not really cooking on the loading do。 right， Now。

 maybe I can put a tiny grill there if I really wanted to。

 but we have to organize and transform this data from its raw state into something that's usable for the kind of insights and analytics that our business wants to generate。

 So we have。Enterprise data， warehouses。Or EDWs。Right。

 where data is loaded in sometimes from a data lake。

 but sometimes from other sources like operational applications。

 and it's optimized and organized to run very specific。Analytical tasks。Now， this could be。

Powering different business intelligence or BI workloads， such as building dashboards and reports。

 or it could be feeding into other。Analytical tools。Just like our pantries and freezers。

 data in the warehouse is cleaned， organized， governed， and should be trusted for integrity。Okay。

 so what are some of the challenges that we see in this approach？ Well， as we said。

 data lakes are really awesome to capture tons of data in a cost effective way。

 but we run into challenges with。😊，Data governance。And data quality。Right。

 and a lot of times these data lakes can become。Data swamps。

And this happens when there's a lot of duplicate， inaccurate。

 or incomplete data making it difficult to track and manage assets。So if you think about it。

 what happens when that data becomes still， Well， it loses its value in creating insights。

 the same way that ingredients go bad over time in our restaurant if we don't use them。

So data lakes also have challenges with query performance。

 since they're not built and optimized to handle the complex analytical queries。

 it can sometimes be tough to get insights out of lakes directly。Okay。

 so let's take a look at the data warehouse Now。 Now these are really great at query performance。

They're exceptional。But they can come at。A high cost， right。

 just like those big freezers are can be very costly to run。

 we can't put everything into a data warehouse。Now they can be better optimized to maintain data governance and quality。

But they have limited support for semistructured and unstructured data sources， by the way。

 the ones that are growing the most that are coming into our organization。

And they can also sometimes be too slow for certain types of applications that require the freshest data because it takes time to sort。

 clean and load data into the warehouse。Okay， so what do we do here？Well。

 developers took a step back and said， hey， let's take the best of both data lakes and data warehouses and combine them into a new technology called。

The data。Lake house。So we get the flexibility。And we get the cost effectiveness。Of a data lake。

And we get。The performance。And structure。Of a data warehouse。

So we'll talk more specifically about the architecture of a data lakehouse in a future video。

 but from a value point of view， the Lake House lets us store data from the exploding number of new sources in a low costt way and then leverages built in data management and governance leaders to allow us to power both business intelligence。

And high performance machine learning workloads quickly。Okay。

 so there are plenty of ways that we can start using a lakehouse。

 we can modernize our existing data lakes， we can complement our data warehouses to support some of these new types of AI and machine learning driven workloads。

 but we'll also talk about that in the future video。So the next time you're at a restaurant。

 I hope you think about how the meal on your plate got there and the steps the ingredients took to go from the kitchen to the meal on your plate。

Thank you。 If you like this video and want to see more like it。

 please like and subscribe If you have questions， please drop them in the comments below。



![](img/cd5bc24c8a5d74e236030b437219b176_54.png)