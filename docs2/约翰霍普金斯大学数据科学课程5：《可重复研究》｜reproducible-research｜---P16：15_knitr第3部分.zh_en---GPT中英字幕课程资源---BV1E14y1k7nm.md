# 约翰霍普金斯大学数据科学课程5：《可重复研究》｜reproducible-research｜ - P16：15_knitr第3部分.zh_en - GPT中英字幕课程资源 - BV1E14y1k7nm

![](img/2d93f7847e8d09b57dcd69ff7684624f_0.png)

So how do we create a basic knitter document so I'm going to talk about this in the context of our studio because I think it's the easiest way to do it。

 there are other ways to do this so this is not really exclusive to our studio but it's just I'll just the example that I'll show here will be in our studio so if you click on the new document button on the upper left you'll see there are a variety of options and you can click the R markdown option to。



![](img/2d93f7847e8d09b57dcd69ff7684624f_2.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_3.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_4.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_5.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_6.png)

To create a new markdown file that I'll have。Your text and code so here's a basic R markdown document so R markdown is basically markeddown with R code embedded it you can see that what I have here is a basic symbol it indicates that I'm going to start a code chunk so when I have the three back ticks and then the curly braces and then an R and then a closed curly brace that indicates that I'm starting a code chunk so you can see I have three lines of R code here set see。

 I generate some random normal variabless and I just take the mean and then I close this code chunk with three back ticks。



![](img/2d93f7847e8d09b57dcd69ff7684624f_8.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_9.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_10.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_11.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_12.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_13.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_14.png)

And so that so you can see above this shaded area with the code， I've got text。

 so it's the title is my first knitter document， and then I say just a line of text that says this is some text and then I say。

 here's a code chunk and then I start the code chunk。



![](img/2d93f7847e8d09b57dcd69ff7684624f_16.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_17.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_18.png)

So in our studio， you'll have this document opened and you'll have the code chunk and the text chunk there together and the idea is that you want to process the knitter document and create some human readable output is the idea is that you' want to run the R code so that you execute these three lines of R code and then you want to put the output from that R code into embedded in your document and what's the output of this R code。

 well it's only one thing that happens you calculate the mean so it's going to generate the mean and it'll be whatever the mean happens to be for that simulated data set。



![](img/2d93f7847e8d09b57dcd69ff7684624f_20.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_21.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_22.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_23.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_24.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_25.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_26.png)

So it's very easy in our studio， you just push the knit HTML button and it will automatically run everything for you。



![](img/2d93f7847e8d09b57dcd69ff7684624f_28.png)

Theres if you're not using RSt， the way you can do this is you can load the knitter package with the library function。

 you can make sure your working directory is set to wherever the R Markdown document is located。

 typically R Markdown documents will have a capital RMD extension。

 it's not necessary but it's just a good way to identify these types of files。

 you can use the knit to HTML function if you want to create a web page。



![](img/2d93f7847e8d09b57dcd69ff7684624f_30.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_31.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_32.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_33.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_34.png)

As your output and it will automatically process the R Markdown file and run the R code and put the output within the file and then within R if you want to open this in your web browser you can use the browse URL function。

 it will create a new file， sorry the mid to HTML function will take your R markdown document。

 create an HTML file with the same name and then you can open in your web browser。



![](img/2d93f7847e8d09b57dcd69ff7684624f_36.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_37.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_38.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_39.png)

So here's the output that you would get， this is the HTML format output that you would get you can see that there's a title in large text there some regular text。

 the code is kind of in the shaded box and then the output from that code is directly below here you can see the mean is 0。

1089 so that's the output that came from the mean function。



![](img/2d93f7847e8d09b57dcd69ff7684624f_41.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_42.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_43.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_44.png)

So in so what happens here is that knitter takes your original R markdown document。

 we can see on the left here， and it processes it into a regular markdown document and so you can see that one thing that happens is that it takes your code and then it reproduces the code in the regular markdown document。

 but you can see that in the markdown document does one extra piece。

 which is that the result of the code which is down here at the bottom。

 and so the result of evaluating the R code is added to the markdown document after evaluating the R code。



![](img/2d93f7847e8d09b57dcd69ff7684624f_46.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_47.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_48.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_49.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_50.png)

So for a couple of things first all， when when you create the new knitter document in R studio。

 it will populate that document with some kind of generic filler text。

 so the first thing you probably want to do is just delete it because that's not going to be relevant to whatever you want to do。

 most likely code chunks again begin with the three back ticks and the brocurly braces with an R and they you end the code chunk with the three back ticks。



![](img/2d93f7847e8d09b57dcd69ff7684624f_52.png)

All of your R code will go between these markers now you can have more than one code chunk you have as many code chunks as you want so you don't have to put all of the R code within the code chunk。

 but any R code that you do have goes in a code chunk indicated by the three back texts you can have names for your code chunks so you can name them after so immediately active in the curly brace in the R you can put a name it can be anything you want and then you can close it with a curly brace and then。



![](img/2d93f7847e8d09b57dcd69ff7684624f_54.png)

By default， the code in the code chunk will be echoed in the output document。

 So just like in in the H document， you saw that it echoed the code。

 and then it gave you the result of that code By default， all the code chunks。

 you'll be able to see in the document the code that was produced。

