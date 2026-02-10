# 约翰霍普金斯大学数据科学课程5：《可重复研究》｜reproducible-research｜ - P5：4_可重复研究概念和想法第3部分.zh_en - GPT中英字幕课程资源 - BV1E14y1k7nm

One basic idea to kind of as a tool to make a lot of this stuff easier is what's known as literate statistical programming and this comes from the idea of literate programming in computer programs and so the idea is to think of an article or a publication or report as a stream of text and code and so the text is kind of readable by people and the code is readable by computers and then the idea is that the analysis is described in a series of text and code chunks and each kind of code chunk will do something that will load some data or computer results and each text chunk will kind of relay something in a human readable language so there may be presentation code that kind of format tables and figures there's article text that explains what's going on around all this code and the idea is that this stream of of text and code is a literate statistical program or literate statistical analysis and these programs can be weaved to produce human readable documents like PDF。



![](img/b8ff894216cf409e061c465df1011082_1.png)

or HTML web pages and they can be tangled to produce machine readable documents so machine readable code and so the basic idea behind literate programming is that you need a documentation language that's human readable and you need a programming language that's machine readable and so one of the original systems in R that was designed to do this was called Sweve and Sweve uses a documentation language called lateteek and a programming language obviously is R and it was developed by Fritzlech who is a core member of R and it's still maintained by R core and its website is listed here Now there are many limitations to the original Swe system one of which is that is focused primarily on latetech which is not a language documentation language that many。

 many people are familiar with and so it can be difficult to learn this type of markup language if you're not already in the field it lacks a lot of features that kind of people want like caching and multiple plot per page and mixing programming languages。

And so。And it's not as frequently updated or very actively developed and so one of the alternatives that has come up in recent times is something called knitter and the knitter package for R is basically kind of takes a lot of these ideas of litter programming kind of updates some in improves upon them and there are a lot of kind of features that are added on the SweEav original kind of concepts and so it' still knitter still uses R as his programming languages but it allows you to mix of other programming languages in and you can use a variety of documentation languages now you can use latete。

 you can also use something called Markdown and you can use HTML and so knitTter was developed by EhuACia while he was a graduate student at Iowa State and it's become a very popular package for doinglyerate statistical programs。

So just to summarize very briefly， reproducible research I think is an important minimum standard for computationally intensive types of analyses where replication is very difficult or if not impossible we still need quite a bit of infrastructure and tools to kind of create and distribute reproducible documents and beyond what is currently available but that's kind of improving as every day and there are lots of new tools kind of coming on the scene so in the next lecture I'll talk about some of these tools in particular I'll talk about knitIT and just to show how you can produce reproducible documents。



![](img/b8ff894216cf409e061c465df1011082_3.png)