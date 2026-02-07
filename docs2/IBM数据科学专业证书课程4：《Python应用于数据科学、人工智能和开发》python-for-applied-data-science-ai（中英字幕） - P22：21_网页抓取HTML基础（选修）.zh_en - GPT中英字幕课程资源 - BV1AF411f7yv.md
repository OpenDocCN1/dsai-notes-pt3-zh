# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P22：21_网页抓取HTML基础（选修）.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

![](img/094def98038d41563c92daa7ae11b99b_0.png)

![](img/094def98038d41563c92daa7ae11b99b_1.png)

In this video， we will review hypertext markup language or H for web scraping Lots of useful data is available on web pages。

 such as real estate prices and solutions to coding questions。

 The web Wikipedia is a repository of the world's information If you have an understanding of H you can use Python to extract this information In this video you will review the HTML of a basic web page。

 Under the composition of an H tag Under HTML trees and understand HTML tables。

 Let us say you had a request to find the name and salary of players in a national basketball league from the following page The webage is comprised of H It consists of text surrounded by a series of bluett elements enclosed in angle brackets called tags The tags tell the browser how to display the content The data we require is in this text。



![](img/094def98038d41563c92daa7ae11b99b_3.png)

![](img/094def98038d41563c92daa7ae11b99b_4.png)

![](img/094def98038d41563c92daa7ae11b99b_5.png)

![](img/094def98038d41563c92daa7ae11b99b_6.png)

![](img/094def98038d41563c92daa7ae11b99b_7.png)

![](img/094def98038d41563c92daa7ae11b99b_8.png)

![](img/094def98038d41563c92daa7ae11b99b_9.png)

![](img/094def98038d41563c92daa7ae11b99b_10.png)

![](img/094def98038d41563c92daa7ae11b99b_11.png)

The first portion contains the doc type H， which declares this document is an H document。

 H element is the root element of an H page and head element contains meta information about the H page Next we have the body。

 This is what is displayed on the web page。 This is usually the data we are interested in。

 We see the elements with an H3。 This means type 3 heading， which makes the text larger and bold。

 These tags have the names of the players。 notice the data is enclosed in the elements。

 It starts with an H3 in brackets and ends in a slash H3 in brackets。

 There is also a different tag P This means paragraph。 H P tag contains a player's salary。

 Let us take a closer look at the composition of an H tag Here is an example of an H anchor tag。

 It will display IBM。 and when you click。

![](img/094def98038d41563c92daa7ae11b99b_13.png)

![](img/094def98038d41563c92daa7ae11b99b_14.png)

![](img/094def98038d41563c92daa7ae11b99b_15.png)

![](img/094def98038d41563c92daa7ae11b99b_16.png)

![](img/094def98038d41563c92daa7ae11b99b_17.png)

![](img/094def98038d41563c92daa7ae11b99b_18.png)

![](img/094def98038d41563c92daa7ae11b99b_19.png)

![](img/094def98038d41563c92daa7ae11b99b_20.png)

![](img/094def98038d41563c92daa7ae11b99b_21.png)

![](img/094def98038d41563c92daa7ae11b99b_22.png)

It will send you to IBM com we have the tag name in this case a this tag defines a hyperlink。

 which is used to link from one page to another。 It is helpful to think of each tag name as a class in Python and each individual tag as an instance We have an opening or start tag and we have the N tag This has the tag name preceded by a s These tags contain the content In this case what is displayed on the web page We have the attribute This is composed of the attribute name and attribute value In this case it is the URL to the destination web page real web pages are more complex and depending on your browser。

 you can select the h element then click In The result will give you the ability to inspect the H There is also other types of content such as CSS and ja that we will not go over in this course the actual。



![](img/094def98038d41563c92daa7ae11b99b_24.png)

![](img/094def98038d41563c92daa7ae11b99b_25.png)

![](img/094def98038d41563c92daa7ae11b99b_26.png)

![](img/094def98038d41563c92daa7ae11b99b_27.png)

![](img/094def98038d41563c92daa7ae11b99b_28.png)

![](img/094def98038d41563c92daa7ae11b99b_29.png)

![](img/094def98038d41563c92daa7ae11b99b_30.png)

![](img/094def98038d41563c92daa7ae11b99b_31.png)

Is shown here。 Each HM L document can actually be referred to as a document tree。

 Let us go over a simple example。 tags may contain strings and other tags。

 These elements are the tag's children。 We can represent this as a family tree。

 Each nested tag is a level in the tree。 The tag， Hm L tag contains the head and body tag。

 The head and the body tag are the descendants of the HM L tag。 In particular。

 they are the children of the HM L tag。 Hml tag is their parent。

 The head and body tag are siblings as they are on the same level。

 Tile tag is the child of the head tag and its parent is the head tag。

 The title tag is a descendant of the HM L tag， but not its child。

 The heading and paragraph tags are the children of the body tag。

 and as they are all children of the body tag。 They are siblings of each other。

 The bold tag is a child of the heading tag。

![](img/094def98038d41563c92daa7ae11b99b_33.png)

![](img/094def98038d41563c92daa7ae11b99b_34.png)

![](img/094def98038d41563c92daa7ae11b99b_35.png)

![](img/094def98038d41563c92daa7ae11b99b_36.png)

![](img/094def98038d41563c92daa7ae11b99b_37.png)

![](img/094def98038d41563c92daa7ae11b99b_38.png)

![](img/094def98038d41563c92daa7ae11b99b_39.png)

![](img/094def98038d41563c92daa7ae11b99b_40.png)

![](img/094def98038d41563c92daa7ae11b99b_41.png)

![](img/094def98038d41563c92daa7ae11b99b_42.png)

![](img/094def98038d41563c92daa7ae11b99b_43.png)

The content of the tag is also part of the tree， but this can get unwielly to draw。



![](img/094def98038d41563c92daa7ae11b99b_45.png)

Next， let us review HTML tables to define an HTML table。 We have the table tag。

 Each table row is defined with a Tr tag， and you can also use a table header tag for the first row the table row cell contains a set of TD tags。

 Each defines a table cell for the first row first cell we have for the first row second cell we have。



![](img/094def98038d41563c92daa7ae11b99b_47.png)

![](img/094def98038d41563c92daa7ae11b99b_48.png)

![](img/094def98038d41563c92daa7ae11b99b_49.png)

![](img/094def98038d41563c92daa7ae11b99b_50.png)

![](img/094def98038d41563c92daa7ae11b99b_51.png)

And so on for the second row we have and for the second row first cell we have。



![](img/094def98038d41563c92daa7ae11b99b_53.png)

![](img/094def98038d41563c92daa7ae11b99b_54.png)

And for the second row， second cell we have。And so on， we now have some basic knowledge of HTML。

 Now let us try and extract some data from a web page。



![](img/094def98038d41563c92daa7ae11b99b_56.png)

![](img/094def98038d41563c92daa7ae11b99b_57.png)