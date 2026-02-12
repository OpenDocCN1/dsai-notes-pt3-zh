# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P75：21_可选：用于网页抓取的HTML.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

![](img/cac513c8850cc8429384489642d09c3b_0.png)

![](img/cac513c8850cc8429384489642d09c3b_1.png)

In this video， we will review hypertext markup language or H for webs scraping。

 Lots of useful data is available on web pages， such as real estate prices and solutions to coding questions。

 The web Wikipedia is a repository of the world's information If you have an understanding of H。

 you can use Python to extract this information In this video you will review the HTML of a basic web page。

 Under the composition of an H tag Under HTML trees and understand HTML tables。

 Let us say you had a request to find the name and salary of players in a national basketball league from the following page The webage is comprised of H。

 It consists of text surrounded by a series of bluet elements enclosed in angle brackets called tags The tags tell the browser how to display the content The data we require is in this text。



![](img/cac513c8850cc8429384489642d09c3b_3.png)

![](img/cac513c8850cc8429384489642d09c3b_4.png)

![](img/cac513c8850cc8429384489642d09c3b_5.png)

![](img/cac513c8850cc8429384489642d09c3b_6.png)

![](img/cac513c8850cc8429384489642d09c3b_7.png)

The first portion contains the doc type H， which declares this document is an H document。

 H element is the root element of an H page and head element contains meta information about the H page Next we have the body。

 This is what is displayed on the web page。 This is usually the data we are interested in。

 We see the elements with an H3。 This means type 3 heading， which makes the text larger and bold。

 These tags have the names of the players。 noticeice the data is enclosed in the elements。

 It starts with an H3 in brackets and ends in a slash H3 in brackets。

 There is also a different tag P This means paragraph H P tag contains a player's salary。

 Let us take a closer look at the composition of an H tag Here is an example of an H anchor tag。

 It will display IBM。 and when you click。

![](img/cac513c8850cc8429384489642d09c3b_9.png)

![](img/cac513c8850cc8429384489642d09c3b_10.png)

![](img/cac513c8850cc8429384489642d09c3b_11.png)

![](img/cac513c8850cc8429384489642d09c3b_12.png)

It will send you to IBM com we have the tag name in this case a this tag defines a hyperlink。

 which is used to link from one page to another。 It is helpful to think of each tag name as a class in Python and each individual tag as an instance We have an opening or start tag and we have the N tag This has the tag name preceded by a slash These tags contain the content In this case what is displayed on the web page We have the attribute This is composed of the attribute name and attribute value In this case it is the URL to the destination web page Real web pages are more complex and depending on your browser。

 you can select the h element than click In The result will give you the ability to inspect the H。

 There is also other types of content such as CSS and ja that we will not go over in this course the actual。



![](img/cac513c8850cc8429384489642d09c3b_14.png)

![](img/cac513c8850cc8429384489642d09c3b_15.png)

![](img/cac513c8850cc8429384489642d09c3b_16.png)

I shown here。 Each HM L document can actually be referred to as a document tree。

 Let us go over a simple example。 tags may contain strings and other tags。

 These elements are the tag's children。 We can represent this as a family tree。

 Each nested tag is a level in the tree。 The tag， Hm L tag contains the head and body tag。

 The head and the body tag are the descendants of the HM L tag。 In particular。

 they are the children of the H tag。 Hml tag is their parent。

 The head and body tag are siblings as they are on the same level。

 Ti tag is the child of the head tag and its parent is the head tag。

 The title tag is a descendant of the HM L tag， but not its child。

 The heading and paragraph tags are the children of the body tag。

 and as they are all children of the body tag。 They are siblings of each other。

 The bold tag is a child of the heading tag。

![](img/cac513c8850cc8429384489642d09c3b_18.png)

The content of the tag is also part of the tree， but this can get unwielly to draw。



![](img/cac513c8850cc8429384489642d09c3b_20.png)

Next， let us review HTML tables to define an HTML table。 We have the table tag。

 Each table row is defined with a Tr tag， and you can also use a table header tag for the first row the table row cell contains a set of TD tags。

 Each defines a table cell for the first row first cell we have for the first row second cell we have。



![](img/cac513c8850cc8429384489642d09c3b_22.png)

And so on。For the second row， we have and for the second row first cell we have。

And for the second row， second cell we have。And so on。

 we now have some basic knowledge of HTML now let us try and extract some data from a web page。



![](img/cac513c8850cc8429384489642d09c3b_24.png)