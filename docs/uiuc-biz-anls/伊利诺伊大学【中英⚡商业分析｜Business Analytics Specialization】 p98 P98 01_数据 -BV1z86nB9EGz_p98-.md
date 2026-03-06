# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p98 P98 01_数据 -BV1z86nB9EGz_p98-

![](img/8b1ef6d3d0fe84f7b2f68892ef742ccc_0.png)

In this video we will take a brief look at the data we will be analyzing throughout this module。

 we'll be using a neat data set created for this course called the TechA data TechA is a fictional company that owns over 150 convenience stores similar to what you see behind me and gas stations throughout the central United States from Wyoming to Minnesota to Arkansas and Alabama。

 this specific data that we will use in this module is a random selection of customer transactions from these convenience stores for the year's 2023 through 2025。

Though our data set is relatively large， including over a million transactions。

 it only includes a small， random sample of all the transactions available。

 A full data set would be over 145 times larger than this and consist of hundreds of millions of transactions。

 These customer transactions include things like purchases of fuel， lottery tickets， soda and candy。

 Let's get back to the studio to dive deeper into the data。😊，When dealing with any data set。

 it's important to know the level of aggregation in the data。

 the level of aggregation refers to what each row in the data represents。

Is each row in the data transactions for a store， is each row a customer and the specific data set that we are examining each row represents a single product purchase as a part of a single transaction。

 thus the data is organized at the transaction product level。

So if a customer goes to a store and purchases three products， chips， soda， and a lottery ticket。

 this would add three rows to our data set， one row for each product purchased in that transaction。

Even though it was one transaction， that transaction is split into the individual products purchased。

 each row has an entry in the column unique ID。This number is unique to that row。

 meaning no other row has that number。 Additionally， each row has an entry for a transaction ID。

 This number is not necessarily unique because one transaction can have multiple products like in the example here where a customer purchased cherry Coke。

 lace potato chips and a lottery ticket。😊，So while the unique ID is different for each row。

 the transaction ID is the same because these three items were all a part of the same transaction。

Many times a transaction will only have one item purchased， but sometimes it will have more。

There are dozens of features or columns in our data set。

 we won't describe them all here but they can be grouped into five categories。

 we will describe these five categories and the main columns or features in each category。

The first group of columns is the transaction group。

 these columns include the unique identifier for the row， the transaction number。

 and the date of the transaction。The next group of columns is the customer group actually this is not a group of columns。

 but really only one column calledCustom ID。This column identifies the customer making the purchase when that customer is known。

Customers are only known when they are loyalty reward members of the company and when they make their purchase with their loyalty reward number。

The third group of columns is the product and category group。

This group of columns identifies the product and its name。

It also identifies the type or category of the product there are different levels of categories for example。

 a category for a Hershey's bar might be chocolate candy。

 a category that would include other chocolates and the broader parent category might be candy。

 a grouping that would include other candies including nonchocolate candies。

So there are two levels of categorization， one being more specific， and one being more broad。

Each product belongs to a category and that category has a parent category or a superet of that category。

This group of columns also includes a count of the product purchase for that transaction。

The fourth group of columns is the site group， this group of columns identifies the convenience stores where the purchases took place。

 including the site name， an address of the site and the longitude and latitude。

It's important to note， however， that to obscure the actual company used in the data set。

 the addresses are masked by referring to the post offices instead of the actual convenience stores。

Nevertheless， these addresses are close to the convenience stores。5， finally。

 the last group of columns present the amount of revenue and profit for the product that was sold。

 These columns are critical to our analysis going forward。

 since techka is a business and is interested in making money。This is just an overview of the data。

 don't worry， we'll explore this data much more and clean it and understand it over the course of this module。



![](img/8b1ef6d3d0fe84f7b2f68892ef742ccc_2.png)

![](img/8b1ef6d3d0fe84f7b2f68892ef742ccc_3.png)