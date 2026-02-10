# 谷歌高阶数据分析 2：《Python入门》get-started-with-python（中英双字） - P36：36_04_02_字典方法.zh_en - GPT中英字幕课程资源 - BV1Jm4y177BW

![](img/8ebd2a8cbae012c4919ea3782e44c56c_0.png)

Previously， you were introduced to dictionaries and learned a little bit about how they work。

 Let's continue our exploration of dictionaries and how to use them。😊。

Let's consider a previous example and revisit the women's basketball team roster。

 recall that the roster was encoded as a list of tuples。Each tuple represented the name。

 age and position of a player on the team。 The list of tus was useful when we had a single team and one player per position。

What if we add more players beyond the starting 5， A dictionary can help us organize their data according to our specific needs。

 For example， what if we want to be able to look up players by their position。

 We can create a dictionary where the positions are the keys and the players are the values。

 Each represented as a tuple that contains two values， their name and age。

We could retype the information into a dictionary or cut and paste it。

 but if you find yourself doing these things， you can take this as an opportunity to improve your coding skills。

Consider that this is the information for just 10 players。 What if we had data for the whole league。

We can convert this information to a dictionary with a for loop and some conditional logic。

Will begin by instantiating an empty dictionary and designing it to a variable named new team。

 The idea is to loop over each tuple in the list。Extract the position and assign it as a dictionary key and extract the player's name and age and assign them as a tuple within a list representing the value for that key。

The process would repeat for each iteration of the loop。

Until all of the players are recorded in the dictionary。

Notice that each position is only represented once as a key， so the final dictionary has five keys。

 and there are two players in the list at each key's value。Now， let's write the loop。First。

 we'll assign the empty dictionary to a variable called new team。

 then we'll write a for loop that unpacks the information in the original tus for name， age。

 position and team， and here's where the conditional logic comes in if the position already exists as a keyword in our dictionary。

 then we want to append the name and H tuple to the list of tus。Remember。

 the value for each key will be a list that contains tuples of player information。

If the position does not already exist as a key word in the dictionary， we'll have to assign it。

 we'll use an out statement to do this。With only a few lines of code。

 we have converted our list of tus to a dictionary。Let's check that。 It works。It sure does。

Creating dictionaries this way is a common practice in data analytics of Python。

 So learning this process will help make you a more capable data professional。Now。

 let's learn about some useful methods that we can use on dictionaries to really take advantage of their power。

Specifically， we'll discuss the keys， values and items methods。If you run a loop over a dictionary。

 the loop will only access the keys， not the values。 For example。

 if we loop over the dictionary we just created and print each iteration。

 the computer will return five positions， the keys of the dictionary。

But you don't need to write a loop every time you want to access the keys of your dictionary。

That's what the keys method is for。The Keys method lets you retrieve only the dictionary's keys。

Returning to our new team dictionary， when we apply the keys method to the dictionary。

 the computer returns a list of all its keys。Similarly。

 the values method lets you retrieve only the dictionary's values。

When applied to our new team dictionary， we get the values returned as a list。

Since our values are lists of tus， it means the result of calling this method is a list of lists of tus。

But what if you want to access both the keys and their values， you can using the items method。

 which lets you retrieve both the dictionary's keys and values。

Let's use a loop to print what the items method returns， so the output is prettier。



![](img/8ebd2a8cbae012c4919ea3782e44c56c_2.png)

Dictionaries make storing and retrieving data fast and efficient。

Keep exploring the many things you can do with them。With time。

 you'll find that they become an important tool in your data analytics toolbox。

