# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p32 31_分类数据介绍.zh_en [BV1Jr421w7wL_p32]

🎼。

![](img/2bcb1a3e09593bf97000016549c86c6c_1.png)

Throughout this course， you've had several chances to look at your weather data set and what kind of data it contains。

Previously， you saw how MATLb data types were used in the data。



![](img/2bcb1a3e09593bf97000016549c86c6c_3.png)

In this video， you'll learn more about how to work with categorical data。



![](img/2bcb1a3e09593bf97000016549c86c6c_5.png)

Categories are everywhere in daily life。 When you wake up。

 your status changes from a category of sleep to one of a awake。

 You could categorize the whole human population into these two groups。

You'd probably find it more convenient to represent these states with a known label。

 rather than a number。 A categorical variable always has a finite set of discrete categories。

 In this example， there would be just two， asleep and awake。



![](img/2bcb1a3e09593bf97000016549c86c6c_7.png)

Consider the data set you imported previously。 Several of the table variables were imported as categorical variables。



![](img/2bcb1a3e09593bf97000016549c86c6c_9.png)

For example， state， month and event type all contain discrete categories。Each value in month。

 for example， will be one of the 12 months of the year。

Let's take a closer look at the data and explore the seasonality of the weather events。



![](img/2bcb1a3e09593bf97000016549c86c6c_11.png)

Which month had the most events and what types of events occurred。



![](img/2bcb1a3e09593bf97000016549c86c6c_13.png)

After loading the data， create a histogram with the month from the table。



![](img/2bcb1a3e09593bf97000016549c86c6c_15.png)

You can now see the number of events grouped by month。

Notice that the months are sorted alphabetically， which is the default setting。

 the categories can have a natural order to see the seasonal pattern。

 you will need to reorder the month category。

![](img/2bcb1a3e09593bf97000016549c86c6c_17.png)

![](img/2bcb1a3e09593bf97000016549c86c6c_18.png)

To do this， you begin by creating a vector of strings that contains the names of the categories in the required order。

 then call the function reorder cats。The first input is the categorical table variable to be reordered。

 and the second input is the vector that defines the order。

The result of the reordering is assigned back to data。month。



![](img/2bcb1a3e09593bf97000016549c86c6c_20.png)

The resulting histogram now reflects the changed order， and you can clearly see a seasonality。

The greatest number of events occur during the summer months。 What is happening during those months？

Extract the data for June and look at the next set of data represented by a categorical data type。

 the type of event， to find out what types of events occurred。



![](img/2bcb1a3e09593bf97000016549c86c6c_22.png)

Select the data for June by clicking in the table and filtering the variable month for June。

Now copy the generated code and paste it in the live script。

Then rename the variable so you don't overwrite the original data set。

Now let's find out what kind of weather events occurred in June。



![](img/2bcb1a3e09593bf97000016549c86c6c_24.png)

Use a histogram again on the event type， it shows you exactly how many floods or other type of events happened。

Look closely and you'll notice that every category is displayed。

 including those that have zero events。For example， in the northern hemisphere。

 you would not expect winter weather events to occur in June。

 because there are so many categories It is difficult to see the trends。

 Let's remove the unused categories to get a better view of the meaningful data。



![](img/2bcb1a3e09593bf97000016549c86c6c_26.png)

Select the table that contains the June data。And edit the categories for the event type。



![](img/2bcb1a3e09593bf97000016549c86c6c_28.png)

Here you see their order， the names for the categories and the counts。

 which represent how many times each event occurred。

Soword this view by clicking the arrow next to counts。

 so all event types with counts equal to0 are listed first。

Now select these event types and click Removeve selecteded。



![](img/2bcb1a3e09593bf97000016549c86c6c_30.png)

Then click OK。And copy the generated code into your live script。

Let's see how this changed the histogram。

![](img/2bcb1a3e09593bf97000016549c86c6c_32.png)

Now you see only the types of events that actually occurred in June。



![](img/2bcb1a3e09593bf97000016549c86c6c_34.png)

At this point in your analysis， it's a good idea to take a close look at your categories。

 Do the displayed categories accurately represent the question you're asking。 Remember。

 you're identifying the type of events that occurred。

Some of the event types are closely related and should be merged into one category。

 like the marine events， for example。

![](img/2bcb1a3e09593bf97000016549c86c6c_36.png)

To do this， first go back to your table。

![](img/2bcb1a3e09593bf97000016549c86c6c_38.png)

There， select the event type again to edit the categories。

Here you add a new category and name it marine events。Next。

 you merge all the related marine type categories into the newly created marine events category。



![](img/2bcb1a3e09593bf97000016549c86c6c_40.png)

This interaction also generates the code that you can learn from or simply copy into your live script。

Here you see an example of a histogram after merging additional categories。



![](img/2bcb1a3e09593bf97000016549c86c6c_42.png)

For this data set， thunderstorm wind is the most frequent event in June。

 You could dig deeper and answer questions about the geographical distribution of the thunderstorms。



![](img/2bcb1a3e09593bf97000016549c86c6c_44.png)

By now， you know how to interactively filter the event type for thunderstorm wind。

When using the generated code， don't forget to rename the variable so you don't overwrite your original data。

To finish your analysis， use the subset of the data containing the June thunderstorms to visualize where they occurred。

Pass the latitude and longitudes of the subset to the geodensity function to see the distribution of storms。

As you've seen， you can use categories to select groups of data。

 such as a specific month or an event type you're interested in。

You have seen the corresponding code generated automatically from your actions。

 which will help you to learn the functions and reuse them for other purposes later。

Use this opportunity to learn more about the functions you've used in their synyntax by selecting a function and pressing F1 to access the help quickly。

In an upcoming video， you will take the next step and use categories to perform group statistics。



![](img/2bcb1a3e09593bf97000016549c86c6c_46.png)