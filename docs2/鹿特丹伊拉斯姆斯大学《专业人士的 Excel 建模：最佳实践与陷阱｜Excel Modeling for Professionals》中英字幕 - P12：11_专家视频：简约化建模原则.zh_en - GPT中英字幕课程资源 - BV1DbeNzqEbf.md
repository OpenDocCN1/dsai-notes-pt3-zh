# 鹿特丹伊拉斯姆斯大学《专业人士的 Excel 建模：最佳实践与陷阱｜Excel Modeling for Professionals》中英字幕 - P12：11_专家视频：简约化建模原则.zh_en - GPT中英字幕课程资源 - BV1DbeNzqEbf

Hello， my name is Arion Dersen， Im a professor in software engineering at Delt University of Technology。

So in teaching is one aspect where I use Excel a lot。



![](img/7e05b0cd76a892009ddb5d0f49024804_1.png)

An honor is I am head of department， so I manage a department of 175 people。

 I'm a member of the management team of the faculty and there' is money involved。

 so we talk about millions of euros that should all be well correctly distributed over all the departments。

That's where we use spreadsheets a lot so we send spreadsheets around and we changed them and tried to understand them so spreadsheets are everywhere as head of department。

Third， I am an engineer， so I teach software engineering。

 we do research in software engineering and we try to help our students become the best software engineers of the world。

That means that we think about good ways for performinging and also good ways of well expressing yourself when trying to create software。

Writing Excel， using Excel， programming， formalizing Excel is another way of programming， and well。

 given my software engineering background， I'm interested in the best ways of doing Excel。

when sharing spreadsheets， the key is that you need to trust the information there。

 so you need to be able to trust that the calculations made and the data presented is actually correct so if the spreadsheets once they become too complex people lose faith in these spreadsheets and then well things go wrong。

Another thing is that in spreadsheets， they can be quite complex and then it becomes easy to make small mistakes and small mistakes can have big consequences。

Yeah， so to me， the most important thing is thinking about the overall design of your spreadsheet。

 So what are the main tabs that you're using and how do they depend on each other。And for me。

 the most important thing is separating clearly the input data that you have from the results that you want to present and the calculations that you need to do in the middle。

As of， for instance， For the grades that I had produced for my students。

There I have a every year I have sort of used the same spreadsheets。

 but I adjust it every year a little bit because change the questions change。

But I try to separate the input as much as possible from the rest so that I can just replace the input and keep the rest the same。

对。A thing that goes wrong is that you have hopefully a well designed spreadsheet。

 but then you need to make some simple changes because well。

 something happens and then it is also easy to make some a hoc changes that sort of compromise the overall clean design of your spreadsheet。

As so， for instance， in one formula， here you have a row and a column and in that column， Well。

 every， every calculation should be the same。 But there's one well。

 row row that is sort of exceptional。And then you can do two things you can do the clean way and making sure that this exceptional case is nicely recognizable in inputs and you structure your spreadsheet correctly or you make one ad hoc change in that column because then the output will be okay。

 but the calculation is so。And for that present spreadsheet， that is no problem probably。

 but then if in the next month you start changing that spreadsheets。

 you lose track of these little changes and slowly everything becomes a mess。

And so that is one change in terms of formulas that well can mess things up。

I think another thing to avoid is well， looking again at the big design。

There should be clear dependencies between the various sheets。

And a thing to avoid our cyclic dependencies， but it is in a way pretty easy to make such cyclic dependencies because in one column in your tap。

 you use spreadsheet in the other tab and there in another column you use that one again and then suddenly your spreadsheet becomes one tangled mess。

 And if you change one tap， it will have effects everywhere in your spreadsheet so。

Try to keep things simple。

![](img/7e05b0cd76a892009ddb5d0f49024804_3.png)