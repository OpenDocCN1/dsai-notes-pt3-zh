# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p54 14_组合数据.zh_en [BV1Jr421w7wL_p54]

🎼，A common task in data science is combining multiple sets of data together。However。

 because data is rarely a perfect match， there is no single approach that works for every case。

In this video， you will learn about five common methods for combining data。

These five methods are horizontal concatenation。Vertical concatenation。joining。Inner joiningining。

And outer joint。First up is concatenation。

![](img/524670c3d1a92a9cf5e883866acad546_1.png)

Which is useful when two sets of data are identically structured。

This is the most basic way to combine data， and this equivalent is simply taping the tables together。



![](img/524670c3d1a92a9cf5e883866acad546_3.png)

Therefore， vertical concatenation is only used when combining data of the same type。



![](img/524670c3d1a92a9cf5e883866acad546_5.png)

This is exactly what you accomplished when you used a data store to bring together the monthly flight data into one table for the entire year。



![](img/524670c3d1a92a9cf5e883866acad546_7.png)

![](img/524670c3d1a92a9cf5e883866acad546_8.png)

Let's apply this concept with a smaller example that you'll revisit throughout this lesson。



![](img/524670c3d1a92a9cf5e883866acad546_10.png)

Let's say you have a table of Nobel Prize winners in physics。

Which contains a row for each prize awarded。And columns for both the year and the prize winner's name。



![](img/524670c3d1a92a9cf5e883866acad546_12.png)

Now， let's say you're trying to add to this list the Nobel Prize winners in Chemis。



![](img/524670c3d1a92a9cf5e883866acad546_14.png)

With vertical concatenation。

![](img/524670c3d1a92a9cf5e883866acad546_16.png)

You can combine the data vertically by stacking the two lists together。



![](img/524670c3d1a92a9cf5e883866acad546_18.png)

Now imagine you have data containing more information on the same rows。For instance。

 your second table is a list of discoveries corresponding to the Nobel Prizes。

Here you need to combine the two tables horizontally。



![](img/524670c3d1a92a9cf5e883866acad546_20.png)

This is called horizontal concatenation。And the final result is one table with all three columns。



![](img/524670c3d1a92a9cf5e883866acad546_22.png)

However， things can get complicated when your two tables aren't sorted or aren't the same length。

For instance， what if your second table is an alphabetical list of various scientists and their countries of origin？



![](img/524670c3d1a92a9cf5e883866acad546_24.png)

Here the rows have in colored to highlight the matching names。

Now you can't horizontally concatenate the tables because not only are the name columns not aligned。

 but the tables are different lengths。

![](img/524670c3d1a92a9cf5e883866acad546_26.png)

So what do you do？

![](img/524670c3d1a92a9cf5e883866acad546_28.png)

In situations like this， where simple concatenation no longer works。

 you'll need to use key variables to direct the joining of the tables。



![](img/524670c3d1a92a9cf5e883866acad546_30.png)

A key is a unique variable that identifies a specific row。

Because you would like to combine the rows that share the same name。

 select the name columns as the key variables。Notice how each key name in the left table has a matching key name in the right table。



![](img/524670c3d1a92a9cf5e883866acad546_32.png)

Now you can join them。

![](img/524670c3d1a92a9cf5e883866acad546_34.png)

And the result is a single table that correctly matches the prize winners with their countries。



![](img/524670c3d1a92a9cf5e883866acad546_36.png)

The concept of joining is illustrated in these Venn diagrams。Here。

 each circle represents a set of data。Their amount of overlap represents the rows shared between them。

 as determined by the key variables。

![](img/524670c3d1a92a9cf5e883866acad546_38.png)

And the colored regions represent which pieces are carried over into the final combined table。



![](img/524670c3d1a92a9cf5e883866acad546_40.png)

For instance， in order to join， it is a requirement that the right data needs a key matching at least every key in the left data。



![](img/524670c3d1a92a9cf5e883866acad546_42.png)

The final result contains all the rows from the left data。



![](img/524670c3d1a92a9cf5e883866acad546_44.png)

But all the variables from both。These diagrams are helpful when deciding which joining method to use based on how much data you want to keep in the combined table。



![](img/524670c3d1a92a9cf5e883866acad546_46.png)

You'll have to make this decision when your tables have missing keys。Or in other words。

 when they don't fully overlap。If this happens， you have a few possible methods to choose from。



![](img/524670c3d1a92a9cf5e883866acad546_48.png)

The two most common are inner and outer joining。

![](img/524670c3d1a92a9cf5e883866acad546_50.png)

Inter joiningining is useful for when you want to save only the rows with matching keys。



![](img/524670c3d1a92a9cf5e883866acad546_52.png)

For instance， let's say your second table is now a list of physicists who have published books。Again。

 the matching names are color coded。But notice that a few of them are only found in one table。

Therefore， you cannot join them together， as you did previously。



![](img/524670c3d1a92a9cf5e883866acad546_54.png)

Instead， inter joiningining these tables drops all the rows that don't match。

The final table is a list of physicists who have both won a Nobel Prize and published a book。

But that was a very selective type of joining。What if instead you wanted to keep all the data in your join table。

 even if the keys don't match。

![](img/524670c3d1a92a9cf5e883866acad546_56.png)

This is where outer joint comes in。When you combine the two tables using an outer join。

 no data is left behind and your final result is a comprehensive table。



![](img/524670c3d1a92a9cf5e883866acad546_58.png)

![](img/524670c3d1a92a9cf5e883866acad546_59.png)

In this case， you end up with a list containing all the physicists， some who won the Nobel Prize。



![](img/524670c3d1a92a9cf5e883866acad546_61.png)

Some who published a book， and some who did both。

![](img/524670c3d1a92a9cf5e883866acad546_63.png)

Note that in order to include every row from both tables。

 the unmatched ones are left with empty values。

![](img/524670c3d1a92a9cf5e883866acad546_65.png)

You may not have known there were so many options available from merging sets of data。

 And this video didn't even cover all of them。

![](img/524670c3d1a92a9cf5e883866acad546_67.png)

Which method you choose depends on what you want to include in your final result。



![](img/524670c3d1a92a9cf5e883866acad546_69.png)

Remember that unless you are performing a simple concatenation。

 you'll need to define the key variables to direct the joining process。



![](img/524670c3d1a92a9cf5e883866acad546_71.png)

Next， you'll learn about combining tables together in MatTLb， and then you can practice on your own。



![](img/524670c3d1a92a9cf5e883866acad546_73.png)