# IBM数据工程专业证书第3课：《Python数据工程项目课程（IBM）》python-project-for-data-engineering - P4：3_可选网络抓取.zh_en - GPT中英字幕课程资源 - BV1xz4y1W7Gb

![](img/64afc6d80ff3abd2216cf6da2d84a609_0.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_1.png)

In this video， we will cover web scraping After watching this video。

 you will be able to define web scraping。 Under the role of beautiful soup objects。 applyly the find。

 underscore all method and webs scrappe a website。 What would you do if you wanted to analyze hundreds of points of data to find the best players of a sports team。

 Would you start manually copying and pasting information from different websites into a spreadsheet。

 spending hours trying to find the right data and eventually giving up because the task was too overwhelming。

 That is where webs scraping can help。 Webs scraping is a process that can be used to automatically extract information from a website and can easily be accomplished within a matter of minutes and not ours。

😊。

![](img/64afc6d80ff3abd2216cf6da2d84a609_3.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_4.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_5.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_6.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_7.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_8.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_9.png)

To get started， we just need a little Python code and the help of two modules named requests and beautiful soup。

 Let us say you were asked to find the name and salary of players in a national basketball league from the following web page First。

 we import beautiful soup。 We can store the web page Hm as a string in the variable H to parse a document。

 pass it into the beautiful soup constructor。 We get the beautiful soup object soup。

 which represents the document as a nested data structure。

 Bea soup represents H as a set of treelike objects with methods used to parse the H。

 We will review the beautiful soup object using the beautiful soup object soup we created。

 The tag object corresponds to an H tag in the original document。 For example， the tag title。

 Consider the tag H3。 If there is more than one tag with the same。😊。



![](img/64afc6d80ff3abd2216cf6da2d84a609_11.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_12.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_13.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_14.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_15.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_16.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_17.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_18.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_19.png)

Name the first element with that tag is selected in this case with Lebron James。

 we see the name is enclosed in the bold attribute B to extract it， use the tree representation。

 So let us use the tree representation。 The variable tag dash object is located here。

 We can access the child of the tag or navigate down the branch as follows。



![](img/64afc6d80ff3abd2216cf6da2d84a609_21.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_22.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_23.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_24.png)

You can navigate up the tree by using the parent attribute。 The variable tag child is located here。

 and we can access the parent。 This is the original tag object。

 We can also find the sibling of tag object。 We simply use the next dash sibling attribute。

 We can find the sibling of sibling1。 We simply use the next sibling attribute。

 Consider the tag dash child object。 You can access the attribute name and value as a key value pair in a dictionary As follows。

 You can return the content as a navigable string。 This is like a python string that supports beautiful soup functionality。



![](img/64afc6d80ff3abd2216cf6da2d84a609_26.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_27.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_28.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_29.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_30.png)

Now， let us review the method。 Find all。 This is a filter。

 You can use filters to filter based on a tag's name， its attributes， the text of a string。

 or on some combination of these。 And consider the list of pizza places。 like before。

 create a beautiful soup object。 But this time， name it table。

 The find underscore all method looks through a tag's descendants and retrieves all descendants that match your filters。

 App it to the table with the tag T R。 The result is a python iterable， just like a list。

 Each element is a tag object for T R。 This corresponds to each row in the list。

 including the table header。😊。

![](img/64afc6d80ff3abd2216cf6da2d84a609_32.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_33.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_34.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_35.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_36.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_37.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_38.png)

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

![](img/64afc6d80ff3abd2216cf6da2d84a609_40.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_41.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_42.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_43.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_44.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_45.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_46.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_47.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_48.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_49.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_50.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_51.png)

Sign it to the variable page， then create a beautiful soup object soup from the variable page。

 it will allow you to parse through the HTML page and you can now scrape the page check out the labs for more。



![](img/64afc6d80ff3abd2216cf6da2d84a609_53.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_54.png)

![](img/64afc6d80ff3abd2216cf6da2d84a609_55.png)