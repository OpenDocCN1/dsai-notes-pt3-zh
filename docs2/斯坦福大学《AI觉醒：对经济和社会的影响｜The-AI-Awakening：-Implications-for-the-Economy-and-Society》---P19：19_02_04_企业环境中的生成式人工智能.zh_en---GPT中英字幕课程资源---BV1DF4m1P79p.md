# 斯坦福大学《AI觉醒：对经济和社会的影响｜The AI Awakening： Implications for the Economy and Society》 - P19：19_02_04_企业环境中的生成式人工智能.zh_en - GPT中英字幕课程资源 - BV1DF4m1P79p

![](img/0e6b6c0d637311775c38805d603e953a_0.png)

Here's where the biggest issue comes and this like kind of leads into my next part Okay in an enterprise context。

 what are you interested in， you're interested in your own data。

 So imagine you're Nike or GM or whatever maybe you have your internal confluence Wiiki and you and you have all of this information about your like codeb or whatever else and what do you want to do you want to create your own custom chat GT right you want to be able to ask questions like hey in GM how do I make you know a particular part of a car or whatever right and。

😊。

![](img/0e6b6c0d637311775c38805d603e953a_2.png)

And right now the answer is GP4 doesn't know it because this is proprietary information。

 the data is like actually does not belong to them。

 so if you ask a question which is very specific to a specific company it's going to probably say I don't know so what do you do So today what people do is they take the relevant data and send it to GPT4。

😊，And then then ask it like here's a bunch of data around my company now I'm going to ask you the question like how do I log into advocus。

 which may be very specific to advos and then it can basically give you the answer。

 Unfortunately the data that you can feed in live is restricted to 32k and that's what's called the context left So the most important thing to know about LLMs is that context length is everything and right now 32K is the highest we've got and only open AI has access to it in a bunch of others and I mean whoever they give access to and pretty much after that the LLM runs out right like it only can get you 32 worth of tokens and that's that So if you have a really big database your big problem then is to find the actual relevant content based on your question and only send that context and that's very hard to do and 322K tokens is roughly 32K words I think it's a little bit more than that but yeah it's okay to assume it's in the thousands of words it's not。

😊，Definitely in tens of millions of words， which is what most people have so what do people do What they do is they actually do a search for the query first。

 So imagine if I said how do I make like some part of a car。

 the first thing you do is actually you do a traditional search for that query on your index meaning on your data find all the relevant documents So similar to a Google search。

 let's say and this is like how you do a Google search you get like say 100 documents back you then take those hundred documents。

 then feed those documents to an LLM and then have that LLM summarized those results so there's a step where you actually basically are restricting your content that you're selling to the LLM to just things that you think are relevant fundamentally that's a little inefficient because it only is as good as the content that you sent it It's very possible that you might not have sent the right data or if it's a confusing question you might not know exactly what to send but this is what people are doing people in the know especially maybe the computer science students here。

😊，We know about this thing called Langcha which is very popular you know and it's already we see funded as well。

 you know it basically enables some of this， it's an open source library it enables this idea of like taking the search query or the chat。

 taking and finding the relevant results， then sending those results to some LLM API。😊。

