# uPenn《如何运用数据1（Python数据分析、SQL、EDA）｜How to Use Data》中英字幕 - P19：18_编程演示：记录筛选与数据排序.zh_en - GPT中英字幕课程资源 - BV1wKxJz3EFB

In this section， we'll look at filtering records and sorting data。



![](img/29d87de3664982738615e924baf55603_1.png)

Let's take a look at the first name and last name of every doctor where the doctor ID is less than three。



![](img/29d87de3664982738615e924baf55603_3.png)

![](img/29d87de3664982738615e924baf55603_4.png)

We'll use the wear clauses and specify a condition to be satisfied。



![](img/29d87de3664982738615e924baf55603_6.png)

This shows us the information for only those doctors who have an ID that's less than three。



![](img/29d87de3664982738615e924baf55603_8.png)

![](img/29d87de3664982738615e924baf55603_9.png)

Let's find all patients with the last name， Jones。

![](img/29d87de3664982738615e924baf55603_11.png)

Again， we'll use the wear clauses， followed by the condition where the patient's last name is equal to Jones。



![](img/29d87de3664982738615e924baf55603_13.png)

This shows the corresponding information for those patients with the last name， Jones。



![](img/29d87de3664982738615e924baf55603_15.png)

![](img/29d87de3664982738615e924baf55603_16.png)

Let's find the doctors who do not have the title MD。



![](img/29d87de3664982738615e924baf55603_18.png)

We'll use the wear clauses followed by the condition where the doctor's title is not equal to MD。



![](img/29d87de3664982738615e924baf55603_20.png)

This shows those doctors。Let's see all of the patients with the first name Becky and last name Jones for this query。

 we'll use the wear clause， followed by multiple conditions to be satisfied。

 The patient's first name must be equal to Becky and the patient's last name must be equal to Jones because we're using and both conditions must be met to satisfy the wear clauses。



![](img/29d87de3664982738615e924baf55603_22.png)

![](img/29d87de3664982738615e924baf55603_23.png)

![](img/29d87de3664982738615e924baf55603_24.png)

![](img/29d87de3664982738615e924baf55603_25.png)

![](img/29d87de3664982738615e924baf55603_26.png)

Let's see all the patients with the last name Jones， or Roberts。



![](img/29d87de3664982738615e924baf55603_28.png)

![](img/29d87de3664982738615e924baf55603_29.png)

Again， we'll use the wear clauses， followed by multiple conditions to be satisfied。

 The patient's last name must be equal to Jones， or the patient's last name must be equal to Roberts。



![](img/29d87de3664982738615e924baf55603_31.png)

![](img/29d87de3664982738615e924baf55603_32.png)

Because we're using or either condition can be true to satisfy the wear clauses。



![](img/29d87de3664982738615e924baf55603_34.png)

![](img/29d87de3664982738615e924baf55603_35.png)

The like operator can be used to compare a column to a given pattern。

 Let's search for patients with first names that begin with the letter J。

 So we'll use the weare clauses， followed by the condition where the patient's first name is like J per。

 So the patient's first name must start with the letter J， followed by0 or more other characters。

 Let's search for doctors with last names that begin with S A and end with A N。

 here we use like to compare the doctor's last name to S A underscore A N。

 which means the doctor's last name must begin with S A end with A N and contain any number of individual characters in between。



![](img/29d87de3664982738615e924baf55603_37.png)

![](img/29d87de3664982738615e924baf55603_38.png)

![](img/29d87de3664982738615e924baf55603_39.png)

![](img/29d87de3664982738615e924baf55603_40.png)

![](img/29d87de3664982738615e924baf55603_41.png)

![](img/29d87de3664982738615e924baf55603_42.png)

![](img/29d87de3664982738615e924baf55603_43.png)

![](img/29d87de3664982738615e924baf55603_44.png)

![](img/29d87de3664982738615e924baf55603_45.png)

Is null searches for records where a column contains a null or unknown value。

 Let's find the doctors with an unknown title。

![](img/29d87de3664982738615e924baf55603_47.png)

![](img/29d87de3664982738615e924baf55603_48.png)

In our condition， we'll look for records where the doctor's title is null。



![](img/29d87de3664982738615e924baf55603_50.png)

This shows the records where the doctor's title is null or unknown。



![](img/29d87de3664982738615e924baf55603_52.png)

Let's compare this to another query where we search for doctors， where the doctor's title is null。



![](img/29d87de3664982738615e924baf55603_54.png)

![](img/29d87de3664982738615e924baf55603_55.png)

Or the doctor's title is equal to an empty string。

![](img/29d87de3664982738615e924baf55603_57.png)

This shows the doctors where the title is null or empty。



![](img/29d87de3664982738615e924baf55603_59.png)

Let's select the first name and last name of all patients， ordering them by last name。



![](img/29d87de3664982738615e924baf55603_61.png)

![](img/29d87de3664982738615e924baf55603_62.png)

We can use order by to order rows by a specific column。



![](img/29d87de3664982738615e924baf55603_64.png)

This shows the patients ordered by last name。 By default， it's an ascending order。



![](img/29d87de3664982738615e924baf55603_66.png)

Now let's order them by last name， then first name。



![](img/29d87de3664982738615e924baf55603_68.png)

![](img/29d87de3664982738615e924baf55603_69.png)

We can use order by and specify multiple columns order by the patient's last name in ascending order。



![](img/29d87de3664982738615e924baf55603_71.png)

And then， by the patient's first name。In ascending order。

This shows the patients ordered by last name and then first name。

