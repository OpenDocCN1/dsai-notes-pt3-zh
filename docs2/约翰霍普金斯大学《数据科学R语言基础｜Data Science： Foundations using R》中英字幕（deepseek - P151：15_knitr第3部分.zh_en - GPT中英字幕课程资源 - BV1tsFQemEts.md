# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P151：15_knitr第3部分.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

![](img/de29ed08a3d0b162efdb4de56247d3f8_0.png)

So how do we create a basic knitter document so I'm going to talk about this in the context of our studio because I think it's the easiest way to do it there are other ways to do this so this is not really exclusive to our studio but it's just I'll just the example that I'll show here will be in our studio so if you click on the new document button on the upper left you'll see there are a variety of options and you can click the R markdown option to。



![](img/de29ed08a3d0b162efdb4de56247d3f8_2.png)

![](img/de29ed08a3d0b162efdb4de56247d3f8_3.png)

![](img/de29ed08a3d0b162efdb4de56247d3f8_4.png)

To create a new markdown file that I'll have。Your text and code So here's a basic R markdown document。

 so R markdown is basically markeddown with R code embedded and you can see that what I have here is a basic symbol it indicates that I'm going to start a code chunk so when I have the three back ticks and then the curly braces and then an R and then a closed curly brace that indicates that I'm starting a code chunk so you can see I have three lines of R code here I got set seat。

 I generate some random normal variablesables and I just take the mean and then I close this code chunk with three back ticks。



![](img/de29ed08a3d0b162efdb4de56247d3f8_6.png)

And so that' so you can see above this shaded area with the code， I've got text。

 so the title is my first knitter document， and then I say just a line of text that says this is some text and then I say。

 here's a code junk and then I start the code chunk。



![](img/de29ed08a3d0b162efdb4de56247d3f8_8.png)

So in our studio， you'll have this document opened and you'll have the code chunk and the text font there together and the idea is that if you want to process the knitter document and create some human readable output is the idea is that you want to run the R code so that you execute these three lines of R code and then you want to put the output from that R code embedded it in your document and what's the output of this R code。

 well it's only one thing that happens you calculate the mean。

 so it's going to generate the mean and it'll be whatever the mean happens to be for that simulated data set。

So it's very easy in our studio， you can just push the knit HTML button and it will automatically run everything for you。



![](img/de29ed08a3d0b162efdb4de56247d3f8_10.png)

There if you're not using RSt， the way you can do this is you can load the knitter package with the library function。

 you can make sure your working directory is set to wherever the R Markdown document is located。

 typically R markdown documents will have a capital RMD extension， it's not necessary。

 but it's just a good way to identify these types of files。

 you can use the knit to HTML function if you want to create a web page。



![](img/de29ed08a3d0b162efdb4de56247d3f8_12.png)

![](img/de29ed08a3d0b162efdb4de56247d3f8_13.png)

As your output and it will automatically process the R Markdown file and run the R code and put the output within the file and then within R if you want to open it this in your web browser you can use the browse URL function。

 it will create a new file， sorry the mid to HTML function will take your R markdown document。

 create an HTML file with the same name and then you can open in your web browser。



![](img/de29ed08a3d0b162efdb4de56247d3f8_15.png)

So here's the output that you would get， this is the HTML format output that you would get you can see that there's a title in large text there some regular text。

 the code is kind of in the shaded box and then the output from that code is directly below here you can see the mean is 0。

1089 so that's the output that came from the mean function。



![](img/de29ed08a3d0b162efdb4de56247d3f8_17.png)

So in what happens here is that knitter takes your original R markdown document。

 we can see on the left here， and it processes it into a regular markdown document and so you can see that one thing that happens is that it takes your code and then it reproduces the code in the regular markdown document。

 but you can see that in the markdown document does one extra piece。

 which is that the result of the code which is down here at the bottom。

 and so the result of evaluating the R code is added to the markdown document after evaluating the R code。



![](img/de29ed08a3d0b162efdb4de56247d3f8_19.png)

![](img/de29ed08a3d0b162efdb4de56247d3f8_20.png)

![](img/de29ed08a3d0b162efdb4de56247d3f8_21.png)

![](img/de29ed08a3d0b162efdb4de56247d3f8_22.png)

So for a couple of things first all， when when you create the new knitter document in our studio。

 it will populate that document with some kind of generic filler text。

 so the first thing you probably want to do is just delete it because that's not going to be relevant to whatever you want to do。

 most likely code chunks again begin with the three back ticks and thecurly braces with an R and they you end the code chunk but the three back ticks。

All of your R code will go between these markers now you can have more than one code chunk you have as many code chunks as you want。

 you don't have to put all of the R code within the code chunk。

 but any R code that you do have goes in a code chunk indicated by the three backts you can have names for your code chunk so you can name them after so immediately after the curly brace in the R you can put a name it can be anything you want and then you can close it with a curly brace and then。

By default， the code in the code chunk will be echoed in the output document。

 So just like in in the HTML document， you saw that it echoed the code。

 and then it gave you the result of that code By default， all the code chunks。

 you'll be able to see in the document the code that was produced。

