# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P8：7_读取json.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

![](img/f72d296ea6a2374eddec379d04cb5c43_0.png)

This lecture is going to be about reading JSON JSON is another file format that's a little bit similar to XML in a sense that is structured and it's also very commonly used on the internet。

 so JSON is short for JavaScript object notation， it's a lightweight for data storage and so it's very common in application programming interfaces which are ways that you can programmatically attack access the data for companies like Twitter or Facebook through URLs。



![](img/f72d296ea6a2374eddec379d04cb5c43_2.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_3.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_4.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_5.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_6.png)

Similar structure to XML in the sense that it's a structured language。

 but it's a very different syntax and format。

![](img/f72d296ea6a2374eddec379d04cb5c43_8.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_9.png)

The data are stored as numbers， strings， Booles， arrays， or objects。

 and so if you want to know a little bit more about JSON。

 the best place to start again as usual is actually a Wikipedia。

 this link will take you to a lot more information about JSON。



![](img/f72d296ea6a2374eddec379d04cb5c43_11.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_12.png)

So this is an example JSON file。 It actually comes from this is the API for Gitthub and this is actually the data about the reos that I am contributing to。

 And so what you can do is go here and look at this file and so there's a overall curly bracket that represents the sort of entire JSON object and then each of the different reos is inside of its own separate curly bracket And so each repo has a bunch of variables associated with it。

 So for example， the ID variable or the full name of the repo and all of that And so what you see is the structure of a JSON file is sort of the ID followed by a colon followed by the value of the variable and so you can have nested sort of structures within so for example。

 an array can be a component of a。

![](img/f72d296ea6a2374eddec379d04cb5c43_14.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_15.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_16.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_17.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_18.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_19.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_20.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_21.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_22.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_23.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_24.png)

The JSON object， so for example， the owner variable here actually has an array as the value。

 so you can see there's a colon and then there's another open curly bracket。

 and then there's a whole bunch of variables like the My login and the Avatar URL and all of that different information。



![](img/f72d296ea6a2374eddec379d04cb5c43_26.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_27.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_28.png)

So in R there's actually a very nice package for reading this data in that's called the JSON light package。

 So what you do is you actually just take the URL where the JSON appears So here's that URL and you pass it to the from JSON function and what you get out is the data frame。

 a structured data frame So if you look at the names of that data frame it's going to be all in the top level variables。

 things like ID and name and full name and so forth So one of those variables as you can see is owner So that's one of the components of this data frame and so if we drill down a little bit and look at the names of that particular variable you see names of JSON data owner So usually this would access one column of the data frame and so it turns out you can actually because of the flexibility of data frames and R store data frame within the data frame So within that column the sort of the column of the data the owner column there's actually a bunch of other information because you remember owner corresponded to an array of values and so you get again the login。

 the ID say。

![](img/f72d296ea6a2374eddec379d04cb5c43_30.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_31.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_32.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_33.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_34.png)

Avatar URL and so forth so we can drill down even further and so we can access say for example the login of all the different repos on this particular page and since we're only looking at the API for my repos you can see that the login is the same for all of them it's JT leak and every single case and so you can see there's one time for every single repo that exists in that data。



![](img/f72d296ea6a2374eddec379d04cb5c43_36.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_37.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_38.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_39.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_40.png)

And so another thing that you can do is actually you can take data sets that are data frames and R so at one example of the very classic dataset。

 the IIS dataset， you can turn it into a JSON dataset set by saying to JSO so this is nice if you're going to be exporting data that's going to be used by an API that requires JSON formatted data so here I've set pretty equal to true and that will give you nice indentation so it's easy to read the file when you look at it so if you look at this variable this variable is now a text variable and so what we can do is we can use the CA command to print it out and you can see that it's nicely structured like that。



![](img/f72d296ea6a2374eddec379d04cb5c43_42.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_43.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_44.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_45.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_46.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_47.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_48.png)

So you can actually take that JSON file we just created， so we took the IIS data set。

 we turned it into a JSON file with the two JSON command。

 we can then take that text and send it right back to a data frame using the from JSON command。



![](img/f72d296ea6a2374eddec379d04cb5c43_50.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_51.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_52.png)

So the interesting thing here is in the first example that we used it was actually a URL here。

 we actually pass the URL for the JSON file and here we're just passing it a variable name which corresponds to a text variable that can then be converted into a data frame so then if we look at the top of that data frame using the head command we see that you get back the IIS data set so if you just look at the IIS data set by itself。

 itll look exactly the same as using this file here。



![](img/f72d296ea6a2374eddec379d04cb5c43_54.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_55.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_56.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_57.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_58.png)

So if you want a little bit more information， you can go to JSON。

org this will give you more information about JSON in general and then a really nice tutorial on JSON Light that was basis for a lot of this lecture is right here at our bloggers and so you can take that take a look at that the JSON Light Bignette is also quite good and give you a lot more information so if you have a more complicated JSON structure that you need to get access to you can go check out those resources and they might give you a little bit more information。



![](img/f72d296ea6a2374eddec379d04cb5c43_60.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_61.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_62.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_63.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_64.png)