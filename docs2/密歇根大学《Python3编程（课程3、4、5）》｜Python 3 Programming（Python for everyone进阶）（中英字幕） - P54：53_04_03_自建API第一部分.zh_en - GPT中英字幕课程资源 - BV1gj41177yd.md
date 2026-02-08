# 密歇根大学《Python3编程（课程3、4、5）》｜Python 3 Programming（Python for everyone进阶）（中英字幕） - P54：53_04_03_自建API第一部分.zh_en - GPT中英字幕课程资源 - BV1gj41177yd

![](img/786288bcf8cce3e799a20f6933c612bd_0.png)

![](img/786288bcf8cce3e799a20f6933c612bd_1.png)

Good afternoon， good evening， good morning， I would like to talk about building your own API。

So what is an API well an API is something that typically you access over a web service over a URL that in this case。

 at least runs a Python script and returns data， so you know common APIs or to access the weather or access data from a service。

 the University of Michigan for example has tons of APIs about all the events we have on campus and about all of our internal data today I would like to think through the hypothetical scenario of making an API that says hello world or some other nice message it's not a real scenario you never actually do this in production but from a learning perspective and kind of understanding of how this works of the cloud it's a good starting point。

So let's define some parameters。 Our API is going to get 10，000 requests per day。

 and each request is going to be a kilobit in size。 so pretty small。

 it's actually going to be smaller than a kilobit， but let's just say a kilobit。

And so we've got a couple of decisions we have to make around our API what is our API at its core well。

 it's Python code and you could build this in Flask or you could build this in Genngo which are two Python frameworks or even fast API which is a newer one of those frameworks but I want to do this in the cloud and there's several reasons why I want to do this in the cloud if I build the entire script myself I've got to be responsible for keeping the servers online making sure that Python processes is running 247365 and if I use the cloud to do this。

 it gets a lot easier。