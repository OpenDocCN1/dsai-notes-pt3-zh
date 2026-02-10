# 鹿特丹伊拉斯姆斯大学《专业人士的 Excel 建模：最佳实践与陷阱｜Excel Modeling for Professionals》中英字幕 - P7：6_专家视频：常用函数公式的潜在陷阱.zh_en - GPT中英字幕课程资源 - BV1DbeNzqEbf

🎼Okay， hi， I'm Charles Williams。Well， most of the time these days。

 I'm using Excel as a software development platform。

 so I'm working in VBA and C++ writing tools to make people's use of Excel easier。



![](img/f86bcbeebfcdd311d42a0a45512e7ea4_1.png)

It's supposed to be a secret really， no it's not。😊，Well， it's basically fairly simple。

 if you think about a formula， there are things that the formula needs to know before it can do its calculation。

So what Excel does is it looks at every formula as you put it in or as you change it。

And it works out what that formula needs to be able to do its calculations。

 so it picks up all the references， etcter。And it does this for every formula as you enter it。

 so it builds up this chain of dependencies they're called that allow it to work out whatever formula needs。

So then when you make a small change somewhere over here。Excle says， I know what that change affects。

 It changes this formula here and that formula there， because they both refer to it。

 So then it recalculates those formulas。But then wait a minute。

 we've got some other formulas that depend on those formulas。 So I've got to recalculate those。

 So it ripples through recalculating the bitts that it needs to。So I call this smart recalculation。

 because what it does is it means that X only recalculates the bits that it needs to every time you make a change。

Things like volatile functions。Like indirect and offset and random and stuff like that。

That always get recalculated。And so they are not very good from this smart recalculation point of view。

Well， the most wonderful pitfall， of course， is the famous V Lookup pitfall。😊，Which yeah well。

 weve got to go into that one， but if we look up， you know。

 you say you give it a number to look up or something to look up and it scans through this big list of stuff until it finds the answer。

 or maybe it finds the written answer。So that's what it ought to do。

 but unfortunately the fourth argument in V Lookup tells it to do what's called an approximate match。

But this only works if the data is sorted。And of course， 99% of the time your data isn't sorted。

Too bad because it defaults to assuming that it's sorted。So people forget to put it in。

 I forget to put it in sometimes。Ca see， yeah。And then you get the wrong answer。Well。

 I think my favorite wrong thing that people do is build up these mega giant formulas that get longer and longer and longer and bigger and bigger and bigger。

And totally incomprehensible。 You know， you might have understood them when you created them， maybe。

 but you probably got it wrong anyway。 And tomorrow is another day。It's gone。

 You can't remember what that horrible long function does。

So the answer is you've got to split it up into lots of separate cells。

 people think it's more efficient to have everything jammed into one giant formula， but it's not。

 it's actually less efficient。ExL works better if these giant formulas are split down into separate cells。

Yeah， you can find me on my website， which is www。decisionmodels。com。And I have a blog。

 which is hm Anyway， it's the Fast Excel blog because my main software product is called Fast Excel。

🎼And it's a tool that people use for finding out where the calculation of bottlenecks in their spreadsheets are and then working out what they can do about it。



![](img/f86bcbeebfcdd311d42a0a45512e7ea4_3.png)