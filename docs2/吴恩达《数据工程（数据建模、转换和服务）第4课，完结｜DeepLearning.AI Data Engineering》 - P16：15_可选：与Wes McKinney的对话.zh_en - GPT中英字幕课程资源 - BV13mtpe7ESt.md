# 吴恩达《数据工程（数据建模、转换和服务）第4课，完结｜DeepLearning.AI Data Engineering》 - P16：15_可选：与Wes McKinney的对话.zh_en - GPT中英字幕课程资源 - BV13mtpe7ESt

So for this lesson we have none other than Wes McKinney to join for a chat today。

 so looking forward to discussing pandas as well as I think other data related topics but for the learners who don't know who you are do you want to give a quick intro Sure my name is Wes McKinney I'm the original creator of the Padas project for Python all the way back in 2008 open source the project in 2000 at the end of 2009 and built a open source community around it。

 I wrote the book Python for Data analysis， which is now in its third edition and a lot of people use that book to learn Padas and it become a staple reference textbook for for the ecosystem I've worked on a bunch of other open source projects like Apache Arrow and Ibis which is another Python project and I' been I would call it an open source entrepreneur so I've started a number of companies。

Datapa UA labbs， Vtron data， basically building software that's connected with this new ecosystem of open source data processing and data science tools and yeah I also more recently I invest in data companies and just generally interested in the growth and development of open source data science and making it easier for people to work with data that's super awesome yeah and I think I have the original Pada's book back I think it was 2010 or 2011 or something like that that came out I can't remember the exact date but yeah that was the classic so I guess for the learners out there who are new to pandas what exactly is pandas well Padas is data like a data management or data manipulation toolkit so it helps you load and manipulate data sets in memory and Python so if you have a CSV file or。

CllF or a database， one of the first steps that you to do any kind of data work in Python is that you need to load the data into memory so you can manipulate it as a table or spreadsheetlike object and so pandas provides you something called a data frame which is a tabular data structure that has an API for doing spreadsheetlike operations。

 call operations data cleaning operations and then a lot of functions that help you load data out of data files and external data sources into into pandas data frames there's obviously like a lot of other stuff in the project。

 you can use it to generate plots and to create nicely formatted tables for inserting into publications it's been a very popular tool for doing interactive exploratory data analysis in Python and it's often the first stop on the way to using some other toolkit for doing statistics or machine learning in Python so if you use stats models。

or psyic learn or Tensorflowlow or pytorch often people are using pandas to load the data do some data cleaning and data data manipulation or emerging data sets together and then they export they hand off the data from pandas and they use it in one of those other those other libraries so pandas isn't trying to be an AI or machine learning toolkit it's just helping you work with data Yeah I remember the first time I encountered it I think it was。

2012 or something like that and I needed something was doing feature engineering for machine learning at the time and using Java and they seemed like the libraries back then were just pretty janky and very hard to deal with but then I talked pandas and it felt like all of a sudden my data was the equivalent of clay I could mold it in any possible shape so what inspired you to create pandas though I mean sorry what you guys say？

Yeah， I was going to say it's amazing how much time is spent just like just getting access to data and loading。

 being able to read a CSV file and have it work reliably is a big deal for a lot of people。

It's a big， big deal。Yeah， and I guess kind of going back to you know Circuitca 2008 like what inspired you to create pandas Well I was in my first job I was working for a quantitative hedge fund。

 it was during the great great financial crisis and we were under a lot of pressure to do a lot of exploratory data analysis and research to be able to make decisions faster and to like many of the tools that I was using there was some people using MATLb people were using R there was a lot of Java and C++ but I wasn't really very satisfied with any of the a lot of SQL to we were using Microsoft SQL server and I discovered Python and I found wow Python is really productive nice programming language to program in and but it was missing missing a data toolkit so I started doing some of my research some of my data analysis work in Python and then started building tools for myself just so that I could。

just that I could do my work and I found that I really enjoyed building tools and I started socializing my little data toolkit with my colleagues I didn't even have a name back then it wasn't called pandas or anything like that and I found that my colleagues really liked using it and eventually it got to a critical mass and where it made sense to like hey this might be useful outside of this company like this could really this could have an impact in the open source open source world what did the name come from I was working with a lot of econometricians who were always talking about panel data and that was so that partially motivated the panda and I was also trying to find some kind of an acronym or like a mishmash of letters and words that would evoke the idea of like Python data analysis and so in kind of writing all those things down I was like oh there's pandas occurring here so that's how the name you know got into。

Okay， this is also one of the biggest mysteries biggest questions I've had so that's interesting Yeah and it feels like the import pandas as PD has pretty much been burned into every data person's brain by this point。

 but obviously pandas wasn't always popular what do you think accounted for the rise and success of pandas I mean there was。

There were a number of factors I think in the 2012-2013 era。

 there was an enormous need for people with data science skills。

 and so programming languages where doing data science work was really accessible was an untapped opportunity to expand access to data science and doing it an open source software meant that there was no paywall like he didn't have to buy software。

 he didn't have to buy MATLb to to get access。And so I think the combination of like there being this great need for data skills and data science。

 a lot of new tech companies who were data focused were comfortable using Python and open source software and they were looking for a data toolkit and so they found they found pandas having my book come out Python for data analysis in 2012 also helped because people could pick up that book and say。

 okay I can read this book and learn how to do basic data work in Python and yeah so it was a combination of like the right place in the right time。

 there' being this great need for great need for data scientists and you know I think people starting to be more forward forward thinking about using adopting open source open source software for data work as as compared with with open with a close source software Oh yeah yeah that was a big one like I think you know I kind of consider。

Paands to be。It felt like that was sort of the gateway drug to data science in a lot of ways where data science was taking off。

 but it just made it so much easier like as running a Python meetup， I think。2012。

 2013 or something like that and discussions back then in Python were mainly about web development like data wasn't really take but it was about the inflection point and I think within a year all the talks。

 the meetup were just machine learning and data and panda prominently everything。Yeah。

 because this was like the like the early 2010s was the era of like the original strata conferences so you had like like big data was everywhere。

 everyone， every company in America and in the world was trying to figure out how to do big data。

 like how to do how to become a data company and。And so yeah。

 I think there was definitely like a gap that that needed to be filled in terms of tools and。Yeah。

 I think you Python for a variety of reasons became the mainstream language for data science and machine learning and AI in particular。

 so having Google and Google and Facebook choose Python is as the language for their machine learning frameworks。

 TensorFlow and Pytororch was a big deal in terms of cementing cementing Python as the language to learn and use。

 oh yeah， it's been amazing to see the success of Python so one part of the course that the learners are going to to explore is when is something like panda' is a good fit and when might they want to try a different approach。

Pandice is a good fit when your data is tabular or rectangular。

 or if you have multiple multiple data sets that are tabular that you need to integrate together。

 so it fits that like spreadsheet like or database like you interface of working with table with you know column names and data in those columns you can use。

Pands to create multidimensional pivot tables and more complex complex objects。

 but its strong suit is really really that that tabularular rectangular data。Interesting。

 when might you opt for maybe a different approach to working with data， if datas are really large。

 like they're too large to fit into memory or they strain the limits of what you can work with on your machine or your laptop。

 you might consider using you might consider using some type some type of database ors another there's other data frame libraries out there。

 there's a new Python project called polars which you could try using which is is built for working with much larger datas in Python but most people have pretty modest sized datas and so that for most pandas users that's that's really an issue。

 but when people truly have like these massive hundreds of millions of rows or billions of rows then that's where that starts can start to become。

Start to become an issue。And yeah and there's yeah。

 there's plenty of users who are working with mostly machine learning dataset sets that are like clean and like nice。

 you know， multidimensional arrays， you know multidimensional arrays stored on disk or they might be using something like X arrayray or another you know multidimensional array framework which is built on top of nuPI and there is intended for use with you Pytorrch or Tensorflow and so there may be instances where using pandas is you know not not necessary at all because you can load your machine learning data sets and and be off the off to the races A I think that's really useful for the learners。

I guess a lot of the people taking this course I'm guessing are going to be aspiring data practitioners。

 do you have any advice for people？Looking to get into the field of data， I would say。

 like in addition to learning the data manipulation， loading， cleaning。Integrating。

 merging like the basics of data wrangling， I think becoming proficient at some of the exploratory data analysis skills like plotting visualization。

 looking at the data getting good at using the Jupyter notebook and different features of the Jupyter notebook I think a lot of what helps people be more productive especially when they're just getting started is being able to look at the data and have more feedback and be able to have like a more iterative cycle with with their analysis as opposed to working in a editor tab of VS code and writing a panda script and then running that panda script on the command line so developing a more interactive iterative approach that's based around looking at the data a lot and visualizing it can help you catch your mistakes faster and。

Ultimatelyly master the skills that you need more quickly that's great advice and kind of closing out where do you see the fields of data I guess in the broadest sense and maybe data engineering specifically where do you where do you see these things going over the next few years I mean I think that well continue to see evolution of the tools and the frameworks for Python in particular I think Python will continue to be a mainstream mainstream programming language for data work I think the role of AI assistance like coppit and chat GBT and LLMs in the loop will become more and more natural and something that's there when you need it but doesn't get in your way because you know chatt GBT and other LLMs like they know an enormous amount about pandas because of all the content that's available on the internet that has to do with pandas and so they can be a really powerful tool to help you。

fi out problems or fix errors in your code or come up with new ideas for how to work with your data and so I think that's just yet another tool in the toolbox that's going to increase accessibility and make people a lot a lot more productive so we can automate more of the boring work and spend more of our energy on the more creative and value at kind of model development and data analysis that's awesome。

A great perspective。Ho West thank you very much for your time it's been great chatting with you and yeah thanks again for your contributions to the field I think that your I think Padas is definitely it's a mainstay so thanks for that and everything else you've done too so yeah。

😊。