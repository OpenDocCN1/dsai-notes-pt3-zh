# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P88：22_网络抓取.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/b6f3d91a9736a733f8f89df301744430_0.png)

![](img/b6f3d91a9736a733f8f89df301744430_1.png)

In this video， we will cover web scraping After watching this video。

 you will be able to define web scraping。 Under the role of beautiful soup objects。 applyly the find。

 underscore all method and webs scrappe a website。 What would you do if you wanted to analyze hundreds of points of data to find the best players of a sports team。

 Would you start manually copying and pasting information from different websites into a spreadsheet。

 spending hours trying to find the right data and eventually giving up because the task was too overwhelming。

 That is where webs scraping can help。 Webs scraping is a process that can be used to automatically extract information from a website and can easily be accomplished within a matter of minutes and not ours。

😊。

![](img/b6f3d91a9736a733f8f89df301744430_3.png)

![](img/b6f3d91a9736a733f8f89df301744430_4.png)

![](img/b6f3d91a9736a733f8f89df301744430_5.png)

![](img/b6f3d91a9736a733f8f89df301744430_6.png)

![](img/b6f3d91a9736a733f8f89df301744430_7.png)

![](img/b6f3d91a9736a733f8f89df301744430_8.png)

![](img/b6f3d91a9736a733f8f89df301744430_9.png)

To get started， we just need a little Python code and the help of two modules named requests and beautiful soup。

 Let us say you were asked to find the name and salary of players in a national basketball league from the following web page First。

 we import beautiful soup。 We can store the web page Hm as a string in the variable H to parse a document。

 pass it into the beautiful soup constructor。 We get the beautiful soup object soup。

 which represents the document as a nested data structure。

 Bea soup represents H as a set of treelike objects with methods used to parse the H。

 We will review the beautiful soup object using the beautiful soup object soup we created。

 The tag object corresponds to an H tag in the original document。 For example， the tag title。

 Consider the tag H3。 If there is more than one tag with the same。😊。



![](img/b6f3d91a9736a733f8f89df301744430_11.png)

![](img/b6f3d91a9736a733f8f89df301744430_12.png)

![](img/b6f3d91a9736a733f8f89df301744430_13.png)

![](img/b6f3d91a9736a733f8f89df301744430_14.png)

![](img/b6f3d91a9736a733f8f89df301744430_15.png)

![](img/b6f3d91a9736a733f8f89df301744430_16.png)

![](img/b6f3d91a9736a733f8f89df301744430_17.png)

![](img/b6f3d91a9736a733f8f89df301744430_18.png)

![](img/b6f3d91a9736a733f8f89df301744430_19.png)

Name the first element with that tag is selected in this case with Lebron James。

 we see the name is enclosed in the bold attribute B to extract it， use the tree representation。

 So let us use the tree representation。 The variable tag dash object is located here。

 We can access the child of the tag or navigate down the branch as follows。



![](img/b6f3d91a9736a733f8f89df301744430_21.png)

![](img/b6f3d91a9736a733f8f89df301744430_22.png)

![](img/b6f3d91a9736a733f8f89df301744430_23.png)

![](img/b6f3d91a9736a733f8f89df301744430_24.png)

You can navigate up the tree by using the parent attribute。 The variable tag child is located here。

 and we can access the parent。 This is the original tag object。

 We can also find the sibling of tag object。 We simply use the next dash sibling attribute。

 We can find the sibling of sibling1。 We simply use the next sibling attribute。

 Consider the tag dash child object。 You can access the attribute name and value as a key value pair in a dictionary As follows。

 You can return the content as a navigable string。 This is like a python string that supports beautiful soup functionality。



![](img/b6f3d91a9736a733f8f89df301744430_26.png)

![](img/b6f3d91a9736a733f8f89df301744430_27.png)

![](img/b6f3d91a9736a733f8f89df301744430_28.png)

![](img/b6f3d91a9736a733f8f89df301744430_29.png)

![](img/b6f3d91a9736a733f8f89df301744430_30.png)

![](img/b6f3d91a9736a733f8f89df301744430_31.png)

Now， let us review the method。 Find all。 This is a filter。

 You can use filters to filter based on a tag's name， its attributes， the text of a string。

 or on some combination of these。 And consider the list of pizza places。 like before。

 create a beautiful soup object。 But this time， name it table。

 The find underscore all method looks through a tag's descendants and retrieves all descendants that match your filters。

 App it to the table with the tag T R。 The result is a python iterable， just like a list。

 Each element is a tag object for T R。 This corresponds to each row in the list。

 including the table header。😊。

![](img/b6f3d91a9736a733f8f89df301744430_33.png)

![](img/b6f3d91a9736a733f8f89df301744430_34.png)

![](img/b6f3d91a9736a733f8f89df301744430_35.png)

![](img/b6f3d91a9736a733f8f89df301744430_36.png)

![](img/b6f3d91a9736a733f8f89df301744430_37.png)

![](img/b6f3d91a9736a733f8f89df301744430_38.png)

![](img/b6f3d91a9736a733f8f89df301744430_39.png)

Each element is a tag object。 So consider the first row。 For example。

 we can extract the first table cell。 We can also iterate through each table cell。 First。

 we iterate through the list table rows via the variable row。

 Each element corresponds to a row in the table。 We can apply the method。

 find all to find all the table cells。 Then we can iterate through the variable cells for each row。

 for each iteration。 The variable cell corresponds to an element in the table for that particular row。

 and we continue to iterate through each element and repeat the process for each row。

 Let us see how to apply beautiful soup to a web page。 to scrape a web page。

 We also need the requests library。 The first step is to import the modules that are needed。

 Use the get method from the requests library to download the web page。 The input is the URL。

 Use the text attribute to get the text and。😊。

![](img/b6f3d91a9736a733f8f89df301744430_41.png)

![](img/b6f3d91a9736a733f8f89df301744430_42.png)

![](img/b6f3d91a9736a733f8f89df301744430_43.png)

![](img/b6f3d91a9736a733f8f89df301744430_44.png)

![](img/b6f3d91a9736a733f8f89df301744430_45.png)

![](img/b6f3d91a9736a733f8f89df301744430_46.png)

![](img/b6f3d91a9736a733f8f89df301744430_47.png)

![](img/b6f3d91a9736a733f8f89df301744430_48.png)

![](img/b6f3d91a9736a733f8f89df301744430_49.png)

![](img/b6f3d91a9736a733f8f89df301744430_50.png)

![](img/b6f3d91a9736a733f8f89df301744430_51.png)

![](img/b6f3d91a9736a733f8f89df301744430_52.png)

Sign it to the variable page， then create a beautiful soup object soup from the variable page。

 it will allow you to parse through the HTML page and you can now scrape the page check out the labs for more。



![](img/b6f3d91a9736a733f8f89df301744430_54.png)

![](img/b6f3d91a9736a733f8f89df301744430_55.png)

![](img/b6f3d91a9736a733f8f89df301744430_56.png)