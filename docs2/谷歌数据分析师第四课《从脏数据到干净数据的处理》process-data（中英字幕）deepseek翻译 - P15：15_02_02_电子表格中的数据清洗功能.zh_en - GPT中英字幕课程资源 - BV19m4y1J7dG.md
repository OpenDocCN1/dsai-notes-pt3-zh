# 谷歌数据分析师第四课《从脏数据到干净数据的处理》process-data（中英字幕）deepseek翻译 - P15：15_02_02_电子表格中的数据清洗功能.zh_en - GPT中英字幕课程资源 - BV19m4y1J7dG

![](img/f07b9342c3a1351868b97aa4c15cfa47_0.png)

Hi again。 As you learned earlier， there's a lot of different ways to clean up data。

 Ive shown you some examples of how you can clean data manually。

 such as searching for and fixing misspellings or removing empty spaces and duplicates。

 We also learned that lots of spreadsheet applications have tools that help simplify and speed up the data cleaning process。

😊，There's a lot of great efficiency tools that data analysts use all the time。

 such as conditional formatting， removing duplicates， formatting dates。

 fixing text strings and substrs， and splitting text to columns。

 We'll explore those in more detail now。😊，The first is something called conditional formatting。

Conditional formatting is a spreadsheet tool that changes how cells appear when values meet specific conditions。

Likewise， it can let you know when a cell does not meet the conditions you've set。

Visual cues like this are very useful for data analysts。

 especially when we're working in a large spreadsheet with lots of data。

Making certain data points stand out makes the information easier to understand and analyze。

 and for cleaning data， knowing when the data doesn't follow the condition is very helpful。

 Let's return to the logistics association spreadsheet to check out conditional formatting in action。

 We'll use conditional formatting to highlight blank cells。 That way。

 we know where there' is missing information so we can add it to the spreadsheet。To do this。

 we'll start by selecting the range we want to search For this example。

 we're not focused on address 3。And address 5。So the fields will include all the columns in our spreadsheets。

 except for F and H。Next， we'll go to format and choose conditional formatting。Great。

 our range is automatically indicated in the field。

The format rule will be to format cells if the cell is empty。Finally。

 we'll choose the formatting style。I'm going to pick a shade of bright pink。

 so my blanks really stand out。Then click done。And the blank cells are instantly highlighted。Okay。

 the next spreadsheet tool removes duplicates。 As you've learned before。

 it's always smart to make a copy of the data set before removing anything。 so let's do that now。

Great， now we can continue。You might remember that our example spreadsheet has one association member listed twice。

To fix that。Go to data。And select Remove duplicates。

Remove duplicateuplicates is a tool that automatically searches for and eliminates duplicate entries from a spreadsheet。

Choose data has head a row。Because our spreadsheet has a row at the very top that describes the contents of each column。

Next， select all。Because we want to inspect our entire spreadsheet。Finally， remove duplicates。

You'll notice the duplicate road was found and immediately removed。

Another useful spreadsheet tool enables you to make formats consistent。For example。

 some of the dates in this spreadsheet are in a standard date format。

This could be confusing if you wanted to analyze when association members joined。

 how often they renewed their memberships or how long they've been with the association。

To make all of our dates consistent， first select column J。Then go to format。Select number。Dandy。Now。

 all of our dates have a consistent format。Before we go over the next tool。

 I want to explain what a text string is。In data analytics。

 a text string is a group of characters within a cell， most often composedive letters。

An important characteristic of a text string is its length， with just the number of characters in it。

You'll learn more about that soon。 For now， it's also useful to note that a sub string is a smaller subset of a text string。

Okay， now let's talk about split。Split is a tool that divides a text string around the specified character and puts each fragment into a new and separate cell。

Split is helpful when you have more than one piece of data in a cell。

 and you want to separate them out。This might be of person's first and last name listed together。

 or it could be a cell that contains someone city， state， country and zip code。

 But you actually want each of those in its own column。

So let's say this association wanted to analyze all of the different professional certifications its members have earned。

To do this， you want each certification separated out into its own column。Right now。

 the certifications are separated by a comma。That's the specified text separating each item。

 also called the delimiter。Let's get them separated。Highlight the column。Then select data。

And split text to columns。This spreadsheet application automatically knew that the comma was a delimiter and separated each certification。

But sometimes you might need to specify what the delimiter should be。 You can do that here。

Split text to columns is also helpful for fixing instances of numbers stored at text。

Sometimes values in your spreadsheet will seem like numbers， but they're formatted as text。

This can happen when copying pasting from one place to another， or if the formatting is wrong。

For this example， let's check out our new spreadsheet from a cosmetics maker。

If a data analyst wanted to determine total profits， they could add up everything in column F。

But there's a problem。 One of the cells has an error。If you check into it。

 you learn that the 707 in this cell is text and can't be changed into a number。

So when the spreadsheet tries to multiply the cost of the product。Buy the number of units sold。

It's unable to make the calculation。But if we select the orders column。

And choose split text to columns。The error is resolved because now it can be treated as a number。

Coming up， you'll learn about a tool that does just the opposite。

Concatenate is a function that joins multiple text strings into a single string。



![](img/f07b9342c3a1351868b97aa4c15cfa47_2.png)

Spreadsheets are a very important part of data analytics。

 They save data analysts time and effort and help us eliminate errors each and every day。

Here you learn about some of the most common tools that we use， but there's a lot more to come。Next。

 we'll learn even more about data cleaning with spreadsheet tools。Bye for now。

