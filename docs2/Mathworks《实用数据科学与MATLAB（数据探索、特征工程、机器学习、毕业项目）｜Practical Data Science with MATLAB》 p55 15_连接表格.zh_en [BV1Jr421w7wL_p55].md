# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p55 15_连接表格.zh_en [BV1Jr421w7wL_p55]

🎼，If you're flying within the United States， there are lots of possible destinations。

But the ones accessible with a direct flight depends on where you start。

And what if you're in a place that has two major airports like New York City？Well。

 then you'll have to consider the destinations from both of them。

This video walks through the joining steps required to produce from the flights data set this map。



![](img/de313bc586be0350b0aea3eae75ac2f4_1.png)

Which shows all of the destinations available to New York City。

Regardless of whether you fly out of John F。 Kennedy or Laguardia Airport。

These steps incorporate different joining methods that you learned about earlier。



![](img/de313bc586be0350b0aea3eae75ac2f4_3.png)

You can follow along with this video using the live script named Joining Tables。



![](img/de313bc586be0350b0aea3eae75ac2f4_5.png)

First， you need to import the flight's data。You have the option to import either the whole year using a file data store。

Or just a single month with the custom import function。In this example。

 only the month of September is imported。

![](img/de313bc586be0350b0aea3eae75ac2f4_7.png)

Next， you want to create two tables。One for each set of flights originating from JFK or LGA。

 which are the two airports in New York City。Finally。

 you want to group the flights in each table by their destination。



![](img/de313bc586be0350b0aea3eae75ac2f4_9.png)

This produces a list of all possible destinations for each airport。

Along with the total number of flights for the time period you've imported。



![](img/de313bc586be0350b0aea3eae75ac2f4_11.png)

Now you're ready to start joining。This example has a live task to assist with the process。



![](img/de313bc586be0350b0aea3eae75ac2f4_13.png)

A live task is an app you can insert into your script that performs a specific set of operations。



![](img/de313bc586be0350b0aea3eae75ac2f4_15.png)

You can find all of the available live tasks in the Live Edor tab。



![](img/de313bc586be0350b0aea3eae75ac2f4_17.png)

But for now， you'll just use the one for joining tables。Within the live taskask。

 you have several options for modifying the input， output and options available when joining tables。

At the top， you can see that the output will be saved to the variable summary and YC。

To select which two tables to join， use the drop down menus for the left and right tables。Next。

 choose the key variable， also known as the merging variable to direct the joining process。



![](img/de313bc586be0350b0aea3eae75ac2f4_19.png)

And finally， specify which joining method to use。For now。

 just stick with outer join so that the result will include all rows from both tables。



![](img/de313bc586be0350b0aea3eae75ac2f4_21.png)

But later， take some time to explore the other options。



![](img/de313bc586be0350b0aea3eae75ac2f4_23.png)

Notice that the output has a separate destination column for each input table。

 one for JFK and one for Laoria。This is in case you want to keep track of which keys came from which table。

Now select the option to combine the key variables。

Because live tasks execute whenever you change an option， you can immediately see the new result。

Which now has just one destinations column。

![](img/de313bc586be0350b0aea3eae75ac2f4_25.png)

Moving on， remember that each destination marker in the final visualization map was sized by the average number of flights on that route per day。

This next section of code sums the number of flights from both JFK and Lauguardia。



![](img/de313bc586be0350b0aea3eae75ac2f4_27.png)

And then divides by the number of days to get flights per day。



![](img/de313bc586be0350b0aea3eae75ac2f4_29.png)

You're almost there。 What's missing is the geographic location for each destination。



![](img/de313bc586be0350b0aea3eae75ac2f4_31.png)

Which isn't stored in the flight's data。 However， it is a variable in the airport's CSV file。

 So you'll need to import that file as a table。Next， you have to convert the airport column。

 which contains the three letter code for each destination。From a string into a categorical variable。

This is because the key variables in both tables need to be the same type。

Now you're ready to join the flights and airport data together。Again。

 a live task is used for this operation。 However， all you see now is the code。

That's because you can hide the interactive controls from the tasks menu。



![](img/de313bc586be0350b0aea3eae75ac2f4_33.png)

Upon showing the controls， you can see how the task was configured。



![](img/de313bc586be0350b0aea3eae75ac2f4_35.png)

Notice that the result has more information than you need， such as a column for city and state。

How can you remove these unwanted variables？

![](img/de313bc586be0350b0aea3eae75ac2f4_37.png)

Well， you can always convert a live task into editable code from the task menu。



![](img/de313bc586be0350b0aea3eae75ac2f4_39.png)

This enables you to specify as an option， which variables to keep from each table。



![](img/de313bc586be0350b0aea3eae75ac2f4_41.png)

Though removing irrelevant data is not required， in this case， it does help clean up your output。



![](img/de313bc586be0350b0aea3eae75ac2f4_43.png)

Finally， you're ready to plot your data using the geobu function。



![](img/de313bc586be0350b0aea3eae75ac2f4_45.png)

Feel free to experiment with this live script to get a feel for how different joining options work in different situations。

For instance， how does a left outer join compare to the outer join you just tried。



![](img/de313bc586be0350b0aea3eae75ac2f4_47.png)

![](img/de313bc586be0350b0aea3eae75ac2f4_48.png)

And if you want an extra challenge， see if you can use table joining methods to plot every airport you can reach from New York City。

 not just directly， but after a single layover。🎼。

![](img/de313bc586be0350b0aea3eae75ac2f4_50.png)